---
title: 在 EOP 中管理邮件用户
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 定义邮件用户是管理 Exchange Online Protection (EOP) 服务的重要部分。
ms.openlocfilehash: 48d530be17a7e75f6e179a50067b1b9526606cb0
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676712"
---
# <a name="manage-mail-users-in-eop"></a>在 EOP 中管理邮件用户

定义邮件用户是管理 Exchange Online Protection (EOP) 服务的重要部分。在 EOP 中，您可以使用多种方法来管理用户：
  
- 使用目录同步管理邮件用户：如果贵公司在本地 Active Directory 环境中已有用户帐户，您可以将这些帐户同步到 Azure Active Directory (AD)，其中，这些帐户的副本会存储在云中。 将现有用户帐户同步到 Azure Active Directory 时, 可以在 Exchange 管理中心 (EAC) 的 "**收件人**" 窗格中查看这些用户。 建议使用目录同步。 

- 使用 EAC 管理邮件用户：在 EAC 中直接添加和管理邮件用户。 这是添加邮件用户最简单的方式，并且对于一次添加一个用户非常有用。

- 使用远程 Windows PowerShell 管理邮件用户：通过运行远程 Windows PowerShell 添加和管理邮件用户。 此方法可用于添加多个记录并创建脚本。

> [!NOTE]
> 你可以在 Microsoft 365 管理中心添加用户, 但这些用户不能用作邮件收件人。
  
## <a name="before-you-begin"></a>开始之前

- 若要打开 Exchange 管理中心, 请参阅 exchange [Online Protection 中的 exchange 管理中心](../exchange-admin-center-in-exchange-online-protection-eop.md)。

- 您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"用户、联系人和角色组"条目。

- 请注意, 在使用 Exchange Online Protection PowerShell cmdlet 创建邮件用户时, 您可能会遇到限制。

- 本主题中的 PowerShell 命令使用一种批处理方法, 该方法会导致在几分钟内发生传播延迟, 然后才能看到命令的结果。

- 若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection, 请参阅[连接到 Exchange Online Protection PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)。

- 有关可能适用于本主题中的过程的键盘快捷方式的信息, 请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛中寻求帮助。
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a>使用目录同步管理邮件用户

本节提供了有关使用目录同步管理电子邮件用户的信息。
  
> [!NOTE]
> 如果使用目录同步来管理收件人, 您仍可以在 Microsoft 365 管理中心中添加和管理用户, 但不会将其与本地 Active Directory 同步。 这是因为目录同步只能将来自本地 Active Directory 的收件人同步到云。 <br/><br/> 建议使用目录同步来实现以下功能: <br/><br/>• **Outlook 安全发件人和阻止的发件人列表**: 当同步到服务时, 这些列表将优先于服务中的垃圾邮件筛选。 这允许用户在每个用户或每个域的基础上管理他们自己的白名单和黑名单。 <br/><br/>•**基于目录的边缘阻止 (DBEB)**: 有关 DBEB 的详细信息, 请参阅[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。 <br/><br/>•**最终用户垃圾邮件隔离**: 为了访问最终用户垃圾邮件隔离, 最终用户必须具有有效的 Office 365 用户 ID 和密码。 负责保护本地邮箱的 EOP 客户必须是有效的电子邮件用户。 <br/><br/>•**邮件流规则**: 当您使用目录同步时, 您的现有 Active directory 用户和组将自动上载到云, 然后您可以创建目标为特定用户和/或的邮件流规则 (也称为传输规则)。组, 而无需通过 EAC 或 Exchange Online Protection PowerShell 手动添加它们。 请注意， [动态通讯组](https://go.microsoft.com/fwlink/?LinkId=507569)无法通过目录同步进行同步。
  
按[准备进行目录同步](https://go.microsoft.com/fwlink/p/?LinkId=308908)中所述，获取所需权限，并准备进行目录同步。
  
### <a name="to-synchronize-user-directories-with-azure-active-directory-connect-aad-connect"></a>将用户目录与 Azure Active Directory Connect 同步 (AAD 连接)

若要将用户同步到 Azure Active Directory (AAD), 您必须首先**激活目录同步**, 如[激活目录同步](https://go.microsoft.com/fwlink/p/?LinkId=308909)中所述。

接下来是安装和配置本地计算机以运行 AAD 连接 (如果尚不存在, 则需要事先检查)。 [设置 Aad 连接,](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)了解如何设置用户并将帐户从本地部署到使用 AAD 连接的 Azure AD 的方法。

但在执行此操作之前, 请务必确保[满足先决条件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites), 并[选择安装类型](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)。 较早的链接指向快速安装的简短文章。 您还可以在[自定义安装](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)中找到文章, 或在需要时[传递身份验证](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)。

> [!IMPORTANT]
> 当您完成 Azure Active Directory 同步工具配置向导时, 将在 Active Directory 林中创建**MSOL_AD_SYNC**帐户。 此帐户用于读取和同步您的本地 Active Directory 信息。 为了使目录同步正常工作，请确保本地目录同步服务器上的 TCP 443 处于打开状态。

在配置同步之后, 请务必验证 EOP 是否正确同步。 在 EAC 中, 转到 "**收件人** \> " "**联系人**", 并查看从您的本地环境中正确同步的用户列表。

## <a name="use-the-eac-to-manage-mail-users"></a>使用 EAC 管理邮件用户

本节提供有关在 EAC 中直接添加和管理电子邮件用户的信息。
  
### <a name="use-the-eac-to-add-a-mail-user"></a>使用 EAC 添加邮件用户

1. 转到 EAC 中的 "**收件人** \> **联系人**", 然后单击 "**新建 +**", 创建电子邮件用户。

2. 在 "**新建邮件用户**" 页上, 输入用户信息, 包括以下信息: 

   ****

   |**邮件用户属性**|**说明**|
   |:-----|:-----|
   |**“名字” **、“姓名缩写”**** 和“姓氏”****|在相应的框中键入用户的全名。|
   |**显示名称**|键入名称，最多 64 个字符。默认情况下，此框将在“名字”****、“姓名缩写”**** 和“姓氏”**** 框中显示名称（如果有）。显示名称是必填项。|
   |**Alias**|为用户键入唯一的别名，最多 64 个字符。别名为必填项。|
   |**外部电子邮件地址**|键入用户的外部电子邮件地址。|
   |**用户 ID**|键入邮件用户将用来登录到服务的名称。用户登录名由 (@) 符号左侧的用户名和右侧的后缀组成。通常，后缀是用户帐户所在域的域名。|
   |**新密码**|键入邮件用户将用来登录到服务的密码。请确保所提供的密码符合在其中创建用户帐户的域的密码长度、复杂程度和历史要求。|
   |**确认密码**|重新键入密码进行确认。|

3. 单击“保存”**** 创建新电子邮件用户。新用户应显示在用户列表中。

### <a name="use-the-eac-to-edit-or-remove-a-mail-user"></a>使用 EAC 编辑或删除邮件用户

- 在 EAC 中, 转到 "**收件人** \> " "**联系人**"。 在用户列表中, 单击要查看或更改的用户, 然后选择 "**编辑** ![编辑" 图标](../media/ITPro-EAC-EditIcon.gif)以根据需要更新用户设置。 您可以更改用户名、别名或联系人信息，还可以记录有关组织中的用户角色的详细信息。 您还可以选择用户, 然后选择 "**删除** ![删除"](../media/ITPro-EAC-RemoveIcon.gif)图标将其删除。 

## <a name="use-exchange-online-protection-powershell-to-manage-mail-users"></a>使用 Exchange Online Protection PowerShell 管理邮件用户

本部分提供了有关使用远程 Windows PowerShell 添加和管理邮件用户的信息。
  
### <a name="use-eop-powershell-to-add-a-mail-user"></a>使用 EOP PowerShell 添加邮件用户
  
此示例使用 [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser) cmdlet 在 EOP 内为 Jeffrey Zeng 创建了一个启用邮件功能的用户帐户，详细信息如下：
  
- 名是 Jeffrey，姓是 Zeng。

- 名字是 Jeffrey，显示名称是 Jeffrey Zeng。

- 别名是 jeffreyz。

- 外部电子邮件地址是 jzeng@tailspintoys.com。

- Office 365 登录名为 jeffreyz@contoso.onmicrosoft.com。

- 密码为 Pa$$word1。

```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

若要验证这是否有效, 请运行以下命令以显示有关新邮件用户 Jeffrey Zeng 的信息:
  
```Powershell
Get-User -Identity "Jeffrey Zeng"
```

有关语法和参数的详细信息, 请参阅[获取用户](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user)。

### <a name="use-eop-powershell-to-edit-the-properties-of-a-mail-user"></a>使用 EOP PowerShell 编辑邮件用户的属性
  
使用 [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) 和 [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser) cmdlet 查看或更改邮件用户的属性。
  
此示例将设置 Pilar Pinilla 的外部电子邮件地址。
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

此示例将所有邮件用户的"公司"属性设置为 Contoso。
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```
  
若要验证是否有效, 请使用 "[获取-收件人](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)" cmdlet 验证更改。 (请注意, 您可以查看多个邮件联系人的多个属性。)
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List
```

在之前的示例中，所有邮件用户的"公司"属性都设置为 Contoso，请运行以下命令验证更改：
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> 此 cmdlet 使用批处理方法，在显示 cmdlet 结果之前，有几分钟的传播延迟。
  
### <a name="use-eop-powershell-to-remove-a-mail-user"></a>使用 EOP PowerShell 删除邮件用户
  
此示例使用 [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient/remove-eopmailuser) cmdlet 删除用户 Jeffrey Zeng：
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 **验证此操作已生效**
  
若要验证此操作是否有效, 请运行 "[获取-收件人](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient)" cmdlet, 以验证邮件用户是否已不再存在。
  
```Powershell
Get-Recipient Jeffrey | Format-List
```

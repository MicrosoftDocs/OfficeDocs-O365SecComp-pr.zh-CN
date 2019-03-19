---
title: 在 EOP 中管理邮件用户
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 定义邮件用户是管理 Exchange Online Protection (EOP) 服务的重要部分。
ms.openlocfilehash: 9ab4420dd9fcf6c056bc661b5f3646672a89a683
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670637"
---
# <a name="manage-mail-users-in-eop"></a>在 EOP 中管理邮件用户

定义邮件用户是管理 Exchange Online Protection (EOP) 服务的重要部分。在 EOP 中，您可以使用多种方法来管理用户：
  
- 使用目录同步管理邮件用户：如果贵公司在本地 Active Directory 环境中已有用户帐户，您可以将这些帐户同步到 Azure Active Directory (AD)，其中，这些帐户的副本会存储在云中。 将现有用户帐户同步到 Azure Active Directory 时, 可以在 Exchange 管理中心 (EAC) 的 "**收件人**" 窗格中查看这些用户。 建议使用目录同步。 
    
- 使用 EAC 管理邮件用户：在 EAC 中直接添加和管理邮件用户。 这是添加邮件用户最简单的方式，并且对于一次添加一个用户非常有用。
    
- 使用远程 Windows PowerShell 管理邮件用户：通过运行远程 Windows PowerShell 添加和管理邮件用户。 此方法可用于添加多个记录并创建脚本。
    
> [!NOTE]
> 你可以在 Microsoft 365 管理中心添加用户, 但这些用户不能用作邮件收件人。 
  
## <a name="before-you-begin"></a>准备工作

- 本主题中的过程需要特定权限。请参阅每个过程，以了解其权限信息。
    
- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
> [!TIP]
> 遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a>使用目录同步管理邮件用户

本节提供了有关使用目录同步管理电子邮件用户的信息。
  
> [!IMPORTANT]
> 如果使用目录同步来管理收件人, 您仍可以在 Microsoft 365 管理中心中添加和管理用户, 但不会将其与本地 Active directory 同步。 这是因为目录同步只能将来自本地 Active Directory 的收件人同步到云。 
  
> [!TIP]
>  建议使用目录同步, 以便与以下功能配合使用: > **Outlook 安全发件人列表和阻止发件人列表**-当同步到服务时, 这些列表将优先于服务中的垃圾邮件筛选。 这允许用户在每个用户或每个域的基础上管理他们自己的白名单和黑名单。 > **基于目录的边缘阻止 (DBEB)** -有关 DBEB 的详细信息, 请参阅[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。 > **最终用户垃圾邮件隔离**-为了访问最终用户的垃圾邮件隔离, 最终用户必须具有有效的 Office 365 用户 ID 和密码。 负责保护本地邮箱的 EOP 客户必须是有效的电子邮件用户。 > **邮件流规则**-使用目录同步时, 会自动将现有的 Active directory 用户和组上载到云, 然后您可以创建针对特定用户和/或的邮件流规则 (也称为传输规则)。组, 而无需通过 EAC 或 Exchange Online Protection PowerShell 手动添加它们。 请注意， [动态通讯组](https://go.microsoft.com/fwlink/?LinkId=507569)无法通过目录同步进行同步。 
  
 **开始之前**
  
按[准备进行目录同步](https://go.microsoft.com/fwlink/p/?LinkId=308908)中所述，获取所需权限，并准备进行目录同步。
  
### <a name="to-synchronize-user-directories"></a>同步用户目录的步骤

1. 按[激活目录同步](https://go.microsoft.com/fwlink/p/?LinkId=308909)中所述，激活目录同步。
    
2. 按[设置目录同步计算机](http://go.microsoft.com/fwlink/p/?LinkId=308911)中所述，设置您的目录同步计算机。
    
3. 按[使用配置向导同步目录](http://go.microsoft.com/fwlink/?LinkId=308912)中所述，同步目录。
    
    > [!IMPORTANT]
    > 当您完成 Azure Active directory 同步工具配置向导时, 将在 Active Directory 林中创建**MSOL_AD_SYNC**帐户。 此帐户用于读取和同步您的本地 Active Directory 信息。 为了使目录同步正常工作，请确保本地目录同步服务器上的 TCP 443 处于打开状态。 
  
4. 按[激活同步用户](http://go.microsoft.com/fwlink/p/?LinkId=308913)中所述，激活同步用户。
    
5. 按[管理目录同步](http://go.microsoft.com/fwlink/p/?LinkId=308915)中所述，管理目录同步。
    
6. 验证 EOP 是否正确同步。 在 EAC 中, 转到 "**收件人** \> " "**联系人**", 并查看从您的本地环境中正确同步的用户列表。 
    
## <a name="use-the-eac-to-manage-mail-users"></a>使用 EAC 管理邮件用户

本节提供有关在 EAC 中直接添加和管理电子邮件用户的信息。
  
 **开始之前**
  
您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"用户、联系人和角色组"条目。
  
### <a name="to-add-a-mail-user-in-the-eac"></a>在 EAC 中添加邮件用户的步骤

1. 转到 EAC 中的 "**收件人** \> **联系人**", 然后单击 "**新建 +**", 创建电子邮件用户。
    
2. 在 "**新建邮件用户**" 页上, 输入用户信息, 包括以下信息: 
    
   ****

|**邮件用户属性**|**Description**|
|:-----|:-----|
|**“名字” **、“姓名缩写”**** 和“姓氏”**** <br/> |在相应的框中键入用户的全名。  <br/> |
|**显示名称** <br/> |键入名称，最多 64 个字符。默认情况下，此框将在“名字”****、“姓名缩写”**** 和“姓氏”**** 框中显示名称（如果有）。显示名称是必填项。<br/> |
|**Alias** <br/> |为用户键入唯一的别名，最多 64 个字符。别名为必填项。  <br/> |
|**外部电子邮件地址** <br/> |键入用户的外部电子邮件地址。  <br/> |
|**用户 ID** <br/> |键入邮件用户将用来登录到服务的名称。用户登录名由 (@) 符号左侧的用户名和右侧的后缀组成。通常，后缀是用户帐户所在域的域名。  <br/> |
|**新密码** <br/> |键入邮件用户将用来登录到服务的密码。请确保所提供的密码符合在其中创建用户帐户的域的密码长度、复杂程度和历史要求。  <br/> |
|**确认密码** <br/> |重新键入密码进行确认。  <br/> |
   
3. 单击“保存”**** 创建新电子邮件用户。新用户应显示在用户列表中。 
    
### <a name="to-edit-or-remove-a-mail-user-in-the-eac"></a>在 EAC 中编辑或删除邮件用户的步骤

- 在 EAC 中, 转到 "**收件人** \> " "**联系人**"。 在用户列表中, 单击要查看或更改的用户, 然后选择 "**编辑** ![编辑" 图标](../media/ITPro-EAC-EditIcon.gif)以根据需要更新用户设置。 您可以更改用户名、别名或联系人信息，还可以记录有关组织中的用户角色的详细信息。 您还可以选择用户, 然后选择 "**删除**![删除"](../media/ITPro-EAC-RemoveIcon.gif)图标将其删除。 
    
## <a name="use-remote-windows-powershell-to-manage-mail-users"></a>使用远程 Windows PowerShell 管理邮件用户

本部分提供了有关使用远程 Windows PowerShell 添加和管理邮件用户的信息。
  
 **开始之前**
  
- 您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"用户、联系人和角色组"条目。
    
- 请注意，在使用远程 PowerShell cmdlet 创建邮件用户时，您可能会遇到限制。
    
- 此 cmdlet 使用批处理方法，在显示 cmdlet 结果之前，有几分钟的传播延迟。
    
- 要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection，请参阅[使用远程 PowerShell 连接到 Exchange Online Protection](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)。
    
 **使用远程 PowerShell 添加邮件用户**
  
此示例使用 [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) cmdlet 在 EOP 内为 Jeffrey Zeng 创建了一个启用邮件功能的用户帐户，详细信息如下： 
  
- 名是 Jeffrey，姓是 Zeng。
    
- 名字是 Jeffrey，显示名称是 Jeffrey Zeng。
    
- 别名是 jeffreyz。
    
- 外部电子邮件地址是 jzeng@tailspintoys.com。
    
- Office 365 登录名为 jeffreyz@contoso.onmicrosoft.com。
    
- 密码为 Pa$$word1。
    
```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

 **验证此操作已生效**
  
运行 [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) cmdlet，如下所示，以显示有关新邮件用户 Jeffrey Zeng 的信息： 
  
```Powershell
Get-User "Jeffrey Zeng"

```

 **若要使用远程 PowerShell 编辑邮件用户的属性**
  
使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 和 [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) cmdlet 查看或更改邮件用户的属性。 
  
此示例将设置 Pilar Pinilla 的外部电子邮件地址。
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

此示例将所有邮件用户的“公司”属性设置为 Contoso。
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}

```

 **验证此操作已生效**
  
在之前的示例中，我们已经为邮件用户 Pilar Pinella 更改了属性，还可以使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet 来验证这些更改。（请注意，您可以查看多个邮件联系人的多个属性。） 
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List 

```

在之前的示例中，所有邮件用户的"公司"属性都设置为 Contoso，请运行以下命令验证更改：
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> 此 cmdlet 使用批处理方法，在显示 cmdlet 结果之前，有几分钟的传播延迟。 
  
 **使用远程 PowerShell 删除邮件用户**
  
此示例使用 [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) cmdlet 删除用户 Jeffrey Zeng： 
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 **验证此操作已生效**
  
如下所述运行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet：因为该用户已不存在，所以您应该会收到错误邮件。 
  
```Powershell
Get-Recipient Jeffrey | fl
```



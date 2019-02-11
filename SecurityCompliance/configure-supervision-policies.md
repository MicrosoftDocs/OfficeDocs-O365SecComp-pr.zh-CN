---
title: 配置组织的监督策略
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 设置监督审阅策略来捕获员工通信进行审阅。
ms.openlocfilehash: 898ef9951ea20dec1e0cc6c28ad1ed6f9a0ded6e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29768033"
---
# <a name="configure-supervision-policies-for-your-organization"></a>配置组织的监督策略

使用监督策略来捕获员工通信的内部或外部的审阅者的检查。有关监督策略可以帮助您监控您的组织中的通信的详细信息，请参阅[Office 365 中的监督策略](supervision-policies.md)。

> [!NOTE]
> 由监督策略监控的用户必须具有与高级合规性加载项的 Office 365 企业版 E3 许可证或包含在 Office 365 企业 E5 订阅。如果您不具有现有企业 E5 计划，并需要尝试监督，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。
  
请按照下列步骤设置和 Office 365 组织中使用监督：
  
- **步骤 1 （可选）** - [为监督设置组](configure-supervision-policies.md#exampledist)

    开始使用监督之前，确定谁将其通信检查以及谁将执行这些 reviews （英文）。如果您想要开始使用几个用户查看监督的工作方式，则可以跳过现在设置组。

- **步骤 2 （必需）** - [使监督在组织中可用](configure-supervision-policies.md#MakeAvailable)

    将自己添加到监督审阅角色组以便您可以设置策略。已分配该角色的任何人都可以访问下**数据调控**中安全 & 合规中心的**监督**页。如果要审阅的电子邮件位于 Exchange Online，每个审阅者还必须[对 Exchange Online 的远程 PowerShell 访问](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。

- **步骤 3 （可选）** - [配置自定义的敏感信息类型或自定义关键字词典/词典](configure-supervision-policies.md#sensitiveinfo)

    如果您需要监督策略中用于自定义的敏感信息类型或自定义关键字字典，您需要在启动监督向导之前创建它。

- **步骤 4 （必需）** - [设置监督策略](configure-supervision-policies.md#setupsuper)

    在安全 & 合规性中心，您将创建监督策略。这些策略定义的通信将受到您的组织中查看和指定用户应执行 reviews （英文）。Communications 包括电子邮件和 Microsoft 团队通信，以及第三方平台 communications （如 Facebook、 Twitter 等。）

- **步骤 5-（可选）**[测试新监督策略](configure-supervision-policies.md#TestPolicy)

    测试您的监督策略以确保其正常根据需要是确保合规性策略会议您标准的重要组成部分。

- **步骤 6-（可选）**[Outlook 外接程序审阅人不想使用 Office 365 监督仪表板或 OWA 查看监管的通信设置](configure-supervision-policies.md#UseOutlook)

    监督外接程序 Outlook 使审阅者访问监督功能右 Outlook 客户端中，以便他们可以评估并对每个项目进行分类。

<a name="exampledist"> </a>

## <a name="step-1---set-up-groups-for-supervision-optional"></a>步骤 1-设置组的监督 （可选）

 创建监督策略时，您将决定谁将具有检查其通信以及谁将执行这些 reviews （英文）。在策略，您将使用电子邮件地址来标识个人或组的人员。若要简化您的设置，创建组会检查其通信的人员和组将查看这些通信的人员。如果您使用的组，则可能需要几个 — 例如，如果您想要监控的人员，两个不同组之间的通信，或如果您想要指定不打算管理组。有关此工作原理的详细信息，请参阅[示例通讯组](configure-supervision-policies.md#GroupExample)。
  
监督 communications 之间或在组织中的组中，请在 Exchange 管理中心中设置通讯组 (转到**收件人** \> **组**)。有关设置通讯组的详细信息，请参阅[管理通讯组](http://go.microsoft.com/fwlink/?LinkId=613635)
  
> [!NOTE]
> 您可还用于动态通讯组或安全组监督如果您愿意。为了帮助您决定是否这些更好地满足组织需求，请参阅[管理已启用邮件的安全组](http://go.microsoft.com/fwlink/?LinkId=627033)和[管理动态通讯组](http://go.microsoft.com/fwlink/?LinkId=627058)。
  
<a name="GroupExample"> </a>

### <a name="example-distribution-groups"></a>示例通讯组

本示例包含已设置名为 Contoso 财务国际财务组织的通讯组。
  
在 Contoso Financial International 中，必须监督美国经纪人之间的通信抽样。但是，无需监督该组中的合规部主管。对于本例，我们可以创建以下组：
  
|**设置此通讯组**|**组地址（别名）**|**说明**|
|:-----|:-----|:-----|
|所有美国经纪人 | US_Brokers@Contoso.com | 此组包括为 Contoso 工作的所有在美国的经纪人的电子邮件地址。 |
| 所有美国合规部主管 | US_Compliance@Contoso.com  | 此组包括所有美国合规部主管，就职 contoso 电子邮件地址。由于此组的所有美国经纪人子集，因此可以从监督策略到例外合规部主管使用此别名。 |
  
<a name="MakeAvailable"> </a>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a>步骤 2-使监督 （必需） 在组织中可用

为了使安全 & 合规性中心**监督**菜单选项，您必须为分配的监督审阅管理员角色。
  
若要执行此操作，也可以将自己添加为监督审阅角色组的成员，也可以创建新的角色组。
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>向主管审阅角色组添加成员

1. 登录到[https://protection.office.com](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。

2. 在安全 & 合规性中心中，转到**权限**。

3. 选择**监督审阅**角色组，然后单击编辑图标。

4. 在**成员**部分中，添加您要管理您的组织的监督的人员。

### <a name="create-a-new-role-group"></a>创建新的角色组

1. 登录到[https://protection.office.com](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。

2. 在安全 & 合规性中心中，转到**权限**，然后单击添加 (**+**)。

3. 在**角色**部分中，单击添加 (**+**) 和向下的滚动到**监督审阅管理员**。将此角色添加到角色组。

4. 在**成员**部分中，添加您要管理您的组织的监督的人员。

有关角色组和权限的详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>远程 PowerShell 访问启用审阅者 （如果电子邮件位于 Exchange Online）

1. 按照[启用或禁用访问 to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指南。

<a name="sensitiveinfo"> </a>
  
## <a name="step-3---create-custom-sensitive-information-types-or-custom-keyword-dictionaries-optional"></a>步骤 3-创建自定义的敏感信息类型或自定义关键字词典 （可选）

若要选择从现有的自定义的敏感信息类型或自定义关键字词典监督策略向导中的，首先需要创建这些项，如果需要。

### <a name="create-custom-sensitive-information-types"></a>创建自定义的敏感信息类型

1. 在 Office 365 安全性 & 合规性中心中创建新的敏感信息类型。导航到**分类** \> **敏感信息类型**并按照**新敏感信息类型向导**中的步骤。此处，您将：

    - 定义的名称和说明的敏感信息类型
    - 定义邻近、 可信度级别和主模式元素
    - 检查您的选择并创建敏感信息类型

    有关详细信息，请参阅[创建自定义的敏感信息类型](create-a-custom-sensitive-information-type.md)。

### <a name="create-custom-keyword-dictionarylexicon"></a>创建自定义关键字词典/词汇表

1. 使用文本编辑器 （如记事本)，创建一个新文件，其中包含您想要监视监督策略中的关键字术语。确保每个术语是单独占一行和**Unicode/utf-16 (少 Endian)** 格式保存文件。
2. 关键字文件导入使用 PowerShell Office 365 租户。若要连接到 Office 365 PowerShell，请参阅[连接到 Office 365 安全性 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

    您已连接到 Office 365 with PowerShell 后，运行以下命令以导入关键字字典：

    ```
    $fileData = Get-Content "your keyword path and file name" -Encoding Byte -ReadCount 0

    New-DlpKeywordDictionary -Name "Name for your keyword dictionary" -Description "optional description for your keyword dictionary" -FileData $fileData
    ```
    有关详细信息，请参阅[Create 关键字词典](create-a-keyword-dictionary.md)。

3. 在 Office 365 安全性 & 合规性中心中创建新的敏感信息类型。导航到**分类** \> **敏感信息类型**并按照**新敏感信息类型向导**中的步骤。此处，您将：

    - 定义的名称和说明的敏感信息类型
    - 将自定义词典添加为匹配的元素的要求
    - 检查您的选择并创建敏感信息类型

    创建自定义词典词汇表后，您可以查看使用[Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet 配置的关键字或添加和删除术语使用[集 DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet。

    有关详细信息，请参阅[创建自定义的敏感信息类型](create-a-custom-sensitive-information-type.md)。

<a name="setupsuper"> </a>

## <a name="step-4---set-up-a-supervision-policy-required"></a>步骤 4-设置 （必需） 监督策略
  
1. 登录到[https://protection.office.com](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。

2. 在安全 & 合规性中心中，选择**监控**。
  
3. 选择**创建**，然后按照向导设置策略的以下页面。使用向导中，您将：

    - 为策略指定的名称和说明。
    - 选择用户或组监督，包括选择用户或您想要排除的组。
    - 定义监督策略条件。
    - 选择是否您想要包含敏感信息类型。这是您可以在其中选择默认和自定义的敏感信息类型。
    - 定义通信，若要查看的百分比。
    - 选择审阅者的策略。审阅者可以是单个用户或[已启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。
    - 检查您的策略选择并创建策略。

<a name="TestPolicy"> </a>

## <a name="step-5---test-your-supervision-policy-optional"></a>步骤 5-测试 （可选） 您监督策略

创建监督策略后，最好进行测试以确保您定义的条件正在正确强制实施策略。如果您监督策略中包括的敏感信息类型，还可能希望向[测试您的数据丢失防护 (DLP) 策略](create-test-tune-dlp-policy.md)。请按照以下步骤以测试监督策略：

1. 打开电子邮件客户端或 Microsoft 团队作为监管用户登录要用于测试的策略中定义。
2. 发送电子邮件或 Microsoft 团队聊天满足监督策略中已定义的条件。这可以是关键字、 附件大小、 域等。请确保您确定是否太严格或太宽松您配置的条件设置在策略。

    > [!Note]
    > 受到定义的策略的电子邮件以处理几乎可以实时和配置的策略后，立即可以测试。在 Microsoft 团队中的聊天可能需要 24 小时完全处理策略中。 

3. 登录到 Office 365 租户为审阅者监督策略中指定。导航到**监督** > *您自定义策略* > **打开**以查看策略的报告。

<a name="UseOutlook"> </a>

## <a name="step-6---set-up-outlook-add-in-for-reviewers-optional"></a>步骤 6-Set up Outlook 外接程序审阅者 （可选）

要使用 Outlook 而不是使用 Office 365 或在 web 上的 Outlook 中的监督仪表板查看 communications 审阅者必须安装监督外接程序其 Outlook 客户端。

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>步骤 1： 复制监督邮箱的地址

若要安装外接程序 Outlook 桌面程序，您将需要作为监督策略设置的一部分创建的监督邮箱地址。
  
> [!NOTE]
> 如果其他人创建策略，您将需要从原始安装外接程序获得此地址。

 **若要查找的监督邮箱地址**
  
1. 登录到[安全&amp;合规性中心](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。

2. 转到**监督**。

3. 单击收集的通信您想要查看的监督策略。

4. 在策略的详细信息弹出下**监管邮箱**，, 复制地址。<br/>![显示突出显示的监督邮箱地址监督策略的详细信息弹出的监督邮箱部分](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a>步骤 2： 配置 Outlook 桌面访问的监督邮箱

接下来，审阅者将需要运行的几 Exchange Online PowerShell 命令，以便他们可以将 Outlook 连接到监督邮箱。
  
1. 连接到 Exchange Online PowerShell 中。[我该如何做？](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. 运行以下命令，其中*SupervisoryReview{GUID}@domain.onmicrosoft.com*是您在上面的步骤 1 中复制的地址，*用户*是将连接到步骤 3 中的监督邮箱审核者的名称。

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. 等待至少一个小时之后才能接着下面的步骤 3。

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>步骤 3： 创建 Outlook 配置文件连接到监督邮箱

最后一步，将需要审阅者创建的 Outlook 配置文件连接到监督邮箱。

> [!NOTE]
> 若要创建新的 Outlook 配置文件，您将使用 Windows 控制面板中邮件设置。您需要访问这些设置的路径可能取决于您使用 Windows 操作系统 （Windows 7、 Windows 8 或 Windows 10），并安装哪个版本的 Outlook。
  
1. 打开控制面板，并在窗口顶部的**搜索**框中，键入**邮件**。<br/>(不确定如何获取控制面板？请参阅[其中是 Control Panel？](https://support.microsoft.com/help/13764/windows-where-is-control-panel))
  
2. 打开**邮件**应用程序。

3. 在**邮件设置-Outlook**中，单击**显示配置文件**。<br/>![邮件设置的 Outlook 与显示配置文件按钮突出显示的对话框](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. 在**邮件**框中，单击**添加**。然后，在**新的配置文件**中，输入监督邮箱 （例如**监督**） 的名称。<br/>![在配置文件名称框中显示名称监督' 新配置文件对话框](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. 在**将 Outlook 连接到 Office 365**中，单击**连接到不同的帐户**。<br/>![突出显示的连接到不同的帐户链接连接到 Office 365 Outlook 邮件](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. 在**自动帐户设置**中，选择**手动安装或其他服务器类型**，然后单击**下一步**。

7. 在**选择帐户类型**，选择**Office 365**。然后，在**电子邮件地址**框中，输入之前复制监督邮箱的地址。<br/>![在 Outlook 中显示电子邮件地址框中突出显示添加帐户对话框的选择您的帐户类型页面。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. 出现提示时，输入您的 Office 365 凭据。

9. 如果成功，您将看到**监督-\<策略名称\>** 在 Outlook 的文件夹列表视图中列出的文件夹。

## <a name="powershell-reference"></a>PowerShell 参考

如果需要您可以创建和管理使用以下 PowerShell cmdlet 的监督策略：

- [新 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [Get SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [设置 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [删除 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [新 SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [设置 SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [Get SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [Get SupervisoryReviewOverallProgressReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [Get SupervisoryReviewTopCasesReport](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)
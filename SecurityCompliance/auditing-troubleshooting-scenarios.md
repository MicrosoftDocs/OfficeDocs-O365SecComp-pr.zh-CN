---
title: 搜索 Office 365 审核日志以解决常见方案
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
description: 您可以使用 Office 365 审核日志搜索工具来帮助您解决常见问题, 例如调查已损坏的帐户、找出设置邮箱的电子邮件转发的用户, 或者确定外部用户为什么能够成功登录到您的组织.
ms.openlocfilehash: 255fd323ca08dd4ea759648fbe0673f5e5254c22
ms.sourcegitcommit: 1947ad3c0dde9163ba9b6834d8b38bd04b4264a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "36643276"
---
# <a name="search-the-office-365-audit-log-to-troubleshoot-common-scenarios"></a>搜索 Office 365 审核日志以解决常见方案

本文介绍如何使用 Office 365 审核日志搜索工具来帮助您解决常见的支持方案。 这包括使用审核日志执行以下操作:

- 查找用于访问已泄露帐户的计算机的 IP 地址
- 确定为邮箱设置电子邮件转发的发件商
- 确定用户是否已删除其邮箱中的电子邮件项目
- 确定用户是否已创建收件箱规则
- 调查您的组织外的用户成功登录的原因

## <a name="using-the-office-365-audit-log-search-tool"></a>使用 Office 365 审核日志搜索工具

本文中介绍的每个故障排除方案都基于 Office 365 安全与合规中心中的审核日志搜索工具。 本节列出了搜索审核日志所需的权限, 并介绍了访问和运行审核日志搜索的步骤。 每个方案部分都提供了有关如何配置审核日志搜索查询的具体指导, 以及在与搜索条件匹配的审核记录中的详细信息中要查找的内容。

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>使用审核日志搜索工具所需的权限

您必须在 Exchange Online 中向您分配 "仅查看审核日志" 或 "审核日志" 角色, 才能搜索 Office 365 审核日志。 默认情况下, 将这些角色分配给 Exchange 管理中心中 "**权限**" 页上的 "合规性管理" 和 "组织管理" 角色组。 Office 365 和 Microsoft 365 中的全局管理员将自动添加为 Exchange Online 中的 "组织管理" 角色组的成员。 有关详细信息, 请参阅[在 Exchange Online 中管理角色组](https://go.microsoft.com/fwlink/p/?LinkID=730688)。

### <a name="running-audit-log-searches"></a>运行审核日志搜索

本部分介绍创建和运行审核日志搜索的基本操作。 请按照本文中的每个疑难解答方案的起始点, 使用这些说明。 有关详细的分步说明, 请参阅[搜索审核日志](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search)。

1. 转到[https://protection.office.com/unifiedauditlog](https://protection.office.com/unifiedauditlog)并使用你的工作或学校帐户登录。
    
    将显示 "**审核日志搜索**" 页。 
    
    ![配置条件, 然后单击 "搜索" 以运行搜索](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. 您可以配置以下搜索条件。 本文中的每个故障排除方案都建议了有关配置这些字段的具体指导。
    
    a. **活动:** 单击下拉列表以显示您可以搜索的活动。 运行搜索后, 仅显示所选活动的审核记录。 选择 "**显示所有活动的结果**" 将显示符合其他搜索条件的所有活动的结果。 在某些故障排除方案中, 您还需要将此字段留空。
    
    b. "**开始日期**" 和 "**结束日期":** 选择要显示在该时间段内发生的事件的日期和时间范围。 默认情况下, 选择最后七天。 日期和时间以协调通用时间 (UTC) 格式显示。 您可以指定的最大日期范围为90天。

    c. **用户:** 在此框中单击, 然后选择要为其显示搜索结果的一个或多个用户。 您在此框中选择的用户执行的选定活动的审核记录将显示在结果列表中。 将此框保留为空将返回组织中所有用户 (和服务帐户) 的条目。
    
    d. **文件、文件夹或网站:** 键入文件或文件夹名称的部分或全部, 以搜索与包含指定关键字的文件夹文件相关的活动。 您还可以指定文件或文件夹的 URL。 如果使用 URL, 请确保键入完整的 URL 路径, 或者如果只键入 URL 的一部分, 请勿包含任何特殊字符或空格。 将此框保留为空将返回组织中的所有文件和文件夹的条目。 在本文的所有故障排除方案中, 此字段保留为空。
    
5. 单击 "**搜索**" 以使用搜索条件运行搜索。 
    
    搜索结果已加载, 并在几分钟后显示在 "**审核日志搜索**" 页上的 "**结果**" 下。 本文中的每个部分都提供了有关在特定故障排除方案的上下文中查找的事项的指南。

    有关查看、筛选或导出审核日志搜索结果的详细信息, 请参阅:

    - [查看搜索结果](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [筛选搜索结果](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [导出搜索结果](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="find-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>查找用于访问已泄露帐户的计算机的 IP 地址

与任何用户执行的活动对应的 IP 地址包含在大多数审核记录中。 有关所使用的客户端的信息也包含在审核记录中。

下面介绍了如何配置此方案的审核日志搜索查询:

**活动:** 如果与你的案例相关, 请选择要搜索的特定活动。 若要对受损帐户进行故障排除, 请考虑选择 " **Exchange 邮箱活动**" 下的 "**登录到邮箱的用户**" 活动。 这将返回审核记录, 显示登录邮箱时使用的 IP 地址。 否则, 将此字段保留为空, 以返回所有活动的审核记录。 

> [!TIP]
> 将此字段留空将返回**UserLoggedIn**活动, 这是一种 Azure Active Directory 活动, 该活动表明有人登录到 Office 365 用户帐户。 使用搜索结果中的筛选功能显示**UserLoggedIn**审核记录。

"**开始日期**" 和 "**结束日期":** 选择适用于调查的日期范围。

**用户:** 如果您正在调查已泄露的帐户, 请选择其帐户已被泄露的用户。 这将返回该用户帐户执行的活动的审核记录。

**文件、文件夹或网站:** 将此字段留空。

运行搜索后, 每个活动的 IP 地址将显示在搜索结果的 " **ip 地址**" 列中。 单击搜索结果中的记录, 以查看有关弹出页面的更多详细信息。

## <a name="determine-who-set-up-email-forwarding-for-a-mailbox"></a>确定为邮箱设置电子邮件转发的发件商

为邮箱配置电子邮件转发后, 发送到该邮箱的电子邮件将被转发到另一个邮箱。 可以将邮件转发给组织内部或外部的用户。 在邮箱上设置电子邮件转发时, 将使用的基础 Exchange Online cmdlet 设置为 "**邮箱**"。

下面介绍了如何配置此方案的审核日志搜索查询:

**活动:** 将此字段保留为空, 以便搜索将返回所有活动的审核记录。 若要返回与**设置邮箱**cmdlet 相关的任何审核记录, 这是必需的。

"**开始日期**" 和 "**结束日期":** 选择适用于调查的日期范围。

**用户:** 除非您要调查特定用户的电子邮件转发问题, 否则请将此字段留空。 这有助于确定是否为任何用户设置了电子邮件转发。

**文件、文件夹或网站:** 将此字段留空。

运行搜索后, 单击搜索结果页上的 "**筛选结果**"。 在 "**活动**" 列标题下的框中, 键入 "**设置"-"邮箱**", 以便只显示与 "**设置邮箱**" cmdlet 相关的审核记录。

![筛选审核日志搜索的结果](media/emailforwarding1.png)

在这种情况下, 您必须查看每个审核记录的详细信息, 以确定该活动是否与电子邮件转发相关。 单击 "审核记录" 以显示 "**详细**信息" 弹出页面, 然后单击 "**详细信息**"。 下面的屏幕截图和说明突出显示了指示邮箱上设置了电子邮件转发的信息。

![审核记录中的详细信息](media/emailforwarding2.png)

a. 在 " **ObjectId** " 字段中, 将显示设置了电子邮件转发的邮箱的别名。 此邮箱也会显示在搜索结果页中的**项目**列上。

b. 在 "**参数**" 字段中, 值*ForwardingSmtpAddress*表示在邮箱上设置了电子邮件转发。 在此示例中, 将邮件转发到 alpinehouse.onmicrosoft.com 组织外部的电子邮件地址 mike@contoso.com。

c. *DeliverToMailboxAndForward*参数的*True*值指示传递给 sarad@alpinehouse.onmicrosoft.com 的邮件的副本 *, 并*转发到 ForwardingSmtpAddress 指定的电子邮件地址。 ** 参数, 在此示例中为 mike@contoso.com。 如果将*DeliverToMailboxAndForward*参数的值设置为*False*, 则仅将电子邮件转发到*ForwardingSmtpAddress*参数指定的地址。 它不会传递到**ObjectId**字段中指定的邮箱。

d. **UserId**字段指示在**ObjectId**字段中指定的邮箱上设置电子邮件转发的用户。 此用户也显示在搜索结果页上的**用户**列中。 在这种情况下, 似乎邮箱的所有者在其邮箱上设置了电子邮件转发。

如果您确定不应在邮箱上设置电子邮件转发, 则可以通过在 Exchange Online PowerShell 中运行以下命令将其删除:

```
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

有关与电子邮件转发相关的参数的详细信息, 请参阅 "[设置邮箱" 一](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)文。

## <a name="determine-if-a-user-deleted-email-items"></a>确定用户是否已删除电子邮件项目

从2019年1月起, Microsoft 将默认针对所有 Office 365 和 Microsoft 组织启用邮箱审核日志记录。 这意味着邮箱所有者执行的某些操作将会自动记录, 当您在邮箱审核日志中搜索时, 相应的邮箱审核记录将可用。 默认情况下, 邮箱审核启用前, 您必须为组织中的每个用户邮箱手动启用它。 

默认情况下记录的邮箱操作包括邮箱所有者执行的 SoftDelete 和 HardDelete 邮箱操作。 这意味着您可以使用以下步骤在审核日志中搜索与已删除电子邮件项目相关的事件。 有关默认情况下邮箱审核的详细信息, 请参阅[管理邮箱审核](enable-mailbox-auditing.md)。

下面介绍了如何配置此方案的审核日志搜索查询:

**活动:** 在 " **Exchange 邮箱活动**" 下, 选择以下一个或两个活动:

- **删除了 "已删除邮件" 文件夹中的邮件:** 此活动对应于**SoftDelete**邮箱审核操作。 当用户通过选择项目并按**Shift + Delete**永久删除项目时, 也会记录此活动。 在永久删除某个项目后, 用户可以恢复该项目, 直到已删除项目的保留期过期。

- 已**清除邮箱中的邮件:** 此活动对应于**HardDelete**邮箱审核操作。 当用户清除 "可恢复的项目" 文件夹中的项目时, 会记录这种情况。 管理员可以使用安全与合规中心中的内容搜索工具搜索和恢复清除的项目, 直到已删除项目的保留期过期或超过用户邮箱处于保留状态。

"**开始日期**" 和 "**结束日期":** 选择适用于调查的日期范围。

**用户:** 如果您在此字段中选择一个用户, 则审核日志搜索工具将返回您指定的用户所删除的电子邮件项目 (SoftDeleted 或 HardDeleted) 的审核记录。 有时, 删除电子邮件的用户可能不是邮箱所有者。

**文件、文件夹或网站:** 将此字段留空。

运行搜索后, 可以筛选搜索结果, 以显示软删除项目或硬删除项目的审核记录。 单击 "审核记录" 以显示 "**详细**信息" 弹出页面, 然后单击 "**详细信息**"。 在 " **AffectedItems** " 字段中显示有关已删除项目的其他信息, 如主题行和项目的删除位置。 下面的屏幕截图显示软删除项和硬删除项中的**AffectedItems**字段的示例。

**软删除项的 AffectedItems 字段的示例**

![软删除项的审核记录](media/softdeleteditem.png)

**硬删除项的 AffectedItems 字段的示例**

![硬删除的电子邮件项目的审核记录](media/harddeleteditem.png)

### <a name="recover-deleted-email-items"></a>恢复已删除的电子邮件项目

如果已删除项目的保留期尚未过期, 则用户可以恢复软删除的项目。 在 Exchange Online 中, 默认的已删除项目保留期为14天, 但管理员可以将此设置增加到最多30天。 将用户指向 "在[Outlook 中恢复已删除项目或电子邮件" web](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4)文章, 以获取有关恢复已删除项目的说明。

如前所述, 如果已删除项目的保留期尚未过期或邮箱处于保留状态, 则管理员可能能够恢复已删除邮件, 在这种情况下, 将保留项目, 直到保留期间过期。 在运行内容搜索时, 如果搜索结果与搜索查询相匹配, 则会在搜索结果中返回软删除和硬删除的项目文件夹中的项目。 有关运行内容搜索的详细信息, 请参阅[Office 365 中的内容搜索](content-search.md)。

> [!TIP]
> 若要搜索已删除的电子邮件项目, 请在审核记录的 " **AffectedItems** " 字段中搜索显示的全部或部分主题行。

## <a name="determine-if-a-user-created-an-inbox-rule"></a>确定用户是否已创建收件箱规则

当用户为其 Exchange Online 邮箱创建收件箱规则时, 会将相应的审核记录保存到审核日志中。 有关收件箱规则的详细信息, 请参阅:

- [在 web 上的 Outlook 中使用收件箱规则](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [使用规则管理 Outlook 中的电子邮件](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

下面介绍了如何配置此方案的审核日志搜索查询:

**活动:** 在 " **Exchange 邮箱活动**" 下, 选择 " **new-inboxrule 创建/修改/启用/禁用收件箱规则"**。

"**开始日期**" 和 "**结束日期":** 选择适用于调查的日期范围。

**用户:** 除非您要调查特定用户, 否则请将此字段留空。 这可帮助您识别由任何用户设置的新收件箱规则。

**文件、文件夹或网站:** 将此字段留空。

运行搜索后, 此活动的所有审核记录都会显示在搜索结果中。 单击某一审核记录以显示 "**详细**信息" 弹出页面, 然后单击 "**详细信息**"。 有关收件箱规则设置的信息将显示在 "**参数**" 字段中。 下面的屏幕截图和说明突出显示了有关收件箱规则的信息。

![新收件箱规则的审核记录](media/NewInboxRuleRecord.png)

a. 在 " **ObjectId** " 字段中, 将显示收件箱规则的完整名称。 此名称包括用户邮箱的别名 (例如, SaraD) 和收件箱规则的名称 (例如, "移动来自管理员的邮件")。

b. 在 "**参数**" 字段中, 显示收件箱规则的条件。 在此示例中, 条件由*From*参数指定。 为*From*参数定义的值表示收件箱规则作用于由 admin@alpinehouse.onmicrosoft.com 发送的电子邮件。 有关可用于定义收件箱规则条件的参数的完整列表, 请参阅[new-inboxrule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)文章。

c. *MoveToFolder*参数指定收件箱规则的操作。 在此示例中, 从 admin@alpinehouse.onmicrosoft.com 接收的邮件将移至名为*AdminSearch*的文件夹中。 另请参阅[new-inboxrule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)文章, 获取可用于定义收件箱规则操作的参数的完整列表。

d. **UserId**字段指示创建了 " **ObjectId** " 字段中指定的收件箱规则的用户。 此用户也显示在搜索结果页上的**用户**列中。

## <a name="investigate-why-there-was-a-successful-login-by-a-user-outside-your-organization"></a>调查您的组织外的用户成功登录的原因

在查看 Office 365 审核日志中的审核记录时, 您可能会看到指示外部用户通过 Azure Active Directory 进行身份验证并成功登录到组织的记录。 例如, contoso.onmicrosoft.com 中的管理员可能会看到一条审核记录, 表明来自不同的 Office 365 组织 (例如, fabrikam.onmicrosoft.com) 的用户已成功登录 contoso.onmicrosoft.com。 同样, 您可能会看到审核记录, 这些记录表明用户使用 Microsoft 帐户 (MSA) (如 Outlook.com 或 Live.com) 成功登录到您的组织。 在这些情况下, 审核的活动是**用户登录**的。 

此行为是设计的。 如果外部用户尝试访问您组织中的 SharePoint 网站或 OneDrive 位置, 则 azure Active Directory (Azure AD) (Office 365 中的目录服务) 将允许出现一种称为 "*传递身份验证" 的*情况。 当外部用户尝试执行此操作时, 系统会提示他们输入其 Office 365 凭据。 Azure AD 使用凭据对用户进行身份验证, 即仅 Azure AD 验证用户是否为他们所声称的用户。 审核记录中成功登录的指示是对用户进行身份验证的 Azure AD 的结果。 成功的登录并不意味着用户能够访问任何资源或在组织中执行任何其他操作。 它仅指示用户由 Azure AD 进行身份验证。 为了使传递用户能够访问 SharePoint 或 OneDrive 资源, 组织中的用户必须通过向外部用户发送共享邀请或匿名共享链接来明确地与外部用户共享资源。 

> [!NOTE]
> Azure AD 仅允许对*第一方应用程序*(如 SharePoint Online 和 OneDrive for business) 进行传递身份验证。 不允许其他第三方应用程序。

下面的示例和描述了作为传递身份验证结果的**用户登录**事件的审核记录中的相关属性。 单击 "审核记录" 以显示 "**详细**信息" 弹出页面, 然后单击 "**详细信息**"。

![成功传递身份验证的审核记录示例](media/PassThroughAuth1.png)

   a. 此字段指示在组织的 Azure AD 中找不到尝试访问组织中的资源的用户。

   b. 此字段显示尝试访问组织中的资源的外部用户的 UPN。 此外, 还会在审核记录的**user**和**UserId**属性中标识此用户 ID。

   c. **ApplicationId**属性标识触发登录请求的应用程序。 此审核记录中的 ApplicationId 属性中显示的为00000003-0000-0ff1-ce00-000000000000 的值表示 SharePoint Online。 OneDrive for Business 也具有此相同的 ApplicationId。

   d. 这表明传递身份验证成功。 换言之, 用户已成功通过 Azure AD 进行身份验证。 

   e. **RecordType**的值为**15**表示审核的活动 (USERLOGGEDIN) 是 Azure AD 中的安全令牌服务 (STS) 登录事件。

有关 UserLoggedIn 审核记录中显示的其他属性的详细信息, 请参阅[Office 365 管理活动 API 架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#azure-active-directory-base-schema)中与 Azure AD 相关的架构信息。

以下两个示例方案将导致成功的**用户在审核活动中登录**, 这是因为传递身份验证: 

  - 拥有 Microsoft 帐户的用户 (如 SaraD@outlook.com) 尝试访问 fourthcoffee.onmicrosoft.com 中的 OneDrive for Business 帐户中的文档, 其不是 SaraD@outlook.com 的相应来宾用户帐户fourthcoffee.onmicrosoft.com。

  - 在 Office 365 组织中拥有工作或学校帐户的用户 (如 pilarp@fabrikam.onmicrosoft.com) 尝试访问 contoso.onmicrosoft.com 中的 SharePoint 网站, 并且他们不是 pilarp@fabrikam.com 的对应来宾用户帐户。contoso.onmicrosoft.com。


### <a name="tips-for-investigating-successful-logins-resulting-from-pass-through-authentication"></a>有关调查由传递身份验证产生的成功登录的提示

- 在审核日志中搜索由外部用户在 "**已登录**的审核记录" 中标识的活动执行的活动。 在 "**用户**" 框中键入外部用户的 UPN, 并使用与您的方案相关的日期范围。 例如, 您可以使用以下搜索条件创建搜索:

   ![搜索外部用户执行的所有活动](media/PassThroughAuth2.png)

    除了**用户登录**的活动之外, 还可以返回其他审核记录, 这是指您的组织中的用户与外部用户共享资源以及外部用户是否访问、修改或下载了一个文档。已与其共享。

- 搜索 SharePoint 共享活动, 该活动将指示文件与由登录审核记录的**用户**标识的外部用户共享。 有关详细信息, 请参阅[在 Office 365 审核日志中使用共享审核](use-sharing-auditing.md)。

- 导出包含与您的调查相关的记录的审核日志搜索结果, 以便您可以使用 Excel 搜索与外部用户相关的其他活动。 有关详细信息, 请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md)。

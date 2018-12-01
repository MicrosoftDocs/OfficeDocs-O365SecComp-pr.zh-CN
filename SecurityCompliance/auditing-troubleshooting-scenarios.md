---
title: Office 365 搜索审核日志来解决常见方案
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
description: Office 365 审核日志搜索工具可用于帮助您解决常见问题，例如调查受到攻击的帐户或找出用户邮箱的电子邮件转发设置。
ms.openlocfilehash: 930e311712e49214ca2a51e256c29e5f959deab8
ms.sourcegitcommit: c34f1a0d560117153fc9a7b8da8994bc6fc53791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2018
ms.locfileid: "27123895"
---
# <a name="search-the-office-365-audit-log-to-troubleshoot-common-scenarios"></a>Office 365 搜索审核日志来解决常见方案

本文介绍如何使用 Office 365 审核日志搜索工具可帮助您解决常见的支持方案。这包括使用审核记录到：

- 查找用来访问受到攻击的帐户的计算机的 IP 地址
- 确定谁设置邮箱的电子邮件转发
- 确定用户是否删除其邮箱中的电子邮件项目
- 确定用户是否创建收件箱规则

## <a name="using-the-office-365-audit-log-search-tool"></a>使用 Office 365 审核日志搜索工具

本文中介绍的疑难解答方案的每个基于使用 Office 365 安全性和合规性中心的审核日志搜索工具。本节列出了所需搜索审核日志的权限，并介绍访问并运行审核日志搜索的步骤。每个方案一节提供有关如何配置审核日志搜索查询和中与搜索条件匹配的审核记录的详细信息中查找内容的特定指南。

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a>若要使用审核日志搜索工具所需的权限

您必须分配仅查看审核日志或审核日志角色在 Exchange Online 要搜索的 Office 365 审核日志。默认情况下，这些角色分配给 Exchange 管理中心中的**权限**页上合规性管理和组织管理角色组。有关详细信息，请参阅[管理角色组在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688)。

### <a name="running-audit-log-searches"></a>运行审核日志搜索

本节介绍用于创建和运行审核日志搜索的基本知识。这些说明用作本文中的每个疑难解答方案的起始点。有关更详细的分步说明，请参阅[审核日志在 Office 365 安全性和合规性中心的搜索](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search)。

1. 转到 [https://protection.office.com](https://protection.office.com)。
  
2. 使用工作或学校帐户登录到 Office 365。

3. 在安全和合规性中心的左窗格中，单击**搜索和调查** > **审核日志搜索**。
    
    将显示**审核日志搜索**页。 
    
    ![配置条件，然后单击要运行搜索的搜索](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. 您可以配置以下搜索条件。请注意，本文中的每个疑难解答方案将建议配置这些字段的特定指南。
    
    a.**活动**-单击下拉列表以显示您可以搜索活动。运行搜索后，将显示仅所选活动的审核记录。选择**显示所有活动的结果**将显示满足其他搜索条件的所有活动的结果。您还需要将此字段留空某些疑难解答方案。
    
    b.**开始日期**和**结束日期**-选择要显示在该时间段内发生的事件日期和时间范围。默认情况下，选中最近七天。以协调世界时 (UTC) 格式显示日期和时间。您可以指定的最大的日期范围是 90 天。

    c.**用户**-在此框，然后选择一个或多个用户的单击以显示搜索结果。通过在此框中选择的用户执行所选活动审核记录显示在结果列表中。将此框保留为空返回组织中的所有用户 （和服务帐户） 的条目。
    
    d.**文件、 文件夹或网站**-键入一些或全部文件或文件夹名称到文件夹包含指定的关键字的文件相关的活动搜索。您还可以指定文件或文件夹的 URL。如果您使用的 URL，确保类型的完整的 URL 路径或如果您只需键入 URL 的任何部分不包括任何特殊字符或空格。将此框保留为空返回组织中的所有文件和文件夹的条目。请注意，此字段留空中所有的疑难解答方案本文中。
    
5. 单击**搜索**以运行搜索使用您的搜索条件。 
    
    加载搜索结果，并在片刻后上所显示在**结果**下**审核日志搜索**页。每以下各节将提供有关要查找特定的疑难解答方案事项指南。

    有关查看、 筛选或导出审核日志搜索结果的详细信息，请参阅：

    - [查看搜索结果](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [筛选搜索结果](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [导出搜索结果](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="finding-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a>查找用来访问受到攻击的帐户的计算机的 IP 地址

大多数审计记录中包含对应于执行的任何用户活动的 IP 地址。审核记录，也包含有关使用的客户端的信息。

下面是如何配置此方案的审核日志搜索查询：

**活动**-如果您的案例相关，选择要搜索的特定活动。对于疑难解答受到攻击的帐户，请考虑选择在**Exchange 邮箱活动**下的**用户登录到邮箱**活动。这将返回审核记录显示登录到邮箱时使用的 IP 地址。否则，将此字段留空以便返回所有活动的审核记录。 

> [!TIP]
> 将此字段留空将返回**UserLoggedIn**活动，这是 Azure Active Directory 活动指示某人已登录到 Office 365 用户帐户。使用筛选搜索结果中显示**UserLoggedIn**审核记录。

**开始日期**和**结束日期**-选择一个日期范围，适用于您的调查。

**用户**-如果您正在调查受到攻击的帐户，选择其帐户被泄露的用户。这将返回活动由该用户帐户执行审核记录。

**文件、 文件夹或网站**-离开此字段留空。

运行搜索后，在搜索结果**IP 地址**列中均显示每个活动的 IP 地址。单击弹出页上查看更多详细的信息在搜索结果中的记录。

## <a name="determining-who-set-up-email-forwarding-for-a-mailbox"></a>确定谁设置邮箱的电子邮件转发

对邮箱配置邮件转发时, 发送到邮箱的电子邮件转发到另一个邮箱。可以将邮件转发到内部或外部组织的用户。邮箱上设置电子邮件转发，使用基础 Exchange Online cmdlet 时**设置邮箱**。

下面是如何配置此方案的审核日志搜索查询：

**活动**-离开此字段留空以便搜索返回的所有活动的审核记录。这是所需返回任何审核记录与**Set-mailbox** cmdlet。

**开始日期**和**结束日期**-选择一个日期范围，适用于您的调查。

**用户**-除非正在研究转接问题特定用户的电子邮件，则将此字段留空。这将帮助您确定如果电子邮件转发已设置为任何用户。

**文件、 文件夹或网站**-离开此字段留空。

运行搜索后，单击搜索结果页上的**筛选结果**。在**活动**列标题下框中，键入**Set-mailbox** ，以便显示仅与**Set-mailbox** cmdlet 相关的审核记录。

![审核日志搜索的结果进行筛选](media/emailforwarding1.png)

此时，您需要查看每个审计记录，以确定是否与活动电子邮件转发的详细信息。单击显示**详细信息**弹出页的审核记录，然后单击**详细信息**。以下屏幕截图和说明亮点邮箱设置指示电子邮件转发的信息。

![审核记录的详细的信息](media/emailforwarding2.png)

a.在**ObjectId**字段中，设置电子邮件转发的邮箱的别名上显示。在**项目**列中的搜索结果页上，还会显示此邮箱。

b.在**参数**字段中， *ForwardingSmtpAddress*的值指示已邮箱上设置电子邮件转发。本示例中，邮件被转发到电子邮件地址 mike@contoso.com，即 alpinehouse.onmicrosoft.com 组织外部。

*DeliverToMailboxAndForward*参数 c. *True*值指示一份邮件传递到 sarad@alpinehouse.onmicrosoft.com*和*被转接至*ForwardingSmtpAddress 由指定的电子邮件地址*参数，它在本例中为 mike@contoso.com。如果*DeliverToMailboxAndForward*参数的值设置为*False*，然后电子邮件仅转发到由*ForwardingSmtpAddress*参数指定的地址中。未送达**ObjectId**字段中指定的邮箱。

d. **UserId**字段指示在**ObjectId**字段字段指定的邮箱设置电子邮件转发的用户。在搜索结果页上的**用户**列中还显示该用户。在这种情况下，似乎邮箱的所有者将其邮箱上设置电子邮件转发。

如果您确定，不应在邮箱上设置电子邮件转发，您可以通过在 Exchange Online PowerShell 中运行以下命令将其删除：

```
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

请参阅[Set-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)文章有关相关电子邮件转发的参数的详细信息。

## <a name="determining-if-a-user-deleted-email-items"></a>确定用户是否删除电子邮件项目

删除有关的审核日志记录之前电子邮件项目保存到 Office 365 审核日志，必须为在组织中每个用户邮箱启用邮箱审核。此外，SoftDelete 和 HardDelete 邮箱操作必须启用审核。有关说明，请参阅[启用邮箱审核 Office 365 中](enable-mailbox-auditing.md)。如果用户已启用邮箱审核，使用以下步骤来搜索与已删除电子邮件项相关的事件的审核日志。

下面是如何配置此方案的审核日志搜索查询：

**活动**-在下**Exchange 邮箱活动**，选择一个或两个以下活动：

- **删除已删除邮件文件夹的邮件**-此活动对应于**SoftDelete**邮箱审核操作。当用户选择并按**Shift + Delete**中永久删除项目时，也会记录此活动。永久删除项目后，用户可以将其恢复已删除的邮件保留期限过期之前。

- **来自邮箱 Purged 邮件**-此活动对应于**HardDelete**邮箱审核操作。当用户清除可恢复邮件文件夹中的项时，这将记录。管理员可以使用 Office 365 安全性和合规性中心的内容搜索工具搜索和用户的邮箱恢复清除项目之前已删除的邮件保留期到期或更长时间如果处于保留状态。

**开始日期**和**结束日期**-选择一个日期范围，适用于您的调查。

**用户**-如果在此字段中选择一个用户，审核日志搜索工具将返回已删除 （带有 SoftDeleted 或 HardDeleted） 通过指定的用户的电子邮件项目的审核的记录。在某些情况下，删除电子邮件的用户可能不是邮箱所有者。

**文件、 文件夹或网站**-离开此字段留空。

运行搜索后，您可以筛选搜索结果显示审核记录软删除项目或硬已删除邮件。单击显示**详细信息**弹出页的审核记录，然后单击**详细信息**。有关已删除项，如主题行和时已删除的项的位置的其他信息显示在**AffectedItems**域。以下屏幕截图显示**AffectedItems**字段的示例从软删除项目和硬删除项目。

**软删除项目的 AffectedItems 字段示例**

![软删除项的审核记录](media/softdeleteditem.png)

**AffectedItems 硬删除项的字段的示例**

![硬删除电子邮件项的审核记录](media/harddeleteditem.png)

### <a name="recovering-deleted-email-items"></a>恢复已删除的电子邮件项目

如果未过期的已删除的邮件保留期，用户可以恢复软删除项目。在 Exchange Online 中，默认删除邮件保留期 14 天，但管理员可以增加此设置为 30 天内的最大值。用户指向说明恢复已删除项目的[恢复已删除的项目或 Outlook Web App 中的电子邮件](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4)文章。

如前所述，管理员可能无法恢复硬已删除邮件，如果已删除的邮件保留期限未过期或当邮箱位于保留，在这种情况下将保留项目，直到保留持续时间过期。当您运行内容的搜索时，如果它们匹配搜索查询在搜索结果中返回软删除和硬删除可恢复邮件文件夹中的项。有关运行内容搜索的详细信息，请参阅[Office 365 中的内容搜索](content-search.md)。

> [!TIP]
> 若要搜索已删除电子邮件项目，搜索审核记录中的**AffectedItems**字段中显示的主题行的全部或部分。

## <a name="determining-if-a-user-created-an-inbox-rule"></a>确定创建收件箱规则的用户

当用户创建其 Exchange Online 邮箱的收件箱规则时，则相应的审核记录将保存到审核日志。有关收件箱规则的详细信息，请参阅：

- [在 web 上的 Outlook 中使用收件箱规则](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [使用规则来管理在 Outlook 中的电子邮件](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

下面是如何配置此方案的审核日志搜索查询：

**活动**-在**Exchange 邮箱活动**，选择下**New-inboxrule 创建/修改/启用/禁用收件箱规则**。

**开始日期**和**结束日期**-选择一个日期范围，适用于您的调查。

**用户**-除非正在研究特定用户，则将此字段留空。这将帮助您确定新设置的任何用户的收件箱规则。

**文件、 文件夹或网站**-离开此字段留空。

运行搜索后，在搜索结果中显示此活动任何审核记录。单击显示**详细信息**弹出页的审核记录，然后单击**详细信息**。在**参数**字段显示收件箱规则设置的信息。以下屏幕截图和说明突出显示收件箱规则的信息。

![新的收件箱规则的审核记录](media/NewInboxRuleRecord.png)

答： 在**ObjectId**字段中，显示收件箱规则的完整名称。此名称包括用户的邮箱 (例如，SaraD) 的别名和收件箱规则 （例如，"移动邮件管理员从"） 的名称。

b.在**参数**字段中，将显示收件箱规则的条件。本示例中，*从*参数指定的条件。*From*参数为定义的值指示收件箱规则对 admin@alpinehouse.onmicrosoft.com 通过发送电子邮件。可以使用定义的收件箱规则的条件的参数的完整列表，请参阅[New-inboxrule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)文章。

c. *MoveToFolder*参数指定收件箱规则; 的操作本示例中，从 admin@alpinehouse.onmicrosoft.com 接收的消息将移动到名为*AdminSearch*的文件夹中。另请参阅[New-inboxrule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)文章的完整列表可以使用定义的收件箱规则操作的参数。

d.**用户 Id**字段指示创建**ObjectId**字段中指定的收件箱规则的用户。在搜索结果页上的**用户**列中还显示该用户。
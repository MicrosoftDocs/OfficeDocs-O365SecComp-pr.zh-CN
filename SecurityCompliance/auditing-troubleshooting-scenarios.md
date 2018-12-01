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
# <a name="search-the-office-365-audit-log-to-troubleshoot-common-scenarios"></a><span data-ttu-id="1ff18-103">Office 365 搜索审核日志来解决常见方案</span><span class="sxs-lookup"><span data-stu-id="1ff18-103">Search the Office 365 audit log to troubleshoot common scenarios</span></span>

<span data-ttu-id="1ff18-p101">本文介绍如何使用 Office 365 审核日志搜索工具可帮助您解决常见的支持方案。这包括使用审核记录到：</span><span class="sxs-lookup"><span data-stu-id="1ff18-p101">This article describes how to use the Office 365 audit log search tool to help you troubleshoot common support scenarios. This includes using the audit log to:</span></span>

- <span data-ttu-id="1ff18-106">查找用来访问受到攻击的帐户的计算机的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="1ff18-106">Find the IP address of the computer used to access a compromised account</span></span>
- <span data-ttu-id="1ff18-107">确定谁设置邮箱的电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="1ff18-107">Determine who set up email forwarding for a mailbox</span></span>
- <span data-ttu-id="1ff18-108">确定用户是否删除其邮箱中的电子邮件项目</span><span class="sxs-lookup"><span data-stu-id="1ff18-108">Determine if a user deleted email items in their mailbox</span></span>
- <span data-ttu-id="1ff18-109">确定用户是否创建收件箱规则</span><span class="sxs-lookup"><span data-stu-id="1ff18-109">Determine if a user created an inbox rule</span></span>

## <a name="using-the-office-365-audit-log-search-tool"></a><span data-ttu-id="1ff18-110">使用 Office 365 审核日志搜索工具</span><span class="sxs-lookup"><span data-stu-id="1ff18-110">Using the Office 365 audit log search tool</span></span>

<span data-ttu-id="1ff18-p102">本文中介绍的疑难解答方案的每个基于使用 Office 365 安全性和合规性中心的审核日志搜索工具。本节列出了所需搜索审核日志的权限，并介绍访问并运行审核日志搜索的步骤。每个方案一节提供有关如何配置审核日志搜索查询和中与搜索条件匹配的审核记录的详细信息中查找内容的特定指南。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p102">Each of the troubleshooting scenarios described in this article are based on using the audit log search tool in the Office 365 Security & Compliance Center. This section lists the permissions required to search the audit log and describes the steps to access and run audit log searches. Each scenario section provides specific guidance about how to configure an audit log search query and what to look for in the detailed information in the audit records that match the search criteria.</span></span>

### <a name="permissions-required-to-use-the-audit-log-search-tool"></a><span data-ttu-id="1ff18-114">若要使用审核日志搜索工具所需的权限</span><span class="sxs-lookup"><span data-stu-id="1ff18-114">Permissions required to use the audit log search tool</span></span>

<span data-ttu-id="1ff18-p103">您必须分配仅查看审核日志或审核日志角色在 Exchange Online 要搜索的 Office 365 审核日志。默认情况下，这些角色分配给 Exchange 管理中心中的**权限**页上合规性管理和组织管理角色组。有关详细信息，请参阅[管理角色组在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688)。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p103">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log. By default, these roles are assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. For more information, see [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).</span></span>

### <a name="running-audit-log-searches"></a><span data-ttu-id="1ff18-118">运行审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="1ff18-118">Running audit log searches</span></span>

<span data-ttu-id="1ff18-p104">本节介绍用于创建和运行审核日志搜索的基本知识。这些说明用作本文中的每个疑难解答方案的起始点。有关更详细的分步说明，请参阅[审核日志在 Office 365 安全性和合规性中心的搜索](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search)。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p104">This section describes the basics for creating and running audit log searches. Use these instructions as a starting point for each troubleshooting scenario in this article. For more detailed step-by-step instructions, see [Search the audit log in the Office 365 Security & Compliance Center ](search-the-audit-log-in-security-and-compliance.md#step-1-run-an-audit-log-search).</span></span>

1. <span data-ttu-id="1ff18-122">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="1ff18-122">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="1ff18-123">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1ff18-123">Sign in to Office 365 using your work or school account.</span></span>

3. <span data-ttu-id="1ff18-124">在安全和合规性中心的左窗格中，单击**搜索和调查** > **审核日志搜索**。</span><span class="sxs-lookup"><span data-stu-id="1ff18-124">In the left pane of the Security & Compliance Center, click **Search & investigation** > **Audit log search**.</span></span>
    
    <span data-ttu-id="1ff18-125">将显示**审核日志搜索**页。</span><span class="sxs-lookup"><span data-stu-id="1ff18-125">The **Audit log search** page is displayed.</span></span> 
    
    ![配置条件，然后单击要运行搜索的搜索](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
4. <span data-ttu-id="1ff18-p105">您可以配置以下搜索条件。请注意，本文中的每个疑难解答方案将建议配置这些字段的特定指南。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p105">You can configure the following search criteria. Note that each troubleshooting scenario in this article will recommend specific guidance for configuring these fields.</span></span>
    
    <span data-ttu-id="1ff18-p106">a.**活动**-单击下拉列表以显示您可以搜索活动。运行搜索后，将显示仅所选活动的审核记录。选择**显示所有活动的结果**将显示满足其他搜索条件的所有活动的结果。您还需要将此字段留空某些疑难解答方案。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p106">a. **Activities** - Click the drop-down list to display the activities that you can search for. After you run the search, only the audit records for the selected activities are displayed. Selecting **Show results for all activities** will display results for all activities that meet the other search criteria. You'll also have to leave this field blank in some of the troubleshooting scenarios.</span></span>
    
    <span data-ttu-id="1ff18-p107">b.**开始日期**和**结束日期**-选择要显示在该时间段内发生的事件日期和时间范围。默认情况下，选中最近七天。以协调世界时 (UTC) 格式显示日期和时间。您可以指定的最大的日期范围是 90 天。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p107">b. **Start date** and **End date** - Select a date and time range to display the events that occurred within that period. The last seven days are selected by default. The date and time are presented in Coordinated Universal Time (UTC) format. The maximum date range that you can specify is 90 days.</span></span>

    <span data-ttu-id="1ff18-p108">c.**用户**-在此框，然后选择一个或多个用户的单击以显示搜索结果。通过在此框中选择的用户执行所选活动审核记录显示在结果列表中。将此框保留为空返回组织中的所有用户 （和服务帐户） 的条目。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p108">c. **Users** - Click in this box and then select one or more users to display search results for. Audit records for the selected activity performed by the users you select in this box are displayed in the list of results. Leave this box blank to return entries for all users (and service accounts) in your organization.</span></span>
    
    <span data-ttu-id="1ff18-p109">d.**文件、 文件夹或网站**-键入一些或全部文件或文件夹名称到文件夹包含指定的关键字的文件相关的活动搜索。您还可以指定文件或文件夹的 URL。如果您使用的 URL，确保类型的完整的 URL 路径或如果您只需键入 URL 的任何部分不包括任何特殊字符或空格。将此框保留为空返回组织中的所有文件和文件夹的条目。请注意，此字段留空中所有的疑难解答方案本文中。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p109">d. **File, folder, or site** - Type some or all of a file or folder name to search for activity related to the file of folder that contains the specified keyword. You can also specify a URL of a file or folder. If you use a URL, be sure the type the full URL path or if you just type a portion of the URL, don't include any special characters or spaces. Leave this box blank to return entries for all files and folders in your organization. Note that this field is left blank in all the troubleshooting scenarios in this article.</span></span>
    
5. <span data-ttu-id="1ff18-149">单击**搜索**以运行搜索使用您的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="1ff18-149">Click **Search** to run the search using your search criteria.</span></span> 
    
    <span data-ttu-id="1ff18-p110">加载搜索结果，并在片刻后上所显示在**结果**下**审核日志搜索**页。每以下各节将提供有关要查找特定的疑难解答方案事项指南。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p110">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page. Each to the following sections will provide guidance about things to look for the specific troubleshooting scenario.</span></span>

    <span data-ttu-id="1ff18-152">有关查看、 筛选或导出审核日志搜索结果的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="1ff18-152">For more information about viewing, filtering, or exporting audit log search results, see:</span></span>

    - [<span data-ttu-id="1ff18-153">查看搜索结果</span><span class="sxs-lookup"><span data-stu-id="1ff18-153">View search results</span></span>](search-the-audit-log-in-security-and-compliance.md#step-2-view-the-search-results)
    - [<span data-ttu-id="1ff18-154">筛选搜索结果</span><span class="sxs-lookup"><span data-stu-id="1ff18-154">Filter search results</span></span>](search-the-audit-log-in-security-and-compliance.md#step-3-filter-the-search-results)
    - [<span data-ttu-id="1ff18-155">导出搜索结果</span><span class="sxs-lookup"><span data-stu-id="1ff18-155">Export search results</span></span>](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)

## <a name="finding-the-ip-address-of-the-computer-used-to-access-a-compromised-account"></a><span data-ttu-id="1ff18-156">查找用来访问受到攻击的帐户的计算机的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="1ff18-156">Finding the IP address of the computer used to access a compromised account</span></span>

<span data-ttu-id="1ff18-p111">大多数审计记录中包含对应于执行的任何用户活动的 IP 地址。审核记录，也包含有关使用的客户端的信息。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p111">The IP address corresponding to an activity performed by any user is included in most audit records. Information about the client used is also included in the audit record.</span></span>

<span data-ttu-id="1ff18-159">下面是如何配置此方案的审核日志搜索查询：</span><span class="sxs-lookup"><span data-stu-id="1ff18-159">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="1ff18-p112">**活动**-如果您的案例相关，选择要搜索的特定活动。对于疑难解答受到攻击的帐户，请考虑选择在**Exchange 邮箱活动**下的**用户登录到邮箱**活动。这将返回审核记录显示登录到邮箱时使用的 IP 地址。否则，将此字段留空以便返回所有活动的审核记录。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p112">**Activities** - If relevant to your case, select a specific activity to search for. For troubleshooting compromised accounts, consider selecting the **User signed in to mailbox** activity under **Exchange mailbox activities**. This will return auditing records showing the IP address that was use when signing in to the mailbox. Otherwise, leave this field blank to return audit records for all activities.</span></span> 

> [!TIP]
> <span data-ttu-id="1ff18-p113">将此字段留空将返回**UserLoggedIn**活动，这是 Azure Active Directory 活动指示某人已登录到 Office 365 用户帐户。使用筛选搜索结果中显示**UserLoggedIn**审核记录。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p113">Leaving this field blank will  return **UserLoggedIn** activities, which is an Azure Active Directory activity that indicates that someone has signed in to an Office 365 user account. Use filtering in the search results to display the **UserLoggedIn** audit records.</span></span>

<span data-ttu-id="1ff18-166">**开始日期**和**结束日期**-选择一个日期范围，适用于您的调查。</span><span class="sxs-lookup"><span data-stu-id="1ff18-166">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="1ff18-p114">**用户**-如果您正在调查受到攻击的帐户，选择其帐户被泄露的用户。这将返回活动由该用户帐户执行审核记录。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p114">**Users** - If you're investigating a compromised account, select the user whose account was compromised. This will return audit records for activities performed by that user account.</span></span>

<span data-ttu-id="1ff18-169">**文件、 文件夹或网站**-离开此字段留空。</span><span class="sxs-lookup"><span data-stu-id="1ff18-169">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="1ff18-p115">运行搜索后，在搜索结果**IP 地址**列中均显示每个活动的 IP 地址。单击弹出页上查看更多详细的信息在搜索结果中的记录。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p115">After you run the search, the IP address for each activity is displayed in the **IP address** column in the search results. Click the record in the search results to view more detailed information on the flyout page.</span></span>

## <a name="determining-who-set-up-email-forwarding-for-a-mailbox"></a><span data-ttu-id="1ff18-172">确定谁设置邮箱的电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="1ff18-172">Determining who set up email forwarding for a mailbox</span></span>

<span data-ttu-id="1ff18-p116">对邮箱配置邮件转发时, 发送到邮箱的电子邮件转发到另一个邮箱。可以将邮件转发到内部或外部组织的用户。邮箱上设置电子邮件转发，使用基础 Exchange Online cmdlet 时**设置邮箱**。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p116">When email forwarding is configured for a mailbox, email messages that are sent to the mailbox are forwarded to another mailbox. Messages can be forwarded to users inside or outside of your organization. When email forwarding is set up on a mailbox, the underlying Exchange Online cmdlet that's used is **Set-Mailbox**.</span></span>

<span data-ttu-id="1ff18-176">下面是如何配置此方案的审核日志搜索查询：</span><span class="sxs-lookup"><span data-stu-id="1ff18-176">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="1ff18-p117">**活动**-离开此字段留空以便搜索返回的所有活动的审核记录。这是所需返回任何审核记录与**Set-mailbox** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p117">**Activities** - Leave this field blank so that the search returns audit records for all activities. This is necessary to return any audit records related to the **Set-Mailbox** cmdlet.</span></span>

<span data-ttu-id="1ff18-179">**开始日期**和**结束日期**-选择一个日期范围，适用于您的调查。</span><span class="sxs-lookup"><span data-stu-id="1ff18-179">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="1ff18-p118">**用户**-除非正在研究转接问题特定用户的电子邮件，则将此字段留空。这将帮助您确定如果电子邮件转发已设置为任何用户。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p118">**Users** - Unless you're investigating a email forwarding issue for a specific user, leave this field blank. This will help you identify if email forwarding was set up for any user.</span></span>

<span data-ttu-id="1ff18-182">**文件、 文件夹或网站**-离开此字段留空。</span><span class="sxs-lookup"><span data-stu-id="1ff18-182">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="1ff18-p119">运行搜索后，单击搜索结果页上的**筛选结果**。在**活动**列标题下框中，键入**Set-mailbox** ，以便显示仅与**Set-mailbox** cmdlet 相关的审核记录。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p119">After you run the search, click **Filter results** on the search results page. In the box under **Activity** column header, type **Set-Mailbox** so that only audit records related to the **Set-Mailbox** cmdlet are displayed.</span></span>

![审核日志搜索的结果进行筛选](media/emailforwarding1.png)

<span data-ttu-id="1ff18-p120">此时，您需要查看每个审计记录，以确定是否与活动电子邮件转发的详细信息。单击显示**详细信息**弹出页的审核记录，然后单击**详细信息**。以下屏幕截图和说明亮点邮箱设置指示电子邮件转发的信息。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p120">At this point, you have to look at the details of each audit record to determine if the activity is related to email forwarding. Click the audit record to display the **Details** flyout page, and then click **More information**. The following screenshot and descriptions highlights the information that indicates email forwarding was set on the mailbox.</span></span>

![审核记录的详细的信息](media/emailforwarding2.png)

<span data-ttu-id="1ff18-p121">a.在**ObjectId**字段中，设置电子邮件转发的邮箱的别名上显示。在**项目**列中的搜索结果页上，还会显示此邮箱。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p121">a. In the **ObjectId** field, the alias of the mailbox that email forwarding was set on is displayed. This mailbox is also displayed on the **Item** column in the search results page.</span></span>

<span data-ttu-id="1ff18-p122">b.在**参数**字段中， *ForwardingSmtpAddress*的值指示已邮箱上设置电子邮件转发。本示例中，邮件被转发到电子邮件地址 mike@contoso.com，即 alpinehouse.onmicrosoft.com 组织外部。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p122">b. In the **Parameters** field, The value *ForwardingSmtpAddress* indicates that email forward has been set on the mailbox. In this example, mail is being forwarded to the email address mike@contoso.com, which is outside of the alpinehouse.onmicrosoft.com organization.</span></span>

<span data-ttu-id="1ff18-p123">*DeliverToMailboxAndForward*参数 c. *True*值指示一份邮件传递到 sarad@alpinehouse.onmicrosoft.com*和*被转接至*ForwardingSmtpAddress 由指定的电子邮件地址*参数，它在本例中为 mike@contoso.com。如果*DeliverToMailboxAndForward*参数的值设置为*False*，然后电子邮件仅转发到由*ForwardingSmtpAddress*参数指定的地址中。未送达**ObjectId**字段中指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p123">c. The *True* value for the *DeliverToMailboxAndForward* parameter indicates that a copy of message delivered to sarad@alpinehouse.onmicrosoft.com *and* is forwarded to the email address specified by the *ForwardingSmtpAddress* parameter, which in this example is mike@contoso.com. If the value for the *DeliverToMailboxAndForward* parameter is set to *False*, then email is only forwarded to the address specified by the *ForwardingSmtpAddress* parameter. It's not delivered to the mailbox specified in the **ObjectId** field.</span></span>

<span data-ttu-id="1ff18-p124">d. **UserId**字段指示在**ObjectId**字段字段指定的邮箱设置电子邮件转发的用户。在搜索结果页上的**用户**列中还显示该用户。在这种情况下，似乎邮箱的所有者将其邮箱上设置电子邮件转发。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p124">d. The **UserId** field indicates the user who set email forwarding on the mailbox specified in the **ObjectId** field field. This user is also displayed in the **User** column on the search results page. In this case, it seems that the owner of the mailbox set email forwarding on her mailbox.</span></span>

<span data-ttu-id="1ff18-204">如果您确定，不应在邮箱上设置电子邮件转发，您可以通过在 Exchange Online PowerShell 中运行以下命令将其删除：</span><span class="sxs-lookup"><span data-stu-id="1ff18-204">If you determine that email forwarding shouldn't be set on the mailbox, you can remove it by running the following command in Exchange Online PowerShell:</span></span>

```
Set-Mailbox <mailbox alias> -ForwardingSmtpAddress $null 
```

<span data-ttu-id="1ff18-205">请参阅[Set-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)文章有关相关电子邮件转发的参数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1ff18-205">See the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) article for more information about the parameters related to email forwarding.</span></span>

## <a name="determining-if-a-user-deleted-email-items"></a><span data-ttu-id="1ff18-206">确定用户是否删除电子邮件项目</span><span class="sxs-lookup"><span data-stu-id="1ff18-206">Determining if a user deleted email items</span></span>

<span data-ttu-id="1ff18-p125">删除有关的审核日志记录之前电子邮件项目保存到 Office 365 审核日志，必须为在组织中每个用户邮箱启用邮箱审核。此外，SoftDelete 和 HardDelete 邮箱操作必须启用审核。有关说明，请参阅[启用邮箱审核 Office 365 中](enable-mailbox-auditing.md)。如果用户已启用邮箱审核，使用以下步骤来搜索与已删除电子邮件项相关的事件的审核日志。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p125">Before audit log records about deleted email items are saved to the Office 365 audit log, mailbox auditing has to be enabled for each user mailbox in your organization. Additionally, the SoftDelete and HardDelete mailbox actions have to be enabled for auditing. For instructions, see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). If mailbox auditing is already enabled for users, use the following steps to search the audit log for events related to deleted email items.</span></span>

<span data-ttu-id="1ff18-211">下面是如何配置此方案的审核日志搜索查询：</span><span class="sxs-lookup"><span data-stu-id="1ff18-211">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="1ff18-212">**活动**-在下**Exchange 邮箱活动**，选择一个或两个以下活动：</span><span class="sxs-lookup"><span data-stu-id="1ff18-212">**Activities** - Under **Exchange mailbox activities**, select one or both of the following activities:</span></span>

- <span data-ttu-id="1ff18-p126">**删除已删除邮件文件夹的邮件**-此活动对应于**SoftDelete**邮箱审核操作。当用户选择并按**Shift + Delete**中永久删除项目时，也会记录此活动。永久删除项目后，用户可以将其恢复已删除的邮件保留期限过期之前。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p126">**Deleted messages from Deleted Items folder** -  This activity corresponds to the **SoftDelete** mailbox auditing action. This activity is also logged when a user permanently deletes an item by selecting it and pressing **Shift+Delete**. After an item is permanently deleted, the user can recover it until the deleted item retention period expires.</span></span>

- <span data-ttu-id="1ff18-p127">**来自邮箱 Purged 邮件**-此活动对应于**HardDelete**邮箱审核操作。当用户清除可恢复邮件文件夹中的项时，这将记录。管理员可以使用 Office 365 安全性和合规性中心的内容搜索工具搜索和用户的邮箱恢复清除项目之前已删除的邮件保留期到期或更长时间如果处于保留状态。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p127">**Purged messages from mailbox** - This activity corresponds to the **HardDelete** mailbox auditing action. This is logged when a user purges an item from the Recoverable Items folder. Admins can use the Content Search tool in the Office 365 Security & Compliance Center to search for and recover purged items until the deleted item retention period expires or longer if the user's mailbox is on hold.</span></span>

<span data-ttu-id="1ff18-219">**开始日期**和**结束日期**-选择一个日期范围，适用于您的调查。</span><span class="sxs-lookup"><span data-stu-id="1ff18-219">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="1ff18-p128">**用户**-如果在此字段中选择一个用户，审核日志搜索工具将返回已删除 （带有 SoftDeleted 或 HardDeleted） 通过指定的用户的电子邮件项目的审核的记录。在某些情况下，删除电子邮件的用户可能不是邮箱所有者。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p128">**Users** - If you select a user in this field, the audit log search tool will return audit records for email items that were deleted (SoftDeleted or HardDeleted) by the user you specify. In some cases, the user who deletes an email might not be the mailbox owner.</span></span>

<span data-ttu-id="1ff18-222">**文件、 文件夹或网站**-离开此字段留空。</span><span class="sxs-lookup"><span data-stu-id="1ff18-222">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="1ff18-p129">运行搜索后，您可以筛选搜索结果显示审核记录软删除项目或硬已删除邮件。单击显示**详细信息**弹出页的审核记录，然后单击**详细信息**。有关已删除项，如主题行和时已删除的项的位置的其他信息显示在**AffectedItems**域。以下屏幕截图显示**AffectedItems**字段的示例从软删除项目和硬删除项目。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p129">After you run the search, you can filter the search results to display the audit records for soft-deleted items or for hard-deleted items. Click the audit record to display the **Details** flyout page, and then click **More information**. Additional information about the deleted item, such as the subject line and the location of the item when it was deleted, is displayed in the **AffectedItems** field. The following screenshots show an example of the **AffectedItems** field from a soft-deleted item and a hard-deleted item.</span></span>

<span data-ttu-id="1ff18-227">**软删除项目的 AffectedItems 字段示例**</span><span class="sxs-lookup"><span data-stu-id="1ff18-227">**Example of AffectedItems field for soft-deleted item**</span></span>

![软删除项的审核记录](media/softdeleteditem.png)

<span data-ttu-id="1ff18-229">**AffectedItems 硬删除项的字段的示例**</span><span class="sxs-lookup"><span data-stu-id="1ff18-229">**Example of AffectedItems field for hard-deleted item**</span></span>

![硬删除电子邮件项的审核记录](media/harddeleteditem.png)

### <a name="recovering-deleted-email-items"></a><span data-ttu-id="1ff18-231">恢复已删除的电子邮件项目</span><span class="sxs-lookup"><span data-stu-id="1ff18-231">Recovering deleted email items</span></span>

<span data-ttu-id="1ff18-p130">如果未过期的已删除的邮件保留期，用户可以恢复软删除项目。在 Exchange Online 中，默认删除邮件保留期 14 天，但管理员可以增加此设置为 30 天内的最大值。用户指向说明恢复已删除项目的[恢复已删除的项目或 Outlook Web App 中的电子邮件](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4)文章。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p130">Users can recover soft-deleted items if the deleted items retention period has not expired. In Exchange Online, the default deleted items retention period is 14 days, but admins can increase this setting to a maximum of 30 days. Point users to the [Recover deleted items or email in Outlook Web App](https://support.office.com/article/Recover-deleted-items-or-email-in-Outlook-Web-App-C3D8FC15-EEEF-4F1C-81DF-E27964B7EDD4) article for instructions on recovering deleted items.</span></span>

<span data-ttu-id="1ff18-p131">如前所述，管理员可能无法恢复硬已删除邮件，如果已删除的邮件保留期限未过期或当邮箱位于保留，在这种情况下将保留项目，直到保留持续时间过期。当您运行内容的搜索时，如果它们匹配搜索查询在搜索结果中返回软删除和硬删除可恢复邮件文件夹中的项。有关运行内容搜索的详细信息，请参阅[Office 365 中的内容搜索](content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p131">As previously explained, admins might be able to recover hard-deleted items if the deleted item retention period has not expired or if the mailbox is on hold, in which case items are retained until the hold duration expires. When you run a content search, soft-deleted and hard-deleted items in the Recoverable Items folder are returned in the search results if they match the search query. For more information about running content searches, see [Content Search in Office 365](content-search.md).</span></span>

> [!TIP]
> <span data-ttu-id="1ff18-238">若要搜索已删除电子邮件项目，搜索审核记录中的**AffectedItems**字段中显示的主题行的全部或部分。</span><span class="sxs-lookup"><span data-stu-id="1ff18-238">To search for deleted email items, search for all or part of the subject line that's displayed in the **AffectedItems** field in the audit record.</span></span>

## <a name="determining-if-a-user-created-an-inbox-rule"></a><span data-ttu-id="1ff18-239">确定创建收件箱规则的用户</span><span class="sxs-lookup"><span data-stu-id="1ff18-239">Determining if a user created an inbox rule</span></span>

<span data-ttu-id="1ff18-p132">当用户创建其 Exchange Online 邮箱的收件箱规则时，则相应的审核记录将保存到审核日志。有关收件箱规则的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="1ff18-p132">When users create an inbox rule for their Exchange Online mailbox, a corresponding audit record is saved to the audit log. For more information about inbox rules, see:</span></span>

- [<span data-ttu-id="1ff18-242">在 web 上的 Outlook 中使用收件箱规则</span><span class="sxs-lookup"><span data-stu-id="1ff18-242">Use inbox rules in Outlook on the web</span></span>](https://support.office.com/article/use-inbox-rules-in-outlook-on-the-web-8400435c-f14e-4272-9004-1548bb1848f2)
- [<span data-ttu-id="1ff18-243">使用规则来管理在 Outlook 中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="1ff18-243">Manage email messages in Outlook by using rules</span></span>](https://support.office.com/article/Manage-email-messages-by-using-rules-C24F5DEA-9465-4DF4-AD17-A50704D66C59)

<span data-ttu-id="1ff18-244">下面是如何配置此方案的审核日志搜索查询：</span><span class="sxs-lookup"><span data-stu-id="1ff18-244">Here's how to configure an audit log search query for this scenario:</span></span>

<span data-ttu-id="1ff18-245">**活动**-在**Exchange 邮箱活动**，选择下**New-inboxrule 创建/修改/启用/禁用收件箱规则**。</span><span class="sxs-lookup"><span data-stu-id="1ff18-245">**Activities** - Under **Exchange mailbox activities**, select **New-InboxRule Create/modify/enable/disable inbox rule**.</span></span>

<span data-ttu-id="1ff18-246">**开始日期**和**结束日期**-选择一个日期范围，适用于您的调查。</span><span class="sxs-lookup"><span data-stu-id="1ff18-246">**Start date** and **End date** - Select a date range that's applicable to your investigation.</span></span>

<span data-ttu-id="1ff18-p133">**用户**-除非正在研究特定用户，则将此字段留空。这将帮助您确定新设置的任何用户的收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p133">**Users** - Unless you're investigating a specific user, leave this field blank. This will help you identify new inbox rules set up by any user.</span></span>

<span data-ttu-id="1ff18-249">**文件、 文件夹或网站**-离开此字段留空。</span><span class="sxs-lookup"><span data-stu-id="1ff18-249">**File, folder, or site** - Leave this field blank.</span></span>

<span data-ttu-id="1ff18-p134">运行搜索后，在搜索结果中显示此活动任何审核记录。单击显示**详细信息**弹出页的审核记录，然后单击**详细信息**。在**参数**字段显示收件箱规则设置的信息。以下屏幕截图和说明突出显示收件箱规则的信息。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p134">After you run the search, any audit records for this activity are displayed in the search results. Click an audit record to display the **Details** flyout page, and then click **More information**. Information about the inbox rule settings are displayed in the **Parameters** field. The following screenshot and descriptions highlights the information about inbox rules.</span></span>

![新的收件箱规则的审核记录](media/NewInboxRuleRecord.png)

<span data-ttu-id="1ff18-p135">答： 在**ObjectId**字段中，显示收件箱规则的完整名称。此名称包括用户的邮箱 (例如，SaraD) 的别名和收件箱规则 （例如，"移动邮件管理员从"） 的名称。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p135">a. In the **ObjectId** field, the full name of the inbox rule is displayed. This name includes the alias of the user's mailbox (for example, SaraD) and the name of the inbox rule (for example, "Move messages from admin").</span></span>

<span data-ttu-id="1ff18-p136">b.在**参数**字段中，将显示收件箱规则的条件。本示例中，*从*参数指定的条件。*From*参数为定义的值指示收件箱规则对 admin@alpinehouse.onmicrosoft.com 通过发送电子邮件。可以使用定义的收件箱规则的条件的参数的完整列表，请参阅[New-inboxrule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)文章。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p136">b. In the **Parameters** field, the condition of the inbox rule is displayed. In this example, the condition is specified by the *From* parameter. The value defined for the *From* parameter indicates that the inbox rule acts on email sent by admin@alpinehouse.onmicrosoft.com. For a complete list of the parameters that can be used to define conditions of inbox rules, see the [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) article.</span></span>

<span data-ttu-id="1ff18-p137">c. *MoveToFolder*参数指定收件箱规则; 的操作本示例中，从 admin@alpinehouse.onmicrosoft.com 接收的消息将移动到名为*AdminSearch*的文件夹中。另请参阅[New-inboxrule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule)文章的完整列表可以使用定义的收件箱规则操作的参数。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p137">c. The *MoveToFolder* parameter specifies the action for the inbox rule; in this example, messages received from admin@alpinehouse.onmicrosoft.com are moved to the folder named *AdminSearch*. Also see the [New-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-inboxrule) article for a complete list of parameters that can used to define the action of an inbox rule.</span></span>

<span data-ttu-id="1ff18-p138">d.**用户 Id**字段指示创建**ObjectId**字段中指定的收件箱规则的用户。在搜索结果页上的**用户**列中还显示该用户。</span><span class="sxs-lookup"><span data-stu-id="1ff18-p138">d. The **UserId** field indicate the user who created the inbox rule specified in the **ObjectId** field. This user is also displayed in the **User** column on the search results page.</span></span>
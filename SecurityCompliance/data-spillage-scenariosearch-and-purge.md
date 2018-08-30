---
title: 电子数据展示解决方案系列数据泄漏方案-搜索和清除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: 使用 Office 365 电子数据展示和搜索工具来管理并响应在组织中的数据泄漏事件。
ms.openlocfilehash: 2bf17923408bd5cf8325d27a38595331d169906f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524912"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a><span data-ttu-id="c644f-103">电子数据展示解决方案系列： 数据泄漏方案-搜索和清除</span><span class="sxs-lookup"><span data-stu-id="c644f-103">eDiscovery solution series: Data spillage scenario - Search and purge</span></span>

 <span data-ttu-id="c644f-p101">**什么是数据泄漏为什么小心您？** 机密文档发布到不受信任的环境时，数据泄漏。检测到数据泄漏事件时，务必快速评估的大小和位置的损耗情况、 检查周围的用户活动，然后在系统中永久清除溅入的数据。</span><span class="sxs-lookup"><span data-stu-id="c644f-p101">**What is data spillage and why should you care?** Data spillage is when a confidential document is released into an untrusted environment. When a data spillage incident is detected, it's important to quickly assess the size and locations of the spillage, examine user activities around it,  and then permanently purge the spilled data from the system.</span></span> 
  
## <a name="data-spillage-scenario"></a><span data-ttu-id="c644f-107">数据泄漏方案</span><span class="sxs-lookup"><span data-stu-id="c644f-107">Data spillage scenario</span></span>

<span data-ttu-id="c644f-p102">您在 Contoso 的潜在顾客信息安全专员。其中员工不知情的情况下共享高度机密文档与多人通过电子邮件的数据泄漏情况的情况下将通知您。您希望快速评估内部和外部，用户会收到此文档。确定后，您想要与其他调查员查看，，然后从 Office 365 永久移除数据共享案例研究结果。完成调查后，您想要永久删除和其他案例的详细信息的任何供他们将来参考的证据生成报告。</span><span class="sxs-lookup"><span data-stu-id="c644f-p102">You’re a lead information security officer at Contoso. You are informed of a data spillage situation where an employee unknowingly shared a highly confidential document with multiple people through email. You want to quickly assess who received this document internally and externally. Once identified, you would like to share case findings with other investigators to review, and then permanently remove the data from Office 365. After the investigation is complete, you want to generate a report with the evidence of permanent removal and other case details for any future reference.</span></span>
  
### <a name="scope-of-this-article"></a><span data-ttu-id="c644f-113">本文的范围</span><span class="sxs-lookup"><span data-stu-id="c644f-113">Scope of this article</span></span>

<span data-ttu-id="c644f-p103">本文档提供有关如何从中永久删除一条消息，Office 365，以便不访问或可恢复的说明的列表。若要删除一条消息，并使其可恢复已删除的邮件保留期限过期之前，请参阅[搜索和删除 Office 365 组织中的电子邮件](search-for-and-delete-messages-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="c644f-p103">This document provides a list of instructions on how to permanently remove a message from Office 365 so that it's not accessible or recoverable. To delete a message and make it recoverable until the deleted item retention period expires, see [Search for and delete email messages in your Office 365 organization](search-for-and-delete-messages-in-your-organization.md).</span></span>
  
## <a name="workflow-for-managing-data-spillage-incidents"></a><span data-ttu-id="c644f-116">用于管理数据泄漏事件工作流</span><span class="sxs-lookup"><span data-stu-id="c644f-116">Workflow for managing data spillage incidents</span></span>

<span data-ttu-id="c644f-117">下面是如何管理数据泄漏事件：</span><span class="sxs-lookup"><span data-stu-id="c644f-117">Here's a how to manage a data spillage incident:</span></span>

![用于管理数据泄漏事件 8 步骤工作流](media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[<span data-ttu-id="c644f-119">（可选）步骤 1： 管理谁可以访问案例和设置合规性边界</span><span class="sxs-lookup"><span data-stu-id="c644f-119">(Optional) Step 1: Manage who can access the case and set compliance boundaries</span></span>](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[<span data-ttu-id="c644f-120">步骤 2： 创建电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="c644f-120">Step 2: Create an eDiscovery case</span></span>](#step-2-create-an-ediscovery-case)<br/>
[<span data-ttu-id="c644f-121">步骤 3： 搜索溅入数据</span><span class="sxs-lookup"><span data-stu-id="c644f-121">Step 3: Search for the spilled data</span></span>](#step-3-search-for-the-spilled-data)<br/>
[<span data-ttu-id="c644f-122">步骤 4： 检查和验证案例研究结果</span><span class="sxs-lookup"><span data-stu-id="c644f-122">Step 4: Review and validate case findings</span></span>](#step-4-review-and-validate-case-findings)<br/>
[<span data-ttu-id="c644f-123">步骤 5： 使用邮件跟踪日志以检查如何溅入的数据的共享</span><span class="sxs-lookup"><span data-stu-id="c644f-123">Step 5: Use message trace log to check how spilled data was shared</span></span>](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[<span data-ttu-id="c644f-124">步骤 6： 准备邮箱</span><span class="sxs-lookup"><span data-stu-id="c644f-124">Step 6: Prepare the mailboxes</span></span>](#step-6-prepare-the-mailboxes)<br/>
[<span data-ttu-id="c644f-125">步骤 7： 永久删除溅入的数据</span><span class="sxs-lookup"><span data-stu-id="c644f-125">Step 7: Permanently delete the spilled data</span></span>](#step-7-permanently-delete-the-spilled-data)<br/>
[<span data-ttu-id="c644f-126">步骤 8： 验证，提供身份证明删除，并审核</span><span class="sxs-lookup"><span data-stu-id="c644f-126">Step 8: Verify, provide a proof of deletion, and audit</span></span>](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a><span data-ttu-id="c644f-127">在开始前须知</span><span class="sxs-lookup"><span data-stu-id="c644f-127">Things to know before you start</span></span>

- <span data-ttu-id="c644f-p104">置于保持状态的邮箱后，已删除的邮件将一直在可恢复邮件文件夹保留期到期或保留释放。[步骤 6](#step-6-prepare-the-mailboxes)介绍如何删除邮箱的保留。删除保留之前咨询您的记录管理或法律部门。您的组织可能必须定义上的邮箱是否保留策略或数据泄漏事件优先。</span><span class="sxs-lookup"><span data-stu-id="c644f-p104">When a mailbox is on hold, a deleted message remains in the Recoverable Items folder until the retention period expires or the hold is released. [Step 6](#step-6-prepare-the-mailboxes) describes how to remove hold from the mailboxes. Check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
    
- <span data-ttu-id="c644f-p105">若要控制哪些用户邮箱数据泄漏调查员可以搜索和管理谁可以访问这种情况，可以设置合规性边界，还可以创建自定义角色组，[第 1 步](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)中所述。若要执行此操作，您必须是组织管理角色组的成员或角色管理角色分配。如果您或在组织中的管理员已设置合规性边界，则可以跳过步骤 1。</span><span class="sxs-lookup"><span data-stu-id="c644f-p105">To control which user mailboxes an data spillage investigator can search and manage who can access the case, you can set up compliance boundaries and create a custom role group, which is described in [Step 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries). To do this, you have to be a member of the Organization Management role group or be assigned the role management role. If you or in administrator in your organization has already set compliance boundaries, you can skip Step 1.</span></span>
    
- <span data-ttu-id="c644f-p106">创建用例，您必须是电子数据展示管理员角色组的成员，或者是已分配的案例管理角色自定义角色组的成员。如果您不是成员，请求[将您添加到电子数据展示管理员角色组](assign-ediscovery-permissions.md)向 Office 365 管理员。</span><span class="sxs-lookup"><span data-stu-id="c644f-p106">To create a case, you must be a member of the eDiscovery Manager role group or be a member of a custom role group that's assigned the Case Management role. If you're not a member, ask an Office 365 administrator to [add you to the eDiscovery manager role group](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="c644f-p107">若要删除溢出至您的组织的数据，您需要在 Exchange Online PowerShell 中使用[Search-mailbox DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps)命令。此外，若要使用*DeleteContent*参数，您还必须是 Exchange Online 邮箱导入导出角色分配中角色组的成员。请参阅在[管理角色组](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx)"将角色添加到角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="c644f-p107">To delete data that's spilled into your organization, you need to use the [Search-Mailbox -DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps) command in Exchange Online PowerShell. Additionally, to use the  *DeleteContent* parameter, you also have to be a member of a role group in Exchange Online that's assigned the Mailbox Import Export role. See the "Add a role to a role group" section in [Manage role groups](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="c644f-p108">若要在步骤 8 中搜索的 Office 365 审核日志电子数据展示活动，必须打开审核为您的组织。您可以搜索最近 90 天内执行的活动。若要详细了解如何启用和使用审核，请参阅步骤 8 中的[审核数据泄漏调查过程](#auditing-the-data-spillage-investigation-process)一节。</span><span class="sxs-lookup"><span data-stu-id="c644f-p108">To search the Office 365 audit log eDiscovery activities in Step 8, auditing must be turned on for your organization. You can search for activities that were performed within the last 90 days. To learn more about how to enable and use auditing, see the [Auditing the data spillage investigation process](#auditing-the-data-spillage-investigation-process) section in Step 8.</span></span> 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a><span data-ttu-id="c644f-143">（可选）步骤 1： 管理谁可以访问案例和设置合规性边界</span><span class="sxs-lookup"><span data-stu-id="c644f-143">(Optional) Step 1: Manage who can access the case and set compliance boundaries</span></span>

<span data-ttu-id="c644f-p109">根据您组织的做法是，您需要控制哪些人可以访问用于调查数据泄漏事件并设置合规性边界电子数据展示事例。执行此操作的最简单方式是为 Office 365 安全性和合规性中心中的现有角色组的成员添加调查人员，然后添加以电子数据展示事例的成员身份的角色组。有关内置电子数据展示角色组以及如何将成员添加到电子数据展示事例的信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="c644f-p109">Depending on your organizational practice, you need to control who can access the eDiscovery case used to investigate a data spillage incident and set up compliance boundaries. The easiest way to do this is to add investigators as members of an existing role group in the Office 365 Security & Compliance Center and then add the role group as a member of the eDiscovery case. For information about the built-in eDiscovery role groups and how to add members to an eDiscovery case, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="c644f-p110">您还可以创建新的角色组的与您组织的需求。例如，您可能希望来访问和协作的所有数据泄漏情况下在组织中的数据泄漏调查人员组。您可以通过创建"数据泄漏调查员"角色组、 分配适当的角色 （导出、 RMS 解密、 审阅、 预览、 合规性搜索和案例管理）、 向角色组中，添加数据泄漏调查人员，然后添加执行此操作数据泄漏电子数据展示事例的成员身份的角色组。有关如何执行此操作的详细说明，请参阅[设置 Office 365 中的电子数据展示调查的合规性边界](set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="c644f-p110">You can also create a new role group that aligns with your organizational needs. For example, you might want a group of data spillage investigators in the organization to access and collaborate on all data spillage cases. You can do this by creating a "Data Spillage Investigator" role group, assigning the appropriate roles (Export, RMS Decrypt, Review, Preview, Compliance Search, and Case Management), adding the data spillage investigators to the role group, and then adding the role group as a member of the data spillage eDiscovery case. See [Set up compliance boundaries for eDiscovery investigations in Office 365](set-up-compliance-boundaries.md) for detailed instructions on how to do this.</span></span> 
  
## <a name="step-2-create-an-ediscovery-case"></a><span data-ttu-id="c644f-151">步骤 2： 创建电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="c644f-151">Step 2: Create an eDiscovery case</span></span>

<span data-ttu-id="c644f-p111">电子数据展示事例提供有效的方式来管理您的数据泄漏调查。可以将成员添加到您在步骤 1 中创建的角色组、 角色组添加成员的新电子数据展示事例，身份执行迭代搜索以查找溅入的数据、 导出报表以共享、 跟踪状态的情况下，然后回顾到 c 的详细信息如果需要，ase。请考虑建立用于数据泄漏事件的电子数据展示事例的命名约定，并提供尽可能多的信息，您可以在的大小写的名称和说明，以便您可以找到并如有必要，以便将来参考。</span><span class="sxs-lookup"><span data-stu-id="c644f-p111">An eDiscovery case provides an effective way to manage your data spillage investigation. You can add members to the role group that you created in Step 1, add the role group as a member of new a eDiscovery case, perform iterative searches to find the spilled data, export a report to share, track the status of the case, and then refer back to the details of the case if needed. Consider establishing a naming convention for eDiscovery cases used for data spillage incidents, and provide as much information as you can in the case name and description so you can locate and refer to in the future if necessary.</span></span>
  
<span data-ttu-id="c644f-p112">若要创建新的用例，可以使用电子数据展示中安全&amp;合规性中心。请参阅[Office 365 安全性和合规性中心中的电子数据展示事例](ediscovery-cases.md#step-2-create-a-new-case)中的"创建新的用例"。</span><span class="sxs-lookup"><span data-stu-id="c644f-p112">To create a new case, you can use eDiscovery in the Security &amp; Compliance Center. See "Create a new case" in [eDiscovery Cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
  
## <a name="step-3-search-for-the-spilled-data"></a><span data-ttu-id="c644f-157">步骤 3： 搜索溅入数据</span><span class="sxs-lookup"><span data-stu-id="c644f-157">Step 3: Search for the spilled data</span></span>

<span data-ttu-id="c644f-p113">现在您已创建案例和托管的访问，您可以使用这种情况反复搜索来查找溅入的数据并确定包含溅入的数据的邮箱。您将使用您用来查找要删除在[步骤 7](#step-7-permanently-delete-the-spilled-data)中这些相同的邮件的电子邮件的同一个搜索查询。</span><span class="sxs-lookup"><span data-stu-id="c644f-p113">Now that you've created a case and managed access, you can use the case to iteratively search to find the spilled data and identify the mailboxes that contain the spilled data. You will use the same search query that you used to find the email messages to delete those same messages in [Step 7](#step-7-permanently-delete-the-spilled-data).</span></span>
  
<span data-ttu-id="c644f-160">若要创建内容电子数据展示事例与搜索关联，请参阅[Office 365 安全性和合规性中心中的电子数据展示事例](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case)中的"创建和运行与案例相关的内容搜索"。</span><span class="sxs-lookup"><span data-stu-id="c644f-160">To create a content searches associated with an eDiscovery case, see "Create and run a Content Search associated with a case" in [eDiscovery Cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case).</span></span>
  
 <span data-ttu-id="c644f-p114">**重要：** 搜索查询中使用的关键字可能包含您要搜索的实际溅入的数据。例如，如果搜索包含社会保险号码和您的文档使用 it 作为搜索关键字，则必须删除查询以后避免进一步损耗情况。请参阅在步骤 8 中的[删除搜索查询](#deleting-the-search-query)。</span><span class="sxs-lookup"><span data-stu-id="c644f-p114">**Important:** The keywords that you use in the search query may contain the actual spilled data that you're searching for. For example, if you searching for documents containing a social security number and you use the it as search keyword, you must delete the query afterwards to avoid further spillage. See [Deleting the search query](#deleting-the-search-query) in Step 8.</span></span> 
  
## <a name="step-4-review-and-validate-case-findings"></a><span data-ttu-id="c644f-164">步骤 4： 检查和验证案例研究结果</span><span class="sxs-lookup"><span data-stu-id="c644f-164">Step 4: Review and validate case findings</span></span>

<span data-ttu-id="c644f-p115">创建内容搜索后，您需要能够查看并验证搜索结果，并验证仅包含，必须先删除电子邮件。在内容搜索中，您可以预览 1,000 电子邮件的随机采样而不导出搜索结果，以避免更多数据泄漏。您可以阅读更多有关预览限制在[Limits for Office 365 安全性内容搜索&amp;合规性中心](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="c644f-p115">After you create a content search, you need to review and validate that the search results and verify that they consist only of the email messages that must be deleted. In a content search, you can preview a random sampling of 1,000 email messages without exporting the search results to avoid further data spillage. You can read more about the preview limitations at [Limits for Content Search in the Office 365 Security &amp; Compliance Center](limits-for-content-search.md).</span></span>
  
<span data-ttu-id="c644f-p116">如果您有邮箱，可查看每 1,000 个以上的邮箱或 100 多个电子邮件，您可以使用其他关键字或日期范围或发件人/收件人如条件的初始搜索将多个搜索分成并查看每个搜索结果单独。请确保记下您删除[步骤 7](#step-7-permanently-delete-the-spilled-data)中的邮件时要使用的所有搜索查询。</span><span class="sxs-lookup"><span data-stu-id="c644f-p116">If you have more than 1,000 mailboxes or more than 100 email messages per mailbox to review, you can divide the initial search into multiple searches by using additional keywords or conditions such as date range or sender/recipient and review the results of each search individually. Make sure to note down all search queries to use when you delete messages in [Step 7](#step-7-permanently-delete-the-spilled-data).</span></span>

<span data-ttu-id="c644f-p117">如果管理员或最终用户分配一个 Office 36 E5 许可证，您可以检查最多 10,000 同时使用 Office 365 高级电子数据展示的搜索结果。如果有 10,000 个以上的电子邮件以查看，您可以除以日期范围的搜索查询并按日期排序结果的搜索单独查看每个结果。在高级电子数据展示，可以标记预览面板中使用**标签作为**功能的搜索结果，并按您标记的标记筛选搜索结果。与辅助审阅者协作时，这非常有用。使用高级电子数据展示，如光学字符识别、 电子邮件超线程，和预测编码中其他分析工具可以快速处理和查看数千个邮件并标记这些进行进一步审阅。请参阅[快速设置 Office 365 高级电子数据展示](quick-setup-for-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="c644f-p117">If a custodian or end user is assigned an Office 36 E5 license, you can examine up to 10,000 search results at once using Office 365 Advanced eDiscovery. If there are more than 10,000 email messages to review, you can divide the search query by date range and review each result individually as search results are sorted by date. In Advanced eDiscovery, you can tag search results using the **Label as** feature in the preview panel and filter the search result by the tag you labeled. This is helpful when you collaborate with a secondary reviewer. By using additional analytics tools in Advanced eDiscovery, such as optical character recognition, email threading, and predictive coding, you can quickly process and review thousands of messages and tag them for further review. See [Quick setup for Office 365 Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md).</span></span>

<span data-ttu-id="c644f-p118">找到包含溅入的数据的电子邮件后，检查邮件以确定共享已从外部的收件人。为进一步的跟踪消息，可以收集发件人信息和日期范围，以便您可以使用邮件跟踪日志，[步骤 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)中所述。</span><span class="sxs-lookup"><span data-stu-id="c644f-p118">When you find an email message that contains spilled data, check the recipients of the message to determine if it was shared externally. To further trace an message, you can collect sender information and date range so you can use the message trace logs, which is described in [Step 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared).</span></span>

<span data-ttu-id="c644f-p119">验证搜索结果的做，您可能想要第二审阅与其他人共享您的发现。分配给这种情况，在步骤 1 中的人员可以查看案例中电子数据展示和高级电子数据展示内容和批准案例研究结果。您还可以生成报表，而不将导出的实际内容。您还可以用作此相同的报告证明删除[第 8 步](#step-8-verify-provide-a-proof-of-deletion-and-audit)中所述。</span><span class="sxs-lookup"><span data-stu-id="c644f-p119">Afer you verified the search results, you may want to share your findings with others for a secondary review. People who you assigned to the case in Step 1 can review the case content in both eDiscovery and Advanced eDiscovery and approve case findings. You can also generate a report without exporting the actual content. You can also use this same report as a proof of deletion, which is described in [Step 8](#step-8-verify-provide-a-proof-of-deletion-and-audit).</span></span>
  
 <span data-ttu-id="c644f-182">**若要生成统计报告：**</span><span class="sxs-lookup"><span data-stu-id="c644f-182">**To generate a statistical report:**</span></span>
  
1. <span data-ttu-id="c644f-183">转到电子数据展示案例，在**搜索**页上，单击您想要生成的报告的搜索。</span><span class="sxs-lookup"><span data-stu-id="c644f-183">Go to the **Search** page in the eDiscovery case, and click the search that you want to generate a report for.</span></span> 
    
2. <span data-ttu-id="c644f-184">在弹出页上，单击**更多 > 将报表导出**。</span><span class="sxs-lookup"><span data-stu-id="c644f-184">On the flyout page, click **More > Export report**.</span></span>
 
      <span data-ttu-id="c644f-185">显示导出报告页。</span><span class="sxs-lookup"><span data-stu-id="c644f-185">The Export report page is displayed.</span></span>

    ![选择搜索，然后单击更多 > 导出弹出上的报告](media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. <span data-ttu-id="c644f-187">选择**所有项目，包括具有无法识别的格式进行加密，或出于其他原因或者没有索引**，然后单击**生成报表**。</span><span class="sxs-lookup"><span data-stu-id="c644f-187">Select **All items, including ones that have unrecognized format, are encrypted, or weren’t indexed for other reasons** and then click **Generate report**.</span></span>

4. <span data-ttu-id="c644f-p120">在电子数据展示案例中，单击**导出**要显示的导出作业列表。您可能需要单击**刷新**更新该列表以显示您刚创建的导出作业。</span><span class="sxs-lookup"><span data-stu-id="c644f-p120">In the eDiscovery case, click **Export** to display the list of export jobs. You may have to click **Refresh** to update the list to display the export job you just created.</span></span>

5. <span data-ttu-id="c644f-190">单击导出作业，，然后单击**下载**弹出页上的报告。</span><span class="sxs-lookup"><span data-stu-id="c644f-190">Click the export job, and then click **Download** report on the flyout page.</span></span>
 
    ![在导出页上，单击导出，然后单击"下载报告"](media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

<span data-ttu-id="c644f-p121">**导出摘要**报告中包含位置发现结果和大小的搜索结果数。您可以使用此进行比较的删除后生成的报告中提供与证明删除。**结果**报告包含搜索结果，包括主题、 发件人、 收件人，如果读取的电子邮件、 日期和每封邮件的大小的更详细的摘要。如果在此报告的详细信息的任何包含实际溅入的数据，请务必完成调查后永久删除 Results.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="c644f-p121">The **Export Summary** report contains the number of locations found with results and the size of the search results. You can use this to compare with the report generated after deletion and provide as a proof of deletion. The **Results** report contains a more detailed summary of the search results, including the subject, sender, recipients, if the email was read, dates, and size of each message. If any of the details in this report contains that actual spilled data, be sure to permanently delete the Results.csv file when the investigation is complete.</span></span>

<span data-ttu-id="c644f-196">有关导出报告的详细信息，请参阅[导出内容的搜索报告](export-a-content-search-report.md)。</span><span class="sxs-lookup"><span data-stu-id="c644f-196">For more information about exporting reports, see [Export a Content Search report](export-a-content-search-report.md).</span></span>
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a><span data-ttu-id="c644f-197">步骤 5： 使用邮件跟踪日志以检查如何溅入的数据的共享</span><span class="sxs-lookup"><span data-stu-id="c644f-197">Step 5: Use message trace log to check how spilled data was shared</span></span>

<span data-ttu-id="c644f-p122">若要进一步调查如果共享溅入数据的电子邮件，您可以 （可选） 查询邮件跟踪日志的发件人信息和步骤 4 中收集的日期范围信息。请注意，邮件跟踪的保留期 30 天的实时数据和 90 天的历史数据。</span><span class="sxs-lookup"><span data-stu-id="c644f-p122">To further investigate if email with spilled data was shared, you can optionally query the message trace logs with the sender information and the date range information that you gathered in Step 4. Note that the retention period for message trace is 30 days for real time data and 90 days for historical data.</span></span>
  
<span data-ttu-id="c644f-p123">您可以使用安全性和合规性中心中的邮件跟踪，或使用相应的 cmdlet 在 Exchange Online PowerShell。请务必注意邮件跟踪不提供完整保证能返回的数据完整性。有关使用邮件跟踪的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c644f-p123">You can use Message trace in the Security & Compliance Center or use the corresponding cmdlets in Exchange Online PowerShell. It's important to note that message tracing doesn't offer full guarantees on the completeness of data returned. For more information about using Message trace, see:</span></span> 
  
- [<span data-ttu-id="c644f-203">邮件跟踪 Office 365 安全性&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="c644f-203">Message trace in the Office 365 Security &amp; Compliance Center</span></span>](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [<span data-ttu-id="c644f-204">新的 Message Trace in Office 365 安全性&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="c644f-204">New Message Trace in Office 365 Security &amp; Compliance Center</span></span>](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a><span data-ttu-id="c644f-205">步骤 6： 准备邮箱</span><span class="sxs-lookup"><span data-stu-id="c644f-205">Step 6: Prepare the mailboxes</span></span>

<span data-ttu-id="c644f-p124">查看并验证搜索结果包含必须删除邮件之后，您需要收集受影响的邮箱，运行**搜索邮箱 DeleteContent**命令时，在步骤 7 中使用的电子邮件地址的列表。您可能还需要准备邮箱之前，可永久删除电子邮件，具体取决于是否在包含溅入的数据或如果任何这些邮箱上保留的邮箱启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="c644f-p124">After you review and validate that the search results contains only the messages that must be deleted, you need to collect a list of the email addresses of the impacted mailboxes to use in Step 7 when you run the **Search-Mailbox -DeleteContent** command. You may also have to prepare the mailboxes before you can permanently delete email messages depending on whether single item recovery is enabled on the mailboxes that contain the spilled data or if any of those mailboxes are on hold.</span></span>
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a><span data-ttu-id="c644f-208">获取与溅入数据的邮箱的地址列表</span><span class="sxs-lookup"><span data-stu-id="c644f-208">Get a list of addresses of mailboxes with spilled data</span></span>

<span data-ttu-id="c644f-209">有两种方法来收集的与溅入数据的邮箱的电子邮件地址列表。</span><span class="sxs-lookup"><span data-stu-id="c644f-209">There are two ways to collect a list of email addresses of mailboxes with spilled data.</span></span>

<span data-ttu-id="c644f-210">**选项 1： 获取与溅入数据的邮箱的地址列表**</span><span class="sxs-lookup"><span data-stu-id="c644f-210">**Option 1: Get a list of addresses of mailboxes with spilled data**</span></span>

1. <span data-ttu-id="c644f-211">打开电子数据展示事例，转到**搜索**页并选择适当的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="c644f-211">Open the eDiscovery case, go to the **Search** page and select the appropriate content search.</span></span> 
    
2. <span data-ttu-id="c644f-212">在弹出页上，单击**查看结果**。</span><span class="sxs-lookup"><span data-stu-id="c644f-212">On the flyout page, click **View results**.</span></span>
    
3. <span data-ttu-id="c644f-213">在**单个结果**下拉列表中单击**搜索统计信息**。</span><span class="sxs-lookup"><span data-stu-id="c644f-213">In the **Individual results** drop down list, click **Search statistics**.</span></span>
    
4. <span data-ttu-id="c644f-214">在**类型**下拉列表中，单击**顶部的位置**。</span><span class="sxs-lookup"><span data-stu-id="c644f-214">In the **Type** drop down list, click **Top locations**.</span></span>
    
    ![获取包含在搜索统计信息的顶部的位置页上的搜索结果的邮箱的列表](media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    <span data-ttu-id="c644f-p125">显示包含搜索结果的邮箱的列表。此外会显示每个邮箱中的搜索查询匹配的项目数。</span><span class="sxs-lookup"><span data-stu-id="c644f-p125">A list of mailboxes that contain search results is displayed. The number of items in each mailbox that match the search query is also displayed.</span></span>
    
5. <span data-ttu-id="c644f-218">列表中的信息复制和保存到文件或单击**下载**以下载到 CSV 文件的信息。</span><span class="sxs-lookup"><span data-stu-id="c644f-218">Copy the information in the list and save it to a file or click **Download** to download the information to a CSV file.</span></span> 
    
<span data-ttu-id="c644f-219">**选项 2： 将邮箱位置获得导出报告**</span><span class="sxs-lookup"><span data-stu-id="c644f-219">**Option 2: Get mailbox locations from the export report**</span></span>

<span data-ttu-id="c644f-p126">在[步骤 4](#step-4-review-and-validate-case-findings)中打开您下载的导出摘要报表。在报表的第一列，**位置**下列出每个邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="c644f-p126">Open the Export Summary report that you downloaded in [Step 4](#step-4-review-and-validate-case-findings). In the first column in the report, the email address of each mailbox is listed under **Locations**.</span></span>
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a><span data-ttu-id="c644f-222">准备邮箱，因此您可以删除溅入的数据</span><span class="sxs-lookup"><span data-stu-id="c644f-222">Prepare the mailboxes so you can delete the spilled data</span></span>

<span data-ttu-id="c644f-p127">如果启用单个项目恢复或邮箱置于保持状态，则将可恢复的项目文件夹中保留永久删除 （清除） 的邮件。因此，可以清除溅入的数据之前，您需要检查的现有邮箱配置并禁用单个项目恢复，删除任何保持或 Office 365 保留策略。请记住，您可以准备一个邮箱一次，然后在不同的邮箱上运行在同一个命令或创建同时准备多个邮箱的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="c644f-p127">If single item recovery is enabled or if a mailbox is placed on hold, a permanently deleted (purged) message will be retained in Recoverable Items folder. So before you can purge spilled data, you need to check the existing mailbox configurations and disable single item recovery and remove any hold or Office 365 retention policy. Keep in mind that you can prepare one mailbox at a time, and then run the same command on different mailboxes or create a PowerShell script to prepare multiple mailboxes at the same time.</span></span>

- <span data-ttu-id="c644f-226">请参阅"步骤 1： 收集信息有关邮箱"中的说明有关如何检查是否启用单个项目恢复或如果邮箱置于保留或分配给[删除在可恢复项目文件夹中的基于云的邮箱的保留项](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox)保留策略。</span><span class="sxs-lookup"><span data-stu-id="c644f-226">See "Step 1: Collect information about the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) for instructions about how to check if single item recovery is enabled or if the mailbox is placed on hold or it's assigned to a retention policy.</span></span> 
    
- <span data-ttu-id="c644f-227">请参阅"步骤 2： 准备邮箱"中[删除在可恢复项目文件夹中的基于云的邮箱的保留的项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox)有关禁用单个项目恢复的说明。</span><span class="sxs-lookup"><span data-stu-id="c644f-227">See "Step 2: Prepare the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) for instructions about disabling single item recovery.</span></span> 
    
- <span data-ttu-id="c644f-228">请参阅"步骤 3： 删除邮箱的所有保留项"中[删除在可恢复项目文件夹中的基于云的邮箱的保留的项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox)有关如何从邮箱中删除保持或保留策略的说明。</span><span class="sxs-lookup"><span data-stu-id="c644f-228">See "Step 3: Remove all holds from the mailbox" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) for instructions about how to remove a hold or retention policy from a mailbox.</span></span> 
    
 <span data-ttu-id="c644f-p128">**重要：** 删除保留或保留策略之前，请与记录管理或法律部门。您的组织可能有定义上的邮箱是否保留策略或数据泄漏事件优先。</span><span class="sxs-lookup"><span data-stu-id="c644f-p128">**Important:** Check with your records management or legal departments before removing a hold or retention policy. Your organization may have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
<span data-ttu-id="c644f-p129">请务必验证溅入的数据已被永久删除后还原到先前的配置的邮箱。请参阅[步骤 7](#step-7-permanently-delete-the-spilled-data)中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c644f-p129">Be sure to revert the mailbox to previous configurations after you verify that the spilled data has been permanently deleted. See the details in [Step 7](#step-7-permanently-delete-the-spilled-data).</span></span>

## <a name="step-7-permanently-delete-the-spilled-data"></a><span data-ttu-id="c644f-233">步骤 7： 永久删除溅入的数据</span><span class="sxs-lookup"><span data-stu-id="c644f-233">Step 7: Permanently delete the spilled data</span></span>

<span data-ttu-id="c644f-p130">使用收集和准备步骤 6 和创建和精简查找包含溅入的数据的电子邮件的步骤 3 中的搜索查询中的邮箱位置，您可以立即永久删除溅入的数据。如前所述，您必须为其分配邮箱导入导出角色在 Exchange Online 中删除邮件使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="c644f-p130">Using the mailbox locations that you collected and prepared in Step 6 and the search query that was created and refined in Step 3 to find email messages that contain the spilled data, you can now permanently delete the spilled data. As previously explained, you have to be assigned the Mailbox Import Export role in Exchange Online to delete messages using the following procedure.</span></span>
  
1. <span data-ttu-id="c644f-236">[连接到 Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="c644f-236">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
2. <span data-ttu-id="c644f-237">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c644f-237">Run the following command:</span></span>
    
    ```
    Search-Mailbox -Identity <mailbox identity> -SearchDumpster -DeleteContent $true -SearchQuery <search query>
    ```
  
3. <span data-ttu-id="c644f-238">重新运行前面的命令通过将为 Identity 参数; 值包含溅入的数据，每个邮箱例如：</span><span class="sxs-lookup"><span data-stu-id="c644f-238">Re-run the previous command for each mailbox that contains the spilled data, by replacing the value for the Identity parameter; for example:</span></span>

    ```
    Search-Mailbox -Identity sarad@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

    ```
    Search-Mailbox -Identity janets@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

   ```
   Search-Mailbox -Identity pilarp@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
   ```
  
<span data-ttu-id="c644f-239">如前面所述，您还可以创建[powershell 脚本](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6)并运行对邮箱的列表，以便该脚本将删除每个邮箱中的溅入的数据。</span><span class="sxs-lookup"><span data-stu-id="c644f-239">As previously stated, you can also create a [powershell script](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6) and run it against a list of mailboxes so that the script deletes the spilled data in each mailbox.</span></span>
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a><span data-ttu-id="c644f-240">步骤 8： 验证，提供身份证明删除，并审核</span><span class="sxs-lookup"><span data-stu-id="c644f-240">Step 8: Verify, provide a proof of deletion, and audit</span></span>

<span data-ttu-id="c644f-p131">工作流来管理数据泄漏事件中的最后一步是确认溅入的数据被永久删除从邮箱通过转到电子数据展示事例并重新运行用于删除该数据，以确认没有结果 ar 同一个搜索查询返回的 e。确认已被永久移除溅入的数据后，可以将报表导出并将其作为证明删除包含 （以及原始报告）。然后，您可以[关闭这种情况](ediscovery-cases.md#optional-step-9-close-a-case)，将使您能够重新打开它，如果将来引用到它。此外，还可以恢复邮箱为其以前的状态，删除用于查找溅入的数据，并搜索审核记录的任务管理数据泄漏事件时执行的搜索查询。</span><span class="sxs-lookup"><span data-stu-id="c644f-p131">The final step in the workflow to manage a data spillage incident is to verify that the spilled data was permanently removed from the mailbox by going to the eDiscovery case and re-running the same search query that was used to delete that data to confirm that no results are returned. After you confirm the spilled data has been permanently removed, you can export a report and include it (along with the original report) as a proof of deletion. Then you can [close the case](ediscovery-cases.md#optional-step-9-close-a-case), which will allow you to re-open it if you have refer to it in the future. Additionally, you can also revert mailboxes to their previous state, delete the search query used to find the spilled data, and search for auditing records of tasks performed when managing the data spillage incident.</span></span> 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a><span data-ttu-id="c644f-245">还原到其以前的状态的邮箱</span><span class="sxs-lookup"><span data-stu-id="c644f-245">Reverting the mailboxes to their previous state</span></span>

<span data-ttu-id="c644f-p132">如果您已经更改准备邮箱溅入的数据被删除之前的步骤 6 中的任何邮箱配置，您需要将其还原为其以前的状态。请参阅"步骤 5： 将恢复其先前状态的邮箱"中[删除在可恢复项目文件夹中的基于云的邮箱的保留的项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-5-revert-the-mailbox-to-its-previous-state)。</span><span class="sxs-lookup"><span data-stu-id="c644f-p132">If you changed any mailbox configuration in Step 6 to prepare the mailboxes before the spilled data was deleted, you will need to revert them to their previous state. See "Step 5: Revert the mailbox to its previous state" in [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-5-revert-the-mailbox-to-its-previous-state).</span></span>
  
### <a name="deleting-the-search-query"></a><span data-ttu-id="c644f-248">删除搜索查询</span><span class="sxs-lookup"><span data-stu-id="c644f-248">Deleting the search query</span></span>

<span data-ttu-id="c644f-249">如果您创建和使用在步骤 3 中的搜索查询中的关键字包含的所有实际溅入数据的一些，应删除的搜索查询，以防止进一步数据泄漏。</span><span class="sxs-lookup"><span data-stu-id="c644f-249">If the keywords in the search query that you created and used in Step 3 contains some of all of the actual spilled data, you should delete the search query to prevent further data spillage.</span></span>
  
1. <span data-ttu-id="c644f-250">中安全性和合规性中心中，打开电子数据展示事例，转到**搜索**页上，然后选择适当的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="c644f-250">In the Security & Compliance Center, open the eDiscovery case, go to the **Search** page, and select the appropriate content search.</span></span>
    
2. <span data-ttu-id="c644f-251">在弹出页上，单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="c644f-251">On the flyout page, click **Delete**.</span></span>

    ![选择搜索，然后单击弹出页上的删除](media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a><span data-ttu-id="c644f-253">审核数据泄漏调查过程</span><span class="sxs-lookup"><span data-stu-id="c644f-253">Auditing the data spillage investigation process</span></span>

<span data-ttu-id="c644f-p133">您可以搜索在调查期间已执行的电子数据展示活动的 Office 365 审核日志。您还可以搜索审核日志来返回审核记录运行**搜索邮箱 DeleteContent**命令以删除溅入的数据时创建的。有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c644f-p133">You can search the Office 365 audit log for the eDiscovery activities that were performed during the investigation. You can also search the audit log to return the audit records that were created when you ran the **Search-Mailbox -DeleteContent** command to delete the spilled data. For more information, see:</span></span>

- [<span data-ttu-id="c644f-257">在 Office 365 安全&amp;合规中心搜索审核日志</span><span class="sxs-lookup"><span data-stu-id="c644f-257">Search the audit log in the Office 365 Security &amp; Compliance Center</span></span>](search-the-audit-log-in-security-and-compliance.md)

- [<span data-ttu-id="c644f-258">Office 365 审核日志中的电子数据展示活动搜索</span><span class="sxs-lookup"><span data-stu-id="c644f-258">Search for eDiscovery activities in the Office 365 audit log</span></span>](search-for-ediscovery-activities-in-the-audit-log.md)

- <span data-ttu-id="c644f-259">请参阅有关如何搜索审核记录与 Exchange Online 中运行 cmdlet 的指南[搜索审核日志在 Office 365 安全性和合规性中心](search-the-audit-log-in-security-and-compliance.md#audited-activities)中的"审核活动-Exchange 管理员审核日志"部分。</span><span class="sxs-lookup"><span data-stu-id="c644f-259">See the "Audited activities - Exchange admin audit log " section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities) for guidance about how to search for audit records related to running cmdlets in Exchange Online.</span></span>
  


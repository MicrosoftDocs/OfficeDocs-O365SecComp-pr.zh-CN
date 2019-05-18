---
title: Microsoft 365 中的数据调查 (预览) 发布说明
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文介绍了 Microsoft 365 中的新数据调查 (预览版) 工具。
ms.openlocfilehash: 200b1c6c08d0fdb1c4af5da59fa75836b4b1fab3
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150894"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a><span data-ttu-id="19318-103">Microsoft 365 中的数据调查 (预览) 发布说明</span><span class="sxs-lookup"><span data-stu-id="19318-103">Release notes for Data Investigations (Preview) in Microsoft 365</span></span>

<span data-ttu-id="19318-104">您可以使用 Microsoft 365 中的新数据调查 (预览版) 工具对数据相关事件进行会审、调查和补救, 如数据外泄事件或内部调查。</span><span class="sxs-lookup"><span data-stu-id="19318-104">You can use the new Data Investigations (Preview) tool in in Microsoft 365 to triage, investigate, and remediate data related incidents, such as a data spillage incident or an internal investigation.</span></span> <span data-ttu-id="19318-105">数据调查的公共预览为您提供了对即将推出的功能和更新的早期访问权限。</span><span class="sxs-lookup"><span data-stu-id="19318-105">The Public Preview of Data Investigations provides you with early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="19318-106">若要尽早访问最新功能, 请在 Security & 合规性中心中创建一个新的数据调查 (预览版) 调查。</span><span class="sxs-lookup"><span data-stu-id="19318-106">To get early access to the newest features, create a new investigation in Data Investigations (Preview) in the Security & Compliance Center.</span></span> <span data-ttu-id="19318-107">若要了解如何操作, 请参阅[在 Microsoft 365 中管理数据外泄事件](manage-data-spillage-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="19318-107">To learn how, see [Manage a data spillage incident in Microsoft 365](manage-data-spillage-incidents.md).</span></span>

## <a name="whats-new"></a><span data-ttu-id="19318-108">新增功能</span><span class="sxs-lookup"><span data-stu-id="19318-108">What’s new</span></span> 

- <span data-ttu-id="19318-109">**调查**-您可以通过创建调查来对搜索和事件进行分组。</span><span class="sxs-lookup"><span data-stu-id="19318-109">**Investigations** - You can group searches and incidents by creating an investigation.</span></span> <span data-ttu-id="19318-110">通过添加或删除成员来管理可访问调查的人员。</span><span class="sxs-lookup"><span data-stu-id="19318-110">Manage who can access the investigation by adding or removing members.</span></span>  <span data-ttu-id="19318-111">您还可以选择并标记您喜爱的调查。</span><span class="sxs-lookup"><span data-stu-id="19318-111">You can also select and mark your favorite investigations.</span></span> <span data-ttu-id="19318-112">使用新仪表板跟踪和监控调查中和跨调查的活动。</span><span class="sxs-lookup"><span data-stu-id="19318-112">Track and monitor activity within and across investigations using new dashboards.</span></span> <span data-ttu-id="19318-113">完成调查后, 可以关闭或删除它。</span><span class="sxs-lookup"><span data-stu-id="19318-113">After you complete your investigation, you can close or delete it.</span></span>

- <span data-ttu-id="19318-114">**感兴趣的人**–当您将用户添加到调查中的人时, 您可以查看他们的邮箱、OneDrive for business 帐户和 Microsoft 团队网站。</span><span class="sxs-lookup"><span data-stu-id="19318-114">**People of interest** – When you add users to investigations as people of interest, you can see their mailbox, OneDrive for Business account, and Microsoft Teams sites.</span></span> <span data-ttu-id="19318-115">您可以使用它们来限定调查内容搜索的范围。</span><span class="sxs-lookup"><span data-stu-id="19318-115">You can use them to scope your investigative content searches.</span></span> <span data-ttu-id="19318-116">若要进一步调查感兴趣的人员, 您还可以查看与 Office 365 和其他 Microsoft 服务中的活动相关的审核记录。</span><span class="sxs-lookup"><span data-stu-id="19318-116">To further investigate a person of interest, you can also view audit records related to their activities in Office 365 and other Microsoft services.</span></span>

- <span data-ttu-id="19318-117">**搜索**–使用各种搜索条件创建组织范围的搜索。</span><span class="sxs-lookup"><span data-stu-id="19318-117">**Searches** – Create a organization-wide search using various search condition.</span></span> <span data-ttu-id="19318-118">如果您知道要搜索的用户或网站, 可以通过将这些用户添加为感兴趣的人员或在 "搜索创建向导" 中指定网站位置来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="19318-118">If you know users or sites that you want to search, you can do so by adding those users as people of interest or specifying site locations in search creation wizard.</span></span> 

- <span data-ttu-id="19318-119">**证据**–创建新的证据集并添加要查看的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="19318-119">**Evidence** – Create a new evidence set and add search results that you want to review.</span></span> <span data-ttu-id="19318-120">您可以查看各个文档、批注以留下调查说明, 以及导出结果以移到不同的环境。</span><span class="sxs-lookup"><span data-stu-id="19318-120">You can review individual documents, annotate to leave investigation notes, and export results to move to a different environment.</span></span> 

- <span data-ttu-id="19318-121">**审阅**–使用本机、文本和近本机视图查看添加到事件中的文档。</span><span class="sxs-lookup"><span data-stu-id="19318-121">**Review** – Use a native, text, and near-native views to review the documents added to an incident.</span></span> <span data-ttu-id="19318-122">您还可以将分析应用于文档以按重复项、电子邮件线索和主题对项目进行分组, 这有助于协助您复查事件。</span><span class="sxs-lookup"><span data-stu-id="19318-122">You can also apply analytics to documents to group items by duplicates, email threads, and themes, which can help assist your review of the incident.</span></span> 

- <span data-ttu-id="19318-123">**密文、标记和批注**–在审阅文档时设置密文、应用标记和批注。</span><span class="sxs-lookup"><span data-stu-id="19318-123">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="19318-124">**高级索引**–如果有任何部分已编制索引的项目, 则将按需重新编制索引, 以便所有数据都可供搜索。</span><span class="sxs-lookup"><span data-stu-id="19318-124">**Advanced indexing** – If there are any partially indexed items, they will be re-indexed on demand so that all data will be available for searching.</span></span>

- <span data-ttu-id="19318-125">**错误修正**–修正或下载处理错误。</span><span class="sxs-lookup"><span data-stu-id="19318-125">**Error remediation** – Remediate or download processing errors.</span></span> <span data-ttu-id="19318-126">这包括对大型文件类型的补救性支持、受密码保护的文件以及与索引错误相关的其他问题。</span><span class="sxs-lookup"><span data-stu-id="19318-126">This includes remediation support for large file types, password protected files, and other issues related to indexing errors.</span></span> 

- <span data-ttu-id="19318-127">**作业**–跟踪长时间运行的进程的状态。</span><span class="sxs-lookup"><span data-stu-id="19318-127">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="19318-128">**硬删除邮箱项目**-在紧急情况下, 您可能需要永久删除错放的项目。</span><span class="sxs-lookup"><span data-stu-id="19318-128">**Hard-delete mailbox items** - In urgent situations, you may need to permanently delete misplaced items.</span></span> <span data-ttu-id="19318-129">为此, 您可以在安全 & 合规中心 PowerShell 中运行**new-compliancesearchaction-PurgeType HardDelete**命令, 以从邮箱中永久删除项目。</span><span class="sxs-lookup"><span data-stu-id="19318-129">To do this, you can run the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell to permanently remove items from mailboxes.</span></span> <span data-ttu-id="19318-130">有关详细信息, 请参阅[new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction)。</span><span class="sxs-lookup"><span data-stu-id="19318-130">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction).</span></span>

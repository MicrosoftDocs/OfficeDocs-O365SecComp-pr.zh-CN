---
title: 高级电子数据展示的发行说明 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文包含适用于高级电子数据展示的发行说明 (预览)。
ms.openlocfilehash: 32a02c16fd30e740fcc6e1c99b46775b97590a28
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240937"
---
# <a name="release-notes-for-advanced-ediscovery-preview"></a><span data-ttu-id="406bf-103">高级电子数据展示的发行说明 (预览)</span><span class="sxs-lookup"><span data-stu-id="406bf-103">Release notes for Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="406bf-104">高级电子数据展示的公共预览计划是提前获取即将推出的功能和更新的方法。</span><span class="sxs-lookup"><span data-stu-id="406bf-104">The Public Preview program for Advanced eDiscovery is the way to get early access to the upcoming functionality and updates.</span></span> <span data-ttu-id="406bf-105">若要尽早访问最新功能, 只需在 Office 365 安全 & 合规中心中创建和使用高级电子数据展示 (预览版) 事例即可。</span><span class="sxs-lookup"><span data-stu-id="406bf-105">To get early access to the newest features, just create and use an Advanced eDiscovery (Preview) case in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="406bf-106">请参阅[创建新事例](create-new-ediscovery-case.md)。</span><span class="sxs-lookup"><span data-stu-id="406bf-106">See [Create a new case](create-new-ediscovery-case.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="406bf-107">已知问题</span><span class="sxs-lookup"><span data-stu-id="406bf-107">Known issues</span></span>

<span data-ttu-id="406bf-108">**Microsoft Forms**</span><span class="sxs-lookup"><span data-stu-id="406bf-108">**Microsoft Forms**</span></span>

- <span data-ttu-id="406bf-109">在将高级电子数据展示 (预览) 中的搜索工具用于搜索保管人邮箱时, 与在2019年1月31日之前创建的表单对应的数据将不可搜索。</span><span class="sxs-lookup"><span data-stu-id="406bf-109">The data corresponding to a form created before January 31, 2019 will not be searchable when using the Search tool in Advanced eDiscovery (Preview) to search custodian mailboxes.</span></span> <span data-ttu-id="406bf-110">在此日期之后创建的表单可供搜索。</span><span class="sxs-lookup"><span data-stu-id="406bf-110">Forms created after this date will be available to search.</span></span>

- <span data-ttu-id="406bf-111">用户创建的表单仍可以接收响应, 即使创建该表单的用户被删除也是如此。</span><span class="sxs-lookup"><span data-stu-id="406bf-111">A form created by a user can still receive responses even after the user who created the Form is deleted.</span></span> <span data-ttu-id="406bf-112">但是, 当使用高级电子数据展示 (预览) 中的搜索工具搜索保管人邮箱时, 这些响应的相应数据 (在保管人邮箱删除之后发生) 将不可搜索。</span><span class="sxs-lookup"><span data-stu-id="406bf-112">However, the corresponding data for those responses (that occurred after the custodian mailbox was deleted) will not be searchable when using the Search tool in Advanced eDiscovery (Preview) to search custodian mailboxes.</span></span>
 
<span data-ttu-id="406bf-113">**Microsoft Sway**</span><span class="sxs-lookup"><span data-stu-id="406bf-113">**Microsoft Sway**</span></span>

- <span data-ttu-id="406bf-114">如果用户在为该 sway 的所有者删除用户帐户之前编辑 sway, 则在使用高级电子数据展示 (预览) 中的搜索工具搜索保管人邮箱时, 这些更改可能无法搜索。</span><span class="sxs-lookup"><span data-stu-id="406bf-114">If a user edits a sway just prior to the deletion of the user account for the owner of that sway, then those changes may not be be searchable when using the Search tool in Advanced eDiscovery (Preview) to search custodian mailboxes.</span></span> <span data-ttu-id="406bf-115">sway 会在收到已删除帐户的信号时立即阻止对该 sway 的更改。</span><span class="sxs-lookup"><span data-stu-id="406bf-115">Sway blocks changes to to a sway as soon as it receives a signal that the account was deleted.</span></span> <span data-ttu-id="406bf-116">但是, 在收到此信号之前, 可以编辑 sway 的可能性很小。</span><span class="sxs-lookup"><span data-stu-id="406bf-116">However, there's a small chance that a sway can be edited before this signal is received.</span></span>

## <a name="issues-fixed-in-this-release"></a><span data-ttu-id="406bf-117">此版本中修复的问题</span><span class="sxs-lookup"><span data-stu-id="406bf-117">Issues fixed in this release</span></span>

- <span data-ttu-id="406bf-118">DCR: 未编制索引的项目和孤立项目的异常处理</span><span class="sxs-lookup"><span data-stu-id="406bf-118">DCR: Exception handling for unindexed items and orphaned items</span></span>
- <span data-ttu-id="406bf-119">DCR: 保留通知</span><span class="sxs-lookup"><span data-stu-id="406bf-119">DCR: Hold notifications</span></span>
- <span data-ttu-id="406bf-120">DCR: 电子数据展示中的保管人</span><span class="sxs-lookup"><span data-stu-id="406bf-120">DCR: Custodians in eDiscovery</span></span>

## <a name="whats-new"></a><span data-ttu-id="406bf-121">新增功能</span><span class="sxs-lookup"><span data-stu-id="406bf-121">What’s new</span></span>

- <span data-ttu-id="406bf-122">**安全 & 合规性中心中重新设计的导航**-高级电子数据展示 (预览) 具有新的外观和感觉。</span><span class="sxs-lookup"><span data-stu-id="406bf-122">**Redesigned navigation in the Security & Compliance Center** – Advanced eDiscovery (Preview) has a new look and feel.</span></span> <span data-ttu-id="406bf-123">使用高级电子数据展示 (预览) 来管理更多的事例工作流。</span><span class="sxs-lookup"><span data-stu-id="406bf-123">Use Advanced eDiscovery (Preview) to manage more of your case workflow.</span></span>

- <span data-ttu-id="406bf-124">**案例管理**–还提供了对新事例类型的其他支持。</span><span class="sxs-lookup"><span data-stu-id="406bf-124">**Case management** – There’s additional support for new case types.</span></span> <span data-ttu-id="406bf-125">您还可以选择并保存最近和喜欢的案例。</span><span class="sxs-lookup"><span data-stu-id="406bf-125">You can also select and save your recent and favorite cases.</span></span> <span data-ttu-id="406bf-126">使用新仪表板跟踪和监控各个事例中的活动。</span><span class="sxs-lookup"><span data-stu-id="406bf-126">Track and monitor activity within and across cases using new dashboards.</span></span>

- <span data-ttu-id="406bf-127">**保管人管理**–在某个情况下将用户添加和删除为数据保管人。</span><span class="sxs-lookup"><span data-stu-id="406bf-127">**Custodian management** – Add and remove users as data custodians within a case.</span></span>

- <span data-ttu-id="406bf-128">**Exchange、onedrive 和团队集成**–自动将用户的当前邮箱、OneDrive for business 帐户和 Microsoft 团队网站添加到一个案例。</span><span class="sxs-lookup"><span data-stu-id="406bf-128">**Exchange, OneDrive, and Teams Integration** – Automatically add a user’s current mailbox, OneDrive for Business account, and Microsoft Teams sites to a case.</span></span> 

- <span data-ttu-id="406bf-129">**保管人通信**–代表你的组织发送和管理法律封存通知。</span><span class="sxs-lookup"><span data-stu-id="406bf-129">**Custodian communications** – Send and manage legal hold notifications on behalf of your organization.</span></span>

- <span data-ttu-id="406bf-130">**保管人门户**–用于保管人的新门户, 可访问他们的活动保留通知。</span><span class="sxs-lookup"><span data-stu-id="406bf-130">**Custodian portal** – New portal for custodians to access their active hold notices.</span></span>

- <span data-ttu-id="406bf-131">**深度索引**–根据需要重新对部分索引项进行爬网。</span><span class="sxs-lookup"><span data-stu-id="406bf-131">**Deep indexing** – Re-crawl partially indexed items on demand.</span></span>

- <span data-ttu-id="406bf-132">**错误修正**–修正或下载处理错误;这包括对大型文件类型、受密码保护的文件等的补救性支持。</span><span class="sxs-lookup"><span data-stu-id="406bf-132">**Error remediation** – Remediate or download processing errors; this include remediation support for large file types, password protected files, and more.</span></span> 

- <span data-ttu-id="406bf-133">**搜索改进**-通过确定保管人和/或位置来创建搜索。</span><span class="sxs-lookup"><span data-stu-id="406bf-133">**Improvements to search** – Create a search by identifying custodians and/or locations.</span></span>

- <span data-ttu-id="406bf-134">**工作集**–管理、跟踪和审核一组静态文档。</span><span class="sxs-lookup"><span data-stu-id="406bf-134">**Working sets** – Manage, track, and audit static sets of documents.</span></span>

- <span data-ttu-id="406bf-135">**审阅**–使用本机、文本和近本机视图查看添加到工作集的文档。</span><span class="sxs-lookup"><span data-stu-id="406bf-135">**Review** – Use a native, text, and near-native view to review documents added to your working set.</span></span>

- <span data-ttu-id="406bf-136">**密文、标记和批注**–在审阅文档时设置密文、应用标记和批注。</span><span class="sxs-lookup"><span data-stu-id="406bf-136">**Redact, tag, and annotate** – Redact text, apply tags, and make annotations as you review documents.</span></span>
  
- <span data-ttu-id="406bf-137">**分析-已通过分析-** 利用电子数据展示分析在工作集中查找、搜索和挑选结果。</span><span class="sxs-lookup"><span data-stu-id="406bf-137">**Analytics-powered review**– Leverage eDiscovery analytics to find, search, and cull results within a working set.</span></span>

- <span data-ttu-id="406bf-138">**作业**–跟踪长时间运行的进程的状态。</span><span class="sxs-lookup"><span data-stu-id="406bf-138">**Jobs** – Track status of long-running processes.</span></span>

- <span data-ttu-id="406bf-139">**新的审核活动**–跟踪并查看高级电子数据展示的新审核活动。</span><span class="sxs-lookup"><span data-stu-id="406bf-139">**New audit activities** – Track and view new audit activity for Advanced eDiscovery.</span></span>

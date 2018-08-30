---
title: Office 365 中搜索审核日志中的用户和管理员的活动
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: Office 365 审核日志是统一的审核日志。为什么统一的审核日志？因为大多数您组织的 Office 365 服务中的事件订阅中的可搜索的单个审核日志记录。这意味着您可以搜索用户和管理活动，这些服务：
ms.openlocfilehash: 7a6a552b1d2569c9e21fe20b39d474dafc026172
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525257"
---
# <a name="search-the-audit-log-for-user-and-admin-activity-in-office-365"></a><span data-ttu-id="5a3a2-106">Office 365 中搜索审核日志中的用户和管理员的活动</span><span class="sxs-lookup"><span data-stu-id="5a3a2-106">Search the audit log for user and admin activity in Office 365</span></span>

<span data-ttu-id="5a3a2-p102">Office 365 审核日志是统一的审核日志。为什么统一的审核日志？因为大多数您组织的 Office 365 服务中的事件订阅中的可搜索的单个审核日志记录。这意味着您可以搜索用户和管理活动，这些服务：</span><span class="sxs-lookup"><span data-stu-id="5a3a2-p102">The Office 365 audit log is a unified audit log. Why a unified audit log? Because events from most Office 365 services that you're organization subscribes to are recorded in a single audit log that you can search. That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="5a3a2-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="5a3a2-111">SharePoint</span></span>
- <span data-ttu-id="5a3a2-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="5a3a2-112">OneDrive</span></span>
- <span data-ttu-id="5a3a2-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="5a3a2-113">Exchange</span></span>
- <span data-ttu-id="5a3a2-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5a3a2-114">Azure Active Directory</span></span>
- <span data-ttu-id="5a3a2-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a3a2-115">Microsoft Teams</span></span>
- <span data-ttu-id="5a3a2-116">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="5a3a2-116">eDiscovery</span></span>
- <span data-ttu-id="5a3a2-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="5a3a2-117">Power BI</span></span>
- <span data-ttu-id="5a3a2-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="5a3a2-118">Yammer</span></span>
- <span data-ttu-id="5a3a2-119">Sway</span><span class="sxs-lookup"><span data-stu-id="5a3a2-119">Sway</span></span>
- <span data-ttu-id="5a3a2-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="5a3a2-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="5a3a2-121">设置审核</span><span class="sxs-lookup"><span data-stu-id="5a3a2-121">Set up auditing</span></span>
  
<span data-ttu-id="5a3a2-122">没有几件事，您需要执行操作之前，您可以搜索 Office 365 审核日志。</span><span class="sxs-lookup"><span data-stu-id="5a3a2-122">There's few things you have to do before you can search the Office 365 audit log.</span></span>
  
- <span data-ttu-id="5a3a2-123">[启用审核日志搜索](turn-audit-log-search-on-or-off.md)开始，可搜索的记录事件</span><span class="sxs-lookup"><span data-stu-id="5a3a2-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="5a3a2-124">[启用邮箱审核](enable-mailbox-auditing.md)，这样您可以搜索邮箱相关的事件;例如，当用户登录到其邮箱或清除项目从其可恢复项目文件夹</span><span class="sxs-lookup"><span data-stu-id="5a3a2-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="5a3a2-125">搜索审核日志</span><span class="sxs-lookup"><span data-stu-id="5a3a2-125">Search the audit log</span></span>
  
<span data-ttu-id="5a3a2-126">启用审核功能后，您搜索数百各个类型的多个 Office 365 服务中的事件。</span><span class="sxs-lookup"><span data-stu-id="5a3a2-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Office 365 services.</span></span>
  
- <span data-ttu-id="5a3a2-127">用户和管理活动的[搜索审核日志](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="5a3a2-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="5a3a2-128">搜索结果中包含每个审核记录中的[了解详细的属性](detailed-properties-in-the-office-365-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="5a3a2-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="5a3a2-129">管理员和合规性管理员执行[电子数据展示相关的活动搜索](search-for-ediscovery-activities-in-the-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="5a3a2-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 

---
title: 在 "审核日志中查找 Office 365 中的用户和管理员活动"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MOE150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: 'Office 365 审核日志是一个统一的审核日志。 为什么要使用统一审核日志？ 由于您组织的大多数 Office 365 服务中的事件将记录在可以搜索的单个审核日志中。 这意味着您可以在这些服务中搜索用户和管理员活动:'
ms.openlocfilehash: 1d3f45d24a8d1a83c20f5d36b12ced761e00f936
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158774"
---
# <a name="search-the-audit-log-for-user-and-admin-activity-in-office-365"></a><span data-ttu-id="324eb-106">在 "审核日志中查找 Office 365 中的用户和管理员活动"</span><span class="sxs-lookup"><span data-stu-id="324eb-106">Search the audit log for user and admin activity in Office 365</span></span>

<span data-ttu-id="324eb-107">Office 365 审核日志是一个统一的审核日志。</span><span class="sxs-lookup"><span data-stu-id="324eb-107">The Office 365 audit log is a unified audit log.</span></span> <span data-ttu-id="324eb-108">为什么要使用统一审核日志？</span><span class="sxs-lookup"><span data-stu-id="324eb-108">Why a unified audit log?</span></span> <span data-ttu-id="324eb-109">由于您组织的大多数 Office 365 服务中的事件将记录在可以搜索的单个审核日志中。</span><span class="sxs-lookup"><span data-stu-id="324eb-109">Because events from most Office 365 services that you're organization subscribes to are recorded in a single audit log that you can search.</span></span> <span data-ttu-id="324eb-110">这意味着您可以在这些服务中搜索用户和管理员活动:</span><span class="sxs-lookup"><span data-stu-id="324eb-110">That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="324eb-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="324eb-111">SharePoint</span></span>
- <span data-ttu-id="324eb-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="324eb-112">OneDrive</span></span>
- <span data-ttu-id="324eb-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="324eb-113">Exchange</span></span>
- <span data-ttu-id="324eb-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="324eb-114">Azure Active Directory</span></span>
- <span data-ttu-id="324eb-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="324eb-115">Microsoft Teams</span></span>
- <span data-ttu-id="324eb-116">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="324eb-116">eDiscovery</span></span>
- <span data-ttu-id="324eb-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="324eb-117">Power BI</span></span>
- <span data-ttu-id="324eb-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="324eb-118">Yammer</span></span>
- <span data-ttu-id="324eb-119">Sway</span><span class="sxs-lookup"><span data-stu-id="324eb-119">Sway</span></span>
- <span data-ttu-id="324eb-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="324eb-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="324eb-121">设置审核</span><span class="sxs-lookup"><span data-stu-id="324eb-121">Set up auditing</span></span>
  
<span data-ttu-id="324eb-122">在可以搜索 Office 365 审核日志之前, 您必须执行的操作很少。</span><span class="sxs-lookup"><span data-stu-id="324eb-122">There's few things you have to do before you can search the Office 365 audit log.</span></span>
  
- <span data-ttu-id="324eb-123">[打开审核日志搜索](turn-audit-log-search-on-or-off.md)以开始记录可搜索的事件</span><span class="sxs-lookup"><span data-stu-id="324eb-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="324eb-124">[启用邮箱审核](enable-mailbox-auditing.md), 以便您可以搜索与邮箱相关的事件;例如, 当用户登录到其邮箱或清除其 "可恢复的项目" 文件夹中的项目时</span><span class="sxs-lookup"><span data-stu-id="324eb-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="324eb-125">搜索审核日志</span><span class="sxs-lookup"><span data-stu-id="324eb-125">Search the audit log</span></span>
  
<span data-ttu-id="324eb-126">启用审核后, 可以从多个 Office 365 服务中搜索数百个不同类型的事件。</span><span class="sxs-lookup"><span data-stu-id="324eb-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Office 365 services.</span></span>
  
- <span data-ttu-id="324eb-127">[在审核日志中搜索](search-the-audit-log-in-security-and-compliance.md)用户和管理员活动</span><span class="sxs-lookup"><span data-stu-id="324eb-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="324eb-128">了解搜索结果中包含的每个审核记录[的详细属性](detailed-properties-in-the-office-365-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="324eb-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="324eb-129">搜索由管理员和合规经理执行的[与电子数据展示相关的活动](search-for-ediscovery-activities-in-the-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="324eb-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 

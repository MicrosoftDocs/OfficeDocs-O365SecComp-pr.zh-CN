---
title: 调查 Office 365 云应用安全中的活动
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 15fa4545-28b4-4dd4-bf85-88e0926bd5fc
description: '使用 office 365 云应用安全性, 可以通过查看和调查活动和帐户来查看 Office 365 环境中发生的情况。 '
ms.openlocfilehash: 0cc3860d953b40b0b0c247af6fb2b157d1abb235
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254824"
---
# <a name="investigate-an-activity-in-office-365-cloud-app-security"></a><span data-ttu-id="3d72c-103">调查 Office 365 云应用安全中的活动</span><span class="sxs-lookup"><span data-stu-id="3d72c-103">Investigate an activity in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="3d72c-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="3d72c-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="3d72c-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="3d72c-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="3d72c-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="3d72c-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="3d72c-107">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3d72c-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="3d72c-108">开始评估</span><span class="sxs-lookup"><span data-stu-id="3d72c-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="3d72c-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="3d72c-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="3d72c-110">开始部署</span><span class="sxs-lookup"><span data-stu-id="3d72c-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="3d72c-111">你在这里!</span><span class="sxs-lookup"><span data-stu-id="3d72c-111">You are here!</span></span>  <br/> [<span data-ttu-id="3d72c-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3d72c-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="3d72c-113">office 365 云应用安全性适用于你的[office 365 审核日志](detailed-properties-in-the-office-365-audit-log.md)。</span><span class="sxs-lookup"><span data-stu-id="3d72c-113">Office 365 Cloud App Security works with your [Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md).</span></span> <span data-ttu-id="3d72c-114">使用 office 365 云应用安全性 (作为全局管理员或安全管理员), 您可以使用 "活动日志" 页查看组织使用 Office 365 的方式中的潜在问题。</span><span class="sxs-lookup"><span data-stu-id="3d72c-114">With Office 365 Cloud App Security, as a global administrator or security administrator, you can use the Activity log page to see potential issues in how your organization is using Office 365.</span></span>
  
## <a name="how-to-get-to-the-activity-log-page"></a><span data-ttu-id="3d72c-115">如何获取 "活动日志" 页</span><span class="sxs-lookup"><span data-stu-id="3d72c-115">How to get to the Activity log page</span></span>

1. <span data-ttu-id="3d72c-116">转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="3d72c-116">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="3d72c-117">在屏幕顶部的导航栏中, 选择 "**调查** \> **活动日志**"。</span><span class="sxs-lookup"><span data-stu-id="3d72c-117">In the navigation bar across the top of the screen, choose **Investigate** \> **Activity log**.</span></span><br/><span data-ttu-id="3d72c-118">![在 O365 CAS 门户中, 选择 "调查"。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span><span class="sxs-lookup"><span data-stu-id="3d72c-118">![In the O365 CAS portal, choose Investigate.](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)</span></span>
  
## <a name="review-and-investigate-activities"></a><span data-ttu-id="3d72c-119">查看和调查活动</span><span class="sxs-lookup"><span data-stu-id="3d72c-119">Review and investigate activities</span></span>

<span data-ttu-id="3d72c-120">在 "活动日志" 页上, 您可以查看使用 Office 365 的组织内发生的各种活动的列表。</span><span class="sxs-lookup"><span data-stu-id="3d72c-120">On the Activity log page, you can see a list of various activities that are taking place within your organization using Office 365.</span></span> <span data-ttu-id="3d72c-121">您可以使用整个屏幕顶部的筛选器来重点关注特定类型的活动或特定用户。</span><span class="sxs-lookup"><span data-stu-id="3d72c-121">You can use filters across the top of the screen to focus on a specific type of activity or a specific user.</span></span> <span data-ttu-id="3d72c-122">例如, 下图显示有关组织的 Office 365 管理员帐户的密码更改的信息:</span><span class="sxs-lookup"><span data-stu-id="3d72c-122">For example, the following image shows information about an organization's Office 365 admin account's password change:</span></span>
  
![在 Office 365 Cloud App Security 中, 选择\> "调查活动日志"。](media/5d54600c-59cd-4f33-b4f0-29b75c37baae.png)
  
<span data-ttu-id="3d72c-124">查看活动日志中的每个项目时, 可以单击省略号以查找其他相关活动。</span><span class="sxs-lookup"><span data-stu-id="3d72c-124">As you look at each item in the Activity log, you can click the ellipses to find other related activities.</span></span> <span data-ttu-id="3d72c-125">例如, 可以从相同的 IP 地址或同一国家/地区查看相同类型的其他活动。</span><span class="sxs-lookup"><span data-stu-id="3d72c-125">For example, you can view other activities of the same type, from the same IP address, or from the same country/region.</span></span>
  
<span data-ttu-id="3d72c-126">您也可以查看许多其他类型的活动的相关信息。</span><span class="sxs-lookup"><span data-stu-id="3d72c-126">You can view information about many other kinds of activities, too.</span></span> <span data-ttu-id="3d72c-127">例如, 以下是您可以在活动日志中查看的一些活动:</span><span class="sxs-lookup"><span data-stu-id="3d72c-127">For example, here are some of the activities you can view in the Activity log:</span></span>
  
- <span data-ttu-id="3d72c-128">添加到组或从组中删除的成员</span><span class="sxs-lookup"><span data-stu-id="3d72c-128">Members added to or removed from groups</span></span>
    
- <span data-ttu-id="3d72c-129">用户许可证中的更改</span><span class="sxs-lookup"><span data-stu-id="3d72c-129">Changes in user licenses</span></span>
    
- <span data-ttu-id="3d72c-130">内部或外部共享的文件或文件夹</span><span class="sxs-lookup"><span data-stu-id="3d72c-130">Files or folders shared internally or externally</span></span>
    
- <span data-ttu-id="3d72c-131">已创建或删除的网站或网站集</span><span class="sxs-lookup"><span data-stu-id="3d72c-131">Created or deleted sites or site collections</span></span>
    
- <span data-ttu-id="3d72c-132">电子邮件转发规则</span><span class="sxs-lookup"><span data-stu-id="3d72c-132">Email forwarding rules</span></span>
    
<span data-ttu-id="3d72c-133">使用 "活动日志" 页面了解组织中的人员如何使用 Office 365 以及他们可能会遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="3d72c-133">Use the Activity log page to get acquainted with how people in your organization are using Office 365 and what issues they might be having along the way.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="3d72c-134">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3d72c-134">Next steps</span></span>

- [<span data-ttu-id="3d72c-135">查看 Office 365 云应用安全中的警报并执行相应操作</span><span class="sxs-lookup"><span data-stu-id="3d72c-135">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="3d72c-136">查看[Office 365 云应用安全性的利用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="3d72c-136">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


---
title: 调查 Office 365 云应用安全中的活动
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 15fa4545-28b4-4dd4-bf85-88e0926bd5fc
description: '与 Office 365 云应用程序安全性，您可以看到查看和调查活动和帐户的最新动态 Office 365 环境中。 '
ms.openlocfilehash: 03db572ebddbdf27371f8e6fd2f0cdd91c14a12f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524994"
---
# <a name="investigate-an-activity-in-office-365-cloud-app-security"></a><span data-ttu-id="e1650-103">调查 Office 365 云应用安全中的活动</span><span class="sxs-lookup"><span data-stu-id="e1650-103">Investigate an activity in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="e1650-104">评估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="e1650-104">****Evaluation** \>**</span></span>|<span data-ttu-id="e1650-105">规划 * *\>**</span><span class="sxs-lookup"><span data-stu-id="e1650-105">****Planning** \>**</span></span>|<span data-ttu-id="e1650-106">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="e1650-106">****Deployment** \>**</span></span>|<span data-ttu-id="e1650-107">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="e1650-107">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="e1650-108">启动评估</span><span class="sxs-lookup"><span data-stu-id="e1650-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="e1650-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="e1650-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="e1650-110">开始部署</span><span class="sxs-lookup"><span data-stu-id="e1650-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="e1650-111">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="e1650-111">You are here!</span></span>  <br/> [<span data-ttu-id="e1650-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e1650-112">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="e1650-p101">Office 365 云应用程序安全性适用于您的[Office 365 审核日志](detailed-properties-in-the-office-365-audit-log.md)。与 Office 365 云应用程序安全性，作为全局管理员或安全管理员，您可以使用活动日志页以查看您的组织如何使用 Office 365 中的潜在问题。</span><span class="sxs-lookup"><span data-stu-id="e1650-p101">Office 365 Cloud App Security works with your [Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md). With Office 365 Cloud App Security, as a global administrator or security administrator, you can use the Activity log page to see potential issues in how your organization is using Office 365.</span></span>
  
## <a name="how-to-get-to-the-activity-log-page"></a><span data-ttu-id="e1650-115">如何获取活动日志页</span><span class="sxs-lookup"><span data-stu-id="e1650-115">How to get to the Activity log page</span></span>

1. <span data-ttu-id="e1650-p102">以全局管理员或 security 管理员程序中，转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。(请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。)</span><span class="sxs-lookup"><span data-stu-id="e1650-p102">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
2. <span data-ttu-id="e1650-118">安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。</span><span class="sxs-lookup"><span data-stu-id="e1650-118">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="e1650-119">选择**转到 Office 365 云应用程序安全性**。</span><span class="sxs-lookup"><span data-stu-id="e1650-119">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. <span data-ttu-id="e1650-121">在屏幕顶部导航栏中，选择**调查** \> **活动日志**。</span><span class="sxs-lookup"><span data-stu-id="e1650-121">In the navigation bar across the top of the screen, choose **Investigate** \> **Activity log**.</span></span>
    
    ![在 O365 CAS 门户中，选择调查。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
## <a name="review-and-investigate-activities"></a><span data-ttu-id="e1650-123">查看和调查活动</span><span class="sxs-lookup"><span data-stu-id="e1650-123">Review and investigate activities</span></span>

<span data-ttu-id="e1650-p103">在活动日志页中，您可以看到正在使用的 Office 365 组织内进行的各种活动的列表。您可以使用跨屏幕顶部筛选器重点介绍特定类型的活动或特定用户。例如下, 图显示了有关组织的 Office 365 管理员帐户的密码更改的信息：</span><span class="sxs-lookup"><span data-stu-id="e1650-p103">On the Activity log page, you can see a list of various activities that are taking place within your organization using Office 365. You can use filters across the top of the screen to focus on a specific type of activity or a specific user. For example, the following image shows information about an organization's Office 365 admin account's password change:</span></span>
  
![在 Office 365 云应用程序安全选择调查\>活动日志。](media/5d54600c-59cd-4f33-b4f0-29b75c37baae.png)
  
<span data-ttu-id="e1650-p104">查看活动日志中的每个项目时，您可以单击省略号查找其他相关的活动。例如，您可以查看相同的类型，从同一个 IP 地址，或相同的国家/地区从其他活动。</span><span class="sxs-lookup"><span data-stu-id="e1650-p104">As you look at each item in the Activity log, you can click the ellipses to find other related activities. For example, you can view other activities of the same type, from the same IP address, or from the same country/region.</span></span>
  
<span data-ttu-id="e1650-p105">您可以太查看关于许多其他类型的活动的信息。例如，下面是一些您可以查看活动日志中的活动：</span><span class="sxs-lookup"><span data-stu-id="e1650-p105">You can view information about many other kinds of activities, too. For example, here are some of the activities you can view in the Activity log:</span></span>
  
- <span data-ttu-id="e1650-132">添加或删除与组的成员</span><span class="sxs-lookup"><span data-stu-id="e1650-132">Members added to or removed from groups</span></span>
    
- <span data-ttu-id="e1650-133">用户许可证中的更改</span><span class="sxs-lookup"><span data-stu-id="e1650-133">Changes in user licenses</span></span>
    
- <span data-ttu-id="e1650-134">文件或文件夹内部或外部共享</span><span class="sxs-lookup"><span data-stu-id="e1650-134">Files or folders shared internally or externally</span></span>
    
- <span data-ttu-id="e1650-135">创建或删除网站或网站集</span><span class="sxs-lookup"><span data-stu-id="e1650-135">Created or deleted sites or site collections</span></span>
    
- <span data-ttu-id="e1650-136">电子邮件转发规则</span><span class="sxs-lookup"><span data-stu-id="e1650-136">Email forwarding rules</span></span>
    
<span data-ttu-id="e1650-137">一路将，使用活动日志页后，可以帮您的组织中的用户如何使用 Office 365 和内容问题它们可能会出现。</span><span class="sxs-lookup"><span data-stu-id="e1650-137">Use the Activity log page to get acquainted with how people in your organization are using Office 365 and what issues they might be having along the way.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="e1650-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e1650-138">Next steps</span></span>

- [<span data-ttu-id="e1650-139">查看 Office 365 云应用安全中的警报并执行相应操作</span><span class="sxs-lookup"><span data-stu-id="e1650-139">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="e1650-140">查看您[的 Office 365 云应用程序安全性的使用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="e1650-140">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


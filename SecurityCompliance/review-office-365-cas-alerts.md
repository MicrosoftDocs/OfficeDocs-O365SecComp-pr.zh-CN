---
title: 查看 Office 365 云应用安全中的警报并执行相应操作
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: 使用 Office 365 Cloud App Security 中的 "通知" 页面查看潜在问题并采取措施。 您可以取消或解决通知, 如有必要, 请挂起用户帐户。
ms.openlocfilehash: 701d80c3f890115c6c403fff21d2d0444d71c95a
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862464"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="c613b-104">查看 Office 365 云应用安全中的警报并执行相应操作</span><span class="sxs-lookup"><span data-stu-id="c613b-104">Review and take action on alerts in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="c613b-105">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c613b-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="c613b-106">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c613b-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="c613b-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="c613b-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="c613b-108">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="c613b-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="c613b-109">开始评估</span><span class="sxs-lookup"><span data-stu-id="c613b-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="c613b-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="c613b-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="c613b-111">开始部署</span><span class="sxs-lookup"><span data-stu-id="c613b-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="c613b-112">你在这里!</span><span class="sxs-lookup"><span data-stu-id="c613b-112">You are here!</span></span>  <br/> [<span data-ttu-id="c613b-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c613b-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="c613b-114">您可以使用 Office 365 Cloud App Security 中的 "通知" 页面查看潜在问题, 并在需要时执行操作。</span><span class="sxs-lookup"><span data-stu-id="c613b-114">You can use the Alerts page in Office 365 Cloud App Security to view potential issues and, if needed, take action.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c613b-115">若要执行本文中的任务, 您必须是全局管理员或安全管理员。</span><span class="sxs-lookup"><span data-stu-id="c613b-115">You must be a global administrator or security administrator to perform the tasks in this article.</span></span> <span data-ttu-id="c613b-116">请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c613b-116">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-to-get-to-the-alerts-page"></a><span data-ttu-id="c613b-117">如何转到 "通知" 页</span><span class="sxs-lookup"><span data-stu-id="c613b-117">How to get to the Alerts page</span></span>

1. <span data-ttu-id="c613b-118">转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="c613b-118">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="c613b-119">在屏幕顶部的导航栏中, 选择 "**通知**"。</span><span class="sxs-lookup"><span data-stu-id="c613b-119">In the navigation bar across the top of the screen, choose **Alerts**.</span></span><br/><span data-ttu-id="c613b-120">![在 "通知" 页面上, 您可以查看触发的警报以及执行的任何操作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span><span class="sxs-lookup"><span data-stu-id="c613b-120">![On the Alerts page, you can see alerts that were triggered and any actions taken.](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)</span></span>
 
> [!NOTE]
> <span data-ttu-id="c613b-121">云应用安全警报在 Office 365 Security & 合规中心 (转到**警报** > **查看警报**) 中也可见。</span><span class="sxs-lookup"><span data-stu-id="c613b-121">Cloud App Security alerts are also visible in the Office 365 Security & Compliance Center (go to **Alerts** > **View alerts**.</span></span> <span data-ttu-id="c613b-122">但是, 目前您必须在云应用安全门户和 Office 365 Security & 合规性中心中解决这些警报。</span><span class="sxs-lookup"><span data-stu-id="c613b-122">Currently, however, you must resolve these alerts in both the Cloud App Security portal and the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="c613b-123">若要了解详细信息, 请参阅[查看云应用安全警报](alert-policies.md#viewing-cloud-app-security-alerts)。)</span><span class="sxs-lookup"><span data-stu-id="c613b-123">To learn more, see [Viewing Cloud App Security alerts](alert-policies.md#viewing-cloud-app-security-alerts).)</span></span> 
 
## <a name="review-and-handle-alerts"></a><span data-ttu-id="c613b-124">查看和处理警报</span><span class="sxs-lookup"><span data-stu-id="c613b-124">Review and handle alerts</span></span>

<span data-ttu-id="c613b-125">警报可帮助您识别 Office 365 云环境中您可能想要进一步调查的活动。</span><span class="sxs-lookup"><span data-stu-id="c613b-125">Alerts help you identify activities in your Office 365 cloud environment that you might want to investigate further.</span></span> <span data-ttu-id="c613b-126">您可能还决定根据您看到的警报创建新策略或编辑现有策略。</span><span class="sxs-lookup"><span data-stu-id="c613b-126">You might also decide to create new policies or edit existing policies based on the alerts you see.</span></span> <span data-ttu-id="c613b-127">例如, 如果您看到管理员从奇怪的位置登录, 则可能决定设置一个策略, 以防止管理员从某些位置登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c613b-127">For example, if you see an administrator logging on from a strange location, you may decide to set up a policy that prevents administrators from signing in to Office 365 from certain locations.</span></span>
  
> [!TIP]
> <span data-ttu-id="c613b-128">您可以按**类别**或**严重性**筛选警报, 以便可以先管理最重要的警报。</span><span class="sxs-lookup"><span data-stu-id="c613b-128">You can filter the alerts by **Category** or by **Severity** so you can manage the most important ones first.</span></span> 
  
<span data-ttu-id="c613b-129">对于每个通知, 请查看导致其出现的原因, 以便您可以决定要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="c613b-129">For each alert, look into what caused it so you can decide what action to take.</span></span> <span data-ttu-id="c613b-130">若要查看有关警报的更多详细信息, 并执行操作 (如解决警报或挂起用户帐户), 请选择 "通知" 以打开 "详细信息" 页。</span><span class="sxs-lookup"><span data-stu-id="c613b-130">To see more details about an alert and to take action, such as resolving the alert or suspending a users account, choose the alert to open a details page.</span></span> <span data-ttu-id="c613b-131">在 "详细信息" 页上, 您可以查看与警报相关的活动日志、帐户和用户, 并执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="c613b-131">On the details page, you can review the activity log, accounts, and users that are related to the alert, and take actions such as the following:</span></span>
  
- <span data-ttu-id="c613b-132">**消除**如果警报为误报, 请将其关闭。</span><span class="sxs-lookup"><span data-stu-id="c613b-132">**Dismiss** If the alert was a false positive, dismiss it.</span></span> <span data-ttu-id="c613b-133">您可以选择添加注释, 说明为什么消除了它。</span><span class="sxs-lookup"><span data-stu-id="c613b-133">You can optionally add a comment explaining why you dismissed it.</span></span> 
    
- <span data-ttu-id="c613b-134">**解决警报**如果警报是由您知道不是威胁的活动触发的, 请对其进行解析。</span><span class="sxs-lookup"><span data-stu-id="c613b-134">**Resolve alert** If the alert was triggered by an activity that you know isn't a threat, resolve it.</span></span> <span data-ttu-id="c613b-135">您可以选择添加注释, 说明您解决它的原因。</span><span class="sxs-lookup"><span data-stu-id="c613b-135">You can optionally add a comment explaining why you resolved it.</span></span> 
    
- <span data-ttu-id="c613b-136">**挂起**如果您怀疑某个帐户上有未经授权登录, 例如, 当您知道该用户实际位于本地办公室时, 某人从其他国家/地区登录, 则可以在调查正在进行的操作时[挂起该帐户](suspend-or-restore-an-account-in-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="c613b-136">**Suspend** If you suspect unauthorized sign ins on an account, for example, someone signing in from another country when you know that person is physically at a local office, you can [suspend the account](suspend-or-restore-an-account-in-ocas.md) while you investigate what's going on.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="c613b-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c613b-137">Next steps</span></span>

- [<span data-ttu-id="c613b-138">调查活动</span><span class="sxs-lookup"><span data-stu-id="c613b-138">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="c613b-139">挂起或还原用户帐户</span><span class="sxs-lookup"><span data-stu-id="c613b-139">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- <span data-ttu-id="c613b-140">查看受支持的[Web 流量日志和数据源](web-traffic-logs-and-data-sources-for-ocas.md)的列表</span><span class="sxs-lookup"><span data-stu-id="c613b-140">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="c613b-141">查看[Office 365 云应用安全性的利用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="c613b-141">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


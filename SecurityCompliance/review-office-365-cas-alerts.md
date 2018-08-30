---
title: 查看 Office 365 云应用安全中的警报并执行相应操作
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
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: 使用在 Office 365 云应用程序安全性通知页上查看潜在问题并执行操作。可以关闭或解决通知，并有必要，暂停的用户帐户。
ms.openlocfilehash: 62431adc73354e573978781f120a11746aef08d9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524792"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="d18b9-104">查看 Office 365 云应用安全中的警报并执行相应操作</span><span class="sxs-lookup"><span data-stu-id="d18b9-104">Review and take action on alerts in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="d18b9-105">评估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="d18b9-105">****Evaluation** \>**</span></span>|<span data-ttu-id="d18b9-106">规划 * *\>**</span><span class="sxs-lookup"><span data-stu-id="d18b9-106">****Planning** \>**</span></span>|<span data-ttu-id="d18b9-107">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="d18b9-107">****Deployment** \>**</span></span>|<span data-ttu-id="d18b9-108">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="d18b9-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="d18b9-109">启动评估</span><span class="sxs-lookup"><span data-stu-id="d18b9-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="d18b9-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="d18b9-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="d18b9-111">开始部署</span><span class="sxs-lookup"><span data-stu-id="d18b9-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="d18b9-112">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="d18b9-112">You are here!</span></span>  <br/> [<span data-ttu-id="d18b9-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d18b9-113">Next steps</span></span>](#next-steps) <br/> |
   
<span data-ttu-id="d18b9-114">可以使用在 Office 365 云应用程序安全性通知页以查看潜在的问题，如果需要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="d18b9-114">You can use the Alerts page in Office 365 Cloud App Security to view potential issues and, if needed, take action.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d18b9-p102">您必须是要执行本文中的任务的全局管理员或 security 管理员程序。请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d18b9-p102">You must be a global administrator or security administrator to perform the tasks in this article. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="how-to-get-to-the-alerts-page"></a><span data-ttu-id="d18b9-117">如何获取通知页面</span><span class="sxs-lookup"><span data-stu-id="d18b9-117">How to get to the Alerts page</span></span>

1. <span data-ttu-id="d18b9-118">以全局管理员或 security 管理员程序中，转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d18b9-118">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="d18b9-119">安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。</span><span class="sxs-lookup"><span data-stu-id="d18b9-119">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="d18b9-120">选择**转到 Office 365 云应用程序安全性**。</span><span class="sxs-lookup"><span data-stu-id="d18b9-120">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. <span data-ttu-id="d18b9-122">在屏幕顶部导航栏中，选择**通知**。</span><span class="sxs-lookup"><span data-stu-id="d18b9-122">In the navigation bar across the top of the screen, choose **Alerts**.</span></span>
    
    ![在通知页中，您可以看到触发的通知和执行任何操作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
## <a name="review-and-handle-alerts"></a><span data-ttu-id="d18b9-124">查看并处理通知</span><span class="sxs-lookup"><span data-stu-id="d18b9-124">Review and handle alerts</span></span>

<span data-ttu-id="d18b9-p103">通知帮助您识别您可能想要进一步调查的 Office 365 云环境中的活动。您还可能决定创建新策略或编辑现有策略基于您看到通知。例如，如果您看到管理员从奇怪位置登录时，您可能决定阻止来自特定位置登录到 Office 365 管理员的策略设置。</span><span class="sxs-lookup"><span data-stu-id="d18b9-p103">Alerts help you identify activities in your Office 365 cloud environment that you might want to investigate further. You might also decide to create new policies or edit existing policies based on the alerts you see. For example, if you see an administrator logging on from a strange location, you may decide to set up a policy that prevents administrators from signing in to Office 365 from certain locations.</span></span>
  
> [!TIP]
> <span data-ttu-id="d18b9-128">使您可以先管理最重要的类型，您可以筛选通知按**类别**或**严重性**。</span><span class="sxs-lookup"><span data-stu-id="d18b9-128">You can filter the alerts by **Category** or by **Severity** so you can manage the most important ones first.</span></span> 
  
<span data-ttu-id="d18b9-p104">每个通知，查找到什么导致它以便您可以决定要采取什么操作。若要查看有关通知的详细信息并采取措施，如解决通知或挂起的用户帐户，请选择该通知可打开的详细信息页。在详细信息页上，您可以查看活动日志、 帐户和与此通知中，相关的用户，并执行如下操作：</span><span class="sxs-lookup"><span data-stu-id="d18b9-p104">For each alert, look into what caused it so you can decide what action to take. To see more details about an alert and to take action, such as resolving the alert or suspending a users account, choose the alert to open a details page. On the details page, you can review the activity log, accounts, and users that are related to the alert, and take actions such as the following:</span></span>
  
- <span data-ttu-id="d18b9-p105">**消除**如果该通知误报，关闭它。您可以选择添加注释，说明为什么您消除的位置。</span><span class="sxs-lookup"><span data-stu-id="d18b9-p105">**Dismiss** If the alert was a false positive, dismiss it. You can optionally add a comment explaining why you dismissed it.</span></span> 
    
- <span data-ttu-id="d18b9-p106">**解决警报**如果通过触发通知您知道活动不威胁，解决问题。您可以选择添加注释，说明您解析的原因。</span><span class="sxs-lookup"><span data-stu-id="d18b9-p106">**Resolve alert** If the alert was triggered by an activity that you know isn't a threat, resolve it. You can optionally add a comment explaining why you resolved it.</span></span> 
    
- <span data-ttu-id="d18b9-136">**挂起**如果您怀疑未经授权的登录帐户，例如，某人时您认识的人登录从另一个国家/地区的项物理上位于本地 office，则可以[挂起帐户](suspend-or-restore-an-account-in-ocas.md)当您研究了什么事。</span><span class="sxs-lookup"><span data-stu-id="d18b9-136">**Suspend** If you suspect unauthorized sign ins on an account, for example, someone signing in from another country when you know that person is physically at a local office, you can [suspend the account](suspend-or-restore-an-account-in-ocas.md) while you investigate what's going on.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="d18b9-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d18b9-137">Next steps</span></span>

- [<span data-ttu-id="d18b9-138">调查活动</span><span class="sxs-lookup"><span data-stu-id="d18b9-138">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="d18b9-139">暂停或还原的用户帐户</span><span class="sxs-lookup"><span data-stu-id="d18b9-139">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- <span data-ttu-id="d18b9-140">查看受支持的[Web 流量日志和数据源](web-traffic-logs-and-data-sources-for-ocas.md)的列表</span><span class="sxs-lookup"><span data-stu-id="d18b9-140">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="d18b9-141">查看您[的 Office 365 云应用程序安全性的使用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="d18b9-141">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


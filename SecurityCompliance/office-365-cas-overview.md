---
title: Office 365 云应用安全概述
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'Office 365 云应用程序安全性，您见解可疑的活动 Office 365 中这样可以调查情况下，可能存在问题，如果需要请执行解决安全问题的操作。 '
ms.openlocfilehash: 84d5b412b62bf113101d6322032f3b643d87d741
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525130"
---
# <a name="overview-of-office-365-cloud-app-security"></a><span data-ttu-id="027c9-103">Office 365 云应用安全概述</span><span class="sxs-lookup"><span data-stu-id="027c9-103">Overview of Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="027c9-104">评估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="027c9-104">****Evaluation** \>**</span></span>|<span data-ttu-id="027c9-105">规划 * *\>**</span><span class="sxs-lookup"><span data-stu-id="027c9-105">****Planning** \>**</span></span>|<span data-ttu-id="027c9-106">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="027c9-106">****Deployment** \>**</span></span>|<span data-ttu-id="027c9-107">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="027c9-107">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="027c9-108">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="027c9-108">You are here!</span></span>  <br/> [<span data-ttu-id="027c9-109">后续步骤</span><span class="sxs-lookup"><span data-stu-id="027c9-109">Next step</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="027c9-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="027c9-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="027c9-111">开始部署</span><span class="sxs-lookup"><span data-stu-id="027c9-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="027c9-112">开始利用</span><span class="sxs-lookup"><span data-stu-id="027c9-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="027c9-p101">Office 365 云应用程序安全性是在 Office 365 企业 E5 中可用。如果您的组织使用的另一个 Office 365 企业版订阅，可以作为购买 Office 365 云应用程序安全性。(作为全局管理员，在 Office 365 管理中心中，选择**帐单** \> **添加订阅**。)有关详细信息，请参阅[Office 365 平台服务说明： Office 365 安全性&amp;合规性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[购买或编辑企业的 Office 365 的加载项](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。</span><span class="sxs-lookup"><span data-stu-id="027c9-p101">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
<span data-ttu-id="027c9-p102">Office 365 云应用程序安全性，您深入可疑的活动 Office 365 中这样可以调查情况下，可能存在问题，如果需要请执行解决安全问题的操作。与 Office 365 云应用程序安全性，您可以接收的典型或可疑活动触发通知的通知，请参阅如何组织的 Office 365 中访问和使用数据，挂起出现可疑活动的用户帐户，并要求重新登录到 Office 365 应用程序后被触发通知的用户。阅读这篇文章，获取 Office 365 云应用程序安全性特性和功能的概述。</span><span class="sxs-lookup"><span data-stu-id="027c9-p102">Office 365 Cloud App Security gives you insight into suspicious activity in Office 365 so you can investigate situations that are potentially problematic and, if needed, take action to address security issues. With Office 365 Cloud App Security, you can receive notifications of triggered alerts for atypical or suspicious activities, see how your organization's data in Office 365 is accessed and used, suspend user accounts exhibiting suspicious activity, and require users to log back in to Office 365 apps after an alert has been triggered. Read this article to get an overview of Office 365 Cloud App Security features and capabilities.</span></span>
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="027c9-119">如何查找 Office 365 云应用程序安全性门户</span><span class="sxs-lookup"><span data-stu-id="027c9-119">How to find the Office 365 Cloud App Security portal</span></span>

> [!NOTE]
> <span data-ttu-id="027c9-p103">若要访问 Office 365 云应用程序安全性门户，您必须是全局管理员、 安全管理员或安全读取器。若要了解详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="027c9-p103">To access the Office 365 Cloud App Security portal, you must be a global administrator, security administrator, or security reader. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
<span data-ttu-id="027c9-p104">您可以获取到 Office 365 云应用程序安全性门户通过 Office 365 安全性&amp;合规性中心。下面是一个好方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="027c9-p104">You can get to the Office 365 Cloud App Security portal through the Office 365 Security &amp; Compliance Center. Here's one good way to do it:</span></span>
  
1. <span data-ttu-id="027c9-p105">转到[https://protection.office.com](https://protection.office.com)和 Office 365 中使用您的工作或学校帐户登录。(您将转到安全&amp;合规性中心。)</span><span class="sxs-lookup"><span data-stu-id="027c9-p105">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="027c9-126">安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。</span><span class="sxs-lookup"><span data-stu-id="027c9-126">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span> 
    
    ![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    <span data-ttu-id="027c9-128">（如果尚未启用 Office 365 云应用程序安全性，并且已[打开 Office 365 云应用程序安全性](turn-on-office-365-cas.md)的全局管理员）。</span><span class="sxs-lookup"><span data-stu-id="027c9-128">(If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)</span></span>
    
3. <span data-ttu-id="027c9-129">选择**转到 Office 365 云应用程序安全性**。</span><span class="sxs-lookup"><span data-stu-id="027c9-129">Choose **Go to Office 365 Cloud App Security**.</span></span> 
    
## <a name="policies"></a><span data-ttu-id="027c9-130">Policies</span><span class="sxs-lookup"><span data-stu-id="027c9-130">Policies</span></span>

<span data-ttu-id="027c9-p106">为组织定义的策略云应用程序安全性适用于 office 365。与 Office 365 云应用程序安全性，您的组织中获取 10 个预定义的异常检测策略和多个活动策略模板。这些策略旨在检测一般异常，确定用户登录从 risky 的 IP 地址、 检测勒索软件活动，检测管理员从非企业 IP 地址和更多的活动。</span><span class="sxs-lookup"><span data-stu-id="027c9-p106">Office 365 Cloud App Security works with the policies that are defined for your organization. With Office 365 Cloud App Security, your organization gets 10 predefined anomaly detection policies and several templates for activity policies. These policies are designed to detect general anomalies, identify users logging in from a risky IP address, detect ransomware activities, detect administrator activities from non-corporate IP addresses, and more.</span></span>
  
![在 CAS 门户中，选择控件\>模板可以查看或创建策略模板](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
<span data-ttu-id="027c9-135">若要查看/使用 Office 365 云应用程序安全性门户策略模板，请转至**控件** \> **模板**。</span><span class="sxs-lookup"><span data-stu-id="027c9-135">To view/use policy templates, in the Office 365 Cloud App Security portal, go to **Control** \> **Templates**.</span></span> 
  
![在 O365 CAS 门户中，选择控件](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
<span data-ttu-id="027c9-137">若要了解有关策略的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="027c9-137">To learn more about policies, see the following resources:</span></span>
  
- [<span data-ttu-id="027c9-138">Office 365 云应用安全中的活动策略和警报</span><span class="sxs-lookup"><span data-stu-id="027c9-138">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="027c9-139">Office 365 云应用安全中的异常检测策略</span><span class="sxs-lookup"><span data-stu-id="027c9-139">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a><span data-ttu-id="027c9-140">警报</span><span class="sxs-lookup"><span data-stu-id="027c9-140">Alerts</span></span>

<span data-ttu-id="027c9-p107">定义了策略，通知有关可疑或非典型活动检测到的通知您。若要查看为您的组织的通知，请在导航栏中的屏幕顶部选择**通知**。</span><span class="sxs-lookup"><span data-stu-id="027c9-p107">When policies are defined, alerts notify you about suspicious or atypical activities that were detected. To view alerts for your organization, choose **Alerts** in the navigation bar across the top of the screen.</span></span> 
  
![在通知页中，您可以看到触发的通知和执行任何操作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
<span data-ttu-id="027c9-p108">触发通知，则可以查看这些以详细了解有关什么事。然后，如果仍然可疑活动，您可以执行操作。例如，可以通知用户有关问题以及挂起登录到 Office 365 用户或要求用户重新登录到 Office 365 应用程序。</span><span class="sxs-lookup"><span data-stu-id="027c9-p108">As alerts are triggered you can review them to learn more about what is going on. Then, if the activity is still suspicious, you can take action. For example, you can notify a user about an issue, suspend a user from signing in to Office 365, or require a user to sign back in to Office 365 apps.</span></span>
  
<span data-ttu-id="027c9-147">若要了解有关通知的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="027c9-147">To learn more about alerts, see the following resources:</span></span>
  
- [<span data-ttu-id="027c9-148">Office 365 云应用安全中的活动策略和警报</span><span class="sxs-lookup"><span data-stu-id="027c9-148">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="027c9-149">Office 365 云应用安全中的异常检测策略</span><span class="sxs-lookup"><span data-stu-id="027c9-149">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="027c9-150">查看和 Office 365 云应用程序安全性通知对其执行操作</span><span class="sxs-lookup"><span data-stu-id="027c9-150">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a><span data-ttu-id="027c9-151">活动日志</span><span class="sxs-lookup"><span data-stu-id="027c9-151">Activity logs</span></span>

<span data-ttu-id="027c9-152">在 Office 365 云应用程序安全性活动日志页上查看有关用户活动的信息。</span><span class="sxs-lookup"><span data-stu-id="027c9-152">View information about user activities on your Activity log page in Office 365 Cloud App Security.</span></span>
  
![在 O365 CAS 门户中，选择调查\>活动日志](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
<span data-ttu-id="027c9-154">若要获取对此页，在 Office 365 云应用程序安全性门户中，转到**调查** \> **活动日志**。</span><span class="sxs-lookup"><span data-stu-id="027c9-154">To get to this page, in the Office 365 Cloud App Security portal, go to **Investigate** \> **Activity log**.</span></span> 
  
![在 O365 CAS 门户中，选择调查。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
<span data-ttu-id="027c9-p109">您可以使用 web 流量日志 Office 365 云应用程序安全性，太。更多详细信息中所包含的日志文件，您必须向用户活动的更好的可见性。您可以使用 Barracuda、 蓝色衣帽、 检查点、 Cisco、 Clavister、 Dell 使 SonicWALL、 Fortinet、 Juniper、 McAfee、 Microsoft、 帕洛阿尔托市、 Sophos、 Squid、 Websence、 Zscaler，和更多的日志文件。</span><span class="sxs-lookup"><span data-stu-id="027c9-p109">You can use your web traffic logs with Office 365 Cloud App Security, too. The more details that are included in those log files, the better visibility you'll have into user activity. You can use log files from Barracuda, Blue Coat, Check Point, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, Palo Alto, Sophos, Squid, Websence, Zscaler, and more.</span></span>
  
[<span data-ttu-id="027c9-159">了解 Office 365 云应用程序安全性 web 流量日志和数据源</span><span class="sxs-lookup"><span data-stu-id="027c9-159">Learn about web traffic logs and data sources for Office 365 Cloud App Security</span></span>](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="app-permissions"></a><span data-ttu-id="027c9-160">应用程序权限</span><span class="sxs-lookup"><span data-stu-id="027c9-160">App permissions</span></span>

<span data-ttu-id="027c9-161">与 Office 365 云应用程序安全性，您可以允许或阻止组织使用的访问 Office 365 中的数据的第三方应用程序中的人员。</span><span class="sxs-lookup"><span data-stu-id="027c9-161">With Office 365 Cloud App Security, you can allow or prevent people in your organization to use third-party apps that access data in Office 365.</span></span>
  
![O365 CA 中可以访问管理应用程序权限页上，从调查菜单。](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
<span data-ttu-id="027c9-163">若要获取对此页，请转到**调查** \> **应用程序权限**。</span><span class="sxs-lookup"><span data-stu-id="027c9-163">To get to this page, go to **Investigate** \> **App permissions**.</span></span> 
  
![在 O365 CAS 门户中，选择调查。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[<span data-ttu-id="027c9-165">使用 Office 365 云应用安全管理应用权限</span><span class="sxs-lookup"><span data-stu-id="027c9-165">Manage app permissions using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a><span data-ttu-id="027c9-166">云发现仪表板</span><span class="sxs-lookup"><span data-stu-id="027c9-166">Cloud Discovery Dashboard</span></span>

<span data-ttu-id="027c9-p110">**云发现仪表板**，也称为**工作效率应用程序发现**，显示有关贵组织中的云应用程序使用情况的信息。您可以查看有关应用程序、 用户、 流量、 事务和使用此仪表板的详细信息。云发现仪表板类似于下图：</span><span class="sxs-lookup"><span data-stu-id="027c9-p110">The **Cloud Discovery Dashboard**, also referred to as **Productivity App Discovery**, shows information about cloud app usage within your organization. You can view information about apps, users, traffic, transactions, and more using this dashboard. The Cloud Discovery Dashboard resembles the following image:</span></span> 
  
![在 Office 365 CAS 门户中，选择发现\>云发现仪表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="027c9-171">若要获取此仪表板中，在 Office 365 云应用程序安全性门户中，转到**发现** \> **云发现仪表板**。</span><span class="sxs-lookup"><span data-stu-id="027c9-171">To get to this dashboard, in the Office 365 Cloud App Security portal, go to **Discover** \> **Cloud Discovery dashboard**.</span></span> 
  
![在 Office 365 CAS 门户中，选择发现](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[<span data-ttu-id="027c9-173">查看 Office 365 云应用安全中的应用发现结果</span><span class="sxs-lookup"><span data-stu-id="027c9-173">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a><span data-ttu-id="027c9-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="027c9-174">Next steps</span></span>

- <span data-ttu-id="027c9-175">获取[Office 365 云应用程序安全用例和使用指南](https://aka.ms/O365CASGuide)</span><span class="sxs-lookup"><span data-stu-id="027c9-175">Get the [Office 365 Cloud App Security Use Cases and Usage Guide](https://aka.ms/O365CASGuide)</span></span>
    
- [<span data-ttu-id="027c9-176">为 Office 365 云应用安全做好准备</span><span class="sxs-lookup"><span data-stu-id="027c9-176">Get ready for Office 365 Cloud App Security</span></span>](get-ready-for-office-365-cas.md)
    


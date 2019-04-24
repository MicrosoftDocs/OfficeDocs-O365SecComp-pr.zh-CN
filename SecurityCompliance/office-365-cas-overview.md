---
title: Overview of Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'office 365 云应用安全可帮助您深入了解 Office 365 中的可疑活动, 以便您可以调查可能存在问题的情况, 并在必要时采取措施解决安全问题。 '
ms.openlocfilehash: 960e4c75a4da13e1a0365f75d290cd18587abd58
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263052"
---
# <a name="overview-of-office-365-cloud-app-security"></a>Overview of Office 365 Cloud App Security
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|你在这里!  <br/> [后续步骤](get-ready-for-office-365-cas.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> office 365 企业版 E5 中提供了 office 365 云应用安全性。 如果您的组织使用的是其他 office 365 企业版订阅, 则可以将 Office 365 云应用安全作为附加项购买。 (作为全局管理员, 在 Microsoft 365 管理中心中, 选择 "**付费** \> **添加订阅**"。)有关详细信息, 请参阅[office 365 Platform 服务说明: office 365 &amp;安全合规性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)和[购买或编辑 Office 365 for business 的加载](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)项。 
  
office 365 云应用安全使您可以深入了解 Office 365 中的可疑活动, 以便调查可能存在问题的情况, 并在必要时采取措施解决安全问题。 使用 Office 365 云应用安全, 您可以收到触发警报的通知, 以发现不正常或可疑的活动、如何访问和使用组织中的数据、暂停用户帐户显示可疑活动, 以及需要触发警报后, 用户可以重新登录到 Office 365 应用程序。 阅读本文, 了解 Office 365 云应用安全特性和功能的概述。
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a>如何查找 Office 365 云应用安全门户

> [!NOTE]
> 若要访问 office 365 云应用安全门户, 您必须是 office 365 全局管理员、安全管理员或安全阅读者。 若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。 
  
您可以通过转到[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)并登录来访问 Office 365 云应用安全门户。 

你也可以从 Office 365 安全&amp;合规中心获取。 下面是执行此操作的一个不错的方法:
  
1. 请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。 (这会将您带到&amp;安全合规中心。)
    
2. 在 "安全&amp;合规性中心" 中, 选择 "**通知** \> " "**管理高级警报**"。 <br/>![选择 "管理高级警报" 以转到 Office 365 云应用安全](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>(如果尚未启用 office 365 云应用安全, 并且你是全局管理员, 请[启用 office 365 云应用安全](turn-on-office-365-cas.md)。)
    
3. 选择 "**转到 Office 365 云应用安全性**"。 
    
## <a name="policies"></a>策略

Office 365 云应用安全性适用于为您的组织定义的策略。 使用 Office 365 云应用安全, 你的组织将获得许多预定义的异常检测策略和多个活动策略模板。 这些策略旨在检测常规异常, 确定从有风险的 IP 地址登录的用户、检测勒索软件活动、检测非公司 IP 地址的管理员活动等。
  
![在 CAS 门户中, 选择 " \>控制模板" 以查看或创建策略模板](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
若要查看/使用策略模板, 请在 Office 365 云应用安全门户中, 转到 "**控件** \> **模板**"。 
  
![在 O365 CAS 门户中, 选择 "控制"](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
若要了解有关策略的详细信息, 请参阅以下资源:
  
- [Office 365 云应用安全中的活动策略和警报](activity-policies-and-alerts.md)
    
- [Office 365 云应用安全中的异常检测策略](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a>警报

定义策略时, 警报会通知您检测到的可疑或非常规活动。 若要查看组织的通知, 请在屏幕顶部的导航栏中选择 "**通知**"。 
  
![在 "通知" 页面上, 您可以查看触发的警报以及执行的任何操作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
当警报被触发时, 您可以查看它们, 以了解有关正在进行的操作的详细信息。 然后, 如果活动仍可疑, 则可以采取措施。 例如, 您可以通知用户一个问题、挂起用户登录 office 365, 或要求用户重新登录 office 365 应用。
  
若要了解有关通知的详细信息, 请参阅以下资源:
  
- [Office 365 云应用安全中的活动策略和警报](activity-policies-and-alerts.md)
    
- [Office 365 云应用安全中的异常检测策略](anomaly-detection-policies-in-ocas.md)
    
- [查看 Office 365 云应用安全警报并对其执行操作](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a>活动日志

查看有关 Office 365 云应用安全中的 "活动日志" 页上的用户活动的信息。
  
![在 O365 CAS 门户中, 选择 " \>调查活动日志"](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
若要获取此页面, 请在 Office 365 云应用安全门户中, 转到 "**调查** \> **活动日志**"。 
  
![在 O365 CAS 门户中, 选择 "调查"。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
你也可以将 web 流量日志与 Office 365 云应用安全性结合使用。 这些日志文件中包含的详细信息越多, 您对用户活动的可见性越好。 您可以使用 Barracuda、Blue Coat、Check Point、Cisco、Clavister、Dell SonicWALL、Fortinet、刺柏、McAfee、Microsoft、Palo Alto、Sophos、Squid、Websence、Zscaler 等的日志文件。
  
[了解有关 Office 365 云应用安全的 web 流量日志和数据源](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="oauth-apps"></a>OAuth 应用程序

使用 office 365 云应用安全, 可以允许或阻止组织中的人员使用第三方应用访问 Office 365 中的数据。
  
![在 O365 CAS 中, 可以从 "调查" 菜单访问 "管理 OAuth 应用" 页面。](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
若要获取此页面, 请转到**调查** \> **OAuth 应用**。 
  
![在 O365 CAS 门户中, 选择 "调查"。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[使用 Office 365 云应用安全管理 OAuth 应用](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a>云发现仪表板

**云发现仪表板**(也称为 "**生产率应用发现**") 显示组织中的云应用使用情况的相关信息。 您可以使用此仪表板查看有关应用、用户、流量、事务等的信息。 云发现仪表板类似于以下图像: 
  
![在 Office 365 CAS 门户中, 选择 " \>发现云发现" 仪表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
若要获取此仪表板, 请在 Office 365 云应用安全门户中, 转到 "**发现** \> **云发现" 仪表板**。 
  
![在 Office 365 CAS 门户中, 选择 "发现"](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[查看 Office 365 云应用安全中的应用发现结果](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a>后续步骤

- 获取[Office 365 云应用安全使用案例和使用指南](https://aka.ms/O365CASGuide)
    
- [准备使用 Office 365 云应用安全](get-ready-for-office-365-cas.md)
    


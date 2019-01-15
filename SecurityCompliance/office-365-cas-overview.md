---
title: Office 365 云应用安全概述
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
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
ms.openlocfilehash: 62b1dc1d9285e60f30c1d5e541973640bb47ae35
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014924"
---
# <a name="overview-of-office-365-cloud-app-security"></a>Office 365 云应用安全概述
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|使用率 ***|
|:-----|:-----|:-----|:-----|
|在这里 ！  <br/> [后续步骤](get-ready-for-office-365-cas.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> Office 365 云应用程序安全性是在 Office 365 企业 E5 中可用。如果您的组织使用的另一个 Office 365 企业版订阅，可以作为购买 Office 365 云应用程序安全性。(作为全局管理员，在 Office 365 管理中心中，选择**帐单** \> **添加订阅**。)有关详细信息，请参阅[Office 365 平台服务说明： Office 365 安全性&amp;合规性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[购买或编辑企业的 Office 365 的加载项](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。 
  
Office 365 云应用程序安全性，您深入可疑的活动 Office 365 中这样可以调查情况下，可能存在问题，如果需要请执行解决安全问题的操作。与 Office 365 云应用程序安全性，您可以接收的典型或可疑活动触发通知的通知，请参阅如何组织的 Office 365 中访问和使用数据，挂起出现可疑活动的用户帐户，并要求重新登录到 Office 365 应用程序后被触发通知的用户。阅读这篇文章，获取 Office 365 云应用程序安全性特性和功能的概述。
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a>如何查找 Office 365 云应用程序安全性门户

> [!NOTE]
> 若要访问 Office 365 云应用程序安全性门户，您必须是全局管理员、 安全管理员或安全读取器。若要了解详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。 
  
您可以获取到 Office 365 云应用程序安全性门户通过 Office 365 安全性&amp;合规性中心。下面是一个好方法执行此操作：
  
1. 转到[https://protection.office.com](https://protection.office.com)和 Office 365 中使用您的工作或学校帐户登录。(您将转到安全&amp;合规性中心。) 
    
2. 安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。 <br/>![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>（如果尚未启用 Office 365 云应用程序安全性，并且已[打开 Office 365 云应用程序安全性](turn-on-office-365-cas.md)的全局管理员）。
    
3. 选择**转到 Office 365 云应用程序安全性**。 
    
## <a name="policies"></a>Policies

为组织定义的策略云应用程序安全性适用于 office 365。与 Office 365 云应用程序安全性，您的组织获取多个预定义的异常检测策略和多个活动策略模板。这些策略旨在检测一般异常，确定用户登录从 risky 的 IP 地址、 检测勒索软件活动，检测管理员从非企业 IP 地址和更多的活动。
  
![在 CAS 门户中，选择控件\>模板可以查看或创建策略模板](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
若要查看/使用 Office 365 云应用程序安全性门户策略模板，请转至**控件** \> **模板**。 
  
![在 O365 CAS 门户中，选择控件](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
若要了解有关策略的详细信息，请参阅以下资源：
  
- [Office 365 云应用安全中的活动策略和警报](activity-policies-and-alerts.md)
    
- [Office 365 云应用安全中的异常检测策略](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a>警报

定义了策略，通知有关可疑或非典型活动检测到的通知您。若要查看为您的组织的通知，请在导航栏中的屏幕顶部选择**通知**。 
  
![在通知页中，您可以看到触发的通知和执行任何操作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
触发通知，则可以查看这些以详细了解有关什么事。然后，如果仍然可疑活动，您可以执行操作。例如，可以通知用户有关问题以及挂起登录到 Office 365 用户或要求用户重新登录到 Office 365 应用程序。
  
若要了解有关通知的详细信息，请参阅以下资源：
  
- [Office 365 云应用安全中的活动策略和警报](activity-policies-and-alerts.md)
    
- [Office 365 云应用安全中的异常检测策略](anomaly-detection-policies-in-ocas.md)
    
- [查看和 Office 365 云应用程序安全性通知对其执行操作](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a>活动日志

在 Office 365 云应用程序安全性活动日志页上查看有关用户活动的信息。
  
![在 O365 CAS 门户中，选择调查\>活动日志](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
若要获取对此页，在 Office 365 云应用程序安全性门户中，转到**调查** \> **活动日志**。 
  
![在 O365 CAS 门户中，选择调查。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
您可以使用 web 流量日志 Office 365 云应用程序安全性，太。更多详细信息中所包含的日志文件，您必须向用户活动的更好的可见性。您可以使用 Barracuda、 蓝色衣帽、 检查点、 Cisco、 Clavister、 Dell 使 SonicWALL、 Fortinet、 Juniper、 McAfee、 Microsoft、 帕洛阿尔托市、 Sophos、 Squid、 Websence、 Zscaler，和更多的日志文件。
  
[了解 Office 365 云应用程序安全性 web 流量日志和数据源](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="oauth-apps"></a>OAuth 应用程序

与 Office 365 云应用程序安全性，您可以允许或阻止组织使用的访问 Office 365 中的数据的第三方应用程序中的人员。
  
![O365 CA 中可以访问管理 OAuth 的应用程序页上，从调查菜单。](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
若要获取对此页，请转到**调查** \> **OAuth 应用程序**。 
  
![在 O365 CAS 门户中，选择调查。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[使用 Office 365 云应用安全管理 OAuth 应用](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a>云发现仪表板

**云发现仪表板**，也称为**工作效率应用程序发现**，显示有关贵组织中的云应用程序使用情况的信息。您可以查看有关应用程序、 用户、 流量、 事务和使用此仪表板的详细信息。云发现仪表板类似于下图： 
  
![在 Office 365 CAS 门户中，选择发现\>云发现仪表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
若要获取此仪表板中，在 Office 365 云应用程序安全性门户中，转到**发现** \> **云发现仪表板**。 
  
![在 Office 365 CAS 门户中，选择发现](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[查看 Office 365 云应用安全中的应用发现结果](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a>后续步骤

- 获取[Office 365 云应用程序安全用例和使用指南](https://aka.ms/O365CASGuide)
    
- [准备使用 Office 365 云应用安全](get-ready-for-office-365-cas.md)
    


---
title: 准备使用 Office 365 云应用安全
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: 开始使用 Office 365 云应用程序安全性
ms.openlocfilehash: 1d1ae464278a5d9aafa5a176298f03174b6a37dc
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603693"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a>准备使用 Office 365 云应用安全
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|使用率 ***|
|:-----|:-----|:-----|:-----|
|[启动评估](office-365-cas-overview.md) <br/> |在这里 ！  <br/> [后续步骤](turn-on-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |
   
准备要打开并为您的组织实现 Office 365 云应用程序安全性 （之前被称为高级安全管理），如有需要考虑的几件事。使用本文作为指南来规划 Office 365 云应用程序安全性。
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a>步骤 1： 确定并保护您的全局和安全管理员帐户

全局管理员、 安全管理员和安全读者可以访问 Office 365 云应用程序安全性门户以查看策略、 查看警报，并使用报表。全局管理员和安全管理员可以定义策略，并执行其他操作来保护您的组织。(有关详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。)查看贵组织的用户帐户的预防提升的权限。 
  
 **[保护 Office 365 全局管理员帐户](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**。 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a>步骤 2： 启用审核日志记录您的组织

对 Office 365 云应用程序安全性以正确的顺序，必须打开审核日志记录。这通常通过 Exchange Online 管理员或全局管理员。
  
 **[打开 Office 365 打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)**。 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a>步骤 3： 转到 Office 365 云应用程序安全性门户

您可以获取到 Office 365 云应用程序安全性门户转到[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)和登录。 

您还可以从 Office 365 安全性而存在获取&amp;合规性中心。下面是一个好方法执行此操作：

1. 转到[https://protection.office.com](https://protection.office.com)和登录英寸 (您将转到安全&amp;合规性中心。)
    
2. 转到**通知** \> **管理高级通知**。
    
3. 选择**转到 Office 365 云应用程序安全性**转到 Office 365 云应用程序安全性门户。<br> ![选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>当您转到 Office 365 云应用程序安全性门户时，您看到的第一页是策略页上，类似于下图：<br>![当您转到 Office 365 云应用程序安全性门户时，启动与策略页](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)<br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a>步骤 4： 定义策略和设置提醒&amp;操作

全局管理员和安全管理员 Office 365 云应用程序安全性定义策略。在定义策略的过程中，警报和操作也设置。警报是基于标准的视图中显示或通过电子邮件发送的通知。 
  
有两种类型的 Office 365 云应用程序安全性的通知： 检测可疑活动的异常检测警报和活动通知，定义可能为您的组织在典型的活动。警报通知全局管理员和安全管理员为您的组织不常见的 Office 365 环境中活动时。
  
请参阅以下资源，以了解详细信息：
  
- [Office 365 云应用安全中的活动策略和警报](activity-policies-and-alerts.md)
    
- [Office 365 云应用安全中的异常检测策略](anomaly-detection-policies-in-ocas.md)
    
- [查看和 Office 365 云应用程序安全性通知对其执行操作](review-office-365-cas-alerts.md)
    
## <a name="step-5-learn-about-your-organizations-cloud-usage"></a>步骤 5： 了解有关您组织的云使用情况

作为全局管理员、 安全管理员或安全读者，您可以了解有关您组织的云通过报告和云发现仪表板 （也称为工作效率应用程序发现） 的使用情况。此仪表板显示有关用户、 应用程序、 web 流量和风险级别信息。
  
![在 Office 365 CAS 门户中，选择发现\>云发现仪表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
若要转到生产效率应用程序发现仪表板，在 Office 365 云应用程序安全性门户中，选择**发现** \> **云发现仪表板**。
  
![在 Office 365 CAS 门户中，选择发现](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
若要填充所需的信息的报告，上载日志文件从您的组织的防火墙和代理。若要了解详细信息，请参阅以下资源：
  
- [在 Office 365 云应用程序安全性中创建应用程序发现报告](create-app-discovery-reports-in-ocas.md)
    
- [查看 Office 365 云应用安全中的应用发现结果](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-6-manage-apps-that-your-organization-is-using-to-access-office-365"></a>步骤 6： 管理您的组织使用访问 Office 365 的应用程序

以全局管理员或安全管理员，您可以管理应用程序，例如自定义应用程序或第三方应用程序，在与 Office 365 其设备上使用您的组织中的人员。例如，假设有人已下载他们想要与 Office 365 一起使用的自定义应用程序。您可以查看用户正在使用的应用程序、 禁止不受信任应用程序，或将应用程序标记为批准可用于跟踪目的。[使用 Office 365 云应用程序安全性的管理 OAuth 应用程序](manage-app-permissions-in-ocas.md)。
  
## <a name="step-7-use-your-siem-server-with-office-365-cloud-app-security"></a>步骤 7： 使用 SIEM 服务器与 Office 365 云应用程序安全性

您的组织使用的安全信息和事件管理 (SIEM) 服务器？Office 365 云应用程序安全性可以现在与集成 SIEM 服务器启用集中式监视进行通知。与 SIEM 服务集成允许您更好地保护同时维护常规安全工作流、 自动化安全过程和关联之间的基于云的云应用程序在本地和事件。SIEM 代理服务器上运行、 提取通知从 Office 365 云应用程序安全性，并将这些通知流式到 SIEM 服务器。请参阅[与 Office 365 云应用程序安全性的 SIEM 集成](integrate-your-siem-server-with-office-365-cas.md)。
  
## <a name="next-steps"></a>后续步骤

- [开启 Office 365 云应用安全](turn-on-office-365-cas.md)
    
- 尝试动手体验如何可以在此演示 Office 365 云应用程序安全性的强大功能，并创建证明我们[测试实验室指南](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment)。 
    


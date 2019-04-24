---
title: 准备使用 Office 365 云应用安全
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/15/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: 开始使用 Office 365 云应用安全
ms.openlocfilehash: 89718adcbb7c77735db3009937d887e88d4a8bc3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254006"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a>准备使用 Office 365 云应用安全
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|[开始评估](office-365-cas-overview.md) <br/> |你在这里!  <br/> [后续步骤](turn-on-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |
   
在准备为组织启用和实施 Office 365 云应用安全时, 需要考虑一些事项。 使用本文作为规划 Office 365 云应用程序安全性的指南。
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a>步骤 1: 标识和保护全局管理员帐户和安全管理员帐户

全局管理员、安全管理员和安全读者可以访问 Office 365 云应用安全门户以查看策略、查看通知和使用报表。 全局管理员和安全管理员可以定义策略并执行其他操作来保护您的组织。 (有关详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。)查看您的组织的用户帐户, 该帐户具有提升的权限作为预防措施。 
  
 **[保护 Office 365 全局管理员帐户](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**。 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a>步骤 2: 为组织启用审核日志记录

为了使 Office 365 云应用安全正常工作, 审核日志记录必须处于打开状态。 这通常是由 Exchange Online 管理员或全局管理员完成的。
  
 **[启用或禁用 "Office 365 审核日志搜索"](turn-audit-log-search-on-or-off.md)**。 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a>步骤 3: 转到 Office 365 云应用安全门户

您可以通过转到[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)并登录来访问 Office 365 云应用安全门户。 

你也可以从 Office 365 安全&amp;合规中心获取。 下面是执行此操作的一个不错的方法:

1. 转到[https://protection.office.com](https://protection.office.com)并登录。 (这会将您带到&amp;安全合规中心。)
    
2. 转到 "**通知** \> " "**管理高级警报**"。
    
3. 选择 "**转到 office 365 云应用安全性**" 以转到 office 365 云应用安全门户。<br> ![选择 "管理高级警报" 以转到 Office 365 云应用安全](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br>当您转到 Office 365 云应用安全门户时, 您看到的第一页是策略页, 类似于以下图像:<br>![当您转到 Office 365 云应用安全门户时, 将从 "策略" 页开始](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)<br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a>步骤 4: 定义策略并设置警报&amp;操作

全局管理员和安全管理员定义 Office 365 云应用安全中的策略。 在定义策略的过程中, 还会设置警报和操作。 警报是显示在视图中或通过电子邮件发送的基于条件的通知。 
  
Office 365 Cloud App Security 中有两种类型的警报: 检测可疑活动的异常检测警报和活动警报 (针对组织的可能是反常的活动) 定义的。 当您的 Office 365 环境中的某个活动在您的组织中不正常时, 会向全局管理员和安全管理员通知这些警报。
  
若要了解详细信息, 请参阅以下资源:
  
- [Office 365 云应用安全中的活动策略和警报](activity-policies-and-alerts.md)
    
- [Office 365 云应用安全中的异常检测策略](anomaly-detection-policies-in-ocas.md)
    
- [查看 Office 365 云应用安全警报并对其执行操作](review-office-365-cas-alerts.md)
    

## <a name="step-5-set-up-conditional-access-app-control"></a>步骤 5: 设置条件访问应用程序控制

根据某些条件 (如哪些用户可以使用哪些应用程序, 以及在哪里) 设置和强制实施您组织的应用程序上的控件。 定义用户应用程序访问和会话策略, 以确定是否可以下载和加密敏感文档, 阻止对某些应用程序的访问, 为某些应用程序设置只读模式, 并限制来自非企业网络的用户会话。

若要了解详细信息, 请参阅以下资源:

- [使用 Office 365 云应用安全条件访问应用控制保护应用](ocas-conditional-access-app-control.md)

- [为 Office 365 应用部署条件访问应用控制](ocas-deploy-conditional-access-app-control.md)

## <a name="step-6-learn-about-your-organizations-cloud-usage"></a>步骤 6: 了解组织的云使用情况

作为全局管理员、安全管理员或安全读者, 您可以通过报告和云发现仪表板 (也称为 "工作效率应用发现") 了解组织的云使用情况。 此仪表板显示有关用户、应用、web 流量和风险级别的信息。
  
![在 Office 365 CAS 门户中, 选择 " \>发现云发现" 仪表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
若要转到工作效率应用发现仪表板, 请在 Office 365 云应用安全门户中, 选择 "**发现** \> **云发现仪表板**"。
  
![在 Office 365 CAS 门户中, 选择 "发现"](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
若要使用所需的信息填充报告, 请从组织的防火墙和代理上载日志文件。 若要了解详细信息, 请参阅以下资源:
  
- [在 Office 365 中创建应用程序发现报告云应用安全](create-app-discovery-reports-in-ocas.md)
    
- [查看 Office 365 云应用安全中的应用发现结果](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-7-manage-apps-that-your-organization-is-using-to-access-office-365"></a>步骤 7: 管理您的组织用来访问 Office 365 的应用程序

作为全局管理员或安全管理员, 您可以管理组织中的用户在使用 Office 365 的设备上使用的自定义应用程序或第三方应用程序。 例如, 假设有人下载了要与 Office 365 一起使用的自定义应用程序。 您可以查看用户正在使用的应用程序、禁止不受信任的应用程序, 或将应用标记为针对跟踪目的进行审批。 [使用 Office 365 云应用安全管理 OAuth 应用](manage-app-permissions-in-ocas.md)。
  
## <a name="step-8-create-a-maintenance-plan"></a>步骤 8: 创建维护计划

在设置和配置 office 365 云应用安全性之后, 您需要将某些使用任务作为组织的 Office 365 全局管理员或安全管理员执行。
通过执行这些任务, 可帮助确保正确配置 Office 365 云应用安全, 策略是最新的, 并且您的组织认识到了 office 365 的价值。 使用本文作为指导来帮助您规划这些任务。 请参阅[在推出 Office 365 云应用安全性后的使用率活动](utilization-activities-for-ocas.md)。

## <a name="optional-step-9-use-your-siem-server-with-office-365-cloud-app-security"></a>Optional步骤 9: 将 SIEM 服务器与 Office 365 云应用程序安全性结合使用

您的组织是否使用安全信息和事件管理 (SIEM) 服务器？ Office 365 云应用安全现在可以与您的 SIEM 服务器集成以启用对警报的集中式监视。 与 SIEM 服务集成, 使您能够更好地保护云应用程序, 同时维护您的常规安全工作流、自动化安全过程以及在基于云的事件和本地事件之间进行关联。 SIEM 代理在您的服务器上运行, 从 Office 365 云应用程序安全性中提取警报, 并将这些警报流出到您的 SIEM 服务器中。 请参阅[SIEM integration with Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md)。
  
## <a name="next-steps"></a>后续步骤

- [启用 Office 365 云应用安全](turn-on-office-365-cas.md)
    
- 尝试使用我们的[测试实验室指南](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment)获取实践体验, 在这里, 你可以演示 Office 365 云应用安全性的强大功能并创建概念证明。 
    


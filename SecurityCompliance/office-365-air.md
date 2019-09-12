---
title: 自动调查并响应 Office 365 中的威胁
keywords: 空气、autoIR、ATP、自动化、调查、响应、修正、威胁、高级、威胁、保护
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 开始使用 Office 365 中的自动事件响应功能高级威胁防护计划2。
ms.openlocfilehash: a7cec69fc7f739e065503121e456cc9bb3a34b31
ms.sourcegitcommit: ff370e93b792204547694139ef99bc0848304570
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2019
ms.locfileid: "36852754"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a>自动调查并响应 Office 365 中的威胁

## <a name="overview"></a>概述

[Office 365 高级威胁防护](office-365-atp.md)计划2包括自动事件响应（空气）功能，可节省安全操作团队在处理警报和威胁时的时间和工作。 阅读本文，了解如何开始使用 Office 365 中的空中功能。 若要了解有关空中工作方式的详细信息，请参阅[Office 365 中的自动化事件响应（空中）](automated-investigation-response-office.md)。

使用 AIR 时，在触发特定警报时，一个或多个安全行动手册启动，并且自动调查开始。 在自动调查过程期间和之后，管理员和安全操作团队可以执行以下操作：

- [查看调查的详细信息](#view-details-of-an-investigation)

- [查看和批准作为调查结果的操作](#review-and-approve-actions) 

- [查看与调查相关的警报的详细信息](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> 您必须是全局管理员、安全管理员、安全操作员或安全读者才能执行本文中所述的任务。 若要了解详细信息，请参阅[Microsoft 365 安全中心：角色和权限](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。

## <a name="view-details-of-an-investigation"></a>查看调查的详细信息

1. 作为 Office 365 全局管理员、安全管理员或安全阅读者，请转到[https://protection.office.com](https://protection.office.com)并登录。 这将转到安全 & 合规性中心。

2. 执行下列操作之一：

    - 转到 "**威胁管理** > **仪表板**"。 这将转到[安全仪表板](security-dashboard.md)。 您的空中小组件显示在[安全仪表板](security-dashboard.md)的顶部。 选择一个小部件，如**调查摘要**。

    - 转到**威胁管理** > **调查**。 

    每种方法都将转到调查列表。

    ![空气的主要调查页面](media/air-maininvestigationpage.png) 

3. 在调查列表中，选择 " **ID** " 列中的项目。 这将打开 "调查详细信息" 页，从调查图形开始。

    ![空中调查图形页面](media/air-investigationgraphpage.png)

4. 使用各种选项卡了解有关调查的详细信息。

## <a name="review-and-approve-actions"></a>审阅和批准操作

在 Office 365 中，自动调查通常会生成一个或多个建议的操作。 但是，在安全操作团队批准之前，不会执行任何操作。 使用以下过程可查看和审批操作。

1. 作为 Office 365 全局管理员、安全管理员或安全阅读者，请转到[https://protection.office.com](https://protection.office.com)并登录。 

2. 转到**威胁管理** > **调查**。

3. 在调查列表中，选择 " **ID** " 列中的项目。 

3. 在调查详细信息视图中，选择 "**操作**" 选项卡。此处列出了待审批的任何操作。

4. 选择列表项。

5. 选择 "**批准**" 以执行建议的操作（或 "**拒绝**" 以在不采取措施的情况下关闭调查）。

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>查看与调查相关的警报的详细信息

某些类型的警报会触发 Office 365 中的自动调查。 若要了解详细信息，请参阅[警报](automated-investigation-response-office.md#alerts)。 使用以下过程可查看与自动调查相关联的警报的详细信息。

1. 作为 Office 365 全局管理员、安全管理员或安全阅读者，请转到[https://protection.office.com](https://protection.office.com)并登录。 这将转到安全 & 合规性中心。

2. 转到**威胁管理** > **调查**。

3. 在调查列表中，选择 " **ID** " 列中的项目。 

4. 通过打开调查的详细信息，选择 "**通知**" 选项卡。下面列出了所有触发调查的警报。

5. 选择列表项。 将打开一个浮出控件，其中包含有关该警报的详细信息以及指向其他信息和操作的链接。

6. 查看浮出控件上的信息，根据特定的通知执行操作，如**Resolve**、**隐含**或**通知用户**。 

    - **Resolve**等效于关闭通知
    
    - **禁止**使策略在指定时间段内触发警报
    
    - **通知用户**启动电子邮件，其中包含已输入的用户电子邮件地址，并允许安全操作团队向这些用户键入邮件。 （这类似于使用[威胁资源管理器](threat-explorer.md)向收件人发送邮件。）  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>将 Office 365 管理活动 API 用于自定义或第三方报告解决方案

如果您的组织使用自定义或第三方报告解决方案，则可以使用 Office 365 管理活动 API 查看该解决方案中有关自动调查的信息。

使用以下资源对此进行设置：

|资源  |说明  |
|---------|---------|
|[Office 365 管理 API 概述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |使用 Office 365 管理活动 API，可从 Office 365 和 Azure Active Directory 活动日志中获取各个用户、管理员、系统以及策略操作和事件的相关信息。         |
|[Office 365 管理 API 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |Office 365 管理 API 使用 Azure AD 为应用程序提供用于访问 Office 365 数据的身份验证服务。 请按照本文中的步骤进行设置。          |
|[Office 365 管理活动 API 参考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |您可以使用 Office 365 管理活动 API，从 Office 365 和 Azure AD 活动日志中检索有关用户、管理员、系统和策略操作以及事件的信息。 阅读本文以了解有关如何工作的详细信息。        |
|[Office 365 管理活动 API 架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |获取[常见架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)和[office 365 ATP 以及威胁调查和响应架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)的概述，以了解通过 OFFICE 365 管理活动 API 提供的特定类型的数据。         |

## <a name="next-steps"></a>后续步骤

[了解有关通知的详细信息](alert-policies.md)

[手动查找和调查 Office 365 中提供的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)

[了解 Microsoft Defender ATP 中的空气](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[访问 Microsoft 365 路线图以了解即将推出和推出的内容](https://www.microsoft.com/microsoft-365/roadmap?filters=)
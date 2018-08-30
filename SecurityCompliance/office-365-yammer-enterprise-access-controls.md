---
title: Office 365 Yammer Enterprise 访问控制
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 简要概述了有关 Yammer Enterprise 访问控件在生产环境中。
ms.openlocfilehash: 3f51e63c16022353e743b57d8e977f2ea2e6a835
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525925"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="2e29f-103">Yammer Enterprise访问控制</span><span class="sxs-lookup"><span data-stu-id="2e29f-103">Yammer Enterprise Access Controls</span></span> 

<span data-ttu-id="2e29f-p101">物理和逻辑访问 Yammer 生产环境被限制为一组很少的人员 （基础结构和操作）。与其他 Office 365 工程师，Yammer 工程师有零位置访问客户数据。必须使用类似于密码箱，基于审批的实时中访问控制系统请求访问并且没有进行有限的数量的审批者。审批者验证请求 （例如，它们验证该请求是合法的基于需要、 业务案例、 时间等），然后批准或拒绝该请求。如果请求已获得批准，定义和有限的时间，其后它自动过期授予 JIT 访问。</span><span class="sxs-lookup"><span data-stu-id="2e29f-p101">Both physical and logical access to the Yammer production environment is restricted to a very small set of people (infrastructure and operations). As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data. Access must be requested using an approval-based just-in-time access control system similar to Lockbox, and there is a limited number of approvers. Approvers verify the request (e.g., they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request. If the request is approved, JIT access is granted for a defined and limited time, after which it automatically expires.</span></span> 

<span data-ttu-id="2e29f-p102">与其他 Office 365 服务，所有访问 Yammer 生产环境都利用多因素身份验证。所有访问和命令历史记录的用户，并记录和 Yammer 安全工作组由定期检查。</span><span class="sxs-lookup"><span data-stu-id="2e29f-p102">As with other Office 365 services, all access to the Yammer production environment leverages multi-factor authentication. All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="2e29f-111">有关 Yammer 管理的详细信息，请参阅[Yammer 管理帮助](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="2e29f-111">For more information about Yammer administration and management, see [Yammer Admin Help](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span></span>
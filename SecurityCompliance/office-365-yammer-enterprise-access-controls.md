---
title: Office 365 Yammer 企业访问控制
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '摘要: 有关生产环境中 Yammer 企业访问控制的简要摘要。'
ms.openlocfilehash: 76b62e7ea026a52d822e5a213461e930b1d595e3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217882"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="8b511-103">Yammer Enterprise访问控制</span><span class="sxs-lookup"><span data-stu-id="8b511-103">Yammer Enterprise Access Controls</span></span> 

<span data-ttu-id="8b511-p101">对 Yammer 生产环境的物理和逻辑访问仅限于一组非常小的人员 (基础结构和操作)。与其他 Office 365 工程师一样, Yammer 工程师可以获得对客户数据的零访问权限。必须使用基于审批的实时访问控制系统 (类似于密码箱) 请求访问权限, 并且审批者数量有限。审批者验证请求 (例如, 他们根据需求、业务案例、时间等验证请求是否合法), 然后批准或拒绝该请求。如果请求得到批准, 则会为已定义和受限制的时间授予 JIT 访问权限, 之后它将自动过期。</span><span class="sxs-lookup"><span data-stu-id="8b511-p101">Both physical and logical access to the Yammer production environment is restricted to a very small set of people (infrastructure and operations). As with other Office 365 engineers, Yammer engineers have zero standing access to Customer Data. Access must be requested using an approval-based just-in-time access control system similar to Lockbox, and there is a limited number of approvers. Approvers verify the request (e.g., they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request. If the request is approved, JIT access is granted for a defined and limited time, after which it automatically expires.</span></span> 

<span data-ttu-id="8b511-p102">与其他 Office 365 服务一样, 对 Yammer 生产环境的所有访问都利用了多重身份验证。所有访问和命令历史记录都属于用户, 并定期由 Yammer 安全团队记录和查看。</span><span class="sxs-lookup"><span data-stu-id="8b511-p102">As with other Office 365 services, all access to the Yammer production environment leverages multi-factor authentication. All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="8b511-111">有关 yammer 管理和管理的详细信息, 请参阅[Yammer 管理员帮助](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="8b511-111">For more information about Yammer administration and management, see [Yammer Admin Help](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US).</span></span>
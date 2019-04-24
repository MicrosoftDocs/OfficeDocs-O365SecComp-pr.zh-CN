---
title: Office 365 Yammer 企业访问控制
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '摘要: 有关生产环境中 Yammer 企业访问控制的简要摘要。'
ms.openlocfilehash: 61598235a010aaa1c578c449cb054073212a41f9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262344"
---
# <a name="yammer-enterprise-access-controls"></a>Yammer Enterprise访问控制 

对 Yammer 生产环境的物理和逻辑访问仅限于一组非常小的人员 (基础结构和操作)。 与其他 Office 365 工程师一样, Yammer 工程师可以获得对客户数据的零访问权限。 必须使用基于审批的实时访问控制系统 (类似于密码箱) 请求访问权限, 并且审批者数量有限。 审批者验证请求 (例如, 他们根据需求、业务案例、时间等验证请求是否合法), 然后批准或拒绝该请求。 如果请求得到批准, 则会为已定义和受限制的时间授予 JIT 访问权限, 之后它将自动过期。 

与其他 Office 365 服务一样, 对 Yammer 生产环境的所有访问都利用了多重身份验证。 所有访问和命令历史记录都属于用户, 并定期由 Yammer 安全团队记录和查看。

有关 yammer 管理和管理的详细信息, 请参阅[Yammer 管理员帮助](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)。
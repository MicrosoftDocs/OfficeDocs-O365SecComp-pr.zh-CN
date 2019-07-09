---
title: 信息障碍概述
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用信息障碍以确保在组织内使用 Microsoft 团队进行通信合规性。
ms.openlocfilehash: e37c97ae8a5e3777e2a30432e8289abadae8f14c
ms.sourcegitcommit: a6f046f1529b0515f4f0e918a19ec83f4138b871
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2019
ms.locfileid: "35587041"
---
# <a name="information-barriers"></a>信息障碍

## <a name="overview"></a>概述

Microsoft 云服务包括强大的通信和协作功能。 但假设您要限制两个组之间的通信, 以避免组织中发生利益冲突。 或者, 您可能希望限制组织内的某些人之间的通信, 以便保护内部信息。 Microsoft 365 支持跨组和组织进行通信和协作, 因此有一种方法可以在必要时限制特定用户组之间的通信吗？ 通过信息障碍, 你可以! 

现在, 信息障碍即将推出, 从 Microsoft 团队开始。 假定你的[订阅](#required-licenses-and-permissions)包括信息障碍, 合规性管理员或信息屏障管理员可以定义策略以允许或阻止 Microsoft 团队中的用户组之间的通信。 信息屏障策略可用于以下情况:

- 一天 trader 无法对市场营销团队中的人员进行呼叫
- 从事机密公司信息的财务人员无法从其组织内的某些组接收呼叫。
- 具有贸易秘密材料的内部团队无法与组织内特定组中的人员进行在线呼叫或聊天
- 研究团队只能与产品开发团队进行在线通话或聊天

对于所有这些示例方案 (及更多), 可以将信息屏障策略定义为阻止或允许在 Microsoft 团队中进行通信。 此类策略可以阻止用户不应对其进行呼叫或聊天, 或使用户只能与 Microsoft 团队中的特定组进行通信。 在信息屏障策略生效时, 只要这些策略涵盖的用户尝试与 Microsoft 团队中的其他人通信, 就会执行检查以阻止 (或允许) 通信 (由信息屏障策略定义)。 若要了解有关信息障碍的用户体验方面的详细信息, 请参阅[Microsoft 团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

> [!IMPORTANT]
> 目前, 信息障碍不适用于电子邮件通信或通过 SharePoint Online 或 OneDrive 进行文件共享。 此外, 信息障碍独立于[合规性边界](set-up-compliance-boundaries.md)。<p>在定义和应用信息屏障策略之前, 请确保您的组织没有有效的[Exchange 通讯簿策略](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies)。 (信息障碍基于通讯簿策略。) 

## <a name="what-happens-with-information-barriers"></a>信息障碍发生的情况

在信息屏障策略就绪后, 不应与其他特定用户通信的人员将无法找到、选择、聊天或呼叫这些用户。 通过信息障碍, 检查措施可防止未经授权的通信。

最初, 信息障碍仅适用于 Microsoft 团队聊天和频道。 在 Microsoft 团队中, 信息障碍策略决定并阻止以下类型的未经授权的通信:
- 搜索用户
- 向团队添加成员
- 启动与某人的聊天会话
- 启动群聊天
- 邀请某人加入会议
- 共享屏幕
- 发出呼叫 

如果涉及的人员包含在信息屏障策略中以阻止活动, 则无法继续。 此外, 在信息屏障策略中包括的每个人都可以阻止与 Microsoft 团队中的其他人通信。 当受信息障碍策略影响的人员是同一个团队或组聊天的一部分时, 他们可能会从这些聊天会话中删除, 并且可能不允许与组进行进一步通信。

若要了解有关信息障碍的用户体验方面的详细信息, 请参阅[Microsoft 团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

## <a name="required-licenses-and-permissions"></a>必需的许可证和权限

信息屏障现在正在推出, 并包含在订阅中, 如:

- Microsoft 365 E5
- Office 365 E5
- Office 365 高级合规版
- Microsoft 365 E5 信息保护和合规性

有关更多详细信息, 请参阅[合规性解决方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。

若要[定义或编辑信息障碍策略](information-barriers-policies.md), 您必须分配有下列角色之一:

- Microsoft 365 全局管理员
- Office 365 全局管理员
- 合规性管理员
- IB 合规性管理 (这是一个新角色!)

(若要了解有关角色和权限的详细信息, 请参阅[Office 365 Security & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。)

您必须熟悉 PowerShell cmdlet, 才能定义、验证或编辑信息屏障策略。 尽管我们在操作[方法一文](information-barriers-policies.md)中提供了几个 PowerShell cmdlet 示例, 但你需要了解组织的其他详细信息, 如参数。

## <a name="next-steps"></a>后续步骤

- [了解有关 Microsoft 团队中的信息障碍的详细信息](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [请参阅可用于信息屏障策略的属性](information-barriers-attributes.md)

- [定义信息障碍策略](information-barriers-policies.md)

- [编辑 (或删除) 信息屏障策略](information-barriers-edit-segments-policies.md.md) 


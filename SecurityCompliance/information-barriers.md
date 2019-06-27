---
title: 信息障碍概述
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/26/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用信息障碍以确保在组织内使用 Microsoft 团队进行通信合规性。
ms.openlocfilehash: 6565fc28d70ac6ff9a6f4df6edc75b89d19ae29a
ms.sourcegitcommit: 1c254108c522d0cb44023565268b5041d07748aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2019
ms.locfileid: "35279470"
---
# <a name="information-barriers-preview"></a>信息障碍 (预览)

## <a name="overview"></a>概述

Microsoft 云服务包括强大的通信和协作功能。 但假设您要限制两个组之间的通信, 以避免组织中发生利益冲突。 或者, 您可能希望限制组织内的某些人之间的通信, 以便保护内部信息。 Microsoft 365 支持跨组和组织进行通信和协作, 因此有一种方法可以在必要时限制特定用户组之间的通信吗？ 通过信息障碍, 你可以! 

信息障碍现在在预览中, 从 Microsoft 团队开始。 当您的组织可使用这些功能时, 合规性管理员或信息屏障管理员可以定义策略以允许或阻止 Microsoft 团队中的用户组之间的通信。 信息屏障策略可用于以下情况:

- 一天 trader 无法对市场营销团队中的人员进行呼叫
- 从事机密公司信息的财务人员无法从其组织内的某些组接收呼叫。
- 具有贸易秘密材料的内部团队无法与组织内特定组中的人员进行在线呼叫或聊天
- 研究团队只能与产品开发团队进行在线通话或聊天

对于所有这些示例方案 (及更多), 可以将信息屏障策略定义为阻止或允许在 Microsoft 团队中进行通信。 此类策略可以阻止用户不应对其进行呼叫或聊天, 或使用户只能与 Microsoft 团队中的特定组进行通信。 在信息屏障策略生效时, 只要这些策略涵盖的用户尝试与 Microsoft 团队中的其他人通信, 就会执行检查以阻止 (或允许) 通信 (由信息屏障策略定义)。 若要了解有关信息障碍的用户体验方面的详细信息, 请参阅[Microsoft 团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。

> [!NOTE]
> 信息障碍不适用于电子邮件通信或通过 SharePoint Online 或 OneDrive 进行文件共享。 此外, 信息障碍独立于[合规性边界](set-up-compliance-boundaries.md)。

## <a name="required-licenses-and-permissions"></a>必需的许可证和权限

**目前, 信息屏障功能位于私人预览版中**。 当这些功能普遍可用时, 它们将包含在订阅中, 例如:

- Microsoft 365 E5
- Office 365 E5
- Office 365 高级合规版
- Microsoft 365 E5 信息保护和合规性

有关更多详细信息, 请参阅[合规性解决方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。

若要[定义或编辑信息障碍策略](information-barriers-policies.md), 您必须分配有下列角色之一:

- Microsoft 365 全局管理员
- Office 365 全局管理员
- 合规性管理员
- 信息障碍管理员

您必须熟悉 PowerShell cmdlet, 才能定义、验证或编辑信息屏障策略。 尽管我们在操作[方法信息](information-barriers-policies.md)中提供了几个 PowerShell cmdlet 示例, 但你需要了解组织的其他详细信息, 如参数。

## <a name="concepts-of-information-barrier-policies"></a>信息屏障策略的概念

了解信息屏障策略的基本概念很有帮助:

- **用户帐户属性**是在 Azure Active Directory (或 Exchange Online) 中定义的。 这些属性可以包括部门、职务、位置、团队名称和其他作业配置文件详细信息。 

- **分段**是在 Office 365 安全 & 合规性中心中使用选定的**用户帐户属性**定义的用户集。 (请参阅[支持的属性列表](information-barriers-attributes.md)。) 

- **信息屏障策略**决定了通信限制或限制。 在定义信息障碍策略时, 可以从以下两种策略中进行选择:
    - "块" 策略防止一个分段与另一个网段通信。
    - "允许" 策略允许一段仅与某些其他段进行通信。

- **策略应用程序**在定义所有信息屏障策略之后完成, 并准备好在您的组织中应用它们。

## <a name="next-steps"></a>后续步骤

- [了解有关 Microsoft 团队中的信息障碍的详细信息](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [请参阅可用于信息屏障策略的属性](information-barriers-attributes.md)
- [定义信息障碍策略](information-barriers-policies.md) 


---
title: Office 365 中的特权访问管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: 使用本主题可了解有关 Office 365 中的特权访问管理的详细信息
ms.openlocfilehash: 2a464bacaa568515e470e29a0c9c45a91a79cf8e
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001245"
---
# <a name="privileged-access-management-in-office-365"></a>Office 365 中的特权访问管理

> [!IMPORTANT]
> 本主题介绍了 Office 365 E5 和高级合规 sku 中目前仅提供的功能的部署和配置指南。

特权访问管理允许对 Office 365 中的特权管理任务进行精确的访问控制。 它可以帮助保护您的组织免受可能使用现有特权管理员帐户访问敏感数据或访问关键配置设置的访问的危害。 启用特权访问管理后, 用户将需要请求实时访问, 以通过高度范围和时间限制的审批工作流来完成提升和特权的任务。 这为用户提供了足够的访问权限来执行任务, 而不会影响敏感数据或关键配置设置的暴露。 启用 Office 365 中的特权访问管理将使组织能够以零为依据的权限运行, 并针对因此类管理访问而引发的漏洞提供防御措施层。

有关集成客户密码箱和权限访问管理端到端工作流的快速概述, 请参阅此[客户密码箱和 Office 365 视频中的特权访问管理](https://go.microsoft.com/fwlink/?linkid=2066800)。

## <a name="layers-of-protection"></a>保护层

特权访问管理补充了 Office 365 安全体系结构中的其他数据和访问功能保护。 通过启用作为安全性的集成方法和保护组织的一部分的特权访问管理, 可使用分层安全模型来最大限度地保护敏感信息和 Office 365 配置设置。 如下图所示, 启用特权访问管理可帮助基于 office 365 数据的本机加密提供的保护和 office 365 服务的基于角色的访问控制安全模型。 与[Azure AD 特权标识管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)结合使用时, 这两个功能将在不同的范围内提供访问控制和实时访问。

![Office 365 中的分层保护](media/pam-layered-protection.png)

Office 365 中的特权访问管理可以在**任务**级别进行定义和作用域, 而 Azure AD 特权标识管理在**角色**级别应用保护, 并且能够执行多项任务。  Azure ad 特权身份管理主要允许管理 AD 角色和角色组的访问, 而 Office 365 中的特权访问管理则仅适用于任务级别。

- **在已使用 Azure AD 特权身份管理的情况下启用 Office 365 中的特权访问管理:** 在 office 365 中添加特权访问管理提供了另一个粒度层的保护和审核功能, 用于对 Office 365 数据进行特权访问。

- **在使用 Office 365 中的特权访问管理时启用 Azure AD 特权标识管理:** 将 Azure AD 特权标识管理添加到 office 365 中的 "特权访问管理" 可以扩展对 office 365 外部的数据的特权访问, 这些数据主要由用户的角色或标识定义。  

## <a name="privileged-access-management-architecture-and-process-flow"></a>特权访问管理体系结构和过程流

下面的每个过程都将概述权限访问的体系结构, 以及它如何与 office 365 基体、office 365 审核和 Exchange 管理运行空间进行交互。

### <a name="step-1-configuring-a-privileged-access-policy"></a>步骤 1: 配置特权访问策略

在使用[Microsoft 365 管理中心](https://admin.microsoft.com)或 Exchange Management PowerShell 配置特权访问策略时, 您可以创建和定义策略, 权限访问功能将处理 Office 365 基体中的策略属性和将活动记录在 Office 365 安全与合规中心中。 现在, 策略已启用, 并准备好处理审批的传入请求。

![步骤 1-策略创建](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>步骤 2: 访问请求

通过使用[Microsoft 365 管理中心](https://admin.microsoft.com)或 Exchange 管理 PowerShell, 用户可以请求对提升或特权的任务进行访问。 特权访问功能将请求发送到 office 365 基体, 以针对配置的权限访问策略进行处理, 并在 Office 365 安全性和合规性中心日志中记录活动。

![步骤 2-访问请求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>步骤 3: 访问审批

将生成一个审批请求, 并通过电子邮件将挂起的请求通知审批组。 如果授予了审批, 则会将特权访问请求作为审批进行处理, 并准备完成该任务。 如果请求被拒绝, 则会阻止任务, 并且不会向请求者授予任何访问权限。 请求批准或通过电子邮件拒绝的请求程序将收到通知。

![步骤 3-访问审批](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>步骤 4: 访问处理

对于经批准的请求, Exchange 管理运行空间将处理该任务。 根据特权访问策略检查审批, 并由 Office 365 基体进行处理。 任务的所有活动都记录在 Office 365 安全与合规中心中。

![步骤 4-访问处理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>常见问题

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a>使用 Office 365 中的特权访问时, 我需要哪些 sku？
特权访问管理目前仅适用于使用 Office 365 E5 和高级合规性 sku 的客户。

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a>何时将权限访问提供给 Office 365 工作负荷之外的 Exchange？
我们计划在其他 Office 365 工作负载中快速提供此功能。 准备好共享日程表时, 可以通过[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)获取它。

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a>我的组织需要30个以上的权限访问策略, 是否会增加此限制？

我们打算尽快增加每个 Office 365 组织的30个特权访问策略的当前限制。

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>我是否需要成为全局管理员才能管理 Office 365 中的特权访问？
否, 您需要将 Exchange 角色管理角色分配给将在 Office 365 中管理特权访问的帐户。 但是, 如果您不想将角色管理角色配置为独立帐户权限, 全局管理员角色将默认包括此角色, 并且可用于管理特权访问。 包含在审批者组中的用户不需要是全局管理员, 也不需要分配有角色管理角色来审阅和批准请求。

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>Office 365 中的特权访问管理是如何与客户密码箱相关的？
[客户密码箱](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)允许组织对其服务提供商 (例如, Microsoft) 访问数据的访问控制级别。 office 365 中的 "特权访问管理" 允许所有 Office 365 的特权任务在组织内获得精确的访问控制。

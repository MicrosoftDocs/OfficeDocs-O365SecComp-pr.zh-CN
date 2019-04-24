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
ms.openlocfilehash: e03b615971b90e8443f73c3ec8c4cd3febe90450
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261800"
---
# <a name="privileged-access-management-in-office-365"></a>Office 365 中的特权访问管理

> [!IMPORTANT]
> 本主题介绍了 Office 365 E5 和高级合规 sku 中目前仅提供的功能的部署和配置指南。

特权访问管理允许对 Office 365 中的特权管理任务进行精确的访问控制。 它可帮助保护您的组织免受使用现有特权管理员帐户的破坏, 以访问敏感数据或访问关键配置设置。 特权访问管理要求用户通过一个高度范围和时间限制的审批工作流请求实时访问, 以完成提升的特权和特权任务。 这为用户提供了足够的访问权限来执行任务, 而不会影响敏感数据或关键配置设置的暴露。 启用 Office 365 中的 "特权访问管理" 使组织能够以零为依据的权限运行, 并提供了抵御受影响的管理访问漏洞的防御层。

有关集成客户密码箱和特权访问管理工作流的快速概述, 请参阅此[客户密码箱和 Office 365 中的特权访问管理](https://go.microsoft.com/fwlink/?linkid=2066800)。

## <a name="layers-of-protection"></a>保护层

特权访问管理补充了 Office 365 安全体系结构中的其他数据和访问功能保护。 在集成和分层的安全方法中包括特权访问管理提供了一种安全模型, 可以最大限度地保护敏感信息和 Office 365 配置设置。 如图中所示, 特权访问管理基于 office 365 数据的本机加密和 office 365 服务的基于角色的访问控制安全模型提供的保护。 在与[Azure AD 特权标识管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)配合使用时, 这两个功能将在不同的范围内提供对实时访问的访问控制。

![Office 365 中的分层保护](media/pam-layered-protection.png)

Office 365 中的特权访问管理在**任务**级别进行定义和作用域, 而 Azure AD 特权标识管理在**角色**级别应用保护, 从而能够执行多项任务。 Azure ad 特权身份管理主要允许管理 AD 角色和角色组的访问, 而 Office 365 中的特权访问管理则仅适用于任务级别。

- **在已使用 Azure AD 特权身份管理的情况下启用 Office 365 中的特权访问管理:** 在 office 365 中添加特权访问管理提供了另一个粒度层的保护和审核功能, 用于对 Office 365 数据进行特权访问。

- **在使用 Office 365 中的特权访问管理时启用 Azure AD 特权标识管理:** 将 Azure AD 特权标识管理添加到 office 365 中的 "特权访问管理" 可以扩展对 office 365 外部的数据的特权访问, 这些数据主要由用户角色或标识定义。  

## <a name="privileged-access-management-architecture-and-process-flow"></a>特权访问管理体系结构和过程流

下面的每个过程都将概述权限访问的体系结构, 以及它如何与 office 365 基体、office 365 审核和 Exchange 管理运行空间进行交互。

### <a name="step-1-configure-a-privileged-access-policy"></a>步骤 1: 配置特权访问策略

当您使用[Microsoft 365 管理中心](https://admin.microsoft.com)或 Exchange 管理 PowerShell 配置特权访问策略时, 可以在 Office 365 基体中定义策略和特权访问功能进程和策略属性。 这些活动记录在 Office 365 安全与合规中心中。 现在, 策略已启用, 并准备好处理审批的传入请求。

![步骤 1: 策略创建](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>步骤 2: 访问请求

在[Microsoft 365 管理中心](https://admin.microsoft.com)或使用 Exchange 管理 PowerShell 时, 用户可以请求对提升或特权的任务进行访问。 特权访问功能将请求发送到 office 365 基体, 以针对配置的权限访问策略进行处理, 并在 Office 365 安全性和合规性中心日志中记录活动。

![步骤 2: 访问请求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>步骤 3: 访问审批

将生成审批请求, 并通过电子邮件将挂起的请求通知通过电子邮件发送给审批者。 如果得到批准, 则会将特权访问请求作为审批进行处理, 并准备完成该任务。 如果拒绝, 该任务将被阻止, 并且不会向请求者授予任何访问权限。 请求者会收到请求审批或通过电子邮件的拒绝通知请求者。

![步骤 3: 访问审批](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>步骤 4: 访问处理

对于批准的请求, Exchange 管理运行空间将处理该任务。 根据特权访问策略检查审批, 并由 Office 365 基体进行处理。 任务的所有活动都记录在 Office 365 安全与合规中心中。

![步骤 4: 访问处理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>常见问题

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>哪些 sku 可以使用 Office 365 中的特权访问？
具有 Office 365 E5 和高级合规性 sku 的客户可以使用 "特权访问管理"。

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>何时将权限访问支持 Exchange 之外的 Office 365 工作负荷？
在其他 Office 365 工作负载中, 将很快提供特权访问管理。 有关更多详细信息, 请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>我的组织需要30个以上的权限访问策略, 是否会增加此限制？
是, 每个 Office 365 组织的最大30个特权访问策略的限制是功能路线图。

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>我是否需要成为全局管理员才能管理 Office 365 中的特权访问？
否, 您需要分配给在 Office 365 中管理权限访问的帐户的 Exchange 角色管理角色。 如果不希望将 Role Management 角色配置为独立帐户权限, 则全局管理员角色默认情况下包括此角色, 并且可以管理特权访问。 包含在审批者组中的用户不需要是全局管理员或已分配角色管理角色以审阅和批准请求。

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>Office 365 中的特权访问管理是如何与客户密码箱相关的？
[客户密码箱](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)允许在 Microsoft 访问数据时为组织提供级别的访问控制。 office 365 中的 "特权访问管理" 允许所有 Office 365 的特权任务在组织内获得精确的访问控制。

## <a name="ready-to-get-started"></a>准备好开始了吗？

开始[为您的组织配置特权访问管理](privileged-access-management-configuration.md)。

## <a name="learn-more"></a>了解更多信息

[交互式指南: 使用特权访问管理监视和控制管理员任务](https://content.cloudguides.com/en-us/guides/Privileged%20Access%20Management)
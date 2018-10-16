---
title: Office 365 中的管理访问权限
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.custom: Ent_Solutions
ms.assetid: ''
description: 使用本主题可了解有关权限的详细信息访问 Office 365 中的管理
ms.openlocfilehash: e92bbecd5957261c1eaf3088d872ae6572b7f235
ms.sourcegitcommit: 659b5f5b38ef7e838cdb44eaa38c18e48d922768
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "25575336"
---
# <a name="privileged-access-management-in-office-365"></a>Office 365 中的管理访问权限

> [!IMPORTANT]
> 本主题介绍了部署和配置指南仅当前 Office 365 E5 和高级合规性 Sku 中可用的功能。

特权访问管理 Office 365 中允许精细的访问控制拥有权限的管理员任务。 它可以帮助保护您的组织可以使用现有拥有权限的管理员帐户所访问敏感数据或关键的配置设置的访问权限的破坏。启用访问权限的管理后, 用户将需要请求中实时访问完成审批工作流高度范围和限制时间内通过提升和特权任务。这使用户刚刚-足够-访问执行的任务，而冒泄露敏感数据或关键的配置设置。启用访问权限的管理 Office 365 中将启用您的组织具有零个位置权限并提供防御下，因为此类所管理的访问权限的安全漏洞的层。 

## <a name="layers-of-protection"></a>层保护

特权访问管理补充中的 Office 365 安全体系结构的其他数据和访问功能保护。通过启用安全的集成方法的一部分的访问权限的管理和保护您的组织，可用于最大限度地保护敏感信息和 Office 365 配置设置的分层的安全模型。如下图所示下，启用特权访问管理帮助基于提供使用本机数据加密的 Office 365 和 Office 365 服务的基于角色的访问控制安全模型的保护。在与[Azure AD 特权标识管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)一起使用时，这两个功能提供实时中访问在不同的范围的访问控制。

![Office 365 中的分层的保护](media/pam-layered-protection.png)

特权访问 Office 365 中的管理可以定义和 Azure AD 特权身份管理能够执行多个任务适用级别**角色**的保护而**任务**级别范围。 Azure AD 权限身份管理主要允许管理 AD 角色和角色组的访问，Office 365 中的管理访问权限时仅在任务级别上应用。

- **启用特权已在使用 Azure AD 特权身份管理时，访问 Office 365 中的管理：** 添加访问权限的管理 Office 365 中提供特权访问 Office 365 数据保护和审核功能的另一个粒度的层。

- **启用 Azure AD 特权时已使用的身份管理特权访问管理 Office 365 中：** 向特权特权 Azure AD 身份管理 Office 365 中的访问管理可以扩展特权的访问由用户的角色或标识主要定义的 Office 365 以外的数据。  

## <a name="privileged-access-management-architecture-and-process-flow"></a>访问权限的管理体系结构和过程流

下面的过程流的每个大纲权限访问和它如何与 Office 365 基底、 Office 365 审核和 Exchange Management 运行空间交互的体系结构。

### <a name="step-1-configuring-a-privileged-access-policy"></a>步骤 1： 配置特权的访问策略

配置时使用的 Office 365 管理中心或 Exchange Management PowerShell 特权的访问策略，您创建并定义策略和授权的访问功能处理中的 Office 365 基底和日志的策略属性Office 365 安全性和合规性中心中的活动。策略现在，已启用，并准备好处理传入请求审批。

![步骤 1-创建策略](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>步骤 2： 访问请求

使用 Office 365 管理中心或 Exchange Management PowerShell，用户可以请求对提升或特权任务的访问。特权的访问功能将请求发送到 Office 365 基底处理对配置的权限访问策略和记录 sctivity Office 365 安全性和合规性中心日志。

![步骤 2-访问请求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>步骤 3： 访问审核

生成审批请求，并审核组通知通过电子邮件的待处理的请求。如果授予审批，作为审批处理特权的访问请求并准备完成任务。如果请求被拒绝，任务已阻止并且没有访问权限授予 reqeustor。请求者将请求批准或拒绝通过电子邮件通知。

![步骤 3-访问审核](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>步骤 4: Access 处理

批准的请求，由 Exchange 管理运行空间处理任务。审批根据的访问权限的策略检查和处理 Office 365 基底。任务的所有活动都登录的 Office 365 安全性和合规性中心。

![步骤 4-访问处理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>常见问题

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a>使用 Office 365 中的访问权限时，需要哪些 Sku？
特权访问管理是当前仅适用于 Office 365 E5 和高级合规性 Sku 以客户。

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a>何时适用于 Office 365 工作负载超过 Exchange 访问权限？
我们计划推出提供此功能的其他 Office 365 工作负载。我们准备好共享一个日程表，它将提供通过 Office 365 路线图。

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a>我的组织需要多个 30 授权的访问权限策略，将增加此限制？

我们计划以提高当前限制的每个推出 Office 365 组织的 30 特权的访问策略。

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>是否需要为全局管理员管理 Office 365 中的授权访问权限？
您需要能够管理特权的访问 Office 365 中的全局管理员特权。包括在审批者组中的用户不需要是全局管理员才能查看和批准请求。 

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>是与客户密码箱的 Office 365 中的访问权限的管理如何？
[客户密码箱](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2)允许访问由其服务提供商，即 Microsoft 的数据的组织的访问控制的级别。特权访问 Office 365 中的管理允许的所有特权的 Office 365 任务组织内的精细的访问控制。
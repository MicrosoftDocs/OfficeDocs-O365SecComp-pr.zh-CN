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
ms.openlocfilehash: 979587e68ea0cbcf255e087eaaeb38dca4fc7ca1
ms.sourcegitcommit: 0ce722533d72fa8dcc1d8a58d3c649cb345b938d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "24016092"
---
# <a name="privileged-access-management-in-office-365"></a><span data-ttu-id="501bb-103">Office 365 中的管理访问权限</span><span class="sxs-lookup"><span data-stu-id="501bb-103">Privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="501bb-104">本主题介绍了部署和配置指南仅当前 Office 365 E5 和高级合规性 Sku 中可用的功能。</span><span class="sxs-lookup"><span data-stu-id="501bb-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="501bb-p101">特权访问管理 Office 365 中允许精细的访问控制拥有权限的管理员任务。 它可以帮助保护您的组织可以使用现有拥有权限的管理员帐户所访问敏感数据或关键的配置设置的访问权限的破坏。启用访问权限的管理后, 用户将需要请求中实时访问完成审批工作流高度范围和限制时间内通过提升和特权任务。这使用户刚刚-足够-访问执行的任务，而冒泄露敏感数据或关键的配置设置。启用访问权限的管理 Office 365 中将启用您的组织具有零个位置权限并提供防御下，因为此类所管理的访问权限的安全漏洞的层。</span><span class="sxs-lookup"><span data-stu-id="501bb-p101">Privileged access management allows granular access control over privileged admin tasks in Office 365.  It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings. After enabling privileged access management, users will need to request just-in-time access to complete elevated and privileged tasks through an approval workflow that is highly scoped and time-bound. This gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings. Enabling privileged access management in Office 365 will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> 

## <a name="layers-of-protection"></a><span data-ttu-id="501bb-110">层保护</span><span class="sxs-lookup"><span data-stu-id="501bb-110">Layers of protection</span></span>

<span data-ttu-id="501bb-p102">特权访问管理补充中的 Office 365 安全体系结构的其他数据和访问功能保护。通过启用安全的集成方法的一部分的访问权限的管理和保护您的组织，可用于最大限度地保护敏感信息和 Office 365 配置设置的分层的安全模型。如下图所示下，启用特权访问管理帮助基于提供使用本机数据加密的 Office 365 和 Office 365 服务的基于角色的访问控制安全模型的保护。在与[Azure AD 特权标识管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)一起使用时，这两个功能提供实时中访问在不同的范围的访问控制。</span><span class="sxs-lookup"><span data-stu-id="501bb-p102">Privileged access management complements other data and access feature protections within the Office 365 security architecture. By enabling privileged access management as part of an integrated approach to security and protecting your organization, a layered security model can be used to maximize protection of sensitive information and Office 365 configuration settings. As shown in the diagram below, enabling privileged access management helps builds on the protection provided with native encryption of Office 365 data and the role based access control security model of Office 365 services. When used in conjunction with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![Office 365 中的分层的保护](media/pam-layered-protection.jpg)

<span data-ttu-id="501bb-p103">特权访问 Office 365 中的管理可以定义和 Azure AD 特权身份管理能够执行多个任务适用级别**角色**的保护而**任务**级别范围。 Azure AD 权限身份管理主要允许管理 AD 角色和角色组的访问，Office 365 中的管理访问权限时仅在任务级别上应用。</span><span class="sxs-lookup"><span data-stu-id="501bb-p103">Privileged access management in Office 365 can be defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.  Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Office 365 is applied only at the task level.</span></span>

- <span data-ttu-id="501bb-118">**启用特权已在使用 Azure AD 特权身份管理时，访问 Office 365 中的管理：** 添加访问权限的管理 Office 365 中提供特权访问 Office 365 数据保护和审核功能的另一个粒度的层。</span><span class="sxs-lookup"><span data-stu-id="501bb-118">**Enabling privileged access management in Office 365 while already using Azure AD Privileged Identity Management:** Adding privileged access management in Office 365 provides another granular layer of protection and audit capabilities for privileged access to Office 365 data.</span></span>

- <span data-ttu-id="501bb-119">**启用 Azure AD 特权时已使用的身份管理特权访问管理 Office 365 中：** 向特权特权 Azure AD 身份管理 Office 365 中的访问管理可以扩展特权的访问由用户的角色或标识主要定义的 Office 365 以外的数据。</span><span class="sxs-lookup"><span data-stu-id="501bb-119">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management in Office 365 can extend privileged access to data outside of Office 365 that’s primarily defined by a user’s role or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="501bb-120">访问权限的管理体系结构和过程流</span><span class="sxs-lookup"><span data-stu-id="501bb-120">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="501bb-121">下面的过程流的每个大纲权限访问和它如何与 Office 365 基底、 Office 365 审核和 Exchange Management 运行空间交互的体系结构。</span><span class="sxs-lookup"><span data-stu-id="501bb-121">Each of the following process flows outline the architecture of priveleged access and how it interacts with the Office 365 substrate, Office 365 auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configuring-a-privileged-access-policy"></a><span data-ttu-id="501bb-122">步骤 1： 配置特权的访问策略</span><span class="sxs-lookup"><span data-stu-id="501bb-122">Step 1: Configuring a privileged access policy</span></span>

<span data-ttu-id="501bb-p104">配置时使用的 Office 365 管理中心或 Exchange Management PowerShell 特权的访问策略，您创建并定义策略和授权的访问功能处理中的 Office 365 基底和日志的策略属性Office 365 安全性和合规性中心中的活动。策略现在，已启用，并准备好处理传入请求审批。</span><span class="sxs-lookup"><span data-stu-id="501bb-p104">When configuring a privileged access policy using either the Office 365 Admin Center or Exchange Management PowerShell, you create and define the policy and the privileged access feature processes the policy attributes in the Office 365 substrate and logs the activity in the Office 365 Security and Compliance Center. The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![步骤 1-创建策略](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="501bb-126">步骤 2： 访问请求</span><span class="sxs-lookup"><span data-stu-id="501bb-126">Step 2: Access request</span></span>

<span data-ttu-id="501bb-p105">使用 Office 365 管理中心或 Exchange Management PowerShell，用户可以请求对提升或特权任务的访问。特权的访问功能将请求发送到 Office 365 基底处理对配置的权限访问策略和记录 sctivity Office 365 安全性和合规性中心日志。</span><span class="sxs-lookup"><span data-stu-id="501bb-p105">Using the Office 365 Admin Center or Exchange Management PowerShell, users can request access to elevated or privileged tasks. The privileged access feature sends the request to the Office 365 substrate for processing against the configured privilege access policy and records the sctivity in the Office 365 Security and Compliance Center logs.</span></span>

![步骤 2-访问请求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="501bb-130">步骤 3： 访问审核</span><span class="sxs-lookup"><span data-stu-id="501bb-130">Step 3: Access approval</span></span>

<span data-ttu-id="501bb-p106">生成审批请求，并审核组通知通过电子邮件的待处理的请求。如果授予审批，作为审批处理特权的访问请求并准备完成任务。如果请求被拒绝，任务已阻止并且没有访问权限授予 reqeustor。</span><span class="sxs-lookup"><span data-stu-id="501bb-p106">An approval request is generated and the approval group is notified by email of the pending request. If approval is granted, the privileged access request is processed as an approval and the task is ready to be completed. If the request is denied, task is block and no access is granted to the reqeustor.</span></span>

![步骤 3-访问审核](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="501bb-135">步骤 4: Access 处理</span><span class="sxs-lookup"><span data-stu-id="501bb-135">Step 4: Access processing</span></span>

<span data-ttu-id="501bb-p107">批准的请求，由 Exchange 管理运行空间处理任务。审批根据的访问权限的策略检查和处理 Office 365 基底。任务的所有活动都登录的 Office 365 安全性和合规性中心。</span><span class="sxs-lookup"><span data-stu-id="501bb-p107">For approved requests, the task is processed by the Exchange Management runspace. The approval is checked against the privileged access policy and processed by the Office 365 substrate. All activity for the task is logged in the Office 365 Security and Compliance Center.</span></span>

![步骤 4-访问处理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="501bb-140">常见问题</span><span class="sxs-lookup"><span data-stu-id="501bb-140">Frequently asked questions</span></span>

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a><span data-ttu-id="501bb-141">使用 Office 365 中的访问权限时，需要哪些 Sku？</span><span class="sxs-lookup"><span data-stu-id="501bb-141">What SKUs do I need to use privileged access in Office 365?</span></span>
<span data-ttu-id="501bb-142">特权访问 Office 365 中的管理是当前仅适用于以 E5 和高级合规性 Sku 客户。</span><span class="sxs-lookup"><span data-stu-id="501bb-142">Privileged access management in Office 365 is currently only available for customers with E5 and Advanced Compliance SKUs.</span></span>

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a><span data-ttu-id="501bb-143">何时适用于 Office 365 工作负载超过 Exchange 访问权限？</span><span class="sxs-lookup"><span data-stu-id="501bb-143">When will privileged access be available for Office 365 workloads beyond Exchange?</span></span>
<span data-ttu-id="501bb-p108">我们计划推出提供此功能的其他 Office 365 工作负载。我们准备好共享一个日程表，它将提供通过 Office 365 路线图。</span><span class="sxs-lookup"><span data-stu-id="501bb-p108">We plan to offer this feature in other Office 365 workloads soon. When we’re ready to share a timeline, it will be available through the Office 365 roadmap.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="501bb-146">是否需要为全局管理员管理 Office 365 中的授权访问权限？</span><span class="sxs-lookup"><span data-stu-id="501bb-146">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>
<span data-ttu-id="501bb-p109">您需要能够管理特权的访问 Office 365 中的全局管理员特权。包括在审批者组中的用户不需要是全局管理员才能查看和批准请求。</span><span class="sxs-lookup"><span data-stu-id="501bb-p109">You need to have Global Admin privilege to be able to manage privileged access in Office 365. Users who are included in an approvers’ group don't need to be a Global Admin to review and approve requests.</span></span> 

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a><span data-ttu-id="501bb-149">是与客户密码箱的 Office 365 中的访问权限的管理如何？</span><span class="sxs-lookup"><span data-stu-id="501bb-149">How is privileged access management in Office 365 related to Customer Lockbox?</span></span>
<span data-ttu-id="501bb-p110">[客户密码箱](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2)允许访问由其服务提供商，即 Microsoft 的数据的组织的访问控制的级别。特权访问 Office 365 中的管理允许的所有特权的 Office 365 任务组织内的精细的访问控制。</span><span class="sxs-lookup"><span data-stu-id="501bb-p110">[Customer Lockbox](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2) allows a level of access control for organizations for access to to data by their service provider, i.e. Microsoft. Privileged access management in Office 365 allows granular access control within an organization for all Office 365 privileged tasks.</span></span>
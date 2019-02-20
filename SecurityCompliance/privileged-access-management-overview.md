---
title: Office 365 中的特权访问管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: 使用本主题可了解有关 Office 365 中的特权访问管理的详细信息
ms.openlocfilehash: 78107ceb497a546ef4d19ba33b8b72ec1406de1b
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090794"
---
# <a name="privileged-access-management-in-office-365"></a><span data-ttu-id="b9269-103">Office 365 中的特权访问管理</span><span class="sxs-lookup"><span data-stu-id="b9269-103">Privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9269-104">本主题介绍了 Office 365 E5 和高级合规 sku 中目前仅提供的功能的部署和配置指南。</span><span class="sxs-lookup"><span data-stu-id="b9269-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="b9269-p101">特权访问管理允许对 Office 365 中的特权管理任务进行精确的访问控制。它可以帮助保护您的组织免受可能使用现有特权管理员帐户访问敏感数据或访问关键配置设置的访问的危害。启用特权访问管理后, 用户将需要请求实时访问, 以通过高度范围和时间限制的审批工作流来完成提升和特权的任务。这为用户提供了足够的访问权限来执行任务, 而不会影响敏感数据或关键配置设置的暴露。启用 Office 365 中的特权访问管理将使组织能够以零为依据的权限运行, 并针对因此类管理访问而引发的漏洞提供防御措施层。</span><span class="sxs-lookup"><span data-stu-id="b9269-p101">Privileged access management allows granular access control over privileged admin tasks in Office 365. It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings. After enabling privileged access management, users will need to request just-in-time access to complete elevated and privileged tasks through an approval workflow that is highly scoped and time-bound. This gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings. Enabling privileged access management in Office 365 will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span>

<span data-ttu-id="b9269-110">有关集成客户密码箱和权限访问管理端到端工作流的快速概述, 请参阅此[客户密码箱和 Office 365 视频中的特权访问管理](https://go.microsoft.com/fwlink/?linkid=2066800)。</span><span class="sxs-lookup"><span data-stu-id="b9269-110">For a quick overview of the integrated Customer Lockbox and privileged access management end-to-end workflow, see this [Customer Lockbox and privileged access management in Office 365 video](https://go.microsoft.com/fwlink/?linkid=2066800).</span></span>

## <a name="layers-of-protection"></a><span data-ttu-id="b9269-111">保护层</span><span class="sxs-lookup"><span data-stu-id="b9269-111">Layers of protection</span></span>

<span data-ttu-id="b9269-p102">特权访问管理补充了 Office 365 安全体系结构中的其他数据和访问功能保护。通过启用作为安全性的集成方法和保护组织的一部分的特权访问管理, 可使用分层安全模型来最大限度地保护敏感信息和 Office 365 配置设置。如下图所示, 启用特权访问管理可帮助基于 office 365 数据的本机加密提供的保护和 office 365 服务的基于角色的访问控制安全模型。与[Azure AD 特权标识管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)结合使用时, 这两个功能将在不同的范围内提供访问控制和实时访问。</span><span class="sxs-lookup"><span data-stu-id="b9269-p102">Privileged access management complements other data and access feature protections within the Office 365 security architecture. By enabling privileged access management as part of an integrated approach to security and protecting your organization, a layered security model can be used to maximize protection of sensitive information and Office 365 configuration settings. As shown in the diagram below, enabling privileged access management helps builds on the protection provided with native encryption of Office 365 data and the role based access control security model of Office 365 services. When used in conjunction with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![Office 365 中的分层保护](media/pam-layered-protection.png)

<span data-ttu-id="b9269-p103">Office 365 中的特权访问管理可以在**任务**级别进行定义和作用域, 而 Azure AD 特权标识管理在**角色**级别应用保护, 并且能够执行多项任务。 Azure ad 特权身份管理主要允许管理 AD 角色和角色组的访问, 而 Office 365 中的特权访问管理则仅适用于任务级别。</span><span class="sxs-lookup"><span data-stu-id="b9269-p103">Privileged access management in Office 365 can be defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.  Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Office 365 is applied only at the task level.</span></span>

- <span data-ttu-id="b9269-119">**在已使用 Azure AD 特权身份管理的情况下启用 Office 365 中的特权访问管理:** 在 office 365 中添加特权访问管理提供了另一个粒度层的保护和审核功能, 用于对 Office 365 数据进行特权访问。</span><span class="sxs-lookup"><span data-stu-id="b9269-119">**Enabling privileged access management in Office 365 while already using Azure AD Privileged Identity Management:** Adding privileged access management in Office 365 provides another granular layer of protection and audit capabilities for privileged access to Office 365 data.</span></span>

- <span data-ttu-id="b9269-120">**在使用 Office 365 中的特权访问管理时启用 Azure AD 特权标识管理:** 将 Azure AD 特权标识管理添加到 office 365 中的 "特权访问管理" 可以扩展对 office 365 外部的数据的特权访问, 这些数据主要由用户的角色或标识定义。</span><span class="sxs-lookup"><span data-stu-id="b9269-120">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management in Office 365 can extend privileged access to data outside of Office 365 that’s primarily defined by a user’s role or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="b9269-121">特权访问管理体系结构和过程流</span><span class="sxs-lookup"><span data-stu-id="b9269-121">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="b9269-122">下面的每个过程都将概述 priveleged 访问的体系结构, 以及它如何与 office 365 基体、office 365 审核和 Exchange 管理运行空间进行交互。</span><span class="sxs-lookup"><span data-stu-id="b9269-122">Each of the following process flows outline the architecture of priveleged access and how it interacts with the Office 365 substrate, Office 365 auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configuring-a-privileged-access-policy"></a><span data-ttu-id="b9269-123">步骤 1: 配置特权访问策略</span><span class="sxs-lookup"><span data-stu-id="b9269-123">Step 1: Configuring a privileged access policy</span></span>

<span data-ttu-id="b9269-p104">在使用 Office 365 管理中心或 Exchange Management PowerShell 配置特权访问策略时, 您可以创建和定义策略, 权限访问功能将处理 office 365 基体中的策略属性并记录Office 365 安全与合规中心中的活动。现在, 策略已启用, 并准备好处理审批的传入请求。</span><span class="sxs-lookup"><span data-stu-id="b9269-p104">When configuring a privileged access policy using either the Office 365 Admin Center or Exchange Management PowerShell, you create and define the policy and the privileged access feature processes the policy attributes in the Office 365 substrate and logs the activity in the Office 365 Security and Compliance Center. The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![步骤 1-策略创建](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="b9269-127">步骤 2: 访问请求</span><span class="sxs-lookup"><span data-stu-id="b9269-127">Step 2: Access request</span></span>

<span data-ttu-id="b9269-p105">通过使用 Office 365 管理中心或 Exchange 管理 PowerShell, 用户可以请求对提升或特权的任务进行访问。特权访问功能将请求发送到 office 365 基体, 以针对配置的权限访问策略进行处理, 并在 office 365 安全性和合规性中心日志中记录 sctivity。</span><span class="sxs-lookup"><span data-stu-id="b9269-p105">Using the Office 365 Admin Center or Exchange Management PowerShell, users can request access to elevated or privileged tasks. The privileged access feature sends the request to the Office 365 substrate for processing against the configured privilege access policy and records the sctivity in the Office 365 Security and Compliance Center logs.</span></span>

![步骤 2-访问请求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="b9269-131">步骤 3: 访问审批</span><span class="sxs-lookup"><span data-stu-id="b9269-131">Step 3: Access approval</span></span>

<span data-ttu-id="b9269-p106">将生成一个审批请求, 并通过电子邮件将挂起的请求通知审批组。如果授予了审批, 则会将特权访问请求作为审批进行处理, 并准备完成该任务。如果请求被拒绝, 则会阻止任务, 并且不会向 reqeustor 授予任何访问权限。请求批准或通过电子邮件拒绝的请求程序将收到通知。</span><span class="sxs-lookup"><span data-stu-id="b9269-p106">An approval request is generated and the approval group is notified by email of the pending request. If approval is granted, the privileged access request is processed as an approval and the task is ready to be completed. If the request is denied, task is blocked and no access is granted to the reqeustor. The requestor will be notified of the request approval or denial via email message.</span></span>

![步骤 3-访问审批](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="b9269-137">步骤 4: 访问处理</span><span class="sxs-lookup"><span data-stu-id="b9269-137">Step 4: Access processing</span></span>

<span data-ttu-id="b9269-p107">对于经批准的请求, Exchange 管理运行空间将处理该任务。根据特权访问策略检查审批, 并由 Office 365 基体进行处理。任务的所有活动都记录在 Office 365 安全与合规中心中。</span><span class="sxs-lookup"><span data-stu-id="b9269-p107">For approved requests, the task is processed by the Exchange Management runspace. The approval is checked against the privileged access policy and processed by the Office 365 substrate. All activity for the task is logged in the Office 365 Security and Compliance Center.</span></span>

![步骤 4-访问处理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="b9269-142">常见问题</span><span class="sxs-lookup"><span data-stu-id="b9269-142">Frequently asked questions</span></span>

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a><span data-ttu-id="b9269-143">使用 Office 365 中的特权访问时, 我需要哪些 sku？</span><span class="sxs-lookup"><span data-stu-id="b9269-143">What SKUs do I need to use privileged access in Office 365?</span></span>
<span data-ttu-id="b9269-144">特权访问管理目前仅适用于使用 Office 365 E5 和高级合规性 sku 的客户。</span><span class="sxs-lookup"><span data-stu-id="b9269-144">Privileged access management is currently only available for customers with Office 365 E5 and Advanced Compliance SKUs.</span></span>

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a><span data-ttu-id="b9269-145">何时将权限访问提供给 Office 365 工作负荷之外的 Exchange？</span><span class="sxs-lookup"><span data-stu-id="b9269-145">When will privileged access be available for Office 365 workloads beyond Exchange?</span></span>
<span data-ttu-id="b9269-p108">我们计划在其他 Office 365 工作负载中快速提供此功能。准备好共享日程表时, 可以通过[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)获取它。</span><span class="sxs-lookup"><span data-stu-id="b9269-p108">We plan to offer this feature in other Office 365 workloads soon. When we’re ready to share a timeline, it will be available through the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a><span data-ttu-id="b9269-148">我的组织需要30个以上的权限访问策略, 是否会增加此限制？</span><span class="sxs-lookup"><span data-stu-id="b9269-148">My organization needs more than 30 privileged access polices, will this limit be increased?</span></span>

<span data-ttu-id="b9269-149">我们打算尽快增加每个 Office 365 组织的30个特权访问策略的当前限制。</span><span class="sxs-lookup"><span data-stu-id="b9269-149">We're planning to increase the current limit of 30 privileged access policies per Office 365 organization soon.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="b9269-150">我是否需要成为全局管理员才能管理 Office 365 中的特权访问？</span><span class="sxs-lookup"><span data-stu-id="b9269-150">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>
<span data-ttu-id="b9269-p109">否, 您需要将 Exchange 角色管理角色分配给将在 Office 365 中管理特权访问的帐户。但是, 如果您不想将角色管理角色配置为独立帐户权限, 全局管理员角色将默认包括此角色, 并且可用于管理特权访问。包含在审批者组中的用户不需要是全局管理员, 也不需要分配有角色管理角色来审阅和批准请求。</span><span class="sxs-lookup"><span data-stu-id="b9269-p109">No, you need to have the Exchange Role Management role assigned to accounts that will manage privileged access in Office 365. However, the Global Administrator role includes this role by default and can be used to manage privileged access if you don’t want to configure the Role Management role as a stand-alone account permission. Users who are included in an approvers’ group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests.</span></span> 

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a><span data-ttu-id="b9269-154">Office 365 中的特权访问管理是如何与客户密码箱相关的？</span><span class="sxs-lookup"><span data-stu-id="b9269-154">How is privileged access management in Office 365 related to Customer Lockbox?</span></span>
<span data-ttu-id="b9269-p110">[客户密码箱](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)允许组织对其服务提供商 (例如, Microsoft) 访问数据的访问控制级别。office 365 中的 "特权访问管理" 允许所有 Office 365 的特权任务在组织内获得精确的访问控制。</span><span class="sxs-lookup"><span data-stu-id="b9269-p110">[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations for access to to data by their service provider, i.e. Microsoft. Privileged access management in Office 365 allows granular access control within an organization for all Office 365 privileged tasks.</span></span>

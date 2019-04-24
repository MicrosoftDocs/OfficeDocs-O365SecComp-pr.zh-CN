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
# <a name="privileged-access-management-in-office-365"></a><span data-ttu-id="71a25-103">Office 365 中的特权访问管理</span><span class="sxs-lookup"><span data-stu-id="71a25-103">Privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71a25-104">本主题介绍了 Office 365 E5 和高级合规 sku 中目前仅提供的功能的部署和配置指南。</span><span class="sxs-lookup"><span data-stu-id="71a25-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="71a25-105">特权访问管理允许对 Office 365 中的特权管理任务进行精确的访问控制。</span><span class="sxs-lookup"><span data-stu-id="71a25-105">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="71a25-106">它可帮助保护您的组织免受使用现有特权管理员帐户的破坏, 以访问敏感数据或访问关键配置设置。</span><span class="sxs-lookup"><span data-stu-id="71a25-106">It can help protect your organization from breaches that use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="71a25-107">特权访问管理要求用户通过一个高度范围和时间限制的审批工作流请求实时访问, 以完成提升的特权和特权任务。</span><span class="sxs-lookup"><span data-stu-id="71a25-107">Privileged access management requires users to request just-in-time access to complete elevated and privileged tasks through a highly scoped and time-bounded approval workflow.</span></span> <span data-ttu-id="71a25-108">这为用户提供了足够的访问权限来执行任务, 而不会影响敏感数据或关键配置设置的暴露。</span><span class="sxs-lookup"><span data-stu-id="71a25-108">This gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings.</span></span> <span data-ttu-id="71a25-109">启用 Office 365 中的 "特权访问管理" 使组织能够以零为依据的权限运行, 并提供了抵御受影响的管理访问漏洞的防御层。</span><span class="sxs-lookup"><span data-stu-id="71a25-109">Enabling privileged access management in Office 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

<span data-ttu-id="71a25-110">有关集成客户密码箱和特权访问管理工作流的快速概述, 请参阅此[客户密码箱和 Office 365 中的特权访问管理](https://go.microsoft.com/fwlink/?linkid=2066800)。</span><span class="sxs-lookup"><span data-stu-id="71a25-110">For a quick overview of the integrated Customer Lockbox and privileged access management workflow, see this [Customer Lockbox and privileged access management in Office 365 video](https://go.microsoft.com/fwlink/?linkid=2066800).</span></span>

## <a name="layers-of-protection"></a><span data-ttu-id="71a25-111">保护层</span><span class="sxs-lookup"><span data-stu-id="71a25-111">Layers of protection</span></span>

<span data-ttu-id="71a25-112">特权访问管理补充了 Office 365 安全体系结构中的其他数据和访问功能保护。</span><span class="sxs-lookup"><span data-stu-id="71a25-112">Privileged access management complements other data and access feature protections within the Office 365 security architecture.</span></span> <span data-ttu-id="71a25-113">在集成和分层的安全方法中包括特权访问管理提供了一种安全模型, 可以最大限度地保护敏感信息和 Office 365 配置设置。</span><span class="sxs-lookup"><span data-stu-id="71a25-113">Including privileged access management as part of an integrated and layered approach to security provides a security model that maximizes protection of sensitive information and Office 365 configuration settings.</span></span> <span data-ttu-id="71a25-114">如图中所示, 特权访问管理基于 office 365 数据的本机加密和 office 365 服务的基于角色的访问控制安全模型提供的保护。</span><span class="sxs-lookup"><span data-stu-id="71a25-114">As shown in the diagram, privileged access management builds on the protection provided with native encryption of Office 365 data and the role-based access control security model of Office 365 services.</span></span> <span data-ttu-id="71a25-115">在与[Azure AD 特权标识管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)配合使用时, 这两个功能将在不同的范围内提供对实时访问的访问控制。</span><span class="sxs-lookup"><span data-stu-id="71a25-115">When used with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![Office 365 中的分层保护](media/pam-layered-protection.png)

<span data-ttu-id="71a25-117">Office 365 中的特权访问管理在**任务**级别进行定义和作用域, 而 Azure AD 特权标识管理在**角色**级别应用保护, 从而能够执行多项任务。</span><span class="sxs-lookup"><span data-stu-id="71a25-117">Privileged access management in Office 365 is defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.</span></span> <span data-ttu-id="71a25-118">Azure ad 特权身份管理主要允许管理 AD 角色和角色组的访问, 而 Office 365 中的特权访问管理则仅适用于任务级别。</span><span class="sxs-lookup"><span data-stu-id="71a25-118">Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Office 365 applies only at the task level.</span></span>

- <span data-ttu-id="71a25-119">**在已使用 Azure AD 特权身份管理的情况下启用 Office 365 中的特权访问管理:** 在 office 365 中添加特权访问管理提供了另一个粒度层的保护和审核功能, 用于对 Office 365 数据进行特权访问。</span><span class="sxs-lookup"><span data-stu-id="71a25-119">**Enabling privileged access management in Office 365 while already using Azure AD Privileged Identity Management:** Adding privileged access management in Office 365 provides another granular layer of protection and audit capabilities for privileged access to Office 365 data.</span></span>

- <span data-ttu-id="71a25-120">**在使用 Office 365 中的特权访问管理时启用 Azure AD 特权标识管理:** 将 Azure AD 特权标识管理添加到 office 365 中的 "特权访问管理" 可以扩展对 office 365 外部的数据的特权访问, 这些数据主要由用户角色或标识定义。</span><span class="sxs-lookup"><span data-stu-id="71a25-120">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management in Office 365 can extend privileged access to data outside of Office 365 that’s primarily defined by user roles or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="71a25-121">特权访问管理体系结构和过程流</span><span class="sxs-lookup"><span data-stu-id="71a25-121">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="71a25-122">下面的每个过程都将概述权限访问的体系结构, 以及它如何与 office 365 基体、office 365 审核和 Exchange 管理运行空间进行交互。</span><span class="sxs-lookup"><span data-stu-id="71a25-122">Each of the following process flows outline the architecture of privileged access and how it interacts with the Office 365 substrate, Office 365 auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configure-a-privileged-access-policy"></a><span data-ttu-id="71a25-123">步骤 1: 配置特权访问策略</span><span class="sxs-lookup"><span data-stu-id="71a25-123">Step 1: Configure a privileged access policy</span></span>

<span data-ttu-id="71a25-124">当您使用[Microsoft 365 管理中心](https://admin.microsoft.com)或 Exchange 管理 PowerShell 配置特权访问策略时, 可以在 Office 365 基体中定义策略和特权访问功能进程和策略属性。</span><span class="sxs-lookup"><span data-stu-id="71a25-124">When you configure a privileged access policy with the [Microsoft 365 admin center](https://admin.microsoft.com) or the Exchange Management PowerShell, you define the policy and the privileged access feature processes and the policy attributes in the Office 365 substrate.</span></span> <span data-ttu-id="71a25-125">这些活动记录在 Office 365 安全与合规中心中。</span><span class="sxs-lookup"><span data-stu-id="71a25-125">The activities are logged in the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="71a25-126">现在, 策略已启用, 并准备好处理审批的传入请求。</span><span class="sxs-lookup"><span data-stu-id="71a25-126">The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![步骤 1: 策略创建](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="71a25-128">步骤 2: 访问请求</span><span class="sxs-lookup"><span data-stu-id="71a25-128">Step 2: Access request</span></span>

<span data-ttu-id="71a25-129">在[Microsoft 365 管理中心](https://admin.microsoft.com)或使用 Exchange 管理 PowerShell 时, 用户可以请求对提升或特权的任务进行访问。</span><span class="sxs-lookup"><span data-stu-id="71a25-129">In the [Microsoft 365 admin center](https://admin.microsoft.com) or with the Exchange Management PowerShell, users can request access to elevated or privileged tasks.</span></span> <span data-ttu-id="71a25-130">特权访问功能将请求发送到 office 365 基体, 以针对配置的权限访问策略进行处理, 并在 Office 365 安全性和合规性中心日志中记录活动。</span><span class="sxs-lookup"><span data-stu-id="71a25-130">The privileged access feature sends the request to the Office 365 substrate for processing against the configured privilege access policy and records the Activity in the Office 365 Security and Compliance Center logs.</span></span>

![步骤 2: 访问请求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="71a25-132">步骤 3: 访问审批</span><span class="sxs-lookup"><span data-stu-id="71a25-132">Step 3: Access approval</span></span>

<span data-ttu-id="71a25-133">将生成审批请求, 并通过电子邮件将挂起的请求通知通过电子邮件发送给审批者。</span><span class="sxs-lookup"><span data-stu-id="71a25-133">An approval request is generated and the pending request notification is emailed to approvers.</span></span> <span data-ttu-id="71a25-134">如果得到批准, 则会将特权访问请求作为审批进行处理, 并准备完成该任务。</span><span class="sxs-lookup"><span data-stu-id="71a25-134">If approved, the privileged access request is processed as an approval and the task is ready to be completed.</span></span> <span data-ttu-id="71a25-135">如果拒绝, 该任务将被阻止, 并且不会向请求者授予任何访问权限。</span><span class="sxs-lookup"><span data-stu-id="71a25-135">If denied, the task is blocked and no access is granted to the requestor.</span></span> <span data-ttu-id="71a25-136">请求者会收到请求审批或通过电子邮件的拒绝通知请求者。</span><span class="sxs-lookup"><span data-stu-id="71a25-136">The requestor is notified of the request approval or denial via email message.</span></span>

![步骤 3: 访问审批](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="71a25-138">步骤 4: 访问处理</span><span class="sxs-lookup"><span data-stu-id="71a25-138">Step 4: Access processing</span></span>

<span data-ttu-id="71a25-139">对于批准的请求, Exchange 管理运行空间将处理该任务。</span><span class="sxs-lookup"><span data-stu-id="71a25-139">For an approved request, the task is processed by the Exchange Management runspace.</span></span> <span data-ttu-id="71a25-140">根据特权访问策略检查审批, 并由 Office 365 基体进行处理。</span><span class="sxs-lookup"><span data-stu-id="71a25-140">The approval is checked against the privileged access policy and processed by the Office 365 substrate.</span></span> <span data-ttu-id="71a25-141">任务的所有活动都记录在 Office 365 安全与合规中心中。</span><span class="sxs-lookup"><span data-stu-id="71a25-141">All activity for the task is logged in the Office 365 Security and Compliance Center.</span></span>

![步骤 4: 访问处理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="71a25-143">常见问题</span><span class="sxs-lookup"><span data-stu-id="71a25-143">Frequently asked questions</span></span>

### <a name="what-skus-can-use-privileged-access-in-office-365"></a><span data-ttu-id="71a25-144">哪些 sku 可以使用 Office 365 中的特权访问？</span><span class="sxs-lookup"><span data-stu-id="71a25-144">What SKUs can use privileged access in Office 365?</span></span>
<span data-ttu-id="71a25-145">具有 Office 365 E5 和高级合规性 sku 的客户可以使用 "特权访问管理"。</span><span class="sxs-lookup"><span data-stu-id="71a25-145">Privileged access management is available for customers with Office 365 E5 and Advanced Compliance SKUs.</span></span>

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a><span data-ttu-id="71a25-146">何时将权限访问支持 Exchange 之外的 Office 365 工作负荷？</span><span class="sxs-lookup"><span data-stu-id="71a25-146">When will privileged access support Office 365 workloads beyond Exchange?</span></span>
<span data-ttu-id="71a25-147">在其他 Office 365 工作负载中, 将很快提供特权访问管理。</span><span class="sxs-lookup"><span data-stu-id="71a25-147">Privileged access management will be available in other Office 365 workloads soon.</span></span> <span data-ttu-id="71a25-148">有关更多详细信息, 请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="71a25-148">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) for more details.</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a><span data-ttu-id="71a25-149">我的组织需要30个以上的权限访问策略, 是否会增加此限制？</span><span class="sxs-lookup"><span data-stu-id="71a25-149">My organization needs more than 30 privileged access policies, will this limit be increased?</span></span>
<span data-ttu-id="71a25-150">是, 每个 Office 365 组织的最大30个特权访问策略的限制是功能路线图。</span><span class="sxs-lookup"><span data-stu-id="71a25-150">Yes, raising the current limit of 30 privileged access policies per Office 365 organization is on the feature roadmap.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="71a25-151">我是否需要成为全局管理员才能管理 Office 365 中的特权访问？</span><span class="sxs-lookup"><span data-stu-id="71a25-151">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>
<span data-ttu-id="71a25-152">否, 您需要分配给在 Office 365 中管理权限访问的帐户的 Exchange 角色管理角色。</span><span class="sxs-lookup"><span data-stu-id="71a25-152">No, you need the Exchange Role Management role assigned to accounts that manage privileged access in Office 365.</span></span> <span data-ttu-id="71a25-153">如果不希望将 Role Management 角色配置为独立帐户权限, 则全局管理员角色默认情况下包括此角色, 并且可以管理特权访问。</span><span class="sxs-lookup"><span data-stu-id="71a25-153">If you don’t want to configure the Role Management role as a stand-alone account permission, the Global Administrator role includes this role by default and can manage privileged access.</span></span> <span data-ttu-id="71a25-154">包含在审批者组中的用户不需要是全局管理员或已分配角色管理角色以审阅和批准请求。</span><span class="sxs-lookup"><span data-stu-id="71a25-154">Users included in an approvers’ group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests.</span></span>

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a><span data-ttu-id="71a25-155">Office 365 中的特权访问管理是如何与客户密码箱相关的？</span><span class="sxs-lookup"><span data-stu-id="71a25-155">How is privileged access management in Office 365 related to Customer Lockbox?</span></span>
<span data-ttu-id="71a25-156">[客户密码箱](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)允许在 Microsoft 访问数据时为组织提供级别的访问控制。</span><span class="sxs-lookup"><span data-stu-id="71a25-156">[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations when Microsoft accesses data.</span></span> <span data-ttu-id="71a25-157">office 365 中的 "特权访问管理" 允许所有 Office 365 的特权任务在组织内获得精确的访问控制。</span><span class="sxs-lookup"><span data-stu-id="71a25-157">Privileged access management in Office 365 allows granular access control within an organization for all Office 365 privileged tasks.</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="71a25-158">准备好开始了吗？</span><span class="sxs-lookup"><span data-stu-id="71a25-158">Ready to get started?</span></span>

<span data-ttu-id="71a25-159">开始[为您的组织配置特权访问管理](privileged-access-management-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="71a25-159">Start [configuring your organization for privileged access management](privileged-access-management-configuration.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="71a25-160">了解更多信息</span><span class="sxs-lookup"><span data-stu-id="71a25-160">Learn more</span></span>

[<span data-ttu-id="71a25-161">交互式指南: 使用特权访问管理监视和控制管理员任务</span><span class="sxs-lookup"><span data-stu-id="71a25-161">Interactive guide: Monitor and control administrator tasks with privileged access management</span></span>](https://content.cloudguides.com/en-us/guides/Privileged%20Access%20Management)
---
title: 合规性分数方法
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性管理器是 Microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使你能够跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。
ms.openlocfilehash: 55f90996997a60fd95347941bdcad7707c890166
ms.sourcegitcommit: f0d23e57b00f07cef5b1b2d366eaeeeacda37e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35786637"
---
# <a name="compliance-score-methodology-preview"></a><span data-ttu-id="43cdc-104">合规性分数方法 (预览)</span><span class="sxs-lookup"><span data-stu-id="43cdc-104">Compliance Score Methodology (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="43cdc-p102">合规性分数并不是组织遵守任何特定标准或法规情况的绝对度量。它表示执行控制措施的程度，这些控制措施可降低个人数据和个人隐私面临的风险。任何服务都无法保证遵守标准或法规，不得以任何方式将合规性分数解读为保证。</span><span class="sxs-lookup"><span data-stu-id="43cdc-p102">The Compliance Score does not express an absolute measure of organizational compliance with any particular standard or regulation. It expresses the extent to which you have adopted controls which can reduce the risks to personal data and individual privacy. No service can guarantee that you are compliant with a standard or regulation, and the Compliance Score should not be interpreted as a guarantee in any way.</span></span>

<span data-ttu-id="43cdc-108">合规性管理器仪表板在每个评估图块中显示评估的总合规性分数。</span><span class="sxs-lookup"><span data-stu-id="43cdc-108">The Compliance Manager dashboard displays a total compliance score for Assessments in each Assessment tile.</span></span> <span data-ttu-id="43cdc-109">这是评估的总体合规性分数, 并且是评估中每个已实施和已测试的控件的已接收点的累积。</span><span class="sxs-lookup"><span data-stu-id="43cdc-109">This is the overall Compliance Score for the Assessment and is the accumulation of points received for each implemented and tested control in the Assessment.</span></span> <span data-ttu-id="43cdc-110">对于新的评估, 合规性分数具有由独立第三方测试的包含的 Microsoft 托管控件的初始值。</span><span class="sxs-lookup"><span data-stu-id="43cdc-110">For a new Assessment, the Compliance Score has an initial value for the included Microsoft-managed controls tested by independent third parties.</span></span> <span data-ttu-id="43cdc-111">合规性分数可帮助您确定重点关注的评估和控制措施, 以改进您的总体合规性状况。</span><span class="sxs-lookup"><span data-stu-id="43cdc-111">Compliance Score can help prioritize which Assessments and controls to focus on to improve your overall compliance posture.</span></span>

<span data-ttu-id="43cdc-112">为该控件显示的符合性分数值将*全部*应用于整个合规性分数, 具体取决于通过/失败。</span><span class="sxs-lookup"><span data-stu-id="43cdc-112">The displayed Compliance Score values for the control are applied *in their entirety* to the total Compliance Score on a pass/fail basis.</span></span> <span data-ttu-id="43cdc-113">该控件已实现并通过后续评估测试, 否则不会执行。</span><span class="sxs-lookup"><span data-stu-id="43cdc-113">Either the control is implemented and passes the subsequent assessment test or it does not.</span></span> <span data-ttu-id="43cdc-114">分部实现没有任何部分积分。</span><span class="sxs-lookup"><span data-stu-id="43cdc-114">There is no partial credit for a partial implementation.</span></span> <span data-ttu-id="43cdc-115">当控件具有以下条件时, 向合规性分数添加分配的点:</span><span class="sxs-lookup"><span data-stu-id="43cdc-115">Assigned points are added to the Compliance Score when the Control has:</span></span>

- <span data-ttu-id="43cdc-116">**实现状态**等于已**实现**或**替代实施**, 以及</span><span class="sxs-lookup"><span data-stu-id="43cdc-116">**Implementation Status** equals **Implemented** or **Alternative Implementation** and,</span></span>
- <span data-ttu-id="43cdc-117">**测试结果**等于已**通过**。</span><span class="sxs-lookup"><span data-stu-id="43cdc-117">**Test Result** equals **Passed**.</span></span>

## <a name="compliance-score"></a><span data-ttu-id="43cdc-118">合规性分数</span><span class="sxs-lookup"><span data-stu-id="43cdc-118">Compliance score</span></span>
  
<span data-ttu-id="43cdc-119">在合规性管理器中, 比较基准分数从控件级别移动到交办事项级别。</span><span class="sxs-lookup"><span data-stu-id="43cdc-119">In Compliance Manager, baseline scores move from the Control level to the Action Item level.</span></span> <span data-ttu-id="43cdc-120">分数基于措施项的用途 (侦探、预防或纠正) 和强制实施 (随意或强制)。</span><span class="sxs-lookup"><span data-stu-id="43cdc-120">Scores are based on the purpose (Detective, Preventative, or Corrective) and enforcement (Discretionary or Mandatory) of the Action Item.</span></span>

<span data-ttu-id="43cdc-121">操作项映射到控件, 当控件映射到多个操作项时, 操作项分数总和是控制得分。</span><span class="sxs-lookup"><span data-stu-id="43cdc-121">Action Items are mapped to Controls, and when a Control is mapped to multiple Action Items, the sum of the Action Item Scores is the Control Score.</span></span> <span data-ttu-id="43cdc-122">给定评估中所有控件的控制得分总和是评估分数。</span><span class="sxs-lookup"><span data-stu-id="43cdc-122">The sum of the Control Score for all Controls in a given Assessment is the Assessment Score.</span></span> <span data-ttu-id="43cdc-123">组中所有评估的平均分数是该组的合规性分数。</span><span class="sxs-lookup"><span data-stu-id="43cdc-123">The average score of all Assessments in a Group is the Compliance Score for that group.</span></span>
  
### <a name="mandatory-or-discretionary-controls"></a><span data-ttu-id="43cdc-124">强制或任意控件</span><span class="sxs-lookup"><span data-stu-id="43cdc-124">Mandatory or discretionary Controls</span></span>
  
 <span data-ttu-id="43cdc-125">**强制控制**措施是不能有意地或无意中回避的操作。</span><span class="sxs-lookup"><span data-stu-id="43cdc-125">**Mandatory Controls** are actions that cannot be bypassed either intentionally or accidentally.</span></span> <span data-ttu-id="43cdc-126">一个常见的强制控制控件是一个集中管理的密码策略, 它设置密码长度、复杂性和到期的要求。</span><span class="sxs-lookup"><span data-stu-id="43cdc-126">An example of a common mandatory control is a centrally managed password policy that sets requirements for password length, complexity, and expiration.</span></span> <span data-ttu-id="43cdc-127">用户必须遵守这些要求才能访问系统。</span><span class="sxs-lookup"><span data-stu-id="43cdc-127">Users must comply with these requirements to access the system.</span></span>
  
 <span data-ttu-id="43cdc-128">**任意控件**依赖于用户了解策略并相应地执行操作。</span><span class="sxs-lookup"><span data-stu-id="43cdc-128">**Discretionary Controls** rely upon users to understand policy and act accordingly.</span></span> <span data-ttu-id="43cdc-129">例如, 要求用户在其离开时锁定其计算机的策略是自由控制, 因为它依赖于用户。</span><span class="sxs-lookup"><span data-stu-id="43cdc-129">For example, a policy requiring users to lock their computer when they leave it is a discretionary control because it relies on the user.</span></span>
  
### <a name="preventative-detective-or-corrective-controls"></a><span data-ttu-id="43cdc-130">预防性、侦探或纠正控制措施</span><span class="sxs-lookup"><span data-stu-id="43cdc-130">Preventative, detective, or corrective Controls</span></span>
  
 <span data-ttu-id="43cdc-131">**预防控制**措施是阻止特定风险的操作。</span><span class="sxs-lookup"><span data-stu-id="43cdc-131">**Preventative Controls** are actions that prevent specific risks.</span></span> <span data-ttu-id="43cdc-132">例如, 使用加密保护静态信息是抵御攻击、泄露的预防控制。</span><span class="sxs-lookup"><span data-stu-id="43cdc-132">For example, protecting information at rest using encryption is a preventative control against attacks, breaches.</span></span> <span data-ttu-id="43cdc-133">分离职责是一种预防性控制, 用于管理利益冲突并防止欺诈行为。</span><span class="sxs-lookup"><span data-stu-id="43cdc-133">Separation of duties is a preventative control to manage conflict of interest and to guard against fraud.</span></span>
  
 <span data-ttu-id="43cdc-134">**侦探控件**是主动监视系统以确定不稳定条件或行为的操作, 这些条件或行为可用于检测入侵情况或确定是否发生了破坏。</span><span class="sxs-lookup"><span data-stu-id="43cdc-134">**Detective Controls** are actions that actively monitor systems to identify irregular conditions or behaviors that represent risk or that can be used to detect intrusions or determine if a breach has occurred.</span></span> <span data-ttu-id="43cdc-135">系统访问审核和特权管理操作审核是侦探监视控件的类型。</span><span class="sxs-lookup"><span data-stu-id="43cdc-135">System access auditing and privileged administrative actions auditing are types of detective monitoring controls.</span></span> <span data-ttu-id="43cdc-136">法规遵从性审核是一种用于查找进程问题的侦探控件。</span><span class="sxs-lookup"><span data-stu-id="43cdc-136">Regulatory compliance audits are a type of detective control used to find process issues.</span></span>
  
<span data-ttu-id="43cdc-137">**更正控件**是尝试将安全事件的负面影响降至最低的控件, 采取纠正措施以降低即时效果, 并在可能的情况下反转损坏。</span><span class="sxs-lookup"><span data-stu-id="43cdc-137">**Corrective Controls** are Controls that try to keep the adverse effects of a security incident to a minimum, take corrective action to reduce the immediate effect, and reverse the damage, if possible.</span></span> <span data-ttu-id="43cdc-138">"隐私事件响应" 是一种纠正控制, 用于将损坏和还原系统限制为受到破坏后的操作状态。</span><span class="sxs-lookup"><span data-stu-id="43cdc-138">Privacy incident response is a corrective control to limit damage and restore systems to an operational state after a breach.</span></span>
  
<span data-ttu-id="43cdc-139">每个控件都在合规性管理器中分配了基于其表示的风险的值:</span><span class="sxs-lookup"><span data-stu-id="43cdc-139">Each Control has an assigned value in Compliance Manager based on the risk that it represents:</span></span>

|<span data-ttu-id="43cdc-140">**Type**</span><span class="sxs-lookup"><span data-stu-id="43cdc-140">**Type**</span></span>|<span data-ttu-id="43cdc-141">**分配分数**</span><span class="sxs-lookup"><span data-stu-id="43cdc-141">**Assigned Score**</span></span>|
|:-----|:-----|
| <span data-ttu-id="43cdc-142">预防性强制</span><span class="sxs-lookup"><span data-stu-id="43cdc-142">Preventative Mandatory</span></span> | <span data-ttu-id="43cdc-143">27</span><span class="sxs-lookup"><span data-stu-id="43cdc-143">27</span></span> |
| <span data-ttu-id="43cdc-144">预防自由</span><span class="sxs-lookup"><span data-stu-id="43cdc-144">Preventative Discretionary</span></span> | <span data-ttu-id="43cdc-145">第</span><span class="sxs-lookup"><span data-stu-id="43cdc-145">9</span></span> |
| <span data-ttu-id="43cdc-146">侦探必备</span><span class="sxs-lookup"><span data-stu-id="43cdc-146">Detective Mandatory</span></span> | <span data-ttu-id="43cdc-147">第三章</span><span class="sxs-lookup"><span data-stu-id="43cdc-147">3</span></span> |
| <span data-ttu-id="43cdc-148">侦探自由</span><span class="sxs-lookup"><span data-stu-id="43cdc-148">Detective Discretionary</span></span> | <span data-ttu-id="43cdc-149">1</span><span class="sxs-lookup"><span data-stu-id="43cdc-149">1</span></span> |
| <span data-ttu-id="43cdc-150">强制纠正</span><span class="sxs-lookup"><span data-stu-id="43cdc-150">Corrective Mandatory</span></span> | <span data-ttu-id="43cdc-151">第三章</span><span class="sxs-lookup"><span data-stu-id="43cdc-151">3</span></span> |
| <span data-ttu-id="43cdc-152">随机纠正</span><span class="sxs-lookup"><span data-stu-id="43cdc-152">Corrective Discretionary</span></span> | <span data-ttu-id="43cdc-153">1</span><span class="sxs-lookup"><span data-stu-id="43cdc-153">1</span></span> |
  
## <a name="action-item-workflow"></a><span data-ttu-id="43cdc-154">操作项工作流</span><span class="sxs-lookup"><span data-stu-id="43cdc-154">Action Item workflow</span></span>

<span data-ttu-id="43cdc-155">下面是典型措施项的基本工作流:</span><span class="sxs-lookup"><span data-stu-id="43cdc-155">Here's the basic workflow for a typical Action Item:</span></span>
  
1. <span data-ttu-id="43cdc-156">组织的合规性、风险、隐私和/或数据保护官员将任务分配给组织中的某个人来实现控件。</span><span class="sxs-lookup"><span data-stu-id="43cdc-156">The Compliance, Risk, Privacy, and/or Data Protection Officer of an organization assigns a task to someone in the organization to implement a control.</span></span> <span data-ttu-id="43cdc-157">此人可能是:</span><span class="sxs-lookup"><span data-stu-id="43cdc-157">That person could be:</span></span>

    - <span data-ttu-id="43cdc-158">业务策略所有者。</span><span class="sxs-lookup"><span data-stu-id="43cdc-158">A business policy owner.</span></span>
    - <span data-ttu-id="43cdc-159">IT 实施人员。</span><span class="sxs-lookup"><span data-stu-id="43cdc-159">An IT implementer.</span></span>
    - <span data-ttu-id="43cdc-160">组织中的另一个人负责执行该任务。</span><span class="sxs-lookup"><span data-stu-id="43cdc-160">Another individual in the organization with responsibility to perform the task.</span></span>

2. <span data-ttu-id="43cdc-161">该个人执行实现控件所需的任务, 将实现的证据上载到合规性管理器中, 并将控制措施标记为已实现的措施项。</span><span class="sxs-lookup"><span data-stu-id="43cdc-161">That individual performs the tasks necessary to implement the control, uploads evidence of implementation into Compliance Manager, and marks the Control tied to the Action Item as implemented.</span></span> <span data-ttu-id="43cdc-162">完成这些任务后, 他们会将措施项分配给评估员进行验证。</span><span class="sxs-lookup"><span data-stu-id="43cdc-162">Once these tasks are completed, they assign the Action Item to an Assessor for validation.</span></span>

    <span data-ttu-id="43cdc-163">评估员可以是:</span><span class="sxs-lookup"><span data-stu-id="43cdc-163">Assessors can be:</span></span>

    - <span data-ttu-id="43cdc-164">在组织内执行控件验证的内部评估员。</span><span class="sxs-lookup"><span data-stu-id="43cdc-164">Internal assessors that perform validation of controls within an organization.</span></span>
    - <span data-ttu-id="43cdc-165">外部评估员, 用于检查、验证和证明合规性, 如审核 Microsoft 云服务的第三方独立组织。</span><span class="sxs-lookup"><span data-stu-id="43cdc-165">External assessors that examine, verify, and certify compliance, such as the third-party independent organizations that audit Microsoft's cloud services.</span></span>

3. <span data-ttu-id="43cdc-166">评估员验证控件并检查证据, 并根据评估和评估的结果对该控件进行标记。</span><span class="sxs-lookup"><span data-stu-id="43cdc-166">The Assessor validates the control and examines the evidence and marks the control as assessed and the results of the assessment.</span></span>

<span data-ttu-id="43cdc-167">评估了与评估相关的所有控件后, 便完成了评估。</span><span class="sxs-lookup"><span data-stu-id="43cdc-167">Once all the Controls associated with an Assessment are assessed, the Assessment is complete.</span></span>
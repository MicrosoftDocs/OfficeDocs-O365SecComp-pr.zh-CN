---
title: 编辑或删除信息障碍策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/24/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 了解如何编辑或删除信息障碍策略。
ms.openlocfilehash: e6bed4df2329d426f86bd4cde07bdc7d1a2792cd
ms.sourcegitcommit: 7c48ce016fa9f45a3813467f7c5a2fd72f9b8f49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35215645"
---
# <a name="edit-or-remove-information-barrier-policies-preview"></a><span data-ttu-id="2f0c5-103">编辑或删除信息障碍策略 (预览)</span><span class="sxs-lookup"><span data-stu-id="2f0c5-103">Edit or remove information barrier policies (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="2f0c5-104">概述</span><span class="sxs-lookup"><span data-stu-id="2f0c5-104">Overview</span></span>

<span data-ttu-id="2f0c5-105">[定义信息障碍策略](information-barriers-policies.md)后, 您可能需要对这些策略或用户区段进行更改, 作为[故障排除](information-barriers-troubleshooting.md)或定期维护的一部分。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-105">After you have [defined information barrier policies](information-barriers-policies.md), you might need to make changes to those policies or to your user segments, as part of [troubleshooting](information-barriers-troubleshooting.md) or as regular maintenance.</span></span> <span data-ttu-id="2f0c5-106">将本文用作指南。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-106">Use this article as a guide.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f0c5-107">若要执行本文中所述的任务, 必须为您分配适当的角色, 如以下某项:</span><span class="sxs-lookup"><span data-stu-id="2f0c5-107">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="2f0c5-108">-Microsoft 365 企业全局管理员</span><span class="sxs-lookup"><span data-stu-id="2f0c5-108">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="2f0c5-109">-Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="2f0c5-109">- Office 365 Global Administrator</span></span><br/><span data-ttu-id="2f0c5-110">-合规性管理员</span><span class="sxs-lookup"><span data-stu-id="2f0c5-110">- Compliance Administrator</span></span><br/><span data-ttu-id="2f0c5-111">-IB 合规性管理 (这是一个新角色!)</span><span class="sxs-lookup"><span data-stu-id="2f0c5-111">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="2f0c5-112">若要了解有关信息障碍的先决条件方面的详细信息, 请参阅[先决条件 (适用于信息屏障策略)](information-barriers-policies.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-112">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="2f0c5-113">请确保[连接到 Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-113">Make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="edit-user-account-attributes"></a><span data-ttu-id="2f0c5-114">编辑用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="2f0c5-114">Edit user account attributes</span></span>

<span data-ttu-id="2f0c5-115">使用此过程可编辑用于分段用户的属性。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-115">Use this procedure to edit attributes that are used for segmenting users.</span></span> 

<span data-ttu-id="2f0c5-116">例如, 如果您使用的是部门属性, 并且一个或多个用户帐户当前没有为部门列出任何值, 则必须编辑这些用户帐户以包含部门信息。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-116">For example, if you are using a Department attribute, and one or more user accounts do not currently have any values listed for Department, you must edit those user accounts to include Department information.</span></span> 

<span data-ttu-id="2f0c5-117">用户帐户属性用于定义段, 以便可以分配信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-117">User account attributes are used for defining segments so that information barrier policies can be assigned.</span></span>

1. <span data-ttu-id="2f0c5-118">若要查看特定用户帐户的详细信息 (如属性值和分配的段), 请使用带有 Identity 参数的**InformationBarrierRecipientStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-118">To view details for a specific user account, such as attribute values and assigned segment(s), use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> 

   <span data-ttu-id="2f0c5-119">语法`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-119">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> 
    
   <span data-ttu-id="2f0c5-120">您可以使用任何唯一标识每个用户的值, 如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-120">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> 
    
   <span data-ttu-id="2f0c5-121">示例：`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-121">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> 
    
   <span data-ttu-id="2f0c5-122">在此示例中, 我们引用 Office 365 中的两个用户帐户: *meganb* for *Megan*和*alexw* for *Alex*。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-122">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> 
    
   <span data-ttu-id="2f0c5-123">(也可以将此 cmdlet 用于单个用户: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span><span class="sxs-lookup"><span data-stu-id="2f0c5-123">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> 
    
2. <span data-ttu-id="2f0c5-124">为您的用户帐户配置文件确定要编辑的属性。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-124">Determine which attribute you want to edit for your user account profile(s).</span></span> <span data-ttu-id="2f0c5-125">有关详细信息, 请参阅[信息屏障策略 (预览版) 的属性](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-125">Refer to [Attributes for information barrier policies (Preview)](information-barriers-attributes.md) for more details.</span></span> 

3. <span data-ttu-id="2f0c5-126">编辑一个或多个用户帐户, 以包含您在上一步中选择的属性的值。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-126">Edit one or more user accounts to include values for the attribute you selected in the previous step.</span></span> <span data-ttu-id="2f0c5-127">为此, 请使用以下过程之一:</span><span class="sxs-lookup"><span data-stu-id="2f0c5-127">To do this, use one of the following procedures:</span></span>

    - <span data-ttu-id="2f0c5-128">若要编辑单个帐户, 请参阅[使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-128">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

    - <span data-ttu-id="2f0c5-129">若要编辑多个帐户 (或使用 PowerShell 编辑单个帐户), 请参阅[Configure user account properties With Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-129">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

## <a name="edit-a-segment"></a><span data-ttu-id="2f0c5-130">编辑段</span><span class="sxs-lookup"><span data-stu-id="2f0c5-130">Edit a segment</span></span>

<span data-ttu-id="2f0c5-131">使用此过程可编辑用户区段的定义。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-131">Use this procedure edit the definition of a user segment.</span></span> <span data-ttu-id="2f0c5-132">例如, 您可以更改段的名称, 或使用用于确定字段中所包含的用户的筛选器。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-132">For example, you might change the name of a segment, or the filter that is used to determine who's included in the segment.</span></span>

1. <span data-ttu-id="2f0c5-133">若要查看所有现有段, 请使用**OrganizationSegment** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-133">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="2f0c5-134">语法`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-134">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="2f0c5-135">你将看到每个段的列表和详细信息, 如段类型、其 UserGroupFilter 值、创建日期或上次修改时间、GUID 等。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-135">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="2f0c5-136">打印或保存段列表以便日后参考。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-136">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="2f0c5-137">例如, 如果您想要编辑某一段, 则需要知道它的名称或标识值 (这与 Identity 参数一起使用)。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-137">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="2f0c5-138">若要编辑分段, 请使用**OrganizationSegment** Cmdlet 和**Identity**参数以及相关详细信息。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-138">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    <span data-ttu-id="2f0c5-139">语法`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-139">Syntax: `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="2f0c5-140">示例：`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-140">Example: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span></span>

    <span data-ttu-id="2f0c5-141">在此示例中, 对于具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的段, 我们将部门名称更新为 "HRDept"。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-141">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>

<span data-ttu-id="2f0c5-142">为组织编辑完段后, 可以[定义](information-barriers-policies.md#part-2-define-information-barrier-policies)或[编辑](#edit-a-policy)信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-142">When you have finished editing segments for your organization, you can either [define](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

## <a name="edit-a-policy"></a><span data-ttu-id="2f0c5-143">编辑策略</span><span class="sxs-lookup"><span data-stu-id="2f0c5-143">Edit a policy</span></span>

1. <span data-ttu-id="2f0c5-144">若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-144">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="2f0c5-145">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-145">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="2f0c5-146">在结果列表中, 标识要更改的策略。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-146">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="2f0c5-147">记下策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-147">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="2f0c5-148">将**InformationBarrierPolicy** Cmdlet 与**Identity**参数一起使用, 并指定要进行的更改。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-148">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="2f0c5-149">示例: 假设定义了一个策略来阻止与*销售*和*市场营销*部门通信的*研究*分段。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-149">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="2f0c5-150">该策略是使用以下 cmdlet 定义的:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-150">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>
    
    <span data-ttu-id="2f0c5-151">假设我们要对其进行更改, 以便*研究*部门中的人员只能与*HR*部门中的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-151">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="2f0c5-152">若要进行此更改, 我们使用以下 cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-152">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="2f0c5-153">在此示例中, 我们将 "SegmentsBlocked" 更改为 "SegmentsAllowed", 并指定*HR*段。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-153">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="2f0c5-154">完成策略的编辑后, 请确保应用所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-154">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="2f0c5-155">(请参阅[Apply 信息屏障策略](information-barriers-policies.md#part-3-apply-information-barrier-policies)。)</span><span class="sxs-lookup"><span data-stu-id="2f0c5-155">(See [Apply information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)</span></span>

## <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="2f0c5-156">将策略设置为非活动状态</span><span class="sxs-lookup"><span data-stu-id="2f0c5-156">Set a policy to inactive status</span></span>

1. <span data-ttu-id="2f0c5-157">若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-157">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="2f0c5-158">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-158">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="2f0c5-159">在结果列表中, 标识要更改 (或删除) 的策略。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-159">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="2f0c5-160">记下策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-160">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="2f0c5-161">若要将策略的状态设置为 "非活动", 请使用带有 Identity 参数的**InformationBarrierPolicy** cmdlet, 将 State 参数设置为 "非活动"。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-161">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    <span data-ttu-id="2f0c5-162">语法`Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-162">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span></span>

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    <span data-ttu-id="2f0c5-163">在此示例中, 我们将具有 GUID *43c37853-ea10-4b90-a23d-ab8c9377247*的信息屏障策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-163">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>

3. <span data-ttu-id="2f0c5-164">若要应用所做的更改, 请使用**InformationBarrierPoliciesApplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-164">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="2f0c5-165">语法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-165">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="2f0c5-166">为您的组织应用更改的用户。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-166">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="2f0c5-167">如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-167">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="2f0c5-168">(一般原则是, 处理5000用户帐户需要大约一小时的时间。)</span><span class="sxs-lookup"><span data-stu-id="2f0c5-168">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="2f0c5-169">在这种情况下, 一个或多个信息障碍策略将设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-169">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="2f0c5-170">在这里, 您可以执行以下任一操作:</span><span class="sxs-lookup"><span data-stu-id="2f0c5-170">From here, you can do any of the following:</span></span>
- <span data-ttu-id="2f0c5-171">将其保留为 (策略设置为非活动状态对用户没有影响)</span><span class="sxs-lookup"><span data-stu-id="2f0c5-171">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="2f0c5-172">编辑策略</span><span class="sxs-lookup"><span data-stu-id="2f0c5-172">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="2f0c5-173">删除策略</span><span class="sxs-lookup"><span data-stu-id="2f0c5-173">Remove a policy</span></span>](#remove-a-policy)

## <a name="remove-a-policy"></a><span data-ttu-id="2f0c5-174">删除策略</span><span class="sxs-lookup"><span data-stu-id="2f0c5-174">Remove a policy</span></span>

1. <span data-ttu-id="2f0c5-175">若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-175">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="2f0c5-176">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-176">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="2f0c5-177">在结果列表中, 标识要删除的策略。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-177">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="2f0c5-178">记下策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-178">Note the policy's GUID and name.</span></span> <span data-ttu-id="2f0c5-179">请确保将策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-179">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="2f0c5-180">将**InformationBarrierPolicy** Cmdlet 与 Identity 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-180">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="2f0c5-181">语法`Remove-InformationBarrierPolicy -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-181">Syntax: `Remove-InformationBarrierPolicy -Identity GUID`</span></span>

    <span data-ttu-id="2f0c5-182">示例: 假设我们要删除 GUID 为*43c37853-ea10-4b90-a23d-ab8c93772471*的策略。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-182">Example: Suppose we want to remove a policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> <span data-ttu-id="2f0c5-183">为此, 我们使用此 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2f0c5-183">To do this, we use this cmdlet:</span></span>
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    <span data-ttu-id="2f0c5-184">出现提示时, 请确认更改。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-184">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="2f0c5-185">对要删除的每个策略重复步骤1-2。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-185">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="2f0c5-186">删除完策略后, 应用所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-186">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="2f0c5-187">为此, 请使用**InformationBarrierPoliciesApplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-187">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="2f0c5-188">语法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-188">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="2f0c5-189">为您的组织应用更改的用户。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-189">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="2f0c5-190">如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-190">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

## <a name="stop-a-policy-application"></a><span data-ttu-id="2f0c5-191">停止策略应用程序</span><span class="sxs-lookup"><span data-stu-id="2f0c5-191">Stop a policy application</span></span>

<span data-ttu-id="2f0c5-192">如果在您开始应用信息屏障策略后, 您想要停止应用这些策略, 请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-192">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="2f0c5-193">请注意, 此过程将需要大约30-35 分钟才能开始。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-193">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="2f0c5-194">若要查看最新信息屏障策略应用程序的状态, 请使用**InformationBarrierPoliciesApplicationStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-194">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="2f0c5-195">语法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-195">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="2f0c5-196">记下应用程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-196">Note the application's GUID.</span></span>

2. <span data-ttu-id="2f0c5-197">将**InformationBarrierPoliciesApplication** Cmdlet 与 Identity 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-197">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="2f0c5-198">语法`Stop-InformationBarrierPoliciesApplication -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-198">Syntax:  `Stop-InformationBarrierPoliciesApplication -Identity GUID`</span></span>

    <span data-ttu-id="2f0c5-199">示例：`Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span><span class="sxs-lookup"><span data-stu-id="2f0c5-199">Example: `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span></span>

    <span data-ttu-id="2f0c5-200">在此示例中, 我们将停止应用信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="2f0c5-200">In this example, we are stopping information barrier policies from being applied.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2f0c5-201">相关文章</span><span class="sxs-lookup"><span data-stu-id="2f0c5-201">Related articles</span></span>

[<span data-ttu-id="2f0c5-202">获取信息障碍概述</span><span class="sxs-lookup"><span data-stu-id="2f0c5-202">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="2f0c5-203">定义信息障碍策略 (预览)</span><span class="sxs-lookup"><span data-stu-id="2f0c5-203">Define policies for information barriers (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="2f0c5-204">了解有关 Microsoft 团队中的信息障碍的详细信息</span><span class="sxs-lookup"><span data-stu-id="2f0c5-204">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="2f0c5-205">信息屏障策略的属性 (预览)</span><span class="sxs-lookup"><span data-stu-id="2f0c5-205">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="2f0c5-206">解决信息障碍 (预览)</span><span class="sxs-lookup"><span data-stu-id="2f0c5-206">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)

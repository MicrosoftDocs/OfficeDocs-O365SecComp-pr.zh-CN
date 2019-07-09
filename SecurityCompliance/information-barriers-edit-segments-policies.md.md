---
title: 编辑信息屏障策略
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
description: 了解如何编辑或删除信息障碍策略。
ms.openlocfilehash: c55ffac0984fe83fec1ef7b995d1589ea770bfef
ms.sourcegitcommit: a6f046f1529b0515f4f0e918a19ec83f4138b871
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2019
ms.locfileid: "35587071"
---
# <a name="edit-or-remove-information-barrier-policies"></a><span data-ttu-id="b88b1-103">编辑 (或删除) 信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="b88b1-103">Edit (or remove) information barrier policies</span></span>

<span data-ttu-id="b88b1-104">[定义信息障碍策略](information-barriers-policies.md)后, 您可能需要对这些策略或用户区段进行更改, 作为[故障排除](information-barriers-troubleshooting.md)或定期维护的一部分。</span><span class="sxs-lookup"><span data-stu-id="b88b1-104">After you have [defined information barrier policies](information-barriers-policies.md), you might need to make changes to those policies or to your user segments, as part of [troubleshooting](information-barriers-troubleshooting.md) or as regular maintenance.</span></span> <span data-ttu-id="b88b1-105">将本文用作指南。</span><span class="sxs-lookup"><span data-stu-id="b88b1-105">Use this article as a guide.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="b88b1-106">要执行什么操作？</span><span class="sxs-lookup"><span data-stu-id="b88b1-106">What do you want to do?</span></span>

|<span data-ttu-id="b88b1-107">操作</span><span class="sxs-lookup"><span data-stu-id="b88b1-107">Action</span></span>  |<span data-ttu-id="b88b1-108">说明</span><span class="sxs-lookup"><span data-stu-id="b88b1-108">Description</span></span> |
|---------|---------|
|[<span data-ttu-id="b88b1-109">编辑用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="b88b1-109">Edit user account attributes</span></span>](#edit-user-account-attributes)     |<span data-ttu-id="b88b1-110">填写可用于定义段的 Azure Active Directory 中的属性。</span><span class="sxs-lookup"><span data-stu-id="b88b1-110">Fill in attributes in Azure Active Directory that can be used to define segments.</span></span><br/><span data-ttu-id="b88b1-111">当用户不包含在应使用的分段中时编辑用户帐户属性, 以更改用户所在的分段, 或使用不同的属性定义分段。</span><span class="sxs-lookup"><span data-stu-id="b88b1-111">Edit user account attributes when users are not included in segments they should be, to change which segments users are in, or to define segments using different attributes.</span></span>         |
|[<span data-ttu-id="b88b1-112">编辑段</span><span class="sxs-lookup"><span data-stu-id="b88b1-112">Edit a segment</span></span>](#edit-a-segment)     |<span data-ttu-id="b88b1-113">当您想要更改分段定义的方式时编辑线段。</span><span class="sxs-lookup"><span data-stu-id="b88b1-113">Edit segments when you want to change how a segment is defined.</span></span> <br/><span data-ttu-id="b88b1-114">例如, 您可能已使用*部门*最初定义了分段, 现在想要使用另一个属性, 如*MemberOf*。</span><span class="sxs-lookup"><span data-stu-id="b88b1-114">For example, you might have originally defined segments using *Department* and now want to use another attribute, such as *MemberOf*.</span></span>         |
|[<span data-ttu-id="b88b1-115">编辑策略</span><span class="sxs-lookup"><span data-stu-id="b88b1-115">Edit a policy</span></span>](#edit-a-policy)     |<span data-ttu-id="b88b1-116">当您想要更改策略的工作方式时, 请编辑信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="b88b1-116">Edit an information barrier policy when you want to change how a policy works.</span></span><br/><span data-ttu-id="b88b1-117">例如, 您可能会决定只允许在某些网段之间进行通信, 而无需阻止两个网段之间的通信。</span><span class="sxs-lookup"><span data-stu-id="b88b1-117">For example, instead of blocking communications between two segments, you might decide you want to allow communications to occur only between certain segments.</span></span>         |
|[<span data-ttu-id="b88b1-118">将策略设置为非活动状态</span><span class="sxs-lookup"><span data-stu-id="b88b1-118">Set a policy to inactive status</span></span>](#set-a-policy-to-inactive-status)     |<span data-ttu-id="b88b1-119">如果要对策略进行更改, 或不希望策略生效, 请将策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="b88b1-119">Set a policy to inactive status when you want to make changes to a policy, or when you don't want a policy to be in effect.</span></span>         |
|[<span data-ttu-id="b88b1-120">删除策略</span><span class="sxs-lookup"><span data-stu-id="b88b1-120">Remove a policy</span></span>](#remove-a-policy)     |<span data-ttu-id="b88b1-121">当不再需要特定策略时, 请删除信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="b88b1-121">Remove an information barrier policy when you no longer need a particular policy in place.</span></span>         |
|[<span data-ttu-id="b88b1-122">停止策略应用程序</span><span class="sxs-lookup"><span data-stu-id="b88b1-122">Stop a policy application</span></span>](#stop-a-policy-application)     |<span data-ttu-id="b88b1-123">如果要停止应用信息屏障策略的过程, 请执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b88b1-123">Do this when you want to stop the process of applying information barrier policies.</span></span><br/><span data-ttu-id="b88b1-124">请注意, 停止策略应用程序不是即时的, 并且不会撤消已应用于用户的策略。</span><span class="sxs-lookup"><span data-stu-id="b88b1-124">Note that stopping a policy application is not instant, and it does not undo policies that are already applied to users.</span></span>         |
|[<span data-ttu-id="b88b1-125">定义信息障碍策略</span><span class="sxs-lookup"><span data-stu-id="b88b1-125">Define policies for information barriers</span></span>](information-barriers-policies.md)     |<span data-ttu-id="b88b1-126">如果不存在此类策略, 请定义信息屏障策略, 并且必须限制或限制特定用户组之间的通信。</span><span class="sxs-lookup"><span data-stu-id="b88b1-126">Define an information barrier policy when you do not already have such policies in place, and you must restrict or limit communications between specific groups of users.</span></span>         |
|[<span data-ttu-id="b88b1-127">信息障碍故障排除</span><span class="sxs-lookup"><span data-stu-id="b88b1-127">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)     |<span data-ttu-id="b88b1-128">遇到信息障碍遇到意外问题时, 请参阅本文。</span><span class="sxs-lookup"><span data-stu-id="b88b1-128">Refer to this article when you run into unexpected issues with information barriers.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="b88b1-129">若要执行本文中所述的任务, 必须为您分配适当的角色, 如以下某项:</span><span class="sxs-lookup"><span data-stu-id="b88b1-129">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="b88b1-130">-Microsoft 365 企业全局管理员</span><span class="sxs-lookup"><span data-stu-id="b88b1-130">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="b88b1-131">-Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="b88b1-131">- Office 365 Global Administrator</span></span><br/><span data-ttu-id="b88b1-132">-合规性管理员</span><span class="sxs-lookup"><span data-stu-id="b88b1-132">- Compliance Administrator</span></span><br/><span data-ttu-id="b88b1-133">-IB 合规性管理 (这是一个新角色!)</span><span class="sxs-lookup"><span data-stu-id="b88b1-133">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="b88b1-134">若要了解有关信息障碍的先决条件方面的详细信息, 请参阅[先决条件 (适用于信息屏障策略)](information-barriers-policies.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="b88b1-134">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="b88b1-135">请确保[连接到 Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="b88b1-135">Make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="edit-user-account-attributes"></a><span data-ttu-id="b88b1-136">编辑用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="b88b1-136">Edit user account attributes</span></span>

<span data-ttu-id="b88b1-137">使用此过程可编辑用于分段用户的属性。</span><span class="sxs-lookup"><span data-stu-id="b88b1-137">Use this procedure to edit attributes that are used for segmenting users.</span></span> 

<span data-ttu-id="b88b1-138">例如, 如果您使用的是部门属性, 并且一个或多个用户帐户当前没有为部门列出任何值, 则必须编辑这些用户帐户以包含部门信息。</span><span class="sxs-lookup"><span data-stu-id="b88b1-138">For example, if you are using a Department attribute, and one or more user accounts do not currently have any values listed for Department, you must edit those user accounts to include Department information.</span></span> 

<span data-ttu-id="b88b1-139">用户帐户属性用于定义段, 以便可以分配信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="b88b1-139">User account attributes are used for defining segments so that information barrier policies can be assigned.</span></span>

1. <span data-ttu-id="b88b1-140">若要查看特定用户帐户的详细信息 (如属性值和分配的段), 请使用带有 Identity 参数的**InformationBarrierRecipientStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b88b1-140">To view details for a specific user account, such as attribute values and assigned segment(s), use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> 

    |<span data-ttu-id="b88b1-141">语法</span><span class="sxs-lookup"><span data-stu-id="b88b1-141">Syntax</span></span>  |<span data-ttu-id="b88b1-142">示例</span><span class="sxs-lookup"><span data-stu-id="b88b1-142">Example</span></span>  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>   <span data-ttu-id="b88b1-143">您可以使用任何唯一标识每个用户的值, 如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="b88b1-143">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p>   <span data-ttu-id="b88b1-144">(也可以将此 cmdlet 用于单个用户: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span><span class="sxs-lookup"><span data-stu-id="b88b1-144">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span>      |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`  <p>   <span data-ttu-id="b88b1-145">在此示例中, 我们引用 Office 365 中的两个用户帐户: *meganb* for *Megan*和*alexw* for *Alex*。</span><span class="sxs-lookup"><span data-stu-id="b88b1-145">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span>         |

2. <span data-ttu-id="b88b1-146">为您的用户帐户配置文件确定要编辑的属性。</span><span class="sxs-lookup"><span data-stu-id="b88b1-146">Determine which attribute you want to edit for your user account profile(s).</span></span> <span data-ttu-id="b88b1-147">有关详细信息, 请参阅[信息障碍策略的属性](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="b88b1-147">Refer to [Attributes for information barrier policies](information-barriers-attributes.md) for more details.</span></span> 

3. <span data-ttu-id="b88b1-148">编辑一个或多个用户帐户, 以包含您在上一步中选择的属性的值。</span><span class="sxs-lookup"><span data-stu-id="b88b1-148">Edit one or more user accounts to include values for the attribute you selected in the previous step.</span></span> <span data-ttu-id="b88b1-149">为此, 请使用以下过程之一:</span><span class="sxs-lookup"><span data-stu-id="b88b1-149">To do this, use one of the following procedures:</span></span>

    - <span data-ttu-id="b88b1-150">若要编辑单个帐户, 请参阅[使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="b88b1-150">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

    - <span data-ttu-id="b88b1-151">若要编辑多个帐户 (或使用 PowerShell 编辑单个帐户), 请参阅[Configure user account properties With Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b88b1-151">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

## <a name="edit-a-segment"></a><span data-ttu-id="b88b1-152">编辑段</span><span class="sxs-lookup"><span data-stu-id="b88b1-152">Edit a segment</span></span>

<span data-ttu-id="b88b1-153">使用此过程可编辑用户区段的定义。</span><span class="sxs-lookup"><span data-stu-id="b88b1-153">Use this procedure edit the definition of a user segment.</span></span> <span data-ttu-id="b88b1-154">例如, 您可以更改段的名称, 或使用用于确定字段中所包含的用户的筛选器。</span><span class="sxs-lookup"><span data-stu-id="b88b1-154">For example, you might change the name of a segment, or the filter that is used to determine who's included in the segment.</span></span>

1. <span data-ttu-id="b88b1-155">若要查看所有现有段, 请使用**OrganizationSegment** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b88b1-155">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="b88b1-156">语法`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="b88b1-156">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="b88b1-157">你将看到每个段的列表和详细信息, 如段类型、其 UserGroupFilter 值、创建日期或上次修改时间、GUID 等。</span><span class="sxs-lookup"><span data-stu-id="b88b1-157">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="b88b1-158">打印或保存段列表以便日后参考。</span><span class="sxs-lookup"><span data-stu-id="b88b1-158">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="b88b1-159">例如, 如果您想要编辑某一段, 则需要知道它的名称或标识值 (这与 Identity 参数一起使用)。</span><span class="sxs-lookup"><span data-stu-id="b88b1-159">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="b88b1-160">若要编辑分段, 请使用**OrganizationSegment** Cmdlet 和**Identity**参数以及相关详细信息。</span><span class="sxs-lookup"><span data-stu-id="b88b1-160">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    |<span data-ttu-id="b88b1-161">语法</span><span class="sxs-lookup"><span data-stu-id="b88b1-161">Syntax</span></span>  |<span data-ttu-id="b88b1-162">示例</span><span class="sxs-lookup"><span data-stu-id="b88b1-162">Example</span></span>  |
    |---------|---------|
    |`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`     |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p><span data-ttu-id="b88b1-163">在此示例中, 对于具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的段, 我们将部门名称更新为 "HRDept"。</span><span class="sxs-lookup"><span data-stu-id="b88b1-163">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>         |

<span data-ttu-id="b88b1-164">为组织编辑完段后, 可以[定义](information-barriers-policies.md#part-2-define-information-barrier-policies)或[编辑](#edit-a-policy)信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="b88b1-164">When you have finished editing segments for your organization, you can either [define](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

## <a name="edit-a-policy"></a><span data-ttu-id="b88b1-165">编辑策略</span><span class="sxs-lookup"><span data-stu-id="b88b1-165">Edit a policy</span></span>

1. <span data-ttu-id="b88b1-166">若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b88b1-166">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="b88b1-167">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="b88b1-167">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="b88b1-168">在结果列表中, 标识要更改的策略。</span><span class="sxs-lookup"><span data-stu-id="b88b1-168">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="b88b1-169">记下策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="b88b1-169">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="b88b1-170">将**InformationBarrierPolicy** Cmdlet 与**Identity**参数一起使用, 并指定要进行的更改。</span><span class="sxs-lookup"><span data-stu-id="b88b1-170">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="b88b1-171">示例: 假设定义了一个策略来阻止与*销售*和*市场营销*部门通信的*研究*分段。</span><span class="sxs-lookup"><span data-stu-id="b88b1-171">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="b88b1-172">该策略是使用以下 cmdlet 定义的:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="b88b1-172">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>
    
    <span data-ttu-id="b88b1-173">假设我们要对其进行更改, 以便*研究*部门中的人员只能与*HR*部门中的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="b88b1-173">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="b88b1-174">若要进行此更改, 我们使用以下 cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="b88b1-174">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="b88b1-175">在此示例中, 我们将 "SegmentsBlocked" 更改为 "SegmentsAllowed", 并指定*HR*段。</span><span class="sxs-lookup"><span data-stu-id="b88b1-175">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="b88b1-176">完成策略的编辑后, 请确保应用所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b88b1-176">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="b88b1-177">(请参阅[Apply 信息屏障策略](information-barriers-policies.md#part-3-apply-information-barrier-policies)。)</span><span class="sxs-lookup"><span data-stu-id="b88b1-177">(See [Apply information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)</span></span>

## <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="b88b1-178">将策略设置为非活动状态</span><span class="sxs-lookup"><span data-stu-id="b88b1-178">Set a policy to inactive status</span></span>

1. <span data-ttu-id="b88b1-179">若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b88b1-179">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="b88b1-180">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="b88b1-180">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="b88b1-181">在结果列表中, 标识要更改 (或删除) 的策略。</span><span class="sxs-lookup"><span data-stu-id="b88b1-181">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="b88b1-182">记下策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="b88b1-182">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="b88b1-183">若要将策略的状态设置为 "非活动", 请使用带有 Identity 参数的**InformationBarrierPolicy** cmdlet, 将 State 参数设置为 "非活动"。</span><span class="sxs-lookup"><span data-stu-id="b88b1-183">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    |<span data-ttu-id="b88b1-184">语法</span><span class="sxs-lookup"><span data-stu-id="b88b1-184">Syntax</span></span>  |<span data-ttu-id="b88b1-185">示例</span><span class="sxs-lookup"><span data-stu-id="b88b1-185">Example</span></span>  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Inactive`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p><span data-ttu-id="b88b1-186">在此示例中, 我们将具有 GUID *43c37853-ea10-4b90-a23d-ab8c9377247*的信息屏障策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="b88b1-186">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>         |

3. <span data-ttu-id="b88b1-187">若要应用所做的更改, 请使用**InformationBarrierPoliciesApplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b88b1-187">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="b88b1-188">语法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="b88b1-188">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="b88b1-189">为您的组织应用更改的用户。</span><span class="sxs-lookup"><span data-stu-id="b88b1-189">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="b88b1-190">如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="b88b1-190">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="b88b1-191">(一般原则是, 处理5000用户帐户需要大约一小时的时间。)</span><span class="sxs-lookup"><span data-stu-id="b88b1-191">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="b88b1-192">在这种情况下, 一个或多个信息障碍策略将设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="b88b1-192">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="b88b1-193">在这里, 您可以执行以下任一操作:</span><span class="sxs-lookup"><span data-stu-id="b88b1-193">From here, you can do any of the following:</span></span>
- <span data-ttu-id="b88b1-194">将其保留为 (策略设置为非活动状态对用户没有影响)</span><span class="sxs-lookup"><span data-stu-id="b88b1-194">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="b88b1-195">编辑策略</span><span class="sxs-lookup"><span data-stu-id="b88b1-195">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="b88b1-196">删除策略</span><span class="sxs-lookup"><span data-stu-id="b88b1-196">Remove a policy</span></span>](#remove-a-policy)

## <a name="remove-a-policy"></a><span data-ttu-id="b88b1-197">删除策略</span><span class="sxs-lookup"><span data-stu-id="b88b1-197">Remove a policy</span></span>

1. <span data-ttu-id="b88b1-198">若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b88b1-198">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="b88b1-199">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="b88b1-199">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="b88b1-200">在结果列表中, 标识要删除的策略。</span><span class="sxs-lookup"><span data-stu-id="b88b1-200">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="b88b1-201">记下策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="b88b1-201">Note the policy's GUID and name.</span></span> <span data-ttu-id="b88b1-202">请确保将策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="b88b1-202">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="b88b1-203">将**InformationBarrierPolicy** Cmdlet 与 Identity 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="b88b1-203">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="b88b1-204">语法</span><span class="sxs-lookup"><span data-stu-id="b88b1-204">Syntax</span></span>  |<span data-ttu-id="b88b1-205">示例</span><span class="sxs-lookup"><span data-stu-id="b88b1-205">Example</span></span>  |
    |---------|---------|
    |`Remove-InformationBarrierPolicy -Identity GUID`     |`Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p><span data-ttu-id="b88b1-206">在此示例中, 我们将删除 GUID 为*43c37853-ea10-4b90-a23d-ab8c93772471*的策略。</span><span class="sxs-lookup"><span data-stu-id="b88b1-206">In this example, we are removing the policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span>          |

    <span data-ttu-id="b88b1-207">出现提示时, 请确认更改。</span><span class="sxs-lookup"><span data-stu-id="b88b1-207">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="b88b1-208">对要删除的每个策略重复步骤1-2。</span><span class="sxs-lookup"><span data-stu-id="b88b1-208">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="b88b1-209">删除完策略后, 应用所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b88b1-209">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="b88b1-210">为此, 请使用**InformationBarrierPoliciesApplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b88b1-210">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="b88b1-211">语法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="b88b1-211">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="b88b1-212">为您的组织应用更改的用户。</span><span class="sxs-lookup"><span data-stu-id="b88b1-212">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="b88b1-213">如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="b88b1-213">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

## <a name="stop-a-policy-application"></a><span data-ttu-id="b88b1-214">停止策略应用程序</span><span class="sxs-lookup"><span data-stu-id="b88b1-214">Stop a policy application</span></span>

<span data-ttu-id="b88b1-215">如果在您开始应用信息屏障策略后, 您想要停止应用这些策略, 请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="b88b1-215">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="b88b1-216">请注意, 此过程将需要大约30-35 分钟才能开始。</span><span class="sxs-lookup"><span data-stu-id="b88b1-216">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="b88b1-217">若要查看最新信息屏障策略应用程序的状态, 请使用**InformationBarrierPoliciesApplicationStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b88b1-217">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="b88b1-218">语法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="b88b1-218">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="b88b1-219">记下应用程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="b88b1-219">Note the application's GUID.</span></span>

2. <span data-ttu-id="b88b1-220">将**InformationBarrierPoliciesApplication** Cmdlet 与 Identity 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="b88b1-220">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="b88b1-221">语法</span><span class="sxs-lookup"><span data-stu-id="b88b1-221">Syntax</span></span>  |<span data-ttu-id="b88b1-222">示例</span><span class="sxs-lookup"><span data-stu-id="b88b1-222">Example</span></span>  |
    |---------|---------|
    |`Stop-InformationBarrierPoliciesApplication -Identity GUID`     |`Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p><span data-ttu-id="b88b1-223">在此示例中, 我们将停止应用信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="b88b1-223">In this example, we are stopping information barrier policies from being applied.</span></span>         |

## <a name="related-articles"></a><span data-ttu-id="b88b1-224">相关文章</span><span class="sxs-lookup"><span data-stu-id="b88b1-224">Related articles</span></span>

[<span data-ttu-id="b88b1-225">获取信息障碍概述</span><span class="sxs-lookup"><span data-stu-id="b88b1-225">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="b88b1-226">定义信息障碍策略</span><span class="sxs-lookup"><span data-stu-id="b88b1-226">Define policies for information barriers</span></span>](information-barriers-policies.md)

[<span data-ttu-id="b88b1-227">了解有关 Microsoft 团队中的信息障碍的详细信息</span><span class="sxs-lookup"><span data-stu-id="b88b1-227">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="b88b1-228">信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="b88b1-228">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="b88b1-229">信息障碍故障排除</span><span class="sxs-lookup"><span data-stu-id="b88b1-229">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)

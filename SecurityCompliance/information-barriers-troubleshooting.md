---
title: 信息障碍故障排除
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用本文作为对信息障碍进行故障排除的指导。
ms.openlocfilehash: b88f97cd872d4ea3b95bfac049f47cd71dfb2cb2
ms.sourcegitcommit: c603a07d24c4c764bdcf13f9354b3b4b7a76f656
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131346"
---
# <a name="troubleshooting-information-barriers-preview"></a><span data-ttu-id="d683e-103">解决信息障碍 (预览)</span><span class="sxs-lookup"><span data-stu-id="d683e-103">Troubleshooting information barriers (Preview)</span></span>

<span data-ttu-id="d683e-104">[信息障碍 (预览版)](information-barriers.md)可帮助您的组织遵守法律要求和行业法规。</span><span class="sxs-lookup"><span data-stu-id="d683e-104">[Information barriers (Preview)](information-barriers.md) can help your organization remain compliant with legal requirements and industry regulations.</span></span> <span data-ttu-id="d683e-105">例如, 通过信息障碍, 可以限制特定用户组之间的通信, 以避免利益冲突或其他问题。</span><span class="sxs-lookup"><span data-stu-id="d683e-105">For example, with information barriers, you can restrict communication between specific groups of users to avoid a conflict of interest or other issues.</span></span> <span data-ttu-id="d683e-106">(若要了解有关如何设置信息屏障的详细信息, 请参阅[定义信息障碍策略 (预览版)](information-barriers-policies.md)。)</span><span class="sxs-lookup"><span data-stu-id="d683e-106">(To learn more about how to set up information barriers, see [Define policies for information barriers (Preview)](information-barriers-policies.md).)</span></span>

<span data-ttu-id="d683e-107">如果用户在发生信息障碍后遇到意外问题, 则可以采取一些步骤来解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="d683e-107">In the event that people run into unexpected issues after information barriers are in place, there are some steps you can take to resolve those issues.</span></span> <span data-ttu-id="d683e-108">将本文用作指南。</span><span class="sxs-lookup"><span data-stu-id="d683e-108">Use this article as a guide.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="d683e-109">开始之前 .。。</span><span class="sxs-lookup"><span data-stu-id="d683e-109">Before you begin...</span></span>

<span data-ttu-id="d683e-110">若要执行本文中所述的任务, 必须为您分配适当的角色, 如以下某项:</span><span class="sxs-lookup"><span data-stu-id="d683e-110">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span>
- <span data-ttu-id="d683e-111">Microsoft 365 企业全局管理员</span><span class="sxs-lookup"><span data-stu-id="d683e-111">Microsoft 365 Enterprise Global Administrator</span></span>
- <span data-ttu-id="d683e-112">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="d683e-112">Office 365 Global Administrator</span></span>
- <span data-ttu-id="d683e-113">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="d683e-113">Compliance Administrator</span></span>
- <span data-ttu-id="d683e-114">IB 合规性管理 (这是一个新角色!)</span><span class="sxs-lookup"><span data-stu-id="d683e-114">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="d683e-115">若要了解有关信息障碍的先决条件方面的详细信息, 请参阅[先决条件 (适用于信息屏障策略)](information-barriers-policies.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="d683e-115">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span>

<span data-ttu-id="d683e-116">请确保[连接到 Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="d683e-116">Make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="issue-communications-are-still-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a><span data-ttu-id="d683e-117">问题: 仍允许在 Microsoft 团队中阻止的用户之间进行通信</span><span class="sxs-lookup"><span data-stu-id="d683e-117">Issue: Communications are still allowed between users who should be blocked in Microsoft Teams</span></span>

<span data-ttu-id="d683e-118">在这种情况下, 尽管信息屏障已定义、活动和应用, 但应阻止其在 Microsoft 团队中相互通信的人员。</span><span class="sxs-lookup"><span data-stu-id="d683e-118">In this case, although information barriers are defined, active, and applied, people who should be prevented from communicating with each other still can in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="d683e-119">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="d683e-119">What to do</span></span>

<span data-ttu-id="d683e-120">验证相关用户是否包含在信息屏障策略中。</span><span class="sxs-lookup"><span data-stu-id="d683e-120">Verify that the users in question are included in an information barrier policy.</span></span> <span data-ttu-id="d683e-121">使用具有 Identity 参数的**InformationBarrierRecipientStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d683e-121">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span>

<span data-ttu-id="d683e-122">语法`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="d683e-122">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> 

<span data-ttu-id="d683e-123">您可以使用任何唯一标识每个用户的值, 如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="d683e-123">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> 

<span data-ttu-id="d683e-124">示例：`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="d683e-124">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> 

<span data-ttu-id="d683e-125">在此示例中, 我们引用 Office 365 中的两个用户帐户: *meganb* for *Megan*和*alexw* for *Alex*。</span><span class="sxs-lookup"><span data-stu-id="d683e-125">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> 

<span data-ttu-id="d683e-126">(也可以将此 cmdlet 用于单个用户: `Get-InformationBarrierRecipientStatus -Identity <value>`) 此 cmdlet 将返回有关用户的信息, 如属性值和应用的任何信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="d683e-126">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`) This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>


|<span data-ttu-id="d683e-127">结果</span><span class="sxs-lookup"><span data-stu-id="d683e-127">Results</span></span>  |<span data-ttu-id="d683e-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d683e-128">Next steps</span></span>  |
|---------|---------|
|<span data-ttu-id="d683e-129">未列出所选用户的任何段</span><span class="sxs-lookup"><span data-stu-id="d683e-129">No segments are listed for the selected user(s)</span></span>     |<span data-ttu-id="d683e-130">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d683e-130">Do one of the following:</span></span><br/><span data-ttu-id="d683e-131">-通过在 Azure Active Directory 中编辑用户配置文件, 将用户分配到现有分段</span><span class="sxs-lookup"><span data-stu-id="d683e-131">- Assign users to an existing segment by editing their user profiles in Azure Active Directory</span></span><br/><span data-ttu-id="d683e-132">-使用[受支持的信息障碍属性](information-barriers-attributes.md)定义段</span><span class="sxs-lookup"><span data-stu-id="d683e-132">- Define a segment using a [supported attribute for information barriers](information-barriers-attributes.md)</span></span>         |
|<span data-ttu-id="d683e-133">列出了分段, 但没有为这些分段分配信息障碍策略</span><span class="sxs-lookup"><span data-stu-id="d683e-133">Segments are listed but no information barrier policies are assigned to those segments</span></span>     |<span data-ttu-id="d683e-134">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d683e-134">Do one of the following:</span></span><br/><span data-ttu-id="d683e-135">- 为问题的每个分段[定义信息障碍策略](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="d683e-135">- [Define an information barrier policy](information-barriers-policies.md#part-2-define-information-barrier-policies) for each segment in question</span></span><br/><span data-ttu-id="d683e-136">- [编辑信息屏障策略](information-barriers-policies.md#edit-a-policy)并将其分配给正确的段</span><span class="sxs-lookup"><span data-stu-id="d683e-136">- [Edit an information barrier policy](information-barriers-policies.md#edit-a-policy) and assign it to the correct segment</span></span>         |
|<span data-ttu-id="d683e-137">列出了分段, 每个段都包含在信息屏障策略中</span><span class="sxs-lookup"><span data-stu-id="d683e-137">Segments are listed and each is included in an information barrier policy</span></span>     |<span data-ttu-id="d683e-138">-运行`Get-InformationBarrierPolicy` cmdlet 以验证信息屏障策略是否处于活动状态</span><span class="sxs-lookup"><span data-stu-id="d683e-138">- Run the `Get-InformationBarrierPolicy` cmdlet to verify that information barrier policies are active</span></span><br/><span data-ttu-id="d683e-139">-运行`Get-InformationBarrierPoliciesApplicationStatus` cmdlet 以确认应用了策略</span><span class="sxs-lookup"><span data-stu-id="d683e-139">- Run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet to confirm the policies are applied</span></span><br/><span data-ttu-id="d683e-140">-运行`Start-InformationBarrierPoliciesApplication` cmdlet 以应用所有活动信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="d683e-140">- Run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies</span></span>          |


## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a><span data-ttu-id="d683e-141">问题: 意外阻止用户在 Microsoft 团队中进行通信</span><span class="sxs-lookup"><span data-stu-id="d683e-141">Issue: People are unexpectedly blocked from communicating in Microsoft Teams</span></span> 

<span data-ttu-id="d683e-142">在这种情况下, 人们会报告在 Microsoft 团队中进行通信时遇到的意外问题。</span><span class="sxs-lookup"><span data-stu-id="d683e-142">In this case, people are reporting unexpected issues communicating in Microsoft Teams.</span></span> <span data-ttu-id="d683e-143">示例：</span><span class="sxs-lookup"><span data-stu-id="d683e-143">Examples:</span></span>
- <span data-ttu-id="d683e-144">用户无法在 Microsoft 团队中找到其他用户或与之通信。</span><span class="sxs-lookup"><span data-stu-id="d683e-144">A user is unable to find or communicate with another user in Microsoft Teams.</span></span>
- <span data-ttu-id="d683e-145">用户无法在 Microsoft 团队中查看或选择其他用户。</span><span class="sxs-lookup"><span data-stu-id="d683e-145">A user cannot see or select another user in Microsoft Teams.</span></span>
- <span data-ttu-id="d683e-146">用户可以查看其他用户, 但不能在 Microsoft 团队中选择或向其他用户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="d683e-146">A user can see another user, but cannot select or send messages to that other user in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="d683e-147">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="d683e-147">What to do</span></span>

1. <span data-ttu-id="d683e-148">确定用户是否受信息屏障策略的影响。</span><span class="sxs-lookup"><span data-stu-id="d683e-148">Determine whether the users are affected by an information barrier policy.</span></span> <span data-ttu-id="d683e-149">为此, 请使用**InformationBarrierRecipientStatus** Cmdlet 和 Identity 参数。</span><span class="sxs-lookup"><span data-stu-id="d683e-149">To do this, use the **Get-InformationBarrierRecipientStatus** cmdlet with the Identity parameter.</span></span> 

    <span data-ttu-id="d683e-150">语法为`Get-InformationBarrierRecipientStatus -Identity`</span><span class="sxs-lookup"><span data-stu-id="d683e-150">The syntax is `Get-InformationBarrierRecipientStatus -Identity`</span></span>

    <span data-ttu-id="d683e-151">您可以使用任何标识值来唯一标识每个收件人, 如名称、别名、可分辨名称 (DN)、规范 DN、电子邮件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="d683e-151">You can use any identity value that uniquely identifies each recipient, such as Name, Alias, Distinguished name (DN), Canonical DN, Email address, or GUID.</span></span>

    <span data-ttu-id="d683e-152">示例：`Get-InformationBarrierRecipientStatus -Identity meganb`</span><span class="sxs-lookup"><span data-stu-id="d683e-152">Example: `Get-InformationBarrierRecipientStatus -Identity meganb`</span></span>

    <span data-ttu-id="d683e-153">在此示例中, 我们使用 Identity 参数的别名 (*meganb*)。</span><span class="sxs-lookup"><span data-stu-id="d683e-153">In this example, we are using an alias (*meganb*) for the Identity parameter.</span></span> <span data-ttu-id="d683e-154">此 cmdlet 将返回指示用户是否受信息屏障策略影响的信息。</span><span class="sxs-lookup"><span data-stu-id="d683e-154">This cmdlet will return information that indicates whether the user is affected by an information barrier policy.</span></span> <span data-ttu-id="d683e-155">(查找 \* ExoPolicyId: \<GUID>。)</span><span class="sxs-lookup"><span data-stu-id="d683e-155">(Look for \*ExoPolicyId: \<GUID>.)</span></span>

    <span data-ttu-id="d683e-156">如果用户未包含在信息屏障策略中, 请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="d683e-156">If the users are not included in information barrier policies, contact support.</span></span> <span data-ttu-id="d683e-157">否则，继续执行下一步。</span><span class="sxs-lookup"><span data-stu-id="d683e-157">Otherwise, proceed to the next step.</span></span>

2. <span data-ttu-id="d683e-158">了解信息屏障策略中包括的段落。</span><span class="sxs-lookup"><span data-stu-id="d683e-158">Find out which segments are included in an information barrier policy.</span></span> <span data-ttu-id="d683e-159">若要执行此操作, `Get-InformationBarrierPolicy`请将 Cmdlet 与 Identity 参数结合使用。</span><span class="sxs-lookup"><span data-stu-id="d683e-159">To do this, use the `Get-InformationBarrierPolicy` cmdlet with the Identity parameter.</span></span> <span data-ttu-id="d683e-160">使用在上一步中收到的策略 GUID (ExoPolicyId) 等详细信息作为标识值。</span><span class="sxs-lookup"><span data-stu-id="d683e-160">Use details, such as the policy GUID (ExoPolicyId) you received during the previous step, as an identity value.</span></span>

    <span data-ttu-id="d683e-161">示例：`Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span><span class="sxs-lookup"><span data-stu-id="d683e-161">Example: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span></span>

    <span data-ttu-id="d683e-162">在此示例中, 我们将获取有关具有 ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*的信息屏障策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d683e-162">In this example, we are getting detailed information about the information barrier policy that has ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span></span>
    
    <span data-ttu-id="d683e-163">运行 cmdlet 后, 在 "结果" 中, 查找 " **AssignedSegment**"、" **SegmentsAllowed**" 和 " **SegmentsBlocked** " 值。</span><span class="sxs-lookup"><span data-stu-id="d683e-163">After you run the cmdlet, in the results, look for **AssignedSegment**, **SegmentsAllowed**, and **SegmentsBlocked** values.</span></span>

    <span data-ttu-id="d683e-164">示例: 运行`Get-InformationBarrierPolicy` cmdlet 后, 我们在结果列表中看到以下内容:</span><span class="sxs-lookup"><span data-stu-id="d683e-164">Example: After running the `Get-InformationBarrierPolicy` cmdlet, we saw the following in our list of results:</span></span>

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    <span data-ttu-id="d683e-165">在这种情况下, 我们可以看到信息障碍策略会影响销售和研究领域中的人员。</span><span class="sxs-lookup"><span data-stu-id="d683e-165">In this case, we can see that an information barrier policy affects people who are in the Sales and Research segments.</span></span> <span data-ttu-id="d683e-166">在这种情况下, 将阻止 Sales 中的人员与 "调查" 中的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="d683e-166">In this case, people in Sales are prevented from communicating with people in Research.</span></span> <span data-ttu-id="d683e-167">如果看上去正确, 则信息障碍按预期工作。</span><span class="sxs-lookup"><span data-stu-id="d683e-167">If this seems correct, then information barriers are working as expected.</span></span> <span data-ttu-id="d683e-168">如果不是, 请继续执行下一步。</span><span class="sxs-lookup"><span data-stu-id="d683e-168">If not, proceed to the next step.</span></span>

4. <span data-ttu-id="d683e-169">请确保正确定义了段。</span><span class="sxs-lookup"><span data-stu-id="d683e-169">Make sure your segments are defined correctly.</span></span> <span data-ttu-id="d683e-170">为此, 请使用`Get-OrganizationSegment` cmdlet, 并查看结果列表。</span><span class="sxs-lookup"><span data-stu-id="d683e-170">To do this, use the `Get-OrganizationSegment` cmdlet, and review the list of results.</span></span> 

    <span data-ttu-id="d683e-171">若要查看特定段的详细信息, 请`Get-OrganizationSegment`将 Cmdlet 与 Identity 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="d683e-171">To view details for a specific segment, use the `Get-OrganizationSegment` cmdlet with an Identity parameter.</span></span> 

    <span data-ttu-id="d683e-172">示例：`Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span><span class="sxs-lookup"><span data-stu-id="d683e-172">Example: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span></span>

    <span data-ttu-id="d683e-173">在此示例中, 我们将获取有关具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的段的信息。</span><span class="sxs-lookup"><span data-stu-id="d683e-173">In this example, we are getting information about the segment that has GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.</span></span>

    <span data-ttu-id="d683e-174">查看段的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d683e-174">Review the details for the segment.</span></span> <span data-ttu-id="d683e-175">如有必要, 请[编辑段](information-barriers-policies.md#edit-a-segment), 然后重新使用`Start-InformationBarrierPoliciesApplication` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d683e-175">If necessary, [edit a segment](information-barriers-policies.md#edit-a-segment), and then re-use the `Start-InformationBarrierPoliciesApplication` cmdlet.</span></span>

    <span data-ttu-id="d683e-176">如果您仍遇到信息障碍策略问题, 请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="d683e-176">If you are still having issues with your information barrier policy, contact support.</span></span>
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a><span data-ttu-id="d683e-177">问题: 信息障碍应用程序进程花费的时间太长</span><span class="sxs-lookup"><span data-stu-id="d683e-177">Issue: The information barrier application process is taking too long</span></span>

<span data-ttu-id="d683e-178">运行**InformationBarrierPoliciesApplication** cmdlet 后, 该过程将花费很长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="d683e-178">After running the **Start-InformationBarrierPoliciesApplication** cmdlet, the process is taking a really long time to finish.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="d683e-179">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="d683e-179">What to do</span></span>

<span data-ttu-id="d683e-180">请注意, 在运行策略应用程序 cmdlet 时, 将为组织中的所有帐户应用 (或删除) 用户的信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="d683e-180">Keep in mind that when you run the policy application cmdlet, information barrier policies are being applied (or removed), user by user, for all accounts in your organization.</span></span> <span data-ttu-id="d683e-181">如果有很多用户, 需要一段时间才能处理。</span><span class="sxs-lookup"><span data-stu-id="d683e-181">If you have a lot of users, it will take a while to process.</span></span> <span data-ttu-id="d683e-182">(一般原则是, 处理5000用户帐户需要大约一小时的时间。)</span><span class="sxs-lookup"><span data-stu-id="d683e-182">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

1. <span data-ttu-id="d683e-183">使用**InformationBarrierPoliciesApplicationStatus** cmdlet 验证最近策略应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="d683e-183">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet to verify status of the most recent policy application.</span></span>

    <span data-ttu-id="d683e-184">语法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="d683e-184">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="d683e-185">(若要显示*所有*信息屏障策略应用程序的状态, 请使用以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d683e-185">(To display status for *all* information barrier policy applications, use this cmdlet:</span></span><br/>
    <span data-ttu-id="d683e-186">`Get-InformationBarrierPoliciesApplicationStatus -All $true`)</span><span class="sxs-lookup"><span data-stu-id="d683e-186"></span></span>

    <span data-ttu-id="d683e-187">这将显示有关策略应用程序是已完成、失败还是正在进行中的信息。。</span><span class="sxs-lookup"><span data-stu-id="d683e-187">This will display information about whether policy application completed, failed, or is in progress..</span></span>

2. <span data-ttu-id="d683e-188">根据上一步的结果, 执行下列步骤之一:</span><span class="sxs-lookup"><span data-stu-id="d683e-188">Depending on the results of the previous step, take one of the following steps:</span></span>
  
    |<span data-ttu-id="d683e-189">状态</span><span class="sxs-lookup"><span data-stu-id="d683e-189">Status</span></span>  |<span data-ttu-id="d683e-190">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d683e-190">Next step</span></span>  |
    |---------|---------|
    |<span data-ttu-id="d683e-191">**未启动**</span><span class="sxs-lookup"><span data-stu-id="d683e-191">**Not started**</span></span>     |<span data-ttu-id="d683e-192">如果自运行**InformationBarrierPoliciesApplication** cmdlet 后, 它已超过45分钟, 请查看您的审核日志, 以确定策略定义中是否存在任何错误, 或者应用程序尚未启动的其他原因。</span><span class="sxs-lookup"><span data-stu-id="d683e-192">If it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started.</span></span> |
    |<span data-ttu-id="d683e-193">**失败**</span><span class="sxs-lookup"><span data-stu-id="d683e-193">**Failed**</span></span>     |<span data-ttu-id="d683e-194">如果应用程序失败, 请查看您的审核日志。</span><span class="sxs-lookup"><span data-stu-id="d683e-194">If the application has failed, review your audit log.</span></span> <span data-ttu-id="d683e-195">此外, 还应查看你的段落和策略。</span><span class="sxs-lookup"><span data-stu-id="d683e-195">Also review your segments and policies.</span></span> <span data-ttu-id="d683e-196">是否有任何用户分配到多个段？</span><span class="sxs-lookup"><span data-stu-id="d683e-196">Are any users assigned to more than one segment?</span></span> <span data-ttu-id="d683e-197">是否为任何段分配了多个 poliicy？</span><span class="sxs-lookup"><span data-stu-id="d683e-197">Are any segments assigned more than one poliicy?</span></span> <span data-ttu-id="d683e-198">如有必要, 请[编辑分段](information-barriers-policies.md#edit-a-segment)和/或[编辑策略](information-barriers-policies.md#edit-a-policy), 然后再次运行**InformationBarrierPoliciesApplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d683e-198">If necessary, [edit segments](information-barriers-policies.md#edit-a-segment) and/or [edit policies](information-barriers-policies.md#edit-a-policy), and then run the **Start-InformationBarrierPoliciesApplication** cmdlet again.</span></span>  |
    |<span data-ttu-id="d683e-199">**进行中**</span><span class="sxs-lookup"><span data-stu-id="d683e-199">**In progress**</span></span>     |<span data-ttu-id="d683e-200">如果仍在运行应用程序, 请等待更多的时间完成。</span><span class="sxs-lookup"><span data-stu-id="d683e-200">If the application is still in progress, allow more time for it to complete.</span></span> <span data-ttu-id="d683e-201">如果是几天, 请收集你的审核日志, 然后与支持人员联系。</span><span class="sxs-lookup"><span data-stu-id="d683e-201">If it has been several days, gather your audit logs, and then contact support.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d683e-202">相关主题</span><span class="sxs-lookup"><span data-stu-id="d683e-202">Related topics</span></span>

[<span data-ttu-id="d683e-203">为 Microsoft 团队中的信息障碍定义策略 (预览)</span><span class="sxs-lookup"><span data-stu-id="d683e-203">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="d683e-204">信息障碍 (预览)</span><span class="sxs-lookup"><span data-stu-id="d683e-204">Information barriers (Preview)</span></span>](information-barriers.md)




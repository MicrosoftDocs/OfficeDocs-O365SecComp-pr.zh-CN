---
title: 信息障碍故障排除
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用本文作为对信息障碍进行故障排除的指导。
ms.openlocfilehash: b37585469ec8bb299b7976f8a330f4c6b29e3f95
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668277"
---
# <a name="troubleshooting-information-barriers-preview"></a><span data-ttu-id="a884e-103">解决信息障碍 (预览)</span><span class="sxs-lookup"><span data-stu-id="a884e-103">Troubleshooting information barriers (Preview)</span></span>

<span data-ttu-id="a884e-104">信息障碍可帮助您的组织遵守法律要求和行业法规。</span><span class="sxs-lookup"><span data-stu-id="a884e-104">Information barriers can help your organization remain compliant with legal requirements and industry regulations.</span></span> <span data-ttu-id="a884e-105">例如, 通过信息障碍, 可以限制特定用户组之间的通信, 以避免利益冲突或其他问题。</span><span class="sxs-lookup"><span data-stu-id="a884e-105">For example, with information barriers, you can restrict communication between specific groups of users to avoid a conflict of interest or other issues.</span></span> <span data-ttu-id="a884e-106">若要了解详细信息, 请参阅[信息障碍 (预览)](information-barriers.md)。</span><span class="sxs-lookup"><span data-stu-id="a884e-106">To learn more, see [Information barriers (Preview)](information-barriers.md).</span></span>

<span data-ttu-id="a884e-107">本文提供的指导可用于获取问题的答案或解决因信息障碍而可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="a884e-107">This article provides guidance you can use to get answers to questions or resolve issues that may arise with information barriers.</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="a884e-108">开始之前 .。。</span><span class="sxs-lookup"><span data-stu-id="a884e-108">Before you begin...</span></span>

<span data-ttu-id="a884e-109">若要执行本文中所述的任务, 必须为您分配适当的角色, 如以下某项:</span><span class="sxs-lookup"><span data-stu-id="a884e-109">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span>
- <span data-ttu-id="a884e-110">Microsoft 365 企业全局管理员</span><span class="sxs-lookup"><span data-stu-id="a884e-110">Microsoft 365 Enterprise Global Administrator</span></span>
- <span data-ttu-id="a884e-111">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="a884e-111">Office 365 Global Administrator</span></span>
- <span data-ttu-id="a884e-112">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="a884e-112">Compliance Administrator</span></span>
- <span data-ttu-id="a884e-113">IB 合规性管理 (这是一个新角色!)</span><span class="sxs-lookup"><span data-stu-id="a884e-113">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="a884e-114">若要了解有关角色和权限的详细信息, 请参阅[Office 365 Security & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a884e-114">To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="a884e-115">若要了解有关信息障碍的先决条件方面的详细信息, 请参阅[先决条件 (适用于信息屏障策略)](information-barriers-policies.md#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="a884e-115">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span>

<span data-ttu-id="a884e-116">此外, 请确保[连接到 Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="a884e-116">Also, make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a><span data-ttu-id="a884e-117">问题: 意外阻止用户在 Microsoft 团队中进行通信</span><span class="sxs-lookup"><span data-stu-id="a884e-117">Issue: People are unexpectedly blocked from communicating in Microsoft Teams</span></span> 

<span data-ttu-id="a884e-118">在这种情况下, 人们会报告在 Microsoft 团队中进行通信时遇到的意外问题。</span><span class="sxs-lookup"><span data-stu-id="a884e-118">In this case, people are reporting unexpected issues communicating in Microsoft Teams.</span></span> <span data-ttu-id="a884e-119">示例：</span><span class="sxs-lookup"><span data-stu-id="a884e-119">Examples:</span></span>
- <span data-ttu-id="a884e-120">用户无法在 Microsoft 团队中找到其他用户或与之通信。</span><span class="sxs-lookup"><span data-stu-id="a884e-120">A user is unable to find or communicate with another user in Microsoft Teams.</span></span>
- <span data-ttu-id="a884e-121">用户无法在 Microsoft 团队中查看或选择其他用户。</span><span class="sxs-lookup"><span data-stu-id="a884e-121">A user cannot see or select another user in Microsoft Teams.</span></span>
- <span data-ttu-id="a884e-122">用户可以查看, 但不能向 Microsoft 团队中的其他用户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="a884e-122">A user can see, but cannot send messages to, another user in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="a884e-123">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="a884e-123">What to do</span></span>

1. <span data-ttu-id="a884e-124">确定用户是否受信息屏障策略的影响。</span><span class="sxs-lookup"><span data-stu-id="a884e-124">Determine whether the users are affected by an information barrier policy.</span></span> <span data-ttu-id="a884e-125">为此, 请使用**InformationBarrierRecipientStatus** Cmdlet 和 Identity 参数。</span><span class="sxs-lookup"><span data-stu-id="a884e-125">To do this, use the **Get-InformationBarrierRecipientStatus** cmdlet with the Identity parameter.</span></span> 

    <span data-ttu-id="a884e-126">语法为`Get-InformationBarrierRecipientStatus -Identity`</span><span class="sxs-lookup"><span data-stu-id="a884e-126">The syntax is `Get-InformationBarrierRecipientStatus -Identity`</span></span>

    <span data-ttu-id="a884e-127">您可以使用任何标识值来唯一标识每个收件人, 如名称、别名、可分辨名称 (DN)、规范 DN、电子邮件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="a884e-127">You can use any identity value that uniquely identifies each recipient, such as Name, Alias, Distinguished name (DN), Canonical DN, Email address, or GUID.</span></span>

    <span data-ttu-id="a884e-128">示例：`Get-InformationBarrierRecipientStatus -Identity meganb`</span><span class="sxs-lookup"><span data-stu-id="a884e-128">Example: `Get-InformationBarrierRecipientStatus -Identity meganb`</span></span>

    <span data-ttu-id="a884e-129">在此示例中, 我们使用 Identity 参数的别名 (*meganb*)。</span><span class="sxs-lookup"><span data-stu-id="a884e-129">In this example, we are using an alias (*meganb*) for the Identity parameter.</span></span> <span data-ttu-id="a884e-130">此 cmdlet 将返回指示用户是否受信息屏障策略影响的信息。</span><span class="sxs-lookup"><span data-stu-id="a884e-130">This cmdlet will return information that indicates whether the user is affected by an information barrier policy.</span></span> <span data-ttu-id="a884e-131">(查找 \* ExoPolicyId: \<GUID>。)</span><span class="sxs-lookup"><span data-stu-id="a884e-131">(Look for \*ExoPolicyId: \<GUID>.)</span></span>

    <span data-ttu-id="a884e-132">如果用户未包含在信息屏障策略中, 请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="a884e-132">If the users are not included in information barrier policies, contact support.</span></span> <span data-ttu-id="a884e-133">否则，继续执行下一步。</span><span class="sxs-lookup"><span data-stu-id="a884e-133">Otherwise, proceed to the next step.</span></span>

2. <span data-ttu-id="a884e-134">了解信息屏障策略中包括的段落。</span><span class="sxs-lookup"><span data-stu-id="a884e-134">Find out which segments are included in an information barrier policy.</span></span> <span data-ttu-id="a884e-135">若要执行此操作, `Get-InformationBarrierPolicy`请将 Cmdlet 与 Identity 参数结合使用。</span><span class="sxs-lookup"><span data-stu-id="a884e-135">To do this, use the `Get-InformationBarrierPolicy` cmdlet with the Identity parameter.</span></span> <span data-ttu-id="a884e-136">使用在上一步中收到的策略 GUID (ExoPolicyId) 等详细信息作为标识值。</span><span class="sxs-lookup"><span data-stu-id="a884e-136">Use details, such as the policy GUID (ExoPolicyId) you received during the previous step, as an identity value.</span></span>

    <span data-ttu-id="a884e-137">示例：`Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span><span class="sxs-lookup"><span data-stu-id="a884e-137">Example: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span></span>

    <span data-ttu-id="a884e-138">在此示例中, 我们将获取有关具有 ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*的信息屏障策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a884e-138">In this example, we are getting detailed information about the information barrier policy that has ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span></span>
    
    <span data-ttu-id="a884e-139">运行 cmdlet 后, 在 "结果" 中, 查找 " **AssignedSegment**"、" **SegmentsAllowed**" 和 " **SegmentsBlocked** " 值。</span><span class="sxs-lookup"><span data-stu-id="a884e-139">After you run the cmdlet, in the results, look for **AssignedSegment**, **SegmentsAllowed**, and **SegmentsBlocked** values.</span></span>

    <span data-ttu-id="a884e-140">示例: 运行`Get-InformationBarrierPolicy` cmdlet 后, 我们在结果列表中看到以下内容:</span><span class="sxs-lookup"><span data-stu-id="a884e-140">Example: After running the `Get-InformationBarrierPolicy` cmdlet, we saw the following in our list of results:</span></span>

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    <span data-ttu-id="a884e-141">在这种情况下, 我们可以看到信息障碍策略会影响销售和研究领域中的人员。</span><span class="sxs-lookup"><span data-stu-id="a884e-141">In this case, we can see that an information barrier policy affects people who are in the Sales and Research segments.</span></span> <span data-ttu-id="a884e-142">在这种情况下, 将阻止 Sales 中的人员与 "调查" 中的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="a884e-142">In this case, people in Sales are prevented from communicating with people in Research.</span></span> <span data-ttu-id="a884e-143">如果看上去正确, 则信息障碍按预期工作。</span><span class="sxs-lookup"><span data-stu-id="a884e-143">If this seems correct, then information barriers are working as expected.</span></span> <span data-ttu-id="a884e-144">如果不是, 请继续执行下一步。</span><span class="sxs-lookup"><span data-stu-id="a884e-144">If not, proceed to the next step.</span></span>

4. <span data-ttu-id="a884e-145">请确保正确定义了段。</span><span class="sxs-lookup"><span data-stu-id="a884e-145">Make sure your segments are defined correctly.</span></span> <span data-ttu-id="a884e-146">为此, 请使用`Get-OrganizationSegment` cmdlet, 并查看结果列表。</span><span class="sxs-lookup"><span data-stu-id="a884e-146">To do this, use the `Get-OrganizationSegment` cmdlet, and review the list of results.</span></span> 

    <span data-ttu-id="a884e-147">若要查看特定段的详细信息, 请`Get-OrganizationSegment`将 Cmdlet 与 Identity 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="a884e-147">To view details for a specific segment, use the `Get-OrganizationSegment` cmdlet with an Identity parameter.</span></span> 

    <span data-ttu-id="a884e-148">示例：`Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span><span class="sxs-lookup"><span data-stu-id="a884e-148">Example: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span></span>

    <span data-ttu-id="a884e-149">在此示例中, 我们将获取有关具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的段的信息。</span><span class="sxs-lookup"><span data-stu-id="a884e-149">In this example, we are getting information about the segment that has GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.</span></span>

    <span data-ttu-id="a884e-150">查看段的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a884e-150">Review the details for the segment.</span></span> <span data-ttu-id="a884e-151">如有必要, 请[编辑段](information-barriers-policies.md#edit-a-segment), 然后重新使用`Start-InformationBarrierPoliciesApplication` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a884e-151">If necessary, [edit a segment](information-barriers-policies.md#edit-a-segment), and then re-use the `Start-InformationBarrierPoliciesApplication` cmdlet.</span></span>

    <span data-ttu-id="a884e-152">如果您仍遇到信息障碍策略问题, 请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="a884e-152">If you are still having issues with your information barrier policy, contact support.</span></span>
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a><span data-ttu-id="a884e-153">问题: 信息障碍应用程序进程花费的时间太长</span><span class="sxs-lookup"><span data-stu-id="a884e-153">Issue: The information barrier application process is taking too long</span></span>

<span data-ttu-id="a884e-154">运行**InformationBarrierPoliciesApplication** cmdlet 后, 该过程将花费很长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="a884e-154">After running the **Start-InformationBarrierPoliciesApplication** cmdlet, the process is taking a really long time to finish.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="a884e-155">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="a884e-155">What to do</span></span>

1. <span data-ttu-id="a884e-156">请注意, 在运行策略应用程序 cmdlet 时, 将为组织中的所有帐户应用 (或删除) 用户的信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="a884e-156">Keep in mind that when you run the policy application cmdlet, information barrier policies are being applied (or removed), user by user, for all accounts in your organization.</span></span> <span data-ttu-id="a884e-157">如果有很多用户, 需要一段时间才能处理。</span><span class="sxs-lookup"><span data-stu-id="a884e-157">If you have a lot of users, it will take a while to process.</span></span> <span data-ttu-id="a884e-158">(一般原则是, 处理5000用户帐户需要大约一小时的时间。)</span><span class="sxs-lookup"><span data-stu-id="a884e-158">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span> 

2. <span data-ttu-id="a884e-159">使用**InformationBarrierPoliciesApplicationStatus** cmdlet 验证状态。</span><span class="sxs-lookup"><span data-stu-id="a884e-159">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet to verify status.</span></span>

    <span data-ttu-id="a884e-160">语法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="a884e-160">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="a884e-161">若要显示所有信息屏障策略应用程序的状态, 请使用`Get-InformationBarrierPoliciesApplicationStatus -All $true`</span><span class="sxs-lookup"><span data-stu-id="a884e-161">To display status for all information barrier policy applications, use `Get-InformationBarrierPoliciesApplicationStatus -All $true`</span></span>

    <span data-ttu-id="a884e-162">这将显示有关策略应用程序是已完成、失败还是正在进行中的信息。。</span><span class="sxs-lookup"><span data-stu-id="a884e-162">This will display information about whether policy application completed, failed, or is in progress..</span></span>

3. <span data-ttu-id="a884e-163">根据步骤2的结果, 执行以下步骤之一:</span><span class="sxs-lookup"><span data-stu-id="a884e-163">Depending on the results of step 2, take one of the following steps:</span></span>

    - <span data-ttu-id="a884e-164">如果应用程序尚未启动, 并且由于已运行**InformationBarrierPoliciesApplication** cmdlet, 则已超过45分钟, 请查看您的审核日志以查看策略定义中是否存在任何错误, 或其他原因。应用程序尚未启动。</span><span class="sxs-lookup"><span data-stu-id="a884e-164">If the application has not started, and it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started.</span></span>

    - <span data-ttu-id="a884e-165">如果应用程序失败, 请查看您的段落和策略。</span><span class="sxs-lookup"><span data-stu-id="a884e-165">If the application has failed, review your segments and policies.</span></span> <span data-ttu-id="a884e-166">如有必要, 请[编辑分段](information-barriers-policies.md#edit-a-segment)和/或[编辑策略](information-barriers-policies.md#edit-a-policy), 然后再次运行**InformationBarrierPoliciesApplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a884e-166">If necessary, [edit segments](information-barriers-policies.md#edit-a-segment) and/or [edit policies](information-barriers-policies.md#edit-a-policy), and then run the **Start-InformationBarrierPoliciesApplication** cmdlet again.</span></span>

    - <span data-ttu-id="a884e-167">如果仍在运行应用程序, 请等待更多的时间完成。</span><span class="sxs-lookup"><span data-stu-id="a884e-167">If the application is still in progress, allow more time for it to complete.</span></span> <span data-ttu-id="a884e-168">如果已过几天, 请联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="a884e-168">If it has been several days, contact support.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a884e-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="a884e-169">Related topics</span></span>

[<span data-ttu-id="a884e-170">为 Microsoft 团队中的信息障碍定义策略 (预览)</span><span class="sxs-lookup"><span data-stu-id="a884e-170">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="a884e-171">信息障碍 (预览)</span><span class="sxs-lookup"><span data-stu-id="a884e-171">Information barriers (Preview)</span></span>](information-barriers.md)




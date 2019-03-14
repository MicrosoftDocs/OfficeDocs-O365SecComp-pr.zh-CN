---
title: Office 365 云应用安全中的会话策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: office 365 云应用安全会话策略启用实时会话级别监控, affording 您可以精细查看 Office 365 应用程序, 以及根据您为用户会话设置的策略执行不同操作的能力。 通过会话控制, 您可以在监视会话和/或限制特定会话活动时使用条件访问应用程序控件的反向代理功能, 而无需完全允许或阻止访问。
ms.openlocfilehash: e0e4b04ee8cc0f7a14adbc26b074a5f2947e44c2
ms.sourcegitcommit: 866d8cab6bcfdd124516a8369e47ec797bc7cf8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2019
ms.locfileid: "30312089"
---
# <a name="session-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="b3635-104">Office 365 云应用安全中的会话策略</span><span class="sxs-lookup"><span data-stu-id="b3635-104">Session policies in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="b3635-105">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b3635-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="b3635-106">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b3635-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="b3635-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b3635-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="b3635-108">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b3635-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="b3635-109">开始评估</span><span class="sxs-lookup"><span data-stu-id="b3635-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="b3635-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="b3635-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="b3635-111">你在这里!</span><span class="sxs-lookup"><span data-stu-id="b3635-111">You are here!</span></span>  <br/> [<span data-ttu-id="b3635-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b3635-112">Next step</span></span>](ocas-access-policies.md) <br/> |[<span data-ttu-id="b3635-113">开始利用</span><span class="sxs-lookup"><span data-stu-id="b3635-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="b3635-114">office 365 云应用安全会话策略启用实时会话级别监控, affording 您可以精细查看 Office 365 应用程序, 以及根据您为用户会话设置的策略执行不同操作的能力。</span><span class="sxs-lookup"><span data-stu-id="b3635-114">Office 365 Cloud App Security session policies enable real-time session-level monitoring, affording you granular visibility into Office 365 apps and the ability to take different actions depending on the policy you set for a user session.</span></span> <span data-ttu-id="b3635-115">通过会话控制, 您可以在监视会话和/或限制特定会话活动时使用条件访问应用程序控件的反向代理功能, 而无需完全允许或阻止访问。</span><span class="sxs-lookup"><span data-stu-id="b3635-115">Instead of allowing or blocking access completely, with session control you can allow access while monitoring the session and/or limit specific session activities using the reverse proxy capabilities of Conditional Access App Control.</span></span>

<span data-ttu-id="b3635-116">例如, 您可以确定来自非托管设备或来自特定位置的会话, 您希望允许用户访问应用程序, 但也限制下载敏感文件或要求在下载时保护特定文档。</span><span class="sxs-lookup"><span data-stu-id="b3635-116">For example, you can decide that from unmanaged devices, or for sessions coming from specific locations, you want to allow the user to access the app but also limit the download of sensitive files or require that certain documents be protected upon download.</span></span> <span data-ttu-id="b3635-117">通过会话策略, 您可以设置这些用户会话控件并允许访问, 并使您能够:</span><span class="sxs-lookup"><span data-stu-id="b3635-117">Session policies enable you to set these user-session controls and allow access and enables you to:</span></span>

- [<span data-ttu-id="b3635-118">监视所有活动</span><span class="sxs-lookup"><span data-stu-id="b3635-118">Monitor all activities</span></span>](#monitor-all-activities)

- [<span data-ttu-id="b3635-119">阻止所有下载</span><span class="sxs-lookup"><span data-stu-id="b3635-119">Block all downloads</span></span>](#block-all-downloads)

- [<span data-ttu-id="b3635-120">阻止特定活动</span><span class="sxs-lookup"><span data-stu-id="b3635-120">Block specific activities</span></span>](#block-specific-activities)

- [<span data-ttu-id="b3635-121">在下载时保护文件</span><span class="sxs-lookup"><span data-stu-id="b3635-121">Protect files on download</span></span>](#protect-files-on-download)

## <a name="prerequisites-to-using-session-policies"></a><span data-ttu-id="b3635-122">使用会话策略的先决条件</span><span class="sxs-lookup"><span data-stu-id="b3635-122">Prerequisites to using session policies</span></span>

- <span data-ttu-id="b3635-123">Azure AD 高级 P1 许可证</span><span class="sxs-lookup"><span data-stu-id="b3635-123">Azure AD Premium P1 license</span></span>

- <span data-ttu-id="b3635-124">应 [使用条件访问应用程序控件部署相关的](ocas-deploy-conditional-access-app-control.md)Office 365 应用程序</span><span class="sxs-lookup"><span data-stu-id="b3635-124">The relevant Office 365 apps should be [deployed with Conditional Access App Control](ocas-deploy-conditional-access-app-control.md)</span></span>

- <span data-ttu-id="b3635-125">应就地将用户重定向到 Office 365 云应用安全性的 [Azure AD 条件访问策略](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) </span><span class="sxs-lookup"><span data-stu-id="b3635-125">An [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) should be in place that redirects users to Office 365 Cloud App Security</span></span>

## <a name="create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="b3635-126">创建 Azure AD 条件访问策略</span><span class="sxs-lookup"><span data-stu-id="b3635-126">Create an Azure AD conditional access policy</span></span>

<span data-ttu-id="b3635-127">Azure Active Directory 条件访问策略和云应用安全会话策略一起运行, 以检查每个用户会话并为每个应用制定策略决策。</span><span class="sxs-lookup"><span data-stu-id="b3635-127">Azure Active Directory conditional access policies and Cloud App Security session policies work in tandem to examine each user session and make policy decisions for each app.</span></span> <span data-ttu-id="b3635-128">若要在 Azure AD 中设置条件访问策略, 请按照以下过程操作:</span><span class="sxs-lookup"><span data-stu-id="b3635-128">To set up a conditional access policy in Azure AD, follow this procedure:</span></span>

1. <span data-ttu-id="b3635-129">使用 "条件访问应用程序" 控件的一个用户或一组用户以及要控制的应用程序的分配来配置 [Azure AD 条件访问策略](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) 。</span><span class="sxs-lookup"><span data-stu-id="b3635-129">Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for a user or group of users and the app you want to control with the Conditional Access App Control.</span></span> <span data-ttu-id="b3635-130">注意: 仅此策略会影响 [使用条件访问应用程序控件](ocas-deploy-conditional-access-app-control.md) 部署的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b3635-130">NOTE: Only apps that were [deployed with Conditional Access App Control](ocas-deploy-conditional-access-app-control.md) will be affected by this policy.</span></span>

2. <span data-ttu-id="b3635-131">通过在 " **会话** " 页中选择 " **使用条件访问应用程序控制强制性限制** " 将用户路由到 Office 365 云应用安全性。</span><span class="sxs-lookup"><span data-stu-id="b3635-131">Route users to Office 365 Cloud App Security by selecting the **Use Conditional Access App Control enforced restrictions** in the **Session** page.</span></span>

## <a name="create-a-cloud-app-security-session-policy"></a><span data-ttu-id="b3635-132">创建云应用安全会话策略</span><span class="sxs-lookup"><span data-stu-id="b3635-132">Create a Cloud App Security session policy</span></span>

<span data-ttu-id="b3635-133">若要创建新的会话策略, 请按照以下过程操作:</span><span class="sxs-lookup"><span data-stu-id="b3635-133">To create a new session policy, follow this procedure:</span></span>

1. <span data-ttu-id="b3635-134">在门户中, 依次选择 " **控制** " 和 " **策略**"。</span><span class="sxs-lookup"><span data-stu-id="b3635-134">In the portal, select **Control** followed by **Policies**.</span></span>

2. <span data-ttu-id="b3635-135">在 " **策略** " 页中, 单击 " **创建策略** ", 然后选择 " **会话策略**"。</span><span class="sxs-lookup"><span data-stu-id="b3635-135">In the **Policies** page, click **Create policy** and select **Session policy**.</span></span>

3. <span data-ttu-id="b3635-136">在 " **会话策略** " 窗口中, 为策略分配名称</span><span class="sxs-lookup"><span data-stu-id="b3635-136">In the **Session policy** window, assign a name for your policy</span></span>

4. <span data-ttu-id="b3635-137">在 " **会话控制类型** " 字段中:</span><span class="sxs-lookup"><span data-stu-id="b3635-137">In the **Session control type** field:</span></span>
    
    - <span data-ttu-id="b3635-138">仅当您只想监视用户的活动时, **才** 选择 "监视器"。</span><span class="sxs-lookup"><span data-stu-id="b3635-138">Select **Monitor only** if you only want to monitor activities by users.</span></span> <span data-ttu-id="b3635-139">此选项将为您选择的应用程序创建 "仅监视" 策略, 在这些应用程序中, 将下载所有登录、启发式下载和活动类型。</span><span class="sxs-lookup"><span data-stu-id="b3635-139">This selection will create a Monitor only policy for the apps you selected where all sign-ins, heuristic downloads, and Activity types will be downloaded.</span></span>
    
    - <span data-ttu-id="b3635-140">如果要监视用户活动, 请选择 " **控制文件下载 (使用 DLP)** "。</span><span class="sxs-lookup"><span data-stu-id="b3635-140">Select **Control file download (with DLP)** if you want to monitor user activities.</span></span> <span data-ttu-id="b3635-141">您可以执行其他操作, 如阻止或保护用户的下载。</span><span class="sxs-lookup"><span data-stu-id="b3635-141">You can take additional actions like block or protect downloads for users.</span></span>
    
    - <span data-ttu-id="b3635-142">选择 " **阻止活动** " 以阻止特定活动, 您可以使用 **活动类型** 筛选器选择这些活动。</span><span class="sxs-lookup"><span data-stu-id="b3635-142">Select **Block activities** to block specific activities, which you can select using the **Activity type** filter.</span></span> <span data-ttu-id="b3635-143">将监视 (并在活动日志中报告) 所选应用中的所有活动。</span><span class="sxs-lookup"><span data-stu-id="b3635-143">All activities from selected apps will be monitored (and reported in the Activity log).</span></span> <span data-ttu-id="b3635-144">如果选择 " **阻止** " 操作, 则将阻止您选择的特定活动。</span><span class="sxs-lookup"><span data-stu-id="b3635-144">The specific activities you select will be blocked if you select the **Block** action.</span></span> <span data-ttu-id="b3635-145">如果选择 " **测试** 操作" 并启用 "通知", 则您选择的特定活动将引发警报。</span><span class="sxs-lookup"><span data-stu-id="b3635-145">The specific activities you selected will raise alerts if you select the **Test** action and have alerts turned on.</span></span>

5. <span data-ttu-id="b3635-146">在 " **活动源** " 下, 在 **匹配以下** 所有部分的活动中, 选择要应用于策略的其他活动筛选器。</span><span class="sxs-lookup"><span data-stu-id="b3635-146">Under **Activity source** in the **Activities matching all of the following** section, select additional activity filters to apply to the policy.</span></span> <span data-ttu-id="b3635-147">这些筛选器可以包含以下选项:</span><span class="sxs-lookup"><span data-stu-id="b3635-147">These filters can include the following options:</span></span>
    
    - <span data-ttu-id="b3635-148">**设备标记**: 使用此筛选器可标识非托管设备。</span><span class="sxs-lookup"><span data-stu-id="b3635-148">**Device tags**: Use this filter to identify unmanaged devices.</span></span>
    
    - <span data-ttu-id="b3635-149">**位置**: 使用此筛选器可确定未知 (因而是有风险的) 位置。</span><span class="sxs-lookup"><span data-stu-id="b3635-149">**Location**: Use this filter to identify unknown (and therefore risky) locations.</span></span>
    
    - <span data-ttu-id="b3635-150">**IP 地址**: 使用此筛选器筛选每个 IP 地址或使用之前分配的 ip 地址标记。</span><span class="sxs-lookup"><span data-stu-id="b3635-150">**IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags.</span></span>
    
    - <span data-ttu-id="b3635-151">**用户代理标记**: 使用此筛选器可启用启发, 以确定移动和桌面应用。</span><span class="sxs-lookup"><span data-stu-id="b3635-151">**User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps.</span></span> <span data-ttu-id="b3635-152">此筛选器可设置为等于或不等于 **本机客户端**。</span><span class="sxs-lookup"><span data-stu-id="b3635-152">This filter can be set to equals or doesn't equal **Native client**.</span></span> <span data-ttu-id="b3635-153">应针对每个云应用为你的移动和桌面应用测试此筛选器。</span><span class="sxs-lookup"><span data-stu-id="b3635-153">This filter should be tested against your mobile and desktop apps for each cloud app.</span></span><br><span data-ttu-id="b3635-154">注意: 会话策略不支持移动和桌面应用。</span><span class="sxs-lookup"><span data-stu-id="b3635-154">NOTE: Session policies don’t support mobile and desktop apps.</span></span> <span data-ttu-id="b3635-155">也可以通过创建访问策略来阻止或允许移动应用和桌面应用。</span><span class="sxs-lookup"><span data-stu-id="b3635-155">Mobile apps and desktop apps can also be blocked or allowed by creating an access policy.</span></span>

6. <span data-ttu-id="b3635-156">如果选择了用于 **控制文件下载 (使用 DLP)** 的选项, 请在 " **活动源** " 下的 " **文件与以下** 所有内容匹配" 部分中, 选择 "其他文件筛选器" 以应用于该策略。</span><span class="sxs-lookup"><span data-stu-id="b3635-156">If you selected the option to **Control file download (with DLP)**, under **Activity source** in the **Files matching all of the following** section, select additional file filters to apply to the policy.</span></span> <span data-ttu-id="b3635-157">这些筛选器可以包含以下选项:</span><span class="sxs-lookup"><span data-stu-id="b3635-157">These filters can include the following options:</span></span>
        
    - <span data-ttu-id="b3635-158">**分类标签** -如果你的组织使用 Azure 信息保护, 并且你的数据已由其分类标签保护, 则使用此筛选器。</span><span class="sxs-lookup"><span data-stu-id="b3635-158">**Classification label** - Use this filter if your organization uses Azure Information Protection and your data has been protected by its Classification labels.</span></span> <span data-ttu-id="b3635-159">您可以根据应用于这些文件的分类标签对文件进行筛选。</span><span class="sxs-lookup"><span data-stu-id="b3635-159">You can filter files based on the Classification label you applied to them.</span></span> <span data-ttu-id="b3635-160">有关与 azure 信息保护的集成的详细信息, 请参阅 [azure 信息保护集成](https://docs.microsoft.com/cloud-app-security/azip-integration)。</span><span class="sxs-lookup"><span data-stu-id="b3635-160">For more information about integration with Azure Information Protection, see [Azure Information Protection integration](https://docs.microsoft.com/cloud-app-security/azip-integration).</span></span>
        
    - <span data-ttu-id="b3635-161">\*\*\*\* 文件名-使用此筛选器将策略应用于特定文件。</span><span class="sxs-lookup"><span data-stu-id="b3635-161">**File name** - Use this filter to apply the policy to specific files.</span></span>
        
    - <span data-ttu-id="b3635-162">**文件类型** -使用此筛选器将策略应用于特定文件类型, 例如, 阻止下载所有 .xls 文件。</span><span class="sxs-lookup"><span data-stu-id="b3635-162">**File type** - Use this filter to apply the policy to specific file types, for example, block download for all .xls files.</span></span>
    
    - <span data-ttu-id="b3635-163">在 " **内容检查** " 部分中, 设置是否要使 DLP 引擎能够扫描文档和文件内容。</span><span class="sxs-lookup"><span data-stu-id="b3635-163">In the **Content inspection** section, set whether you want to enable the DLP engine to scan documents and file content.</span></span>
    
    - <span data-ttu-id="b3635-164">在 " **操作**" 下, 选择以下项之一:</span><span class="sxs-lookup"><span data-stu-id="b3635-164">Under **Actions**, select one of the following items:</span></span>
        
        - <span data-ttu-id="b3635-165">**测试 (监视所有活动)**: 将此操作设置为根据您设置的策略筛选器明确允许下载。</span><span class="sxs-lookup"><span data-stu-id="b3635-165">**Test (Monitor all activities)**: Set this action to explicitly allow download according to the policy filters you set.</span></span>
        
        - <span data-ttu-id="b3635-166">**阻止 (阻止文件下载和监视所有活动)**: 将此操作设置为根据您设置的策略筛选器显式阻止下载。</span><span class="sxs-lookup"><span data-stu-id="b3635-166">**Block (Block file download and monitor all activities)**: Set this action to explicitly block download according to the policy filters you set.</span></span> <span data-ttu-id="b3635-167">有关详细信息, 请参阅 [阻止下载的工作原理](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#block-download)。</span><span class="sxs-lookup"><span data-stu-id="b3635-167">For more information, see [How block download works](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#block-download).</span></span>
        
        - <span data-ttu-id="b3635-168">**保护 (应用分类标签以下载和监视所有活动)**: 只有在 " **会话策略**" 下选择了 " **控制文件下载 (使用 DLP)** " 时, 此选项才可用。</span><span class="sxs-lookup"><span data-stu-id="b3635-168">**Protect (Apply classification label to download and monitor all activities)**: This option is only available if you selected **Control file download (with DLP)** under **Session policy**.</span></span> <span data-ttu-id="b3635-169">如果你的组织使用 azure 信息保护, 则可以将 **操作** 设置为对文件应用 azure 信息保护中的分类标签集。</span><span class="sxs-lookup"><span data-stu-id="b3635-169">If your organization uses Azure Information Protection, you can set an **Action** to apply a classification label set in Azure Information Protection to the file.</span></span> <span data-ttu-id="b3635-170">有关详细信息, 请参阅 [保护下载的工作原理](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#protect-download)。</span><span class="sxs-lookup"><span data-stu-id="b3635-170">For more information, see [How protect download works](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#protect-download).</span></span>

7. <span data-ttu-id="b3635-171">您 可以 **为具有策略严重性的每个匹配事件创建一个警报**, 并设置一个警报限制。</span><span class="sxs-lookup"><span data-stu-id="b3635-171">You can **Create an alert for each matching event with the policy's severity** and set an alert limit.</span></span> <span data-ttu-id="b3635-172">选择要将警报作为电子邮件、短信还是同时作为这两者。</span><span class="sxs-lookup"><span data-stu-id="b3635-172">Select whether you want the alert as an email, a text message, or both.</span></span>

## <a name="monitor-all-activities"></a><span data-ttu-id="b3635-173">监视所有活动</span><span class="sxs-lookup"><span data-stu-id="b3635-173">Monitor all activities</span></span>

<span data-ttu-id="b3635-174">创建会话策略时, 匹配策略的每个用户会话将被重定向到会话控制, 而不是直接重定向到应用。</span><span class="sxs-lookup"><span data-stu-id="b3635-174">When you create a session policy, each user session that matches the policy is redirected to session control rather than to the app directly.</span></span> <span data-ttu-id="b3635-175">用户将看到一个监控通知, 让他们知道他们的会话已被监视。</span><span class="sxs-lookup"><span data-stu-id="b3635-175">The user will see a monitoring notice to let them know that their sessions are being monitored.</span></span>

<span data-ttu-id="b3635-176">如果您不想通知用户他们被监视, 可以禁用通知消息。</span><span class="sxs-lookup"><span data-stu-id="b3635-176">If you don't want to notify the user that they're being monitored, you can disable the notification message.</span></span>

1. <span data-ttu-id="b3635-177">在 "设置" cog 下, 选择 " **常规设置**"。</span><span class="sxs-lookup"><span data-stu-id="b3635-177">Under the settings cog, select **General settings**.</span></span>

2. <span data-ttu-id="b3635-178">然后, 在 " **条件 Access 应用程序控制** " 下, 选择 " **用户监视** ", 然后取消选中 " **通知用户** " 复选</span><span class="sxs-lookup"><span data-stu-id="b3635-178">Then, under **Conditional Access App Control** select **User monitoring** and unselect the **Notify users** checkbox.</span></span>

<span data-ttu-id="b3635-179">若要将用户保留在会话中, 条件访问应用程序控件将使用 Office 365 云应用安全 url 替换应用程序会话中的所有相关 url、Java 脚本和 cookie。</span><span class="sxs-lookup"><span data-stu-id="b3635-179">To keep the user within the session, Conditional Access App Control replaces all the relevant URLs, Java scripts, and cookies within the app session with Office 365 Cloud App Security URLs.</span></span> <span data-ttu-id="b3635-180">例如, 如果应用返回的页面的链接的域以其所属的`myapp.com`域结束, 则条件 Access 应用程序控件将使用以类似`myapp.com.us.cas.ms`方式结尾的域替换链接。</span><span class="sxs-lookup"><span data-stu-id="b3635-180">For example, if the app returns a page with links whose domains ends with `myapp.com`, Conditional Access App Control replaces the links with domains ending with something like `myapp.com.us.cas.ms`.</span></span> <span data-ttu-id="b3635-181">通过这种方式, 将通过 Office 365 云应用安全性监视整个会话。</span><span class="sxs-lookup"><span data-stu-id="b3635-181">This way the entire session is monitored by Office 365 Cloud App Security.</span></span>

<span data-ttu-id="b3635-182">条件访问应用程序控件记录通过它路由的每个用户会话的流量日志。</span><span class="sxs-lookup"><span data-stu-id="b3635-182">Conditional Access App Control records the traffic logs of every user session that is routed through it.</span></span> <span data-ttu-id="b3635-183">流量日志包括时间、IP、用户代理、访问的 url 以及已上载和下载的字节数。</span><span class="sxs-lookup"><span data-stu-id="b3635-183">The traffic logs include the time, IP, user agent, URLs visited, and the number of bytes uploaded and downloaded.</span></span> <span data-ttu-id="b3635-184">将对这些日志进行分析, 并将连续报告 " **云应用安全条件访问应用程序" 控件**添加到云发现仪表板中的云发现报告列表中。</span><span class="sxs-lookup"><span data-stu-id="b3635-184">These logs are analyzed and a continuous report, **Cloud App Security Conditional Access App Control**, is added to the list of Cloud Discovery reports in the Cloud Discovery dashboard.</span></span>

### <a name="to-export-these-logs"></a><span data-ttu-id="b3635-185">若要导出这些日志:</span><span class="sxs-lookup"><span data-stu-id="b3635-185">To export these logs:</span></span>

1. <span data-ttu-id="b3635-186">转到 "设置" "cog", 然后单击 " **条件访问应用程序控制**"。</span><span class="sxs-lookup"><span data-stu-id="b3635-186">Go to the settings cog and click **Conditional Access App Control**.</span></span>

2. <span data-ttu-id="b3635-187">在表的右侧, 单击 "导出" 按钮。</span><span class="sxs-lookup"><span data-stu-id="b3635-187">On the right side of the table, click the export button.</span></span><br>!["导出" 按钮](media/image3.png)<br>

3. <span data-ttu-id="b3635-189">选择报告的范围, 然后单击 " **导出**"。</span><span class="sxs-lookup"><span data-stu-id="b3635-189">Select the range of the report and click **Export**.</span></span> <span data-ttu-id="b3635-190">此过程可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="b3635-190">This process may take some time.</span></span>

### <a name="to-download-the-exported-log"></a><span data-ttu-id="b3635-191">下载导出的日志:</span><span class="sxs-lookup"><span data-stu-id="b3635-191">To download the exported log:</span></span>

1. <span data-ttu-id="b3635-192">报告准备就绪后, 转到 " **设置** ", 然后按 " **导出报告**"。</span><span class="sxs-lookup"><span data-stu-id="b3635-192">After the report is ready, go to **Settings** and then **Exported reports**.</span></span>

2. <span data-ttu-id="b3635-193">在表中, 从 **条件访问应用程序控制流量日志** 列表中选择相关报告, 然后单击 "下载"。</span><span class="sxs-lookup"><span data-stu-id="b3635-193">In the table, select the relevant report from the list of **Conditional Access App Control traffic logs** and click download.</span></span><br><span data-ttu-id="b3635-194">![下载按钮](media/image4.png)</span><span class="sxs-lookup"><span data-stu-id="b3635-194">![download button](media/image4.png)</span></span><br>

## <a name="block-all-downloads"></a><span data-ttu-id="b3635-195">阻止所有下载</span><span class="sxs-lookup"><span data-stu-id="b3635-195">Block all downloads</span></span>

<span data-ttu-id="b3635-196">将 **Block** 设置为您希望在云应用安全会话策略中执行的 **操作** 时, 条件访问应用程序控件将阻止用户按照策略的文件筛选器下载文件。</span><span class="sxs-lookup"><span data-stu-id="b3635-196">When **Block** is set as the **Action** you want to take in the Cloud App Security session policy, Conditional Access App Control prevents a user from downloading a file per the policy’s file filters.</span></span> <span data-ttu-id="b3635-197">当用户开始下载时, 每个应用的 Office 365 云应用安全将识别下载事件。</span><span class="sxs-lookup"><span data-stu-id="b3635-197">A download event is recognized by Office 365 Cloud App Security for each app when a user starts a download.</span></span> <span data-ttu-id="b3635-198">条件访问应用程序控制实时 intervenes 阻止其运行。</span><span class="sxs-lookup"><span data-stu-id="b3635-198">Conditional Access App Control intervenes in real time to prevent it from running.</span></span> <span data-ttu-id="b3635-199">当收到用户已启动下载的信号时, 条件 Access 应用程序控件将向用户返回 **下载限制** 的邮件, 并将下载的文件替换为文本文件。</span><span class="sxs-lookup"><span data-stu-id="b3635-199">When the signal is received that a user has initiated a download, Conditional Access App Control returns a **Download restricted** message to the user and replaces the downloaded file with a text file.</span></span> <span data-ttu-id="b3635-200">可以在会话策略中配置和自定义文本文件的邮件。</span><span class="sxs-lookup"><span data-stu-id="b3635-200">The text file's message to the user can be configured and customized from the session policy.</span></span>

## <a name="block-specific-activities"></a><span data-ttu-id="b3635-201">阻止特定活动</span><span class="sxs-lookup"><span data-stu-id="b3635-201">Block specific activities</span></span>

<span data-ttu-id="b3635-202">将 " **阻止活动** " 设置为 " **活动类型**" 时, 可以选择要在特定应用程序中阻止的特定活动。</span><span class="sxs-lookup"><span data-stu-id="b3635-202">When **Block activities** is set as the **Activity type**, you can select specific activities to block in specific apps.</span></span> <span data-ttu-id="b3635-203">将在活动日志中监视和报告来自所选应用的所有活动。</span><span class="sxs-lookup"><span data-stu-id="b3635-203">All activities from selected apps will be monitored and reported in the Activity log.</span></span> <span data-ttu-id="b3635-204">如果选择 " **阻止** " 操作, 则将阻止您选择的特定活动。</span><span class="sxs-lookup"><span data-stu-id="b3635-204">The specific activities you select will be blocked if you select the **Block** action.</span></span> <span data-ttu-id="b3635-205">如果选择 " **测试**操作" 并启用 "通知", 则您选择的特定活动将引发警报。</span><span class="sxs-lookup"><span data-stu-id="b3635-205">The specific activities you selected will raise alerts if you select the **Test** action and have alerts turned on.</span></span>

<span data-ttu-id="b3635-206">**阻止特定的活动** 并将其应用到特定组, 以为您的组织创建全面的只读模式。</span><span class="sxs-lookup"><span data-stu-id="b3635-206">**Block specific activities** and apply it to specific groups to create a comprehensive read-only mode for your organization.</span></span>

## <a name="protect-files-on-download"></a><span data-ttu-id="b3635-207">在下载时保护文件</span><span class="sxs-lookup"><span data-stu-id="b3635-207">Protect files on download</span></span>

<span data-ttu-id="b3635-208">选择 " **阻止活动** " 以阻止特定活动, 您可以使用 **活动类型** 筛选器找到这些活动。</span><span class="sxs-lookup"><span data-stu-id="b3635-208">Select **Block activities** to block specific activities, which you can find using the **Activity type** filter.</span></span> <span data-ttu-id="b3635-209">将监视 (并在活动日志中报告) 所选应用中的所有活动。</span><span class="sxs-lookup"><span data-stu-id="b3635-209">All activities from selected apps will be monitored (and reported in the Activity log).</span></span> <span data-ttu-id="b3635-210">如果选择 " **阻止** " 操作, 则将阻止您选择的特定活动。</span><span class="sxs-lookup"><span data-stu-id="b3635-210">The specific activities you select will be blocked if you select the **Block** action.</span></span> <span data-ttu-id="b3635-211">如果选择 " **测试** 操作" 并启用 "通知", 则您选择的特定活动将引发警报。</span><span class="sxs-lookup"><span data-stu-id="b3635-211">The specific activities you selected will raise alerts if you select the **Test** action and have alerts turned on.</span></span>

<span data-ttu-id="b3635-212">如果将 " **保护** " 设置为在云应用安全会话策略中执行的 **操作** , 则条件访问应用程序控件将根据策略的文件筛选器强制对文件进行标记和后续保护。</span><span class="sxs-lookup"><span data-stu-id="b3635-212">When **Protect** is set as the **Action** to be taken in the Cloud App Security session policy, Conditional Access App Control enforces the labeling and subsequent protection of a file per the policy’s file filters.</span></span> <span data-ttu-id="b3635-213">标签在 Azure 信息保护控制台中配置, 并且必须在标签中选择 " **保护** " 以使其在云应用安全策略中显示为一个选项。</span><span class="sxs-lookup"><span data-stu-id="b3635-213">Labels are configured in the Azure Information Protection console and **Protect** must be selected within the label for it to appear as an option in the Cloud App Security policy.</span></span> <span data-ttu-id="b3635-214">如果选择了标签, 并且下载了符合云应用安全策略条件的文件, 则会在下载时对该文件应用标签和相应的保护 (带有权限)。</span><span class="sxs-lookup"><span data-stu-id="b3635-214">When a label is selected, and a file is downloaded that meets the criteria of the Cloud App Security policy, the label, and corresponding protection (with permissions) is applied to the file upon download.</span></span> <span data-ttu-id="b3635-215">在下载的文件现在受到保护时, 原始文件仍保持原样在云应用程序中。</span><span class="sxs-lookup"><span data-stu-id="b3635-215">The original file remains as-is in the cloud app while the downloaded file is now protected.</span></span> <span data-ttu-id="b3635-216">尝试访问该文件的用户必须满足应用的保护所确定的权限要求。</span><span class="sxs-lookup"><span data-stu-id="b3635-216">Users who try to access the file must meet the permission requirements determined by the protection applied.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3635-217">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b3635-217">Next steps</span></span>

- [<span data-ttu-id="b3635-218">了解 Office 365 中的访问策略云应用安全</span><span class="sxs-lookup"><span data-stu-id="b3635-218">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md)

- [<span data-ttu-id="b3635-219">使用 Azure AD 条件访问应用程序控制功能阻止非托管设备上的下载</span><span class="sxs-lookup"><span data-stu-id="b3635-219">Blocking downloads on unmanaged devices using Azure AD Conditional Access App Control capabilities</span></span>](https://docs.microsoft.com/en-us/cloud-app-security/use-case-proxy-block-session-aad)


---
title: Microsoft 安全功能分数
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何计算详细信息以及安全管理员使用它的方式。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 27a9d137bde0dd23be8824d94a25364f89706563
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852776"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="0e473-104">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="0e473-104">Microsoft Secure Score</span></span>

>[!IMPORTANT]
><span data-ttu-id="0e473-105">一些信息与 prereleased 产品相关, 在正式发布之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="0e473-105">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0e473-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="0e473-106">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="0e473-107">通过 microsoft 365 安全中心中的 Microsoft 安全评分, 可以更好地查看和控制组织的安全状况。</span><span class="sxs-lookup"><span data-stu-id="0e473-107">With Microsoft Secure Score in the Microsoft 365 security center, you can have increased visibility and control over your organization’s security posture.</span></span> <span data-ttu-id="0e473-108">通过集中式仪表板, 可以监视和提高 Microsoft 365 标识、数据、应用程序、设备和基础结构的安全性。</span><span class="sxs-lookup"><span data-stu-id="0e473-108">From a centralized dashboard you can monitor and improve the security for your Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="0e473-109">Microsoft 安全分数为您提供了强健的可视化效果、与其他 Microsoft 产品的集成、与其他公司的分数比较、按类别筛选, 以及更多。</span><span class="sxs-lookup"><span data-stu-id="0e473-109">Microsoft Secure Score gives you robust visualizations, integration with other Microsoft products, comparison of your score with other companies, filtering by category, and much more.</span></span> <span data-ttu-id="0e473-110">使用此工具, 您可以在组织内完成安全改进操作并跟踪分数的历史记录。</span><span class="sxs-lookup"><span data-stu-id="0e473-110">With the tool, you can complete security improvement actions within your organization and track the history of your score.</span></span> <span data-ttu-id="0e473-111">分数还可以反映第三方解决方案解决建议的改进操作的时间。</span><span class="sxs-lookup"><span data-stu-id="0e473-111">The score can also reflect when third-party solutions have addressed recommended improvement actions.</span></span>  

## <a name="how-it-works"></a><span data-ttu-id="0e473-112">运作方式</span><span class="sxs-lookup"><span data-stu-id="0e473-112">How it works</span></span>

<span data-ttu-id="0e473-113">为您提供配置推荐安全功能、执行与安全相关的任务 (如查看报告) 或使用第三方应用程序或软件解决改进操作的相关积分。</span><span class="sxs-lookup"><span data-stu-id="0e473-113">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="0e473-114">某些操作在部分完成时被评分, 例如为您的用户启用多重身份验证 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="0e473-114">Some actions are scored for partial completion, like enabling multi-factor authentication (MFA) for your users.</span></span> <span data-ttu-id="0e473-115">安全应始终平衡可用性, 而不是每个建议都适用于您的环境。</span><span class="sxs-lookup"><span data-stu-id="0e473-115">Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="0e473-116">所需权限</span><span class="sxs-lookup"><span data-stu-id="0e473-116">Required permissions</span></span>

<span data-ttu-id="0e473-117">目前, 若要查看 Microsoft 安全分数, 您必须在 Azure Active Directory 中分配以下角色之一:</span><span class="sxs-lookup"><span data-stu-id="0e473-117">Currently, to view Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory:</span></span>

* <span data-ttu-id="0e473-118">全局管理员</span><span class="sxs-lookup"><span data-stu-id="0e473-118">Global Administrator</span></span>
* <span data-ttu-id="0e473-119">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="0e473-119">Security Administrator</span></span>
* <span data-ttu-id="0e473-120">安全读者</span><span class="sxs-lookup"><span data-stu-id="0e473-120">Security Reader</span></span>

## <a name="rich-experiences--additional-security-recommendations"></a><span data-ttu-id="0e473-121">& 其他安全建议的丰富体验</span><span class="sxs-lookup"><span data-stu-id="0e473-121">Rich experiences & additional security recommendations</span></span>

<span data-ttu-id="0e473-122">在 Microsoft 安全分数中, 我们已从 Azure AD、Intune 和云应用程序安全性中添加了建议, 其中包含来自 Azure 安全中心的建议和 Microsoft Defender ATP 即将推出的建议。</span><span class="sxs-lookup"><span data-stu-id="0e473-122">In Microsoft Secure Score, we’ve added recommendations from Azure AD, Intune, and Cloud App Security, with recommendations from Azure Security Center and Microsoft Defender ATP coming soon.</span></span> <span data-ttu-id="0e473-123">我们还添加了更为多的 Office 365 安全建议。</span><span class="sxs-lookup"><span data-stu-id="0e473-123">We've also added even more Office 365 security recommendations.</span></span> <span data-ttu-id="0e473-124">通过其他见解并更好地了解更广泛的一组 Microsoft 产品和服务, 您可以放心地报告有关组织安全运行状况的管理。</span><span class="sxs-lookup"><span data-stu-id="0e473-124">With additional insights and more visibility into a broader set of Microsoft products and services, you can feel confident reporting up to management about your organization’s security health.</span></span> <span data-ttu-id="0e473-125">您还可以使用[Microsoft GRAPH API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)获取成绩。</span><span class="sxs-lookup"><span data-stu-id="0e473-125">You can also get your score using the [Microsoft Graph API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta).</span></span>

<span data-ttu-id="0e473-126">为了帮助您更快地了解所需的信息, Microsoft 建议已分成组:</span><span class="sxs-lookup"><span data-stu-id="0e473-126">To help you the information you need more quickly, Microsoft recommendations are organized into groups:</span></span>

* <span data-ttu-id="0e473-127">标识 (Azure AD 帐户和角色的保护状态)</span><span class="sxs-lookup"><span data-stu-id="0e473-127">Identity (protection state of your Azure AD accounts and roles)</span></span>
* <span data-ttu-id="0e473-128">数据 (Office 365 文档的保护状态)</span><span class="sxs-lookup"><span data-stu-id="0e473-128">Data (protection state of your Office 365 documents)</span></span>
* <span data-ttu-id="0e473-129">设备 (设备的保护状态;即将推出 Microsoft Defender ATP 的改进操作)</span><span class="sxs-lookup"><span data-stu-id="0e473-129">Device (protection state of your devices; Microsoft Defender ATP improvement actions coming soon)</span></span>
* <span data-ttu-id="0e473-130">应用 (电子邮件和云应用的保护状态)</span><span class="sxs-lookup"><span data-stu-id="0e473-130">App (protection state of your email and cloud apps)</span></span>
* <span data-ttu-id="0e473-131">基础结构 (Azure 资源的保护状态; 即将推出)</span><span class="sxs-lookup"><span data-stu-id="0e473-131">Infrastructure (protection state of your Azure resources; coming soon)</span></span>

<span data-ttu-id="0e473-132">在 "Microsoft 安全分数概述" 页中, 您可以看到在这些组之间如何拆分点以及哪些点可用。</span><span class="sxs-lookup"><span data-stu-id="0e473-132">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="0e473-133">[! 注意] 概述页面也是获取总分和基准对比的安全分数的历史趋势的完整视图的位置, 以及可采取的优先改进措施以提高成绩。</span><span class="sxs-lookup"><span data-stu-id="0e473-133">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span> <span data-ttu-id="0e473-134">您可以使用此数据进行操作, 并对安全状态进行重大差别。</span><span class="sxs-lookup"><span data-stu-id="0e473-134">You can use this data to act and make big differences in your security posture.</span></span>  

<span data-ttu-id="0e473-135">![M365 主页](./media/secure-score/homepage-original.png)
*图 1: Microsoft 安全分数概述页面*</span><span class="sxs-lookup"><span data-stu-id="0e473-135">![M365 homepage](./media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="0e473-136">采取行动以提高成绩</span><span class="sxs-lookup"><span data-stu-id="0e473-136">Take action to improve your score</span></span>

<span data-ttu-id="0e473-137">"改进操作" 选项卡列出了适用于你的租户的所有安全建议及其状态 (已完成、未完成、已通过第三方解决, 并将被忽略)。</span><span class="sxs-lookup"><span data-stu-id="0e473-137">The improvement actions tab lists all the security recommendations applicable to your tenant along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="0e473-138">您可以搜索、筛选和分组所有控件。</span><span class="sxs-lookup"><span data-stu-id="0e473-138">You can search, filter, and group all the controls.</span></span>  <span data-ttu-id="0e473-139">排名基于 Microsoft 对安全价值和努力完成的评估。</span><span class="sxs-lookup"><span data-stu-id="0e473-139">Ranking is based on Microsoft’s evaluation of both security value and effort to complete.</span></span>

<span data-ttu-id="0e473-140">Microsoft 安全分数不会跟踪标记为 [未评分] 的操作。</span><span class="sxs-lookup"><span data-stu-id="0e473-140">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="0e473-141">你仍可以采取措施, 但完成这些操作不会影响你的分数。</span><span class="sxs-lookup"><span data-stu-id="0e473-141">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="0e473-142">如果某个操作在将来被 Microsoft 安全得分跟踪, 并且您已完成该操作, 则安全得分将自动反映所做的更改。</span><span class="sxs-lookup"><span data-stu-id="0e473-142">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="0e473-143">当您单击 "改进" 操作时, 将显示 "飞出"。</span><span class="sxs-lookup"><span data-stu-id="0e473-143">When you click on an improvement action, a fly out appears.</span></span> <span data-ttu-id="0e473-144">若要完成此操作, 您有几个选项:</span><span class="sxs-lookup"><span data-stu-id="0e473-144">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="0e473-145">选择 "**查看设置**" 以转到配置屏幕并进行更改。</span><span class="sxs-lookup"><span data-stu-id="0e473-145">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="0e473-146">然后, 您将获得该操作所需要的要点, 在飞出的顶部可见。点可能需要长达24小时才能更新。</span><span class="sxs-lookup"><span data-stu-id="0e473-146">You will then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="0e473-147">选择 "**通过第三方解决**", 因为改进操作已由第三方应用程序或软件解决。</span><span class="sxs-lookup"><span data-stu-id="0e473-147">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="0e473-148">你将获得该操作所需要的要点, 因此你的安全得分更好地反映了你的总体安全状况。</span><span class="sxs-lookup"><span data-stu-id="0e473-148">You will gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="0e473-149">如果第三方不再涵盖该控件, 则可以将 "改进" 操作标记为 "不完成"。</span><span class="sxs-lookup"><span data-stu-id="0e473-149">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="0e473-150">请注意, 如果将改进操作标记为通过第三方解决, 则 Microsoft 将无法了解是否符合评分要求。</span><span class="sxs-lookup"><span data-stu-id="0e473-150">Please keep in mind, Microsoft will have no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="0e473-151">选择 "**忽略**", 因为您已决定接受风险而不执行改进操作。</span><span class="sxs-lookup"><span data-stu-id="0e473-151">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="0e473-152">忽略 "改进" 操作后, 您可以达到的安全分数点总数将减少。</span><span class="sxs-lookup"><span data-stu-id="0e473-152">Once you ignore an improvement action, the total number of secure score points you can achieve will be reduced.</span></span> <span data-ttu-id="0e473-153">您可以在历史记录中查看此操作, 也可以随时撤消。</span><span class="sxs-lookup"><span data-stu-id="0e473-153">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="0e473-154">选择 "**审阅**", 因为改进操作要求您定期查看环境的一部分以获取和保留点。</span><span class="sxs-lookup"><span data-stu-id="0e473-154">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="0e473-155">例如, 应每周查看邮箱转发规则, 以确保不会从您的网络中泄露数据。</span><span class="sxs-lookup"><span data-stu-id="0e473-155">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="0e473-156">您无需进行任何更改, 但需要执行操作。</span><span class="sxs-lookup"><span data-stu-id="0e473-156">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="0e473-157">如果您定期查看规则, 您将收到要点。</span><span class="sxs-lookup"><span data-stu-id="0e473-157">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="0e473-158">如果不是, 分数将减少。</span><span class="sxs-lookup"><span data-stu-id="0e473-158">If not, the score will be reduced.</span></span>

![M365 主页](./media/secure-score/secure-score1x450.png) ![M365 主页](./media/secure-score/secure-score2x450.png)

<span data-ttu-id="0e473-161">*图 2 & 3: 改进操作 flyouts*</span><span class="sxs-lookup"><span data-stu-id="0e473-161">*Figures 2 & 3: Improvement action flyouts*</span></span>

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="0e473-162">随着时间的推移监视改进</span><span class="sxs-lookup"><span data-stu-id="0e473-162">Monitor improvements over time</span></span>

<span data-ttu-id="0e473-163">您可以在 "**历史记录**" 选项卡中查看组织的分数在一段时间内的关系图。此视图包含全局平均值、行业平均和相似的座位计数, 以及在所选时间范围内执行的所有操作。</span><span class="sxs-lookup"><span data-stu-id="0e473-163">You can view a graph of your organization's score over time in the **History** tab. This view includes the global average, industry average, and similar seat count, along with all the actions taken in the selected time range.</span></span> <span data-ttu-id="0e473-164">您还可以自定义日期范围并按类别进行筛选。</span><span class="sxs-lookup"><span data-stu-id="0e473-164">You can also customize a date range and filter by category.</span></span>

<span data-ttu-id="0e473-165">分数每日计算一次 (大约 1:00 AM PST)。</span><span class="sxs-lookup"><span data-stu-id="0e473-165">The score is calculated once per day (around 1:00 AM PST).</span></span> <span data-ttu-id="0e473-166">如果对已衡量的操作进行了更改, 则分数将自动更新到下一天。</span><span class="sxs-lookup"><span data-stu-id="0e473-166">If you make a change to a measured action, the score will automatically update the next day.</span></span> <span data-ttu-id="0e473-167">另外, 请务必注意, 其他一些门户会显示 Microsoft 安全分数的一部分 (如 Microsoft Defender 安全中心)。</span><span class="sxs-lookup"><span data-stu-id="0e473-167">It is also important to note that some other portals show parts of the Microsoft Secure Score (like Microsoft Defender Security Center).</span></span> <span data-ttu-id="0e473-168">如果你完成了改进操作, 这些门户中的得分增加了, 则在 Microsoft 365 安全中心中显示更新的分数可能需要长达24小时。</span><span class="sxs-lookup"><span data-stu-id="0e473-168">If you complete an improvement action and the score is increased in those portals, it may take up to 24 hours for the updated score to display in Microsoft 365 security center.</span></span>  

## <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="0e473-169">如何对改进行动进行评分</span><span class="sxs-lookup"><span data-stu-id="0e473-169">How improvement actions are scored</span></span>

<span data-ttu-id="0e473-170">大多数都是以二进制方式进行评分-如果实施改进操作 (如创建新策略或打开特定设置), 您将获得 100% 的数据点。</span><span class="sxs-lookup"><span data-stu-id="0e473-170">Most are scored in a binary fashion - you get 100% of the points if you implement the improvement action, like creating a new policy or turning on a specific setting.</span></span> <span data-ttu-id="0e473-171">对于其他改进操作, 点作为总配置的百分比提供。</span><span class="sxs-lookup"><span data-stu-id="0e473-171">For other improvement actions, points are given as a percentage of the total configuration.</span></span> <span data-ttu-id="0e473-172">例如, 如果您使用多重身份验证保护您的所有用户, 并且仅有 5% 以上的用户受到保护, 则 "改进" 操作将获得30个点。您可以获得2个点 (5 100 个受保护的/100 总数 \* 30 max pt = 2) 的部分分数。 pt 部分分数)。</span><span class="sxs-lookup"><span data-stu-id="0e473-172">For example, if the improvement action states you’ll get 30 points if you protect all your users with multi-factor authentication and you only have 5 of 100 total users protected, you would be given a partial score of around 2 points (5 protected / 100 total \* 30 max pts = 2 pts partial score).</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="0e473-173">风险感知</span><span class="sxs-lookup"><span data-stu-id="0e473-173">Risk awareness</span></span>

<span data-ttu-id="0e473-174">Microsoft 安全分数是基于系统配置、用户行为和其他安全相关度量的安全状态的数字摘要;它并不是对系统或数据受到破坏的可能性的绝对度量。</span><span class="sxs-lookup"><span data-stu-id="0e473-174">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="0e473-175">相反, 它表示您在 Microsoft 环境中已采用安全控制的程度, 这有助于抵消受到破坏的风险。</span><span class="sxs-lookup"><span data-stu-id="0e473-175">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="0e473-176">无在线服务完全不受安全破坏, 并且安全分数不应以任何方式解释为保证安全。</span><span class="sxs-lookup"><span data-stu-id="0e473-176">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="0e473-177">我们希望收到你的来信</span><span class="sxs-lookup"><span data-stu-id="0e473-177">We want to hear from you</span></span>

<span data-ttu-id="0e473-178">如果你有任何问题, 请通过在[安全、隐私 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社区中发布来告知我们。</span><span class="sxs-lookup"><span data-stu-id="0e473-178">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="0e473-179">我们正在监视社区, 并将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="0e473-179">We're monitoring the community and will provide help.</span></span>

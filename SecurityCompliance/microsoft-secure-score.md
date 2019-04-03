---
title: Microsoft 安全功能分数
description: 介绍 Microsoft 365 安全分数、如何计算详细信息以及安全管理员可以使用它的方式。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: fa76e2edd3f66595a47fb511881f15c07b441c77
ms.sourcegitcommit: 8213c353954b92f5c3979bee4aa049da0fd28a18
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2019
ms.locfileid: "31043243"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="a9791-104">Microsoft 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="a9791-104">Microsoft Secure Score</span></span>

<span data-ttu-id="a9791-105">通过 microsoft 365 安全中心中的 microsoft 安全评分, 可以更好地查看和控制组织的安全状况。</span><span class="sxs-lookup"><span data-stu-id="a9791-105">With Microsoft Secure Score in the Microsoft 365 security center, you can have increased visibility and control over your organization’s security posture.</span></span> <span data-ttu-id="a9791-106">通过集中式仪表板, 可以监视和提高 Microsoft 365 标识、数据、应用程序、设备和基础结构的安全性。</span><span class="sxs-lookup"><span data-stu-id="a9791-106">From a centralized dashboard you can monitor and improve the security for your Microsoft 365 identities, data, apps, devices, and infrastructure.</span></span>

<span data-ttu-id="a9791-107">Microsoft 安全分数为您提供了强健的可视化效果、与其他 Microsoft 产品的集成、与其他公司的分数比较、按类别筛选, 以及更多。</span><span class="sxs-lookup"><span data-stu-id="a9791-107">Microsoft Secure Score gives you robust visualizations, integration with other Microsoft products, comparison of your score with other companies, filtering by category, and much more.</span></span> <span data-ttu-id="a9791-108">使用此工具, 您可以在组织内完成安全改进操作并跟踪分数的历史记录。</span><span class="sxs-lookup"><span data-stu-id="a9791-108">With the tool, you can complete security improvement actions within your organization and track the history of your score.</span></span> <span data-ttu-id="a9791-109">分数还可以反映第三方解决方案解决建议的改进操作的时间。</span><span class="sxs-lookup"><span data-stu-id="a9791-109">The score can also reflect when third-party solutions have addressed recommended improvement actions.</span></span>  

## <a name="how-it-works"></a><span data-ttu-id="a9791-110">工作原理</span><span class="sxs-lookup"><span data-stu-id="a9791-110">How it works</span></span>

<span data-ttu-id="a9791-111">为您提供配置推荐安全功能、执行与安全相关的任务 (如查看报告) 或使用第三方应用程序或软件解决改进操作的相关积分。</span><span class="sxs-lookup"><span data-stu-id="a9791-111">You are given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing the improvement action with a third-party application or software.</span></span> <span data-ttu-id="a9791-112">某些操作在部分完成时被评分, 例如为您的用户启用多重身份验证 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="a9791-112">Some actions are scored for partial completion, like enabling multi-factor authentication (MFA) for your users.</span></span> <span data-ttu-id="a9791-113">安全应始终平衡可用性, 而不是每个建议都适用于您的环境。</span><span class="sxs-lookup"><span data-stu-id="a9791-113">Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="a9791-114">必需的权限</span><span class="sxs-lookup"><span data-stu-id="a9791-114">Required permissions</span></span>

<span data-ttu-id="a9791-115">目前, 若要查看 Microsoft 安全分数, 您必须在 Azure Active Directory 中分配以下角色之一:</span><span class="sxs-lookup"><span data-stu-id="a9791-115">Currently, to view Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory:</span></span>

* <span data-ttu-id="a9791-116">全局管理员</span><span class="sxs-lookup"><span data-stu-id="a9791-116">Global Administrator</span></span>
* <span data-ttu-id="a9791-117">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="a9791-117">Security Administrator</span></span>
* <span data-ttu-id="a9791-118">安全读者</span><span class="sxs-lookup"><span data-stu-id="a9791-118">Security Reader</span></span>

## <a name="rich-experiences--additional-security-recommendations"></a><span data-ttu-id="a9791-119">丰富的体验 & 其他安全建议</span><span class="sxs-lookup"><span data-stu-id="a9791-119">Rich experiences & additional security recommendations</span></span>

<span data-ttu-id="a9791-120">在 Microsoft 安全分数中, 我们已从 azure AD、Intune 和云应用程序安全性中添加了建议, 其中包含来自 azure 安全中心和 Windows Defender ATP 的建议。</span><span class="sxs-lookup"><span data-stu-id="a9791-120">In Microsoft Secure Score, we’ve added recommendations from Azure AD, Intune, and Cloud App Security, with recommendations from Azure Security Center and Windows Defender ATP coming soon.</span></span> <span data-ttu-id="a9791-121">我们还添加了更为多的 Office 365 安全建议。</span><span class="sxs-lookup"><span data-stu-id="a9791-121">We've also added even more Office 365 security recommendations.</span></span> <span data-ttu-id="a9791-122">通过其他见解并更好地了解更广泛的一组 Microsoft 产品和服务, 您可以放心地报告有关组织安全运行状况的管理。</span><span class="sxs-lookup"><span data-stu-id="a9791-122">With additional insights and more visibility into a broader set of Microsoft products and services, you can feel confident reporting up to management about your organization’s security health.</span></span> <span data-ttu-id="a9791-123">您还可以使用[Microsoft Graph API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta)获取成绩。</span><span class="sxs-lookup"><span data-stu-id="a9791-123">You can also get your score using the [Microsoft Graph API](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta).</span></span>

<span data-ttu-id="a9791-124">为了帮助您更快地了解所需的信息, Microsoft 建议已分成组:</span><span class="sxs-lookup"><span data-stu-id="a9791-124">To help you the information you need more quickly, Microsoft recommendations are organized into groups:</span></span>

* <span data-ttu-id="a9791-125">标识 (Azure AD 帐户和角色的保护状态)</span><span class="sxs-lookup"><span data-stu-id="a9791-125">Identity (protection state of your Azure AD accounts and roles)</span></span>
* <span data-ttu-id="a9791-126">数据 (Office 365 文档的保护状态)</span><span class="sxs-lookup"><span data-stu-id="a9791-126">Data (protection state of your Office 365 documents)</span></span>
* <span data-ttu-id="a9791-127">设备 (设备的保护状态;即将推出 Windows Defender ATP 改进操作)</span><span class="sxs-lookup"><span data-stu-id="a9791-127">Device (protection state of your devices; Windows Defender ATP improvement actions coming soon)</span></span>
* <span data-ttu-id="a9791-128">应用 (电子邮件和云应用的保护状态)</span><span class="sxs-lookup"><span data-stu-id="a9791-128">App (protection state of your email and cloud apps)</span></span>
* <span data-ttu-id="a9791-129">基础结构 (Azure 资源的保护状态; 即将推出)</span><span class="sxs-lookup"><span data-stu-id="a9791-129">Infrastructure (protection state of your Azure resources; coming soon)</span></span>

<span data-ttu-id="a9791-130">在 "Microsoft 安全分数概述" 页中, 您可以看到在这些组之间如何拆分点以及哪些点可用。</span><span class="sxs-lookup"><span data-stu-id="a9791-130">In the Microsoft Secure Score overview page, you can see how points are split between these groups and what points are available.</span></span> <span data-ttu-id="a9791-131">[! 注意] 概述页面也是获取总分和基准对比的安全分数的历史趋势的完整视图的位置, 以及可采取的优先改进措施以提高成绩。</span><span class="sxs-lookup"><span data-stu-id="a9791-131">The overview page is also the place to get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span> <span data-ttu-id="a9791-132">您可以使用此数据进行操作, 并对安全状态进行重大差别。</span><span class="sxs-lookup"><span data-stu-id="a9791-132">You can use this data to act and make big differences in your security posture.</span></span>  

![<span data-ttu-id="a9791-133">M365 主页](./media/secure-score/homepage-original.png)
*图 1: Microsoft 安全分数概述页面*</span><span class="sxs-lookup"><span data-stu-id="a9791-133">M365 homepage](./media/secure-score/homepage-original.png)
*Figure 1: Microsoft Secure Score overview page*</span></span>

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="a9791-134">采取行动以提高成绩</span><span class="sxs-lookup"><span data-stu-id="a9791-134">Take action to improve your score</span></span>

<span data-ttu-id="a9791-135">"改进操作" 选项卡列出了适用于你的租户的所有安全建议及其状态 (已完成、未完成、已通过第三方解决, 并将被忽略)。</span><span class="sxs-lookup"><span data-stu-id="a9791-135">The improvement actions tab lists all the security recommendations applicable to your tenant along with their status (completed, not completed, resolved through third party, and ignored).</span></span> <span data-ttu-id="a9791-136">您可以搜索、筛选和分组所有控件。</span><span class="sxs-lookup"><span data-stu-id="a9791-136">You can search, filter, and group all the controls.</span></span>  <span data-ttu-id="a9791-137">排名基于 Microsoft 对安全价值和努力完成的评估。</span><span class="sxs-lookup"><span data-stu-id="a9791-137">Ranking is based on Microsoft’s evaluation of both security value and effort to complete.</span></span>

<span data-ttu-id="a9791-138">Microsoft 安全分数不会跟踪标记为 [未评分] 的操作。</span><span class="sxs-lookup"><span data-stu-id="a9791-138">Actions labeled as [Not Scored] are not tracked by Microsoft Secure Score.</span></span> <span data-ttu-id="a9791-139">你仍可以采取措施, 但完成这些操作不会影响你的分数。</span><span class="sxs-lookup"><span data-stu-id="a9791-139">You can still take action but completing them will not affect your score.</span></span> <span data-ttu-id="a9791-140">如果某个操作在将来被 Microsoft 安全得分跟踪, 并且您已完成该操作, 则安全得分将自动反映所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a9791-140">If an action becomes tracked by Microsoft Secure Score in the future and you have already completed it, your secure score will automatically reflect the change.</span></span>

<span data-ttu-id="a9791-141">当您单击 "改进" 操作时, 将显示 "飞出"。</span><span class="sxs-lookup"><span data-stu-id="a9791-141">When you click on an improvement action, a fly out appears.</span></span> <span data-ttu-id="a9791-142">若要完成此操作, 您有几个选项:</span><span class="sxs-lookup"><span data-stu-id="a9791-142">To complete the action, you have a few options:</span></span>

1. <span data-ttu-id="a9791-143">选择 "**查看设置**" 以转到配置屏幕并进行更改。</span><span class="sxs-lookup"><span data-stu-id="a9791-143">Select **View settings** to go the configuration screen and make the change.</span></span> <span data-ttu-id="a9791-144">然后, 您将获得该操作所需要的要点, 在飞出的顶部可见。点可能需要长达24小时才能更新。</span><span class="sxs-lookup"><span data-stu-id="a9791-144">You will then gain the points that the action is worth, visible at the top of the fly out. Points may take up to 24 hours to update.</span></span>

2. <span data-ttu-id="a9791-145">选择 "**通过第三方解决**", 因为改进操作已由第三方应用程序或软件解决。</span><span class="sxs-lookup"><span data-stu-id="a9791-145">Select **Resolve through third party** because the improvement action has already been addressed by a third-party application or software.</span></span> <span data-ttu-id="a9791-146">你将获得该操作所需要的要点, 因此你的安全得分更好地反映了你的总体安全状况。</span><span class="sxs-lookup"><span data-stu-id="a9791-146">You will gain the points that the action is worth, so your secure score better reflects your overall security posture.</span></span> <span data-ttu-id="a9791-147">如果第三方不再涵盖该控件, 则可以将 "改进" 操作标记为 "不完成"。</span><span class="sxs-lookup"><span data-stu-id="a9791-147">If a third party no longer covers the control, you can mark the improvement action as not complete.</span></span> <span data-ttu-id="a9791-148">请注意, 如果将改进操作标记为通过第三方解决, 则 Microsoft 将无法了解是否符合评分要求。</span><span class="sxs-lookup"><span data-stu-id="a9791-148">Please keep in mind, Microsoft will have no visibility into whether the score requirements have been met if the improvement action is marked as resolved through third party.</span></span>

3. <span data-ttu-id="a9791-149">选择 "**忽略**", 因为您已决定接受风险而不执行改进操作。</span><span class="sxs-lookup"><span data-stu-id="a9791-149">Select **Ignore** because you have decided to accept the risk and not enact the improvement action.</span></span> <span data-ttu-id="a9791-150">忽略 "改进" 操作后, 您可以达到的安全分数点总数将减少。</span><span class="sxs-lookup"><span data-stu-id="a9791-150">Once you ignore an improvement action, the total number of secure score points you can achieve will be reduced.</span></span> <span data-ttu-id="a9791-151">您可以在历史记录中查看此操作, 也可以随时撤消。</span><span class="sxs-lookup"><span data-stu-id="a9791-151">You can view this action in history or undo it at any time.</span></span>

4. <span data-ttu-id="a9791-152">选择 "**审阅**", 因为改进操作要求您定期查看环境的一部分以获取和保留点。</span><span class="sxs-lookup"><span data-stu-id="a9791-152">Select **Review** because the improvement action requires you to regularly review a part of your environment to gain and retain points.</span></span> <span data-ttu-id="a9791-153">例如, 应每周查看邮箱转发规则, 以确保不会从您的网络中泄露数据。</span><span class="sxs-lookup"><span data-stu-id="a9791-153">For example, mailbox forwarding rules should be reviewed on a weekly basis to make sure data is not being exfiltrated from your network.</span></span> <span data-ttu-id="a9791-154">您无需进行任何更改, 但需要执行操作。</span><span class="sxs-lookup"><span data-stu-id="a9791-154">You do not need to make any changes, but an action will need to be performed.</span></span> <span data-ttu-id="a9791-155">如果您定期查看规则, 您将收到要点。</span><span class="sxs-lookup"><span data-stu-id="a9791-155">If you regularly review the rules, you will receive the points.</span></span> <span data-ttu-id="a9791-156">如果不是, 分数将减少。</span><span class="sxs-lookup"><span data-stu-id="a9791-156">If not, the score will be reduced.</span></span>

![M365 主页](./media/secure-score/secure-score1x450.png) ![M365 主页](./media/secure-score/secure-score2x450.png)

*<span data-ttu-id="a9791-159">图 2 & 3: 改进操作 flyouts</span><span class="sxs-lookup"><span data-stu-id="a9791-159">Figures 2 & 3: Improvement action flyouts</span></span>*

## <a name="monitor-improvements-over-time"></a><span data-ttu-id="a9791-160">随着时间的推移监视改进</span><span class="sxs-lookup"><span data-stu-id="a9791-160">Monitor improvements over time</span></span>

<span data-ttu-id="a9791-161">您可以在 "**历史记录**" 选项卡中查看组织的分数在一段时间内的关系图。此视图包含全局平均值、行业平均和相似的座位计数, 以及在所选时间范围内执行的所有操作。</span><span class="sxs-lookup"><span data-stu-id="a9791-161">You can view a graph of your organization's score over time in the **History** tab. This view includes the global average, industry average, and similar seat count, along with all the actions taken in the selected time range.</span></span> <span data-ttu-id="a9791-162">您还可以自定义日期范围并按类别进行筛选。</span><span class="sxs-lookup"><span data-stu-id="a9791-162">You can also customize a date range and filter by category.</span></span>

<span data-ttu-id="a9791-163">分数每日计算一次 (大约 1:00 AM PST)。</span><span class="sxs-lookup"><span data-stu-id="a9791-163">The score is calculated once per day (around 1:00 AM PST).</span></span> <span data-ttu-id="a9791-164">如果对已衡量的操作进行了更改, 则分数将自动更新到下一天。</span><span class="sxs-lookup"><span data-stu-id="a9791-164">If you make a change to a measured action, the score will automatically update the next day.</span></span> <span data-ttu-id="a9791-165">另外, 请务必注意, 其他一些门户会显示 Microsoft 安全分数的一部分 (如 Windows Defender 安全中心)。</span><span class="sxs-lookup"><span data-stu-id="a9791-165">It is also important to note that some other portals show parts of the Microsoft Secure Score (like Windows Defender Security Center).</span></span> <span data-ttu-id="a9791-166">如果你完成了改进操作, 这些门户中的得分增加了, 则在 Microsoft 365 安全中心中显示更新的分数可能需要长达24小时。</span><span class="sxs-lookup"><span data-stu-id="a9791-166">If you complete an improvement action and the score is increased in those portals, it may take up to 24 hours for the updated score to display in Microsoft 365 security center.</span></span>  

## <a name="risk-awareness"></a><span data-ttu-id="a9791-167">风险感知</span><span class="sxs-lookup"><span data-stu-id="a9791-167">Risk awareness</span></span>

<span data-ttu-id="a9791-168">Microsoft 安全分数是基于系统配置、用户行为和其他安全相关度量的安全状态的数字摘要;它并不是对系统或数据受到破坏的可能性的绝对度量。</span><span class="sxs-lookup"><span data-stu-id="a9791-168">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior and other security related measurements; it is not an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="a9791-169">相反, 它表示您在 Microsoft 环境中已采用安全控制的程度, 这有助于抵消受到破坏的风险。</span><span class="sxs-lookup"><span data-stu-id="a9791-169">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment which can help offset the risk of being breached.</span></span> <span data-ttu-id="a9791-170">无在线服务完全不受安全破坏, 并且安全分数不应以任何方式解释为保证安全。</span><span class="sxs-lookup"><span data-stu-id="a9791-170">No online service is completely immune from security breaches, and secure score should not be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="a9791-171">我们希望收到你的来信</span><span class="sxs-lookup"><span data-stu-id="a9791-171">We want to hear from you</span></span>

<span data-ttu-id="a9791-172">如果您有任何问题, 请通过在[Security、隐私权 & 合规](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)社区中发布来告知我们。</span><span class="sxs-lookup"><span data-stu-id="a9791-172">If you have any issues, please let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="a9791-173">我们正在监视社区, 并将提供帮助。</span><span class="sxs-lookup"><span data-stu-id="a9791-173">We're monitoring the community and will provide help.</span></span>

---
title: 当邮件为红色标记时, 如何组合策略和保护
description: 当电子邮件标记为恶意软件、垃圾邮件、高可信度垃圾邮件、网络钓鱼, 以及 EOP 和/或 ATP 时, 将应用哪些策略以及要采取的操作。
keywords: security、恶意软件、Microsoft 365、M365、security center、ATP、Windows Defender ATP、Office 365 atp、Azure atp
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 03/26/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 7aa0f89eed379273cb069cd65c083749a9552e91
ms.sourcegitcommit: a79eb9907759d4cd849c3f948695a9ff890b19bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "30926461"
---
# <a name="what-policy-applies-when-multiple-protection-methods-and-detection-scans-run-on-your-email"></a><span data-ttu-id="34b9f-104">在您的电子邮件上运行多个保护方法和检测扫描时应用什么策略</span><span class="sxs-lookup"><span data-stu-id="34b9f-104">What policy applies when multiple protection methods and detection scans run on your email</span></span>

<span data-ttu-id="34b9f-105">您的传入邮件可能会被多个保护形式 (例如 *, EOP 和*ATP) 标记, 以及多个检测扫描 (例如垃圾邮件*和*网络钓鱼)。</span><span class="sxs-lookup"><span data-stu-id="34b9f-105">Potentially, your incoming mail may be flagged by multiple forms of protection (for example both EOP *and* ATP), and multiple detection scans (such as spam *and* phishing).</span></span> <span data-ttu-id="34b9f-106">这是因为 atp 客户有 atp 反网络钓鱼策略, 并为 EOP 客户提供了 EOP 反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="34b9f-106">This is possible because there are ATP Anti-phishing policies for ATP customers, and EOP Anti-phishing policies for EOP customers.</span></span> <span data-ttu-id="34b9f-107">这也意味着邮件可能会针对恶意软件、网络钓鱼和用户模拟浏览多个检测扫描。</span><span class="sxs-lookup"><span data-stu-id="34b9f-107">This also means the message may navigate multiple detection scans for malware, phishing, and user-impersonation, for example.</span></span> <span data-ttu-id="34b9f-108">对于所有此活动, 可能会对应用的策略产生一些困惑。</span><span class="sxs-lookup"><span data-stu-id="34b9f-108">Given all this activity, there may be some confusion as to which policy applies.</span></span>

<span data-ttu-id="34b9f-109">通常情况下, 应用于邮件的策略在**CAT (Category)** 属性中的**X-Forefront-反垃圾邮件报告**标头中进行标识。</span><span class="sxs-lookup"><span data-stu-id="34b9f-109">In general, the policy applied to a message is identified in the **X-Forefront-Antispam-Report** header in the **CAT (Category)** property.</span></span> <span data-ttu-id="34b9f-110">如果您有多个反网络钓鱼策略, 则会应用最高优先级的策略。</span><span class="sxs-lookup"><span data-stu-id="34b9f-110">If you have multiple Anti-phishing policies, the one at the highest priority will apply.</span></span>

<span data-ttu-id="34b9f-111">以下策略适用于_所有组织_。</span><span class="sxs-lookup"><span data-stu-id="34b9f-111">The Policies below apply to _all organizations_.</span></span>

|<span data-ttu-id="34b9f-112">优先级</span><span class="sxs-lookup"><span data-stu-id="34b9f-112">Priority</span></span> |<span data-ttu-id="34b9f-113">策略</span><span class="sxs-lookup"><span data-stu-id="34b9f-113">Policy</span></span>  |<span data-ttu-id="34b9f-114">类别</span><span class="sxs-lookup"><span data-stu-id="34b9f-114">Category</span></span>  |<span data-ttu-id="34b9f-115">托管</span><span class="sxs-lookup"><span data-stu-id="34b9f-115">Where Managed</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="34b9f-116">1</span><span class="sxs-lookup"><span data-stu-id="34b9f-116">1</span></span>     | <span data-ttu-id="34b9f-117">恶意软件</span><span class="sxs-lookup"><span data-stu-id="34b9f-117">Malware</span></span>      | <span data-ttu-id="34b9f-118">MALW</span><span class="sxs-lookup"><span data-stu-id="34b9f-118">MALW</span></span>      | <span data-ttu-id="34b9f-119">恶意软件策略</span><span class="sxs-lookup"><span data-stu-id="34b9f-119">Malware policy</span></span>   |
|<span data-ttu-id="34b9f-120">双面</span><span class="sxs-lookup"><span data-stu-id="34b9f-120">2</span></span>     | <span data-ttu-id="34b9f-121">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="34b9f-121">Phishing</span></span>     | <span data-ttu-id="34b9f-122">PHSH</span><span class="sxs-lookup"><span data-stu-id="34b9f-122">PHSH</span></span>     | <span data-ttu-id="34b9f-123">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="34b9f-123">Configure your spam filter policies</span></span>     |
|<span data-ttu-id="34b9f-124">第三章</span><span class="sxs-lookup"><span data-stu-id="34b9f-124">3</span></span>     | <span data-ttu-id="34b9f-125">高可信度垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="34b9f-125">High confidence spam</span></span>      | <span data-ttu-id="34b9f-126">HSPM</span><span class="sxs-lookup"><span data-stu-id="34b9f-126">HSPM</span></span>        | <span data-ttu-id="34b9f-127">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="34b9f-127">Configure your spam filter policies</span></span>        |
|<span data-ttu-id="34b9f-128">4</span><span class="sxs-lookup"><span data-stu-id="34b9f-128">4</span></span>     | <span data-ttu-id="34b9f-129">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="34b9f-129">Spoofing</span></span>        | <span data-ttu-id="34b9f-130">SPOOF</span><span class="sxs-lookup"><span data-stu-id="34b9f-130">SPOOF</span></span>        | <span data-ttu-id="34b9f-131">反网络钓鱼策略、欺骗性智能</span><span class="sxs-lookup"><span data-stu-id="34b9f-131">Anti-phishing policy, spoof intelligence</span></span>        |
|<span data-ttu-id="34b9f-132">5</span><span class="sxs-lookup"><span data-stu-id="34b9f-132">5</span></span>     | <span data-ttu-id="34b9f-133">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="34b9f-133">Spam</span></span>         | <span data-ttu-id="34b9f-134">SPM</span><span class="sxs-lookup"><span data-stu-id="34b9f-134">SPM</span></span>         | <span data-ttu-id="34b9f-135">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="34b9f-135">Configure your spam filter policies</span></span>         |
|<span data-ttu-id="34b9f-136">型</span><span class="sxs-lookup"><span data-stu-id="34b9f-136">6</span></span>     | <span data-ttu-id="34b9f-137">批量邮件</span><span class="sxs-lookup"><span data-stu-id="34b9f-137">Bulk</span></span>         | <span data-ttu-id="34b9f-138">BULK</span><span class="sxs-lookup"><span data-stu-id="34b9f-138">BULK</span></span>        | <span data-ttu-id="34b9f-139">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="34b9f-139">Configure your spam filter policies</span></span>         |

<span data-ttu-id="34b9f-140">此外, 这些策略适用于_具有 ATP 的组织_。</span><span class="sxs-lookup"><span data-stu-id="34b9f-140">In addition, these policies apply to _organizations with ATP_.</span></span>

|<span data-ttu-id="34b9f-141">优先级</span><span class="sxs-lookup"><span data-stu-id="34b9f-141">Priority</span></span> |<span data-ttu-id="34b9f-142">策略</span><span class="sxs-lookup"><span data-stu-id="34b9f-142">Policy</span></span>  |<span data-ttu-id="34b9f-143">类别</span><span class="sxs-lookup"><span data-stu-id="34b9f-143">Category</span></span>  |<span data-ttu-id="34b9f-144">托管</span><span class="sxs-lookup"><span data-stu-id="34b9f-144">Where Managed</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="34b9f-145">步</span><span class="sxs-lookup"><span data-stu-id="34b9f-145">7</span></span>     | <span data-ttu-id="34b9f-146">域模拟</span><span class="sxs-lookup"><span data-stu-id="34b9f-146">Domain Impersonation</span></span>         | <span data-ttu-id="34b9f-147">DIMP</span><span class="sxs-lookup"><span data-stu-id="34b9f-147">DIMP</span></span>         | <span data-ttu-id="34b9f-148">设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="34b9f-148">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>        |
|<span data-ttu-id="34b9f-149">utf-8</span><span class="sxs-lookup"><span data-stu-id="34b9f-149">8</span></span>     | <span data-ttu-id="34b9f-150">用户模拟</span><span class="sxs-lookup"><span data-stu-id="34b9f-150">User Impersonation</span></span>        | <span data-ttu-id="34b9f-151">UIMP</span><span class="sxs-lookup"><span data-stu-id="34b9f-151">UIMP</span></span>         | <span data-ttu-id="34b9f-152">设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="34b9f-152">Set up Office 365 ATP anti-phishing and anti-phishing policies</span></span>         |

<span data-ttu-id="34b9f-153">例如, 如果您有两个策略:</span><span class="sxs-lookup"><span data-stu-id="34b9f-153">As an example, if you have two policies:</span></span>

|<span data-ttu-id="34b9f-154">策略</span><span class="sxs-lookup"><span data-stu-id="34b9f-154">Policy</span></span>  |<span data-ttu-id="34b9f-155">优先级</span><span class="sxs-lookup"><span data-stu-id="34b9f-155">Priority</span></span>  |<span data-ttu-id="34b9f-156">用户/域模拟</span><span class="sxs-lookup"><span data-stu-id="34b9f-156">User/Domain Impersonation</span></span>  |<span data-ttu-id="34b9f-157">反欺骗</span><span class="sxs-lookup"><span data-stu-id="34b9f-157">Anti-spoofing</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="34b9f-158">A</span><span class="sxs-lookup"><span data-stu-id="34b9f-158">A</span></span>     | <span data-ttu-id="34b9f-159">1</span><span class="sxs-lookup"><span data-stu-id="34b9f-159">1</span></span>        | <span data-ttu-id="34b9f-160">开</span><span class="sxs-lookup"><span data-stu-id="34b9f-160">On</span></span>        |<span data-ttu-id="34b9f-161">关</span><span class="sxs-lookup"><span data-stu-id="34b9f-161">Off</span></span>         |
|<span data-ttu-id="34b9f-162">B</span><span class="sxs-lookup"><span data-stu-id="34b9f-162">B</span></span>     | <span data-ttu-id="34b9f-163">双面</span><span class="sxs-lookup"><span data-stu-id="34b9f-163">2</span></span>        | <span data-ttu-id="34b9f-164">关</span><span class="sxs-lookup"><span data-stu-id="34b9f-164">Off</span></span>        | <span data-ttu-id="34b9f-165">开</span><span class="sxs-lookup"><span data-stu-id="34b9f-165">On</span></span>        |

<span data-ttu-id="34b9f-166">如果一封邮件同时被标识为_用户模拟_和_欺骗_(请参阅上表中的反欺骗), 并且范围为策略 a 的同一组用户的范围为策略 B, 则该邮件将被标记并被视为_欺骗_邮件, 但不由于反欺骗已关闭, 并且**欺骗以更高优先级 (4) 而不是用户模拟 (8) 运行**, 因此应用了操作。</span><span class="sxs-lookup"><span data-stu-id="34b9f-166">If a message comes in identified as both _user impersonation_ and _spoofing_ (see anti-spoofing in the table above), and the same set of users scoped to policy A is scoped to policy B, then the message is flagged and treated as a _spoof_, but no action is applied since Anti-spoofing is turned off, and because **spoof runs at a higher priority (4) than User Impersonation (8)**.</span></span>

<span data-ttu-id="34b9f-167">若要应用其他类型的网络钓鱼策略, 您将需要调整应用不同策略的用户的设置。</span><span class="sxs-lookup"><span data-stu-id="34b9f-167">To make other types of phishing policy apply, you will need to adjust the settings of who the various policies apply to.</span></span>




---
title: 威胁浏览器 (和实时检测)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/20/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 了解安全&amp;合规性中心中的资源管理器 (和实时检测)。
ms.openlocfilehash: 3d2eab30b97655b692ed1bfe089b6a79834fd110
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394347"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="567d1-103">威胁浏览器 (和实时检测)</span><span class="sxs-lookup"><span data-stu-id="567d1-103">Threat Explorer (and real-time detections)</span></span>

<span data-ttu-id="567d1-104">如果您的组织具有[Office 365 高级威胁防护](office-365-atp.md)(OFFICE 365 ATP), 并且您拥有[必要的权限](#required-licenses-and-permissions), 则您可以使用**资源管理器**或**实时检测**(以前的*实时报告*)。[请参阅新增功能](#new-features-in-real-time-detections)!</span><span class="sxs-lookup"><span data-stu-id="567d1-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly *real-time reports* — [see what's new](#new-features-in-real-time-detections)!).</span></span> <span data-ttu-id="567d1-105">在安全 & 合规性中心中, 转到 "**威胁管理**", 然后选择 "**浏览器**" 或 "**实时检测**"。</span><span class="sxs-lookup"><span data-stu-id="567d1-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** OR **Real-time detections**.</span></span> 

|<span data-ttu-id="567d1-106">在 ATP 计划2中, 您将看到:</span><span class="sxs-lookup"><span data-stu-id="567d1-106">With ATP Plan 2, you see:</span></span>  |<span data-ttu-id="567d1-107">在 ATP 计划1中, 您将看到:</span><span class="sxs-lookup"><span data-stu-id="567d1-107">With ATP Plan 1, you see:</span></span>  |
|---------|---------|
|![威胁资源管理器](media/threatmgmt-explorer.png)      |![实时检测](media/threatmgmt-realtimedetections.png)         |

<span data-ttu-id="567d1-110">使用浏览器 (或实时检测) 时, 您将拥有一个强大的报告, 使安全操作团队能够有效地调查威胁并对其做出响应, 这与以下图像类似:</span><span class="sxs-lookup"><span data-stu-id="567d1-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently, and it resembles the following image:</span></span> 

![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="567d1-112">使用此报告, 可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="567d1-112">With this report, you can:</span></span>
- [<span data-ttu-id="567d1-113">查看 Office 365 安全功能检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="567d1-113">See malware detected by Office 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="567d1-114">查看有关仿冒 Url 的数据, 然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="567d1-114">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- <span data-ttu-id="567d1-115">[从资源管理器中的视图启动自动调查和响应过程](#start-automated-investigation-and-response)(仅 ATP 计划 2)</span><span class="sxs-lookup"><span data-stu-id="567d1-115">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="567d1-116">...[调查恶意电子邮件,](#more-ways-to-use-explorer-or-real-time-detections)等等!</span><span class="sxs-lookup"><span data-stu-id="567d1-116">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="new-features-in-real-time-detections"></a><span data-ttu-id="567d1-117">实时检测中的新功能</span><span class="sxs-lookup"><span data-stu-id="567d1-117">New features in real-time detections</span></span>

<span data-ttu-id="567d1-118">资源管理器/实时检测添加新的新字段, 旨在为您提供电子邮件领域的更完整的详细信息。</span><span class="sxs-lookup"><span data-stu-id="567d1-118">Explorer / real-time detections adds fresh new fields designed to give you a more complete picture of where your emails land.</span></span> <span data-ttu-id="567d1-119">此更改的目标部分是使搜索更易于进行安全操作人员, 但最终结果是了解问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="567d1-119">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem emails at a glance.</span></span>

<span data-ttu-id="567d1-120">这是如何完成的？</span><span class="sxs-lookup"><span data-stu-id="567d1-120">How is this done?</span></span> <span data-ttu-id="567d1-121">传递状态现已分为两列:</span><span class="sxs-lookup"><span data-stu-id="567d1-121">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="567d1-122">传递操作-此电子邮件的状态是什么？</span><span class="sxs-lookup"><span data-stu-id="567d1-122">Delivery Action - What is the status of this email?</span></span>
- <span data-ttu-id="567d1-123">送达位置-此电子邮件的路由结果</span><span class="sxs-lookup"><span data-stu-id="567d1-123">Delivery Location - Where was this email routed as a result?</span></span>

<span data-ttu-id="567d1-124">传递操作是由于现有策略或检测而导致对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="567d1-124">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="567d1-125">以下是电子邮件可能执行的操作:</span><span class="sxs-lookup"><span data-stu-id="567d1-125">Here are the possible actions an email can take:</span></span>

|<span data-ttu-id="567d1-126">附带</span><span class="sxs-lookup"><span data-stu-id="567d1-126">Delivered</span></span>  |<span data-ttu-id="567d1-127">Junked</span><span class="sxs-lookup"><span data-stu-id="567d1-127">Junked</span></span>  |<span data-ttu-id="567d1-128">Blocked</span><span class="sxs-lookup"><span data-stu-id="567d1-128">Blocked</span></span>  |<span data-ttu-id="567d1-129">代替</span><span class="sxs-lookup"><span data-stu-id="567d1-129">Replaced</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="567d1-130">电子邮件已传递到用户的收件箱或文件夹, 用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="567d1-130">Email was delivered to Inbox or folder of a user and the user can directly access it.</span></span>    | <span data-ttu-id="567d1-131">电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹, 并且用户有权访问这些文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="567d1-131">Email was sent to either user’s Junk folder or Deleted folder, and the user has access to emails in those folders.</span></span>       | <span data-ttu-id="567d1-132">隔离的、失败的或已丢弃的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="567d1-132">Any emails that are quarantined, that  failed, or were dropped.</span></span> <span data-ttu-id="567d1-133">用户完全无法访问它!</span><span class="sxs-lookup"><span data-stu-id="567d1-133">This is completely inaccessible by the user!</span></span>     | <span data-ttu-id="567d1-134">所有恶意附件都被替换为 .txt 文件的电子邮件, 以表明附件是恶意的。</span><span class="sxs-lookup"><span data-stu-id="567d1-134">Any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>     |

<span data-ttu-id="567d1-135">用户可以看到的内容及其不能执行的操作:</span><span class="sxs-lookup"><span data-stu-id="567d1-135">And here is what the user can see, and what they can't:</span></span>

|<span data-ttu-id="567d1-136">最终用户可以访问</span><span class="sxs-lookup"><span data-stu-id="567d1-136">Accessible to end users</span></span>  |<span data-ttu-id="567d1-137">最终用户无法访问</span><span class="sxs-lookup"><span data-stu-id="567d1-137">Inaccessible to end users</span></span>  |
|---------|---------|
|<span data-ttu-id="567d1-138">附带</span><span class="sxs-lookup"><span data-stu-id="567d1-138">Delivered</span></span>     | <span data-ttu-id="567d1-139">Blocked</span><span class="sxs-lookup"><span data-stu-id="567d1-139">Blocked</span></span>        |
|<span data-ttu-id="567d1-140">Junked</span><span class="sxs-lookup"><span data-stu-id="567d1-140">Junked</span></span>     | <span data-ttu-id="567d1-141">代替</span><span class="sxs-lookup"><span data-stu-id="567d1-141">Replaced</span></span>        |

<span data-ttu-id="567d1-142">"送达位置" 显示运行送达后的策略和检测结果。</span><span class="sxs-lookup"><span data-stu-id="567d1-142">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="567d1-143">它已链接到传递操作。</span><span class="sxs-lookup"><span data-stu-id="567d1-143">It's linked to a Delivery Action.</span></span> <span data-ttu-id="567d1-144">添加此字段是为了深入了解在发现问题邮件时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="567d1-144">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="567d1-145">以下是送达位置的 possilbe 值:</span><span class="sxs-lookup"><span data-stu-id="567d1-145">Here are the possilbe values of delivery location:</span></span>

1. <span data-ttu-id="567d1-146">收件箱或文件夹–电子邮件位于收件箱或文件夹中 (根据您的电子邮件规则)。</span><span class="sxs-lookup"><span data-stu-id="567d1-146">Inbox or folder – The email is in inbox or a folder (according to your email rules).</span></span>
2. <span data-ttu-id="567d1-147">本地或外部–邮箱在云上不存在, 但在本地。</span><span class="sxs-lookup"><span data-stu-id="567d1-147">On-prem or external – The mailbox doesn’t exist on cloud but is on-premises.</span></span>
3. <span data-ttu-id="567d1-148">垃圾邮件文件夹–在用户的 "垃圾邮件" 文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="567d1-148">Junk folder – The email in in the Junk folder of a user.</span></span>
4. <span data-ttu-id="567d1-149">"已删除邮件" 文件夹–用户的 "已删除邮件" 文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="567d1-149">Deleted items folder – The email in the Deleted items folder of a user.</span></span>
5. <span data-ttu-id="567d1-150">隔离–隔离中的电子邮件, 并且不在用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="567d1-150">Quarantine – The email in quarantine, and is not in a user’s mailbox.</span></span>
6. <span data-ttu-id="567d1-151">失败–电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="567d1-151">Failed – The email failed to reach the mailbox.</span></span>
7. <span data-ttu-id="567d1-152">丢弃–电子邮件在邮件流中的某个位置丢失。</span><span class="sxs-lookup"><span data-stu-id="567d1-152">Dropped – The email gets lost somewhere in the Mailflow.</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="567d1-153">查看电子邮件中的技术检测到恶意软件</span><span class="sxs-lookup"><span data-stu-id="567d1-153">See malware detected in email by technology</span></span>

<span data-ttu-id="567d1-154">假设您想要查看 Office 365 技术在电子邮件中检测到的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="567d1-154">Suppose you want to see malware detected in email, by Office 365 technology.</span></span> <span data-ttu-id="567d1-155">为此, 请使用[电子邮件 >](threat-explorer-views.md#email--malware)浏览器 (或实时检测) 的恶意软件视图。</span><span class="sxs-lookup"><span data-stu-id="567d1-155">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="567d1-156">在 "安全性 & 合规性中心[https://protection.office.com](https://protection.office.com)() 中, 选择"**威胁管理** > **资源管理器**"(或"**实时检测**")。</span><span class="sxs-lookup"><span data-stu-id="567d1-156">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="567d1-157">(此示例使用 Explorer。)</span><span class="sxs-lookup"><span data-stu-id="567d1-157">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="567d1-158">在 "**视图**" 菜单中, 选择 "**电子邮件** > **恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="567d1-158">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="567d1-159">![浏览器的视图菜单](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="567d1-159">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>

3. <span data-ttu-id="567d1-160">单击 "**发件人**", 然后选择 "**基本** > **检测技术**"。</span><span class="sxs-lookup"><span data-stu-id="567d1-160">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="567d1-161">您的检测技术现在可用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="567d1-161">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="567d1-162">![恶意软件检测技术](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="567d1-162">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 

4. <span data-ttu-id="567d1-163">选择一个选项, 然后单击 "**刷新**" 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="567d1-163">Select an option, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="567d1-164">![选定的检测技术](media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="567d1-164">![Selected detection technology](media/ExplorerEmailMalwareDetectionTechATP.png)</span></span><br/> 

<span data-ttu-id="567d1-165">报告将刷新, 以显示使用您选择的技术选项在电子邮件中检测到恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="567d1-165">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="567d1-166">在这里, 你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="567d1-166">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="567d1-167">查看有关仿冒 Url 的数据, 然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="567d1-167">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="567d1-168">假定您要查看通过电子邮件中的 Url 进行的网络钓鱼尝试, 包括允许、阻止和重写的 Url 的列表。</span><span class="sxs-lookup"><span data-stu-id="567d1-168">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="567d1-169">标识所单击的 Url 需要配置[ATP 安全链接](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="567d1-169">Identifying URLs that were clicked requires [ATP Safe links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="567d1-170">确保已为单击时的保护设置了[Atp 安全链接策略](set-up-atp-safe-links-policies.md), 然后通过 ATP 安全链接单击 "verdicts" 进行日志记录。</span><span class="sxs-lookup"><span data-stu-id="567d1-170">Make sure that you have set up [ATP Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by ATP Safe Links.</span></span> 

<span data-ttu-id="567d1-171">若要查看邮件中的网络钓鱼 Url 并单击网络钓鱼邮件中的 Url, 请使用[电子邮件 >](threat-explorer-views.md#email--phish)浏览器 (或实时检测) 的网络钓鱼视图。</span><span class="sxs-lookup"><span data-stu-id="567d1-171">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="567d1-172">在 "安全性 & 合规性中心[https://protection.office.com](https://protection.office.com)() 中, 选择"**威胁管理** > **资源管理器**"(或"**实时检测**")。</span><span class="sxs-lookup"><span data-stu-id="567d1-172">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="567d1-173">(此示例使用 Explorer。)</span><span class="sxs-lookup"><span data-stu-id="567d1-173">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="567d1-174">在 "**视图**" 菜单中, 选择 "**电子邮件** > **网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="567d1-174">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="567d1-175">![浏览器的视图菜单](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="567d1-175">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>

3. <span data-ttu-id="567d1-176">单击 "**发件人**", 然后选择 " **url** > **" 单击 "判定"**。</span><span class="sxs-lookup"><span data-stu-id="567d1-176">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="567d1-177">选择一个或多个选项 (如 "已**阻止**" 和 "**阻止被覆盖**"), 然后单击与应用该筛选器的选项位于同一行中的 "**刷新**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="567d1-177">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="567d1-178">(不要刷新浏览器窗口。)</span><span class="sxs-lookup"><span data-stu-id="567d1-178">(Don't refresh your browser window.)</span></span><br/><span data-ttu-id="567d1-179">![Url 并单击 "verdicts"](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="567d1-179">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

    <span data-ttu-id="567d1-180">报告将刷新, 以在报告下的 "URL" 选项卡上显示两个不同的 URL 表:</span><span class="sxs-lookup"><span data-stu-id="567d1-180">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   1. <span data-ttu-id="567d1-181">**上面的 url**是您已筛选出的邮件中包含的 url, 并且每个 URL 的电子邮件传递操作都会计数。</span><span class="sxs-lookup"><span data-stu-id="567d1-181">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="567d1-182">在网络钓鱼电子邮件视图中, 此列表通常包含合法的 Url。</span><span class="sxs-lookup"><span data-stu-id="567d1-182">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="567d1-183">攻击者在其邮件中加入了好和坏的 Url, 以尝试传递它们, 但它们会使用户更有趣地单击恶意链接。</span><span class="sxs-lookup"><span data-stu-id="567d1-183">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="567d1-184">Url 表按总电子邮件计数进行排序 (注意: 此列不显示为简化视图)。</span><span class="sxs-lookup"><span data-stu-id="567d1-184">The table of URLs is sorted by total email count (NOTE: This column is not shown to simplify the view).</span></span>

   2. <span data-ttu-id="567d1-185">单击 "**上**一条" 可将已单击的安全链接包装的 url 按总点击次数排序 (此列也不显示为简化视图)。</span><span class="sxs-lookup"><span data-stu-id="567d1-185">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="567d1-186">"总计计数依据" 列指示安全链接单击每个单击的 URL 的 "已判定计数"。</span><span class="sxs-lookup"><span data-stu-id="567d1-186">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="567d1-187">在网络钓鱼电子邮件视图中, 这通常是可疑或恶意的 Url, 但可能包含网络钓鱼邮件中的干净 Url。</span><span class="sxs-lookup"><span data-stu-id="567d1-187">In the phish email view, these are more often suspicious or malicious URLs, but could include clean URLs that are in phish messages.</span></span> <span data-ttu-id="567d1-188">URL 单击未打开的链接将不会显示在此处。</span><span class="sxs-lookup"><span data-stu-id="567d1-188">URL clicks on unwrapped links will not show up here.</span></span>
   
   <span data-ttu-id="567d1-189">这两个 Url 表通过传递操作和位置显示网络钓鱼电子邮件中的前几个 Url, 并显示已阻止 (或在出现警告的情况下访问) 的 URL 单击, 以便您可以了解用户收到的潜在错误链接以及用户的交互情况。</span><span class="sxs-lookup"><span data-stu-id="567d1-189">The two URLs tables show top URLs in phishing emails by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="567d1-190">在这里, 你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="567d1-190">From here, you can conduct further analysis.</span></span> <span data-ttu-id="567d1-191">例如, 在图表下方, 您可以看到在组织的环境中被阻止的电子邮件中的最高 Url。</span><span class="sxs-lookup"><span data-stu-id="567d1-191">For example, below the chart, you can see the top URLs in emails that were blocked in your organization's environment.</span></span>
   
   ![阻止的资源管理器 Url](media/ExplorerPhishClickVerdictURLs.png)
   
   <span data-ttu-id="567d1-193">选择一个 URL 以查看更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="567d1-193">Select a URL to view more detailed information.</span></span> <span data-ttu-id="567d1-194">请注意, 在 "URL 飞出" 对话框中, 将删除对电子邮件的筛选, 以向您显示在您的环境中 URL 公开的完整视图。</span><span class="sxs-lookup"><span data-stu-id="567d1-194">Note that in the URL flyout dialog, the filtering on emails is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="567d1-195">这样, 您就可以在资源管理器中筛选出您关注的电子邮件, 查找潜在威胁的特定 Url, 然后展开您对环境中的 URL 公开的了解 (通过 URL 详细信息对话框), 而无需将 URL 筛选器添加到资源管理器视图本身。</span><span class="sxs-lookup"><span data-stu-id="567d1-195">This lets you filter down emails in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="567d1-196">查看用户报告的电子邮件</span><span class="sxs-lookup"><span data-stu-id="567d1-196">Review email messages reported by users</span></span>

<span data-ttu-id="567d1-197">假设您想要查看您的组织中的用户使用[Outlook 和 web 上的 outlook 的报告邮件外接程序](enable-the-report-message-add-in.md)报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="567d1-197">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="567d1-198">为此, 请使用[电子邮件 >](threat-explorer-views.md#email--user-reported)浏览器的用户报告视图 (或实时检测)。</span><span class="sxs-lookup"><span data-stu-id="567d1-198">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="567d1-199">在 "安全性 & 合规性中心[https://protection.office.com](https://protection.office.com)() 中, 选择"**威胁管理** > **资源管理器**"(或"**实时检测**")。</span><span class="sxs-lookup"><span data-stu-id="567d1-199">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="567d1-200">(此示例使用 Explorer。)</span><span class="sxs-lookup"><span data-stu-id="567d1-200">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="567d1-201">在 "**视图**" 菜单中, 选择 "**电子邮件** > **用户报告**"。</span><span class="sxs-lookup"><span data-stu-id="567d1-201">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="567d1-202">![浏览器的视图菜单](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="567d1-202">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>

3. <span data-ttu-id="567d1-203">单击 "**发件人**", 然后选择 "**基本** > **报告类型**"。</span><span class="sxs-lookup"><span data-stu-id="567d1-203">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="567d1-204">选择一个选项, 如 "**网络钓鱼**", 然后单击 "**刷新**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="567d1-204">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="567d1-205">![用户报告的网络钓鱼](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="567d1-205">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="567d1-206">报告将刷新, 以显示组织中的人员已报告为网络钓鱼尝试的电子邮件的相关数据。</span><span class="sxs-lookup"><span data-stu-id="567d1-206">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="567d1-207">您可以使用此信息进行进一步分析, 如有必要, 调整您的[ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="567d1-207">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="567d1-208">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="567d1-208">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="567d1-209">**Office 365 ATP 计划 2**和**Office 365 E5**中提供了自动调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="567d1-209">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="567d1-210">(新!)[自动化调查和响应](automated-investigation-response-office.md)可在调查和缓解网络攻击方面为安全操作团队节省大量时间和精力。</span><span class="sxs-lookup"><span data-stu-id="567d1-210">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyber attacks.</span></span> <span data-ttu-id="567d1-211">除了配置可触发安全行动手册的警报外, 还可以从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="567d1-211">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> 

<span data-ttu-id="567d1-212">有关此操作的详细信息, 请参阅[示例: 安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="567d1-212">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="567d1-213">使用资源管理器 (或实时检测) 的更多方法</span><span class="sxs-lookup"><span data-stu-id="567d1-213">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="567d1-214">除了本文中介绍的方案之外, 您还可以使用浏览器 (或实时检测) 中提供的更多报告选项。</span><span class="sxs-lookup"><span data-stu-id="567d1-214">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span> 
- [<span data-ttu-id="567d1-215">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="567d1-215">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="567d1-216">查看 SharePoint Online、OneDrive 和 Microsoft 团队中检测到的恶意文件</span><span class="sxs-lookup"><span data-stu-id="567d1-216">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="567d1-217">获取威胁资源管理器中的视图 (和实时检测) 的概述</span><span class="sxs-lookup"><span data-stu-id="567d1-217">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="567d1-218">必需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="567d1-218">Required licenses and permissions</span></span>

<span data-ttu-id="567d1-219">您必须具有[Office 365 ATP](office-365-atp.md)才能获取资源管理器或实时检测。</span><span class="sxs-lookup"><span data-stu-id="567d1-219">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>
- <span data-ttu-id="567d1-220">资源管理器包含在 Office 365 ATP 计划2中。</span><span class="sxs-lookup"><span data-stu-id="567d1-220">Explorer is included in Office 365 ATP Plan 2.</span></span> 
- <span data-ttu-id="567d1-221">实时检测报告包含在 Office 365 ATP 计划1中。</span><span class="sxs-lookup"><span data-stu-id="567d1-221">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>
- <span data-ttu-id="567d1-222">计划为应由 ATP 保护的所有用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="567d1-222">Plan to assign licenses for all users who should be protected by ATP.</span></span> <span data-ttu-id="567d1-223">(资源管理器或实时检测将显示许可用户的检测数据。)</span><span class="sxs-lookup"><span data-stu-id="567d1-223">(Explorer or real-time detections will show detection data for licensed users.)</span></span>

<span data-ttu-id="567d1-224">若要查看和使用资源管理器或实时检测, 您必须具有适当的权限, 例如, 授予安全管理员或安全阅读者的权限。</span><span class="sxs-lookup"><span data-stu-id="567d1-224">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="567d1-225">对于安全&amp;合规中心, 您必须具有以下分配的角色之一:</span><span class="sxs-lookup"><span data-stu-id="567d1-225">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="567d1-226">组织管理</span><span class="sxs-lookup"><span data-stu-id="567d1-226">Organization Management</span></span>
    - <span data-ttu-id="567d1-227">安全管理员 (可在 Azure Active Directory 管理中心中分配 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="567d1-227">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="567d1-228">安全读者</span><span class="sxs-lookup"><span data-stu-id="567d1-228">Security Reader</span></span>

- <span data-ttu-id="567d1-229">对于 Exchange Online, 必须在 Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell cmdlet 中分配以下角色之一 (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="567d1-229">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="567d1-230">组织管理</span><span class="sxs-lookup"><span data-stu-id="567d1-230">Organization Management</span></span>
    - <span data-ttu-id="567d1-231">仅限查看组织管理</span><span class="sxs-lookup"><span data-stu-id="567d1-231">View-only Organization Management</span></span>
    - <span data-ttu-id="567d1-232">“仅供查看收件人”角色</span><span class="sxs-lookup"><span data-stu-id="567d1-232">View-Only Recipients role</span></span>
    - <span data-ttu-id="567d1-233">合规性管理</span><span class="sxs-lookup"><span data-stu-id="567d1-233">Compliance Management</span></span>

<span data-ttu-id="567d1-234">若要了解有关角色和权限的详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="567d1-234">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="567d1-235">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="567d1-235">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="567d1-236">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="567d1-236">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  

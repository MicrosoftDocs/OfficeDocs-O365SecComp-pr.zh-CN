---
title: 在 Microsoft 365 安全中监视设备
description: 介绍如何确保你的设备安全、最新和发现组织中的潜在威胁
keywords: security、恶意软件、Microsoft 365、M365、security center、monitor、report、devices
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
ms.openlocfilehash: 31d89b8bbcad98814ff33764bad24bffbbba4968
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263498"
---
# <a name="monitor-devices-in-microsoft-365-security"></a><span data-ttu-id="82cfc-104">在 Microsoft 365 安全中监视设备</span><span class="sxs-lookup"><span data-stu-id="82cfc-104">Monitor devices in Microsoft 365 security</span></span>

<span data-ttu-id="82cfc-105">确保你的设备在 Microsoft 365 安全中心中安全、保持最新并找出潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="82cfc-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="82cfc-106">查看设备警报</span><span class="sxs-lookup"><span data-stu-id="82cfc-106">View device alerts</span></span>

<span data-ttu-id="82cfc-107">从 Windows Defender ATP 获取有关你的设备上的入侵活动和其他威胁的最新警报 (适用于 E5 许可证)。</span><span class="sxs-lookup"><span data-stu-id="82cfc-107">Get up-to-date alerts about breach activity and other threats on your devices from Windows Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="82cfc-108">Microsoft 365 安全中心有几张卡, 可让您根据首选工作流在高级别有效地监视这些警报。</span><span class="sxs-lookup"><span data-stu-id="82cfc-108">Microsoft 365 security center has several cards that allow you to effectively monitor these alerts at a high-level, depending on your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="82cfc-109">监视高影响警报</span><span class="sxs-lookup"><span data-stu-id="82cfc-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="82cfc-110">每个 Windows Defender ATP 警报都具有相应的严重性 (高、中、低或信息), 指示其对你的网络的潜在影响 (如果不采用无人参与)。</span><span class="sxs-lookup"><span data-stu-id="82cfc-110">Each Windows Defender ATP alert has a corresponding severity—high, medium, low, or informational—that indicates its potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="82cfc-111">使用**设备警报严重级别**卡专门关注更严重且可能需要立即响应的警报。</span><span class="sxs-lookup"><span data-stu-id="82cfc-111">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="82cfc-112">在此卡片中, 可以查看有关 Windows Defender 安全中心门户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="82cfc-112">From this card, you can view more information on the Windows Defender Security Center portal.</span></span>

![设备警报严重级别卡片](./media/security-docs/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="82cfc-114">了解警报的来源</span><span class="sxs-lookup"><span data-stu-id="82cfc-114">Understand sources of alerts</span></span>

<span data-ttu-id="82cfc-115">Windows Defender ATP 利用各种安全传感器和智能源中的数据来生成警报。</span><span class="sxs-lookup"><span data-stu-id="82cfc-115">Windows Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="82cfc-116">例如, 它可以使用 Windows Defender 防病毒和第三方反恶意软件中的检测信息, 以及通过 web 服务 API 提供的自定义威胁智能。</span><span class="sxs-lookup"><span data-stu-id="82cfc-116">For example, it can use detection information from Windows Defender Antivirus and third-party antimalware, as well as your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="82cfc-117">**设备警报检测**源卡按来源显示警报的分布情况。</span><span class="sxs-lookup"><span data-stu-id="82cfc-117">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="82cfc-118">此卡片可帮助您跟踪与某些来源 (尤其是自定义源) 相关的活动。</span><span class="sxs-lookup"><span data-stu-id="82cfc-118">This card can help you track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="82cfc-119">您还可以使用此操作来重点关注来自未配置为自动阻止恶意活动或组件的传感器发出的警报。</span><span class="sxs-lookup"><span data-stu-id="82cfc-119">You can also use this to focus on alerts coming from sensors that are not configured to automatically block malicious activity or components.</span></span>

![设备警报检测源卡](./media/security-docs/device-alert-detection-sources.png)

<span data-ttu-id="82cfc-121">在此卡片中, 可以查看有关 Windows Defender 安全中心门户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="82cfc-121">From this card, you can view more information on the Windows Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="82cfc-122">了解触发警报的威胁类型</span><span class="sxs-lookup"><span data-stu-id="82cfc-122">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="82cfc-123">Windows Defender ATP 将每个警报分类到一个类别, 表示攻击链中的某个阶段或威胁组件的类型。</span><span class="sxs-lookup"><span data-stu-id="82cfc-123">Windows Defender ATP sorts each alert into a category representing a certain stage in the attack chain or a type of threat component.</span></span> <span data-ttu-id="82cfc-124">例如, 检测到的威胁活动可能会分类到 "横向移动", 以指示活动试图访问网络上的其他设备, 并且在攻击者获得初始 foothold 时可能会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="82cfc-124">For example, detected threat activity might be categorized into “lateral movement” to indicate that the activity involved an attempt to reach other devices on the network and has likely occurred after attackers have gained an initial foothold.</span></span> <span data-ttu-id="82cfc-125">检测到威胁组件时, 可能会将其广泛分类为 "恶意软件", 或者更具体地说为 "勒索软件"、"凭据窃取" 或其他类型的恶意软件或不需要的软件。</span><span class="sxs-lookup"><span data-stu-id="82cfc-125">When detected, a threat component might either be classified broadly as “malware” or more specifically as “ransomware”, “credential stealing” or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="82cfc-126">**设备威胁类别**卡片显示了将警报分布到这些类别中的情况。</span><span class="sxs-lookup"><span data-stu-id="82cfc-126">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="82cfc-127">您可以使用此信息来确定威胁活动, 如凭据窃取时的尝试, 与社会工程手段的尝试相比, 这可能会产生更大的影响。</span><span class="sxs-lookup"><span data-stu-id="82cfc-127">You can use this information to identify threat activity, such as attempts at credential theft, which can have more significant impact compared to attempts at social engineering, for example.</span></span> <span data-ttu-id="82cfc-128">您还可以使用它来监视与勒索软件类似的潜在破坏性威胁。</span><span class="sxs-lookup"><span data-stu-id="82cfc-128">You can also use this to monitor for potentially destructive threats like ransomware.</span></span>

![设备威胁类别卡片](./media/security-docs/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="82cfc-130">监视活动警报</span><span class="sxs-lookup"><span data-stu-id="82cfc-130">Monitor active alerts</span></span>

<span data-ttu-id="82cfc-131">**设备警报状态**卡指示尚未解决且可能需要注意的警报的数量。</span><span class="sxs-lookup"><span data-stu-id="82cfc-131">The **Device alert status** card indicates the number of alerts that have not been resolved and might require attention.</span></span> <span data-ttu-id="82cfc-132">在此卡片中, 可以查看有关 Windows Defender 安全中心门户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="82cfc-132">From this card, you can view more information on the Windows Defender Security Center portal.</span></span>

![设备警报状态卡片](./media/security-docs/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="82cfc-134">监视已解决警报的分类</span><span class="sxs-lookup"><span data-stu-id="82cfc-134">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="82cfc-135">解析 Window Defender ATP 警报时, 安全人员可以指定是否已将警报验证为:</span><span class="sxs-lookup"><span data-stu-id="82cfc-135">When resolving a Window Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="82cfc-136">真正的警报, 用于标识实际的违规活动或威胁组件</span><span class="sxs-lookup"><span data-stu-id="82cfc-136">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="82cfc-137">未正确检测到正常活动的假警报</span><span class="sxs-lookup"><span data-stu-id="82cfc-137">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="82cfc-138">**设备警报分类**卡显示已解决的警报是否已分类为 "真" 或 "假" 通知。</span><span class="sxs-lookup"><span data-stu-id="82cfc-138">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="82cfc-139">在此卡片中, 可以查看有关 Windows Defender 安全中心门户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="82cfc-139">From this card, you can view more information on the Windows Defender Security Center portal.</span></span>

<span data-ttu-id="82cfc-140">注意: 在某些情况下, 分类信息对某些通知不可用。</span><span class="sxs-lookup"><span data-stu-id="82cfc-140">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![设备警报分类卡](./media/security-docs/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="82cfc-142">监视已解决警报的确定</span><span class="sxs-lookup"><span data-stu-id="82cfc-142">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="82cfc-143">除了在解决方案解析过程中对警报是否为 true 或 false 进行分类之外, 您的安全人员可以确定在验证警报时发现的正常或恶意活动的类型。</span><span class="sxs-lookup"><span data-stu-id="82cfc-143">In addition to classifying whether an alert is true or false during resolution, your security staff can provide a determination, indicating the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="82cfc-144">**设备警报确定**卡显示为每个警报提供的决定, 具体如下:</span><span class="sxs-lookup"><span data-stu-id="82cfc-144">The **Device alert determination** card shows the determination provided for each alert, specifically:</span></span>

* <span data-ttu-id="82cfc-145">**apt.** –高级持久威胁, 表明检测到的活动或威胁组件是旨在获取受影响网络中的 foothold 的完善的安全漏洞的一部分</span><span class="sxs-lookup"><span data-stu-id="82cfc-145">**APT** – advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="82cfc-146">**恶意软件**–恶意文件或代码</span><span class="sxs-lookup"><span data-stu-id="82cfc-146">**Malware** – malicious file or code</span></span>
* <span data-ttu-id="82cfc-147">**安全人员**–安全人员执行的常规活动</span><span class="sxs-lookup"><span data-stu-id="82cfc-147">**Security personnel** – normal activity performed by security staff</span></span>
* <span data-ttu-id="82cfc-148">**安全测试**–旨在模拟实际威胁并预期触发安全传感器和生成警报的活动或组件</span><span class="sxs-lookup"><span data-stu-id="82cfc-148">**Security testing** – activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="82cfc-149">不**需要的软件**–不会被视为恶意的应用程序和其他软件, 但也违反了策略或可接受的使用标准</span><span class="sxs-lookup"><span data-stu-id="82cfc-149">**Unwanted software** – apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="82cfc-150">**其他**–不属于所提供类型的任何其他决定</span><span class="sxs-lookup"><span data-stu-id="82cfc-150">**Others** – any other determination that does not fall under the provided types</span></span>

<span data-ttu-id="82cfc-151">在此卡片中, 可以在 Windows Defender 安全中心中查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="82cfc-151">From this card, you can view more information in Windows Defender security center.</span></span>

![设备警报确定卡](./media/security-docs/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="82cfc-153">了解哪些设备有风险</span><span class="sxs-lookup"><span data-stu-id="82cfc-153">Understand which devices are at risk</span></span>

<span data-ttu-id="82cfc-154">**设备保护**显示设备的风险级别。</span><span class="sxs-lookup"><span data-stu-id="82cfc-154">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="82cfc-155">风险级别基于设备上的警报的类型和严重性等因素。</span><span class="sxs-lookup"><span data-stu-id="82cfc-155">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![设备保护卡](./media/security-docs/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="82cfc-157">监视和报告 Intune 管理的设备的状态</span><span class="sxs-lookup"><span data-stu-id="82cfc-157">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="82cfc-158">以下监视和报告包含在 Intune 中注册的设备的数据。</span><span class="sxs-lookup"><span data-stu-id="82cfc-158">The following monitoring and reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="82cfc-159">不包括来自 unenrolled 设备的数据。</span><span class="sxs-lookup"><span data-stu-id="82cfc-159">Data from unenrolled devices is not included.</span></span> <span data-ttu-id="82cfc-160">只有全局管理员才能查看这些卡片。</span><span class="sxs-lookup"><span data-stu-id="82cfc-160">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="82cfc-161">Intune 注册的设备数据包括:</span><span class="sxs-lookup"><span data-stu-id="82cfc-161">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="82cfc-162">设备合规性</span><span class="sxs-lookup"><span data-stu-id="82cfc-162">Device compliance</span></span>
* <span data-ttu-id="82cfc-163">具有活动恶意软件的设备</span><span class="sxs-lookup"><span data-stu-id="82cfc-163">Devices with active malware</span></span>
* <span data-ttu-id="82cfc-164">设备上的恶意软件类型</span><span class="sxs-lookup"><span data-stu-id="82cfc-164">Types of malware on devices</span></span>
* <span data-ttu-id="82cfc-165">设备上的恶意软件</span><span class="sxs-lookup"><span data-stu-id="82cfc-165">Malware on devices</span></span>
* <span data-ttu-id="82cfc-166">包含恶意软件检测的设备</span><span class="sxs-lookup"><span data-stu-id="82cfc-166">Devices with malware detections</span></span>
* <span data-ttu-id="82cfc-167">包含恶意软件检测的用户</span><span class="sxs-lookup"><span data-stu-id="82cfc-167">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="82cfc-168">监视设备合规性</span><span class="sxs-lookup"><span data-stu-id="82cfc-168">Monitor device compliance</span></span>

<span data-ttu-id="82cfc-169">**设备符合性**显示在 Intune 中注册的设备数量符合配置策略。</span><span class="sxs-lookup"><span data-stu-id="82cfc-169">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![设备合规性卡](./media/security-docs/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="82cfc-171">发现包含恶意软件检测的设备</span><span class="sxs-lookup"><span data-stu-id="82cfc-171">Discover devices with malware detections</span></span>

<span data-ttu-id="82cfc-172">**设备恶意软件检测**提供了包含恶意软件的 Intune 注册设备的数量, 这些设备尚未完全解决, 原因是挂起的操作有: 重新启动、完全扫描或手动用户操作, 或者更正操作未成功完成。</span><span class="sxs-lookup"><span data-stu-id="82cfc-172">**Device malware detections** provides the number of Intune enrolled devices with malware that have not been fully resolved due to pending actions—a restart, a full scan or manual user actions—or if the remediation action did not complete successfully.</span></span>

![设备恶意软件检测卡片](./media/security-docs/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="82cfc-174">了解检测到的恶意软件的类型</span><span class="sxs-lookup"><span data-stu-id="82cfc-174">Understand the types of malware detected</span></span>

<span data-ttu-id="82cfc-175">**设备上的恶意软件类型**显示在 Intune 中注册的设备上检测到的不同类型的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="82cfc-175">**Types of malware on devices** shows different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="82cfc-176">您可以调查 Microsoft 365 安全中心中的每种类型。</span><span class="sxs-lookup"><span data-stu-id="82cfc-176">You can investigate each type in Microsoft 365 security center.</span></span>

![设备卡上的恶意软件类型](./media/security-docs/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="82cfc-178">了解在你的设备上检测到的特定恶意软件</span><span class="sxs-lookup"><span data-stu-id="82cfc-178">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="82cfc-179">**设备上的恶意软件**提供在设备上检测到的特定恶意软件的列表。</span><span class="sxs-lookup"><span data-stu-id="82cfc-179">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![设备卡上的恶意软件](./media/security-docs/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="82cfc-181">了解哪些设备具有最多的恶意软件</span><span class="sxs-lookup"><span data-stu-id="82cfc-181">Understand which devices have the most malware</span></span>

<span data-ttu-id="82cfc-182">**包含恶意**软件检测的设备会显示哪些设备具有最多的恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="82cfc-182">**Devices with malware detections** shows which devices have the most malware detections.</span></span> <span data-ttu-id="82cfc-183">在 Microsoft 365 安全中心中, 可以调查恶意软件是处于活动状态、使用设备的用户及其在 Intune 中的管理状态。</span><span class="sxs-lookup"><span data-stu-id="82cfc-183">In Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![包含恶意软件检测卡片的设备](./media/security-docs/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="82cfc-185">了解哪些用户具有最多恶意软件的设备</span><span class="sxs-lookup"><span data-stu-id="82cfc-185">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="82cfc-186">**具有恶意软件检测的用户**显示具有最多恶意软件检测到的设备的用户。</span><span class="sxs-lookup"><span data-stu-id="82cfc-186">**Users with malware detections** shows users with devices that had the most malware detections.</span></span> <span data-ttu-id="82cfc-187">在 Microsoft 365 安全中心中, 可以查看为每个用户分配了多少个设备, 以及有关每个设备和恶意软件类型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="82cfc-187">In Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![具有恶意软件检测卡片的用户](./media/security-docs/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a><span data-ttu-id="82cfc-189">监视和管理 ASR 规则部署和检测</span><span class="sxs-lookup"><span data-stu-id="82cfc-189">Monitor and manage ASR rule deployment and detections</span></span>

<span data-ttu-id="82cfc-190">[攻击面减少 (ASR) 规则](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)可帮助阻止使用者查找恶意软件时通常使用的操作和应用程序感染计算机。</span><span class="sxs-lookup"><span data-stu-id="82cfc-190">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) help prevent actions and apps that are typically used by exploit-seeking malware to infect machines.</span></span> <span data-ttu-id="82cfc-191">这些规则控制何时以及如何运行可执行文件。</span><span class="sxs-lookup"><span data-stu-id="82cfc-191">These rules control when and how executables can run.</span></span> <span data-ttu-id="82cfc-192">例如, 可以阻止 JavaScript 或 VBScript 启动下载的可执行文件、阻止来自 Office 宏的 Win32 API 调用或阻止从 USB 驱动器运行的进程。</span><span class="sxs-lookup"><span data-stu-id="82cfc-192">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![攻击面缩减卡片](./media/security-docs/attack-surface-reduction-rules.png)

<span data-ttu-id="82cfc-194">**攻击面减少规则**卡提供了跨设备部署规则的概述。</span><span class="sxs-lookup"><span data-stu-id="82cfc-194">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="82cfc-195">卡片上的顶栏显示了以下部署模式中的设备总数:</span><span class="sxs-lookup"><span data-stu-id="82cfc-195">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="82cfc-196">**块状模式**–至少有一个配置为阻止检测活动的规则的设备</span><span class="sxs-lookup"><span data-stu-id="82cfc-196">**Block mode** – devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="82cfc-197">**审核模式**–没有设置任何规则的设备阻止检测到的活动, 但至少有一个规则集来审核检测到的活动</span><span class="sxs-lookup"><span data-stu-id="82cfc-197">**Audit mode** – devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="82cfc-198">**off** -所有 ASR 规则关闭的设备</span><span class="sxs-lookup"><span data-stu-id="82cfc-198">**Off** – devices with all ASR rules turned off</span></span>

<span data-ttu-id="82cfc-199">此卡片的下半部分按规则显示设备上的设置。</span><span class="sxs-lookup"><span data-stu-id="82cfc-199">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="82cfc-200">每条栏指示设置为阻止或审核检测或完全关闭规则的设备的数量。</span><span class="sxs-lookup"><span data-stu-id="82cfc-200">Each bar indicates the number of devices that are set to block or audit detection or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="82cfc-201">查看 ASR 检测</span><span class="sxs-lookup"><span data-stu-id="82cfc-201">View ASR detections</span></span>

<span data-ttu-id="82cfc-202">若要查看有关网络中的 ASR 规则检测的详细信息, 请选择 "查看**受攻击面减少的规则**卡片上的**检测**"。</span><span class="sxs-lookup"><span data-stu-id="82cfc-202">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="82cfc-203">将打开 "详细报告" 页中的 "**检测**到" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="82cfc-203">The **Detections** tab in the detailed report page will open.</span></span>

![检测项选项卡](./media/security-docs/detections-tab.png)

<span data-ttu-id="82cfc-205">页面顶部的图表显示了已被阻止或审核的时间堆栈检测中的检测项。</span><span class="sxs-lookup"><span data-stu-id="82cfc-205">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="82cfc-206">底部的表列出了最近检测到的内容。</span><span class="sxs-lookup"><span data-stu-id="82cfc-206">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="82cfc-207">使用表中的以下信息来了解检测项的性质:</span><span class="sxs-lookup"><span data-stu-id="82cfc-207">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="82cfc-208">**检测到的文件**–文件 (通常为脚本或文档), 其内容触发了可疑的攻击活动</span><span class="sxs-lookup"><span data-stu-id="82cfc-208">**Detected file** – the file, typically a script or a document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="82cfc-209">**Rule** –描述规则旨在捕获的攻击活动的名称。</span><span class="sxs-lookup"><span data-stu-id="82cfc-209">**Rule** – name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="82cfc-210">阅读有关现有 ASR 规则的信息</span><span class="sxs-lookup"><span data-stu-id="82cfc-210">Read about existing ASR rules</span></span>
* <span data-ttu-id="82cfc-211">**源应用**–加载或执行了触发可疑攻击活动的内容的应用程序。</span><span class="sxs-lookup"><span data-stu-id="82cfc-211">**Source app** – the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="82cfc-212">这可能是合法的应用程序, 如 web 浏览器、Office 应用程序或 PowerShell 等系统工具</span><span class="sxs-lookup"><span data-stu-id="82cfc-212">This could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="82cfc-213">**Publisher** –发布源应用程序的供应商</span><span class="sxs-lookup"><span data-stu-id="82cfc-213">**Publisher** – the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="82cfc-214">查看设备 ASR 规则设置</span><span class="sxs-lookup"><span data-stu-id="82cfc-214">Review device ASR rule settings</span></span>

<span data-ttu-id="82cfc-215">在 "**攻击面降低规则**报告" 页上, 转到 "**配置**" 选项卡以查看各个设备的规则设置。</span><span class="sxs-lookup"><span data-stu-id="82cfc-215">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="82cfc-216">选择一个设备, 以获取有关每个规则是处于阻止模式、审核模式还是完全关闭状态的详细信息。</span><span class="sxs-lookup"><span data-stu-id="82cfc-216">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

!["配置" 选项卡](./media/security-docs/configuration-tab.png)

<span data-ttu-id="82cfc-218">Microsoft Intune 为你的 ASR 规则提供管理功能。</span><span class="sxs-lookup"><span data-stu-id="82cfc-218">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="82cfc-219">如果要更新设置, 请选择选项卡中的 "**配置设备**" 下的 "**启动**", 以在 Intune 上打开 "设备管理"。</span><span class="sxs-lookup"><span data-stu-id="82cfc-219">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="82cfc-220">从 ASR 规则中排除文件</span><span class="sxs-lookup"><span data-stu-id="82cfc-220">Exclude files from ASR rules</span></span>

<span data-ttu-id="82cfc-221">通过从检测中排除文件, 可以防止不需要的误报检测, 并更自信地在阻止模式下部署攻击面降低规则。</span><span class="sxs-lookup"><span data-stu-id="82cfc-221">By excluding files from detections, you can prevent unwanted false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="82cfc-222">虽然在 microsoft Intune 上对攻击面降低规则的文件排除项进行了管理, 但 microsoft 365 安全中心提供了一个分析工具, 可帮助您了解触发检测项的文件。</span><span class="sxs-lookup"><span data-stu-id="82cfc-222">While file exclusions for attack surface reduction rules are managed on Microsoft Intune, Microsoft 365 security center provides an analysis tool to help you understand the files that are triggering detections.</span></span> <span data-ttu-id="82cfc-223">它还有助于收集您可能想要排除的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="82cfc-223">It also helps collect the names of the files you might want to exclude.</span></span>

<span data-ttu-id="82cfc-224">若要开始分析检测项并收集文件以进行排除, 请转到**攻击面减少规则**报告页中的 "**添加排除**项" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="82cfc-224">To start analyzing detections and collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

![添加排除选项卡](./media/security-docs/add-exclusions-tab.png)

<span data-ttu-id="82cfc-226">该表列出了受攻击面减少规则检测到的所有文件名。</span><span class="sxs-lookup"><span data-stu-id="82cfc-226">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="82cfc-227">选择一个文件或多个文件后, 可以查看将这些文件添加到例外中的影响:</span><span class="sxs-lookup"><span data-stu-id="82cfc-227">Once you select a file or multiple files, you can review the impact of adding those files to your exceptions:</span></span>

* <span data-ttu-id="82cfc-228">减少检测项总次数</span><span class="sxs-lookup"><span data-stu-id="82cfc-228">The reduction in the total number of detections</span></span>
* <span data-ttu-id="82cfc-229">减少检测项影响的设备总数</span><span class="sxs-lookup"><span data-stu-id="82cfc-229">The reduction in the total number of devices affected by the detections</span></span>

<span data-ttu-id="82cfc-230">若要获取所选文件的完整路径的列表以供排除, 请选择 "**获取排除路径**"。</span><span class="sxs-lookup"><span data-stu-id="82cfc-230">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="82cfc-231">若要详细了解如何添加排除项和有关如何添加它们的详细说明, 请阅读[解决攻击面减少规则](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr)。</span><span class="sxs-lookup"><span data-stu-id="82cfc-231">For more information about exclusions and detailed instructions about how to add them, read [troubleshoot attack surface reduction rules](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr).</span></span>

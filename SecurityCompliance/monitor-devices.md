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
ms.openlocfilehash: 2984231caba574b8fa47b725ab77227f6ab5ae56
ms.sourcegitcommit: 468a7c72df3206333d7d633dd7ce1f210dc1ef3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "33302736"
---
# <a name="monitor-devices-in-microsoft-365-security"></a>在 Microsoft 365 安全中监视设备

确保你的设备在 Microsoft 365 安全中心中安全、保持最新并找出潜在威胁。

## <a name="view-device-alerts"></a>查看设备警报

从 Windows Defender ATP 获取有关你的设备上的入侵活动和其他威胁的最新警报 (适用于 E5 许可证)。 Microsoft 365 安全中心使用你首选的工作流在较高的层次上有效地监视这些警报。

### <a name="monitor-high-impact-alerts"></a>监视高影响警报

每个 Windows Defender ATP 警报都具有相应的严重性 (高、中、低或信息), 指示其对你的网络的潜在影响 (如果不采用无人参与)。  

使用**设备警报严重级别**卡专门关注更严重且可能需要立即响应的警报。 在此卡片中, 可以查看有关 Windows Defender 安全中心门户的详细信息。

![设备警报严重级别卡片](./media/security-docs/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>了解警报的来源

Windows Defender ATP 利用各种安全传感器和智能源中的数据来生成警报。 例如, 它可以使用 Windows Defender 防病毒和第三方反恶意软件中的检测信息, 以及通过 web 服务 API 提供的自定义威胁智能。

**设备警报检测**源卡按来源显示警报的分布情况。 此卡片可帮助您跟踪与某些来源 (尤其是自定义源) 相关的活动。 您还可以使用此操作来重点关注来自未配置为自动阻止恶意活动或组件的传感器发出的警报。

![设备警报检测源卡](./media/security-docs/device-alert-detection-sources.png)

在此卡片中, 可以查看有关 Windows Defender 安全中心门户的详细信息。

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>了解触发警报的威胁类型

Windows Defender ATP 将每个警报分类到一个类别, 表示攻击链中的某个阶段或威胁组件的类型。 例如, 检测到的威胁活动可能会分类到 "横向移动", 以指示活动试图访问网络上的其他设备, 并且在攻击者获得初始 foothold 时可能会发生此事件。 检测到威胁组件时, 可能会将其广泛分类为 "恶意软件", 或者更具体地说为 "勒索软件"、"凭据窃取" 或其他类型的恶意软件或不需要的软件。

**设备威胁类别**卡片显示了将警报分布到这些类别中的情况。 您可以使用此信息来确定威胁活动, 如凭据窃取时的尝试, 与社会工程手段的尝试相比, 这可能会产生更大的影响。 您还可以使用它来监视与勒索软件类似的潜在破坏性威胁。

![设备威胁类别卡片](./media/security-docs/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>监视活动警报

**设备警报状态**卡指示尚未解决且可能需要注意的警报的数量。 在此卡片中, 可以查看有关 Windows Defender 安全中心门户的详细信息。

![设备警报状态卡片](./media/security-docs/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>监视已解决警报的分类

解析 Window Defender ATP 警报时, 安全人员可以指定是否已将警报验证为:

* 真正的警报, 用于标识实际的违规活动或威胁组件
* 未正确检测到正常活动的假警报

**设备警报分类**卡显示已解决的警报是否已分类为 "真" 或 "假" 通知。 在此卡片中, 可以查看有关 Windows Defender 安全中心门户的详细信息。

注意: 在某些情况下, 分类信息对某些通知不可用。

![设备警报分类卡](./media/security-docs/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>监视已解决警报的确定

除了在解决方案解析过程中对警报是否为 true 或 false 进行分类之外, 您的安全人员可以确定在验证警报时发现的正常或恶意活动的类型。

**设备警报确定**卡显示为每个警报提供的决定, 具体如下:

* **apt.** –高级持久威胁, 表明检测到的活动或威胁组件是旨在获取受影响网络中的 foothold 的完善的安全漏洞的一部分  
* **恶意软件**–恶意文件或代码
* **安全人员**–安全人员执行的常规活动
* **安全测试**–旨在模拟实际威胁并预期触发安全传感器和生成警报的活动或组件
* 不**需要的软件**–不会被视为恶意的应用程序和其他软件, 但也违反了策略或可接受的使用标准
* **其他**–不属于所提供类型的任何其他决定

在此卡片中, 可以在 Windows Defender 安全中心中查看详细信息。

![设备警报确定卡](./media/security-docs/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>了解哪些设备有风险

**设备保护**显示设备的风险级别。 风险级别基于设备上的警报的类型和严重性等因素。

![设备保护卡](./media/security-docs/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>监视和报告 Intune 管理的设备的状态

以下监视和报告包含在 Intune 中注册的设备的数据。 不包括来自 unenrolled 设备的数据。 只有全局管理员才能查看这些卡片。

Intune 注册的设备数据包括:

* 设备合规性
* 具有活动恶意软件的设备
* 设备上的恶意软件类型
* 设备上的恶意软件
* 包含恶意软件检测的设备
* 包含恶意软件检测的用户

### <a name="monitor-device-compliance"></a>监视设备合规性

**设备符合性**显示在 Intune 中注册的设备数量符合配置策略。

![设备合规性卡](./media/security-docs/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>发现包含恶意软件检测的设备

**设备恶意软件检测**提供了包含恶意软件的 Intune 注册设备的数量, 这些设备尚未完全解决, 原因是挂起的操作有: 重新启动、完全扫描或手动用户操作, 或者更正操作未成功完成。

![设备恶意软件检测卡片](./media/security-docs/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>了解检测到的恶意软件的类型

**设备上的恶意软件类型**显示在 Intune 中注册的设备上检测到的不同类型的恶意软件。 您可以调查 Microsoft 365 安全中心中的每种类型。

![设备卡上的恶意软件类型](./media/security-docs/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>了解在你的设备上检测到的特定恶意软件

**设备上的恶意软件**提供在设备上检测到的特定恶意软件的列表。

![设备卡上的恶意软件](./media/security-docs/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>了解哪些设备具有最多的恶意软件

**包含恶意**软件检测的设备会显示哪些设备具有最多的恶意软件检测。 在 Microsoft 365 安全中心中, 可以调查恶意软件是处于活动状态、使用设备的用户及其在 Intune 中的管理状态。

![包含恶意软件检测卡片的设备](./media/security-docs/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>了解哪些用户具有最多恶意软件的设备

**具有恶意软件检测的用户**显示具有最多恶意软件检测到的设备的用户。 在 Microsoft 365 安全中心中, 可以查看为每个用户分配了多少个设备, 以及有关每个设备和恶意软件类型的详细信息。

![具有恶意软件检测卡片的用户](./media/security-docs/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a>监视和管理 ASR 规则部署和检测

[攻击面减少 (ASR) 规则](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)可帮助阻止使用者查找恶意软件时通常使用的操作和应用程序感染计算机。 这些规则控制何时以及如何运行可执行文件。 例如, 可以阻止 JavaScript 或 VBScript 启动下载的可执行文件、阻止来自 Office 宏的 Win32 API 调用或阻止从 USB 驱动器运行的进程。

![攻击面缩减卡片](./media/security-docs/attack-surface-reduction-rules.png)

**攻击面减少规则**卡提供了跨设备部署规则的概述。

卡片上的顶栏显示了以下部署模式中的设备总数:

* **块状模式**–至少有一个配置为阻止检测活动的规则的设备
* **审核模式**–没有设置任何规则的设备阻止检测到的活动, 但至少有一个规则集来审核检测到的活动  
* **off** -所有 ASR 规则关闭的设备

此卡片的下半部分按规则显示设备上的设置。 每条栏指示设置为阻止或审核检测或完全关闭规则的设备的数量。

### <a name="view-asr-detections"></a>查看 ASR 检测

若要查看有关网络中的 ASR 规则检测的详细信息, 请选择 "查看**受攻击面减少的规则**卡片上的**检测**"。 将打开 "详细报告" 页中的 "**检测**到" 选项卡。

![检测项选项卡](./media/security-docs/detections-tab.png)

页面顶部的图表显示了已被阻止或审核的时间堆栈检测中的检测项。 底部的表列出了最近检测到的内容。 使用表中的以下信息来了解检测项的性质:

* **检测到的文件**–文件 (通常为脚本或文档), 其内容触发了可疑的攻击活动
* **Rule** –描述规则旨在捕获的攻击活动的名称。 阅读有关现有 ASR 规则的信息
* **源应用**–加载或执行了触发可疑攻击活动的内容的应用程序。 这可能是合法的应用程序, 如 web 浏览器、Office 应用程序或 PowerShell 等系统工具
* **Publisher** –发布源应用程序的供应商

### <a name="review-device-asr-rule-settings"></a>查看设备 ASR 规则设置

在 "**攻击面降低规则**报告" 页上, 转到 "**配置**" 选项卡以查看各个设备的规则设置。 选择一个设备, 以获取有关每个规则是处于阻止模式、审核模式还是完全关闭状态的详细信息。

!["配置" 选项卡](./media/security-docs/configuration-tab.png)

Microsoft Intune 为你的 ASR 规则提供管理功能。 如果要更新设置, 请选择选项卡中的 "**配置设备**" 下的 "**启动**", 以在 Intune 上打开 "设备管理"。

### <a name="exclude-files-from-asr-rules"></a>从 ASR 规则中排除文件

Microsoft 365 security center 根据攻击面减少规则收集[您可能要](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive)从检测中排除的文件的名称。 通过排除文件, 可以减少误报检测, 并更自信地在阻止模式下部署攻击面降低规则。

排除在 microsoft Intune 上进行管理, 但 microsoft 365 安全中心提供了分析工具, 可帮助您了解这些文件。 若要开始收集要排除的文件, 请转到**攻击面减少规则**报告页中的 "**添加排除**" 选项卡。

>[!NOTE]  
>该工具将分析所有攻击面减少规则的检测项, 但[只有某些规则支持排除](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules)项。

![添加排除选项卡](./media/security-docs/add-exclusions-tab.png)

该表列出了受攻击面减少规则检测到的所有文件名。 您可以选择文件以查看排除它们的影响:

* 检测项的少多少
* 多少较少的设备报告检测

若要获取所选文件的完整路径的列表以供排除, 请选择 "**获取排除路径**"。

用于 ASR 规则**块凭据的日志从 Windows 本地安全颁发机构子系统 (lsass.exe)** 捕获源应用**lsass**(如检测到的文件)。 因此, 生成的排除路径列表将包含此文件。 若要排除触发此规则而不是**lsass.exe**的文件, 请使用源应用的路径, 而不是检测到的文件。

若要查找源应用程序, 请对此特定规则运行以下[高级搜寻查询](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection)(由规则 ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2): 

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>检查要排除的文件
在从 ASR 中排除文件之前, 我们建议您检查该文件以确定它是否确实不是恶意的。

若要查看文件, 请使用 Windows Defender 安全中心上的[文件信息页面](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/investigate-files-windows-defender-advanced-threat-protection)。 页面提供了传播信息以及 VirusTotal 防病毒检测比率。 您还可以使用页面提交文件进行深入分析。

若要在 Windows Defender 安全中心中查找检测到的文件, 请使用以下高级搜寻查询搜索所有 ASR 检测:

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

在结果中使用**SHA1**或**InitiatingProcessSHA1**在 Windows Defender 安全中心中使用通用搜索栏搜索文件。

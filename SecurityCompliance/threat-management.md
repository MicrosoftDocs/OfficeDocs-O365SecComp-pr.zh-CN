---
title: Threat management in the Office 365 Security &amp; Compliance Center
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 9/24/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0a73d5fa-b2c8-43e7-9ed4-61f0552b1c98
ms.collection:
- M365-security-compliance
description: 使用威胁管理来帮助控制和管理对组织数据的移动设备访问, 帮助保护组织不会丢失数据, 并帮助保护入站和出站邮件免受恶意软件和垃圾邮件的攻击。 您还可以使用威胁管理来保护您的域的信誉, 并确定发件人是否是您的域中的恶意欺骗帐户。
ms.openlocfilehash: 9c6c39b7edc008c4a44146fac8076897e705b5f5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259934"
---
# <a name="threat-management-in-the-office-365-security-amp-compliance-center"></a>Threat management in the Office 365 Security &amp; Compliance Center

使用威胁管理来帮助控制和管理对组织数据的移动设备访问, 帮助保护组织不会丢失数据, 并帮助保护入站和出站邮件免受恶意软件和垃圾邮件的攻击。 您还可以使用威胁管理来保护您的域的信誉, 并确定发件人是否是您的域中的恶意欺骗帐户。
  
## <a name="how-to-view-and-use-threat-management-in-the-security-amp-compliance-center"></a>如何在安全&amp;合规中心中查看和使用威胁管理

在 Office 365 中, 使用安全&amp;合规性中心管理组织中的威胁。
  
 **若要直接转到安全&amp;合规中心, 请执行以下操作:**
  
1. 转到 [https://protection.office.com](https://protection.office.com)。

2. 使用工作或学校帐户登录到 Office 365。

3. 在左窗格中, 选择 "**威胁管理**"。

    ![Office 365 安全&amp;合规中心威胁管理菜单](media/dca29ff2-ad6d-4c27-becb-b5947268d55a.png)
  
 **若要使用 Office 365 &amp;应用启动器转到安全合规中心, 请执行以下操作:**
  
1. 使用工作或学校帐户登录到 Office 365。

2. 在左上角的![Office 365](media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png)中选择应用启动器图标, 然后选择 " ** &amp;安全符合性**磁贴"。 

3. 在左窗格中, 选择 "**威胁管理**"。

## <a name="about-threat-management-in-office-365"></a>关于 Office 365 中的威胁管理

这些选项在安全&amp;合规性中心中的 "**威胁管理**" 下提供。
  
我们仍在为安全&amp;合规中心推出威胁管理, 因此您可能无法看到所有这些, 也可能会看到此处列出的选项不止这些。 在首次部署期间, 在有限的时间内, 将继续在 Exchange 管理中心 (EAC) 中提供其中一些 (例如反恶意软件、Dkim 和其他)。

在某些情况下, EAC 和安全&amp;合规性中心实现之间存在细微差异。 例如, 两个平台之间的垃圾邮件筛选器支持的字符不同。 提供了可在发生特定差异时提供详细信息的文章。
  
|**工具**|**Description**|
|:-----|:-----|
|**仪表板、威胁资源管理器和事件** <br/> |启用后, 这些窗格允许您管理 Office 365 分析和威胁调查和响应。 有关详细信息, 请参阅[Office 365 高级威胁防护计划 2](office-365-ti.md)。  <br/> |
|**邮件筛选** <br/> |微调和监控有助于防止 Office 365 中的垃圾邮件的设置。 创建允许和阻止名单, 确定谁正在欺骗你的域和原因, 以及配置和查看垃圾邮件筛选器策略。 有关详细信息, 请参阅[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)。  <br/> 您还可以设置策略以检查您的用户是否不会发送垃圾邮件。 例如, 如果用户的计算机受到编程为发送电子邮件的恶意软件感染, 则可能会发生这种情况。 若要了解如何阻止出站垃圾邮件, 请参阅[配置出站垃圾邮件策略](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx)。  <br/> 如果您当前遇到垃圾邮件问题, 则可以使用[垃圾邮件和恶意软件疑难解答](https://configure.office.com/Scenario.aspx?sid=73)。           |
|**反恶意软件** <br/> |防止在 Office 365 中传播到组织或从组织传播的病毒和间谍软件。 病毒是恶意软件程序, 这些程序在执行时复制自己并修改计算机上的其他程序和数据。 病毒在整个计算机中查找要感染的程序, 同时还从一台计算机共享到另一台计算机, 通常通过电子邮件进行共享。 间谍软件可收集你的个人信息, 例如登录信息, 并将其发送回其作者。 若要开始配置反恶意软件策略, 请参阅[配置反恶意软件策略](https://technet.microsoft.com/library/jj200745%28v=exchg.150%29.aspx)。  <br/> 如果您当前遇到恶意软件问题, 则可以使用[垃圾邮件和恶意软件疑难解答](https://configure.office.com/Scenario.aspx?sid=73)。           |
|**DKIM** <br/> |适用于更高级的 office 365 管理员, 但适用于所有 office 365 客户, 域密钥识别邮件 (DKIM) 可帮助确保其他电子邮件系统信任从 Office 365 发送的邮件。 DKIM 通过向从您的组织发送的电子邮件添加唯一的数字签名来实现此功能。 接收电子邮件的电子邮件系统可以使用此数字签名来帮助确定电子邮件是否合法。  <br/> 如果在 Office 365 中为您设置的默认设置应适用于大多数组织, 请不要担心。 如果您没有自己设置 DKIM, Office 365 将使用其默认策略和创建的密钥, 以便为您的域启用 DKIM。 此外, 如果您禁用 DKIM 签名, 在一段时间后, office 365 将自动为您的域启用 Office 365 默认策略。  <br/> 如果需要, 可以在安全&amp;合规中心中查看此页, 并查看当前是否为您的域启用了 DKIM 签名, 并且您可以查看 Office 365 使用的加密密钥的上次旋转时间。 您也可以手动旋转键。  <br/> **重要!** DKIM 是 Office 365 使用的一种电子邮件身份验证技术。 为最有效, DKIM 将与其他受支持的技术 (如发件人策略框架 (SPF) 和基于域的邮件身份验证、报告和一致性 (DMARC)) 一起使用。 这些基于域的身份验证技术共同帮助防止垃圾邮件和不必要的欺骗。<br/>  在使用安全&amp;合规中心对 DKIM 进行更改之前, 请先熟悉该技术及其工作方式。 若要开始, 请参阅[除了基础知识之外, 阻止 Office 365 中的垃圾邮件的方法](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365)。           |
|**安全附件**<br/>|[安全附件](atp-safe-attachments.md)是高级威胁防护的一部分。 启用后, 电子邮件附件将在特殊的独立环境中打开, 并在将其发送到收件人收件箱之前与 Office 365 分开。 安全附件旨在帮助检测恶意附件, 即使在防病毒签名可用之前也是如此。 若要了解详细信息, 请参阅[Office 365 中的安全附件](atp-safe-attachments.md)。<br/> |
|**安全链接** <br/> |[安全链接](atp-safe-links.md)是高级威胁防护的一部分。 安全链接有助于防止用户在电子邮件或 Office 文档中以指向被识别为恶意的网站的 url。 若要了解详细信息, 请参阅[Office 365 中的安全链接](atp-safe-links.md)。<br/> |
|**隔离**<br/>|为 Office 365 中的传入电子邮件设置[隔离](http://go.microsoft.com/fwlink/p/?LinkID=809005), 其中已被筛选为垃圾邮件、批量、网络钓鱼和恶意软件邮件的邮件可以保留供以后查看。 用户和管理员都可以使用隔离邮件。 用户只能在隔离中处理自己的已筛选邮件。 管理员可以搜索和管理所有用户的隔离邮件。  <br/> |
|**高级威胁** <br/> |查看 "[威胁防护状态报告](https://support.office.com/article/View-the-reports-for-Advanced-Threat-Protection-E47E838C-D99E-4C0B-B9AA-E66C4FAE902F#advancedthreats)", 以查看 Exchange Online Protection 和高级威胁防护发现和阻止的恶意内容的相关信息。  <br/> |

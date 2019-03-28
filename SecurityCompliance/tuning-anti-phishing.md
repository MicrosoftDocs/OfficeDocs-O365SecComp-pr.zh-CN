---
title: 优化 Office 365 中的反网络钓鱼保护
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 管理员可以了解如何确定仿冒邮件的原因以及在将来阻止更多的网络钓鱼邮件的原因。
ms.openlocfilehash: efda9e16c23e4533b6951e43ac085b7640e84576
ms.sourcegitcommit: 8a65a29aa3bfe5dcad0ff152a7cd795e02877dd9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2019
ms.locfileid: "30937816"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a>优化 Office 365 中的反网络钓鱼保护

尽管 Office 365 附带了在默认情况下启用的各种反网络钓鱼功能, 但有些网络钓鱼邮件仍可能会到达您的邮箱。 本主题介绍您可以执行哪些操作来发现仿冒邮件的访问原因, 以及您可以采取什么措施来调整 Exchange Online 组织中的反网络钓鱼设置,_而不会意外地使事情更糟_。

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>首先要做的第一件事: 处理任何受损帐户, 并确保阻止任何更多的网络钓鱼邮件

如果收件人的帐户因仿冒邮件而受损, 请按照在[Office 365 中响应受损电子邮件帐户](responding-to-a-compromised-email-account.md)中的步骤操作。

如果你的订阅包括高级威胁防护 (ATP), 则可以使用[Office 365 威胁智能](office-365-ti.md)标识也收到网络钓鱼邮件的其他用户。 您还可以使用其他选项阻止网络钓鱼邮件:

- [ATP 安全链接](set-up-atp-safe-links-policies.md)

- [ATP 安全附件](set-up-atp-safe-attachments-policies.md)

- [ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)。 请注意, 可以暂时将策略中的**高级网络钓鱼阈值**从**Standard**提高到**主动**、**更主动**或**最严格**的。

验证这些 ATP 功能是否已打开。

## <a name="report-the-phishing-message-to-microsoft"></a>向 Microsoft 报告网络钓鱼邮件

在调整用于保护 Office 365 中所有客户的筛选器时, 报告网络钓鱼邮件非常有帮助。

将仿冒邮件作为新的 (否则为空邮件) 的_附件_发送到**phish@office365.microsoft.com**。 不要直接转发原始邮件;否则, 我们无法检查原始邮件头。 或者, 您可以在 outlook 或 web 上的 outlook (以前称为 Outlook web App) 中使用[报告邮件](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in)加载项。

有关详细信息, 请参阅[将垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。

## <a name="inspect-the-message-headers"></a>检查邮件头

您可以检查网络钓鱼邮件的标头, 以查看是否有任何可以执行的操作, 以防止更多的网络钓鱼邮件进入。 换句话说, 检查邮件头可以帮助您确定组织中负责允许网络钓鱼邮件的任何设置。

具体来说, 应检查邮件头中的**X-Forefront-反垃圾邮件报告**标头字段, 以了解垃圾邮件筛选判定 (SFV) 值中跳过的垃圾邮件或网络钓鱼筛选的指示。 跳过筛选的邮件将具有一个条目`SCL:-1`, 这意味着您的设置允许此邮件通过覆盖由该服务确定的垃圾邮件或网络钓鱼 verdicts。 有关如何获取邮件头以及所有可用的反垃圾邮件和反网络钓鱼邮件头的完整列表的详细信息, 请参阅[反垃圾邮件邮件头](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers)。

## <a name="best-practices-to-stay-protected"></a>保持受保护状态的最佳做法

- 在每月的基础上, 运行[office 365 安全分数](office-365-secure-score.md)以评估 office 365 组织的安全设置。

- 定期查看[欺骗智能报告](learn-about-spoof-intelligence.md)并[在反网络钓鱼策略中启用反欺骗保护](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy)以**隔离**可疑邮件, 而不是将其传递到用户的 "垃圾邮件" 文件夹。

- 定期查看[威胁防护状态报告](view-reports-for-atp.md#threat-protection-status-report)。

- 某些客户通过将自己的域放在反垃圾邮件策略中的 "允许发件人" 或 "允许域" 列表中, 在无意中允许网络钓鱼邮件。 如果选择执行此操作, 则必须小心使用。 虽然此配置将允许某些合法邮件通过, 但它还会允许由 Office 365 垃圾邮件和/或网络钓鱼筛选器通常阻止的恶意邮件。

  若要处理受 office 365 (误报) 阻止的合法邮件 (涉及域中的发件人), 最佳方法是在 DNS 中为 office 365 中的_所有_电子邮件域完全和完全配置 SPF、DKIM 和 DMARC 记录:

  - 验证您的 SPF 记录是否标识了您的域中的发件人的_所有_电子邮件源 (不要忘记第三方服务!)。

  - 使用硬故障 (\-) 以确保配置为这样做的电子邮件系统拒绝未经授权的发件人。 您可以使用[欺骗智能](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence)来帮助标识使用您的域的发件人, 以便您可以在 SPF 记录中包括授权的第三方发件人。

  有关配置说明, 请参阅:
  
  - [在 Office 365 中设置 SPF 以防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)

  - [使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)

- 如果可能, 我们建议您将您的域的电子邮件直接传递到 Office 365。 换言之, 将您的 office 365 域的 MX 记录指向 office 365。 Exchange Online Protection (EOP) 能够在将其邮件直接传递到 Office 365 时为你的云用户提供最佳保护。 如果您必须在 EOP 前使用第三方电子邮件清洁系统, 请确保已按照[此处](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)的指导进行。

- 多重因素身份验证 (MFA) 是防止受损帐户的一种非常好的方法。 强烈考虑为所有用户启用 MFA。 对于分阶段的方法, 先在为每个人启用 mfa 之前为最敏感的用户 (管理员、高级管理人员等) 启用 mfa。 有关说明, 请参阅[设置多因素身份验证](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)。

- 将规则转发给外部收件人通常由攻击者用来提取数据。 使用 "查看[Office 365 安全分数](office-365-secure-score.md)中的**邮箱转发规则**" 信息查找甚至阻止外部收件人的转发规则。 有关详细信息, 请参阅[通过安全分数缓解客户端外部转发规则](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)。

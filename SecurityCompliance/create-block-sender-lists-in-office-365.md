---
title: 在 Office 365 中创建阻止发件人列表
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 阻止发件人列表选项包括 Outlook 阻止的发件人、反垃圾邮件发件人/域阻止列表、IP 阻止列表和 Exchange 传输规则 (Etr) 也称为邮件流规则。
ms.openlocfilehash: 9933cb79b7dce949384815a7b2ed8a9ac8a7824b
ms.sourcegitcommit: f96029928a6cdd141783026d57bc2179d7963af6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2019
ms.locfileid: "35017684"
---
# <a name="create-block-sender-lists-in-office-365"></a>在 Office 365 中创建阻止发件人列表

有时, 有必要阻止发件人发来的不需要的电子邮件。 有几种方法可供选择。 这些选项包括 Outlook 阻止的发件人、反垃圾邮件发件人/域阻止列表、IP 阻止列表和 Exchange 传输规则 (Etr, 也称为邮件流规则)。

> [!NOTE]
> 虽然可以使用组织阻止列表来解决漏报 (丢失的垃圾邮件), 但还应将那些候选人提交给 Microsoft 进行分析。 使用阻止列表管理漏报会显著增加管理开销。 如果要使用阻止列表来实现此目的, 则在准备好时, 还需要保留将[垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)的文章。

配置被阻止的发件人列表的适当方法取决于影响的范围。 对于单用户影响, 正确的解决方案可以是使用 Outlook 阻止的发件人, 但如果多个用户或所有用户受到影响, 则其他选项之一更合适。

## <a name="options-from-least-to-broadest-scope"></a>从最小到最广泛的范围的选项

创建阻止列表时, 一定要根据影响的范围 (将影响多少人) 选择适当的方法, 以使其与阻止方法的广度相匹配。 下面列出的选项按作用域和广度进行排序。 列表从窄到范围, 但阅读完整建议的*细节*。

- Outlook 阻止的发件人
- 反垃圾邮件策略: 发件人/域阻止列表
- Exchange 传输规则 (Etr 也称为邮件流规则)
- 反垃圾邮件策略: IP 阻止列表

## <a name="use-outlook-blocked-senders"></a>使用 Outlook 阻止的发件人

如果只有少量用户受到影响, 则应使用 Outlook 阻止的发件人, 因为这只会影响向其发送邮件。

> [!IMPORTANT]
> 如果不需要的邮件是来自可信且可识别的来源的新闻快递, 则取消订阅该电子邮件是另一个选项, 阻止用户将来收到该电子邮件。

设置此设置的步骤在[Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46)和[outlook 客户端](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)之间有所不同。 **当邮件由于被阻止的发件人而成功被阻止时, 您将在 X Forefront-反垃圾邮件中看到 SFV: BLK** , 这表明该邮件已被阻止。

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a>使用反垃圾邮件策略发件人/域阻止列表

当多个用户受到影响时, 范围将变宽, 您需要使用公司范围内的发件人/域阻止列表反垃圾邮件策略。 可在[配置垃圾邮件筛选器策略](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies)文档中找到详细步骤。 通过此方法阻止的任何邮件都将遵循策略中配置的垃圾邮件操作。

## <a name="use-exchange-transport-rules-etrs-to-block-specific-senders"></a>使用 Exchange 传输规则 (Etr) 阻止特定发件人

如果需要阻止发送到特定用户或整个组织的邮件, 则可以使用 Etr (也称为邮件流规则)。 Etr 更灵活, 因为它们可以触发发件人电子邮件地址或域, 以及邮件中的关键词语和其他属性。 这种灵活性使您能够创建部分到完整的块。 [请单击以查看创建 ETR 的步骤, 也称为邮件流规则](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages)。

> [!IMPORTANT]
> 创建的规则非常简单, 因为这** 会导致所使用的条件尽可能具体, 这一点非常重要。 此外, 请确保对所创建的规则启用审核并进行测试, 以确保一切按预期工作。

## <a name="use-anti-spam-policy-ip-block-lists"></a>使用反垃圾邮件策略 IP 阻止列表

如果不能使用其他选项之一阻止发件人,*则*可以使用反垃圾邮件策略 IP 阻止列表。 [可以在配置连接筛选器策略一文中找到详细步骤](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy)。 建议不要将阻止 Ip 的列表保持在*最少*, 并且在此处使用 IP 地址范围,*不*建议这样做。

您应该*特别*避免添加属于消费者服务或共享基础结构的 ip 地址范围, 还应确保在定期维护过程中查看允许的 ip 地址列表。 **由于允许条目可以打开用于攻击的路由, 因此您必须仔细管理此列表, 并定期删除不再需要的允许条目。** 此外, 如果您将允许在安全发件人列表中使用, 请务必阅读并了解在*[Office 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)* 中的风险和注意事项。
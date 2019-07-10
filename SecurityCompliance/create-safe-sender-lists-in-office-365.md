---
title: 在 Office 365 中创建安全发件人列表
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 4/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 如果您想要确保收到来自特定发件人的邮件, 因为您信任这些邮件及其邮件, 您可以在 Exchange 管理中心的垃圾邮件筛选器策略中调整您的允许列表。
ms.openlocfilehash: f0397ce3d26f6c539b3d7d663298c468e1155161
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599978"
---
# <a name="create-safe-sender-lists-in-office-365"></a>在 Office 365 中创建安全发件人列表

如果您想要确保用户收到来自特定发件人或发件人的电子邮件, 因为您信任这些发件人或发件人的邮件, 则可以从中选择多个可用方法。 这些选项包括 Exchange 传输规则 (Etr)、Outlook 安全发件人、IP 允许列表、反垃圾邮件发件人/域允许列表。

> [!IMPORTANT]
> 虽然可以使用组织允许列表来解决误报, 但应将其视为临时解决方案, 并尽可能避免。 建议不要通过使用 "允许列表" 来管理误报, 因为这可能会在无意中将组织打开为欺骗、模拟和其他攻击。 如果要使用允许列表实现此目的, 则在准备就绪时, 您将需要警惕并保留将[垃圾邮件、非垃圾邮件和网络钓鱼邮件提交给 Microsoft 进行分析](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)的文章。

配置安全发件人列表的建议方法是使用 Exchange 传输规则 (Etr), 因为这会提供最大的灵活性, 以确保仅允许正确的邮件。 *反垃圾邮件策略电子邮件地址*和*基于域的允许列表*不像*基于 IP 地址的列表*那样安全, 因为域很容易被欺骗。 但是, 基于反垃圾邮件策略的允许列表还显示了风险, 因为它们将允许通过该 IP 发送的任何域绕过垃圾邮件筛选。 请务必小心, 并谨慎监视所做的*任何*异常。

> [!IMPORTANT]
> 有关如何创建**被阻止的发件人列表**的信息在[这里](create-block-sender-lists-in-office-365.md)。

## <a name="options-from-most-to-least-recommended"></a>从最多到最小建议的选项

应始终限制允许列表, 因为它们会绕过许多安全措施。 您必须重新检查所有允许列表作为标准维护的一部分, 以便您知道允许绕过的用户。 建议尽可能使用限制性 Etr。

- Exchange 传输规则 (Etr 也称为邮件流规则)
- Outlook 安全发件人
- 反垃圾邮件策略: IP 允许列表
- 反垃圾邮件策略: 发件人/域允许列表

## <a name="using-exchange-transport-rules-etrs-to-allow-specific-senders-recommended"></a>使用 Exchange 传输规则 (Etr) 允许特定发件人 (推荐)

若要确保仅允许组织中的合法邮件, 条件应为以下项之一:

- 使用发送域的发件人身份验证状态。 这是通过检查身份验证结果标头来确保它包含 "dmarc = pass" 或 "dmarc = bestguesspass" 来实现的。 这可确保发送域已通过身份验证, 且未被欺骗。 单击以了解有关[SPF](https://docs.microsoft.com/en-us/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)和[DMARC](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-dmarc-to-validate-email)电子邮件身份验证的详细信息。

- 或者, 如果发送域没有身份验证, 请使用发送域*和*发送 IP (或 IP 范围)。 确保尽可能地*限制*您的安全, 目标是尽可能安全地执行此操作。 *不*建议使用大于/24 的 IP 范围。 避免添加属于消费者服务或共享基础结构的 IP 地址范围。

> [!IMPORTANT]
> 如果允许某个 IP 地址为 NATted, 您应该知道该 NAT 池中涉及的计算机, 以便知道您的允许的范围。 请注意, IP 地址可能会更改, 并且 NAT 参与者也可能会更改。 您必须重新检查所有允许列表, 包括 IP 允许作为标准维护的一部分。

- (*可选*) 添加邮件来自组织外部的条件 (这是隐式的, 但可以将其作为条件添加到可能未正确配置的本地服务器的条件中)。

- *(可选*) 如果您可以确定电子邮件主题或正文中的任何唯一关键字或短语, 请将此信息用作附加条件, 以进一步限制邮件流规则允许的电子邮件。

规则上的操作必须遵循以下模式:

1. 将垃圾邮件可信度 (SCL) 设置为-1 (绕过垃圾邮件筛选)。

2. 添加 X 标头, 以指示规则执行的操作。 在下面的示例中, 您可以添加一个简单的标头 "X-ETR: 绕过经过`contoso.com`身份验证的发件人的垃圾邮件筛选"。 如果在此规则中有多个域, 则可以根据需要更改标题文本。**当邮件由于 ETR 而跳过筛选时, 它会在 X-Forefront-反垃圾邮件报告标头中标记 SFV: SKN**(**如果它位于 IP 允许列表中, 它还会标记 IPV: CAL**)。 这将帮助进行故障排除。

![用于绕过垃圾邮件筛选的 GUI。](media/1-AllowList-SkipFilteringFromContoso.png)

> [!CAUTION]
> 不要将邮件流规则配置为只使用*发件人域*作为跳过垃圾邮件筛选的条件。 此方法会显著增加垃圾邮件制造者可以欺骗发送域 (或模拟完整电子邮件地址)。跳过所有垃圾邮件筛选、发件人身份验证检查, 邮件将会在个人的 "收件箱" 中收到。

![如何将 SCL 设置为减号-1。](media/2-AllowList-SetsSCLMinus1.png)

请勿将您拥有的域或受欢迎的域 (例如`microsoft.com`) 作为条件添加到邮件流规则。 这被认为是高风险, 因为它会给不良参与者带来机会, 以向您发送邮件, 否则将被筛选掉。

[请单击以查看创建 ETR 的步骤, 也称为邮件流规则](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages)。

## <a name="use-outlook-safe-senders-end-user-managed"></a>使用 Outlook 安全发件人 (最终用户托管)

最终用户也可以通过 Outlook 安全发件人来允许发送地址, 而不是在全局范围内授权地址、域或 IP 地址。 设置此设置的步骤在[Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46)和[outlook 客户端](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)之间有所不同。 **如果由于安全发件人而成功授权邮件, 则会在 X-Forefront-反垃圾邮件报告中看到 SFV: SFE** , 这表示将绕过垃圾邮件/欺骗/网络钓鱼筛选。

## <a name="use-anti-spam-policy-ip-allow-lists"></a>使用反垃圾邮件策略 IP 允许列表

如果在验证发件人身份验证时不能使用 Etr 全局允许特定发件人, 或者通过将一个域和 IP 与它们结合在一起, 则下一个最佳选择是将发件人添加到*反垃圾邮件策略 IP 允许列表*中。 [可以在配置连接筛选器策略文档中找到详细步骤](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy)。 一定要将允许的 IP 地址列表保持为最小, 并避免使用 IP 地址范围。 避免添加属于消费者服务或共享基础结构的 IP 地址范围, 还应*确保*定期查看允许的 IP 地址列表, 并删除不再需要的 ip 地址。

> [!CAUTION]
> 将反垃圾邮件策略配置为仅允许基于发件人 IP 地址将导致跳过允许规则中来自该 IP 地址的所有邮件的垃圾邮件筛选。 这将产生较差的参与者向您发送邮件的高风险, 否则将被筛选掉。此方法还会跳过所有垃圾邮件筛选、发件人身份验证检查和邮件发送到用户的收件箱中, 从而增加风险。

## <a name="use-anti-spam-policy-senderdomain-allow-lists"></a>使用反垃圾邮件策略发件人/域允许列表

最不理想的选择是通过发件人/域进行授权。 应*尽可能*避免此选项, 因为它会完全绕过垃圾邮件/欺骗/网络钓鱼保护, 并且不会评估发件人身份验证。 此方法可提高从错误的参与者接收邮件的风险, 并且仅在测试时暂时和仅进行建议。 可在[配置垃圾邮件筛选器策略](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies)文档中找到详细步骤。

这些列表的最大限制约为1000个条目。

> [!CAUTION]
> 将反垃圾邮件策略配置为*允许发件人/允许域*会导致邮件跳过来自允许列表中的发件人或 b 的来自允许域的发件人发来的邮件的垃圾邮件筛选。 此方法会显著增加垃圾邮件制造者可以欺骗发送域 (或模拟完整电子邮件地址) 的邮件, 该邮件会跳过所有垃圾邮件筛选、发件人身份验证检查, 并将邮件直接发送到用户的收件箱。
> 
> 不要将拥有或受欢迎域的域 (例如`microsoft.com`) 作为一个条件添加到邮件流规则。 此方法被认为是高风险, 因为它会给不良参与者带来机会, 以向您发送邮件, 否则将被筛选掉, 从而增加风险。

> [!IMPORTANT]
> 有关如何创建**被阻止的发件人列表**的信息在[这里](create-block-sender-lists-in-office-365.md)。

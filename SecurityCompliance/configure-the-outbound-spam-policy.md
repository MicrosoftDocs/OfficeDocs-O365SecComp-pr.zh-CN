---
title: 在 Office 365 中配置出站垃圾邮件策略通知
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/10/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Office 365 中修改出站垃圾邮件检测的通知设置。
ms.openlocfilehash: c48b6cd634417a00040fb5479313782b44f6aa8d
ms.sourcegitcommit: 81b3bff27bc60235a38004c5b0297ac454331b25
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "36822512"
---
# <a name="configure-outbound-spam-policy-notifications-in-office-365"></a>在 Office 365 中配置出站垃圾邮件策略通知

如果您使用出站垃圾邮件筛选来发送出站电子邮件，那么将始终启用该服务，从而保护使用此服务的组织及其目标收件人。 与入站筛选类似，出站垃圾邮件筛选由连接筛选和内容筛选构成，但出站筛选设置无法配置。 如果出站邮件确定为垃圾邮件，则会通过高风险传送池进行路由，这会降低正常出站 IP 池添加到阻止列表的可能性。 如果客户继续通过该服务发送出站垃圾邮件，其邮件的发送将受到阻止。

虽然您无法禁用或更改出站垃圾邮件筛选，但您可以配置以下出站垃圾邮件通知设置：

- **发送可疑邮件的副本**：这些邮件被标记为垃圾邮件（无论 SCL 分级），并且不会被筛选器拒绝，而是通过更高的风险传递池进行路由。 您可以使用 exchange online PowerShell 或 exchange online Protection PowerShell 中的 exchange 管理中心（EAC）或** \*-HostedOutboundSpamFilterPolicy** cmdlet 为这些检测到的邮件指定添加收件人。 请注意，收件人被添加为**Bcc**收件人（"**发**件人" 和 "**收件人" 字段是**原始发件人和收件人）。

- **阻止发件人时发送通知**：当来自特定用户的大量垃圾邮件时，将禁用该用户发送电子邮件。 默认情况下，管理员会收到通知，但您可以在 Office 365 安全 & 合规性中心中使用**限制发送电子邮件**[通知策略](alert-policies.md)的用户来配置其他通知收件人。

  若要查看此通知的样式，请参阅[发件人被阻止发送出站垃圾邮件时的示例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)。 有关重新启用的详细信息，请参阅[Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 估计完成时间：5 分钟

- 若要打开安全与合规中心，请参阅[转到 Office 365 安全与合规中心](go-to-the-securitycompliance-center.md)。

- 若要打开 EAC，请参阅 exchange [online 中的 exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)或 Exchange [online Protection 中的 exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要打开 Exchange Online PowerShell，请参阅[连接到 Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 若要打开 Exchange Online Protection PowerShell，请参阅[连接到 Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)。

- 您的帐户需要先分配权限，然后才能执行此过程。 若要查看所需的权限，请参阅[Office 365 Security & 合规性中心](permissions-in-the-security-and-compliance-center.md)中 "权限" 中的 "管理通知" 角色条目。

## <a name="use-the-eac-to-configure-additional-recipients-for-outbound-spam-messages"></a>使用 EAC 为出站垃圾邮件配置其他收件人

1. 在 EAC 中，转到 "**保护** \> **出站垃圾邮件**"。

2. 选择名为 "**默认**" 的策略， **** ![然后单击 "](media/ITPro-EAC-EditIcon.png)编辑编辑图标"。

3. 在打开的 "属性" 页中，验证是否已选择 "**出站垃圾邮件首**选项" 选项卡，然后配置以下设置：

   将**所有可疑的出站电子邮件的副本发送到以下电子邮件地址或地址**：选中 "" 复选框，并输入应添加到检测到的邮件的 "**密件抄送**" 字段的一个或多个管理员的电子邮件地址。 使用分号（;）分隔多个电子邮件地址。

   完成后，单击“保存”****。

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-additional-recipients-for-outbound-spam-messages"></a>使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 为出站垃圾邮件配置其他收件人

若要为出站垃圾邮件启用和配置其他收件人，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients <recipients>
```

- 若要指定覆盖所有现有值的收件人，请使用`emailaddress1,emailaddress2,...emailaddressN`语法。

- 若要在不影响其他条目的情况下选择性地添加或删除`@{Add="\<emailaddress1\>","\<emailaddress2\>"...; Remove="\<emailaddress1\>","\<emailaddress2\>"...}`收件人，请使用语法。

本示例为出站垃圾邮件的密件抄送收件人启用和配置 chris@contoso.com、laura@contoso.com 和 julia@contoso.com。

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients chris@contoso.com,laura@contoso.com,julia@contoso.com
```

本示例将 michelle@contoso.com 添加为其他密件抄送收件人。

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Add=michelle@contoso.com}
```

本示例从密件抄送收件人列表中删除 chris@contoso.com 和 julia@contoso.com。

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Remove='chris@contoso.com','julia@contoso.com'}
```

有关语法和参数的详细信息，请参阅[HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)。

**注意**：运行命令`Get-HostedOutboundSpamFilterPolicy | Format-List`以查看*BccSuspiciousOutboundMail*和*BccSuspiciousOutboundAdditionalRecipients*属性的当前值。

## <a name="use-the-security--compliance-center-to-configure-notifications-when-a-sender-is-blocked"></a>当发件人被阻止时，使用安全 & 合规性中心配置通知

1. 在安全 & 合规性中心中，转到**警报** \> **警报策略**。

2. 查找并选择名为**User 限制的用于发送电子邮件**的策略。

3. 在 "飞出" 打开的情况下，单击 "**编辑策略**"。

4. 在出现的 "**编辑收件人**" 页中，配置以下设置：

   - **发送电子邮件通知**：验证是否已选择 **"打开"** 。

   - **电子邮件收件人**：默认情况下， **TenantAdmins**是此处的唯一值。 若要添加其他收件人，请单击此框中的空白点，开始键入收件人，并在其名称解析时选择收件人。 若要删除收件人，请单击其名称旁边的 " **X** "。

   - **每日通知限制**：默认值为**无限制**，但您可以配置从1到200的各种限制。

   完成后，单击“保存”****。

## <a name="for-more-information"></a>详细信息

[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)

[反垃圾邮件保护常见问题](anti-spam-protection-faq.md)

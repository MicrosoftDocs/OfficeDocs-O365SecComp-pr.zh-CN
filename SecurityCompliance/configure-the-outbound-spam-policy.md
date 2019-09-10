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
# <a name="configure-outbound-spam-policy-notifications-in-office-365"></a><span data-ttu-id="3eee1-103">在 Office 365 中配置出站垃圾邮件策略通知</span><span class="sxs-lookup"><span data-stu-id="3eee1-103">Configure outbound spam policy notifications in Office 365</span></span>

<span data-ttu-id="3eee1-104">如果您使用出站垃圾邮件筛选来发送出站电子邮件，那么将始终启用该服务，从而保护使用此服务的组织及其目标收件人。</span><span class="sxs-lookup"><span data-stu-id="3eee1-104">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients.</span></span> <span data-ttu-id="3eee1-105">与入站筛选类似，出站垃圾邮件筛选由连接筛选和内容筛选构成，但出站筛选设置无法配置。</span><span class="sxs-lookup"><span data-stu-id="3eee1-105">Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering, however the outbound filter settings are not configurable.</span></span> <span data-ttu-id="3eee1-106">如果出站邮件确定为垃圾邮件，则会通过高风险传送池进行路由，这会降低正常出站 IP 池添加到阻止列表的可能性。</span><span class="sxs-lookup"><span data-stu-id="3eee1-106">If an outbound message is determined to be spam, it is routed through the higher risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span> <span data-ttu-id="3eee1-107">如果客户继续通过该服务发送出站垃圾邮件，其邮件的发送将受到阻止。</span><span class="sxs-lookup"><span data-stu-id="3eee1-107">If a customer continues to send outbound spam through the service, they will be blocked from sending messages.</span></span>

<span data-ttu-id="3eee1-108">虽然您无法禁用或更改出站垃圾邮件筛选，但您可以配置以下出站垃圾邮件通知设置：</span><span class="sxs-lookup"><span data-stu-id="3eee1-108">Although you can't disable or change outbound spam filtering, you can configure the following outbound spam notification settings:</span></span>

- <span data-ttu-id="3eee1-109">**发送可疑邮件的副本**：这些邮件被标记为垃圾邮件（无论 SCL 分级），并且不会被筛选器拒绝，而是通过更高的风险传递池进行路由。</span><span class="sxs-lookup"><span data-stu-id="3eee1-109">**Send copies of suspicious messages**: These messages are marked as spam (regardless of the SCL rating) and are not rejected by the filter, but are routed through the higher risk delivery pool.</span></span> <span data-ttu-id="3eee1-110">您可以使用 exchange online PowerShell 或 exchange online Protection PowerShell 中的 exchange 管理中心（EAC）或\*\* \*-HostedOutboundSpamFilterPolicy\*\* cmdlet 为这些检测到的邮件指定添加收件人。</span><span class="sxs-lookup"><span data-stu-id="3eee1-110">You can use the Exchange admin center (EAC) or the **\*-HostedOutboundSpamFilterPolicy** cmdlets in Exchange Online PowerShell or Exchange Online Protection PowerShell to specify addition recipients for these detected messages.</span></span> <span data-ttu-id="3eee1-111">请注意，收件人被添加为**Bcc**收件人（"**发**件人" 和 "**收件人" 字段是**原始发件人和收件人）。</span><span class="sxs-lookup"><span data-stu-id="3eee1-111">Note that the recipients are added as **Bcc** recipients (the **From** and **To** fields are the original sender and recipient).</span></span>

- <span data-ttu-id="3eee1-112">**阻止发件人时发送通知**：当来自特定用户的大量垃圾邮件时，将禁用该用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3eee1-112">**Send notifications when a sender is blocked**: When a significant amount of spam is coming from a particular user, the user is disabled from sending email messages.</span></span> <span data-ttu-id="3eee1-113">默认情况下，管理员会收到通知，但您可以在 Office 365 安全 & 合规性中心中使用**限制发送电子邮件**[通知策略](alert-policies.md)的用户来配置其他通知收件人。</span><span class="sxs-lookup"><span data-stu-id="3eee1-113">Admins are notified by default, but you can use the **User restricted from sending email** [alert policy](alert-policies.md) in the Office 365 Security & Compliance Center to configure additional notification recipients.</span></span>

  <span data-ttu-id="3eee1-114">若要查看此通知的样式，请参阅[发件人被阻止发送出站垃圾邮件时的示例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="3eee1-114">To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).</span></span> <span data-ttu-id="3eee1-115">有关重新启用的详细信息，请参阅[Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3eee1-115">For information about getting re-enabled, see [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3eee1-116">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="3eee1-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3eee1-117">估计完成时间：5 分钟</span><span class="sxs-lookup"><span data-stu-id="3eee1-117">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="3eee1-118">若要打开安全与合规中心，请参阅[转到 Office 365 安全与合规中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="3eee1-118">To open the Security & Compliance Center, see [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span>

- <span data-ttu-id="3eee1-119">若要打开 EAC，请参阅 exchange [online 中的 exchange 管理中心](https://docs.microsoft.com/Exchange/exchange-admin-center)或 Exchange [online Protection 中的 exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="3eee1-119">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="3eee1-120">若要打开 Exchange Online PowerShell，请参阅[连接到 Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3eee1-120">To open Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3eee1-121">若要打开 Exchange Online Protection PowerShell，请参阅[连接到 Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3eee1-121">To open Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3eee1-122">您的帐户需要先分配权限，然后才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="3eee1-122">Your account needs to be assigned permissions before you can perform this procedure.</span></span> <span data-ttu-id="3eee1-123">若要查看所需的权限，请参阅[Office 365 Security & 合规性中心](permissions-in-the-security-and-compliance-center.md)中 "权限" 中的 "管理通知" 角色条目。</span><span class="sxs-lookup"><span data-stu-id="3eee1-123">To see what permissions you need, see the "Manage Alerts" role entry in [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-eac-to-configure-additional-recipients-for-outbound-spam-messages"></a><span data-ttu-id="3eee1-124">使用 EAC 为出站垃圾邮件配置其他收件人</span><span class="sxs-lookup"><span data-stu-id="3eee1-124">Use the EAC to configure additional recipients for outbound spam messages</span></span>

1. <span data-ttu-id="3eee1-125">在 EAC 中，转到 "**保护** \> **出站垃圾邮件**"。</span><span class="sxs-lookup"><span data-stu-id="3eee1-125">In the EAC, go to **Protection** \> **Outbound spam**.</span></span>

2. <span data-ttu-id="3eee1-126">选择名为 "**默认**" 的策略， \*\*\*\* ![然后单击 "](media/ITPro-EAC-EditIcon.png)编辑编辑图标"。</span><span class="sxs-lookup"><span data-stu-id="3eee1-126">Select the policy named **Default**, and then click **Edit** ![Edit icon](media/ITPro-EAC-EditIcon.png).</span></span>

3. <span data-ttu-id="3eee1-127">在打开的 "属性" 页中，验证是否已选择 "**出站垃圾邮件首**选项" 选项卡，然后配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="3eee1-127">In the properties page that opens, verify that the **Outbound spam preferences** tab is selected, and then configure the following setting:</span></span>

   <span data-ttu-id="3eee1-128">将**所有可疑的出站电子邮件的副本发送到以下电子邮件地址或地址**：选中 "" 复选框，并输入应添加到检测到的邮件的 "**密件抄送**" 字段的一个或多个管理员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3eee1-128">**Send a copy of all suspicious outbound email messages to the following email address or addresses**: Select the check box and enter the email addresses of one or more administrators who should be added to the **Bcc** field of detected messages.</span></span> <span data-ttu-id="3eee1-129">使用分号（;）分隔多个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3eee1-129">Separate multiple email addresses with a semicolon ( ; ).</span></span>

   <span data-ttu-id="3eee1-130">完成后，单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3eee1-130">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-additional-recipients-for-outbound-spam-messages"></a><span data-ttu-id="3eee1-131">使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 为出站垃圾邮件配置其他收件人</span><span class="sxs-lookup"><span data-stu-id="3eee1-131">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure additional recipients for outbound spam messages</span></span>

<span data-ttu-id="3eee1-132">若要为出站垃圾邮件启用和配置其他收件人，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3eee1-132">To enable and configure additional recipients for outbound spam messages, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients <recipients>
```

- <span data-ttu-id="3eee1-133">若要指定覆盖所有现有值的收件人，请使用`emailaddress1,emailaddress2,...emailaddressN`语法。</span><span class="sxs-lookup"><span data-stu-id="3eee1-133">To specify recipients that overwrite all existing values, use the syntax `emailaddress1,emailaddress2,...emailaddressN`.</span></span>

- <span data-ttu-id="3eee1-134">若要在不影响其他条目的情况下选择性地添加或删除`@{Add="\<emailaddress1\>","\<emailaddress2\>"...; Remove="\<emailaddress1\>","\<emailaddress2\>"...}`收件人，请使用语法。</span><span class="sxs-lookup"><span data-stu-id="3eee1-134">To selectively add or remove recipients without affecting the other entries, use the syntax `@{Add="\<emailaddress1\>","\<emailaddress2\>"...; Remove="\<emailaddress1\>","\<emailaddress2\>"...}`.</span></span>

<span data-ttu-id="3eee1-135">本示例为出站垃圾邮件的密件抄送收件人启用和配置 chris@contoso.com、laura@contoso.com 和 julia@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3eee1-135">This example enables and configures chris@contoso.com, laura@contoso.com and julia@contoso.com as Bcc recipients for outbound spam messages.</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients chris@contoso.com,laura@contoso.com,julia@contoso.com
```

<span data-ttu-id="3eee1-136">本示例将 michelle@contoso.com 添加为其他密件抄送收件人。</span><span class="sxs-lookup"><span data-stu-id="3eee1-136">This example adds michelle@contoso.com as an additional Bcc recipient.</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Add=michelle@contoso.com}
```

<span data-ttu-id="3eee1-137">本示例从密件抄送收件人列表中删除 chris@contoso.com 和 julia@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3eee1-137">This example removes chris@contoso.com and julia@contoso.com from the list of Bcc recipients.</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Remove='chris@contoso.com','julia@contoso.com'}
```

<span data-ttu-id="3eee1-138">有关语法和参数的详细信息，请参阅[HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="3eee1-138">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

<span data-ttu-id="3eee1-139">**注意**：运行命令`Get-HostedOutboundSpamFilterPolicy | Format-List`以查看*BccSuspiciousOutboundMail*和*BccSuspiciousOutboundAdditionalRecipients*属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="3eee1-139">**Note**: Run the command `Get-HostedOutboundSpamFilterPolicy | Format-List` to see the current values of the *BccSuspiciousOutboundMail* and *BccSuspiciousOutboundAdditionalRecipients* properties.</span></span>

## <a name="use-the-security--compliance-center-to-configure-notifications-when-a-sender-is-blocked"></a><span data-ttu-id="3eee1-140">当发件人被阻止时，使用安全 & 合规性中心配置通知</span><span class="sxs-lookup"><span data-stu-id="3eee1-140">Use the Security & Compliance Center to configure notifications when a sender is blocked</span></span>

1. <span data-ttu-id="3eee1-141">在安全 & 合规性中心中，转到**警报** \> **警报策略**。</span><span class="sxs-lookup"><span data-stu-id="3eee1-141">In the Security & Compliance Center, go to **Alerts** \> **Alert Policies**.</span></span>

2. <span data-ttu-id="3eee1-142">查找并选择名为**User 限制的用于发送电子邮件**的策略。</span><span class="sxs-lookup"><span data-stu-id="3eee1-142">Find and select the policy named **User restricted from sending email**.</span></span>

3. <span data-ttu-id="3eee1-143">在 "飞出" 打开的情况下，单击 "**编辑策略**"。</span><span class="sxs-lookup"><span data-stu-id="3eee1-143">In the fly out that opens, click **Edit policy**.</span></span>

4. <span data-ttu-id="3eee1-144">在出现的 "**编辑收件人**" 页中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="3eee1-144">In the **Edit recipients** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="3eee1-145">**发送电子邮件通知**：验证是否已选择 **"打开"** 。</span><span class="sxs-lookup"><span data-stu-id="3eee1-145">**Send email notifications**: Verify that **On** is selected.</span></span>

   - <span data-ttu-id="3eee1-146">**电子邮件收件人**：默认情况下， **TenantAdmins**是此处的唯一值。</span><span class="sxs-lookup"><span data-stu-id="3eee1-146">**Email recipients**: By default **TenantAdmins** is the only value here.</span></span> <span data-ttu-id="3eee1-147">若要添加其他收件人，请单击此框中的空白点，开始键入收件人，并在其名称解析时选择收件人。</span><span class="sxs-lookup"><span data-stu-id="3eee1-147">To add additional recipients, click in an empty spot in this box, start typing the recipient, and select the recipient when their name resolves.</span></span> <span data-ttu-id="3eee1-148">若要删除收件人，请单击其名称旁边的 " **X** "。</span><span class="sxs-lookup"><span data-stu-id="3eee1-148">To remove recipients, click on the **X** next to their names.</span></span>

   - <span data-ttu-id="3eee1-149">**每日通知限制**：默认值为**无限制**，但您可以配置从1到200的各种限制。</span><span class="sxs-lookup"><span data-stu-id="3eee1-149">**Daily notification limit**: The default value is **No limit**, but you can configure various limits from 1 to 200.</span></span>

   <span data-ttu-id="3eee1-150">完成后，单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3eee1-150">When you're finished, click **Save**.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="3eee1-151">详细信息</span><span class="sxs-lookup"><span data-stu-id="3eee1-151">For more information</span></span>

[<span data-ttu-id="3eee1-152">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="3eee1-152">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="3eee1-153">反垃圾邮件保护常见问题</span><span class="sxs-lookup"><span data-stu-id="3eee1-153">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

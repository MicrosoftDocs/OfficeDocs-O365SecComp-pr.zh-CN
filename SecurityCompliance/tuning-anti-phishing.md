---
title: 优化 Office 365 中的反网络钓鱼保护
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 管理员可以了解如何确定仿冒邮件的原因以及在将来阻止更多的网络钓鱼邮件的原因。
ms.openlocfilehash: b17cdc6ec6cfc07642a6a40657009b46b83f1559
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156344"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a><span data-ttu-id="27730-103">优化 Office 365 中的反网络钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="27730-103">Tune anti-phishing protection in Office 365</span></span>

<span data-ttu-id="27730-104">尽管 Office 365 附带了在默认情况下启用的各种反网络钓鱼功能, 但有些网络钓鱼邮件仍可能会到达您的邮箱。</span><span class="sxs-lookup"><span data-stu-id="27730-104">Although Office 365 comes with a variety of anti-phishing features that are enabled by default, it's possible that some phishing messages could still get through to your mailboxes.</span></span> <span data-ttu-id="27730-105">本主题介绍您可以执行哪些操作来发现仿冒邮件的访问原因, 以及您可以采取什么措施来调整 Exchange Online 组织中的反网络钓鱼设置,_而不会意外地使事情更糟_。</span><span class="sxs-lookup"><span data-stu-id="27730-105">This topic describes what you can do to discover why a phishing message got through, and what you can do to adjust the anti-phishing settings in your Exchange Online organization _without accidentally making things worse_.</span></span>

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a><span data-ttu-id="27730-106">首先要做的第一件事: 处理任何受损帐户, 并确保阻止任何更多的网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="27730-106">First things first: deal with any compromised accounts and make sure you block any more phishing messages from getting through</span></span>

<span data-ttu-id="27730-107">如果收件人的帐户因仿冒邮件而受损, 请按照在[Office 365 中响应受损电子邮件帐户](responding-to-a-compromised-email-account.md)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="27730-107">If a recipient's account was compromised as a result of the phishing message, follow the steps in [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="27730-108">如果你的订阅包括高级威胁防护 (ATP), 则可以使用[Office 365 威胁智能](office-365-ti.md)标识也收到网络钓鱼邮件的其他用户。</span><span class="sxs-lookup"><span data-stu-id="27730-108">If your subscription includes Advanced Threat Protection (ATP), you can use [Office 365 Threat Intelligence](office-365-ti.md) to identify other users who also received the phishing message.</span></span> <span data-ttu-id="27730-109">您还可以使用其他选项阻止网络钓鱼邮件:</span><span class="sxs-lookup"><span data-stu-id="27730-109">You have additional options to block phishing messages:</span></span>

- [<span data-ttu-id="27730-110">ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="27730-110">ATP Safe Links</span></span>](set-up-atp-safe-links-policies.md)

- [<span data-ttu-id="27730-111">ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="27730-111">ATP Safe Attachments</span></span>](set-up-atp-safe-attachments-policies.md)

- <span data-ttu-id="27730-112">[ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="27730-112">[ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="27730-113">请注意, 可以暂时将策略中的**高级网络钓鱼阈值**从**Standard**提高到**主动**、**更主动**或**最严格**的。</span><span class="sxs-lookup"><span data-stu-id="27730-113">Note that you can temporarily increase the **Advanced phishing thresholds** in the policy from **Standard** to **Aggressive**, **More aggressive**, or **Most aggressive**.</span></span>

<span data-ttu-id="27730-114">验证这些 ATP 功能是否已打开。</span><span class="sxs-lookup"><span data-stu-id="27730-114">Verify these ATP features are turned on.</span></span>

## <a name="report-the-phishing-message-to-microsoft"></a><span data-ttu-id="27730-115">向 Microsoft 报告网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="27730-115">Report the phishing message to Microsoft</span></span>

<span data-ttu-id="27730-116">在调整用于保护 Office 365 中所有客户的筛选器时, 报告网络钓鱼邮件非常有帮助。</span><span class="sxs-lookup"><span data-stu-id="27730-116">Reporting phishing messages is helpful in tuning the filters that are used to protect all customers in Office 365.</span></span>

<span data-ttu-id="27730-117">将仿冒邮件作为新的 (否则为空邮件) 的_附件_发送到**phish@office365.microsoft.com**。</span><span class="sxs-lookup"><span data-stu-id="27730-117">Send the phishing message _as an attachment_ in a new, otherwise empty message to **phish@office365.microsoft.com**.</span></span> <span data-ttu-id="27730-118">不要直接转发原始邮件;否则, 我们无法检查原始邮件头。</span><span class="sxs-lookup"><span data-stu-id="27730-118">Don't just forward the original message; otherwise, we can't examine the original message headers.</span></span> <span data-ttu-id="27730-119">或者, 您可以在 Outlook 或 web 上的 Outlook (以前称为 Outlook Web App) 中使用[报告邮件](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in)加载项。</span><span class="sxs-lookup"><span data-stu-id="27730-119">Or, you can use the [Report Message](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in) add-in in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span>

<span data-ttu-id="27730-120">有关详细信息, 请参阅[将垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="27730-120">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span>

## <a name="inspect-the-message-headers"></a><span data-ttu-id="27730-121">检查邮件头</span><span class="sxs-lookup"><span data-stu-id="27730-121">Inspect the message headers</span></span>

<span data-ttu-id="27730-122">您可以检查网络钓鱼邮件的标头, 以查看是否有任何可以执行的操作, 以防止更多的网络钓鱼邮件进入。</span><span class="sxs-lookup"><span data-stu-id="27730-122">You can examine the headers of the phishing message to see if there's anything that you can do yourself to prevent more phishing messages from coming through.</span></span> <span data-ttu-id="27730-123">换句话说, 检查邮件头可以帮助您确定组织中负责允许网络钓鱼邮件的任何设置。</span><span class="sxs-lookup"><span data-stu-id="27730-123">In other words, examining the messages headers can help you identify any settings in your organization that were responsible for allowing the phishing messages in.</span></span>

<span data-ttu-id="27730-124">具体来说, 应检查邮件头中的**X-Forefront-反垃圾邮件报告**标头字段, 以了解垃圾邮件筛选判定 (SFV) 值中跳过的垃圾邮件或网络钓鱼筛选的指示。</span><span class="sxs-lookup"><span data-stu-id="27730-124">Specifically, you should check the **X-Forefront-Antispam-Report** header field in the message headers for indications of skipped spam or phish filtering in the Spam Filtering Verdict (SFV) value.</span></span> <span data-ttu-id="27730-125">跳过筛选的邮件将具有一个条目`SCL:-1`, 这意味着您的设置允许此邮件通过覆盖由该服务确定的垃圾邮件或网络钓鱼 verdicts。</span><span class="sxs-lookup"><span data-stu-id="27730-125">Messages that skip filtering will have an entry of `SCL:-1`, which means one of your settings allowed this message through by overriding the spam or phish verdicts that were determined by the service.</span></span> <span data-ttu-id="27730-126">有关如何获取邮件头以及所有可用的反垃圾邮件和反网络钓鱼邮件头的完整列表的详细信息, 请参阅[反垃圾邮件邮件头](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers)。</span><span class="sxs-lookup"><span data-stu-id="27730-126">For more details on how to get message headers and the complete list of all available anti-spam and anti-phish message headers, see [Anti-spam message headers](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers).</span></span>

## <a name="best-practices-to-stay-protected"></a><span data-ttu-id="27730-127">保持受保护状态的最佳做法</span><span class="sxs-lookup"><span data-stu-id="27730-127">Best practices to stay protected</span></span>

- <span data-ttu-id="27730-128">在每月的基础上, 运行[安全得分](microsoft-secure-score.md)来评估 Office 365 组织的安全设置。</span><span class="sxs-lookup"><span data-stu-id="27730-128">On a monthly basis, run [Secure Score](microsoft-secure-score.md) to assess your Office 365 organization's security settings.</span></span>

- <span data-ttu-id="27730-129">定期查看[欺骗智能报告](learn-about-spoof-intelligence.md)并[在反网络钓鱼策略中启用反欺骗保护](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy)以**隔离**可疑邮件, 而不是将其传递到用户的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="27730-129">Periodically review the [Spoof intelligence report](learn-about-spoof-intelligence.md) and [enable anti-spoofing protection in the anti-phishing policy](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy) to **quarantine** suspicious messages instead of delivering them to the user's Junk Email folder.</span></span>

- <span data-ttu-id="27730-130">定期查看[威胁防护状态报告](view-reports-for-atp.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="27730-130">Periodically review the [Threat Protection Status report](view-reports-for-atp.md#threat-protection-status-report).</span></span>

- <span data-ttu-id="27730-131">某些客户通过将自己的域放在反垃圾邮件策略中的 "允许发件人" 或 "允许域" 列表中, 在无意中允许网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="27730-131">Some customers inadvertently allow phishing messages through by putting their own domains in the Allow sender or Allow domain list in anti-spam policies.</span></span> <span data-ttu-id="27730-132">如果选择执行此操作, 则必须小心使用。</span><span class="sxs-lookup"><span data-stu-id="27730-132">If you choose to do this, you must use extreme caution.</span></span> <span data-ttu-id="27730-133">虽然此配置将允许某些合法邮件通过, 但它还会允许由 Office 365 垃圾邮件和/或网络钓鱼筛选器通常阻止的恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="27730-133">Although this configuration will allow some legitimate messages through, it will also allow malicious messages that would normally be blocked by the Office 365 spam and/or phish filters.</span></span>

  <span data-ttu-id="27730-134">若要处理受 Office 365 (误报) 阻止的合法邮件 (涉及域中的发件人), 最佳方法是在 DNS 中为 Office 365 中的_所有_电子邮件域完全和完全配置 SPF、DKIM 和 DMARC 记录:</span><span class="sxs-lookup"><span data-stu-id="27730-134">The best way to deal with legitimate messages that are blocked by Office 365 (false positives) that involve senders in your domain is to fully and completely configure the SPF, DKIM, and DMARC records in DNS for _all_ of your email domains in Office 365:</span></span>

  - <span data-ttu-id="27730-135">验证您的 SPF 记录是否标识了您的域中的发件人的_所有_电子邮件源 (不要忘记第三方服务!)。</span><span class="sxs-lookup"><span data-stu-id="27730-135">Verify that your SPF record identifies _all_ sources of email for senders in your domain (don't forget third-party services!).</span></span>

  - <span data-ttu-id="27730-136">使用硬故障 (\-) 以确保配置为这样做的电子邮件系统拒绝未经授权的发件人。</span><span class="sxs-lookup"><span data-stu-id="27730-136">Use hard fail (\-) to ensure that unauthorized senders are rejected by email systems that are configured to do so.</span></span> <span data-ttu-id="27730-137">您可以使用[欺骗智能](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence)来帮助标识使用您的域的发件人, 以便您可以在 SPF 记录中包括授权的第三方发件人。</span><span class="sxs-lookup"><span data-stu-id="27730-137">You can use [spoof intelligence](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence) to help identify senders that are using your domain so that you can include authorized third-party senders in your SPF record.</span></span>

  <span data-ttu-id="27730-138">有关配置说明, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="27730-138">For configuration instructions, see:</span></span>
  
  - [<span data-ttu-id="27730-139">在 Office 365 中设置 SPF 以防止欺骗</span><span class="sxs-lookup"><span data-stu-id="27730-139">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [<span data-ttu-id="27730-140">使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件</span><span class="sxs-lookup"><span data-stu-id="27730-140">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md)

  - [<span data-ttu-id="27730-141">使用 DMARC 验证 Office 365 中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="27730-141">Use DMARC to validate email in Office 365</span></span>](use-dmarc-to-validate-email.md)

- <span data-ttu-id="27730-142">如果可能, 我们建议您将您的域的电子邮件直接传递到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="27730-142">Whenever possible, we recommend that you deliver email for your domain directly to Office 365.</span></span> <span data-ttu-id="27730-143">换言之, 将您的 Office 365 域的 MX 记录指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="27730-143">In other words, point your Office 365 domain's MX record to Office 365.</span></span> <span data-ttu-id="27730-144">Exchange Online Protection (EOP) 能够在将其邮件直接传递到 Office 365 时为你的云用户提供最佳保护。</span><span class="sxs-lookup"><span data-stu-id="27730-144">Exchange Online Protection (EOP) is able to provide the best protection for your cloud users when their mail is delivered directly to Office 365.</span></span> <span data-ttu-id="27730-145">如果您必须在 EOP 前使用第三方电子邮件清洁系统, 请确保已按照[此处](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)的指导进行。</span><span class="sxs-lookup"><span data-stu-id="27730-145">If you must use a third-party email hygiene system in front of EOP, ensure you have followed the guidance [here](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span>

- <span data-ttu-id="27730-146">多重因素身份验证 (MFA) 是防止受损帐户的一种非常好的方法。</span><span class="sxs-lookup"><span data-stu-id="27730-146">Multi factor authentication (MFA) is a really good way to prevent compromised accounts.</span></span> <span data-ttu-id="27730-147">强烈考虑为所有用户启用 MFA。</span><span class="sxs-lookup"><span data-stu-id="27730-147">You should strongly consider enabling MFA for all of your users.</span></span> <span data-ttu-id="27730-148">对于分阶段的方法, 先在为每个人启用 MFA 之前为最敏感的用户 (管理员、高级管理人员等) 启用 MFA。</span><span class="sxs-lookup"><span data-stu-id="27730-148">For a phased approach, start by enabling MFA for your most sensitive users (admins, executives, etc.) before you enable MFA for everyone.</span></span> <span data-ttu-id="27730-149">有关说明, 请参阅[设置多因素身份验证](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="27730-149">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="27730-150">将规则转发给外部收件人通常由攻击者用来提取数据。</span><span class="sxs-lookup"><span data-stu-id="27730-150">Forwarding rules to external recipients are often used by attackers to extract data.</span></span> <span data-ttu-id="27730-151">使用 "审阅[Microsoft 安全分数](microsoft-secure-score.md)中的**邮箱转发规则**" 信息查找甚至阻止外部收件人的转发规则。</span><span class="sxs-lookup"><span data-stu-id="27730-151">Use the **Review mailbox forwarding rules** information in [Microsoft Secure Score](microsoft-secure-score.md) to find and even prevent forwarding rules to external recipients.</span></span> <span data-ttu-id="27730-152">有关详细信息, 请参阅[通过安全分数缓解客户端外部转发规则](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)。</span><span class="sxs-lookup"><span data-stu-id="27730-152">For more information, see [Mitigating Client External Forwarding Rules with Secure Score](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/).</span></span>

---
title: 未验证发件人
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/11/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 若要防止仿冒邮件到达邮箱, Outlook.com 和 web 上的 Outlook 验证发件人是否是他们所说的人, 并将可疑邮件标记为垃圾邮件。
ms.openlocfilehash: 233474dbfff430be8dd95d513adeb257bb26c5c7
ms.sourcegitcommit: 9e2df36b05a2c93ce2629a7a5eda8f44159d114d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "35628505"
---
# <a name="unverified-sender"></a><span data-ttu-id="a0226-103">未验证发件人</span><span class="sxs-lookup"><span data-stu-id="a0226-103">Unverified Sender</span></span>

> [!NOTE] 
> <span data-ttu-id="a0226-104">这些更新现在即将推出, 可能对所有用户不可用。</span><span class="sxs-lookup"><span data-stu-id="a0226-104">These updates are rolling out now, and might not be available yet for all users.</span></span>

<span data-ttu-id="a0226-105">若要防止仿冒邮件到达邮箱, Outlook.com 和 web 上的 Outlook 验证发件人是否是他们所说的人, 并将可疑邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="a0226-105">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0226-106">将邮件标记为 "仿冒骗局" 时, Outlook.com 和 web 上的 Outlook 将在页面顶部显示警告, 但仍可打开邮件中的任何链接。</span><span class="sxs-lookup"><span data-stu-id="a0226-106">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="a0226-107">如何在收件箱中识别可疑邮件？</span><span class="sxs-lookup"><span data-stu-id="a0226-107">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="a0226-108">当邮件的发件人无法识别或其身份与 "发件人" 地址中所示的不同时, web 上的 Outlook.com 和 Outlook 显示指示器。</span><span class="sxs-lookup"><span data-stu-id="a0226-108">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="a0226-109">如何管理哪些邮件会收到未验证的发件人处理</span><span class="sxs-lookup"><span data-stu-id="a0226-109">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="a0226-110">如果你是 Office 365 客户, 则可以通过安全 & 合规中心管理此功能。</span><span class="sxs-lookup"><span data-stu-id="a0226-110">If you are an Office 365 customer you can manage this feature through the Security & Compliance Center.</span></span> 

- <span data-ttu-id="a0226-111">在 Office 365 安全 & 合规性中心中, 全局或安全管理员可以通过反网络钓鱼策略下的反欺骗保护来打开或关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="a0226-111">In the Office 365 Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="a0226-112">此外, 还可以通过 "AntiPhishPolicy" cmdlet 对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="a0226-112">Additionally, it can be managed through the ‘Set-AntiPhishPolicy’ cmdlet.</span></span> <span data-ttu-id="a0226-113">有关更多详细信息, 请参阅[Office 365 中的反钓鱼防护](anti-phishing-protection.md)和 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="a0226-113">For more details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy?view=exchange-ps).</span></span>

    ![在图形界面中编辑未经身份验证的发件人。](media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="a0226-115">如果管理员已识别误报, 并且发件人不应接收未验证的发件人治疗, 则可以执行下列操作之一将发件人添加到欺骗智能欺骗允许列表:</span><span class="sxs-lookup"><span data-stu-id="a0226-115">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment they can take one of the following actions to add the sender to the Spoof Intelligence spoof allow list:</span></span>
        
    - <span data-ttu-id="a0226-116">通过欺骗性智能洞察力添加域对。</span><span class="sxs-lookup"><span data-stu-id="a0226-116">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="a0226-117">有关更多详细信息, 请参阅演练: 欺骗性智能洞察力</span><span class="sxs-lookup"><span data-stu-id="a0226-117">For more details, see Walkthrough: spoof intelligence insight</span></span>
                
    - <span data-ttu-id="a0226-118">通过将 get-phishfilterpolicy cmdlet 添加域对。</span><span class="sxs-lookup"><span data-stu-id="a0226-118">Add the domain pair through the PhishFilterPolicy cmdlet.</span></span> <span data-ttu-id="a0226-119">有关更多详细信息, 请参阅 Office 365 中的将 get-phishfilterpolicy 和反欺骗保护</span><span class="sxs-lookup"><span data-stu-id="a0226-119">For more details, see Set-PhishFilterPolicy and Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="a0226-120">此外, 如果通过管理员允许列表 (包括电子邮件传输规则 (Etr)、安全域列表 (反垃圾邮件策略)、安全发件人列表或用户已将此用户设置为 "安全发件人", 则不会应用未验证的发件人治疗收件箱.</span><span class="sxs-lookup"><span data-stu-id="a0226-120">Additionally, we do not apply the unverified sender treatment if it was delivered to the inbox via an admin allow list, including Email Transport Rules (ETRs), Safe Domain List (Anti-Spam Policy), Safe Sender List or a user has set this user as a “Safe Sender” in their inbox.</span></span>

### <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="a0226-121">您将在发件人图像中看到 "？"</span><span class="sxs-lookup"><span data-stu-id="a0226-121">You see a '?' in the sender image</span></span>

<span data-ttu-id="a0226-122">当 Outlook.com 和 Outlook 网页上的 Outlook 无法使用电子邮件身份验证技术验证发件人的身份时, 它们将在发件人照片中显示 "？"。</span><span class="sxs-lookup"><span data-stu-id="a0226-122">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span> 

![邮件未通过验证](media/message-did-not-pass-verification.jpg)

<span data-ttu-id="a0226-124">并不是每个验证失败的邮件都是恶意的。</span><span class="sxs-lookup"><span data-stu-id="a0226-124">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="a0226-125">但是, 如果您不识别发件人, 则应注意与不进行身份验证的邮件进行交互。</span><span class="sxs-lookup"><span data-stu-id="a0226-125">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="a0226-126">或者, 如果您识别的发件人在发件人图像中通常不包含 '？ ', 但突然开始看到它, 则可能是发件人哄骗的签名。</span><span class="sxs-lookup"><span data-stu-id="a0226-126">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a0226-127">常见问题</span><span class="sxs-lookup"><span data-stu-id="a0226-127">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="a0226-128">Outlook.com 和 Outlook 在 web 上使用哪些条件来添加 '？ ' 和 ' via ' 属性？</span><span class="sxs-lookup"><span data-stu-id="a0226-128">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="a0226-129">对于发件人图像中的 "？": Outlook.com 要求邮件传递 SPF 或 DKIM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="a0226-129">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication.</span></span> <span data-ttu-id="a0226-130">有关更多详细信息, 请参阅[在 office 365 中设置 SPF 以帮助阻止哄骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和[使用 DKIM 验证从您的自定义域在 Office 365 中发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="a0226-130">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="a0226-131">对于 via 标记: 如果 "发件人" 地址中的域不同于 DKIM 签名中的域, 或者 SMTP 邮件来自, 则 Outlook.com 将在这两个字段之一中显示域 (首选 DKIM 签名)。</span><span class="sxs-lookup"><span data-stu-id="a0226-131">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the-"></a><span data-ttu-id="a0226-132">如何删除 "？"</span><span class="sxs-lookup"><span data-stu-id="a0226-132">How do I remove the '?'</span></span>

<span data-ttu-id="a0226-133">对于发件人图像中的 '？ ', 作为发件人, 应使用 SPF 或 DKIM 对邮件进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a0226-133">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="a0226-134">对于 via 标记: 作为发件人, 应确保 "DKIM" 签名中的域或 "发件人" 中的 "SMTP 邮件" 与 "发件人" 地址中的域相同, 或者是的子域。</span><span class="sxs-lookup"><span data-stu-id="a0226-134">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="a0226-135">Outlook.com 和 Outlook 网页版是否对未通过身份验证的每封邮件显示此功能？</span><span class="sxs-lookup"><span data-stu-id="a0226-135">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="a0226-136">不一定。</span><span class="sxs-lookup"><span data-stu-id="a0226-136">Not necessarily.</span></span> <span data-ttu-id="a0226-137">Outlook.com 和 web 上的 Outlook 在邮件中的其他属性可能会对发件人进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="a0226-137">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a0226-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="a0226-138">Related topics</span></span>

[<span data-ttu-id="a0226-139">帮助保护你的 Outlook.com 电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="a0226-139">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="a0226-140">处理 Outlook.com 中的滥用、网络钓鱼或欺骗</span><span class="sxs-lookup"><span data-stu-id="a0226-140">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="a0226-141">在 web 上的 Outlook 中筛选垃圾电子邮件和垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="a0226-141">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)

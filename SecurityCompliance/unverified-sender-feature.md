---
title: 识别 Outlook.com 中的可疑邮件和 web 上的 Outlook
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 若要防止仿冒邮件到达邮箱, Outlook.com 和 web 上的 Outlook 验证发件人是否是他们所说的人, 并将可疑邮件标记为垃圾邮件。
ms.openlocfilehash: edba30bb2ac0f9dc6ebc12db957a518de0c1b543
ms.sourcegitcommit: 9907bebc5f225032f681c4952de0b0be2df278ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2019
ms.locfileid: "33345882"
---
# <a name="identify-suspicious-messages-in-outlookcom-and-outlook-on-the-web"></a><span data-ttu-id="b0c5a-103">识别 Outlook.com 中的可疑邮件和 web 上的 Outlook</span><span class="sxs-lookup"><span data-stu-id="b0c5a-103">Identify suspicious messages in Outlook.com and Outlook on the web</span></span>

<span data-ttu-id="b0c5a-104">若要防止仿冒邮件到达邮箱, Outlook.com 和 web 上的 Outlook 验证发件人是否是他们所说的人, 并将可疑邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-104">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0c5a-105">将邮件标记为 "仿冒骗局" 时, Outlook.com 和 web 上的 Outlook 将在页面顶部显示警告, 但仍可打开邮件中的任何链接。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-105">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="b0c5a-106">如何在收件箱中识别可疑邮件？</span><span class="sxs-lookup"><span data-stu-id="b0c5a-106">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="b0c5a-107">当邮件的发件人无法识别或其身份与 "发件人" 地址中所示的不同时, web 上的 Outlook.com 和 Outlook 显示指示器。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-107">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

### <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="b0c5a-108">您将在发件人图像中看到 "？"</span><span class="sxs-lookup"><span data-stu-id="b0c5a-108">You see a '?' in the sender image</span></span>

<span data-ttu-id="b0c5a-109">当 Outlook.com 和 Outlook 网页上的 Outlook 无法使用电子邮件身份验证技术验证发件人的身份时, 它们将在发件人照片中显示 "？"。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-109">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span>

![邮件未通过验证](media/message-did-not-pass-verification.jpg)

<span data-ttu-id="b0c5a-111">并不是每个验证失败的邮件都是恶意的。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-111">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="b0c5a-112">但是, 如果您不识别发件人, 则应注意与不进行身份验证的邮件进行交互。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-112">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="b0c5a-113">或者, 如果您识别的发件人在发件人图像中通常不包含 '？ ', 但突然开始看到它, 则可能是发件人哄骗的签名。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-113">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

### <a name="the-senders-address-is-different-than-what-appears-in-the-from-address"></a><span data-ttu-id="b0c5a-114">发件人的地址与 "发件人" 地址中显示的地址不同</span><span class="sxs-lookup"><span data-stu-id="b0c5a-114">The sender's address is different than what appears in the From address</span></span>

<span data-ttu-id="b0c5a-115">通常, 您在邮件中看到的电子邮件地址与 "发件人" 地址中显示的内容不同。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-115">Frequently, the email address you see in a message is different than what you see in the From address.</span></span> <span data-ttu-id="b0c5a-116">有时, 仿冒者会尝试欺骗你, 让你认为发件人不是真正的人。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-116">Sometimes phishers try to trick you into thinking that the sender is someone other than who they really are.</span></span>

<span data-ttu-id="b0c5a-117">当 Outlook.com 和 Outlook 网页检测到发件人的实际地址和 "发件人" 地址中的地址之间存在差异时, 它们将使用 via 标记显示实际发件人, 这将带下划线。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-117">When Outlook.com and Outlook on the web detect a difference between the sender's actual address and the address on the From address, they show the actual sender using the via tag, which will be underlined.</span></span>

![未验证发件人替换文本](media/unverified-sender-feature1.png)

<span data-ttu-id="b0c5a-119">在此示例中, 发送域`suspicious.com`已通过身份验证, 但发`unknown@contoso.com`件人放在 "发件人" 地址中。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-119">In this example, the sending domain `suspicious.com` is authenticated, but the sender put `unknown@contoso.com` in the From address.</span></span>

<span data-ttu-id="b0c5a-120">并不是每个带 via 标记的邮件都是可疑的。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-120">Not every message with a via tag is suspicious.</span></span> <span data-ttu-id="b0c5a-121">但是, 如果您不识别带 via 标记的邮件, 则在与之进行交互时应谨慎。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-121">However, if you don't recognize a message with a via tag, you should be cautious about interacting with it.</span></span>

<span data-ttu-id="b0c5a-122">在 Outlook.com 和 web 上的新 Outlook 中, 您可以将光标悬停在邮件列表中的发件人的姓名或地址上, 以查看其电子邮件地址, 而无需打开邮件。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-122">In Outlook.com and the new Outlook on the web, you can hover your cursor over a sender's name or address in the message list to see their email address, without needing to open the message.</span></span>

![OneDrive 入门](media/get-started-with-onedrive-message.png)

<span data-ttu-id="b0c5a-124">如何知道您是否正在使用新的 Outlook 网页？</span><span class="sxs-lookup"><span data-stu-id="b0c5a-124">How do you know if you're using the new Outlook on the web?</span></span> <span data-ttu-id="b0c5a-125">请参阅以下示例:</span><span class="sxs-lookup"><span data-stu-id="b0c5a-125">See the following examples:</span></span>

![Outlook vs Office 365](media/outlook-vs-outlook365.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="b0c5a-127">常见问题</span><span class="sxs-lookup"><span data-stu-id="b0c5a-127">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="b0c5a-128">Outlook.com 和 Outlook 在 web 上使用哪些条件来添加 '？ ' 和 ' via ' 属性？</span><span class="sxs-lookup"><span data-stu-id="b0c5a-128">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="b0c5a-129">对于发件人图像中的 "？": Outlook.com 要求邮件传递 SPF 或 DKIM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-129">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication.</span></span> <span data-ttu-id="b0c5a-130">有关更多详细信息, 请参阅[在 office 365 中设置 SPF 以帮助阻止哄骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和[使用 DKIM 验证从您的自定义域在 Office 365 中发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-130">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="b0c5a-131">对于 via 标记: 如果 "发件人" 地址中的域不同于 DKIM 签名中的域, 或者 SMTP 邮件来自, 则 Outlook.com 将在这两个字段之一中显示域 (首选 DKIM 签名)。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-131">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="can-i-override-these-properties-with-ip-allows-exchange-transport-rule-allows-or-safe-senders"></a><span data-ttu-id="b0c5a-132">是否可以使用 IP 允许、Exchange 传输规则允许或安全发件人替代这些属性？</span><span class="sxs-lookup"><span data-stu-id="b0c5a-132">Can I override these properties with IP Allows, Exchange Transport Rule Allows, or safe senders?</span></span>

<span data-ttu-id="b0c5a-133">您不能覆盖这些属性。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-133">You can't override these properties.</span></span>

### <a name="how-do-i-remove-these-properties"></a><span data-ttu-id="b0c5a-134">如何删除这些属性？</span><span class="sxs-lookup"><span data-stu-id="b0c5a-134">How do I remove these properties?</span></span>

<span data-ttu-id="b0c5a-135">对于发件人图像中的 '？ ', 作为发件人, 应使用 SPF 或 DKIM 对邮件进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-135">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="b0c5a-136">对于 via 标记: 作为发件人, 应确保 "DKIM" 签名中的域或 "发件人" 中的 "SMTP 邮件" 与 "发件人" 地址中的域相同, 或者是的子域。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-136">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="b0c5a-137">Outlook.com 和 Outlook 网页版是否对未通过身份验证的每封邮件显示此功能？</span><span class="sxs-lookup"><span data-stu-id="b0c5a-137">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="b0c5a-138">不一定。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-138">Not necessarily.</span></span> <span data-ttu-id="b0c5a-139">Outlook.com 和 web 上的 Outlook 在邮件中的其他属性可能会对发件人进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b0c5a-139">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b0c5a-140">相关主题</span><span class="sxs-lookup"><span data-stu-id="b0c5a-140">Related topics</span></span>

[<span data-ttu-id="b0c5a-141">帮助保护你的 Outlook.com 电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="b0c5a-141">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="b0c5a-142">处理 Outlook.com 中的滥用、网络钓鱼或欺骗</span><span class="sxs-lookup"><span data-stu-id="b0c5a-142">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="b0c5a-143">在 web 上的 Outlook 中筛选垃圾电子邮件和垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="b0c5a-143">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)

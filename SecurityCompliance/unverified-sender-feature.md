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
# <a name="identify-suspicious-messages-in-outlookcom-and-outlook-on-the-web"></a>识别 Outlook.com 中的可疑邮件和 web 上的 Outlook

若要防止仿冒邮件到达邮箱, Outlook.com 和 web 上的 Outlook 验证发件人是否是他们所说的人, 并将可疑邮件标记为垃圾邮件。

> [!IMPORTANT]
> 将邮件标记为 "仿冒骗局" 时, Outlook.com 和 web 上的 Outlook 将在页面顶部显示警告, 但仍可打开邮件中的任何链接。

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>如何在收件箱中识别可疑邮件？

当邮件的发件人无法识别或其身份与 "发件人" 地址中所示的不同时, web 上的 Outlook.com 和 Outlook 显示指示器。

### <a name="you-see-a--in-the-sender-image"></a>您将在发件人图像中看到 "？"

当 Outlook.com 和 Outlook 网页上的 Outlook 无法使用电子邮件身份验证技术验证发件人的身份时, 它们将在发件人照片中显示 "？"。

![邮件未通过验证](media/message-did-not-pass-verification.jpg)

并不是每个验证失败的邮件都是恶意的。 但是, 如果您不识别发件人, 则应注意与不进行身份验证的邮件进行交互。 或者, 如果您识别的发件人在发件人图像中通常不包含 '？ ', 但突然开始看到它, 则可能是发件人哄骗的签名。

### <a name="the-senders-address-is-different-than-what-appears-in-the-from-address"></a>发件人的地址与 "发件人" 地址中显示的地址不同

通常, 您在邮件中看到的电子邮件地址与 "发件人" 地址中显示的内容不同。 有时, 仿冒者会尝试欺骗你, 让你认为发件人不是真正的人。

当 Outlook.com 和 Outlook 网页检测到发件人的实际地址和 "发件人" 地址中的地址之间存在差异时, 它们将使用 via 标记显示实际发件人, 这将带下划线。

![未验证发件人替换文本](media/unverified-sender-feature1.png)

在此示例中, 发送域`suspicious.com`已通过身份验证, 但发`unknown@contoso.com`件人放在 "发件人" 地址中。

并不是每个带 via 标记的邮件都是可疑的。 但是, 如果您不识别带 via 标记的邮件, 则在与之进行交互时应谨慎。

在 Outlook.com 和 web 上的新 Outlook 中, 您可以将光标悬停在邮件列表中的发件人的姓名或地址上, 以查看其电子邮件地址, 而无需打开邮件。

![OneDrive 入门](media/get-started-with-onedrive-message.png)

如何知道您是否正在使用新的 Outlook 网页？ 请参阅以下示例:

![Outlook vs Office 365](media/outlook-vs-outlook365.png)

## <a name="frequently-asked-questions"></a>常见问题

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a>Outlook.com 和 Outlook 在 web 上使用哪些条件来添加 '？ ' 和 ' via ' 属性？

对于发件人图像中的 "？": Outlook.com 要求邮件传递 SPF 或 DKIM 身份验证。 有关更多详细信息, 请参阅[在 office 365 中设置 SPF 以帮助阻止哄骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和[使用 DKIM 验证从您的自定义域在 Office 365 中发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。

对于 via 标记: 如果 "发件人" 地址中的域不同于 DKIM 签名中的域, 或者 SMTP 邮件来自, 则 Outlook.com 将在这两个字段之一中显示域 (首选 DKIM 签名)。

### <a name="can-i-override-these-properties-with-ip-allows-exchange-transport-rule-allows-or-safe-senders"></a>是否可以使用 IP 允许、Exchange 传输规则允许或安全发件人替代这些属性？

您不能覆盖这些属性。

### <a name="how-do-i-remove-these-properties"></a>如何删除这些属性？

对于发件人图像中的 '？ ', 作为发件人, 应使用 SPF 或 DKIM 对邮件进行身份验证。

对于 via 标记: 作为发件人, 应确保 "DKIM" 签名中的域或 "发件人" 中的 "SMTP 邮件" 与 "发件人" 地址中的域相同, 或者是的子域。

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a>Outlook.com 和 Outlook 网页版是否对未通过身份验证的每封邮件显示此功能？

不一定。 Outlook.com 和 web 上的 Outlook 在邮件中的其他属性可能会对发件人进行身份验证。

## <a name="related-topics"></a>相关主题

[帮助保护你的 Outlook.com 电子邮件帐户](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[处理 Outlook.com 中的滥用、网络钓鱼或欺骗](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[在 web 上的 Outlook 中筛选垃圾电子邮件和垃圾邮件](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)

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
# <a name="unverified-sender"></a>未验证发件人

> [!NOTE] 
> 这些更新现在即将推出, 可能对所有用户不可用。

若要防止仿冒邮件到达邮箱, Outlook.com 和 web 上的 Outlook 验证发件人是否是他们所说的人, 并将可疑邮件标记为垃圾邮件。

> [!IMPORTANT]
> 将邮件标记为 "仿冒骗局" 时, Outlook.com 和 web 上的 Outlook 将在页面顶部显示警告, 但仍可打开邮件中的任何链接。

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>如何在收件箱中识别可疑邮件？

当邮件的发件人无法识别或其身份与 "发件人" 地址中所示的不同时, web 上的 Outlook.com 和 Outlook 显示指示器。

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a>如何管理哪些邮件会收到未验证的发件人处理 

如果你是 Office 365 客户, 则可以通过安全 & 合规中心管理此功能。 

- 在 Office 365 安全 & 合规性中心中, 全局或安全管理员可以通过反网络钓鱼策略下的反欺骗保护来打开或关闭该功能。 此外, 还可以通过 "AntiPhishPolicy" cmdlet 对其进行管理。 有关更多详细信息, 请参阅[Office 365 中的反钓鱼防护](anti-phishing-protection.md)和 [AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy?view=exchange-ps)。

    ![在图形界面中编辑未经身份验证的发件人。](media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- 如果管理员已识别误报, 并且发件人不应接收未验证的发件人治疗, 则可以执行下列操作之一将发件人添加到欺骗智能欺骗允许列表:
        
    - 通过欺骗性智能洞察力添加域对。 有关更多详细信息, 请参阅演练: 欺骗性智能洞察力
                
    - 通过将 get-phishfilterpolicy cmdlet 添加域对。 有关更多详细信息, 请参阅 Office 365 中的将 get-phishfilterpolicy 和反欺骗保护

此外, 如果通过管理员允许列表 (包括电子邮件传输规则 (Etr)、安全域列表 (反垃圾邮件策略)、安全发件人列表或用户已将此用户设置为 "安全发件人", 则不会应用未验证的发件人治疗收件箱.

### <a name="you-see-a--in-the-sender-image"></a>您将在发件人图像中看到 "？"

当 Outlook.com 和 Outlook 网页上的 Outlook 无法使用电子邮件身份验证技术验证发件人的身份时, 它们将在发件人照片中显示 "？"。 

![邮件未通过验证](media/message-did-not-pass-verification.jpg)

并不是每个验证失败的邮件都是恶意的。 但是, 如果您不识别发件人, 则应注意与不进行身份验证的邮件进行交互。 或者, 如果您识别的发件人在发件人图像中通常不包含 '？ ', 但突然开始看到它, 则可能是发件人哄骗的签名。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a>Outlook.com 和 Outlook 在 web 上使用哪些条件来添加 '？ ' 和 ' via ' 属性？

对于发件人图像中的 "？": Outlook.com 要求邮件传递 SPF 或 DKIM 身份验证。 有关更多详细信息, 请参阅[在 office 365 中设置 SPF 以帮助阻止哄骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)和[使用 DKIM 验证从您的自定义域在 Office 365 中发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。

对于 via 标记: 如果 "发件人" 地址中的域不同于 DKIM 签名中的域, 或者 SMTP 邮件来自, 则 Outlook.com 将在这两个字段之一中显示域 (首选 DKIM 签名)。

### <a name="how-do-i-remove-the-"></a>如何删除 "？"

对于发件人图像中的 '？ ', 作为发件人, 应使用 SPF 或 DKIM 对邮件进行身份验证。

对于 via 标记: 作为发件人, 应确保 "DKIM" 签名中的域或 "发件人" 中的 "SMTP 邮件" 与 "发件人" 地址中的域相同, 或者是的子域。

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a>Outlook.com 和 Outlook 网页版是否对未通过身份验证的每封邮件显示此功能？

不一定。 Outlook.com 和 web 上的 Outlook 在邮件中的其他属性可能会对发件人进行身份验证。

## <a name="related-topics"></a>相关主题

[帮助保护你的 Outlook.com 电子邮件帐户](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[处理 Outlook.com 中的滥用、网络钓鱼或欺骗](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[在 web 上的 Outlook 中筛选垃圾电子邮件和垃圾邮件](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)

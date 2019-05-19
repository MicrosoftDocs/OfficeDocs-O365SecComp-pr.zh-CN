---
title: 为使用 Office 365 高级邮件加密进行加密的电子邮件设置到期日期
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: 使用 office 365 高级邮件加密功能在 Office 365 邮件加密 (OME) 上, 您可以通过自定义品牌化模板来设置电子邮件的过期日期, 从而扩展电子邮件的安全性。
ms.openlocfilehash: 260e6032d3b7a4c9b81fca73dfbcd57fa01168cb
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157664"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>为使用 Office 365 高级邮件加密进行加密的电子邮件设置到期日期

Office 365 高级邮件加密在特定订阅中的 Office 365 邮件加密的顶层可用。 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)e5、Office 365 企业版 E5 和 Office 365 教育版 A5 中包含高级邮件加密。 如果您的组织有一个不包含 Office 365 高级邮件加密的 Office 365 订阅, 则可以将高级邮件加密作为加载项进行购买, 使其具有高级合规性 SKU 的 E5 合规性。

您可以使用您的用户发送给使用 OME 门户访问加密电子邮件的外部收件人的电子邮件的邮件过期。 您可以通过使用在 Windows Powershell 中指定过期日期的自定义品牌模板, 强制收件人使用 OME 门户查看并回复您的组织发送的加密电子邮件。

作为 O365 全局管理员, 当您应用公司品牌以自定义 Office 365 组织的电子邮件的外观时, 您还可以为这些电子邮件指定过期时间。 使用 Office 365 高级邮件加密, 可以为来自您的组织的加密电子邮件创建多个模板。 使用模板, 可以控制收件人访问您的用户发送的邮件的时间长短。

当最终用户收到设置了过期日期的邮件时, 用户会看到包装电子邮件中的到期日期。 如果用户尝试打开已过期的邮件, 则会在 OME 门户中显示一个错误。

您只能将电子邮件的到期日期设置为外部收件人。

使用 Office 365 高级邮件加密, 无论何时应用自定义品牌打造, Office 365 都会将包装应用于与应用该模板的邮件流规则相适应的电子邮件。 此外, 如果使用自定义品牌, 则只能使用过期时间。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>使用 PowerShell 创建自定义品牌模板以强制邮件过期

1. 使用在 Office 365 组织中具有全局管理员权限的帐户[连接到 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。

2. 运行 Set-omeconfiguration cmdlet。

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" ExternalMailExpiryInDays 7
     ```

其中：

- `Identity`是自定义模板的名称。

- `ExternalMailExpiryInDays`标识收件人在过期前可保留邮件的天数。 可以使用1到730天之间的任意值。

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有关 Office 365 高级邮件加密的详细信息

- [Office 365 高级邮件加密](ome-advanced-message-encryption.md)

- [撤销使用 Office 365 高级邮件加密进行加密的电子邮件](revoke-ome-encrypted-mail.md)

- [邮件策略和合规性服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
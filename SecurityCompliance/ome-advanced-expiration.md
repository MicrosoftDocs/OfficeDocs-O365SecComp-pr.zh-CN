---
title: 为由 Office 365 高级邮件加密加密的电子邮件设置到期日期
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: 使用 office 365 高级邮件加密功能在 office 365 邮件加密 (OME) 上, 您可以通过自定义品牌化模板来设置电子邮件的过期日期, 从而扩展电子邮件的安全性。
ms.openlocfilehash: c1fb876724bed970095e950906500ff551d93cee
ms.sourcegitcommit: 8eb3cb4ec45ae0bb75fde249e35c4bc3d263b84f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506706"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>为由 Office 365 高级邮件加密加密的电子邮件设置到期日期

office 365 高级邮件加密在特定订阅中的 office 365 邮件加密的顶层可用。 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)e5、office 365 企业版 e5 和 Office 365 教育版 A5 中包含高级邮件加密。 如果您的组织有一个不包含 office 365 高级邮件加密的 office 365 订阅, 则可以将高级邮件加密作为加载项进行购买, 使其具有高级合规性 SKU 的 E5 合规性。

您可以使用您的用户发送给使用 OME 门户访问加密电子邮件的外部收件人的电子邮件的邮件过期。 您可以通过使用在 Windows Powershell 中指定过期日期的自定义品牌模板, 强制收件人使用 OME 门户查看并回复您的组织发送的加密电子邮件。

作为 O365 全局管理员, 当您应用公司品牌以自定义 Office 365 组织的电子邮件的外观时, 您还可以为这些电子邮件指定过期时间。 使用 Office 365 高级邮件加密, 可以为来自组织的加密电子邮件创建多个模板。 使用模板, 可以控制收件人访问您的用户发送的邮件的时间长短。

当最终用户收到设置了过期日期的邮件时, 用户会看到包装电子邮件中的到期日期。 如果用户尝试打开已过期的邮件, 则会在 OME 门户中显示一个错误。

仅向外部收件人发送电子邮件过期。

使用 office 365 高级邮件加密时, 无论何时应用自定义品牌打造, Office 365 都会将包装应用于与应用该模板的邮件流规则相适应的电子邮件。 此外, 只有在使用自定义品牌的情况下, 才能使用过期。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>使用 PowerShell 创建自定义品牌模板以强制邮件过期

1. 使用 Office 365 租户中具有全局管理员权限的帐户[连接到 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。

2. 运行 set-omeconfiguration cmdlet。

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" ExternalMailExpiryInDays 7
     ```

其中：

- Identity 是自定义模板的名称。

- ExternalMailExpiryInDays 标识您希望收件人能够在邮件过期之前保留邮件的天数。 可以使用介于1到730天之间的任何值。

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有关 Office 365 高级邮件加密的详细信息

- [Office 365 高级邮件加密](ome-advanced-message-encryption.md)

- [撤消由 Office 365 加密的电子邮件高级邮件加密](revoke-ome-encrypted-mail.md)

- [邮件策略和合规性服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
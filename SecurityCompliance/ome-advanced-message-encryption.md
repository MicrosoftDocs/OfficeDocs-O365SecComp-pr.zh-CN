---
title: Office 365 高级邮件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: office 365 中的高级邮件加密帮助组织通过 Office 365 web 门户对加密电子邮件的访问权限过期并撤消访问权限, 从而帮助组织满足其合规性义务。
ms.openlocfilehash: a775803a8d2678441f319c0145e96e7d19c26f7e
ms.sourcegitcommit: 8eb3cb4ec45ae0bb75fde249e35c4bc3d263b84f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506707"
---
# <a name="office-365-advanced-message-encryption"></a>Office 365 高级邮件加密

office 365 高级邮件加密在特定订阅中的 office 365 邮件加密的顶层可用。 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)e5、office 365 企业版 e5 和 Office 365 教育版 A5 中包含高级邮件加密。 如果您的组织有一个不包含 office 365 高级邮件加密的 office 365 订阅, 则可以将高级邮件加密作为加载项进行购买, 使其具有高级合规性 SKU 的 E5 合规性。

本文是有关[Office 365 邮件加密](ome.md)的更多系列文章的一部分。

Office 365 中的高级邮件加密帮助客户满足法规遵从性义务, 这些要求对外部收件人和其加密电子邮件的访问权限要求更灵活的控制。 使用 Office 365 中的高级邮件加密, 可以控制使用自动策略在组织外共享的敏感电子邮件。 您可以配置这些策略以标识敏感信息类型 (如 PII、财务或运行状况 id), 也可以使用关键字来增强保护。 配置策略后, 您可以使用自定义品牌的电子邮件模板对策略进行配对, 然后为符合该策略的电子邮件添加其他控件的到期日期。 此外, 管理员可以随时撤销对邮件的访问权限, 从而进一步控制在外部通过安全 web 门户访问的加密电子邮件。

您只能为发送给外部收件人的电子邮件设置过期日期和吊销。

使用 office 365 高级邮件加密时, 无论何时应用自定义品牌打造, Office 365 都会将包装应用于与应用该模板的邮件流规则相适应的电子邮件。 此外, 只有在使用自定义品牌的情况下, 才能使用过期。 只能撤消通过门户接收的邮件。

## <a name="get-started-with-office-365-advanced-message-encryption"></a>开始使用 Office 365 高级邮件加密

下列主题介绍了如何设置和使用高级邮件加密。

您的组织必须具有包含 Office 365 高级邮件加密的订阅。 有关受支持订阅的详细信息, 请参阅[邮件策略和合规性服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。

设置新的 Office 365 邮件加密功能 (如果尚未设置) 以利用高级邮件加密功能, 这些功能在外部共享的加密邮件顶部提供了增强保护。 如果没有设置 office 365 邮件加密, 请参阅[设置新的 office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

[为通过 Office 365 高级邮件加密加密的电子邮件设置到期日期](ome-advanced-expiration.md)。 使用自动策略控制在组织外部共享的敏感电子邮件, 从而通过将安全 web 门户转到加密电子邮件来实现访问权限, 从而增强保护。

[撤消由 Office 365 高级邮件加密加密的电子邮件](revoke-ome-encrypted-mail.md)。 控制在组织外共享的敏感电子邮件, 并通过将访问安全的 web 门户转到加密电子邮件来增强保护。  
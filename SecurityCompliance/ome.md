---
title: Office 365 邮件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/6/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: 与 Office 365 邮件加密，您的组织可以发送和接收组织内外的人员之间的加密的电子邮件。仅预期收件人的电子邮件加密有助于确保可以查看邮件的内容。
ms.openlocfilehash: 57b1d34902bb1522a7974e97f8cd90e9f19b76f5
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696256"
---
# <a name="office-365-message-encryption"></a>Office 365 邮件加密

与 Office 365 邮件加密，您的组织可以发送和接收组织内外的人员之间的加密的电子邮件。Office 365 邮件加密处理 Outlook.com、 yahoo ！、 Gmail 和其他电子邮件服务。仅预期收件人的电子邮件加密有助于确保可以查看邮件的内容。
  
本文是系列的有关 Office 365 邮件加密的文章的较大一部分。使用下表可以快速找到所需的信息。
  
|||
|:-----|:-----|
|阅读这篇文章...  <br/> |如果您是...  <br/> |
|[了解 Office 365 中的受保护邮件](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx) <br/> |最终用户想要了解有关如何加密邮件工作，哪些选项可供您。  <br/> |
|[如何打开受保护的邮件？](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx) <br/> |想要读取受保护的邮件发送给您的最终用户。本文包括读取多个版本的 Outlook 和从不同的电子邮件帐户，如 gmail 和 yahoo ！ 帐户包括那些外部 Office 365 中的邮件的信息。  <br/> |
|[发送、 查看和回复 Outlook 中的加密邮件](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx) <br/> |最终用户想要发送、 查看或从 Outlook 回复加密邮件。即使您不是 Office 365 组织的成员，您仍收到发送给您在 Outlook 中的加密邮件的通知。有关如何查看和回复加密邮件从 Office 365 发送到的说明使用本文。  <br/> |
|[发送数字签名或加密邮件](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547) <br/> |最终用户想要发送、 查看或回复加密邮件使用 Outlook for mac。本文还介绍如何使用之外 OME，如 S/MIME 加密方法。  <br/> |
|[在 Android 设备上查看加密的邮件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> |已收到邮件加密与 Office 365 邮件加密 Android 设备上的最终用户，您可以使用免费 OME 查看器应用程序以查看该邮件并发送加密的答复。本文介绍如何。  <br/> |
|[在 iPhone 或 iPad 上查看加密的邮件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |已收到邮件加密与 Office 365 邮件加密 iPhone 或 iPad 上的最终用户，您可以使用免费 OME 查看器应用程序以查看该邮件并发送加密的答复。本文介绍如何。  <br/> |
|Office 365 邮件加密 (OME) （本文）  <br/> |Office 365 或 Exchange Online Protection 管理员希望了解您可以在其中找到其他资源。  <br/> |
|[比较 OME 的版本](ome-version-comparison.md)  <br/> |Office 365 或 Exchange Online Protection 管理员希望了解旧的 Office 365 邮件加密和新的 OME 功能之间的差异，它们可以协同工作的方式。  <br/> |
|[Office 365 邮件加密常见问题解答](ome-faq.md) <br/> |Office 365 或 Exchange Online Protection 管理员通常有力答案常见问题包括许可和新功能和旧 OME 之间的比较。  <br/> |
|[设置全新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md) <br/> |Office 365 或 Exchange Online Protection 的管理员希望了解如何设置新的 Office 365 组织的 Office 365 邮件加密功能。  <br/> |
|[定义用于加密 Office 365 中的电子邮件的邮件流规则](define-mail-flow-rules-to-encrypt-email.md) <br/> |具有已设置 Office 365 邮件加密和您的 Office 365 或 Exchange Online Protection 管理员便可定义邮件流规则进行自动加密从组织发出的电子邮件。  <br/> |
|[管理 Office 365 邮件加密](manage-office-365-message-encryption.md) <br/> |Office 365 或 Exchange Online Protection 管理员已设置 Office 365 邮件加密和想要配置的 OME 可选设置。  <br/> |
|[在加密的邮件中添加组织的品牌名称](add-your-organization-brand-to-encrypted-messages.md) <br/> |Office 365 或 Exchange Online Protection 的管理员希望应用您公司品牌自定义您的组织的 Office 365 邮件加密电子邮件的外观和 OME 门户的内容。  <br/> |
|[Office 365 邮件加密电子邮件吊销](revoke-ome-encrypted-mail.md) <br/> |Office 365 或 Exchange Online Protection 的管理员希望取消使用 Office 365 邮件加密加密电子邮件。  <br/> |
|[邮件策略和合规性服务说明](https://technet.microsoft.com/en-us/library/5c43c8eb-f8f7-4b5a-a743-b1dab7dc2fc8#bkmk_O365_MessageEncryption)中的 office 365 邮件加密 <br/> |查找有关 Office 365 邮件加密功能的详细说明，包括支持 Sku，可从 Office 365。  <br/> |
|[Office 365 邮件加密的旧信息](legacy-information-for-message-encryption.md) <br/> |具有已设置 Office 365 邮件加密和您的 Office 365 或 Exchange Online Protection 管理员希望 OME 之前的版本的新功能的工作方式的信息。时无法设置新部署的新功能，不使用 OME，Microsoft 将继续支持现有部署。  <br/> |
||

本文的其余部分适用于新 OME 功能。
  
## <a name="how-office-365-message-encryption-works"></a>Office 365 邮件加密的工作原理

Office 365 邮件加密是基于 Microsoft Azure 权限管理 (Azure RMS) Azure 信息保护的一部分的联机服务。Office 365 管理员可以定义邮件流规则来确定加密的条件。例如，规则可以要求的所有邮件发送到特定收件人的加密。
  
当某人发送一封电子邮件 in Exchange Online 的加密邮件流规则相匹配时，在发送之前对邮件进行加密。使用 Outlook 客户端读取邮件的所有 Office 365 最终用户都收到本机、 一流阅读加密和受权限保护的邮件的体验，即使它们不在同一组织为发件人。支持的 Outlook 客户端包括 Outlook 桌面，Outlook Mac 上 iOS 和 Android，移动 Outlook 和 Outlook Web App。
  
接收加密或权限保护的邮件发送到其 Outlook.com、 Gmail 和 Yahoo 帐户加密邮件的收件人可以轻松地到 OME 门户使用其 Microsoft 帐户或 Gmail 或 Yahoo 凭据进行验证。
  
读取 Outlook 之外的客户端上的加密或权限保护邮件的最终用户还使用 OME 门户查看加密和受权限保护收到的邮件。
  
我们已增加邮件和附件，您可以使用 Office 365 邮件加密来加密的大小的限制。有关限制的详细信息，请参阅[Exchange Online 限制。](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
  
## <a name="defining-rules-for-office-365-message-encryption"></a>定义 Office 365 邮件加密的规则

Exchange Online 和 Exchange Online Protection 管理员定义邮件流规则是一种方法来为 Office 365 邮件加密启用新功能。这些规则确定应在哪些条件电子邮件加密邮件。当加密操作设置规则时，匹配的规则条件的任何邮件进行加密，他们正在发送之前。
  
邮件流规则是灵活，让您组合条件，所以您可以满足在单个规则中的特定的安全要求。例如，您可以创建所有包含指定的关键词和发往外部收件人的邮件进行加密的规则。Office 365 邮件加密的新功能还加密从加密电子邮件的收件人的答复。
  
有关如何创建邮件流规则以充分利用新的 OME 功能的详细信息，请参阅[Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>发送、查看和回复加密电子邮件

与 Office 365 邮件加密，用户可以从 Outlook 和 Outlook web 上的发送加密电子邮件。此外，管理员可以设置 Office 365 中的邮件流规则进行自动加密电子邮件基于关键字匹配或其他条件。
  
Office 365 组织中的加密邮件的收件人将能够读取在任何版本的 Outlook，包括 PC 的 Outlook、 Outlook for Mac、 web 上的 Outlook、 适用于 iOS，Outlook 和 Outlook for Android 中无缝这些邮件。接收其他电子邮件客户端上的加密的邮件的用户可以查看 OME 门户中的消息。
  
有关如何发送和查看加密的邮件的详细指南，了解一下这些文章：
  
- [如何打开受保护的邮件？](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)

- [发送、 查看和回复 Outlook 中的加密邮件](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)

## <a name="get-started-with-the-new-ome-capabilities"></a>开始使用新的 OME 功能

如果您已准备好开始使用您的组织中的新 OME 功能，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

---
title: Office 365 邮件加密
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: 使用 Office 365 邮件加密, 组织可以在组织内部和外部的人员之间发送和接收加密的电子邮件。 电子邮件加密有助于确保只有预期的收件人可以查看邮件内容。
ms.openlocfilehash: d9716d3021f4190f1679a5d387e9378b60586154
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157584"
---
# <a name="office-365-message-encryption"></a>Office 365 邮件加密

人们经常使用电子邮件来交换敏感信息，例如财务数据、法律合同、机密产品信息、销售报表和预测、患者健康信息或客户和员工信息。因此，邮箱可能会成为一个包含大量潜在敏感信息的存储库，信息泄露可能会成为您组织的严重威胁。

使用 Office 365 邮件加密, 组织可以在组织内部和外部的人员之间发送和接收加密的电子邮件。 Office 365 邮件加密适用于 Outlook.com、Yahoo!、Gmail 和其他电子邮件服务。 电子邮件加密有助于确保只有预期的收件人可以查看邮件内容。
  
本文的其余部分适用于新的 OME 功能。
  
## <a name="how-office-365-message-encryption-works"></a>Office 365 邮件加密的工作原理

Office 365 邮件加密是基于 Microsoft Azure 权限管理 (Azure RMS) 构建的一种在线服务, 它是 Azure 信息保护的一部分。 这包括加密、标识和授权策略, 以帮助保护您的电子邮件。 您可以使用权限管理模板、"不[转发](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)" 和 "[仅加密" 选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)对邮件进行加密。

然后, 用户可以使用这些选项来加密电子邮件和各种 Office 365 附件。 有关受支持的附件类型的完整列表, 请参阅[关于电子邮件的 Irm 简介中的 "在将 irm 策略附加到邮件时受 irm 策略覆盖的文件类型"](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)。

作为管理员, 您还可以定义邮件流规则以应用此保护。 例如, 您可以创建需要对发送到特定收件人的所有邮件进行加密, 或在主题行中包含特定词语的规则, 同时指定收件人无法复制或打印邮件的内容。

与早期版本的 OME 不同, 新功能提供了统一的发件人体验, 无论您是将邮件发送到组织内部还是位于 Office 365 之外的收件人。 此外, 收到受保护电子邮件的收件人将发送到 Outlook 2016 中的 Office 365 帐户或 web 上的 Outlook, 而无需执行任何其他操作来查看邮件。 无缝运行。 使用其他电子邮件客户端和电子邮件服务提供商的收件人也具有改进的体验。 有关信息, 请参阅[了解 Office 365 中的受保护邮件](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)和[如何打开受保护的邮件](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)。

有关 OME 的早期版本和新的 OME 功能之间的差异的详细列表, 请参阅[比较版本的 OME](ome-version-comparison.md)。

当某人发送与加密邮件流规则匹配的电子邮件时, 会在发送邮件之前对其进行加密。 所有使用 Outlook 客户端的 Office 365 最终用户读取邮件接收对加密和受权限保护的邮件的本机、第一类阅读体验, 即使它们与发件人不在同一组织中也是如此。 支持的 Outlook 客户端包括 Outlook 桌面、Outlook Mac、iOS 和 Android 上的 Outlook 移动以及 web 上的 Outlook (以前称为 Outlook Web App)。
  
接收加密邮件或受权限保护的邮件发送到其 Outlook.com、Gmail 和 Yahoo 帐户的收件人将收到一封包装邮件, 该邮件将其定向到 OME 门户, 在该门户中, 可以使用 Microsoft 帐户、Gmail 或Yahoo 凭据。
  
在 Outlook 之外的客户端上阅读加密或受权限保护邮件的最终用户也使用 OME 门户来查看他们收到的加密邮件和受权限保护的邮件。

此外, 如果受保护邮件的发件人在 GCC 高, 且收件人不在 GCC 高 (包括商业 Office 365 用户、Outlook.com 用户和其他电子邮件提供商 (如 Gmail) 的用户) 中, 则收件人会收到可重定向到的包装邮件收件人能够读取和回复邮件的 OME 门户。 否则, 如果发件人和收件人在 GCC 高环境中, 则使用 Outlook 客户端读取邮件的收件人可接收对加密和受权限保护的邮件的本机、第一类阅读体验, 即使它们不在同一组织中也是如此作为发件人。 有关 GCC High 中的不同体验的详细信息, 请参阅[比较版本的 OME](ome-version-comparison.md)。
  
增加了您可以使用 OME 加密的邮件和附件的大小限制。 有关限制的详细信息, 请参阅[Exchange Online 限制](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)。

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Office 365 高级邮件加密在 OME 上的工作原理

Office 365 高级邮件加密功能使您可以创建多个品牌打造模板, 以便您可以微调对收件人邮件的控制并创建自定义品牌打造体验以支持不同的组织结构。

Office 365 中的高级邮件加密帮助您满足合规性义务, 这些要求需要更灵活地控制外部收件人对加密电子邮件的访问。 使用 Office 365 中的高级邮件加密作为管理员, 您可以控制在组织外共享的敏感电子邮件以及检测敏感信息类型 (如 PII、财务或运行状况 Id) 的自动策略, 或要增强的关键字通过将安全 web 门户访问加密电子邮件来实现保护。 此外, 作为管理员, 您可以通过 Office 365 web 门户来进一步控制在外部访问的加密电子邮件, 方法是随时撤销对电子邮件的访问权限。

邮件吊销和过期仅适用于您的用户向您的 Office 365 组织之外的收件人发送的电子邮件。 此外, 收件人必须通过 web 门户访问电子邮件。 为了确保收件人使用门户接收电子邮件, 您设置了一个应用包装的自定义品牌模板。 然后, 在邮件流规则中应用品牌模板。 有关高级邮件加密的详细信息, 请参阅[Office 365 高级邮件加密](https://ome-advanced-message-encryption.md)。

## <a name="defining-rules-for-office-365-message-encryption"></a>定义 Office 365 邮件加密的规则

启用 Office 365 邮件加密的新功能的一种方法是 Exchange Online 和 Exchange Online Protection 管理员定义邮件流规则。 这些规则确定应在哪些条件下加密电子邮件。 为规则设置加密操作后, 与规则条件匹配的任何邮件在发送之前都会被加密。
  
邮件流规则是灵活的, 允许您将条件组合在一起, 以便您可以在单个规则中满足特定的安全要求。 例如，您可以创建一个规则，对包含特定关键字且发送给外部收件人的所有邮件进行加密。 Office 365 邮件加密的新功能还对来自加密电子邮件收件人的答复进行加密。
  
有关如何创建邮件流规则以利用新的 OME 功能的详细信息, 请参阅[Define rules For Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="get-started-with-the-new-ome-capabilities"></a>开始使用新的 OME 功能

如果你已准备好开始使用组织中的新 OME 功能, 请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>发送、查看和回复加密电子邮件

使用 Office 365 邮件加密, 用户可以从 Outlook 和 web 上的 Outlook 发送加密电子邮件。 此外, 管理员还可以设置 Office 365 中的邮件流规则, 以根据关键字匹配或其他条件自动加密电子邮件。
  
Office 365 组织中的加密邮件收件人将能够在任何版本的 Outlook 中无缝阅读这些邮件, 包括 Outlook for PC、Outlook for Mac、Outlook 网页版、Outlook for iOS 和 Outlook for Android。 在其他电子邮件客户端上接收加密邮件的用户可以在 OME 门户中查看这些邮件。
  
有关如何发送和查看加密邮件的详细指导, 请参阅以下文章:
  
|||
|:-----|:-----|
|阅读本文 .。。  <br/> |如果您是 .。。  <br/> |
|[了解 Office 365 中的受保护邮件](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx) <br/> |想要详细了解加密邮件的工作方式以及可供您使用的选项的最终用户。  <br/> |
|[如何打开受保护的邮件？](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx) <br/> |要读取已发送给您的受保护邮件的最终用户。 本文包含有关在 Outlook 的多个版本以及来自不同的电子邮件帐户 (包括与 gmail 和 yahoo! 等外部的电子邮件帐户) 中读取邮件365的信息。 账号.  <br/> |
|[在 Outlook 中发送、查看和回复加密邮件](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx) <br/> |要从 Outlook 发送、查看或回复加密邮件的最终用户。 即使您不是 Office 365 组织的成员, 仍会收到在 Outlook 中发送给您的加密邮件的通知。 使用此文章可获取有关如何查看和回复从 Office 365 发送的加密邮件的说明。  <br/> |
|[发送经过数字签名或加密的邮件](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547) <br/> |希望使用 Outlook for Mac 发送、查看或回复加密邮件的最终用户。 本文还介绍了如何使用 OME 以外的加密方法, 如 S/MIME。  <br/> |
|[在 Android 设备上查看加密邮件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> |已收到使用 Office 365 邮件加密在 Android 设备上加密的邮件的最终用户, 可以使用免费的 OME 查看器应用程序查看邮件并发送加密答复。 本文介绍如何操作。  <br/> |
|[查看 iPhone 或 iPad 上的加密邮件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |已收到使用 Office 365 邮件加密在 iPhone 或 iPad 上加密的邮件的最终用户, 您可以使用免费的 OME 查看器应用来查看邮件并发送加密答复。 本文介绍如何操作。  <br/> |
||
---
title: Office 365 邮件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/6/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: 使用 Office 365 邮件加密, 组织可以在组织内部和外部的人员之间发送和接收加密的电子邮件。 电子邮件加密有助于确保只有预期的收件人可以查看邮件内容。
ms.openlocfilehash: 06c43bcb3364b83114e2d7b1a2ef0273858cffb0
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261310"
---
# <a name="office-365-message-encryption"></a>Office 365 邮件加密

使用 Office 365 邮件加密, 组织可以在组织内部和外部的人员之间发送和接收加密的电子邮件。 Office 365 邮件加密适用于 Outlook.com、yahoo!、Gmail 和其他电子邮件服务。 电子邮件加密有助于确保只有预期的收件人可以查看邮件内容。
  
本文是有关 Office 365 邮件加密的更多系列文章的一部分。 使用下表可以快速查找所需信息。
  
|||
|:-----|:-----|
|阅读本文 .。。  <br/> |如果您是 .。。  <br/> |
|[了解 Office 365 中的受保护邮件](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx) <br/> |想要详细了解加密邮件的工作方式以及可供您使用的选项的最终用户。  <br/> |
|[如何打开受保护的邮件？](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx) <br/> |要读取已发送给您的受保护邮件的最终用户。 本文包含有关在 Outlook 的多个版本以及来自不同的电子邮件帐户 (包括与 gmail 和 yahoo! 等外部的电子邮件帐户) 中读取邮件的信息。 账号.  <br/> |
|[在 Outlook 中发送、查看和回复加密邮件](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx) <br/> |要从 Outlook 发送、查看或回复加密邮件的最终用户。 即使您不是 Office 365 组织的成员, 仍会收到在 Outlook 中发送给您的加密邮件的通知。 使用此文章可获取有关如何查看和回复从 Office 365 发送的加密邮件的说明。  <br/> |
|[发送经过数字签名或加密的邮件](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547) <br/> |希望使用 Outlook for Mac 发送、查看或回复加密邮件的最终用户。 本文还介绍了如何使用 OME 以外的加密方法, 如 S/MIME。  <br/> |
|[在 Android 设备上查看加密邮件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> |已收到使用 Office 365 邮件加密在 Android 设备上加密的邮件的最终用户, 可以使用免费的 OME 查看器应用程序查看邮件并发送加密答复。 本文介绍如何操作。  <br/> |
|[查看 iPhone 或 iPad 上的加密邮件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |已收到使用 Office 365 邮件加密在 iPhone 或 iPad 上加密的邮件的最终用户, 您可以使用免费的 OME 查看器应用来查看邮件并发送加密答复。 本文介绍如何操作。  <br/> |
|Office 365 邮件加密 (OME) (本文)  <br/> |一种 Office 365 或 Exchange Online Protection 管理员, 希望了解在哪里可以找到其他资源。  <br/> |
|[比较 OME 的版本](ome-version-comparison.md)  <br/> |office 365 或 Exchange Online Protection 管理员, 希望了解旧版 Office 365 邮件加密和新 OME 功能之间的差异, 以及它们如何协同工作。  <br/> |
|[Office 365 邮件加密常见问题解答](ome-faq.md) <br/> |要解答常见问题的 Office 365 或 Exchange Online Protection 管理员, 其中包括许可以及新功能和旧 OME 之间的比较。  <br/> |
|[设置全新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md) <br/> |想要了解如何为 office 365 组织设置新的 office 365 邮件加密功能的 Office 365 或 Exchange Online Protection 管理员。  <br/> |
|[定义用于加密 Office 365 中的电子邮件的邮件流规则](define-mail-flow-rules-to-encrypt-email.md) <br/> |已设置 office 365 邮件加密的 office 365 或 Exchange Online Protection 管理员, 并准备好定义邮件流规则, 以自动对从您的组织发送的电子邮件进行加密。  <br/> |
|[管理 Office 365 邮件加密](manage-office-365-message-encryption.md) <br/> |已设置 office 365 邮件加密并希望为 OME 配置可选设置的 Office 365 或 Exchange Online Protection 管理员。  <br/> |
|[在加密的邮件中添加组织的品牌名称](add-your-organization-brand-to-encrypted-messages.md) <br/> |想要应用公司品牌的 Office 365 或 Exchange Online Protection 管理员, 以自定义组织的 Office 365 邮件加密电子邮件的外观和 OME 门户的内容。  <br/> |
|[Office 365 邮件加密电子邮件吊销](revoke-ome-encrypted-mail.md) <br/> |要吊销使用 office 365 邮件加密进行加密的电子邮件的 Office 365 或 Exchange Online Protection 管理员。  <br/> |
|[邮件策略和合规性服务说明](https://technet.microsoft.com/en-us/library/5c43c8eb-f8f7-4b5a-a743-b1dab7dc2fc8#bkmk_O365_MessageEncryption)中的 Office 365 邮件加密 <br/> |在 office 365 中查找 office 365 邮件加密功能 (包括受支持的 sku) 的详细说明。  <br/> |
|[Office 365 邮件加密的旧信息](legacy-information-for-message-encryption.md) <br/> |已设置 office 365 邮件加密的 office 365 或 Exchange Online Protection 管理员, 您需要有关 OME 在新功能发布之前的工作方式的信息。 虽然您无法使用不具有新功能的 OME 设置新的部署, 但 Microsoft 仍将继续支持现有部署。 <br/> |
||

本文的其余部分适用于新的 OME 功能。
  
## <a name="how-office-365-message-encryption-works"></a>Office 365 邮件加密的工作原理

Office 365 邮件加密是基于 Microsoft azure 权限管理 (azure RMS) 构建的一种在线服务, 它是 Azure 信息保护的一部分。 这包括加密、标识和授权策略, 以帮助保护您的电子邮件。 您可以使用权限管理模板、"不[转发](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)" 和 "[仅加密" 选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)对邮件进行加密。

然后, 用户可以使用这些选项来加密电子邮件和各种 Office 365 附件。 有关受支持的附件类型的完整列表, 请参阅[关于电子邮件的 irm 简介中的 "在将 irm 策略附加到邮件时受 irm 策略覆盖的文件类型"](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)。

作为管理员, 您还可以定义邮件流规则以应用此保护。 例如, 您可以创建需要对发送到特定收件人的所有邮件进行加密, 或在主题行中包含特定词语的规则, 同时指定收件人无法复制或打印邮件的内容。

与早期版本的 OME 不同, 新功能提供了统一的发件人体验, 无论您是将邮件发送到组织内部还是位于 Office 365 之外的收件人。 此外, 收到受保护电子邮件的收件人将发送到 Outlook 2016 中的 Office 365 帐户或 web 上的 outlook, 而无需执行任何其他操作来查看邮件。 无缝运行。 使用其他电子邮件客户端和电子邮件服务提供商的收件人也具有改进的体验。 有关信息, 请参阅[了解 Office 365 中的受保护邮件](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)和[如何打开受保护的邮件](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)。

有关 OME 的早期版本和新的 OME 功能之间的差异的详细列表, 请参阅[比较版本的 OME](ome-version-comparison.md)。

当某人发送与加密邮件流规则匹配的电子邮件时, 会在发送邮件之前对其进行加密。 所有使用 Outlook 客户端的 Office 365 最终用户读取邮件接收对加密和受权限保护的邮件的本机、第一类阅读体验, 即使它们与发件人不在同一组织中也是如此。 支持的 outlook 客户端包括 outlook 桌面、outlook Mac、iOS 和 Android 上的 outlook 移动以及 web 上的 outlook (以前称为 outlook web App)。
  
接收加密邮件或受权限保护的邮件发送到其 Outlook.com、gmail 和 Yahoo 帐户的收件人将收到一封包装邮件, 该邮件将其定向到 OME 门户, 在该门户中, 可以使用 Microsoft 帐户、Gmail 或Yahoo 凭据。
  
在 Outlook 之外的客户端上阅读加密或受权限保护邮件的最终用户也使用 OME 门户来查看他们收到的加密邮件和受权限保护的邮件。

此外, 如果受保护邮件的发件人在 gcc 高, 且收件人不在 gcc 高 (包括商业 Office 365 用户、Outlook.com 用户和其他电子邮件提供商 (如 Gmail) 的用户) 中, 则收件人会收到可重定向到的包装邮件收件人能够读取和回复邮件的 OME 门户。 否则, 如果发件人和收件人在 GCC 高环境中, 则使用 Outlook 客户端读取邮件的收件人可接收对加密和受权限保护的邮件的本机、第一类阅读体验, 即使它们不在同一组织中也是如此作为发件人。
  
增加了您可以使用 OME 加密的邮件和附件的大小限制。 有关限制的详细信息, 请参阅[Exchange Online 限制](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)。
  
## <a name="defining-rules-for-office-365-message-encryption"></a>定义 Office 365 邮件加密的规则

启用 Office 365 邮件加密的新功能的一种方法是 exchange online 和 exchange online Protection 管理员定义邮件流规则。 这些规则确定应在哪些条件下加密电子邮件。 为规则设置加密操作后, 与规则条件匹配的任何邮件在发送之前都会被加密。
  
邮件流规则是灵活的, 允许您将条件组合在一起, 以便您可以在单个规则中满足特定的安全要求。 例如，您可以创建一个规则，对包含特定关键字且发送给外部收件人的所有邮件进行加密。 Office 365 邮件加密的新功能还对来自加密电子邮件收件人的答复进行加密。
  
有关如何创建邮件流规则以利用新的 OME 功能的详细信息, 请参阅[Define rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>发送、查看和回复加密电子邮件

使用 Office 365 邮件加密, 用户可以从 outlook 和 web 上的 outlook 发送加密电子邮件。 此外, 管理员还可以设置 Office 365 中的邮件流规则, 以根据关键字匹配或其他条件自动加密电子邮件。
  
Office 365 组织中的加密邮件收件人将能够在任何版本的 outlook 中无缝阅读这些邮件, 包括 outlook for PC、outlook for Mac、outlook 网页版、outlook for iOS 和 outlook for Android。 在其他电子邮件客户端上接收加密邮件的用户可以在 OME 门户中查看这些邮件。
  
有关如何发送和查看加密邮件的详细指导, 请参阅以下文章:
  
- [如何打开受保护的邮件？](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)

- [在 Outlook 中发送、查看和回复加密邮件](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)

## <a name="get-started-with-the-new-ome-capabilities"></a>开始使用新的 OME 功能

如果你已准备好开始使用组织中的新 OME 功能, 请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

---
title: Office 365 邮件加密版本比较
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
description: 可以帮助您理解的两个继续为协同工作的方式与不同版本的 Office 365 邮件加密以及传递的功能差异。
ms.openlocfilehash: a418d840c7e0eb50ae076bf2b03164bef9488058
ms.sourcegitcommit: 88f3982217c29b558e3f9e838bcb425da395dd5e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2019
ms.locfileid: "29708539"
---
# <a name="compare-versions-of-ome"></a>比较 OME 的版本

本文比较旧 Office 365 邮件加密的新 OME 功能。新的功能是合并和较新版本的 OME 和信息权限管理 (IRM)。我们还将介绍如何两个可以共存于您的 Office 365 组织。

||
|:-----|
|本文是系列的有关 Office 365 邮件加密的文章的较大一部分。本文旨在为管理员和 ITPros。如果您只查找有关的信息发送或接收加密的邮件， [Office 365 邮件加密 (OME)](ome.md)中的文章的列表，请参阅并找到最适合您的需求的文章。 |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>特性和功能的并行比较

|                                   |旧功能       |                   |新增功能              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**功能**                     | **旧 OME**    | **IRM**           | **OME 的新功能** |
|*发送加密的邮件*        |通过 Exchange 邮件流规则|最终用户从 Outlook 桌面或 Outlook Web; 上启动或通过 Exchange 邮件流规则|最终用户从 Outlook 桌面、 for Mac、 Outlook 或 Outlook Web; 上启动通过 Exchange 传输规则和 Office 365 数据丢失防护 (DLP)|
|*权限管理模板*       |   不适用      |不转接选项和自定义模板|执行不转接选项，仅加密选项和自定义模板|
|*收件人类型*                   |内部和外部收件人|仅内部收件人         |内部和外部收件人|
|*内部收件人的体验*|收件人收到 HTML 邮件，其中他们下载并在 web 浏览器或移动应用程序中打开|Outlook 客户端中的本机内嵌体验|Office 365 收件人的本机内嵌体验。所有其他收件人可以阅读邮件从 OME 门户 （任何下载或所需的应用程序）。|
|*外部收件人的体验*|收件人收到 HTML 邮件，其中他们下载并在 web 浏览器或移动应用程序中打开|不适用|Office 365 收件人的本机内嵌体验。所有其他收件人可以阅读邮件从 OME 门户 （任何下载或所需的应用程序）。|
|*附件权限*           |附件没有限制|受保护附件|不要转发选项和自定义模板的受保护附件。管理员可以选择是否或不受保护附件仅加密选项。|
|*使您自己的密钥 (BYOK) 支持*|无                |无               |BYOK 支持          |
||

## <a name="advantages-of-using-the-new-ome-capabilities-over-legacy-ome"></a>通过旧 OME 使用的新功能，OME 的优点

新功能提供以下优点：

- 能够使用加密仅 （使安全协作），不要转发，以及自定义的限制。
- 发件人可以发送的新功能，从 Outlook 桌面、 Outlook for Mac 和 web 客户端上的 Outlook 中手动使用加密的邮件。
- Office 365 收件人获取中支持的 Outlook 客户端使用内联体验。此外，管理员可以选择要显示的品牌的体验的 Office 365 收件人。
- 与 OME 门户中，为这些收件人提供更好的用户体验联盟 Gmail、 Yahoo 和 Microsoft 帐户，例如 Office 365 以外的帐户。所有其他标识使用一次性密码来访问加密的邮件。
- 管理员可以自定义品牌和创建多个品牌模板。
- 管理员可以取消的新功能，通过加密的电子邮件。
- 新功能提供通过安全性的详细的使用率报告&amp;合规性中心。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>旧 OME 和同一租户中的新功能共存

可以在同一租户中使用旧 OME 和新功能。作为管理员，您选择哪个版本的 OME 您想要使用创建您的邮件流规则时执行此操作。

- 若要指定 OME 的旧版本，请使用 Exchange 邮件流规则操作"应用 OME 的早期版本"。
- 若要指定的新功能，请使用 Exchange 邮件流规则操作"应用 Office 365 邮件加密和权限保护"。

用户还可以发送的新功能，从 Outlook 桌面、 Outlook for Mac 和 web 客户端上的 Outlook 中手动使用加密的邮件。

## <a name="migrating-from-legacy-ome-to-the-new-capabilities"></a>从旧 OME 迁移到新功能

即使 OME 的两个版本可以共存，我们强烈建议您编辑您使用的规则操作的旧邮件流规则"应用 OME 的早期版本"使用指定的邮件流规则操作"应用 Office 365 邮件加密的新功能和权限保护"。有关说明，请参阅[定义邮件流规则来加密 Office 365 中的电子邮件](define-mail-flow-rules-to-encrypt-email.md)。

## <a name="getting-started-with-ome"></a>入门 OME

通常情况下，为您的 Office 365 组织自动启用新的 OME 功能。如果您已准备好开始使用您的组织中的新 OME 功能，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

如果启用了 Azure 信息保护，会自动为您的 Office 365 组织启用 OME 的旧版本。过去，旧 OME 有效即使 Azure 信息保护未启用。不再是这样。

要开始使用旧 OME，如果已启用 Azure 信息保护，您需要执行所有，可以配置邮件流规则，使用"应用 OME 的早期版本"的规则操作。有关说明，请参阅[定义邮件流规则来加密 Office 365 中的电子邮件](define-mail-flow-rules-to-encrypt-email.md)。
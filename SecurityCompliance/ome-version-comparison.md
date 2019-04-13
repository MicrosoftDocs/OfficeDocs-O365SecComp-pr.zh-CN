---
title: Office 365 邮件加密 (OME) 版本比较
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 帮助解释随不同版本的 Office 365 邮件加密提供的功能之间的差异, 以及这两个如何继续协同工作。
ms.openlocfilehash: bb13208e2b630c8a6217b78b48a4cd3bb4b0de79
ms.sourcegitcommit: 895f67531f2b4afe46c7487ca5b44555ca791bae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2019
ms.locfileid: "31836836"
---
# <a name="compare-versions-of-ome"></a>比较 OME 的版本

本文将旧版 Office 365 邮件加密 (OME) 与新的 OME 功能进行比较。 新功能是 OME 和信息权限管理 (IRM) 的合并和更新版本。 此外, 还概述了将部署到 GCC 高的独特特征。 我们还将介绍这两个如何在 Office 365 组织中共存。

||
|:-----|
|本文是有关 Office 365 邮件加密的更多系列文章的一部分。 本文适用于管理员和 ITPros。 如果只是查找有关发送或接收加密邮件的信息, 请参阅[Office 365 邮件加密 (OME)](ome.md)中的文章列表, 并找到最符合您的需求的文章。 |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>特性和功能的并排比较

|                                   |旧功能       |                   |新增功能              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**功能**                     | **旧版 OME**    | **IRM**           | **新的 OME 功能** |
|*发送加密邮件*        |通过 Exchange 邮件流规则|最终用户是从 Outlook 桌面或 Web 上的 outlook 启动的;或通过 Exchange 邮件流规则|最终用户从 outlook 桌面、outlook for Mac 或 Web 上的 outlook 启动;通过 Exchange 邮件流规则 (也称为传输规则) 和 Office 365 数据丢失防护 (DLP)|
|*权限管理模板*       |   不适用      |"不要转发" 选项和自定义模板|不转发选项、仅加密选项和自定义模板|
|*收件人类型*                   |内部和外部收件人|仅限内部收件人         |内部和外部收件人|
|*内部收件人的体验*|收件人收到 HTML 邮件, 并在 web 浏览器或移动应用程序中将其下载和打开|Outlook 客户端中的本机内嵌体验|Office 365 收件人的本机内嵌体验。 所有其他收件人都可以从 OME 门户读取邮件 (无需下载或应用程序)。|
|*外部收件人的体验*|收件人收到 HTML 邮件, 并在 web 浏览器或移动应用程序中将其下载和打开|不适用|Office 365 收件人的本机内嵌体验。 所有其他收件人都可以从 OME 门户读取邮件 (无需下载或应用程序)。|
|*附件权限*           |对附件没有限制|附件受到保护|附件受到保护, 可用于 "不转发" 选项和自定义模板。 管理员可以选择仅加密选项的附件是否受保护。|
|*引入你自己的密钥 (BYOK) 支持*|无                |无               |支持的 BYOK          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>新的 OME 功能与旧版 OME 的优势

新功能具有以下优点:

- 能够使用仅加密 (启用安全协作)、不转发和自定义限制。
- 发件人可以使用新功能从 outlook Desktop、outlook for Mac 和 web 客户端上的 outlook 手动发送已加密的邮件。
- Office 365 收件人在受支持的 Outlook 客户端中使用内嵌体验。 此外, 管理员还可以选择向 Office 365 收件人显示品牌丰富的体验。
- Office 365 之外的帐户 (如 Gmail、Yahoo 和 Microsoft 帐户) 与 OME 门户联合在一起, 从而为这些收件人提供了更好的用户体验。 所有其他标识都使用一次性传递代码来访问加密的邮件。
- 管理员可以自定义品牌打造和创建多个品牌打造模板。
- 管理员可以使用新功能撤消加密电子邮件。
- 新功能通过安全&amp;合规性中心提供详细的使用情况报告。

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>GCC 高部署中的 Office 365 邮件加密的独特特征

如果您计划在 GCC 高环境中使用 Office 365 邮件加密, 则有一些关于收件人体验的独特特征。

### <a name="encrypted-email-from-gcc-high-to-gcc-high-recipients"></a>来自 gcc 高到 gcc 的加密电子邮件高收件人

发件人可以在 Outlook 中为电脑和 Mac 和 outlook 网页版手动加密电子邮件, 或者组织可以设置策略以使用 Exchange 邮件流规则对电子邮件进行加密。

GCC 内的收件人在 Outlook 中对电脑和 Mac 和 outlook 网页版中的所有其他 Office 365 用户都具有相同的内嵌阅读体验。

### <a name="encrypted-email-from-gcc-high-to-non-gcc-high-recipients"></a>来自 gcc 高到非 GCC 高收件人的加密电子邮件

gcc high 中的发件人可以在 gcc 的高边界之外发送加密电子邮件。

所有超出 GCC 的收件人, 包括商业 Office 365 用户、Outlook.com 用户和其他电子邮件提供商 (如 Gmail 和 Yahoo) 的用户, 接收将收件人重定向到 OME 门户的包装邮件, 以便收件人能够读取和答复邮件。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>旧版 OME 的共存和同一租户中的新功能

您可以在同一个租户中使用这两个旧的 OME 和新功能。 作为管理员, 您可以通过在创建邮件流规则时选择要使用的 OME 版本来执行此操作。

- 若要指定旧版本的 OME, 请使用 Exchange 邮件流规则操作 "**应用以前版本的 OME"**。
- 若要指定新的功能, 请使用 Exchange 邮件流规则操作 "**应用 Office 365 邮件加密" 和 "权限保护**"。

用户可以使用 outlook Desktop 中的新功能、outlook for Mac 和 web 上的 outlook 手动发送已加密的邮件。

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>从旧 OME 迁移到新功能

尽管这两个版本的 OME 都可以共存, 但我们强烈建议您编辑旧的邮件流规则, 这些规则使用规则操作 "**应用以前版本的 OME** " 以使用新功能。 更新这些规则以使用邮件流规则操作 "**应用 Office 365 邮件加密" 和 "权限保护**"。 有关说明, 请参阅[在 Office 365 中定义用于加密电子邮件的邮件流规则](define-mail-flow-rules-to-encrypt-email.md)。

## <a name="get-started-with-ome"></a>开始使用 OME

通常情况下, 会自动为 Office 365 组织启用新的 OME 功能。 有关贵组织内的新 OME 功能的详细信息, 请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

如果已启用 Azure 信息保护, 则将自动为 Office 365 组织启用旧版本的 OME。 以前, 即使未启用 Azure 信息保护, 旧版 OME 也能正常工作。 但现在不再如此。

若要开始使用旧版 OME, 如果已启用 Azure 信息保护, 只需配置使用规则操作的邮件流规则。**应用以前版本的 OME**。 有关说明, 请参阅[在 Office 365 中定义用于加密电子邮件的邮件流规则](define-mail-flow-rules-to-encrypt-email.md)。
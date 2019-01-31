---
title: 使用 Exchange Online 和安全与合规中心来遵守 SEC 规则 17a-4
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Cohasset Associates 已验证，当 Exchange Online 和安全与合规中心按建议配置时，它们满足 CFTC 规则 1.31(c)-(d)、FINRA 规则 4511 和 SEC 规则 17a-4 的相关存储要求。可以下载评估报告。
ms.openlocfilehash: 0b81c99eeff65e5e9d98c6167d8e8f52b9535d98
ms.sourcegitcommit: d05a9937780d210b7ad48e721b947397ac5405a2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29610559"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a>使用 Exchange Online 和安全与合规中心来遵守 SEC 规则 17a-4

如果组织需要遵守保留数据的相关法规标准，Office 365 安全与合规中心将提供一些功能来管理 Exchange Online 中数据的生命周期。包括保留、审核、搜索和导出数据的功能。这些功能足以满足大多数组织的需求。

然而，高度监管行业中的某些组织会受到更严格的法规要求。例如，银行或经纪交易商等金融机构必须遵守美国证券交易委员会 (SEC) 颁布的规则 17a-4。这条规则对电子数据存储有特定要求，包括记录管理的许多方面，如记录保留的持续时间、格式、质量、可用性和责任。

为了帮助这些组织更好地了解如何利用安全与合规中心来履行其对 Exchange Online 的监管义务，特别是与规则 17a-4 要求相关的监管义务，我们已与 Cohasset Associates 合作发布了一份评估报告。

Cohasset 验证了当 Exchange Online 和安全与合规中心按照建议进行配置时，它们将符合 CFTC 规则 1.31(c)-(d)、FINRA 规则 4511 和 SEC 规则 17a-4 的相关存储要求。我们以这组规则为准绳，因为它们代表了针对金融机构保留记录的最为规范的全球性指导。

## <a name="download-the-cohasset-assessment"></a>下载 Cohasset 评估报告

可[在此处下载 Cohasset 评估报告](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)。

![Cohasset Associates 可下载评估的标题页](media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a>此评估专门针对 Exchange Online

请注意，此评估专门针对 Exchange Online。该评估不包括其他 Office 365 服务，如 SharePoint Online 或 OneDrive for Business（尽管我们计划在未来就 SEC 17a-4 对这些服务提供支持）。

请务必知晓 Skype for Business 和 Teams 也会在 Exchange Online 中存储数据。因此，评估涵盖了 Skype for Business 和频道的消息，以及 Teams 的聊天消息。

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a>使用保留锁定是推荐配置的关键

高度监管行业通常需要存储电子通信来满足 WORM（一次写入，多次读取）要求。WORM 要求规定了一个存储解决方案，其中的记录必须：

- 在规定的保留期内保留，不能缩短，只能增加。
- 不可变，即在要求的保留期间，不能覆盖、删除或更改记录。

在 Exchange Online 中，当将[保留策略](retention-policies.md)应用于用户邮箱时，用户的所有内容都将根据策略标准进行保留。实际上，如果用户试图删除或修改电子邮件，更改前的电子邮件副本将保留在用户邮箱中的安全、隐藏位置。保留策略可确保组织保留电子通信，但可以修改这些策略。

通过对保留策略实施保留锁定，组织可确保策略不会遭到修改。实际上，在将保留锁定应用于保留策略后，以下操作将受到限制：

- 策略的保留期限只能增加，不能缩短。
- 可以将用户添加到策略，但不能删除用户。
- 管理员无法删除保留策略。

保留锁定可有助于满足 SEC 17a-4 法规要求。

## <a name="how-to-set-up-preservation-lock"></a>如何设置保留锁定

可以使用 PowerShell 锁定保留策略。有关详细信息，请参阅[锁定保留策略](retention-policies.md#locking-a-retention-policy)。

## <a name="known-limitations"></a>已知限制

我们注意到，Exchange Online 中存在一些限制。目前正在积极处理，并希望在 2019 年 7 月发布对以下场景的支持：

- 项目级审核在 Office 365 组邮箱中不可用。
- 线程通信不适用于 Teams 聊天和频道消息。
- 不会为 Teams 聊天和频道消息保留赞。

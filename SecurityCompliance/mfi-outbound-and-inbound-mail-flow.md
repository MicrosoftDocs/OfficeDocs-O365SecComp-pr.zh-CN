---
title: 入站和出站邮件流
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 8/7/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理员可以了解安全 & 合规性中心的邮件流仪表板中的出站和入站邮件流小组件。
ms.openlocfilehash: 89408618e7c5b3c921382b3efa0257f263509b6d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252204"
---
# <a name="outbound-and-inbound-mail-flow"></a>入站和出站邮件流

**出站和入站邮件流**小组件将**连接器报告**和以前的**TLS 概述报告**中的信息合并到一个位置。

![Security & 合规性中心的邮件流仪表板中的出站和入站邮件流报告](media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

小组件中的信息与 Office 365 中的连接器和 TLS 邮件保护有关。 有关详细信息, 请参阅以下主题:

- [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)

- [Exchange Online 如何使用 TLS 保护 Office 365 中的电子邮件连接](https://support.office.com/article/4CDE0CDA-3430-4DC0-B489-F2C0736C929F)

## <a name="message-protected-in-transit-by-tls"></a>邮件在传输过程中受到保护 (通过 TLS)

"**出站和入站邮件流**" 小组件显示当邮件传递到您的 Office 365 组织或从您的 Office 组织中传递时用于该连接的 TLS 加密。 当双方提供 tls 时, 使用其他电子邮件服务建立的连接将由 tls 进行加密。 小组件提供邮件流的最后一周的快照。 单击 "**查看详细信息**" 时,**在传输过程中保护的邮件 (通过 TLS)** 浮出控件将向您显示进入和离开组织的邮件的 TLS 保护。

![安全 & 合规中心中的传输中受保护的邮件 (通过 TLS) 浮出控件](media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

目前, tls 1.2 是 Office 365 提供的最安全的 tls 版本。 通常, 您需要知道正在用于合规性审核的 TLS 加密。 您可能没有与源和目标电子邮件服务器的直接关系 (您不拥有它们, 也没有 Microsoft), 因此, 不需要使用很多选项来改进这些服务器所使用的 TLS 加密。

不过, 您可以使用[连接器](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)来确保在电子邮件服务器和 Office 365 之间发送的邮件的最佳可用 TLS 保护。 Office 365 与您自己的电子邮件服务器或属于您的合作伙伴的服务器之间的邮件流通常比常规邮件更重要且敏感, 因此您需要对这些邮件应用额外的安全和 vigilance。 您可以升级或修复自己的电子邮件服务器, 以改进正在使用的 TLS 加密, 或与您的合作伙伴进行相同的操作。 **连接器报告**为使用 Office 365 连接器的邮件显示邮件流卷和 TLS 加密。

## <a name="connector-report"></a>连接器报告

当您从**传输 (通过 TLS)** 浮出控件中保护的邮件中单击**连接器报告**链接时, 报告将显示使用连接器在 Office 365 组织中传递和发送的邮件的相关信息。 您可以在自己的电子邮件服务器和 office 365 或合作伙伴的服务器和 office 365 之间使用连接器。 每个连接器的邮件量和连接的 TLS 加密均可用。 此外, 您还可以查看 Office 365 中发送或接收的邮件的数据, 而无需使用连接器。

"**邮件流**" 视图显示过去一周内通过连接器的邮件量。 您可以更改日期范围, 方法是选择 "**筛选器**" 可将范围增加到最多30天。 "**所有邮件流**" 视图显示通过所有连接器的 Office 365 组织发往和发来的所有邮件流。 您可以在下拉菜单中按名称选择特定的连接器。

您可以从下拉视图中选择 " **tls 使用状况**" 视图, 以查看通过连接器的邮件的 tls 保护细目。 与**tls 概述报告**报告一样, 此视图显示不同 TLS 版本的百分比。 对于 tls 1.0 连接, 确实需要将您的电子邮件服务器或合作伙伴的服务器升级或修复, 以避免在 TLS 1.0 支持最终在 Office 365 中被弃用时出现的任何问题。 有关详细信息, 请参阅[Office 365 中有关加密的技术参考详细](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221)信息。

Insights 指向连接器, 有助于吸引你关注连接器的潜在 TLS 加密问题。 见解为:**没有任何 TLS 超过 25%** 或**tls 1.0 高于 50%**。 如果你看到这些见解, 则需要调查与连接器关联的电子邮件服务器, 或与合作伙伴组织联系。

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中的其他邮件流见解的详细信息, 请参阅[Security & 合规性中心中的邮件流见解](mail-flow-insights.md)。

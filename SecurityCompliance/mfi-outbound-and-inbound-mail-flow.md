---
title: 出站和入站邮件流
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 8/7/2018
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理员可以了解有关的出站和入站的邮件流小部件中 Office 365 安全性 & 合规中心的邮件流仪表板。
ms.openlocfilehash: 57792c0347490b40f97a8b92945a9c809484ba4f
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685348"
---
# <a name="outbound-and-inbound-mail-flow"></a>出站和入站邮件流

**出站和入站的邮件流**小部件结合使用**连接器报告**和以前**TLS 概述报表**在一个位置中的信息。

![Office 365 安全性 & 合规性中心中的邮件流仪表板中出站和入站邮件流报表](media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

在小部件中的信息与连接器和 Office 365 中的 TLS 邮件保护。有关详细信息，请参阅下列主题：

- [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)

- [Exchange Online 如何使用 TLS 保护 Office 365 中的电子邮件连接](https://support.office.com/article/4CDE0CDA-3430-4DC0-B489-F2C0736C929F)

## <a name="message-protected-in-transit-by-tls"></a>邮件在传输过程中保护 （通过 TLS)

**出站和入站的邮件流**小部件将显示与您的 Office 365 组织发送邮件时用于连接 TLS 加密。与其他电子邮件服务建立的连接进行加密 tls，TLS 提供程序两侧时。小部件提供邮件流的最后一个星期的快照。时单击**查看详细信息**，**在传输过程 （通过 TLS) 中的邮件保护**弹出将显示 TLS 保护输入和离开组织的邮件。

![在 Office 365 安全性 & 合规性中心在传输过程 （通过 TLS) 弹出中受保护邮件](media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

目前，TLS 1.2 是最安全的 Office 365 提供的 TLS 版本。通常，您需要知道所使用的合规性审核 TLS 加密。您可能没有直接的关系的大部分 （您不拥有，以及 Microsoft 既不） 的源和目标电子邮件服务器，所以您不必以提高 TLS 加密由这些服务器的多个选项。

但是，您可以使用[连接器](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)来确保最佳可用 TLS 保护您的电子邮件服务器和 Office 365 之间发送的邮件。Office 365 与您自己的电子邮件服务器或属于您的合作伙伴的服务器之间的邮件流通常会更重要且敏感比普通邮件，因此您需要额外的安全和警戒应用于那些邮件。您可以升级或修复您自己的电子邮件服务器以提高正在使用，或访问您的合作伙伴进行相同的 TLS 加密。**连接器报表**显示邮件流量和使用 Office 365 连接器的邮件的 TLS 加密。

## <a name="connector-report"></a>连接器报告

当您单击**邮件保护 （通过 TLS) 的传输过程中**的弹出**连接器报告**链接时，报告将显示有关与 Office 365 组织使用连接器传递的邮件的信息。电子邮件服务器和 Office 365 或您的伙伴服务器与 Office 365 之间使用连接器。对于每个连接器消息音量和 TLS 加密连接才可用。此外，您还可以查看已发送或接收 Office 365 中不使用连接器的邮件的数据。

**邮件流**视图显示上周的邮件通过连接器量。您可以通过选择**筛选器**，您可以增加到 30 天内的最大范围更改的日期范围。**所有邮件流**视图显示所有的邮件流与 Office 365 组织通过所有连接线。您可以通过名称的下拉菜单中选择特定的连接器。

您可以从以查看的 TLS 保护的邮件通过连接器细分下拉列表选择**TLS 使用率**视图。为使用**TLS 概述报表**报表，此视图显示不同的 TLS 版本的百分比。对于 TLS 1.0 连接，您真正需要获取电子邮件服务器或您的伙伴服务器升级或固定 TLS 1.0 支持最终已过时 Office 365 中时，应避免的任何问题。有关详细信息，请参阅[Office 365 中的加密技术参考信息](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221)。

见解指向可帮助您关注连接器的潜在 TLS 加密问题的连接器。见解是：**无 TLS 是超过 25%** 或**TLS 1.0 大于 50%**。如果您看到这些见解，您需要调查的连接器，与关联或访问合作伙伴组织的电子邮件服务器。

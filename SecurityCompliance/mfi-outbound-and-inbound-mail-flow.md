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
# <a name="outbound-and-inbound-mail-flow"></a><span data-ttu-id="ca00e-103">出站和入站邮件流</span><span class="sxs-lookup"><span data-stu-id="ca00e-103">Outbound and inbound mail flow</span></span>

<span data-ttu-id="ca00e-104">**出站和入站的邮件流**小部件结合使用**连接器报告**和以前**TLS 概述报表**在一个位置中的信息。</span><span class="sxs-lookup"><span data-stu-id="ca00e-104">The **Outbound and inbound mail flow** widget combines the information from the **Connector Report** and the former **TLS Overview Report** in one place.</span></span>

![Office 365 安全性 & 合规性中心中的邮件流仪表板中出站和入站邮件流报表](media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

<span data-ttu-id="ca00e-p101">在小部件中的信息与连接器和 Office 365 中的 TLS 邮件保护。有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="ca00e-p101">The information in the widget is related to connectors and TLS message protection in Office 365. For more information, see these topics:</span></span>

- [<span data-ttu-id="ca00e-108">Configure mail flow using connectors in Office 365</span><span class="sxs-lookup"><span data-stu-id="ca00e-108">Configure mail flow using connectors in Office 365</span></span>](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)

- [<span data-ttu-id="ca00e-109">Exchange Online 如何使用 TLS 保护 Office 365 中的电子邮件连接</span><span class="sxs-lookup"><span data-stu-id="ca00e-109">How Exchange Online uses TLS to secure email connections in Office 365</span></span>](https://support.office.com/article/4CDE0CDA-3430-4DC0-B489-F2C0736C929F)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="ca00e-110">邮件在传输过程中保护 （通过 TLS)</span><span class="sxs-lookup"><span data-stu-id="ca00e-110">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="ca00e-p102">**出站和入站的邮件流**小部件将显示与您的 Office 365 组织发送邮件时用于连接 TLS 加密。与其他电子邮件服务建立的连接进行加密 tls，TLS 提供程序两侧时。小部件提供邮件流的最后一个星期的快照。时单击**查看详细信息**，**在传输过程 （通过 TLS) 中的邮件保护**弹出将显示 TLS 保护输入和离开组织的邮件。</span><span class="sxs-lookup"><span data-stu-id="ca00e-p102">The **Outbound and inbound mail flow** widget displays the TLS encryption that's used for the connection when messages are delivered to and from your Office 365 organization. The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides. The widget offers a snapshot of the last week of mail flow. When you click **View Details**, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![在 Office 365 安全性 & 合规性中心在传输过程 （通过 TLS) 弹出中受保护邮件](media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

<span data-ttu-id="ca00e-p103">目前，TLS 1.2 是最安全的 Office 365 提供的 TLS 版本。通常，您需要知道所使用的合规性审核 TLS 加密。您可能没有直接的关系的大部分 （您不拥有，以及 Microsoft 既不） 的源和目标电子邮件服务器，所以您不必以提高 TLS 加密由这些服务器的多个选项。</span><span class="sxs-lookup"><span data-stu-id="ca00e-p103">Currently, TLS 1.2 is the most secure version of TLS that's offered by Office 365. Often, you'll need to know the TLS encryption that's being used for compliance audits. You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="ca00e-p104">但是，您可以使用[连接器](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)来确保最佳可用 TLS 保护您的电子邮件服务器和 Office 365 之间发送的邮件。Office 365 与您自己的电子邮件服务器或属于您的合作伙伴的服务器之间的邮件流通常会更重要且敏感比普通邮件，因此您需要额外的安全和警戒应用于那些邮件。您可以升级或修复您自己的电子邮件服务器以提高正在使用，或访问您的合作伙伴进行相同的 TLS 加密。**连接器报表**显示邮件流量和使用 Office 365 连接器的邮件的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="ca00e-p104">But, you can use [connectors](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx) to ensure the best available TLS protection for messages that are sent between your email servers and Office 365. Mail flow between Office 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages. You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same. The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Office 365 connectors.</span></span>

## <a name="connector-report"></a><span data-ttu-id="ca00e-123">连接器报告</span><span class="sxs-lookup"><span data-stu-id="ca00e-123">Connector report</span></span>

<span data-ttu-id="ca00e-p105">当您单击**邮件保护 （通过 TLS) 的传输过程中**的弹出**连接器报告**链接时，报告将显示有关与 Office 365 组织使用连接器传递的邮件的信息。电子邮件服务器和 Office 365 或您的伙伴服务器与 Office 365 之间使用连接器。对于每个连接器消息音量和 TLS 加密连接才可用。此外，您还可以查看已发送或接收 Office 365 中不使用连接器的邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="ca00e-p105">When you click on the **Connector Report** link from the **Message protected in transit (by TLS)** flyout, the report displays information about messages that are delivered to and from your Office 365 organization using connectors. You use connectors between your own email servers and Office 365 or your partner's servers and Office 365. The message volume for each connector and the TLS encryption for the connection is available. In addition, you can also view data for messages that were sent or received in Office 365 without using a connector.</span></span>

<span data-ttu-id="ca00e-p106">**邮件流**视图显示上周的邮件通过连接器量。您可以通过选择**筛选器**，您可以增加到 30 天内的最大范围更改的日期范围。**所有邮件流**视图显示所有的邮件流与 Office 365 组织通过所有连接线。您可以通过名称的下拉菜单中选择特定的连接器。</span><span class="sxs-lookup"><span data-stu-id="ca00e-p106">The **Mail Flow** view shows the volume of messages through the connector for the past week. You can change the date range by selecting **Filter** where you can increase the range to a maximum of 30 days. The **All Mail Flow** view shows all mail flow to and from your Office 365 organization through all connectors. You can select a specific connector by name in the drop down menu.</span></span>

<span data-ttu-id="ca00e-p107">您可以从以查看的 TLS 保护的邮件通过连接器细分下拉列表选择**TLS 使用率**视图。为使用**TLS 概述报表**报表，此视图显示不同的 TLS 版本的百分比。对于 TLS 1.0 连接，您真正需要获取电子邮件服务器或您的伙伴服务器升级或固定 TLS 1.0 支持最终已过时 Office 365 中时，应避免的任何问题。有关详细信息，请参阅[Office 365 中的加密技术参考信息](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221)。</span><span class="sxs-lookup"><span data-stu-id="ca00e-p107">You can select the **TLS usage** view from the drop down to see the breakdown of TLS protection for messages through the connector. As with the **TLS Overview Report** report, this view shows the percentage of the different TLS versions. For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Office 365. For more information, see [Technical reference details about encryption in Office 365](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221).</span></span>

<span data-ttu-id="ca00e-p108">见解指向可帮助您关注连接器的潜在 TLS 加密问题的连接器。见解是：**无 TLS 是超过 25%** 或**TLS 1.0 大于 50%**。如果您看到这些见解，您需要调查的连接器，与关联或访问合作伙伴组织的电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="ca00e-p108">Insights point to connectors to help draw your attention to potential TLS encryption problems for the connector. The insights are: **No TLS is over 25%** or **TLS 1.0 is above 50%**. If you see these insights, you need to investigate your email servers that are associated with the connector, or reach out to your partner organization.</span></span>

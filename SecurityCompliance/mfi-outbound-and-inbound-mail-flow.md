---
title: 入站和出站邮件流
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理员可以了解安全 & 合规性中心的邮件流仪表板中的出站和入站邮件流小组件。
ms.openlocfilehash: 629599f6a71c1b871abb819ae4cdd339ffa5e56b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158724"
---
# <a name="outbound-and-inbound-mail-flow"></a><span data-ttu-id="bf98f-103">入站和出站邮件流</span><span class="sxs-lookup"><span data-stu-id="bf98f-103">Outbound and inbound mail flow</span></span>

<span data-ttu-id="bf98f-104">**出站和入站邮件流**小组件将**连接器报告**和以前的**TLS 概述报告**中的信息合并到一个位置。</span><span class="sxs-lookup"><span data-stu-id="bf98f-104">The **Outbound and inbound mail flow** widget combines the information from the **Connector Report** and the former **TLS Overview Report** in one place.</span></span>

![Security & 合规性中心的邮件流仪表板中的出站和入站邮件流报告](media/2c591d1c-bad6-4b72-890e-f8fdfd4f447a.png)

<span data-ttu-id="bf98f-106">小组件中的信息与 Office 365 中的连接器和 TLS 邮件保护有关。</span><span class="sxs-lookup"><span data-stu-id="bf98f-106">The information in the widget is related to connectors and TLS message protection in Office 365.</span></span> <span data-ttu-id="bf98f-107">有关详细信息, 请参阅以下主题:</span><span class="sxs-lookup"><span data-stu-id="bf98f-107">For more information, see these topics:</span></span>

- [<span data-ttu-id="bf98f-108">Configure mail flow using connectors in Office 365</span><span class="sxs-lookup"><span data-stu-id="bf98f-108">Configure mail flow using connectors in Office 365</span></span>](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)

- [<span data-ttu-id="bf98f-109">Exchange Online 如何使用 TLS 保护 Office 365 中的电子邮件连接</span><span class="sxs-lookup"><span data-stu-id="bf98f-109">How Exchange Online uses TLS to secure email connections in Office 365</span></span>](https://support.office.com/article/4CDE0CDA-3430-4DC0-B489-F2C0736C929F)

## <a name="message-protected-in-transit-by-tls"></a><span data-ttu-id="bf98f-110">邮件在传输过程中受到保护 (通过 TLS)</span><span class="sxs-lookup"><span data-stu-id="bf98f-110">Message protected in transit (by TLS)</span></span>

<span data-ttu-id="bf98f-111">"**出站和入站邮件流**" 小组件显示当邮件传递到您的 Office 365 组织或从您的 Office 组织中传递时用于该连接的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="bf98f-111">The **Outbound and inbound mail flow** widget displays the TLS encryption that's used for the connection when messages are delivered to and from your Office 365 organization.</span></span> <span data-ttu-id="bf98f-112">当双方提供 TLS 时, 使用其他电子邮件服务建立的连接将由 TLS 进行加密。</span><span class="sxs-lookup"><span data-stu-id="bf98f-112">The connections that are established with other email services are encrypted by TLS when TLS is offered by both sides.</span></span> <span data-ttu-id="bf98f-113">小组件提供邮件流的最后一周的快照。</span><span class="sxs-lookup"><span data-stu-id="bf98f-113">The widget offers a snapshot of the last week of mail flow.</span></span> <span data-ttu-id="bf98f-114">单击 "**查看详细信息**" 时,**在传输过程中保护的邮件 (通过 TLS)** 浮出控件将向您显示进入和离开组织的邮件的 TLS 保护。</span><span class="sxs-lookup"><span data-stu-id="bf98f-114">When you click **View Details**, the **Message protected in transit (by TLS)** flyout shows you the TLS protection for messages entering and leaving your organization.</span></span>

![安全 & 合规中心中的传输中受保护的邮件 (通过 TLS) 浮出控件](media/825aa74c-413d-4141-8e3c-dfe68ae78eed.png)

<span data-ttu-id="bf98f-116">目前, TLS 1.2 是 Office 365 提供的最安全的 TLS 版本。</span><span class="sxs-lookup"><span data-stu-id="bf98f-116">Currently, TLS 1.2 is the most secure version of TLS that's offered by Office 365.</span></span> <span data-ttu-id="bf98f-117">通常, 您需要知道正在用于合规性审核的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="bf98f-117">Often, you'll need to know the TLS encryption that's being used for compliance audits.</span></span> <span data-ttu-id="bf98f-118">您可能没有与源和目标电子邮件服务器的直接关系 (您不拥有它们, 也没有 Microsoft), 因此, 不需要使用很多选项来改进这些服务器所使用的 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="bf98f-118">You probably don't have a direct relationship with most of the source and destination email servers (you don't own them, and neither does Microsoft), so you don't have many options to improve the TLS encryption that's used by those servers.</span></span>

<span data-ttu-id="bf98f-119">不过, 您可以使用[连接器](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx)来确保在电子邮件服务器和 Office 365 之间发送的邮件的最佳可用 TLS 保护。</span><span class="sxs-lookup"><span data-stu-id="bf98f-119">But, you can use [connectors](https://technet.microsoft.com/library/ms.exch.eac.connectorselection.aspx) to ensure the best available TLS protection for messages that are sent between your email servers and Office 365.</span></span> <span data-ttu-id="bf98f-120">Office 365 与您自己的电子邮件服务器或属于您的合作伙伴的服务器之间的邮件流通常比常规邮件更重要且敏感, 因此您需要对这些邮件应用额外的安全和 vigilance。</span><span class="sxs-lookup"><span data-stu-id="bf98f-120">Mail flow between Office 365 and your own email servers or servers that belong to your partners is often more important and sensitive than regular messages, so you'll want to apply extra security and vigilance to those messages.</span></span> <span data-ttu-id="bf98f-121">您可以升级或修复自己的电子邮件服务器, 以改进正在使用的 TLS 加密, 或与您的合作伙伴进行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="bf98f-121">You can upgrade or fix your own email servers to improve the TLS encryption that's being used, or reach out to your partners to do the same.</span></span> <span data-ttu-id="bf98f-122">**连接器报告**为使用 Office 365 连接器的邮件显示邮件流卷和 TLS 加密。</span><span class="sxs-lookup"><span data-stu-id="bf98f-122">The **Connector Report** displays both mail flow volume and TLS encryption for messages that use your Office 365 connectors.</span></span>

## <a name="connector-report"></a><span data-ttu-id="bf98f-123">连接器报告</span><span class="sxs-lookup"><span data-stu-id="bf98f-123">Connector report</span></span>

<span data-ttu-id="bf98f-124">当您从**传输 (通过 TLS)** 浮出控件中保护的邮件中单击**连接器报告**链接时, 报告将显示使用连接器在 Office 365 组织中传递和发送的邮件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="bf98f-124">When you click on the **Connector Report** link from the **Message protected in transit (by TLS)** flyout, the report displays information about messages that are delivered to and from your Office 365 organization using connectors.</span></span> <span data-ttu-id="bf98f-125">您可以在自己的电子邮件服务器和 Office 365 或合作伙伴的服务器和 Office 365 之间使用连接器。</span><span class="sxs-lookup"><span data-stu-id="bf98f-125">You use connectors between your own email servers and Office 365 or your partner's servers and Office 365.</span></span> <span data-ttu-id="bf98f-126">每个连接器的邮件量和连接的 TLS 加密均可用。</span><span class="sxs-lookup"><span data-stu-id="bf98f-126">The message volume for each connector and the TLS encryption for the connection is available.</span></span> <span data-ttu-id="bf98f-127">此外, 您还可以查看 Office 365 中发送或接收的邮件的数据, 而无需使用连接器。</span><span class="sxs-lookup"><span data-stu-id="bf98f-127">In addition, you can also view data for messages that were sent or received in Office 365 without using a connector.</span></span>

<span data-ttu-id="bf98f-128">"**邮件流**" 视图显示过去一周内通过连接器的邮件量。</span><span class="sxs-lookup"><span data-stu-id="bf98f-128">The **Mail Flow** view shows the volume of messages through the connector for the past week.</span></span> <span data-ttu-id="bf98f-129">您可以更改日期范围, 方法是选择 "**筛选器**" 可将范围增加到最多30天。</span><span class="sxs-lookup"><span data-stu-id="bf98f-129">You can change the date range by selecting **Filter** where you can increase the range to a maximum of 30 days.</span></span> <span data-ttu-id="bf98f-130">"**所有邮件流**" 视图显示通过所有连接器的 Office 365 组织发往和发来的所有邮件流。</span><span class="sxs-lookup"><span data-stu-id="bf98f-130">The **All Mail Flow** view shows all mail flow to and from your Office 365 organization through all connectors.</span></span> <span data-ttu-id="bf98f-131">您可以在下拉菜单中按名称选择特定的连接器。</span><span class="sxs-lookup"><span data-stu-id="bf98f-131">You can select a specific connector by name in the drop down menu.</span></span>

<span data-ttu-id="bf98f-132">您可以从下拉视图中选择 " **tls 使用状况**" 视图, 以查看通过连接器的邮件的 tls 保护细目。</span><span class="sxs-lookup"><span data-stu-id="bf98f-132">You can select the **TLS usage** view from the drop down to see the breakdown of TLS protection for messages through the connector.</span></span> <span data-ttu-id="bf98f-133">与**Tls 概述报告**报告一样, 此视图显示不同 TLS 版本的百分比。</span><span class="sxs-lookup"><span data-stu-id="bf98f-133">As with the **TLS Overview Report** report, this view shows the percentage of the different TLS versions.</span></span> <span data-ttu-id="bf98f-134">对于 TLS 1.0 连接, 确实需要将您的电子邮件服务器或合作伙伴的服务器升级或修复, 以避免在 TLS 1.0 支持最终在 Office 365 中被弃用时出现的任何问题。</span><span class="sxs-lookup"><span data-stu-id="bf98f-134">For TLS 1.0 connections, you really need to get your email server or your partner's server upgraded or fixed to avoid any issues when TLS 1.0 support is eventually deprecated in Office 365.</span></span> <span data-ttu-id="bf98f-135">有关详细信息, 请参阅[Office 365 中有关加密的技术参考详细](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221)信息。</span><span class="sxs-lookup"><span data-stu-id="bf98f-135">For more information, see [Technical reference details about encryption in Office 365](https://support.office.com/article/862cbe93-4268-4ef9-ba79-277545ecf221).</span></span>

<span data-ttu-id="bf98f-136">Insights 指向连接器, 有助于吸引你关注连接器的潜在 TLS 加密问题。</span><span class="sxs-lookup"><span data-stu-id="bf98f-136">Insights point to connectors to help draw your attention to potential TLS encryption problems for the connector.</span></span> <span data-ttu-id="bf98f-137">见解为:**没有任何 TLS 超过 25%** 或**tls 1.0 高于 50%**。</span><span class="sxs-lookup"><span data-stu-id="bf98f-137">The insights are: **No TLS is over 25%** or **TLS 1.0 is above 50%**.</span></span> <span data-ttu-id="bf98f-138">如果你看到这些见解, 则需要调查与连接器关联的电子邮件服务器, 或与合作伙伴组织联系。</span><span class="sxs-lookup"><span data-stu-id="bf98f-138">If you see these insights, you need to investigate your email servers that are associated with the connector, or reach out to your partner organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf98f-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf98f-139">See also</span></span>

<span data-ttu-id="bf98f-140">有关邮件流仪表板中的其他邮件流见解的详细信息, 请参阅[Security _AMP_ 合规性中心中的邮件流见解](mail-flow-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="bf98f-140">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights.md).</span></span>

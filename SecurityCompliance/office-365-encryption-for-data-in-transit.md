---
title: Office 365 加密在传输过程中的数据
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： Microsoft 如何加密在传输过程中的数据的简要说明。
ms.openlocfilehash: 8f4781cf1127fb1b6bf742c267c76e3df39b8209
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524858"
---
# <a name="office-365-encryption-for-data-in-transit"></a><span data-ttu-id="8b5f1-103">Office 365 加密在传输过程中的数据</span><span class="sxs-lookup"><span data-stu-id="8b5f1-103">Office 365 encryption for data in transit</span></span>

<span data-ttu-id="8b5f1-104">保护客户静态数据，除了 Microsoft 使用加密技术来保护在传输过程中的 Office 365 客户数据。</span><span class="sxs-lookup"><span data-stu-id="8b5f1-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect Office 365 customer data in transit.</span></span> 

<span data-ttu-id="8b5f1-105">数据是在传输过程中：</span><span class="sxs-lookup"><span data-stu-id="8b5f1-105">Data is in transit:</span></span>
- <span data-ttu-id="8b5f1-106">当客户端计算机与 Office 365 服务器; 通信</span><span class="sxs-lookup"><span data-stu-id="8b5f1-106">when a client machine communicates with an Office 365 server;</span></span>
- <span data-ttu-id="8b5f1-107">Office 365 服务器与其他 Office 365 服务器; 的通信时和</span><span class="sxs-lookup"><span data-stu-id="8b5f1-107">when an Office 365 server communicates with another Office 365 server; and</span></span>
- <span data-ttu-id="8b5f1-108">当 Office 365 服务器与 Office 365 服务器 （例如，Exchange Online 提供电子邮件到外部电子邮件服务器） 进行通信。</span><span class="sxs-lookup"><span data-stu-id="8b5f1-108">when an Office 365 server communicates with a non-Office 365 server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="8b5f1-p101">Office 365 服务器之间的数据中心之间的通信会接管进行 TLS 或 IPsec，和面向客户的所有服务器都协商安全会话 TLS 使用客户端计算机 (例如，使用 TLS 1.2 256 位密钥长度与 Exchange Online 使用 (FIPS140-2 级别 2 验证)。（列表，请参阅[Office 365 中的加密技术参考信息](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221)的 Office 365 支持 TLS 加密套件。）这适用于使用客户端如 Outlook、 Skype for Business 和 Outlook web （例如，HTTP、 POP3 等） 上的协议。</span><span class="sxs-lookup"><span data-stu-id="8b5f1-p101">Inter-datacenter communications between Office 365 servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated). (See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="8b5f1-p102">公共证书颁发由 Microsoft IT SSL 使用 SSLAdmin，内部的 Microsoft 工具以保护机密性传输的信息。所有由 Microsoft IT 颁发的证书具有至少为 2048 位长度，并[Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf)合规性要求 SSLAdmin 以确保仅对公共 IP 地址，由 Microsoft 拥有所颁发证书。通过一个异常的过程，无法满足此条件的任何 IP 地址进行路由。</span><span class="sxs-lookup"><span data-stu-id="8b5f1-p102">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information. All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft. Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="8b5f1-p103">公共提供了所有的实现详细信息，如 TLS 正在使用的版本、 是否启用向前保密 (FS)、 等密码套件的顺序。若要查看这些详细信息的一种方法是使用第三方网站，如 Qualys SSL 实验室 (www.ssllabs.com)。下面显示用于以下服务的信息的 Qualys 从是自动的测试的页面的链接：</span><span class="sxs-lookup"><span data-stu-id="8b5f1-p103">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly. One way to see these details is to use a third-party website, such as Qualys SSL Labs (www.ssllabs.com). Below are the links to automated test pages from Qualys that display information for the following services:</span></span>
- [<span data-ttu-id="8b5f1-117">Office 365 门户</span><span class="sxs-lookup"><span data-stu-id="8b5f1-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="8b5f1-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8b5f1-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="8b5f1-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8b5f1-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="8b5f1-120">Skype for Business (SIP)</span><span class="sxs-lookup"><span data-stu-id="8b5f1-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="8b5f1-121">Skype for Business (Web)</span><span class="sxs-lookup"><span data-stu-id="8b5f1-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="8b5f1-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8b5f1-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="8b5f1-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b5f1-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="8b5f1-124">为 Exchange Online Protection，Url 因租户名称;但是，所有客户可以都测试 Office 365 使用**microsoft com.mail.protection.outlook.com**。</span><span class="sxs-lookup"><span data-stu-id="8b5f1-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Office 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>

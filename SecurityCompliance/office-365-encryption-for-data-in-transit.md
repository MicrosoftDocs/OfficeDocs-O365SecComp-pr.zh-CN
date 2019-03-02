---
title: Office 365 传输中的数据加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: '摘要: 关于 Microsoft 如何在传输中加密数据的简要说明。'
ms.openlocfilehash: ba1317a0a2a685d0f3ac2216939d04e402503e49
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357603"
---
# <a name="office-365-encryption-for-data-in-transit"></a><span data-ttu-id="842ba-103">Office 365 传输中的数据加密</span><span class="sxs-lookup"><span data-stu-id="842ba-103">Office 365 encryption for data in transit</span></span>

<span data-ttu-id="842ba-104">除了保护静态客户数据之外, Microsoft 还使用加密技术来保护传输中的 Office 365 客户数据。</span><span class="sxs-lookup"><span data-stu-id="842ba-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect Office 365 customer data in transit.</span></span> 

<span data-ttu-id="842ba-105">数据在传输中:</span><span class="sxs-lookup"><span data-stu-id="842ba-105">Data is in transit:</span></span>

- <span data-ttu-id="842ba-106">当客户端计算机与 Office 365 服务器通信时;</span><span class="sxs-lookup"><span data-stu-id="842ba-106">when a client machine communicates with an Office 365 server;</span></span>
- <span data-ttu-id="842ba-107">当 office 365 服务器与其他 office 365 服务器通信时;并</span><span class="sxs-lookup"><span data-stu-id="842ba-107">when an Office 365 server communicates with another Office 365 server; and</span></span>
- <span data-ttu-id="842ba-108">当 Office 365 服务器与非 Office 365 服务器通信时 (例如, Exchange Online 将电子邮件传递到外部电子邮件服务器)。</span><span class="sxs-lookup"><span data-stu-id="842ba-108">when an Office 365 server communicates with a non-Office 365 server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="842ba-p101">Office 365 服务器之间的数据中心之间的通信是通过 tls 或 IPsec 进行的, 并且所有面向客户的服务器都使用 tls 与客户端计算机协商安全会话 (例如, Exchange Online 使用 tls 1.2 和256位密码强度) (FIPS140-2 级别 2-已验证)。(有关 office 365 支持的 TLS 密码套件列表, 请参阅[office 365 中有关加密的技术参考详细信息](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221)。)这适用于客户端 (如 outlook、Skype for business) 和 web 上的 outlook (例如, HTTP、POP3 等) 使用的协议。</span><span class="sxs-lookup"><span data-stu-id="842ba-p101">Inter-datacenter communications between Office 365 servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated). (See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="842ba-p102">公共证书由 Microsoft IT SSL 使用 SSLAdmin (一个内部 Microsoft 工具) 颁发, 以保护传输信息的机密性。Microsoft 颁发的所有证书的长度都至少为2048位, 并且[Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf)合规性要求 SSLAdmin 确保仅将证书颁发给 Microsoft 拥有的公用 IP 地址。任何无法满足此条件的 IP 地址都将通过异常过程进行路由。</span><span class="sxs-lookup"><span data-stu-id="842ba-p102">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information. All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft. Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="842ba-p103">所有实现详细信息 (如使用的 TLS 版本、是否已启用向前保密 (FS)) 都可公开使用密码套件等的顺序。查看这些详细信息的一种方法是使用第三方网站, 如 Qualys SSL 实验室 (www.ssllabs.com)。以下是来自 Qualys 的自动测试页面的链接, 这些页面显示以下服务的信息:</span><span class="sxs-lookup"><span data-stu-id="842ba-p103">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly. One way to see these details is to use a third-party website, such as Qualys SSL Labs (www.ssllabs.com). Below are the links to automated test pages from Qualys that display information for the following services:</span></span>

- [<span data-ttu-id="842ba-117">Office 365 门户</span><span class="sxs-lookup"><span data-stu-id="842ba-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="842ba-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="842ba-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="842ba-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="842ba-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="842ba-120">Skype for business (SIP)</span><span class="sxs-lookup"><span data-stu-id="842ba-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="842ba-121">Skype for business (Web)</span><span class="sxs-lookup"><span data-stu-id="842ba-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="842ba-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="842ba-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="842ba-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="842ba-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="842ba-124">对于 Exchange Online Protection, url 会因租户名称而异;但是, 所有客户都可以使用**microsoft-com.mail.protection.outlook.com**测试 Office 365。</span><span class="sxs-lookup"><span data-stu-id="842ba-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Office 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>

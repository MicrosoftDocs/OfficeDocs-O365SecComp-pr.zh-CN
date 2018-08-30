---
title: 防御 Office 365 中的拒绝服务攻击
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
description: Overview of 拒绝服务 (DoS) 攻击。
ms.openlocfilehash: b5a51ae332b32142d9ab993a29763b2160c3ce97
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524797"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="7db28-103">防御 Office 365 中的拒绝服务攻击</span><span class="sxs-lookup"><span data-stu-id="7db28-103">Defending Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="7db28-104">简介</span><span class="sxs-lookup"><span data-stu-id="7db28-104">Introduction</span></span>
<span data-ttu-id="7db28-105">Microsoft 提供了超过 200 云服务，包括 Microsoft Azure、 Microsoft Bing、 Microsoft Office 365、 Microsoft Dynamics 365、 Microsoft OneDrive、 Skype，和 Xbox Live 我们全局云中承载的可信赖性基础结构100 多个数据中心的基础结构。</span><span class="sxs-lookup"><span data-stu-id="7db28-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services, including Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype, and Xbox Live that are hosted in our global cloud infrastructure of more than 100 datacenters.</span></span>

<span data-ttu-id="7db28-p101">重要的 Internet 展示与许多主要 Internet 属性提供云服务的全局组织，作为 Microsoft 是大型、 公共黑客和其他恶意个人的目标。网络--客户端和 Microsoft 云-之间的通信层是恶意攻击的最大的目标之一。实际上，多年，Microsoft 一直持续和永久某种形式的网络基于恐怖下。几乎任何时候，至少一个 Microsoft 的 Internet 属性遇到某种形式的攻击。如果没有可防御这些攻击的可靠且持久缓解系统，Microsoft 云服务将脱机和对客户不可用。</span><span class="sxs-lookup"><span data-stu-id="7db28-p101">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals. The network--the communication layer between clients and the Microsoft Cloud--is one of the biggest targets of malicious attacks. In fact, for many years, Microsoft has been continuously and persistently under some form of network-based cyberattack. At almost all times, at least one of Microsoft's Internet properties is experiencing some form of attack. Without reliable and persistent mitigation systems that can defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

<span data-ttu-id="7db28-111">Microsoft 使用-深度防御安全原则以保护其云服务和网络。</span><span class="sxs-lookup"><span data-stu-id="7db28-111">Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="7db28-112">定义和拒绝服务攻击症状</span><span class="sxs-lookup"><span data-stu-id="7db28-112">Definition and Symptoms of Denial-of-Service Attacks</span></span>
<span data-ttu-id="7db28-p102">攻击网络服务的一种方法是创建多个请求针对服务的主机淹没网络和服务器拒绝服务对合法用户。这称为拒绝服务 (DoS) 攻击。由多个参与者、 终结点和/或向量执行攻击时，它称为分布式拒绝服务 (DDoS) 攻击。表示、 动机和目标会有所不同，但受到 DoS 和 DDoS 攻击通常包含的工作人员以防止 Internet 站点或服务运行正常，或在所有，临时或无限期。</span><span class="sxs-lookup"><span data-stu-id="7db28-p102">One way to attack network services is to create many requests against a service's hosts to overwhelm the network and servers to deny service to legitimate users. This is referred to as a denial-of-service (DoS) attack. When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack. Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of the efforts of a person or persons to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="7db28-117">[美国计算机紧急准备小组](https://www.us-cert.gov/)(美国 CERT) 定义要包含的 DoS 攻击的症状：</span><span class="sxs-lookup"><span data-stu-id="7db28-117">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>
- <span data-ttu-id="7db28-118">异常网络性能降低 (时打开文件或访问 Internet 网站)</span><span class="sxs-lookup"><span data-stu-id="7db28-118">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="7db28-119">网站不可用</span><span class="sxs-lookup"><span data-stu-id="7db28-119">Unavailability of a Web site</span></span>
- <span data-ttu-id="7db28-120">无法访问网站</span><span class="sxs-lookup"><span data-stu-id="7db28-120">Inability to access a Web site</span></span>
- <span data-ttu-id="7db28-121">显著增加收到的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="7db28-121">Dramatic increase in received spam</span></span>
- <span data-ttu-id="7db28-122">断开连接的无线或有线的 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="7db28-122">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="7db28-123">长期无法访问网站或任何 Internet 服务</span><span class="sxs-lookup"><span data-stu-id="7db28-123">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="7db28-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="7db28-124">Related Topics</span></span>
- [<span data-ttu-id="7db28-125">防御拒绝服务攻击的核心原则</span><span class="sxs-lookup"><span data-stu-id="7db28-125">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="7db28-126">Microsoft 的拒绝服务防御战略</span><span class="sxs-lookup"><span data-stu-id="7db28-126">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="7db28-127">辩护抵御拒绝服务攻击的 Microsoft 云服务</span><span class="sxs-lookup"><span data-stu-id="7db28-127">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)

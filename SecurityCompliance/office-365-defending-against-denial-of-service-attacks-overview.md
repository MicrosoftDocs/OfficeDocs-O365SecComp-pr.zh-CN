---
title: 防御 Office 365 中的拒绝服务攻击
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 拒绝服务 (DoS) 攻击概述。
ms.openlocfilehash: a7e67fcc87867190f345c5dad14e38a473420eab
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004069"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a><span data-ttu-id="de1db-103">防御 Office 365 中的拒绝服务攻击</span><span class="sxs-lookup"><span data-stu-id="de1db-103">Defending Against Denial-of-Service Attacks in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="de1db-104">简介</span><span class="sxs-lookup"><span data-stu-id="de1db-104">Introduction</span></span>
<span data-ttu-id="de1db-105">microsoft 为超过200个云服务 (包括 microsoft Azure、microsoft Bing、microsoft Office 365、microsoft Dynamics 365、microsoft OneDrive、Skype 和 Xbox Live) 提供托管在我们的全球云中的可信赖基础结构超过100个数据中心的基础结构。</span><span class="sxs-lookup"><span data-stu-id="de1db-105">Microsoft delivers a trustworthy infrastructure for more than 200 cloud services, including Microsoft Azure, Microsoft Bing, Microsoft Office 365, Microsoft Dynamics 365, Microsoft OneDrive, Skype, and Xbox Live that are hosted in our global cloud infrastructure of more than 100 datacenters.</span></span>

<span data-ttu-id="de1db-106">作为具有大量 internet 状态以及提供云服务的显著 internet 属性的全球组织, Microsoft 是黑客和其他恶意用户的一个大型、常见的目标。</span><span class="sxs-lookup"><span data-stu-id="de1db-106">As a global organization with a significant Internet presence and many prominent Internet properties that provide cloud services, Microsoft is a large, common target for hackers and other malicious individuals.</span></span> <span data-ttu-id="de1db-107">网络--客户端与 Microsoft 云之间的通信层--是恶意攻击的最大目标之一。</span><span class="sxs-lookup"><span data-stu-id="de1db-107">The network--the communication layer between clients and the Microsoft Cloud--is one of the biggest targets of malicious attacks.</span></span> <span data-ttu-id="de1db-108">事实上, 在很多年中, Microsoft 一直在某种形式的基于网络的 cyberattack 持续和永久地进行。</span><span class="sxs-lookup"><span data-stu-id="de1db-108">In fact, for many years, Microsoft has been continuously and persistently under some form of network-based cyberattack.</span></span> <span data-ttu-id="de1db-109">大多数情况下, 至少有一个 Microsoft 的 Internet 属性遇到某种形式的攻击。</span><span class="sxs-lookup"><span data-stu-id="de1db-109">At almost all times, at least one of Microsoft's Internet properties is experiencing some form of attack.</span></span> <span data-ttu-id="de1db-110">如果没有可抵御这些攻击的可靠且持久的缓解系统, Microsoft 的云服务将处于脱机状态, 并且对客户不可用。</span><span class="sxs-lookup"><span data-stu-id="de1db-110">Without reliable and persistent mitigation systems that can defend against these attacks, Microsoft's cloud services would be offline and unavailable to customers.</span></span>

<span data-ttu-id="de1db-111">Microsoft 使用纵深防御安全原则来保护其云服务和网络。</span><span class="sxs-lookup"><span data-stu-id="de1db-111">Microsoft uses defense-in-depth security principles to protect its cloud services and networks.</span></span> 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a><span data-ttu-id="de1db-112">拒绝服务攻击的定义和症状</span><span class="sxs-lookup"><span data-stu-id="de1db-112">Definition and Symptoms of Denial-of-Service Attacks</span></span>
<span data-ttu-id="de1db-113">攻击网络服务的一种方法是创建针对服务主机的多个请求, 以使网络和服务器在网络和服务器上严重, 以拒绝向合法用户发送服务。</span><span class="sxs-lookup"><span data-stu-id="de1db-113">One way to attack network services is to create many requests against a service's hosts to overwhelm the network and servers to deny service to legitimate users.</span></span> <span data-ttu-id="de1db-114">这称为拒绝服务 (DoS) 攻击。</span><span class="sxs-lookup"><span data-stu-id="de1db-114">This is referred to as a denial-of-service (DoS) attack.</span></span> <span data-ttu-id="de1db-115">当多个参与者、终结点和/或向量执行攻击时, 它称为分布式拒绝服务 (DDoS) 攻击。</span><span class="sxs-lookup"><span data-stu-id="de1db-115">When the attack is performed by multiple actors, endpoints, and/or vectors, it is referred to as a distributed denial-of-service (DDoS) attack.</span></span> <span data-ttu-id="de1db-116">尽管 motives 和目标各不相同, 但 DoS 和 DDoS 攻击通常由人员或人员的努力阻止 Internet 站点或服务正常运行, 或者暂时或无限期地运行。</span><span class="sxs-lookup"><span data-stu-id="de1db-116">Although the means, motives, and targets vary, DoS and DDoS attacks generally consist of the efforts of a person or persons to prevent an Internet site or service from functioning correctly or at all, either temporarily or indefinitely.</span></span>

<span data-ttu-id="de1db-117">[美国计算机紧急就绪团队](https://www.us-cert.gov/)(美国-CERT) 定义 DoS 攻击的症状, 以包括:</span><span class="sxs-lookup"><span data-stu-id="de1db-117">The [United States Computer Emergency Readiness Team](https://www.us-cert.gov/) (US-CERT) defines symptoms of DoS attacks to include:</span></span>
- <span data-ttu-id="de1db-118">网络性能异常慢 (打开文件或访问 Internet 站点时)</span><span class="sxs-lookup"><span data-stu-id="de1db-118">Unusually slow network performance (when opening files or accessing Internet sites)</span></span>
- <span data-ttu-id="de1db-119">网站不可用</span><span class="sxs-lookup"><span data-stu-id="de1db-119">Unavailability of a Web site</span></span>
- <span data-ttu-id="de1db-120">无法访问网站</span><span class="sxs-lookup"><span data-stu-id="de1db-120">Inability to access a Web site</span></span>
- <span data-ttu-id="de1db-121">收到的垃圾邮件大大增加</span><span class="sxs-lookup"><span data-stu-id="de1db-121">Dramatic increase in received spam</span></span>
- <span data-ttu-id="de1db-122">断开无线连接或有线 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="de1db-122">Disconnection of a wireless or wired Internet connection</span></span>
- <span data-ttu-id="de1db-123">长期失去对 Web 或任何 Internet 服务的访问权限</span><span class="sxs-lookup"><span data-stu-id="de1db-123">Long-term loss of access to the Web or any Internet services</span></span>

## <a name="related-topics"></a><span data-ttu-id="de1db-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="de1db-124">Related Topics</span></span>
- [<span data-ttu-id="de1db-125">防御拒绝服务攻击的核心原则</span><span class="sxs-lookup"><span data-stu-id="de1db-125">Core Principles of Defense Against Denial-of-Service Attacks</span></span>](office-365-core-principles-of-defense-against-dos-attacks.md)
- [<span data-ttu-id="de1db-126">Microsoft 的拒绝服务防御策略</span><span class="sxs-lookup"><span data-stu-id="de1db-126">Microsoft's Denial-of-Service Defense Strategy</span></span>](office-365-microsoft-dos-defense-strategy.md)
- [<span data-ttu-id="de1db-127">防御拒绝服务攻击的 Microsoft 云服务</span><span class="sxs-lookup"><span data-stu-id="de1db-127">Defending Microsoft Cloud Services Against Denial-of-Service Attacks</span></span>](office-365-defending-cloud-services-against-dos-attacks.md)

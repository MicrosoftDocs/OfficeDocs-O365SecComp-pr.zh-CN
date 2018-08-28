---
title: Exchange Online Protection 概述
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: Microsoft Exchange Online Protection (EOP) 是基于云的电子邮件筛选服务，可帮助您的组织防御垃圾邮件和恶意邮件，并包括用于保护您的组织避免违反邮件策略的功能。
ms.openlocfilehash: 89852c7ba211ccb266c8b231b00d3d83987a5f20
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026689"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="1745c-103">Exchange Online Protection 概述</span><span class="sxs-lookup"><span data-stu-id="1745c-103">Exchange Online Protection overview</span></span>

<span data-ttu-id="1745c-p101">Microsoft Exchange Online Protection (EOP) 是基于云的电子邮件筛选服务，可帮助您的组织防御垃圾邮件和恶意邮件，并包括用于保护您的组织避免违反邮件策略的功能。EOP 可以简化对邮件环境的管理，缓解由于维护内部部署硬件和软件而产生的许多负担。</span><span class="sxs-lookup"><span data-stu-id="1745c-p101">Microsoft Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware, and includes features to safeguard your organization from messaging-policy violations. EOP can simplify the management of your messaging environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>
  
<span data-ttu-id="1745c-106">以下是您可以使用 EOP 进行邮件保护的主要方式：</span><span class="sxs-lookup"><span data-stu-id="1745c-106">The following are the primary ways you can use EOP for messaging protection:</span></span>
  
- <span data-ttu-id="1745c-107">**在独立方案**EOP 提供基于云的电子邮件保护为您的本地 Microsoft Exchange Server 2013 环境、 旧版 Exchange Server，或任何其他内部部署 SMTP 电子邮件解决方案。</span><span class="sxs-lookup"><span data-stu-id="1745c-107">**In a standalone scenario** EOP provides cloud-based email protection for your on-premises Microsoft Exchange Server 2013 environment, legacy Exchange Server versions, or for any other on-premises SMTP email solution.</span></span> 
    
- <span data-ttu-id="1745c-108">**作为 Microsoft Exchange Online 的一部分** 默认情况下，EOP 保护 Microsoft Exchange Online 云托管的邮箱。</span><span class="sxs-lookup"><span data-stu-id="1745c-108">**As a part of Microsoft Exchange Online** By default, EOP protects Microsoft Exchange Online cloud-hosted mailboxes.</span></span> 
    
- <span data-ttu-id="1745c-109">**在混合部署中** 当您的邮箱为内部部署和云邮箱的混合时，可以对 EOP 进行配置以保护您的邮件环境并控制邮件路由。</span><span class="sxs-lookup"><span data-stu-id="1745c-109">**In a hybrid deployment** EOP can be configured to protect your messaging environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span> 
    
## <a name="how-eop-works"></a><span data-ttu-id="1745c-110">EOP 如何工作</span><span class="sxs-lookup"><span data-stu-id="1745c-110">How EOP works</span></span>

<span data-ttu-id="1745c-111">了解 EOP 如何工作，有助于查看其如何处理传入的电子邮件：</span><span class="sxs-lookup"><span data-stu-id="1745c-111">To understand how EOP works, it helps to see how it processes incoming email:</span></span>
  
![EOP 电子邮件处理](../media/EOP-email-processing.png)
  
<span data-ttu-id="1745c-p102">传入消息最初通过连接筛选，其检查发件人信誉，并将检查邮件进行恶意软件。垃圾邮件的大部分是停止此时，删除通过 EOP。邮件将继续通过策略筛选的邮件针对自定义传输规则创建或模板中强制实施的求值的位置。例如，您可以将通知发送给经理，邮件到达来自特定发件人时的规则。（数据丢失防护检查也会发生在这里，如果您有功能; 有关功能的可用性的信息，请参阅[Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619)。）接下来，消息通过内容筛选，其中内容检查的术语或属性常见垃圾邮件。一条消息，确定内容筛选的垃圾邮件可以发送到用户的垃圾邮件文件夹或隔离，除了其他一些选项，根据您的设置。邮件成功通过所有这些保护层后，则将其传递给收件人。</span><span class="sxs-lookup"><span data-stu-id="1745c-p102">An incoming message initially passes through connection filtering, which checks the sender's reputation and inspects the message for malware. The majority of spam is stopped at this point and deleted by EOP. Messages continue through policy filtering, where messages are evaluated against custom transport rules that you create or enforce from a template. For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender. (Data loss prevention checks also occur at this point, if you have that feature; for information about feature availability, see the [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).) Next, messages pass through content filtering, where content is checked for terminology or properties common to spam. A message determined to be spam by the content filter can be sent to a user's Junk Email folder or to the quarantine, among other options, based on your settings. After a message passes all of these protection layers successfully, it's delivered to the recipient.</span></span>
  
### <a name="eop-datacenters"></a><span data-ttu-id="1745c-120">EOP 数据中心</span><span class="sxs-lookup"><span data-stu-id="1745c-120">EOP datacenters</span></span>

<span data-ttu-id="1745c-p103">EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。例如，如果某个数据中心不可用，则会将电子邮件自动路由到其他数据中心，而不会对服务有任何中断。每个数据中心的服务器代表您接受邮件，在您的组织和 Internet 之间提供一个分离层，从而减少您服务器的负载。通过此高可用性网络，Microsoft 可以确保电子邮件及时到达您的组织。</span><span class="sxs-lookup"><span data-stu-id="1745c-p103">EOP runs on a worldwide network of datacenters that are designed to provide the best availability. For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service. Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the Internet, thereby reducing load on your servers. Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span> 
  
<span data-ttu-id="1745c-p104">EOP 在数据中心之间执行负载平衡，但仅限在一个区域内。如果在一个区域中设置，将使用该区域的邮件路由处理所有邮件。下面的列表显示了 EOP 数据中心的区域邮件路由如何工作：</span><span class="sxs-lookup"><span data-stu-id="1745c-p104">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>
  
- <span data-ttu-id="1745c-p105">在美国，所有 Exchange Online 邮箱均位于美国数据中心，但南美洲除外，其中使用巴西和智利中的数据中心和加拿大使用在加拿大数据中心的位置。通过以进行 EOP 筛选; 美国数据中心路由所有电子邮件，包括南美洲和加拿大的客户的消息但是 quaratined 电子邮件存储在租户所在的数据中心正在</span><span class="sxs-lookup"><span data-stu-id="1745c-p105">In the America's, all Exchange Online mailboxes are located in U.S. datacenters, with the exception of South America where datacenters in Brazil and Chile are used and in Canada where datacenters in Canada are used. All email messages, including messages for customers in South America and Canada, are routed through U.S. datacenters for EOP filtering; however quaratined email is stored in the datacenter where the tenant is located..</span></span>
    
- <span data-ttu-id="1745c-130">在欧洲、中东和非洲 (EMEA)，所有 Exchange Online 邮箱均位于 EMEA 数据中心，所有邮件均通过 EMEA 数据中心路由以进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="1745c-130">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="1745c-p106">在亚洲太平洋地区 (APAC)，所有 Exchange Online 邮箱均位于 APAC 数据中心，但邮件当前通过 EMEA 数据中心路由以进行 EOP 筛选。计划将在 2014 年第四季度进行变更，届时邮件将通过 APAC 数据中心路由以进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="1745c-p106">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, but messages are currently routed through EMEA datacenters for EOP filtering. This is targeted to be changing in the fourth quarter of 2014, when messages will be routed through APAC datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="1745c-133">对于政府社区云 (GCC)，所有 Exchange Online 邮箱均位于美国数据中心，所有邮件均通过美国数据中心路由以进行 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="1745c-133">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>
    
## <a name="eop-plans-and-features"></a><span data-ttu-id="1745c-134">EOP 计划和功能</span><span class="sxs-lookup"><span data-stu-id="1745c-134">EOP plans and features</span></span>

<span data-ttu-id="1745c-135">以下是可用的 EOP 订阅计划：</span><span class="sxs-lookup"><span data-stu-id="1745c-135">The following are the available EOP subscription plans:</span></span>
  
- <span data-ttu-id="1745c-136">**独立 EOP** 其中，EOP 保护您的内部部署邮箱。</span><span class="sxs-lookup"><span data-stu-id="1745c-136">**EOP standalone** Where EOP protects your on-premises mailboxes.</span></span> 
    
- <span data-ttu-id="1745c-137">**Exchange Online 中的 EOP 功能** 其中，EOP 保护您的 Exchange Online 云托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="1745c-137">**EOP features in Exchange Online** Where EOP protects your Exchange Online cloud-hosted mailboxes.</span></span> 
    
- <span data-ttu-id="1745c-138">**Exchange Enterprise CAL with Services** 其中 EOP 将像独立 EOP 一样保护您的内部部署邮箱，并包含数据丢失预防 (DLP) 和使用 Web 服务报告的功能。</span><span class="sxs-lookup"><span data-stu-id="1745c-138">**Exchange Enterprise CAL with Services** Where EOP protects your on-premises mailboxes, like EOP standalone, and includes data loss prevention (DLP) and reporting using web services.</span></span> 
    
<span data-ttu-id="1745c-139">有关跨所有 EOP 订阅计划的要求、重要限制和功能可用性的信息，请参阅 [Exchange Online Protection 服务说明](https://go.microsoft.com/fwlink/p/?LinkId=320619)。</span><span class="sxs-lookup"><span data-stu-id="1745c-139">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).</span></span>
  
## <a name="setting-up-eop"></a><span data-ttu-id="1745c-140">设置 EOP</span><span class="sxs-lookup"><span data-stu-id="1745c-140">Setting up EOP</span></span>

<span data-ttu-id="1745c-p107">设置 EOP 可能很简单，尤其是在组织比较小，且拥有少数符合性规则的情况下。但是，如果组织较大，且拥有多个域、自定义符合性规则或混合邮件流，设置可能需要更多规划和时间。</span><span class="sxs-lookup"><span data-stu-id="1745c-p107">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>
  
<span data-ttu-id="1745c-143">如果您已购买 EOP，请参阅 [设置 EOP 服务](set-up-your-eop-service.md)，确保完成配置 EOP 所需的所有步骤，以保护您的邮件环境。</span><span class="sxs-lookup"><span data-stu-id="1745c-143">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="1745c-144">详细信息</span><span class="sxs-lookup"><span data-stu-id="1745c-144">For more information</span></span>

[<span data-ttu-id="1745c-145">EOP 功能</span><span class="sxs-lookup"><span data-stu-id="1745c-145">EOP features</span></span>](eop-features.md)
  
[<span data-ttu-id="1745c-146">EOP 入门视频</span><span class="sxs-lookup"><span data-stu-id="1745c-146">Videos for getting started with EOP</span></span>](videos-for-getting-started-with-eop.md)
  
[<span data-ttu-id="1745c-147">EOP 一般常见问题解答</span><span class="sxs-lookup"><span data-stu-id="1745c-147">EOP general FAQ</span></span>](eop-general-faq.md)
  
[<span data-ttu-id="1745c-148">EOP 排队、延迟以及退回邮件的常见问题</span><span class="sxs-lookup"><span data-stu-id="1745c-148">EOP queued, deferred, and bounced messages FAQ</span></span>](eop-queued-deferred-and-bounced-messages-faq.md)
  
[<span data-ttu-id="1745c-149">委派管理常见问题解答</span><span class="sxs-lookup"><span data-stu-id="1745c-149">Delegated administration FAQ</span></span>](delegated-administration-faq.md)
  
[<span data-ttu-id="1745c-150">将域和设置从一个 EOP 组织移动到另一个 EOP 组织</span><span class="sxs-lookup"><span data-stu-id="1745c-150">Move domains and settings from one EOP organization to another EOP organization</span></span>](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  

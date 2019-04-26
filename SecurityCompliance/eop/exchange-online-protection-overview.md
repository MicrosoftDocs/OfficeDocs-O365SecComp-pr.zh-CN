---
title: Exchange Online Protection 概述
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 01/31/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: Microsoft Exchange Online Protection (EOP) 是基于云的电子邮件筛选服务，可帮助您的组织防御垃圾邮件和恶意邮件，并包括用于保护您的组织避免违反邮件策略的功能。
ms.openlocfilehash: a0b736eb9773ace87f32f1272b3f4326532206d2
ms.sourcegitcommit: eca85431f4e57878a8c160b7620adf5c44ef40e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "33306576"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 概述

Microsoft Exchange Online Protection (EOP) 是基于云的电子邮件筛选服务，可帮助您的组织防御垃圾邮件和恶意邮件，并包括用于保护您的组织避免违反邮件策略的功能。EOP 可以简化对邮件环境的管理，缓解由于维护内部部署硬件和软件而产生的许多负担。
  
以下是您可以使用 EOP 进行邮件保护的主要方式：
  
- **在独立方案中**EOP 为您的本地 Microsoft Exchange server 2013 环境、旧版 Exchange server 版本或任何其他本地 SMTP 电子邮件解决方案提供基于云的电子邮件保护。 
    
- **作为 Microsoft Exchange Online 的一部分** 默认情况下，EOP 保护 Microsoft Exchange Online 云托管的邮箱。 有关配置这些 Exchange Online 功能的帮助, 请参阅防止[威胁](../protect-against-threats.md)。 
    
- **在混合部署中** 如果您既有本地邮箱，也有云邮箱，则可以将 EOP 配置为保护您的邮件环境并控制邮件路由。 

这些 Exchange Online Protection 文章适用于混合和本地环境。 
    
## <a name="how-eop-works"></a>EOP 如何工作

了解 EOP 如何工作，有助于查看其如何处理传入的电子邮件：
  
![EOP-处理电子邮件](../media/EOP-email-processing.png)
  
传入邮件最初通过连接筛选, 它会检查发件人的信誉并检查邮件中是否存在恶意软件。 大多数垃圾邮件在这时就会被 EOP 阻止并删除。 邮件将继续通过策略筛选, 其中将根据您从模板创建或实施的自定义邮件流规则 (也称为传输规则) 对邮件进行评估。 例如，你可以将规则设置为当收到来自特定发件人的邮件时向管理器发送通知。 (此时也会发生数据丢失防护检查, 如果你具有该功能, 则为; 有关功能可用性的信息, 请参阅[Exchange Online Protection 服务说明](https://go.microsoft.com/fwlink/p/?LinkId=320619)。)接下来, 邮件通过内容筛选, 在其中对内容进行检查, 了解公共的垃圾邮件的术语或属性。 通过内容筛选器确定为垃圾邮件的邮件可以发送到用户的 "垃圾邮件" 文件夹或 "隔离", 具体取决于您的设置。 在邮件成功传递所有这些保护层后, 会将其传递给收件人。
  
### <a name="eop-datacenters"></a>EOP 数据中心

EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。例如，如果某个数据中心不可用，则会将电子邮件自动路由到其他数据中心，而不会对服务有任何中断。每个数据中心的服务器代表您接受邮件，在您的组织和 Internet 之间提供一个分离层，从而减少您服务器的负载。通过此高可用性网络，Microsoft 可以确保电子邮件及时到达您的组织。 
  
EOP 在数据中心之间执行负载平衡，但仅限在一个区域内。如果在一个区域中设置，将使用该区域的邮件路由处理所有邮件。下面的列表显示了 EOP 数据中心的区域邮件路由如何工作：
  
    
- 在欧洲、中东和非洲 (EMEA)，所有 Exchange Online 邮箱均位于 EMEA 数据中心，所有邮件均通过 EMEA 数据中心路由以进行 EOP 筛选。
    
- 在亚太地区 (APAC) 中, 所有 Exchange Online 邮箱均位于 APAC 数据中心, 但邮件当前通过 APAC 数据中心路由以进行 EOP 筛选。

- 在美洲, 所有 Exchange Online 邮箱均位于美国数据中心, 但使用巴西和智利中的数据中心和加拿大中使用数据中心 (在加拿大的位置) 的情况除外。 所有电子邮件 (包括在南美洲和加拿大的客户的邮件) 通过本地数据中心进行路由, 以进行 EOP 筛选;quaratined 电子邮件存储在租户所在的数据中心中。
    
- 在欧洲、中东和非洲 (EMEA)，所有 Exchange Online 邮箱均位于 EMEA 数据中心，所有邮件均通过 EMEA 数据中心路由以进行 EOP 筛选。
    
- 在亚太地区 (APAC) 中, 所有 Exchange Online 邮箱均位于 APAC 数据中心中, 并且邮件当前通过 APAC 数据中心路由以进行 EOP 筛选。
    
- 对于政府社区云 (GCC)，所有 Exchange Online 邮箱均位于美国数据中心，所有邮件均通过美国数据中心路由以进行 EOP 筛选。
    
## <a name="eop-plans-and-features"></a>EOP 计划和功能

以下是可用的 EOP 订阅计划：
  
- **独立 EOP** 其中，EOP 保护您的内部部署邮箱。 
    
- **Exchange Online 中的 EOP 功能** 其中，EOP 保护您的 Exchange Online 云托管邮箱。 
    
- **Exchange Enterprise CAL with Services** 其中 EOP 将像独立 EOP 一样保护您的内部部署邮箱，并包含数据丢失预防 (DLP) 和使用 Web 服务报告的功能。 
    
有关跨所有 EOP 订阅计划的要求、重要限制和功能可用性的信息，请参阅 [Exchange Online Protection 服务说明](https://go.microsoft.com/fwlink/p/?LinkId=320619)。
  
## <a name="setting-up-eop"></a>设置 EOP

设置 EOP 可能很简单，尤其是在组织比较小，且拥有少数符合性规则的情况下。但是，如果组织较大，且拥有多个域、自定义符合性规则或混合邮件流，设置可能需要更多规划和时间。
  
如果您已购买 EOP，请参阅 [设置 EOP 服务](set-up-your-eop-service.md)，确保完成配置 EOP 所需的所有步骤，以保护您的邮件环境。 
  
## <a name="for-more-information"></a>详细信息

[EOP 功能](eop-features.md)
  
[EOP 一般常见问题解答](eop-general-faq.md)
  
[EOP 排队、延迟以及退回邮件的常见问题](eop-queued-deferred-and-bounced-messages-faq.md)
  
[委派管理常见问题解答](delegated-administration-faq.md)
  
[将域和设置从一个 EOP 组织移动到另一个 EOP 组织](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  


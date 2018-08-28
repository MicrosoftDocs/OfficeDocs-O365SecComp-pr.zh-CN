---
title: Exchange Online Protection IP 地址
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: eb14f38b-7b55-4a47-84a0-4a56a59e4111
description: 以下 Microsoft 数据中心 IP 地址用于通过 Microsoft Exchange Online Protection (EOP) 发送电子邮件、 时接收电子邮件，或 Exchange Online Protection 门户和管理服务。发送和接收来自 EOP 的邮件或使用管理服务，请确保您的网络以允许从这些 IP 地址连接。
ms.openlocfilehash: 853b64410969fcc2f3c9ef238d2e9f4a4bb36e7b
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23230004"
---
# <a name="exchange-online-protection-ip-addresses"></a>Exchange Online Protection IP 地址

以下 Microsoft 数据中心 IP 地址用于通过 Microsoft Exchange Online Protection (EOP) 发送电子邮件、 时接收电子邮件，或 Exchange Online Protection 门户和管理服务。发送和接收来自 EOP 的邮件或使用管理服务，请确保您的网络以允许从这些 IP 地址连接。
 
> [!NOTE]
> Microsoft 正在开发基于 REST 的 web 服务的 IP 地址和此页上的 FQDN 条目。此新服务将帮助您配置和更新网络外围设备，如防火墙和代理服务器。您可以下载的终结点、 列表或特定更改的当前版本的列表。XML 文档、 RSS 源，和 IP 地址和 FQDN 条目，此页上的，则最终将替换此服务。若要试用此新的服务，请转到[Web 服务](https://support.office.com/article/managing-office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#webservice)。 
 
## <a name="eop-ip-address-ranges"></a>EOP IP 地址范围

||||
|:-----|:-----|:-----|
|**IPv4 地址范围** <br/> |**IPv6 地址范围** <br/> |
| 23.103.132.0/22 | 2a01:111:f400:7 c 00:: / 54 |
| 23.103.136.0/21 | 2a01:111:f400:fc00:: / 54 |
| 23.103.144.0/20 | 2a01:111:f403:: / 48 |
| 23.103.198.0/23 |  |
| 23.103.200.0/22 |  |
| 40.92.0.0/14 |  |
| 40.107.0.0/17 |  |
| 52.100.0.0/14 |  |
| 52.238.78.88/32 |  |
| 65.55.88.0/24 |  |
| 65.55.169.0/24 |  |
| 94.245.120.64/26 |  |
| 104.47.0.0/17 |  |
| 157.55.234.0/24 |  |
| 157.56.110.0/23 |  |
| 157.56.112.0/24 |  |
| 207.46.100.0/24 |  |
| 207.46.163.0/24 |  |
| 213.199.154.0/24 |  |
| 213.199.180.128/26 |  |
| 216.32.180.0/23 |  |
||||
 
> [!IMPORTANT]
> 此处提供的 IP 地址范围仅用于通过客户连接器的中继。到的 IP 地址列表的更改很少，和提前传送。若要确保到您的业务合作伙伴、 智能主机或在本地环境路由通过该服务的已发布的 IP 地址范围发送的邮件，您必须配置路由到每个目标的正确连接器。有关连接器的详细信息，请参阅[决定其连接器用于](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)。 本主题中的 IP 地址可随时间变化。记录的所有 IP 地址已添加，更改或弃用在过去一年中，请参阅[更改 EOP IP 地址的通知](change-notification-for-eop-ip-addresses.md)。 
 
有关 Microsoft Office 365 使用的 IP 地址的信息，请参阅 [Office 365 URL 和 IP 地址范围](https://go.microsoft.com/fwlink/p/?LinkId=324165)。
 
## <a name="ip-ranges-by-region"></a>按区域划分的 IP 范围

Exchange Online Protection 路由邮件，同时保持遵守我们合同义务为我们的客户最有效的方式。这一点，下面 EOP 终结点是当前列表的区域 IPv4 范围;但是，这些 IP 地址可能会重新设置未到另一个函数以支持容量和效率的 EOP 内通知。在邮件将这些事件仍然流基于我们合同义务以及我们将操作我们最佳后进行了更改及时更新此列表的终结点。目前我们不 Office 365 的其他部分维护区域的终结点的列表。
 
||||
|:-----|:-----|:-----|
|**美洲** <br/> |**欧洲、中东和非洲** <br/> |**亚太地区** <br/> |
| 23.103.132.0/22 | 23.103.132.0/22 |23.103.136.0/21 |
| 23.103.136.0/21 | 23.103.144.0/22 |23.103.152.0/22 |
| 23.103.148.0/22 | 40.92.0.0/18 |40.92.128.0/17 |
| 23.103.152.0/21 | 40.93.0.0/18 |40.93.128.0/17 |
| 23.103.156.0/22 | 40.94.0.0/18 |40.94.128.0/17 |
| 23.103.198.0/24 | 40.95.0.0/18 |40.95.128.0/17 |
| 23.103.200.0/22 | 40.107.0.0/18 |52.100.128.0/17 |
| 40.92.64.0/18 | 52.100.0.0/18 |52.101.128.0/17 |
| 40.93.64.0/18 | 52.101.0.0/18 |52.102.128.0/17 |
| 40.94.64.0/18 | 52.102.0.0/18 |52.103.128.0/17 |
| 40.95.64.0/18 | 52.103.0.0/18 |65.55.88.0/24 |
| 40.107.64.0/18 | 94.245.120.64/27 |104.47.64.0/18 |
| 52.100.64.0/18 | 104.47.0.0/19 |2a01:111:f400:7 c 00:: / 54 |
| 52.101.64.0/18 | 157.55.234.0/24 |  |
| 52.102.64.0/18 | 157.56.112.0/24 | |
| 52.103.64.0/18 | 213.199.154.0/24 | |
| 65.55.169.0/24 | 213.199.180.128/26 | |
| 104.47.32.0/19 | 2a01:111:f400:7e00:: / 56 | |
| 157.56.110.0/23 | 2a01:111:f400:fe00:: / 56 | |
| 207.46.100.0/24 |  | |
| 207.46.163.0/24 |  | |
| 216.32.180.0/23 |  | |
| 2a01:111:f400:7 c 00:: / 54 |  | |
||||


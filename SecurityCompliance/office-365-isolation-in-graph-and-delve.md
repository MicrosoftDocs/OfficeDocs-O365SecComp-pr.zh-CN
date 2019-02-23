---
title: office 365 租户在 office Graph 和 Delve 中的隔离
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '摘要: 对 Office Graph 中和 Delve 中的租户隔离的说明。'
ms.openlocfilehash: cb1b432dccff6c4f890ef4aeb8ea4c19989b09d5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216802"
---
# <a name="tenant-isolation-in-the-office-graph-and-delve"></a>Office Graph 和 Delve 中的租户隔离

## <a name="tenant-isolation-in-the-office-graph"></a>Office Graph 中的租户隔离
office 365 服务中的[office Graph](https://dev.office.com/officegraph)模型活动, 包括 Exchange online、SharePoint online、Yammer、Skype for business、Azure Active Directory 等, 以及外部服务 (如其他 Microsoft 服务或第三方服务) 中的活动。office 365 中使用 office Graph 组件。Office Graph 表示内容和活动的集合, 以及在整个 Office 套件中发生的关系。它使用先进的机器学习技术将用户连接到相关内容、对话和用户周围的人员。例如, sharepoint online 中的租户索引具有一个用于为 Delve 查询提供服务的 Office Graph 索引, SharePoint online 中的分析处理引擎用于存储信号并计算见解, Exchange Online 计算每个用户的将收件人缓存用作租户分析的输入。

Office Graph 包含有关企业对象的信息, 例如人员和文档, 以及这些对象之间的关系和交互。关系和交互表示为*边缘*。Office Graph 由租户分段, 因此, 边缘只能存在于同一租赁中的*节点*之间。*节点*是具有统一资源标识符 (URI)、节点类型、访问控制列表以及包含*元数据*和边缘的一组 facet 的实体。每个节点都有关联的元数据和边缘, 它们按常见知识模型中的*facet*排列。*元数据*是存储在节点上的命名属性, 可用于在 office graph 中进行搜索、筛选或分析。*facet*是节点上的元数据和边缘的逻辑集合。每个 facet 描述节点的一个方面。 

Office Graph 不会将所有数据都引入单个存储库;相反, 它存储有关位于其他位置的数据的元数据和关系。Office Graph 由多个数据存储和处理组件组成:
- 租户图形存储为高效分析提供了批量存储优化。
- 活动内容缓存可提供对主动节点和边缘的随机访问, 以推动用户体验。
- 输入路由器会将组件的内部和外部更改通知给租户图形。

每个工作负荷内的分析推断与租户范围内的计算相关的见解, 并将其推送到租户图。租户中的所有活动的租户分析原因, 以在行为模式中生成见解。例如, Exchange Online 计算每个用户的收件人缓存, 并对每个用户的邮箱的有效原因进行分析。这些每用户分析在每个人上生成一组*RecipientCache 边缘*, 这些边缘又被推入租户图。这将使尽可能多的分析处理保持尽可能接近的源数据。

## <a name="tenant-isolation-in-delve"></a>Delve 中的租户隔离
如前所述, Office Graph 能够帮助用户发现企业中的当前活动并进行协作, 并提供以实体为中心的平台, 用于跨工作负载的内容和活动的分析和超过 Office 365。Delve 是由 Office Graph 提供支持的第一种体验。Delve 是 office 365 web 体验, 它通过 office Graph 将内容从 office 365 和 Yammer Enterprise 显示为 office 365 用户。web 体验将数据显示为不同的板, 每个板都有一定的主题, 如*周围的趋势分析*或*由我修改的*。每个板都包含多个文档卡片, 这些卡片显示摘要文本和文档中的图片。智能卡使用户可以执行以下操作: 打开文档或文档的 Yammer 页面。Office 365 租户中的每个人都有一个页面, 其中显示了此人最相关的文档, 以及可以调用 Exchange Online 或 Skype for business 以与此人交互的图标。由于 Delve 基于 Office Graph API, 因此它受该 api 基于租户的隔离的约束。
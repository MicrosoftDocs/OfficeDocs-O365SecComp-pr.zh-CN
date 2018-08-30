---
title: Office 中的 office 365 租户隔离图表和深入
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
description: 摘要： 租户隔离和 Delve Office 图形中的说明。
ms.openlocfilehash: bdc0f34d558f25ec139861c9a91261a72418f18a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525242"
---
# <a name="tenant-isolation-in-the-office-graph-and-delve"></a>Office Graph 和 Delve 中的租户隔离

## <a name="tenant-isolation-in-the-office-graph"></a>Office 图形中的租户隔离
在 Office 365 服务，业务、 Azure Active Directory 和详细信息，包括 Exchange Online、 SharePoint Online、 Yammer、 Skype 和外部服务，例如其他 Microsoft 服务或第三方服务中， [Office 图](https://dev.office.com/officegraph)模型的活动。在 Office 365 整个中使用 office 图组件。Office 图形表示内容和活动，它们发生跨整个 Office 套件之间的关系的集合。它使用复杂学习技术的计算机连接到相关的内容、 对话和人员在其周围的人员。例如，SharePoint Online 中的租户索引具有 Office 图形索引用于提供 Delve 查询服务、 分析处理引擎，以在 SharePoint Online 中用于存储信号和计算见解，和 Exchange Online 计算每个用户作为输入到租户分析的收件人缓存。

Office 图表包含有关企业对象，如人员和文档，以及关系以及这些对象之间的交互的信息。关系和交互都表示为*边缘*。Office 图形分段租户以便只能在同一租户中的*节点*之间存在边缘。*节点*是统一资源标识符 (URI)、 节点类型、 访问控制列表和包含*元数据*和边缘方面的一组具有的实体。每个节点具有关联的元数据和边缘，排列到*方面*，如常见的知识模型中所示。*元数据*被命名存储在其可用于搜索、 筛选或分析 office 图形中的节点上的属性。*方面*是元数据和节点上的边缘的逻辑集合。每个层面描述一个方面的节点。 

Office 图表不将所有数据导入单个存储库;相反，它存储元数据和有关数据的其他位置所在的关系。Office 图形由多个数据存储和处理组件组成：
- 租户图存储提供批量存储为有效的分析进行了优化。
- 活动的内容缓存提供快速随机访问主动节点和边缘到驱动器用户体验。
- 输入的路由器通知组件内部和外部到租户图表的更改。

分析中每个工作负荷推导见解相关的租户级计算，并将这些到租户关系图。通过在租赁中的所有活动租户分析原因以生成见解的行为方式。例如，Exchange Online 计算高效地原因到每个用户的邮箱的分析与每个用户的收件人缓存。这些每用户分析生成一*RecipientCache 边缘*上每个用户，其中反过来推送到租户图。这会使 as 多如接近尽可能的源数据分析处理。

## <a name="tenant-isolation-in-delve"></a>在租户隔离深入
如前所述，Office 图形电源帮助用户发现和协作他们的企业中的当前活动的体验并提供以实体为中心的平台到原因分析内容和活动跨工作负荷和超出 Office 365。深入是第一个此类由 Office 图形的体验。深入是通过 Office 图形内容来自 Office 365 和 Yammer Enterprise 显示到 Office 365 用户的 Office 365 web 体验。Web 体验每个都与一个特定主题，例如*趋势环绕在我*或*由我修改*不同板以显示数据。每个主板包含显示摘要的文本和文档中的图片的多个文档卡。卡片允许用户执行某些操作，如打开的文档的 Yammer 页。没有用于显示此人，最相关的文档的 Office 365 租户和可以与此人交互调用 Exchange Online 或 for Business 的 Skype 图标中每个人的页面。Delve 基于 Office 图形 API，因为它是绑定的 API 的基于租户隔离由。
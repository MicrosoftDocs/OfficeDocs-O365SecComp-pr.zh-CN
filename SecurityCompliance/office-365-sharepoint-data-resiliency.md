---
title: Office 365 SharePoint 数据恢复能力
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
description: Office 365 中的 SharePoint Online 中的数据恢复概述。
ms.openlocfilehash: 4fd17b50551639f6e11975acbc3822fb6ffa8bb2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214802"
---
# <a name="sharepoint-online-data-resiliency"></a>SharePoint Online 数据恢复能力
SharePoint Online 的关键原则是永远不会有任何数据块的单个副本。SharePoint Online 使用 SQL Server 复制, 这是一组用于将数据和数据库对象从一个数据库复制并分发到另一个数据库的技术, 然后在数据库之间进行同步以保持一致性。 

例如, 当用户在 SharePoint Online 中保存文件时, 该文件将被分块、加密并存储在 Azure Blob 存储中。Azure Blob 服务提供了确保在应用程序层和传输层上的数据完整性的机制。此文章将从服务和客户端角度详细说明这些机制。MD5 检查在 PUT 和 GET 操作中都是可选的;但是, 它确实提供了便利功能, 以确保使用 HTTP 时跨网络的数据完整性。此外, 由于 https 会提供传输层安全性, 因此通过 https 连接时不需要额外的 MD5 检查, 因为它将是冗余的。Azure Blob 服务提供持久存储介质, 并对存储的数据使用自己的完整性检查。在与应用程序交互时使用的 MD5's 提供用于在通过 HTTP 传输应用程序和服务之间的数据时检查数据的完整性。 

为了确保数据完整性, Azure Blob 服务在几个不同的 manners 中使用数据的 MD5 哈希。一定要了解如何计算、传输、存储和最终实施这些值, 以便正确地设计应用程序以提供数据完整性。有关详细信息, 请参阅[Windows Azure Blob MD5 概述](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx)。 

元数据和指向文件的指针存储在 SQL Server 数据库 (内容数据库) 中。所有区块–文件、文件碎片和更新增量–存储为 Azure 存储中随机分布在多个 azure 存储帐户中的 blob。SQL 数据库托管在 RAID 10 存储阵列上, 该阵列同步镜像到同一数据中心内单独的机架中的另一个 raid 10 存储阵列。然后, 使用异步日志传送将数据复制到第二个数据中心的另一个 RAID 10 存储阵列中。除了使用 RAID 10 同步和异步复制保护数据之外, 还会采用计划的数据备份, 这些备份也会异步复制到第二个数据中心。 

在 SharePoint Online 中, 数据备份每12小时执行一次, 保留14天。SharePoint Online 还使用热备用系统, 其中包括在同一客户数据位置区域 (例如, 芝加哥和 San Antonio 中已为美国预配有租户的客户) 内的成对地理位置不同的数据中心。配置为主动/主动。例如, 有个活动用户将芝加哥作为其主数据中心和 san Antonio 作为故障转移数据中心, 并且具有 san Antonio 的 live 用户作为其故障转移数据中心作为其主数据中心。 
---
title: 在 Office 365 视频中的 office 365 租户隔离
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
description: 摘要： 在 Office 365 视频租户隔离的说明。
ms.openlocfilehash: 9476047d56161ec2589fdf743d7ee837ea558865
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525668"
---
# <a name="tenant-isolation-in-office-365-video"></a>Office 365 视频中的租户隔离

> [!NOTE]
> Office 365 视频将由 Microsoft 流被替换。若要了解新的企业视频服务将智能添加到视频协作并了解有关转换计划的当前的 Office 365 视频客户的详细信息，请参阅[迁移到 Office 365 视频流](https://docs.microsoft.com/stream/)。

## <a name="introduction"></a>简介
Azure 存储用于存储数据的多个 Office 365 服务，包括 Office 365 视频和 Sway。Azure 存储包括 Blob 存储，它是用于存储非结构化的数据的高度可扩展的、 基于 REST 的云对象存储区。Azure 存储使用简单的访问控制模型;每个 Azure 订阅可以创建一个或多个存储帐户。每个存储帐户具有一个用于控制该存储帐户中的所有数据的访问的密钥。这样可以支持的典型方案，其中存储是与应用程序关联，这些应用程序具有完全控制其关联的数据;例如，在 Azure 存储 Sway 存储的内容。所有 Sway 客户内容都存储在共享 Azure 存储帐户。每个用户的内容是在单独的目录树中的 blob Azure 存储中。

管理访问客户环境 （例如，Azure 门户、 SMAPI 等） 的系统已由 Microsoft Azure 应用程序内隔离。此逻辑分离开来客户 access 基础结构的客户应用程序和存储层。

## <a name="tenant-isolation-in-office-365-video"></a>Office 365 视频中的租户隔离
[Office 365 视频](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)是提供用于发布、 共享和发现视频内容的高度安全的、 组织范围内的目标组织的企业门户。在 Office 365 视频中，每个租户的视频将保留隔离和加密在所有位置，并将只能具有访问权以及对组织的视频的权限的已验证用户。Office 365 视频使用技术的组合来实现这一点：
- SharePoint Online 用于存储的视频文件和元数据 （视频标题、 说明等）。它还提供了安全性和遵从性层 （包括身份验证），并搜索功能。
- Azure Media Services 提供转码、 自适应流式处理、 安全传递 （使用 AES 加密），和缩略图的功能。

[Azure 媒体服务](https://azure.microsoft.com/services/media-services/)是一平台-作为-a-为服务启用在云中的端到端媒体工作流。平台提供有关上载、 编码、 （带有 PlayReady)，加密和媒体世界各地的 Azure 数据中心通过传递 REST API。

所有 Office 365 视频上载都发生通过 HTTPS。视频文件在上载时，该记录存储在 SharePoint Online 和文件的副本通过加密通道发送到 Azure 媒体服务。Azure Media Services 必要转换为优化查看体验 （例如，移动、 低带宽高带宽、 等） 的多种格式的视频。这些文件，以及上载期间，获得的原始文件存储在 Azure Blob 存储中。文件使用 AES 128 每进行播放，MPEG 常见加密打包算法 （或更早的 PlayReady 版本） 进行加密和使用之前 Azure Blob 存储中存储的 AES 256 存储加密加密。（使用 Azure 媒体服务客户端 SDK，客户可以控制使用哪些加密。例如，客户可以应用于 Azure Media Services 存储加密 (AES 256) 高价值媒体资产之前将其上载 Azure Blob 存储。）

Azure 媒体服务还会生成它传输以及通过加密通道 to SharePoint Online 的缩略图元数据的视频缩略图。

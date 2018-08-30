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
# <a name="tenant-isolation-in-office-365-video"></a><span data-ttu-id="e6ee5-103">Office 365 视频中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="e6ee5-103">Tenant Isolation in Office 365 Video</span></span>

> [!NOTE]
> <span data-ttu-id="e6ee5-p101">Office 365 视频将由 Microsoft 流被替换。若要了解新的企业视频服务将智能添加到视频协作并了解有关转换计划的当前的 Office 365 视频客户的详细信息，请参阅[迁移到 Office 365 视频流](https://docs.microsoft.com/stream/)。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-p101">Office 365 Video will be replaced by Microsoft Stream. To learn more about the new enterprise video service that adds intelligence to video collaboration and learn about the transition plans for current Office 365 Video customers, see [Migrate to Stream from Office 365 Video](https://docs.microsoft.com/stream/).</span></span>

## <a name="introduction"></a><span data-ttu-id="e6ee5-106">简介</span><span class="sxs-lookup"><span data-stu-id="e6ee5-106">Introduction</span></span>
<span data-ttu-id="e6ee5-p102">Azure 存储用于存储数据的多个 Office 365 服务，包括 Office 365 视频和 Sway。Azure 存储包括 Blob 存储，它是用于存储非结构化的数据的高度可扩展的、 基于 REST 的云对象存储区。Azure 存储使用简单的访问控制模型;每个 Azure 订阅可以创建一个或多个存储帐户。每个存储帐户具有一个用于控制该存储帐户中的所有数据的访问的密钥。这样可以支持的典型方案，其中存储是与应用程序关联，这些应用程序具有完全控制其关联的数据;例如，在 Azure 存储 Sway 存储的内容。所有 Sway 客户内容都存储在共享 Azure 存储帐户。每个用户的内容是在单独的目录树中的 blob Azure 存储中。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-p102">Azure Storage is used to store data for multiple Office 365 services, including Office 365 Video and Sway. Azure Storage includes Blob storage, which is a highly-scalable, REST-based, cloud object store that is used for storing unstructured data. Azure Storage uses a simple access control model; each Azure subscription can create one or more Storage Accounts. Each Storage Account has a single secret key that is used to control access to all data in that Storage Account. This supports the typical scenario where storage is associated with applications and those applications have full control over their associated data; for example, Sway storing content in Azure Storage. All customer content for Sway is stored in shared Azure storage accounts. Each user's content is in a separate directory tree of blobs in Azure storage.</span></span>

<span data-ttu-id="e6ee5-p103">管理访问客户环境 （例如，Azure 门户、 SMAPI 等） 的系统已由 Microsoft Azure 应用程序内隔离。此逻辑分离开来客户 access 基础结构的客户应用程序和存储层。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-p103">The systems managing access to customer environments (e.g., the Azure Portal, SMAPI, etc.) are isolated within an Azure application operated by Microsoft. This logically separates the customer access infrastructure from the customer applications and storage layer.</span></span>

## <a name="tenant-isolation-in-office-365-video"></a><span data-ttu-id="e6ee5-116">Office 365 视频中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="e6ee5-116">Tenant Isolation in Office 365 Video</span></span>
<span data-ttu-id="e6ee5-p104">[Office 365 视频](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)是提供用于发布、 共享和发现视频内容的高度安全的、 组织范围内的目标组织的企业门户。在 Office 365 视频中，每个租户的视频将保留隔离和加密在所有位置，并将只能具有访问权以及对组织的视频的权限的已验证用户。Office 365 视频使用技术的组合来实现这一点：</span><span class="sxs-lookup"><span data-stu-id="e6ee5-p104">[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) is an enterprise portal that provides organizations with a highly secure, organization-wide destination for posting, sharing, and discovering video content. In Office 365 Video, each tenant's videos are kept isolated and encrypted in all locations, and are only available to authenticated users that have access and permissions to the organization's videos. Office 365 Video uses a combination of technologies to accomplish this:</span></span>
- <span data-ttu-id="e6ee5-p105">SharePoint Online 用于存储的视频文件和元数据 （视频标题、 说明等）。它还提供了安全性和遵从性层 （包括身份验证），并搜索功能。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-p105">SharePoint Online is used for storing the video file and metadata (video title, description, etc.). It also provides the security and compliance layer (including authentication), and search features.</span></span>
- <span data-ttu-id="e6ee5-122">Azure Media Services 提供转码、 自适应流式处理、 安全传递 （使用 AES 加密），和缩略图的功能。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-122">Azure Media Services provides transcoding, adaptive streaming, secure delivery (using AES encryption), and thumbnail features.</span></span>

<span data-ttu-id="e6ee5-p106">[Azure 媒体服务](https://azure.microsoft.com/services/media-services/)是一平台-作为-a-为服务启用在云中的端到端媒体工作流。平台提供有关上载、 编码、 （带有 PlayReady)，加密和媒体世界各地的 Azure 数据中心通过传递 REST API。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-p106">[Azure Media Services](https://azure.microsoft.com/services/media-services/) is a platform-as-a-service offering for enabling end-to-end media workflows in the cloud. The platform provides a REST API for uploading, encoding, encrypting (with PlayReady), and delivery of media through Azure datacenters around the world.</span></span>

<span data-ttu-id="e6ee5-p107">所有 Office 365 视频上载都发生通过 HTTPS。视频文件在上载时，该记录存储在 SharePoint Online 和文件的副本通过加密通道发送到 Azure 媒体服务。Azure Media Services 必要转换为优化查看体验 （例如，移动、 低带宽高带宽、 等） 的多种格式的视频。这些文件，以及上载期间，获得的原始文件存储在 Azure Blob 存储中。文件使用 AES 128 每进行播放，MPEG 常见加密打包算法 （或更早的 PlayReady 版本） 进行加密和使用之前 Azure Blob 存储中存储的 AES 256 存储加密加密。（使用 Azure 媒体服务客户端 SDK，客户可以控制使用哪些加密。例如，客户可以应用于 Azure Media Services 存储加密 (AES 256) 高价值媒体资产之前将其上载 Azure Blob 存储。）</span><span class="sxs-lookup"><span data-stu-id="e6ee5-p107">All uploads for Office 365 Video occur via HTTPS. When a video file is uploaded, it is stored in SharePoint Online, and a copy of the file is sent via an encrypted channel to Azure Media Services. Azure Media Services transcodes the video into multiple formats that are optimized for viewing experience (e.g., mobile, low-bandwidth, high-bandwidth, etc.). These files, along with the original file acquired during upload, are stored in Azure Blob storage. The files are encrypted using AES 128 per the MPEG Common Encryption packaging algorithm (or an earlier PlayReady version) for playback, and encrypted using AES 256 storage encryption before being stored in Azure Blob storage. (Using the Azure Media Services Client SDK, customers can control which encryption is used. For example, a customer could apply Azure Media Services storage encryption (AES 256) to a high-value media asset before uploading it Azure Blob storage.)</span></span>

<span data-ttu-id="e6ee5-132">Azure 媒体服务还会生成它传输以及通过加密通道 to SharePoint Online 的缩略图元数据的视频缩略图。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-132">Azure Media Services also generates a thumbnail for the video, which it transmits along with thumbnail metadata to SharePoint Online via an encrypted channel.</span></span>

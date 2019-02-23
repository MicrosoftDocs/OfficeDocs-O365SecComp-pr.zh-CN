---
title: OneDrive for Business 和 SharePoint Online 中的数据加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
description: 了解 OneDrive for Business 和 SharePoint Online 中数据安全加密的基本元素。
ms.openlocfilehash: a43db3da6e4663aee4437689ff51276972298872
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223211"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a><span data-ttu-id="34984-103">OneDrive for Business 和 SharePoint Online 中的数据加密</span><span class="sxs-lookup"><span data-stu-id="34984-103">Data Encryption in OneDrive for Business and SharePoint Online</span></span>

<span data-ttu-id="34984-104">了解 OneDrive for Business 和 SharePoint Online 中数据安全加密的基本元素。</span><span class="sxs-lookup"><span data-stu-id="34984-104">Understand the basic elements of encryption for data security in OneDrive for Business and SharePoint Online.</span></span>
  
## <a name="overview"></a><span data-ttu-id="34984-105">概述</span><span class="sxs-lookup"><span data-stu-id="34984-105">Overview</span></span>

<span data-ttu-id="34984-p101">Office 365 是高度安全的环境，提供多个层的广泛保护：物理数据中心安全、网络安全、访问安全、应用程序安全和数据安全。本文特别侧重于 OneDrive for Business 和 SharePoint Online 数据安全的中转和静态加密端。</span><span class="sxs-lookup"><span data-stu-id="34984-p101">Office 365 is a highly secure environment that offers extensive protection in multiple layers: physical data center security, network security, access security, application security, and data security. This article specifically focuses on the in-transit and at-rest encryption side of data security for OneDrive for Business and SharePoint Online.</span></span>
  
<span data-ttu-id="34984-108">有关 office 365 安全整体的说明, 请参阅[office 365 白皮书中的安全性](https://go.microsoft.com/fwlink/p/?LinkId=270895)。</span><span class="sxs-lookup"><span data-stu-id="34984-108">For a description of Office 365 security as a whole, see [Security in Office 365 White Paper](https://go.microsoft.com/fwlink/p/?LinkId=270895).</span></span>
  
<span data-ttu-id="34984-109">观看以下视频，了解数据加密的工作方式。</span><span class="sxs-lookup"><span data-stu-id="34984-109">Watch how data encryption works in the following video.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a><span data-ttu-id="34984-110">中转数据的加密</span><span class="sxs-lookup"><span data-stu-id="34984-110">Encryption of data in transit</span></span>

<span data-ttu-id="34984-111">在 OneDrive for Business 和 SharePoint Online 中，有两种数据进入和退出数据中心的方案。</span><span class="sxs-lookup"><span data-stu-id="34984-111">In OneDrive for Business and SharePoint Online, there are two scenarios in which data enters and exits the datacenters.</span></span>
  
- <span data-ttu-id="34984-p102">**与服务器进行的客户端通信**：在 Internet 上与 OneDrive for Business 的通信使用的是 SSL/TLS 连接。所有 SSL 连接都是使用 2048 位密钥建立而成。</span><span class="sxs-lookup"><span data-stu-id="34984-p102">**Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections. All SSL connections are established using 2048-bit keys.</span></span> 
    
- <span data-ttu-id="34984-p103">**数据中心之间的数据移动**：之所以要在数据中心之间移动数据，主要原因是为了通过异地复制来实现灾难恢复。例如，SQL Server 事务日志和 blob 存储增量沿着此管道传输。虽然已使用专用网络传输此数据，但还将进一步使用一流加密技术来保护此数据。</span><span class="sxs-lookup"><span data-stu-id="34984-p103">**Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery. For instance, SQL Server transaction logs and blob storage deltas travel along this pipe. While this data is already transmitted by using a private network, it is further protected with best-in-class encryption.</span></span> 
    
## <a name="encryption-of-data-at-rest"></a><span data-ttu-id="34984-117">静态数据的加密</span><span class="sxs-lookup"><span data-stu-id="34984-117">Encryption of data at rest</span></span>

<span data-ttu-id="34984-118">静态加密包括两个组件：BitLocker 磁盘级别加密和客户内容的每个文件加密。</span><span class="sxs-lookup"><span data-stu-id="34984-118">Encryption at rest includes two components: BitLocker disk-level encryption and per-file encryption of customer content.</span></span>
  
<span data-ttu-id="34984-p104">BitLocker 在服务中为 OneDrive for business 和 SharePoint Online 进行了部署。在 Office 365 多租户和 SharePoint Online 中, 每个文件加密也是基于多租户技术构建的 OneDrive for business 和 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="34984-p104">BitLocker is deployed for OneDrive for Business and SharePoint Online across the service. Per-file encryption is also in OneDrive for Business and SharePoint Online in Office 365 multi-tenant and new dedicated environments that are built on multi-tenant technology.</span></span>
  
<span data-ttu-id="34984-p105">虽然 BitLocker 加密磁盘上的所有数据，每个文件加密还是会通过包含唯一加密密钥来进一步加密每个文件。此外，对每个文件的每次更新都使用其自己的加密密钥进行加密。在存储之前，加密内容的密钥存储在与内容不同的单独物理位置中。此加密的每一个步骤都使用带有 256 位密钥的高级加密标准 (AES)，并且符合美国联邦信息处理标准 (FIPS) 140-2。加密的内容分布在整个数据中心的多个容器中，每个容器都有唯一的凭据。这些凭据存储在与内容和内容密钥存储位置不同的单独物理位置中。</span><span class="sxs-lookup"><span data-stu-id="34984-p105">While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file. Further, every update to every file is encrypted using its own encryption key. Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content. Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant. The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials. These credentials are stored in a separate physical location from either the content or the content keys.</span></span>
  
<span data-ttu-id="34984-127">有关 fips 140-2 合规性的详细信息, 请参阅[FIPS 140-2 合规性](https://go.microsoft.com/fwlink/?LinkId=517625)。</span><span class="sxs-lookup"><span data-stu-id="34984-127">For additional information about FIPS 140-2 compliance, see [FIPS 140-2 Compliance](https://go.microsoft.com/fwlink/?LinkId=517625).</span></span>
  
<span data-ttu-id="34984-p106">静态文件级加密利用 blob 存储来提供实际的无限存储增长并实现前所未有的保护。OneDrive for business 和 SharePoint Onlinewill 中的所有客户内容都将迁移到 blob 存储。下面介绍了如何保护数据:</span><span class="sxs-lookup"><span data-stu-id="34984-p106">File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection. All customer content in OneDrive for Business and SharePoint Onlinewill be migrated to blob storage. Here's how that data is secured:</span></span>
  
1. <span data-ttu-id="34984-p107">所有内容都可能使用多个密钥进行加密，并分布在整个数据中心中。根据每个要存储的文件大小，将其分成一个或多个区块。然后，使用每个区块自己的唯一密钥对其进行加密。类似地处理更新：将用户提交的更改或增量集分成多个区块，并使用其自己的密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="34984-p107">All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span></span>
    
2. <span data-ttu-id="34984-p108">在我们的 blob 存储中，所有这些区块（文件、文件片段和更新增量）都存储为 blob。它们还会随机分布在多个 blob 容器中。</span><span class="sxs-lookup"><span data-stu-id="34984-p108">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.</span></span>
    
3. <span data-ttu-id="34984-137">用于从文件的组件重组此文件的"映射"存储在内容数据库中。</span><span class="sxs-lookup"><span data-stu-id="34984-137">The "map" used to re-assemble the file from its components is stored in the Content Database.</span></span>
    
4. <span data-ttu-id="34984-p109">每个 blob 容器根据访问类型（读取、写入、枚举和删除）的不同，具有其自己的唯一凭据。每组凭据都存放在安全的密钥存储中，并定期刷新。</span><span class="sxs-lookup"><span data-stu-id="34984-p109">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.</span></span>
    
<span data-ttu-id="34984-140">换言之，静态的每个文件加密涉及三种不同存储类型，每种类型都有不同的功能：</span><span class="sxs-lookup"><span data-stu-id="34984-140">In other words, there are three different types of stores involved in per-file encryption at rest, each with a distinct function:</span></span>
  
- <span data-ttu-id="34984-p110">在 blob 存储中，将内容存储为加密的 blob。每个内容区块的密钥都进行加密，并单独存储在内容数据库中。内容本身不包含如何对其进行解密的任何线索。</span><span class="sxs-lookup"><span data-stu-id="34984-p110">Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.</span></span>
    
- <span data-ttu-id="34984-p111">"内容数据库"是一个 SQL Server 数据库。它存放所需的映射，以便找到并重组保留在 blob 存储中的所有内容 blob，以及解密这些 blob 所需的密钥。</span><span class="sxs-lookup"><span data-stu-id="34984-p111">The Content Database is a SQL Server database. It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.</span></span>
    
<span data-ttu-id="34984-p112">这三个存储组件（blob 存储、内容数据库和密钥存储）在物理上相互独立。保留在其中任一个组件中的信息在其自身上都不可用。这提供了前所未有的安全级别。不访问所有这三个组件就不可能实现以下操作：检索这些区块的密钥，解密这些密钥来使它们可用，将这些密钥与其相应的区块关联，解密任何区块或通过其构成区块重新构建文档。</span><span class="sxs-lookup"><span data-stu-id="34984-p112">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span></span>
  


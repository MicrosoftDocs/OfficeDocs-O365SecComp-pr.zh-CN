---
title: OneDrive for Business 和 SharePoint Online 中的数据加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
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
ms.openlocfilehash: c8ac6f0a4364117c475637e0288d7a1a790d57c2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151094"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>OneDrive for Business 和 SharePoint Online 中的数据加密

了解 OneDrive for Business 和 SharePoint Online 中数据安全加密的基本元素。
  
## <a name="overview"></a>概述

Office 365 是高度安全的环境，提供多个层的广泛保护：物理数据中心安全、网络安全、访问安全、应用程序安全和数据安全。本文特别侧重于 OneDrive for Business 和 SharePoint Online 数据安全的中转和静态加密端。
  
有关 Office 365 安全整体的说明, 请参阅[office 365 白皮书中的安全性](https://go.microsoft.com/fwlink/p/?LinkId=270895)。
  
观看以下视频，了解数据加密的工作方式。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>中转数据的加密

在 OneDrive for Business 和 SharePoint Online 中，有两种数据进入和退出数据中心的方案。
  
- **与服务器进行的客户端通信**：在 Internet 上与 OneDrive for Business 的通信使用的是 SSL/TLS 连接。所有 SSL 连接都是使用 2048 位密钥建立而成。

- **数据中心之间的数据移动**：之所以要在数据中心之间移动数据，主要原因是为了通过异地复制来实现灾难恢复。例如，SQL Server 事务日志和 blob 存储增量沿着此管道传输。虽然已使用专用网络传输此数据，但还将进一步使用一流加密技术来保护此数据。 

## <a name="encryption-of-data-at-rest"></a>静态数据的加密

静态加密包括两个组件：BitLocker 磁盘级别加密和客户内容的每个文件加密。
  
已为 OneDrive for Business 和 SharePoint Online 跨服务部署 BitLocker。 在 Office 365 多租户和 SharePoint Online 中, 每个文件加密也是基于多租户技术构建的 OneDrive for Business 和 SharePoint Online。
  
虽然 BitLocker 加密磁盘上的所有数据，每个文件加密还是会通过包含唯一加密密钥来进一步加密每个文件。此外，对每个文件的每次更新都使用其自己的加密密钥进行加密。在存储之前，加密内容的密钥存储在与内容不同的单独物理位置中。此加密的每一个步骤都使用带有 256 位密钥的高级加密标准 (AES)，并且符合美国联邦信息处理标准 (FIPS) 140-2。加密的内容分布在整个数据中心的多个容器中，每个容器都有唯一的凭据。这些凭据存储在与内容和内容密钥存储位置不同的单独物理位置中。
  
有关 FIPS 140-2 合规性的详细信息, 请参阅[FIPS 140-2 合规性](https://go.microsoft.com/fwlink/?LinkId=517625)。
  
静态文件级加密利用 blob 存储提供几乎不受限制的存储增长，并启用前所未有的保护。OneDrive for Business 和 SharePoint Online 中的所有客户内容都将被迁移到 blob 存储。下面介绍了保护此数据的方法：
  
1. 所有内容都可能使用多个密钥进行加密，并分布在整个数据中心中。根据每个要存储的文件大小，将其分成一个或多个区块。然后，使用每个区块自己的唯一密钥对其进行加密。类似地处理更新：将用户提交的更改或增量集分成多个区块，并使用其自己的密钥进行加密。

2. 在我们的 blob 存储中，所有这些区块（文件、文件片段和更新增量）都存储为 blob。它们还会随机分布在多个 blob 容器中。

3. 用于从文件的组件重组此文件的"映射"存储在内容数据库中。

4. 每个 blob 容器根据访问类型（读取、写入、枚举和删除）的不同，具有其自己的唯一凭据。每组凭据都存放在安全的密钥存储中，并定期刷新。

换言之，静态的每个文件加密涉及三种不同存储类型，每种类型都有不同的功能：
  
- 在 blob 存储中，将内容存储为加密的 blob。每个内容区块的密钥都进行加密，并单独存储在内容数据库中。内容本身不包含如何对其进行解密的任何线索。

- "内容数据库"是一个 SQL Server 数据库。它存放所需的映射，以便找到并重组保留在 blob 存储中的所有内容 blob，以及解密这些 blob 所需的密钥。

这三个存储组件（blob 存储、内容数据库和密钥存储）在物理上相互独立。保留在其中任一个组件中的信息在其自身上都不可用。这提供了前所未有的安全级别。不访问所有这三个组件就不可能实现以下操作：检索这些区块的密钥，解密这些密钥来使它们可用，将这些密钥与其相应的区块关联，解密任何区块或通过其构成区块重新构建文档。
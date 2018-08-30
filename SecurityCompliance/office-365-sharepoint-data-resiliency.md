---
title: Office 365 SharePoint 数据恢复能力
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
description: Overview of Office 365 中 SharePoint Online 中的数据恢复能力。
ms.openlocfilehash: ba6259e8e582a4abcf0f184b162177119a57718f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525405"
---
# <a name="sharepoint-online-data-resiliency"></a><span data-ttu-id="041c1-103">SharePoint Online 数据恢复能力</span><span class="sxs-lookup"><span data-stu-id="041c1-103">SharePoint Online Data Resiliency</span></span>
<span data-ttu-id="041c1-p101">SharePoint online 的基本原则是永远不会有任何段数据的单个副本。SharePoint Online 使用 SQL Server 复制，这是一组用于复制和分发数据和数据库对象从一个数据库到另一个，然后同步数据库维护一致性之间的技术。</span><span class="sxs-lookup"><span data-stu-id="041c1-p101">A key principle for SharePoint Online is to never have a single copy of any piece of data. SharePoint Online uses SQL Server replication, which is a set of technologies for copying and distributing data and database objects from one database to another, and then synchronizing between databases to maintain consistency.</span></span> 

<span data-ttu-id="041c1-p102">例如，当用户在 SharePoint Online 中保存文件，该文件是分块、 加密，，存储在 Azure Blob 存储。Azure Blob 服务提供机制，以确保数据完整性这两个应用程序和传输层。此文章将详细介绍这些机制从服务和客户端的角度。MD5 检查是可选上传和 GET 操作;但是，它提供了可使用 HTTP 时通过网络确保数据完整性的便利工具。此外，由于 HTTPS 提供其他的传输层安全性 MD5 检查不需要时，就像冗余 https 连接。Azure Blob 服务提供一个持久存储媒体，并使用其自己的完整性检查存储的数据。通过 HTTP 的应用程序和服务之间传输的数据时检查数据的完整性提供 MD5 的应用程序的交互时使用。</span><span class="sxs-lookup"><span data-stu-id="041c1-p102">For example, when a user saves a file in SharePoint Online, the file is chunked, encrypted, and stored within Azure Blob storage. Azure Blob service provides mechanisms to ensure data integrity both at the application and transport layers. This post will detail these mechanisms from the service and client perspective. MD5 checking is optional on both PUT and GET operations; however, it does provide a convenience facility to ensure data integrity across the network when using HTTP. Additionally, since HTTPS provides transport layer security additional MD5 checking is not needed while connecting over HTTPS as it would be redundant. Azure Blob service provides a durable storage medium, and uses its own integrity checking for stored data. The MD5's that are used when interacting with an application are provided for checking the integrity of the data when transferring that data between the application and service via HTTP.</span></span> 

<span data-ttu-id="041c1-p103">以确保数据完整性 Azure Blob 服务中的几个不同的方式使用 MD5 哈希值的数据。务必要了解如何这些值是计算、 传输、 存储和最终实施适当地设计您的应用程序，利用它们提供数据完整性。有关详细信息，请参阅[Windows Azure Blob MD5 Overview](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx)。</span><span class="sxs-lookup"><span data-stu-id="041c1-p103">To ensure data integrity the Azure Blob service uses MD5 hashes of the data in a couple different manners. It is important to understand how these values are calculated, transmitted, stored, and eventually enforced to appropriately design your application to utilize them to provide data integrity. For more information, see [Windows Azure Blob MD5 Overview](http://blogs.msdn.com/b/windowsazurestorage/archive/2011/02/18/windows-azure-blob-md5-overview.aspx).</span></span> 

<span data-ttu-id="041c1-p104">元数据和指向该文件存储在 SQL Server 数据库 （内容数据库）。为 Azure 存储随机分布在多个 Azure 存储帐户的 blob 存储 – 文件、 文件和更新增量部分 – 的所有块。SQL 数据库的同步镜像到同一数据中心内单独机架中的另一个 RAID 10 存储阵列 RAID 10 存储阵列上承载。异步日志传送然后用于数据复制到第二个数据中心中的另一个 RAID 10 存储阵列。除了使用 RAID 10 和同步和异步复制的数据保护，其中还异步复制到第二个数据中心执行计划的数据备份。</span><span class="sxs-lookup"><span data-stu-id="041c1-p104">Metadata and pointers to the file are stored in a SQL Server database (the content database). All the chunks – files, pieces of files, and update deltas – are stored as blobs in Azure storage that are randomly distributed across multiple Azure storage accounts. The SQL database is hosted on a RAID 10 storage array which is synchronously mirrored to another RAID 10 storage array in a separate rack within the same datacenter. Asynchronous log shipping is then used to replicate the data to another RAID 10 storage array in a second datacenter. In addition to protecting data with RAID 10 and synchronous and asynchronous replication, scheduled data backups are taken which are also asynchronously replicated to the second datacenter.</span></span> 

<span data-ttu-id="041c1-p105">SharePoint Online 中数据备份是执行每 12 个小时，并保留 14 天。SharePoint Online 还使用包括同一客户数据位置区域 （例如，芝加哥和圣安东尼奥的已设置在美国其租户的用户） 内的配对地理上单独数据中心热待机系统配置为主动/主动。例如，有 live 用户具有其主数据中心和故障转移数据中心，作为圣安东尼奥芝加哥和实时用户为其主数据中心和芝加哥作为其故障转移数据中心具有圣安东尼奥。</span><span class="sxs-lookup"><span data-stu-id="041c1-p105">In SharePoint Online, data backups are performed every 12 hours and retained for 14 days. SharePoint Online also uses a hot standby system that includes paired geographically-separate datacenters within the same customer data location region (for example, Chicago and San Antonio for customers who have provisioned their tenant in the United States) configured as active/active. For example, there are live users that have Chicago as their primary datacenter and San Antonio as a failover datacenter, and live users that have San Antonio as their primary datacenter and Chicago as their failover datacenter.</span></span> 
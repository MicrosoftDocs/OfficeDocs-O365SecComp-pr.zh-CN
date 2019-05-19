---
title: 下载导出作业
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 56ed8eac259974b43ca0cd26b2bd0c339a5fc05b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155144"
---
# <a name="download-export-jobs"></a><span data-ttu-id="f8044-102">下载导出作业</span><span class="sxs-lookup"><span data-stu-id="f8044-102">Download export jobs</span></span>

<span data-ttu-id="f8044-103">所有导出的数据都将添加到 Microsoft Azure blob 中。</span><span class="sxs-lookup"><span data-stu-id="f8044-103">All exported data is added to a Microsoft Azure blob.</span></span> <span data-ttu-id="f8044-104">这提供了多个用于处理下游数据的选项。</span><span class="sxs-lookup"><span data-stu-id="f8044-104">This provides multiple options to handle the data downstream.</span></span> <span data-ttu-id="f8044-105">有几种访问 Azure blob 的方法。</span><span class="sxs-lookup"><span data-stu-id="f8044-105">There are several ways to access an Azure blob.</span></span> <span data-ttu-id="f8044-106">一种方法是使用 Azure 存储资源管理器。</span><span class="sxs-lookup"><span data-stu-id="f8044-106">One method is to use Azure Storage Explorer.</span></span> <span data-ttu-id="f8044-107">此方法支持简单连接, 浏览和下载。</span><span class="sxs-lookup"><span data-stu-id="f8044-107">This method supports simple connection, browsing and downloading.</span></span> <span data-ttu-id="f8044-108">有关详细信息, 请访问<https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer></span><span class="sxs-lookup"><span data-stu-id="f8044-108">For more information, visit <https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer></span></span>

1.  <span data-ttu-id="f8044-109">若要在完成导出作业后下载内容, 请转到 "导出" 选项卡, 然后选择 "导出作业"。</span><span class="sxs-lookup"><span data-stu-id="f8044-109">To download content after an export job is complete, go to the Exports tab and select an export job.</span></span>

2.  <span data-ttu-id="f8044-110">复制浮出控件的 "位置" 部分中的文本。</span><span class="sxs-lookup"><span data-stu-id="f8044-110">Copy the text in the “Locations” section of the flyout.</span></span>

![](../media/eDiscoExportJob.png)

3.  <span data-ttu-id="f8044-111">打开 Azure 存储资源管理器, 然后单击 "连接" 按钮</span><span class="sxs-lookup"><span data-stu-id="f8044-111">Open Azure Storage Explorer and click the “Connect” button</span></span>

![](../media/AzureStorageConnect.png)

4.  <span data-ttu-id="f8044-112">选择 "使用共享访问签名 URI", 然后单击 "下一步"</span><span class="sxs-lookup"><span data-stu-id="f8044-112">Select “Use a shared access signature URI” and click next</span></span>

![](../media/AzureStorageConnect2.png)

5.  <span data-ttu-id="f8044-113">将位置文本粘贴到 URI 文本框中, 然后单击 "下一步"</span><span class="sxs-lookup"><span data-stu-id="f8044-113">Paste the Location text in the URI text box and click next</span></span>

![](../media/AzureStorageConnect3.png)

6.  <span data-ttu-id="f8044-114">单击 "连接"</span><span class="sxs-lookup"><span data-stu-id="f8044-114">Click Connect</span></span>

![](../media/AzureStorageConnect4.png)

<span data-ttu-id="f8044-115">这会将导出添加为存储在存储帐户/SAS 附加的服务/Blob 容器中的对象。</span><span class="sxs-lookup"><span data-stu-id="f8044-115">This will add the export as an object in Storage Accounts/SAS-Attached Services/Blob Containers.</span></span> <span data-ttu-id="f8044-116">你将能够浏览导出和下载导出的全部或部分。</span><span class="sxs-lookup"><span data-stu-id="f8044-116">You will be able to explore the export and download all or portions of the export.</span></span>

![](../media/AzureStorageConnect5.png)
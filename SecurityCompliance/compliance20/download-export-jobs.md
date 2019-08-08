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
description: 安装和使用 Azure 存储资源管理器下载从高级电子数据展示中的审阅集导出的文档。
ms.openlocfilehash: f236f53be9dda88fe5b8448011aa651603e38182
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230981"
---
# <a name="download-export-jobs"></a><span data-ttu-id="765f9-103">下载导出作业</span><span class="sxs-lookup"><span data-stu-id="765f9-103">Download export jobs</span></span>

<span data-ttu-id="765f9-104">在高级电子数据展示案例中从审阅集导出文档时, 会将文档上载到 Microsoft 提供的 Azure 存储位置或由组织管理的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="765f9-104">When you export documents from a review set in an Advanced eDiscovery case, the documents are uploaded to a Microsoft-provided Azure Storage location or to an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="765f9-105">所使用的 Azure 存储位置的类型取决于导出文档时选择的选项。</span><span class="sxs-lookup"><span data-stu-id="765f9-105">The type of Azure Storage location used depends on which option was selected when the documents were exported.</span></span> 

<span data-ttu-id="765f9-106">本文提供了有关如何使用 Microsoft Azure 存储资源管理器连接到 Azure 存储位置以浏览和下载导出的文档的说明。</span><span class="sxs-lookup"><span data-stu-id="765f9-106">This article provides instructions for how to use the Microsoft Azure Storage Explorer to connect to an Azure Storage location to browse and download the exported documents.</span></span> <span data-ttu-id="765f9-107">有关 Azure 存储资源管理器的详细信息, 请参阅[快速入门: 使用 Azure 存储资源管理器](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。</span><span class="sxs-lookup"><span data-stu-id="765f9-107">For more information about Azure Storage Explorer, see [Quickstart: Use Azure Storage Explorer](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).</span></span>

## <a name="step-1-install-the-azure-storage-explorer"></a><span data-ttu-id="765f9-108">步骤 1: 安装 Azure 存储资源管理器</span><span class="sxs-lookup"><span data-stu-id="765f9-108">Step 1: Install the Azure Storage Explorer</span></span>

<span data-ttu-id="765f9-109">第一步是下载并安装 Azure 存储资源管理器。</span><span class="sxs-lookup"><span data-stu-id="765f9-109">The first step is to download and install the Azure Storage Explorer.</span></span> <span data-ttu-id="765f9-110">有关说明, 请参阅[Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="765f9-110">For instructions, see [Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span> <span data-ttu-id="765f9-111">您可以使用此工具在步骤3中连接到并下载导出的文档。</span><span class="sxs-lookup"><span data-stu-id="765f9-111">You use this tool to connect to and download the exported documents in Step 3.</span></span>

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a><span data-ttu-id="765f9-112">步骤 2: 从导出作业中获取 SAS URL</span><span class="sxs-lookup"><span data-stu-id="765f9-112">Step 2: Obtain the SAS URL from the export job</span></span>

<span data-ttu-id="765f9-113">下一步是获取在创建导出作业以[从审阅集导出文档](export-documents-from-review-set.md)时生成的共享访问签名 (SAS) URL。</span><span class="sxs-lookup"><span data-stu-id="765f9-113">The next step is to obtain the shared access signature (SAS) URL that's generated when you created the export job to [export documents from a review set](export-documents-from-review-set.md).</span></span> <span data-ttu-id="765f9-114">您可以复制上载到 Microsoft 提供的 Azure 存储位置或由组织管理的 Azure 存储位置的文档的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="765f9-114">You can copy the SAS URL for documents that are uploaded to a Microsoft-provided Azure Storage location or an Azure Storage location managed by your organization.</span></span> <span data-ttu-id="765f9-115">无论在哪种情况下, 都可以使用 SAS URL 连接到步骤3中的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="765f9-115">In either case, you use the SAS URL to connect to the Azure Storage location in Step 3.</span></span>

1. <span data-ttu-id="765f9-116">在 "**高级电子数据展示**" 页上, 转到事例, 然后单击 "**导出**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="765f9-116">On the **Advanced eDiscovery** page, go to the case, and then click the **Exports** tab.</span></span>

2. <span data-ttu-id="765f9-117">在 "**导出**" 选项卡上, 单击要下载的导出作业。</span><span class="sxs-lookup"><span data-stu-id="765f9-117">On the **Exports** tab, click the export job that you want to download.</span></span>

3. <span data-ttu-id="765f9-118">在弹出页面上的 "**位置**" 下, 复制所显示的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="765f9-118">On the flyout page, under **Locations**, copy the SAS URL that's displayed.</span></span> <span data-ttu-id="765f9-119">如有必要, 可将其保存到文件中, 以便您可以在第3步中访问它。</span><span class="sxs-lookup"><span data-stu-id="765f9-119">If necessary, you can save it to a file so you can access it in Step 3.</span></span>
 
   ![复制在 "位置" 下显示的 SAS URL](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a><span data-ttu-id="765f9-121">步骤 3: 连接到 Azure 存储位置</span><span class="sxs-lookup"><span data-stu-id="765f9-121">Step 3: Connect to the Azure Storage location</span></span>

<span data-ttu-id="765f9-122">最后一步是使用 Azure 存储资源管理器和 SAS URL 连接到 Azure 存储位置, 并下载导出到本地计算机的文档。</span><span class="sxs-lookup"><span data-stu-id="765f9-122">The final step is to use the Azure Storage Explorer and the SAS URL to connect to the Azure Storage location and download the documents that you exported to a local computer.</span></span>

1.  <span data-ttu-id="765f9-123">打开您在步骤1中安装的 Azure 存储资源管理器。</span><span class="sxs-lookup"><span data-stu-id="765f9-123">Open the Azure Storage Explorer that you installed in Step 1.</span></span>

2. <span data-ttu-id="765f9-124">单击 "**添加帐户**" 图标。</span><span class="sxs-lookup"><span data-stu-id="765f9-124">Click the **Add account** icon.</span></span> <span data-ttu-id="765f9-125">或者, 也可以右键单击 "**存储帐户**"。</span><span class="sxs-lookup"><span data-stu-id="765f9-125">Alternatively, you can right-click **Storage Accounts**.</span></span>

   ![单击 "添加帐户" 图标](../media/AzureStorageConnect.png)

3.  <span data-ttu-id="765f9-127">在 "**连接到 Azure 存储**" 页上, 单击 "**使用共享访问签名 (SA)" URI** , 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="765f9-127">On the **Connect to Azure Storage** page, click **Use a shared access signature (SAS) URI** and then click **Next**.</span></span>

    ![单击 "使用共享访问签名 (SA)" URI, 然后单击 "下一步"](../media/AzureStorageConnect2.png)

4.  <span data-ttu-id="765f9-129">在 "**附加到 SAS uri** " 页上, 在 "URI" 框中单击, 然后粘贴您在步骤2中获取的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="765f9-129">On the **Attach with SAS URI** page, click in the URI box, and then paste the SAS URL that you obtained in Step 2.</span></span> 

    ![将 SAS URL 粘贴到 URI 框中](../media/AzureStorageConnect3.png)

    <span data-ttu-id="765f9-131">请注意, SAS URL 的一部分显示在 "**显示名称**" 框中。</span><span class="sxs-lookup"><span data-stu-id="765f9-131">Notice that a portion of the SAS URL is displayed in the **Display name** box.</span></span> <span data-ttu-id="765f9-132">这将在连接到存储位置后用作**存储帐户**下创建的容器的显示名称。</span><span class="sxs-lookup"><span data-stu-id="765f9-132">This will be used as the display name of the container that's created under the **Storage accounts** after you connect to the storage location.</span></span> <span data-ttu-id="765f9-133">此名称由高级电子数据展示事例的 ID 和唯一标识符组成。</span><span class="sxs-lookup"><span data-stu-id="765f9-133">This name consists of the ID of the Advanced eDiscovery case is from and a unique identifier.</span></span> <span data-ttu-id="765f9-134">您可以保留默认的显示名称, 也可以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="765f9-134">You can keep the default display name or change it.</span></span> <span data-ttu-id="765f9-135">如果您更改它, 则显示名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="765f9-135">If you change it, the display name must be unique.</span></span>

5.  <span data-ttu-id="765f9-136">单击“下一步”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="765f9-136">Click **Next**.</span></span>

    <span data-ttu-id="765f9-137">将显示 "**连接摘要**" 页。</span><span class="sxs-lookup"><span data-stu-id="765f9-137">The **Connection summary** page is displayed.</span></span>
   
    ![单击 "连接摘要" 页面上的 "连接" 以连接到 Azure 存储位置](../media/AzureStorageConnect4.png)

6. <span data-ttu-id="765f9-139">在 "**连接摘要**" 页上, 查看连接信息, 然后单击 "**连接**"。</span><span class="sxs-lookup"><span data-stu-id="765f9-139">On the **Connection summary** page, review the connection information, and then click **Connect**.</span></span> 

    <span data-ttu-id="765f9-140">" **Blob 容器**" 节点 (在 "**存储帐户** > **(附加容器)** \> " 下打开)。</span><span class="sxs-lookup"><span data-stu-id="765f9-140">The **Blob containers** node (under **Storage Accounts** > **(Attached Containers)** \> is opened.</span></span> 

    ![](../media/AzureStorageConnect5.png)

    <span data-ttu-id="765f9-141">它包含使用步骤4中的显示名称命名的容器。</span><span class="sxs-lookup"><span data-stu-id="765f9-141">It contains a container named with the display name from step 4.</span></span> <span data-ttu-id="765f9-142">此容器包含您创建的每个导出作业的文件夹。</span><span class="sxs-lookup"><span data-stu-id="765f9-142">This container contains a folder for each export job that you've created.</span></span> <span data-ttu-id="765f9-143">这些文件夹使用与导出作业的 ID 对应的 ID 进行命名。</span><span class="sxs-lookup"><span data-stu-id="765f9-143">These folders are named with an ID that corresponds to the ID of the export job.</span></span> <span data-ttu-id="765f9-144">您可以在弹出页面上的 "**支持信息**" 下找到这些导出 id (和导出的名称), 在 "**作业**" 选项卡上列出的每个**为导出作业准备数据的每个准备数据**。</span><span class="sxs-lookup"><span data-stu-id="765f9-144">You can find these export IDs (and the name of the export) under **Support information** on the flyout page for each **Preparing data for export** job listed on the **Jobs** tab.</span></span>

7. <span data-ttu-id="765f9-145">双击 "导出作业" 文件夹将其打开。</span><span class="sxs-lookup"><span data-stu-id="765f9-145">Double-click the export job folder to open it.</span></span>

   <span data-ttu-id="765f9-146">将显示文件夹列表和导出报告。</span><span class="sxs-lookup"><span data-stu-id="765f9-146">A list of folders and export reports is displayed.</span></span>
   
    ![导出文件夹包含导出的文件并导出报告](../media/AzureStorageConnect6.png)

   <span data-ttu-id="765f9-148">"导出作业" 文件夹包含以下项目。</span><span class="sxs-lookup"><span data-stu-id="765f9-148">The export job folder contains the following items.</span></span> <span data-ttu-id="765f9-149">导出文件夹中的实际项目由创建导出作业时配置的导出选项决定。</span><span class="sxs-lookup"><span data-stu-id="765f9-149">The actual items in the export folder are determined by the export options configured when the export job was created.</span></span> <span data-ttu-id="765f9-150">有关详细信息, 请参阅[从审阅集导出文档](export-documents-from-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="765f9-150">For more information, see [Export documents from a review set](export-documents-from-review-set.md).</span></span>

    - <span data-ttu-id="765f9-151">Export_load_file: 此 CSV 文件是包含有关每个导出文档的信息的详细导出报告。</span><span class="sxs-lookup"><span data-stu-id="765f9-151">Export_load_file.csv: This CSV file is a detail export report that contains information about each exported document.</span></span> <span data-ttu-id="765f9-152">该文件由一个用于文档的每个元数据属性的列组成。</span><span class="sxs-lookup"><span data-stu-id="765f9-152">The file consists of a column for each metadata property for a document.</span></span> <span data-ttu-id="765f9-153">有关此报告中包含的元数据的列表和说明, 请参阅[高级电子数据展示中的文档元数据字段](document-metadata-fields.md)的表中的 "**导出的字段名称**" 列。</span><span class="sxs-lookup"><span data-stu-id="765f9-153">For a list and description of the metadata that's included in this report, see the **Exported field name** column in the table in [Document metadata fields in Advanced eDiscovery](document-metadata-fields.md).</span></span>
    
    - <span data-ttu-id="765f9-154">摘要: 包含导出摘要 (包括导出统计信息) 的文本文件。</span><span class="sxs-lookup"><span data-stu-id="765f9-154">Summary.txt: A text file that contains a summary of the export including export statistics.</span></span>
    
    - <span data-ttu-id="765f9-155">Extracted_text_files: 此文件夹包含每个导出文档的文本文件版本。</span><span class="sxs-lookup"><span data-stu-id="765f9-155">Extracted_text_files: This folder contains a text file version of each exported document.</span></span>
     
    - <span data-ttu-id="765f9-156">NativeFiles: 此文件夹包含每个导出文档的本机文件版本。</span><span class="sxs-lookup"><span data-stu-id="765f9-156">NativeFiles: This folder contains a native file version of each exported document.</span></span>
    
    - <span data-ttu-id="765f9-157">Error_files: 当导出作业包含任何错误文件时, 此文件夹包含以下项:</span><span class="sxs-lookup"><span data-stu-id="765f9-157">Error_files: This folder includes the following items when the export job contains any error files:</span></span> 
        
      - <span data-ttu-id="765f9-158">ExtractionError: 此 CSV 文件包含未从其父项正确提取的文件的可用元数据。</span><span class="sxs-lookup"><span data-stu-id="765f9-158">ExtractionError.csv: This CSV file contains the available metadata for files that weren't properly extracted from their parent item.</span></span>
        
      - <span data-ttu-id="765f9-159">ProcessingError: 此文件夹包含有处理错误的文档。</span><span class="sxs-lookup"><span data-stu-id="765f9-159">ProcessingError: This folder contains documents with processing errors.</span></span> <span data-ttu-id="765f9-160">此内容位于项目级别, 这意味着如果附件有处理错误, 则包含附件的文档也将包含在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="765f9-160">This content is at an item level, which means if an attachment had a processing error, the document that contains the attachment will also be included in this folder.</span></span>
 
8. <span data-ttu-id="765f9-161">若要导出导出中的所有内容, 请选择 "导出" 文件夹, 然后单击 "**下载**"。</span><span class="sxs-lookup"><span data-stu-id="765f9-161">To export all contents in the export, select the export folder, and then click **Download**.</span></span>

9. <span data-ttu-id="765f9-162">指定要在其中下载导出文件的位置, 然后单击 "选择文件夹"。</span><span class="sxs-lookup"><span data-stu-id="765f9-162">Specify the location where you want to download the exported files, and then click Select folder.</span></span>

    <span data-ttu-id="765f9-163">Azure 存储资源管理器将启动导出过程。</span><span class="sxs-lookup"><span data-stu-id="765f9-163">The Azure Storage Explorer starts the export process.</span></span> <span data-ttu-id="765f9-164">下载导出项目的状态将显示在 "**活动**" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="765f9-164">The status of the downloading the exported items is displayed in the **Activities** pane.</span></span> <span data-ttu-id="765f9-165">下载完成后, 会显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="765f9-165">A message is displayed when the download is finished.</span></span>

    ![下载完成时显示一条消息](../media/AzureStorageConnect8.png)

> [!NOTE]
> <span data-ttu-id="765f9-167">您可以选择要下载的特定项目, 而不是下载整个导出作业。</span><span class="sxs-lookup"><span data-stu-id="765f9-167">Instead of downloading the entire export job, you can select specific items to download.</span></span> <span data-ttu-id="765f9-168">您可以双击项目进行查看, 而无需下载项目。</span><span class="sxs-lookup"><span data-stu-id="765f9-168">And instead of downloading items, you can double-click an item to view it.</span></span>
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
# <a name="download-export-jobs"></a>下载导出作业

在高级电子数据展示案例中从审阅集导出文档时, 会将文档上载到 Microsoft 提供的 Azure 存储位置或由组织管理的 Azure 存储位置。 所使用的 Azure 存储位置的类型取决于导出文档时选择的选项。 

本文提供了有关如何使用 Microsoft Azure 存储资源管理器连接到 Azure 存储位置以浏览和下载导出的文档的说明。 有关 Azure 存储资源管理器的详细信息, 请参阅[快速入门: 使用 Azure 存储资源管理器](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)。

## <a name="step-1-install-the-azure-storage-explorer"></a>步骤 1: 安装 Azure 存储资源管理器

第一步是下载并安装 Azure 存储资源管理器。 有关说明, 请参阅[Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。 您可以使用此工具在步骤3中连接到并下载导出的文档。

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>步骤 2: 从导出作业中获取 SAS URL

下一步是获取在创建导出作业以[从审阅集导出文档](export-documents-from-review-set.md)时生成的共享访问签名 (SAS) URL。 您可以复制上载到 Microsoft 提供的 Azure 存储位置或由组织管理的 Azure 存储位置的文档的 SAS URL。 无论在哪种情况下, 都可以使用 SAS URL 连接到步骤3中的 Azure 存储位置。

1. 在 "**高级电子数据展示**" 页上, 转到事例, 然后单击 "**导出**" 选项卡。

2. 在 "**导出**" 选项卡上, 单击要下载的导出作业。

3. 在弹出页面上的 "**位置**" 下, 复制所显示的 SAS URL。 如有必要, 可将其保存到文件中, 以便您可以在第3步中访问它。
 
   ![复制在 "位置" 下显示的 SAS URL](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a>步骤 3: 连接到 Azure 存储位置

最后一步是使用 Azure 存储资源管理器和 SAS URL 连接到 Azure 存储位置, 并下载导出到本地计算机的文档。

1.  打开您在步骤1中安装的 Azure 存储资源管理器。

2. 单击 "**添加帐户**" 图标。 或者, 也可以右键单击 "**存储帐户**"。

   ![单击 "添加帐户" 图标](../media/AzureStorageConnect.png)

3.  在 "**连接到 Azure 存储**" 页上, 单击 "**使用共享访问签名 (SA)" URI** , 然后单击 "**下一步**"。

    ![单击 "使用共享访问签名 (SA)" URI, 然后单击 "下一步"](../media/AzureStorageConnect2.png)

4.  在 "**附加到 SAS uri** " 页上, 在 "URI" 框中单击, 然后粘贴您在步骤2中获取的 SAS URL。 

    ![将 SAS URL 粘贴到 URI 框中](../media/AzureStorageConnect3.png)

    请注意, SAS URL 的一部分显示在 "**显示名称**" 框中。 这将在连接到存储位置后用作**存储帐户**下创建的容器的显示名称。 此名称由高级电子数据展示事例的 ID 和唯一标识符组成。 您可以保留默认的显示名称, 也可以对其进行更改。 如果您更改它, 则显示名称必须是唯一的。

5.  单击“下一步”。****

    将显示 "**连接摘要**" 页。
   
    ![单击 "连接摘要" 页面上的 "连接" 以连接到 Azure 存储位置](../media/AzureStorageConnect4.png)

6. 在 "**连接摘要**" 页上, 查看连接信息, 然后单击 "**连接**"。 

    " **Blob 容器**" 节点 (在 "**存储帐户** > **(附加容器)** \> " 下打开)。 

    ![](../media/AzureStorageConnect5.png)

    它包含使用步骤4中的显示名称命名的容器。 此容器包含您创建的每个导出作业的文件夹。 这些文件夹使用与导出作业的 ID 对应的 ID 进行命名。 您可以在弹出页面上的 "**支持信息**" 下找到这些导出 id (和导出的名称), 在 "**作业**" 选项卡上列出的每个**为导出作业准备数据的每个准备数据**。

7. 双击 "导出作业" 文件夹将其打开。

   将显示文件夹列表和导出报告。
   
    ![导出文件夹包含导出的文件并导出报告](../media/AzureStorageConnect6.png)

   "导出作业" 文件夹包含以下项目。 导出文件夹中的实际项目由创建导出作业时配置的导出选项决定。 有关详细信息, 请参阅[从审阅集导出文档](export-documents-from-review-set.md)。

    - Export_load_file: 此 CSV 文件是包含有关每个导出文档的信息的详细导出报告。 该文件由一个用于文档的每个元数据属性的列组成。 有关此报告中包含的元数据的列表和说明, 请参阅[高级电子数据展示中的文档元数据字段](document-metadata-fields.md)的表中的 "**导出的字段名称**" 列。
    
    - 摘要: 包含导出摘要 (包括导出统计信息) 的文本文件。
    
    - Extracted_text_files: 此文件夹包含每个导出文档的文本文件版本。
     
    - NativeFiles: 此文件夹包含每个导出文档的本机文件版本。
    
    - Error_files: 当导出作业包含任何错误文件时, 此文件夹包含以下项: 
        
      - ExtractionError: 此 CSV 文件包含未从其父项正确提取的文件的可用元数据。
        
      - ProcessingError: 此文件夹包含有处理错误的文档。 此内容位于项目级别, 这意味着如果附件有处理错误, 则包含附件的文档也将包含在此文件夹中。
 
8. 若要导出导出中的所有内容, 请选择 "导出" 文件夹, 然后单击 "**下载**"。

9. 指定要在其中下载导出文件的位置, 然后单击 "选择文件夹"。

    Azure 存储资源管理器将启动导出过程。 下载导出项目的状态将显示在 "**活动**" 窗格中。 下载完成后, 会显示一条消息。

    ![下载完成时显示一条消息](../media/AzureStorageConnect8.png)

> [!NOTE]
> 您可以选择要下载的特定项目, 而不是下载整个导出作业。 您可以双击项目进行查看, 而无需下载项目。
---
title: 准备 CSV 文件的 ID 列表在 Office 365 中的内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: 从现有的内容搜索的 Results.csv 或未编制索引 Items.csv 文件用于创建返回特定的电子邮件 ID 列表搜索。ID 列表搜索通常用于返回部分索引的邮箱项目。
ms.openlocfilehash: 9a7583c8f83626afb8dc0452bf72d834c8a28275
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038275"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a><span data-ttu-id="49e80-104">准备 CSV 文件的 ID 列表在 Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="49e80-104">Prepare a CSV file for an ID list Content Search in Office 365</span></span>

<span data-ttu-id="49e80-p102">您可以搜索特定邮箱的电子邮件和使用 Exchange Id 的列表的其他邮箱项目。若要创建 （正式称为目标的搜索） 的 ID 列表搜索，您可以提交标识要搜索的特定邮箱项目以逗号分隔的值 (CSV) 文件。对于此 CSV 文件可以使用**Results.csv**文件或将内容搜索结果导出或导出从内容搜索报告和现有的内容搜索时要包括的**未编制索引 Items.csv**文件。然后您编辑这些文件，以指示要搜索，然后创建一个新的 ID 列表搜索和提交 CSV 文件的特定项之一。</span><span class="sxs-lookup"><span data-stu-id="49e80-p102">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs. To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for. For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search. Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span> 
  
<span data-ttu-id="49e80-109">下面是过程的创建 ID 列表搜索的快速概述。</span><span class="sxs-lookup"><span data-stu-id="49e80-109">Here's a quick overview of the process for creating an ID list search.</span></span>
  
1. <span data-ttu-id="49e80-110">创建和运行安全中新的或指导性内容搜索&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="49e80-110">Create and run a new or guided Content Search in the Security &amp; Compliance Center.</span></span>
    
2. <span data-ttu-id="49e80-p103">将内容搜索结果导出或导出内容的搜索报告。有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="49e80-p103">Export the content search results or export the content search report. For more information, see:</span></span>
    
    - [<span data-ttu-id="49e80-113">从 Office 365 安全性导出内容的搜索结果&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="49e80-113">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
    - [<span data-ttu-id="49e80-114">导出内容搜索报告</span><span class="sxs-lookup"><span data-stu-id="49e80-114">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
3. <span data-ttu-id="49e80-p104">编辑**Results.csv**文件或**未编制索引 Items.csv**并确定要在 ID 列表搜索中包括的特定邮箱项目。请参阅准备 ID 列表搜索 CSV 文件的[说明](#prepare-the-csv-file-for-an-id-list-search)。</span><span class="sxs-lookup"><span data-stu-id="49e80-p104">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search. See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span> 
    
4. <span data-ttu-id="49e80-p105">创建新的 ID 列表搜索 （请参阅的[说明](#create-an-id-list-search)） 和提交准备 CSV 文件。创建搜索查询将仅搜索该 CSV 文件中选定的项目。</span><span class="sxs-lookup"><span data-stu-id="49e80-p105">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared. The search query that's created will only search for the items selected in the CSV file.</span></span>
    
> [!NOTE]
> <span data-ttu-id="49e80-p106">ID 列表搜索仅支持的邮箱项目。不能搜索 SharePoint 和 ID 中的 OneDrive 文档列表搜索。</span><span class="sxs-lookup"><span data-stu-id="49e80-p106">ID list searches are only supported for mailbox items. You can't search for SharePoint and OneDrive documents in an ID list search.</span></span> 
  
 <span data-ttu-id="49e80-p107">**原因创建 ID 列表搜索？** 如果您无法确定基于**Results.csv**或**未编制索引 Items.csv**文件中的元数据的电子数据展示请求做出迅速响应项目时，您可以使用 ID 列表搜索来查找，预览，，然后将导出的项来确定如果它具有与您正在调查的案例响应。ID 列表搜索通常用于搜索并返回一组特定的未编制索引的项目。</span><span class="sxs-lookup"><span data-stu-id="49e80-p107">**Why create an ID list search?** If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating. ID list searches are typically used to search for and return a specific set of unindexed items.</span></span> 
  
## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="49e80-124">准备 CSV 文件的 ID 列表搜索</span><span class="sxs-lookup"><span data-stu-id="49e80-124">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="49e80-p108">导出的搜索结果或报表的内容搜索后，您可以执行以下步骤来准备 ID 列表搜索的 CSV 文件。此 CSV 文件将识别 ID 列表搜索中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="49e80-p108">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search. This CSV file will identify every item in the ID list search.</span></span>
  
<span data-ttu-id="49e80-p109">请注意，您可以使用 CSV 文件从包含 SharePoint 网站和 OneDrive 帐户的搜索，但您可以选择*仅*ID 列表搜索的邮箱项目。如果您在 SharePoint 或 OneDrive 中选择一个文档，该 CSV 文件时创建 ID 列表搜索将失败验证。</span><span class="sxs-lookup"><span data-stu-id="49e80-p109">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search. If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span> 
  
1. <span data-ttu-id="49e80-129">在 Excel 中打开的**Results.csv**或**未编制索引 Items.csv**文件。</span><span class="sxs-lookup"><span data-stu-id="49e80-129">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span> 
    
2. <span data-ttu-id="49e80-p110">插入新列并将其命名为**选中**。并不重要插入列的位置。为方便起见，请考虑将其插入到第一列的左侧。</span><span class="sxs-lookup"><span data-stu-id="49e80-p110">Insert a new column and name it **Selected**. It doesn't matter where you insert the column. For convenience, consider inserting it to the left of the first column.</span></span>
    
3. <span data-ttu-id="49e80-p111">在**选择**列中，键入**是**中的单元格对应于您想要搜索的项。对于您要搜索的每个项重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="49e80-p111">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for. Repeat this step for every item that you want to search for.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="49e80-p112">当您在 Excel 中打开 CSV 文件时，**文档 ID**列的数据格式更改为**常规**。这将导致项目的文档 ID 显示科学记数法。例如，"481037338205"的 ID 显示为"4.81037E + 11"的文档必须执行的下一步步骤，将**文档 ID**列的数据格式更改为**号码**还原正确的格式的文档 id。如果您不执行此操作，使用 CSV 文件的 ID 列表搜索将失败。</span><span class="sxs-lookup"><span data-stu-id="49e80-p112">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**. This results in displaying the document ID for an item in scientific notation. For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID. If you don't do this, the ID list search that uses the CSV file will fail.</span></span> 
  
4. <span data-ttu-id="49e80-139">右键单击整个**文档 ID**列中，选择**单元格格式**。</span><span class="sxs-lookup"><span data-stu-id="49e80-139">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>
    
5. <span data-ttu-id="49e80-140">在**类别**框中，单击**编号**。</span><span class="sxs-lookup"><span data-stu-id="49e80-140">In the **Category** box, click **Number**.</span></span>
    
6. <span data-ttu-id="49e80-p113">为**0**，更改的小数位数，然后单击**确定**以保存所做的更改。请注意，文档 ID 列中的值更改为号码。</span><span class="sxs-lookup"><span data-stu-id="49e80-p113">Change the number of decimal places to **0**, and then click **OK** to save your changes. Notice that the values in the Document ID column are changed to numbers.</span></span> 
    
    <span data-ttu-id="49e80-143">下面是一个示例的已准备好进行 ID 列表内容搜索提交 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="49e80-143">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>
    
    ![目标内容搜索 CSV 文件的示例](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)
  
7. <span data-ttu-id="49e80-p114">保存 CSV 文件或保存使用**另存为**具有不同的文件名称的文件。在这两种情况下，确保 CSV 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="49e80-p114">Save the CSV file or use **Save As** to the save the file with different file name. In both cases, be sure to save the file with the CSV format.</span></span> 
  
## <a name="create-an-id-list-search"></a><span data-ttu-id="49e80-147">创建 ID 列表搜索</span><span class="sxs-lookup"><span data-stu-id="49e80-147">Create an ID list search</span></span>

<span data-ttu-id="49e80-148">下一步是创建一个新的 ID 列表内容搜索并提交上一步中准备的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="49e80-148">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="49e80-p115">您应创建 ID 列表搜索不超过 2 天后从内容搜索导出的结果或报表。如果搜索结果，或报表在导出 2 天之前，您应重新导出的搜索结果或报表来生成更新的 CSV 文件。然后您可以准备一个更新后的 CSV 文件，并使用它来创建 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="49e80-p115">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search. If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files. Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span> 
  
1. <span data-ttu-id="49e80-152">安全中&amp;合规性中心中，转到**搜索&amp;调查** \> **内容搜索**。</span><span class="sxs-lookup"><span data-stu-id="49e80-152">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Content search**.</span></span>
    
2. <span data-ttu-id="49e80-153">在**搜索**页上，单击箭头下一步为![添加图标](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新搜索**，然后单击**搜索按 ID 列表**。</span><span class="sxs-lookup"><span data-stu-id="49e80-153">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>
    
    ![从新搜索下拉列表中单击搜索按 ID 列表](media/e65f9942-09b2-4127-865e-e64029a590df.png)
  
3. <span data-ttu-id="49e80-155">**按 ID 列表搜索**飞出，在名称搜索 （和 （可选） 描述），然后单击**浏览**并选择上一步骤中的准备 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="49e80-155">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span> 
    
    <span data-ttu-id="49e80-p116">Office 365 尝试验证 CSV 文件。如果验证失败，将显示一条错误消息可帮助您解决验证错误。CSV 文件已成功验证创建 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="49e80-p116">Office 365 attempts to validate the CSV file. If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors. The CSV file has to be successfully validated to create an ID list search.</span></span>
    
4. <span data-ttu-id="49e80-159">后的 CSV 文件成功验证，单击**搜索**创建 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="49e80-159">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span> 
    
    <span data-ttu-id="49e80-160">下面是估计的搜索结果和生成的 ID 列表搜索查询的示例。</span><span class="sxs-lookup"><span data-stu-id="49e80-160">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>
    
    ![在细节窗格中的目标内容搜索的搜索查询](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)
  
    <span data-ttu-id="49e80-162">请注意，估计 ID 搜索统计信息中显示的项目数应匹配在 CSV 文件中所选的项目数。</span><span class="sxs-lookup"><span data-stu-id="49e80-162">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>
    
5. <span data-ttu-id="49e80-163">预览或导出 ID 列表搜索返回的项。</span><span class="sxs-lookup"><span data-stu-id="49e80-163">Preview or export the items returned by the ID list search.</span></span>
    
> [!NOTE]
> <span data-ttu-id="49e80-p117">如果您创建的 ID 列表搜索后移动邮箱，搜索查询不会返回指定的项。这是因为邮箱移动时，会更改邮箱项目的**DocumentId**属性。在极少数实例邮箱移动时创建的 ID 列表搜索后，您应创建一个新的内容搜索 （或更新现有内容搜索的搜索结果），然后导出搜索结果或报告生成更新可用的 CSV 文件 若要创建一个新的 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="49e80-p117">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items. That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved. In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span> 

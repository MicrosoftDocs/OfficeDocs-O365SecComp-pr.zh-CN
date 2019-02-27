---
title: 为 Office 365 中的 ID 列表内容搜索准备 CSV 文件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: 使用来自现有内容搜索的结果 .csv 或未编制索引的项目 .csv 文件来创建一个可返回特定电子邮件的 ID 列表搜索。ID 列表搜索通常用于返回部分索引的邮箱项目。
ms.openlocfilehash: 558a8512ed133995b2cc1d0d8b78fd7f08d11168
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296735"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a><span data-ttu-id="03eba-104">为 Office 365 中的 ID 列表内容搜索准备 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="03eba-104">Prepare a CSV file for an ID list Content Search in Office 365</span></span>

<span data-ttu-id="03eba-p102">您可以使用 Exchange id 列表搜索特定邮箱电子邮件和其他邮箱项目。若要创建 ID 列表搜索 (正式称为目标搜索), 请提交一个逗号分隔值 (CSV) 文件, 该文件标识要搜索的特定邮箱项目。对于此 CSV 文件, 您可以使用导出内容搜索结果或从现有内容搜索中导出内容搜索报告时包含的**结果 .csv**文件或未**编制索引的项目 .csv**文件。然后, 编辑其中一个文件以指示要搜索的特定项目, 然后创建一个新的 ID 列表搜索并提交 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="03eba-p102">You can search for specific mailbox email messages and other mailbox items using a list of Exchange IDs. To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for. For this CSV file you use the **Results.csv** file or the **Unindexed Items.csv** file that are included when you export the Content Search results or export a Content Search report from and existing Content Search. Then you edit one of these files to indicate the specific items to search for, and then create a new ID list search and submit the CSV file.</span></span> 
  
<span data-ttu-id="03eba-109">以下是创建 ID 列表搜索的过程的快速概述。</span><span class="sxs-lookup"><span data-stu-id="03eba-109">Here's a quick overview of the process for creating an ID list search.</span></span>
  
1. <span data-ttu-id="03eba-110">在安全&amp;合规中心中创建和运行新的或引导的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="03eba-110">Create and run a new or guided Content Search in the Security &amp; Compliance Center.</span></span>
    
2. <span data-ttu-id="03eba-p103">导出内容搜索结果或导出内容搜索报告。有关详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="03eba-p103">Export the content search results or export the content search report. For more information, see:</span></span>
    
    - [<span data-ttu-id="03eba-113">从 Office 365 安全&amp;合规中心导出内容搜索结果</span><span class="sxs-lookup"><span data-stu-id="03eba-113">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
    - [<span data-ttu-id="03eba-114">导出内容搜索报告</span><span class="sxs-lookup"><span data-stu-id="03eba-114">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
3. <span data-ttu-id="03eba-p104">编辑**结果 .csv**文件或未**编制索引的项目 .csv** , 并标识要包括在 ID 列表搜索中的特定邮箱项目。有关为 ID 列表搜索准备 CSV 文件的[说明](#prepare-the-csv-file-for-an-id-list-search), 请参阅。</span><span class="sxs-lookup"><span data-stu-id="03eba-p104">Edit the **Results.csv** file or the **Unindexed Items.csv** and identify the specific mailbox items that you want to include in the ID list search. See the [instructions](#prepare-the-csv-file-for-an-id-list-search) for preparing a CSV file for an ID list search.</span></span> 
    
4. <span data-ttu-id="03eba-p105">创建新的 ID 列表搜索 (请参阅[说明](#create-an-id-list-search)) 并提交您准备的 CSV 文件。创建的搜索查询将仅搜索 CSV 文件中选定的项目。</span><span class="sxs-lookup"><span data-stu-id="03eba-p105">Create a new ID list search (see the [instructions](#create-an-id-list-search)) and submit the CSV file that you prepared. The search query that's created will only search for the items selected in the CSV file.</span></span>
    
> [!NOTE]
> <span data-ttu-id="03eba-p106">仅邮箱项目支持 ID 列表搜索。您无法在 ID 列表搜索中搜索 SharePoint 和 OneDrive 文档。</span><span class="sxs-lookup"><span data-stu-id="03eba-p106">ID list searches are only supported for mailbox items. You can't search for SharePoint and OneDrive documents in an ID list search.</span></span> 
  
 <span data-ttu-id="03eba-p107">**为什么要创建 ID 列表搜索？** 如果您无法根据**结果 .csv**或未**编制索引的项目 .csv**文件中的元数据确定某个项目是否响应电子数据展示请求, 则可以使用 ID 列表搜索来查找、预览和导出该项目, 以确定是否对正在调查的案例做出响应。ID 列表搜索通常用于搜索和返回一组特定的未编制索引的项目。</span><span class="sxs-lookup"><span data-stu-id="03eba-p107">**Why create an ID list search?** If you're unable to determine if an item is responsive to an eDiscovery request based on the metadata in the **Results.csv** or **Unindexed Items.csv** files, you can use an ID list search to find, preview, and then export that item to determine if it's responsive to the case you're investigating. ID list searches are typically used to search for and return a specific set of unindexed items.</span></span> 
  
## <a name="prepare-the-csv-file-for-an-id-list-search"></a><span data-ttu-id="03eba-124">为 ID 列表搜索准备 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="03eba-124">Prepare the CSV file for an ID list search</span></span>

<span data-ttu-id="03eba-p108">导出内容搜索的搜索结果或报告之后, 可以执行以下步骤来准备用于 ID 列表搜索的 CSV 文件。此 CSV 文件将标识 ID 列表搜索中的每个项目。</span><span class="sxs-lookup"><span data-stu-id="03eba-p108">After you export the search results or report for a content search, you can perform the following steps to prepare the CSV file for an ID list search. This CSV file will identify every item in the ID list search.</span></span>
  
<span data-ttu-id="03eba-p109">请注意, 可以从包含 SharePoint 网站和 OneDrive 帐户的搜索中使用 CSV 文件, 但只能为 ID 列表\*\* 搜索选择邮箱项目。如果选择 SharePoint 或 OneDrive 中的文档, 则创建 ID 列表搜索时, CSV 文件验证将失败。</span><span class="sxs-lookup"><span data-stu-id="03eba-p109">Note that you can use a CSV file from a search that included SharePoint sites and OneDrive accounts, but you can select  *only*  mailbox items for an ID list search. If you select a document in SharePoint or OneDrive, the CSV file will fail validation when you create an ID list search.</span></span> 
  
1. <span data-ttu-id="03eba-129">在 Excel 中打开**结果 .csv**或未**编制索引的项目 .csv**文件。</span><span class="sxs-lookup"><span data-stu-id="03eba-129">Open the **Results.csv** or **Unindexed Items.csv** file in Excel.</span></span> 
    
2. <span data-ttu-id="03eba-p110">插入一个新列并将其命名为 "已**选择**"。插入列的位置无关紧要。为方便起见, 请考虑将其插入第一列的左侧。</span><span class="sxs-lookup"><span data-stu-id="03eba-p110">Insert a new column and name it **Selected**. It doesn't matter where you insert the column. For convenience, consider inserting it to the left of the first column.</span></span>
    
3. <span data-ttu-id="03eba-p111">在 "**所选**" 列中, 在与要搜索的项目相对应的单元格中键入 **"是"** 。对要搜索的每个项目重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="03eba-p111">In the **Selected** column, type **Yes** in the cell that corresponds to the item that you want to search for. Repeat this step for every item that you want to search for.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="03eba-p112">当您在 Excel 中打开 CSV 文件时, "**文档 ID** " 列的数据格式将更改为 "**常规**"。这将导致显示科学记数法中项的文档 ID。例如, 文档 id "481037338205" 显示为 "4.81037 e + 11"。必须执行后续步骤将**文档 id**列的数据格式更改为 "**数字**", 以还原文档 id 的正确格式。如果不执行此操作, 则使用 CSV 文件的 ID 列表搜索将失败。</span><span class="sxs-lookup"><span data-stu-id="03eba-p112">When you open the CSV file in Excel, the data format for the **Document ID** column is changed to **General**. This results in displaying the document ID for an item in scientific notation. For example, the document ID of "481037338205" is displayed as "4.81037E+11" You have to perform the next steps to change the data format of the **Document ID** column to **Number** to restore the correct format for the document ID. If you don't do this, the ID list search that uses the CSV file will fail.</span></span> 
  
4. <span data-ttu-id="03eba-139">右键单击整个 "**文档 ID** " 列, 然后选择 "**设置单元格格式**"。</span><span class="sxs-lookup"><span data-stu-id="03eba-139">Right-click the entire **Document ID** column and select **Format Cells**.</span></span>
    
5. <span data-ttu-id="03eba-140">在 "**类别**" 框中, 单击 "**数字**"。</span><span class="sxs-lookup"><span data-stu-id="03eba-140">In the **Category** box, click **Number**.</span></span>
    
6. <span data-ttu-id="03eba-p113">将小数位数更改为**0**, 然后单击 **"确定"** 以保存所做的更改。请注意, "文档 ID" 列中的值更改为 "数字"。</span><span class="sxs-lookup"><span data-stu-id="03eba-p113">Change the number of decimal places to **0**, and then click **OK** to save your changes. Notice that the values in the Document ID column are changed to numbers.</span></span> 
    
    <span data-ttu-id="03eba-143">下面的示例展示了一个为 ID 列表内容搜索准备提交的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="03eba-143">Here's an example of the a CSV file that's ready to be submitted for a ID list content search.</span></span>
    
    ![目标内容搜索的 CSV 文件的示例](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)
  
7. <span data-ttu-id="03eba-p114">保存 CSV 文件或使用 "**另存为**" 将文件保存为其他文件名。在这两种情况下, 请务必使用 CSV 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="03eba-p114">Save the CSV file or use **Save As** to the save the file with different file name. In both cases, be sure to save the file with the CSV format.</span></span> 
  
## <a name="create-an-id-list-search"></a><span data-ttu-id="03eba-147">创建 ID 列表搜索</span><span class="sxs-lookup"><span data-stu-id="03eba-147">Create an ID list search</span></span>

<span data-ttu-id="03eba-148">下一步是创建新的 ID 列表内容搜索, 并提交在上一步中准备的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="03eba-148">The next step is to create a new ID list Content Search and submit the CSV file that you prepared in the previous step.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="03eba-p115">在从内容搜索导出结果或报告之后, 您应创建一个 ID 列表搜索不超过2天的时间。如果在超过2天前导出的搜索结果或报告, 应重新导出搜索结果或报告以生成更新的 CSV 文件。然后, 您可以准备一个更新的 CSV 文件, 并使用它来创建一个 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="03eba-p115">You should create an ID list search no more than 2 days after exporting the results or report from a Content Search. If the search results or report where exported more than 2 days ago, you should re-export the search results or report to generate updated CSV files. Then you can prepare one of the updated CSV files and use it to create an ID list search.</span></span> 
  
1. <span data-ttu-id="03eba-152">在 "安全&amp;合规性中心" 中, 转到 "**搜索&amp;调查** \> **内容搜索**"。</span><span class="sxs-lookup"><span data-stu-id="03eba-152">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Content search**.</span></span>
    
2. <span data-ttu-id="03eba-153">在 "**搜索**" 页上, 单击 " ![添加图标](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **新搜索**" 旁边的箭头, 然后单击 "**按 ID 列表搜索**"。</span><span class="sxs-lookup"><span data-stu-id="03eba-153">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**, and then click **Search by ID List**.</span></span>
    
    ![单击 "新建搜索" 下拉列表中的 "按 ID 列表搜索"](media/e65f9942-09b2-4127-865e-e64029a590df.png)
  
3. <span data-ttu-id="03eba-155">在 "**按标识号搜索" 列表**中, 命名搜索 (并根据需要对其进行描述), 然后单击 "**浏览**" 并选择在上一步中准备的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="03eba-155">On the **Search by ID List** flyout, name the search (and optionally describe it) and then click **Browse** and select the CSV file that you prepared in the previous step.</span></span> 
    
    <span data-ttu-id="03eba-p116">Office 365 尝试验证 CSV 文件。如果验证失败, 将显示一条错误消息, 可能会帮助您解决验证错误。必须成功验证 CSV 文件, 才能创建 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="03eba-p116">Office 365 attempts to validate the CSV file. If the validation is unsuccessful, an error message is displayed that might help you troubleshoot the validation errors. The CSV file has to be successfully validated to create an ID list search.</span></span>
    
4. <span data-ttu-id="03eba-159">成功验证 CSV 文件后, 单击 "**搜索**" 以创建 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="03eba-159">After the CSV file is successfully validated, click **Search** to create the ID list search.</span></span> 
    
    <span data-ttu-id="03eba-160">下面的示例展示了估计的搜索结果和为 ID 列表搜索生成的查询。</span><span class="sxs-lookup"><span data-stu-id="03eba-160">Here's an example of the estimated search results and the query that's generated for an ID list search.</span></span>
    
    ![详细信息窗格中的目标内容搜索的搜索查询](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)
  
    <span data-ttu-id="03eba-162">请注意, ID 搜索的统计信息中显示的估计项目数应与您在 CSV 文件中选择的项目数相匹配。</span><span class="sxs-lookup"><span data-stu-id="03eba-162">Note that the number of estimated items displayed in statistics for the ID search should match the number of items that you selected in the CSV file.</span></span>
    
5. <span data-ttu-id="03eba-163">预览或导出由 ID 列表搜索返回的项目。</span><span class="sxs-lookup"><span data-stu-id="03eba-163">Preview or export the items returned by the ID list search.</span></span>
    
> [!NOTE]
> <span data-ttu-id="03eba-p117">如果您在创建 ID 列表搜索之后移动邮箱, 搜索的查询不会返回指定的项目。这是因为在移动邮箱时, 邮箱项目的**DocumentId**属性会发生更改。在创建 ID 列表搜索之后移动邮箱时, 在少数情况下, 您应创建新的内容搜索 (或更新现有内容搜索的搜索结果), 然后导出搜索结果或报表以生成可使用的已更新 CSV 文件 创建新的 ID 列表搜索。</span><span class="sxs-lookup"><span data-stu-id="03eba-p117">If you move a mailbox after creating an ID list search, the query for the search won't return the specified items. That's because the **DocumentId** property for mailbox items are changed when a mailbox is moved. In the rare instance when a mailbox is moved after you create an ID list search, you should create a new content search (or update the search results for the existing content search) and then export the search results or report to generate updated CSV files that can be used to create a new ID list search.</span></span> 

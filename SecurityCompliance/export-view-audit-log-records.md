---
title: 导出、配置和查看审核日志记录
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: 将 Office 365 审核日志搜索的结果导出并下载到 CSV 文件后, 可以使用 Excel 中 Power Query 编辑器中的 JSON 转换功能将 AuditData 列中的 JSON 对象中的每个属性拆分为自己的列。 这可以帮助您快速找到要查找的特定审核数据。
ms.openlocfilehash: 7dac373e8f25ead38dddbe2663e521b35b3153ef
ms.sourcegitcommit: b262d40f6daf06be26e7586f37b736e09f8a4511
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35462885"
---
# <a name="export-configure-and-view-audit-log-records"></a><span data-ttu-id="2771b-104">导出、配置和查看审核日志记录</span><span class="sxs-lookup"><span data-stu-id="2771b-104">Export, configure, and view audit log records</span></span>

<span data-ttu-id="2771b-105">在搜索 Office 365 审核日志并将搜索结果下载到 CSV 文件后, 该文件包含一个名为 " **AuditData**" 的列, 其中包含有关每个事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="2771b-105">After you search the Office 365 audit log and download the search results to a CSV file, the file contains a column named **AuditData**, which contains additional information about each event.</span></span> <span data-ttu-id="2771b-106">此列中的数据的格式为 JSON 对象, 该对象包含多个配置为 "*属性: 值*" 对 (用逗号分隔) 的属性。</span><span class="sxs-lookup"><span data-stu-id="2771b-106">The data in this column is formatted as a JSON object, which contains multiple properties that are configured as *property:value* pairs separated by commas.</span></span> <span data-ttu-id="2771b-107">您可以使用 Excel 中 Power Query 编辑器中的 JSON 转换功能, 将**AuditData**列中的 json 对象中的每个属性拆分为多个列, 以便每个属性都有自己的列。</span><span class="sxs-lookup"><span data-stu-id="2771b-107">You can use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into multiple columns so that each property has its own column.</span></span> <span data-ttu-id="2771b-108">这样, 您可以对一个或多个这些属性进行排序和筛选, 这有助于您快速找到要查找的特定审核数据。</span><span class="sxs-lookup"><span data-stu-id="2771b-108">This lets you sort and filter on one or more of these properties, which can help you quickly locate the specific auditing data you're looking for.</span></span>

## <a name="step-1-export-audit-log-search-results"></a><span data-ttu-id="2771b-109">步骤 1: 导出审核日志搜索结果</span><span class="sxs-lookup"><span data-stu-id="2771b-109">Step 1: Export audit log search results</span></span>

<span data-ttu-id="2771b-110">第一步是搜索审核日志, 然后将逗号分隔值 (CSV) 文件中的结果导出到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="2771b-110">The first step is to search the audit log and then export the results in a comma-separated value (CSV) file to your local computer.</span></span>
  
1. <span data-ttu-id="2771b-111">如有必要, 请运行[审核日志搜索](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log)并修改搜索条件, 直到获得所需的结果。</span><span class="sxs-lookup"><span data-stu-id="2771b-111">Run an [audit log search](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) and revise the search criteria if necessary until you have the desired results.</span></span>
    
2. <span data-ttu-id="2771b-112">单击 "**导出结果**", 然后选择 "**下载所有结果**"。</span><span class="sxs-lookup"><span data-stu-id="2771b-112">Click **Export results** and select **Download all results**.</span></span> 
    
   ![单击 "下载所有结果"](media/ExportAuditSearchResults.png)

   <span data-ttu-id="2771b-114">此选项可从您在步骤1中运行的审核日志搜索中导出所有审核记录, 并将该审核日志中的原始数据下载到 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="2771b-114">This option to exports all the audit records from the audit log search you ran in step 1, and downloads the raw data from the audit log to a CSV file.</span></span> 

   <span data-ttu-id="2771b-115">将在窗口底部显示一条消息, 提示您打开或保存 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="2771b-115">A message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span> 

3. <span data-ttu-id="2771b-116">单击 "**保存 > 另存为**", 然后将 CSV 文件保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="2771b-116">Click **Save > Save as** and save the CSV file to your local computer.</span></span> <span data-ttu-id="2771b-117">下载多个搜索结果需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="2771b-117">It takes a while to download many search results.</span></span> <span data-ttu-id="2771b-118">在搜索所有活动或广泛的日期范围时, 通常会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="2771b-118">This is typically the case when searching for all activities or a broad date range.</span></span> <span data-ttu-id="2771b-119">当 CSV 文件下载完成时, 将在窗口底部显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="2771b-119">A message at the bottom of the windows is displayed when the CSV file is finished downloading.</span></span>
 
   ![CSV 文件下载完成时显示的消息](media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > <span data-ttu-id="2771b-121">您可以从单个审核日志搜索中最多将50000个条目下载到 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="2771b-121">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="2771b-122">如果将50000条目下载到 CSV 文件中, 您可能会假定有超过50000个事件满足搜索条件。</span><span class="sxs-lookup"><span data-stu-id="2771b-122">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="2771b-123">若要导出超过此限制, 请尝试使用日期范围来减少审核日志记录的数量。</span><span class="sxs-lookup"><span data-stu-id="2771b-123">To export more than this limit, try using a date range to reduce the number of audit log records.</span></span> <span data-ttu-id="2771b-124">您可能需要运行包含较小日期范围的多个搜索以导出50000个以上的条目。</span><span class="sxs-lookup"><span data-stu-id="2771b-124">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a><span data-ttu-id="2771b-125">步骤 2: 使用 Power Query 编辑器格式化导出的审核日志</span><span class="sxs-lookup"><span data-stu-id="2771b-125">Step 2: Format the exported audit log using the Power Query Editor</span></span>

<span data-ttu-id="2771b-126">下一步是在 Excel 的 Power Query 编辑器中使用 JSON 转换功能, 将**AuditData**列中的 json 对象中的每个属性拆分为其自己的列。</span><span class="sxs-lookup"><span data-stu-id="2771b-126">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="2771b-127">然后, 筛选列以根据特定属性的值查看记录。</span><span class="sxs-lookup"><span data-stu-id="2771b-127">Then you filter columns to view records based on the values of specific properties.</span></span> <span data-ttu-id="2771b-128">这可以帮助您快速找到要查找的特定审核数据。</span><span class="sxs-lookup"><span data-stu-id="2771b-128">This can help you quickly locate the specific auditing data you're looking for.</span></span>

1. <span data-ttu-id="2771b-129">在 Excel 中打开一个空白工作簿, 以用于 Office 365、Excel 2019 或 Excel 2016。</span><span class="sxs-lookup"><span data-stu-id="2771b-129">Open a blank workbook in Excel for Office 365, Excel 2019, or Excel 2016.</span></span>
    
2.  <span data-ttu-id="2771b-130">在 "**数据**" 选项卡上的 "**获取 & 转换数据**" 功能区组中, 单击 "**发件人文本/CSV**"。</span><span class="sxs-lookup"><span data-stu-id="2771b-130">On the **Data** tab, in the **Get & Transform Data** ribbon group, click **From Text/CSV**.</span></span>

    ![在 "数据" 选项卡上, 单击 "发件人文本/CSV"](media/JSONTransformOpenCSVFile.png)

3. <span data-ttu-id="2771b-132">打开您在步骤1中下载的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="2771b-132">Open the CSV file that you downloaded in Step 1.</span></span>
    
4. <span data-ttu-id="2771b-133">在显示的窗口中, 单击 "**转换数据**"。</span><span class="sxs-lookup"><span data-stu-id="2771b-133">In the window that's displayed, click **Transform Data**.</span></span>

   ![单击 "转换数据"](media/JSONOpenPowerQuery.png)

<span data-ttu-id="2771b-135">CSV 文件将在**查询编辑器**中打开。</span><span class="sxs-lookup"><span data-stu-id="2771b-135">The CSV file is opened in the **Query Editor**.</span></span> <span data-ttu-id="2771b-136">共有四列: **CreationDate**、 **UserIds**、 **Operations**和**AuditData**。</span><span class="sxs-lookup"><span data-stu-id="2771b-136">There are four columns: **CreationDate**, **UserIds**, **Operations**, and **AuditData**.</span></span> <span data-ttu-id="2771b-137">**AuditData**列是一个包含多个属性的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="2771b-137">The **AuditData** column is a JSON object that contains multiple properties.</span></span> <span data-ttu-id="2771b-138">下一步是为 JSON 对象中的每个属性创建一个列。</span><span class="sxs-lookup"><span data-stu-id="2771b-138">The next step is to create a column for each property in the JSON object.</span></span>
    
5. <span data-ttu-id="2771b-139">右键单击 " **AuditData** " 列中的标题, 单击 "**转换**", 然后单击 " **JSON**"。</span><span class="sxs-lookup"><span data-stu-id="2771b-139">Right-click the title in the **AuditData** column, click **Transform**, and then click **JSON**.</span></span> 
 
   ![右键单击 "AuditData" 列, 单击 "转换", 然后选择 "JSON"。](media/JSONTransform.png)

6. <span data-ttu-id="2771b-141">在 " **AuditData** " 列的右上角, 单击 "展开" 图标。</span><span class="sxs-lookup"><span data-stu-id="2771b-141">In the upper-right corner of the **AuditData** column, click the expand icon.</span></span>
    
   ![在 "AuditData" 列中, 单击展开图标](media/JSONTransformExpandIcon.png)

   <span data-ttu-id="2771b-143">将显示**AuditData**列中 JSON 对象中的属性的部分列表。</span><span class="sxs-lookup"><span data-stu-id="2771b-143">A partial list of the properties in the JSON objects in the **AuditData** column is displayed.</span></span>

7. <span data-ttu-id="2771b-144">单击 "**加载更多**" 以在**AuditData**列中的 JSON 对象中显示所有属性。</span><span class="sxs-lookup"><span data-stu-id="2771b-144">Click **Load more** to display all properties in the JSON objects in the **AuditData** column.</span></span>

   ![单击 "加载更多" 以显示 JSON 对象中的所有属性](media/JSONTransformLoadJSONProperties.png)

   <span data-ttu-id="2771b-146">您可以取消选中任何您不想包含的属性旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="2771b-146">You can unselect the checkbox next to any property that you don't want to include.</span></span> <span data-ttu-id="2771b-147">删除对调查不有用的列是减少审核日志中显示的数据量的好方法。</span><span class="sxs-lookup"><span data-stu-id="2771b-147">Eliminating columns that aren't useful for your investigation is a good way to reduce the amount of data displayed in the audit log.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="2771b-148">上面的屏幕截图中显示的 JSON 属性 (在单击 "**加载更多**" 之后) 基于 CSV 文件中的前1000行中的 " **AuditData** " 列中的属性。</span><span class="sxs-lookup"><span data-stu-id="2771b-148">The JSON properties displayed in the previous screenshot (after you click **Load more**) are based on the properties found in the **AuditData** column from the first 1,000 rows in the CSV file.</span></span> <span data-ttu-id="2771b-149">如果第一个1000行后面的记录中有不同的 JSON 属性, 则当**AuditData**列拆分为多个列时, 将不会包含这些属性 (和相应的列)。</span><span class="sxs-lookup"><span data-stu-id="2771b-149">If there are different JSON properties in records after the first 1,000 rows, these properties (and a corresponding column) won't be included when the **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="2771b-150">若要帮助防止这种情况, 请考虑重新运行审核日志搜索并缩小搜索条件, 以便返回的记录较少。</span><span class="sxs-lookup"><span data-stu-id="2771b-150">To help prevent this, consider re-running the audit log search and narrow the search criteria so that fewer records are returned.</span></span> <span data-ttu-id="2771b-151">另一种解决方法是在转换 " **AuditData** " 列中的 JSON 对象之前, 筛选 "**操作**" 列中的项目, 以减少行数 (在前面执行第5步之前)。</span><span class="sxs-lookup"><span data-stu-id="2771b-151">Another workaround is to filter items in the **Operations** column to reduce the number of rows (before you perform step 5 above) before transforming the JSON object in the **AuditData** column.</span></span>

8. <span data-ttu-id="2771b-152">执行下列操作之一, 设置为所选的每个 JSON 属性添加的列的标题。</span><span class="sxs-lookup"><span data-stu-id="2771b-152">Do one of the following things to format the title of the columns that are added for each JSON property that's selected.</span></span>

    - <span data-ttu-id="2771b-153">取消选中 "**使用原始列名称作为前缀**" 复选框, 以将 JSON 属性的名称用作列名称;例如, **RecordType**或**SourceFileName**。</span><span class="sxs-lookup"><span data-stu-id="2771b-153">Unselect the **Use original column name as prefix** checkbox to use the name of the JSON property as the column names; for example, **RecordType** or **SourceFileName**.</span></span>
    
   - <span data-ttu-id="2771b-154">将 "**使用原始列名称作为前缀**" 复选框保留为选中状态, 以将 AuditData 前缀添加到列名称中;例如, RecordType 或**AuditData**。 **AuditData** 。</span><span class="sxs-lookup"><span data-stu-id="2771b-154">Leave the **Use original column name as prefix** checkbox selected to add the AuditData prefix to the column names; for example, **AuditData.RecordType** or **AuditData.SourceFileName**.</span></span>

9. <span data-ttu-id="2771b-155">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2771b-155">Click **OK**.</span></span>
    
    <span data-ttu-id="2771b-156">**AuditData**列拆分为多个列。</span><span class="sxs-lookup"><span data-stu-id="2771b-156">The **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="2771b-157">每个新列对应于 AuditData JSON 对象中的一个属性。</span><span class="sxs-lookup"><span data-stu-id="2771b-157">Each new column corresponds to a property in the AuditData JSON object.</span></span> <span data-ttu-id="2771b-158">该列中的每一行都包含属性的值。</span><span class="sxs-lookup"><span data-stu-id="2771b-158">Each row in the column contains the value for the property.</span></span> <span data-ttu-id="2771b-159">如果属性不包含值, 则显示*null*值。</span><span class="sxs-lookup"><span data-stu-id="2771b-159">If the property doesn't contain a value, the *null* value is displayed.</span></span> <span data-ttu-id="2771b-160">在 Excel 中, 空值的单元格为空。</span><span class="sxs-lookup"><span data-stu-id="2771b-160">In Excel, cells with null values are empty.</span></span>
  
10. <span data-ttu-id="2771b-161">在 "**开始**" 选项卡上, 单击 "**关闭 & 加载**" 以关闭 Power Query 编辑器, 并在 Excel 工作簿中打开转换后的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="2771b-161">On the **Home** tab, click **Close & Load** to close the Power Query Editor and open the transformed CSV file in an Excel workbook.</span></span> 

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a><span data-ttu-id="2771b-162">导出和查看审核日志的提示</span><span class="sxs-lookup"><span data-stu-id="2771b-162">Tips for exporting and viewing the audit log</span></span>

<span data-ttu-id="2771b-163">下面是在使用 JSON 转换功能将**AuditData**列拆分为多个列之前和之后导出和查看审核日志的一些提示和示例。</span><span class="sxs-lookup"><span data-stu-id="2771b-163">Here are some tips and examples of exporting and viewing the audit log before and after you use the JSON transform feature to split the **AuditData** column into multiple columns.</span></span>

- <span data-ttu-id="2771b-164">筛选**RecordType**列以仅显示特定的 Office 365 服务或功能区域中的记录。</span><span class="sxs-lookup"><span data-stu-id="2771b-164">Filter the **RecordType** column to display only the records from a specific Office 365 service or functional area.</span></span> <span data-ttu-id="2771b-165">例如, 若要显示与 SharePoint 共享相关的事件, 请选择**14**个 (由 SharePoint 共享活动触发的记录的枚举值)。</span><span class="sxs-lookup"><span data-stu-id="2771b-165">For example, to show events related to SharePoint sharing, you would select **14** (the enum value for records triggered by SharePoint sharing activities).</span></span> <span data-ttu-id="2771b-166">有关与**RecordType**列中显示的枚举值相对应的 Office 365 服务的列表, 请参阅[Office 365 审核日志中的详细属性](detailed-properties-in-the-office-365-audit-log.md)。</span><span class="sxs-lookup"><span data-stu-id="2771b-166">For a list of the Office 365 services that correspond to the enum values displayed in the **RecordType** column, see [Detailed properties in the Office 365 audit log](detailed-properties-in-the-office-365-audit-log.md).</span></span>

- <span data-ttu-id="2771b-167">筛选 "**操作**" 列以显示特定活动的记录。</span><span class="sxs-lookup"><span data-stu-id="2771b-167">Filter the **Operations** column to display the records for specific activities.</span></span> <span data-ttu-id="2771b-168">有关与安全 & 合规中心中的审核日志搜索工具中的可搜索活动对应的大多数操作的列表, 请参阅在[安全 & 合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md#audited-activities)中的 "已审核的活动" 部分。</span><span class="sxs-lookup"><span data-stu-id="2771b-168">For a list of most operations that correspond to a searchable activity in the audit log search tool in the Security & Compliance Center, see the "Audited activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>

- <span data-ttu-id="2771b-169">您可以使用 Exchange Online Powershell 中的[UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) Cmdlet 将 Office 365 审核日志搜索的结果导出到 CSV 文件, 而不是使用安全 & 合规中心中的审核日志搜索工具。</span><span class="sxs-lookup"><span data-stu-id="2771b-169">Instead of using the audit log search tool in the Security & Compliance Center, you can use the [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) cmdlet in Exchange Online Powershell to export the results of an Office 365 audit log search to a CSV file.</span></span> <span data-ttu-id="2771b-170">然后, 您可以按照步骤2中描述的相同过程使用 Power Query 编辑器格式化审核日志。</span><span class="sxs-lookup"><span data-stu-id="2771b-170">Then you can follow the same procedure described in Step 2 to format the audit log using the Power Query editor.</span></span> <span data-ttu-id="2771b-171">使用 PowerShell cmdlet 的一个优点是, 您可以使用*RecordType*参数从特定的 Office 365 服务中搜索事件。</span><span class="sxs-lookup"><span data-stu-id="2771b-171">One advantage of using the PowerShell cmdlet is that you can search for events from a specific Office 365 service by using the *RecordType* parameter.</span></span> <span data-ttu-id="2771b-172">下面是使用 PowerShell 将审核记录导出到 CSV 文件的几个示例, 以便您可以使用 Power Query 编辑器转换**AuditData**列中的 JSON 对象, 如步骤2中所述。</span><span class="sxs-lookup"><span data-stu-id="2771b-172">Here are few examples of using PowerShell to export audit records to a CSV file so you can use the Power Query editor to transform the JSON object in the **AuditData** column as described in Step 2.</span></span>

   <span data-ttu-id="2771b-173">在此示例中, 运行以下命令以返回与 SharePoint 共享操作相关的所有记录。</span><span class="sxs-lookup"><span data-stu-id="2771b-173">In this example, run the following commands to return all records related to SharePoint sharing operations.</span></span> 
   
   ```
   $auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
   ```

   ```
   $auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
   ```

   - <span data-ttu-id="2771b-174">搜索结果将导出到名为*PowerShellAuditlog*的 CSV 文件中, 该文件包含四列: CreationDate、UserIds、RecordType、AuditData)。</span><span class="sxs-lookup"><span data-stu-id="2771b-174">The search results are exported to a CSV file named *PowerShellAuditlog* that contains four columns: CreationDate, UserIds, RecordType, AuditData).</span></span>

   - <span data-ttu-id="2771b-175">您可以将记录类型的名称或枚举值用作*RecordType*参数的值。</span><span class="sxs-lookup"><span data-stu-id="2771b-175">You can use the name or enum value for the record type as the value for the *RecordType* parameter.</span></span> <span data-ttu-id="2771b-176">有关记录类型名称及其相应的枚举值的列表, 请参阅[Office 365 管理活动 API 架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)中的*AuditLogRecordType*表。</span><span class="sxs-lookup"><span data-stu-id="2771b-176">For a list of record type names and their corresponding enum values, see the *AuditLogRecordType* table in [Office 365 Management Activity API schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32).</span></span>
   
   - <span data-ttu-id="2771b-177">此参数仅可包含一个值。</span><span class="sxs-lookup"><span data-stu-id="2771b-177">You can only include a single value for this parameter.</span></span> <span data-ttu-id="2771b-178">若要搜索其他记录类型的审核记录, 您必须再次运行前面的两个命令以指定不同的记录类型, 并将这些结果追加到原始 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="2771b-178">To search for audit records for other record types, you have to run the two previous commands again to specify a different record type and append those results to the original CSV file.</span></span> <span data-ttu-id="2771b-179">例如, 您可以运行以下两个命令, 将 SharePoint 文件活动从同一日期范围添加到 PowerShellAuditlog 文件中。</span><span class="sxs-lookup"><span data-stu-id="2771b-179">For example, you would run these two commands to add SharePoint file activities from the same date range to the PowerShellAuditlog.csv file.</span></span>

       ```
      $auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
      ```

      ```
      $auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
      ```

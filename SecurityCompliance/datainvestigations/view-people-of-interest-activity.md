---
title: 查看相关人员的审核活动
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 82c6cb419ce00aca0d636083aa41a3384cb6bb01
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "31029924"
---
# <a name="view-the-audit-activity-of-people-of-interest"></a><span data-ttu-id="9abc5-102">查看相关人员的审核活动</span><span class="sxs-lookup"><span data-stu-id="9abc5-102">View the audit activity of people of interest</span></span>

<span data-ttu-id="9abc5-103">需要查找用户是否查看了特定文档或清除了其邮箱中的项目？</span><span class="sxs-lookup"><span data-stu-id="9abc5-103">Need to find if a user viewed a specific document or purged an item from their mailbox?</span></span> <span data-ttu-id="9abc5-104">数据调查 (预览版) 现已与 Security & 合规中心中的现有审核日志搜索工具集成。</span><span class="sxs-lookup"><span data-stu-id="9abc5-104">Data Investigations (Preview) is now integrated with the existing audit log search tool in the Security & Compliance Center.</span></span> <span data-ttu-id="9abc5-105">使用这种嵌入的体验, 您可以使用 "数据调查" (预览) 相关人员管理工具来帮助您进行调查, 从而轻松访问和搜索调查中感兴趣的人员的活动。</span><span class="sxs-lookup"><span data-stu-id="9abc5-105">Using this embedded experience, you can use the Data Investigations (Preview) People of interest Management tool to facilitate your investigation by easily accessing and searching the activity for people of interest within your investigation.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9abc5-106">开始之前</span><span class="sxs-lookup"><span data-stu-id="9abc5-106">Before you begin</span></span>

<span data-ttu-id="9abc5-107">您必须在 Exchange Online 中向您分配 "仅查看审核日志" 或 "审核日志" 角色, 才能搜索 Office 365 审核日志。</span><span class="sxs-lookup"><span data-stu-id="9abc5-107">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log.</span></span> <span data-ttu-id="9abc5-108">默认情况下, 将这些角色分配给 Exchange 管理中心中 "权限" 页上的 "合规性管理" 和 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="9abc5-108">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="9abc5-109">若要使用户能够使用最低级别的权限搜索数据调查 (预览) 审核日志, 您可以在 Exchange Online 中创建自定义角色组, 添加仅查看审核日志或审核日志角色, 然后将该用户添加为新角色 gr 的成员oup。</span><span class="sxs-lookup"><span data-stu-id="9abc5-109">To give a user the ability to search the Data Investigations (Preview) audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="9abc5-110">有关详细信息, 请参阅在 Exchange Online 中管理角色组。</span><span class="sxs-lookup"><span data-stu-id="9abc5-110">For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9abc5-111">如果在 Security & 合规性中心的 "权限" 页上为用户分配 "仅查看审核日志" 或 "审核日志" 角色, 则他们将无法搜索 Office 365 审核日志。</span><span class="sxs-lookup"><span data-stu-id="9abc5-111">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the Office 365 audit log.</span></span> <span data-ttu-id="9abc5-112">您必须在 Exchange Online 中分配权限。</span><span class="sxs-lookup"><span data-stu-id="9abc5-112">You have to assign the permissions in Exchange Online.</span></span> <span data-ttu-id="9abc5-113">这是因为用于搜索审核日志的基础 cmdlet 是 Exchange Online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9abc5-113">This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-create-an-data-investigations-preview-audit-log-search"></a><span data-ttu-id="9abc5-114">步骤 1: 创建数据调查 (预览) 审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="9abc5-114">Step 1: Create an Data Investigations (Preview) audit log search</span></span>

   1. <span data-ttu-id="9abc5-115">从**Security & 合规性中心 > 数据调查 (预览)** 中选择现有调查。</span><span class="sxs-lookup"><span data-stu-id="9abc5-115">Select an existing investigation from the **Security & Compliance Center > Data Investigations (Preview)**.</span></span>
   
   2. <span data-ttu-id="9abc5-116">导航到 "**感兴趣的人员**" 选项卡, 然后选择一个人员。</span><span class="sxs-lookup"><span data-stu-id="9abc5-116">Navigate to the **People of interest** tab and select a person.</span></span>
   
   3. <span data-ttu-id="9abc5-117">选择人员后, 单击 "详细信息" 面板中的 "**查看活动**"。</span><span class="sxs-lookup"><span data-stu-id="9abc5-117">Once you have selected a person, click **View Activity** from the details panel.</span></span>
   
   4. <span data-ttu-id="9abc5-118">配置以下搜索条件:</span><span class="sxs-lookup"><span data-stu-id="9abc5-118">Configure the following search criteria:</span></span>
      
      <span data-ttu-id="9abc5-119">a.</span><span class="sxs-lookup"><span data-stu-id="9abc5-119">a.</span></span> <span data-ttu-id="9abc5-120">**活动**-单击下拉列表以显示可以搜索的活动。</span><span class="sxs-lookup"><span data-stu-id="9abc5-120">**Activities** - Click the drop-down list to display the activities that you can search for.</span></span> <span data-ttu-id="9abc5-121">运行搜索后, 仅显示所选活动的审核记录。</span><span class="sxs-lookup"><span data-stu-id="9abc5-121">After you run the search, only the audit records for the selected activities are displayed.</span></span> <span data-ttu-id="9abc5-122">选择 "**显示所有活动的结果**" 将显示符合其他搜索条件的所有活动的结果。</span><span class="sxs-lookup"><span data-stu-id="9abc5-122">Selecting **Show results for all activities** will display results for all activities that meet the other search criteria.</span></span>
      
      <span data-ttu-id="9abc5-123">b.</span><span class="sxs-lookup"><span data-stu-id="9abc5-123">b.</span></span> <span data-ttu-id="9abc5-124">"**开始日期" 和 "结束日期**"-选择要显示在该时间段内发生的事件的日期和时间范围。</span><span class="sxs-lookup"><span data-stu-id="9abc5-124">**Start date and End date** - Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="9abc5-125">默认情况下, 选择最后七天。</span><span class="sxs-lookup"><span data-stu-id="9abc5-125">The last seven days are selected by default.</span></span> <span data-ttu-id="9abc5-126">日期和时间以协调通用时间 (UTC) 格式显示。</span><span class="sxs-lookup"><span data-stu-id="9abc5-126">The date and time are presented in Coordinated Universal Time (UTC) format.</span></span> <span data-ttu-id="9abc5-127">您可以指定的最大日期范围为一年。</span><span class="sxs-lookup"><span data-stu-id="9abc5-127">The maximum date range that you can specify is one year.</span></span>
      
      <span data-ttu-id="9abc5-128">c.</span><span class="sxs-lookup"><span data-stu-id="9abc5-128">c.</span></span> <span data-ttu-id="9abc5-129">**感兴趣的人**-在此框中单击, 然后选择要显示其搜索结果的特定管理员。</span><span class="sxs-lookup"><span data-stu-id="9abc5-129">**People of interest** - Click in this box and then select a specific custodian to display search results for.</span></span> <span data-ttu-id="9abc5-130">您在此框中选择的用户执行的选定活动的审核记录将显示在结果列表中。</span><span class="sxs-lookup"><span data-stu-id="9abc5-130">Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
    
    1. <span data-ttu-id="9abc5-131">单击 "**搜索**" 以使用搜索条件运行搜索。</span><span class="sxs-lookup"><span data-stu-id="9abc5-131">Click **Search** to run the search using your search criteria.</span></span> <span data-ttu-id="9abc5-132">搜索结果已加载, 并在几分钟后显示在 "相关人员活动搜索" 页的 "结果" 下。</span><span class="sxs-lookup"><span data-stu-id="9abc5-132">The search results are loaded, and after a few moments they are displayed under Results on the People of interest Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="9abc5-133">步骤 2: 查看审核日志搜索结果</span><span class="sxs-lookup"><span data-stu-id="9abc5-133">Step 2: View the audit log search results</span></span>

<span data-ttu-id="9abc5-134">审核日志搜索的结果将显示在 "感兴趣的人的审核日志" 页上的 "结果" 下。</span><span class="sxs-lookup"><span data-stu-id="9abc5-134">The results of an audit log search are displayed under Results on the People of interest Audit log page.</span></span> <span data-ttu-id="9abc5-135">最多 5000 (最新) 事件以150个事件为增量显示。</span><span class="sxs-lookup"><span data-stu-id="9abc5-135">A maximum of 5,000 (newest) events are displayed in increments of 150 events.</span></span> <span data-ttu-id="9abc5-136">若要显示更多事件, 可以使用 "结果" 窗格中的滚动条, 也可以按 Shift + End 显示接下来的150事件。</span><span class="sxs-lookup"><span data-stu-id="9abc5-136">To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="9abc5-137">结果中包含有关搜索返回的每个事件的以下信息。</span><span class="sxs-lookup"><span data-stu-id="9abc5-137">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="9abc5-138">**日期**: 事件发生时的日期和时间 (采用 UTC 格式)。</span><span class="sxs-lookup"><span data-stu-id="9abc5-138">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="9abc5-139">**IP 地址**: 记录活动时使用的设备的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="9abc5-139">**IP address**: The IP address of the device that was used when the activity was logged.</span></span> <span data-ttu-id="9abc5-140">IP 地址显示为 IPv4 或 IPv6 地址格式。</span><span class="sxs-lookup"><span data-stu-id="9abc5-140">The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="9abc5-141">**user**: 执行触发事件的操作的用户 (或服务帐户)。</span><span class="sxs-lookup"><span data-stu-id="9abc5-141">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="9abc5-142">**活动**: 用户执行的活动。</span><span class="sxs-lookup"><span data-stu-id="9abc5-142">**Activity**: The activity performed by the user.</span></span> <span data-ttu-id="9abc5-143">此值与您在 "活动" 下拉列表中选择的活动相对应。</span><span class="sxs-lookup"><span data-stu-id="9abc5-143">This value corresponds to the activities that you selected in the Activities drop down list.</span></span> <span data-ttu-id="9abc5-144">对于来自 exchange 管理员审核日志的事件, 此列中的值为 exchange cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9abc5-144">For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="9abc5-145">**Item**: 作为相应活动的结果创建或修改的对象。</span><span class="sxs-lookup"><span data-stu-id="9abc5-145">**Item**: The object that was created or modified as a result of the corresponding activity.</span></span> <span data-ttu-id="9abc5-146">例如, 已查看或修改的文件或已更新的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9abc5-146">For example, the file that was viewed or modified or the user account that was updated.</span></span> <span data-ttu-id="9abc5-147">此列中并非所有活动都具有值。</span><span class="sxs-lookup"><span data-stu-id="9abc5-147">Not all activities have a value in this column.</span></span>

- <span data-ttu-id="9abc5-148">**详细**信息: 活动的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="9abc5-148">**Detail**: Additional detail about an activity.</span></span> <span data-ttu-id="9abc5-149">同样, 并非所有活动都具有值。</span><span class="sxs-lookup"><span data-stu-id="9abc5-149">Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="9abc5-150">步骤 3: 筛选搜索结果</span><span class="sxs-lookup"><span data-stu-id="9abc5-150">Step 3: Filter the search results</span></span>

<span data-ttu-id="9abc5-151">除了排序之外, 您还可以筛选审核日志搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="9abc5-151">In addition to sorting, you can also filter the results of an audit log search.</span></span> <span data-ttu-id="9abc5-152">这可帮助您快速筛选特定用户或活动的结果。</span><span class="sxs-lookup"><span data-stu-id="9abc5-152">This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="9abc5-153">筛选结果:</span><span class="sxs-lookup"><span data-stu-id="9abc5-153">To filter the results:</span></span>

 1. <span data-ttu-id="9abc5-154">创建和运行审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="9abc5-154">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="9abc5-155">显示结果后, 单击 "**筛选结果**"。</span><span class="sxs-lookup"><span data-stu-id="9abc5-155">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="9abc5-156">关键字框显示在每个列标题下。</span><span class="sxs-lookup"><span data-stu-id="9abc5-156">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="9abc5-157">单击列标题下的一个框, 并根据要筛选的列键入一个词或短语。</span><span class="sxs-lookup"><span data-stu-id="9abc5-157">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on.</span></span> <span data-ttu-id="9abc5-158">结果将会动态调整, 以显示与您的筛选器匹配的事件。</span><span class="sxs-lookup"><span data-stu-id="9abc5-158">The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="9abc5-159">若要清除筛选器, 请单击 "筛选器" 框中的 " **X** " 或只单击 "**隐藏筛选**"。</span><span class="sxs-lookup"><span data-stu-id="9abc5-159">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="9abc5-160">将搜索结果导出到文件</span><span class="sxs-lookup"><span data-stu-id="9abc5-160">Export the search results to a file</span></span>

<span data-ttu-id="9abc5-161">您可以将审核日志搜索的结果导出到本地计算机上的逗号分隔值 (CSV) 文件中。</span><span class="sxs-lookup"><span data-stu-id="9abc5-161">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer.</span></span> <span data-ttu-id="9abc5-162">可以在 Microsoft Excel 中打开此文件, 并使用诸如搜索、排序、筛选和拆分单个列 (包含多值单元格) 的多个列中的功能。</span><span class="sxs-lookup"><span data-stu-id="9abc5-162">You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="9abc5-163">运行审核日志搜索, 然后修改搜索条件, 直到获得所需的结果。</span><span class="sxs-lookup"><span data-stu-id="9abc5-163">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="9abc5-164">单击 "导出结果", 然后选择下列选项之一:</span><span class="sxs-lookup"><span data-stu-id="9abc5-164">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="9abc5-165">**保存加载的结果:** 如果选择此选项, 则仅导出 "**感兴趣的人员" 审核日志搜索**页上的 "**结果**" 下显示的条目。</span><span class="sxs-lookup"><span data-stu-id="9abc5-165">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **People of interest Audit log search** page.</span></span> <span data-ttu-id="9abc5-166">下载的 CSV 文件包含页面上显示的相同列 (和数据) (日期、用户、活动、项和详细信息)。</span><span class="sxs-lookup"><span data-stu-id="9abc5-166">The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details).</span></span> <span data-ttu-id="9abc5-167">包含来自审核日志条目的详细信息的 CSV 文件中包含其他列 (标题**更详细**)。</span><span class="sxs-lookup"><span data-stu-id="9abc5-167">An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry.</span></span> <span data-ttu-id="9abc5-168">因为您要导出的结果与在审核日志搜索页面上加载 (和查看) 的结果相同, 所以最多可以导出5000个条目。</span><span class="sxs-lookup"><span data-stu-id="9abc5-168">Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="9abc5-169">**下载所有结果:** 选择此选项可导出符合搜索条件的 Office 365 审核日志中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="9abc5-169">**Download all results:** Choose this option to export all entries from the Office 365 audit log that meet the search criteria.</span></span> <span data-ttu-id="9abc5-170">对于较大的搜索结果集, 请选择此选项, 从审核日志中下载所有条目, 除了可在 "**感兴趣的人员" 审核日志**搜索页上显示的5000结果。</span><span class="sxs-lookup"><span data-stu-id="9abc5-170">For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **People of interest Audit log** search page.</span></span> <span data-ttu-id="9abc5-171">此选项将从审核日志中将原始数据下载到 CSV 文件, 并包含来自名为 AuditData 的列中的审核日志条目的其他信息。</span><span class="sxs-lookup"><span data-stu-id="9abc5-171">This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData.</span></span> <span data-ttu-id="9abc5-172">如果选择此导出选项, 可能需要较长时间下载文件, 因为如果选择其他选项, 文件可能会比下载的文件大得多。</span><span class="sxs-lookup"><span data-stu-id="9abc5-172">It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="9abc5-173">您可以从单个审核日志搜索中最多将50000个条目下载到 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="9abc5-173">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="9abc5-174">如果将50000条目下载到 CSV 文件中, 您可能会假定有超过50000个事件满足搜索条件。</span><span class="sxs-lookup"><span data-stu-id="9abc5-174">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="9abc5-175">若要导出超过此限制, 请尝试使用日期范围来减少审核日志条目的数量。</span><span class="sxs-lookup"><span data-stu-id="9abc5-175">To export more than this limit, try using a date range to reduce the number of audit log entries.</span></span> <span data-ttu-id="9abc5-176">您可能需要运行包含较小日期范围的多个搜索以导出50000个以上的条目。</span><span class="sxs-lookup"><span data-stu-id="9abc5-176">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="9abc5-177">选择 "导出" 选项后, 将在窗口底部显示一条消息, 提示您打开 CSV 文件, 将其保存到 "下载" 文件夹中, 或将其保存到特定文件夹中</span><span class="sxs-lookup"><span data-stu-id="9abc5-177">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="9abc5-178">有关查看、筛选或导出审核日志搜索结果的详细信息, 请参阅[在 Office 365 中搜索审核日志](../search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="9abc5-178">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Office 365](../search-the-audit-log-in-security-and-compliance.md).</span></span>
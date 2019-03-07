---
title: 查看保管人审核活动
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
ms.openlocfilehash: defc89f1d54238e62f947fd197e7a866380ee601
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455164"
---
# <a name="view-custodian-audit-activity"></a><span data-ttu-id="a23ec-102">查看保管人审核活动</span><span class="sxs-lookup"><span data-stu-id="a23ec-102">View custodian audit activity</span></span>

<span data-ttu-id="a23ec-103">需要查找用户是否查看了特定文档或清除了其邮箱中的项目？</span><span class="sxs-lookup"><span data-stu-id="a23ec-103">Need to find if a user viewed a specific document or purged an item from their mailbox?</span></span> <span data-ttu-id="a23ec-104">高级电子数据展示 (预览版) 现已与 Security & 合规中心中的现有审核日志搜索工具集成。</span><span class="sxs-lookup"><span data-stu-id="a23ec-104">Advanced eDiscovery (Preview) is now integrated with the existing audit log search tool in the Security & Compliance Center.</span></span> <span data-ttu-id="a23ec-105">使用此嵌入的体验, 您可以使用高级电子数据展示 (预览) 保管人管理工具来促进您的调查, 并在您的案例中轻松访问和搜索保管人的活动。</span><span class="sxs-lookup"><span data-stu-id="a23ec-105">Using this embedded experience, you can use the Advanced eDiscovery (Preview) Custodian Management tool to facilitate your investigation by easily accessing and searching the activity for custodians within your case.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a23ec-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="a23ec-106">Before you begin</span></span>

<span data-ttu-id="a23ec-107">您必须在 Exchange Online 中向您分配 "仅查看审核日志" 或 "审核日志" 角色, 才能搜索 Office 365 审核日志。</span><span class="sxs-lookup"><span data-stu-id="a23ec-107">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log.</span></span> <span data-ttu-id="a23ec-108">默认情况下, 将这些角色分配给 Exchange 管理中心中 "权限" 页上的 "合规性管理" 和 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="a23ec-108">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="a23ec-109">若要使用户能够使用最低级别的权限搜索高级电子数据展示 (预览) 审核日志, 您可以在 Exchange Online 中创建自定义角色组, 添加仅查看审核日志或审核日志角色, 然后将该用户添加为新角色 gr 的成员oup。</span><span class="sxs-lookup"><span data-stu-id="a23ec-109">To give a user the ability to search the Advanced eDiscovery (Preview) audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group.</span></span> <span data-ttu-id="a23ec-110">有关详细信息, 请参阅在 Exchange Online 中管理角色组。</span><span class="sxs-lookup"><span data-stu-id="a23ec-110">For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a23ec-111">如果在 Security & 合规性中心的 "权限" 页上为用户分配 "仅查看审核日志" 或 "审核日志" 角色, 则他们将无法搜索 Office 365 审核日志。</span><span class="sxs-lookup"><span data-stu-id="a23ec-111">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the Office 365 audit log.</span></span> <span data-ttu-id="a23ec-112">您必须在 Exchange Online 中分配权限。</span><span class="sxs-lookup"><span data-stu-id="a23ec-112">You have to assign the permissions in Exchange Online.</span></span> <span data-ttu-id="a23ec-113">这是因为用于搜索审核日志的基础 cmdlet 是 Exchange Online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a23ec-113">This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-create-an-advanced-ediscovery-preview-audit-log-search"></a><span data-ttu-id="a23ec-114">步骤 1: 创建高级电子数据展示 (预览) 审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="a23ec-114">Step 1: Create an Advanced eDiscovery (Preview) audit log search</span></span>

   1. <span data-ttu-id="a23ec-115">从**Security & 合规性中心 > 高级电子数据展示 (预览)** 中选择现有事例。</span><span class="sxs-lookup"><span data-stu-id="a23ec-115">Select an existing case from the **Security & Compliance Center > Advanced eDiscovery (Preview)**.</span></span>
   
   2. <span data-ttu-id="a23ec-116">导航到 "**保管人**" 选项卡, 然后选择管理员。</span><span class="sxs-lookup"><span data-stu-id="a23ec-116">Navigate to the **Custodians** tab and select a custodian.</span></span>
   
   3. <span data-ttu-id="a23ec-117">选择管理员后, 单击</span><span class="sxs-lookup"><span data-stu-id="a23ec-117">Once you have selected a custodian, click</span></span>  ![查看保管人活动](../media/ViewCustodianActivity.PNG)  <span data-ttu-id="a23ec-119">从 "详细信息" 面板中。</span><span class="sxs-lookup"><span data-stu-id="a23ec-119">from the details panel.</span></span>
   
   4. <span data-ttu-id="a23ec-120">配置以下搜索条件:</span><span class="sxs-lookup"><span data-stu-id="a23ec-120">Configure the following search criteria:</span></span>
      
      <span data-ttu-id="a23ec-121">a.</span><span class="sxs-lookup"><span data-stu-id="a23ec-121">a.</span></span> <span data-ttu-id="a23ec-122">**活动**-单击下拉列表以显示可以搜索的活动。</span><span class="sxs-lookup"><span data-stu-id="a23ec-122">**Activities** - Click the drop-down list to display the activities that you can search for.</span></span> <span data-ttu-id="a23ec-123">运行搜索后, 仅显示所选活动的审核记录。</span><span class="sxs-lookup"><span data-stu-id="a23ec-123">After you run the search, only the audit records for the selected activities are displayed.</span></span> <span data-ttu-id="a23ec-124">选择 "**显示所有活动的结果**" 将显示符合其他搜索条件的所有活动的结果。</span><span class="sxs-lookup"><span data-stu-id="a23ec-124">Selecting **Show results for all activities** will display results for all activities that meet the other search criteria.</span></span>

      ![活动列表](../media/CustodianActivityAudit.PNG)
      
      <span data-ttu-id="a23ec-126">b.</span><span class="sxs-lookup"><span data-stu-id="a23ec-126">b.</span></span> <span data-ttu-id="a23ec-127">"**开始日期" 和 "结束日期**"-选择要显示在该时间段内发生的事件的日期和时间范围。</span><span class="sxs-lookup"><span data-stu-id="a23ec-127">**Start date and End date** - Select a date and time range to display the events that occurred within that period.</span></span> <span data-ttu-id="a23ec-128">默认情况下, 选择最后七天。</span><span class="sxs-lookup"><span data-stu-id="a23ec-128">The last seven days are selected by default.</span></span> <span data-ttu-id="a23ec-129">日期和时间以协调通用时间 (UTC) 格式显示。</span><span class="sxs-lookup"><span data-stu-id="a23ec-129">The date and time are presented in Coordinated Universal Time (UTC) format.</span></span> <span data-ttu-id="a23ec-130">您可以指定的最大日期范围为一年。</span><span class="sxs-lookup"><span data-stu-id="a23ec-130">The maximum date range that you can specify is one year.</span></span>
      
      <span data-ttu-id="a23ec-131">c.</span><span class="sxs-lookup"><span data-stu-id="a23ec-131">c.</span></span> <span data-ttu-id="a23ec-132">**保管人**-在此框中单击, 然后选择要显示其搜索结果的特定管理员。</span><span class="sxs-lookup"><span data-stu-id="a23ec-132">**Custodians** - Click in this box and then select a specific custodian to display search results for.</span></span> <span data-ttu-id="a23ec-133">您在此框中选择的用户执行的选定活动的审核记录将显示在结果列表中。</span><span class="sxs-lookup"><span data-stu-id="a23ec-133">Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
      
   5. <span data-ttu-id="a23ec-134">单击"</span><span class="sxs-lookup"><span data-stu-id="a23ec-134">Click</span></span>   ![搜索按钮](../media/SearchButton.PNG)  <span data-ttu-id="a23ec-136">使用搜索条件运行搜索。</span><span class="sxs-lookup"><span data-stu-id="a23ec-136">to run the search using your search criteria.</span></span> <span data-ttu-id="a23ec-137">搜索结果已加载, 并在几分钟后, 它们将显示在 "保管人活动搜索" 页的 "结果" 下。</span><span class="sxs-lookup"><span data-stu-id="a23ec-137">The search results are loaded, and after a few moments they are displayed under Results on the Custodian Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="a23ec-138">步骤 2: 查看审核日志搜索结果</span><span class="sxs-lookup"><span data-stu-id="a23ec-138">Step 2: View the audit log search results</span></span>

<span data-ttu-id="a23ec-139">审核日志搜索的结果将显示在 "保管人审核日志" 页上的 "结果" 下。</span><span class="sxs-lookup"><span data-stu-id="a23ec-139">The results of an audit log search are displayed under Results on the Custodian Audit log page.</span></span> <span data-ttu-id="a23ec-140">最多 5000 (最新) 事件以150个事件为增量显示。</span><span class="sxs-lookup"><span data-stu-id="a23ec-140">A maximum of 5,000 (newest) events are displayed in increments of 150 events.</span></span> <span data-ttu-id="a23ec-141">若要显示更多事件, 可以使用 "结果" 窗格中的滚动条, 也可以按 Shift + End 显示接下来的150事件。</span><span class="sxs-lookup"><span data-stu-id="a23ec-141">To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="a23ec-142">结果中包含有关搜索返回的每个事件的以下信息。</span><span class="sxs-lookup"><span data-stu-id="a23ec-142">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="a23ec-143">**日期**: 事件发生时的日期和时间 (采用 UTC 格式)。</span><span class="sxs-lookup"><span data-stu-id="a23ec-143">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="a23ec-144">**IP 地址**: 记录活动时使用的设备的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="a23ec-144">**IP address**: The IP address of the device that was used when the activity was logged.</span></span> <span data-ttu-id="a23ec-145">IP 地址显示为 IPv4 或 IPv6 地址格式。</span><span class="sxs-lookup"><span data-stu-id="a23ec-145">The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="a23ec-146">**user**: 执行触发事件的操作的用户 (或服务帐户)。</span><span class="sxs-lookup"><span data-stu-id="a23ec-146">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="a23ec-147">**活动**: 用户执行的活动。</span><span class="sxs-lookup"><span data-stu-id="a23ec-147">**Activity**: The activity performed by the user.</span></span> <span data-ttu-id="a23ec-148">此值与您在 "活动" 下拉列表中选择的活动相对应。</span><span class="sxs-lookup"><span data-stu-id="a23ec-148">This value corresponds to the activities that you selected in the Activities drop down list.</span></span> <span data-ttu-id="a23ec-149">对于来自 exchange 管理员审核日志的事件, 此列中的值为 exchange cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a23ec-149">For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="a23ec-150">**Item**: 作为相应活动的结果创建或修改的对象。</span><span class="sxs-lookup"><span data-stu-id="a23ec-150">**Item**: The object that was created or modified as a result of the corresponding activity.</span></span> <span data-ttu-id="a23ec-151">例如, 已查看或修改的文件或已更新的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a23ec-151">For example, the file that was viewed or modified or the user account that was updated.</span></span> <span data-ttu-id="a23ec-152">此列中并非所有活动都具有值。</span><span class="sxs-lookup"><span data-stu-id="a23ec-152">Not all activities have a value in this column.</span></span>

- <span data-ttu-id="a23ec-153">**详细**信息: 活动的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="a23ec-153">**Detail**: Additional detail about an activity.</span></span> <span data-ttu-id="a23ec-154">同样, 并非所有活动都具有值。</span><span class="sxs-lookup"><span data-stu-id="a23ec-154">Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="a23ec-155">步骤 3: 筛选搜索结果</span><span class="sxs-lookup"><span data-stu-id="a23ec-155">Step 3: Filter the search results</span></span>

<span data-ttu-id="a23ec-156">除了排序之外, 您还可以筛选审核日志搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="a23ec-156">In addition to sorting, you can also filter the results of an audit log search.</span></span> <span data-ttu-id="a23ec-157">这可帮助您快速筛选特定用户或活动的结果。</span><span class="sxs-lookup"><span data-stu-id="a23ec-157">This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="a23ec-158">筛选结果:</span><span class="sxs-lookup"><span data-stu-id="a23ec-158">To filter the results:</span></span>

 1. <span data-ttu-id="a23ec-159">创建和运行审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="a23ec-159">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="a23ec-160">显示结果后, 单击 "**筛选结果**"。</span><span class="sxs-lookup"><span data-stu-id="a23ec-160">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="a23ec-161">关键字框显示在每个列标题下。</span><span class="sxs-lookup"><span data-stu-id="a23ec-161">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="a23ec-162">单击列标题下的一个框, 并根据要筛选的列键入一个词或短语。</span><span class="sxs-lookup"><span data-stu-id="a23ec-162">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on.</span></span> <span data-ttu-id="a23ec-163">结果将会动态调整, 以显示与您的筛选器匹配的事件。</span><span class="sxs-lookup"><span data-stu-id="a23ec-163">The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="a23ec-164">若要清除筛选器, 请单击 "筛选器" 框中的 " **X** " 或只单击 "**隐藏筛选**"。</span><span class="sxs-lookup"><span data-stu-id="a23ec-164">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="a23ec-165">将搜索结果导出到文件</span><span class="sxs-lookup"><span data-stu-id="a23ec-165">Export the search results to a file</span></span>

<span data-ttu-id="a23ec-166">您可以将审核日志搜索的结果导出到本地计算机上的逗号分隔值 (CSV) 文件中。</span><span class="sxs-lookup"><span data-stu-id="a23ec-166">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer.</span></span> <span data-ttu-id="a23ec-167">可以在 Microsoft Excel 中打开此文件, 并使用诸如搜索、排序、筛选和拆分单个列 (包含多值单元格) 的多个列中的功能。</span><span class="sxs-lookup"><span data-stu-id="a23ec-167">You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="a23ec-168">运行审核日志搜索, 然后修改搜索条件, 直到获得所需的结果。</span><span class="sxs-lookup"><span data-stu-id="a23ec-168">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="a23ec-169">单击 "导出结果", 然后选择下列选项之一:</span><span class="sxs-lookup"><span data-stu-id="a23ec-169">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="a23ec-170">**保存加载的结果:** 选择此选项以仅导出在 "**保管人审核日志搜索**" 页上的 "**结果**" 下显示的条目。</span><span class="sxs-lookup"><span data-stu-id="a23ec-170">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **Custodian Audit log search** page.</span></span> <span data-ttu-id="a23ec-171">下载的 CSV 文件包含页面上显示的相同列 (和数据) (日期、用户、活动、项和详细信息)。</span><span class="sxs-lookup"><span data-stu-id="a23ec-171">The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details).</span></span> <span data-ttu-id="a23ec-172">包含来自审核日志条目的详细信息的 CSV 文件中包含其他列 (标题**更详细**)。</span><span class="sxs-lookup"><span data-stu-id="a23ec-172">An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry.</span></span> <span data-ttu-id="a23ec-173">因为您要导出的结果与在审核日志搜索页面上加载 (和查看) 的结果相同, 所以最多可以导出5000个条目。</span><span class="sxs-lookup"><span data-stu-id="a23ec-173">Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="a23ec-174">**下载所有结果:** 选择此选项可导出符合搜索条件的 Office 365 审核日志中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="a23ec-174">**Download all results:** Choose this option to export all entries from the Office 365 audit log that meet the search criteria.</span></span> <span data-ttu-id="a23ec-175">对于大型搜索结果集, 选择此选项可从审核日志中下载所有条目, 除了可在**保管人审核日志**搜索页面上显示的5000结果。</span><span class="sxs-lookup"><span data-stu-id="a23ec-175">For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **Custodian Audit log** search page.</span></span> <span data-ttu-id="a23ec-176">此选项将从审核日志中将原始数据下载到 CSV 文件, 并包含来自名为 AuditData 的列中的审核日志条目的其他信息。</span><span class="sxs-lookup"><span data-stu-id="a23ec-176">This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData.</span></span> <span data-ttu-id="a23ec-177">如果选择此导出选项, 可能需要较长时间下载文件, 因为如果选择其他选项, 文件可能会比下载的文件大得多。</span><span class="sxs-lookup"><span data-stu-id="a23ec-177">It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="a23ec-178">您可以从单个审核日志搜索中最多将50000个条目下载到 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="a23ec-178">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="a23ec-179">如果将50000条目下载到 CSV 文件中, 您可能会假定有超过50000个事件满足搜索条件。</span><span class="sxs-lookup"><span data-stu-id="a23ec-179">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="a23ec-180">若要导出超过此限制, 请尝试使用日期范围来减少审核日志条目的数量。</span><span class="sxs-lookup"><span data-stu-id="a23ec-180">To export more than this limit, try using a date range to reduce the number of audit log entries.</span></span> <span data-ttu-id="a23ec-181">您可能需要运行包含较小日期范围的多个搜索以导出50000个以上的条目。</span><span class="sxs-lookup"><span data-stu-id="a23ec-181">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="a23ec-182">选择 "导出" 选项后, 将在窗口底部显示一条消息, 提示您打开 CSV 文件, 将其保存到 "下载" 文件夹中, 或将其保存到特定文件夹中</span><span class="sxs-lookup"><span data-stu-id="a23ec-182">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="a23ec-183">有关查看、筛选或导出审核日志搜索结果的详细信息, 请参阅[在 Office 365 安全 & 合规中心中搜索审核日志](../search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="a23ec-183">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Office 365 Security & Compliance Center](../search-the-audit-log-in-security-and-compliance.md).</span></span>

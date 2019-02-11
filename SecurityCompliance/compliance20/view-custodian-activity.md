---
title: 查看管理员审核活动
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 34e3fe207cf440c5992cdba7186e919a3968db22
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706143"
---
# <a name="view-custodian-audit-activity"></a><span data-ttu-id="b9f7a-102">查看管理员审核活动</span><span class="sxs-lookup"><span data-stu-id="b9f7a-102">View custodian audit activity</span></span>

<span data-ttu-id="b9f7a-p101">是否要查找是否用户查看特定文档或清除其邮箱中的项目？高级电子数据展示 （预览） 现在与安全 & 合规中心的现有审核日志搜索工具集成。使用此嵌入的体验，您可以使用高级电子数据展示 （预览） Custodian 管理工具便于您调查通过轻松地访问并在您的案例管理员搜索活动。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p101">Need to find if a user viewed a specific document or purged an item from their mailbox? Advanced eDiscovery (Preview) is now integrated with the existing audit log search tool in the Security & Compliance Center. Using this embedded experience, you can use the Advanced eDiscovery (Preview) Custodian Management tool to facilitate your investigation by easily accessing and searching the activity for custodians within your case.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b9f7a-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="b9f7a-106">Before you begin</span></span>

<span data-ttu-id="b9f7a-p102">您必须分配仅查看审核日志或审核日志角色在 Exchange Online 要搜索的 Office 365 审核日志。默认情况下，这些角色分配给的合规性管理和在 Exchange 管理中心中的权限页上的 Organization Management 角色组。若要使用户能够搜索的最小的权限级别的高级电子数据展示 （预览） 审核日志，可以在 Exchange Online 中创建自定义角色组、 添加仅查看审核日志或审核日志角色中，然后将用户添加新角色星号的成员oup。有关详细信息，请参阅 Exchange Online 中的管理角色组。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p102">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log. By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center. To give a user the ability to search the Advanced eDiscovery (Preview) audit log with the minimum level of privileges, you can create a custom role group in Exchange Online, add the View-Only Audit Logs or Audit Logs role, and then add the user as a member of the new role group. For more information, see Manage role groups in Exchange Online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9f7a-p103">如果您在安全 & 合规中心的权限页上的仅查看审核日志或审核日志角色分配用户，他们也不能以搜索的 Office 365 审核日志。您必须分配 Exchange Online 中的权限。这是因为基础 cmdlet 用于搜索的审核日志是 Exchange Online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p103">If you assign a user the View-Only Audit Logs or Audit Logs role on the Permissions page in the Security & Compliance Center, they won't be able to search the Office 365 audit log. You have to assign the permissions in Exchange Online. This is because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet.</span></span>

## <a name="step-1-create-an-advanced-ediscovery-preview-audit-log-search"></a><span data-ttu-id="b9f7a-114">步骤 1： 创建高级电子数据展示 （预览） 审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="b9f7a-114">Step 1: Create an Advanced eDiscovery (Preview) audit log search</span></span>

   1. <span data-ttu-id="b9f7a-115">从**安全 & 合规性中心 > 高级电子数据展示 (Preview)** 中选择现有用例。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-115">Select an existing case from the **Security & Compliance Center > Advanced eDiscovery (Preview)**.</span></span>
   
   2. <span data-ttu-id="b9f7a-116">导航到**管理员**选项卡，然后选择管理员。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-116">Navigate to the **Custodians** tab and select a custodian.</span></span>
   
   3. <span data-ttu-id="b9f7a-117">选中管理员后，从详细信息面板中单击**查看 Custodian 活动**。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-117">Once you have selected a custodian, click **View Custodian Activity** from the details panel.</span></span>
   
   4. <span data-ttu-id="b9f7a-118">配置以下搜索条件：</span><span class="sxs-lookup"><span data-stu-id="b9f7a-118">Configure the following search criteria:</span></span>
      
      <span data-ttu-id="b9f7a-p104">a.**活动**-单击下拉列表以显示您可以搜索活动。运行搜索后，将显示仅所选活动的审核记录。选择**显示所有活动的结果**将显示满足其他搜索条件的所有活动的结果。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p104">a. **Activities** - Click the drop-down list to display the activities that you can search for. After you run the search, only the audit records for the selected activities are displayed. Selecting **Show results for all activities** will display results for all activities that meet the other search criteria.</span></span>
      
      <span data-ttu-id="b9f7a-p105">b.**开始日期和结束日期**-选择要显示在该时间段内发生的事件日期和时间范围。默认情况下，选中最近七天。以协调世界时 (UTC) 格式显示日期和时间。您可以指定的最大的日期范围是一年。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p105">b. **Start date and End date** - Select a date and time range to display the events that occurred within that period. The last seven days are selected by default. The date and time are presented in Coordinated Universal Time (UTC) format. The maximum date range that you can specify is one year.</span></span>
      
      <span data-ttu-id="b9f7a-p106">c.**管理员**-单击在此框，然后选择特定的管理员，以显示搜索结果。通过在此框中选择的用户执行所选活动审核记录显示在结果列表中。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p106">c. **Custodians** - Click in this box and then select a specific custodian to display search results for. Audit records for the selected activity performed by the users you select in this box are displayed in the list of results.</span></span>
    
    1. <span data-ttu-id="b9f7a-p107">单击**搜索**以运行搜索使用您的搜索条件。加载搜索结果，并在片刻后被显示在结果 Custodian 活动搜索页面上。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p107">Click **Search** to run the search using your search criteria. The search results are loaded, and after a few moments they are displayed under Results on the Custodian Activities search page.</span></span> 

## <a name="step-2-view-the-audit-log-search-results"></a><span data-ttu-id="b9f7a-133">步骤 2： 查看审核日志搜索结果</span><span class="sxs-lookup"><span data-stu-id="b9f7a-133">Step 2: View the audit log search results</span></span>

<span data-ttu-id="b9f7a-p108">在结果下管理员审核日志页上显示审核日志搜索的结果。增量为 150 事件显示最多 5000 个 （最新） 的事件。要显示多个事件可以在结果窗格中使用滚动条，或您可以通过按 Shift + End 显示下一步 150 事件。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p108">The results of an audit log search are displayed under Results on the Custodian Audit log page. A maximum of 5,000 (newest) events are displayed in increments of 150 events. To display more events you can use the scroll bar in the Results pane or you can press Shift + End to display the next 150 events.</span></span>

<span data-ttu-id="b9f7a-137">结果包含以下有关搜索返回的每个事件的信息。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-137">The results contain the following information about each event returned by the search.</span></span>
- <span data-ttu-id="b9f7a-138">**日期**： 的日期和时间 （采用 UTC 格式） 时事件发生。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-138">**Date**: The date and time (in UTC format) when the event occurred.</span></span>

- <span data-ttu-id="b9f7a-p109">**IP 地址**： 活动是否已记录时所使用的设备的 IP 地址。IP 地址被显示在 IPv4 或 IPv6 地址格式。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p109">**IP address**: The IP address of the device that was used when the activity was logged. The IP address is displayed in either an IPv4 or IPv6 address format.</span></span>

- <span data-ttu-id="b9f7a-141">**用户**： 用户 （或服务帐户） 执行触发该事件的操作的人员。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-141">**User**: The user (or service account) who performed the action that triggered the event.</span></span>

- <span data-ttu-id="b9f7a-p110">**活动**： 执行用户的活动。此值对应于您在活动下拉列表中选择的活动。Exchange 管理员审核日志中的事件，此列中的值是 Exchange cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p110">**Activity**: The activity performed by the user. This value corresponds to the activities that you selected in the Activities drop down list. For an event from the Exchange admin audit log, the value in this column is an Exchange cmdlet.</span></span>

- <span data-ttu-id="b9f7a-p111">**项目**： 创建或修改相应的活动由于的对象。例如，查看或修改的文件或已更新的用户帐户。并非所有活动都具有此列中的值。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p111">**Item**: The object that was created or modified as a result of the corresponding activity. For example, the file that was viewed or modified or the user account that was updated. Not all activities have a value in this column.</span></span>

- <span data-ttu-id="b9f7a-p112">**详细信息**： 有关活动的其他详细信息。同样，并非所有活动将都具有的值。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p112">**Detail**: Additional detail about an activity. Again, not all activities will have a value.</span></span>

## <a name="step-3-filter-the-search-results"></a><span data-ttu-id="b9f7a-150">步骤 3： 筛选搜索结果</span><span class="sxs-lookup"><span data-stu-id="b9f7a-150">Step 3: Filter the search results</span></span>

<span data-ttu-id="b9f7a-p113">除了排序，您还可以筛选审核日志搜索的结果。这可以帮助您快速筛选特定用户或活动的结果。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p113">In addition to sorting, you can also filter the results of an audit log search. This can help you quickly filter the results for a specific user or activity.</span></span> 

<span data-ttu-id="b9f7a-153">若要筛选结果：</span><span class="sxs-lookup"><span data-stu-id="b9f7a-153">To filter the results:</span></span>

 1. <span data-ttu-id="b9f7a-154">创建和运行审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-154">Create and run an audit log search.</span></span>
  
2. <span data-ttu-id="b9f7a-155">结果显示后，单击**筛选结果**。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-155">When the results are displayed, click **Filter results**.</span></span>
 
3. <span data-ttu-id="b9f7a-156">关键字框都显示在每个列标题下。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-156">Keyword boxes are displayed under each column header.</span></span>
  
4. <span data-ttu-id="b9f7a-p114">单击其中一个框列标题下，键入的字词或短语，具体取决于您要筛选的列。结果将动态重新调整以显示与筛选器匹配的事件。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p114">Click one of the boxes under a column header and type a word or phrase, depending on the column you're filtering on. The results will dynamically readjust to display the events that match your filter.</span></span>
  
5. <span data-ttu-id="b9f7a-159">若要清除筛选器，请单击筛选器框中的**X** ，或只需单击**隐藏筛选**。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-159">To clear a filter, click the **X** in the filter box or just click **Hide filtering**.</span></span>

## <a name="export-the-search-results-to-a-file"></a><span data-ttu-id="b9f7a-160">将搜索结果导出到文件</span><span class="sxs-lookup"><span data-stu-id="b9f7a-160">Export the search results to a file</span></span>

<span data-ttu-id="b9f7a-p115">您可以到本地计算机上的逗号分隔的值 (CSV) 文件导出审核日志搜索的结果。您可以在 Microsoft Excel 中打开此文件并用功能，如搜索、 排序、 筛选和拆分单列 （它包含的多值单元格） 到多个列。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p115">You can export the results of an audit log search to a comma separated value (CSV) file on your local computer. You can open this file in Microsoft Excel and use features such as search, sorting, filtering, and splitting a single column (that contains multi-value cells) into multiple columns.</span></span>

1. <span data-ttu-id="b9f7a-163">运行审核日志搜索，，然后再修订的搜索条件，直到您拥有所需的结果。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-163">Run an audit log search, and then revise the search criteria until you have the desired results.</span></span>
  
2. <span data-ttu-id="b9f7a-164">单击导出结果，然后选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="b9f7a-164">Click Export results and select one of the following options:</span></span>

    - <span data-ttu-id="b9f7a-p116">**保存加载结果：** 选择此选项可导出仅都显示在**结果**下，在**管理员审核日志搜索**页的项。下载的 CSV 文件包含相同列 （和数据） 显示在上 （日期、 用户、 活动、 项目和详细信息）。包含审核日志条目的详细信息的 CSV 文件中包含其他列 （名为**详细**）。您正在导出已加载 （且可查看） 相同的结果导出审核日志搜索页上，最多 5,000 项。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p116">**Save loaded results:** Choose this option to export only the entries that are displayed under **Results** on the **Custodian Audit log search** page. The CSV file that is downloaded contains the same columns (and data) displayed on the page (Date, User, Activity, Item, and Details). An additional column (titled **More**) is included in the CSV file that contains more information from the audit log entry. Because you're exporting the same results that are loaded (and viewable) on the Audit log search page, a maximum of 5,000 entries are exported.</span></span>
        
    - <span data-ttu-id="b9f7a-p117">**下载所有结果：** 选择此选项可导出符合搜索条件的 Office 365 审核日志中的所有条目。搜索结果的一大组，选择此选项，除了可以显示在**管理员审核日志**搜索页的 5,000 结果审核日志中下载的所有条目。此选项将中审核日志中下载的原始数据到 CSV 文件，并包含名为 AuditData 的列中的审核日志条目的其他信息。可能需要长下载文件，如果您选择此导出选项，因为文件可能比下载，如果您选择其他选项的一个大得多。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p117">**Download all results:** Choose this option to export all entries from the Office 365 audit log that meet the search criteria. For a large set of search results, choose this option to download all entries from the audit log in addition to the 5,000 results that can be displayed on the **Custodian Audit log** search page. This option will download the raw data from the audit log to a CSV file, and contains additional information from the audit log entry in a column named AuditData. It may take longer to download the file if you choose this export option because the file may be much larger than the one that's downloaded if you choose the other option.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="b9f7a-p118">您可以从单个审核日志搜索到 CSV 文件下载最多 50,000 条目。如果 50,000 条目下载到 CSV 文件中，您可能可以假定有超过 50,000 个的满足搜索条件的事件。若要导出超过此限制，请尝试使用日期范围减少审核日志条目的数量。您可能需要使用较小要导出超过 50,000 个条目的日期范围运行多个搜索。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-p118">You can download a maximum of 50,000 entries to a CSV file from a single audit log search. If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria. To export more than this limit, try using a date range to reduce the number of audit log entries. You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>
        

3. <span data-ttu-id="b9f7a-177">选择导出选项后，在提示您打开 CSV 文件，将其保存到下载文件夹中，或将其保存到特定文件夹的窗口的底部显示一条消息</span><span class="sxs-lookup"><span data-stu-id="b9f7a-177">After you select an export option, a message is displayed at the bottom of the window that prompts you to open the CSV file, save it to the Downloads folder, or save it to a specific folder</span></span>

<span data-ttu-id="b9f7a-178">查看有关的详细信息，筛选或导出审核日志搜索结果，请参阅[审核日志在 Office 365 安全性 & 合规中心的搜索](../search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="b9f7a-178">For more information about viewing, filtering, or exporting audit log search results, see [Search the audit log in the Office 365 Security & Compliance Center](../search-the-audit-log-in-security-and-compliance.md).</span></span>
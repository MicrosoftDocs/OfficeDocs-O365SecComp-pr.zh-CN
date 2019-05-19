---
title: 导出内容搜索报告
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: 除了在 Office 365 的 Security & 合规性中心中导出内容搜索的实际结果, 您只需导出搜索结果报告即可。 报告包含搜索结果摘要和文档, 其中包含有关要导出的每个项目的详细信息。
ms.openlocfilehash: 8e33a7ba236e0890fc5985aa9a00cba904a40793
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154604"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="0e122-104">导出内容搜索报告</span><span class="sxs-lookup"><span data-stu-id="0e122-104">Export a Content Search report</span></span>

<span data-ttu-id="0e122-105">而不是从 Security & 合规性中心 (和从与电子数据展示事例关联的内容搜索) 的内容搜索中导出完整的搜索结果集, 您只需导出在导出搜索时生成的相同报告即可。引起.</span><span class="sxs-lookup"><span data-stu-id="0e122-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="0e122-106">导出报表时, 它会下载到与内容搜索同名的文件夹中, 但附加在 *_ReportsOnly*中。</span><span class="sxs-lookup"><span data-stu-id="0e122-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  .</span></span> <span data-ttu-id="0e122-107">例如, 如果内容搜索名为*ContosoCase0815* , 则会将报告下载到名为*ContosoCase0815_ReportsOnly*的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0e122-107">For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  .</span></span> <span data-ttu-id="0e122-108">有关报告中包含的文档的列表, 请参阅[报告中包含的内容](#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="0e122-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0e122-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="0e122-109">Before you begin</span></span>

- <span data-ttu-id="0e122-110">若要导出内容搜索报告, 您必须在安全 & 合规性中心中分配合规性搜索管理角色。</span><span class="sxs-lookup"><span data-stu-id="0e122-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="0e122-111">此角色分配给内置电子数据展示管理器和组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="0e122-111">This role is assigned to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="0e122-112">它没有默认分配至组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="0e122-112">It isn't assigned by default to the Organization Management role group.</span></span> <span data-ttu-id="0e122-113">有关详细信息, 请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="0e122-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="0e122-114">导出报表时, 数据临时存储在 Microsoft 云中的唯一 Windows Azure 存储区域中, 然后将其下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="0e122-114">When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="0e122-115">确保您的组织可以连接到 Azure 中的终结点, \*\* \*即 blob.core.windows.net\*\* (通配符代表导出的唯一标识符)。</span><span class="sxs-lookup"><span data-stu-id="0e122-115">Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="0e122-116">搜索结果数据在创建后两周从 Azure 存储区域中删除。</span><span class="sxs-lookup"><span data-stu-id="0e122-116">The search results data is deleted from the Azure storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="0e122-117">用于导出搜索结果的计算机必须满足以下系统要求：</span><span class="sxs-lookup"><span data-stu-id="0e122-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="0e122-118">32 位或 64 位版本的 Windows 7 和更高版本</span><span class="sxs-lookup"><span data-stu-id="0e122-118">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="0e122-119">Microsoft .NET Framework 4。7</span><span class="sxs-lookup"><span data-stu-id="0e122-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="0e122-120">支持的浏览器：</span><span class="sxs-lookup"><span data-stu-id="0e122-120">A supported browser:</span></span>
    
    - <span data-ttu-id="0e122-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0e122-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="0e122-122">或</span><span class="sxs-lookup"><span data-stu-id="0e122-122">or</span></span>
    
    - <span data-ttu-id="0e122-123">Microsoft Internet Explorer 10 及更高版本</span><span class="sxs-lookup"><span data-stu-id="0e122-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="0e122-124">**注意:** Microsoft 不会为 ClickOnce 应用程序制造第三方扩展或加载项。</span><span class="sxs-lookup"><span data-stu-id="0e122-124">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="0e122-125">使用不受支持的浏览器导出搜索结果, 但不支持第三方分机或加载项。</span><span class="sxs-lookup"><span data-stu-id="0e122-125">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 

- <span data-ttu-id="0e122-126">如果内容搜索返回的结果的估计总大小超过 20&nbsp;TB, 则导出报告将失败。</span><span class="sxs-lookup"><span data-stu-id="0e122-126">If the estimated total size of the results returned by a Content Search exceeds 20&nbsp;TB, exporting the report will fail.</span></span> <span data-ttu-id="0e122-127">若要成功导出报告, 请尝试缩小范围并重新运行搜索, 以使结果的估计大小小于 20&nbsp;TB。</span><span class="sxs-lookup"><span data-stu-id="0e122-127">To successfully export the report, try to narrow the scope and re-run the search so the estimated size of the results is less than 20&nbsp;TB.</span></span>

- <span data-ttu-id="0e122-128">导出内容搜索报告会对同时运行的最大导出数和单个用户可以运行的最大导出数进行计数。</span><span class="sxs-lookup"><span data-stu-id="0e122-128">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="0e122-129">有关导出限制的详细信息, 请参阅[导出内容搜索结果](export-search-results.md#export-limits)。</span><span class="sxs-lookup"><span data-stu-id="0e122-129">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="0e122-130">生成和下载内容搜索报告</span><span class="sxs-lookup"><span data-stu-id="0e122-130">Generate and download a Content Search report</span></span>

<span data-ttu-id="0e122-131">生成和下载内容搜索报告的步骤与实际导出搜索结果非常相似。</span><span class="sxs-lookup"><span data-stu-id="0e122-131">The steps to generate and download a Content Search report are very similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="0e122-132">步骤 1: 生成要导出的报告</span><span class="sxs-lookup"><span data-stu-id="0e122-132">Step 1: Generate the report for export</span></span>

<span data-ttu-id="0e122-133">第一步是准备要下载到计算机导出的报告。</span><span class="sxs-lookup"><span data-stu-id="0e122-133">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="0e122-134">在报告中, 报告文档将上载到 Microsoft 云中的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="0e122-134">When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="0e122-135">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="0e122-135">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="0e122-136">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0e122-136">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="0e122-137">在安全 & 合规性中心的左侧窗格中, 单击 "**搜索** \> **内容搜索**"。</span><span class="sxs-lookup"><span data-stu-id="0e122-137">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="0e122-138">在 "**内容搜索**" 页上, 选择 "搜索"。</span><span class="sxs-lookup"><span data-stu-id="0e122-138">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="0e122-139">在详细信息窗格中的 "**将报告导出到计算机**" 下, 单击 "**生成报告**"。</span><span class="sxs-lookup"><span data-stu-id="0e122-139">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e122-140">如果搜索结果超过 7 天，将提示你更新搜索结果。</span><span class="sxs-lookup"><span data-stu-id="0e122-140">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="0e122-141">如果发生这种情况, 请取消导出, 在 "详细信息" 窗格中单击 "**更新搜索结果**" 以选择搜索, 然后在结果更新后再次启动报告导出。</span><span class="sxs-lookup"><span data-stu-id="0e122-141">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="0e122-142">在 "**导出报告**" 页上的 "**从搜索中包含这些项目**" 下, 选择下列选项之一:</span><span class="sxs-lookup"><span data-stu-id="0e122-142">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="0e122-143">仅导出索引项</span><span class="sxs-lookup"><span data-stu-id="0e122-143">Export only indexed items</span></span>
    
    - <span data-ttu-id="0e122-144">导出索引和未编制索引项</span><span class="sxs-lookup"><span data-stu-id="0e122-144">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="0e122-145">仅导出未编制索引项</span><span class="sxs-lookup"><span data-stu-id="0e122-145">Export only unindexed items</span></span>
    
    <span data-ttu-id="0e122-146">有关未编制索引的项目的详细信息, 请参阅[内容搜索中的部分索引项目](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="0e122-146">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="0e122-147">选择包括所有版本的 SharePoint 文档的搜索统计信息。</span><span class="sxs-lookup"><span data-stu-id="0e122-147">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="0e122-148">仅当搜索的内容源包括 SharePoint 或 OneDrive for Business 网站时, 才会显示此选项。</span><span class="sxs-lookup"><span data-stu-id="0e122-148">This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="0e122-149">单击 "**生成报告**"。</span><span class="sxs-lookup"><span data-stu-id="0e122-149">Click **Generate report**.</span></span>
    
    <span data-ttu-id="0e122-150">搜索结果报告已准备好下载, 这意味着将报告文档上载到 Microsoft 云中的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="0e122-150">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud.</span></span> <span data-ttu-id="0e122-151">当报告准备好下载时, 将在详细信息窗格中的 "**将报告导出到计算机**" 下显示 "**下载报告**" 链接。</span><span class="sxs-lookup"><span data-stu-id="0e122-151">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0e122-152">您还可以导出与电子数据展示事例相关联的内容搜索的报告。</span><span class="sxs-lookup"><span data-stu-id="0e122-152">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="0e122-153">若要执行此操作, 请转到**电子数据展示** \> **电子数据展示**, 选择一个](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)事例, 然后单击 "**编辑** ![编辑图标"。</span><span class="sxs-lookup"><span data-stu-id="0e122-153">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="0e122-154">在 "**搜索**" 页上, 选择 "搜索", 然后单击 "**导出** ![导出](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \>搜索结果" 图标 "**导出报告**"。</span><span class="sxs-lookup"><span data-stu-id="0e122-154">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="0e122-155">步骤 2: 下载报告</span><span class="sxs-lookup"><span data-stu-id="0e122-155">Step 2: Download the report</span></span>

<span data-ttu-id="0e122-156">下一步是将报告从 Azure 存储区域下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="0e122-156">The next step is to download the report from the Azure storage area to your local computer.</span></span>
  
1. <span data-ttu-id="0e122-157">在为其生成报告的搜索的详细信息窗格中, 在 "**将报告导出到计算机**" 下, 单击 "**下载报告**"。</span><span class="sxs-lookup"><span data-stu-id="0e122-157">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="0e122-158">将显示 "**下载报告**" 页, 其中包含有关报告的以下信息, 即将其下载到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="0e122-158">The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="0e122-159">将下载的项的数目。</span><span class="sxs-lookup"><span data-stu-id="0e122-159">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="0e122-160">将下载的项的预计总大小。</span><span class="sxs-lookup"><span data-stu-id="0e122-160">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="0e122-161">是否导出索引或未编制索引。</span><span class="sxs-lookup"><span data-stu-id="0e122-161">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="0e122-162">未编制索引项是可以识别格式的项目，出于其他原因被加密或未编入索引。</span><span class="sxs-lookup"><span data-stu-id="0e122-162">Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="0e122-163">SharePoint 文档版本是否将被下载。</span><span class="sxs-lookup"><span data-stu-id="0e122-163">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="0e122-164">报告导出过程的状态。</span><span class="sxs-lookup"><span data-stu-id="0e122-164">The status of the report export process.</span></span> <span data-ttu-id="0e122-165">即使报表准备尚未完成, 也可以开始下载报告。</span><span class="sxs-lookup"><span data-stu-id="0e122-165">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="0e122-166">在“**导出密钥**”下，单击“**复制到剪贴板**”。</span><span class="sxs-lookup"><span data-stu-id="0e122-166">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="0e122-167">您将在步骤5中使用此项下载报告。</span><span class="sxs-lookup"><span data-stu-id="0e122-167">You will use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0e122-168">由于任何人都可以安装和启动电子数据展示导出工具, 然后使用此密钥下载搜索报告, 因此请务必采取预防措施来保护此项, 就像保护密码或其他与安全相关的信息一样。</span><span class="sxs-lookup"><span data-stu-id="0e122-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="0e122-169">单击 "**下载报告**"。</span><span class="sxs-lookup"><span data-stu-id="0e122-169">Click **Download report**.</span></span>
    
4. <span data-ttu-id="0e122-170">如果系统提示您安装**MicrosoftOffice 365 电子数据展示导出工具**, 请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="0e122-170">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="0e122-171">在“电子数据展示导出工具”\*\*\*\* 中，将你在步骤 2 中复制的导出密钥粘贴在相应的框中。</span><span class="sxs-lookup"><span data-stu-id="0e122-171">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="0e122-172">单击 "**浏览**" 以指定要下载报告的位置。</span><span class="sxs-lookup"><span data-stu-id="0e122-172">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="0e122-173">单击\*\*\*\*“启动”将搜索结果下载到计算机。</span><span class="sxs-lookup"><span data-stu-id="0e122-173">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="0e122-174">**电子数据展示工具**显示有关导出过程的状态信息，包括要下载的剩余项的估计数量（和大小）。</span><span class="sxs-lookup"><span data-stu-id="0e122-174">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="0e122-175">导出过程完成后, 可以在文件的下载位置访问这些文件。</span><span class="sxs-lookup"><span data-stu-id="0e122-175">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0e122-176">您可以下载与电子数据展示事例相关联的内容搜索的报告。</span><span class="sxs-lookup"><span data-stu-id="0e122-176">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="0e122-177">若要执行此操作, 请转到**电子数据展示** \> **电子数据展示**, 选择一个](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)事例, 然后单击 "**编辑** ![编辑图标"。</span><span class="sxs-lookup"><span data-stu-id="0e122-177">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="0e122-178">在 "**导出**" 页上, 选择报告导出, 然后单击 "详细信息" 窗格中的 "**下载报告**"。</span><span class="sxs-lookup"><span data-stu-id="0e122-178">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="0e122-179">报告中包含的内容</span><span class="sxs-lookup"><span data-stu-id="0e122-179">What's included in the report</span></span>

<span data-ttu-id="0e122-180">生成和导出有关内容搜索结果的报告时, 将下载以下文档:</span><span class="sxs-lookup"><span data-stu-id="0e122-180">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="0e122-181">**导出摘要**-包含导出摘要的 Excel 文档。</span><span class="sxs-lookup"><span data-stu-id="0e122-181">**Export Summary** - An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="0e122-182">其中包括以下信息: 已搜索的内容源的数量、每个内容位置的搜索结果数、估计的项目数、要导出的实际项目数, 以及项目的估计和实际大小将导出的。</span><span class="sxs-lookup"><span data-stu-id="0e122-182">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0e122-183">如果在导出报表时包含未编制索引的项目, 未编制索引的项目数将包含在估计的搜索结果总数和已下载的搜索结果总数 (如果您要导出搜索结果) 中列出的导出摘要报告。</span><span class="sxs-lookup"><span data-stu-id="0e122-183">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="0e122-184">换言之, 要下载的项目总数等于估计结果的总数和未编制索引项目总数的总数。</span><span class="sxs-lookup"><span data-stu-id="0e122-184">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="0e122-185">**清单**-包含搜索结果中包含的每个项目的相关信息的清单文件 (XML 格式)。</span><span class="sxs-lookup"><span data-stu-id="0e122-185">**Manifest** - A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="0e122-186">**结果**-包含一行的 Excel 文档, 其中包含有关将随搜索结果导出的每个索引项的信息。</span><span class="sxs-lookup"><span data-stu-id="0e122-186">**Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="0e122-187">对于电子邮件, 结果日志包含有关每封邮件的信息, 其中包括:</span><span class="sxs-lookup"><span data-stu-id="0e122-187">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="0e122-188">邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。</span><span class="sxs-lookup"><span data-stu-id="0e122-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="0e122-189">发送或接收邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="0e122-189">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="0e122-190">邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="0e122-190">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="0e122-191">邮件的发件人和收件人。</span><span class="sxs-lookup"><span data-stu-id="0e122-191">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="0e122-192">对于 SharePoint 和 OneDrive for business 网站中的文档, 结果日志包含有关每个文档的信息, 包括:</span><span class="sxs-lookup"><span data-stu-id="0e122-192">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="0e122-193">文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="0e122-193">The URL for the document.</span></span>
    
  - <span data-ttu-id="0e122-194">文档所在的网站集的 URL 。</span><span class="sxs-lookup"><span data-stu-id="0e122-194">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="0e122-195">上次修改文档的日期。</span><span class="sxs-lookup"><span data-stu-id="0e122-195">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="0e122-196">文档的名称（位于结果日志中的主题列）。</span><span class="sxs-lookup"><span data-stu-id="0e122-196">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e122-197">**结果**报告中的行数应等于要下载的搜索结果的总数减去未**编制索引的项目**报告中列出的总项目数。</span><span class="sxs-lookup"><span data-stu-id="0e122-197">The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="0e122-198">未**编制索引的项目**-包含搜索结果中将包含的任何未编制索引项目的相关信息的 Excel 文档。</span><span class="sxs-lookup"><span data-stu-id="0e122-198">**Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results.</span></span> <span data-ttu-id="0e122-199">如果在生成搜索结果报告时未包含未编制索引的项目, 则仍将下载此报告, 但会将其保留为空。</span><span class="sxs-lookup"><span data-stu-id="0e122-199">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>

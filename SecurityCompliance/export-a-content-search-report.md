---
title: 导出内容搜索报告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: 而不是实际的 Office 365 安全性内容的搜索结果导出&amp;合规性中心，可以仅导出搜索结果报告。报告中包含搜索结果以及包含有关每个项目将导出的详细信息的文档的摘要。
ms.openlocfilehash: e15c6550d58701abe9b268455deca0aef60265fb
ms.sourcegitcommit: 1bc36cd57ab1604f057e2b5d336cf1893ba00125
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2018
ms.locfileid: "27283138"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="838c4-104">导出内容搜索报告</span><span class="sxs-lookup"><span data-stu-id="838c4-104">Export a Content Search report</span></span>

<span data-ttu-id="838c4-105">而不是导出整套搜索结果从 Office 365 安全性内容搜索&amp;合规性中心 （以及从与电子数据展示事例相关联的内容搜索），您只可以导出的同一个报告生成时您导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="838c4-105">Instead of exporting the full set of search results from a Content Search in the Office 365 Security &amp; Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="838c4-p102">导出报表时，它是将其下载到具有同名内容的搜索，但与 *_ReportsOnly*追加的文件夹。例如，如果内容搜索名为*ContosoCase0815* ，然后报告被下载到一个名为*ContosoCase0815_ReportsOnly*文件夹。报表中包含的文档的列表，请参阅[报表中包含的内容](#whats-included-in-the-report)。</span><span class="sxs-lookup"><span data-stu-id="838c4-p102">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  . For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  . For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="838c4-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="838c4-109">Before you begin</span></span>

- <span data-ttu-id="838c4-p103">若要导出内容的搜索报表，您必须在 Office 365 安全性合规性搜索管理角色分配&amp;合规性中心。此角色分配给内置电子数据展示管理器和组织管理角色组。它不是默认情况下分配给组织管理角色组。有关详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="838c4-p103">To export a Content Search report, you have to be assigned the Compliance Search management role in the Office 365 Security &amp; Compliance Center. This role is assigned to the built-in eDiscovery Manager and Organization Management role groups. It isn't assigned by default to the Organization Management role group. For more information, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="838c4-p104">导出报表时，数据暂时存储在 Microsoft 云的唯一的 Windows Azure 存储区之前其下载到本地计算机。确保您的组织可以连接到 Azure，即中的终结点**\*。 blob.core.windows.net** （通配符表示导出的唯一标识符）。搜索结果数据从 Azure 存储区创建后两周删除。</span><span class="sxs-lookup"><span data-stu-id="838c4-p104">When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer. Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export). The search results data is deleted from the Azure storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="838c4-117">用于导出搜索结果的计算机必须满足以下系统要求：</span><span class="sxs-lookup"><span data-stu-id="838c4-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="838c4-118">32 位或 64 位版本的 Windows 7 和更高版本</span><span class="sxs-lookup"><span data-stu-id="838c4-118">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="838c4-119">Microsoft.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="838c4-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="838c4-120">支持的浏览器：</span><span class="sxs-lookup"><span data-stu-id="838c4-120">A supported browser:</span></span>
    
    - <span data-ttu-id="838c4-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="838c4-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="838c4-122">或</span><span class="sxs-lookup"><span data-stu-id="838c4-122">or</span></span>
    
    - <span data-ttu-id="838c4-123">Microsoft Internet Explorer 10 和更高版本</span><span class="sxs-lookup"><span data-stu-id="838c4-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="838c4-p105">**注意：** Microsoft 不制造第三方扩展或 ClickOnce 应用程序加载项。导出搜索结果不受支持的浏览器使用第三方扩展或加载项中不受支持。</span><span class="sxs-lookup"><span data-stu-id="838c4-p105">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 

- <span data-ttu-id="838c4-p106">如果内容搜索返回的结果的估计总大小超过 20&nbsp;TB，导出报表将失败。若要成功导出该报表，请尝试缩小范围，并重新运行搜索，因此结果的估计的大小是小于 20&nbsp;TB。</span><span class="sxs-lookup"><span data-stu-id="838c4-p106">If the estimated total size of the results returned by a Content Search exceeds 20&nbsp;TB, exporting the report will fail. To successfully export the report, try to narrow the scope and re-run the search so the estimated size of the results is less than 20&nbsp;TB.</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="838c4-128">生成并下载内容的搜索报告</span><span class="sxs-lookup"><span data-stu-id="838c4-128">Generate and download a Content Search report</span></span>

<span data-ttu-id="838c4-129">生成和下载的内容搜索报表的步骤是非常类似于实际导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="838c4-129">The steps to generate and download a Content Search report are very similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="838c4-130">步骤 1： 生成导出的报告</span><span class="sxs-lookup"><span data-stu-id="838c4-130">Step 1: Generate the report for export</span></span>

<span data-ttu-id="838c4-p107">第一步是准备报表下载到您计算机导出。当您报表，报表文档上载到 microsoft Azure 存储区时云。</span><span class="sxs-lookup"><span data-stu-id="838c4-p107">The first step is to prepare the report for downloading to your computer exporting. When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="838c4-133">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="838c4-133">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="838c4-134">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="838c4-134">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="838c4-135">在安全与合规中心的左侧窗格中，单击“搜索和调查”\*\*\*\*\>\*\*\*\*“内容搜索”。</span><span class="sxs-lookup"><span data-stu-id="838c4-135">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="838c4-136">在**内容搜索**页上，选择搜索。</span><span class="sxs-lookup"><span data-stu-id="838c4-136">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="838c4-137">在详细信息窗格中，在**导出到的计算机上的报告**，下单击**生成报表**。</span><span class="sxs-lookup"><span data-stu-id="838c4-137">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="838c4-p108">如果搜索结果不超过 7 天，系统会提示您更新搜索结果。如果发生这种情况，取消导出单击**更新搜索结果**在所选的搜索的详细信息窗格中，然后在结果更新后重新启动报表导出。</span><span class="sxs-lookup"><span data-stu-id="838c4-p108">If the results for a search are older than 7 days, you are prompted to update the search results. If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="838c4-140">在**将报表导出**页上的在**包括中搜索这些项目**，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="838c4-140">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="838c4-141">仅导出索引项</span><span class="sxs-lookup"><span data-stu-id="838c4-141">Export only indexed items</span></span>
    
    - <span data-ttu-id="838c4-142">导出索引和未编制索引项</span><span class="sxs-lookup"><span data-stu-id="838c4-142">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="838c4-143">仅导出未编制索引项</span><span class="sxs-lookup"><span data-stu-id="838c4-143">Export only unindexed items</span></span>
    
    <span data-ttu-id="838c4-144">有关未编制索引的项目的详细信息，请参阅[部分索引内容的搜索功能中的项目](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="838c4-144">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="838c4-p109">选择要包含的所有版本的 SharePoint 文档的搜索统计信息。此选项仅会显示搜索的内容源业务网站包括 SharePoint 或 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="838c4-p109">Choose to include search statistics for all versions of SharePoint documents. This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="838c4-147">单击**生成报告**。</span><span class="sxs-lookup"><span data-stu-id="838c4-147">Click **Generate report**.</span></span>
    
    <span data-ttu-id="838c4-p110">搜索结果报告随时下载，这意味着报表文档将上载到 Microsoft 云中的 Azure 存储区。供下载报表时，**下载报告**链接详细信息窗格中显示在**导出到的计算机上的报告**下。</span><span class="sxs-lookup"><span data-stu-id="838c4-p110">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud. When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="838c4-p111">此外可以将报表导出为与电子数据展示事例相关联的内容搜索。若要执行此操作，请转到**搜索&amp;调查** \> **电子数据展示**，选择种情况下，然后单击**编辑**![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。在**搜索**页上，选择搜索，，然后单击**导出**![导出搜索结果图标](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **将报表导出**。</span><span class="sxs-lookup"><span data-stu-id="838c4-p111">You can also export a report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="838c4-153">步骤 2： 下载报告</span><span class="sxs-lookup"><span data-stu-id="838c4-153">Step 2: Download the report</span></span>

<span data-ttu-id="838c4-154">下一步是到本地计算机从 Azure 存储区下载报告。</span><span class="sxs-lookup"><span data-stu-id="838c4-154">The next step is to download the report from the Azure storage area to your local computer.</span></span>
  
1. <span data-ttu-id="838c4-155">在生成的报告，在**导出到的计算机上的报告**下的搜索的详细信息窗格中，单击**下载报告**。</span><span class="sxs-lookup"><span data-stu-id="838c4-155">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="838c4-156">**下载报告**页上显示，其中包含以下信息后报告下载到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="838c4-156">The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="838c4-157">将下载的项的数目。</span><span class="sxs-lookup"><span data-stu-id="838c4-157">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="838c4-158">将下载的项的预计总大小。</span><span class="sxs-lookup"><span data-stu-id="838c4-158">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="838c4-p112">将导出编制索引还是未编制索引。未编制索引的项目是具有识别的格式、 进行加密，或出于其他原因无法编制索引项。</span><span class="sxs-lookup"><span data-stu-id="838c4-p112">Whether indexed or unindexed will be exported. Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="838c4-161">SharePoint 文档版本是否将被下载。</span><span class="sxs-lookup"><span data-stu-id="838c4-161">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="838c4-p113">报表导出过程的状态。您可以开始下载报告，即使准备的林中的报表不完整。</span><span class="sxs-lookup"><span data-stu-id="838c4-p113">The status of the report export process. You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="838c4-p114">在**导出密钥**下单击**复制到剪贴板**。您将在步骤 5 中使用此项，若要下载报告。</span><span class="sxs-lookup"><span data-stu-id="838c4-p114">Under **Export key**, click **Copy to clipboard**. You will use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="838c4-166">因为任何人都可以安装和启动电子数据展示导出工具，然后使用此密钥下载搜索报告，请确保采取预防措施来防止此密钥像将保护密码或其他安全相关的信息。</span><span class="sxs-lookup"><span data-stu-id="838c4-166">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="838c4-167">单击**下载报告**。</span><span class="sxs-lookup"><span data-stu-id="838c4-167">Click **Download report**.</span></span>
    
4. <span data-ttu-id="838c4-168">如果提示您安装**MicrosoftOffice 365 电子数据展示导出工具**，请单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="838c4-168">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="838c4-169">在**电子数据展示导出工具**中，粘贴您在步骤 2 中相应的框中复制的导出密钥。</span><span class="sxs-lookup"><span data-stu-id="838c4-169">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="838c4-170">单击**浏览**以指定要从中下载报告的位置。</span><span class="sxs-lookup"><span data-stu-id="838c4-170">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="838c4-171">单击“**开始**”将搜索结果下载到计算机。</span><span class="sxs-lookup"><span data-stu-id="838c4-171">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="838c4-p115">**电子数据展示导出工具**显示有关导出过程，包括估计的数量 （和大小） 的剩余的项的下载状态信息。在导出过程完成后，您可以访问他们已下载的位置中的文件。</span><span class="sxs-lookup"><span data-stu-id="838c4-p115">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="838c4-p116">与电子数据展示事例相关联的内容搜索，您可以下载报告。若要执行此操作，请转到**搜索&amp;调查** \> **电子数据展示**，选择种情况下，然后单击**编辑**![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。在**导出**页上，选择报表导出，，然后单击详细信息窗格中的**下载报告**。</span><span class="sxs-lookup"><span data-stu-id="838c4-p116">You can download the report for a Content Search that's associated with an eDiscovery case. To do this, go to **Search &amp; investigation** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif). On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="838c4-177">在报表中包含的内容</span><span class="sxs-lookup"><span data-stu-id="838c4-177">What's included in the report</span></span>

<span data-ttu-id="838c4-178">时生成，导出有关的内容的搜索结果的报告，请下载以下文档：</span><span class="sxs-lookup"><span data-stu-id="838c4-178">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="838c4-p117">**摘要导出**-Excel 文档包含在导出操作的摘要。这包括信息，如搜索的内容源的数量，从每个内容的位置，项的估计的数目，将导出的项目的实际数目的搜索结果数和项目的估计和实际大小将导出的。</span><span class="sxs-lookup"><span data-stu-id="838c4-p117">**Export Summary** - An Excel document that contains a summary of the export. This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="838c4-p118">如果包含未编制索引的项目导出报表时，未编制索引的项目数是包含在估计的搜索结果的总数和下载的搜索结果 （如果您打算将搜索结果导出） 中列出的总数导出摘要报告。换句话说，将下载的项目总数等于估计结果总数和未编制索引的项目总数。</span><span class="sxs-lookup"><span data-stu-id="838c4-p118">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report. In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="838c4-183">**清单**-包含有关包含在搜索结果中每个项目的信息的清单文件 （以 XML 格式）。</span><span class="sxs-lookup"><span data-stu-id="838c4-183">**Manifest** - A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="838c4-p119">**结果**-包含信息将与搜索结果导出每个索引项的行的 Excel 文档。为电子邮件，结果日志包含有关每封邮件的信息包括：</span><span class="sxs-lookup"><span data-stu-id="838c4-p119">**Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results. For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="838c4-186">邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。</span><span class="sxs-lookup"><span data-stu-id="838c4-186">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="838c4-187">发送或接收邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="838c4-187">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="838c4-188">邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="838c4-188">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="838c4-189">邮件的发件人和收件人。</span><span class="sxs-lookup"><span data-stu-id="838c4-189">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="838c4-190">对于来自 SharePoint 和 OneDrive for Business 站点的文档，结果日志包含有关每个文档的信息包括：</span><span class="sxs-lookup"><span data-stu-id="838c4-190">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="838c4-191">文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="838c4-191">The URL for the document.</span></span>
    
  - <span data-ttu-id="838c4-192">文档所在的网站集的 URL 。</span><span class="sxs-lookup"><span data-stu-id="838c4-192">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="838c4-193">上次修改文档的日期。</span><span class="sxs-lookup"><span data-stu-id="838c4-193">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="838c4-194">文档的名称（位于结果日志中的主题列）。</span><span class="sxs-lookup"><span data-stu-id="838c4-194">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="838c4-195">在**结果**报告中的行数应等于值**未编制索引的项目**报告中列出的项目总数减会下载的搜索结果的总数。</span><span class="sxs-lookup"><span data-stu-id="838c4-195">The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="838c4-p120">**未编制索引的项目**-Excel 文档包含有关将搜索结果中包含任何未编制索引项的信息。如果生成搜索结果报告时，不包括未编制索引的项目，此报告将仍下载，但将为空。</span><span class="sxs-lookup"><span data-stu-id="838c4-p120">**Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results. If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>

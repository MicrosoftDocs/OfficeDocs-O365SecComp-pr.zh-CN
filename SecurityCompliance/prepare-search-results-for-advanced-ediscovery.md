---
title: 为 Office 365 高级电子数据展示准备搜索结果
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: 了解如何在 Office 365 安全&amp;合规中心中准备内容搜索的结果, 以使用高级电子数据展示工具进行进一步分析。
ms.openlocfilehash: 52573169692c2457e51898f9f36d2c586c7e7a4b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30212672"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a><span data-ttu-id="6a3d8-103">为 Office 365 高级电子数据展示准备搜索结果</span><span class="sxs-lookup"><span data-stu-id="6a3d8-103">Prepare search results for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="6a3d8-p101">成功运行与 office 365 安全&amp;合规中心中的电子数据展示事例相关联的搜索后, 可以使用 office 365 高级电子数据展示进一步分析搜索结果, 这样您可以分析大型、非结构化数据集和减少与法律案件相关的数据量。高级电子数据展示功能包括:</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p101">After a search that's associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center is successfully run, you can prepare the search results for further analysis with Office 365 Advanced eDiscovery, which lets you analyze large, unstructured data sets and reduce the amount of data that's relevant to a legal case. Advanced eDiscovery features include:</span></span>
  
- <span data-ttu-id="6a3d8-p102">**光学字符识别**-为高级电子数据展示准备搜索结果时, 光学字符识别 (OCR) 功能会自动从图像中提取文本, 并将其包含在加载到中的搜索结果中。高级电子数据展示以进行分析。稀疏文件、电子邮件附件和嵌入图像支持 OCR。这使您可以将高级电子数据展示的文本分析功能 (临近重复项、电子邮件线程、主题和预测编码) 应用于图像文件中的文本内容。高级电子数据展示 OCR 支持图像文件的以下格式:</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p102">**Optical character recognition** - When you prepare search results for Advanced eDiscovery, optical character recognition (OCR) functionality automatically extracts text from images, and includes this with the search results that are loaded in to Advanced eDiscovery for analysis. OCR is supported for loose files, email attachments, and embedded images. This allows you to apply the text analytic capabilities of Advanced eDiscovery (near-duplicates, email threading, themes, and predictive coding) to the text content in image files. Advanced eDiscovery OCR supports the following formats for image files:</span></span>

    - <span data-ttu-id="6a3d8-110">GIF</span><span class="sxs-lookup"><span data-stu-id="6a3d8-110">GIF</span></span>
    - <span data-ttu-id="6a3d8-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="6a3d8-111">JPEG</span></span>
    - <span data-ttu-id="6a3d8-112">.jpg</span><span class="sxs-lookup"><span data-stu-id="6a3d8-112">JPG</span></span>
    - <span data-ttu-id="6a3d8-113">PNG</span><span class="sxs-lookup"><span data-stu-id="6a3d8-113">PNG</span></span>
    - <span data-ttu-id="6a3d8-114">TIFF</span><span class="sxs-lookup"><span data-stu-id="6a3d8-114">TIFF</span></span>
    
- <span data-ttu-id="6a3d8-p103">**接近重复的检测**-使您能够更高效地构建数据审核, 这样一人可以查看一组相似的文档。这有助于防止多个审阅者查看同一文档的不同版本。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p103">**Near-duplicate detection** - Lets you structure your data review more efficiently, so one person reviews a group of similar documents. This helps prevent multiple reviewers from having to view different versions of the same document.</span></span> 
    
- <span data-ttu-id="6a3d8-p104">**电子邮件线程处理**-帮助您标识电子邮件线程中的唯一邮件, 以便只关注每封邮件中的新信息。在电子邮件线索中, 第二封邮件包含第一封邮件。同样, 后续邮件也包含以前的所有邮件。电子邮件线程消除了在电子邮件线程中完整查看每封邮件的需求。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p104">**Email threading** - Helps you identify the unique messages in an email thread so you can focus on only the new information in each message. In an email thread, the second message contains the first message. Likewise, later messages contain all the previous messages. Email threading removes the need to review every message in its entirety in an email thread.</span></span> 
    
- <span data-ttu-id="6a3d8-p105">**主题**-帮助您获得有关数据的有价值的见解, 而不仅仅是关键字搜索统计信息。主题帮助调查通过对相关文档进行分组, 以便您可以在上下文中查看文档。使用主题时, 您可以查看一组文档的相关主题, 确定任何重叠, 然后确定相关数据的各个部分。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p105">**Themes** - Help you get valuable insight about your data beyond just keyword search statistics. Themes help investigations by grouping related documents so you can look at the documents in context. When using themes, you can view the related themes for a set of documents, determine any overlap, and then identify cross-sections of related data.</span></span> 
    
- <span data-ttu-id="6a3d8-p106">**预测编码**-通过允许您在一小组文档上做出决定 (有关是否有相关的信息), 让您对系统进行培训。然后, 高级电子数据展示在分析数据集中的所有文档时应用该学习 (基于您的指导)。根据该学习, 高级电子数据展示会提供相关性排名, 以便您可以根据最可能与案例相关的文档来决定要查看哪些文档。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p106">**Predictive coding** - Lets you train the system on what you're looking for, by allowing you to make decisions (about whether something is relevant or not) on a small set of documents. Advanced eDiscovery then applies that learning (based on your guidance) when analyzing all of the documents in the data set. Based on that learning, Advanced eDiscovery provides a relevance ranking so you can decide which documents to review based on what document are the most likely to be relevant to the case.</span></span> 
    
- <span data-ttu-id="6a3d8-p107">**导出数据以供审阅应用程序**-在完成分析并减小数据集后, 您可以从高级电子数据展示和 Office 365 导出数据。导出包包含一个 CSV 文件, 其中包含导出的内容和分析元数据中的属性。然后, 可以将此导出包导入到电子数据展示审阅应用程序中。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p107">**Exporting data for review applications**  - You can export data from Advanced eDiscovery and Office 365 after you've completed your analysis and reduced the data set. The export package includes a CSV file that contains the properties from the exported content and analytics metadata. This export package can then be imported to an eDiscovery review application.</span></span> 
    
## <a name="before-you-begin"></a><span data-ttu-id="6a3d8-130">准备工作</span><span class="sxs-lookup"><span data-stu-id="6a3d8-130">Before you begin</span></span>

- <span data-ttu-id="6a3d8-p108">若要使用高级电子数据展示分析用户的数据, 必须为用户 (数据管理员) 分配 Office 365 E5 许可证。或者, 可以为具有 Office 365 E1 或 E3 许可证的用户分配高级电子数据展示独立许可证。分配给案例并使用高级电子数据展示分析数据的管理员和合规性监察官不需要 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p108">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="6a3d8-p109">您必须是电子数据展示管理器或 Office 365 安全&amp;合规中心中的电子数据展示管理员才能为高级电子数据展示准备搜索结果。电子数据展示管理器是电子数据展示管理器角色组的成员。电子数据展示管理员也是电子数据展示管理器角色组的成员, 但已分配了其他电子数据展示权限。有关分配电子数据展示管理员权限的说明, 请参阅[Office 365 Security & 合规中心中的电子数据展示事例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的步骤1。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p109">You have to be an eDiscovery Manager or an eDiscovery Administrator in the Office 365 Security &amp; Compliance Center to prepare search results for Advanced eDiscovery. An eDiscovery Manager is a member of the eDiscovery Manager role group. An eDiscovery Administrator is also member of the eDiscovery Manager role group, but has been assigned additional eDiscovery privileges. For instructions about assigning eDiscovery Administrator permissions, see Step 1 in [eDiscovery cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a><span data-ttu-id="6a3d8-138">步骤 1: 为高级电子数据展示准备搜索结果</span><span class="sxs-lookup"><span data-stu-id="6a3d8-138">Step 1: Prepare search results for Advanced eDiscovery</span></span>

<span data-ttu-id="6a3d8-p110">您可以准备与电子数据展示事例相关联的搜索结果。在为高级电子数据展示准备搜索结果时, 数据将上传并临时存储在 Microsoft 云中的唯一 Windows Azure 存储区域中。在这种情况中, OCR 功能会从搜索结果中的图像中提取文本。在[第2步](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery)中, 此文本和其他搜索结果数据将加载到高级电子数据展示的案例中。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p110">You can prepare the results of a search that's associated with an eDiscovery case. When you prepare search results for Advanced eDiscovery, the data is uploaded and temporarily stored in a unique Windows Azure storage area in the Microsoft cloud. It's at this point that the OCR functionality extracts text from images in the search results. In [Step 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), this text and the other search results data is loaded in to the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="6a3d8-143">在安全与合规中心内，依次单击“搜索和调查”\*\*\*\* 和“电子数据展示”\*\*\*\*，以显示组织中的案件集列表。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-143">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="6a3d8-144">在高级电子数据展示中, 单击要为分析准备搜索结果的事例旁边的 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-144">Click **Open** next to the case that you want to prepare search results for analysis in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="6a3d8-145">在该案例的**主页**上, 单击 "**搜索**", 然后选择 "搜索"。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-145">On the **Home** page for the case, click **Search**, and then select the search.</span></span>
    
4. <span data-ttu-id="6a3d8-146">在详细信息窗格中, 在 "**使用高级电子数据展示分析结果**" 下, 单击 "**准备结果以供分析**"。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-146">In the details pane, under **Analyze results with Advanced eDiscovery**, click **Prepare results for analysis**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6a3d8-147">如果搜索结果超过 7 天，将会提示你更新搜索结果。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-147">If the search results are older than 7 days, you will be prompted to update the search results.</span></span> 
  
5. <span data-ttu-id="6a3d8-148">在 "**准备用于分析的结果**" 页上, 执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="6a3d8-148">On the **Prepare results for analysis** page, do the following:</span></span> 
    
    - <span data-ttu-id="6a3d8-149">选择为高级电子数据展示中的分析准备已编制索引的项目、已编制索引和未编制索引的项目或仅索引项目。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-149">Choose to prepare indexed items, indexed and unindexed items, or only unindexed items for analysis in Advanced eDiscovery.</span></span>
    
    - <span data-ttu-id="6a3d8-p111">选择是否包含在 SharePoint 上找到的符合搜索条件的所有版本的文档。仅当搜索的内容源包括网站时, 才会显示此选项。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p111">Choose whether to include all versions of documents found on SharePoint that met the search criteria. This option appears only if the content sources for the search includes sites.</span></span>
    
    - <span data-ttu-id="6a3d8-152">指定在准备过程完成且数据已准备好在高级电子数据展示中进行处理时, 您是否希望向某人发送 (或复制) 通知邮件。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-152">Specify whether you want a notification message sent (or copied) to a person when the preparation process is completed and the data is ready to be processed in Advanced eDiscovery.</span></span>
    
6. <span data-ttu-id="6a3d8-153">单击 "**准备**"。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-153">Click **Prepare**.</span></span>
    
    <span data-ttu-id="6a3d8-154">搜索结果已准备好使用高级电子数据展示进行分析。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-154">The search results are prepared for analysis with Advanced eDiscovery.</span></span>
    
7. <span data-ttu-id="6a3d8-p112">在 "详细信息" 窗格中, 单击 "**检查准备状态**" 以显示有关准备过程的信息。准备过程完成后, 可以转到高级电子数据展示中的案例以处理数据以进行分析。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p112">In the details pane, click **Check preparation status** to display information about the preparation process. When the preparation process is finished, you can go to the case in Advanced eDiscovery to process the data for analysis.</span></span> 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a><span data-ttu-id="6a3d8-157">步骤 2: 将搜索结果数据添加到高级电子数据展示中的事例</span><span class="sxs-lookup"><span data-stu-id="6a3d8-157">Step 2: Add the search results data to the case in Advanced eDiscovery</span></span>
<span data-ttu-id="6a3d8-158"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="6a3d8-158"></span></span>

<span data-ttu-id="6a3d8-p113">准备完成后, 下一步是转到高级电子数据展示, 并将搜索结果数据 (已上载到 Microsoft 云中的 Azure 存储区域) 发送到高级电子数据展示中的情况。如前所述, 若要访问高级电子数据展示, 您必须是安全&amp;合规性中心中的电子数据展示管理员或高级电子数据展示中的管理员。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p113">When the preparation is finished, the next step is to go to Advanced eDiscovery and load the search results data (which have been uploaded to an Azure storage area in the Microsoft cloud ) to the case in Advanced eDiscovery. As previously explained, to access Advanced eDiscovery you have to be an eDiscovery Administrator in the Security &amp; Compliance Center or an administrator in Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a3d8-161">根据电子数据展示搜索结果的大小不同, &amp;安全合规中心中的数据可在高级电子数据展示中添加到事例所需的时间。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-161">The time it takes for the data from the Security &amp; Compliance Center to be available to add to a case in Advanced eDiscovery varies, depending on the size of the results from the eDiscovery search.</span></span> 
  
1. <span data-ttu-id="6a3d8-162">在安全与合规中心内，依次单击“搜索和调查”\*\*\*\* 和“电子数据展示”\*\*\*\*，以显示组织中的案件集列表。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-162">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="6a3d8-163">在高级电子数据展示中, 单击要在其中将数据加载到的事例旁边的 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-163">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="6a3d8-164">在此案件集的“主页”\*\*\*\* 上，单击“高级电子数据展示”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-164">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![单击 "切换到高级电子数据展示" 以在高级电子数据展示中打开事例](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="6a3d8-p114">将显示 "**连接到高级电子数据展示**进度栏"。当您连接到高级电子数据展示时, 会在 "设置" 页上显示一个容器列表。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p114">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![事例显示在高级电子数据展示](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="6a3d8-p115">这些容器代表您在步骤1中的高级电子数据展示中准备进行分析的搜索结果。请注意, 在安全&amp;合规中心的情况下, 容器名称与搜索的名称相同。列表中的容器是您准备的容器。如果其他用户为高级电子数据展示准备了搜索结果, 则相应的容器将不会包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p115">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1. Note that the name of the container has the same name as the search in the case in the Security &amp; Compliance Center. The containers in the list are the ones that you prepared. If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
4. <span data-ttu-id="6a3d8-173">若要在高级电子数据展示中将容器中的搜索结果数据加载到事例中, 请选择一个容器, 然后单击 "**处理**"。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-173">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="6a3d8-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6a3d8-174">Next steps</span></span>

<span data-ttu-id="6a3d8-p116">将电子数据展示搜索的结果添加到事例之后, 下一步是使用高级电子数据展示工具来分析数据, 并确定对特定法律案例做出响应的内容。有关使用高级电子数据展示的信息, 请参阅[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p116">After the results of an eDiscovery search are added to a case, the next step is to use the Advanced eDiscovery tools to analyze the data and identify the content that's responsive to a specific legal case. For information about using Advanced eDiscovery, see [Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="6a3d8-177">更多信息</span><span class="sxs-lookup"><span data-stu-id="6a3d8-177">More information</span></span>

<span data-ttu-id="6a3d8-p117">在准备高级电子数据展示中的分析时, 搜索结果中包含的任何 RMS 加密的电子邮件都将被解密。默认情况下, 将为电子数据展示管理器角色组的成员启用此解密功能。这是因为将 RMS 解密管理角色分配给此角色组。请记住以下有关解密电子邮件的事项:</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p117">Any RMS-encrypted email messages that are included in the search results will be decrypted when you prepare them for analysis in Advanced eDiscovery. This decryption capability is enabled by default for members of the eDiscovery Manager role group. This is because the RMS Decrypt management role is assigned to this role group. Keep the following things in mind about decrypting email messages:</span></span>
  
- <span data-ttu-id="6a3d8-p118">目前, 此解密功能不包括 SharePoint 和 OneDrive for business 网站中的加密内容。导出 RMS 加密的电子邮件时, 只会对其进行解密。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p118">Currently, this decryption capability doesn't include encrypted content from SharePoint and OneDrive for Business sites. Only RMS-encrypted email messages will be decrypted when you export them.</span></span>
    
- <span data-ttu-id="6a3d8-184">如果 RMS 加密的电子邮件包含同样加密的附件 (如文档或其他电子邮件), 则仅对顶级电子邮件进行解密。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-184">If an RMS-encrypted email message has an attachment (such as a document or another email message) that's also encrypted, only the top-level email message will be decrypted.</span></span>
    
- <span data-ttu-id="6a3d8-p119">如果需要防止某人在为高级电子数据展示中的分析准备搜索结果时对受 RMS 加密的邮件进行解密, 则必须创建自定义角色组 (通过复制内置的电子数据展示管理器角色组), 然后删除 RMS从自定义角色组中解密管理角色。然后, 将您不想将邮件解密的人员添加为自定义角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="6a3d8-p119">If you need to prevent someone from decrypting RMS-encrypted messages when preparing search results for analysis in Advanced eDiscovery, you'll have to create a custom role group (by copying the built-in eDiscovery Manager role group) and then remove the RMS Decrypt management role from the custom role group. Then add the person who you don't want to decrypt messages as a member of the custom role group.</span></span>

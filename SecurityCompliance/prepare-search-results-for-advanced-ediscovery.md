---
title: 为 Office 365 高级电子数据展示准备搜索结果
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/10/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: 了解如何准备 Office 365 安全性内容的搜索结果的&amp;的进一步分析高级电子数据展示工具的合规性中心。
ms.openlocfilehash: 4e5668c88d62e99f7a5f40ed2e17f4687a7e9adb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526074"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a><span data-ttu-id="4eff8-103">为 Office 365 高级电子数据展示准备搜索结果</span><span class="sxs-lookup"><span data-stu-id="4eff8-103">Prepare search results for Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="4eff8-p101">与 Office 365 安全性电子数据展示事例相关联的搜索后&amp;成功运行合规性中心，您可以准备进一步分析 Office 365 高级电子数据展示，该对话框可以分析大型，搜索结果非结构化的数据设置，并降低与法律案件相关的数据量。高级电子数据展示功能包括：</span><span class="sxs-lookup"><span data-stu-id="4eff8-p101">After a search that's associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center is successfully run, you can prepare the search results for further analysis with Office 365 Advanced eDiscovery, which lets you analyze large, unstructured data sets and reduce the amount of data that's relevant to a legal case. Advanced eDiscovery features include:</span></span>
  
- <span data-ttu-id="4eff8-p102">**光学字符识别**-自动准备搜索结果的高级电子数据展示，光学字符识别 (OCR) 功能时从图像中提取文本和这包括与加载到的搜索结果高级电子数据展示进行分析。OCR 松散文件支持、 电子邮件附件，并嵌入图像。这样，您将高级电子数据展示 （近乎重复项、 电子邮件线程、 主题和预测编码） 的文本分析功能应用于图像文件中的文本内容。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p102">**Optical character recognition** - When you prepare search results for Advanced eDiscovery, optical character recognition (OCR) functionality automatically extracts text from images, and includes this with the search results that are loaded in to Advanced eDiscovery for analysis. OCR is supported for loose files, email attachments, and embedded images. This allows you to apply the text analytic capabilities of Advanced eDiscovery (near-duplicates, email threading, themes, and predictive coding) to the text content in image files.</span></span> 
    
- <span data-ttu-id="4eff8-p103">**近乎重复检测**-允许您更有效地结构您数据进行审阅以便人审阅类似的文档的组。这有助于防止多个审阅者不必查看不同版本的同一文档。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p103">**Near-duplicate detection** - Lets you structure your data review more efficiently, so one person reviews a group of similar documents. This helps prevent multiple reviewers from having to view different versions of the same document.</span></span> 
    
- <span data-ttu-id="4eff8-p104">**电子邮件线程**-可帮助您确定电子邮件主题中的唯一消息，使您可以集中在仅每条消息中的新信息。在电子邮件线程，第二个消息包含第一条消息。同样，更高版本的消息将包含所有前面的消息。电子邮件线程删除需要查看整个电子邮件线程中的每条消息。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p104">**Email threading** - Helps you identify the unique messages in an email thread so you can focus on only the new information in each message. In an email thread, the second message contains the first message. Likewise, later messages contain all the previous messages. Email threading removes the need to review every message in its entirety in an email thread.</span></span> 
    
- <span data-ttu-id="4eff8-p105">**主题**-帮助您获得有关超出刚刚关键字搜索统计数据的价值。主题帮助调查由分组相关的文档，以便您可以查看的上下文中的文档。时使用主题，您可以查看相关的主题的一组文档、 确定任何重叠，然后确定的相关数据横截面。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p105">**Themes** - Help you get valuable insight about your data beyond just keyword search statistics. Themes help investigations by grouping related documents so you can look at the documents in context. When using themes, you can view the related themes for a set of documents, determine any overlap, and then identify cross-sections of related data.</span></span> 
    
- <span data-ttu-id="4eff8-p106">**预测编码**-允许您培训上正在查找的内容，从而可以决定 （关于是否内容是相关或不） 的系统上的小型文档集。高级电子数据展示然后应用该学习 （基于您指南） 分析的所有数据集中文档时。基于该学习，高级电子数据展示提供相关性排名，以便您可以确定哪些文档查看基于哪些文档是最有可能与案例相关。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p106">**Predictive coding** - Lets you train the system on what you're looking for, by allowing you to make decisions (about whether something is relevant or not) on a small set of documents. Advanced eDiscovery then applies that learning (based on your guidance) when analyzing all of the documents in the data set. Based on that learning, Advanced eDiscovery provides a relevance ranking so you can decide which documents to review based on what document are the most likely to be relevant to the case.</span></span> 
    
- <span data-ttu-id="4eff8-p107">**导出的数据查看应用程序**的已完成您的分析，并降低数据集后，您可以从高级电子数据展示和 Office 365 导出数据。导出包包括 CSV 文件包含来自导出的内容并分析元数据属性。此导出包然后导入到电子数据展示查看应用程序。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p107">**Exporting data for review applications**  - You can export data from Advanced eDiscovery and Office 365 after you've completed your analysis and reduced the data set. The export package includes a CSV file that contains the properties from the exported content and analytics metadata. This export package can then be imported to an eDiscovery review application.</span></span> 
    
## <a name="before-you-begin"></a><span data-ttu-id="4eff8-124">准备工作</span><span class="sxs-lookup"><span data-stu-id="4eff8-124">Before you begin</span></span>

- <span data-ttu-id="4eff8-p108">若要分析使用高级电子数据展示的用户的数据，用户 (数据的 custodian) 必须分配的 Office 365 E5 许可证。此外，可使用 Office 365 E1 或 E3 许可证的用户分配的高级电子数据展示独立许可证。管理员和合规部主管分配给情况下，并使用高级电子数据展示以分析数据不需要 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p108">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="4eff8-p109">您必须是电子数据展示中管理器或 Office 365 安全性的管理员电子数据展示&amp;合规性中心以准备高级电子数据展示搜索结果。电子数据展示中管理器是电子数据展示管理员角色组的成员。电子数据展示管理员也是电子数据展示管理员角色组的成员，但已分配其他电子数据展示权限。有关分配管理员权限的电子数据展示的说明，请参阅[电子数据展示](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)的情况下，在 Office 365 安全性和合规性中心的步骤 1。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p109">You have to be an eDiscovery Manager or an eDiscovery Administrator in the Office 365 Security &amp; Compliance Center to prepare search results for Advanced eDiscovery. An eDiscovery Manager is a member of the eDiscovery Manager role group. An eDiscovery Administrator is also member of the eDiscovery Manager role group, but has been assigned additional eDiscovery privileges. For instructions about assigning eDiscovery Administrator permissions, see Step 1 in [eDiscovery cases in the Office 365 Security & Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a><span data-ttu-id="4eff8-132">步骤 1： 准备搜索结果的高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="4eff8-132">Step 1: Prepare search results for Advanced eDiscovery</span></span>

<span data-ttu-id="4eff8-p110">您可以准备电子数据展示事例与相关联的搜索的结果。当您准备高级电子数据展示搜索结果时，并将数据上载临时存储在 Microsoft 云的唯一的 Windows Azure 存储区。此时是 OCR 功能从搜索结果中的图像中提取文本。在[步骤 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery)、 此文本和其他搜索结果数据中加载到中高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p110">You can prepare the results of a search that's associated with an eDiscovery case. When you prepare search results for Advanced eDiscovery, the data is uploaded and temporarily stored in a unique Windows Azure storage area in the Microsoft cloud. It's at this point that the OCR functionality extracts text from images in the search results. In [Step 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery), this text and the other search results data is loaded in to the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="4eff8-137">安全中&amp;合规性中心，单击**搜索&amp;调查** \> **电子数据展示**案例列表中的显示您的组织中。</span><span class="sxs-lookup"><span data-stu-id="4eff8-137">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="4eff8-138">旁边的情况下，您想要准备分析高级电子数据展示中搜索结果中，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="4eff8-138">Click **Open** next to the case that you want to prepare search results for analysis in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="4eff8-139">在**主页**页为用例，单击**搜索**，然后选择搜索。</span><span class="sxs-lookup"><span data-stu-id="4eff8-139">On the **Home** page for the case, click **Search**, and then select the search.</span></span>
    
4. <span data-ttu-id="4eff8-140">在详细信息窗格中，在**与高级电子数据展示的分析结果**，单击**准备进行分析的结果**。</span><span class="sxs-lookup"><span data-stu-id="4eff8-140">In the details pane, under **Analyze results with Advanced eDiscovery**, click **Prepare results for analysis**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4eff8-141">如果搜索结果超过 7 天，将会提示你更新搜索结果。</span><span class="sxs-lookup"><span data-stu-id="4eff8-141">If the search results are older than 7 days, you will be prompted to update the search results.</span></span> 
  
5. <span data-ttu-id="4eff8-142">在**准备进行分析的结果**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4eff8-142">On the **Prepare results for analysis** page, do the following:</span></span> 
    
    - <span data-ttu-id="4eff8-143">选择高级电子数据展示中的分析准备索引和未编制索引的项目或仅未编制索引的项目的索引的项。</span><span class="sxs-lookup"><span data-stu-id="4eff8-143">Choose to prepare indexed items, indexed and unindexed items, or only unindexed items for analysis in Advanced eDiscovery.</span></span>
    
    - <span data-ttu-id="4eff8-p111">选择是否包括找到符合搜索条件的 SharePoint 上的文档的所有版本。此选项仅会显示搜索的内容源包括网站。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p111">Choose whether to include all versions of documents found on SharePoint that met the search criteria. This option appears only if the content sources for the search includes sites.</span></span>
    
    - <span data-ttu-id="4eff8-146">指定是否希望一封通知邮件发送 （或复制） 到个人准备过程完成和已准备好高级电子数据展示中处理数据。</span><span class="sxs-lookup"><span data-stu-id="4eff8-146">Specify whether you want a notification message sent (or copied) to a person when the preparation process is completed and the data is ready to be processed in Advanced eDiscovery.</span></span>
    
6. <span data-ttu-id="4eff8-147">单击**准备**。</span><span class="sxs-lookup"><span data-stu-id="4eff8-147">Click **Prepare**.</span></span>
    
    <span data-ttu-id="4eff8-148">搜索结果准备好使用高级电子数据展示的分析。</span><span class="sxs-lookup"><span data-stu-id="4eff8-148">The search results are prepared for analysis with Advanced eDiscovery.</span></span>
    
7. <span data-ttu-id="4eff8-p112">在细节窗格中，单击**检查准备状态**以显示有关准备过程的信息。准备过程完成后，您可以转到这种情况在高级电子数据展示处理分析的数据。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p112">In the details pane, click **Check preparation status** to display information about the preparation process. When the preparation process is finished, you can go to the case in Advanced eDiscovery to process the data for analysis.</span></span> 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a><span data-ttu-id="4eff8-151">步骤 2： 将搜索结果数据添加到在高级电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="4eff8-151">Step 2: Add the search results data to the case in Advanced eDiscovery</span></span>
<span data-ttu-id="4eff8-152"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="4eff8-152"></span></span>

<span data-ttu-id="4eff8-p113">完成准备工作后下, 一步是转到高级电子数据展示并加载与案例高级电子数据展示中搜索结果数据 （其中已上载到云中 Microsoft Azure 存储区）。如上文所述，访问您必须是电子数据展示管理员安全中的高级电子数据展示&amp;合规性中心或高级电子数据展示中的管理员。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p113">When the preparation is finished, the next step is to go to Advanced eDiscovery and load the search results data (which have been uploaded to an Azure storage area in the Microsoft cloud ) to the case in Advanced eDiscovery. As previously explained, to access Advanced eDiscovery you have to be an eDiscovery Administrator in the Security &amp; Compliance Center or an administrator in Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4eff8-155">花费的时间的数据从安全&amp;合规性中心，以将其添加到在高级电子数据展示事例有所不同，具体取决于电子数据展示搜索的结果的大小。</span><span class="sxs-lookup"><span data-stu-id="4eff8-155">The time it takes for the data from the Security &amp; Compliance Center to be available to add to a case in Advanced eDiscovery varies, depending on the size of the results from the eDiscovery search.</span></span> 
  
1. <span data-ttu-id="4eff8-156">安全中&amp;合规性中心，单击**搜索&amp;调查** \> **电子数据展示**案例列表中的显示您的组织中。</span><span class="sxs-lookup"><span data-stu-id="4eff8-156">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="4eff8-157">要加载中的数据到高级电子数据展示案例旁边，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="4eff8-157">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="4eff8-158">在**主页**页为用例，单击**高级电子数据展示**。</span><span class="sxs-lookup"><span data-stu-id="4eff8-158">On the **Home** page for the case, click **Advanced eDiscovery**.</span></span> 
    
    ![单击切换高级电子数据展示高级电子数据展示中打开这种情况](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="4eff8-p114">显示**连接到高级电子数据展示**进度栏。当您连接到高级电子数据展示时，将用例设置页上显示容器的列表。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p114">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![用例显示在高级电子数据展示](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="4eff8-p115">这些容器表示您在步骤 1 中的高级电子数据展示中的分析准备好的搜索结果。请注意，容器的名称在的情况下，安全中有相同的名称搜索&amp;合规性中心。在容器列表中的准备。如果其他用户准备高级电子数据展示搜索结果，在相应的容器不会包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p115">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1. Note that the name of the container has the same name as the search in the case in the Security &amp; Compliance Center. The containers in the list are the ones that you prepared. If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
4. <span data-ttu-id="4eff8-167">若要从容器中加载搜索结果数据，与在高级电子数据展示案例，选择容器，然后单击**过程**。</span><span class="sxs-lookup"><span data-stu-id="4eff8-167">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="4eff8-168">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4eff8-168">Next steps</span></span>

<span data-ttu-id="4eff8-p116">后的结果的电子数据展示搜索被添加到种情况下下, 一步是使用高级电子数据展示工具分析数据，并确定特定法律案件做出迅速响应的内容。有关使用高级电子数据展示的信息，请参阅[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p116">After the results of an eDiscovery search are added to a case, the next step is to use the Advanced eDiscovery tools to analyze the data and identify the content that's responsive to a specific legal case. For information about using Advanced eDiscovery, see [Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="4eff8-171">详细信息</span><span class="sxs-lookup"><span data-stu-id="4eff8-171">More information</span></span>

<span data-ttu-id="4eff8-p117">当准备高级电子数据展示中的分析时，将解密的搜索结果中包含任何 RMS 加密电子邮件。默认情况下，此解密功能启用的电子数据展示管理员角色组的成员。这是因为 RMS 解密管理角色分配给此角色组。注意有关解密邮件以下几点：</span><span class="sxs-lookup"><span data-stu-id="4eff8-p117">Any RMS-encrypted email messages that are included in the search results will be decrypted when you prepare them for analysis in Advanced eDiscovery. This decryption capability is enabled by default for members of the eDiscovery Manager role group. This is because the RMS Decrypt management role is assigned to this role group. Keep the following things in mind about decrypting email messages:</span></span>
  
- <span data-ttu-id="4eff8-p118">当前，此解密功能不包括来自 SharePoint 和 OneDrive for Business 站点加密的内容。当您将其导出时，将解密仅 RMS 加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p118">Currently, this decryption capability doesn't include encrypted content from SharePoint and OneDrive for Business sites. Only RMS-encrypted email messages will be decrypted when you export them.</span></span>
    
- <span data-ttu-id="4eff8-178">如果 RMS 加密电子邮件带有附件 （如文档或另一个电子邮件） 还加密的仅顶级电子邮件将被解密。</span><span class="sxs-lookup"><span data-stu-id="4eff8-178">If an RMS-encrypted email message has an attachment (such as a document or another email message) that's also encrypted, only the top-level email message will be decrypted.</span></span>
    
- <span data-ttu-id="4eff8-p119">如果您需要防止他人解密 RMS 加密的邮件，准备进行分析高级电子数据展示中搜索结果时，您将需要 （通过复制内置电子数据展示管理员角色组） 中创建自定义角色组，然后删除 RMS解密自定义角色组中的管理角色。然后，添加您不想要自定义角色组的成员身份解密消息的人员。</span><span class="sxs-lookup"><span data-stu-id="4eff8-p119">If you need to prevent someone from decrypting RMS-encrypted messages when preparing search results for analysis in Advanced eDiscovery, you'll have to create a custom role group (by copying the built-in eDiscovery Manager role group) and then remove the RMS Decrypt management role from the custom role group. Then add the person who you don't want to decrypt messages as a member of the custom role group.</span></span>

---
title: 在 Office 365 高级电子数据展示中运行流程模块并加载数据
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: '了解如何使用 Office 365 安全性&amp;合规性中心以访问 Office 365 高级电子数据展示和运行进程模块用例。  '
ms.openlocfilehash: 32052bccc37d20c8707a1efb0592f7c93daf3590
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525415"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a><span data-ttu-id="d3861-103">在 Office 365 高级电子数据展示中运行流程模块并加载数据</span><span class="sxs-lookup"><span data-stu-id="d3861-103">Run the Process module and load data in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="d3861-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="d3861-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="d3861-106">本节介绍了高级电子数据展示流程模块的功能。</span><span class="sxs-lookup"><span data-stu-id="d3861-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="d3861-p102">除了文件数据，可以为元数据文件类型、 扩展名、 位置或路径、 创建日期和时间、 作者、 管理员，以及主题，例如加载到高级电子数据展示和每种情况下保存。某些元数据由计算高级电子数据展示，例如，在加载时本机文件。</span><span class="sxs-lookup"><span data-stu-id="d3861-p102">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case. Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="d3861-p103">高级电子数据展示提供系统的元数据值，如近乎重复分组或相关性分数。可以由管理员添加其他元数据，例如文件批注。</span><span class="sxs-lookup"><span data-stu-id="d3861-p103">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores. Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="d3861-111">正在运行的进程</span><span class="sxs-lookup"><span data-stu-id="d3861-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="d3861-p104">批处理号码分配给文件过程中允许的文件的跟踪。批处理号还允许重新处理选项的过程批次的标识。其他筛选器是可用于筛选按批处理编号和会话。</span><span class="sxs-lookup"><span data-stu-id="d3861-p104">Batch numbers are assigned to a file during Process to allow the tracking of files. The batch number also enables identification of Process batches for reprocessing options. Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="d3861-115">执行以下步骤运行过程。</span><span class="sxs-lookup"><span data-stu-id="d3861-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="d3861-116">[打开 Office 365 安全性&amp;合规性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d3861-116">[Open the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="d3861-117">转到**搜索&amp;调查** \> **电子数据展示**，然后单击**转到高级电子数据展示**。</span><span class="sxs-lookup"><span data-stu-id="d3861-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="d3861-118">在高级电子数据展示，在显示的**情况下**页中选择适当的案例，然后单击**转到用例**。</span><span class="sxs-lookup"><span data-stu-id="d3861-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="d3861-119">在**准备** \> **过程** \> **安装程序**，选择一个可用的容器的列表中的容器。</span><span class="sxs-lookup"><span data-stu-id="d3861-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![单击过程以添加到用例的搜索结果](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="d3861-121">如果您想要添加容器作为种子文件或前标记文件，请单击**高级设置...** 。</span><span class="sxs-lookup"><span data-stu-id="d3861-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="d3861-p105">使用种子文件可与低丰富加速培训问题 (通常是 2%或更少)。对于种子文件，建议您选择各种清晰相关文件，并处理有关每个问题 （种子文件太多可能会扭曲相关性结果） 的 20 50 种子。种子文件应由相同将培训问题的人进行审阅。</span><span class="sxs-lookup"><span data-stu-id="d3861-p105">Use seed files to accelerate training for issues with low richness (usually 2%, or less). For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results). Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="d3861-p106">使用预标记的文件自动化相关性培训。您应标记至少 1,500 文件，并保留与非相关文件相关的比例集合添加到相关性相同。这些文件应手动标记，并且您应该确保质量标记中。</span><span class="sxs-lookup"><span data-stu-id="d3861-p106">Use pre-tagged files to automate Relevance training. You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance. These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![处理批处理文件的屏幕快照的高级设置页](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="d3861-129">在**种子**部分中：</span><span class="sxs-lookup"><span data-stu-id="d3861-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="d3861-p107">选择**标记为种子文件**标记为种子文件的容器。您还需要选择将其分配**问题**下拉列表中的每个问题。从**标记**下拉列表中选择**相关**或**不相关**。</span><span class="sxs-lookup"><span data-stu-id="d3861-p107">Choose **Mark as seed files** to mark the container as seed files. You also need choose to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d3861-133">一旦作为**种子**设置文件，您无法将它们标记为**预先标记**。</span><span class="sxs-lookup"><span data-stu-id="d3861-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="d3861-134">在**预先标记的文件**部分中：</span><span class="sxs-lookup"><span data-stu-id="d3861-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="d3861-p108">选择**标记为已标记前文件**标记为前标记文件的容器。您还需要将其分配**问题**下拉列表中的每个问题。从**标记**下拉列表中选择**相关**或**不相关**。</span><span class="sxs-lookup"><span data-stu-id="d3861-p108">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files. You also need to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d3861-138">一旦为**预先标记**设置文件，您无法将它们标记为**种子**。</span><span class="sxs-lookup"><span data-stu-id="d3861-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="d3861-p109">在**电子邮件标签**部分中。处理电子邮件的哪一部分都标记为培养或前已标记的设置。</span><span class="sxs-lookup"><span data-stu-id="d3861-p109">In the **Email tagging** section. set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="d3861-p110">若要开始，请单击**过程**。完成后，将显示处理结果。</span><span class="sxs-lookup"><span data-stu-id="d3861-p110">To begin, click **Process**. When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="d3861-143">（可选）如果您需要将数据源分配给特定的管理员，您可以添加和编辑**管理员**custodian 名称\>**管理员**在**管理**和分配管理员\>**分配**。</span><span class="sxs-lookup"><span data-stu-id="d3861-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="d3861-144">如果您将添加到这种情况，然后您可以重新处理。</span><span class="sxs-lookup"><span data-stu-id="d3861-144">If you add to the case, then you can process again.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d3861-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3861-145">See also</span></span>

[<span data-ttu-id="d3861-146">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="d3861-146">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d3861-147">查看过程模块结果</span><span class="sxs-lookup"><span data-stu-id="d3861-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)


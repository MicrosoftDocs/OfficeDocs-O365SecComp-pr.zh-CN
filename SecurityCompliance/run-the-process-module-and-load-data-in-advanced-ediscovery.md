---
title: 在 Office 365 高级电子数据展示中运行流程模块并加载数据
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: '了解如何使用 office 365 安全&amp;合规中心访问 office 365 高级电子数据展示, 并运行 Process module for a case。  '
ms.openlocfilehash: 95c73c034ed2ffa1c45f9aacd8463c497a842859
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217602"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a><span data-ttu-id="f9175-103">在 Office 365 高级电子数据展示中运行流程模块并加载数据</span><span class="sxs-lookup"><span data-stu-id="f9175-103">Run the Process module and load data in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="f9175-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="f9175-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="f9175-106">本节介绍高级电子数据展示过程模块的功能。</span><span class="sxs-lookup"><span data-stu-id="f9175-106">This section describes the functionality of the Advanced eDiscovery Process module.</span></span> 
  
<span data-ttu-id="f9175-p102">除了文件数据之外, 元数据 (如文件类型、扩展名、位置或路径、创建日期和时间、作者、管理员和主题) 可以加载到高级电子数据展示中并为每个事例保存。有些元数据是由高级电子数据展示计算的, 例如, 在加载本机文件时。</span><span class="sxs-lookup"><span data-stu-id="f9175-p102">In addition to file data, metadata such as file type, extension, location or path, creation date and time, author, custodian, and subject, can be loaded into Advanced eDiscovery and saved for each case. Some metadata is calculated by Advanced eDiscovery, for example, when native files are loaded.</span></span> 
  
<span data-ttu-id="f9175-p103">高级电子数据展示提供系统元数据值, 如接近重复的分组或相关性分数。其他元数据 (如文件批注) 可由管理员添加。</span><span class="sxs-lookup"><span data-stu-id="f9175-p103">Advanced eDiscovery provides system metadata values, such as Near-duplicate groupings or Relevance scores. Other metadata, such as file annotations, can be added by the Administrator.</span></span> 
  
## <a name="running-process"></a><span data-ttu-id="f9175-111">正在运行的进程</span><span class="sxs-lookup"><span data-stu-id="f9175-111">Running Process</span></span>

> [!NOTE]
> <span data-ttu-id="f9175-p104">批处理号在进程中分配给文件以允许跟踪文件。批处理号还允许对处理选项的进程批处理进行标识。可以按批处理号和会话筛选其他筛选器。</span><span class="sxs-lookup"><span data-stu-id="f9175-p104">Batch numbers are assigned to a file during Process to allow the tracking of files. The batch number also enables identification of Process batches for reprocessing options. Additional filters are available for filtering by batch number and sessions.</span></span> 
  
<span data-ttu-id="f9175-115">执行以下步骤以运行进程。</span><span class="sxs-lookup"><span data-stu-id="f9175-115">Perform the following steps to run Process.</span></span>
  
1. <span data-ttu-id="f9175-116">[打开 "Office 365 安全&amp;合规中心"](go-to-the-securitycompliance-center.md) 。</span><span class="sxs-lookup"><span data-stu-id="f9175-116">[Open the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md) .</span></span> 
    
2. <span data-ttu-id="f9175-117">转到**搜索&amp;调查** \> **电子数据展示**, 然后单击 "**转到高级电子数据展示**"。</span><span class="sxs-lookup"><span data-stu-id="f9175-117">Go to **Search &amp; investigation** \> **eDiscovery** and then click **Go to Advanced eDiscovery**.</span></span>
    
3. <span data-ttu-id="f9175-118">在高级电子数据展示中, 在 "显示**事例**" 页面中选择适当的事例, 然后单击 "**转到大小写**"。</span><span class="sxs-lookup"><span data-stu-id="f9175-118">In Advanced eDiscovery, select the appropriate case in the displayed **Cases** page and click **Go to case**.</span></span>
    
4. <span data-ttu-id="f9175-119">在 "**准备** \> **过程** \> **安装**" 中, 从可用容器列表中选择一个容器。</span><span class="sxs-lookup"><span data-stu-id="f9175-119">In **Prepare** \> **Process** \> **Setup**, select a container from the list of available containers.</span></span>
    
    ![单击 "处理" 以将搜索结果添加到案例](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. <span data-ttu-id="f9175-121">如果要将容器添加为 seed 文件或预先加标签的文件, 请单击 "**高级设置"。**</span><span class="sxs-lookup"><span data-stu-id="f9175-121">Click **Advanced settings...** if you want to add the container as seed files or as pre-tagged files.</span></span> 
    
    <span data-ttu-id="f9175-p105">使用种子文件加快丰富程度较低的问题 (通常为 2% 或更少) 的培训。对于种子文件, 建议您选择各种明显相关的文件, 并在每个问题中处理大约20-50 种子 (种子文件太多可能会扭曲相关性结果)。应由将对问题进行培训的同一人审阅种子文件。</span><span class="sxs-lookup"><span data-stu-id="f9175-p105">Use seed files to accelerate training for issues with low richness (usually 2%, or less). For seed files, it is recommended that you select a variety of distinctly relevant files and process about 20-50 seeds per issue (too many seed files can skew Relevance results). Seed files should be reviewed by the same person who will train the issue.</span></span>
    
    <span data-ttu-id="f9175-p106">使用预先加标签的文件以自动进行相关性培训。应标记至少1500个文件, 并将与非相关文件相关的比例与添加到相关性的集合中的比例保持一致。应手动标记这些文件, 并且您应该自信标记质量。</span><span class="sxs-lookup"><span data-stu-id="f9175-p106">Use pre-tagged files to automate Relevance training. You should tag at least 1,500 files, and keep the proportion of relevant to non-relevant files the same as in the collection added to Relevance. These files should be manually tagged, and you should be confident in the quality of tagging.</span></span>
    
    ![用于处理批处理文件的 "高级设置" 页的屏幕截图](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - <span data-ttu-id="f9175-129">在 "**种子**" 部分中:</span><span class="sxs-lookup"><span data-stu-id="f9175-129">In the **Seed** section:</span></span> 
    
    <span data-ttu-id="f9175-p107">选择 "**标记为种子文件**" 以将容器标记为种子文件。您还需要根据问题下拉下拉箭头, 选择为\*\*\*\* 其分配每个问题。从 "**标记**" 下拉选择 "**相关**或**不相关**"。</span><span class="sxs-lookup"><span data-stu-id="f9175-p107">Choose **Mark as seed files** to mark the container as seed files. You also need choose to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f9175-133">将文件设置为**种子**后, 不能将其标记为**预先加标签**的。</span><span class="sxs-lookup"><span data-stu-id="f9175-133">Once you set files as **Seed**, you cannot mark them as **Pre-tagged**.</span></span> 
  
  - <span data-ttu-id="f9175-134">在 "**预加标签的文件**" 部分:</span><span class="sxs-lookup"><span data-stu-id="f9175-134">In the **Pre-tagged files** section:</span></span> 
    
    <span data-ttu-id="f9175-p108">选择 "**标记为预先加加标签的文件**" 以将容器标记为预先加标签的文件。您还需要根据问题下拉下拉项为其\*\*\*\* 分配每个问题。从 "**标记**" 下拉选择 "**相关**或**不相关**"。</span><span class="sxs-lookup"><span data-stu-id="f9175-p108">Choose **Mark as pre-tagged files** to mark the container as pre-tagged files. You also need to assign them per issue from the **For issue** drop-down. Choose either **Relevant** or **Not relevant** from the **Tag** drop-down.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f9175-138">将文件设置为**预先加标签**后, 不能将其标记为**种子**。</span><span class="sxs-lookup"><span data-stu-id="f9175-138">Once you set files as **Pre-tagged**, you cannot mark them as **Seed**.</span></span> 
  
  - <span data-ttu-id="f9175-p109">在 "**电子邮件标签**" 部分。设置已处理的电子邮件的哪一部分将被标记为种子或预先标记。</span><span class="sxs-lookup"><span data-stu-id="f9175-p109">In the **Email tagging** section. set which part of a processed email are to be marked as Seed or Pre-tagged.</span></span> 
    
6. <span data-ttu-id="f9175-p110">若要开始, 请单击 "**处理**"。完成后, 将显示流程结果。</span><span class="sxs-lookup"><span data-stu-id="f9175-p110">To begin, click **Process**. When completed, the Process results are displayed.</span></span>
    
7. <span data-ttu-id="f9175-143">Optional如果需要向特定保管人分配数据源, 可以在**保管人** \>中添加和编辑保管人名称**管理**和分配保管人\*\*\*\* \> **assign**中的保管人。</span><span class="sxs-lookup"><span data-stu-id="f9175-143">(Optional) If you need to assign data sources to a specific custodian, you can add and edit custodian names in **Custodians** \> **Manage** and assign custodians in **Custodians** \> **Assign**.</span></span> 
    
<span data-ttu-id="f9175-144">如果向事例添加, 则可以再次处理。</span><span class="sxs-lookup"><span data-stu-id="f9175-144">If you add to the case, then you can process again.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f9175-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9175-145">See also</span></span>

[<span data-ttu-id="f9175-146">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="f9175-146">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="f9175-147">查看流程模块结果</span><span class="sxs-lookup"><span data-stu-id="f9175-147">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)


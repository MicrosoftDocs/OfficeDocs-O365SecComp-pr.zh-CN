---
title: 查看 Office 365 高级电子数据展示中的分析结果
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: '了解在 Office 365 高级电子数据展示中查看分析过程结果的位置, 包括所显示的任务选项的定义。  '
ms.openlocfilehash: 092daa506316b5eb1ef1f5c466055b29e350dc18
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157854"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="80916-103">查看 Office 365 高级电子数据展示中的分析结果</span><span class="sxs-lookup"><span data-stu-id="80916-103">View Analyze results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="80916-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="80916-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="80916-106">在高级电子数据展示中, 分析过程的进度和结果可在各种显示器中查看, 如下所述。</span><span class="sxs-lookup"><span data-stu-id="80916-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="80916-107">查看分析任务状态</span><span class="sxs-lookup"><span data-stu-id="80916-107">View Analyze task status</span></span>

<span data-ttu-id="80916-108">在**准备\>分析\>结果\>任务状态**中, 状态在分析流程执行期间和之后都会显示。</span><span class="sxs-lookup"><span data-stu-id="80916-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![分析任务状态](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="80916-110">根据所选的选项, 显示的任务可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="80916-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="80916-111">**ND/ET: setup**: 为运行做准备, 例如, 设置运行和用例参数。</span><span class="sxs-lookup"><span data-stu-id="80916-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="80916-112">**Nd/ET: nd 计算**: 处理文件的近乎重复的分析。</span><span class="sxs-lookup"><span data-stu-id="80916-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="80916-113">**ND/ET: ET 计算**: 对整个电子邮件集执行电子邮件线程分析。</span><span class="sxs-lookup"><span data-stu-id="80916-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="80916-114">**ND/ET: 透视和相似性**: 执行透视和文件相似性处理。</span><span class="sxs-lookup"><span data-stu-id="80916-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="80916-115">**ND/ET: 元数据更新**: 最终完成在数据库中的文件上收集的新数据。</span><span class="sxs-lookup"><span data-stu-id="80916-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="80916-116">**主题: 主题计算**: 运行主题分析。</span><span class="sxs-lookup"><span data-stu-id="80916-116">**Themes: themes calculation**: Runs themes analysis.</span></span> <span data-ttu-id="80916-117">(仅在选中时显示。)</span><span class="sxs-lookup"><span data-stu-id="80916-117">(Displayed only if selected.)</span></span>
    
- <span data-ttu-id="80916-118">**任务状态**: 此代码行在任务完成后显示。</span><span class="sxs-lookup"><span data-stu-id="80916-118">**Task status**: This line is displayed after task completion.</span></span> <span data-ttu-id="80916-119">运行任务时, 将显示 "运行持续时间"。</span><span class="sxs-lookup"><span data-stu-id="80916-119">While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="80916-120">邻近重复和电子邮件线程 (ND 和 ED) 的分析结果适用于要处理的文档数。</span><span class="sxs-lookup"><span data-stu-id="80916-120">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed.</span></span> <span data-ttu-id="80916-121">它不包含完全重复的文件。</span><span class="sxs-lookup"><span data-stu-id="80916-121">It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="80916-122">查看临近的重复和电子邮件线程状态</span><span class="sxs-lookup"><span data-stu-id="80916-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="80916-123">**目标**填充结果显示目标填充中的文档数、电子邮件、附件和错误。</span><span class="sxs-lookup"><span data-stu-id="80916-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="80916-124">**文档**结果显示透视次数、唯一的临近重复项和完全重复的文件。</span><span class="sxs-lookup"><span data-stu-id="80916-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="80916-125">**电子**邮件结果显示包含的包含的、包含的减去、唯一的包含副本的数量以及其余的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="80916-125">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages.</span></span> <span data-ttu-id="80916-126">不同类型的电子邮件结果为:</span><span class="sxs-lookup"><span data-stu-id="80916-126">The different types of email results are:</span></span> 
  
- <span data-ttu-id="80916-127">**包括**: 包含电子邮件的电子邮件线程中的终止节点, 并包含该线程的所有以前的历史记录。</span><span class="sxs-lookup"><span data-stu-id="80916-127">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread.</span></span> <span data-ttu-id="80916-128">因此, 审阅者可以安全地重点关注包含的电子邮件, 而无需读取该线程中的前一封邮件。</span><span class="sxs-lookup"><span data-stu-id="80916-128">As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="80916-129">**包含减号**: 如果有一个或多个不同的附件与包含的邮件的父项关联, 则将包含的电子邮件指定为包含的减号。</span><span class="sxs-lookup"><span data-stu-id="80916-129">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message.</span></span> <span data-ttu-id="80916-130">在此上下文中, 术语 "父级" 用于向上的电子邮件线程或该特定包含电子邮件中包含的对话的邮件。</span><span class="sxs-lookup"><span data-stu-id="80916-130">In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email.</span></span> <span data-ttu-id="80916-131">审阅者可以使用包含的减号表示作为信号, 尽管可能不需要查看包含的电子邮件父项的内容, 但查看与包含的路径父项关联的附件可能很有用。</span><span class="sxs-lookup"><span data-stu-id="80916-131">A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="80916-132">**包含副本**: 如果是被标记为包含或包含减号的另一封邮件的副本, 则将包含的电子邮件指定为包含副本。</span><span class="sxs-lookup"><span data-stu-id="80916-132">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus.</span></span> <span data-ttu-id="80916-133">换句话说, 此邮件与另一个包含邮件具有相同的主题和正文, 因此共同驻留在同一节点中。</span><span class="sxs-lookup"><span data-stu-id="80916-133">In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node.</span></span> <span data-ttu-id="80916-134">由于包含副本邮件包含相同的内容, 因此通常可以在审阅过程中跳过它们。</span><span class="sxs-lookup"><span data-stu-id="80916-134">Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="80916-135">**Rest**: 这表示电子邮件不包含任何唯一的内容, 因此不属于上述三个类别中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="80916-135">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories.</span></span> <span data-ttu-id="80916-136">不需要查看这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="80916-136">These email messages don't need to be reviewed.</span></span> <span data-ttu-id="80916-137">如果邮件包含不在后续包含的电子邮件中的附件, 则可能需要审阅附件。</span><span class="sxs-lookup"><span data-stu-id="80916-137">If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed.</span></span> <span data-ttu-id="80916-138">这由线程中的包含负电子邮件的存在指示。</span><span class="sxs-lookup"><span data-stu-id="80916-138">This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="80916-139">**附件**结果将根据此类类型 (唯一和重复) 显示附件数。</span><span class="sxs-lookup"><span data-stu-id="80916-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![近似重复和电子邮件线程](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="80916-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80916-141">See also</span></span>

[<span data-ttu-id="80916-142">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="80916-142">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="80916-143">了解文档相似性</span><span class="sxs-lookup"><span data-stu-id="80916-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="80916-144">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="80916-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="80916-145">设置忽略文本</span><span class="sxs-lookup"><span data-stu-id="80916-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="80916-146">设置分析高级设置</span><span class="sxs-lookup"><span data-stu-id="80916-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)


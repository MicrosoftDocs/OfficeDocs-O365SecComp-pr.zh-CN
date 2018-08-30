---
title: 使用 Office 365 高级电子数据展示实用工具
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: '了解 Office 365 高级电子数据展示，包括案例日志中的实用程序、 清除数据、 处理错误、 修改相关性和透明度分析。  '
ms.openlocfilehash: a68c98dd353971fcaa13fdc6b8e12bcf00c2faf0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524887"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a><span data-ttu-id="a6a9d-103">使用 Office 365 高级电子数据展示实用工具</span><span class="sxs-lookup"><span data-stu-id="a6a9d-103">Use Office 365 Advanced eDiscovery utilities</span></span>

> [!NOTE]
> <span data-ttu-id="a6a9d-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="a6a9d-106">显示和高级电子数据展示中可用的实用程序取决于上下文和用户角色。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="a6a9d-107">案例日志</span><span class="sxs-lookup"><span data-stu-id="a6a9d-107">Case log</span></span>

<span data-ttu-id="a6a9d-p102">案例日志提供应用程序处理活动，可以用于跟踪，疑难解答，并解决错误和警告的详细的列表。日志可以生成和本地存储在主机或服务器，或直接发送到的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p102">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings. The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="a6a9d-p103">日志文件还可以下载到客户端的计算机。客户端下载选项可能需要启用或禁用根据配置和用户角色。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p103">The log file can also be downloaded to the client's computer. The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="a6a9d-112">在菜单栏中，单击**Cogwheel**图标。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="a6a9d-113">在**设置和实用程序\>实用程序**选项卡上，选择**案例日志\>安装**。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="a6a9d-114">选择**日志级别**，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a6a9d-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="a6a9d-p104">**标准**： 包括基本的日志数据。此选项通常是必需的监控，，，否则建议除非应使用。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p104">**Standard**: Includes the basic log data. This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="a6a9d-117">**最少**： 用于非常大的情况下，并且仅返回的最新数据。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="a6a9d-p105">单击**运行案例日志**。生成日志并显示路径。在任务状态窗格中显示当前和最后一个任务的任务进度信息。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p105">Click **Run Case log**. The log is generated and path is displayed. The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="a6a9d-121">清除数据</span><span class="sxs-lookup"><span data-stu-id="a6a9d-121">Clear data</span></span>

<span data-ttu-id="a6a9d-p106">如有必要删除或重新初始化案例数据，必须初始化数据库实例。清除数据实用程序案例数据库、 文本文件、 案例文件夹和累计的结果中删除所有指定的条目。该函数只能由管理员执行。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p106">If it is necessary to delete or reinitialize case data, the database instance must be initialized. The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results. The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a6a9d-p107">此操作是不可逆的并将清除所有相关性标记和由专家执行分析。如有必要，请保存数据的备份。极高强度谨慎使用此选项。删除标记和排名文件会影响相关性结果。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p107">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert. Save a backup of data, if necessary. Use this option with extreme care. Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="a6a9d-129">在菜单栏中，单击**Cogwheel**图标。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="a6a9d-130">在**设置和实用程序\>实用程序**选项卡上，选择**清除数据\>安装**。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="a6a9d-131">选择一个选项以初始化的信息：</span><span class="sxs-lookup"><span data-stu-id="a6a9d-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="a6a9d-p108">**相关性**： 删除完成相关性，包括负载的定义和加载的文件关联的所有工作。将删除所有示例和标签。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p108">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads. It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="a6a9d-134">**近乎重复项和电子邮件线程**： 删除近乎重复项的所有分析信息和电子邮件线程。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="a6a9d-135">**主题**： 删除主题相关的数据。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="a6a9d-136">**导出历史记录**： 删除导出批次的历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="a6a9d-p109">单击**数据清除**。案例数据为清除状态。在**任务状态**窗格中显示当前和最后一个任务的任务进度信息。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p109">Click **Clear data**. The case data is cleared. The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="a6a9d-140">修改相关性</span><span class="sxs-lookup"><span data-stu-id="a6a9d-140">Modify Relevance</span></span>

<span data-ttu-id="a6a9d-141">本节介绍如何跳过或回滚相关性示例。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="a6a9d-142">在菜单栏中，单击**Cogwheel**图标。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="a6a9d-143">在**设置和实用程序\>实用程序**选项卡上，选择**修改相关性**。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="a6a9d-144">从选项中选择：</span><span class="sxs-lookup"><span data-stu-id="a6a9d-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="a6a9d-p110">**跳过当前示例-当前用户**： 这将标记，以**跳过**，运行该实用程序的用户打开案例示例中的所有无标记邮件的文件。相关性处理不会执行对标记为**跳过**的文件。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p110">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility. Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="a6a9d-p111">**跳过当前示例-所有打开的示例**： 这将标记，以**跳过**，所有打开的示例中的所有用户的所有无标记邮件的文件。不建议使用此选项，如果用户当前标记示例。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p111">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users. This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="a6a9d-p112">**回滚最后一个示例**： 最后完成的培训示例将被回滚，无论是否"计算"过程之前或之后的相关性。不允许的追赶示例回滚。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p112">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process. Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="a6a9d-151">单击**执行**运行。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="a6a9d-152">Transparency 分析</span><span class="sxs-lookup"><span data-stu-id="a6a9d-152">Transparency analysis</span></span>

<span data-ttu-id="a6a9d-p113">Transparency 分析实用程序使文件和其分配的相关性分数的详细的视图。可以使用此报告，作为健全性检查或比较由 human 审阅者分配高级电子数据展示相关性与定义文件的相关性。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p113">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score. The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="a6a9d-p114">除了相关性分数高级电子数据展示计算并分配考虑关键字上下文的关键字权重。可以将文件中的相同单词分配不同的权重，具体取决于上下文和位置。每个关键字使用的颜色强度从到深橙色黄色和 varying 灰色底纹的增加小数标记。颜色编码用于直观地指示 word 的相对的相关性分数的正整数或负贡献。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p114">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context. The same word in a file can be assigned different weights, depending on context and location. Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray. Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="a6a9d-159">在多问题的情况下，可以生成透明度分析报告每个问题。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="a6a9d-160">在菜单栏中，单击**Cogwheel**图标。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="a6a9d-161">在**设置和实用程序\>实用程序**选项卡上，选择**透明度分析\>安装**。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="a6a9d-162">中 * * 文件 ID * *，输入要处理的文件的文件 ID。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-162">In ** File ID **, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="a6a9d-163">在**问题**列表中，选择相关的问题。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="a6a9d-p115">单击**透明度分析**。完成后，将显示透明度分析报告文件，这将显示标记的关键字颜色与的总体相关性分数的关联方式。</span><span class="sxs-lookup"><span data-stu-id="a6a9d-p115">Click **Transparency analysis**. Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a6a9d-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6a9d-166">See also</span></span>

[<span data-ttu-id="a6a9d-167">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="a6a9d-167">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a6a9d-168">定义案例和租户设置</span><span class="sxs-lookup"><span data-stu-id="a6a9d-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)


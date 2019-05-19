---
title: 使用 Office 365 高级电子数据展示实用程序
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: '了解 Office 365 高级电子数据展示中的实用程序, 包括案例日志、清除数据、处理错误、修改相关性和透明度分析。  '
ms.openlocfilehash: df769ddddd37284da50bc715444f2bf928307706
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157954"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a><span data-ttu-id="a8ce2-103">使用 Office 365 高级电子数据展示实用程序</span><span class="sxs-lookup"><span data-stu-id="a8ce2-103">Use Office 365 Advanced eDiscovery utilities</span></span>

> [!NOTE]
> <span data-ttu-id="a8ce2-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="a8ce2-106">在高级电子数据展示中显示和可用的实用程序取决于上下文和用户角色。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="a8ce2-107">案例日志</span><span class="sxs-lookup"><span data-stu-id="a8ce2-107">Case log</span></span>

<span data-ttu-id="a8ce2-108">事例日志提供了应用程序处理活动的详细列表, 可用于跟踪、排除故障以及解决错误和警告。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="a8ce2-109">可以生成日志并将其存储在主机或服务器上的本地, 也可以直接发送到电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="a8ce2-110">日志文件也可以下载到客户端的计算机上。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="a8ce2-111">根据配置和用户角色, 可以启用或禁用客户端下载选项。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="a8ce2-112">在菜单栏中, 单击 " **Cogwheel** " 图标。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="a8ce2-113">在 "**设置和实用\>程序实用程序**" 选项卡中, 选择 "**事例日志\>设置**"。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="a8ce2-114">选择**日志级别**, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="a8ce2-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="a8ce2-115">**Standard**: 包含基本日志数据。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="a8ce2-116">此选项通常是监视所必需的, 除非另外推荐, 否则应使用此选项。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="a8ce2-117">**最小**: 用于非常大的情况, 仅返回最新数据。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="a8ce2-118">单击 "**运行案例日志**"。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-118">Click **Run Case log**.</span></span> <span data-ttu-id="a8ce2-119">生成日志并显示路径。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="a8ce2-120">当前任务和最后一项任务的任务进度信息将显示在 "任务状态" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="a8ce2-121">清除数据</span><span class="sxs-lookup"><span data-stu-id="a8ce2-121">Clear data</span></span>

<span data-ttu-id="a8ce2-122">如果需要删除或重新初始化事例数据, 则必须对数据库实例进行初始化。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="a8ce2-123">Clear data 实用工具从事例数据库、文本文件、事例文件夹和累积结果中删除所有指定的条目。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="a8ce2-124">此函数只能由管理员执行。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a8ce2-125">此操作是不可逆的, 将清除由专家执行的所有相关性标记和分析。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="a8ce2-126">如有必要, 保存数据的备份。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="a8ce2-127">使用此选项时应特别小心。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-127">Use this option with extreme care.</span></span> <span data-ttu-id="a8ce2-128">删除已标记和排名的文件会影响相关性结果。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="a8ce2-129">在菜单栏中, 单击 " **Cogwheel** " 图标。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="a8ce2-130">在 "**设置和实用工具\>实用程序**" 选项卡中, 选择 "**清除\>数据安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="a8ce2-131">选择要初始化的信息的选项:</span><span class="sxs-lookup"><span data-stu-id="a8ce2-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="a8ce2-132">**相关性**: 删除所有已完成的工作, 包括要加载的文件的加载和关联的定义。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="a8ce2-133">它将删除所有示例和标记。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="a8ce2-134">**临近的重复和电子邮件线程**: 删除临近的重复和电子邮件线程的所有分析信息。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="a8ce2-135">**主题**: 删除与主题相关的数据。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="a8ce2-136">**导出历史记录**: 删除导出批处理的历史记录信息。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="a8ce2-137">单击 "**清除数据**"。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-137">Click **Clear data**.</span></span> <span data-ttu-id="a8ce2-138">清除事例数据。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-138">The case data is cleared.</span></span> <span data-ttu-id="a8ce2-139">当前任务和最后一项任务的任务进度信息将显示在 "**任务状态**" 窗格中。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="a8ce2-140">修改相关性</span><span class="sxs-lookup"><span data-stu-id="a8ce2-140">Modify Relevance</span></span>

<span data-ttu-id="a8ce2-141">本节介绍如何跳过或回滚相关性示例。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="a8ce2-142">在菜单栏中, 单击 " **Cogwheel** " 图标。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="a8ce2-143">在 "**设置和实用工具\>实用程序**" 选项卡中, 选择 "**修改相关性**"。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="a8ce2-144">从选项中选择:</span><span class="sxs-lookup"><span data-stu-id="a8ce2-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="a8ce2-145">**跳过当前示例-为当前用户**: 这将标记为**跳过**, 在运行该实用工具的用户的打开事例示例中的所有未加标签的文件。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="a8ce2-146">将不会对标记为 "**跳过**" 的文件执行相关性处理。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="a8ce2-147">**Skip current sample-所有打开的**示例: 这将标记为**跳过**所有用户所有打开的样本中的所有未加标签的文件。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="a8ce2-148">如果用户当前正在标记示例, 则不建议使用此选项。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="a8ce2-149">**回滚上一个示例**: 最后完成的相关性培训示例将回滚, 而不管它是在 "计算" 过程之前还是之后。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="a8ce2-150">不允许回滚的追赶示例。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="a8ce2-151">单击 "**执行**" 以运行。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="a8ce2-152">透明度分析</span><span class="sxs-lookup"><span data-stu-id="a8ce2-152">Transparency analysis</span></span>

<span data-ttu-id="a8ce2-153">透明度分析实用程序启用文件及其分配的相关性分数的详细视图。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="a8ce2-154">该报告可用作健全性检查, 或比较由人工审阅者定义的文件的相关性, 与高级电子数据展示分配的相关性。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="a8ce2-155">除了相关性分数之外, 高级电子数据展示还计算和分配考虑关键字上下文的关键字权重。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="a8ce2-156">根据上下文和位置, 可以为文件中的同一个词分配不同的权重。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="a8ce2-157">每个关键字都使用增加的颜色强度范围 (从黄色到深橙色和不同的灰色底纹) 进行标记。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="a8ce2-158">颜色编码用于直观地指示单词相对分数的相对正负号或负份额。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="a8ce2-159">在多问题案例方案中, 可以为每个问题生成一个透明度分析报告。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="a8ce2-160">在菜单栏中, 单击 " **Cogwheel** " 图标。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="a8ce2-161">在 "**设置和实用工具\>实用程序**" 选项卡中, 选择 "**透明度\>分析安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="a8ce2-162">在 \* \* 文件 ID \* \* 中, 输入要处理的文件的文件 ID。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="a8ce2-163">在 "**问题**" 列表中, 选择相关问题。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="a8ce2-164">单击 "**透明度分析**"。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="a8ce2-165">完成后, 将显示文件的透明度分析报告, 其中显示了标记的关键字颜色与总体相关性分数的关联情况。</span><span class="sxs-lookup"><span data-stu-id="a8ce2-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a8ce2-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8ce2-166">See also</span></span>

[<span data-ttu-id="a8ce2-167">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="a8ce2-167">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a8ce2-168">定义大小写和租户设置</span><span class="sxs-lookup"><span data-stu-id="a8ce2-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)


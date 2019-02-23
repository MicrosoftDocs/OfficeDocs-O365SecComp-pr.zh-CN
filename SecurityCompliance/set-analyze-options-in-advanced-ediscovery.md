---
title: 在 Office 365 高级电子数据展示中设置分析选项
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: '查看为 Office 365 高级电子数据展示中的分析过程设置选项的步骤, 包括临近重复项、电子邮件线索和主题。  '
ms.openlocfilehash: 12bbe4043803c165a58adac80b72d03afd48adc7
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218222"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="dedd9-103">在 Office 365 高级电子数据展示中设置分析选项</span><span class="sxs-lookup"><span data-stu-id="dedd9-103">Set Analyze options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="dedd9-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="dedd9-106">在高级电子数据展示中, 在运行分析之前设置 "分析" 选项。</span><span class="sxs-lookup"><span data-stu-id="dedd9-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="dedd9-107">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="dedd9-107">Set Analyze options</span></span>

<span data-ttu-id="dedd9-p102">打开**准备\>分析** \> **设置**。将显示以下窗口。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p102">Open **Prepare \> Analyze** \> **Setup**. The following window is displayed.</span></span>
  
![设置分析选项](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="dedd9-p103">**临近的重复和电子邮件线索**如果要运行分析, 请选中此框。默认情况下处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p103">**Near-duplicates and email threads** Check this box if you want to run the analysis. It is selected by default.</span></span> 
  
 <span data-ttu-id="dedd9-113">**文档相似性**输入 "接近重复的阈值" 值或接受默认值 "65%"。</span><span class="sxs-lookup"><span data-stu-id="dedd9-113">**Document similarity**Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="dedd9-p104">**主题**选中此框可处理所有文件并为其分配主题。默认情况下, 未选中此复选框。如果要执行主题处理, 请输入以下选项。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p104">**Themes**Check this box to process all files and assign themes to them. By default, this check box is not selected. Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="dedd9-p105">**主题的最大数量**为要创建的主题数输入或选择一个值。默认值为200。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p105">**Max number of themes**Enter or select a value for the number of themes to create. The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="dedd9-p106">增加主题的数量将影响性能, 并使主题能够通用化。主题的数量越高, 它们的粒度就越多。例如, 如果一组50主题包含一个主题, 如 "篮球、Spurs、Clippers、Lakers", 则300主题可能包含单独的主题: "Spurs"、"Clippers"、"Lakers"。如果您不知道主题 "篮球" 并对 ECA 使用此功能, 则查看主题 "篮球" 可能有用。但是, 如果处理的主题过多, 则您可能永远无法看到 "篮球" 一词, 也可能不知道 Spurs 和 Clippers 是要查看的理想的篮球主题, 而不是执行启动并用于头发的项目。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p106">Increasing the number of themes affects performance, as well as the ability of a theme to generalize. The higher the number of themes, the more granular they are. For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers". If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful. But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="dedd9-p107">**建议的主题**您可以建议用主题单词来控制主题处理。高级电子数据展示将重点放在这些建议的单词上, 并根据 "最大主题数" 设置尝试创建一个或多个相关主题。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p107">**Suggested themes**You can suggest theme words to control Themes processing. Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="dedd9-p108">例如, 如果建议的单词是 "computer", 并且您将 "2" 指定为 "最大主题数", 高级电子数据展示将尝试生成与 "computer" 一词相关的两个主题。例如, 这两个主题可能是 "计算机软件" 和 "计算机硬件"。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p108">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer". The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![添加建议的主题](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="dedd9-129">若要查看、添加或编辑建议的主题, 请单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="dedd9-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="dedd9-p109">在 "**建议的主题**" 面板中, 单击 "](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) **添加**![" "添加图标" 图标以添加主题。在 "**添加建议的主题**" 面板中, 添加单词, 并以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p109">In the **Suggested themes** panel, click the **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme. In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="dedd9-132">在 "**主题数量**" 中, 选择一个值以确定高级电子数据展示将尝试为这些单词生成的主题数 (默认为1主题)。</span><span class="sxs-lookup"><span data-stu-id="dedd9-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="dedd9-133">单击 "**保存**", 然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="dedd9-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="dedd9-p110">主题的总数包括建议的主题。建议的主题总数不能超过总主题。如果有多个建议的主题相对于总主题, 则系统只会检测到几个 "novel" 主题, 因为大多数主题将专用于建议的主题。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p110">The total number of themes includes Suggested Themes. The total Suggested Themes cannot exceed the total themes. If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="dedd9-137">**模式**从下拉列表中, 选择 "**主题**" 选项:</span><span class="sxs-lookup"><span data-stu-id="dedd9-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="dedd9-138">**创建和应用模型**: 从一段文件的模型计算主题, 然后在它们之间分发文件。</span><span class="sxs-lookup"><span data-stu-id="dedd9-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="dedd9-p111">**创建模型**: 计算来自一段文件的主题模型。拆分文件的应用过程是在其他时间单独完成的。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p111">**Create model**: Calculates a themes model from a segment of the files. The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="dedd9-p112">**应用模型**: 仅当以前创建且尚未应用模型时, 才会显示此选项。这将根据主题划分这些文件。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p112">**Apply model**: This option is only shown if a model was created previously and not yet applied. This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="dedd9-143">您还可以[设置 "忽略文本](set-ignore-text-in-advanced-ediscovery.md)" 并设置分析的[高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="dedd9-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="dedd9-p113">设置这些选项后, 请单击 "**分析**" 以运行。显示 "[查看分析结果](view-analyze-results-in-advanced-ediscovery.md)"。</span><span class="sxs-lookup"><span data-stu-id="dedd9-p113">After you've set these options, click **Analyze** to run. [View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dedd9-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dedd9-146">See also</span></span>

[<span data-ttu-id="dedd9-147">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="dedd9-147">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="dedd9-148">了解文档相似性</span><span class="sxs-lookup"><span data-stu-id="dedd9-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="dedd9-149">设置忽略文本</span><span class="sxs-lookup"><span data-stu-id="dedd9-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="dedd9-150">设置分析高级设置</span><span class="sxs-lookup"><span data-stu-id="dedd9-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="dedd9-151">查看分析结果</span><span class="sxs-lookup"><span data-stu-id="dedd9-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)


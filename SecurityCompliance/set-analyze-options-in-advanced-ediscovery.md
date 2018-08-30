---
title: 在 Office 365 高级电子数据展示中设置分析选项
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: '查看设置选项的 Office 365 高级电子数据展示，包括近乎重复项、 电子邮件线程和主题中的分析过程的步骤。  '
ms.openlocfilehash: a0ebbadb180321a3094cb1056ed8e0e6500ee66a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525395"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="fbfa0-103">在 Office 365 高级电子数据展示中设置分析选项</span><span class="sxs-lookup"><span data-stu-id="fbfa0-103">Set Analyze options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="fbfa0-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="fbfa0-106">在高级电子数据展示，设置之前运行分析分析选项。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="fbfa0-107">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="fbfa0-107">Set Analyze options</span></span>

<span data-ttu-id="fbfa0-p102">打开**准备\>分析** \> **安装程序**。将显示以下窗口。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p102">Open **Prepare \> Analyze** \> **Setup**. The following window is displayed.</span></span>
  
![设置分析选项](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="fbfa0-p103">**近乎重复项和电子邮件线程**如果您想要运行分析，请选中此框。默认情况下选择它。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p103">**Near-duplicates and email threads** Check this box if you want to run the analysis. It is selected by default.</span></span> 
  
 <span data-ttu-id="fbfa0-113">**文档相似性**输入 Near 重复阈值或接受默认值 65%。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-113">**Document similarity**Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="fbfa0-p104">**主题**选中此框可处理所有文件并将主题分配给它们。默认情况下不选中此复选框。如果您想要执行处理的主题，请输入以下选项。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p104">**Themes**Check this box to process all files and assign themes to them. By default, this check box is not selected. Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="fbfa0-p105">**主题的最大数目**输入或选择主题创建的数目的值。默认值为 200。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p105">**Max number of themes**Enter or select a value for the number of themes to create. The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fbfa0-p106">增加了主题会影响性能，以及使通用化主题的能力。主题的更高版本数、 更精细它们是。例如，如果一 50 主题中包含"篮球、 支路，剪，Lakers"; 例如主题300 主题可能包括单独的主题:"支路"、"剪 2"、"Lakers"。如果您具有"篮球"的任何认知度的主题，并对 ECA 使用该功能，查看主题"篮球"非常有用。但是，如果处理有太多的主题，您可能永远不会看到的单词"篮球"并可能不知道，支路和剪是好篮球主题，若要查看，而不是项目上，启动和用于字形。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p106">Increasing the number of themes affects performance, as well as the ability of a theme to generalize. The higher the number of themes, the more granular they are. For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers". If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful. But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="fbfa0-p107">**建议主题**您可以选择建议主题单词以控制处理的主题。高级电子数据展示将专注于这些建议单词，然后尝试创建一个或多个相关的主题，基于"最大主题数目"设置。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p107">**Suggested themes**You can suggest theme words to control Themes processing. Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="fbfa0-p108">例如，如果所建议的单词"computer"，并且您"主题的最大数量"指定"2"，高级电子数据展示将尝试生成与 word"computer"的两个主题。两个主题可能是"计算机 software"和"计算机 hardware"，例如。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p108">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer". The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![添加建议的主题](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="fbfa0-129">若要查看、 添加或编辑建议的主题，请单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="fbfa0-p109">在**建议主题**面板中，单击**添加**![添加图标](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)图标添加主题。在**添加建议的主题**面板中，添加的单词，以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p109">In the **Suggested themes** panel, click the **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme. In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="fbfa0-132">在**主题数目**，选择一个值，确定高级电子数据展示将尝试为这些单词 （默认值为 1 主题） 生成的主题的数目。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="fbfa0-133">单击**保存**，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fbfa0-p110">主题的总数目包括建议的主题。总的建议主题不能超过总主题。如果有许多建议主题相对于总主题，因为大多数的主题将专用于建议主题，系统会检测仅少数"小说"主题。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p110">The total number of themes includes Suggested Themes. The total Suggested Themes cannot exceed the total themes. If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="fbfa0-137">**模式**从下拉列表中，选择**主题**选项:</span><span class="sxs-lookup"><span data-stu-id="fbfa0-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="fbfa0-138">**创建和应用模型**： 计算由模型文件的一段中的主题，然后分布在它们之间的文件。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="fbfa0-p111">**创建模型**： 计算一段的文件中的主题模型。划分文件的应用过程是单独完成另一次。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p111">**Create model**: Calculates a themes model from a segment of the files. The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="fbfa0-p112">**应用模型**： 是否以前创建和尚未应用模型，才会显示此选项。这将分割基于主题的文件。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p112">**Apply model**: This option is only shown if a model was created previously and not yet applied. This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="fbfa0-143">您还可以[设置忽略文本](set-ignore-text-in-advanced-ediscovery.md)并[设置分析高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md)的分析。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="fbfa0-p113">您已设置这些选项后，单击**分析**运行。显示[视图分析结果](view-analyze-results-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="fbfa0-p113">After you've set these options, click **Analyze** to run. [View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fbfa0-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbfa0-146">See also</span></span>

[<span data-ttu-id="fbfa0-147">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="fbfa0-147">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="fbfa0-148">了解文档相似性</span><span class="sxs-lookup"><span data-stu-id="fbfa0-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="fbfa0-149">设置忽略文本</span><span class="sxs-lookup"><span data-stu-id="fbfa0-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="fbfa0-150">设置分析高级设置</span><span class="sxs-lookup"><span data-stu-id="fbfa0-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="fbfa0-151">查看分析结果</span><span class="sxs-lookup"><span data-stu-id="fbfa0-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)


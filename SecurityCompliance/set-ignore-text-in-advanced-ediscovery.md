---
title: 设置用于在 Office 365 高级电子数据展示中进行分析的 "忽略文本" 选项
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
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: '了解在使用 Office 365 高级电子数据展示中的分析和处理模块时, 如何定义要忽略特定文本的规则。  '
ms.openlocfilehash: 3a4c1d17a9a56d3018509a8dcfd6b49abb951676
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260814"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a><span data-ttu-id="a0431-103">设置用于在 Office 365 高级电子数据展示中进行分析的 "忽略文本" 选项</span><span class="sxs-lookup"><span data-stu-id="a0431-103">Set Ignore Text option for Analyze in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="a0431-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="a0431-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="a0431-106">"忽略文本" 功能可应用于以下所有高级电子数据展示模块或以下任一高级电子数据展示模块: 分析 (接近重复项、电子邮件线程、主题) 和相关性。</span><span class="sxs-lookup"><span data-stu-id="a0431-106">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance.</span></span> <span data-ttu-id="a0431-107">已忽略的文本不会出现在相关性中显示的文件中, 并且分析/计算将丢弃忽略的文本。</span><span class="sxs-lookup"><span data-stu-id="a0431-107">Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="a0431-108">如果之前已为已运行的模块定义了 ignore text 功能, 则 "忽略文本" 设置现在将受到保护, 无法进行修改。</span><span class="sxs-lookup"><span data-stu-id="a0431-108">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified.</span></span> <span data-ttu-id="a0431-109">但是, 相关性模块的 Ignore Text 功能仍可在任何时候更改。</span><span class="sxs-lookup"><span data-stu-id="a0431-109">However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="a0431-110">如何应用 "忽略文本" 筛选器</span><span class="sxs-lookup"><span data-stu-id="a0431-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="a0431-111">将按输入的顺序应用多个 "忽略文本" 筛选器。</span><span class="sxs-lookup"><span data-stu-id="a0431-111">Multiple Ignore Text filters are applied in the order that they were entered.</span></span> <span data-ttu-id="a0431-112">若要更改应用顺序, 必须按所需顺序将其删除并重新输入。</span><span class="sxs-lookup"><span data-stu-id="a0431-112">To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="a0431-113">例如, 如果文本内容是: "DAVE 小明小红 CAROL 前夕", 以下是忽略文本项和结果的示例:</span><span class="sxs-lookup"><span data-stu-id="a0431-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a0431-114">**忽略文本输入**</span><span class="sxs-lookup"><span data-stu-id="a0431-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="a0431-115">**结果**</span><span class="sxs-lookup"><span data-stu-id="a0431-115">**Results**</span></span> <br/> |
|<span data-ttu-id="a0431-116">"小红", "BOB CAROL"</span><span class="sxs-lookup"><span data-stu-id="a0431-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="a0431-117">"DAVE 前夕"</span><span class="sxs-lookup"><span data-stu-id="a0431-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="a0431-118">"小红", "BOB ALICE CAROL"</span><span class="sxs-lookup"><span data-stu-id="a0431-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="a0431-119">"DAVE BOB CAROL 前夕"</span><span class="sxs-lookup"><span data-stu-id="a0431-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="a0431-120">未实现第二个 "忽略" 文本条目, 因为在应用第一个 "忽略" 文本后, 不会找到该字符串。</span><span class="sxs-lookup"><span data-stu-id="a0431-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="a0431-121">在定义 Ignore Text 时使用正则表达式</span><span class="sxs-lookup"><span data-stu-id="a0431-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="a0431-122">在定义 Ignore Text 时, 支持使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="a0431-122">Regular expressions are supported for use when defining Ignore Text.</span></span> <span data-ttu-id="a0431-123">以下是正则表达式语法和用法的示例:</span><span class="sxs-lookup"><span data-stu-id="a0431-123">The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="a0431-124">若要删除 (忽略) 文本, 请从行尾开始:</span><span class="sxs-lookup"><span data-stu-id="a0431-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="a0431-125">其中, "Begin" 是此字符串在行中的初始匹配项。</span><span class="sxs-lookup"><span data-stu-id="a0431-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="a0431-126">例如, 对于以下文本:</span><span class="sxs-lookup"><span data-stu-id="a0431-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="a0431-127">**这是第一句, 第一行**</span><span class="sxs-lookup"><span data-stu-id="a0431-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="a0431-128">**这是第二个句子和第二行 "**</span><span class="sxs-lookup"><span data-stu-id="a0431-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="a0431-129">正则表达式 first (.\*)$ 将导致:</span><span class="sxs-lookup"><span data-stu-id="a0431-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="a0431-130">**"这是**</span><span class="sxs-lookup"><span data-stu-id="a0431-130">**"This is**</span></span>
    
    <span data-ttu-id="a0431-131">**这是第二个句子和第二行 "**</span><span class="sxs-lookup"><span data-stu-id="a0431-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="a0431-132">若要删除在电子邮件线程结束时自动插入的免责声明和法律声明, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="a0431-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="a0431-133">其中, "Begin" 和 "end" 是换行文本段落的开头和结尾的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="a0431-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="a0431-134">例如, 以下正则表达式将删除在开始和结束字符串之间的电子邮件线程中的免责声明和法律声明:</span><span class="sxs-lookup"><span data-stu-id="a0431-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="a0431-135">**此邮件包含机密信息 (. |\s)\*如果需要验证, 请请求硬复制版本**</span><span class="sxs-lookup"><span data-stu-id="a0431-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="a0431-136">若要删除免责声明 (包括特殊字符), 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="a0431-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="a0431-137">例如, 对于以下文本 (在 x 的此处用免责声明表示):</span><span class="sxs-lookup"><span data-stu-id="a0431-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="a0431-138">**/\*\ 此邮件包含机密信息。xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="a0431-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="a0431-139">**xxxx xxxx xxxx xxxx xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="a0431-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="a0431-140">\**xxxx xxxx 如果需要验证, 请请求硬复制版本。/\*\**</span><span class="sxs-lookup"><span data-stu-id="a0431-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="a0431-141">要删除上述免责声明的正则表达式应为:</span><span class="sxs-lookup"><span data-stu-id="a0431-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="a0431-142">**\/\\*\\此邮件包含机密信息\.(. |\s)\*如果需要验证, 请请求硬复制版本\.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="a0431-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="a0431-143">正则表达式规则:</span><span class="sxs-lookup"><span data-stu-id="a0431-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="a0431-144">除空格、"_" 和 "-" 之外不属于字母表的任何字符都必须以 "\"." 开头。</span><span class="sxs-lookup"><span data-stu-id="a0431-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="a0431-145">正则 eExpression 字段的长度不受限制。</span><span class="sxs-lookup"><span data-stu-id="a0431-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="a0431-146">有关正则表达式的说明和详细语法, 请参阅:[正则表达式语言-快速参考](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a0431-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="a0431-147">定义 "忽略文本" 规则</span><span class="sxs-lookup"><span data-stu-id="a0431-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="a0431-148">在 "**管理\>分析\>分析选项**" 选项卡的 "**忽略文本**" 部分中**+** , 单击图标以添加规则。</span><span class="sxs-lookup"><span data-stu-id="a0431-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="a0431-149">在 "**添加忽略文本**" 对话框的 "**名称**" 字段中, 为 "忽略文本" 规则键入一个名称。</span><span class="sxs-lookup"><span data-stu-id="a0431-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![添加忽略的文本](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="a0431-151">在 "**文本**" 框中, 键入要忽略的文本。</span><span class="sxs-lookup"><span data-stu-id="a0431-151">In the **Text** box, type the text to be ignored.</span></span> <span data-ttu-id="a0431-152">文本字段允许不受限制的字符数。</span><span class="sxs-lookup"><span data-stu-id="a0431-152">The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="a0431-153">如上面的窗口中所示, 单击**灯泡**以查看 "忽略文本" 规则的通用语法准则。</span><span class="sxs-lookup"><span data-stu-id="a0431-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="a0431-154">如果需要, 选中 "**区分大小写**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a0431-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="a0431-155">在 "**应用于**" 列表中, 选择要应用定义的高级电子数据展示模块。</span><span class="sxs-lookup"><span data-stu-id="a0431-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="a0431-156">如果要对示例文本运行测试, 请在 "**输入**" 文本框中键入示例文本, 然后单击 "**测试**"。</span><span class="sxs-lookup"><span data-stu-id="a0431-156">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**.</span></span> <span data-ttu-id="a0431-157">结果将显示在 "**输出**" 文本框中。</span><span class="sxs-lookup"><span data-stu-id="a0431-157">The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="a0431-158">单击 **"确定"** 以保存 "忽略" 文本规则。</span><span class="sxs-lookup"><span data-stu-id="a0431-158">Click **OK** to save the Ignore Text rule.</span></span> <span data-ttu-id="a0431-159">将显示 "定义的忽略文本" 规则。</span><span class="sxs-lookup"><span data-stu-id="a0431-159">The defined Ignore Text rule is displayed.</span></span> 
    
    ![设置被忽略的文本名称](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="a0431-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0431-161">See also</span></span>

[<span data-ttu-id="a0431-162">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="a0431-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a0431-163">了解文档相似性</span><span class="sxs-lookup"><span data-stu-id="a0431-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a0431-164">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="a0431-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a0431-165">设置分析高级设置</span><span class="sxs-lookup"><span data-stu-id="a0431-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a0431-166">查看分析结果</span><span class="sxs-lookup"><span data-stu-id="a0431-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)


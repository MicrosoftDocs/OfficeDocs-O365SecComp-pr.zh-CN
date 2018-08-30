---
title: 在 Office 365 高级电子数据展示中为分析设置“忽略文本”选项
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
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: '了解如何定义要使用 Office 365 高级电子数据展示中的分析和过程模块时忽略特定文本的规则。  '
ms.openlocfilehash: eb7e7052979087b7dba98aac3b0c9ab75ec0d02a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525447"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a><span data-ttu-id="8928d-103">在 Office 365 高级电子数据展示中为分析设置“忽略文本”选项</span><span class="sxs-lookup"><span data-stu-id="8928d-103">Set Ignore Text option for Analyze in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="8928d-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="8928d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="8928d-p102">忽略文本功能可以应用于所有或任何以下高级电子数据展示模块： 分析 （重复附近，电子邮件线程主题） 和相关性。忽略的文本不会出现在文件中相关性，显示和分析/计算将放弃忽略的文本。</span><span class="sxs-lookup"><span data-stu-id="8928d-p102">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance. Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="8928d-p103">如果忽略文本功能之前已经运行的模块的定义忽略文本设置将现在受保护不被修改。但是，仍可以随时更改相关性模块的忽略文本功能。</span><span class="sxs-lookup"><span data-stu-id="8928d-p103">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified. However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="8928d-110">如何应用忽略文本筛选器</span><span class="sxs-lookup"><span data-stu-id="8928d-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="8928d-p104">多个忽略文本筛选器中的输入顺序应用。若要更改所应用的顺序，它们必须删除并重新输入所需的顺序。</span><span class="sxs-lookup"><span data-stu-id="8928d-p104">Multiple Ignore Text filters are applied in the order that they were entered. To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="8928d-113">例如，如果文本内容:"DAVE BOB 刘爱琳 CAROL 前夕"，下面是示例忽略文本条目和的结果：</span><span class="sxs-lookup"><span data-stu-id="8928d-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results:</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="8928d-114">**忽略文本条目**</span><span class="sxs-lookup"><span data-stu-id="8928d-114">**Ignore Text entries**</span></span> <br/> |**==\>** <br/> |<span data-ttu-id="8928d-115">**结果**</span><span class="sxs-lookup"><span data-stu-id="8928d-115">**Results**</span></span> <br/> |
|<span data-ttu-id="8928d-116">"刘爱琳""BOB 康"</span><span class="sxs-lookup"><span data-stu-id="8928d-116">"ALICE", "BOB CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="8928d-117">"DAVE 前夕"</span><span class="sxs-lookup"><span data-stu-id="8928d-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="8928d-118">"刘爱琳"，"BOB 刘爱琳 CAROL"</span><span class="sxs-lookup"><span data-stu-id="8928d-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |==\>  <br/> |<span data-ttu-id="8928d-119">"DAVE BOB CAROL 前夕"</span><span class="sxs-lookup"><span data-stu-id="8928d-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="8928d-120">由于字符串找不到此类应用第一个忽略文本后未实现的第二个忽略文本项。</span><span class="sxs-lookup"><span data-stu-id="8928d-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="8928d-121">在定义忽略文本时使用正则表达式</span><span class="sxs-lookup"><span data-stu-id="8928d-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="8928d-p105">定义忽略文本时使用支持正则表达式。正则表达式语法和用法的示例如下：</span><span class="sxs-lookup"><span data-stu-id="8928d-p105">Regular expressions are supported for use when defining Ignore Text. The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="8928d-124">若要删除 （忽略） 从开始到结束的行的文本：</span><span class="sxs-lookup"><span data-stu-id="8928d-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="8928d-125">"开始"所在的行中的此字符串的初始匹配项。</span><span class="sxs-lookup"><span data-stu-id="8928d-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="8928d-126">例如，对于以下文本：</span><span class="sxs-lookup"><span data-stu-id="8928d-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="8928d-127">**"This is 第一句和第一行**</span><span class="sxs-lookup"><span data-stu-id="8928d-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="8928d-128">**这是第二个句子和第二行"**</span><span class="sxs-lookup"><span data-stu-id="8928d-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="8928d-129">正则表达式 first(.\*)$ 将导致：</span><span class="sxs-lookup"><span data-stu-id="8928d-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="8928d-130">**"This is**</span><span class="sxs-lookup"><span data-stu-id="8928d-130">**"This is**</span></span>
    
    <span data-ttu-id="8928d-131">**这是第二个句子和第二行"**</span><span class="sxs-lookup"><span data-stu-id="8928d-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="8928d-132">若要删除免责声明和自动插入到电子邮件线程的末尾的法律语句：</span><span class="sxs-lookup"><span data-stu-id="8928d-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="8928d-133">其中"开始"和"结束"是唯一的字符串的开头和换行的文本段落的末尾。</span><span class="sxs-lookup"><span data-stu-id="8928d-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="8928d-134">例如，下面的正则表达式将删除免责声明和 Begin 和 End 字符串之间的电子邮件主题中的法律语句：</span><span class="sxs-lookup"><span data-stu-id="8928d-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="8928d-135">**此消息包含机密信息 (。 |\s)\*如果需要验证，则请请求书面版本**</span><span class="sxs-lookup"><span data-stu-id="8928d-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="8928d-136">若要删除免责声明 （包括特殊字符）：</span><span class="sxs-lookup"><span data-stu-id="8928d-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="8928d-137">例如，对于 （带免责声明此处由 x） 的以下文本：</span><span class="sxs-lookup"><span data-stu-id="8928d-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="8928d-138">**/\*\ 此邮件包含机密信息。格式格式**</span><span class="sxs-lookup"><span data-stu-id="8928d-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="8928d-139">**格式格式格式格式格式格式格式**</span><span class="sxs-lookup"><span data-stu-id="8928d-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="8928d-140">\**格式格式如果验证是必需的请请求书面版本。/\*\**</span><span class="sxs-lookup"><span data-stu-id="8928d-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="8928d-141">应删除上述免责声明的正则表达式：</span><span class="sxs-lookup"><span data-stu-id="8928d-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="8928d-142">**\/\\*\\此消息包含机密信息\.(。 |\s)\*如果需要验证，则请请求书面版本\.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="8928d-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="8928d-143">正则表达式规则：</span><span class="sxs-lookup"><span data-stu-id="8928d-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="8928d-144">不属于除空格，"_"字母任何字符和"-"前面必须有"\"。</span><span class="sxs-lookup"><span data-stu-id="8928d-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="8928d-145">正则 eExpression 字段可以是无限的长度。</span><span class="sxs-lookup"><span data-stu-id="8928d-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="8928d-146">说明和正则表达式的详细的语法，请参阅：[正则表达式语言-快速参考](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8928d-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="8928d-147">定义忽略文本规则</span><span class="sxs-lookup"><span data-stu-id="8928d-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="8928d-148">在**管理\>分析\>分析选项**选项卡上**忽略文字**部分中，单击**+** 添加规则的图标。</span><span class="sxs-lookup"><span data-stu-id="8928d-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="8928d-149">在**添加忽略文本**对话框中，在**名称**字段中，键入忽略文本规则的名称。</span><span class="sxs-lookup"><span data-stu-id="8928d-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![添加忽略的文本](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="8928d-p106">在**文本**框中，键入要忽略的文本。文本字段允许任意的数量的字符。</span><span class="sxs-lookup"><span data-stu-id="8928d-p106">In the **Text** box, type the text to be ignored. The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="8928d-153">如下所示在上面的窗口中，单击**灯泡**以查看忽略文本规则的通用语法指南。</span><span class="sxs-lookup"><span data-stu-id="8928d-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="8928d-154">如果需要，请选择**区分大小写**复选框。</span><span class="sxs-lookup"><span data-stu-id="8928d-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="8928d-155">在**应用于**列表中，选择要应用的定义中的高级电子数据展示模块。</span><span class="sxs-lookup"><span data-stu-id="8928d-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="8928d-p107">如果您希望示例文本上运行测试，在**输入**文本框中键入示例文本，然后单击**测试**。结果将显示在**输出**文本框中。</span><span class="sxs-lookup"><span data-stu-id="8928d-p107">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**. The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="8928d-p108">单击**确定**以保存忽略文本规则。显示定义的忽略文本规则。</span><span class="sxs-lookup"><span data-stu-id="8928d-p108">Click **OK** to save the Ignore Text rule. The defined Ignore Text rule is displayed.</span></span> 
    
    ![设置被忽略的文本名称](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="8928d-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8928d-161">See also</span></span>

[<span data-ttu-id="8928d-162">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="8928d-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8928d-163">了解文档相似性</span><span class="sxs-lookup"><span data-stu-id="8928d-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8928d-164">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="8928d-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8928d-165">设置分析高级设置</span><span class="sxs-lookup"><span data-stu-id="8928d-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8928d-166">查看分析结果</span><span class="sxs-lookup"><span data-stu-id="8928d-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)


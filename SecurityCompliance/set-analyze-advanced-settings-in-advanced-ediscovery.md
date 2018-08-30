---
title: 在 Office 365 高级电子数据展示中设置分析高级设置
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
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: '了解如何配置高级的设置，包括近乎重复项、 电子邮件线程和主题、 为 Office 365 高级电子数据展示中的分析过程。 '
ms.openlocfilehash: 7ffb80230a43eacb98a9c4ecb569f03cff134aac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524868"
---
# <a name="set-analyze-advanced-settings-in-office-365-advanced-ediscovery"></a><span data-ttu-id="1b5d8-103">在 Office 365 高级电子数据展示中设置分析高级设置</span><span class="sxs-lookup"><span data-stu-id="1b5d8-103">Set Analyze advanced settings in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="1b5d8-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="1b5d8-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="1b5d8-p102">高级电子数据展示提供用于分析模块设置默认的高级参数。以下过程介绍了可为指定的设置。</span><span class="sxs-lookup"><span data-stu-id="1b5d8-p102">Advanced eDiscovery provides default advanced parameters for Analyze module settings. The following procedure describes settings that can be specified.</span></span>
  
1. <span data-ttu-id="1b5d8-p103">在**准备\>分析\>安装**选项卡上，单击**高级设置**（位于页面底部）。将显示以下窗格。</span><span class="sxs-lookup"><span data-stu-id="1b5d8-p103">In the **Prepare \> Analyze \> Setup** tab, click **Advanced settings** (at the bottom of the page). The following panel is displayed.</span></span> 
    
    ![设置分析高级设置](media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. <span data-ttu-id="1b5d8-111">在**靠近重复项和电子邮件线程参数**，根据需要选择以下值：</span><span class="sxs-lookup"><span data-stu-id="1b5d8-111">In **Near-duplicates and Email threads parameters**, select values for the following as necessary:</span></span>
    
  - <span data-ttu-id="1b5d8-112">**单词的最小数目**： 单词，下面的文件不会提交进行近乎重复分析的最小数字。</span><span class="sxs-lookup"><span data-stu-id="1b5d8-112">**Minimum number of words**: Minimum number for words, below which a file is not submitted for Near-duplicate analysis.</span></span> 
    
  - <span data-ttu-id="1b5d8-113">**最大单词数**： 单词，上面的文件不会提交进行近乎重复分析的最大数量。</span><span class="sxs-lookup"><span data-stu-id="1b5d8-113">**Maximum number of words**: Maximum number for words, above which a file is not submitted for Near-duplicate analysis.</span></span>
    
  - <span data-ttu-id="1b5d8-p104">**电子邮件相似性**： 类似的两个电子邮件视为类似的最低级别。该值始终是等于或大于文档相似性。默认值为 90%。</span><span class="sxs-lookup"><span data-stu-id="1b5d8-p104">**Email similarity**: Minimal level of resemblance for two emails to be considered similar. Value is always equal to, or larger than document similarity. Default is 90%.</span></span>
    
3. <span data-ttu-id="1b5d8-117">**主题参数**，选择**包含主题分析中的号码**复选框，在处理期间分析主题中包括号。</span><span class="sxs-lookup"><span data-stu-id="1b5d8-117">In **Themes parameters**, select the **Include numbers in theme analysis** check box to include numbers in the processing of Themes during Analyze.</span></span> 
    
4. <span data-ttu-id="1b5d8-118">单击“保存”****。</span><span class="sxs-lookup"><span data-stu-id="1b5d8-118">Click **Save**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="1b5d8-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b5d8-119">See also</span></span>

[<span data-ttu-id="1b5d8-120">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="1b5d8-120">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="1b5d8-121">了解文档相似性</span><span class="sxs-lookup"><span data-stu-id="1b5d8-121">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1b5d8-122">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="1b5d8-122">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1b5d8-123">设置忽略文本</span><span class="sxs-lookup"><span data-stu-id="1b5d8-123">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="1b5d8-124">查看分析结果</span><span class="sxs-lookup"><span data-stu-id="1b5d8-124">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)


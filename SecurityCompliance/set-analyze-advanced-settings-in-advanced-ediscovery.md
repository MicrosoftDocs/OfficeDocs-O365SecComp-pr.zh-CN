---
title: 在 Office 365 高级电子数据展示中设置分析高级设置
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
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: '了解如何为 Office 365 高级电子数据展示中的分析过程配置高级设置, 包括接近重复的电子邮件线程和主题。 '
ms.openlocfilehash: d8dfb9f3ecfcda0f267dfccdc716eda40fe450b2
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260852"
---
# <a name="set-analyze-advanced-settings-in-office-365-advanced-ediscovery"></a><span data-ttu-id="762d1-103">在 Office 365 高级电子数据展示中设置分析高级设置</span><span class="sxs-lookup"><span data-stu-id="762d1-103">Set Analyze advanced settings in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="762d1-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="762d1-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="762d1-106">高级电子数据展示可提供分析模块设置的默认高级参数。</span><span class="sxs-lookup"><span data-stu-id="762d1-106">Advanced eDiscovery provides default advanced parameters for Analyze module settings.</span></span> <span data-ttu-id="762d1-107">下面的过程介绍了可指定的设置。</span><span class="sxs-lookup"><span data-stu-id="762d1-107">The following procedure describes settings that can be specified.</span></span>
  
1. <span data-ttu-id="762d1-108">在 "**准备\>分析\>设置**" 选项卡上, 单击页面底部的 "**高级设置**"。</span><span class="sxs-lookup"><span data-stu-id="762d1-108">In the **Prepare \> Analyze \> Setup** tab, click **Advanced settings** (at the bottom of the page).</span></span> <span data-ttu-id="762d1-109">将显示以下面板。</span><span class="sxs-lookup"><span data-stu-id="762d1-109">The following panel is displayed.</span></span> 
    
    ![设置分析高级设置](media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. <span data-ttu-id="762d1-111">在 "**临近副本" 和 "电子邮件线程" 参数**中, 根据需要选择以下值:</span><span class="sxs-lookup"><span data-stu-id="762d1-111">In **Near-duplicates and Email threads parameters**, select values for the following as necessary:</span></span>
    
  - <span data-ttu-id="762d1-112">**最小单词数**: 单词的最小数目, 在以下情况下, 不会将文件提交到接近重复的分析。</span><span class="sxs-lookup"><span data-stu-id="762d1-112">**Minimum number of words**: Minimum number for words, below which a file is not submitted for Near-duplicate analysis.</span></span> 
    
  - <span data-ttu-id="762d1-113">**最大单词数**: 单词的最大数目, 超过该数目时不会将文件提交到接近重复的分析。</span><span class="sxs-lookup"><span data-stu-id="762d1-113">**Maximum number of words**: Maximum number for words, above which a file is not submitted for Near-duplicate analysis.</span></span>
    
  - <span data-ttu-id="762d1-114">**电子邮件相似性**: 将两封电子邮件视为相似的最小 resemblance 级别。</span><span class="sxs-lookup"><span data-stu-id="762d1-114">**Email similarity**: Minimal level of resemblance for two emails to be considered similar.</span></span> <span data-ttu-id="762d1-115">值始终等于或大于文档相似性。</span><span class="sxs-lookup"><span data-stu-id="762d1-115">Value is always equal to, or larger than document similarity.</span></span> <span data-ttu-id="762d1-116">默认值为 90%。</span><span class="sxs-lookup"><span data-stu-id="762d1-116">Default is 90%.</span></span>
    
3. <span data-ttu-id="762d1-117">在 "**主题参数**" 中, 选中 "将**数字包含在主题分析**中" 复选框, 以在分析期间包含处理主题过程中的数字。</span><span class="sxs-lookup"><span data-stu-id="762d1-117">In **Themes parameters**, select the **Include numbers in theme analysis** check box to include numbers in the processing of Themes during Analyze.</span></span> 
    
4. <span data-ttu-id="762d1-118">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="762d1-118">Click **Save**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="762d1-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="762d1-119">See also</span></span>

[<span data-ttu-id="762d1-120">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="762d1-120">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="762d1-121">了解文档相似性</span><span class="sxs-lookup"><span data-stu-id="762d1-121">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="762d1-122">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="762d1-122">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="762d1-123">设置忽略文本</span><span class="sxs-lookup"><span data-stu-id="762d1-123">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="762d1-124">查看分析结果</span><span class="sxs-lookup"><span data-stu-id="762d1-124">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)


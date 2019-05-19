---
title: 在 Office 365 高级电子数据展示中定义突出显示的关键字和高级选项
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 03cc4387-2c7d-4058-8a44-0deefb58f011
description: '了解如何将用户定义的关键字添加到相关性, 以帮助在 Office 365 高级电子数据展示中标记时识别相关文件, 并指定成本参数。  '
ms.openlocfilehash: 4542e80e5324a35df2e7dc8e7e0cf09f37ae1ef4
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153384"
---
# <a name="define-highlighted-keywords-and-advanced-options-in-office-365-advanced-ediscovery"></a><span data-ttu-id="393a2-103">在 Office 365 高级电子数据展示中定义突出显示的关键字和高级选项</span><span class="sxs-lookup"><span data-stu-id="393a2-103">Define highlighted keywords and advanced options in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="393a2-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="393a2-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="393a2-106">在高级电子数据展示中, 可以将用户定义的关键字添加到相关性, 以帮助您在标记时识别相关文件。</span><span class="sxs-lookup"><span data-stu-id="393a2-106">In Advanced eDiscovery, it's possible to add user-defined keywords to Relevance in order to help you identify relevant files while tagging.</span></span> <span data-ttu-id="393a2-107">关键字将以指定的颜色显示在**相关性\>标记**中。</span><span class="sxs-lookup"><span data-stu-id="393a2-107">Keywords will be displayed in the specified colors in **Relevance \> Tag**.</span></span> 
  
<span data-ttu-id="393a2-108">如下所述, 可以添加关键字列表, 并将颜色分配给关键字列表和相关问题。</span><span class="sxs-lookup"><span data-stu-id="393a2-108">As described below, keyword lists can be added, and colors assigned to the Keywords list and the related issues.</span></span> <span data-ttu-id="393a2-109">如果有, 工具提示将显示关键字的说明 (如果有), 如双下划线所示。</span><span class="sxs-lookup"><span data-stu-id="393a2-109">A tooltip displays the keyword's description, if one exists, as indicated by a double underline.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="393a2-110">相关性标记期间, 相关性和查看关键字命中结果中的搜索词突出显示不适用于日语、中文和朝鲜语双字节字符集。</span><span class="sxs-lookup"><span data-stu-id="393a2-110">Hit highlighting in Relevance and viewing keyword hit results within documents during Relevance tagging does not work for the Japanese, Chinese, and Korean double-byte character sets.</span></span> 
  
## <a name="adding-highlighted-keywords"></a><span data-ttu-id="393a2-111">添加突出显示的关键字</span><span class="sxs-lookup"><span data-stu-id="393a2-111">Adding highlighted keywords</span></span>

1. <span data-ttu-id="393a2-112">在 "**相关性\>关联设置**" 选项卡中, 选择 "**突出显示的关键字**"。</span><span class="sxs-lookup"><span data-stu-id="393a2-112">In the **Relevance \> Relevance setup** tab, select **Highlighted keywords**.</span></span>
    
2. <span data-ttu-id="393a2-113">单击**+** 图标以添加关键字。</span><span class="sxs-lookup"><span data-stu-id="393a2-113">Click the **+** icon to add keywords.</span></span> <span data-ttu-id="393a2-114">将显示 "**添加新关键字**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="393a2-114">The **Add new keywords** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="393a2-115">在 "**关键字**" 中, 键入关键字列表, 用逗号分隔关键字。</span><span class="sxs-lookup"><span data-stu-id="393a2-115">In **Keywords**, type the keywords list, separating keywords with commas.</span></span> 
    
4. <span data-ttu-id="393a2-116">在 "**颜色**" 列表中, 选择要突出显示 "输入的关键字" 列表的颜色。</span><span class="sxs-lookup"><span data-stu-id="393a2-116">In the **Color** list, select the color to highlight the entered keywords list.</span></span> 
    
5. <span data-ttu-id="393a2-117">在 "**选择问题**" 列表中, 选择是否将关键字列表应用于 "所有问题" 或已选择的问题。</span><span class="sxs-lookup"><span data-stu-id="393a2-117">In the **Select issue** list, select whether to apply the keywords list to "All issues" or to selected issues.</span></span> 
    
6. <span data-ttu-id="393a2-118">在 "**说明**" 中, 键入关键字列表 (可选)。</span><span class="sxs-lookup"><span data-stu-id="393a2-118">In **Description**, type the keywords list (optional).</span></span>
    
    ![添加新的关键字](media/1683a71f-0875-48fc-b4ef-01f3b0e8e8e9.png)
  
7. <span data-ttu-id="393a2-120">完成后, 单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="393a2-120">Click **OK** when done.</span></span> <span data-ttu-id="393a2-121">创建的列表将添加到关键字列表表中, 并且可以编辑或删除。</span><span class="sxs-lookup"><span data-stu-id="393a2-121">The created list is added to the keywords list table and can be edited or deleted.</span></span> 
    
    ![相关性设置关键字列表](media/a05d5ec0-8bde-470d-97e2-456b169281d6.png)
  
<span data-ttu-id="393a2-123">用户定义的关键字将以关联\>标记中的指定颜色显示。</span><span class="sxs-lookup"><span data-stu-id="393a2-123">The user-defined keywords will be displayed, in the specified colors in Relevance \> Tag.</span></span> 
  
## <a name="specifying-relevance-setup-advanced-settings"></a><span data-ttu-id="393a2-124">指定相关性设置程序的高级设置</span><span class="sxs-lookup"><span data-stu-id="393a2-124">Specifying Relevance setup advanced settings</span></span>

<span data-ttu-id="393a2-125">这些设置会影响跟踪并决定关系图的相关性。</span><span class="sxs-lookup"><span data-stu-id="393a2-125">These settings affect the Track and Decide graphs in Relevance.</span></span>
  
1. <span data-ttu-id="393a2-126">在 "**相关性\>关联设置**" 选项卡中, 选择 "**高级设置**"。</span><span class="sxs-lookup"><span data-stu-id="393a2-126">In the **Relevance \> Relevance setup** tab, select **Advanced settings**.</span></span>
    
2. <span data-ttu-id="393a2-127">在 "**成本参数**" 对话框中, 进行以下选择:</span><span class="sxs-lookup"><span data-stu-id="393a2-127">In the **Cost parameters** dialog, make the following selections:</span></span> 
    
1. <span data-ttu-id="393a2-128">在 "**每小时成本评审 ($)** " 列表中, 选择以美元为单位的金额或接受默认值。</span><span class="sxs-lookup"><span data-stu-id="393a2-128">In the **Cost review per hour ($)** list, select the amount in dollars or accept the default.</span></span> 
    
2. <span data-ttu-id="393a2-129">在 "**按小时审阅的文件数**" 列表中, 选择 "金额" 或接受默认值。</span><span class="sxs-lookup"><span data-stu-id="393a2-129">In the **Number of files reviewed by hour** list, select the amount or accept the default.</span></span> 
    
    ![成本参数的相关性设置](media/bab7b5b7-6297-4e7c-b0a6-ba5aa8b21787.png)
  
3. <span data-ttu-id="393a2-131">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="393a2-131">Click **Save**.</span></span> <span data-ttu-id="393a2-132">将保存所选设置。</span><span class="sxs-lookup"><span data-stu-id="393a2-132">The selected settings are saved.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="393a2-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="393a2-133">See also</span></span>

[<span data-ttu-id="393a2-134">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="393a2-134">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="393a2-135">定义问题和分配用户</span><span class="sxs-lookup"><span data-stu-id="393a2-135">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="393a2-136">设置将已导入文件添加到的负载</span><span class="sxs-lookup"><span data-stu-id="393a2-136">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)


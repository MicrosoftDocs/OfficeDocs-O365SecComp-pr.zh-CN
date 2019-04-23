---
title: 将数据从一个工作集添加到另一个工作集
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e9e34d112cb84c27fec35e752eb2bfcbfe3136a3
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958233"
---
# <a name="add-data-to-a-working-set-from-another-working-set"></a><span data-ttu-id="a80ce-102">从另一个工作集向工作集添加数据</span><span class="sxs-lookup"><span data-stu-id="a80ce-102">Add data to a working set from another working set</span></span>
<span data-ttu-id="a80ce-103">在某些情况下, 可能需要从一个工作集 carve 出文档的一部分, 并在另一个工作集中单独处理这些文档的一部分。</span><span class="sxs-lookup"><span data-stu-id="a80ce-103">In some cases, it may be necessary to carve out a portion of documents from one working set and work with them individually in another working set.</span></span>  <span data-ttu-id="a80ce-104">如果您已在工作集中 culled 内容并希望对数据子集运行分析, 这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="a80ce-104">This is especially useful if you've culled content in a working set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="a80ce-105">使用以下工作流可将内容从一个工作集添加到另一个工作集。</span><span class="sxs-lookup"><span data-stu-id="a80ce-105">Use the following workflow to add content from one working set to another.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="a80ce-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="a80ce-106">Before you start</span></span>
<span data-ttu-id="a80ce-107">在开始之前, 您需要创建一个新的工作集。</span><span class="sxs-lookup"><span data-stu-id="a80ce-107">Before you start, you'll need to create a new working set.</span></span>  <span data-ttu-id="a80ce-108">可以通过 "*工作集*" 选项卡添加新的工作集。[了解详细信息](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-working-sets)。</span><span class="sxs-lookup"><span data-stu-id="a80ce-108">A new working set can be added through the *Working sets* tab [Learn more](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-working-sets).</span></span>

## <a name="step-1-identify-content-to-add-to-another-working-set"></a><span data-ttu-id="a80ce-109">步骤 1: 确定要添加到另一个工作集的内容</span><span class="sxs-lookup"><span data-stu-id="a80ce-109">Step 1: Identify content to add to another working set</span></span>
<span data-ttu-id="a80ce-110">您可以通过在文档网格中选择电子邮件和文档或搜索结果中的所有项目, 向工作集添加内容。</span><span class="sxs-lookup"><span data-stu-id="a80ce-110">You can add content to a working set by selecting emails and documents in the document grid or all items in a search result.</span></span>  <span data-ttu-id="a80ce-111">如果选择添加所选项目, 请选择这些项目并单击 "*操作*" 下拉选项, 然后*添加到另一个工作集*。</span><span class="sxs-lookup"><span data-stu-id="a80ce-111">If choosing to add selected items, select the items and click the *Action* drop down then *Add to another working set*.</span></span>

![添加到另一个工作集](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-workings-set"></a><span data-ttu-id="a80ce-113">步骤 2: 指定用于添加到另一个工作原理集的选项</span><span class="sxs-lookup"><span data-stu-id="a80ce-113">Step 2: Specify options for adding to another workings set</span></span>
<span data-ttu-id="a80ce-114">在 "*添加到另一个工作集选项*" 浮出控件中, 首先选择要向其添加项目的工作集。</span><span class="sxs-lookup"><span data-stu-id="a80ce-114">In the *Add to another working set options* flyout, first choose the working set you want to add the items to.</span></span>  <span data-ttu-id="a80ce-115">选择是否添加所有搜索结果或选定的项目。</span><span class="sxs-lookup"><span data-stu-id="a80ce-115">Choose whether to add All search results or Selected items.</span></span>  <span data-ttu-id="a80ce-116">其他信息提供选项以包含项目中的所有元数据, 以及是否应将文档标记包含在新的工作集中。</span><span class="sxs-lookup"><span data-stu-id="a80ce-116">Additional information provides options to include all metadata from the items and finally whether or not the document tags should be included in the new working set.</span></span>  <span data-ttu-id="a80ce-117">单击 *"确定"* 后, 将创建新作业以将内容添加到工作集, 您可以在 "[作业](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-jobs-ediscovery20)" 选项卡中监视该作业的![进度。添加到另一个工作集](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)</span><span class="sxs-lookup"><span data-stu-id="a80ce-117">After clicking *OK* a new job will be created to add the content to a working set, you can monitor the progress of that job in the [Jobs](https://docs.microsoft.com/en-us/office365/securitycompliance/compliance20/managing-jobs-ediscovery20) tab. ![Add to another working set](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)</span></span>

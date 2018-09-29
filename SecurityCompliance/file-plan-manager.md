---
title: 文件计划管理器概述
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 9/25/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 文件计划管理器提供了对保留标签和保留策略的高级管理功能，并提供了便于遍历整个内容生存期（从创建、协作、记录声明、保留到最终处置）中的标签活动和标签到内容活动的集成方式。
ms.openlocfilehash: 4feacf20444591f6da2d55a928a81e86b56c5d9a
ms.sourcegitcommit: 9f34ace6bbe3d5e07e24ebaae96613750869cddf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25019273"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="ddbb5-103">文件计划管理器概述</span><span class="sxs-lookup"><span data-stu-id="ddbb5-103">Overview of file plan manager</span></span>

<span data-ttu-id="ddbb5-104">文件计划管理器提供了对保留标签和保留策略的高级管理功能，并提供了便于遍历整个内容生存期（从创建、协作、记录声明、保留到最终处置）中的标签活动和标签到内容活动的集成方式。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![文件计划页面](media/file-plan-page.png)

## <a name="important-this-feature-is-currently-available-only-as-part-of-the-office-365-preview-program"></a><span data-ttu-id="ddbb5-106">重要提示：目前，只能在 Office 365 Preview 程序中使用此功能</span><span class="sxs-lookup"><span data-stu-id="ddbb5-106">Important: This feature is currently available only as part of the Office 365 Preview program</span></span>

<span data-ttu-id="ddbb5-107">仅当组织已注册 Office 365 Preview 程序时，此功能才会在租户中可用。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-107">You will see this feature in your tenant only if your organization has enrolled in the Office 365 Preview program.</span></span>

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="ddbb5-108">访问文件计划管理器</span><span class="sxs-lookup"><span data-stu-id="ddbb5-108">Accessing file plan manager</span></span>

<span data-ttu-id="ddbb5-109">若要访问文件计划管理器，需要满足以下两项要求：</span><span class="sxs-lookup"><span data-stu-id="ddbb5-109">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="ddbb5-110">拥有 Office 365 企业版 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-110">An Office 365 Enterprise E5 subscription with user licenses.</span></span>
- <span data-ttu-id="ddbb5-111">用户已分配有下面的安全与合规中心角色之一：</span><span class="sxs-lookup"><span data-stu-id="ddbb5-111">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span> 
    - <span data-ttu-id="ddbb5-112">保留管理者</span><span class="sxs-lookup"><span data-stu-id="ddbb5-112">Retention Manager</span></span>
    - <span data-ttu-id="ddbb5-113">仅拥有查看权限的保留管理者</span><span class="sxs-lookup"><span data-stu-id="ddbb5-113">View-only Retention Manager</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="ddbb5-114">浏览文件计划</span><span class="sxs-lookup"><span data-stu-id="ddbb5-114">Navigating your file plan</span></span>

<span data-ttu-id="ddbb5-115">使用文件计划管理器，可以更轻松地在一个视图中查看所有保留标签和保留策略的设置。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-115">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="ddbb5-116">请注意，文件计划中包含在文件计划内外创建的保留标签。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-116">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="ddbb5-117">“文件计划标签”\*\*\*\* 选项卡提供了以下附加信息和功能：</span><span class="sxs-lookup"><span data-stu-id="ddbb5-117">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="ddbb5-118">“标签设置”列</span><span class="sxs-lookup"><span data-stu-id="ddbb5-118">Label settings columns</span></span>
 
- <span data-ttu-id="ddbb5-p101">“依据”\*\*\*\* 列指明将启动保留期的触发器类型。有效值为：</span><span class="sxs-lookup"><span data-stu-id="ddbb5-p101">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="ddbb5-121">事件</span><span class="sxs-lookup"><span data-stu-id="ddbb5-121">Event</span></span>
    - <span data-ttu-id="ddbb5-122">创建时间</span><span class="sxs-lookup"><span data-stu-id="ddbb5-122">When created</span></span>
    - <span data-ttu-id="ddbb5-123">上次修改时间</span><span class="sxs-lookup"><span data-stu-id="ddbb5-123">When last modified</span></span>
    - <span data-ttu-id="ddbb5-124">标记时间</span><span class="sxs-lookup"><span data-stu-id="ddbb5-124">When labeled</span></span>
- <span data-ttu-id="ddbb5-p102">“记录”\*\*\*\* 列指明项是否在标签应用时成为已声明记录。有效值为：</span><span class="sxs-lookup"><span data-stu-id="ddbb5-p102">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="ddbb5-127">否</span><span class="sxs-lookup"><span data-stu-id="ddbb5-127">No</span></span>
    - <span data-ttu-id="ddbb5-128">是</span><span class="sxs-lookup"><span data-stu-id="ddbb5-128">Yes</span></span>
    - <span data-ttu-id="ddbb5-129">是(法规)</span><span class="sxs-lookup"><span data-stu-id="ddbb5-129">Yes(Regulatory)</span></span>
- <span data-ttu-id="ddbb5-p103">“保留”\*\*\*\* 列指明保留类型。有效值为：</span><span class="sxs-lookup"><span data-stu-id="ddbb5-p103">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="ddbb5-132">保留</span><span class="sxs-lookup"><span data-stu-id="ddbb5-132">Keep</span></span>
    - <span data-ttu-id="ddbb5-133">保留和删除</span><span class="sxs-lookup"><span data-stu-id="ddbb5-133">Keep and delete</span></span>
    - <span data-ttu-id="ddbb5-134">删除</span><span class="sxs-lookup"><span data-stu-id="ddbb5-134">Delete</span></span>
- <span data-ttu-id="ddbb5-p104">“处置”\*\*\*\* 列指明在保留期到期时如何处置内容。有效值为：</span><span class="sxs-lookup"><span data-stu-id="ddbb5-p104">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="ddbb5-137">Null</span><span class="sxs-lookup"><span data-stu-id="ddbb5-137">Null</span></span>
    - <span data-ttu-id="ddbb5-138">无操作</span><span class="sxs-lookup"><span data-stu-id="ddbb5-138">No action necessary.</span></span>
    - <span data-ttu-id="ddbb5-139">自动删除</span><span class="sxs-lookup"><span data-stu-id="ddbb5-139">Auto-delete</span></span>
    - <span data-ttu-id="ddbb5-140">需要评审(亦称为“处置评审”)</span><span class="sxs-lookup"><span data-stu-id="ddbb5-140">Review required (aka Disposition review)</span></span>

![文件计划中的“标签设置”](media/file-plan-label-columns.png)

### <a name="label-file-plan-descriptors-columns"></a><span data-ttu-id="ddbb5-142">标签文件计划描述符列</span><span class="sxs-lookup"><span data-stu-id="ddbb5-142">Label file plan descriptors columns</span></span>

<span data-ttu-id="ddbb5-p105">现在可以在保留标签的配置中添加更多信息。将文件计划描述符插入标签，可提升文件计划的可管理性和条理性。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-p105">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="ddbb5-p106">为了便于用户上手，文件计划管理器提供了一些现成值：“功能/部门”、“类别”、“权限类型”和“预配/引文”。可以在创建或编辑保留标签时，添加新的文件计划描述符值。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-p106">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="ddbb5-147">下图展示了创建或编辑保留标签时有关文件计划描述符的步骤。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-147">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![文件计划描述符](media/file-plan-descriptors.png)

<span data-ttu-id="ddbb5-149">下图展示了文件计划管理器的“标签”选项卡上的文件计划描述符列。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-149">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a><span data-ttu-id="ddbb5-151">导出文件计划的标签</span><span class="sxs-lookup"><span data-stu-id="ddbb5-151">Export labels out of your file plan</span></span>

<span data-ttu-id="ddbb5-152">在文件计划管理器中，可以将所有保留标签的详细信息都导出到 .csv 文件中，这样做有助于推动定期与组织中数据管理利益干系人一起执行合规性评审。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-152">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="ddbb5-153">若要导出所有保留标签，请依次转到“文件计划管理器”\*\*\*\*\>“文件计划操作”\*\*\*\*\>“导出标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-153">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![文件计划导出选项](media/file-plan-export-labels-option.png)

<span data-ttu-id="ddbb5-155">此时，包含所有现有保留标签的 \*.csv 文件打开。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-155">A \*.csv file containing all existing retention labels will open.</span></span>

![包含所有保留标签的 CSV 文件](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a><span data-ttu-id="ddbb5-157">向文件计划导入标签</span><span class="sxs-lookup"><span data-stu-id="ddbb5-157">Import labels into your file plan</span></span>

<span data-ttu-id="ddbb5-158">在文件计划管理器中，可以批量导入新标签，并能修改现有保留标签。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-158">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="ddbb5-159">若要导入新保留标签，并更新现有保留标签，请依次转到“文件计划管理器”\*\*\*\*\>“文件计划操作”\*\*\*\*\>“导入标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-159">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![文件计划导入选项](media/file-plan-import-labels-option.png)

![空白文件计划模板下载选项](media/file-plan-blank-template-option.png)

<span data-ttu-id="ddbb5-162">下载空白模板（或从当前文件计划导出开始）。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-162">Download a blank template (or start from an export of your current file plan).</span></span>

![在 Excel 中打开的空白文件计划模板](media/file-plan-blank-template.png)

<span data-ttu-id="ddbb5-164">填写模板（即将发布有关条目有效值的参考信息）。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-164">Fill-out the template (coming soon is reference information about valid values for entries).</span></span>

![填写了信息的文件计划模板](media/file-plan-filled-out-template.png)

<span data-ttu-id="ddbb5-166">上传已填写的模板，此时文件计划管理器会验证条目，并显示导入统计信息。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-166">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![文件计划导入统计信息](media/file-plan-import-statistics.png)

<span data-ttu-id="ddbb5-168">导入完成后，返回到文件计划管理器，将新标签分配到新策略或现有策略。</span><span class="sxs-lookup"><span data-stu-id="ddbb5-168">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![“发布标签”选项](media/file-plan-publish-labels-option.png)


---
title: 文件计划管理器概述
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 9/25/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 文件计划管理器提供了对保留标签和保留策略的高级管理功能，并提供了便于遍历整个内容生存期（从创建、协作、记录声明、保留到最终处置）中的标签活动和标签到内容活动的集成方式。
ms.openlocfilehash: d972a7ea6507e51c4efaaef30c98d55a87912417
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454824"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="d9d7e-103">文件计划管理器概述</span><span class="sxs-lookup"><span data-stu-id="d9d7e-103">Overview of file plan manager</span></span>

<span data-ttu-id="d9d7e-104">文件计划管理器提供了对保留标签和保留策略的高级管理功能，并提供了便于遍历整个内容生存期（从创建、协作、记录声明、保留到最终处置）中的标签活动和标签到内容活动的集成方式。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![文件计划页面](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="d9d7e-106">访问文件计划管理器</span><span class="sxs-lookup"><span data-stu-id="d9d7e-106">Accessing file plan manager</span></span>

<span data-ttu-id="d9d7e-107">若要访问文件计划管理器，需要满足以下两项要求：</span><span class="sxs-lookup"><span data-stu-id="d9d7e-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="d9d7e-108">拥有 Office 365 企业版 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="d9d7e-109">用户已分配有下面的安全与合规中心角色之一：</span><span class="sxs-lookup"><span data-stu-id="d9d7e-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span> 
    - <span data-ttu-id="d9d7e-110">保留管理者</span><span class="sxs-lookup"><span data-stu-id="d9d7e-110">Retention Manager</span></span>
    - <span data-ttu-id="d9d7e-111">仅拥有查看权限的保留管理者</span><span class="sxs-lookup"><span data-stu-id="d9d7e-111">View-only Retention Manager</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="d9d7e-112">浏览文件计划</span><span class="sxs-lookup"><span data-stu-id="d9d7e-112">Navigating your file plan</span></span>

<span data-ttu-id="d9d7e-113">使用文件计划管理器，可以更轻松地在一个视图中查看所有保留标签和保留策略的设置。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-113">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="d9d7e-114">请注意，文件计划中包含在文件计划内外创建的保留标签。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-114">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="d9d7e-115">“文件计划标签”\*\*\*\* 选项卡提供了以下附加信息和功能：</span><span class="sxs-lookup"><span data-stu-id="d9d7e-115">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="d9d7e-116">“标签设置”列</span><span class="sxs-lookup"><span data-stu-id="d9d7e-116">Label settings columns</span></span>
 
- <span data-ttu-id="d9d7e-p101">“依据”\*\*\*\* 列指明将启动保留期的触发器类型。有效值为：</span><span class="sxs-lookup"><span data-stu-id="d9d7e-p101">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="d9d7e-119">事件</span><span class="sxs-lookup"><span data-stu-id="d9d7e-119">Event</span></span>
    - <span data-ttu-id="d9d7e-120">创建时间</span><span class="sxs-lookup"><span data-stu-id="d9d7e-120">When created</span></span>
    - <span data-ttu-id="d9d7e-121">上次修改时间</span><span class="sxs-lookup"><span data-stu-id="d9d7e-121">When last modified</span></span>
    - <span data-ttu-id="d9d7e-122">标记时间</span><span class="sxs-lookup"><span data-stu-id="d9d7e-122">When labeled</span></span>
- <span data-ttu-id="d9d7e-p102">“记录”\*\*\*\* 列指明项是否在标签应用时成为已声明记录。有效值为：</span><span class="sxs-lookup"><span data-stu-id="d9d7e-p102">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="d9d7e-125">否</span><span class="sxs-lookup"><span data-stu-id="d9d7e-125">No</span></span>
    - <span data-ttu-id="d9d7e-126">是</span><span class="sxs-lookup"><span data-stu-id="d9d7e-126">Yes</span></span>
    - <span data-ttu-id="d9d7e-127">是(法规)</span><span class="sxs-lookup"><span data-stu-id="d9d7e-127">Yes(Regulatory)</span></span>
- <span data-ttu-id="d9d7e-p103">“保留”\*\*\*\* 列指明保留类型。有效值为：</span><span class="sxs-lookup"><span data-stu-id="d9d7e-p103">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="d9d7e-130">保留</span><span class="sxs-lookup"><span data-stu-id="d9d7e-130">Keep</span></span>
    - <span data-ttu-id="d9d7e-131">保留和删除</span><span class="sxs-lookup"><span data-stu-id="d9d7e-131">Keep and delete</span></span>
    - <span data-ttu-id="d9d7e-132">删除</span><span class="sxs-lookup"><span data-stu-id="d9d7e-132">Delete</span></span>
- <span data-ttu-id="d9d7e-p104">“处置”\*\*\*\* 列指明在保留期到期时如何处置内容。有效值为：</span><span class="sxs-lookup"><span data-stu-id="d9d7e-p104">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span> 
    - <span data-ttu-id="d9d7e-135">Null</span><span class="sxs-lookup"><span data-stu-id="d9d7e-135">null</span></span>
    - <span data-ttu-id="d9d7e-136">无操作</span><span class="sxs-lookup"><span data-stu-id="d9d7e-136">No action</span></span>
    - <span data-ttu-id="d9d7e-137">自动删除</span><span class="sxs-lookup"><span data-stu-id="d9d7e-137">Auto-delete</span></span>
    - <span data-ttu-id="d9d7e-138">需要评审(亦称为“处置评审”)</span><span class="sxs-lookup"><span data-stu-id="d9d7e-138">Review required (aka Disposition review)</span></span>

![文件计划中的“标签设置”](media/file-plan-label-columns.png)

### <a name="label-file-plan-descriptors-columns"></a><span data-ttu-id="d9d7e-140">标签文件计划描述符列</span><span class="sxs-lookup"><span data-stu-id="d9d7e-140">Label file plan descriptors columns</span></span>

<span data-ttu-id="d9d7e-p105">现在可以在保留标签的配置中添加更多信息。将文件计划描述符插入标签，可提升文件计划的可管理性和条理性。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-p105">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="d9d7e-p106">为了便于用户上手，文件计划管理器提供了一些现成值：“功能/部门”、“类别”、“权限类型”和“预配/引文”。可以在创建或编辑保留标签时，添加新的文件计划描述符值。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-p106">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="d9d7e-145">下图展示了创建或编辑保留标签时有关文件计划描述符的步骤。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-145">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![文件计划描述符](media/file-plan-descriptors.png)

<span data-ttu-id="d9d7e-147">下图展示了文件计划管理器的“标签”选项卡上的文件计划描述符列。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-147">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-labels-out-of-your-file-plan"></a><span data-ttu-id="d9d7e-149">导出文件计划的标签</span><span class="sxs-lookup"><span data-stu-id="d9d7e-149">Export labels out of your file plan</span></span>

<span data-ttu-id="d9d7e-150">在文件计划管理器中，可以将所有保留标签的详细信息都导出到 .csv 文件中，这样做有助于推动定期与组织中数据管理利益干系人一起执行合规性评审。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-150">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="d9d7e-151">若要导出所有保留标签，请依次转到“文件计划管理器”\*\*\*\*\>“文件计划操作”\*\*\*\*\>“导出标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-151">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![文件计划导出选项](media/file-plan-export-labels-option.png)

<span data-ttu-id="d9d7e-153">此时，包含所有现有保留标签的 \*.csv 文件打开。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-153">A \*.csv file containing all existing retention labels will open.</span></span>

![包含所有保留标签的 CSV 文件](media/file-plan-csv-file.png)

## <a name="import-labels-into-your-file-plan"></a><span data-ttu-id="d9d7e-155">向文件计划导入标签</span><span class="sxs-lookup"><span data-stu-id="d9d7e-155">Import labels into your file plan</span></span>

<span data-ttu-id="d9d7e-156">在文件计划管理器中，可以批量导入新标签，并能修改现有保留标签。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-156">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="d9d7e-157">若要导入新保留标签，并更新现有保留标签，请依次转到“文件计划管理器”\*\*\*\*\>“文件计划操作”\*\*\*\*\>“导入标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-157">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![文件计划导入选项](media/file-plan-import-labels-option.png)

![空白文件计划模板下载选项](media/file-plan-blank-template-option.png)

<span data-ttu-id="d9d7e-160">下载空白模板（或从当前文件计划导出开始）。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-160">Download a blank template (or start from an export of your current file plan).</span></span>

![在 Excel 中打开的空白文件计划模板](media/file-plan-blank-template.png)

<span data-ttu-id="d9d7e-162">填写模板（即将发布有关条目有效值的参考信息）。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-162">Fill-out the template (coming soon is reference information about valid values for entries).</span></span>

![填写了信息的文件计划模板](media/file-plan-filled-out-template.png)

<span data-ttu-id="d9d7e-164">上传已填写的模板，此时文件计划管理器会验证条目，并显示导入统计信息。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-164">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![文件计划导入统计信息](media/file-plan-import-statistics.png)

<span data-ttu-id="d9d7e-166">导入完成后，返回到文件计划管理器，将新标签分配到新策略或现有策略。</span><span class="sxs-lookup"><span data-stu-id="d9d7e-166">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![“发布标签”选项](media/file-plan-publish-labels-option.png)


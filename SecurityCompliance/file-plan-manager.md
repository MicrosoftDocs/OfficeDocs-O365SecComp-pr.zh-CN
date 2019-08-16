---
title: 文件计划管理器概述
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 文件计划管理器提供了对保留标签和保留标签策略的高级管理功能，并提供了便于遍历整个内容生存期（从创建、协作、记录声明、保留到最终处置）中的标签活动和标签到内容活动的集成方式。
ms.openlocfilehash: 38bfb1e6a6cde931804e518660ddf6c2b45205b0
ms.sourcegitcommit: f443de08971da2fe200a159b8efbed40effba125
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "36430009"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="cd5bd-103">文件计划管理器概述</span><span class="sxs-lookup"><span data-stu-id="cd5bd-103">Overview of file plan manager</span></span>

<span data-ttu-id="cd5bd-104">文件计划管理器提供了对保留标签和保留标签策略的高级管理功能，并提供了便于遍历整个内容生存期（从创建、协作、记录声明、保留到最终处置）中的标签活动和标签到内容活动的集成方式。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![文件计划页面](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="cd5bd-106">访问文件计划管理器</span><span class="sxs-lookup"><span data-stu-id="cd5bd-106">Accessing file plan manager</span></span>

<span data-ttu-id="cd5bd-107">若要访问文件计划管理器，需要满足以下两项要求：</span><span class="sxs-lookup"><span data-stu-id="cd5bd-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="cd5bd-108">拥有 Office 365 企业版 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="cd5bd-109">用户已分配有下面的安全与合规中心角色之一：</span><span class="sxs-lookup"><span data-stu-id="cd5bd-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span>
    - <span data-ttu-id="cd5bd-110">保留管理者</span><span class="sxs-lookup"><span data-stu-id="cd5bd-110">Retention Manager</span></span>
    - <span data-ttu-id="cd5bd-111">仅拥有查看权限的保留管理者</span><span class="sxs-lookup"><span data-stu-id="cd5bd-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="cd5bd-112">默认保留标签和标签策略</span><span class="sxs-lookup"><span data-stu-id="cd5bd-112">Default retention labels and label policy</span></span>

<span data-ttu-id="cd5bd-113">如果“安全与合规中心”没有保留标签，则第一次在左侧导航栏中选择**文件计划**时，将创建名为**默认数据治理发布策略**的标签策略。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="cd5bd-114">此标签策略包含三个保留标签：</span><span class="sxs-lookup"><span data-stu-id="cd5bd-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="cd5bd-115">**操作过程**</span><span class="sxs-lookup"><span data-stu-id="cd5bd-115">**Operational procedure**</span></span>
- <span data-ttu-id="cd5bd-116">**业务常规**</span><span class="sxs-lookup"><span data-stu-id="cd5bd-116">**Business general**</span></span>
- <span data-ttu-id="cd5bd-117">**合同协议**</span><span class="sxs-lookup"><span data-stu-id="cd5bd-117">**Contract agreement**</span></span>

<span data-ttu-id="cd5bd-118">这些保留标签仅为保留内容，而非为删除内容而配置。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="cd5bd-119">此标签策略将发布到整个公司，可以禁用或删除。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="cd5bd-120">可以通过查看保留策略的**创建的保留策略**和**创建的保留配置**活动的审核日志来判断谁打开了文件计划管理器并启动了首次运行体验。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="cd5bd-121">因客户反馈，我们已删除创建上述默认保留标签和保留标签策略的功能。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-121">Due to customer feedback, we have removed this feature that creates the default retention labels and label policy mentioned above.</span></span> <span data-ttu-id="cd5bd-122">如果你在 2019 年 4 月 11 日之前打开文件计划管理器，则将只能看到这些保留标签和保留标签策略。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-122">You will only see this policy and labels if you used file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="cd5bd-123">浏览文件计划</span><span class="sxs-lookup"><span data-stu-id="cd5bd-123">Navigating your file plan</span></span>

<span data-ttu-id="cd5bd-124">使用文件计划管理器，可以更轻松地在一个视图中查看所有保留标签和保留策略的设置。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="cd5bd-125">请注意，文件计划中包含在文件计划内外创建的保留标签。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="cd5bd-126">“文件计划标签”\*\*\*\* 选项卡提供了以下附加信息和功能：</span><span class="sxs-lookup"><span data-stu-id="cd5bd-126">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="cd5bd-127">“标签设置”列</span><span class="sxs-lookup"><span data-stu-id="cd5bd-127">Label settings columns</span></span>

- <span data-ttu-id="cd5bd-p103">“依据”\*\*\*\* 列指明将启动保留期的触发器类型。有效值为：</span><span class="sxs-lookup"><span data-stu-id="cd5bd-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="cd5bd-130">事件</span><span class="sxs-lookup"><span data-stu-id="cd5bd-130">Event</span></span>
    - <span data-ttu-id="cd5bd-131">创建时间</span><span class="sxs-lookup"><span data-stu-id="cd5bd-131">When created</span></span>
    - <span data-ttu-id="cd5bd-132">上次修改时间</span><span class="sxs-lookup"><span data-stu-id="cd5bd-132">When last modified</span></span>
    - <span data-ttu-id="cd5bd-133">标记时间</span><span class="sxs-lookup"><span data-stu-id="cd5bd-133">When labeled</span></span>
- <span data-ttu-id="cd5bd-p104">“记录”\*\*\*\* 列指明项是否在标签应用时成为已声明记录。有效值为：</span><span class="sxs-lookup"><span data-stu-id="cd5bd-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="cd5bd-136">否</span><span class="sxs-lookup"><span data-stu-id="cd5bd-136">No</span></span>
    - <span data-ttu-id="cd5bd-137">是</span><span class="sxs-lookup"><span data-stu-id="cd5bd-137">Yes</span></span>
    - <span data-ttu-id="cd5bd-138">是(法规)</span><span class="sxs-lookup"><span data-stu-id="cd5bd-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="cd5bd-p105">“保留”\*\*\*\* 列指明保留类型。有效值为：</span><span class="sxs-lookup"><span data-stu-id="cd5bd-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="cd5bd-141">保留</span><span class="sxs-lookup"><span data-stu-id="cd5bd-141">Keep</span></span>
    - <span data-ttu-id="cd5bd-142">保留和删除</span><span class="sxs-lookup"><span data-stu-id="cd5bd-142">Keep and delete</span></span>
    - <span data-ttu-id="cd5bd-143">删除</span><span class="sxs-lookup"><span data-stu-id="cd5bd-143">Delete</span></span>
- <span data-ttu-id="cd5bd-p106">“处置”\*\*\*\* 列指明在保留期到期时如何处置内容。有效值为：</span><span class="sxs-lookup"><span data-stu-id="cd5bd-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="cd5bd-146">Null</span><span class="sxs-lookup"><span data-stu-id="cd5bd-146">null</span></span>
    - <span data-ttu-id="cd5bd-147">无操作</span><span class="sxs-lookup"><span data-stu-id="cd5bd-147">No action</span></span>
    - <span data-ttu-id="cd5bd-148">自动删除</span><span class="sxs-lookup"><span data-stu-id="cd5bd-148">Auto-delete</span></span>
    - <span data-ttu-id="cd5bd-149">需要评审(亦称为“处置评审”)</span><span class="sxs-lookup"><span data-stu-id="cd5bd-149">Review required (aka Disposition review)</span></span>

![文件计划中的“标签设置”](media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="cd5bd-151">保留标签文件计划描述符列</span><span class="sxs-lookup"><span data-stu-id="cd5bd-151">Label file plan descriptors columns</span></span>

<span data-ttu-id="cd5bd-p107">现在可以在保留标签的配置中添加更多信息。将文件计划描述符插入保留标签，可提升文件计划的可管理性和条理性。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-p107">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="cd5bd-p108">为了便于用户上手，文件计划管理器提供了一些现成值：“功能/部门”、“类别”、“权限类型”和“预配/引文”。可以在创建或编辑保留标签时，添加新的文件计划描述符值。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-p108">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="cd5bd-156">下图展示了创建或编辑保留标签时有关文件计划描述符的步骤。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-156">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![文件计划描述符](media/file-plan-descriptors.png)

<span data-ttu-id="cd5bd-158">下图展示了文件计划管理器的“标签”选项卡上的文件计划描述符列。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-158">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="cd5bd-160">导出所有现有保留标签以分析和/或执行离线评审</span><span class="sxs-lookup"><span data-stu-id="cd5bd-160">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="cd5bd-161">在文件计划管理器中，可以将所有保留标签的详细信息都导出到 .csv 文件中，这样做有助于推动定期与组织中数据管理利益干系人一起执行合规性评审。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-161">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="cd5bd-162">若要导出所有保留标签，请依次转到“文件计划管理器”\*\*\*\*\>“文件计划操作”\*\*\*\*\>“导出标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-162">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![文件计划导出选项](media/file-plan-export-labels-option.png)

<span data-ttu-id="cd5bd-164">此时，包含所有现有保留标签的 \*.csv 文件打开。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-164">A \*.csv file containing all existing retention labels will open.</span></span>

![包含所有保留标签的 CSV 文件](media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="cd5bd-166">向文件计划导入保留标签</span><span class="sxs-lookup"><span data-stu-id="cd5bd-166">Import labels into your file plan</span></span>

<span data-ttu-id="cd5bd-167">在文件计划管理器中，可以批量导入新保留标签，并能修改现有保留标签。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-167">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="cd5bd-168">若要导入新保留标签，并更新现有保留标签，请依次转到“**文件计划管理器**”\>“**文件计划操作**”\>“**导入标签**”。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-168">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![文件计划导入选项](media/file-plan-import-labels-option.png)

![空白文件计划模板下载选项](media/file-plan-blank-template-option.png)

<span data-ttu-id="cd5bd-171">下载空白模板（或从当前文件计划导出开始）。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-171">Download a blank template (or start from an export of your current file plan).</span></span>

![在 Excel 中打开的空白文件计划模板](media/file-plan-blank-template.png)

<span data-ttu-id="cd5bd-173">填写模板。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-173">Fill-out the template.</span></span> <span data-ttu-id="cd5bd-174">此表提供了有效值。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-174">This table provides valid values.</span></span>

|<span data-ttu-id="cd5bd-175">**属性**</span><span class="sxs-lookup"><span data-stu-id="cd5bd-175">**Property**</span></span>|<span data-ttu-id="cd5bd-176">**类型**</span><span class="sxs-lookup"><span data-stu-id="cd5bd-176">**Type**</span></span>|<span data-ttu-id="cd5bd-177">**有效值**</span><span class="sxs-lookup"><span data-stu-id="cd5bd-177">**Valid values**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cd5bd-178">LabelName</span><span class="sxs-lookup"><span data-stu-id="cd5bd-178">LabelName</span></span>|<span data-ttu-id="cd5bd-179">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-179">String</span></span>|<span data-ttu-id="cd5bd-180">如果值包含空格，请使用双引号 (") 将此值括起来。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-180">If the value contains spaces, enclose the value in quotation marks (").</span></span>|
|<span data-ttu-id="cd5bd-181">评论</span><span class="sxs-lookup"><span data-stu-id="cd5bd-181">Comment</span></span>|<span data-ttu-id="cd5bd-182">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-182">String</span></span>|<span data-ttu-id="cd5bd-183">如果值包含空格，请使用双引号 (") 将此值括起来。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-183">If the value contains spaces, enclose the value in quotation marks (").</span></span> |
|<span data-ttu-id="cd5bd-184">Notes</span><span class="sxs-lookup"><span data-stu-id="cd5bd-184">Notes</span></span>|<span data-ttu-id="cd5bd-185">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-185">String</span></span>|<span data-ttu-id="cd5bd-186">自定义</span><span class="sxs-lookup"><span data-stu-id="cd5bd-186">Custom</span></span>|
|<span data-ttu-id="cd5bd-187">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="cd5bd-187">IsRecordLabel</span></span>|<span data-ttu-id="cd5bd-188">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-188">String</span></span>|<span data-ttu-id="cd5bd-189">$true：标签是记录标签。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-189">The 
                IsRecordLabel
              parameter specifies whether the label is a record label.</span></span></br><span data-ttu-id="cd5bd-190">$false：标签不是记录标签。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-190">$false: The label isn't a record label.</span></span> <span data-ttu-id="cd5bd-191">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-191">This is the default value.</span></span>|
|<span data-ttu-id="cd5bd-192">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="cd5bd-192">RetentionAction</span></span>|<span data-ttu-id="cd5bd-193">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-193">String</span></span>|<span data-ttu-id="cd5bd-194">Delete</span><span class="sxs-lookup"><span data-stu-id="cd5bd-194">Delete</span></span></br><span data-ttu-id="cd5bd-195">Keep</span><span class="sxs-lookup"><span data-stu-id="cd5bd-195">Keep</span></span></br><span data-ttu-id="cd5bd-196">KeepAndDelete</span><span class="sxs-lookup"><span data-stu-id="cd5bd-196">KeepAndDelete</span></span> |
|<span data-ttu-id="cd5bd-197">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="cd5bd-197">RetentionDuration</span></span>|<span data-ttu-id="cd5bd-198">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-198">String</span></span>|<span data-ttu-id="cd5bd-199">此属性指定内容保留的天数。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-199">The RetentionDuration parameter specifies the number of days to retain the content.</span></span> <span data-ttu-id="cd5bd-200">有效值是：</span><span class="sxs-lookup"><span data-stu-id="cd5bd-200">Valid values are:</span></span></br><span data-ttu-id="cd5bd-201">正整数。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-201">A positive integer.</span></span></br><span data-ttu-id="cd5bd-202">值不受限制。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-202">The default value is unlimited.</span></span>|
|<span data-ttu-id="cd5bd-203">RetentionType</span><span class="sxs-lookup"><span data-stu-id="cd5bd-203">RetentionType</span></span>|<span data-ttu-id="cd5bd-204">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-204">String</span></span>|<span data-ttu-id="cd5bd-205">此属性指定保留期限是从内容创建日期、标记的日期还是从上次修改日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-205">The RetentionType parameter specifies whether the retention duration is calculated  from the content creation date, tagged date, or last modification date.</span></span> <span data-ttu-id="cd5bd-206">有效值是：</span><span class="sxs-lookup"><span data-stu-id="cd5bd-206">Valid values are:</span></span></br><span data-ttu-id="cd5bd-207">CreationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="cd5bd-207">CreationAgeInDays</span></span></br><span data-ttu-id="cd5bd-208">EventAgeInDays</span><span class="sxs-lookup"><span data-stu-id="cd5bd-208">EventAgeInDays</span></span></br><span data-ttu-id="cd5bd-209">ModificationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="cd5bd-209">ModificationAgeInDays</span></span></br><span data-ttu-id="cd5bd-210">TaggedAgeInDays</span><span class="sxs-lookup"><span data-stu-id="cd5bd-210">TaggedAgeInDays</span></span> |
|<span data-ttu-id="cd5bd-211">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="cd5bd-211">ReviewerEmail</span></span>|<span data-ttu-id="cd5bd-212">SmtpAddress[]</span><span class="sxs-lookup"><span data-stu-id="cd5bd-212">SmtpAddress</span></span>|<span data-ttu-id="cd5bd-213">此属性指定 Delete 和 KeepAndDelete 保留操作的审阅者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-213">The ReviewerEmail parameter specifies the email address of a reviewer for Delete and KeepAndDelete retention actions.</span></span> <span data-ttu-id="cd5bd-214">可以指定多个电子邮件地址，中间用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-214">You can specify multiple email addresses separated by commas.</span></span>|
|<span data-ttu-id="cd5bd-215">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="cd5bd-215">ReferenceId</span></span>|<span data-ttu-id="cd5bd-216">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-216">String</span></span>|<span data-ttu-id="cd5bd-217">自定义</span><span class="sxs-lookup"><span data-stu-id="cd5bd-217">Custom</span></span>|
|<span data-ttu-id="cd5bd-218">Departmentname</span><span class="sxs-lookup"><span data-stu-id="cd5bd-218">Departmentname</span></span>|<span data-ttu-id="cd5bd-219">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-219">String</span></span>|<span data-ttu-id="cd5bd-220">自定义</span><span class="sxs-lookup"><span data-stu-id="cd5bd-220">Custom</span></span>|
|<span data-ttu-id="cd5bd-221">类别</span><span class="sxs-lookup"><span data-stu-id="cd5bd-221">Category</span></span>|<span data-ttu-id="cd5bd-222">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-222">String</span></span>|<span data-ttu-id="cd5bd-223">自定义</span><span class="sxs-lookup"><span data-stu-id="cd5bd-223">Custom</span></span>|
|<span data-ttu-id="cd5bd-224">SubCategory</span><span class="sxs-lookup"><span data-stu-id="cd5bd-224">SubCategory</span></span>|<span data-ttu-id="cd5bd-225">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-225">String</span></span>|<span data-ttu-id="cd5bd-226">自定义</span><span class="sxs-lookup"><span data-stu-id="cd5bd-226">Custom</span></span>|
|<span data-ttu-id="cd5bd-227">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="cd5bd-227">AuthorityType</span></span>|<span data-ttu-id="cd5bd-228">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-228">String</span></span>|<span data-ttu-id="cd5bd-229">自定义</span><span class="sxs-lookup"><span data-stu-id="cd5bd-229">Custom</span></span>|
|<span data-ttu-id="cd5bd-230">CitationName</span><span class="sxs-lookup"><span data-stu-id="cd5bd-230">CitationName</span></span>|<span data-ttu-id="cd5bd-231">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-231">String</span></span>|<span data-ttu-id="cd5bd-232">自定义</span><span class="sxs-lookup"><span data-stu-id="cd5bd-232">Custom</span></span>|
|<span data-ttu-id="cd5bd-233">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="cd5bd-233">CitationUrl</span></span>|<span data-ttu-id="cd5bd-234">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-234">String</span></span>|<span data-ttu-id="cd5bd-235">自定义</span><span class="sxs-lookup"><span data-stu-id="cd5bd-235">Custom</span></span>|
|<span data-ttu-id="cd5bd-236">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="cd5bd-236">CitationJurisdiction</span></span>|<span data-ttu-id="cd5bd-237">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-237">String</span></span>|<span data-ttu-id="cd5bd-238">自定义</span><span class="sxs-lookup"><span data-stu-id="cd5bd-238">Custom</span></span>|
|<span data-ttu-id="cd5bd-239">Regulatory</span><span class="sxs-lookup"><span data-stu-id="cd5bd-239">Regulatory</span></span>|<span data-ttu-id="cd5bd-240">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-240">String</span></span>|<span data-ttu-id="cd5bd-241">自定义</span><span class="sxs-lookup"><span data-stu-id="cd5bd-241">Custom</span></span>|
|<span data-ttu-id="cd5bd-242">EventType</span><span class="sxs-lookup"><span data-stu-id="cd5bd-242">EventType</span></span>|<span data-ttu-id="cd5bd-243">String</span><span class="sxs-lookup"><span data-stu-id="cd5bd-243">String</span></span>|<span data-ttu-id="cd5bd-244">此属性指定与标签关联的保留规则。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-244">This property specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="cd5bd-245">可以使用唯一标识该规则的任何值。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-245">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="cd5bd-246">例如：</span><span class="sxs-lookup"><span data-stu-id="cd5bd-246">For example:</span></span></br><span data-ttu-id="cd5bd-247">名称</span><span class="sxs-lookup"><span data-stu-id="cd5bd-247">Name</span></span></br><span data-ttu-id="cd5bd-248">可分辨名称 (DN)</span><span class="sxs-lookup"><span data-stu-id="cd5bd-248">Distinguished name (DN)</span></span></br><span data-ttu-id="cd5bd-249">GUID</span><span class="sxs-lookup"><span data-stu-id="cd5bd-249">GUID</span></span> </br><span data-ttu-id="cd5bd-250">可使用 [Get-RetentionComplianceRule](https://docs.microsoft.com/zh-CN/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet 来查看可用的保留规则。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-250">You can use the [Get-RetentionComplianceRule](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available retention rules.</span></span>|

![填写了信息的文件计划模板](media/file-plan-filled-out-template.png)

<span data-ttu-id="cd5bd-252">上传已填写的模板，此时文件计划管理器会验证条目，并显示导入统计信息。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-252">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![文件计划导入统计信息](media/file-plan-import-statistics.png)

<span data-ttu-id="cd5bd-254">如果出现验证错误，文件计划导入将继续验证导入文件中的每个条目，并显示导入文件中引用行/行编号的所有错误，复制显示的错误结果，以便能够轻松返回导入文件并更正错误。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-254">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easilly return to the import file and correct the errors.</span></span> 

<span data-ttu-id="cd5bd-255">导入完成后，返回到文件计划管理器，以将新保留标签与新的或现有的保留标签策略相关联。</span><span class="sxs-lookup"><span data-stu-id="cd5bd-255">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![“发布标签”选项](media/file-plan-publish-labels-option.png)


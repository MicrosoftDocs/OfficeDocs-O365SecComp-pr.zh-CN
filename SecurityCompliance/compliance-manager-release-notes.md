---
title: Microsoft 合规性管理器发行说明
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性管理器是 Microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使你能够跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。
ms.openlocfilehash: 196118972079f83ba2f6a59ce1ae1514d9616599
ms.sourcegitcommit: 1947ad3c0dde9163ba9b6834d8b38bd04b4264a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "36643234"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="b1abb-104">合规性管理器的发行说明 (预览)</span><span class="sxs-lookup"><span data-stu-id="b1abb-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="b1abb-105">合规性管理器的公共预览版为您提供早期访问即将推出的功能和更新。</span><span class="sxs-lookup"><span data-stu-id="b1abb-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="b1abb-106">您可以使用[服务信任门户](https://servicetrust.microsoft.com)上的更新的[合规性管理器](https://servicetrust.microsoft.com/ComplianceManager)工具来跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。</span><span class="sxs-lookup"><span data-stu-id="b1abb-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="b1abb-107">合规性管理器中的新增功能 (预览)</span><span class="sxs-lookup"><span data-stu-id="b1abb-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="b1abb-108">**与 Microsoft 安全分数的集成:** 合规性管理器通过将客户管理的操作映射到50以上的安全分数操作, 支持与[Microsoft 安全分数](microsoft-secure-score.md)的集成。</span><span class="sxs-lookup"><span data-stu-id="b1abb-108">**Integration with Microsoft Secure Score:** Compliance Manager supports integration with [Microsoft Secure Score](microsoft-secure-score.md) by mapping customer-managed Actions to more than 50 Secure Score actions.</span></span> <span data-ttu-id="b1abb-109">在安全分数中完成映射的操作后, 相应的合规性管理器操作将自动更新。</span><span class="sxs-lookup"><span data-stu-id="b1abb-109">When you complete a mapped action in Secure Score, the corresponding Compliance Manager Action automatically updates.</span></span>

- <span data-ttu-id="b1abb-110">**导入自定义评估:** 除了内置评估, 合规性管理器现在还支持导入自定义模板。</span><span class="sxs-lookup"><span data-stu-id="b1abb-110">**Import custom Assessments:** In addition to built-in Assessments, Compliance Manager now supports importing custom Templates.</span></span> <span data-ttu-id="b1abb-111">您可以为任何产品或服务以及任何标准或法规创建自定义评估。</span><span class="sxs-lookup"><span data-stu-id="b1abb-111">You can create custom Assessments for any product or service and any standard or regulation.</span></span>

- <span data-ttu-id="b1abb-112">**Actions 项:** 操作项现在是单个项目, 并且许多包含来自 Microsoft 安全分数图形 API 的遥测集合。</span><span class="sxs-lookup"><span data-stu-id="b1abb-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="b1abb-113">在可能的情况下, 技术操作建议现在有指向 Office 365 服务中适用配置页面的链接。</span><span class="sxs-lookup"><span data-stu-id="b1abb-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="b1abb-114">**租户管理:** 用于管理合规性管理器中的新数据元素的新界面 (预览):</span><span class="sxs-lookup"><span data-stu-id="b1abb-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="b1abb-115">**维:** 查看、添加和自定义模板、评估和操作项的元数据, 以允许您为筛选器创建自定义透视。</span><span class="sxs-lookup"><span data-stu-id="b1abb-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="b1abb-116">**所有者:** 为每个即席项目指定一个所有者。</span><span class="sxs-lookup"><span data-stu-id="b1abb-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="b1abb-117">**客户操作:** 管理合规性管理器 (预览版) 中包含的操作项的完整列表, 并启用/禁用与安全得分集成的操作项的安全分数监视。</span><span class="sxs-lookup"><span data-stu-id="b1abb-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

- <span data-ttu-id="b1abb-118">**更新了合规性分数**: 该方法已更改为支持与 Microsoft 安全分数同步。</span><span class="sxs-lookup"><span data-stu-id="b1abb-118">**Updated Compliance Score**: The methodology has changed to support syncing with Microsoft Secure Score.</span></span> <span data-ttu-id="b1abb-119">评分系统删除了 Microsoft 托管的控制积分, 并仅侧重于客户托管的控制措施的完成。</span><span class="sxs-lookup"><span data-stu-id="b1abb-119">The scoring system removes the Microsoft-managed control credits and focuses solely on the completion of customer-managed controls.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="b1abb-120">合规性管理器中的已知问题 (预览)</span><span class="sxs-lookup"><span data-stu-id="b1abb-120">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="b1abb-121">以下各节介绍了即将在即将发布的合规性管理器中解决的已知问题。</span><span class="sxs-lookup"><span data-stu-id="b1abb-121">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="b1abb-122">合规性分数</span><span class="sxs-lookup"><span data-stu-id="b1abb-122">Compliance Score</span></span>

- <span data-ttu-id="b1abb-123">对于标记为**不在范围**内的交办事项, 分配给措施项的分数不会从合规性分数计算中排除。</span><span class="sxs-lookup"><span data-stu-id="b1abb-123">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the Compliance Score calculation.</span></span> <span data-ttu-id="b1abb-124">标记为**不在范围内的**操作项不会增加合规性分数。</span><span class="sxs-lookup"><span data-stu-id="b1abb-124">Action Items marked **Not in Scope** do not increase your Compliance Score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="b1abb-125">安全功能分数</span><span class="sxs-lookup"><span data-stu-id="b1abb-125">Secure Score</span></span>

- <span data-ttu-id="b1abb-126">安全分数结果不适用于某些 Microsoft 365 和 Office 365 订阅中的某些操作项。</span><span class="sxs-lookup"><span data-stu-id="b1abb-126">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="b1abb-127">在这些情况下, 安全得分结果为 "无法检测到"。</span><span class="sxs-lookup"><span data-stu-id="b1abb-127">The Secure Score result is 'Could not be detected' in these cases.</span></span>
- <span data-ttu-id="b1abb-128">有时, 不完成相应策略和操作项目的安全分数结果。</span><span class="sxs-lookup"><span data-stu-id="b1abb-128">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="b1abb-129">Microsoft 托管控件</span><span class="sxs-lookup"><span data-stu-id="b1abb-129">Microsoft-managed Controls</span></span>

- <span data-ttu-id="b1abb-130">Microsoft 托管控件的测试日期不会显示在 UI 中, 即使在评估中也不会如此。</span><span class="sxs-lookup"><span data-stu-id="b1abb-130">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="b1abb-131">若要查看测试日期信息, 必须导出该评估。</span><span class="sxs-lookup"><span data-stu-id="b1abb-131">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="b1abb-132">自定义</span><span class="sxs-lookup"><span data-stu-id="b1abb-132">Customization</span></span>

- <span data-ttu-id="b1abb-133">通过添加自定义控件, 可以向现有控件系列添加新控件, 但不允许添加新的控件系列。</span><span class="sxs-lookup"><span data-stu-id="b1abb-133">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="b1abb-134">此版本不支持链接操作项或向评估添加操作项或控件。</span><span class="sxs-lookup"><span data-stu-id="b1abb-134">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="b1abb-135">如果创建自定义操作, 则无法对其进行编辑或将其删除。</span><span class="sxs-lookup"><span data-stu-id="b1abb-135">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="b1abb-136">控制系列未在评估中显示</span><span class="sxs-lookup"><span data-stu-id="b1abb-136">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="b1abb-137">导入模板时, 基于该模板的所有评估都会反映属于该模板的所有控制系列。</span><span class="sxs-lookup"><span data-stu-id="b1abb-137">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="b1abb-138">但是, 如果向模板中添加新的控制系列, 则任何现有评估都不会反映所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b1abb-138">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="b1abb-139">仅由更新后的模板创建的新评估将反映所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b1abb-139">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="filters"></a><span data-ttu-id="b1abb-140">筛选器</span><span class="sxs-lookup"><span data-stu-id="b1abb-140">Filters</span></span>

- <span data-ttu-id="b1abb-141">对交办事项或控件的筛选不会始终如一地生成正确的结果。</span><span class="sxs-lookup"><span data-stu-id="b1abb-141">Filtering on Action Items or Controls does not consistently produce correct results.</span></span>

### <a name="templates"></a><span data-ttu-id="b1abb-142">模板</span><span class="sxs-lookup"><span data-stu-id="b1abb-142">Templates</span></span>

- <span data-ttu-id="b1abb-143">存档的模板是可编辑的, 不应是可编辑的。</span><span class="sxs-lookup"><span data-stu-id="b1abb-143">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="b1abb-144">锁定的模板允许在不应进行评估时创建评估。</span><span class="sxs-lookup"><span data-stu-id="b1abb-144">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="b1abb-145">锁定模板旨在防止它用于创建评估。</span><span class="sxs-lookup"><span data-stu-id="b1abb-145">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="b1abb-146">导出</span><span class="sxs-lookup"><span data-stu-id="b1abb-146">Export</span></span>

- <span data-ttu-id="b1abb-147">将模板状态设置为 "已**导入**" 或 "**待审批**" 时, 模板导出到 JSON 失败。</span><span class="sxs-lookup"><span data-stu-id="b1abb-147">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="b1abb-148">支持的浏览器</span><span class="sxs-lookup"><span data-stu-id="b1abb-148">Supported browsers</span></span>

- <span data-ttu-id="b1abb-149">Microsoft Edge、Chrome 和 Safari 的最新版本均受支持。</span><span class="sxs-lookup"><span data-stu-id="b1abb-149">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="b1abb-150">在刷新浏览器之前, 可能会出现更新后的数据未出现的情况。</span><span class="sxs-lookup"><span data-stu-id="b1abb-150">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="b1abb-151">Microsoft Edge 的预览版本不受支持, 但没有已知问题。</span><span class="sxs-lookup"><span data-stu-id="b1abb-151">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="b1abb-152">不支持 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="b1abb-152">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="b1abb-153">会话超时</span><span class="sxs-lookup"><span data-stu-id="b1abb-153">Session timeout</span></span>

- <span data-ttu-id="b1abb-154">会话超时时, 可能会出现 "发生错误" 错误。</span><span class="sxs-lookup"><span data-stu-id="b1abb-154">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="b1abb-155">若要解决此问题, 请转到[合规性管理器](https://servicetrust.microsoft.com/ComplianceManager), 然后重新登录。</span><span class="sxs-lookup"><span data-stu-id="b1abb-155">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="b1abb-156">语言支持</span><span class="sxs-lookup"><span data-stu-id="b1abb-156">Language support</span></span>

- <span data-ttu-id="b1abb-157">所有网页都不支持所有语言。</span><span class="sxs-lookup"><span data-stu-id="b1abb-157">All languages are not supported for all webpages.</span></span> <span data-ttu-id="b1abb-158">如果本地语言不受支持, 请在美国英语中查看。</span><span class="sxs-lookup"><span data-stu-id="b1abb-158">If your local language is unsupported, view in US English.</span></span>
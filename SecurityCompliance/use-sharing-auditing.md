---
title: 审核共享以查找与外部用户共享的资源
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共享是 SharePoint Online 和 OneDrive for business 中的关键活动。 管理员现在可以在 Office 365 审核日志中使用共享审核来确定如何在组织中使用共享。 '
ms.openlocfilehash: e2865d35e988d8c0e42a6c51f78507db8b170d4c
ms.sourcegitcommit: b262d40f6daf06be26e7586f37b736e09f8a4511
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35435233"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="2e7b6-104">审核共享以查找与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="2e7b6-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="2e7b6-105">共享是 SharePoint Online 和 OneDrive for business 中的关键活动, 并在 Office 365 组织中广泛使用。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-105">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations.</span></span> <span data-ttu-id="2e7b6-106">管理员现在可以在 Office 365 审核日志中使用共享审核来确定如何在组织中使用共享。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-106">Administrators can now use sharing auditing in the Office 365 audit log to determine how sharing is being used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="2e7b6-107">SharePoint 共享架构</span><span class="sxs-lookup"><span data-stu-id="2e7b6-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="2e7b6-108">共享事件 (不包括共享策略和共享链接事件) 与文件和文件夹相关的事件有一个主要的不同之处: 一个用户正在采取对另一个用户有影响的操作。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-108">Sharing events (excluding sharing policy and sharing link events) are different from file- and folder-related events in one primary way: one user is taking an action that has some effect on another user.</span></span> <span data-ttu-id="2e7b6-109">例如, 用户 A 向用户 B 授予对文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-109">For example, User A gives User B access to a file.</span></span> <span data-ttu-id="2e7b6-110">在此示例中, 用户 A 是*作用用户*, 而用户 B 是*目标用户*。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-110">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="2e7b6-111">在 SharePoint 文件架构中, 作用用户的操作仅影响文件本身。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-111">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="2e7b6-112">当用户 A 打开文件时, **FileAccessed**事件中所需的唯一信息是操作用户。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-112">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="2e7b6-113">为了解决这种差异, 有一个称为*SharePoint 共享架构*的单独架构, 可捕获有关共享事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-113">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="2e7b6-114">这可确保管理员能够更好地了解共享资源的人员和共享资源的用户。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-114">This ensures that administrators have more insight into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="2e7b6-115">共享架构在与共享事件相关的审核日志中提供了两个附加字段:</span><span class="sxs-lookup"><span data-stu-id="2e7b6-115">The Sharing schema provides two additional fields in the audit log related to sharing events:</span></span> 
  
- <span data-ttu-id="2e7b6-116">**TargetUserOrGroupName** –存储与之共享资源的目标用户或组的 UPN 或名称 (上一示例中的用户 B)。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-116">**TargetUserOrGroupName** – Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 
    
- <span data-ttu-id="2e7b6-117">**TargetUserOrGroupType** –标识目标用户或组是否为成员、来宾、组或合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-117">**TargetUserOrGroupType** – Identifies whether the target user or group is a Member, Guest, Group, or Partner.</span></span> 
    
<span data-ttu-id="2e7b6-118">除了 Office 365 审核日志架构 (如用户、操作和日期) 以外的其他属性, 这两个字段还可以详细说明*哪些*用户共享了哪些用户与*谁*共享了*哪些*资源。 \*\*</span><span class="sxs-lookup"><span data-stu-id="2e7b6-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="2e7b6-119">还有另一个架构属性, 对共享情景很重要。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-119">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="2e7b6-120">**EventData**属性存储有关共享事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-120">The **EventData** property stores additional information about sharing events.</span></span> <span data-ttu-id="2e7b6-121">例如, 当用户与其他用户共享网站时, 可以通过将目标用户添加到 SharePoint 组来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-121">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="2e7b6-122">**EventData**属性捕获此附加信息, 以便为管理员提供上下文。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-122">The **EventData** property captures this additional information to provide context for administrators.</span></span> 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a><span data-ttu-id="2e7b6-123">SharePoint 共享模型和共享事件</span><span class="sxs-lookup"><span data-stu-id="2e7b6-123">The SharePoint Sharing model and sharing events</span></span>

<span data-ttu-id="2e7b6-124">共享由三个单独的事件定义: **SharingSet**、 **SharingInvitationCreated**和**SharingInvitaitonAccepted**。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-124">Sharing is defined by three separate events: **SharingSet**, **SharingInvitationCreated**, and **SharingInvitaitonAccepted**.</span></span> <span data-ttu-id="2e7b6-125">下面介绍了如何在 Office 365 审核日志中记录共享事件的工作流。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-125">Here's the work flow for how sharing events are logged in the Office 365 audit log.</span></span> 
  
![共享审核工作原理的流程图](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
<span data-ttu-id="2e7b6-127">当用户 (用户) 想要与其他用户 (目标用户) 共享资源时, SharePoint (或 OneDrive for Business) 先检查目标用户的电子邮件地址是否已与组织目录中的用户帐户相关联。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-127">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="2e7b6-128">如果目标用户在组织的目录中, 则 SharePoint 将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="2e7b6-128">If the target user is in the organization's directory, SharePoint does the following:</span></span>
  
-  <span data-ttu-id="2e7b6-129">立即向目标用户分配访问资源的权限。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-129">Immediately assigns the target user permissions to access the resource.</span></span> 
    
- <span data-ttu-id="2e7b6-130">向目标用户的电子邮件地址发送共享通知。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-130">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="2e7b6-131">记录**SharingSet**事件。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-131">Logs a **SharingSet** event.</span></span> 
    
 <span data-ttu-id="2e7b6-132">如果目标用户的用户帐户不在组织的目录中, 则 SharePoint 将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="2e7b6-132">If a user account for the target user isn't in the organization's directory, SharePoint does the following:</span></span> 
  
- <span data-ttu-id="2e7b6-133">创建共享邀请, 并将其发送到目标用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-133">Creates a sharing invitation and sends it to the email address of the target user.</span></span>
    
- <span data-ttu-id="2e7b6-134">记录**SharingInvitationCreated**事件。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-134">Logs a **SharingInvitationCreated** event.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2e7b6-135">当目标用户没有访问共享资源的权限时, **SharingInvitationCreated**事件最常与外部共享或来宾共享关联。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-135">The **SharingInvitationCreated** event is most always associated with external or guest sharing when the target user doesn't have access to the resource that was shared.</span></span> 
  
<span data-ttu-id="2e7b6-136">当目标用户接受发送给他们的共享邀请 (通过单击邀请中的链接) 时, SharePoint 会记录一个**SharingInvitationAccepted**事件并为目标用户分配访问资源的权限。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-136">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="2e7b6-137">还会记录有关目标用户的其他信息, 例如向其发送邀请的用户的标识以及实际接受邀请的用户。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-137">Additional information about the target user is also logged, such as the identity of the user that the invitation was sent to and the user who actually accepted the invitation.</span></span> <span data-ttu-id="2e7b6-138">在某些情况下, 这些用户 (或电子邮件地址) 可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-138">In some case, these users (or email addresses) might be different.</span></span> 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="2e7b6-139">如何识别与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="2e7b6-139">How to identify resources shared with external users</span></span>

<span data-ttu-id="2e7b6-140">管理员的常见要求是创建已与组织外部的用户共享的所有资源的列表。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-140">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="2e7b6-141">通过使用 Office 365 中的共享审核, 管理员现在可以生成此列表。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-141">By using sharing auditing in Office 365, administrators can now generate this list.</span></span> <span data-ttu-id="2e7b6-142">方法如下：</span><span class="sxs-lookup"><span data-stu-id="2e7b6-142">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="2e7b6-143">步骤 1: 搜索共享事件并将结果导出到 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="2e7b6-143">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="2e7b6-144">第一步是在 Office 365 审核日志中搜索共享事件。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-144">The first step is to search the Office 365 audit log for sharing events.</span></span> <span data-ttu-id="2e7b6-145">有关搜索审核日志的详细信息 (包括所需的权限), 请参阅[在安全 & 合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-145">For more information (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="2e7b6-146">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="2e7b6-147">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="2e7b6-148">在安全性 & 合规性中心的左侧窗格中, 单击 "**搜索**  > **审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-148">In the left pane of the Security & Compliance Center, click **Search**  > **Audit log search**.</span></span>
    
    <span data-ttu-id="2e7b6-149">将显示 "**审核日志搜索**" 页。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-149">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="2e7b6-150">在 "**活动**" 下, 单击 "**共享和访问请求活动**" 以搜索与共享相关的事件。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-150">Under **Activities**, click **Sharing and access request activities** to search for sharing-related events.</span></span> 
    
    ![在 "活动" 下, 选择 "共享和访问请求活动"](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="2e7b6-152">选择日期和时间范围以查找在该时间段内发生的共享事件。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-152">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="2e7b6-153">单击 "**搜索**" 以运行搜索。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-153">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="2e7b6-154">当搜索运行完成并显示结果后, 单击 "**导出结果** \> " "**下载所有结果**"。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-154">When the search is finished running and the results are displayed, click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="2e7b6-155">选择 "导出" 选项后, 会在窗口底部显示一条消息, 提示您打开或保存 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-155">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="2e7b6-156">单击 "**另** \>存**为**", 然后将 CSV 文件保存到本地计算机上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-156">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 

### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="2e7b6-157">步骤 2: 筛选 CSV 文件, 以获取与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="2e7b6-157">Step 2: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="2e7b6-158">下一步是筛选**SharingSet**和**SHARINGINVITATIONCREATED**事件的 CSV, 并显示**TargetUserOrGroupType**属性为 "**来宾**" 的那些事件。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-158">The next step is to filter the CSV for the **SharingSet** and **SharingInvitationCreated** events, and to display those events where the **TargetUserOrGroupType** property is **Guest**.</span></span> <span data-ttu-id="2e7b6-159">您可以使用 Excel 中的 Power Query 编辑器工具执行此操作。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-159">You use the Power Query Editor tool in Excel to do this.</span></span> <span data-ttu-id="2e7b6-160">有关分步说明, 请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md)。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-160">For step-by-step instructions, see [Export, configure, and view audit log records](export-view-audit-log-records.md).</span></span> 

<span data-ttu-id="2e7b6-161">按照上一主题中的说明准备 CSV 文件后, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="2e7b6-161">After you've followed the instructions in the previous topic to prepare the CSV file, do the following:</span></span>
    
1. <span data-ttu-id="2e7b6-162">打开使用 Power Query 编辑器准备的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-162">Open the CSV file that you prepared with the Power Query Editor.</span></span> 

2. <span data-ttu-id="2e7b6-163">在 "**开始**" 选项卡上, 单击 "**排序 & 筛选**", 然后单击 "**筛选**"。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-163">On the **Home** tab, click **Sort & Filter**, and then click **Filter**.</span></span>
    
3. <span data-ttu-id="2e7b6-164">在 "**操作**" 列上的 "**排序 & 筛选**" 下拉列表中, 清除所有选择, 然后选择 " **SharingSet** " 和 " **SharingInvitationCreated**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-164">In the **Sort & Filter** dropdown list on the **Operations** column, clear all selections, then select **SharingSet** and **SharingInvitationCreated**, and click **OK**.</span></span>
    
    <span data-ttu-id="2e7b6-165">Excel 显示**SharingSet**和**SharingInvitationCreated**事件的行。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-165">Excel displays the rows for the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
4. <span data-ttu-id="2e7b6-166">转到名为**TargetUserOrGroupType**的列, 然后选择它。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-166">Go to the column named **TargetUserOrGroupType** and select it.</span></span> 
    
5. <span data-ttu-id="2e7b6-167">在 "**排序 & 筛选**" 下拉列表中, 清除 "所有选择", 然后选择 " **TargetUserOrGroupType: Guest**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-167">In the **Sort & Filter** dropdown list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **OK**.</span></span>
    
    <span data-ttu-id="2e7b6-168">现在, Excel 将显示**SharingInvitationCreated**和**SharingSet**事件的行, 以及目标用户在组织外部的位置, 因为外部用户由值**TargetUserOrGroupType: Guest**标识。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-168">Now Excel displays the rows for **SharingInvitationCreated** and **SharingSet** events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
    
<span data-ttu-id="2e7b6-169">下表显示在指定日期范围内与来宾用户共享资源的组织中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-169">The following table shows all users in the organization who shared resources with a guest user within a specified date range.</span></span>
  
![在 Office 365 审核日志中共享事件](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
<span data-ttu-id="2e7b6-171">[! 注意] **ObjectId**属性不包含在上表中, 但它标识与目标用户共享的资源;例如`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-171">Although it's not included in the previous table, the **ObjectId** property identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
  
> [!TIP]
> <span data-ttu-id="2e7b6-172">如果要标识来宾用户实际何时被分配访问某个资源的权限 (而不只是与它们共享的资源), 请重复步骤2、3和 4, 并在**SharingInvitationAccepted**和**SharingSet**上进行筛选。步骤5中的事件。</span><span class="sxs-lookup"><span data-stu-id="2e7b6-172">If you want to identify when a guest user was actually assigned permissions to access a resource (as opposed to just the resources that where shared with them), repeat Steps 2, 3, and 4, and filter on the **SharingInvitationAccepted** and **SharingSet** events in Step 5.</span></span> 

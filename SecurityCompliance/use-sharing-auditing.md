---
title: 审核共享以查找与外部用户共享的资源
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共享是 SharePoint Online 和 OneDrive for business 中的关键活动。管理员现在可以在 Office 365 审核日志中使用共享审核来确定如何在组织中使用共享。 '
ms.openlocfilehash: 919592bff43379b552b83258c7b22b7eddb14e7a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219882"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="62a0d-104">审核共享以查找与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="62a0d-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="62a0d-p102">共享是 SharePoint Online 和 OneDrive for business 中的关键活动, 并在 Office 365 组织中广泛使用。管理员现在可以在 Office 365 审核日志中使用共享审核来确定如何在组织中使用共享。</span><span class="sxs-lookup"><span data-stu-id="62a0d-p102">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations. Administrators can now use sharing auditing in the Office 365 audit log to determine how sharing is being used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="62a0d-107">SharePoint 共享架构</span><span class="sxs-lookup"><span data-stu-id="62a0d-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="62a0d-p103">共享事件 (不包括共享策略和共享链接事件) 与文件和文件夹相关的事件有一个主要的不同之处: 一个用户正在采取对另一个用户有影响的操作。例如, 用户 A 向用户 B 授予对文件的访问权限。在此示例中, 用户 A 是*作用用户*, 而用户 B 是*目标用户*。在 SharePoint 文件架构中, 作用用户的操作仅影响文件本身。当用户 A 打开文件时, **FileAccessed**事件中所需的唯一信息是操作用户。为了解决这种差异, 有一个称为*SharePoint 共享架构*的单独架构, 可捕获有关共享事件的详细信息。这可确保管理员能够更好地了解共享资源的人员和共享资源的用户。</span><span class="sxs-lookup"><span data-stu-id="62a0d-p103">Sharing events (excluding sharing policy and sharing link events) are different from file- and folder-related events in one primary way: one user is taking an action that has some effect on another user. For example, User A gives User B access to a file. In this example, User A is the  *acting user*  and User B is the  *target user*. In the SharePoint File schema, the acting user's action only affects the file itself. When User A opens a file, the only information needed in the **FileAccessed** event is the acting user. To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events. This ensures that administrators have more insight into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="62a0d-115">共享架构在与共享事件相关的审核日志中提供了两个附加字段:</span><span class="sxs-lookup"><span data-stu-id="62a0d-115">The Sharing schema provides two additional fields in the audit log related to sharing events:</span></span> 
  
- <span data-ttu-id="62a0d-116">**TargetUserOrGroupName** -存储与之共享资源的目标用户或组的 UPN 或名称 (上一示例中的用户 B)。</span><span class="sxs-lookup"><span data-stu-id="62a0d-116">**TargetUserOrGroupName** - Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 
    
- <span data-ttu-id="62a0d-117">**TargetUserOrGroupType** -确定目标用户或组是否为成员、来宾、组或合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="62a0d-117">**TargetUserOrGroupType** - Identifies whether the target user or group is a Member, Guest, Group, or Partner.</span></span> 
    
<span data-ttu-id="62a0d-118">除了 Office 365 审核日志架构 (如用户、操作和日期) 以外的其他属性, 这两个字段还可以详细说明*哪些*用户共享了哪些用户与*谁*共享了*哪些*资源。 \*\*</span><span class="sxs-lookup"><span data-stu-id="62a0d-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="62a0d-p104">还有另一个架构属性, 对共享情景很重要。**EventData**属性存储有关共享事件的其他信息。例如, 当用户与其他用户共享网站时, 可以通过将目标用户添加到 SharePoint 组来实现此目的。**EventData**属性捕获此附加信息, 以便为管理员提供上下文。</span><span class="sxs-lookup"><span data-stu-id="62a0d-p104">There's another schema property that's important to the sharing story. The **EventData** property stores additional information about sharing events. For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group. The **EventData** property captures this additional information to provide context for administrators.</span></span> 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a><span data-ttu-id="62a0d-123">SharePoint 共享模型和共享事件</span><span class="sxs-lookup"><span data-stu-id="62a0d-123">The SharePoint Sharing model and sharing events</span></span>

<span data-ttu-id="62a0d-p105">共享实际上是由三个单独的事件定义的: **SharingSet**、 **SharingInvitationCreated**和**SharingInvitaitonAccepted**。下面介绍了如何在 Office 365 审核日志中记录共享事件的工作流。</span><span class="sxs-lookup"><span data-stu-id="62a0d-p105">Sharing is actually defined by three separate events: **SharingSet**, **SharingInvitationCreated**, and **SharingInvitaitonAccepted**. Here's the work flow for how sharing events are logged in the Office 365 audit log.</span></span> 
  
![共享审核工作原理的流程图](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
<span data-ttu-id="62a0d-p106">当用户 (用户) 想要与其他用户 (目标用户) 共享资源时, SharePoint (或 OneDrive for business) 先检查目标用户的电子邮件地址是否已与组织目录中的用户帐户相关联。如果目标用户在组织的目录中, 则 SharePoint 将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="62a0d-p106">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory. If the target user is in the organization's directory, SharePoint does the following:</span></span>
  
-  <span data-ttu-id="62a0d-129">立即向目标用户分配访问资源的权限。</span><span class="sxs-lookup"><span data-stu-id="62a0d-129">Immediately assigns the target user permissions to access the resource.</span></span> 
    
- <span data-ttu-id="62a0d-130">向目标用户的电子邮件地址发送共享通知。</span><span class="sxs-lookup"><span data-stu-id="62a0d-130">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="62a0d-131">记录**SharingSet**事件。</span><span class="sxs-lookup"><span data-stu-id="62a0d-131">Logs a **SharingSet** event.</span></span> 
    
 <span data-ttu-id="62a0d-132">如果目标用户的用户帐户不在组织的目录中, 则 SharePoint 将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="62a0d-132">If a user account for the target user isn't in the organization's directory, SharePoint does the following:</span></span> 
  
- <span data-ttu-id="62a0d-133">创建共享邀请, 并将其发送到目标用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="62a0d-133">Creates a sharing invitation and sends it to the email address of the target user.</span></span>
    
- <span data-ttu-id="62a0d-134">记录**SharingInvitationCreated**事件。</span><span class="sxs-lookup"><span data-stu-id="62a0d-134">Logs a **SharingInvitationCreated** event.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="62a0d-135">当目标用户没有访问共享资源的权限时, **SharingInvitationCreated**事件最常与外部共享或来宾共享关联。</span><span class="sxs-lookup"><span data-stu-id="62a0d-135">The **SharingInvitationCreated** event is most always associated with external or guest sharing when the target user doesn't have access to the resource that was shared.</span></span> 
  
<span data-ttu-id="62a0d-p107">当目标用户接受发送给他们的共享邀请 (通过单击邀请中的链接) 时, SharePoint 会记录一个**SharingInvitationAccepted**事件并为目标用户分配访问资源的权限。还会记录有关目标用户的其他信息, 例如向其发送邀请的用户的标识以及实际接受邀请的用户。在某些情况下, 这些用户 (或电子邮件地址) 可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="62a0d-p107">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource. Additional information about the target user is also logged, such as the identity of the user that the invitation was sent to and the user who actually accepted the invitation. In some case, these users (or email addresses) might be different.</span></span> 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="62a0d-139">如何识别与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="62a0d-139">How to identify resources shared with external users</span></span>

<span data-ttu-id="62a0d-p108">管理员的常见要求是创建已与组织外部的用户共享的所有资源的列表。通过使用 Office 365 中的共享审核, 管理员现在可以生成此列表。操作方法如下。</span><span class="sxs-lookup"><span data-stu-id="62a0d-p108">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization. By using sharing auditing in Office 365, administrators can now generate this list. Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="62a0d-143">步骤 1: 搜索共享事件并将结果导出到 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="62a0d-143">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="62a0d-p109">第一步是在 Office 365 审核日志中搜索共享事件。有关搜索审核日志的更多详细信息 (包括所需的权限), 请参阅[在 Office 365 安全&amp;合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="62a0d-p109">The first step is to search the Office 365 audit log for sharing events. For more details (including the required permissions) about searching the audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="62a0d-146">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="62a0d-146">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="62a0d-147">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="62a0d-147">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="62a0d-148">在安全&amp;合规性中心的左侧窗格中, 单击 **" &amp;搜索调查**", 然后单击 "**审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="62a0d-148">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation**, and then click **Audit log search**.</span></span>
    
    <span data-ttu-id="62a0d-149">将显示 "**审核日志搜索**" 页。</span><span class="sxs-lookup"><span data-stu-id="62a0d-149">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="62a0d-150">在 "**活动**" 下, 单击 "**共享活动**以仅搜索共享事件"。</span><span class="sxs-lookup"><span data-stu-id="62a0d-150">Under **Activities**, click **Sharing activities** to search only for sharing events.</span></span> 
    
    ![在 "活动" 下, 选择 "共享活动"](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="62a0d-152">选择日期和时间范围以查找在该时间段内发生的共享事件。</span><span class="sxs-lookup"><span data-stu-id="62a0d-152">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="62a0d-153">单击 "**搜索**" 以运行搜索。</span><span class="sxs-lookup"><span data-stu-id="62a0d-153">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="62a0d-154">当搜索运行完成并显示结果后, 单击 "**导出结果** \> " "**下载所有结果**"。</span><span class="sxs-lookup"><span data-stu-id="62a0d-154">When the search is finished running and the results are displayed , click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="62a0d-155">选择 "导出" 选项后, 会在窗口底部显示一条消息, 提示您打开或保存 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="62a0d-155">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="62a0d-156">单击 "**另** \>存**为**", 然后将 CSV 文件保存到本地计算机上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="62a0d-156">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="62a0d-157">步骤 2: 筛选 CSV 文件, 以获取与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="62a0d-157">Step 2: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="62a0d-p110">下一步是筛选**SharingSet**和**SharingInvitationCreated**事件的 CSV, 并显示**TargetUserOrGroupType**属性为 "**来宾**" 的那些事件。您将使用 Excel 中的 Power Query 功能执行此操作。以下过程在 Excel 2016 中执行。</span><span class="sxs-lookup"><span data-stu-id="62a0d-p110">The next step is to filter the CSV for the **SharingSet** and **SharingInvitationCreated** events, and to display those events where the **TargetUserOrGroupType** property is **Guest**. You'll use the Power Query feature in Excel to do this. The following procedure is performed in Excel 2016.</span></span> 
  
1. <span data-ttu-id="62a0d-161">在 Excel 2016 中, 打开一个空白工作簿。</span><span class="sxs-lookup"><span data-stu-id="62a0d-161">In Excel 2016, open a blank workbook.</span></span>
    
2. <span data-ttu-id="62a0d-162">单击“数据”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="62a0d-162">Click the **Data** tab.</span></span> 
    
3. <span data-ttu-id="62a0d-163">单击 "从**CSV\*\*\*\*文件** \> **新建查询** \> "。</span><span class="sxs-lookup"><span data-stu-id="62a0d-163">Click **New Query** \> **From file** \> **From CSV**.</span></span>
    
    ![在 "数据" 选项卡上, 选择 "新建查询", 选择 "源文件", 然后选择 "从 CSV](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. <span data-ttu-id="62a0d-165">打开您在步骤1中下载的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="62a0d-165">Open the CSV file that you downloaded in Step 1.</span></span>
    
    <span data-ttu-id="62a0d-p111">CSV 文件将在查询编辑器中打开。请注意, 有四列:**时间**、**用户**、**操作**和**详细信息**。**详细信息**列是一个多属性字段。下一步是为 "**详细信息**" 列中的每个属性创建一个新列。</span><span class="sxs-lookup"><span data-stu-id="62a0d-p111">The CSV file is opened in the Query Editor. Note that there are four columns: **Time**, **User**, **Action**, and **Detail**. The **Detail** column is a multi-property field. The next step is to create a new column for each of the properties in the **Detail** column.</span></span> 
    
5. <span data-ttu-id="62a0d-170">选择 "**详细信息**" 列, 然后在 "**开始**" 选项卡上, 单击 "**按分隔符\*\*\*\*拆分列** \> "。</span><span class="sxs-lookup"><span data-stu-id="62a0d-170">Select the **Detail** column, and then on the **Home** tab, click **Split Column** \> **By Delimiter**.</span></span>
    
    ![在 "开始" 选项卡上, 单击 "拆分列", 然后单击 "按分隔符"](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. <span data-ttu-id="62a0d-172">在 "**拆分列 (按分隔符**)" 窗口中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="62a0d-172">In the **Split Column by Delimiter** window, do the following:</span></span> 
    
      - <span data-ttu-id="62a0d-173">在 "**选择或输入分隔符**" 下, 选择 "**逗号**"。</span><span class="sxs-lookup"><span data-stu-id="62a0d-173">Under **Select or enter delimiter**, select **Comma**.</span></span>
    
      - <span data-ttu-id="62a0d-174">在 "**拆分**" 下, 在**分隔符的每次出现时**选择。</span><span class="sxs-lookup"><span data-stu-id="62a0d-174">Under **Split**, select **At each occurrence of the delimiter**.</span></span>
    
7. <span data-ttu-id="62a0d-175">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="62a0d-175">Click **OK**.</span></span>
    
    <span data-ttu-id="62a0d-p112">**详细信息**列拆分为多个列。每个新列的名称分别为**详细信息. 1**、**详细信息. 2**、**详细信息. 3**等。您会注意到详细信息中每个单元格中的值 **。 n**个列以属性名称作为前缀;例如,**操作: SharingSet**、 **operation: SharingInvitationAccepted**和**Operation: SharingInvitationCreated**。</span><span class="sxs-lookup"><span data-stu-id="62a0d-p112">The **Detail** column is split into multiple columns. Each new column is named **Detail.1**, **Detail.2**, **Detail.3**, and so on. You'll notice the values in each cell in the **Detail.n** columns are prefixed with the name of the property; for example, **Operation:SharingSet**, **Operation:SharingInvitationAccepted**, and **Operation:SharingInvitationCreated**.</span></span>
    
    ![详细信息列拆分为多个列, 每个属性一个列](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. <span data-ttu-id="62a0d-180">在 "**文件**" 选项卡上, 单击 "**关闭&amp;加载**" 以关闭查询编辑器并在 Excel 工作簿中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="62a0d-180">On the **File** tab, click **Close &amp; Load** to close the Query Editor and open the file in an Excel workbook.</span></span> 
    
    <span data-ttu-id="62a0d-181">下一步是筛选文件以仅显示**SharingSet**和**SharingInvitationCreated**事件。</span><span class="sxs-lookup"><span data-stu-id="62a0d-181">The next step is to filter the file to only display the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
9. <span data-ttu-id="62a0d-182">转到 "**开始**" 选项卡, 然后选择 "**操作**" 列。</span><span class="sxs-lookup"><span data-stu-id="62a0d-182">Go to the **Home** tab, and then select the **Action** column.</span></span> 
    
10. <span data-ttu-id="62a0d-183">在 "**排序&amp;筛选器**" 下拉列表中, 清除所有选择, 然后选择 " **SharingSet** " 和 " **SharingInvitationCreated**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="62a0d-183">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **SharingSet** and **SharingInvitationCreated**, and click **OK**.</span></span>
    
    <span data-ttu-id="62a0d-184">Excel 显示**SharingSet**和**SharingInvitationCreated**事件的行。</span><span class="sxs-lookup"><span data-stu-id="62a0d-184">Excel displays the rows for the **SharingSet** and **SharingInvitationCreated** events.</span></span> 
    
11. <span data-ttu-id="62a0d-185">转到名为**Detail. 17** (或任何列包含**TargetUserOrGroupType**属性) 的列并将其选中。</span><span class="sxs-lookup"><span data-stu-id="62a0d-185">Go to the column named **Detail.17** (or whichever column contains the **TargetUserOrGroupType** property) and select it.</span></span> 
    
12. <span data-ttu-id="62a0d-186">在 "**排序&amp;筛选器**" 下拉列表中, 清除 "所有选择", 然后选择 " **TargetUserOrGroupType: Guest**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="62a0d-186">In the **Sort &amp; Filter** drop-down list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **OK**.</span></span>
    
    <span data-ttu-id="62a0d-187">现在, Excel 将显示**SharingInvitationCreated**和**SharingSet**事件的行, 以及目标用户在组织外部的位置, 因为外部用户由值**TargetUserOrGroupType: Guest**标识。</span><span class="sxs-lookup"><span data-stu-id="62a0d-187">Now Excel displays the rows for **SharingInvitationCreated** and **SharingSet** events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
    
<span data-ttu-id="62a0d-188">下表显示在指定日期范围内与来宾用户共享资源的组织中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="62a0d-188">The following table shows all users in the organization who shared resources with a guest user within a specified date range.</span></span>
  
![在 Office 365 审核日志中共享事件](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
<span data-ttu-id="62a0d-190">[! 注意] 尽管它不包含在上表中, 但第**10**列 (或任何包含**ObjectId**属性的列) 标识与目标用户共享的资源;例如`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`。</span><span class="sxs-lookup"><span data-stu-id="62a0d-190">Although it's not included in the previous table, the **Detail.10** column (or whichever column contains the **ObjectId** property) identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>
  
> [!TIP]
> <span data-ttu-id="62a0d-191">如果要标识来宾用户实际何时被分配访问资源的权限 (而不只是与他们共享的资源), 请重复步骤10、11和 12, 并在**SharingInvitationAccepted**和 SharingSet 上进行筛选。 \*\*\*\* 步骤10中的事件。</span><span class="sxs-lookup"><span data-stu-id="62a0d-191">If you want to identify when a guest user was actually assigned permissions to access a resource (as opposed to just the resources that where shared with them), repeat Steps 10, 11, and 12, and filter on the **SharingInvitationAccepted** and **SharingSet** events in Step 10.</span></span> 

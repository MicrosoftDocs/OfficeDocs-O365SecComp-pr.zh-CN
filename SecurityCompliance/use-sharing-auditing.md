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
ms.collection: M365-security-compliance
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共享是 SharePoint Online 和 OneDrive for business 中的关键活动。 管理员现在可以在 Office 365 审核日志中使用共享审核, 以确定与组织外部的用户共享的资源。 '
ms.openlocfilehash: 54fa32ec9ed16a65354eb845421c56f6d58559e4
ms.sourcegitcommit: c8ea7c0900e69e69bd5c735960df70aae27690a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2019
ms.locfileid: "36258565"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a><span data-ttu-id="8e294-104">审核共享以查找与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="8e294-104">Use sharing auditing in the Office 365 audit log</span></span>

<span data-ttu-id="8e294-105">共享是 SharePoint Online 和 OneDrive for business 中的关键活动, 并在 Office 365 组织中广泛使用。</span><span class="sxs-lookup"><span data-stu-id="8e294-105">Sharing is a key activity in SharePoint Online and OneDrive for Business, and it's widely used in Office 365 organizations.</span></span> <span data-ttu-id="8e294-106">管理员可以使用 Office 365 审核日志中的共享审核来确定如何在组织中使用共享。</span><span class="sxs-lookup"><span data-stu-id="8e294-106">Administrators can use sharing auditing in the Office 365 audit log to determine how sharing is used in their organization.</span></span> 
  
## <a name="the-sharepoint-sharing-schema"></a><span data-ttu-id="8e294-107">SharePoint 共享架构</span><span class="sxs-lookup"><span data-stu-id="8e294-107">The SharePoint Sharing schema</span></span>

<span data-ttu-id="8e294-108">共享事件 (不包括与共享策略和共享链接相关的事件) 与文件和文件夹相关的事件有一个主要方式不同: 一个用户执行的操作对另一个用户有影响。</span><span class="sxs-lookup"><span data-stu-id="8e294-108">Sharing events (not including events related to sharing policy and sharing links) are different from file- and folder-related events in one primary way: one user is performing an action that has an effect on another user.</span></span> <span data-ttu-id="8e294-109">例如, 当资源用户 A 向用户 B 授予对文件的访问权限时。</span><span class="sxs-lookup"><span data-stu-id="8e294-109">For example, when a resource User A gives User B access to a file.</span></span> <span data-ttu-id="8e294-110">在此示例中, 用户 A 是*作用用户*, 而用户 B 是*目标用户*。</span><span class="sxs-lookup"><span data-stu-id="8e294-110">In this example, User A is the  *acting user*  and User B is the  *target user*.</span></span> <span data-ttu-id="8e294-111">在 SharePoint 文件架构中, 作用用户的操作仅影响文件本身。</span><span class="sxs-lookup"><span data-stu-id="8e294-111">In the SharePoint File schema, the acting user's action only affects the file itself.</span></span> <span data-ttu-id="8e294-112">当用户 A 打开文件时, **FileAccessed**事件中所需的唯一信息是操作用户。</span><span class="sxs-lookup"><span data-stu-id="8e294-112">When User A opens a file, the only information needed in the **FileAccessed** event is the acting user.</span></span> <span data-ttu-id="8e294-113">为了解决这种差异, 有一个称为*SharePoint 共享架构*的单独架构, 可捕获有关共享事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8e294-113">To address this difference, there is a separate schema, called the  *SharePoint Sharing schema*, that captures more information about sharing events.</span></span> <span data-ttu-id="8e294-114">这可确保管理员可以查看共享资源的人员以及共享资源的用户。</span><span class="sxs-lookup"><span data-stu-id="8e294-114">This ensures that administrators have visibility into who shared a resource and the user the resource was shared with.</span></span> 
  
<span data-ttu-id="8e294-115">共享架构在与共享事件相关的审核记录中提供了两个附加字段:</span><span class="sxs-lookup"><span data-stu-id="8e294-115">The Sharing schema provides two additional fields in an audit record related to sharing events:</span></span> 
  
- <span data-ttu-id="8e294-116">**TargetUserOrGroupType:** 标识目标用户或组是成员、来宾、SharePointGroup、SecurityGroup 还是合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="8e294-116">**TargetUserOrGroupType:** Identifies whether the target user or group is a Member, Guest, SharePointGroup, SecurityGroup, or Partner.</span></span>

- <span data-ttu-id="8e294-117">**TargetUserOrGroupName:** 存储与之共享资源的目标用户或组的 UPN 或名称 (上一示例中的用户 B)。</span><span class="sxs-lookup"><span data-stu-id="8e294-117">**TargetUserOrGroupName:** Stores the UPN or name of the target user or group that a resource was shared with (User B in the previous example).</span></span> 

<span data-ttu-id="8e294-118">除了 Office 365 审核日志架构 (如用户、操作和日期) 以外的其他属性, 这两个字段还可以详细说明*哪些*用户共享了哪些用户与*谁*共享了*哪些*资源。 \*\*</span><span class="sxs-lookup"><span data-stu-id="8e294-118">These two fields, in addition to other properties from the Office 365 audit log schema such as User, Operation, and Date can tell the full story about  *which*  user shared  *what*  resource with  *whom*  and  *when*.</span></span> 
  
<span data-ttu-id="8e294-119">还有另一个架构属性, 对共享情景很重要。</span><span class="sxs-lookup"><span data-stu-id="8e294-119">There's another schema property that's important to the sharing story.</span></span> <span data-ttu-id="8e294-120">当您导出审核日志搜索结果时, 导出的 CSV 文件中的 " **AuditData** " 列存储有关共享事件的信息。</span><span class="sxs-lookup"><span data-stu-id="8e294-120">When you export audit log search results, the **AuditData** column in the exported CSV file stores information about sharing events.</span></span> <span data-ttu-id="8e294-121">例如, 当用户与其他用户共享网站时, 可以通过将目标用户添加到 SharePoint 组来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="8e294-121">For example, when a user shares a site with another user, this is accomplished by adding the target user to a SharePoint group.</span></span> <span data-ttu-id="8e294-122">**AuditData**列捕获此信息, 以便为管理员提供上下文。</span><span class="sxs-lookup"><span data-stu-id="8e294-122">The **AuditData** column captures this information to provide context for administrators.</span></span> <span data-ttu-id="8e294-123">有关如何分析**AuditData**列中的信息的说明, 请参阅[步骤 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) 。</span><span class="sxs-lookup"><span data-stu-id="8e294-123">See [Step 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) for instructions on how to parse the information in the **AuditData** column.</span></span>

## <a name="sharepoint-sharing-events"></a><span data-ttu-id="8e294-124">SharePoint 共享事件</span><span class="sxs-lookup"><span data-stu-id="8e294-124">SharePoint sharing events</span></span>

<span data-ttu-id="8e294-125">当用户 (用户) 要与其他用户\*\* 共享资源 (*目标*用户) 时, 将定义共享。</span><span class="sxs-lookup"><span data-stu-id="8e294-125">Sharing is defined by when a user (the *acting* user) wants to share a resource with another user (the *target* user).</span></span> <span data-ttu-id="8e294-126">与外部用户共享资源的审核记录 (组织外部的用户, 在组织的 Azure Active Directory 中没有来宾帐户) 由以下事件标识, 这些事件记录在 Office 365 中。审核日志:</span><span class="sxs-lookup"><span data-stu-id="8e294-126">Audit records related to sharing a resource with an external user (a user who is outside of your organization and doesn't have a guest account in your organization's Azure Active Directory) are identified by the following events, which are logged in the Office 365 audit log:</span></span>

- <span data-ttu-id="8e294-127">**SharingInvitationCreated:** 您的组织中的用户尝试与外部用户共享资源 (可能是网站)。</span><span class="sxs-lookup"><span data-stu-id="8e294-127">**SharingInvitationCreated:** A user in your organization tried to share a resource (likely a site) with an external user.</span></span> <span data-ttu-id="8e294-128">这将导致向目标用户发送外部共享邀请。</span><span class="sxs-lookup"><span data-stu-id="8e294-128">This results in an external sharing invitation sent to the target user.</span></span> <span data-ttu-id="8e294-129">此时不授予对资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8e294-129">No access to the resource is granted at this point.</span></span>

- <span data-ttu-id="8e294-130">**SharingInvitationAccepted:** 外部用户接受了由操作用户发送的共享邀请, 现在有权访问该资源。</span><span class="sxs-lookup"><span data-stu-id="8e294-130">**SharingInvitationAccepted:** The external user has accepted the sharing invitation sent by the acting user and now has access to the resource.</span></span>

- <span data-ttu-id="8e294-131">**AnonymousLinkCreated:** 为资源创建匿名链接 (也称为 "任何人" 链接)。</span><span class="sxs-lookup"><span data-stu-id="8e294-131">**AnonymousLinkCreated:** An anonymous link (also called an "Anyone" link) is created for a resource.</span></span> <span data-ttu-id="8e294-132">由于可以创建匿名链接, 然后复制它, 因此假定具有匿名链接的任何文档已与目标用户共享, 这是合理的。</span><span class="sxs-lookup"><span data-stu-id="8e294-132">Because an anonymous link can be created and then copied, it's reasonable to assume that any document that has an anonymous link has been shared with a target user.</span></span>

- <span data-ttu-id="8e294-133">**AnonymousLinkUsed:** 顾名思义, 当使用匿名链接访问资源时, 将记录此事件。</span><span class="sxs-lookup"><span data-stu-id="8e294-133">**AnonymousLinkUsed:** As the name implies, this event is logged when an anonymous link is used to access a resource.</span></span> 

- <span data-ttu-id="8e294-134">**SecureLinkCreated:** 用户已创建 "特定人员链接" 以与特定人员共享资源。</span><span class="sxs-lookup"><span data-stu-id="8e294-134">**SecureLinkCreated:** A user has created a "specific people link" to share a resource with a specific person.</span></span> <span data-ttu-id="8e294-135">此目标用户可能是你的组织外部的人员。</span><span class="sxs-lookup"><span data-stu-id="8e294-135">This target user may be someone who is external to your organization.</span></span>

- <span data-ttu-id="8e294-136">**AddedToSecureLink:** 向特定人员链接添加了用户。</span><span class="sxs-lookup"><span data-stu-id="8e294-136">**AddedToSecureLink:** A user was added to a specific people link.</span></span> <span data-ttu-id="8e294-137">此目标用户可能是你的组织外部的人员。</span><span class="sxs-lookup"><span data-stu-id="8e294-137">This target user may be someone who is external to your organization.</span></span>

## <a name="sharing-auditing-work-flow"></a><span data-ttu-id="8e294-138">共享审核工作流</span><span class="sxs-lookup"><span data-stu-id="8e294-138">Sharing auditing work flow</span></span>
  
<span data-ttu-id="8e294-139">当用户 (用户) 想要与其他用户 (目标用户) 共享资源时, SharePoint (或 OneDrive for Business) 先检查目标用户的电子邮件地址是否已与组织目录中的用户帐户相关联。</span><span class="sxs-lookup"><span data-stu-id="8e294-139">When a user (the acting user) wants to share a resource with another user (the target user), SharePoint (or OneDrive for Business) first checks if the email address of the target user is already associated with a user account in the organization's directory.</span></span> <span data-ttu-id="8e294-140">如果目标用户位于目录中 (并具有相应的来宾用户帐户), SharePoint 将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="8e294-140">If the target user is in the directory (and has a corresponding guest user account), SharePoint does the following things:</span></span>
  
-  <span data-ttu-id="8e294-141">通过将目标用户添加到相应的 SharePoint 组, 立即为目标用户分配访问资源的权限, 并记录**AddedToGroup**事件。</span><span class="sxs-lookup"><span data-stu-id="8e294-141">Immediately assigns the target user permissions to access the resource by adding the target user to the appropriate SharePoint group, and logs an **AddedToGroup** event.</span></span> 
    
- <span data-ttu-id="8e294-142">向目标用户的电子邮件地址发送共享通知。</span><span class="sxs-lookup"><span data-stu-id="8e294-142">Sends a sharing notification to the email address of the target user.</span></span>
    
- <span data-ttu-id="8e294-143">记录**SharingSet**事件。</span><span class="sxs-lookup"><span data-stu-id="8e294-143">Logs a **SharingSet** event.</span></span> <span data-ttu-id="8e294-144">此事件在审核日志搜索工具的活动选取器中的 "共享**和访问请求" 活动**下有一个友好名称 "共享文件、文件夹或站点"。</span><span class="sxs-lookup"><span data-stu-id="8e294-144">This event has a friendly name of "Shared file, folder, or site" under **Sharing and access request activities** in the activities picker of the audit log search tool.</span></span> <span data-ttu-id="8e294-145">请参阅[第1步](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)中的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="8e294-145">See the screenshot in [Step 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file).</span></span> 
    
<span data-ttu-id="8e294-146">如果目标用户的用户帐户不在目录中, 则 SharePoint 将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="8e294-146">If a user account for the target user isn't in the directory, SharePoint does the following:</span></span> 
    
   - <span data-ttu-id="8e294-147">根据资源的共享方式, 记录以下事件之一:</span><span class="sxs-lookup"><span data-stu-id="8e294-147">Logs one of the following events, based on how the resource is shared:</span></span>
   
      - <span data-ttu-id="8e294-148">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="8e294-148">**AnonymousLinkCreated**</span></span>
   
      - <span data-ttu-id="8e294-149">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="8e294-149">**SecureLinkCreated**</span></span>
   
      - <span data-ttu-id="8e294-150">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="8e294-150">**AddedToSecureLink**</span></span> 

      - <span data-ttu-id="8e294-151">**SharingInvitationCreated**(仅当共享资源是网站时, 才会记录此事件)</span><span class="sxs-lookup"><span data-stu-id="8e294-151">**SharingInvitationCreated** (this event is logged only when the shared resource is a site)</span></span>
    
   - <span data-ttu-id="8e294-152">当目标用户接受发送给他们的共享邀请 (通过单击邀请中的链接) 时, SharePoint 会记录一个**SharingInvitationAccepted**事件并为目标用户分配访问资源的权限。</span><span class="sxs-lookup"><span data-stu-id="8e294-152">When the target user accepts the sharing invitation that's sent to them (by clicking the link in the invitation), SharePoint logs a **SharingInvitationAccepted** event and assigns the target user permissions to access the resource.</span></span> <span data-ttu-id="8e294-153">如果向目标用户发送匿名链接, 则在目标用户使用该链接访问资源后记录**AnonymousLinkUsed**事件。</span><span class="sxs-lookup"><span data-stu-id="8e294-153">If the target user is sent an anonymous link, the **AnonymousLinkUsed** event is logged after the target user uses the link to access the resource.</span></span> <span data-ttu-id="8e294-154">对于安全链接, 当外部用户使用链接访问资源时, 将记录**FileAccessed**事件。</span><span class="sxs-lookup"><span data-stu-id="8e294-154">For secure links, a **FileAccessed** event is logged when an external user uses the link to access the resource.</span></span>

<span data-ttu-id="8e294-155">还会记录有关目标用户的其他信息, 如邀请的用户的标识和实际接受邀请的用户。</span><span class="sxs-lookup"><span data-stu-id="8e294-155">Additional information about the target user is also logged, such as the identity of the user that the invitation is to and the user who actually accepts the invitation.</span></span> <span data-ttu-id="8e294-156">在某些情况下, 这些用户 (或电子邮件地址) 可以不同。</span><span class="sxs-lookup"><span data-stu-id="8e294-156">In some case, these users (or email addresses) can be different.</span></span> 

## <a name="how-to-identify-resources-shared-with-external-users"></a><span data-ttu-id="8e294-157">如何识别与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="8e294-157">How to identify resources shared with external users</span></span>

<span data-ttu-id="8e294-158">管理员的常见要求是创建已与组织外部的用户共享的所有资源的列表。</span><span class="sxs-lookup"><span data-stu-id="8e294-158">A common requirement for administrators is creating a list of all resources that have been shared with users outside of the organization.</span></span> <span data-ttu-id="8e294-159">通过使用 Office 365 中的共享审核, 管理员可以生成此列表。</span><span class="sxs-lookup"><span data-stu-id="8e294-159">By using sharing auditing in Office 365, administrators can generate this list.</span></span> <span data-ttu-id="8e294-160">方法如下：</span><span class="sxs-lookup"><span data-stu-id="8e294-160">Here's how.</span></span>
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a><span data-ttu-id="8e294-161">步骤 1: 搜索共享事件并将结果导出到 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="8e294-161">Step 1: Search for sharing events and export the results to a CSV file</span></span>

<span data-ttu-id="8e294-162">第一步是在 Office 365 审核日志中搜索共享事件。</span><span class="sxs-lookup"><span data-stu-id="8e294-162">The first step is to search the Office 365 audit log for sharing events.</span></span> <span data-ttu-id="8e294-163">有关搜索审核日志的详细信息 (包括所需的权限), 请参阅[在安全 & 合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="8e294-163">For more information (including the required permissions) about searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
  
1. <span data-ttu-id="8e294-164">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="8e294-164">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="8e294-165">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8e294-165">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="8e294-166">在安全性 & 合规性中心的左侧窗格中, 单击 "**搜索**  > **审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="8e294-166">In the left pane of the Security & Compliance Center, click **Search**  > **Audit log search**.</span></span>
    
    <span data-ttu-id="8e294-167">将显示 "**审核日志搜索**" 页。</span><span class="sxs-lookup"><span data-stu-id="8e294-167">The **Audit log search** page is displayed.</span></span> 
    
4. <span data-ttu-id="8e294-168">在 "**活动**" 下, 单击 "**共享和访问请求活动**" 以搜索与共享相关的事件。</span><span class="sxs-lookup"><span data-stu-id="8e294-168">Under **Activities**, click **Sharing and access request activities** to search for sharing-related events.</span></span> 
    
    ![在 "活动" 下, 选择 "共享和访问请求活动"](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  <span data-ttu-id="8e294-170">选择日期和时间范围以查找在该时间段内发生的共享事件。</span><span class="sxs-lookup"><span data-stu-id="8e294-170">Select a date and time range to find the sharing events that occurred within that period.</span></span> 
    
6. <span data-ttu-id="8e294-171">单击 "**搜索**" 以运行搜索。</span><span class="sxs-lookup"><span data-stu-id="8e294-171">Click **Search** to run the search.</span></span> 
    
7. <span data-ttu-id="8e294-172">当搜索运行完成并显示结果后, 单击 "**导出结果** \> " "**下载所有结果**"。</span><span class="sxs-lookup"><span data-stu-id="8e294-172">When the search is finished running and the results are displayed, click **Export results** \> **Download all results**.</span></span>
    
    <span data-ttu-id="8e294-173">选择 "导出" 选项后, 会在窗口底部显示一条消息, 提示您打开或保存 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="8e294-173">After you select the export option, a message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span>
    
8. <span data-ttu-id="8e294-174">单击 "**另** \>存**为**", 然后将 CSV 文件保存到本地计算机上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8e294-174">Click **Save** \> **Save as** and save the CSV file to a folder on your local computer.</span></span> 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a><span data-ttu-id="8e294-175">步骤 2: 使用 PowerQuery 编辑器设置导出的审核日志的格式</span><span class="sxs-lookup"><span data-stu-id="8e294-175">Step 2: Use the PowerQuery Editor to format the exported audit log</span></span>

<span data-ttu-id="8e294-176">下一步是在 Excel 的 Power Query 编辑器中使用 JSON 转换功能, 以将**AuditData**列中的每个属性 (由多属性 JSON 对象组成) 拆分为自己的列。</span><span class="sxs-lookup"><span data-stu-id="8e294-176">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the **AuditData** column (which consists of a multi-property JSON object) into its own column.</span></span> <span data-ttu-id="8e294-177">这样, 您就可以筛选列以查看与共享相关的记录</span><span class="sxs-lookup"><span data-stu-id="8e294-177">This lets you filter columns to view records related to sharing</span></span>

<span data-ttu-id="8e294-178">有关分步说明, 请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)中的 "步骤 2: 使用 Power Query Editor 格式化导出的审核日志"。</span><span class="sxs-lookup"><span data-stu-id="8e294-178">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a><span data-ttu-id="8e294-179">步骤 3: 筛选 CSV 文件, 以获取与外部用户共享的资源</span><span class="sxs-lookup"><span data-stu-id="8e294-179">Step 3: Filter the CSV file for resources shared with external users</span></span>

<span data-ttu-id="8e294-180">下一步是筛选 CSV, 以获取之前在 " [SharePoint 共享事件](#sharepoint-sharing-events)" 部分中描述的与共享相关的不同事件。</span><span class="sxs-lookup"><span data-stu-id="8e294-180">The next step is to filter the CSV for the different sharing-related events that were previously described in the [SharePoint sharing events](#sharepoint-sharing-events) section.</span></span> <span data-ttu-id="8e294-181">或者, 可以筛选**TargetUserOrGroupType**列以显示此属性的值为 "**来宾**" 的所有记录。</span><span class="sxs-lookup"><span data-stu-id="8e294-181">Alternatively, you can filter the **TargetUserOrGroupType** column to display all records where the value of this property is **Guest**.</span></span> 

<span data-ttu-id="8e294-182">按照上一步中的说明操作, 使用 PowerQuery 编辑器准备 CSV 文件后, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="8e294-182">After you've followed the instructions in the previous step to prepare the CSV file by using the PowerQuery editor, do the following:</span></span>
    
1. <span data-ttu-id="8e294-183">打开您在步骤2中创建的 Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="8e294-183">Open the Excel file that you created in Step 2.</span></span> 

2. <span data-ttu-id="8e294-184">在 "**开始**" 选项卡上, 单击 "**排序 & 筛选**", 然后单击 "**筛选**"。</span><span class="sxs-lookup"><span data-stu-id="8e294-184">On the **Home** tab, click **Sort & Filter**, and then click **Filter**.</span></span>
    
3. <span data-ttu-id="8e294-185">在 "**操作**" 列上的 "**排序 & 筛选**" 下拉列表中, 清除所有选择, 然后选择一个或多个以下与共享相关的事件, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="8e294-185">In the **Sort & Filter** dropdown list on the **Operations** column, clear all selections, then select one or more the following sharing-related events and then click **Ok**.</span></span>
 
   - <span data-ttu-id="8e294-186">**SharingInvitationCreated**</span><span class="sxs-lookup"><span data-stu-id="8e294-186">**SharingInvitationCreated**</span></span>
   
   - <span data-ttu-id="8e294-187">**AnonymousLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="8e294-187">**AnonymousLinkCreated**</span></span>
   
   - <span data-ttu-id="8e294-188">**SecureLinkCreated**</span><span class="sxs-lookup"><span data-stu-id="8e294-188">**SecureLinkCreated**</span></span>
   
   - <span data-ttu-id="8e294-189">**AddedToSecureLink**</span><span class="sxs-lookup"><span data-stu-id="8e294-189">**AddedToSecureLink**</span></span> 
    
    <span data-ttu-id="8e294-190">Excel 将显示所选事件的行。</span><span class="sxs-lookup"><span data-stu-id="8e294-190">Excel displays the rows for the events you selected.</span></span>
    
4. <span data-ttu-id="8e294-191">转到名为**TargetUserOrGroupType**的列, 然后选择它。</span><span class="sxs-lookup"><span data-stu-id="8e294-191">Go to the column named **TargetUserOrGroupType** and select it.</span></span> 
    
5. <span data-ttu-id="8e294-192">在 "**排序 & 筛选**" 下拉列表中, 清除 "所有选择", 然后选择 " **TargetUserOrGroupType: Guest**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="8e294-192">In the **Sort & Filter** dropdown list, clear all selections, then select **TargetUserOrGroupType:Guest**, and click **Ok**.</span></span>
    
    <span data-ttu-id="8e294-193">现在, Excel 将显示共享事件的行以及目标用户在组织外部的位置, 因为外部用户由值**TargetUserOrGroupType: Guest**标识。</span><span class="sxs-lookup"><span data-stu-id="8e294-193">Now Excel displays the rows for sharing events AND where the target user is outside of your organization, because external users are identified by the value **TargetUserOrGroupType:Guest**.</span></span> 
  
> [!TIP]
> <span data-ttu-id="8e294-194">对于显示的审核记录, **ObjectId**列标识与目标用户共享的资源;例如`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`。</span><span class="sxs-lookup"><span data-stu-id="8e294-194">For the audit records that are displayed, the **ObjectId** column identifies the resource that was shared with the target user; for example  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.</span></span>

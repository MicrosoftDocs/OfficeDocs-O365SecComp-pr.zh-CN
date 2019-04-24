---
title: 打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
description: 了解如何为 SharePoint、OneDrive 和团队打开 ATP, 包括如何为检测到的文件设置通知。
ms.openlocfilehash: 30eb28bfc5156664656ca1c200f9e999661b3b0c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264288"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ad6ec-103">打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ad6ec-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="ad6ec-104">[适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](atp-for-spo-odb-and-teams.md)可防止您的组织无意中共享恶意文件。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-104">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="ad6ec-105">检测到恶意文件时, 将阻止该文件, 以便在组织的安全团队执行进一步操作之前, 任何人都无法打开、复制、移动或共享该文件。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-105">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="ad6ec-106">阅读本文以打开 SharePoint、OneDrive 和团队的 ATP, 设置通知以获得检测到的文件的通知, 并采取后续步骤。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-106">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span> 
  
<span data-ttu-id="ad6ec-107">若要定义 (或编辑) ATP 策略, 必须为您分配适当的角色。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-107">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="ad6ec-108">下表介绍了一些示例:</span><span class="sxs-lookup"><span data-stu-id="ad6ec-108">Some examples are described in the following table:</span></span>

|<span data-ttu-id="ad6ec-109">Role</span><span class="sxs-lookup"><span data-stu-id="ad6ec-109">Role</span></span>  |<span data-ttu-id="ad6ec-110">分配的位置/方式</span><span class="sxs-lookup"><span data-stu-id="ad6ec-110">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="ad6ec-111">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="ad6ec-111">Office 365 Global Administrator</span></span> |<span data-ttu-id="ad6ec-112">默认情况下, 注册购买 Office 365 的人是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-112">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="ad6ec-113">(请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)</span><span class="sxs-lookup"><span data-stu-id="ad6ec-113">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="ad6ec-114">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="ad6ec-114">Security Administrator</span></span> |<span data-ttu-id="ad6ec-115">Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="ad6ec-115">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="ad6ec-116">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="ad6ec-116">Exchange Online Organization Management</span></span> |<span data-ttu-id="ad6ec-117">Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="ad6ec-117">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="ad6ec-118">或</span><span class="sxs-lookup"><span data-stu-id="ad6ec-118">or</span></span> <br>  <span data-ttu-id="ad6ec-119">PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="ad6ec-119">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ad6ec-120">启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="ad6ec-120">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="ad6ec-121">在**开始此过程之前, 请确保已为您的 Office 365 环境启用审核日志记录**。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-121">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**.</span></span> <span data-ttu-id="ad6ec-122">这通常由在 Exchange Online 中分配了审核日志角色的人完成。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-122">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="ad6ec-123">有关详细信息, 请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-123">For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
  
1. <span data-ttu-id="ad6ec-124">转到[https://protection.office.com](https://protection.office.com), 然后使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-124">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="ad6ec-125">在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下, 选择 "**策略** \> **安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-125">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span> <br/><span data-ttu-id="ad6ec-126">![在 "安全&amp;合规性中心" 中, \>选择 "威胁管理策略"](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span><span class="sxs-lookup"><span data-stu-id="ad6ec-126">![In the Security &amp; Compliance Center, choose Threat management \> Policy](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span></span>
  
3. <span data-ttu-id="ad6ec-127">选择 "**为 SharePoint、OneDrive 和 Microsoft 团队启用 ATP**"。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-127">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span><br/><span data-ttu-id="ad6ec-128">![为 SharePoint Online、OneDrive for business 和 Microsoft 团队启用高级威胁防护](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span><span class="sxs-lookup"><span data-stu-id="ad6ec-128">![Turn on Advanced Threat Protection for SharePoint Online, OneDrive for Business, and Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span></span>
  
4. <span data-ttu-id="ad6ec-129">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-129">Click **Save**.</span></span>
    
5. <span data-ttu-id="ad6ec-130">查看 (并根据需要编辑) 您组织的[安全附件策略](set-up-atp-safe-attachments-policies.md)和[安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-130">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>
    
6. <span data-ttu-id="ad6ec-131">适合作为全局管理员或 SharePoint Online 管理员, 运行**[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet, 并将**DisallowInfectedFileDownload**参数设置为*true*。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-131">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true*.</span></span> <br/>
      - <span data-ttu-id="ad6ec-132">如果将参数设置为*true, 则*会阻止检测到的文件的所有操作 (删除除外)。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-132">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="ad6ec-133">用户无法打开、移动、复制或共享检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-133">People cannot open, move, copy, or share detected files.</span></span>
      - <span data-ttu-id="ad6ec-134">将参数设置为*false*将阻止除 "删除" 和 "下载" 以外的所有操作。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-134">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="ad6ec-135">用户可以选择接受风险并下载检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-135">People can choose to accept the risk and download a detected file.</span></span>  
   
7. <span data-ttu-id="ad6ec-136">允许最长30分钟的更改传播到所有的 Office 365 数据中心。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-136">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>
    
8. <span data-ttu-id="ad6ec-137">适合继续设置针对检测到的文件的通知。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-137">(Recommended) Proceed to set up alerts for detected files.</span></span>
    
<span data-ttu-id="ad6ec-138">若要了解有关在 Office 365 中使用 PowerShell 的详细信息, 请参阅[使用 powershell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-138">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span> 

<span data-ttu-id="ad6ec-139">若要详细了解在将文件检测为恶意时的用户体验, 请参阅在[SharePoint Online、OneDrive 或 Microsoft 团队中找到恶意文件时应执行的操作](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-139">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span> 
  
## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="ad6ec-140">为检测到的文件设置通知</span><span class="sxs-lookup"><span data-stu-id="ad6ec-140">Set up alerts for detected files</span></span>

<span data-ttu-id="ad6ec-141">若要在 SharePoint Online、OneDrive for business 或 Microsoft 团队中的文件被标识为恶意文件时收到通知, 可以设置警报。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-141">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>
  
1. <span data-ttu-id="ad6ec-142">在 " [Office 365 安全&amp;合规中心](https://protection.office.com)" 中, 选择 "**通知** \> " "**管理通知**"。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-142">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>
    
2. <span data-ttu-id="ad6ec-143">选择 "**新建警报策略**"。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-143">Choose **New alert policy**.</span></span>
    
3. <span data-ttu-id="ad6ec-144">指定警报的名称。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-144">Specify a name for the alert.</span></span> <span data-ttu-id="ad6ec-145">例如, 可以在库中键入恶意文件。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-145">For example, you could type Malicious Files in Libraries.</span></span>
    
4. <span data-ttu-id="ad6ec-146">键入警报的说明。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-146">Type a description for the alert.</span></span> <span data-ttu-id="ad6ec-147">例如, 可以键入在 SharePoint Online、OneDrive 或 Microsoft 团队中检测到恶意文件时通知管理员。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-147">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
    
5. <span data-ttu-id="ad6ec-148">在 "**发送此通知**的条件 ..." 部分, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="ad6ec-148">In the **Send this alert when...** section, do the following:</span></span> 
    
    <span data-ttu-id="ad6ec-149">a.</span><span class="sxs-lookup"><span data-stu-id="ad6ec-149">a.</span></span> <span data-ttu-id="ad6ec-150">在 "**活动**" 列表中, 选择 "**文件中检测到的恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-150">In the **Activities** list, choose **Detected malware in file**.</span></span>
    
    <span data-ttu-id="ad6ec-151">b.</span><span class="sxs-lookup"><span data-stu-id="ad6ec-151">b.</span></span> <span data-ttu-id="ad6ec-152">将 "**用户**" 字段留空。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-152">Leave the **Users** field empty.</span></span> 
    
6. <span data-ttu-id="ad6ec-153">在 "**将此通知发送给 ...** " 部分, 选择一个或多个全局管理员、安全管理员或在检测到恶意文件时应收到通知的安全阅读者。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-153">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span> 
    
7. <span data-ttu-id="ad6ec-154">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-154">Click **Save**.</span></span>
    
<span data-ttu-id="ad6ec-155">若要了解有关通知的详细信息, 请参阅[在 Office 365 安全&amp;合规中心中创建活动通知](create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="ad6ec-155">To learn more about alerts, see [Create activity alerts in the Office 365 Security &amp; Compliance Center](create-activity-alerts.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="ad6ec-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ad6ec-156">Next steps</span></span>

1. [<span data-ttu-id="ad6ec-157">查看有关在 SharePoint、OneDrive 或 Microsoft 团队中检测到的恶意文件的信息</span><span class="sxs-lookup"><span data-stu-id="ad6ec-157">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [<span data-ttu-id="ad6ec-158">以 Office 365 中的管理员身份管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="ad6ec-158">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
    

  


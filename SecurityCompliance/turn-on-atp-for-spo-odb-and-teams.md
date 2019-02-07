---
title: 打开 Office 365 ATP SharePoint、 OneDrive 和 Microsoft 团队
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
description: 了解如何开启 ATP for OneDrive 和团队，包括如何设置检测到的文件的通知。
ms.openlocfilehash: 9745d45428035cc52346d19aa42e5e134123d016
ms.sourcegitcommit: d6a28c4f6db6a676ca960173e8ff8f17d4aa1c4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29755293"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7611a-103">打开 Office 365 ATP SharePoint、 OneDrive 和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="7611a-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="7611a-p101">[Office 365 ATP SharePoint、 OneDrive 和 Microsoft 团队](atp-for-spo-odb-and-teams.md)可防止组织不小心共享恶意文件。检测到恶意文件时，该文件被阻止，以便没有打开、 复制、 移动或共享它，直到由组织的安全组采取进一步的操作。阅读此文，针对 SharePoint 打开 ATP，OneDrive 和团队，设置警报通知有关检测到的文件，并执行您下一步步骤。</span><span class="sxs-lookup"><span data-stu-id="7611a-p101">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files. When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team. Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span> 
  
<span data-ttu-id="7611a-107">若要定义 （或编辑） ATP 策略，您必须为分配下表中所述的角色之一：</span><span class="sxs-lookup"><span data-stu-id="7611a-107">To define (or edit) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="7611a-108">角色</span><span class="sxs-lookup"><span data-stu-id="7611a-108">Role</span></span>  |<span data-ttu-id="7611a-109">其中/如何分配</span><span class="sxs-lookup"><span data-stu-id="7611a-109">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="7611a-110">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="7611a-110">Office 365 Global Administrator</span></span> |<span data-ttu-id="7611a-p102">注册以购买 Office 365 的人是默认情况下是全局管理员。（请参阅要了解的[有关 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。</span><span class="sxs-lookup"><span data-stu-id="7611a-p102">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="7611a-113">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="7611a-113">Security Administrator</span></span> |<span data-ttu-id="7611a-114">Azure Active Directory 管理员中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="7611a-114">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="7611a-115">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="7611a-115">Exchange Online Organization Management</span></span> |<span data-ttu-id="7611a-116">Exchange 管理员中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="7611a-116">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="7611a-117">或</span><span class="sxs-lookup"><span data-stu-id="7611a-117">or</span></span> <br>  <span data-ttu-id="7611a-118">PowerShell cmdlet (请参阅[Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="7611a-118">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="7611a-119">启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="7611a-119">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="7611a-p103">**开始此过程，请确保审核日志记录您的 Office 365 环境已开启**。这通常是具有审核日志角色分配在 Exchange Online 的人。有关详细信息，请参阅[打开或关闭，打开 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="7611a-p103">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>
  
1. <span data-ttu-id="7611a-123">转到[https://protection.office.com](https://protection.office.com)，并使用您的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="7611a-123">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="7611a-124">Office 365 安全性&amp;合规性中心在左侧的导航窗格中，**威胁管理**下面，选择**策略** \> **安全的附件**。</span><span class="sxs-lookup"><span data-stu-id="7611a-124">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span> <br/><span data-ttu-id="7611a-125">![安全中&amp;合规性中心中，选择威胁管理\>策略](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span><span class="sxs-lookup"><span data-stu-id="7611a-125">![In the Security &amp; Compliance Center, choose Threat management \> Policy](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)</span></span>
  
3. <span data-ttu-id="7611a-126">选择**SharePoint、 OneDrive 和 Microsoft 团队 ATP 打开**。</span><span class="sxs-lookup"><span data-stu-id="7611a-126">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span><br/><span data-ttu-id="7611a-127">![启用高级的威胁 Protection for SharePoint Online，OneDrive for Business 和 Microsoft 团队](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span><span class="sxs-lookup"><span data-stu-id="7611a-127">![Turn on Advanced Threat Protection for SharePoint Online, OneDrive for Business, and Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)</span></span>
  
4. <span data-ttu-id="7611a-128">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7611a-128">Click **Save**.</span></span>
    
5. <span data-ttu-id="7611a-129">查看 （和，根据需要编辑） 贵组织的[安全附件策略](set-up-atp-safe-attachments-policies.md)和[安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7611a-129">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>
    
6. <span data-ttu-id="7611a-130">（推荐）以全局管理员或 SharePoint Online 管理员，运行**[Set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet， **DisallowInfectedFileDownload**参数设置为*true*。</span><span class="sxs-lookup"><span data-stu-id="7611a-130">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true*.</span></span> <br/>
      - <span data-ttu-id="7611a-p104">设置为*true*的块的参数 （除删除） 的所有操作检测到文件。人员无法打开、 移动、 复制或共享检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="7611a-p104">Setting the parameter to *true* blocks all actions (except Delete) for detected files. People cannot open, move, copy, or share detected files.</span></span>
      - <span data-ttu-id="7611a-p105">参数设置为*false*会阻止除删除和下载的所有操作。人员可以选择接受风险并下载检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="7611a-p105">Setting the parameter to *false* blocks all actions except Delete and Download. People can choose to accept the risk and download a detected file.</span></span>  
   
7. <span data-ttu-id="7611a-135">允许您更改传播到所有 Office 365 数据中心最多 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="7611a-135">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>
    
8. <span data-ttu-id="7611a-136">（推荐）继续设置通知检测到的文件。</span><span class="sxs-lookup"><span data-stu-id="7611a-136">(Recommended) Proceed to set up alerts for detected files.</span></span>
    
<span data-ttu-id="7611a-137">若要了解有关使用 Office 365 PowerShell 的详细信息，请参阅[使用 PowerShell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7611a-137">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span> 

<span data-ttu-id="7611a-138">若要了解有关用户体验的详细信息时为恶意检测到一个文件，请参阅[SharePoint Online、 OneDrive 或的 Microsoft 团队中找到的恶意文件时要执行什么](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。</span><span class="sxs-lookup"><span data-stu-id="7611a-138">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span> 
  
## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="7611a-139">设置通知检测到的文件</span><span class="sxs-lookup"><span data-stu-id="7611a-139">Set up alerts for detected files</span></span>

<span data-ttu-id="7611a-140">若要在 SharePoint Online、 OneDrive 业务，或 Microsoft 团队的文件已被标识为恶意时收到通知，您可以设置一条通知。</span><span class="sxs-lookup"><span data-stu-id="7611a-140">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>
  
1. <span data-ttu-id="7611a-141">在[Office 365 安全性&amp;合规性中心](https://protection.office.com)，选择**警报** \> **管理通知**。</span><span class="sxs-lookup"><span data-stu-id="7611a-141">In the [Office 365 Security &amp; Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>
    
2. <span data-ttu-id="7611a-142">选择**新建通知的策略**。</span><span class="sxs-lookup"><span data-stu-id="7611a-142">Choose **New alert policy**.</span></span>
    
3. <span data-ttu-id="7611a-p106">指定通知的名称。例如，您可以在库中键入恶意文件。</span><span class="sxs-lookup"><span data-stu-id="7611a-p106">Specify a name for the alert. For example, you could type Malicious Files in Libraries.</span></span>
    
4. <span data-ttu-id="7611a-p107">键入通知的说明。例如，SharePoint Online、 OneDrive 或的 Microsoft 团队中检测到恶意文件时，您可以键入通知管理员。</span><span class="sxs-lookup"><span data-stu-id="7611a-p107">Type a description for the alert. For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
    
5. <span data-ttu-id="7611a-147">在**发送此通知时...** 部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7611a-147">In the **Send this alert when...** section, do the following:</span></span> 
    
    <span data-ttu-id="7611a-p108">答： 在**活动**列表中，选择**文件中的检测到恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="7611a-p108">a. In the **Activities** list, choose **Detected malware in file**.</span></span>
    
    <span data-ttu-id="7611a-p109">b.保留**用户**字段为空。</span><span class="sxs-lookup"><span data-stu-id="7611a-p109">b. Leave the **Users** field empty.</span></span> 
    
6. <span data-ttu-id="7611a-152">在**发送到此通知...** 部分中，选择一个或多个全局管理员、 安全管理员或安全读者应在检测到恶意文件时收到通知。</span><span class="sxs-lookup"><span data-stu-id="7611a-152">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span> 
    
7. <span data-ttu-id="7611a-153">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7611a-153">Click **Save**.</span></span>
    
<span data-ttu-id="7611a-154">若要了解有关通知的详细信息，请参阅[在 Office 365 安全性中创建活动通知&amp;合规性中心](create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="7611a-154">To learn more about alerts, see [Create activity alerts in the Office 365 Security &amp; Compliance Center](create-activity-alerts.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="7611a-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7611a-155">Next steps</span></span>

1. [<span data-ttu-id="7611a-156">查看有关在 SharePoint、 OneDrive 或的 Microsoft 团队中检测到的恶意文件的信息</span><span class="sxs-lookup"><span data-stu-id="7611a-156">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [<span data-ttu-id="7611a-157">为 Office 365 中的管理员管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="7611a-157">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
    

  


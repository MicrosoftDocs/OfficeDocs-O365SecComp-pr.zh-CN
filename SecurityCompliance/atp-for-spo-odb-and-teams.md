---
title: 适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 11/08/2018
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
description: 将 Office 365 高级威胁保护扩展到 SharePoint Online、 OneDrive for Business 和 Microsoft 团队进行更安全协作为您的组织中的文件。
ms.openlocfilehash: 29676bf7c326adf366cca79a59f5b4c40c672baa
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014814"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ef8de-103">适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ef8de-103">Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="ef8de-104">Office 365 ATP SharePoint、 OneDrive 和 Microsoft 团队的概述</span><span class="sxs-lookup"><span data-stu-id="ef8de-104">Overview of Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="ef8de-p101">定期人员共享文件和协作使用 SharePoint、 OneDrive 和 Microsoft 团队。与[Office 365 高级威胁保护](office-365-atp.md)(ATP)，您的组织可以更安全的方式进行协作。ATP 有助于检测和阻止的工作组网站和文档库中标识为恶意文件。</span><span class="sxs-lookup"><span data-stu-id="ef8de-p101">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams. With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner. ATP helps detect and block files that are identified as malicious in team sites and document libraries.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="ef8de-108">如何工作</span><span class="sxs-lookup"><span data-stu-id="ef8de-108">How it works</span></span>

<span data-ttu-id="ef8de-p102">当 SharePoint Online 中的文件时，OneDrive for Business 和 Microsoft 团队被标识为恶意，ATP 直接与锁定该文件的文件存储集成。下图显示了在库中检测到恶意文件的示例。</span><span class="sxs-lookup"><span data-stu-id="ef8de-p102">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file. The following image shows an example of a malicious file detected in a library.</span></span>
  
<span data-ttu-id="ef8de-111">[![文件中的 OneDrive for Business 使用一个检测为恶意](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="ef8de-111">[![Files in OneDrive for Business with one detected as malicious](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="ef8de-p103">尽管阻止的文件仍列在的文档库和 web、 移动或桌面应用程序，但阻止的文件无法打开、 复制、 移动或共享。人员可以但是，删除被阻止的文件。下面是用户的移动设备的内容的示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="ef8de-p103">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared. People can, however, delete a blocked file. Here's an example of what that looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="ef8de-115">[![从 OneDrive 移动应用程序的 OneDrive for Business 中删除阻止的文件](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="ef8de-115">[![Deleting a blocked file from OneDrive for Business from the OneDrive mobile app](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="ef8de-p104">根据 Office 365 的配置方式，人员可能或可能不具有下载阻止的文件的功能。下面是什么下载阻止的文件在用户的移动设备上如下所示：</span><span class="sxs-lookup"><span data-stu-id="ef8de-p104">Depending on how Office 365 is configured, people might or might not have the ability to download a blocked file. Here's what downloading a blocked file looks like on a user's mobile device:</span></span>
  
<span data-ttu-id="ef8de-118">[![下载阻止的文件中的 OneDrive for Business](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="ef8de-118">[![Downloading a blocked file in OneDrive for Business](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span></span>
  
<span data-ttu-id="ef8de-119">若要了解详细信息，请参阅[打开 SharePoint、 OneDrive 和 Microsoft 团队的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ef8de-119">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
  
## <a name="keep-these-points-in-mind"></a><span data-ttu-id="ef8de-120">请记住以下几点</span><span class="sxs-lookup"><span data-stu-id="ef8de-120">Keep these points in mind</span></span>

- <span data-ttu-id="ef8de-p105">ATP 将不扫描业务，或 Microsoft 团队的 SharePoint Online、 OneDrive 中的每个文件。这是设计。通过使用共享和来宾活动事件，以及智能启发和威胁信号标识恶意文件的过程以异步方式，扫描文件。</span><span class="sxs-lookup"><span data-stu-id="ef8de-p105">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams. This is by design. Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="ef8de-p106">请确保您的 SharePoint 网站配置为使用[现代体验](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。当文件被标识为恶意和被阻止时，用户可以看到的现代的体验，但不是经典视图中已发生此。ATP 保护适用是使用现代体验还是经典视图;但是，文件被阻止的可视指示器中存在仅现代的体验。</span><span class="sxs-lookup"><span data-stu-id="ef8de-p106">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view. ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.</span></span>
    
- <span data-ttu-id="ef8de-127">标识为恶意 SharePoint Online 中的文件，OneDrive for Business 或 Microsoft 团队会显示在[Office 365 高级威胁保护报告](view-reports-for-atp.md)和威胁资源管理器 （ [Office 365 威胁智能](office-365-ti.md)的一部分）。</span><span class="sxs-lookup"><span data-stu-id="ef8de-127">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in Threat Explorer (part of [Office 365 Threat Intelligence](office-365-ti.md)).</span></span>
    
- <span data-ttu-id="ef8de-p107">ATP 是贵组织的总体威胁保护策略，其中包括反垃圾邮件和反恶意软件保护，以及安全链接和安全的附件的一部分。若要了解详细信息，请参阅[Office 365 中的威胁的保护](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="ef8de-p107">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments. To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="ef8de-p108">SharePoint Online 管理员可以确定是否启用人员下载检测为恶意的文件。这通过运行 Set-spotenant PowerShell cmdlet 使用 DisallowInfectedFileDownload 参数 （请参阅[打开 SharePoint、 OneDrive 和 Microsoft 团队的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)）。</span><span class="sxs-lookup"><span data-stu-id="ef8de-p108">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious. This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>
    
## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="ef8de-132">联机隔离 ATP for SharePoint、 OneDrive for Business 和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="ef8de-132">Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="ef8de-133">开始在后期年 5 月 2018 安全中[隔离](quarantine-email-messages.md)功能&amp;合规性中心将正在扩展到 ATP for SharePoint Online，OneDrive for Business 和 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="ef8de-133">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>
  
<span data-ttu-id="ef8de-p109">当 SharePoint Online 中的文件时，OneDrive for Business 或 Microsoft 团队被标识为恶意，除了 ATP 阻止中打开或共享的文件，该文件包含的隔离项目列表中。(安全中&amp;合规性中心中，转到**威胁管理** \> **审阅** \> **隔离**和**内容**筛选器。)</span><span class="sxs-lookup"><span data-stu-id="ef8de-p109">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items. (In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for **Content**.)</span></span> 
  
<span data-ttu-id="ef8de-136">如果您是组织的 Office 365 安全工作组的一部分，并且具有必要[Office 365 安全性分配权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)，可以下载、 发布、 报告和删除为恶意 ATP 检测的文件从隔离。</span><span class="sxs-lookup"><span data-stu-id="ef8de-136">If you're part of your organization's Office 365 security team and have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>
  
- <span data-ttu-id="ef8de-p110">**释放和报告**文件中删除文件的 ATP 块各自的工作组网站或文档库中针对 SharePoint、 OneDrive 或 Microsoft 团队。用户就能够打开、 共享和下载文件。和，选中**将报告发送给 Microsoft**选项后，该文件报告为误报给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="ef8de-p110">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams. Users are then able to open, share, and download the file. And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span> 
    
- <span data-ttu-id="ef8de-p111">**删除文件**从隔离区; 删除的文件但是，阻止的文件是仍要打开或共享。此外必须在其各自的文档库或团队的网站 （SharePoint Online、 OneDrive for Business 或 Microsoft 团队） 中删除文件。</span><span class="sxs-lookup"><span data-stu-id="ef8de-p111">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared. The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span> 
    
- <span data-ttu-id="ef8de-142">**下载文件**，可以下载和分析的文件的任何误报。</span><span class="sxs-lookup"><span data-stu-id="ef8de-142">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="ef8de-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ef8de-143">Next steps</span></span>

1. [<span data-ttu-id="ef8de-144">打开 Office 365 ATP SharePoint、 OneDrive 和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="ef8de-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)
    
2. [<span data-ttu-id="ef8de-145">查看有关在 SharePoint、 OneDrive 或的 Microsoft 团队中检测到的恶意文件的信息</span><span class="sxs-lookup"><span data-stu-id="ef8de-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
    

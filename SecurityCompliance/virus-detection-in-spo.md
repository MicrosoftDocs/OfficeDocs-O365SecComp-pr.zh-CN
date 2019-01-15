---
title: SharePoint Online 中的病毒检测
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 01/14/2019
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
description: Office 365 可以帮助用户上载到 SharePoint Online 的文件中检测病毒通过从恶意软件保护您的环境。上载后执行病毒扫描文件。如果找到的文件感染，属性将设置，以便用户无法下载或同步该文件。
ms.openlocfilehash: ab02d2d4e82e9427ec6b512490f94ccc9c14b54e
ms.sourcegitcommit: 5ccc3dd0d1c087bffd3a8fc807d5d1750f046eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2019
ms.locfileid: "28009588"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="075b4-105">SharePoint Online 中的病毒检测</span><span class="sxs-lookup"><span data-stu-id="075b4-105">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="075b4-p102">Office 365 可以帮助用户上载到 SharePoint Online 的文件中检测病毒通过从恶意软件保护您的环境。上载后执行病毒扫描文件。如果找到的文件感染，属性将设置，以便用户无法下载或同步该文件。</span><span class="sxs-lookup"><span data-stu-id="075b4-p102">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online. Files are scanned for viruses after they are uploaded. If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="075b4-p103">SharePoint Online 中的这些防病毒功能包含病毒的方式。他们不作为单一防御为您的环境的恶意软件。我们鼓励所有客户评估和实施在各个层的反恶意软件保护并应用保护企业基础结构的最佳做法。有关策略和最佳实践的详细信息，请参阅[Office 365 的安全性最佳实践](security-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="075b4-p103">These antivirus capabilities in SharePoint Online are a way to contain viruses. They aren't intended as a single point of defense against malware for your environment. We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure. For more information about strategies and best practices, see [Security best practices for Office 365](security-best-practices.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="075b4-113">感染病毒的文件上载到 SharePoint Online 时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="075b4-113">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="075b4-p104">Office 365 使用的常见病毒检测引擎。引擎在 SharePoint Online 中异步运行，并上载之后扫描文件。当找到的文件包含病毒时，它标记，以使它不能再次下载。在年 4 月 2018，我们将删除扫描文件的 25 MB 限制。</span><span class="sxs-lookup"><span data-stu-id="075b4-p104">Office 365 uses a common virus detection engine. The engine runs asynchronously within SharePoint Online, and scans files after they're uploaded. When a file is found to contain a virus, it's flagged so that it can't be downloaded again. In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="075b4-118">下面是会发生什么情况：</span><span class="sxs-lookup"><span data-stu-id="075b4-118">Here's what happens:</span></span>
  
1. <span data-ttu-id="075b4-119">用户将文件上载到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="075b4-119">A user uploads a file to SharePoint Online.</span></span>
    
2. <span data-ttu-id="075b4-120">病毒检测引擎来扫描该文件。</span><span class="sxs-lookup"><span data-stu-id="075b4-120">The virus detection engine scans the file.</span></span>
    
3. <span data-ttu-id="075b4-121">如果找到了病毒，则病毒引擎指示它被感染的文件上设置的属性。</span><span class="sxs-lookup"><span data-stu-id="075b4-121">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="075b4-122">当用户尝试使用浏览器中下载受感染的文件时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="075b4-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="075b4-123">如果文件感染了病毒，用户不能使用浏览器从 SharePoint Online 下载文件。</span><span class="sxs-lookup"><span data-stu-id="075b4-123">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="075b4-124">下面是会发生什么情况：</span><span class="sxs-lookup"><span data-stu-id="075b4-124">Here's what happens:</span></span>
  
1. <span data-ttu-id="075b4-125">用户打开 web 浏览器并尝试从 SharePoint Online 下载受感染的文件。</span><span class="sxs-lookup"><span data-stu-id="075b4-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="075b4-p105">为用户提供已检测到病毒警告。用户提供下载文件，并尝试进行清理使用自己的病毒软件的选项。</span><span class="sxs-lookup"><span data-stu-id="075b4-p105">The user is given a warning that a virus has been detected. The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="075b4-p106">可以使用**DisallowInfectedFileDownload**参数使用 Set-spotenant cmdlet 以不允许用户下载检测到的文件，即使在防病毒警告窗口中。请参阅 [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。</span><span class="sxs-lookup"><span data-stu-id="075b4-p106">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window. See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="075b4-130">当 OneDrive 同步客户端尝试同步感染病毒的文件时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="075b4-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="075b4-p107">如果文件包含病毒，用户同步与新 OneDrive 同步客户端 (OneDrive.exe) 或以前 OneDrive for Business 同步客户端 (Groove.exe) 文件，是否同步客户端不会对其进行下载。同步客户端将显示通知，不能同步该文件。</span><span class="sxs-lookup"><span data-stu-id="075b4-p107">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it. The sync client will display a notification that the file can't be synced.</span></span>
  


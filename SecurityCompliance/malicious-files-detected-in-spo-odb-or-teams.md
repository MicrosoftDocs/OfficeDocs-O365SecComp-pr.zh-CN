---
title: 查看有关在 SharePoint、 OneDrive 或的 Microsoft 团队中检测到的恶意文件的信息
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
description: 了解在哪里查看有关在 SharePoint、 OneDrive 或团队中检测到的恶意文件的信息以及如何对这些文件执行操作。
ms.openlocfilehash: c22e57e34cccafa3dd30a77a5a6011f2999f708c
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706196"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a><span data-ttu-id="928d0-103">查看有关在 SharePoint、 OneDrive 或的 Microsoft 团队中检测到的恶意文件的信息</span><span class="sxs-lookup"><span data-stu-id="928d0-103">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>

<span data-ttu-id="928d0-p101">[SharePoint、 OneDrive 和 Microsoft 团队的 office 365 ATP](atp-for-spo-odb-and-teams.md)从文档库和工作组网站中的恶意文件保护您的组织。检测到恶意文件时，该文件被阻止，以便没有打开、 复制、 移动或共享它，直到由组织的安全组采取进一步的操作。阅读此文，了解如何查看有关检测到的文件的信息和要采取的操作。</span><span class="sxs-lookup"><span data-stu-id="928d0-p101">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from malicious files in document libraries and team sites. When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team. Read this article to learn how to view information about detected files and what actions to take.</span></span> 

<span data-ttu-id="928d0-107">若要执行本文中描述的任务，您必须具有必要[Office 365 安全权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="928d0-107">In order to perform the tasks described in this article, you must have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="view-reports-with-information-about-detected-files"></a><span data-ttu-id="928d0-108">查看报告包含有关检测到的文件的信息</span><span class="sxs-lookup"><span data-stu-id="928d0-108">View reports with information about detected files</span></span>

<span data-ttu-id="928d0-109">若要查看状态和有关通过 Office 365 ATP 检测到的文件的详细的信息，您可以使用威胁保护状态报告。</span><span class="sxs-lookup"><span data-stu-id="928d0-109">To view status and detailed information about files that were detected by Office 365 ATP, you can use the Threat Protection Status report.</span></span>
  
1. <span data-ttu-id="928d0-110">在[Office 365 安全性&amp;合规性中心](https://security.microsoft.com)，选择**报告** \> **仪表板** \> **威胁保护状态**。</span><span class="sxs-lookup"><span data-stu-id="928d0-110">In the [Office 365 Security &amp; Compliance Center](https://security.microsoft.com), choose **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
    
2. <span data-ttu-id="928d0-111">在报表的右上角，选择**查看详细信息表**。</span><span class="sxs-lookup"><span data-stu-id="928d0-111">In the upper right corner of the report, choose **View details table**.</span></span>
    
3. <span data-ttu-id="928d0-112">查看报告中检测到的文件的列表。</span><span class="sxs-lookup"><span data-stu-id="928d0-112">View the list of files that were detected in the report.</span></span>
    
4. <span data-ttu-id="928d0-113">在查看详细的信息，包括执行的操作、 文件名、 文件路径，和列表中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="928d0-113">Select an item in the list to view detailed information, including actions taken, the file name, the file path, and more.</span></span>
    
5. <span data-ttu-id="928d0-114">选择**高级分析**选项卡查看信息，如观察到的行为和分析详细信息。</span><span class="sxs-lookup"><span data-stu-id="928d0-114">Choose the **Advanced Analysis** tab to view information, such as observed behavior and analysis details.</span></span> 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a><span data-ttu-id="928d0-115">查看并隔离中对文件执行操作</span><span class="sxs-lookup"><span data-stu-id="928d0-115">View and take action on files in quarantine</span></span>

1. <span data-ttu-id="928d0-116">Office 365 安全性&amp;合规性中心中，选择**威胁管理** \> **审阅** \> **隔离**。</span><span class="sxs-lookup"><span data-stu-id="928d0-116">In the Office 365 Security &amp; Compliance Center, choose **Threat management** \> **Review** \> **Quarantine**.</span></span>
    
2. <span data-ttu-id="928d0-117">左上角，将筛选器从**电子邮件**更改为**内容**。</span><span class="sxs-lookup"><span data-stu-id="928d0-117">In the upper left corner, change the filter from **Email** to **Content**.</span></span>
    
3. <span data-ttu-id="928d0-118">在查看详细的信息，包括文件的 URL 列表中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="928d0-118">Select an item in the list to view detailed information, including the file's URL.</span></span>
    
4. <span data-ttu-id="928d0-119">选择可用操作。</span><span class="sxs-lookup"><span data-stu-id="928d0-119">Choose an available action.</span></span>
    
  - <span data-ttu-id="928d0-120">选择**版本&amp;报告**取消阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="928d0-120">Choose **Release &amp; report** to unblock the file.</span></span> 
    
    <span data-ttu-id="928d0-121">选择**将报告发送给 Microsoft**以向 Microsoft 将该文件报告为误报。</span><span class="sxs-lookup"><span data-stu-id="928d0-121">Select **Send report to Microsoft** to report the file as a false positive to Microsoft.</span></span> 
    
  - <span data-ttu-id="928d0-122">选择**文件下载**来进行调查进一步的文件。</span><span class="sxs-lookup"><span data-stu-id="928d0-122">Choose **Download file** to investigate the file further.</span></span> 
    
  - <span data-ttu-id="928d0-p102">选择**删除**以从隔离项目的列表中删除该文件。如果您选择此选项，还必须适用于商务或 Microsoft 团队从其各自的库中 SharePoint Online、 OneDrive 删除该文件。打开或共享，则此选项不会不取消阻止被文件。</span><span class="sxs-lookup"><span data-stu-id="928d0-p102">Choose **Delete** to remove the file from the list of quarantined items. If you choose this option, you must also delete the file from its respective library in SharePoint Online, OneDrive for Business, or Microsoft Teams. This option does not unblock a file from being opened or shared.</span></span> 
    
5. <span data-ttu-id="928d0-126">选择**关闭**以关闭的选定项的详细信息。</span><span class="sxs-lookup"><span data-stu-id="928d0-126">Choose **Close** to close the details for a selected item.</span></span> 
  
  


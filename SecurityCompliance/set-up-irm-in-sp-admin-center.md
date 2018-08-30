---
title: 在 SharePoint 管理中心中设置信息权限管理 (IRM)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: 了解如何使用 SharePoint Online IRM 通过 Microsoft Azure Active Directory 权限管理服务 (RMS) 来保护 SharePoint 列表和文档库。
ms.openlocfilehash: dea8c71ce67207b3c40a1f934f90e63740f70f29
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525406"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a><span data-ttu-id="c006f-103">在 SharePoint 管理中心中设置信息权限管理 (IRM)</span><span class="sxs-lookup"><span data-stu-id="c006f-103">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>

<span data-ttu-id="c006f-p101">在 SharePoint Online，IRM 保护应用于列表和库级别的文件。您的组织可以使用 IRM 保护之前，您必须首先设置权限管理。IRM 依赖于中 Azure 信息保护用于加密和分配使用率限制为 Azure 权限管理服务。某些 Office 365 计划包括 Azure 权限管理，而不是所有。若要了解详细信息，请阅读[如何 Office 应用程序和服务支持 Azure 权限管理](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)。</span><span class="sxs-lookup"><span data-stu-id="c006f-p101">Within SharePoint Online, IRM protection is applied to files at the list and library level. Before your organization can use IRM protection, you must first set up Rights Management. IRM relies on the Azure Rights Management service from Azure Information Protection to encrypt and assign usage restrictions. Some Office 365 plans include Azure Rights Management, but not all. To learn more, read [How Office applications and services support Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).</span></span>
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a><span data-ttu-id="c006f-109">启用 IRM 服务使用 SharePoint 管理中心</span><span class="sxs-lookup"><span data-stu-id="c006f-109">Turn on IRM service using SharePoint admin center</span></span>

<span data-ttu-id="c006f-p102">您的组织可以 IRM 保护的 SharePoint 列表和库之前，必须先激活您的组织的权限管理服务。若要了解如何查看[激活 Azure 权限管理](https://docs.microsoft.com/information-protection/deploy-use/activate-service)。您必须使用拥有 Office 365 全局管理员权限，若要启用权限管理服务的工作或学校帐户。否则，您将无法与 SharePoint Online 中使用 IRM 功能。</span><span class="sxs-lookup"><span data-stu-id="c006f-p102">Before your organization can IRM-protect SharePoint lists and libraries, you must first activate the Rights Management service for your organization. To learn how see [Activating Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service). You must use a work or school account that has Office 365 global administrator privileges to enable the Rights Management service. Otherwise, you won't be able to use IRM features with SharePoint Online.</span></span>
  
<span data-ttu-id="c006f-114">激活的权限管理服务后, 登录到 SharePoint 管理中心来启用 IRM。</span><span class="sxs-lookup"><span data-stu-id="c006f-114">After activating the Rights Management service, sign in to the SharePoint admin center to turn on IRM.</span></span>
  
1. <span data-ttu-id="c006f-115">以全局管理员或 SharePoint 管理员身份登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c006f-115">Sign in to Office 365 as a global admin or SharePoint admin.</span></span>
    
2. <span data-ttu-id="c006f-p103">在左上角选择应用启动器图标 ![Office 365 中的应用启动器图标](media/e5aee650-c566-4100-aaad-4cc2355d909f.png)，然后选择“管理”**** 以打开 Office 365 管理中心。（如果看不到“管理”磁贴，表明你在组织中没有 Office 365 管理员权限。）</span><span class="sxs-lookup"><span data-stu-id="c006f-p103">Select the app launcher icon ![The app launcher icon in Office 365](media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in the upper-left and choose **Admin** to open the Office 365 admin center. (If you don't see the Admin tile, you don't have Office 365 administrator permissions in your organization.)</span></span> 
    
3. <span data-ttu-id="c006f-118">在左窗格中，选择**管理中心** \> **SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="c006f-118">In the left pane, choose **Admin centers** \> **SharePoint**.</span></span>
    
4. <span data-ttu-id="c006f-119">在左窗格中，选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="c006f-119">In the left pane, choose **settings**.</span></span>
    
5. <span data-ttu-id="c006f-p104">在**信息权限管理 (IRM)** 部分中，选择**使用您的配置中指定的 IRM 服务**，，然后选择**刷新 IRM 设置**。刷新 IRM 设置后，您的组织中的人员可以开始使用其 SharePoint 列表和文档库中的 IRM。但是，这样的选项可能占用一个小时到要显示在库设置和列表设置中。</span><span class="sxs-lookup"><span data-stu-id="c006f-p104">In the **Information Rights Management (IRM)** section, choose **Use the IRM service specified in your configuration**, and then choose **Refresh IRM Settings**. After you refresh IRM settings, people in your organization can begin using IRM in their SharePoint lists and document libraries. However, the options to do so may take up to an hour to appear in Library Settings and List Settings.</span></span>
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a><span data-ttu-id="c006f-123">IRM 启用 SharePoint 文档库和列表</span><span class="sxs-lookup"><span data-stu-id="c006f-123">IRM-enable SharePoint document libraries and lists</span></span>
<span data-ttu-id="c006f-124"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="c006f-124"></span></span>

<span data-ttu-id="c006f-p105">后，刷新 IRM 设置，网站所有者可 IRM 保护其 SharePoint 列表和文档库。有关详细信息，请参阅[向列表或库应用信息权限管理](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="c006f-p105">After refreshing IRM settings, site owners can IRM-protect their SharePoint lists and document libraries. For more information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="c006f-p106">当网站所有者的列表或库启用 IRM 时，他们可以保护该列表或库中的任何受支持的文件类型。当为库启用 IRM 时，权限管理适用于所有的库中的文件。当您为列表启用 IRM 时，权限管理仅适用于附加到列表项，不是实际列表项的文件。</span><span class="sxs-lookup"><span data-stu-id="c006f-p106">When site owners enable IRM for a list or library, they can protect any supported file types in that list or library. When IRM is enabled for a library, rights management applies to all of the files in that library. When you enable IRM for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="c006f-p107">当人员下载 IRM 启用列表或库中的文件时，对文件进行加密，以便只有授权的用户可以查看它们。每个权限管理文件还包含对查看该文件的人员限制的发布许可证。典型的限制包括使文件只读的禁用文本，禁止用户保存的本地副本，并禁止用户打印文件复制。可以读取 IRM 支持的文件类型的客户端程序权限管理文件内使用的发布许可证强制实施这些限制。这是如何权限管理文件保留保护，即使它为下载。若要在列表或库上启用 IRM，请参阅[对列表或库应用信息权限管理](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="c006f-p107">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them. Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file. Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file. Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions. This is how a rights-managed file retains its protection even after it is downloaded. To enable IRM on a list or library, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="c006f-p108">您无法创建或编辑文档中使用 Office Online 的已启用 IRM 的库。相反，一次一个人可以下载和编辑 IRM 加密的文件。使用签入和签出管理*共同创作*，或创作跨多个用户。</span><span class="sxs-lookup"><span data-stu-id="c006f-p108">You cannot create or edit documents in an IRM-enabled library using Office Online. Instead, one person at a time can download and edit IRM-encrypted files. Use check-in and check-out to manage  *co-authoring*  , or authoring across multiple users.</span></span> 
  
<span data-ttu-id="c006f-p109">从受 IRM 保护的库中下载 PDF 文件时，Office 365 创建受保护的 PDF 文件。都不会更改文件扩展名，但该文件受保护。要查看此文件，您将需要 Azure 信息保护查看器中，完整的 Azure 信息保护客户端，或另一个应用程序支持查看受保护的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="c006f-p109">When you download a PDF file from an IRM-protected library, Office 365 creates a protected PDF file. The file's extension won't change, but the file is protected. To view this file you'll need the Azure Information Protection viewer, the full Azure Information Protection client, or another application that supports viewing protected PDF files.</span></span> 
  
<span data-ttu-id="c006f-142">SharePoint Online 支持以下文件类型的加密：</span><span class="sxs-lookup"><span data-stu-id="c006f-142">SharePoint Online supports encryption of the following file types:</span></span>
  
- <span data-ttu-id="c006f-143">PDF</span><span class="sxs-lookup"><span data-stu-id="c006f-143">PDF</span></span>
    
- <span data-ttu-id="c006f-144">下面的 Microsoft Office 程序的 97-2003年文件格式： Word、 Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c006f-144">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="c006f-145">以下 Microsoft Office 程序的 Office Open XML 格式： Word、 Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c006f-145">The Office Open XML formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="c006f-146">XML 纸张规范 (XPS) 格式</span><span class="sxs-lookup"><span data-stu-id="c006f-146">The XML Paper Specification (XPS) format</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="c006f-147">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c006f-147">Next steps</span></span>
<span data-ttu-id="c006f-148"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="c006f-148"></span></span>

<span data-ttu-id="c006f-p110">一旦 for SharePoint Online 中启用 IRM，您可以开始将权限管理应用于列表和库。有关信息，请参阅[向列表或库应用信息权限管理](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="c006f-p110">Once you've enabled IRM for SharePoint Online, you can start applying rights management to lists and libraries. For information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="c006f-p111">用于 Windows 的新 OneDrive 同步客户端现在支持同步受 IRM 保护的 SharePoint 文档库和 OneDrive 位置 （只要库的 IRM 设置未设置到期文档访问权限）。有关详细信息，或开始部署新的同步客户端，请参阅[Deploy Windows 的新 OneDrive 同步客户端](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668)。</span><span class="sxs-lookup"><span data-stu-id="c006f-p111">The new OneDrive sync client for Windows now supports synchronizing IRM-protected SharePoint document libraries and OneDrive locations (as long as the IRM setting for the library isn't set to expire document access rights). For more information, or to get started deploying the new sync client, see [Deploy the new OneDrive sync client for Windows](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668).</span></span>
  
[<span data-ttu-id="c006f-153">返回页首</span><span class="sxs-lookup"><span data-stu-id="c006f-153">Top of Page</span></span>](set-up-irm-in-sp-admin-center.md#__top)
  


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
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>在 SharePoint 管理中心中设置信息权限管理 (IRM)

在 SharePoint Online，IRM 保护应用于列表和库级别的文件。您的组织可以使用 IRM 保护之前，您必须首先设置权限管理。IRM 依赖于中 Azure 信息保护用于加密和分配使用率限制为 Azure 权限管理服务。某些 Office 365 计划包括 Azure 权限管理，而不是所有。若要了解详细信息，请阅读[如何 Office 应用程序和服务支持 Azure 权限管理](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)。
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>启用 IRM 服务使用 SharePoint 管理中心

您的组织可以 IRM 保护的 SharePoint 列表和库之前，必须先激活您的组织的权限管理服务。若要了解如何查看[激活 Azure 权限管理](https://docs.microsoft.com/information-protection/deploy-use/activate-service)。您必须使用拥有 Office 365 全局管理员权限，若要启用权限管理服务的工作或学校帐户。否则，您将无法与 SharePoint Online 中使用 IRM 功能。
  
激活的权限管理服务后, 登录到 SharePoint 管理中心来启用 IRM。
  
1. 以全局管理员或 SharePoint 管理员身份登录 Office 365。
    
2. 在左上角选择应用启动器图标 ![Office 365 中的应用启动器图标](media/e5aee650-c566-4100-aaad-4cc2355d909f.png)，然后选择“管理”**** 以打开 Office 365 管理中心。（如果看不到“管理”磁贴，表明你在组织中没有 Office 365 管理员权限。） 
    
3. 在左窗格中，选择**管理中心** \> **SharePoint**。
    
4. 在左窗格中，选择**设置**。
    
5. 在**信息权限管理 (IRM)** 部分中，选择**使用您的配置中指定的 IRM 服务**，，然后选择**刷新 IRM 设置**。刷新 IRM 设置后，您的组织中的人员可以开始使用其 SharePoint 列表和文档库中的 IRM。但是，这样的选项可能占用一个小时到要显示在库设置和列表设置中。
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>IRM 启用 SharePoint 文档库和列表
<a name="__toc220831191"> </a>

后，刷新 IRM 设置，网站所有者可 IRM 保护其 SharePoint 列表和文档库。有关详细信息，请参阅[向列表或库应用信息权限管理](apply-irm-to-a-list-or-library.md)。
  
当网站所有者的列表或库启用 IRM 时，他们可以保护该列表或库中的任何受支持的文件类型。当为库启用 IRM 时，权限管理适用于所有的库中的文件。当您为列表启用 IRM 时，权限管理仅适用于附加到列表项，不是实际列表项的文件。
  
当人员下载 IRM 启用列表或库中的文件时，对文件进行加密，以便只有授权的用户可以查看它们。每个权限管理文件还包含对查看该文件的人员限制的发布许可证。典型的限制包括使文件只读的禁用文本，禁止用户保存的本地副本，并禁止用户打印文件复制。可以读取 IRM 支持的文件类型的客户端程序权限管理文件内使用的发布许可证强制实施这些限制。这是如何权限管理文件保留保护，即使它为下载。若要在列表或库上启用 IRM，请参阅[对列表或库应用信息权限管理](apply-irm-to-a-list-or-library.md)。
  
您无法创建或编辑文档中使用 Office Online 的已启用 IRM 的库。相反，一次一个人可以下载和编辑 IRM 加密的文件。使用签入和签出管理*共同创作*，或创作跨多个用户。 
  
从受 IRM 保护的库中下载 PDF 文件时，Office 365 创建受保护的 PDF 文件。都不会更改文件扩展名，但该文件受保护。要查看此文件，您将需要 Azure 信息保护查看器中，完整的 Azure 信息保护客户端，或另一个应用程序支持查看受保护的 PDF 文件。 
  
SharePoint Online 支持以下文件类型的加密：
  
- PDF
    
- 下面的 Microsoft Office 程序的 97-2003年文件格式： Word、 Excel 和 PowerPoint
    
- 以下 Microsoft Office 程序的 Office Open XML 格式： Word、 Excel 和 PowerPoint
    
- XML 纸张规范 (XPS) 格式
    
## <a name="next-steps"></a>后续步骤
<a name="__toc220831191"> </a>

一旦 for SharePoint Online 中启用 IRM，您可以开始将权限管理应用于列表和库。有关信息，请参阅[向列表或库应用信息权限管理](apply-irm-to-a-list-or-library.md)。
  
用于 Windows 的新 OneDrive 同步客户端现在支持同步受 IRM 保护的 SharePoint 文档库和 OneDrive 位置 （只要库的 IRM 设置未设置到期文档访问权限）。有关详细信息，或开始部署新的同步客户端，请参阅[Deploy Windows 的新 OneDrive 同步客户端](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668)。
  
[返回页首](set-up-irm-in-sp-admin-center.md#__top)
  


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
# <a name="virus-detection-in-sharepoint-online"></a>SharePoint Online 中的病毒检测

Office 365 可以帮助用户上载到 SharePoint Online 的文件中检测病毒通过从恶意软件保护您的环境。上载后执行病毒扫描文件。如果找到的文件感染，属性将设置，以便用户无法下载或同步该文件。
  
> [!IMPORTANT]
> SharePoint Online 中的这些防病毒功能包含病毒的方式。他们不作为单一防御为您的环境的恶意软件。我们鼓励所有客户评估和实施在各个层的反恶意软件保护并应用保护企业基础结构的最佳做法。有关策略和最佳实践的详细信息，请参阅[Office 365 的安全性最佳实践](security-best-practices.md)。 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>感染病毒的文件上载到 SharePoint Online 时，会发生什么情况？

Office 365 使用的常见病毒检测引擎。引擎在 SharePoint Online 中异步运行，并上载之后扫描文件。当找到的文件包含病毒时，它标记，以使它不能再次下载。在年 4 月 2018，我们将删除扫描文件的 25 MB 限制。
  
下面是会发生什么情况：
  
1. 用户将文件上载到 SharePoint Online。
    
2. 病毒检测引擎来扫描该文件。
    
3. 如果找到了病毒，则病毒引擎指示它被感染的文件上设置的属性。
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>当用户尝试使用浏览器中下载受感染的文件时，会发生什么情况？

如果文件感染了病毒，用户不能使用浏览器从 SharePoint Online 下载文件。
  
下面是会发生什么情况：
  
1. 用户打开 web 浏览器并尝试从 SharePoint Online 下载受感染的文件。
    
2. 为用户提供已检测到病毒警告。用户提供下载文件，并尝试进行清理使用自己的病毒软件的选项。

> [!NOTE]
> 可以使用**DisallowInfectedFileDownload**参数使用 Set-spotenant cmdlet 以不允许用户下载检测到的文件，即使在防病毒警告窗口中。请参阅 [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)。
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>当 OneDrive 同步客户端尝试同步感染病毒的文件时，会发生什么情况？

如果文件包含病毒，用户同步与新 OneDrive 同步客户端 (OneDrive.exe) 或以前 OneDrive for Business 同步客户端 (Groove.exe) 文件，是否同步客户端不会对其进行下载。同步客户端将显示通知，不能同步该文件。
  


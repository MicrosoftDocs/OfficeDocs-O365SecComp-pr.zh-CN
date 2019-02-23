---
title: 适用于 Project Server 的 GDPR
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: 了解如何解决本地 Project Server 中的 GDPR 要求。
ms.openlocfilehash: 67097cdab4fdab31537cf4b6dd27ce17234c2bdc
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219011"
---
# <a name="gdpr-for-project-server"></a><span data-ttu-id="17d3a-103">适用于 Project Server 的 GDPR</span><span class="sxs-lookup"><span data-stu-id="17d3a-103">GDPR for Project Server</span></span>

<span data-ttu-id="17d3a-p101">Project Server 使用自定义脚本在 Project Web App 中导出和修订用户数据。基本过程是：</span><span class="sxs-lookup"><span data-stu-id="17d3a-p101">Project Server uses custom scripts to export and redact user data in Project Web App. The basic process is:</span></span>

1.  <span data-ttu-id="17d3a-106">在服务器场中找到 Project Web App 网站。</span><span class="sxs-lookup"><span data-stu-id="17d3a-106">Find the Project Web App sites in your farm.</span></span>

2.  <span data-ttu-id="17d3a-107">在包含此用户的每个网站中找到项目。</span><span class="sxs-lookup"><span data-stu-id="17d3a-107">Find the projects in each site that contain the user.</span></span>

3.  <span data-ttu-id="17d3a-108">导出并查看想要查看的数据类型。</span><span class="sxs-lookup"><span data-stu-id="17d3a-108">Export and review the types of data that you want to review.</span></span>

4.  <span data-ttu-id="17d3a-109">根据需要修订数据。</span><span class="sxs-lookup"><span data-stu-id="17d3a-109">Redact data as needed.</span></span>

<span data-ttu-id="17d3a-110">下文详细介绍了这些步骤：</span><span class="sxs-lookup"><span data-stu-id="17d3a-110">These steps are covered in detail in the following articles:</span></span>

- [<span data-ttu-id="17d3a-111">从 Project Server 中导出用户数据</span><span class="sxs-lookup"><span data-stu-id="17d3a-111">Export user data from Project Server</span></span>](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [<span data-ttu-id="17d3a-112">从 Project Server 中删除用户数据</span><span class="sxs-lookup"><span data-stu-id="17d3a-112">Delete user data from Project Server</span></span>](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


<span data-ttu-id="17d3a-p102">请注意，Project Server 是在 SharePoint Server 的基础之上构建而成，将事件记录到 SharePoint ULS 日志和使用情况数据库中。有关详细信息，请参阅[适用于 SharePoint Server 的 GDPR](gdpr-for-sharepoint-server.md)。</span><span class="sxs-lookup"><span data-stu-id="17d3a-p102">Note that Project Server is built on top of SharePoint Server and logs events to the SharePoint ULS logs and Usage database. See [GDPR for SharePoint Server](gdpr-for-sharepoint-server.md) for more information.</span></span>

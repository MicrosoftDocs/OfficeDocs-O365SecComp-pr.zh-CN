---
title: 适用于 Project Server 的 GDPR
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: ''
localization_priority: Priority
description: 了解如何解决本地 Project Server 中的 GDPR 要求。
ms.openlocfilehash: aa74f29e522f24f330db6e53c7c81bc5b708bcf0
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272147"
---
# <a name="gdpr-for-project-server"></a>适用于 Project Server 的 GDPR

Project Server 使用自定义脚本在 Project Web App 中导出和修订用户数据。基本过程是：

1.  在服务器场中找到 Project Web App 网站。

2.  在包含此用户的每个网站中找到项目。

3.  导出并查看想要查看的数据类型。

4.  根据需要修订数据。

下文详细介绍了这些步骤：

- [从 Project Server 中导出用户数据](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [从 Project Server 中删除用户数据](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


请注意，Project Server 是在 SharePoint Server 的基础之上构建而成，将事件记录到 SharePoint ULS 日志和使用情况数据库中。有关详细信息，请参阅[适用于 SharePoint Server 的 GDPR](gdpr-for-sharepoint-server.md)。

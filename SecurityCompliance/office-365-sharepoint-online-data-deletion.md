---
title: Office 365 SharePoint Online 数据删除
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: SharePoint Online 中的数据删除的说明。
ms.openlocfilehash: 8a84859ce170a4c3ca713c751aef2b6d5b911c55
ms.sourcegitcommit: 29ba4c36af8e90ddc8d885863ef25bac2cffbe94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2018
ms.locfileid: "27411158"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a>Office 365 中的 SharePoint Online 数据删除

SharePoint Online 作为抽象代码中应用程序数据库存储对象。如果用户将文件上载到 SharePoint Online，该文件为分解和翻译应用程序代码，并跨多个数据库存储在多个表中。在 SharePoint Online 中，客户上载的所有内容分成块的大小，（可能使用多个 AES 256 位键中） 加密和分布在数据中心。有关分块和加密过程的详细信息，请参阅[Microsoft 云中的加密](office-365-encryption-in-the-microsoft-cloud-overview.md)。 

SharePoint Online 中的项目的保留从其原始位置从删除时间 93 天。他们随时了解最新网站回收站的整个时间，除非某人从中删除这些或清空的回收站。在这种情况下，项目转到网站集回收站中，其中他们保持 93 天的其余部分。有关还原已删除的项目的信息，请参阅[还原 SharePoint 网站的回收站中的项目](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
)，并[恢复已删除网站集回收站中的项](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)。回收站保留时间不是 SharePoint Online 中配置的。

删除网站集时，还正在删除网站集和其中的所有内容中的层次结构：
- 文档和文档库
- 列表和列表数据
- 网站配置设置
- 与网站或子网站相关的角色和安全信息
- 子网站的顶级网站、 其内容和用户信息

如果您意外删除网站集，它可以还原的全局或 SharePoint 管理员使用 SharePoint 管理中心。 

当用户从网站集回收站中，清除已删除的邮件保留期和备份期到期时, 或管理员永久删除网站集使用[Remove-spodeletedsite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)时，将发生硬删除。当用户硬删除 （永久删除，或清除） 从 SharePoint Online 内容，所有的已删除的块的加密密钥也将被删除。以前存储已删除的块的磁盘上的块被标记为未使用并且可供重复使用。

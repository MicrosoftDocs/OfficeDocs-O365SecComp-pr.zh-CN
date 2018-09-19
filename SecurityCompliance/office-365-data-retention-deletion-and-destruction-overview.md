---
title: Office 365 中的数据保留、删除和销毁
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
description: 有关数据保留期、 删除和销毁 for Office 365 的 Microsoft 的策略的概述。
ms.openlocfilehash: bb038f8bd8e3f0286ea7d673e5e286bdc4a9677d
ms.sourcegitcommit: 1bccdaacf358505604c9cf422cb1e272aefae19d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "23999143"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Office 365 中的数据保留、删除和销毁

## <a name="introduction"></a>简介
Microsoft 已指定客户数据后要删除的保留多长时间的 Office 365 的数据处理标准的策略。一般情况下，Office 365 中有两种方案中删除客户数据：
- **活动删除**-用户删除数据，或专用于用户的数据将被删除之后的活动的租户管理员删除该用户。
- **被动删除**-租户订阅结束。

Microsoft 的 Office 365 的数据处理标准策略指定数据每个这些方案中的保留多长时间。以下各节描述数据 （基于 Microsoft 的 Office 365 资产分类标准） 和活动和被动删除方案的保留期的类别。

## <a name="active-deletion-retention"></a>活动删除保留

| 数据类别 | 至少保留 | 最保留 |
|---------------------------------------|:-----------------:|:-----------------:|:----------------------------------:|:-------------------------------:|
| 访问控制数据 | 不适用 | 不适用 |
| 客户内容 | 7 天 | 30 天 |
| 最终用户身份信息 | 90 天 | 180 天 |
| 帐户数据 | 1 年 | 3 年 |
| 组织识别信息 | 90 天 | 180 天 |
| 系统元数据 | 请参阅安全日志 | 请参阅安全日志 |
| 安全日志 | 最小值 1 年 | 最大 1 年 |
| Exchange Online 存档日志 | Min 3 年 | 最大 3 年 |

## <a name="passive-deletion-retention"></a>被动删除保留

| 数据类别 | 至少保留 | 最保留 |
|---------------------------------------|:-----------------:|:-----------------:|:----------------------------------:|:-------------------------------:|
| 访问控制数据 | 90 天 （用于内容恢复） | 180 天 （用于内容恢复） |
| 客户内容 | 90 天 （功能有限的帐户） | 180 天 |
| 最终用户身份信息 | 90 天 | 180 天 |
| 帐户数据 | 1 年 | 3 年 |
| 组织识别信息 | 90 天 | 180 天 |
| 系统元数据 | 请参阅安全日志 | 请参阅安全日志 |
| 安全日志 | 最小值 1 年 | 最大 1 年 |
| Exchange Online 存档日志 | Min 3 年 | 最大 3 年 |

## <a name="subscription-rentention"></a>订阅 Rentention

客户内容定义为 Exchange Online 邮箱内容 (电子邮件正文、 日历项和电子邮件附件的内容，如果适用，则业务内容的 Skype)，SharePoint Online 网站内容的文件存储在网站和文件适用于商务或 for Business 的 Skype 上载到 OneDrive。

订阅的所有时间期间术语 at，订阅者可以访问和提取存储在 Office 365 中的客户数据。除免费试用版和 LinkedIn 服务，Microsoft 保留客户数据存储在 Office 365 中的功能有限的帐户 90 天后到期或终止要启用订阅者提取数据的订阅。（对于免费的试用版、 试用版过期时，它将移至宽限期，为您提供 （对于大多数试用版，在大多数国家和地区） 的 30 天内购买 Office 365。如果您决定不购买 Office 365，您可以让您的试用版过期或取消该过程。推出后 30 天宽限期，您的试用版的帐户信息和数据是永久删除。）

90 天保留期结束后，Microsoft 帐户禁用和删除客户数据。不能超过 180 天后到期或 Office 365 订阅终止 Microsoft 将禁用帐户和帐户中删除所有客户数据。后经过的任何数据的最大保留期后，数据呈现商业不可恢复。

Microsoft 还有地址的回收和释放磁盘驱动器和失败或停用服务器的数据处理标准策略。重新使用 Office 365 中的任何磁盘驱动器之前, Microsoft 执行符合 NIST SP 800 88 物理过滤过程。使用现场包含被销毁磁盘的数据中心内执行的物理销毁过程的情况下，不能重复使用的磁盘驱动器都得到释放。由 Microsoft 云基础结构和操作 (MCIO) 执行这些过程。有关详细信息，请参阅审核报告[服务信任预览](https://aka.ms/STP)MCIO。

## <a name="expedited-deletion"></a>加快的删除
订阅的所有时间期间术语 at，订阅者可以联系 Microsoft 支持和快速请求取消订阅设置。在此过程中，所有的用户数据，包括在 SharePoint Online 中，Exchange Online 的可能下的数据保留或存储在非活动邮箱是已删除的三天后管理员输入由 Microsoft 提供的锁定代码。加快取消设置的详细信息，请参阅[取消 Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a)。

## <a name="related-links"></a>相关的链接
- [Exchange Online 数据删除](office-365-exchange-online-data-deletion.md)
- [SharePoint Online 数据删除](office-365-sharepoint-online-data-deletion.md)
- [Skype for Business 数据删除](office-365-skype-data-deletion.md)
- [Office 365 中的永久性](office-365-data-immutability.md)
- [数据销毁](office-365-data-destruction.md)
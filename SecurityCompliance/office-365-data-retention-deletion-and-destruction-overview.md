---
title: Office 365 中的数据保留、删除和销毁
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 有关 Microsoft 针对 Office 365 的策略的概述, 涉及数据保留、删除和销毁。
ms.openlocfilehash: 6aa272ece723aa83e15581062fd2348c508b04d5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219952"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Office 365 中的数据保留、删除和销毁

Microsoft 具有 Office 365 的数据处理标准策略, 用于指定客户数据在被删除后将保留多长时间。在以下两种情况下, 将删除客户数据:

- **主动删除**-租户具有活动订阅且用户删除了数据, 或者由管理员删除了用户提供的数据。
- **被动删除**-租户订阅结束。

## <a name="data-retention"></a>数据保留

对于每个删除方案, 下表显示了数据类别和分类的最大数据保留期:

| 数据类别 | 数据分类 | 说明 | 示例 | 保留期 |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| 客户数据 | 客户内容| 由管理员和用户直接提供/创建的内容 <br><br> 这包括在使用 Office 365 中的服务时, 创建和存储在 Microsoft 数据中心中的所有文本、声音、视频、图像文件和软件 | 最常用的 Office 365 应用程序的示例, 这些应用程序允许用户创作数据, 包括 Word、Excel、PowerPoint、Outlook 和 OneNote <br><br> 客户内容还包括由客户拥有/提供的机密 (密码、证书、加密密钥、存储密钥) | **主动删除方案:** 最多30天 <br><br> **被动删除方案:** 最多180天 |
| 客户数据 | 最终用户身份信息 (EUII) | 标识或可用于标识 Microsoft 服务用户的数据。EUII 不包含客户内容 | 用户名或显示名称 (域 \ 用户名) <br><br> 用户主体名称 (name @ domain) <br><br>  特定于用户的 IP 地址 | **主动删除方案:** 最多180天 (仅租户管理员操作) <br><br> **被动删除方案:** 最多180天 |
| 个人数据 <br> (客户数据中未包含的数据) | 最终用户匿名标识符 (EUPI) | microsoft 创建的与 microsoft 服务用户关联的标识符。当 EUPI 与其他信息 (如映射表) 结合使用时, 它将标识最终用户 <br><br> EUPI 不包含由客户上传或创建的信息 | 用户 guid、PUIDs 或 sid <br><br> 会话 id | **主动删除方案:** 最多30天 <br><br> **被动删除方案:** 最多180天 |

## <a name="subscription-retention"></a>订阅保留

在有效订阅期间的任何时候, 订阅者都可以访问、提取或删除存储在 Office 365 中的客户数据。如果付费订阅结束或终止, Microsoft 将在90天内将存储在 Office 365 中的客户数据保留天, 以使订阅者能够提取数据。在90天的保留期结束后, Microsoft 将禁用该帐户并删除客户数据。在过期或终止对 Office 365 的订阅后, 不超过180天, Microsoft 将禁用帐户并从帐户中删除所有客户数据。一旦所有数据的最大保留期已过, 数据将以商业方式呈现, 从而无法恢复。

在免费试用的情况下, 在大多数国家和地区, 你的帐户将在30天内移动到宽限期状态。在此宽限期期间, 您可以选择购买 Office 365。如果你决定不购买 Office 365, 可以取消试用或让宽限期过期, 并且你的试用帐户信息和数据将被删除。

## <a name="expedited-deletion"></a>加速删除
在任何订阅的任何时候, 订阅者都可以与 Microsoft 支持人员联系, 并请求加速订阅取消。在此过程中, 在管理员输入 Microsoft 提供的锁定代码后, 将在三天内删除在 SharePoint online 中可能处于保留或存储在非活动邮箱中的 Exchange online 中的所有用户数据。有关快速取消启用的详细信息, 请参阅[Cancel Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a)。

## <a name="related-links"></a>相关链接
- [数据销毁](office-365-data-destruction.md)
- [Office 365 中的永久性](office-365-data-immutability.md)
- [Exchange Online 数据删除](office-365-exchange-online-data-deletion.md)
- [SharePoint Online 数据删除](office-365-sharepoint-online-data-deletion.md)
- [Skype for Business 数据删除](office-365-skype-data-deletion.md)
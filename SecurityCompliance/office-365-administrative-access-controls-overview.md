---
title: Office 365 中的管理访问控制
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '摘要: Office 365 的管理访问控制和数据分类概述。'
ms.openlocfilehash: 90dd00049e7e3a9b9548530c42b1c21534cfd7fd
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262974"
---
# <a name="administrative-access-controls-in-office-365"></a>Office 365 中的管理访问控制 

## <a name="introduction"></a>介绍
microsoft 已在系统和控件中进行了大量投资, 以自动化大多数 Office 365 操作, 同时有意限制 Microsoft 对客户内容的访问。 人类控制服务, 软件运行服务。 这使 Microsoft 能够以扩展方式管理 Office 365, 并管理对客户内容 (如恶意参与者、Microsoft 工程师的 spear 和网络钓鱼等) 的内部威胁的风险。

By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Office 365. microsoft 工程师在有限的时间段中, 可以对客户的内容进行有限、经过审核和安全的访问, 但仅当服务操作必要时, 并且仅当由 Microsoft 高级管理人员批准时 (对于那些授权为客户密码箱功能 (客户)。

Microsoft 提供了在线服务, 包括 Office 365, 使用了多种形式的云传递:

- **公共云**-包括在北美、南美洲、欧洲、亚洲、澳大利亚等托管的 Office 365、Azure 和其他服务的多租户版本。
- **国家/地区云**-包括美国境外的所有 sovereign 和第三方运营云 (上面提到的云除外), 如中国 (由世纪互联运营) 的 office 365 和德国的 office (由 Microsoft 运营, 但在一种模型中, 德国数据受信者、德国电信, 控制并监控 Microsoft 对客户数据和包含客户数据的系统的访问。
- **政府群**-包括适用于美国政府客户的 Office 365 和 Azure 服务。

出于本文的目的, Office 365 服务包括[exchange online](https://docs.microsoft.com/Exchange/exchange-online)、 [exchange online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)、 [SharePoint online](https://docs.microsoft.com/sharepoint/sharepoint-online) (包括[OneDrive for business](https://docs.microsoft.com/OneDrive/onedrive)) 和[Skype for](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)business, 以及其他信息关于一些[Yammer Enterprise](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US) access 控件。 其他 Office 365 服务超出了本文的范围。

## <a name="office-365-access-controls"></a>Office 365 访问控制
出于访问控制目的, Office 365 数据被分类为 "客户数据" 或其他类型的数据。 客户数据是由客户使用 Office 365 服务提供或代表客户提供的所有数据, 例如客户内容 (由 office 365 用户直接创建或上载的内容, 包括电子邮件、SharePoint Online 内容、即时消息存储在 Office 365 中的日历项目、文档和联系人) 和最终用户的可识别信息 (EUII) (用户特有或 linkable 给个人用户但不包含客户内容的数据)。 

其他类型的数据包括帐户数据 (包括管理数据, 即管理员在注册或购买服务时提供的信息) 和付款数据 (这是有关付款仪器的信息, 如信用卡详细信息)。组织可识别信息 (可用于标识租户的数据; 或使用率数据; 不 linkable 单个用户, 也不包含客户内容) 和系统元数据 (包括包含配置设置的服务日志) 和系统元数据 (包括包含配置设置的服务日志)系统状态、Microsoft IP 地址和有关订阅和租户的技术信息)。

Microsoft 已建立了访问控制机制, 以确保没有人对客户数据或访问控制数据 (用于管理对环境中其他类型的数据或函数的访问, 包括对客户内容或 EUII 的访问) 进行未批准的访问权限; 它包括 Microsoft 密码、安全证书和其他与身份验证相关的数据) 或对 Office 365 生产环境的未经批准的物理、逻辑或远程访问。

Microsoft for Office 365 使用的访问控制可分为以下三类:
- 隔离控件
- 人员控制
- 技术控制

组合后, 这些控件有助于防止和检测 Office 365 中的恶意操作。 除了 Microsoft 使用的隔离、人员和技术控件之外, 还有第四个类别的控件: 由客户实施的控件。

Office 365 使您能够以与在本地环境中管理数据的相同方式管理数据。 注册 Office 365 组织的人员将自动成为全局管理员 (管理员)。 全局管理员可以访问管理门户中的所有功能 (例如, admin 中心和远程 PowerShell), 还可以创建或编辑用户、向其他人分配管理员角色、重置用户密码、管理用户许可证、管理域和批准客户密码箱请求, 以及其他操作。 我们建议每个组织至少指定两个管理员帐户, 并且根据组织的规模, 您可能需要指定多个服务的不同管理员。 有关分配管理员角色和权限的信息, 请参阅[在 office 365 中分配管理员角色](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504)和[关于 Office 365 管理员角色](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D)。


## <a name="related-links"></a>相关链接

- [隔离控件](office-365-isolation-controls.md)
- [人员控制](office-365-personnel-controls.md)
- [技术控制](office-365-technology-controls.md)
- [监视和审核访问控制](office-365-monitoring-and-auditing-access-controls.md)
- [Yammer Enterprise访问控制](office-365-yammer-enterprise-access-controls.md)
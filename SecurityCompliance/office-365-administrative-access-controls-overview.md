---
title: Office 365 中的管理访问控制
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： Office 365 管理的访问控制和数据分类的概述。
ms.openlocfilehash: afa15d37aa8542985c59dbd9e3d82368421530e8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525411"
---
# <a name="administrative-access-controls-in-office-365"></a>Office 365 中的管理访问控制 

## <a name="introduction"></a>简介
Microsoft 投资主要和相应系统和自动化 Office 365 的大多数操作，同时有意限制对客户内容的 Microsoft 的访问控制。人类管理该服务，而且软件运行该服务。这使 Microsoft Office 365 管理规模情况下，以及管理内部威胁客户内容恶意参与者，例如 Microsoft 工程师等矛网络钓鱼的风险。

默认情况下，Microsoft 工程师 Office 365 中具有零个位置管理权限和零位置访问客户内容。Microsoft 工程师可以具有有限，经过审核，和对的安全访问客户的内容的有限的时间，但仅在所必需的服务操作仅在批准的 Microsoft 高级管理 （和客户的成员许可客户密码箱功能，客户）。

Microsoft 提供的在线服务，包括 Office 365 中，使用多个窗体的云传递：

- **公有云**-包括多租户版本的 Office 365 和 Azure 承载在北美、 南美洲、 欧洲、 亚洲、 澳大利亚等其他服务。
- **国家/地区 Cloud** -例如中国 （这由 21Vianet），Office 365 和 Office 365 德国包括 （除上述），美国之外的所有 sovereign 和第三方客户群 (这由 Microsoft 操作但在模型下在其中德语数据受信任项，德国 Telekom 控制和监视 Microsoft 的客户数据和包含客户数据的系统访问）。
- **政府 Cloud** -包含可供美国政府客户的 Office 365 和 Azure 服务。

出于本文，Office 365 服务包括[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)、 [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)、 [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) （包括[OneDrive for Business](https://docs.microsoft.com/OneDrive/onedrive)） 和[for Business 的 Skype](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)，与其他信息有关某些[Yammer Enterprise](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US)访问控制。其他 Office 365 服务是超出本文的范围。

## <a name="office-365-access-controls"></a>Office 365 的访问控制
为了控制访问，Office 365 数据属于客户数据或其他类型的数据。客户数据是由或代表通过 Office 365 服务，例如客户内容 （内容直接创建或上载的 Office 365 用户电子邮件，SharePoint Online 内容，包括即时消息客户使用的客户提供的所有数据日历项、 文档和存储在 Office 365 中的联系人） 和最终用户身份信息 (EUII) （这是唯一的用户或的是可链接到单个用户，但不包括客户内容数据）。 

其他类型的数据包括帐户数据 （包括管理数据，这是他们注册或购买服务并付款数据，这是付款方式，如 credit 信息卡片详细信息时，由管理员提供的信息）组织身份信息 (用于标识租户; 的数据或使用率数据; 它不是可链接到单个用户，不包括客户内容)，和系统元数据 （包括包含配置设置的服务日志系统状态、 Microsoft IP 地址和订阅和租户的技术信息）。

Microsoft 建立访问控制机制，以确保没有人可以对客户数据或访问控制数据的未批准的访问 (用于管理访问其他类型的数据或函数在环境中，包括访问客户内容或 EUII; 它包括 Microsoft 密码、 安全证书和身份验证相关的其他数据） 或未批准物理、 逻辑，或远程访问 Office 365 生产环境。

由 Microsoft 用于运行 Office 365 的访问控制可以分为三类：
- 隔离控件
- 人员控件
- 技术控件

结合使用时，这些控件有助于防止并检测 Office 365 中的恶意操作。除了隔离、 人员和 Microsoft 所使用的技术控件中，没有控件的第四个类别： 那些由客户实现。

Office 365 允许您管理您何中相同的方式数据管理内部部署环境中的数据。用户注册组织 Office 365 自动成为全局管理员 （管理员）。全局管理员 （例如，管理中心和远程 PowerShell） 的管理门户中有权访问所有功能和可以创建或编辑用户、 分配给其他人的管理角色、 重置用户密码、 管理用户许可证、 管理域，和批准客户密码箱请求，其他一些内容。我们建议每个组织指定至少两个管理帐户，并根据您的组织的大小，您可能想要指定多个管理员提供不同的功能。有关分配管理角色和权限的信息，请参阅[Office 365 中的管理角色分配](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504)和[有关 Office 365 管理员角色](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D)。


## <a name="related-links"></a>相关的链接

- [隔离控件](office-365-isolation-controls.md)
- [人员控件](office-365-personnel-controls.md)
- [技术控件](office-365-technology-controls.md)
- [监视和审核访问控制](office-365-monitoring-and-auditing-access-controls.md)
- [Yammer Enterprise访问控制](office-365-yammer-enterprise-access-controls.md)
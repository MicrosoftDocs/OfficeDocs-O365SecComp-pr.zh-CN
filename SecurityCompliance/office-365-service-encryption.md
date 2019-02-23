---
title: Office 365 服务加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '摘要: 了解 Microsoft Office 365 中的数据恢复能力。'
ms.openlocfilehash: 4e9dd52adbeada92d14db369b386ff1ca7e42fc5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220342"
---
# <a name="office-365-service-encryption"></a>Office 365 服务加密

除了使用卷级加密之外, Exchange Online、Skype for business、SharePoint online 和 OneDrive for business 还使用服务加密来加密客户数据。服务加密允许两个密钥管理选项:
- Microsoft 管理所有加密密钥。(此选项目前在 SharePoint Online、OneDrive for business 和 Skype for business 中可用。它当前位于 Exchange Online 的路线图中。
- 客户提供用于服务加密的根键, 并且客户使用 Azure Key Vault 管理这些密钥。Microsoft 管理所有其他密钥。此选项称为 "客户密钥", 目前适用于 Exchange online、SharePoint online 和 OneDrive for business。(以前称为使用 BYOK 的高级加密。请参阅增强针对原始公告的[Office 365 客户的透明度和控制](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/)。

服务加密提供了多项优势。例如, 它:
- 在强加密保护之上提供权限保护和管理功能。
- 包括一个 "客户密钥" 选项, 该选项使多租户服务能够提供每租户密钥管理。
- 提供 Windows 操作系统管理员的分离, 以访问由操作系统存储或处理的客户数据。
- 增强了 Office 365 满足有关加密合规性要求的客户需求的能力。

## <a name="customer-key"></a>客户密钥
使用客户密钥, 您可以使用本地 HSM 或 Azure Key Vault 生成自己的加密密钥。无论密钥的生成方式如何, 客户都可以使用 Azure key Vault 控制和管理 Office 365 使用的加密密钥。密钥存储在 Azure Key Vault 中后, 可以将其分配给诸如 Exchange online 和 SharePoint online 之类的工作负荷, 并可用作用于对邮箱数据和文件进行加密的密钥链的根。使用客户密钥的另一个好处是, 控制 Microsoft 处理客户数据的能力。此功能存在, 以便希望从 Office 365 中删除数据的客户 (例如, 当客户终止使用 Microsoft 的服务或删除存储在云中的数据部分时) 可以这样做, 并将客户密钥用作技术控制, 以确保没有任何人(包括 Microsoft) 可以访问或处理数据。这是对客户密码箱功能的补充 (和补充), 可用于控制 Microsoft 人员对客户数据的访问。

若要了解如何设置适用于 Exchange Online、Skype for business、SharePoint online 和 OneDrive for business 的 office 365 客户密钥, 请参阅[使用客户密钥在 Office 365 中控制您的数据](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697)。有关详细信息, 请参阅[适用于 Office 365 FAQ 的客户密钥](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6), 并[管理和控制你的数据, 以使用客户密钥帮助满足合规性需求](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580)。

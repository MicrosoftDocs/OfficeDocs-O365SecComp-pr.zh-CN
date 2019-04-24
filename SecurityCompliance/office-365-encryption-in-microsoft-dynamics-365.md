---
title: Microsoft Dynamics 365 中的 Office 365 加密
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
description: '摘要: 了解 Microsoft Dynamics 365 中的加密。'
ms.openlocfilehash: 7c2a352dd712b0db9d2ad623745f854b863dd2e0
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265964"
---
# <a name="office-365-encryption-in-microsoft-dynamics-365"></a>Microsoft Dynamics 365 中的 Office 365 加密

microsoft 使用加密技术保护动态365中的客户数据, 而不是 microsoft 数据库中的静态, 同时在用户设备和我们的数据中心之间传输。 在客户和 Microsoft 数据中心之间建立的连接将进行加密, 并使用工业标准 TLS 来保护所有公用终结点。 TLS 可有效建立安全性增强的浏览器到服务器连接, 以帮助确保桌面和数据中心之间的数据机密性和完整性。 在激活数据加密之后, 将无法关闭该功能。 有关详细信息, 请参阅[字段级数据加密](https://msdn.microsoft.com/en-us/library/dn481562.aspx)。

Dynamics 365 对包含敏感信息 (如用户名和电子邮件密码) 的一组默认实体属性使用标准的 Microsoft SQL Server cell 级加密。 此功能可帮助组织满足与 FIPS 140-2 相关的合规性要求。 在利用[Microsoft Dynamics CRM 电子邮件路由器](https://technet.microsoft.com/en-us/library/hh699800.aspx)的方案中, 字段级数据加密尤为重要, 后者必须存储用户名和密码, 才能在 Dynamics 365 实例和电子邮件服务之间实现集成。 

Dynamics 365 的所有实例都使用[Microsoft SQL Server 透明数据加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017)(TDE), 在写入磁盘 (静态) 时执行数据的实时加密。 TDE 对 SQL Server、azure sql 数据库和 azure sql 数据仓库数据文件进行加密。 默认情况下, Microsoft 存储和管理 Dynamics 365 实例的数据库加密密钥。 (Dynamics 365 for 金融使用的键由 .net Framework 数据保护 API 生成。) 

Dynamics 365 管理中心中的 "管理密钥" 功能使管理员能够自行管理与 Dynamics 365 实例关联的数据库加密密钥。 (自托管数据库加密密钥仅适用于 Microsoft Dynamics 365 的2017年1月版更新, 可能不适用于更高版本。 有关详细信息, 请参阅[管理 Dynamics 365 (online) 实例的加密密钥](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)。密钥管理功能支持 PFX 和 BYOK 加密密钥文件, 如存储在 HSM 中的密钥。 (有关在 Internet 上生成和传输受 hsm 保护的密钥的详细信息, 请参阅[如何为 Azure key Vault 生成和传输受 hsm 保护的](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys)密钥。) 

若要使用 "上载加密密钥" 选项, 您需要公钥和私钥加密密钥。

密钥管理功能通过使用 Azure key Vault 安全存储加密密钥来降低加密密钥管理的复杂性。 Azure Key Vault 可帮助保护云应用程序和服务使用的加密密钥和机密。 密钥管理功能不要求您拥有 Azure key Vault 订阅, 并且在大多数情况下, 无需访问保管库中用于 Dynamics 365 的加密密钥。

---
title: Microsoft Dynamics 365 中的 office 365 加密
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 5/31/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 了解 Microsoft Dynamics 365 中的加密。
ms.openlocfilehash: 181db1724f140c86fb1ac1dbf4a4bfb7063d25a3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524804"
---
# <a name="office-365-encryption-in-microsoft-dynamics-365"></a>Microsoft Dynamics 365 中的 office 365 加密

Microsoft 使用加密技术来保护同时 rest Microsoft 数据库中并在用户设备和我们数据中心之间传输时 Dynamics 365 中的客户数据。客户和 Microsoft 数据中心之间建立的连接进行加密，并使用行业标准 TLS 保护所有公用终结点。TLS 有效地建立安全性增强的浏览器到服务器连接以帮助确保数据机密性和桌面和数据中心之间的完整性。数据加密激活后，就无法关闭。有关详细信息，请参阅[字段级数据加密](https://msdn.microsoft.com/en-us/library/dn481562.aspx)。

Dynamics 365 使用的默认实体属性包含敏感信息，如用户名和电子邮件密码的一组标准 Microsoft SQL Server 单元格级别的加密。此功能可帮助组织满足合规性要求 FIPS 140 2 相关联。利用[Microsoft Dynamics CRM 电子邮件传送器](https://technet.microsoft.com/en-us/library/hh699800.aspx)，其中必须存储用户的用户名和密码以启用 Dynamics 365 实例的电子邮件服务之间的集成的方案中尤其重要字段级数据加密。 

Dynamics 365 的所有实例都使用[Microsoft SQL Server 透明数据加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017)(TDE) 执行实时加密的数据写入磁盘 （在 rest) 时。TDE 对 SQL Server、 Azure SQL 数据库和 Azure SQL 数据仓库的数据文件进行加密。默认情况下，Microsoft 存储和管理您实例 Dynamics 365 数据库加密密钥。（的键的财务 Dynamics 365 使用的是由生成.NET Framework 数据保护 API。） 

Dynamics 365 管理中心中的管理键功能使管理员能够自我管理与 Dynamics 365 的实例关联的数据库加密密钥。（自我管理的数据库加密密钥才 Microsoft Dynamics 365 2017 年 1 月更新中可用，并且不能设置为可供更高版本。有关详细信息，请参阅[管理 Dynamics 365 （联机） 实例的加密密钥](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)。）密钥管理功能支持 PFX 和 BYOK 加密密钥文件，如存储在 HSM。（有关生成和通过 Internet 转移 HSM 保护密钥的详细信息，请参阅[如何生成和传输 Azure 键电子仓库 HSM 保护密钥](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys)）。 

若要使用上载加密密钥选项，您需要两个公用和专用的加密密钥。

密钥管理功能所需使用 Azure 键仓库安全地存储加密密钥的加密密钥管理不足的复杂性。Azure 键仓库帮助保护加密密钥和云应用程序和服务使用的机密。密钥管理功能不需要拥有 Azure 键存储库订阅和大多数情况下没有不需要访问用于 Dynamics 365 存储库中的加密密钥。

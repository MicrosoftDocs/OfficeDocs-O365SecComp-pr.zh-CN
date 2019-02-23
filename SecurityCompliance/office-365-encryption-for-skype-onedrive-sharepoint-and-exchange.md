---
title: Skype、OneDrive、SharePoint 和 Exchange 的 Office 365 加密
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
description: '摘要: 对 Skype、OneDrive、SharePoint 和 Exchange Online 加密的说明。'
ms.openlocfilehash: b08b9d00dc83ab59cf2f5b979fb9b6079990a8e8
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216932"
---
# <a name="office-365-encryption-for-skype-for-business-onedrive-for-business-sharepoint-online-and-exchange-online"></a>适用于 Skype for business、OneDrive for business、SharePoint online 和 Exchange online 的 Office 365 加密

Office 365 是一个高度安全的环境, 可在多个层中提供广泛保护: 物理数据中心安全性、网络安全性、访问安全性、应用程序安全性和数据安全性。

## <a name="skype-for-business"></a>Skype for Business
Skype for business 客户数据可能以会议参与者上载的文件或演示文稿形式存储在 rest 上。Web 会议服务器使用具有256位密钥的 AES 对客户数据进行加密。加密的客户数据存储在文件共享上。每个客户数据都使用不同的随机生成的256位密钥进行加密。当在会议中共享一段客户数据时, Web 会议服务器会指示会议客户端通过 HTTPS 下载加密的客户数据。它将对应的密钥发送给客户端, 以便可以对客户数据进行解密。在允许客户端访问会议客户数据之前, Web 会议服务器还会对会议客户端进行身份验证。加入 Web 会议时, 每个会议客户端将首先建立 SIP 对话框, 通过 TLS 在前端服务器中运行会议焦点组件。会议焦点将由 Web 会议服务器生成的身份验证 cookie 传递给会议客户端。然后, 会议客户端将连接到 Web 会议服务器, 以呈现由服务器进行身份验证的身份验证 cookie。

## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 和 OneDrive for Business
SharePoint Online 中的所有客户文件均受唯一的、每个文件的密钥保护, 这些密钥对于单个租户始终是独占的。这些密钥是由 SharePoint Online 服务创建和管理的, 或者是在使用客户密钥时, 由客户创建和管理。上载文件时, SharePoint Online 将在上载请求的上下文中执行加密, 然后再将其发送到 Azure 存储。下载文件时, SharePoint Online 将根据唯一的文档标识符从 Azure 存储中检索加密的客户数据, 并在将客户数据发送给用户之前对其进行解密。Azure 存储不能解密, 甚至无法识别或理解客户数据。所有加密和解密在强制实施租户隔离的系统中发生, 即 Azure Active Directory 和 SharePoint Online。

Office 365 中的多个工作负荷在 sharepoint online 中存储数据, 包括 Microsoft 团队, 其中存储了 sharepoint online 中的所有文件和 OneDrive for business, 后者使用 sharepoint online 存储它。存储在 SharePoint Online 中的所有客户数据都经过加密 (包含一个或多个 AES 256 位密钥), 并分布在整个数据中心中, 如下所示。(此加密过程的每个步骤都是验证了 FIPS 140-2 级别2。有关 fips 140-2 合规性的详细信息, 请参阅[FIPS 140-2 合规性](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105))。
- 根据文件大小, 将每个文件拆分为一个或多个块。每个区块都使用其自己唯一的 AES 256 位密钥进行加密。
- 更新文件时, 将以相同的方式处理更新: 将更改拆分为一个或多个块, 并使用单独的唯一键对每个区块进行加密。
- 这些区块–文件、文件碎片和更新增量–存储为 Azure 存储中随机分布在多个 azure 存储帐户中的 blob。 
- 这些客户数据块的加密密钥集本身是加密的。
   - 用于加密 blob 的密钥存储在 SharePoint Online 内容数据库中。
   - 内容数据库受数据库访问控制和静态加密的保护。使用[Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview)中的[透明数据加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-tde)(TDE) 执行加密。(Azure SQL Database 是 Microsoft Azure 中的常规用途关系数据库服务, 它支持关系数据、JSON、空间和 XML 等结构。这些机密是 SharePoint Online 的服务级别, 而不是租户级别。这些机密 (有时称为主密钥) 存储在单独的安全存储库中, 称为 "密钥存储区"。TDE 为活动数据库和数据库备份和事务日志提供了 rest 的安全性。 
   - 当客户提供可选密钥时, 客户密钥存储在 Azure key Vault 中, 服务使用密钥来加密租户密钥, 该密钥用于加密网站密钥, 然后使用它来加密文件级密钥。实质上, 当客户提供密钥时, 会引入新的密钥层次结构。
- 用于重新装配文件的映射与加密密钥一起存储在内容数据库中, 并与解密时所需的主密钥分开。
- 每个 Azure 存储帐户都有其自己的每个访问类型的唯一凭据 (读取、写入、枚举和删除)。每组凭据都保留在安全密钥存储中, 并定期刷新。如上所述, 有三种不同类型的存储, 每种类型都有不同的功能:
- 在 Azure 存储中, 客户数据存储为加密的 blob。每个客户数据块的键都会被加密并单独存储在内容数据库中。客户数据本身不包含有关如何对其进行解密的任何线索。
- 内容数据库是 SQL Server 数据库。它包含查找和重新组装存储在 Azure 存储中的客户数据 blob 所需的映射, 以及加密这些 blob 所需的密钥。但是, 键集本身是加密的 (如上所述), 并保存在单独的密钥存储中。
- 密钥存储区在物理上独立于内容数据库和 Azure 存储。它将每个 Azure 存储容器的凭据和主密钥保存到内容数据库中保留的加密密钥集。

这三个存储组件 (Azure blob 存储、内容数据库和密钥存储) 中的每一个都在物理上是独立的。任何一个组件中保存的信息本身不可用。如果没有访问所有三项, 则无法将密钥检索到块中, 对密钥进行解密以使其可用, 将密钥与相应的区块相关联, 对每个区块进行解密, 或从其构成块中重新构造文档。

保护数据中心中的计算机上的物理磁盘卷的 BitLocker 证书存储在受服务器场密钥保护的安全存储库 (SharePoint Online 密钥存储) 中。

保护每个 blob 密钥的 TDE 项存储在两个位置:
- 用于承载 BitLocker 证书并受服务器场密钥保护的安全存储库;并
- 在由 Azure SQL 数据库管理的安全存储库中。

用于访问 Azure 存储容器的凭据也保留在 SharePoint online 密钥存储中, 并根据需要委派给每个 sharepoint online 场。这些凭据是 Azure 存储 SAS 签名, 使用单独的凭据读取或写入数据, 并应用策略, 以便它们每60天自动过期。使用不同的凭据来读取或写入数据 (而不是同时读取或写入), 并且不会向 SharePoint Online 场授予枚举权限。

> 注意对于 Office 365 美国政府版客户, 数据 blob 存储在 Azure 美国政府存储中。此外, office 365 美国政府版中对 SharePoint Online 密钥的访问权限仅限于专门筛选过的 office 365 员工。Azure 美国政府运营人员无法访问用于加密数据 blob 的 SharePoint Online 密钥存储。

有关 SharePoint Online 和 OneDrive for business 中的数据加密的详细信息, 请参阅[OneDrive for business 和 SharePoint Online 中的数据加密](https://technet.microsoft.com/en-us/library/dn905447.aspx)。

### <a name="list-items-in-sharepoint-online"></a>SharePoint Online 中的列表项
列表项是较小的用户数据块, 可在网站中进行临时 (如用户创建的列表中的行、sharepoint online 博客中的各个帖子或 sharepoint online wiki 页面中的条目) 而创建。列表项存储在内容数据库 (Azure SQL 数据库) 中, 并受 TDE 保护。

## <a name="encryption-of-data-in-transit"></a>中转数据的加密
在 OneDrive for Business 和 SharePoint Online 中，有两种数据进入和退出数据中心的方案。
- **与服务器通信的客户端与**Internet 上的 OneDrive for business 使用 SSL/TLS 连接。所有 SSL 连接都是使用2048位密钥建立的。
- **数据中心之间的数据移动**-在数据中心之间移动数据的主要原因是为了实现灾难恢复。例如, SQL Server 事务日志和 blob 存储增量沿此管道传播。虽然已使用专用网络传输此数据, 但使用最受一流的加密进一步保护。


## <a name="exchange-online"></a>Exchange Online
Exchange Online 对所有邮箱数据使用 BitLocker, 并且 bitlocker 配置在[bitlocker 中对加密](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)进行了描述。服务级别加密对邮箱级别的所有邮箱数据进行加密。 

除了服务加密之外, Office 365 还支持客户密钥, 这是基于服务加密的基础构建的。"客户密钥" 是 Exchange Online 服务加密的 microsoft 托管密钥选项, 也在 microsoft 的路线图中。此加密方法可提供 BitLocker 不提供的增强保护, 因为它提供了服务器管理员的分离和解密数据所需的加密密钥, 并且由于加密直接应用于数据 (在与在逻辑磁盘卷上应用加密的 BitLocker 相比, 从 Exchange 服务器复制的任何客户数据仍保持加密。

exchange online 服务加密的作用域是 exchange online 中存储在 rest 上的客户数据。(Skype for business 存储几乎在用户的 exchange online 邮箱中的所有用户生成的内容, 因此继承了 exchange online 的服务加密功能。)

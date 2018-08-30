---
title: Office 365 加密的 Skype、 OneDrive、 SharePoint 和 Exchange
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
description: 摘要： 加密 Skype、 OneDrive、 SharePoint、 和 Exchange Online 的说明。
ms.openlocfilehash: 5b839b8d290306f2334d3ca3278d0d5dac20a56f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525416"
---
# <a name="office-365-encryption-for-skype-for-business-onedrive-for-business-sharepoint-online-and-exchange-online"></a>Skype for Business、 OneDrive for Business、 SharePoint Online 和 Exchange Online 的 office 365 加密

Office 365 是提供多层中的大量保护高度安全环境： 物理数据中心安全、 网络安全、 访问安全性、 应用程序安全性和数据安全。

## <a name="skype-for-business"></a>Skype for Business
可能会 Skype 业务客户数据存储在文件或演示文稿的上载的会议参与者的窗体中的其余部分。Web 会议服务器对使用 256 位密钥使用 AES 客户数据进行加密。文件共享上存储加密的客户数据。使用不同的随机生成的 256 位密钥加密每段客户数据。当一段客户数据共享在会议中时，Web 会议服务器将指示会议客户端下载通过 HTTPS 加密的客户数据。以便可以解密客户数据，它会向客户端发送对应的键。允许客户端访问会议客户数据之前，Web 会议服务器还进行会议客户端身份验证。时加入 Web 会议，每个会议客户端与会议会议状态中心组件运行在前端服务器通过 TLS 首先建立 SIP 对话。会议焦点会议客户端可以访问 Web 会议服务器生成的身份验证 cookie。会议客户端然后连接到 Web 会议服务器演示由服务器进行身份验证的身份验证 cookie。

## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 和 OneDrive for Business
SharePoint Online 中的所有客户文件都受始终是专用于单租户的唯一的每个文件键。注册表项创建和管理 SharePoint Online 服务，或使用客户参数时，创建和管理的客户。当将文件上载时，加密执行由 SharePoint Online 上载请求的上下文中之前发送到 Azure 存储。下载文件时，SharePoint Online 检索加密的客户 Azure 存储中的数据基于文档的唯一标识符，并将其发送到用户之前的位置解密客户数据。Azure 存储已不能以解密，或者甚至标识或了解客户数据。所有加密和解密都发生强制执行租户隔离，它们是 Azure Active Directory 和 SharePoint Online 的同一个系统中。

Office 365 中的多个工作负荷存储在 SharePoint Online，包括将所有文件都存储在 SharePoint Online 和 OneDrive for Business，使用 SharePoint Online 及其存储的 Microsoft 团队中的数据。存储在 SharePoint Online 中的所有客户数据是 （使用一个或多个 AES 256 位键） 加密和分布数据中心，如下所示。（此加密过程的每一个步骤是的 FIPS 140-2 级别 2 验证。有关 FIPS 140 2 合规性的其他信息，请参阅[FIPS 140-2 合规性](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105))。）
- 每个文件拆分为一个或多个块，根据文件大小。每个块是使用其自己的唯一 AES 256 位键进行加密。
- 更新文件后，相同的方式处理更新： 更改拆分成一个或多个块的大小，并使用单独的唯一密钥加密每个块。
- 为 Azure 存储随机分布在多个 Azure 存储帐户的 blob 存储 – 文件、 文件和更新增量部分 – 这些数据块。 
- 本身进行加密的加密密钥的客户数据的这些数据块集。
   - SharePoint Online 内容数据库中存储用于加密 blob 的键。
   - 数据库访问控制和静态加密受内容数据库。[Azure SQL 数据库](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview)中使用[透明数据加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-tde)(TDE) 来执行加密。（azure SQL 数据库是通用的关系数据库服务中支持如关系数据、 JSON，空间和 XML 结构的 Microsoft Azure。）在 SharePoint Online，不能在租户级别的服务级别都是这些机密。这些机密 （有时称为主密钥） 存储在称为项存储区的单独安全存储库中。TDE 提供安全的活动数据库并将数据库备份和事务日志的其余部分。 
   - 当客户提供可选的密钥时，客户参数存储在 Azure 键电子仓库，和服务使用密钥加密租户密钥，用于加密网站密钥，然后用来加密文件级别参数。实际上，引入了新的密钥层次结构时客户提供键。
- 单独来自主密钥解密它们所需的加密键以及内容数据库中存储用于重新组合文件的映射。
- 每个 Azure 存储帐户具有自己唯一的凭据，每个访问类型 （读取、 写入、 枚举和删除）。每个组的凭据保存在安全密钥存储，定期刷新。如上所述，有三种不同类型的存储，每个都与一个不同的函数：
- 作为在 Azure 存储中的加密 blob 存储客户数据。客户数据的每个块的关键是加密的单独存储在内容数据库。客户数据本身包含来解密如何对不知道。
- 内容数据库是 SQL Server 数据库。它包含所需找到并重组客户数据 blob 保留在 Azure 存储，以及加密这些 blob 所需要的项中的映射。但是，键集本身就是加密 （如上所述） 和保存在单独的项存储区。
- 从内容数据库和 Azure 存储不同的物理密钥存储区。到的内容数据库中保留的加密密钥集，它包含每个 Azure 存储容器和主密钥的凭据。

每个 – Azure blob 存储和内容数据库，键存储 – 这三个存储组件是不同的物理。保留的任意一种组件的信息将自己上不可用。无法访问所有这三个，而是无法检索到块的键，解密要使其可用、 将键与它们对应的块关联、 解密每个块，或重新构造其构成块中的一个文档的键。

保护数据中心中的计算机上的物理磁盘卷的 BitLocker 证书存储中的安全存储库 （SharePoint Online 的机密存储） 是受保护的服务器场密钥。

保护的每个 blob 键的 TDE 密钥存储在两个位置：
- 安全存储库，装有 BitLocker 证书，并且受服务器场密钥;和
- 在托管的 Azure SQL 数据库的安全存储库。

在 SharePoint Online 中机密存储和委派给每个 SharePoint Online 的服务器场，根据需要还保留用于访问的 Azure 存储容器的凭据。这些凭据是 Azure 存储 SAS 签名，与用于读取或写入数据的单独凭据和应用，以便它们自动-每 60 天过期策略。使用不同凭据读取或写入数据 （不能同时） 和 SharePoint Online 的服务器场不授予权限枚举。

> 注意有关 Office 365 美国政府客户，数据 blob 存储在 Azure 美国政府存储中。此外，访问 Office 365 美国政府部门中的 SharePoint Online 密钥仅限于已专门屏蔽的 Office 365 员工。Azure 美国政府操作人员没有访问的 SharePoint Online 的关键存储用于加密数据的 blob。

有关 SharePoint Online 和 OneDrive for Business 中的数据加密的详细信息，请参阅[OneDrive for Business 和 SharePoint Online 中的数据加密](https://technet.microsoft.com/en-us/library/dn905447.aspx)。

### <a name="list-items-in-sharepoint-online"></a>SharePoint Online 中的列表项
列表项是客户的临时或创建的数据可以更动态 live 网站，如用户创建的列表中的行、 SharePoint Online 博客 （英文） 或 SharePoint Online wiki 页面中的条目中的单个文章中的小数据块。列表项是存储在内容数据库 （Azure SQL 数据库） 和术 シ モ メ TDE。

## <a name="encryption-of-data-in-transit"></a>中转数据的加密
在 OneDrive for Business 和 SharePoint Online 中，有两种数据进入和退出数据中心的方案。
- **与服务器的客户端通信**-到 OneDrive for Business 通过 Internet 的通信使用 SSL/TLS 连接。使用 2048年位密钥建立所有 SSL 连接。
- **数据中心之间移动数据**的数据中心之间移动数据的主要原因是 geo 复制启用灾难恢复。例如，SQL Server 事务日志和 blob 存储增量沿移动此管道。时已使用专用网络传输此数据，进一步保护与同类的加密。


## <a name="exchange-online"></a>Exchange Online
Exchange Online 的邮箱的所有数据，使用 BitLocker 和 BitLocker 配置所述[BitLocker 加密](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)。服务级别的加密对邮箱级别的所有邮箱数据进行都加密。 

除了服务加密，Office 365 支持客户参数，构建于服务加密。客户参数是 Microsoft 托管密钥选项也位于 Microsoft 的路线图的 Exchange Online 服务加密。此方法的加密提供增强的保护不提供通过 BitLocker，因为它提供了服务器管理员和解密的数据所需的加密密钥的分离，而且加密直接于 （中的数据与适用在逻辑磁盘批量加密的 BitLocker 对比度） 从 Exchange 服务器复制的任何客户数据保持加密。

Exchange Online 服务加密的范围是在 Exchange Online 中的其余部分存储的客户数据。（for Business 的 Skype 存储几乎所有用户都生成的内容中用户的 Exchange Online 邮箱，并因此继承的 Exchange Online 的服务加密功能。）

---
title: Azure 中的 office 365 加密
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
description: 摘要： Azure 中的加密的说明。
ms.openlocfilehash: 5e1d0fc02daa7fe057e14045d1948762612b3674
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525453"
---
# <a name="office-365-encryption-in-azure"></a>Azure 中的 office 365 加密

## <a name="introduction"></a>简介
加密的通信和操作过程，如技术在 Azure 中的安全保护帮助保护数据安全。您还可以灵活地实施其他加密功能和管理加密密钥。无论客户配置 Microsoft 适用加密来保护在 Azure 中的客户数据。Microsoft 还使您能够控制您通过多种加密、 控制和管理加密密钥的高级技术承载在 Azure 中的数据控件和审核对数据的访问。此外，Azure 存储提供了一组全面的安全功能一起使开发人员可以构建安全的应用程序。

Azure 提供了许多用来保护数据从一个位置移动到另一个机制。Microsoft 使用 TLS 保护时它在旅行云服务和客户之间的数据。Microsoft 的数据中心协商 TLS 连接与连接到 Azure 服务的客户端系统。完全向前保密 (PFS) 的唯一键保护客户的客户端系统和 Microsoft 云服务之间的连接。连接还使用 RSA 基于 2048 位密钥长度。此组合使其变得比较困难的人的传输中截距和访问数据。

可以通过使用[客户端加密](https://docs.microsoft.com/azure/storage/storage-client-side-encryption)、 HTTPS 或 SMB 3.0 应用程序和 Azure 之间传输过程中保护数据。您可以自己虚拟机 (Vm) 与您的用户之间启用通信的加密。使用[Azure 虚拟网络](https://azure.microsoft.com/services/virtual-network/)，可以使用行业标准 IPsec 协议以及 Azure 虚拟机上虚拟网络产权您公司的 VPN 网关之间的通信进行加密。

对于静态数据，Azure 提供许多加密选项，如支持 AES-256 个，所以您可以灵活选择最能满足您需求的数据存储方案。数据可以自动加密时写入到 Azure 存储使用[存储服务加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)，并可以使用[Azure 磁盘加密](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)进行加密操作系统和使用的虚拟机的数据磁盘。此外，可以使用[共享访问签名](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1)授予委派的访问 Azure 存储中的数据对象。Azure 还提供了使用[Azure SQL 数据库和数据仓库透明数据加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)的静态数据的加密。

关于 Azure 中的加密的详细信息，请参阅[Azure 加密概述](https://docs.microsoft.com/azure/security/security-azure-encryption-overview)和[Azure 数据加密在 Rest](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest)。

## <a name="azure-disk-encryption"></a>Azure 磁盘加密
[Azure 磁盘加密](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)，您可以加密您的 Windows 和 Linux 基础结构作为服务 (IaaS) VM 磁盘。Azure 磁盘加密利用的 BitLocker 功能的 Windows 和 Linux 操作系统和数据磁盘提供音量级别加密的 DM Crypt 功能。此外可以确保 VM 磁盘上的所有数据进行都加密在您的 Azure 存储中的其余部分。与 Azure 键存储库，以帮助您控制、 管理和审核加密密钥和机密信息的使用集成 azure 磁盘加密。

有关详细信息，请参阅[Azure 磁盘加密 for Windows 和 Linux IaaS 虚拟机](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)。

## <a name="azure-storage-service-encryption"></a>Azure 存储服务加密
使用[Azure 存储服务加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)，Azure 存储自动加密之前持久化数据之前检索的数据存储，将解密它。加密、 解密和密钥管理过程是完全透明的用户。Azure 存储服务加密可用于[Azure Blob 存储](https://azure.microsoft.com/services/storage/blobs/)和[Azure 文件](https://azure.microsoft.com/services/storage/files/)。您还可以使用 Azure 存储服务加密，使用 Microsoft 托管加密密钥，或者您可以使用您自己的加密密钥。（有关使用您自己的密钥的信息，请参阅[使用客户的存储服务加密托管密钥 Azure 键存储库中](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys)。有关使用 Microsoft 托管的键的信息，请参阅[为静态数据的存储服务加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)。）此外，您可以自动执行使用加密。例如，您可以以编程方式启用或禁用使用[Azure 存储资源提供程序 REST API](https://msdn.microsoft.com/library/azure/mt163683.aspx)、[存储资源提供程序.NET 客户端库](https://msdn.microsoft.com/library/azure/mt131037.aspx)、 [Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)，存储帐户存储服务加密或[Azure CLI](https://docs.microsoft.com/azure/storage/storage-azure-cli)。

某些 Office 365 服务使用 Azure 存储数据。例如，SharePoint Online 和 OneDrive for Business 在 Azure Blob 存储中存储数据和 Microsoft 团队表、 blob 和队列中存储其聊天服务的数据。此外，在服务信任门户的合规性管理器功能存储客户输入的数据存储在加密形式[Azure 宇宙 DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)，作为服务 (PaaS) 全局分布式、 多个模型的数据库的平台。Azure 存储服务加密数据存储在 Azure Blob 存储和在表中，进行加密和 Azure 磁盘加密队列，以及 Windows 和 IaaS 提供批量加密操作系统的虚拟机磁盘和数据磁盘中的数据进行加密。解决方案可确保虚拟机磁盘上的所有数据进行都加密在您的 Azure 存储中的其余部分。使用多个安全技术，包括安全密钥存储系统、 加密的网络和加密 Api 实现[加密在 Azure 宇宙 DB 中的其余部分](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)。

## <a name="azure-key-vault"></a>Azure Key Vault
不加密的最佳做法; 只核心安全密钥管理。它也是必需的云中的数据保护。[Azure 键仓库](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)使您能够加密密钥和小机密像使用硬件安全模块 (Hsm) 中存储的密钥的密码。Azure 键存储库是 Microsoft 的建议的解决方案，用于管理和控制访问由云服务的加密密钥。为服务或使用 Azure Active Directory 帐户的用户，可以分配访问项的权限。Azure 键仓库减少了对组织的需要配置、 修补程序，和维护 Hsm 和密钥管理软件。与 Azure 键电子仓库，Microsoft 永远不会看到您的密钥和应用程序不能直接访问它们。维护控件。您还可以导入或在 Hsm。 生成密钥的订阅包含 Azure 信息保护组织可以配置其 Azure 信息保护租户，使用客户托管密钥[使您自己的密钥](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions)(BYOK)) 和[日志用法](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage)。

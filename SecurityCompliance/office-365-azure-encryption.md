---
title: Azure 中的 Office 365 加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: '摘要: Azure 中的加密说明。'
ms.openlocfilehash: b8980b3979ada9ac02232065a27a7891936aa945
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32265874"
---
# <a name="office-365-encryption-in-azure"></a>Azure 中的 Office 365 加密

## <a name="introduction"></a>介绍

Azure 中的技术保护措施 (如加密通信和操作进程) 有助于确保数据的安全。 您还可以灵活地实施其他加密功能并管理自己的加密密钥。 无论客户配置如何, Microsoft 都应用加密以保护 Azure 中的客户数据。 Microsoft 还使您能够通过一系列高级技术控制托管的数据, 以加密、控制和管理加密密钥、控制和审核对数据的访问。 此外, Azure 存储提供一组全面的安全功能, 使开发人员能够构建安全的应用程序。

Azure 提供了多种机制, 可在数据从一个位置移动到另一个位置时对其进行保护。 当在云服务和客户之间进行传输时, Microsoft 使用 TLS 来保护数据。 Microsoft 的数据中心与连接到 Azure 服务的客户端系统协商 TLS 连接。 "完全向前保密 (PFS)" 通过唯一密钥保护客户的客户端系统和 Microsoft 云服务之间的连接。 连接还使用基于 RSA 的2048位加密密钥长度。 这种组合使得某人难以截获和访问正在传输中的数据。

可以在应用程序和 Azure 之间通过使用[客户端加密](https://docs.microsoft.com/azure/storage/storage-client-side-encryption)、HTTPS 或 SMB 3.0 在传输过程中保护数据。 您可以对您自己的虚拟机 (vm) 和您的用户之间的流量启用加密。 使用[Azure 虚拟网络](https://azure.microsoft.com/services/virtual-network/), 您可以使用行业标准 IPsec 协议来加密公司 VPN 网关和 Azure 之间以及位于虚拟网络上的虚拟机之间的通信。

对于静态数据, Azure 提供多种加密选项, 如支持 AES-256, 让你能够灵活地选择最能满足你的需求的数据存储方案。 在使用[存储服务加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)向 Azure 存储写入数据时, 可以自动对数据进行加密, 并且可以使用[Azure 磁盘加密](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)对 vm 使用的操作系统和数据磁盘进行加密。 此外, 还可以使用[共享访问签名](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1)授予对 Azure 存储中的数据对象的委派访问权限。 azure 还使用[azure SQL 数据库和数据仓库的透明数据加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql), 为静态数据提供加密。

有关 azure 中的加密的详细信息, 请参阅[azure 加密概述](https://docs.microsoft.com/azure/security/security-azure-encryption-overview)和[azure 数据加密 (静态](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest))。

## <a name="azure-disk-encryption"></a>Azure 磁盘加密

[Azure 磁盘加密](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)使您能够将 Windows 和 Linux 基础结构加密为服务 (IaaS) VM 磁盘。 Azure 磁盘加密利用 Windows 的 BitLocker 功能和 Linux 的 DM Crypt 功能为操作系统和数据磁盘提供卷级加密。 此外, 它还可确保 VM 磁盘上的所有数据在 Azure 存储中的静态加密。 azure 磁盘加密与 azure 密钥存储库集成, 可帮助您控制、管理和审核加密密钥和密码的使用。

有关详细信息, 请参阅[适用于 Windows 和 Linux IaaS 虚拟机的 Azure 磁盘加密](https://docs.microsoft.com/azure/security/azure-security-disk-encryption)。

## <a name="azure-storage-service-encryption"></a>Azure 存储服务加密

通过[azure 存储服务加密](https://docs.microsoft.com/azure/storage/storage-service-encryption), Azure 存储会在检索数据之前将数据自动加密, 并将其保存到存储区并对数据进行解密。 加密、解密和密钥管理过程对用户完全透明。 azure 存储服务加密可用于[azure Blob 存储](https://azure.microsoft.com/services/storage/blobs/)和[azure 文件](https://azure.microsoft.com/services/storage/files/)。 您还可以使用 Microsoft 托管的加密密钥和 Azure 存储服务加密, 也可以使用自己的加密密钥。 (有关使用您自己的密钥的信息, 请参阅[使用 Azure Key Vault 中的客户托管密钥存储服务加密](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys)。 有关使用 Microsoft 管理的密钥的信息, 请参阅[存储服务对静态数据的加密](https://docs.microsoft.com/azure/storage/storage-service-encryption)。此外, 还可以自动使用加密。 例如, 可以使用[Azure 存储资源提供程序 REST API](https://msdn.microsoft.com/library/azure/mt163683.aspx)以编程方式在存储帐户上启用或禁用存储服务加密、用于 .net、 [Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)的[存储资源提供程序客户端库](https://msdn.microsoft.com/library/azure/mt131037.aspx)或[Azure CLI](https://docs.microsoft.com/azure/storage/storage-azure-cli)。

一些 Office 365 服务使用 Azure 存储数据。 例如, SharePoint Online 和 OneDrive for business store data in Azure Blob 存储, Microsoft 团队在表、blob 和队列中存储其聊天服务的数据。 此外, 服务信任门户的合规性管理器功能会存储客户输入的数据, 这些数据以加密形式存储在[Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)中, 即作为服务 (PaaS) 的平台, 即全局分布式的多模型数据库。 azure 存储服务加密对存储在 Azure Blob 存储和表中的数据进行加密, azure 磁盘加密会对队列中的数据以及 Windows 和 IaaS 虚拟机磁盘进行加密, 以提供操作系统和数据磁盘的卷加密。 此解决方案可确保虚拟机磁盘上的所有数据在 Azure 存储中的静态位置进行加密。 [Azure Cosmos DB 中的静态加密](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)是通过使用多种安全技术实现的, 包括安全密钥存储系统、加密的网络和加密 api。

## <a name="azure-key-vault"></a>Azure Key Vault

安全密钥管理不仅仅是加密最佳做法的核心;在云中保护数据也是必要的。 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)使你能够加密密钥和小型密码, 例如使用存储在硬件安全模块 (hsm) 中密钥的密码。 Azure Key Vault 是 Microsoft 推荐的管理和控制对云服务使用的加密密钥的访问的解决方案。 可以将访问密钥的权限分配给服务或具有 Azure Active Directory 帐户的用户。 Azure Key Vault 缓解了需要配置、修补和维护 hsm 和密钥管理软件的组织。 使用 Azure Key Vault, Microsoft 永远无法看到你的密钥和应用程序无法直接访问它们;您保持控制。 您还可以在 hsm 中导入或生成密钥。 具有包含 Azure 信息保护的订阅的组织可以将其 azure 信息保护租户配置为使用客户管理的密钥, 从而[引入您自己的密钥](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions)(BYOK), 并[记录其使用情况](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage)。

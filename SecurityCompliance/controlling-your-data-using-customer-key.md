---
title: 使用客户密钥控制 Office 365 中的数据
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
description: 了解如何为 Exchange Online、Skype for business、SharePoint Online 和 OneDrive for business 设置适用于 Office 365 的客户密钥。使用 "客户密钥", 可以控制组织的加密密钥, 然后配置 Office 365 以使用它们在 Microsoft 数据中心中对静态数据进行加密。
ms.openlocfilehash: a14a213951bc87e4106e150c88c6b1461a5e685e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218752"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>使用客户密钥控制 Office 365 中的数据

使用 "客户密钥", 可以控制组织的加密密钥, 然后配置 Office 365 以使用它们在 Microsoft 数据中心中对静态数据进行加密。静态数据包含来自 Exchange online 和 Skype for business 的数据, 这些数据存储在存储在 SharePoint online 和 OneDrive for business 中的邮箱和文件中。
  
您必须先安装 Azure, 然后才能使用适用于 Office 365 的客户密钥。本主题介绍了创建和配置所需 Azure 资源时需要遵循的步骤, 然后提供在 Office 365 中设置客户密钥的步骤。完成 Azure 安装后, 确定要为组织中的邮箱和文件分配的策略, 并因此确定哪些项。未分配策略的邮箱和文件将使用由 Microsoft 控制和管理的加密策略。有关客户密钥的详细信息, 或有关一般概述的详细信息, 请参阅[Customer key for Office 365 FAQ](service-encryption-with-customer-key-faq.md)。
  
> [!IMPORTANT]
> 强烈建议您遵循本主题中的最佳实践。这些信息称为**提示**和**重要**。通过 "客户密钥", 您可以控制其作用域与整个组织一样大的根加密密钥。这意味着, 使用这些密钥进行的错误可能会产生很大影响, 并且可能会导致数据中断或无法挽回的数据丢失。 
  
## <a name="before-you-begin-setting-up-customer-key"></a>开始设置客户密钥之前
<a name="Beforeyoustart"> </a>

在开始之前, 请确保你的组织拥有适当的许可。office 365 中的客户密钥在 office 365 E5 或高级合规性 SKU 中提供。
  
然后, 若要了解本主题中的概念和过程, 应查看[Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/)文档。此外, 还应熟悉 Azure 中使用的术语 (例如[租户](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant))。
  
若要提供有关客户密钥的反馈 (包括文档), 请将你的想法、建议和观点发送到 customerkeyfeedback@microsoft.com。
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>设置适用于 Office 365 的客户密钥的概述
<a name="Overview"> </a>

若要设置客户密钥, 你将完成这些任务。本主题的其余部分提供有关每个任务的详细说明, 或链接到过程中每个步骤的详细信息。
  
**在 Azure 和 Microsoft FastTrack 中:**
  
你将通过远程连接到 Azure PowerShell 来完成大部分这些任务。为获得最佳结果, 请使用版本4.4.0 或更高版本的 Azure PowerShell。
  
- [创建两个新的 Azure 订阅](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [注册 Azure 订阅以使用强制保留期](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    注册可能需要一到五个工作日的时间。
    
- [提交为激活 Office 365 的客户密钥的请求](controlling-your-data-using-customer-key.md#FastTrack)
    
    创建了这两个新的 Azure 订阅后, 您需要通过完成 Microsoft FastTrack 门户中承载的 web 表单来提交相应的客户密钥提供请求。**FastTrack 团队不会向客户密钥提供帮助。Office 只是使用 FastTrack 门户来允许您提交表单并帮助我们跟踪客户密钥的相关优惠**。
  
提交客户密钥提供后, Microsoft 会查看你的请求, 并在你继续执行其余设置任务时通知你。此过程最长可能需要5个工作日。
    
- [在每个订阅中创建高级 Azure 密钥保管库](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [将权限分配给每个密钥存储库](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [启用然后确认密钥电子仓库上的软删除](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [通过创建或导入密钥将密钥添加到每个密钥存储库](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [检查密钥的恢复级别](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [备份 Azure 密钥存储库](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [验证 Azure Key Vault 配置设置](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [获取每个 Azure Key Vault 密钥的 URI](controlling-your-data-using-customer-key.md#GetKeyURI)
    
**在 Office 365 中:**
  
Exchange Online 和 Skype for business:
  
- [创建与 Exchange Online 和 Skype for business 一起使用的数据加密策略 (DEP)](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [将 DEP 分配给邮箱](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [验证邮箱加密](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint Online 和 OneDrive for business:
  
- [为每个 SharePoint Online 和 OneDrive for business 地域创建数据加密策略 (DEP)](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [验证组网站、团队网站和 OneDrive for business 的加密](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>在 Azure key Vault 和 Microsoft FastTrack 中完成对客户密钥的任务
<a name="AzureSteps"> </a>

在 Azure Key Vault 中完成这些任务, 以便设置适用于 Office 365 的客户密钥。您需要完成这些步骤, 而不管您打算为 Exchange online 和 Skype for business 或 SharePoint online 和 OneDrive for business 或 SharePoint online 和 OneDrive for business 或 Office 365 中的所有受支持的服务设置客户密钥。
  
### <a name="create-two-new-azure-subscriptions"></a>创建两个新的 Azure 订阅
<a name="Create2newsubs"> </a>

客户密钥需要两个 Azure 订阅。作为一种最佳做法, Microsoft 建议您创建新的 Azure 订阅以用于客户密钥。azure Key Vault 密钥只能为同一 azure Active Directory (AAD) 租户中的应用程序授权, 您必须使用用于将 DEPs 分配到的 Office 365 组织使用的相同 Azure AD 租户创建新订阅。例如, 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户。有关详细步骤, 请参阅[将 Azure 注册为组织](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)。
  
> [!IMPORTANT]
> 客户密钥需要每个数据加密策略 (DEP) 的两个密钥。若要实现此目的, 必须创建两个 Azure 订阅。作为一种最佳做法, Microsoft 建议您的组织的各个成员在每个订阅中配置一个密钥。此外, 这些 Azure 订阅应仅用于管理 Office 365 的加密密钥。这将保护您的组织, 以防您在某个操作员意外、有意或恶意删除或以其他方式 mismanages 它们所负责的密钥。<br/> 我们建议您设置新的 azure 订阅, 这些订阅仅用于管理 Azure key Vault 资源, 以便与客户密钥配合使用。您可以为您的组织创建的 Azure 订阅数没有实际限制。按照这些最佳做法, 可以最大限度地减少人为错误的影响, 同时帮助管理由客户密钥使用的资源。 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>提交为激活 Office 365 的客户密钥的请求
<a name="FastTrack"> </a>

完成 Azure 步骤后, 你需要在[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)中提交服务请求。通过 FastTrack web 门户提交请求后, Microsoft 将验证您提供的 Azure 密钥 Vault 配置数据和联系人信息。您在 "产品" 窗体中所做的有关组织的授权监察官的选择对完成客户密钥注册至关重要且必需。您在表单中选择的您组织的监察官将用于确保任何请求吊销的真实性, 并销毁与客户密钥数据加密策略一起使用的所有密钥。您需要执行此步骤一次, 激活 Exchange online 和 Skype for business 覆盖的客户密钥, 并再次激活适用于 SharePoint online 和 OneDrive for business 的客户密钥。
  
若要提交用于激活客户密钥的服务, 请完成以下步骤:
  
1. 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 登录到[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。
    
2. 登录后, 请浏览到**仪表板**。
    
3. 选择 "**服务**", 并查看当前提供的列表。
    
4. 有关适用于你的优惠, 请选择 "**了解详细信息**": 
    
  - **Exchange Online 和 Skype for business:** 选择 "了解 Exchange 的**客户密钥**" 提供的**详细信息**。 
    
  - **SharePoint Online 和 OneDrive for business:** 选择了解有关**SharePoint 和 OneDrive for** business 产品的客户密钥的**详细信息**。 
    
5. 在 "**提供详细信息**" 页上, 选择 "**创建请求**"。
    
6. 填写 "产品" 窗体上的所有适用详细信息和请求的信息。特别注意您的组织中要授权的监察官, 以批准永久和不可恢复的加密密钥和数据的销毁。完成表单后, 选择 "**提交**"。
    
    在 Microsoft 收到你的请求通知后, 此过程最长可能需要5个工作日。
    
7. 继续执行下面的必需保留期部分。
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>注册 Azure 订阅以使用强制保留期
<a name="RegisterSubsforMRP"> </a>

临时或永久丢失根加密密钥可能会非常中断, 甚至会导致服务操作发生故障, 并可能导致数据丢失。出于此原因, 使用客户密钥的资源需要加强保护。与客户密钥结合使用的所有 Azure 资源在默认配置之外提供保护机制。可以通过阻止即时和不可撤销取消的方式对 Azure 订阅进行标记或注册。这称为注册强制保留期。为强制保留期注册 Azure 订阅所需的步骤需要与 Office 365 团队进行协作。此过程可能需要一至五个工作日。以前, 这有时称为 "不取消"。
  
在联系 Office 365 团队之前, 必须为您使用客户密钥的每个 Azure 订阅执行以下步骤:
  
1. 使用 azure PowerShell 登录到 azure 订阅。有关说明, 请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。
    
2. 运行 AzureRmProviderFeature cmdlet 以注册你的订阅, 以使用强制保留期。
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. 请与 Microsoft 联系以完成此过程。对于 SharePoint 和 OneDrive for business 团队, 请联系[spock@microsoft.com](mailto:spock@microsoft.com)。对于 Exchange Online 和 Skype for business, 请联系[exock@microsoft.com](mailto:exock@microsoft.com)。完成此过程所需的服务级别协议 (SLA) 是在 Microsoft 经过通知 (并验证) 后, 注册了你的订阅以使用强制保留期后, 此过程的服务级别协议 (SLA) 就是5个工作日。在您的电子邮件中包括以下内容:
    
    **Subject**: \<*租户的完全限定域名*的客户密钥\> 
    
    **正文**: 要为其完成强制保留期的订阅 id。 
    
4. 收到 Microsoft 注册已完成的通知后, 通过运行 AzureRmProviderFeature cmdlet 验证注册的状态, 如下所示:
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. 在验证 AzureRmProviderFeature cmdlet 中的**注册状态**属性返回**已注册**的值后, 请运行以下命令来完成此过程:
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每个订阅中创建高级 Azure 密钥保管库
<a name="CreateKeyVault"> </a>

创建密钥存储库的步骤在[开始使用 azure key vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)时进行介绍, 此步骤将指导你完成安装和启动 azure PowerShell, 连接到 azure 订阅, 创建资源组, 以及在其中创建密钥存储库资源组。
  
创建密钥存储库时, 必须选择 SKU: 标准版或高级存储库。标准 sku 允许 Azure Key Vault 密钥受软件保护-没有硬件安全模块 (HSM) 密钥保护-并且 Premium SKU 允许使用 hsm 来保护关键保管库密钥。客户密钥接受使用任何 SKU 的密钥电子仓库, 尽管 Microsoft 强烈建议您仅使用高级 SKU。无论是哪种类型的键的运算开销都是一样的, 因此, 每个受 HSM 保护的密钥的成本的唯一区别是每个月的成本。有关详细信息, 请参阅[主要保管库定价](https://azure.microsoft.com/pricing/details/key-vault/)。 
  
> [!IMPORTANT]
> 对生产数据使用 Premium sku 密钥电子仓库和受 HSM 保护的密钥, 并且仅使用标准 SKU 密钥电子仓库和密钥进行测试和验证。 
  
对于每个将使用客户密钥的 Office 365 服务, 请在您创建的两个 Azure 订阅中的每个中创建一个密钥存储库。例如, 仅针对 Exchange Online 和 Skype for business 或 SharePoint online 和 OneDrive for business, 你将仅创建一对电子仓库。若要同时为 Exchange online 和 SharePoint online 启用客户密钥, 您将创建两对主要电子仓库。
  
对密钥库使用命名约定, 以反映将与保管库关联的 DEP 的预期用途。请参阅下面的 "最佳实践" 部分, 了解命名约定建议。
  
为每个数据加密策略创建一组单独的、成对的电子仓库。对于 Exchange Online, 当您将策略分配给邮箱时, 会选择数据加密策略的范围。一个邮箱只能分配一个策略, 并且最多可以创建50个策略。对于 SharePoint Online, 策略的范围是组织内的所有数据 (地理位置或地理位置)。
  
创建密钥存储库还需要创建 Azure 资源组, 因为密钥存储库需要存储容量 (尽管非常小) 和密钥存储库日志记录 (如果启用) 也会生成存储的数据。作为一种最佳做法, Microsoft 建议使用单独的管理员来管理每个资源组, 并将管理与将管理所有相关客户密钥资源的一组管理员相一致。
  
> [!IMPORTANT]
> 若要最大限度地提高可用性, 关键电子仓库应位于与 Office 365 服务接近的区域。例如, 如果您的 Exchange Online 组织在北美, 请将您的密钥电子仓库放在北美。如果你的 Exchange Online 组织在欧洲, 请将你的密钥电子仓库放在欧洲。<br/>对密钥存储库使用公用前缀, 并包含密钥保管库和密钥的使用和作用域的缩写 (例如, 对于将在北美使用电子仓库的 Contoso SharePoint 服务, 可能的姓名对是 contoso-O365SP-VaultA1,Contoso-O365SP-NA-VaultA2。保管库名称在 Azure 中是全局唯一的字符串, 因此, 如果所需名称已由其他 Azure 客户声明, 则可能需要尝试其他名称的变体。从7月2017电子仓库名称无法更改, 因此最佳做法是为设置编写计划, 并使用第二个人验证是否正确执行了计划。<br/>如果可能, 请在非配对区域中创建您的电子仓库。配对的 Azure 区域在服务故障域之间提供高可用性。因此, 可以将区域对视为彼此的备份区域。这意味着, 放置在一个区域中的 Azure 资源将自动获得配对区域的容错能力。出于此原因, 为在区域为成对的 DEP 中使用的两个电子仓库选择区域是指仅有两个可用性区域在使用中。大多数地理位置仅有两个区域, 因此尚不能选择非配对区域。如果可能, 请为用于 DEP 的两个电子仓库选择两个不成对的区域。这从总共四个可用区域获益。有关详细信息, 请参阅[业务连续性和灾难恢复 (BCDR):](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)当前区域对列表的 Azure 配对区域。 
  
### <a name="assign-permissions-to-each-key-vault"></a>将权限分配给每个密钥存储库
<a name="KeyVaultPerms"> </a>

对于每个密钥存储库, 您将需要为客户密钥定义三组不同的权限, 具体取决于您的实现。例如, 您需要为以下各项定义一组权限:
  
- 将对您的组织执行关键电子仓库的日常管理的**主要保管库管理员**。这些任务包括备份、创建、获取、导入、列出和还原。 
    
    > [!IMPORTANT]
    > 分配给主要保管库管理员的权限集不包含删除密钥的权限。这是有意和重要的做法。通常情况下, 删除加密密钥不会完成, 因为这样做会永久破坏数据。作为一种最佳做法, 默认情况下不要向主要保管库管理员授予此权限。相反, 请为重要的保管库参与者预留此权限, 并在清楚了解结果的情况下, 仅在短期内将其分配给管理员。 
  
    若要将这些权限分配给 Office 365 组织中的用户, 请使用 azure PowerShell 登录 azure 订阅。有关说明, 请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。
    
- 运行 AzureRmKeyVaultAccessPolicy cmdlet 以分配所需的权限。
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  例如：
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- 可以更改 Azure 密钥存储库本身权限的**主要保管库参与者**。您需要更改这些权限, 因为员工离开或加入团队, 或者在极少数情况下, 主要保管库管理员合法需要删除或还原密钥的权限。需要在密钥保管库中向此组密钥 vault 参与者授予**参与者**角色。您可以使用 Azure 资源管理器分配此角色。有关详细步骤, 请参阅[使用基于角色的访问控制管理对 Azure 订阅资源的访问权限](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。创建订阅的管理员将隐式拥有此访问权限, 以及将其他管理员分配给参与者角色的能力。
    
- 如果打算将客户密钥用于 exchange online 和 skype for business, 则需要向 Office 365 授予权限, 以代表 Exchange online 和 skype for business 使用密钥保管库。同样, 如果您打算将客户密钥与 sharepoint online 和 onedrive for business 结合使用, 则需要添加 Office 365 的权限, 以代表 SharePoint online 和 onedrive for business 使用密钥存储库。若要向 Office 365 授予权限, 请使用以下语法运行**AzureRmKeyVaultAccessPolicy** cmdlet: 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    其中：
    
  - *vaultname*是您创建的主要保管库的名称。 
    
  - 对于 Exchange Online 和 Skype for business, 请将*Office 365 appID*替换为`00000002-0000-0ff1-ce00-000000000000`
    
  - 对于 SharePoint Online 和 OneDrive for business, 请将*Office 365 appID*替换为`00000003-0000-0ff1-ce00-000000000000`
    
  示例: 设置 Exchange Online 和 Skype for business 的权限:
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  示例: 设置 SharePoint Online 和 OneDrive for business 的权限
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>启用然后确认密钥电子仓库上的软删除
<a name="SoftDelete"> </a>

如果可以快速恢复密钥, 则由于意外或恶意删除的密钥而遇到的扩展服务故障的可能性较小。您需要先启用此配置 (称为 "软删除"), 然后才能在 "客户密钥" 中使用密钥。启用软删除允许您在删除90天内恢复密钥或电子仓库, 而无需从备份中还原它们。
  
若要在密钥保管库上启用软删除, 请完成以下步骤:
  
1. 使用 Windows Powershell 登录到你的 Azure 订阅。有关说明, 请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。
    
2. 运行[AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet。在此示例中, *vaultname*是要为其启用软删除的主要保管库的名称: 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. 通过运行**AzureRmKeyVault** cmdlet, 确认已为密钥存储库配置了软删除。如果为密钥存储库正确配置了软删除, 则会启用软删除？属性返回的值**为 True**: 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>通过创建或导入密钥将密钥添加到每个密钥存储库
<a name="AddKeystoKeyVault"> </a>

有两种方法可以将密钥添加到 Azure Key Vault;可以直接在密钥保管库中创建密钥, 也可以导入密钥。直接在 "密钥存储库" 中创建密钥是不太复杂的方法, 而导入密钥提供了对如何生成密钥的总体控制。
  
若要直接在密钥保管库中创建密钥, 请运行[AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet, 如下所示: 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

其中：
  
-  *vaultname*是要在其中创建密钥的密钥保管库的名称。 
    
-  *keyname*是要赋予新键的名称。 
    
    > [!TIP]
    > 使用上面的密钥库的命名约定命名键。这样一来, 在仅显示密钥名称的工具中, 字符串是自我描述的。 
  
- 如果打算使用 hsm 保护密钥, 请确保将**HSM**指定为_Destination_参数的值, 否则指定 "**软件**"。
    
例如，
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

若要将密钥直接导入到密钥存储库中, 您需要具有 Thales nShield 硬件安全模块。
  
某些组织首选使用此方法来建立其密钥的 provenance, 此方法还提供以下内容:
  
- 用于导入的工具集包括来自 Thales 的证明, 用于加密所生成密钥的密钥交换密钥 (KEK) 不可导出, 并在 Thales 制造的正版 HSM 中生成。
    
- 该工具集包括来自 Thales 的证明, 这些安全世界也是在由 Thales 生产的正版 HSM 上生成的。此认证向你证明 Microsoft 也在使用正版 Thales 硬件。
    
检查安全组以确定是否需要上述 attestations。有关在本地创建密钥并将其导入到密钥保管库的详细步骤, 请参阅 how [to 为 Azure key vault 生成和传输受 HSM 保护的密钥](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。使用 Azure 说明在每个密钥存储库中创建密钥。
  
### <a name="check-the-recovery-level-of-your-keys"></a>检查密钥的恢复级别
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 要求 Azure Key Vault 订阅设置为 "不取消", 并且客户密钥使用的密钥启用了软删除。你可以通过查看密钥上的恢复级别来确认这一点。
  
若要检查注册表项的恢复级别, 请在 Azure PowerShell 中运行 AzureKeyVaultKey cmdlet, 如下所示:
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

如果_恢复级别_属性返回的值不是**可恢复 + ProtectedSubscription**的值, 则需要查看本主题, 并确保已按照所有步骤将订阅放在 "不要取消" 列表中, 并将已在每个密钥保管库上启用软删除。
  
### <a name="backup-azure-key-vault"></a>备份 Azure 密钥存储库
<a name="BackupAzureKeyVaultkeys"> </a>

立即完成创建或对某个键的任何更改, 执行备份并存储联机和脱机的备份副本。脱机副本不应连接到任何网络, 例如在物理安全或商业存储设施中。至少应将备份的一个副本存储在灾难发生时可访问的位置。备份 blob 是恢复密钥材料的唯一方法 (应永久销毁密钥保管库密钥), 或以其他方式呈现为不可操作。azure key vault 外部的密钥和已导入到 azure key vault 的密钥不能作为备份, 因为客户密钥使用密钥所需的元数据在外部密钥中不存在。只有从 Azure 密钥存储库中获取的备份才能用于使用客户密钥的还原操作。因此, 在上载或创建密钥时, 应创建 Azure 密钥存储库的备份, 这一点非常重要。
  
若要创建 Azure key Vault 密钥的备份, 请运行[AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet, 如下所示:
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

确保输出文件使用后缀`.backup`。
  
此 cmdlet 生成的输出文件已加密, 不能在 Azure 密钥保管库外部使用。只能将备份还原到从中获取备份的 Azure 订阅。
  
> [!TIP]
> 对于输出文件, 选择您的电子仓库名称和密钥名称的组合。这将使文件名自我描述。它还将确保备份文件名称不会发生冲突。 
  
例如：
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>验证 Azure Key Vault 配置设置
<a name="Validateconfiguration"> </a>

在 DEP 中使用密钥之前执行验证是可选的, 但强烈建议这样做。特别是, 如果您使用步骤设置了除本主题中所述的密钥和电子仓库之外的密钥和电子仓库, 则应在配置客户密钥之前验证 Azure Key Vault 资源的运行状况。
  
若要验证您的密钥是否启用了 get、wrapKey 和 unwrapKey 操作, 请执行以下操作:
  
运行[AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet, 如下所示: 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

在 "输出" 中, 根据需要查找访问策略和 Exchange online 标识 (guid) 或 SharePoint online 标识 (guid)。所有三个权限都必须显示在 "键的权限" 下。
  
如果访问策略配置不正确, 请运行 AzureRmKeyVaultAccessPolicy cmdlet, 如下所示:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

例如, 对于 Exchange Online 和 Skype for business:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

例如, 对于 SharePoint Online 和 OneDrive for business:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

若要验证没有为你的密钥设置到期日期, 请运行[AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet, 如下所示: 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

已过期的密钥不能由客户密钥使用, 尝试使用过期密钥的操作将会失败, 并且可能会导致服务中断。强烈建议使用与客户密钥一起使用的密钥不具有过期日期。过期日期一旦设置, 便无法删除, 但可以更改为不同的日期。如果必须使用具有过期日期设置的密钥, 请将 "过期" 值更改为 "12/31/9999"。过期日期设置为12/31/9999 之外的密钥将不会通过 Office 365 验证。
  
若要更改已设置为12/31/9999 以外的任何其他值的过期日期, 请运行[AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet, 如下所示: 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 不要在与客户密钥结合使用的加密密钥上设置到期日期。 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>获取每个 Azure Key Vault 密钥的 URI
<a name="GetKeyURI"> </a>

完成 Azure 中的所有步骤以设置密钥存储库并添加密钥后, 运行以下命令以获取每个密钥存储库中的密钥的 URI。在稍后创建和分配每个 DEP 时, 需要使用这些 uri, 将此信息保存在安全的位置。请务必为每个密钥保管库运行一次此命令。
  
在 Azure PowerShell 中:
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: 设置 Exchange Online 和 Skype for business 的客户密钥
<a name="AzureSteps"> </a>

在开始之前, 请确保您已完成设置 Azure Key Vault 所需的任务。有关信息, 请参阅[Azure Key Vault 和 Microsoft FastTrack 中的 "完成任务" 以获取客户密钥](controlling-your-data-using-customer-key.md#AzureSteps)。 
  
若要设置 exchange online 和 Skype for business 的客户密钥, 你将需要通过 Windows PowerShell 远程连接到 exchange online 来执行这些步骤。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>创建与 Exchange Online 和 Skype for business 一起使用的数据加密策略 (DEP)
<a name="CreateDEP4EXOSkype"> </a>

一个 DEP 与 Azure Key Vault 中存储的一组密钥相关联。您在 Office 365 中向邮箱分配了一个 DEP。然后, Office 365 将使用在策略中标识的密钥来加密邮箱。若要创建 DEP, 您需要之前获取的主要保管库 uri。有关说明, 请参阅[获取每个 Azure Key Vault 密钥的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。 
  
还!创建 DEP 时, 请指定驻留在两个不同的 Azure Key 保管库中的两个密钥。确保这些项位于两个单独的 Azure 区域中, 以确保地域冗余。
  
若要创建 DEP, 请按照以下步骤操作:
  
1. 在您的本地计算机上, 使用在 Office 365 组织中具有全局管理员权限的工作或学校帐户, 通过打开 Windows PowerShell 并运行以下命令[连接到 Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) 。 
    
   ```
   $UserCredential = Get-Credential
   ```

2. 在 "Windows PowerShell 凭据请求" 对话框中, 输入你的工作或学校帐户信息, 单击 **"确定**", 然后输入以下命令。 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. 运行以下命令。
    
   ```
   Import-PSSession $Session
   ```

4. 若要创建 DEP, 请通过键入以下命令来使用 DataEncryptionPolicy cmdlet。
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   其中：
    
   -  *PolicyName*是要用于策略的名称。名称不能包含空格。例如, USA_mailboxes。 
    
   -  *PolicyDescription*是一种用户友好的策略说明, 可帮助您记住该策略的用途。您可以在说明中包含空格。例如, 美国邮箱和其区域的根键。 
    
   -  *KeyVaultURI1*是策略中的第一个项的 URI。例如, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。 
    
   -  *KeyVaultURI2*是策略中的第二个项的 URI。例如, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。用逗号和空格分隔两个 uri。 
    
   示例：
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>将 DEP 分配给邮箱
<a name="assignDEPtomailbox"> </a>

使用 "设置邮箱" cmdlet 将 DEP 分配给邮箱。一旦分配了策略, Office 365 就可以使用 DEP 中指定的密钥对邮箱进行加密。
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中*MailboxIdParameter*指定邮箱。有关设置邮箱 cmdlet 的详细信息, 请参阅[set-邮箱](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)。
  
### <a name="validate-mailbox-encryption"></a>验证邮箱加密
<a name="validatemailboxencryption"> </a>

对邮箱加密可能需要一段时间。在首次分配策略时, 该邮箱还必须完成从一个数据库到另一个数据库的移动, 然后才能对该邮箱进行加密。建议您在更改 dep 或首次将 dep 分配到邮箱之后, 先等待72小时, 再尝试验证加密。
  
使用 get-mailboxstatistics cmdlet 可以确定邮箱是否已加密。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果邮箱已加密, 则 IsEncrypted 属性返回**true** , 如果邮箱未加密, 则返回**false**值。 

完成邮箱移动的时间取决于第一次为其分配 DEP 的邮箱数以及邮箱的大小。如果自您分配 DEP 之后一周后邮箱尚未加密, 请使用 new-moverequest cmdlet 为未加密邮箱启动邮箱移动。

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365: 设置适用于 SharePoint Online 和 OneDrive for business 的客户密钥
<a name="AzureSteps"> </a>

在开始之前, 请确保您已完成设置 Azure Key Vault 所需的任务。有关信息, 请参阅[Azure Key Vault 和 Microsoft FastTrack 中的 "完成任务" 以获取客户密钥](controlling-your-data-using-customer-key.md#AzureSteps)。 
  
若要设置适用于 sharepoint online 和 OneDrive for business 的客户密钥, 你将需要通过使用 Windows PowerShell 远程连接到 SharePoint online 来执行这些步骤。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>为每个 SharePoint Online 和 OneDrive for business 地域创建数据加密策略 (DEP)
<a name="CreateDEP4SPOODfB"> </a>

一个 DEP 与 Azure Key Vault 中存储的一组密钥相关联。您将 DEP 应用于一个地理位置 (也称为地理位置) 中的所有数据。如果您使用的是 Office 365 的多地理位置功能 (当前处于预览阶段), 您可以为每个地理位置创建一个 DEP。如果您不使用多地理位置, 则可以在 Office 365 中创建一个用于 SharePoint Online 和 OneDrive for business 的 DEP。然后, Office 365 将使用在 DEP 中标识的密钥来加密该地理位置中的数据。若要创建 DEP, 您需要之前获取的主要保管库 uri。有关说明, 请参阅[获取每个 Azure Key Vault 密钥的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。 
  
还!创建 DEP 时, 请指定驻留在两个不同的 Azure Key 保管库中的两个密钥。确保这些项位于两个单独的 Azure 区域中, 以确保地域冗余。
  
若要创建 DEP, 您需要使用 Windows PowerShell 远程连接到 SharePoint Online。
  
1. 在您的本地计算机上, 使用在 Office 365 组织中具有全局管理员权限的工作或学校帐户,[连接到 SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx)。
    
2. 在 Microsoft SharePoint Online 命令行管理程序中, 运行[SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet, 如下所示: 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   注册 DEP 时, 会开始对 geo 中的数据进行加密。这可能需要一些时间。
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>验证组网站、团队网站和 OneDrive for business 的加密
<a name="validateencryptionSPO"> </a>

您可以通过运行 SPODataEncryptionPolicy cmdlet 来检查加密状态, 如下所示:
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

此 cmdlet 的输出包括:
  
- 主键的 URI。
    
- 辅助密钥的 URI。
    
- 地理位置的加密状态。可能的状态包括:
    
  - 未**注册:** 尚未应用客户密钥加密。 
    
  - **注册:** 客户密钥加密已应用, 并且您的文件正在被加密。如果你的地理位置处于此状态, 则还会显示有关 geo 中的多少个网站的完成百分比的信息, 以便你可以监视加密进度。 
    
  - **注册:** 客户密钥加密已应用, 并且所有网站中的所有文件均已加密。 
    
  - **滚动:** 正在进行密钥滚动。如果你的地理位置处于此状态, 则还会显示有关已完成密钥滚动操作的网站百分比的信息, 以便你可以监视进度。 
    
## <a name="managing-customer-key-for-office-365"></a>管理 Office 365 的客户密钥
<a name="ManageCustomerKey"> </a>

在设置了适用于 Office 365 的客户密钥之后, 可以执行这些额外的管理任务。
  
- [还原 Azure Key Vault 密钥](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [在使用客户密钥的 Azure key Vault 中滚动或旋转密钥](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [管理密钥存储库权限](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [确定分配给邮箱的 DEP](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>还原 Azure Key Vault 密钥
<a name="RestoreAzureKeyVaultKeys"> </a>

在执行还原之前, 请使用由软删除提供的恢复功能。需要使用与客户密钥一起使用的所有密钥才能启用软删除。软删除操作类似于回收站, 允许恢复最长为90天, 而无需进行还原。只有在极端或异常情况下才需要还原, 例如, 密钥或密钥存储库丢失。如果您必须还原密钥以用于客户密钥, 请在 Azure PowerShell 中运行 AzureKeyVaultKey cmdlet, 如下所示:
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

例如：
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

如果密钥存储区中已存在具有相同名称的键, 还原操作将失败。Restore-AzureKeyVaultKey 还原密钥的所有密钥版本和所有元数据, 包括密钥名称。
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>在使用客户密钥的 Azure key Vault 中滚动或旋转密钥
<a name="RollCKkey"> </a>

Azure Key Vault 或 Customer 密钥不需要滚动密钥。此外, 通过 HSM 保护的密钥几乎不可能受到危害。即使某个根键是在拥有恶意参与者的情况下, 也没有使用它来解密数据的可行方法, 因为只有 Office 365 代码知道了如何使用它。但是, 滚动密钥是由客户密钥支持的。
  
> [!CAUTION]
> 在明确的技术原因或合规性要求规定您必须滚动密钥时, 只需滚动与客户密钥一起使用的加密密钥。此外, 请勿删除与策略关联的或与之相关联的任何密钥。在滚动键时, 会使用以前的密钥对内容进行加密。例如, 虽然活动邮箱将被频繁地重新加密, 但非活动邮箱、断开连接和已禁用邮箱仍可以使用以前的密钥进行加密。SharePoint Online 执行用于还原和恢复目的的内容备份, 因此可能仍有存档的内容使用旧密钥。<br/> 为了确保数据的安全性, SharePoint Online 将不允许一个以上的键滚动操作一次进行。如果要将密钥存储库中的两个密钥一起滚动, 则需要等待第一个密钥滚动操作完全完成。我们建议您将密钥滚动操作以不同的间隔错开, 这样就不会出现问题。 
  
当您滚动某个键时, 您请求的是现有密钥的新版本。若要请求现有密钥的新版本, 请使用相同的 cmdlet ( [AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)), 其语法与您在第一个位置创建密钥时使用的语法相同。
  
例如：
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

在此示例中, 由于名为**contoso-O365EX-VaultA1-Key001**的键在**contoso-O365EX-na-VaultA1**保管库中已存在, 将创建一个新的密钥版本。该操作将添加新的密钥版本。此操作将保留密钥版本历史记录中以前的密钥版本, 以便仍可以解密之前使用该密钥加密的数据。完成滚动与 DEP 关联的任何键后, 必须运行其他 cmdlet, 以确保客户密钥开始使用新密钥。 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>在滚动或旋转 Azure key Vault 中的密钥之后, 启用 Exchange Online 和 Skype for business 以使用新密钥

当您滚动与 Exchange Online 和 Skype for business 使用的 DEP 相关联的任何 Azure Key Vault 密钥时, 您必须运行以下命令来更新 DEP 并启用 Office 365 以开始使用新密钥。
  
若要指示客户密钥使用新密钥加密 Office 365 中的邮箱, 请运行 DataEncryptionPolicy cmdlet, 如下所示:
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

在48小时内, 使用此策略加密的活动邮箱将会与更新的密钥相关联。按照[确定分配给邮箱的 DEP](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)中的步骤检查邮箱的 DataEncryptionPolicyID 属性的值。一旦应用了更新的键, 此属性的值将更改。 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>启用 SharePoint Online 和 OneDrive for business 以在 Azure key Vault 中滚动或旋转密钥后使用新密钥

当您滚动与 SharePoint Online 和 OneDrive for business 使用的 DEP 相关联的任何 Azure Key Vault 密钥时, 您必须运行[SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet 以更新 DEP, 并启用 Office 365 以开始使用新密钥。 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

这将启动 SharePoint Online 和 OneDrive for business 的密钥滚动操作。此操作不是即时执行的。若要查看密钥滚动操作的进度, 请运行 SPODataEncryptionPolicy cmdlet, 如下所示:
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>管理密钥存储库权限
<a name="Managekeyvaultperms"> </a>

提供了多个 cmdlet, 以便你可以查看并在必要时删除密钥保管库权限 (如有必要)。您可能需要删除权限, 例如, 当员工离开团队时。
  
若要查看密钥存储区权限, 请运行 AzureRmKeyVault cmdlet:
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

例如：
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

若要删除管理员权限, 请运行 AzureRmKeyVaultAccessPolicy cmdlet:
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

例如：
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>确定分配给邮箱的 DEP
<a name="DeterminemailboxDEP"> </a>

若要确定分配给邮箱的 DEP, 请使用 get-mailboxstatistics cmdlet。cmdlet 返回唯一标识符 (GUID)。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

其中*GeneralMailboxOrMailUserIdParameter*指定邮箱。有关 get-mailboxstatistics cmdlet 的详细信息, 请参阅[get-mailboxstatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)。
  
通过运行以下 cmdlet, 使用 GUID 找出邮箱所分配到的 DEP 的友好名称。
  
```
Get-DataEncryptionPolicy <GUID>
```

其中*guid*是上一步中的 get-mailboxstatistics cmdlet 返回的 guid。 
  


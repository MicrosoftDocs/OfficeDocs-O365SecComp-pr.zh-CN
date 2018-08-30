---
title: 使用客户密钥控制 Office 365 中的数据
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
description: 了解如何设置客户参数 Office 365 的 Exchange Online、 Skype 的业务和 SharePoint Online 的 OneDrive for Business。与客户参数，您将控制组织的加密密钥，然后配置 Office 365 使用它们在 Microsoft 数据中心中的 rest 数据进行加密。
ms.openlocfilehash: f8d7c12c32ca74b842f676f4a2ccde4d1c758361
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22559227"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a>使用客户密钥控制 Office 365 中的数据

与客户参数，您将控制组织的加密密钥，然后配置 Office 365 使用它们在 Microsoft 数据中心中的 rest 数据进行加密。静态数据包括 Exchange Online 和 Skype for Business 内的邮箱和 SharePoint Online 中存储的文件中存储和 OneDrive for Business 中的数据。
  
可以使用的 Office 365 客户密钥之前，必须设置 Azure。本主题介绍了您需要按照创建和配置所需的 Azure 资源的步骤，然后设置 Office 365 中的客户参数提供的步骤。Azure 安装完成后，您可以确定哪些策略，因此，哪些键，分配给邮箱和您的组织中的文件。邮箱和不为其分配策略的文件将使用的控制以及由 Microsoft 托管加密策略。有关客户参数的详细信息，或的一般概述，请参阅[Office 365 常见问题的客户参数](service-encryption-with-customer-key-faq.md)。
  
> [!IMPORTANT]
> 我们强烈建议您按照本主题中的最佳做法。这些称为作为**提示**和**重要**。客户密钥使您能够控制其范围可为您的整个组织的根加密密钥。这意味着错误用这些项可以具有广泛的影响，并且可能会导致服务中断或不可撤消丢失数据。 
  
## <a name="before-you-begin-setting-up-customer-key"></a>开始之前设置客户参数
<a name="Beforeyoustart"> </a>

在开始之前，确保您具有相应组织的授权。Office 365 中的客户参数是 Office 365 E5 或高级合规性 SKU 中提供的。
  
然后，若要了解的概念和本主题中的过程，您应当查看[Azure 键仓库](https://azure.microsoft.com/en-us/documentation/services/key-vault/)文档。此外，先熟悉在 Azure，例如，[租户](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)中使用的术语。
  
若要提供反馈客户项，包括文档，请向 customerkeyfeedback@microsoft.com 发送您的想法、 建议和角度。
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a>客户参数设置为 Office 365 概述
<a name="Overview"> </a>

若要设置客户参数将完成这些任务。本主题的其余部分提供了详细的说明每项任务，或出过程中每个步骤的详细信息的链接。
  
**Azure 和 Microsoft FastTrack： 中**
  
您将通过远程连接到 Azure PowerShell 完成这些任务的大部分。为了获得最佳结果，使用版本 4.4.0 或更高版本的 Azure PowerShell。
  
- [创建两个新的 Azure 订阅](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [注册使用强制性的保留期的 Azure 订阅](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    注册可能需要介于 1 到 5 个工作日。
    
- [提交一个请求激活的 Office 365 客户参数](controlling-your-data-using-customer-key.md#FastTrack)
    
    创建两个新 Azure 订阅后，您需要通过完成 Microsoft FastTrack 门户中承载的 web 表单提交适当的客户参数提供请求。FastTrack 团队不与客户参数提供帮助。Office 只需使用 FastTrack 门户以允许您来提交表单，并将有助于我们开发出跟踪客户项相关的产品。
  
后已提交客户参数版，Microsoft 审阅您的请求，并且可以继续执行安装任务的其余部分时通知您。此过程可能需要最多五个工作日。
    
- [在每个订阅中创建 Azure 键仓库 premium](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [将权限分配给每个主要的存储库](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [启用，然后确认软删除的主要存储库](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [将项添加到每个关键电子仓库可以通过创建或导入密钥](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [检查您的密钥的恢复级别](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [备份 Azure 存储库](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [验证 Azure 键仓库配置设置](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [获取每个 Azure 键仓库键的 URI](controlling-your-data-using-customer-key.md#GetKeyURI)
    
**Office 365： 中**
  
Exchange Online 和 Skype for Business:
  
- [创建用于 Exchange Online 和 Skype 的业务数据加密策略 (DEP)](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [分配邮箱的 DEP](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [验证邮箱加密](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
SharePoint Online 和 OneDrive for Business:
  
- [为业务地理位置的每个 SharePoint Online 和 OneDrive 创建数据加密策略 (DEP)](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [验证组网站、 工作组网站和 OneDrive for Business 的加密](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Azure 键仓库和客户键的 Microsoft FastTrack 中完成任务
<a name="AzureSteps"> </a>

Office 365 客户密钥设置为了完成 Azure 键存储库中的这些任务。您需要完成这些步骤，无论您是否打算客户参数为 Exchange Online 和设置 Skype 业务或 SharePoint Online 和 OneDrive for Business 或 Office 365 中的所有受支持的服务。
  
### <a name="create-two-new-azure-subscriptions"></a>创建两个新的 Azure 订阅
<a name="Create2newsubs"> </a>

两个 Azure 订阅所需的客户参数。作为最佳实践，Microsoft 建议您与客户参数创建用于新 Azure 订阅。仅授权中相同的 Azure Active Directory (AAD) 租户的应用程序的 azure 键仓库键，您必须创建使用用于 Office 365 组织将分配给 DEPs 同一 Azure AD 租户的新订阅。例如，使用工作或学校帐户已在 Office 365 组织中的全局管理员权限。有关详细步骤，请参阅[注册为组织的 Azure](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)。
  
> [!IMPORTANT]
> 客户参数为每个数据加密策略 (DEP) 需要两个键。若要实现此目的，您必须创建两个 Azure 订阅。作为最佳实践，Microsoft 建议您让组织的单独成员在每个订阅中配置一个键。此外，这些 Azure 订阅，只应使用 Office 365 中管理加密密钥。您运算符之一意外、 有意，或恶意删除或否则 mismanages 他们有责任的键的情况下，此保护您的组织。<br/> 我们建议您设置仅用于客户密钥管理使用 Azure 键仓库资源的新 Azure 订阅。没有可行到可以为组织创建的 Azure 订阅数限制。遵循这些最佳做法将最小化人为错误的影响同时帮助管理客户参数使用的资源。 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>提交一个请求激活的 Office 365 客户参数
<a name="FastTrack"> </a>

完成的 Azure 步骤之后，您需要提交[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)中的提供请求。一旦您已提交一个请求通过 FastTrack web 门户，Microsoft 将验证您提供的 Azure 键仓库配置数据和联系人信息。提供有关授权部主管的形式组织做的选择是关键和所需完成客户参数注册。您在窗体中选择您所在组织的部主管将用于确保任何请求撤销并销毁与客户参数数据加密策略所使用的所有项的可靠性。您需要执行一次此步骤的 Exchange Online 和 Skype 的业务范围和第二次 SharePoint Online 和 OneDrive for Business 的激活客户密钥激活客户参数。
  
若要提交提供的激活客户密钥，请完成以下步骤：
  
1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，登录到[Microsoft FastTrack 门户](https://fasttrack.microsoft.com/)。
    
2. 一旦您登录，浏览到**仪表板**。
    
3. 选择**提供**，并查看当前提供的列表。
    
4. **了解更多**选择为优惠适用于您： 
    
  - **Exchange Online 和 Skype for Business:****Exchange 的客户参数**版上，选择**了解更多**。 
    
  - **SharePoint Online 和 OneDrive for Business:** 在**SharePoint 和 OneDrive for Business 的客户参数**版上，选择**了解更多**。 
    
5. 在**提供详细信息**页上，选择**创建申请**。
    
6. 填写所有适用的详细信息和费窗体上的请求的信息。应特别注意您要对您的选择为哪些官员贵组织的授权批准永久和不可逆转地销毁加密密钥和数据。完成窗体后，选择**提交**。
    
    此过程可能需要最多五个工作日后 Microsoft 已经被通知您的请求。
    
7. 继续执行下面的强制性的保留期部分。
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>注册使用强制性的保留期的 Azure 订阅
<a name="RegisterSubsforMRP"> </a>

根加密密钥的临时或永久丢失可以非常中断或甚至灾难性服务操作，并会导致数据丢失。因此，与客户参数一起使用的资源要求强保护。与客户参数一起使用的所有 Azure 资源提供了保护机制超出默认配置。可以标记或以一种将阻止即时和不可撤消取消注册 azure 订阅。这称为为强制性的保留期注册。必需的保留期注册 Azure 订阅所需的步骤需要与 Office 365 团队协作。此过程可能需要介于 1 到 5 个工作日。以前，这是有时称为"不取消"。
  
与 Office 365 团队联系之前, 必须为每个 Azure 订阅与客户参数一起使用来执行以下步骤：
  
1. 登录到您使用 Azure PowerShell 的 Azure 订阅。有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。
    
2. 运行注册 AzureRmProviderFeature cmdlet 以注册您的订阅用于强制性的保留期。
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. 与 Microsoft 联系以具有已完成的过程。有关 SharePoint 和 OneDrive for Business 团队，请联系[spock@microsoft.com](mailto:spock@microsoft.com)。有关 Exchange Online 和 for Business 的 Skype，联系人[exock@microsoft.com](mailto:exock@microsoft.com)。服务级别协议 (SLA) 用于完成此过程的前 5 个工作日后 Microsoft 已通知 （并验证） 的已注册您的订阅用于强制性的保留期。您的电子邮件中包括以下内容：
    
    **主题**： 为客户参数\<*租户的完全限定的域名*\> 
    
    **正文**： 您希望其具有期间已完成强制保留的订阅 Id。 
    
4. 一旦您收到来自 Microsoft 注册已完成的通知，通过运行 Get AzureRmProviderFeature cmdlet，如下所示验证您注册的状态：
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. 确认后从 Get AzureRmProviderFeature cmdlet**注册 State**属性返回的值为**已注册**，运行以下命令以完成该过程：
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>在每个订阅中创建 Azure 键仓库 premium
<a name="CreateKeyVault"> </a>

要创建密钥的存储库的步骤均编档在[Getting Started with Azure 键存储库](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)，它将引导您安装和启动 Azure PowerShell、 连接到您的 Azure 订阅、 创建资源组，并创建中的关键电子仓库资源组。
  
当您创建一个关键电子仓库时，您必须选择 SKU： 标准或者 Premium。标准 SKU 允许 Azure 键仓库键术 シ モ メ 软件-没有硬件安全模块 (HSM) 密钥保护-并 Premium SKU 允许 Hsm 用于保护密钥仓库键。客户参数接受使用任一 SKU、 的关键电子仓库，但 Microsoft 强烈建议您使用只有 Premium SKU。具有任一类型的项的操作的成本是相同的因此成本中唯一的区别是每月的每个 HSM 保护密钥的成本。有关详细信息，请参阅[键仓库定价](https://azure.microsoft.com/pricing/details/key-vault/)。 
  
> [!IMPORTANT]
> 用于生产数据的高级版 SKU 关键电子仓库和 HSM 保护键和仅用于测试和验证使用标准 SKU 关键电子仓库和键。 
  
为与每个 Office 365 服务将使用客户参数，每个您创建的两个 Azure 订阅中创建关键存储库。例如，为 Exchange Online 和 Skype 业务仅或 SharePoint Online 的 OneDrive for Business 仅，您将创建只有一个对存储库。启用 Exchange Online 和 SharePoint Online 客户参数，您将创建两个关键电子仓库对。
  
使用反映将与其关联电子仓库 DEP 的预期的用途的关键电子仓库的命名约定。请参阅下面的命名约定建议的最佳实践部分。
  
创建一套单独、 配对的每个数据加密策略电子仓库。Exchange Online 的数据加密策略的作用域是由您时选择将策略分配到邮箱。邮箱可以具有只能有一个策略分配，并且您可以创建最多为 50 个策略。SharePoint online 的范围是策略的所有地理位置或地理位置中组织内的数据。
  
关键电子仓库创建还需要创建 Azure 资源组，因为关键电子仓库需要存储容量 （尽管非常小） 和密钥仓库日志记录，如果启用，还会生成存储的数据。最佳做法是 Microsoft 建议使用单独的管理员管理每个资源组，与右边缘与一组将管理所有相关的客户关键资源的管理员管理。
  
> [!IMPORTANT]
> 要最大化可用性，您关键电子仓库应为 Office 365 服务附近的区域。例如，在北美 Exchange Online 组织时，将您关键电子仓库放在北美。如果在欧洲 Exchange Online 组织，置于欧洲关键存储库。<br/>用于关键电子仓库，公共前缀，包含使用缩写和关键仓库和键的范围 (例如，用于电子仓库将位于北美的名称可能对 Contoso SharePoint 服务 Contoso O365SP NA VaultA1 和Contoso-O365SP-NA-VaultA2。存储库名称是 Azure 中的全局唯一字符串，因此可能需要已经由其他 Azure 客户占用了所需的名称的情况下尝试变体的程序所需的名称。从年 7 月 2017年仓库名称不能更改，因此最佳做法是已安装的编写的计划和另一个人用于验证正确执行计划。<br/>如果可能，在非配对区域中创建存储库。配对 Azure 区域跨服务故障域提供高可用性。因此，可以将区域对看作彼此的备份的区域。这意味着放在一个区域的 Azure 资源自动获得通过配对区域的容错能力。因此，选择两个电子仓库其中区域是仅两个区域的可用性总共正在使用的配对的意味着 DEP 中使用的区域。多数地区仅具有两个区域，因此尚未可以选择非配对区域。如果可能，请选择用于部署的两个电子仓库的两个非配对地区这会受益总共四个区域的可用性。有关详细信息，请参阅[业务连续性和灾难恢复 (BCDR): Azure 配对区域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)区域对的当前列表。 
  
### <a name="assign-permissions-to-each-key-vault"></a>将权限分配给每个主要的存储库
<a name="KeyVaultPerms"> </a>

每个关键电子仓库，需要定义三个单独的客户键，具体取决于您的实现的权限集。例如，需要定义一组的每个以下权限：
  
- 将为您的组织中执行日常管理的关键存储库的**密钥仓库管理员**。这些任务包括备份、 创建、 获取、 导入列表，并还原。 
    
    > [!IMPORTANT]
    > 一组权限分配给键仓库管理员不包括删除项的权限。这是有意以及重要实践。删除加密密钥不通常，因为执行操作，以便永久性销毁数据。最佳做法是，不要授予此权限关键仓库管理员默认情况下。而是保留此键仓库参与者和仅理解的后果清楚地了解后将其分配给短期基础上的管理员。 
  
    若要将这些权限分配给您的 Office 365 组织中的用户，登录到您使用 Azure PowerShell 的 Azure 订阅。有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)。
    
- 运行设置 AzureRmKeyVaultAccessPolicy cmdlet 分配所需的权限。
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  例如：
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- 可以更改权限 Azure 键存储库本身的**密钥仓库参与者**。您需要更改这些权限，如员工离开或加入您的团队，或在极少的情况下，该密钥保险存储管理员合法需删除或还原项的权限。这套关键仓库参与者需要被授予您密钥的存储库上的**参与者**角色。您可以通过使用 Azure 资源管理器中分配此角色。详细步骤，请参阅[Use Role-Based 访问控制，来管理 Azure 订阅资源的访问权限](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)。创建订阅的管理员访问此隐式，以及其他管理员分配参与者角色的功能。
    
- 如果您打算使用 Exchange Online 和 Skype 客户键用于业务，您需要向 Office 365 for Business 使用代表 Exchange Online 和 Skype 的关键电子仓库授予权限。同样，如果您想要使用客户参数 SharePoint Online 和 OneDrive for Business，您需要为 Office 365 使用的关键电子仓库，代表 SharePoint Online 和 OneDrive for Business 添加权限。若要向 Office 365 授予权限，运行**设置 AzureRmKeyVaultAccessPolicy** cmdlet 使用以下语法： 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    其中：
    
  - *vaultname*是您创建的关键电子仓库的名称。 
    
  - 有关 Exchange Online 和 for Business 的 Skype，替换与*Office 365 appID*`00000002-0000-0ff1-ce00-000000000000`
    
  - 有关 SharePoint Online 和 OneDrive for Business，替换与*Office 365 appID*`00000003-0000-0ff1-ce00-000000000000`
    
  示例： 设置 Exchange Online 和 Skype for Business 的权限：
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  示例： 设置 SharePoint Online 和 OneDrive for Business 的权限
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>启用，然后确认软删除的主要存储库
<a name="SoftDelete"> </a>

当您可以快速恢复您的密钥时，您是不太可能会遇到意外或恶意删除的项由于扩展的服务中断。您需要启用此配置中，称为软删除之前可用于您的密钥客户参数。启用软删除允许您删除的 90 天内恢复键或电子仓库，而无需从备份中还原。
  
若要启用关键存储库上的软删除，完成以下步骤：
  
1. 登录到您使用 Windows Powershell 的 Azure 订阅。有关说明，请参阅[使用 Azure PowerShell 登录](https://docs.microsoft.com/powershell/azure/authenticate-azureps)。
    
2. 运行[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet。本示例中， *vaultname*是要为其启用软删除该密钥存储库的名称： 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. 确认软删除配置为关键仓库通过运行**Get AzureRmKeyVault** cmdlet。如果关键电子仓库，软删除的配置是否正确，然后软删除启用？属性返回值为**True**: 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>将项添加到每个关键电子仓库可以通过创建或导入密钥
<a name="AddKeystoKeyVault"> </a>

有两种方法将项添加到 Azure 键仓库;您可以直接在项存储库中创建项或可以导入一个键。直接在项存储库中创建项时的复杂程度低方法，导入密钥提供总控制如何生成密钥。
  
直接在您密钥的存储库中创建一个密钥，请运行[添加 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet，如下所示： 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

其中：
  
-  *vaultname*是您要在其中创建项关键存储库的名称。 
    
-  *键名*是要为新的密钥的名称。 
    
    > [!TIP]
    > 使用类似的命名约定，如上述关键电子仓库名称键。这种方式，在显示仅键名的工具，该字符串自我描述。 
  
- 如果您打算使用 HSM 保护密钥，确保，否则，为_目标_参数的值指定**HSM**指定**软件**。
    
例如，
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

直接在您密钥的存储库导入密钥，您需要具有 Thales nShield 硬件安全模块。
  
某些组织希望此方法建立的其键，并且此 provenance 方法还提供以下各项：
  
- 用于导入工具集包括从 Thales 用于加密的密钥，生成密钥 Exchange 键 (KEK) 不是可导出的审计和内已由 Thales 生产正版 HSM 生成。
    
- 工具集包括从 Thales 上由 Thales 生产正版 HSM 还生成 Azure 键仓库安全领域的审计。此审计向您证明 Microsoft 也使用正版 Thales 硬件。
    
请与您的安全组，以确定是否需要进行上述 attestations。若要创建键，在部署并将其导入您的主要存储库的详细步骤，请参阅[如何生成和传输 Azure 键电子仓库 HSM 保护密钥](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)。使用 Azure 说明在每个主要的存储库中创建一个键。
  
### <a name="check-the-recovery-level-of-your-keys"></a>检查您的密钥的恢复级别
<a name="CheckKeyRecoveryLevel"> </a>

Office 365 需要 Azure 键存储库订阅被设置为不取消和所使用的客户参数项已启用的软删除。您可以通过查看您的密钥上恢复级别进行确认。
  
若要检查恢复级别的某个键，在 Azure PowerShell 中，运行 Get AzureKeyVaultKey cmdlet，如下所示：
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

如果_恢复级别_属性返回的值为**恢复 + ProtectedSubscription**之外的任何内容，您将需要查看以下主题，并确保您已按照所有订阅置于不取消列表的步骤和是否已在每个关键存储库上启用的软删除。
  
### <a name="backup-azure-key-vault"></a>备份 Azure 存储库
<a name="BackupAzureKeyVaultkeys"> </a>

紧跟创建或任何更改到某个键，执行备份，并将存储的联机和脱机的备份副本。脱机副本应不连接到任何网络，如在物理安全或商业存储设备上。应将在发生灾难时可访问的位置中存储的备份的至少一个副本。备份 blob 应键仓库键永久性销毁或否则呈现一直还原密钥材料的唯一方法。键的外部到 Azure 键仓库和已导入到 Azure 键仓库未限定为备份由于客户参数使用密钥所需的元数据不存在具有外部键。仅备份 Azure 键存储库中可具有客户键用于还原操作。因此，很重要的 Azure 键仓库备份进行后上载或创建密钥。
  
若要创建的 Azure 键仓库密钥备份，请运行[备份 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet，如下所示：
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

确保您的输出文件使用后缀`.backup`。
  
此 cmdlet 生成的输出文件进行加密和不能使用 Azure 键仓库之外。可以仅与 Azure 订阅从中备份中还原备份。
  
> [!TIP]
> 对于输出文件中，选择您的电子仓库名称和键名的组合。这将使文件名称自我描述。它还可以确保备份文件名称不执行发生冲突。 
  
例如：
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>验证 Azure 键仓库配置设置
<a name="Validateconfiguration"> </a>

执行在 DEP 中使用键之前验证是可选的但强烈建议您部署。特别是，如果您使用步骤设置键和电子仓库本主题中描述的之外，您应验证 Azure 键仓库资源的运行状况之前配置客户参数。
  
若要验证您的密钥已启用的 get wrapKey，以及 unwrapKey 操作：
  
运行[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet，如下所示： 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

在输出中，根据需要查找访问策略和 Exchange Online 的标识 (GUID) 或 SharePoint Online 的标识 (GUID)。向键，必须在权限下显示所有这三个以上的权限。
  
如果访问策略配置不正确，请运行设置 AzureRmKeyVaultAccessPolicy cmdlet，如下所示：
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

例如，对于 Exchange Online 和 Skype for Business:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

例如，对于 SharePoint Online 和 OneDrive for Business:
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

若要验证您运行[Get AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet，如下所示的密钥的未设置到期日期： 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

过期的项不能由客户参数并尝试与过期键的操作将失败，并可能导致服务中断。我们强烈建议键用于客户参数没有到期日期。到期日期后设置，无法删除，但可以更改到不同的日期。如果必须使用密钥已设置的过期日期，更改为 12/31/9999 到期值。到期日期设置为日期以外 12/31/9999 将不能通过 Office 365 验证键。
  
若要更改已设置为 12/31/9999 之外的任何值的到期日期，请运行[设置 AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet，如下所示： 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 不能在与客户参数一起使用的加密密钥设置到期日期。 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>获取每个 Azure 键仓库键的 URI
<a name="GetKeyURI"> </a>

一旦您具有完成 Azure 设置键存储库中的所有步骤，并添加您的密钥，运行以下命令以获取 URI 的每个主要的存储库中的键。您将需要使用以下 Uri 时创建并分配每个 DEP 更高版本，因此将此信息保存在安全的地方。记住要运行此命令一次的每个主要的存储库。
  
在 Azure PowerShell 中：
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365： 为 Exchange Online 和 Skype for Business 设置客户参数
<a name="AzureSteps"> </a>

在开始之前，确保您已完成的任务，需要设置 Azure 键存储库。信息，请参阅[在 Azure 键仓库和客户键的 Microsoft FastTrack 完成任务](controlling-your-data-using-customer-key.md#AzureSteps)。 
  
若要为 Exchange Online 和 Skype for Business 设置客户参数，您需要通过远程连接到 Exchange Online 使用 Windows PowerShell 执行这些步骤。
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>创建用于 Exchange Online 和 Skype 的业务数据加密策略 (DEP)
<a name="CreateDEP4EXOSkype"> </a>

DEP 是与 Azure 键存储库中存储的键集相关联。Office 365 中的邮箱中分配 DEP。Office 365 将使用该策略中标识的键进行加密邮箱。若要创建 DEP，您需要之前获得的密钥仓库 Uri。有关说明，请参阅[获取每个 Azure 键仓库键的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。 
  
请记住 ！创建 DEP 时，您可以指定驻留在两个不同的 Azure 键电子仓库的两个键。确保这些注册表项位于两个单独的 Azure 区域以确保地理位置冗余。
  
若要创建 DEP，请按照下列步骤：
  
1. 在本地计算机上使用工作或学校帐户已[连接到 Exchange Online PowerShell 中](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)打开 Windows PowerShell 并运行以下命令在 Office 365 组织中的全局管理员权限。 
    
   ```
   $UserCredential = Get-Credential
   ```

2. Windows PowerShell 凭据请求对话框中，输入您的工作或学校帐户信息，再单击**确定**，，然后输入以下命令。 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. 运行以下命令。
    
   ```
   Import-PSSession $Session
   ```

4. 若要创建 DEP，通过键入以下命令使用新建 DataEncryptionPolicy cmdlet。
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   其中：
    
   -  *PolicyName*是想要使用的策略的名称。名称不能包含空格。例如，USA_mailboxes。 
    
   -  *使用 PolicyDescription*是策略的将有助于您记住策略的用途的用户友好说明。在说明，可以包含空格。例如，根 USA 和其区域中的邮箱的键。 
    
   -  *KeyVaultURI1*是策略中的第一个键的 URI。例如， https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。 
    
   -  *KeyVaultURI2*是策略中的第二个键的 URI。例如， https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。分隔逗号和空格的两个 Uri。 
    
   示例：
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a>分配邮箱的 DEP
<a name="assignDEPtomailbox"> </a>

使用 Set-mailbox cmdlet 分配邮箱 DEP。Office 365 后分配策略时，可以使用部署中指定密钥加密邮箱
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

其中*MailboxIdParameter*指定邮箱。有关 Set-mailbox cmdlet 的详细信息，请参阅[Set-mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)。
  
### <a name="validate-mailbox-encryption"></a>验证邮箱加密
<a name="validatemailboxencryption"> </a>

加密邮箱可能需要一些时间。第一个时间策略分配，邮箱也必须完成移动到另一个数据库中的，该服务可以加密邮箱之前。我们建议您等待 72 小时尝试后更改 DEP 或第一次您对邮箱分配 DEP 验证加密之前。
  
使用 Get-mailboxstatistics cmdlet 可确定是否加密邮箱。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

如果该邮箱未加密，进行加密属性返回值为**true**如果加密邮箱和值为**false** 。 

若要完成邮箱移动的时间取决于为邮箱的大小或向其分配的第一次，DEP 的邮箱数。如果邮箱已经不加密指派 DEP 的时间从每周后，使用 New-moverequest cmdlet 启动的未加密的邮箱的邮箱移动。

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a>Office 365： 为 SharePoint Online 和 OneDrive for Business 设置客户参数
<a name="AzureSteps"> </a>

在开始之前，确保您已完成的任务，需要设置 Azure 键存储库。信息，请参阅[在 Azure 键仓库和客户键的 Microsoft FastTrack 完成任务](controlling-your-data-using-customer-key.md#AzureSteps)。 
  
若要为 SharePoint Online 和 OneDrive for Business 设置客户参数，您需要通过远程连接到 SharePoint Online 使用 Windows PowerShell 执行这些步骤。
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>为业务地理位置的每个 SharePoint Online 和 OneDrive 创建数据加密策略 (DEP)
<a name="CreateDEP4SPOODfB"> </a>

DEP 是与 Azure 键存储库中存储的键集相关联。您将 DEP 应用于所有在一个地理位置，也称为地理位置数据。如果您使用 Office 365 的多地理位置功能 （当前在预览） 时，您可以创建一个 DEP 每地理位置。如果您没有使用多地理位置，可以使用 SharePoint Online 和 OneDrive for Business 的用于 Office 365 中创建一个 DEP。Office 365 将使用 DEP 中标识的项中的地理位置数据进行加密。若要创建 DEP，您需要之前获得的密钥仓库 Uri。有关说明，请参阅[获取每个 Azure 键仓库键的 URI](controlling-your-data-using-customer-key.md#GetKeyURI) 。 
  
请记住 ！创建 DEP 时，您可以指定驻留在两个不同的 Azure 键电子仓库的两个键。确保这些注册表项位于两个单独的 Azure 区域以确保地理位置冗余。
  
若要创建 DEP，您需要远程使用 Windows PowerShell 连接到 SharePoint Online。
  
1. 在本地计算机上使用工作或学校帐户已[连接到 SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx)在 Office 365 组织中的全局管理员权限。
    
2. Microsoft SharePoint Online Management Shell 中，运行[注册 SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet，如下所示： 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   注册 DEP 时，加密在其上开始地理位置中的数据。这可能需要一些时间。
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a>验证组网站、 工作组网站和 OneDrive for Business 的加密
<a name="validateencryptionSPO"> </a>

您可以通过运行 Get SPODataEncryptionPolicy cmdlet，如下所示检查加密的状态：
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

此 cmdlet 的输出包括：
  
- 主键的 URI。
    
- 第二项的 URI。
    
- Geo 加密状态。状态可能包括：
    
  - **未注册：** 尚未应用客户密钥加密。 
    
  - **注册：** 已应用客户密钥加密和文件正在进行加密。如果您地理处于此状态，您将还上会显示信息的地理位置中的网站百分比已完成，以便您可以监视加密进度。 
    
  - **注册：** 已应用客户密钥加密，且已加密的所有网站中的所有文件。 
    
  - **推出：** 关键滚正在进行。如果您地理处于此状态，您将还上会显示信息站点的比例完成关键滚动操作，以便您可以监视进度。 
    
## <a name="managing-customer-key-for-office-365"></a>管理 Office 365 的客户密钥
<a name="ManageCustomerKey"> </a>

已设置 Office 365 客户参数后，您可以执行这些额外的管理任务。
  
- [还原 Azure 键仓库键](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [回滚或旋转中与客户参数一起使用的 Azure 键仓库的键](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [管理密钥的存储库的权限](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [确定分配给某个邮箱 DEP](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a>还原 Azure 键仓库键
<a name="RestoreAzureKeyVaultKeys"> </a>

在执行还原之前, 使用软删除由提供的恢复功能。与客户参数一起使用的所有项都是必需已启用的软删除。软删除相当于回收站中，通过达 90 天内无需还原恢复。只应在极端或特殊情况下，例如，丢失的键或键的存储库时所需还原。如果您必须使用客户密钥还原密钥，以用于在 Azure PowerShell 中，运行还原 AzureKeyVaultKey cmdlet，如下所示：
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

例如：
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

如果键存储库中已存在同名的键，还原操作将失败。还原 AzureKeyVaultKey 还原所有的主要版本和所有元数据，包括键名键。
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a>回滚或旋转中与客户参数一起使用的 Azure 键仓库的键
<a name="RollCKkey"> </a>

回滚键则不需要按任一 Azure 键仓库或客户键。此外，シ シ 术 シ HSM 的项是几乎可能破坏。即使根密钥已拥有的恶意 actor 没有可行使用它来解密数据，因为仅 Office 365 代码知道如何使用它的方法。但是，推出键都支持客户参数。
  
> [!CAUTION]
> 仅将鼠标移存在清除技术原因或合规性要求指示已进行回滚键时，与客户参数使用加密密钥。此外，不要删除任何键或与其关联的策略。如果将您的键，将提供内容加密与以前的密钥。例如，活动邮箱都将被重新加密频繁，处于非活动状态，而断开连接，并禁用邮箱可能仍加密与以前的密钥。SharePoint Online 执行备份的内容的还原和恢复目的，因此可能仍使用原来的密钥的存档的内容。<br/> 若要确保您的数据的安全，SharePoint Online： 将允许不多个键滚动操作，正在进行的一次。如果您想要在密钥的存储库中的滚动这两个注册表项，您需要等待到第一个关键滚动操作完全完成。我们建议是在不同的时间间隔，错开关键滚动操作，以便不是问题。 
  
如果将某个键，您正在请求现有密钥的新版本。以请求现有密钥的新版本，请使用相同，[添加 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)，带有 cmdlet 相同的语法用于首先创建项。
  
例如：
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

本示例中，因为一个名为**Contoso-O365EX-NA-VaultA1-Key001**已项存在**Contoso O365EX NA VaultA1**存储库中的将创建一个新的主要版本。操作中添加一个新的主要版本。此操作，以便仍然可以解密之前使用该密钥加密的数据保留中的项的版本历史记录的早期主要版本。完成推出相关联 DEP 任意键后，您必须运行其他 cmdlet，以确保客户参数开始使用新密钥。 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>启用 Exchange Online 和 for Business 的 Skype 以使用新密钥后滚动或旋转 Azure 键存储库中的项

当您滚动任一 DEP 与关联的 Azure 键仓库键与 Exchange Online 和 Skype 用于业务，必须运行以下命令以更新 DEP 和启用 Office 365 开始使用新的密钥。
  
若要指示客户参数使用新密钥来加密 Office 365 中的邮箱运行设置 DataEncryptionPolicy cmdlet，如下所示：
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

48 小时内使用此策略加密的活动邮箱将成为与更新键关联。使用[Determine DEP 分配给某个邮箱](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)中的步骤检查邮箱的 DataEncryptionPolicyID 属性的值。在应用更新的密钥后，将更改此属性的值。 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a>启用 SharePoint Online 和 OneDrive for Business 使用新密钥后滚动或旋转 Azure 键存储库中的项

当您滚动任一 DEP 与关联的 Azure 键仓库键用于 SharePoint Online 和 OneDrive for Business，您必须运行[更新 SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet 以更新 DEP 和启用 Office 365 开始使用新密钥。 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

这将启动 SharePoint Online 和 OneDrive for Business 的关键回滚操作。此操作不会立即。若要查看的密钥滚动操作的进度，请运行 Get SPODataEncryptionPolicy cmdlet，如下所示：
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a>管理密钥的存储库的权限
<a name="Managekeyvaultperms"> </a>

有多个 cmdlet，可以查看和，如有必要，删除键仓库权限。您可能需要删除权限，例如，当员工离开团队。
  
若要查看关键仓库权限，请运行 Get AzureRmKeyVault cmdlet:
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

例如：
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

若要删除的管理员权限，请运行删除 AzureRmKeyVaultAccessPolicy cmdlet:
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

例如：
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>确定分配给某个邮箱 DEP
<a name="DeterminemailboxDEP"> </a>

若要确定 DEP 分配给某个邮箱，请使用 Get-mailboxstatistics cmdlet。此 cmdlet 返回的唯一标识符 (GUID)。
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

其中*GeneralMailboxOrMailUserIdParameter*指定邮箱。有关 Get-mailboxstatistics cmdlet 的详细信息，请参阅[Get-mailboxstatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)。
  
使用 GUID 以找出通过运行以下 cmdlet，邮箱分配到 DEP 的友好名称。
  
```
Get-DataEncryptionPolicy <GUID>
```

其中*GUID*是使用 Get-mailboxstatistics cmdlet 在上一步返回的 GUID。 
  


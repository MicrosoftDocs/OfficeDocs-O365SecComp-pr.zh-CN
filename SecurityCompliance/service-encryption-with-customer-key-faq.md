---
title: 有关使用 Office 365 客户密钥执行服务加密的 FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: 除了基线，通过 BitLocker 和分布式密钥管理器 (DKM) 启用的音量级别加密 Office 365 提供加密的 Office 365，包括从交换的数据中的客户内容应用程序级别添加的层联机，业务、 SharePoint Online，和 OneDrive for Business 的 Skype。这称为服务加密。
ms.openlocfilehash: ceba35233872bb65b7706ed4e11a263057adc6c1
ms.sourcegitcommit: 659b5f5b38ef7e838cdb44eaa38c18e48d922768
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "25575326"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>有关使用 Office 365 客户密钥执行服务加密的 FAQ

除了基线，通过 BitLocker 和分布式密钥管理器 (DKM) 启用的音量级别加密 Office 365 提供加密的 Office 365，包括从交换的数据中的客户内容应用程序级别添加的层联机，业务、 SharePoint Online，和 OneDrive for Business 的 Skype。这称为服务加密。
  
客户参数基于服务加密，并使您可以提供和控制键用于加密在 Office 365 中的 rest 数据[联机服务条款 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)中所述。客户参数可帮助您满足合规性要求，因为您控制 Office 365 使用的数据进行解密的加密密钥。
  
若要提供反馈客户项，包括文档，请向 customerkeyfeedback@microsoft.com 发送您的想法、 建议和角度。
  
## <a name="what-is-service-encryption-with-customer-key"></a>与客户参数服务加密是什么？

客户参数增强您的组织能够满足合规性要求指定排列云服务提供商的关键功能的要求。与客户参数提供，并为您 Office 365 存放的数据应用程序级别控制加密密钥。因此，您可能进行控制和撤消贵组织的键，您应确定退出服务。由撤消注册表项，数据不可读到服务。密钥吊销是数据删除达到路径上的第一步。

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>由客户参数覆盖静态哪些 Office 365 数据？
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

介绍了 SharePoint Online 网站内容和存储在该网站上的文件上载到 OneDrive for Business 的文件。介绍 Exchange Online 邮箱内容 （电子邮件正文、 日历项和电子邮件附件的内容）。介绍从 for Business 的 Skype 文本对话的但不是介绍 Skype 会议广播录制和 Skype 会议内容上载。Skype 会议广播和 Skype 会议内容上载与 Office 365 中的所有其他内容一起加密，但我们当前不提供客户控件的加密密钥。
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>客户密钥与使您自己键 (BYOK) 与 Azure 信息 Protection for Exchange Online 之间的区别是什么？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

这两个选项使您能够提供和控制您自己的加密密钥;但是，服务加密客户参数与数据进行加密您在 rest、 驻留在 Office 365 服务器静止，与 Azure 信息 Protection for Exchange Online BYOK 加密在传输数据和提供持久联机和脱机时为电子邮件和附件以供 Office 365 的保护。客户参数和 BYOK 与 Azure 信息 Protection for Exchange Online 补充，并且在是否您选择使用 Microsoft 的服务托管键或自己键，加密您的数据在 rest 和传输过程中可以提供添加了的保护恶意攻击。
  
BYOK 与 Azure 信息 Protection for Exchange Online 的 Office 365 邮件加密功能中提供。
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>Office 365 邮件加密并使您自己的密钥与 Azure 信息保护更改 Microsoft 的方法为第三方数据请求，例如传讯？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

不。Office 365 邮件加密和选项，以提供并控制您自己的加密密钥与使您自己键 (BYOK) Azure 信息保护 (AIP) 不旨在法律强制实施传讯响应。Office 365 邮件加密的 AIP BYOK 与设计的合规性中心客户需要满足其内部或外部的合规性义务。Microsoft 非常严重采用第三方客户数据请求。为云服务提供程序，我们始终提倡隐私的客户数据。在事件我们获得传唤，我们始终尝试将第三方重定向客户以获取信息。(请阅读 Brad Smith 的博客：[从政府窥探 Protecting 客户数据](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。我们定期发布我们收到的请求的详细的信息[此处](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)。
  
请参阅有关第三方数据请求[Microsoft 信任中心](https://www.microsoft.com/en-us/trustcenter/default.aspx)和"泄露的客户数据"的详细信息的[联机服务条款 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)文件中。
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>与客户参数服务加密更改 Microsoft 的方法第三方数据请求，例如传讯？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

不。不旨在响应法律强制实施传讯客户参数。其设计的监管客户以满足其内部或外部的合规性义务。Microsoft 非常严重采用第三方客户数据请求。为云服务提供程序，我们始终提倡隐私的客户数据。在事件我们获得传唤，我们始终尝试将第三方重定向客户以获取信息。(请阅读 Brad Smith 的博客：[从政府窥探 Protecting 客户数据](http://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。我们定期发布我们收到的请求的详细的信息[此处](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)。
  
请参阅有关第三方数据请求[Microsoft 信任中心](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)和"泄露的客户数据"的详细信息的[联机服务条款 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)文件中。 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>是 FastTrack 支持可用于实现客户参数？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

不。FastTrack 仅用于收集租户和服务所需客户项注册的配置信息。客户键提供发布通过 FastTrack 以便并且可以很方便客户和合作伙伴进行提交此所需的信息，使用相同的方法和简化的存档中提供的客户提供的数据。
  
如果您需要其他支持文档之外，与 Microsoft 咨询服务 (MCS)、 高级字段工程 (PFE) 或 Microsoft 合作伙伴联系以获取帮助。
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>如果我键被破坏，如何恢复？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性键为您提供了从您管理的根键无法预知丢失恢复的功能。如果您丢失根键，联系 Microsoft 支持并 Microsoft 将帮助您通过启用可用性密钥的过程。您将使用的可用性密钥与新的密钥设置您将迁移到新的数据加密策略。 
  
## <a name="what-is-the-availability-key"></a>可用性关键是什么？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性该键创建数据加密策略时设置根键。存储和受保护的 Office 365 中的可用性密钥和功能上类似于均附带您用于服务加密客户参数的两个根键。与您提供和管理 Azure 键存储库中的项，您无法直接访问可用性键。存储和可用性项的控件是有意不同 Azure 键仓库键的三个原因： 首先，可用性键提供高可用性功能中的 Office 365 服务都无法访问承载在 Azure 键的项存储库;其次，可用性键提供"中断玻璃"功能的这两个 Azure 键仓库键都将丢失;和第三的逻辑控件分离提供了纵深防御--防止单个攻击中的所有项丢失或故障点。共享保护键，同时使用各种保护和流程的密钥管理责任最终降低了风险，将丢失或损坏所有键 （和您的数据）。通过可用性键销毁中，Microsoft 为您提供唯一的证书颁发机构。按照设计，microsoft 没有人有权访问可用性密钥-仅可访问 Office 365 服务代码。
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>可以创建多少数据加密策略 (DEPs)？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for Business:** 您可以创建最多 50 DEPs。 
  
 **SharePoint Online 和 OneDrive for Business:** DEP 适用于在一个地理位置，也称为地理位置的数据。如果您使用 Office 365 的多地理位置功能，您可以创建一个 DEP 每地理位置。如果您没有使用多地理位置，您可以创建一个 dep。
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>可以将邮箱迁移到云中之前分配数据加密策略？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

是的。您可以使用 Windows PowerShell cmdlet Set-mailuser 分配数据加密策略 (DEP) 之前迁移到 Office 365 的邮箱用户。执行此操作时，将内容迁移使用分配给的 DEP 加密邮箱的内容。这可以是已迁移的邮箱后分配 DEP，然后等待加密才能开始，它可以几天需要数小时或可能比更有效。 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>如何验证与客户密钥加密激活和 Office 365 已完成使用客户密钥加密？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for Business:** 您可以[连接到 Exchange Online 使用远程 PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) ，然后使用 **[Get-mailboxstatistics]** cmdlet，您想要检查的每个邮箱。在从 Get-mailboxstatistics cmdlet 输出中，_进行加密_属性返回值为**true**如果加密邮箱和值为**false**则。如果该邮箱进行加密， _DataEncryptionPolicyID_属性返回的值是用于加密邮箱 DEP 的 GUID。运行此 cmdlet 的详细信息，请参阅[Get-mailboxstatistics](https://technet.microsoft.com/en-us/library/bb124612%28v=exchg.160%29.aspx)和使用 PowerShell 和 Exchange Online。 
  
如果邮箱不加密等待 72 小时数从指派 DEP 的时间后，启动的邮箱移动。若要执行此操作，[连接到 Exchange Online 使用远程 PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)然后使用 New-moverequest cmdlet 并提供邮箱的别名，如下所示： 
  
```
New-MoveRequest <alias>
```

 **SharePoint Online 和 OneDrive for Business:** 您可以[连接到 SharePoint Online PowerShell 中](https://technet.microsoft.com/en-us/library/fp161372.aspx)，然后使用 **[Get SPODataEncryptionPolicy]** cmdlet 检查您的租户的状态。* *_状态_* * 属性返回的**注册**一个值，如果启用客户密钥加密和已加密的所有网站中的所有文件。如果仍在进行加密，此 cmdlet 将提供有关站点的比例已完成的信息。 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>如果我想要切换到一组不同的键，如何长的一组新的键来保护我的数据？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for Business:** 可能需要 72 小时从新 DEP 指派给邮箱的时间保护邮箱根据新数据加密策略 (DEP)。 
  
 **SharePoint Online 和 OneDrive for Business:** 可能需要四个小时后已分配新密钥重新加密您的整个租户。 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>我现有数据存储不在任何时候加密解密或使用客户密钥加密时？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

不。在 DKM BitLocker 与 Office 365 服务中的 rest 始终加密数据。有关详细信息，请参阅"安全、 隐私和 Office 365 的合规性信息"，并[如何 Exchange Online 保护您的电子邮件机密](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376)。
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>如果我不再想要使用的客户管理加密密钥，可以切换到 Microsoft 托管密钥？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for Business:** 还没有。Office 365 中使用 Microsoft 托管密钥的服务加密广泛推出后将支持此。我们希望推出这服务中后，我们使用客户密钥发布服务加密。 
  
 **SharePoint Online 和 OneDrive for Business:** 是的。您可以选择要恢复到使用 Microsoft 托管密钥单独为每个地理位置 （如果您使用多地理位置功能） 或所有数据是否单个地理位置。 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>如果我丢失了我密钥，如何长时间来恢复使用恢复密钥的服务可用性？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for Business:** 一旦您呼叫中使用的可用性密钥，请分钟内将可以访问邮箱。 
  
 **SharePoint Online 和 OneDrive for Business:** 此操作是与您具有的网站数成比例。后调用 Microsoft 使用可用性密钥，您将处于完全联机状态大约四个小时内。 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>如何与 Exchange Online 一起使用的可用性密钥？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

有三种方法可用性密钥用于与 Exchange Online:
  
- Azure 键仓库键都无法访问的情况下服务可用性 —。
    
- 操作启动 Office 365 服务代码-例如，搜索索引创建或邮箱移动。
    
- 恢复关键丢失-例如丢失与单个部署关联的两个 Azure 键仓库键
    
 **在事件 Azure 键仓库键都无法访问，请使用可用性密钥的服务可用性。**
  
Office 365 的 Exchange Online 使用可用性密钥对服务可用性和恢复从不正常的客户参数状态。没有使用客户键的项的层次结构。下图说明了此层次结构。
  
![](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
Office 365 不可用这两个 Azure 键仓库键的单个数据加密策略 (DEP) 时，可以使用的可用性密钥更改为新的部署 Office 365 确定是否使用可用性键，具体取决于不同的服务可用性用户启动的活动，例如，当用户将电子邮件下载到 Outlook 客户端或系统启动活动，如索引邮箱内容，或电子数据展示搜索时触发过程。
  
Office 365 遵循此过程以响应用户启动操作来确定是否对用户邮箱中使用的可用性密钥：
  
1. Office 365 读取 DEP 为其邮箱分配来确定 Azure 键存储库中的两个客户键的位置。
    
2. Office 365 随机选择两个客户键之一从 DEP，并将请求发送到 Azure 键仓库解包使用客户参数的 DEP 键。
    
3. 如果请求解包 DEP 主要使用客户参数失败并返回错误，已将第二个请求 Office 365 发送到 Azure 键仓库，指示它使用备用此时间 （秒） 客户参数。
    
4. 如果第二个请求解包使用客户关键失败的 DEP 键，并将返回错误，Office 365 将检查这两个请求的结果：
    
  - 如果检查确定错误不客户 identity 反映明确的操作，Office 365 将使用可用性密钥 DEP 密钥进行解密。然后使用 DEP 该键解密邮箱密钥并完成用户请求。
    
    在这种情况下，Azure 键存储库是无法响应或无法访问出于任何原因。Office 365 具有无法确定是否客户有意已吊销访问密钥。
    
  - 如果检查指示已执行该谨慎操作呈现客户键不可用，然后将不会使用可用性键用户请求失败，和用户会收到一条错误消息，如登录故障。
    
    这种情况下，客户由请注意，服务会受到影响，，客户参数的条件不正常。例如，如果客户组织中所有邮箱使用单一 DEP，客户可能会遇到普遍存在失败其中用户无法访问其邮箱。这样可确保正常两个客户密钥后，客户才可了解需要进行更正这种情况，并将服务还原到正常运行状态。
    
 **使用 Office 365 服务代码触发动作可用性密钥。**
  
Office 365 服务代码始终有一个有效登录令牌，并不能被阻止。因此，直到可用性密钥已被删除，它可用于启动，或者为，Office 365 服务代码，如搜索索引创建内部或移动的邮箱的操作。
  
 **使用可用性键恢复关键丢失。**
  
可用性密钥可用于恢复丢失的两个 Azure 键仓库密钥与关联的相同 DEP，如下所述的答案常见问题条目中"当我的密钥破坏时，如何恢复？"。
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>如何为可用性使用密钥与 SharePoint Online 和 OneDrive for Business？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

SharePoint Online 的 OneDrive for Business 体系结构和实施客户参数和可用性的键具有不同和 Exchange Online 和 Skype for Business 中。
  
当客户移动到客户托管密钥时，Office 365 创建特定于租户的中间键 (TIK)。Office 365 加密 TIK 两次，一次使用每个客户键，并将存储 TIK 加密的两个版本。存储仅 TIK 加密的版本，并只能与客户键解密 TIK。TIK 然后用于加密站点密钥，然后用于加密 blob 键。有自己的 blob 加密和存储在 Microsoft Azure Blob 存储服务。
  
Office 365 遵循此过程来访问已客户文件数据的 blob:
  
1. 解密 TIK 使用客户参数。
    
2. 解密的 TIK 用于解密网站密钥。
    
3. 使用解密的网站键解密 blob 密钥。
    
4. 使用解密的 blob 键解密 blob。
    
时解密 TIK，Office 365 问题两个解密请求到 Azure 键仓库微小的偏移量。若要完成的第一个提供结果，取消其他请求。
  
以防客户无法访问其客户键，Office 365 还使用可用性密钥加密 TIK 该文件，并将此存储以及与每个客户密钥加密 TIKs。使用可用性密钥加密 TIK 客户呼叫 Microsoft 时他们无法再访问其密钥，恶意或意外登记恢复路径时，仅使用。
  
出于可用性及刻度考虑，解密的 TIKs 缓存时间限制内存缓存中。两个小时才能 TIK 缓存设置为过期，Office 365 尝试解密每个 TIK。解密 TIKs 扩展缓存的生存期。如果 TIK 解密失败很长时间，Office 365 生成警报通知工程之前缓存到期时间。仅当客户调用 Microsoft Office 365 将启动恢复操作，这会涉及解密与可用性键 TIK 存储在 Microsoft 的机密存储和入职培训再次使用解密租户 TIK 和一组新的客户提供 Azure 键仓库键。
  
从现在起，客户参数所涉及的 SharePoint Online 中的 Azure blob 存储，但不是 SharePoint Online 的列表项或元数据存储在 SQL 数据库中存储的文件数据加密和解密链中。Office 365 不使用可用性或的项 SharePoint Online 的 OneDrive for Business 之外这种情况，上述，即客户启动。客户密码箱受 human 访问客户数据。
  
## <a name="how-is-customer-key-licensed"></a>如何获取客户密钥的许可证？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

客户参数是 Office 365 企业套件、"E5"和高级合规性 SKU 中提供的。此外，客户还必须购买使用 Azure 键仓库适当的许可证。
  
受益于客户参数每个用户需要如果他们想要覆盖由客户参数可获得许可。
  
SharePoint online，配置客户参数的 Office 365 管理员还需要可获得许可，以执行安装步骤。此外，受益于功能的用户需要被许可-这包括网站所有者和访问文件使用客户参数进行加密的一个或多个网站上任何用户。外部用户不需要被许可使用客户参数进行加密的一个或多个网站上访问文件。
  
有关 Exchange Online 中，必须许可"user"邮箱和邮箱"邮件用户"。所有其他成员，如共享邮箱不需要具有许可证的客户参数。若要检查正确许可 Exchange Online 邮箱，请运行以下 cmdlet:
  
```
(Get-Mailbox <alias >).PersistedCapabilities
```

如果存在字符串 BPOS_S_EquivioAnalytics，是正确许可邮箱。如果没有，您必须以用于此邮箱的客户参数功能应用适当的许可。
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>可以启用试用订阅客户参数？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

不。根据定义，试用版订阅具有有限的生存期。试用生存期的末尾，位于试用版订阅的加密密钥可能会丢失。因为 Microsoft 不能并且不会阻止客户将重要的客户数据放入试用版订阅，禁止客户键用于试用版订阅。
  
## <a name="how-much-will-using-customer-key-cost"></a>多少将使用客户参数成本？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

除了所需的客户参数许可，客户将会引发键存储库使用成本。[Azure 键仓库定价的详细信息](https://azure.microsoft.com/en-us/pricing/details/key-vault/)描述成本模型，并将帮助估计。没有方法来预测由于使用模式不同，将会引发任何客户的确切成本。经验表明成本很低，并且通常范围内的 $0.002 到 $0.005 每用户每月的范围以及 HSM 备份项的成本。成本将也不尽客户和用于 Azure 键仓库日志的 Azure 存储量由选择的日志记录配置。 
  
## <a name="for-more-information"></a>详细信息
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

若要开始与客户参数，请参阅[控制您使用客户密钥的 Office 365 中的数据](controlling-your-data-using-customer-key.md)。
  


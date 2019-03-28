---
title: 有关使用 Office 365 客户密钥执行服务加密的 FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 41ae293a-bd5c-4083-acd8-e1a2b4329da6
description: 除了通过 BitLocker 和分布式密钥管理器 (DKM) 启用的对卷级别加密之外, office 365 还在应用程序级别为 office 365 中的客户内容 (包括来自 Exchange 的数据) 提供了额外的加密层Online、Skype for business、SharePoint Online 和 OneDrive for business。 这称为 "服务加密"。
ms.openlocfilehash: 5e1acca69ccdd8acb986acb4d7a302d4ca3fbe8a
ms.sourcegitcommit: 8a65a29aa3bfe5dcad0ff152a7cd795e02877dd9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2019
ms.locfileid: "30936762"
---
# <a name="service-encryption-with-customer-key-for-office-365-faq"></a>有关使用 Office 365 客户密钥执行服务加密的 FAQ

除了通过 BitLocker 和分布式密钥管理器 (DKM) 启用的对卷级别加密之外, office 365 还在应用程序级别为 office 365 中的客户内容 (包括来自 Exchange 的数据) 提供了额外的加密层Online、Skype for business、SharePoint Online 和 OneDrive for business。 这称为 "服务加密"。
  
客户密钥是基于服务加密构建的, 使您能够提供和控制用于在 Office 365 中对静态数据进行加密的密钥, 如[联机服务条款 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)中所述。 客户密钥可帮助您满足合规性义务, 因为您控制 Office 365 用于解密数据的加密密钥。
  
若要提供有关客户密钥的反馈 (包括文档), 请将你的想法、建议和观点发送到 customerkeyfeedback@microsoft.com。
  
## <a name="what-is-service-encryption-with-customer-key"></a>使用客户密钥的服务加密是什么？

客户密钥增强了贵组织满足符合性要求的能力, 这些要求通过云服务提供商指定关键安排。 使用 "客户密钥", 可以在应用程序级别为 Office 365 数据提供和控制加密密钥。 因此, 如果决定退出服务, 您可以控制和撤消您的组织的密钥。 通过吊销密钥, 该服务无法读取数据。 密钥吊销是删除数据的路径中的第一步。

## <a name="what-office-365-data-at-rest-is-covered-by-customer-key"></a>客户密钥涵盖什么是 rest 的 Office 365 数据？
<a name="WhatDataIsCoveredbyCustomerKey"> </a>

其中介绍了 SharePoint Online 网站内容以及存储在该网站上的文件以及上传到 OneDrive for business 的文件。 包含 Exchange Online 邮箱内容 (电子邮件正文、日历条目和电子邮件附件的内容)。 已覆盖 skype for business 中的文本对话, 但不包括 skype 会议广播录制和 skype 会议内容上载。 skype 会议直播和 skype 会议内容上载与 Office 365 中的其他所有内容一起进行加密, 但我们目前不提供对加密密钥的客户控制。
  
## <a name="what-is-the-difference-between-customer-key-and-bring-your-own-key-byok-with-azure-information-protection-for-exchange-online"></a>客户密钥与使用 Exchange Online 的 Azure 信息保护为你自己的密钥 (BYOK) 的区别是什么？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

这两个选项都使您能够提供和控制自己的加密密钥;但是, 使用客户密钥进行的服务加密会对静态数据进行加密, 驻留在 Office 365 服务器的 BYOK 中, 而在 Exchange Online 中使用 Azure 信息保护会对您的数据传输进行加密, 并提供持续在线和离线对适用于 Office 365 的电子邮件和附件的保护。 使用 Exchange Online 的 Azure 信息保护的 Customer Key 和 BYOK 是互补的, 无论您是选择使用 Microsoft 服务托管的密钥还是您自己的密钥, 加密数据的同时还可以提供额外的保护。恶意攻击。
  
使用 Exchange Online 的 Azure 信息保护的 BYOK 在 Office 365 邮件加密功能中提供。
  
## <a name="does-office-365-message-encryption-and-bring-your-own-key-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>Office 365 邮件加密和使用您自己的密钥进行 Azure 信息保护更改 Microsoft 对第三方数据请求 (如 subpoenas) 的方法？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

不能。 Office 365 邮件加密和用于提供和控制您自己的加密密钥的选项, 为 Azure 信息保护 (AIP) 引入你自己的密钥 (BYOK) 的目的不是为了响应执法部门的 subpoenas。 BYOK for AIP 的 Office 365 邮件加密专为需要满足其内部或外部合规性义务的合规性客户而设计。 Microsoft 会对客户数据进行非常严重的第三方请求。 作为云服务提供商, 我们始终提倡客户数据的隐私。 在我们获取传唤时, 我们总是会尝试将第三方重定向到客户来获取信息。 (请阅读 Brad Smith 的博客:[保护客户数据免受政府窥探](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。 我们会定期发布我们在[此处](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)收到的请求的详细信息。
  
有关详细信息, 请参阅[联机服务条款 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)中有关第三方数据请求和 "客户数据泄露" 的[Microsoft 信任中心](https://www.microsoft.com/en-us/trustcenter/default.aspx)。
  
## <a name="does-service-encryption-with-customer-key-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>服务加密是否具有客户密钥更改 Microsoft 对第三方数据请求 (如 subpoenas) 的方法？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

不能。 客户密钥不旨在响应执法部门的 subpoenas。 它是为管控客户设计的, 以满足其内部或外部合规性义务。 Microsoft 会对客户数据进行非常严重的第三方请求。 作为云服务提供商, 我们始终提倡客户数据的隐私。 在我们获取传唤时, 我们总是会尝试将第三方重定向到客户来获取信息。 (请阅读 Brad Smith 的博客:[保护客户数据免受政府窥探](http://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。 我们会定期发布我们在[此处](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)收到的请求的详细信息。
  
有关详细信息, 请参阅[联机服务条款 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)中有关第三方数据请求和 "客户数据泄露" 的[Microsoft 信任中心](https://www.microsoft.com/en-us/trustcenter/Privacy/govt-requests-for-data)。 
  
## <a name="is-fasttrack-support-available-for-implementing-customer-key"></a>是否有可用于实现客户密钥的 FastTrack 支持？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

不能。 FastTrack 仅用于收集注册客户密钥所需的租户和服务配置信息。 客户密钥提供通过 FastTrack 发布, 以便客户和合作伙伴可以使用相同的方法提交所需的信息, 并轻松存档客户提供的数据。
  
如果你需要文档之外的其他支持, 请联系 microsoft 咨询服务 (MCS)、首要现场工程 (PFE) 或 Microsoft 合作伙伴以获取帮助。
  
## <a name="if-my-keys-are-destroyed-how-can-i-recover"></a>如果我的密钥已损坏, 如何进行恢复？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性密钥使您能够从所管理的根密钥的意外丢失中恢复。 如果丢失了根密钥, 请与 microsoft 支持部门联系, microsoft 将协助你完成启用可用性密钥的过程。 你将使用可用性密钥迁移到新的数据加密策略, 并使用你预配的新密钥。 
  
## <a name="what-is-the-availability-key"></a>可用性密钥是什么？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性密钥是在创建数据加密策略时设置的根键。 可用性密钥在 Office 365 中进行存储和保护, 并且功能类似于您提供的用于与客户密钥一起使用的服务加密的两个根键。 与在 Azure Key Vault 中提供和管理的密钥不同, 您不能直接访问可用性密钥。 由于以下三个原因, 可用性密钥的存储和控制特意不同于 Azure 密钥存储库密钥: 首先, 可用性密钥提供了高可用性功能, 在 Office 365 服务无法访问 Azure key 中托管的密钥的情况下。保险柜其次, 可用性密钥在两个 Azure 密钥保管库密钥丢失的情况下提供 "中断玻璃" 功能;第三, 逻辑控件的分离可提供深入防护, 防止丢失单个攻击或故障点的所有密钥。 共享责任来保护密钥, 同时使用各种保护和流程进行密钥管理, 最终降低了所有密钥 (因而您的数据) 将丢失或损坏的风险。 Microsoft 为你提供了对可用性密钥销毁的唯一权限。 根据设计, Microsoft 没有任何人可以访问可用性密钥-它只能通过 Office 365 服务代码访问。
  
## <a name="how-many-data-encryption-policies-deps-can-i-create"></a>可以创建多少个数据加密策略 (DEPs)？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for business:** 最高可创建 50 DEPs。 
  
 **SharePoint Online 和 OneDrive for business:** DEP 适用于一个地理位置 (也称为地理位置) 中的数据。 如果使用 Office 365 的多地理位置功能, 则可以为每个地理位置创建一个 DEP。 如果您不使用多地理位置, 则可以创建一个 DEP。
  
## <a name="can-i-assign-a-data-encryption-policy-before-migrating-a-mailbox-to-the-cloud"></a>是否可以在将邮箱迁移到云中之前分配数据加密策略？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可以。 您可以使用 Windows PowerShell cmdlet MailUser 在将邮箱迁移到 Office 365 之前向用户分配数据加密策略 (DEP)。 执行此操作时, 将使用分配的 DEP 在迁移内容时加密邮箱的内容。 这比在邮箱迁移后分配 DEP, 然后等待加密以进行, 这可能需要数小时或数天的效率更高。 
  
## <a name="how-do-i-verify-that-encryption-with-customer-key-is-activated-and-office-365-has-finished-encrypting-with-customer-key"></a>如何验证是否已激活客户密钥的加密功能, 以及 Office 365 是否已完成客户密钥加密？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for business:** 您可以[使用远程 PowerShell 连接到 Exchange Online](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) , 然后对要检查的每个邮箱使用 **[get-mailboxstatistics]** cmdlet。 在 get-mailboxstatistics cmdlet 的输出中, 如果邮箱已加密, 则_IsEncrypted_属性返回**true** , 如果不是, 则返回值**false** 。 如果邮箱已加密, 则为_DataEncryptionPolicyID_属性返回的值是邮箱加密的 DEP 的 GUID。 有关运行此 cmdlet 的详细信息, 请参阅[get-mailboxstatistics](https://technet.microsoft.com/en-us/library/bb124612%28v=exchg.160%29.aspx)和使用 PowerShell with Exchange Online。 
  
如果邮箱在您分配 DEP 之后的等待时间为72小时之后未加密, 请启动邮箱移动。 为此, 请[使用远程 PowerShell 连接到 Exchange Online](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) , 然后使用 new-moverequest cmdlet, 并提供邮箱的别名, 如下所示: 
  
```
New-MoveRequest <alias>
```

 **SharePoint Online 和 OneDrive for business:** 您可以[连接到 SharePoint Online PowerShell](https://technet.microsoft.com/en-us/library/fp161372.aspx), 然后使用 **[SPODataEncryptionPolicy]** cmdlet 检查租户的状态。 如果启用了客户密钥加密且所有站点中的所有文件均已加密, * * _State_* * 属性将返回一个**注册**值。 如果仍在进行加密, 则此 cmdlet 提供有关已完成的网站百分比的信息。 
  
## <a name="if-i-want-to-switch-to-a-different-set-of-keys-how-long-does-it-take-for-the-new-set-of-keys-to-protect-my-data"></a>如果我要切换到一组不同的键, 则需要多长时间才能保护我的数据的新密钥集？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for business:** 在将新的 DEP 分配到邮箱时, 最长可能需要72小时才能根据新的数据加密策略 (DEP) 保护邮箱。 
  
 **SharePoint Online 和 OneDrive for business:** 一旦分配了新密钥, 它最长可能需要四个小时才能重新加密整个租户。 
  
## <a name="is-my-existing-data-stored-without-encryption-at-any-time-while-it-is-decrypted-or-encrypted-with-customer-key"></a>在使用客户密钥对其进行解密或加密时, 是否已在不加密的情况下存储现有数据？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

不能。 Office 365 服务中的静态数据始终在 BitLocker 和 DKM 中进行加密。 有关详细信息, 请参阅 "Office 365 的安全性、隐私和合规性信息", 以及[Exchange Online 如何保护您的电子邮件密码](https://support.office.com/article/989BA10C-F73F-4EFB-AD1B-AF3322E5F376)。
  
## <a name="if-i-no-longer-want-to-use-customer-managed-encryption-keys-can-i-switch-to-microsoft-managed-keys"></a>如果我不想再使用客户管理的加密密钥, 是否可以切换到 Microsoft 管理的密钥？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for business:** 还没有。 在 Office 365 中通过 Microsoft 托管密钥进行的服务加密将被广泛汇总。 我们预计在使用客户密钥发布服务加密后, 将在服务中进行汇总。 
  
 **SharePoint Online 和 OneDrive for business:** 是的。 您可以选择恢复为在每个地理位置 (如果使用多地理位置功能) 或所有数据 (如果您使用的是单个地理位置) 中单独使用 Microsoft 托管键。 
  
## <a name="if-i-lose-my-keys-how-long-does-it-take-to-recover-service-availability-using-the-recovery-key"></a>如果我的密钥丢失, 使用恢复密钥恢复服务可用性需要多长时间？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

 **Exchange Online 和 Skype for business:** 在调用以使用可用性密钥之后, 邮箱将在几分钟内可供访问。 
  
 **SharePoint Online 和 OneDrive for business:** 此操作与您拥有的网站数成比例。 一旦您调用 Microsoft 使用可用性密钥, 你将在大约4小时内完全在线。 
  
## <a name="how-is-the-availability-key-used-with-exchange-online"></a>如何将可用性密钥用于 Exchange Online？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

可用性密钥与 Exchange Online 结合使用的方式有三种:
  
- 服务可用性-当 Azure 密钥保管库密钥不可访问时。
    
- 由 Office 365 服务代码启动的操作-如搜索索引创建或邮箱移动。
    
- 从密钥丢失恢复-例如, 丢失与单个 DEP 相关联的 Azure key Vault 密钥。
    
 **在 Azure key Vault 密钥中使用服务可用性的可用性密钥是不可访问的。**
  
Office 365 使用可用性密钥来实现服务可用性, 并从 Exchange Online 的不正常客户密钥状态恢复。 有一个由客户密钥使用的密钥的层次结构。 此层次结构如下图所示。
  
![](media/a760156b-737f-469a-80ab-c28b7a8b9160.png)
  
如果单个数据加密策略 (DEP) 的两个 Azure 密钥保管库密钥均不可用, 则 Office 365 可以使用可用性密钥更改为新的 DEP。 Office 365 根据用户启动的活动 (例如, 用户是否将电子邮件下载到 Outlook 客户端) 或系统启动的活动 (如索引), 确定是否使用可用性密钥以不同方式使用可用性密钥。邮箱内容或电子数据展示搜索触发此过程。
  
Office 365 按照此过程响应用户启动的操作, 以确定是否对用户邮箱使用可用性密钥:
  
1. Office 365 读取邮箱分配到的 DEP, 以便确定两个客户密钥在 Azure Key Vault 中的位置。
    
2. Office 365 从 DEP 中随机选择两个客户密钥中的一个, 并向 Azure key Vault 发送一个请求, 以使用客户密钥解包 DEP 密钥。
    
3. 如果使用客户密钥对对 DEP 密钥进行解包的请求失败并返回错误, 则 Office 365 会向 Azure key Vault 发送第二个请求, 这次指示它使用备用 (第二) 客户密钥。
    
4. 如果第二个请求使用客户密钥解包 DEP 密钥失败并返回错误, 则 Office 365 会检查两个请求的结果:
    
  - 如果检查确定错误未反映客户标识的显式操作, 则 Office 365 将使用可用性密钥对 DEP 密钥进行解密。 然后, 使用 DEP 密钥来解密邮箱密钥, 并完成用户请求。
    
    在这种情况下, 由于任何原因, Azure 密钥存储库都无法响应或不可访问。 Office 365 无法确定客户是否已有意撤销对密钥的访问权限。
    
  - 如果检查表明已采取有意的措施来呈现客户密钥不可用, 则将不会使用可用性密钥, 用户请求将失败, 并且用户收到一条错误消息, 如登录失败。
    
    当发生这种情况时, 客户会意识到服务受到影响, 客户密钥的条件不正常。 例如, 如果客户对组织中的所有邮箱使用一个 DEP, 则该客户可能会遇到广泛的故障, 用户无法访问其邮箱。 这样可确保当两个客户密钥不正常时, 客户就会意识到需要纠正这种情况, 并将服务还原到正常状态。
    
 **使用 Office 365 服务代码启动的操作的可用性密钥。**
  
Office 365 服务代码始终具有有效的登录令牌, 不能被阻止。 因此, 在删除可用性密钥之前, 可将其用于 Office 365 服务代码 (如搜索索引创建或移动邮箱) 启动的操作或内部的操作。
  
 **使用可用性密钥从密钥丢失中恢复。**
  
您可以使用可用性密钥恢复与同一个 DEP 相关联的 Azure key Vault 密钥的丢失, 如 FAQ 条目的答案中所述, "如果我的密钥已损坏, 如何恢复？"。
  
## <a name="how-is-the-availability-key-used-with-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 和 OneDrive for business 使用的可用性密钥有何功能？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

SharePoint online 和 OneDrive for business 体系结构以及客户密钥和可用性密钥实现不同于 Exchange Online 和 Skype for business。
  
当客户移动到客户管理的密钥时, Office 365 将创建特定于租户的中间密钥 (TIK)。 Office 365 将 TIK 加密两次, 每个客户密钥一次, 并存储 TIK 的两个加密版本。 仅存储 TIK 的加密版本, 并且 TIK 只能使用客户密钥进行解密。 然后, 使用 TIK 对网站密钥进行加密, 然后使用这些密钥对 blob 密钥进行加密。 blob 本身被加密并存储在 Microsoft Azure Blob 存储服务中。
  
Office 365 遵循此过程来访问包含客户文件数据的 blob:
  
1. 使用客户密钥对 TIK 进行解密。
    
2. 使用解密的 TIK 解密网站密钥。
    
3. 使用解密的网站密钥对 blob 密钥进行解密。
    
4. 使用解密的 blob 密钥对 blob 进行解密。
    
解密 TIK 时, Office 365 会向 Azure Key Vault 颁发两个解密请求, 但具有轻微偏移量。 第一个要完成的提供结果, 取消了另一个请求。
  
如果客户失去对其客户密钥的访问权限, Office 365 还会使用可用性密钥对 TIK 进行加密, 并将其与使用每个客户密钥加密的 TIKs 存储在一起。 使用 availability 密钥加密的 TIK 仅当客户在失去对其密钥的访问权限 (恶意或意外) 时, 才将 Microsoft 用于登记恢复路径。
  
出于可用性和扩展原因, 解密的 TIKs 缓存在一个时间有限的内存缓存中。 在 TIK 缓存设置为过期之前的两个小时, Office 365 将尝试对每个 TIK 进行解密。 对 TIKs 进行解密会延长缓存的生存期。 如果 TIK 解密在很长一段时间后失败, Office 365 将生成一个警报, 以在缓存过期之前通知工程。 仅当客户呼叫 microsoft 时, Office 365 才会启动恢复操作, 这涉及使用存储在 Microsoft 机密存储中的可用性密钥对 TIK 进行解密, 并使用解密的 TIK 再次载入租户, 并使用一组新的客户提供的 Azure Key Vault 密钥。
  
到目前为止, 客户密钥包含在 Azure blob 存储中存储的 sharepoint online 文件数据的加密和解密链中, 但不包含在 SQL 数据库中存储的 sharepoint online 列表项或元数据中。 除了客户启动的情况之外, Office 365 不使用 SharePoint Online 或 OneDrive for business 的可用性密钥 (而不是上面介绍的事例)。 对客户数据的人对客户数据的访问受客户密码箱保护。
  
## <a name="how-is-customer-key-licensed"></a>如何许可客户密钥？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

客户密钥在 Office 365 企业套件、"E5" 和高级合规性 SKU 中提供。 此外, 客户还必须购买使用 Azure Key Vault 的相应许可证。
  
如果客户密钥需要获得客户密钥的涵盖, 则每个用户都可以从客户密钥中受益。
  
对于 SharePoint Online, 配置客户密钥的 Office 365 管理员也需要获得许可, 以执行设置步骤。 此外, 需要许可的用户才需要获得许可, 这包括网站所有者和访问使用客户密钥加密的一个或多个网站上的文件的用户。 外部用户无需许可即可访问使用客户密钥加密的一个或多个站点上的文件。
  
对于 Exchange Online, "用户" 邮箱和 "邮件用户" 邮箱必须获得许可。 所有其他 (如共享邮箱) 不需要拥有客户密钥许可证。 若要检查您的 Exchange Online 邮箱是否已得到正确许可, 请运行以下 cmdlet:
  
```
(Get-Mailbox <alias >).PersistedCapabilities
```

如果字符串 BPOS_S_EquivioAnalytics 存在, 则对邮箱进行了正确的授权。 如果不是, 则必须应用适当的许可证, 才能使用此邮箱的客户密钥功能。
  
## <a name="can-i-enable-customer-key-for-a-trial-subscription"></a>我是否可以为试用订阅启用客户密钥？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

不能。 根据定义, 试用订阅的生命周期有限。 在试用版订阅结束时托管的加密密钥可能会在试用期结束时丢失。 由于 Microsoft 无法且不会阻止客户将重要的客户数据放在试用订阅中, 因此不允许对试用订阅使用客户密钥。
  
## <a name="how-much-will-using-customer-key-cost"></a>使用客户密钥的成本有多大？
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

除了客户密钥所需的许可, 客户将对密钥存储使用承担成本。 [Azure Key Vault 定价详细信息](https://azure.microsoft.com/en-us/pricing/details/key-vault/)介绍了成本模型, 并将协助估计。 由于使用模式不同, 因此无法预测任何客户将产生的确切成本。 经验表明, 成本非常低, 并且通常在每个用户每月 $0.002 到 $0.005 的范围内, 再加上受 HSM 支持的密钥的成本。 根据客户选择的日志记录配置和用于 azure Key Vault 日志的 azure 存储量, 该成本也会有所不同。 
  
## <a name="for-more-information"></a>有关详细信息
<a name="DiffCustomerKeyandBYOKAzureIP"> </a>

若要开始使用客户密钥, 请参阅[使用客户密钥控制 Office 365 中的数据](controlling-your-data-using-customer-key.md)。
  


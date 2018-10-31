---
title: 为 Office 365 邮件加密激活 Azure 权限管理
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 以前版本的 Office 365 邮件加密取决于在 Microsoft Azure 权限管理 （以前称为 Windows Azure Active Directory 权限管理）。
ms.openlocfilehash: f8759da8628d4c78fe5409f5c47e3fc2b3e9484e
ms.sourcegitcommit: c05076501dfe118e575998ecfc08ad69d13c8abc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25853067"
---
# <a name="this-article-applies-to-the-previous-version-of-ome"></a>本文适用于 OME 的早期版本
如果您没有尚未将您的 Office 365 组织移到 OME 的新功能，但您已经部署了 OME，本文中的信息适用于您的组织。Microsoft 建议您进行规划，以将移动到新的 OME 功能只要很合理为您的组织。有关说明，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。如果您想要找出有关的新功能，首先工作的方式的详细信息，请参阅[Office 365 邮件加密](ome.md)。本文的其余部分是指之前的版本的新功能，OME OME 行为。

# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a>为以前版本的 Office 365 邮件加密设置 Azure 权限管理

本主题介绍需要才能激活并将设置 Azure 权限管理 (RMS)，用于与 Office 365 邮件加密 (OME) 的 Azure 信息保护的一部分执行的步骤。
  
## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>使用以前版本的 Office 365 邮件加密的先决条件
<a name="warmprereqs"> </a>

Office 365 邮件加密 (OME)，包括 IRM，取决于 Azure 权限管理 (Azure RMS)。Azure RMS 是使用 Azure 信息保护保护技术。若要使用 OME，您的 Office 365 组织必须包括 Exchange Online 或 Exchange Online Protection 的订阅，反过来，包括 Azure 权限管理订阅。
  
- 如果您不确定您的订阅所包含的内容，请参阅[邮件策略、 恢复以及合规性](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)的 Exchange Online 服务说明。
    
- 如果您没有 Azure RMS 订阅 Exchange Online 或 Exchange Online Protection，您必须购买订阅和先激活。
    
    有关购买订阅 Azure 权限管理的信息，请参阅[Azure 权限管理](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT)。下一节提供了有关激活 Azure 权限管理的信息。
    
- 如果您有 Azure 权限管理，但它未设置 Exchange Online 或 Exchange Online Protection，这篇文章介绍如何激活 Azure 权限管理，然后介绍设置 OME 以使用 Azure 权限管理的最佳方式。
    
- 如果您已设置 OME 能够使用 Azure 权限管理 Exchange Online 或 Exchange Online Protection，具体取决于您将其设置，您可能已准备好开始立即使用 OME 和其新的功能。本文介绍如何确定是否您已设置 OME 正确，如果您需要更改您的设置，怎么办以及如果您选择不更改您的安装程序会发生什么情况。例如，若要使用的新功能，您必须使用 Azure RMS OME。不能使用内部部署 Active Directory RMS 的新功能。
    
## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>早期版本的 Office 365 中的 OME 激活 Azure 权限管理
<a name="activatewarm"> </a>

您需要激活 Azure 权限管理，以便您的组织中的用户可以应用于他们发送的消息的信息保护和打开邮件和 Azure Rights Management 服务受保护的文件。有关说明，请参阅[激活 Azure 权限管理](https://go.microsoft.com/fwlink/p/?LinkId=525775)。完成激活之后，此处返回，并继续执行本文中的任务。
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>将以前版本的 OME 设置为使用 Azure RMS 通过导入可信发布域 (TPDs)
<a name="importTPDs"> </a>

TPD 是一个 XML 文件包含有关您组织的权限管理设置的信息。例如，TPD 包含有关用于签名和加密证书和许可证的服务器许可方证书 (SLC) 的信息，Url 用于许可和发布，等等。使用 Windows PowerShell 您导入您的 Office 365 组织的 TPD。
  
> [!IMPORTANT]
> 以前，您可以选择将 TPDs 从 Active Directory 权限管理服务 (AD RMS) 导入您的 Office 365 组织。但是，这样会阻止您使用的新 OME 功能并不建议使用。如果这种方式配置 Office 365 组织的当前状态，Microsoft 建议您制定的计划以从您的本地 Active Directory RMS 迁移到基于云的 Azure 信息保护。有关详细信息，请参阅[Migrating from AD RMS 到 Azure 信息保护](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。您将无法使用新的 OME 功能，直到您已完成迁移到 Azure 信息保护。 
  
 **从 Azure RMS 导入 TPDs**
  
1. [连接到 Exchange Online 使用远程 PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。
    
2. 选择对应于您的 Office 365 组织的地理位置的关键共享 URL:
    
|**位置**|**关键共享位置的 URL**|
|:-----|:-----|
|北美  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|欧盟  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|亚洲  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|南美洲  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|政府用 Office 365（政府社区云）  <br/> 此 RMS 密钥共享位置以供客户已购买 Office 365 政府版 sku。  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. 通过运行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet，如下所示配置密钥共享位置： 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    例如，若要配置的关键共享位置，如果在北美位于您的组织：
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. 与-RMSOnline 开关从 Azure 权限管理导入 TPD 运行[Import-rmstrustedpublishingdomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet: 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    您想要用于 TPD 其中*TPDName*是名称。例如，"Contoso 北美 TPD"。 
    
5. 若要验证已成功配置了 Office 365 组织以使用 Azure 权限管理服务，请运行[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet 与-RMSOnline 开关，如下所示： 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    除此之外，此 cmdlet 检查与 Azure 权限管理服务的连接，下载 TPD，并检查其有效性。
    
6. 运行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet，如下所示禁用 Outlook 在 web 和 Outlook 中不可用的 Azure 权限管理模板： 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. 运行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet，如下所示的基于云的电子邮件组织启用 Azure 权限管理并将其配置为使用 Office 365 邮件加密 Azure 权限管理： 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. 若要验证您已成功导入 TPD 并启用 Azure 权限管理，请使用 Test-irmconfiguration cmdlet 来测试 Azure 权限管理功能。有关详细信息，请参阅[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)中的"示例 1"。
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>我有以前版本的 OME 设置与 Active Directory 权限管理不 Azure 信息保护，我该怎么办？
<a name="importTPDs"> </a>

您可以继续使用您现有的 Office 365 邮件加密邮件流规则与 Active Directory 权限管理，但您无法配置或使用新的 OME 功能。相反，您需要将迁移到 Azure 信息保护。有关迁移和这意味着您的组织的信息，请参阅[Migrating from AD RMS 到 Azure 信息保护](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)。
  
## <a name="next-steps"></a>后续步骤
<a name="importTPDs"> </a>

当您完成 Azure 权限管理设置，如果您想要启用新的 OME 功能，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部。](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)
  
已设置您的组织使用的新 OME 功能后，您已准备好[定义邮件流规则来保护与 OME 的新功能的电子邮件消息](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="related-topics"></a>相关主题
<a name="importTPDs"> </a>

[Office 365 中的加密](encryption.md)
  
[有关 Office 365 加密的技术参考详情](technical-reference-details-about-encryption.md)
  
[什么是 Azure 权限管理？](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  


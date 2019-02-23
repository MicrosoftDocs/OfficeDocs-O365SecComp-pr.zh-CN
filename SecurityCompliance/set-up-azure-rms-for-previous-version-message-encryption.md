---
title: 为以前版本的 Office 365 邮件加密设置 Azure 权限管理
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 早期版本的 Office 365 邮件加密取决于 Microsoft azure 权限管理 (以前称为 "Windows azure Active Directory 权限管理")。
ms.openlocfilehash: 89b86035f57699457c86fefb49888b8428f4e01c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214372"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a>为以前版本的 Office 365 邮件加密设置 Azure 权限管理

本主题介绍了为激活前一版本的 Office 365 邮件加密 (OME) 而激活和设置 azure 权限管理 (RMS) (azure 信息保护的一部分) 时需要遵循的步骤。

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>本文仅适用于早期版本的 OME
如果您尚未将 Office 365 组织移动到新的 OME 功能, 但您已经部署了 OME, 则本文中的信息适用于您的组织。Microsoft 建议您制定一个计划, 尽快移动到新的 OME 功能, 因为它对您的组织合理。有关说明, 请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。如果您想要详细了解新功能的工作方式, 请参阅[Office 365 邮件加密](ome.md)。本文的其余部分是在发布新的 OME 功能之前的 OME 行为。

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>使用早期版本的 Office 365 邮件加密的先决条件
<a name="warmprereqs"> </a>

Office 365 邮件加密 (OME) (包括 IRM) 取决于 Azure 权限管理 (azure RMS)。azure RMS 是 azure 信息保护使用的保护技术。若要使用 OME, Office 365 组织必须包括 exchange online 或 exchange online 保护订阅, 这些订阅又包括 Azure 权限管理订阅。
  
- 如果你不确定订阅包含的内容, 请参阅 Exchange Online 服务说明[中的邮件策略、恢复和合规性](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)。

- 如果没有适用于 exchange online 或 exchange online Protection 的 Azure RMS 订阅, 则必须先购买订阅并将其激活。

    有关购买 azure 权限管理订阅的信息, 请参阅[azure 权限管理](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT)。下一节提供了有关激活 Azure 权限管理的信息。

- 如果你拥有 Azure 权限管理, 但未针对 exchange online 或 exchange online Protection 进行设置, 则本文介绍如何激活 azure 权限管理, 然后介绍了设置 OME 以使用 Azure 权限管理的最佳方式。

- 如果你已将 OME 设置为使用适用于 Azure 权限管理的 exchange online 或 exchange online Protection, 则可能已准备好立即开始使用 OME 及其新功能。本文介绍如何确定您是否已正确设置 OME, 如果需要更改设置, 应执行的操作, 如果您选择不更改设置, 会发生什么情况。例如, 若要使用新功能, 必须将 Azure RMS 与 OME 结合使用。您不能将新功能用于本地 Active Directory RMS。

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>为 Office 365 中的早期版本的 OME 激活 Azure 权限管理

您需要激活 azure 权限管理, 以便组织中的用户可以对其发送的邮件应用信息保护, 并打开由 Azure 权限管理服务保护的邮件和文件。有关说明, 请参阅[激活 Azure 权限管理](https://go.microsoft.com/fwlink/p/?LinkId=525775)。完成激活后, 请返回此处并继续执行本文中的任务。
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>通过导入受信任的发布域 (tpd), 将早期版本的 OME 设置为使用 Azure RMS

TPD 是一个 XML 文件, 其中包含有关您的组织的权限管理设置的信息。例如, TPD 包含有关用于对证书和许可证进行签名和加密的服务器许可方证书 (SLC) 的信息、用于许可和发布的 url 等。您可以使用 Windows PowerShell 将 TPD 导入到 Office 365 组织中。
  
> [!IMPORTANT]
> 以前, 可以选择将 tpd 从 Active Directory 权限管理服务 (AD RMS) 导入 Office 365 组织中。但是, 这样做会阻止您使用新的 OME 功能, 不建议这样做。如果您的 Office 365 组织当前以这种方式配置, Microsoft 建议您创建从本地 Active Directory RMS 迁移到基于云的 Azure 信息保护的计划。有关详细信息, 请参阅[从 AD RMS 迁移到 Azure 信息保护](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。在完成到 Azure 信息保护的迁移之前, 你将无法使用新的 OME 功能。
  
 **从 Azure RMS 导入 tpd**
  
1. [使用远程 PowerShell 连接到 Exchange Online](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。

2. 选择与您的 Office 365 组织的地理位置对应的密钥共享 URL:

|**位置**|**键共享位置 URL**|
|:-----|:-----|
|北美  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|欧盟  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|亚洲  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|南美洲  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|政府用 Office 365（政府社区云）  <br/> 此 RMS 密钥共享位置是为购买了 Office 365 for 政府 sku 的客户预留的。  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. 通过运行[get-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet 配置键共享位置, 如下所示: 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    例如, 如果您的组织位于北美, 若要配置关键共享位置, 请执行以下操作:
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. 使用-RMSOnline 开关运行[import-rmstrustedpublishingdomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet, 以从 Azure 权限管理导入 TPD: 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    其中, *TPDName*是要用于 TPD 的名称。例如, "Contoso 北方美洲 TPD"。 
    
5. 若要验证您是否已成功将 Office 365 组织配置为使用 Azure 权限管理服务, 请运行[get-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet 和-RMSOnline 开关, 如下所示: 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    此外, 此 cmdlet 还检查与 Azure 权限管理服务的连接, 下载 TPD, 并检查其有效性。
    
6. 运行[get-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet, 如下所示, 以禁用 web 和 outlook 上的 outlook 中提供的 Azure 权限管理模板: 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. 运行[get-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet, 如下所示, 为您的基于云的电子邮件组织启用 azure 权限管理, 并将其配置为使用 azure 权限管理 for Office 365 邮件加密: 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. 若要验证您是否已成功导入 TPD 并启用 azure 权限管理, 请使用 get-irmconfiguration cmdlet 测试 Azure 权限管理功能。有关详细信息, 请参阅[get-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)中的 "示例 1"。
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>我已将早期版本的 OME 设置为使用 Active Directory 权限管理, 而不是 Azure 信息保护, 我该怎么办？
<a name="importTPDs"> </a>

您可以继续使用现有的 Office 365 邮件加密邮件流规则与 Active Directory 权限管理, 但不能配置或使用新的 OME 功能。而是需要迁移到 Azure 信息保护。有关迁移和组织的这种方法的信息, 请参阅[从 AD RMS 迁移到 Azure 信息保护](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)。
  
## <a name="next-steps"></a>后续步骤
<a name="importTPDs"> </a>

完成 Azure 权限管理安装程序后, 如果要启用新的 OME 功能, 请参阅[设置基于 Azure 信息保护基础构建的新 Office 365 邮件加密功能。](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)
  
将组织设置为使用新的 OME 功能之后, 您就可以[定义邮件流规则, 以使用新的 OME 功能保护电子](define-mail-flow-rules-to-encrypt-email.md)邮件。
  
## <a name="related-topics"></a>相关主题
<a name="importTPDs"> </a>

[Office 365 中的加密](encryption.md)
  
[有关 Office 365 加密的技术参考详情](technical-reference-details-about-encryption.md)
  
[什么是 Azure 权限管理？](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  


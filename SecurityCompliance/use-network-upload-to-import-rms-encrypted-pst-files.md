---
title: 使用网络上载将 RMS 加密的 PST 文件导入到 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: 了解如何使用网络上传将 RMS 加密的 PST 文件导入 Office 365 中的用户邮箱。
ms.openlocfilehash: 46f77f3fe173da23e08284884bb85c69ab53f710
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958293"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>使用网络上载将 RMS 加密的 PST 文件导入到 Office 365

**本文适用于管理员。您是否尝试将 PST 文件导入到自己的邮箱？请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
使用 "网络上载" 选项和 Office 365 导入服务将 PST 文件导入到用户邮箱。 网络上载是指将 PST 文件上载到 Microsoft 云中的临时存储区域。 然后, Office 365 导入服务将 PST 文件从存储区域复制到目标用户邮箱。 导入服务的新功能允许您在将 PST 文件上传和存储到 Microsoft 云之前对其进行加密。 在将这些文件导入到用户邮箱中时，不会对这些文件进行加密。 
  
以下是将 PST 文件加密和导入到 Office 365 邮箱所需的步骤:
  
[步骤 1: 为 PST 导入设置 Azure 权限管理](#step-1-set-up-azure-rights-management-for-pst-import)

[步骤 2：生成 PST 导入的加密密钥](#step-2-generate-an-encryption-key-for-pst-import)

[步骤 3: 获取 RMS 租户 ID 和许可 URL](#step-3-obtain-rms-tenant-id-and-licensing-url)

[步骤 4: 下载 PST 导入工具并复制 SAS URL](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[步骤 5: 将 PST 文件加密并上载到 Office 365](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[Optional步骤 6: 查看已上载到 Office 365 的 PST 文件的列表](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[步骤 7: 创建 PST 导入映射文件](#step-7-create-the-pst-import-mapping-file)

[步骤 8：在 Office 365 中创建 PST 导入作业](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> 您只需执行步骤1到步骤4一次, 即可设置并配置组织, 以加密和将 PST 文件导入到 Office 365 邮箱。 执行这些步骤后, 请按照第5步到第8步进行加密、上传和导入一批 PST 文件。 
  
有关将数据导入到 office 365 的详细信息, 请参阅将[组织 PST 文件导入到 office 365 概述](importing-pst-files-to-office-365.md)。
  
## <a name="before-you-begin"></a>准备工作

- 您必须在 Exchange Online 中分配 "邮箱导入导出" 角色, 才能将 PST 文件导入到 Office 365 邮箱。 默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. 有关详细信息, 请参阅[管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的 "向角色组添加角色" 或 "创建角色组" 部分。
    
    此外, 若要在 Security & 合规性中心中创建导入作业, 必须满足以下条件之一:
    
  - 您必须在 Exchange Online 中向您分配 "邮件收件人" 角色。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    或
    
  - 您必须是 Office 365 组织中的全局管理员。
    
  > [!TIP]
  > 请考虑在 Exchange Online 中创建一个专门用于将 PST 文件导入到 Office 365 的新角色组。 若要获取导入 PST 文件所需的最低级别权限, 请将 "邮箱导入导出" 和 "邮件收件人" 角色分配给新的角色组, 然后添加成员。 
  
- 您需要将您要导入的 PST 文件存储到组织中的文件服务器或共享文件夹上的 Office 365 中。 在步骤5中, 将运行 office 365 ImportTool, 它会将存储在此文件服务器或共享文件夹上的 PST 文件加密并上载到 Office 365。
    
- 此过程涉及到复制和保存加密密钥、存储密钥和一些标识密钥及 URL 的副本。 将在步骤5中使用此信息来加密和上传您的 PST 文件。 一定要采取预防措施来保护这些文件，就像保护密码或其他与安全相关的信息一样。 例如，您可能将它们保存到受密码保护的 Microsoft Word 文档，或者将它们保存到已加密的 USB 驱动器。 请参阅[详细信息](#more-information)部分，查看包含这些密钥、ID 和 URL 的示例。 
    
- 您可以将 PST 文件导入到 Office 365 中的非活动邮箱。 为此, 请在 PST 导入映射文件的`Mailbox`参数中指定非活动邮箱的 GUID。 有关详细信息, 请参阅[步骤 7](#step-7-create-the-pst-import-mapping-file) 。 
    
- 在 Exchange 混合部署中, 可以将 PST 文件导入到主邮箱位于本地的用户的基于云的存档邮箱。 为此, 请在 PST 导入映射文件中执行以下操作:
    
  - 在`Mailbox`参数中指定用户的内部部署邮箱的电子邮件地址。 
    
  - 在`IsArchive`参数中指定**TRUE**值。 
    
    有关详细信息, 请参阅[步骤 7](#step-7-create-the-pst-import-mapping-file) 。 
    
- 将 PST 文件导入到 Office 365 邮箱后, 邮箱的保留挂起设置将处于无限期的期限内打开。 这意味着将不会处理分配给邮箱的保留策略, 除非您关闭保留挂起或设置关闭保留的日期。 我们为什么要这么做呢？ 如果导入到邮箱的邮件是旧邮件, 则可能会永久删除 (清除), 因为他们的保留期已过, 因为其保留期已根据邮箱配置的保留设置而过期。 将邮箱置于保留挂起状态将使邮箱所有者时间管理这些新导入的邮件, 或为您提供更改邮箱保留设置的时间。 有关管理保留挂起的建议, 请参阅[详细信息](#more-information)部分。 
    
- 如果您在将 pst 文件上传到 office 365 之前不需要对其进行加密, 请参阅[使用网络上载将 pst 文件导入到 office 365](use-network-upload-to-import-pst-files.md)。
    
- 有关使用网络上载将 pst 文件导入到 office 365 的常见问题, 请参阅[常见问题: 将 pst 文件导入 office 365](faqimporting-pst-files-to-office-365.md)。
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>步骤 1：对 PST 导入设置 Azure 权限管理 

PST 导入使用 Office 365 中的 azure 权限管理 (azure RMS) 服务提供的加密功能。 这样, 您就可以在将 PST 文件上载到 Office 365 之前对其进行加密。 
  
为 PST 导入配置 Azure RMS 包括三个步骤:
  
- [激活 Azure RMS](#activating-azure-rms)
    
- [在 Exchange Online 中配置 RMS](#configuring-rms-in-exchange-online)
    
- [安装 Active Directory RMS 客户端](#installing-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>激活 Azure RMS

Azure RMS 默认情况下处于禁用状态, 但你或组织中的其他管理员可能已将其激活。 按照[激活 azure 权限管理](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)以安装和激活 azure DRM 中的说明进行操作。
  
### <a name="configuring-rms-in-exchange-online"></a>在 Exchange Online 中配置 RMS

激活 Rights Management service 后, 下一步是在 Exchange Online 中设置信息权限管理 (IRM), 以使用 Azure RMS。 有关详细信息, 请参阅[将 IRM 配置为使用 Azure 权限管理](https://go.microsoft.com/fwlink/p/?LinkId=394816)。
  
1. [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554 )。
    
2. 运行以下命令来设置 RMS 密钥共享 URL。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    使用下表确定正确的 RMS 密钥共享您组织所处位置。
    
    |**Location**|**RMS 关键共享位置**|
    |:-----|:-----|
    |北美  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |欧盟  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |亚洲  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |南美洲  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |政府用 Office 365（政府社区云）  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup> 只有已购买政府用 Office 365 SKU（政府社区云）的客户才应使用此 RMS 密钥共享位置。 
  
    例如, 此命令在 Exchange online 中为位于北美的客户配置 RMS online 关键共享位置。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. 运行以下命令, 将受信任的发布域 (TPD) 从 RMS Online 导入到 Office 365 组织中。 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    TPD 包含在您的组织中使用 RMS 功能所需的设置，包括加密 PST 文件。  
    
4. 运行以下命令, 为 Office 365 组织启用 IRM。
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>安装 Active Directory RMS 客户端

本节的最后一步是下载权限管理服务 (RMS) 客户端 2.1。 此软件可帮助保护对 Azure rms 的访问, 并保护通过使用 Azure rms 的应用程序流动的信息。 在您将用于在步骤5中加密和上载 PST 文件的同一台计算机上安装 RMS 客户端。 
  
1. 下载[权限管理服务客户端 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396)。
    
2. 运行 Active Directory 权限管理服务客户端 2.1 向导来安装客户端。

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>步骤 2：生成 PST 导入的加密密钥

在设置 Azure RMS 之后, 下一步是生成将用于对上载到 Office 365 的 PST 文件进行加密的加密密钥 (称为对称密钥)。 你将通过在 Azure Active Directory 中将 PST 导入服务添加为服务主体来实现此目的。 将此应用程序添加为服务主体将允许 pst 导入服务在第5步中向 azure 存储位置上传加密 pst 文件时, 直接与 azure Active Directory 进行身份验证。
  
1. 启动用于 Windows PowerShell 的 Azure Active Directory 模块。
    
2. 运行下面的命令以连接到 Microsoft Online 服务。
    
    ```
    Connect-MsolService
    ```

3. 输入 Office 365 组织中管理员帐户的凭据, 然后单击 **"确定"**。
    
4. 运行以下命令以生成加密密钥（也称作“对称密钥”）。 您将通过创建新的 PST 加密主体来执行此操作。
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    系统将显示新 PST 加密主体的对称密钥和属性。
    
    ![复制并保存显示的对称密钥](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. 将对称密钥复制到文本或 Word 文件中。如前所述，一定要采取预防措施来保护此文件。因为这是显示对称密钥的唯一时机，所以您也可以考虑对此窗口拍摄屏幕快照并将其保存到同一文件中。  
    
    > [!IMPORTANT]
    > 创建 PST 加密主体后，您将无法通过使用 **Get-MsolServicePrincipal** cmdlet 检索对称密钥。 这就是保存该密钥非常重要的原因。 
  
将用于 Windows PowerShell 的 Azure Active Directory 模块保持打开并连接到 Microsoft Online 服务。 在下一步中，您将在此窗口中运行一个命令。

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>步骤 3: 获取 RMS 租户 ID 和许可 URL

下一步是获取组织的 Azure RMS 服务的租户 ID 和许可位置 URL。 将此信息复制并保存到包含步骤 2 中的对称密钥的同一个文件中。 将在步骤5中使用 ID 和 URL 来加密 PST 文件。
  
1. 在用于 Windows PowerShell 的 Azure Active Directory 模块 (连接到 Microsoft Online 服务) 中, 运行以下命令以连接到您的 Office 365 组织中的 Azure RMS 服务。
    
    ```
    Connect-AadrmService 
    ```

2. 输入 Office 365 组织中管理员帐户的凭据, 然后单击 **"确定"**。
    
3. 运行以下命令以显示 Office 365 组织中的 Azure RMS 服务的租户 ID。
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    复制并保存`BPOSId`属性的值。 
    
4. 运行以下命令以显示 Azure RMS 服务的许可位置。
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    复制并保存`LicensingIntranetDistributionPointUrl`属性的值。 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>步骤 4: 下载 PST 导入工具并复制 SAS URL

现在, 你已配置了 Azure RMS 并获取了加密 PST 文件所需的 id, 下一步是下载并安装将在步骤5中运行的工具, 以将 pst 文件加密并上载到 Office 365。 这些工具是 Azure AzCopy 工具和 Office 365 数据加密工具。 您还将为您的组织复制 SAS URL。 此 URL 是用于组织的 Microsoft 云中的 Azure 存储位置的网络 URL 和共享访问签名 (SAS) 密钥的组合。 此项为你提供将 PST 文件上载到 Azure 存储位置所需的权限。 将该文件保存到第2步和第3步中您已将其他信息复制到的同一文件中。 如前面所述, 采取预防措施来保护 SAS URL。 
  
> [!IMPORTANT]
> 您必须使用 azure AzCopy 版本5.0 成功将 PST 文件上载到 Azure 存储位置。 将 PST 文件导入到 Office 365 不支持 AzCopy 工具的较新版本。 按照本步骤中的过程操作, 确保从 "**上载文件**" 页面下载 AzCopy 工具。 
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 使用 office 365 组织中的管理员帐户凭据登录 Office 365。
    
3. 在左窗格中, 单击 "**数据管理**", 然后单击 "**导入**"。
    
4. 在“导入”**** 页上，单击“转到导入服务”****。
    
5. 在 "将**数据导入到 Office 365** " 页上, 单击](media/ITPro-EAC-AddIcon.gif)"**新建作业** ![添加图标", 然后单击 "**上载电子邮件 (PST 文件)**"。
    
6. 在第2步中的 "**通过网络上载文件**" 页上, 单击 "**显示网络上载 SAS URL**"。
    
7. 显示 URL 后, 将其复制并保存在保存其他密钥的文件中。 请务必复制整个 URL。 
    
8. 在步骤3中, 单击 **"下载 azure AzCopy 工具**" 以下载并安装 azure AzCopy 工具。 
    
9. 在弹出的窗口中，单击“运行”**** 来安装 Azure AzCopy 工具。 
    
    > [!IMPORTANT]
    > 请务必在运行64位 Windows 的计算机`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`上的默认位置安装 Azure AzCopy 工具。 这是因为当您在步骤5中运行 o365importtool.zip 时, 它会在此位置中查找 AzCopy 工具。 
  
10. 安装 Azure AzCopy 工具后, 单击 "**下载 Office 365 数据加密和导入工具**"。
    
11. 在弹出窗口中, 单击 "**保存** \> **另存为**", 将 o365importtool.zip 文件保存到本地计算机上的文件夹中。 
    
12. 提取 O365ImportTool.zip 文件。
    
13. 单击 "**取消**" 以关闭 "**通过网络上载文件**" 页面。 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>步骤 5: 将 PST 文件加密并上载到 Office 365

完成步骤1到步骤4后, 即可使用 o365importtool.zip 工具将 PST 文件加密并上载到 Office 365。 此工具对您的 PST 文件进行加密, 然后将其上载并存储在 Microsoft 云中的 Azure 存储位置中。 若要完成此步骤，PST 文件必须位于您的组织中的文件共享或文件服务器中。 这在下面的过程中称为源目录。 每次运行 O365ImportTool.exe 工具时，您将可以指定一个不同的源目录。 
  
1. 在您的本地计算机上打开命令提示符。
    
2. 转到您在步骤 4 中安装 O365ImportTool.exe 工具的目录。
    
3. 运行以下命令, 将 PST 文件加密并上载到 Office 365。
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    下表描述了各个参数及其所需值。请注意，在前面的步骤中获取的信息会用在这些参数的值中。
    
    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |指定组织中包含将上载到 Office 365 的 PST 文件的源目录。  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |指定 Azure RMS 服务的许可位置。 使用您在步骤 3 `LicensingIntranetDistributionPointUrl`中获取的属性的值。 请务必将此参数的值括在双引号 ("") 中  <br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |指定你的 Azure RMS 组织的标识。 使用您在步骤 3 `BPOSId`中获取的属性的值。  <br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |指定您在步骤 2 中获得的对称密钥。 请务必用双引号 (" ") 引住此参数的值。  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |指定您通过网络上载 PST 文件还是将它们传送到硬盘上。 该值`upload`指示你正在通过网络上传文件。 该值`drive`指示你要在硬盘驱动器上传送 pst。  <br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |指定要将 PST 文件上载到的 Office 365 中的目标;这是你的组织的 Azure 存储位置。 此参数的值由您在步骤4中复制的 SAS URL 中的网络上载 URL 组成。 请务必用双引号 (" ") 引住此参数的值。  <br/><br/> **提示:** Optional您可以在 Azure 存储位置指定一个子文件夹, 将加密的 PST 文件上载到。 为此, 可在网络上载 URL 中添加子文件夹位置 (在 "ingestiondata" 之后)。 第一个示例未指定子文件夹;这意味着 pst 将被上载到 Azure 存储位置的根 (名为*ingestiondata* )。 第二个示例将 PST 文件上载到 Azure 存储位置中的一个子文件夹 (名为*EncryptedPSTs* )。           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> 或  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |为你的组织指定 SAS 密钥。 此参数的值由您在步骤4中复制的 sas URL 中的 sas 密钥组成。 请注意, sa 密钥中的第一个字符是问号 ("？")。 请务必用双引号 (" ") 引住此参数的值。  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |此可选开关指定递归模式, 以便 o365importtool.zip 工具将复制位于由`/srcdir:`参数指定的源目录中的子文件夹中的 pst 文件。  <br/><br/> **注意:** 如果包含此开关, 则在上载后, 在 Azure 存储位置中, 子文件夹中的 PST 文件将具有不同的文件路径。 您必须在您在步骤 7 中创建的 CSV 文件中指定确切的文件路径名。           | `/recurse` <br/> |
   
    以下是对每个参数使用实际值的 O365ImportTool.exe 工具的语法示例：
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    运行该命令后，显示的状态消息会显示对 PST 文件进行加密和上载的进度。最终状态消息显示已成功加密并上载的文件的总数。  
    
    > [!TIP]
    > 在成功运行 O365ImportTool.exe 命令并验证所有参数都正确后，将命令行语法副本保存到您复制在前面步骤中获得的信息所使用的相同（安全）文件中。 然后, 您可以在每次运行 o365importtool.zip 工具以将 PST 文件加密并上载到 Office 365 时, 在命令提示符下复制并粘贴此命令。 您可能需要更改的唯一值是`/srcdir:`和`/upload-dest:`参数的值。 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Optional步骤 6: 查看已上载到 Office 365 的 PST 文件的列表

作为可选步骤, 您可以安装并使用 Microsoft Azure 存储资源管理器 (它是一个免费的开源工具), 以查看已上载到 Azure blob 的 PST 文件的列表。 为此, 有以下三个很合理的原因:
  
- 验证组织中的共享文件夹或文件服务器中的 PST 文件是否已成功上载到 Azure blob。

- 验证 PST 文件是否已加密。 加密的 pst 文件将`.pfile`扩展名追加到 PST 文件名;例如, `pilarp.pst.pfile`。
    
- 验证上载到 Azure blob 的每个 PST 文件的文件名 (和子文件夹路径名)。 当您在下一步中创建 PST 映射文件时，这确实非常有用，因为您必须为每个 PST 文件指定文件夹路径名和文件名。 验证这些名称可以帮助减少 PST 映射文件中的潜在错误。
    
Microsoft Azure 存储资源管理器处于预览阶段。 
  
 > [!IMPORTANT]
>  无法使用 Azure 存储资源管理器上传或修改 PST 文件。 将 PST 文件导入到 Office 365 的唯一受支持的方法是使用 AzCopy。 此外, 也不能删除已上载到 Azure blob 的 PST 文件。 如果尝试删除 PST 文件，将看到提示没有所需权限的错误消息。 请注意, 所有 PST 文件都将自动从 Azure 存储区域中删除。 If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created. 
  
若要安装 azure 存储资源管理器并连接到 Azure 存储区, 请执行以下操作:
  
1. 下载并安装[Microsoft Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
2. 启动 Microsoft Azure 存储资源管理器, 在左窗格中右键单击 "**存储帐户**", 然后单击 "**连接到 Azure 存储**"。 
    
    ![右键单击 "存储帐户", 然后单击 "连接到 Azure 存储"](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. 在 "**连接到 Azure 存储**" 下的框中, 粘贴您在步骤4中获取的 SAS URL, 然后单击 "**下一步**"。 
    
    ![将 SAS URL 粘贴到 "连接到 Azure 存储" 页上的框中](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. 在 "**连接摘要**" 页上, 您可以查看连接信息, 然后单击 "**连接**"。 
    
5. 在 "**存储帐户**" 下, 展开 " **(服务 sa)** " 节点, 然后展开 " **Blob 容器**" 节点。 
    
6. 右键单击“ingestiondata”****，然后单击“打开 Blob 容器编辑器”****。
    
    ![右键单击 ingestiondata，然后单击“打开 Blob 容器编辑器”](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    将显示 Azure 存储区域, 其中包含您在步骤5中上载的 PST 文件的列表。
    
    ![Azure 存储资源管理器显示你上载的 PST 文件的列表](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. 使用 Microsoft Azure 存储资源管理器完成后, 右键单击 " **ingestiondata**", 然后单击 "**分离**" 断开与 Azure 存储区域的连接。 否则，下次尝试附加时您会收到错误消息。 
    
    ![右键单击“引入”，然后单击“分离”以从 Azure 存储区域断开连接](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>步骤 7: 创建 PST 导入映射文件

将 pst 文件加密并上载到 Office 365 组织的 Azure 存储位置之后, 下一步是创建一个逗号分隔值 (CSV) 文件, 该文件指定要将 PST 文件导入到哪些用户邮箱。 在下一步中，创建 PST 导入作业时，将提交此 CSV 文件。
  
1. [下载 PST 导入映射文件的副本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。 
    
2. 打开或将 CSV 文件保存到您的本地计算机。下面的示例显示已完成的 PST 导入映射文件（在记事本中打开）。使用 Microsoft Excel 编辑 CSV 文件变得容易得多。
    
    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst.pfile,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst.pfile,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,donh.pst.pfile,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst.pfile,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,pilarp.pst.pfile,pilarp@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,pilarp_archive.pst.pfile,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,tonyk.pst.pfile,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,tonyk_archive.pst.pfile,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,zrinkam.pst.pfile,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,zrinkam_archive.pst.pfile,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    该 CSV 文件的第一行（或者说标题行）列出了 PST 导入服务将用于将 PST 文件导入到用户邮箱中的参数。 每个参数名称都用逗号分隔开。 标题行下的每一行代表将 PST 文件导入到特定邮箱所对应的参数值。 您将需要用一行来对应每个要导入到用户邮箱中的 PST 文件。 一定要用实际数据替换映射文件中的占位符数据。
    
    > [!NOTE]
    > 不要更改标题行中的任何内容，包括 SharePoint 参数；这些内容会在 PST 导入过程中被忽略。 
  
3. 使用下表中的信息来填充附有所需信息的 CSV 文件。
    
    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定要将数据导入到的 Office 365 服务。 若要将 PST 文件导入到用户`Exchange`邮箱, 请使用。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |指定在第5步中将 PST 文件上载到的 Azure 存储位置中的文件夹位置。  <br/>  如果在第5步中的`/upload-dest:`参数中未将可选子文件夹名称包含在网络 URL 中, 则在 CSV 文件中将此参数留空。 如果包含子文件夹名称, 请在此参数中指定它。 此参数的值区分大小写。 无论采用哪种方式, 都*不要*在`FilePath`参数的值中包含 "ingestiondata"。  <br/> <br/>**重要说明:** 如果在步骤5的`/upload-dest:`参数中的 SAS URL 中包含可选子文件夹名称, 则文件路径名称的大小写必须与您使用的大小写相同。 例如, 如果您在步骤`EncryptedPSTs` 5 中用于子文件夹名称, 然后在 CSV `encryptedpsts`文件中`FilePath`的参数中使用, 则 PST 文件的导入将失败。 请务必在两个实例中使用相同的大小写。           |（保留为空白）  <br/> 或  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |指定要导入到用户邮箱的 PST 文件的名称。  此参数的值区分大小写。 由于已对上载到 Azure 存储位置的 PST 文件进行加密, 因此会`.pfile`将扩展名添加到 PST 文件名中。 您必须将`.pfile`扩展名添加到 CSV 文件中的 PST 文件的名称。  <br/><br/> **重要说明:** CSV 文件中的 pst 文件名的大小写必须与上传到第5步中的 Azure 存储位置的 pst 文件相同。 例如, 如果在 CSV 文件`annb.pst.pfile`的`Name`参数中使用, 但实际的 pst 文件的名称是`AnnB.pst`, 则该 pst 文件的导入将失败。 请确保 CSV 文件中的 PST 名称使用与实际 pst 文件相同的大小写。           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |指定要将 PST 文件导入到其中的邮箱的电子邮件地址。   <br/> 若要将 PST 文件导入到非活动邮箱, 您必须为此参数指定邮箱 GUID。 若要获取此 GUID, 请在 Exchange Online 中运行以下 PowerShell 命令:`Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid` <br/><br/> **注意:** 在某些情况下, 您可能有多个邮箱具有相同的电子邮件地址, 其中一个邮箱是活动邮箱, 另一个邮箱处于软删除 (或非活动) 状态。 在这些情况下, 您可以指定邮箱 GUID, 以唯一标识要将 PST 文件导入到的邮箱。 若要获取活动邮箱的此 GUID, 请运行以下 PowerShell 命令`Get-Mailbox - <identity of active mailbox> | FL Guid`:。 若要获取软删除 (或非活动) 邮箱的 GUID, 请运行以下命令`Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`           | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要将 PST 文件导入到用户的存档邮箱。 有两个选项：  <br/> **FALSE**将 PST 文件导入到用户的主邮箱。  <br/> **TRUE**将 PST 文件导入到用户的存档邮箱。  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/><br/> **注意:** 若要将 PST 文件导入到其主邮箱是本地邮箱的用户的基于云的存档邮箱, 只需为此参数指定**TRUE** , 并为该`Mailbox`参数指定用户的内部部署邮箱的电子邮件地址。           | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定将 PST 文件导入到的邮箱文件夹。  <br/>  如果将此参数留空, 则会将 PST 导入到位于邮箱根级别 (与 "收件箱" 文件夹和其他默认邮箱文件夹相同的级别) 的名为 "**导入**" 的新文件夹中。  <br/>  如果指定`/`, 则 PST 文件中的项目将直接导入到用户的 "收件箱" 文件夹中。  <br/>  如果指定`/<foldername>`, 则 PST 文件中的项目将被导入到名为* \<"\> *文件夹名称" 的子文件夹中。 例如, 如果使用`/ImportedPst`, 则会将项目导入到名为**ImportedPst**的子文件夹中。 此子文件夹将位于用户的 "收件箱" 文件夹中。  <br/><br/> **提示:** 请考虑运行几个测试批处理, 以试用此参数, 以便您可以确定将 pst 文件导入到的最佳文件夹位置。           |（保留为空白）  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此可选参数指定用于以 ANSI 文件格式导入 PST 文件的代码页的数值。 此参数用于从中文、日语和朝鲜语 (CJK) 组织导入 PST 文件, 这是因为这些语言通常使用双字节字符集 (DBCS) 进行字符编码。 如果未使用此参数导入使用 DBCS 作为邮箱文件夹名称的语言的 PST 文件, 则在导入这些文件夹名称时通常会出现乱码。 有关要用于此参数的受支持值的列表, 请参阅[代码页标识符](https://go.microsoft.com/fwlink/p/?LinkId=328514)。  <br/><br/> **注意:** 如前所述, 这是一个可选参数, 无需将其包含在 CSV 文件中。 或者, 可以将其包含在一个或多个行中, 并为其保留值为空。           |（保留为空白）  <br/> 或  <br/>  `932`(ANSI/OEM 日语的代码页标识符)  <br/> |
    | `SPFileContainer` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
    | `SPManifestContainer` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
    | `SPSiteUrl` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>步骤 8：在 Office 365 中创建 PST 导入作业

最后一步是在 Office 365 中的 "导入服务" 中创建 PST 导入作业。 如前所述，您将提交在步骤 7 中创建的 PST 导入映射文件。 创建新作业后, 导入服务将使用映射文件中的信息来取消加密, 并将在步骤5中上载到 Office 365 的 PST 文件导入到指定的用户邮箱。 
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 使用 office 365 组织中的管理员帐户凭据登录 Office 365。
    
3. 在左窗格中, 单击 "**数据管理**", 然后单击 "**导入**"。
    
4. 在“导入”**** 页上，单击“转到导入服务”****。
    
5. 在 "将**数据导入到 Office 365** " 页上, 单击](media/ITPro-EAC-AddIcon.gif)"**新建作业**![添加图标", 然后单击 "**上载电子邮件 (PST 文件)**"。
    
6. 在“通过网络上载文件”**** 页面中，依次选中“我已完成上载我的文件”**** 和“我可以访问映射文件”**** 复选框，然后单击“下一步”****。  
    
7. 为 PST 导入作业键入一个名称，然后单击“下一步”****。
    
8. 单击 "**添加** ![添加](media/ITPro-EAC-AddIcon.gif) " 图标, 选择您在步骤7中创建的 PST 映射文件。 
    
9. CSV 文件的名称显示在列表中之后，选中它，然后单击“验证”**** 来检查 CSV 文件中的错误。  
    
    > [!NOTE]
    > 如前所述, 当加密 pst 文件时, 会将`.pfile`扩展名追加到 pst 文件名。 您必须将`.pfile`扩展名添加到 CSV 文件中的 PST 文件的名称。 如果不这样做，该 CSV 文件的验证将会失败。 
  
    CSV 文件必须经过成功验证才能创建 PST 导入作业。如果验证失败，请单击“状态”**** 列中的“无效”**** 链接。PST 导入映射文件的副本处于打开状态，文件中的每一行会提供失败的错误消息。 
    
10. 当成功验证 PST 映射文件时，请阅读条款和条件文档，然后单击复选框。
    
11. 单击“完成”**** 提交作业。 
    
    该作业显示在 "将**数据导入到 Office 365** " 页上的 PST 导入作业列表中。 
    
12. 选择该作业, 然后****![单击 "刷新](media/O365-MDM-Policy-RefreshIcon.gif)刷新" 图标以更新显示在详细信息窗格中的状态信息。 
    
13. 在详细信息窗格中，单击“查看详细信息”**** 以获取所选作业的最新状态。 
 
## <a name="more-information"></a>详细信息

- 为什么要将 PST 文件导入 Office 365？
    
  - 这是将组织的电子邮件迁移到 Office 365 的一种不错的方法。
    
  - 通过允许您执行以下操作，有助于满足您的组织的合规性需求：
    
  - 启用存档邮箱为用户提供额外的邮箱存储空间。
    
  - 将邮箱置于保留状态以保留内容。
    
  - 使用 Microsoft 电子数据展示工具搜索邮箱中的内容。
    
  - 使用保留策略控制邮箱保留内容的时长。
    
  - 在 Office 365 审核日志中搜索与邮箱相关的事件。
    
  - 有助于防止数据丢失。 导入到 Office 365 邮箱的 PST 文件可继承 Exchange Online 的高可用性功能, 而不是将数据存储在用户的计算机上。
    
  - 用户在任意设备上都可以使用数据，因为数据存储在云中。
    
- 下面是在步骤2、3和4中获取的键、id 和 url 的示例。 此示例还包含在 o365importtool.zip 工具中运行的命令的语法, 用于将 PST 文件加密并上载到 Office 365。 一定要采取预防措施来保护这些文件，就像保护密码或其他与安全相关的信息一样。
    
  ```
  Symmetric key: l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=

  BPOSId: 42745b33-2a5c-4726-8a2a-ca43caa0f74b

  LicensingIntranetDistributionPointUrl (RMS licensing location): https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing
  
  SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D
  
  O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL from the SAS URL> /upload-destSAS:<SAS key from the SAS URL>
  
  EXAMPLES
  
  This example uploads PST files to the root of the Azure storage location:

  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  
  This example uploads PST files to a subfolder named EncryptedPSTs  in the Azure storage location:
  
  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  ```

- 如前所述, Office 365 导入服务在将 PST 文件导入邮箱后, 将启用保留挂起设置 (无限期)。 这意味着*RentionHoldEnabled*属性设置为`True` , 因此不会处理分配给邮箱的保留策略。 这使邮箱所有者可以通过阻止删除或存档策略来删除或存档较旧的邮件来管理新导入的邮件。 若要管理此保留挂起, 可以执行以下步骤: 
    
  - 在特定时间段后, 可以通过运行`Set-Mailbox -RetentionHoldEnabled $false`命令关闭保留挂起。 有关说明, 请参阅[将邮箱放在保留挂起](https://go.microsoft.com/fwlink/p/?LinkId=544749)中。
    
  - 您可以配置保留挂起, 使其在将来某个日期处于关闭状态。 可以通过运行`Set-Mailbox -EndDateForRetentionHold <date>`命令来执行此操作。 例如, 假定今天的日期为2016年6月1日, 并且您希望在30天内关闭保留挂起功能, 请运行以下命令: `Set-Mailbox -EndDateForRetentionHold 7/1/2016`。 在这种情况下, 您会将*RentionHoldEnabled*属性设置`True`为。 有关详细信息, 请参阅[设置邮箱](https://go.microsoft.com/fwlink/p/?LinkId=150317)。
    
  - 您可以更改已分配给邮箱的保留策略的设置, 以便不会立即删除导入的旧项目, 也不会将其移动到用户的存档邮箱。 例如, 您可以延长分配给邮箱的删除或存档策略的保留期限。 在这种情况下, 您可以在更改保留策略的设置后关闭邮箱的保留挂起。 有关详细信息, 请参阅为[Office 365 组织中的邮箱设置存档和删除策略](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。

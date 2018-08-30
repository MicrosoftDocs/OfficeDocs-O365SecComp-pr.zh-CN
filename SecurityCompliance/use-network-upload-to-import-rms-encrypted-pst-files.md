---
title: 使用网络上载将 RMS 加密的 PST 文件导入到 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: 了解如何使用网络上载到 Office 365 中的用户邮箱导入 RMS 加密 PST 文件。
ms.openlocfilehash: 6460512e2d6085df684841248dc286d39dbd9d87
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526020"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>使用网络上载将 RMS 加密的 PST 文件导入到 Office 365

**本文是针对管理员。您试图将 PST 文件导入到您自己的邮箱？请参阅[导入电子邮件、 联系人和日历从 Outlook.pst 文件](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
使用网络上载到用户邮箱导入 PST 文件的选项和导入 Office 365 服务。网络上载意味着您在 Microsoft 云中的临时存储区上载 PST 文件。然后 Office 365 导入服务将复制的 PST 文件从存储区域到目标用户邮箱。导入服务的新功能，可以被上载并存储在 Microsoft 云之前加密 PST 文件。正在导入到用户邮箱时，这些文件将不加密。 
  
下面是用于加密和 PST 文件导入 Office 365 邮箱所需的步骤：
  
[步骤 1：对 PST 导入设置 Azure 权限管理 ](#step-1-set-up-azure-rights-management-for-pst-import)

[步骤 2：生成 PST 导入的加密密钥](#step-2-generate-an-encryption-key-for-pst-import)

[步骤 3： 获取 RMS 租户 ID 和授权的 URL](#step-3-obtain-rms-tenant-id-and-licensing-url)

[步骤 4： 下载 PST 导入工具和复制 SAS URL](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[步骤 5： 加密和 PST 文件上传到 Office 365](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[（可选）步骤 6： 查看列表的 PST 文件上载到 Office 365](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[步骤 7： 创建 PST 导入映射文件](#step-7-create-the-pst-import-mapping-file)

[步骤 8：在 Office 365 中创建 PST 导入作业](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> 您必须执行步骤 1 到步骤 4 仅执行一次设置和配置您的组织进行加密和 PST 文件导入 Office 365 邮箱。执行这些步骤后，按照步骤 5 到步骤 8 您想要加密、 上载和导入 PST 文件一批每的次。 
  
有关将数据导入到 Office 365 的详细信息，请参阅[Overview of 导入您的组织 PST 文件迁移到 Office 365](importing-pst-files-to-office-365.md)。
  
## <a name="before-you-begin"></a>准备工作

- 您必须为其分配导入导出邮箱角色在 Exchange Online 到 Office 365 邮箱导入 PST 文件。默认情况下，此角色不分配给任何角色组在 Exchange Online。您可以向组织管理角色组中添加邮箱导入导出角色。或者，您可以创建新的角色组、 分配的邮箱导入导出角色中，然后将自己添加为成员。有关详细信息，请参阅"添加角色向角色组"或"创建角色组"部分中[管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
    
    此外，若要创建导入作业 Office 365 安全性&amp;必须满足合规中心，下列选项之一：
    
  - 您必须分配 Mail Recipients 角色在 Exchange Online。默认情况下，此角色分配给组织管理和 Recipient Management 角色组。
    
    或
    
  - 您必须是 Office 365 组织中的全局管理员。
    
  > [!TIP]
  > 请考虑在 Exchange Online 的专门用于将 PST 文件导入到 Office 365 中创建新的角色组。最小的导入 PST 文件所需的权限级别，将邮箱导入导出和 Mail Recipients 角色分配给新角色组中，，然后添加成员。 
  
- 您需要存储要导入到 Office 365 上的文件服务器或在组织中的共享的文件夹的 PST 文件。在步骤 5 中，您将运行 Office 365 ImportTool，这将加密并上载该文件服务器上存储或共享到 Office 365 的文件夹的 PST 文件。
    
- 此过程涉及复制并保存一份加密密钥、 存储键和大量标识键和 Url。此信息将用于在步骤 5 中加密和上传 PST 文件。请确保采取预防措施来保护这些只，如将保护密码或其他安全相关的信息。例如，您可能会将其保存到受密码保护的 Microsoft Word 文档或将其保存到加密的 USB 驱动器。请参阅有关这些项、 Id、 和 Url 示例[详细信息](#more-information)部分。 
    
- 您可以向 Office 365 中的非活动邮箱导入 PST 文件。执行此操作通过指定中的非活动邮箱的 GUID `Mailbox` PST 导入映射文件中的参数。有关详细信息，请参阅[步骤 7](#step-7-create-the-pst-import-mapping-file) 。 
    
- 在 Exchange 混合部署，您可以 PST 文件导入为其主邮箱位于内部部署用户的基于云的存档邮箱。通过执行以下 PST 导入映射文件中的执行此操作：
    
  - 指定用户的内部部署邮箱中的电子邮件地址`Mailbox`参数。 
    
  - 指定**TRUE**值在`IsArchive`参数。 
    
    有关详细信息，请参阅[步骤 7](#step-7-create-the-pst-import-mapping-file) 。 
    
- PST 文件导入到 Office 365 邮箱后，设置为该邮箱保留挂起是无限期的持续时间内，打开的。这意味着关闭保留挂起或设置要关闭保留日期之前，将不会处理分配给邮箱的保留策略。为什么做的原因？如果旧导入到邮箱的邮件，它们可能被永久删除 （清除） 由于其保留期已过期基于配置为该邮箱的保留设置。将邮箱放在保留挂起将给邮箱所有者时间来管理这些新导入的邮件或授予时间更改邮箱的保留设置。请参阅有关管理保留挂起的建议的[详细信息](#more-information)部分。 
    
- 如果您不需要加密 PST 文件，将它们上载到 Office 365 之前，请参阅[使用网络上载以导入 PST 文件迁移到 Office 365](use-network-upload-to-import-pst-files.md)。
    
- 有关使用网络上载到 Office 365 导入 PST 文件的常见问题进行了问题，请参阅[有关导入 PST 文件迁移到 Office 365 的常见问题](faqimporting-pst-files-to-office-365.md)。
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>步骤 1：对 PST 导入设置 Azure 权限管理 

PST 导入使用 Office 365 中的 Azure 权限管理 (Azure RMS) 服务提供的加密功能。这样可以将其上载到 Office 365 之前加密 PST 文件。 
  
PST 导入的配置 Azure RMS 包括三个步骤：
  
- [激活 Azure RMS](#activate-azure-rms)
    
- [配置 Exchange 在 Online RMS](#configure-rms-in-exchange-online)
    
- [安装 Active Directory RMS 客户端](#install-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>激活 Azure RMS

Azure RMS 禁用默认情况下，但您或您的组织中的其他管理员可能已激活它。按照上[激活 Azure 权限管理](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)来安装和激活 Azure DRM 的说明。
  
### <a name="configuring-rms-in-exchange-online"></a>配置 Exchange 在 Online RMS

已激活的权限管理服务后下, 一步是在 Exchange Online 使用 Azure RMS 设置信息权限管理 (IRM)。有关详细信息，请参阅[配置 IRM 以使用 Azure 权限管理](https://go.microsoft.com/fwlink/p/?LinkId=394816)。
  
1. [连接到 Exchange Online 使用远程 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554 )。
    
2. 运行以下命令来设置 RMS 密钥共享 URL。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    使用下表确定正确的 RMS 密钥共享您组织所处位置。
    
    |**位置**|**RMS 关键共享位置**|
    |:-----|:-----|
    |北美  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |欧盟  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |亚洲  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |南美洲  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |政府用 Office 365（政府社区云）  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup> 只有已购买政府用 Office 365 SKU（政府社区云）的客户才应使用此 RMS 密钥共享位置。 
  
    例如，此命令会配置的 RMS Online 关键共享位置在 Exchange Online 为客户位于北美。
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. 运行以下命令以受信任发布域 (TPD) 从 RMS Online 导入到您的 Office 365 组织。 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    TPD 包含在您的组织中使用 RMS 功能所需的设置，包括加密 PST 文件。  
    
4. 运行以下命令来为 Office 365 组织中启用 IRM。
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>安装 Active Directory RMS 客户端

本节中的最后一步是下载权限管理服务 (RMS) 客户端 2.1。本软件有助于保护 Azure RMS 访问并保护流经使用 Azure RMS.安装的应用程序将用于加密和上载 PST 文件中的步骤 5 中的同一台计算机上的 RMS 客户端的信息。 
  
1. 下载[权限管理服务客户端 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396)。
    
2. 运行 Active Directory 权限管理服务客户端 2.1 向导来安装客户端。

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>步骤 2：生成 PST 导入的加密密钥

您已设置 Azure RMS 后下, 一步是生成加密密钥将用于加密的 PST 文件上载到 Office 365 的 （称为对称密钥）。将作为服务主体 Azure Active Directory 中添加 PST 导入服务来执行此操作。作为服务主体将允许 PST 导入服务进行身份验证直接与 Azure Active Directory 上传时添加此应用程序加密 PST 文件迁移到步骤 5 中的 Azure 的存储位置。
  
1. 启动 Windows powershell 的 Azure Active Directory 模块。
    
2. 运行下面的命令以连接到 Microsoft Online 服务。
    
    ```
    Connect-MsolService
    ```

3. 在 Office 365 组织中的管理员帐户输入凭据，然后单击**确定**。
    
4. 运行以下命令以生成加密密钥（也称作“对称密钥”）。您将通过创建新的 PST 加密主体来执行此操作。
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    系统将显示新 PST 加密主体的对称密钥和属性。
    
    ![复制并保存显示的对称密钥](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. 将对称密钥复制到文本或 Word 文件中。如前所述，一定要采取预防措施来保护此文件。因为这是显示对称密钥的唯一时机，所以您也可以考虑对此窗口拍摄屏幕快照并将其保存到同一文件中。  
    
    > [!IMPORTANT]
    > 创建 PST 加密主体后，您将无法通过使用 **Get-MsolServicePrincipal** cmdlet 检索对称密钥。这就是保存该密钥非常重要的原因。 
  
将保留 Azure Active Directory 模块用于 Windows PowerShell 的打开和连接到 Microsoft Online 服务。您将在下一步中此窗口中运行命令。

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>步骤 3： 获取 RMS 租户 ID 和授权的 URL

下一步是获取租户 ID 和许可位置组织的 Azure RMS 服务 URL。复制并将此信息保存到包含从步骤 2 的对称密钥的同一文件。ID 和 URL 将用于在步骤 5 中加密 PST 文件。
  
1. 在 Azure Active Directory 模块 （这连接到 Microsoft Online 服务） 的 Windows powershell，运行以下命令以连接到 Office 365 组织中的 Azure RMS 服务。
    
    ```
    Connect-AadrmService 
    ```

2. Office 365 组织中的管理员帐户输入凭据，然后单击**确定**。
    
3. 运行以下命令以显示 Office 365 组织中的 Azure RMS 服务的租户 ID。
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    复制和保存的值`BPOSId`属性。 
    
4. 运行以下命令以显示为 Azure RMS 服务的许可位置。
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    复制和保存的值`LicensingIntranetDistributionPointUrl`属性。 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>步骤 4： 下载 PST 导入工具和复制 SAS URL

现在，您已配置 Azure RMS 并获得需要加密 PST 文件的 Id 下, 一步是下载并安装到 Office 365 进行加密的步骤 5 中将运行并上载 PST 文件的工具。这些工具是 Azure AzCopy 工具和 Office 365 数据加密工具。您还将为您的组织复制 SAS URL。此 URL 是 Microsoft 云的组织和共享访问签名 (SA) 键中的 Azure 存储位置的网络 URL 的组合。此项为您提供所需的权限将 PST 文件上载到 Azure 存储位置。将其保存到相同的文件，您已在步骤 2 和步骤 3 中复制到的其他信息。如前面所述，采取预防措施来保护 SAS URL。 
  
> [!IMPORTANT]
> 您需要使用 Azure AzCopy 5.0 成功将 PST 文件上载到 Azure 存储位置。将 PST 文件导入到 Office 365 不支持较新版本的 AzCopy 工具。请务必在此步骤中的过程从**上载文件通过网络**页上下载 AzCopy 工具。 
  
1. 转到[https://protection.office.com](https://protection.office.com)。
    
2. 登录到 Office 365 使用 Office 365 组织中的管理员帐户的凭据。
    
3. 在左窗格中，单击**数据管理**，然后单击**导入**。
    
4. 在**导入**页上，单击**转到导入服务**。
    
5. 在**到 Office 365 的导入数据**页上，单击**新建作业**![添加图标](media/ITPro-EAC-AddIcon.gif)，，然后单击**上载电子邮件 （PST 文件）**。
    
6. 在**将通过网络的文件上载**页上的步骤 2 中，单击**显示网络上载 SAS URL**。
    
7. 显示 URL 后，将其复制，并将其保存在文件中保存其他注册表项的位置。请务必将复制的完整 URL。 
    
8. 在步骤 3 中，单击**下载 Azure AzCopy 工具**以下载并安装 Azure AzCopy 工具。 
    
9. 在弹出窗口中，单击**运行**以安装 Azure AzCopy 工具。 
    
    > [!IMPORTANT]
    > 请务必在默认位置，即安装 Azure AzCopy 工具`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`的计算机上运行 64 位 Windows。这是因为您在步骤 5 中运行 O365ImportTool.exe，当它查找该位置的 AzCopy 工具。 
  
10. 您已安装 Azure AzCopy 工具后，单击**下载 Office 365 数据加密和导入工具**。
    
11. 在弹出窗口中，单击**保存** \> **另存为**本地计算机上将 O365ImportTool.zip 文件保存到文件夹。 
    
12. 提取 O365ImportTool.zip 文件。
    
13. 单击**取消**以关闭**上载文件通过网络**页。 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>步骤 5： 加密和 PST 文件上传到 Office 365

完成步骤 1 到步骤 4 之后，就可以使用 O365ImportTool.exe 工具进行加密和将 PST 文件上载到 Office 365。此工具加密 PST 文件，然后上载并将其存储在云中的 Microsoft Azure 的存储位置。若要完成此步骤，PST 文件必须位于文件共享或组织中的文件服务器。这就是在下面的过程的源目录。每次运行 O365ImportTool.exe 工具，您将可以指定一个不同的源目录。 
  
1. 在您的本地计算机上打开命令提示符。
    
2. 转到您在步骤 4 中安装 O365ImportTool.exe 工具的目录。
    
3. 运行以下命令来加密和将 PST 文件上载到 Office 365。
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    下表描述了各个参数及其所需值。请注意，在前面的步骤中获取的信息会用在这些参数的值中。
    
    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |指定包含 PST 文件将上载到 Office 365 组织中的源目录。  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |指定 Azure RMS 服务的许可位置。使用的值`LicensingIntranetDistributionPointUrl`在步骤 3 中获取的属性。请务必包围双引号与此参数的值 ("")<br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |指定 Azure RMS 组织的标识。使用的值`BPOSId`在步骤 3 中获取的属性。<br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |在步骤 2 中指定您获取的对称密钥。请务必包围双引号与此参数的值 ("")。  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |指定是否通过网络上载 PST 文件或将它们发送硬盘驱动器上。值`upload`指示通过网络上载文件。值`drive`指示，您将在硬盘驱动器上传送 Pst。<br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |指定在其中 PST 文件将上载到; Office 365 中的目标这是您的组织的 Azure 存储位置。此参数的值包含您在步骤 4 中复制的 SAS URL 中的网络上载 URL。请务必包围双引号与此参数的值 ("")。<br/><br/> **提示：**（可选）Azure 的存储位置上载到加密的 PST 文件中，您可以指定子文件夹。通过在网络上载 URL 添加 （之后"ingestiondata") 的子文件夹位置执行此操作。第一个示例不指定子文件夹;这意味着 Pst 将上载到根目录 （名为*ingestiondata* ） Azure 的存储位置。第二个示例中的 Azure 的存储位置上载到子文件夹 （名为*EncryptedPSTs* ） 的 PST 文件。           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> 或  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |指定您的组织的 SAS 键。此参数的值包含您在步骤 4 中复制的 SAS URL 中的 SAS 键。请注意，在 SAS 注册表项中的第一个字符是一个问号 ("？")。请务必包围双引号与此参数的值 ("")。  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |此可选开关指定递归模式，以便 O365ImportTool.exe 工具会将位于指定源目录中的子文件夹中的 Pst 文件复制`/srcdir:`参数。  <br/><br/> **注意：** 如果包括此开关，子文件夹中的 PST 文件将 Azure 存储位置中具有不同文件路径名，他们正在上载后。您将需要在您在步骤 7 中创建的 CSV 文件中指定的确切文件路径名。           | `/recurse` <br/> |
   
    以下是对每个参数使用实际值的 O365ImportTool.exe 工具的语法示例：
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    运行该命令后，显示的状态消息会显示对 PST 文件进行加密和上载的进度。最终状态消息显示已成功加密并上载的文件的总数。  
    
    > [!TIP]
    > 在成功运行 O365ImportTool.exe 命令并确认所有参数都正确无误后，保存一份同一个复制信息的位置 （安全） 文件的命令行语法获取在前面的步骤。然后可以复制并粘贴在命令提示符处每次您想要运行 O365ImportTool.exe 工具进行加密和将 PST 文件上载到 Office 365 的此命令。您可能需要更改的唯一值是为`/srcdir:`和`/upload-dest:`参数。 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>（可选）步骤 6： 查看列表的 PST 文件上载到 Office 365

作为一个可选步骤，您可以安装和使用 Microsoft Azure 存储浏览器 （这是一个免费的开源工具） 若要查看已上载到 Azure blob PST 文件的列表。有三个良好的原因，若要执行此操作：
  
- 验证 PST 文件从共享的文件夹或组织中的文件服务器已成功上载到 Azure 的 blob。

- 验证 PST 文件进行加密。加密的 PST 文件具有`.pfile`扩展追加到 PST 文件名;例如， `pilarp.pst.pfile`。
    
- 验证每个 PST 文件上载到 Azure blob 的文件名 （和子文件夹路径名如果包括了一个）。正在创建 PST 映射文件的下一步，因为您有时必须指定的文件夹路径名和文件名为每个 PST 文件时，这是非常有用。验证这些名称，可帮助减少 PST 映射文件中的潜在错误。
    
Microsoft Azure 存储 Explorer 正处于预览。 
  
 > [!IMPORTANT]
>  不能使用 Azure 存储资源管理器上载或修改 PST 文件。将 PST 文件导入到 Office 365 唯一受支持的方法是使用 AzCopy。此外，您不能删除已上载到 Azure blob 的 PST 文件。如果尝试删除 PST 文件，您会收到了有关未获得所需的权限的错误。请注意自动从您 Azure 存储区删除所有 PST 文件。如果有任何导入作业正在进行，然后中的所有 PST 文件**ingestiondata**容器中将不删除 30 天后创建的最新的导入作业。 
  
安装 Azure 存储浏览器并连接到 Azure 存储区：
  
1. 下载并安装[Microsoft Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
2. 启动 Microsoft Azure 存储资源管理器，在左窗格中右键单击**存储帐户**，然后单击**连接到 Azure 存储**。 
    
    ![右键单击存储帐户，然后单击连接到 Azure 存储](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. 在**连接到 Azure 存储**下的框中，在步骤 4，粘贴您获得 SAS URL，然后单击**下一步**。 
    
    ![在连接到 Azure 存储页上框中粘贴 SAS URL](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. 在**连接摘要**页中，您可以查看连接信息，然后单击**连接**。 
    
5. **存储帐户**下, 展开 **(服务 SAS)** 节点，然后展开**Blob 容器**节点。 
    
6. 右键单击**ingestiondata**，，，然后单击**打开 Blob 容器编辑器**。
    
    ![右键单击 ingestiondata，然后单击“打开 Blob 容器编辑器”](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    显示的 Azure 存储区，与在步骤 5 中上载的 PST 文件的列表。
    
    ![Azure 存储资源管理器显示你上载的 PST 文件的列表](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. 完成后使用 Microsoft Azure 存储浏览器，右键单击**ingestiondata**，，然后单击**分离**断开 Azure 存储区。否则，您会收到错误的下次尝试附加。 
    
    ![右键单击“引入”，然后单击“分离”以从 Azure 存储区域断开连接](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>步骤 7： 创建 PST 导入映射文件

具有已加密的 PST 文件，并将其上载到 Office 365 组织的 Azure 存储位置后下, 一步是创建逗号分隔值 (CSV) 文件，指定 PST 文件将被导入到哪些用户邮箱。创建 PST 导入作业时，您将提交的下一步此 CSV 文件。
  
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

    标题行，CSV 文件的第一行中，列出 PST 导入服务将用于将 PST 文件导入到用户邮箱的参数。每个参数名称并用逗号分隔。在标题行下的各行代表 PST 文件导入到特定邮箱的参数值。对于每个要导入到用户邮箱的 PST 文件，您将需要一行。请务必映射文件中的占位符数据替换为实际数据。
    
    > [!NOTE]
    > 不要更改标题行中的任何内容，包括 SharePoint 参数；这些内容会在 PST 导入过程中被忽略。 
  
3. 使用下表中的信息来填充附有所需信息的 CSV 文件。
    
    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定数据将导入到的 Office 365 服务。若要为用户邮箱导入 PST 文件，请使用`Exchange`。<br/> | `Exchange` <br/> |
    | `FilePath` <br/> |在您上载 PST 文件迁移到步骤 5 中的 Azure 的存储位置指定的文件夹位置。  <br/>  如果您没有在的网络 URL 中包括的可选子文件夹名称`/upload-dest:`参数在步骤 5 中，将此参数留空 CSV 文件中。如果包括子文件夹名称，则此参数中指定它。此参数的值是区分大小写。两种方法，在的值*不*包括"ingestiondata"`FilePath`参数。<br/> <br/>**重要：** 种情况的文件路径名称必须是相同的大小写，如果在 SAS URL 中包含的可选子文件夹名称使用`/upload-dest:`步骤 5 中的参数。例如，如果您使用`EncryptedPSTs`的子文件夹命名为在步骤 5 中，然后使用`encryptedpsts`的`FilePath`CSV 文件中的参数，PST 文件导入将失败。请务必在这两种情况下使用相同的大小写。           |（保留为空白）  <br/> 或  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |指定将导入到用户邮箱的 PST 文件的名称。此参数的值是区分大小写。上载到 Azure 的存储位置的 PST 文件进行加密，因为`.pfile`扩展名添加到 PST 文件名。您必须添加`.pfile`中 CSV 文件的文件扩展名为 PST 的名称。<br/><br/> **重要：** CSV 文件中的 PST 文件名称的大小写必须与已上载到在步骤 5 中的 Azure 的存储位置的 PST 文件相同。例如，如果您使用`annb.pst.pfile`中`Name`CSV 文件，但实际的 PST 文件的名称中的参数是`AnnB.pst`，该 PST 文件导入将失败。确保 CSV 文件中 PST 的名称，为实际的 PST 文件使用相同的大小写。           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |指定要将 PST 文件导入到其中的邮箱的电子邮件地址。   <br/> 若要导入非活动邮箱 PST 文件，您必须指定此参数的邮箱的邮箱 GUID。若要获取此 GUID，请运行以下 PowerShell 命令在 Exchange Online: Get-mailbox InactiveMailboxOnly<identity of inactive mailbox> | FL Guid` <br/><br/> **Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-mailbox-<identity of active mailbox> | FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-mailbox- <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid           | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要将 PST 文件导入到用户的存档邮箱。有两个选项：<br/> **FALSE**PST 文件导入到用户的主邮箱中。  <br/> **TRUE**将 PST 文件导入到用户的存档邮箱。  <br/>  如果将此参数留空，PST 文件导入到用户的主邮箱。  <br/><br/> **注意：** 若要 PST 文件导入到其主邮箱位于内部部署用户的基于云的存档邮箱中，只需指定此参数**为 TRUE** ，并指定用户的内部部署邮箱的电子邮件地址`Mailbox`参数。           | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定 PST 文件导入到的邮箱文件夹。  <br/>  如果将此参数留空，PST 将导入到新文件夹命名的**导入**位于 （相同级别的收件箱文件夹和其他默认邮箱文件夹） 的邮箱的根级别。  <br/>  如果指定`/`，PST 文件中的项目在导入将直接在用户的收件箱文件夹。  <br/>  如果指定`/<foldername>`，PST 文件中的项目将导入到一个名为子*\<foldername\> * 。例如，如果您使用`/ImportedPst`，项目将导入到名为**ImportedPst**子文件夹。此子文件夹将位于用户的收件箱文件夹中。<br/><br/> **提示：** 考虑运行几个测试批次试验使用此参数，以便您可以确定要导入到 Pst 文件的最佳文件夹位置。           |（保留为空白）  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此可选参数指定要用于导入 PST 文件中的 ANSI 文件格式的代码页的数字值。此参数用于中文、 日语和朝鲜语 (CJK) 的组织中导入 PST 文件，因为这些语言通常用于双字节字符集 (DBCS) 字符编码。如果此参数不用于导入 PST 文件的邮箱文件夹名称中使用 DBCS 的语言，文件夹名称是通常会乱码后会在导入。有关受支持的值用于此参数的列表，请参阅[代码页标识符](https://go.microsoft.com/fwlink/p/?LinkId=328514)。<br/><br/> **注意：** 如上文所述，这是一个可选参数，并且没有要包含在 CSV 文件中。或者，您可以将其包括并保留为空的一个或多个行。           |（保留为空白）  <br/> 或  <br/>  `932`（这是代码页标识符的 ANSI/OEM 日语）  <br/> |
    | `SPFileContainer` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
    | `SPManifestContainer` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
    | `SPSiteUrl` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>步骤 8：在 Office 365 中创建 PST 导入作业

最后一步是创建 Office 365 中导入服务中的 PST 导入作业。如前所述，您将提交您在步骤 7 中创建的 PST 导入映射文件。导入服务创建新的作业后，将取消映射文件中使用的信息的加密和导入指定的用户邮箱的 PST 文件 （您上载到 Office 365 步骤 5 中）。 
  
1. 转到[https://protection.office.com](https://protection.office.com)。
    
2. 登录到 Office 365 使用 Office 365 组织中的管理员帐户的凭据。
    
3. 在左窗格中，单击**数据管理**，然后单击**导入**。
    
4. 在**导入**页上，单击**转到导入服务**。
    
5. 在**到 Office 365 的导入数据**页上，单击**新建作业**![添加图标](media/ITPro-EAC-AddIcon.gif)，，然后单击**上载电子邮件 （PST 文件）**。
    
6. 在**上载文件通过网络**页上单击**我已经完成了上载我文件**和**我有权访问映射文件**，选中框中，，然后单击**下一步**。 
    
7. 为 PST 导入作业中，键入一个名称，然后单击**下一步**。
    
8. 单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)选择在步骤 7 中创建的映射 PST 文件。 
    
9. CSV 文件的名称出现在列表中后，选择它，然后单击**验证**以检查 CSV 文件中的错误。 
    
    > [!NOTE]
    > 与以前所述，PST 文件进行加密时，`.pfile`扩展追加到 PST 文件名。您必须添加`.pfile`中 CSV 文件的文件扩展名为 PST 的名称。否则，验证的 CSV 文件将失败。 
  
    CSV 文件已成功验证创建 PST 导入作业。如果验证失败，请单击**状态**列中的链接**无效**。打开时的 PST 导入映射文件的副本，失败的文件中的各行的错误消息。 
    
10. 当成功验证 PST 映射文件时，请阅读条款和条件文档，然后单击复选框。
    
11. 单击**完成**以提交的作业。 
    
    在**到 Office 365 的导入数据**页上的 PST 导入作业列表中显示该作业。 
    
12. 选择该作业，单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)要更新的详细信息窗格中显示的状态信息。 
    
13. 在详细信息窗格中，单击**查看详细信息**，以获取所选作业的最新状态。 
 
## <a name="more-information"></a>详细信息

- 为什么到 Office 365 导入 PST 文件？
    
  - 它是您组织的电子邮件迁移到 Office 365 的好方法。
    
  - 通过允许您执行以下操作，有助于满足您的组织的合规性需求：
    
  - 启用存档邮箱为用户提供额外的邮箱存储空间。
    
  - 将邮箱置于保留状态以保留内容。
    
  - 使用 Microsoft 电子数据展示工具搜索邮箱中的内容。
    
  - 使用保留策略控制邮箱保留内容的时长。
    
  - 搜索 Office 365 审核日志中的邮箱相关的事件。
    
  - 它有助于防止数据丢失。PST 文件导入到 Office 365 邮箱继承而不是用户的计算机上存储数据的 Exchange Online 的高可用性功能。
    
  - 用户在任意设备上都可以使用数据，因为数据存储在云中。
    
- 下面是一个示例的键、 Id 和步骤 2、 3 和 4 中获得的 Url。此示例还包含 O365ImportTool.exe 工具进行加密中运行和上载 PST 文件到 Office 365 的命令的语法。请确保采取预防措施来保护这些只，如将保护密码或其他安全相关的信息。
    
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

- 如前所述，Office 365 导入服务启用设置 （无限期的持续时间） PST 文件导入到邮箱后保留挂起状态。这意味着*RentionHoldEnabled*属性设置为`True`，以便将不会处理分配给邮箱的保留策略。这可以通过防止删除或较旧的消息进行存档的存档策略管理的新导入的邮件的邮箱所有者时间。下面是一些用于管理此保留挂起时可采取的步骤： 
    
  - 在一段后的时间，则可以关闭保留挂起通过运行`Set-Mailbox -RetentionHoldEnabled $false`命令。有关说明，请参阅[就地保留邮箱保留](https://go.microsoft.com/fwlink/p/?LinkId=544749)。
    
  - 您可以配置保留挂起，以便它已关闭，以便将来一些日期。执行此操作通过运行`Set-Mailbox -EndDateForRetentionHold <date>`命令。例如，假设今天的日期是 2016 年 7 月 1，并且您希望保留保留在 30 天内已关闭，将运行以下命令： `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。在此方案中，将保留*RentionHoldEnabled*属性设置为`True`。有关详细信息，请参阅[Set-mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317)。
    
  - 您可以更改，以便不会立即删除或移动到用户的存档邮箱均已导入的旧项目分配给邮箱的保留策略的设置。例如，您无法加长删除或存档策略分配给邮箱的保留期限。在此方案中，则会关闭邮箱保留挂起后更改保留策略的设置。有关详细信息，请参阅[Office 365 组织中邮箱的存档和删除策略设置](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。

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
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a><span data-ttu-id="6b521-103">使用网络上载将 RMS 加密的 PST 文件导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="6b521-103">Use network upload to import RMS-encrypted PST files to Office 365</span></span>

<span data-ttu-id="6b521-104">**本文是针对管理员。您试图将 PST 文件导入到您自己的邮箱？请参阅[导入电子邮件、 联系人和日历从 Outlook.pst 文件](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span><span class="sxs-lookup"><span data-stu-id="6b521-104">**This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span></span>
   
<span data-ttu-id="6b521-p101">使用网络上载到用户邮箱导入 PST 文件的选项和导入 Office 365 服务。网络上载意味着您在 Microsoft 云中的临时存储区上载 PST 文件。然后 Office 365 导入服务将复制的 PST 文件从存储区域到目标用户邮箱。导入服务的新功能，可以被上载并存储在 Microsoft 云之前加密 PST 文件。正在导入到用户邮箱时，这些文件将不加密。</span><span class="sxs-lookup"><span data-stu-id="6b521-p101">Use the network upload option and the Office 365 Import service to import PST files to user mailboxes. Network upload means that you upload the PST files a temporary storage area in the Microsoft cloud. Then the Office 365 Import service copies the PST files from the storage area to the target user mailboxes. A new feature of the Import service lets you encrypt your PST files before they are uploaded and stored on the Microsoft cloud. These files will be un-encrypted when they're imported to user mailboxes.</span></span> 
  
<span data-ttu-id="6b521-110">下面是用于加密和 PST 文件导入 Office 365 邮箱所需的步骤：</span><span class="sxs-lookup"><span data-stu-id="6b521-110">Here are the steps required to encrypt and import PST files to Office 365 mailboxes:</span></span>
  
[<span data-ttu-id="6b521-111">步骤 1：对 PST 导入设置 Azure 权限管理 </span><span class="sxs-lookup"><span data-stu-id="6b521-111">Step 1: Set up Azure Rights Management for PST Import</span></span>](#step-1-set-up-azure-rights-management-for-pst-import)

[<span data-ttu-id="6b521-112">步骤 2：生成 PST 导入的加密密钥</span><span class="sxs-lookup"><span data-stu-id="6b521-112">Step 2: Generate an encryption key for PST Import</span></span>](#step-2-generate-an-encryption-key-for-pst-import)

[<span data-ttu-id="6b521-113">步骤 3： 获取 RMS 租户 ID 和授权的 URL</span><span class="sxs-lookup"><span data-stu-id="6b521-113">Step 3: Obtain RMS tenant ID and licensing URL</span></span>](#step-3-obtain-rms-tenant-id-and-licensing-url)

[<span data-ttu-id="6b521-114">步骤 4： 下载 PST 导入工具和复制 SAS URL</span><span class="sxs-lookup"><span data-stu-id="6b521-114">Step 4: Download the PST Import tools and copy the SAS URL</span></span>](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[<span data-ttu-id="6b521-115">步骤 5： 加密和 PST 文件上传到 Office 365</span><span class="sxs-lookup"><span data-stu-id="6b521-115">Step 5: Encrypt and upload your PST files to Office 365</span></span>](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[<span data-ttu-id="6b521-116">（可选）步骤 6： 查看列表的 PST 文件上载到 Office 365</span><span class="sxs-lookup"><span data-stu-id="6b521-116">(Optional) Step 6: View a list of the PST files uploaded to Office 365</span></span>](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[<span data-ttu-id="6b521-117">步骤 7： 创建 PST 导入映射文件</span><span class="sxs-lookup"><span data-stu-id="6b521-117">Step 7: Create the PST Import mapping file</span></span>](#step-7-create-the-pst-import-mapping-file)

[<span data-ttu-id="6b521-118">步骤 8：在 Office 365 中创建 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="6b521-118">Step 8: Create a PST Import job in Office 365</span></span>](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> <span data-ttu-id="6b521-p102">您必须执行步骤 1 到步骤 4 仅执行一次设置和配置您的组织进行加密和 PST 文件导入 Office 365 邮箱。执行这些步骤后，按照步骤 5 到步骤 8 您想要加密、 上载和导入 PST 文件一批每的次。</span><span class="sxs-lookup"><span data-stu-id="6b521-p102">You have to perform Step 1 through Step 4 only once to set up and configure your organization to encrypt and import PST files to Office 365 mailboxes. After you perform these steps, follow Step 5 through Step 8 each time you want to encrypt, upload, and import a batch of PST files.</span></span> 
  
<span data-ttu-id="6b521-121">有关将数据导入到 Office 365 的详细信息，请参阅[Overview of 导入您的组织 PST 文件迁移到 Office 365](importing-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="6b521-121">For more information about importing data to Office 365, see [Overview of importing your organization PST files to Office 365](importing-pst-files-to-office-365.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="6b521-122">准备工作</span><span class="sxs-lookup"><span data-stu-id="6b521-122">Before you begin</span></span>

- <span data-ttu-id="6b521-p103">您必须为其分配导入导出邮箱角色在 Exchange Online 到 Office 365 邮箱导入 PST 文件。默认情况下，此角色不分配给任何角色组在 Exchange Online。您可以向组织管理角色组中添加邮箱导入导出角色。或者，您可以创建新的角色组、 分配的邮箱导入导出角色中，然后将自己添加为成员。有关详细信息，请参阅"添加角色向角色组"或"创建角色组"部分中[管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)。</span><span class="sxs-lookup"><span data-stu-id="6b521-p103">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
    
    <span data-ttu-id="6b521-128">此外，若要创建导入作业 Office 365 安全性&amp;必须满足合规中心，下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="6b521-128">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
    
  - <span data-ttu-id="6b521-p104">您必须分配 Mail Recipients 角色在 Exchange Online。默认情况下，此角色分配给组织管理和 Recipient Management 角色组。</span><span class="sxs-lookup"><span data-stu-id="6b521-p104">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="6b521-131">或</span><span class="sxs-lookup"><span data-stu-id="6b521-131">Or</span></span>
    
  - <span data-ttu-id="6b521-132">您必须是 Office 365 组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="6b521-132">You have to be a global administrator in your Office 365 organization.</span></span>
    
  > [!TIP]
  > <span data-ttu-id="6b521-p105">请考虑在 Exchange Online 的专门用于将 PST 文件导入到 Office 365 中创建新的角色组。最小的导入 PST 文件所需的权限级别，将邮箱导入导出和 Mail Recipients 角色分配给新角色组中，，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="6b521-p105">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
- <span data-ttu-id="6b521-p106">您需要存储要导入到 Office 365 上的文件服务器或在组织中的共享的文件夹的 PST 文件。在步骤 5 中，您将运行 Office 365 ImportTool，这将加密并上载该文件服务器上存储或共享到 Office 365 的文件夹的 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="6b521-p106">You need to store the PST files that you want to import to Office 365 on a file server or shared folder in your organization. In Step 5, you'll run the Office 365 ImportTool, which will encrypt and upload the PST files that are stored on this file server or shared folder to Office 365.</span></span>
    
- <span data-ttu-id="6b521-p107">此过程涉及复制并保存一份加密密钥、 存储键和大量标识键和 Url。此信息将用于在步骤 5 中加密和上传 PST 文件。请确保采取预防措施来保护这些只，如将保护密码或其他安全相关的信息。例如，您可能会将其保存到受密码保护的 Microsoft Word 文档或将其保存到加密的 USB 驱动器。请参阅有关这些项、 Id、 和 Url 示例[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="6b521-p107">This procedure involves copying and saving a copy of an encryption key, a storage key, and a number of identification keys and URLs. This information will be used in Step 5 to encrypt and upload your PST files. Be sure to take precautions to protect these just like you would protect passwords or other security-related information. For example you might save them to a password-protected Microsoft Word document or save them to an encrypted USB drive. See the [More information](#more-information) section for an example of these keys, IDs, and URLs.</span></span> 
    
- <span data-ttu-id="6b521-p108">您可以向 Office 365 中的非活动邮箱导入 PST 文件。执行此操作通过指定中的非活动邮箱的 GUID `Mailbox` PST 导入映射文件中的参数。有关详细信息，请参阅[步骤 7](#step-7-create-the-pst-import-mapping-file) 。</span><span class="sxs-lookup"><span data-stu-id="6b521-p108">You can import PST files to an inactive mailbox in Office 365. You do this by specifying the GUID of the inactive mailbox in the  `Mailbox` parameter in the PST Import mapping file. See [Step 7](#step-7-create-the-pst-import-mapping-file) for more information.</span></span> 
    
- <span data-ttu-id="6b521-p109">在 Exchange 混合部署，您可以 PST 文件导入为其主邮箱位于内部部署用户的基于云的存档邮箱。通过执行以下 PST 导入映射文件中的执行此操作：</span><span class="sxs-lookup"><span data-stu-id="6b521-p109">In an Exchange hybrid deployment, you can import PST files to a cloud-based archive mailbox for a user whose primary mailbox is on-premises. You do this by doing the following in the PST Import mapping file:</span></span>
    
  - <span data-ttu-id="6b521-147">指定用户的内部部署邮箱中的电子邮件地址`Mailbox`参数。</span><span class="sxs-lookup"><span data-stu-id="6b521-147">Specify the email address for the user's on-premises mailbox in the  `Mailbox` parameter.</span></span> 
    
  - <span data-ttu-id="6b521-148">指定**TRUE**值在`IsArchive`参数。</span><span class="sxs-lookup"><span data-stu-id="6b521-148">Specify the **TRUE** value in the  `IsArchive` parameter.</span></span> 
    
    <span data-ttu-id="6b521-149">有关详细信息，请参阅[步骤 7](#step-7-create-the-pst-import-mapping-file) 。</span><span class="sxs-lookup"><span data-stu-id="6b521-149">See [Step 7](#step-7-create-the-pst-import-mapping-file) for more information.</span></span> 
    
- <span data-ttu-id="6b521-p110">PST 文件导入到 Office 365 邮箱后，设置为该邮箱保留挂起是无限期的持续时间内，打开的。这意味着关闭保留挂起或设置要关闭保留日期之前，将不会处理分配给邮箱的保留策略。为什么做的原因？如果旧导入到邮箱的邮件，它们可能被永久删除 （清除） 由于其保留期已过期基于配置为该邮箱的保留设置。将邮箱放在保留挂起将给邮箱所有者时间来管理这些新导入的邮件或授予时间更改邮箱的保留设置。请参阅有关管理保留挂起的建议的[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="6b521-p110">After PST files are imported to an Office 365 mailbox, the retention hold setting for the mailbox is turned on for an indefinite duration. This means that the retention policy assigned to the mailbox won't be processed until you turn off the retention hold or set a date to turn off the hold. Why do we do this? If messages imported to a mailbox are old, they might be permanently deleted (purged) because their retention period has expired based on the retention settings configured for the mailbox. Placing the mailbox on retention hold will give the mailbox owner time to manage these newly-imported messages or give you time to change the retention settings for the mailbox. See the [More information](#more-information) section for suggestions about managing the retention hold.</span></span> 
    
- <span data-ttu-id="6b521-156">如果您不需要加密 PST 文件，将它们上载到 Office 365 之前，请参阅[使用网络上载以导入 PST 文件迁移到 Office 365](use-network-upload-to-import-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="6b521-156">If you don't need to encrypt your PST files before you upload them to Office 365, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
    
- <span data-ttu-id="6b521-157">有关使用网络上载到 Office 365 导入 PST 文件的常见问题进行了问题，请参阅[有关导入 PST 文件迁移到 Office 365 的常见问题](faqimporting-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="6b521-157">For frequently asked questions about using network upload to import PST files to Office 365, see [FAQ about importing PST files to Office 365](faqimporting-pst-files-to-office-365.md).</span></span>
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a><span data-ttu-id="6b521-158">步骤 1：对 PST 导入设置 Azure 权限管理 </span><span class="sxs-lookup"><span data-stu-id="6b521-158">Step 1: Set up Azure Rights Management for PST Import</span></span>

<span data-ttu-id="6b521-p111">PST 导入使用 Office 365 中的 Azure 权限管理 (Azure RMS) 服务提供的加密功能。这样可以将其上载到 Office 365 之前加密 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="6b521-p111">PST Import uses the encryption functionality provided by the Azure Rights Management (Azure RMS) service in Office 365. This lets you to encrypt PST files before uploading them to Office 365.</span></span> 
  
<span data-ttu-id="6b521-161">PST 导入的配置 Azure RMS 包括三个步骤：</span><span class="sxs-lookup"><span data-stu-id="6b521-161">Configuring Azure RMS for PST Import consists of three steps:</span></span>
  
- [<span data-ttu-id="6b521-162">激活 Azure RMS</span><span class="sxs-lookup"><span data-stu-id="6b521-162">Activating Azure RMS</span></span>](#activate-azure-rms)
    
- [<span data-ttu-id="6b521-163">配置 Exchange 在 Online RMS</span><span class="sxs-lookup"><span data-stu-id="6b521-163">Configuring RMS in Exchange Online</span></span>](#configure-rms-in-exchange-online)
    
- [<span data-ttu-id="6b521-164">安装 Active Directory RMS 客户端</span><span class="sxs-lookup"><span data-stu-id="6b521-164">Installing the Active Directory RMS Client</span></span>](#install-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a><span data-ttu-id="6b521-165">激活 Azure RMS</span><span class="sxs-lookup"><span data-stu-id="6b521-165">Activating Azure RMS</span></span>

<span data-ttu-id="6b521-p112">Azure RMS 禁用默认情况下，但您或您的组织中的其他管理员可能已激活它。按照上[激活 Azure 权限管理](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)来安装和激活 Azure DRM 的说明。</span><span class="sxs-lookup"><span data-stu-id="6b521-p112">Azure RMS is disabled by default, but you or another administrator in your organization might have activated it. Follow instructions on [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) to install and activate Azure DRM.</span></span>
  
### <a name="configuring-rms-in-exchange-online"></a><span data-ttu-id="6b521-168">配置 Exchange 在 Online RMS</span><span class="sxs-lookup"><span data-stu-id="6b521-168">Configuring RMS in Exchange Online</span></span>

<span data-ttu-id="6b521-p113">已激活的权限管理服务后下, 一步是在 Exchange Online 使用 Azure RMS 设置信息权限管理 (IRM)。有关详细信息，请参阅[配置 IRM 以使用 Azure 权限管理](https://go.microsoft.com/fwlink/p/?LinkId=394816)。</span><span class="sxs-lookup"><span data-stu-id="6b521-p113">After you've activated the Rights Management service, the next step is to set up Information Rights Management (IRM) in Exchange Online to use Azure RMS. For more information, see [Configure IRM to use Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=394816).</span></span>
  
1. <span data-ttu-id="6b521-171">[连接到 Exchange Online 使用远程 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554 )。</span><span class="sxs-lookup"><span data-stu-id="6b521-171">[Connect to Exchange Online using Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554 ).</span></span>
    
2. <span data-ttu-id="6b521-172">运行以下命令来设置 RMS 密钥共享 URL。</span><span class="sxs-lookup"><span data-stu-id="6b521-172">Run the following command to set the RMS key sharing URL.</span></span>
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    <span data-ttu-id="6b521-173">使用下表确定正确的 RMS 密钥共享您组织所处位置。</span><span class="sxs-lookup"><span data-stu-id="6b521-173">Use the following table to determine the correct RMS key sharing location for the location of your organization.</span></span>
    
    |<span data-ttu-id="6b521-174">**位置**</span><span class="sxs-lookup"><span data-stu-id="6b521-174">**Location**</span></span>|<span data-ttu-id="6b521-175">**RMS 关键共享位置**</span><span class="sxs-lookup"><span data-stu-id="6b521-175">**RMS key sharing location**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6b521-176">北美</span><span class="sxs-lookup"><span data-stu-id="6b521-176">North America</span></span>  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="6b521-177">欧盟</span><span class="sxs-lookup"><span data-stu-id="6b521-177">European Union</span></span>  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="6b521-178">亚洲</span><span class="sxs-lookup"><span data-stu-id="6b521-178">Asia</span></span>  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="6b521-179">南美洲</span><span class="sxs-lookup"><span data-stu-id="6b521-179">South America</span></span>  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |<span data-ttu-id="6b521-180">政府用 Office 365（政府社区云）</span><span class="sxs-lookup"><span data-stu-id="6b521-180">Office 365 for Government (Government Community Cloud)</span></span>  <br/> | <span data-ttu-id="6b521-181">`https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6b521-181">`https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup></span></span> <br/> |
   
    > [!NOTE]
    > <span data-ttu-id="6b521-182"><sup>1</sup> 只有已购买政府用 Office 365 SKU（政府社区云）的客户才应使用此 RMS 密钥共享位置。</span><span class="sxs-lookup"><span data-stu-id="6b521-182"><sup>1</sup> Only customers who have purchased Office 365 for Government SKUs (Government Community Cloud) should use this RMS key sharing location.</span></span> 
  
    <span data-ttu-id="6b521-183">例如，此命令会配置的 RMS Online 关键共享位置在 Exchange Online 为客户位于北美。</span><span class="sxs-lookup"><span data-stu-id="6b521-183">For example, this command configures the RMS Online key sharing location in Exchange Online for a customer located in North America.</span></span>
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. <span data-ttu-id="6b521-184">运行以下命令以受信任发布域 (TPD) 从 RMS Online 导入到您的 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="6b521-184">Run the following command to import a Trusted Publishing Domain (TPD) from RMS Online to your Office 365 organization.</span></span> 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    <span data-ttu-id="6b521-185">TPD 包含在您的组织中使用 RMS 功能所需的设置，包括加密 PST 文件。 </span><span class="sxs-lookup"><span data-stu-id="6b521-185">A TPD contains the settings needed to use RMS features in your organization, including encrypting PST files.</span></span> 
    
4. <span data-ttu-id="6b521-186">运行以下命令来为 Office 365 组织中启用 IRM。</span><span class="sxs-lookup"><span data-stu-id="6b521-186">Run the following command to enable IRM for your Office 365 organization.</span></span>
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a><span data-ttu-id="6b521-187">安装 Active Directory RMS 客户端</span><span class="sxs-lookup"><span data-stu-id="6b521-187">Installing the Active Directory RMS Client</span></span>

<span data-ttu-id="6b521-p114">本节中的最后一步是下载权限管理服务 (RMS) 客户端 2.1。本软件有助于保护 Azure RMS 访问并保护流经使用 Azure RMS.安装的应用程序将用于加密和上载 PST 文件中的步骤 5 中的同一台计算机上的 RMS 客户端的信息。</span><span class="sxs-lookup"><span data-stu-id="6b521-p114">The last step in this section is to download the Rights Management Services (RMS) Client 2.1. This software helps protect access to Azure RMS and protects information flowing through applications that use Azure RMS. Install the RMS client on the same computer that you'll use to encrypt and upload PST files in Step 5.</span></span> 
  
1. <span data-ttu-id="6b521-191">下载[权限管理服务客户端 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396)。</span><span class="sxs-lookup"><span data-stu-id="6b521-191">Download [Rights Management Service Client 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396).</span></span>
    
2. <span data-ttu-id="6b521-192">运行 Active Directory 权限管理服务客户端 2.1 向导来安装客户端。</span><span class="sxs-lookup"><span data-stu-id="6b521-192">Run the Active Directory Rights Management Service Client 2.1 wizard to install the client.</span></span>

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a><span data-ttu-id="6b521-193">步骤 2：生成 PST 导入的加密密钥</span><span class="sxs-lookup"><span data-stu-id="6b521-193">Step 2: Generate an encryption key for PST Import</span></span>

<span data-ttu-id="6b521-p115">您已设置 Azure RMS 后下, 一步是生成加密密钥将用于加密的 PST 文件上载到 Office 365 的 （称为对称密钥）。将作为服务主体 Azure Active Directory 中添加 PST 导入服务来执行此操作。作为服务主体将允许 PST 导入服务进行身份验证直接与 Azure Active Directory 上传时添加此应用程序加密 PST 文件迁移到步骤 5 中的 Azure 的存储位置。</span><span class="sxs-lookup"><span data-stu-id="6b521-p115">After you've set up Azure RMS, the next step is to generate an encryption key (called a symmetric key) that will be used to encrypt the PST files that you upload to Office 365. You'll do this by adding the PST Import service as a service principal in Azure Active Directory. Adding this application as a service principal will allow the PST Import service to authenticate directly with Azure Active Directory when you upload encrypted the PST files to the Azure storage location in Step 5.</span></span>
  
1. <span data-ttu-id="6b521-197">启动 Windows powershell 的 Azure Active Directory 模块。</span><span class="sxs-lookup"><span data-stu-id="6b521-197">Start the Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="6b521-198">运行下面的命令以连接到 Microsoft Online 服务。</span><span class="sxs-lookup"><span data-stu-id="6b521-198">Run the following command to connect to the Microsoft Online service.</span></span>
    
    ```
    Connect-MsolService
    ```

3. <span data-ttu-id="6b521-199">在 Office 365 组织中的管理员帐户输入凭据，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6b521-199">Enter the credentials for an administrator account in your Office 365 organization, and then click **OK**.</span></span>
    
4. <span data-ttu-id="6b521-p116">运行以下命令以生成加密密钥（也称作“对称密钥”）。您将通过创建新的 PST 加密主体来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6b521-p116">Run the following command to generate an encryption key (call a symmetric key). You'll do this by creating a new PST Encryption Principal.</span></span>
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    <span data-ttu-id="6b521-202">系统将显示新 PST 加密主体的对称密钥和属性。</span><span class="sxs-lookup"><span data-stu-id="6b521-202">The system displays the symmetric key and the properties for the new PST Encryption Principal.</span></span>
    
    ![复制并保存显示的对称密钥](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. <span data-ttu-id="6b521-p117">将对称密钥复制到文本或 Word 文件中。如前所述，一定要采取预防措施来保护此文件。因为这是显示对称密钥的唯一时机，所以您也可以考虑对此窗口拍摄屏幕快照并将其保存到同一文件中。 </span><span class="sxs-lookup"><span data-stu-id="6b521-p117">Copy the symmetric key to a text or Word file. As previously stated, be sure to take precautions to protect this file. Because this is the only time that the symmetric key is displayed, you might also consider taking a screenshot of this window and saving it to the same file.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="6b521-p118">创建 PST 加密主体后，您将无法通过使用 **Get-MsolServicePrincipal** cmdlet 检索对称密钥。这就是保存该密钥非常重要的原因。</span><span class="sxs-lookup"><span data-stu-id="6b521-p118">After you create the PST Encryption Principal, you won't be able to retrieve the symmetric key by using the **Get-MsolServicePrincipal** cmdlet. That's why it's important to save the key.</span></span> 
  
<span data-ttu-id="6b521-p119">将保留 Azure Active Directory 模块用于 Windows PowerShell 的打开和连接到 Microsoft Online 服务。您将在下一步中此窗口中运行命令。</span><span class="sxs-lookup"><span data-stu-id="6b521-p119">Keep the Azure Active Directory Module for Windows PowerShell open and connected to the Microsoft Online service. You'll run a command in this window in the next step.</span></span>

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a><span data-ttu-id="6b521-211">步骤 3： 获取 RMS 租户 ID 和授权的 URL</span><span class="sxs-lookup"><span data-stu-id="6b521-211">Step 3: Obtain RMS tenant ID and licensing URL</span></span>

<span data-ttu-id="6b521-p120">下一步是获取租户 ID 和许可位置组织的 Azure RMS 服务 URL。复制并将此信息保存到包含从步骤 2 的对称密钥的同一文件。ID 和 URL 将用于在步骤 5 中加密 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="6b521-p120">The next step is to obtain the tenant ID and licensing location URL for the Azure RMS service for your organization. Copy and save this information to the same file that contains the symmetric key from Step 2. The ID and URL will be used in Step 5 to encrypt your PST files.</span></span>
  
1. <span data-ttu-id="6b521-215">在 Azure Active Directory 模块 （这连接到 Microsoft Online 服务） 的 Windows powershell，运行以下命令以连接到 Office 365 组织中的 Azure RMS 服务。</span><span class="sxs-lookup"><span data-stu-id="6b521-215">In the Azure Active Directory Module for Windows PowerShell (which is connected to the Microsoft Online service), run the following command to connect to the Azure RMS service in your Office 365 organization.</span></span>
    
    ```
    Connect-AadrmService 
    ```

2. <span data-ttu-id="6b521-216">Office 365 组织中的管理员帐户输入凭据，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6b521-216">Enter the credentials for an administrator account in your Office 365 organization and then click **OK**.</span></span>
    
3. <span data-ttu-id="6b521-217">运行以下命令以显示 Office 365 组织中的 Azure RMS 服务的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="6b521-217">Run the following command to display the tenant ID for the Azure RMS service in your Office 365 organization.</span></span>
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    <span data-ttu-id="6b521-218">复制和保存的值`BPOSId`属性。</span><span class="sxs-lookup"><span data-stu-id="6b521-218">Copy and save the value for the  `BPOSId` property.</span></span> 
    
4. <span data-ttu-id="6b521-219">运行以下命令以显示为 Azure RMS 服务的许可位置。</span><span class="sxs-lookup"><span data-stu-id="6b521-219">Run the following command to display the licensing location for your Azure RMS service.</span></span>
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    <span data-ttu-id="6b521-220">复制和保存的值`LicensingIntranetDistributionPointUrl`属性。</span><span class="sxs-lookup"><span data-stu-id="6b521-220">Copy and save the value for the  `LicensingIntranetDistributionPointUrl` property.</span></span> 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a><span data-ttu-id="6b521-221">步骤 4： 下载 PST 导入工具和复制 SAS URL</span><span class="sxs-lookup"><span data-stu-id="6b521-221">Step 4: Download the PST Import tools and copy the SAS URL</span></span>

<span data-ttu-id="6b521-p121">现在，您已配置 Azure RMS 并获得需要加密 PST 文件的 Id 下, 一步是下载并安装到 Office 365 进行加密的步骤 5 中将运行并上载 PST 文件的工具。这些工具是 Azure AzCopy 工具和 Office 365 数据加密工具。您还将为您的组织复制 SAS URL。此 URL 是 Microsoft 云的组织和共享访问签名 (SA) 键中的 Azure 存储位置的网络 URL 的组合。此项为您提供所需的权限将 PST 文件上载到 Azure 存储位置。将其保存到相同的文件，您已在步骤 2 和步骤 3 中复制到的其他信息。如前面所述，采取预防措施来保护 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="6b521-p121">Now that you've configured Azure RMS and obtained the IDs necessary to encrypt PST files, the next step is to download and install the tools that you will run in Step 5 to encrypt and upload PST files to Office 365. These tools are the Azure AzCopy tool and the Office 365 Data Encryption tool. You'll also copy the SAS URL for your organization. This URL is a combination of the network URL for the Azure storage location in the Microsoft cloud for your organization and a Shared Access Signature (SAS) key. This key provides you with the necessary permissions to upload PST files to your Azure storage location. Save it to the same file that you've copied the other information to in Step 2 and Step 3. As previously stated, take precautions to protect the SAS URL.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6b521-p122">您需要使用 Azure AzCopy 5.0 成功将 PST 文件上载到 Azure 存储位置。将 PST 文件导入到 Office 365 不支持较新版本的 AzCopy 工具。请务必在此步骤中的过程从**上载文件通过网络**页上下载 AzCopy 工具。</span><span class="sxs-lookup"><span data-stu-id="6b521-p122">You have to use Azure AzCopy version 5.0 to successfully upload PST files to the Azure storage location. Newer versions of the AzCopy tool aren't supported for importing PST files to Office 365. Be sure to download the AzCopy tool from the **Upload files over the network** page by following the procedures in this step.</span></span> 
  
1. <span data-ttu-id="6b521-232">转到[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="6b521-232">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="6b521-233">登录到 Office 365 使用 Office 365 组织中的管理员帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="6b521-233">Sign in to Office 365 using the credentials for an administrator account in your Office 365 organization.</span></span>
    
3. <span data-ttu-id="6b521-234">在左窗格中，单击**数据管理**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="6b521-234">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
4. <span data-ttu-id="6b521-235">在**导入**页上，单击**转到导入服务**。</span><span class="sxs-lookup"><span data-stu-id="6b521-235">On the **Import** page, click **Go to the Import service**.</span></span>
    
5. <span data-ttu-id="6b521-236">在**到 Office 365 的导入数据**页上，单击**新建作业**![添加图标](media/ITPro-EAC-AddIcon.gif)，，然后单击**上载电子邮件 （PST 文件）**。</span><span class="sxs-lookup"><span data-stu-id="6b521-236">On the **Import data to Office 365** page, click **New job** ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **Upload email messages (PST files)**.</span></span>
    
6. <span data-ttu-id="6b521-237">在**将通过网络的文件上载**页上的步骤 2 中，单击**显示网络上载 SAS URL**。</span><span class="sxs-lookup"><span data-stu-id="6b521-237">On the **Upload files over the network** page, in step 2, click **Show network upload SAS URL**.</span></span>
    
7. <span data-ttu-id="6b521-p123">显示 URL 后，将其复制，并将其保存在文件中保存其他注册表项的位置。请务必将复制的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="6b521-p123">After the URL is displayed, copy it and save it in the file where you saved the other keys. Be sure to copy the entire URL.</span></span> 
    
8. <span data-ttu-id="6b521-240">在步骤 3 中，单击**下载 Azure AzCopy 工具**以下载并安装 Azure AzCopy 工具。</span><span class="sxs-lookup"><span data-stu-id="6b521-240">In step 3, click **Download the Azure AzCopy tool** to download and install the Azure AzCopy tool.</span></span> 
    
9. <span data-ttu-id="6b521-241">在弹出窗口中，单击**运行**以安装 Azure AzCopy 工具。</span><span class="sxs-lookup"><span data-stu-id="6b521-241">In the pop-up window, click **Run** to install the Azure AzCopy tool.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="6b521-p124">请务必在默认位置，即安装 Azure AzCopy 工具`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`的计算机上运行 64 位 Windows。这是因为您在步骤 5 中运行 O365ImportTool.exe，当它查找该位置的 AzCopy 工具。</span><span class="sxs-lookup"><span data-stu-id="6b521-p124">Be sure to install the Azure AzCopy tool in the default location, which is `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy` on a computer running 64-bit Windows. That's because when you run the O365ImportTool.exe in Step 5, it looks for the AzCopy tool in this location.</span></span> 
  
10. <span data-ttu-id="6b521-244">您已安装 Azure AzCopy 工具后，单击**下载 Office 365 数据加密和导入工具**。</span><span class="sxs-lookup"><span data-stu-id="6b521-244">After you've installed the Azure AzCopy tool, click **Download the Office 365 Data Encryption and Import tool**.</span></span>
    
11. <span data-ttu-id="6b521-245">在弹出窗口中，单击**保存** \> **另存为**本地计算机上将 O365ImportTool.zip 文件保存到文件夹。</span><span class="sxs-lookup"><span data-stu-id="6b521-245">In the pop-up window, click **Save** \> **Save as** to save the O365ImportTool.zip file to a folder on your local computer.</span></span> 
    
12. <span data-ttu-id="6b521-246">提取 O365ImportTool.zip 文件。</span><span class="sxs-lookup"><span data-stu-id="6b521-246">Extract the O365ImportTool.zip file.</span></span>
    
13. <span data-ttu-id="6b521-247">单击**取消**以关闭**上载文件通过网络**页。</span><span class="sxs-lookup"><span data-stu-id="6b521-247">Click **Cancel** to close the **Upload files over the network** page.</span></span> 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a><span data-ttu-id="6b521-248">步骤 5： 加密和 PST 文件上传到 Office 365</span><span class="sxs-lookup"><span data-stu-id="6b521-248">Step 5: Encrypt and upload your PST files to Office 365</span></span>

<span data-ttu-id="6b521-p125">完成步骤 1 到步骤 4 之后，就可以使用 O365ImportTool.exe 工具进行加密和将 PST 文件上载到 Office 365。此工具加密 PST 文件，然后上载并将其存储在云中的 Microsoft Azure 的存储位置。若要完成此步骤，PST 文件必须位于文件共享或组织中的文件服务器。这就是在下面的过程的源目录。每次运行 O365ImportTool.exe 工具，您将可以指定一个不同的源目录。</span><span class="sxs-lookup"><span data-stu-id="6b521-p125">After you have completed Step 1 through Step 4, you're ready to use the O365ImportTool.exe tool to encrypt and upload PST files to Office 365. This tool encrypts your PST files and then uploads and stores them in an Azure storage location in the Microsoft cloud. To complete this step, the PST files have to be located in a file share or file server in your organization. This is known as the source directory in the following procedure. Each time you run the O365ImportTool.exe tool, you'll can specify a different source directory.</span></span> 
  
1. <span data-ttu-id="6b521-254">在您的本地计算机上打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="6b521-254">Open a Command Prompt on your local computer.</span></span>
    
2. <span data-ttu-id="6b521-255">转到您在步骤 4 中安装 O365ImportTool.exe 工具的目录。</span><span class="sxs-lookup"><span data-stu-id="6b521-255">Go to the directory where you installed the O365ImportTool.exe tool in Step 4.</span></span>
    
3. <span data-ttu-id="6b521-256">运行以下命令来加密和将 PST 文件上载到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="6b521-256">Run the following command to encrypt and upload PST files to Office 365.</span></span>
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    <span data-ttu-id="6b521-p126">下表描述了各个参数及其所需值。请注意，在前面的步骤中获取的信息会用在这些参数的值中。</span><span class="sxs-lookup"><span data-stu-id="6b521-p126">The following table describes the parameters and their required values. Note that the information you obtained in the previous steps is used in the values for these parameters.</span></span>
    
    |<span data-ttu-id="6b521-259">**参数**</span><span class="sxs-lookup"><span data-stu-id="6b521-259">**Parameter**</span></span>|<span data-ttu-id="6b521-260">**说明**</span><span class="sxs-lookup"><span data-stu-id="6b521-260">**Description**</span></span>|<span data-ttu-id="6b521-261">**示例**</span><span class="sxs-lookup"><span data-stu-id="6b521-261">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |<span data-ttu-id="6b521-262">指定包含 PST 文件将上载到 Office 365 组织中的源目录。</span><span class="sxs-lookup"><span data-stu-id="6b521-262">Specifies the source directory in your organization that contains the PST files that will be uploaded to Office 365.</span></span>  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |<span data-ttu-id="6b521-p127">指定 Azure RMS 服务的许可位置。使用的值`LicensingIntranetDistributionPointUrl`在步骤 3 中获取的属性。请务必包围双引号与此参数的值 ("")</span><span class="sxs-lookup"><span data-stu-id="6b521-p127">Specifies the licensing location for your Azure RMS service. Use the value of the  `LicensingIntranetDistributionPointUrl` property that you obtained in Step 3. Be sure to surround the value of this parameter with double-quotation marks (" ")  </span></span><br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |<span data-ttu-id="6b521-p128">指定 Azure RMS 组织的标识。使用的值`BPOSId`在步骤 3 中获取的属性。</span><span class="sxs-lookup"><span data-stu-id="6b521-p128">Specifies the identity of your Azure RMS organization. Use the value of the  `BPOSId` property that you obtained in Step 3.  </span></span><br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |<span data-ttu-id="6b521-p129">在步骤 2 中指定您获取的对称密钥。请务必包围双引号与此参数的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="6b521-p129">Specifies the symmetric key that you obtained in Step 2. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |<span data-ttu-id="6b521-p130">指定是否通过网络上载 PST 文件或将它们发送硬盘驱动器上。值`upload`指示通过网络上载文件。值`drive`指示，您将在硬盘驱动器上传送 Pst。</span><span class="sxs-lookup"><span data-stu-id="6b521-p130">Specifies whether you upload PST files over the network or ship them on a hard drive. The value  `upload` indicates that you are uploading the files over the network. The value  `drive` indicates that you are shipping the PSTs on a hard drive.  </span></span><br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |<span data-ttu-id="6b521-p131">指定在其中 PST 文件将上载到; Office 365 中的目标这是您的组织的 Azure 存储位置。此参数的值包含您在步骤 4 中复制的 SAS URL 中的网络上载 URL。请务必包围双引号与此参数的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="6b521-p131">Specifies the destination in Office 365 where your PST files will be uploaded to; this is the Azure storage location for your organization. The value for this parameter consists of the network upload URL from the SAS URL that you copied in Step 4. Be sure to surround the value of this parameter with double-quotation marks (" ").  </span></span><br/><br/> <span data-ttu-id="6b521-p132">**提示：**（可选）Azure 的存储位置上载到加密的 PST 文件中，您可以指定子文件夹。通过在网络上载 URL 添加 （之后"ingestiondata") 的子文件夹位置执行此操作。第一个示例不指定子文件夹;这意味着 Pst 将上载到根目录 （名为*ingestiondata* ） Azure 的存储位置。第二个示例中的 Azure 的存储位置上载到子文件夹 （名为*EncryptedPSTs* ） 的 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="6b521-p132">**Tip:** (Optional) You can specify a subfolder in the Azure storage location to upload the encrypted PST files to. You do this by adding a subfolder location (after "ingestiondata") in the network upload URL. The first example doesn't specify a subfolder; that means the PSTs will be uploaded to the root (named  *ingestiondata*  ) of the Azure storage location. The second example uploads the PST files to a subfolder (named  *EncryptedPSTs*  ) in the Azure storage location.</span></span>           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> <span data-ttu-id="6b521-280">或</span><span class="sxs-lookup"><span data-stu-id="6b521-280">Or</span></span>  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |<span data-ttu-id="6b521-p133">指定您的组织的 SAS 键。此参数的值包含您在步骤 4 中复制的 SAS URL 中的 SAS 键。请注意，在 SAS 注册表项中的第一个字符是一个问号 ("？")。请务必包围双引号与此参数的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="6b521-p133">Specifies the SAS key for you organization. The value for this parameter consists of the SAS key from the SAS URL that you copied in Step 4. Note that first character in the SAS key is a question mark ("?"). Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |<span data-ttu-id="6b521-285">此可选开关指定递归模式，以便 O365ImportTool.exe 工具会将位于指定源目录中的子文件夹中的 Pst 文件复制`/srcdir:`参数。</span><span class="sxs-lookup"><span data-stu-id="6b521-285">This optional switch specifies the recursive mode so that the O365ImportTool.exe tool will copy PSTs files that are located in subfolders in the source directory that is specified by the  `/srcdir:` parameter.</span></span>  <br/><br/> <span data-ttu-id="6b521-p134">**注意：** 如果包括此开关，子文件夹中的 PST 文件将 Azure 存储位置中具有不同文件路径名，他们正在上载后。您将需要在您在步骤 7 中创建的 CSV 文件中指定的确切文件路径名。</span><span class="sxs-lookup"><span data-stu-id="6b521-p134">**Note:** If you include this switch, PST files in subfolders will have a different file pathname in the Azure storage location after they're uploaded. You'll have to specify the exact file pathname in the CSV file that you create in Step 7.</span></span>           | `/recurse` <br/> |
   
    <span data-ttu-id="6b521-288">以下是对每个参数使用实际值的 O365ImportTool.exe 工具的语法示例：</span><span class="sxs-lookup"><span data-stu-id="6b521-288">Here's an example of the syntax for the O365ImportTool.exe tool using actual values for each parameter:</span></span>
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    <span data-ttu-id="6b521-p135">运行该命令后，显示的状态消息会显示对 PST 文件进行加密和上载的进度。最终状态消息显示已成功加密并上载的文件的总数。 </span><span class="sxs-lookup"><span data-stu-id="6b521-p135">After you run the command, status messages are displayed that show the progress of encrypting and uploading the PST files. A final status message shows the total number of files that were successfully encrypted and uploaded.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="6b521-p136">在成功运行 O365ImportTool.exe 命令并确认所有参数都正确无误后，保存一份同一个复制信息的位置 （安全） 文件的命令行语法获取在前面的步骤。然后可以复制并粘贴在命令提示符处每次您想要运行 O365ImportTool.exe 工具进行加密和将 PST 文件上载到 Office 365 的此命令。您可能需要更改的唯一值是为`/srcdir:`和`/upload-dest:`参数。</span><span class="sxs-lookup"><span data-stu-id="6b521-p136">After you successfully run the O365ImportTool.exe command and verify that all the parameters are correct, save a copy of the command line syntax to the same (secured) file where you copied the information you obtained in the previous steps. Then you can copy and paste this command in a Command Prompt each time that you want to run the O365ImportTool.exe tool to encrypt and upload PST files to Office 365. The only values you might have to change are the ones for the  `/srcdir:` and  `/upload-dest:` parameters.</span></span> 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a><span data-ttu-id="6b521-294">（可选）步骤 6： 查看列表的 PST 文件上载到 Office 365</span><span class="sxs-lookup"><span data-stu-id="6b521-294">(Optional) Step 6: View a list of the PST files uploaded to Office 365</span></span>

<span data-ttu-id="6b521-p137">作为一个可选步骤，您可以安装和使用 Microsoft Azure 存储浏览器 （这是一个免费的开源工具） 若要查看已上载到 Azure blob PST 文件的列表。有三个良好的原因，若要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="6b521-p137">As an optional step, you can install and use the Microsoft Azure Storage Explorer (which is a free, open source tool) to view the list of the PST files that you've uploaded to the Azure blob. There are three good reasons to do this:</span></span>
  
- <span data-ttu-id="6b521-297">验证 PST 文件从共享的文件夹或组织中的文件服务器已成功上载到 Azure 的 blob。</span><span class="sxs-lookup"><span data-stu-id="6b521-297">Verify that PST files from the shared folder or file server in your organization were successfully uploaded to the Azure blob.</span></span>

- <span data-ttu-id="6b521-p138">验证 PST 文件进行加密。加密的 PST 文件具有`.pfile`扩展追加到 PST 文件名;例如， `pilarp.pst.pfile`。</span><span class="sxs-lookup"><span data-stu-id="6b521-p138">Verify that the PST files are encrypted. Encrypted PST files have a  `.pfile` extension appended to the PST filename; for example,  `pilarp.pst.pfile`.</span></span>
    
- <span data-ttu-id="6b521-p139">验证每个 PST 文件上载到 Azure blob 的文件名 （和子文件夹路径名如果包括了一个）。正在创建 PST 映射文件的下一步，因为您有时必须指定的文件夹路径名和文件名为每个 PST 文件时，这是非常有用。验证这些名称，可帮助减少 PST 映射文件中的潜在错误。</span><span class="sxs-lookup"><span data-stu-id="6b521-p139">Verify the filename (and the subfolder pathname if you included one) for each PST file uploaded to the Azure blob. This is really helpful when you're creating the PST mapping file in the next step because you have to specify both the folder pathname and filename for each PST file. Verifying these names can help reduce potential errors in your PST mapping file.</span></span>
    
<span data-ttu-id="6b521-303">Microsoft Azure 存储 Explorer 正处于预览。</span><span class="sxs-lookup"><span data-stu-id="6b521-303">The Microsoft Azure Storage Explorer is in Preview.</span></span> 
  
 > [!IMPORTANT]
>  <span data-ttu-id="6b521-p140">不能使用 Azure 存储资源管理器上载或修改 PST 文件。将 PST 文件导入到 Office 365 唯一受支持的方法是使用 AzCopy。此外，您不能删除已上载到 Azure blob 的 PST 文件。如果尝试删除 PST 文件，您会收到了有关未获得所需的权限的错误。请注意自动从您 Azure 存储区删除所有 PST 文件。如果有任何导入作业正在进行，然后中的所有 PST 文件**ingestiondata**容器中将不删除 30 天后创建的最新的导入作业。</span><span class="sxs-lookup"><span data-stu-id="6b521-p140">You can't use the Azure Storage Explorer to upload or modify PST files. The only supported method for importing PST files to Office 365 is to use AzCopy. Also, you can't delete PST files that you've uploaded to the Azure blob. If you try to delete a PST file, you'll receive an error about not having the required permissions. Note that all PST files are automatically deleted from your Azure storage area. If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created.</span></span> 
  
<span data-ttu-id="6b521-310">安装 Azure 存储浏览器并连接到 Azure 存储区：</span><span class="sxs-lookup"><span data-stu-id="6b521-310">To install the Azure Storage Explorer and connect to your Azure storage area:</span></span>
  
1. <span data-ttu-id="6b521-311">下载并安装[Microsoft Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="6b521-311">Download and install the [Microsoft Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span>
    
2. <span data-ttu-id="6b521-312">启动 Microsoft Azure 存储资源管理器，在左窗格中右键单击**存储帐户**，然后单击**连接到 Azure 存储**。</span><span class="sxs-lookup"><span data-stu-id="6b521-312">Start the Microsoft Azure Storage Explorer, right-click **Storage Accounts** in the left pane, and then click **Connect to Azure storage**.</span></span> 
    
    ![右键单击存储帐户，然后单击连接到 Azure 存储](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. <span data-ttu-id="6b521-314">在**连接到 Azure 存储**下的框中，在步骤 4，粘贴您获得 SAS URL，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6b521-314">In the box under **Connect to Azure storage**, paste the SAS URL that you obtained in Step 4, and then click **Next**.</span></span> 
    
    ![在连接到 Azure 存储页上框中粘贴 SAS URL](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. <span data-ttu-id="6b521-316">在**连接摘要**页中，您可以查看连接信息，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="6b521-316">On the **Connection summary** page, you can review the connection information, and then click **Connect**.</span></span> 
    
5. <span data-ttu-id="6b521-317">**存储帐户**下, 展开 **(服务 SAS)** 节点，然后展开**Blob 容器**节点。</span><span class="sxs-lookup"><span data-stu-id="6b521-317">Under **Storage Accounts**, expand the **(Service SAS)** node, and then expand the **Blob Containers** node.</span></span> 
    
6. <span data-ttu-id="6b521-318">右键单击**ingestiondata**，，，然后单击**打开 Blob 容器编辑器**。</span><span class="sxs-lookup"><span data-stu-id="6b521-318">Right-click **ingestiondata**, and then click **Open Blob Container Editor**.</span></span>
    
    ![右键单击 ingestiondata，然后单击“打开 Blob 容器编辑器”](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    <span data-ttu-id="6b521-320">显示的 Azure 存储区，与在步骤 5 中上载的 PST 文件的列表。</span><span class="sxs-lookup"><span data-stu-id="6b521-320">The Azure storage area, with a list of the PST files that you uploaded in Step 5 is displayed.</span></span>
    
    ![Azure 存储资源管理器显示你上载的 PST 文件的列表](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. <span data-ttu-id="6b521-p141">完成后使用 Microsoft Azure 存储浏览器，右键单击**ingestiondata**，，然后单击**分离**断开 Azure 存储区。否则，您会收到错误的下次尝试附加。</span><span class="sxs-lookup"><span data-stu-id="6b521-p141">When you're finished using the Microsoft Azure Storage Explorer, right-click **ingestiondata**, and then click **Detach** to disconnect from your Azure storage area. Otherwise, you'll receive an error the next time you try to attach.</span></span> 
    
    ![右键单击“引入”，然后单击“分离”以从 Azure 存储区域断开连接](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a><span data-ttu-id="6b521-325">步骤 7： 创建 PST 导入映射文件</span><span class="sxs-lookup"><span data-stu-id="6b521-325">Step 7: Create the PST Import mapping file</span></span>

<span data-ttu-id="6b521-p142">具有已加密的 PST 文件，并将其上载到 Office 365 组织的 Azure 存储位置后下, 一步是创建逗号分隔值 (CSV) 文件，指定 PST 文件将被导入到哪些用户邮箱。创建 PST 导入作业时，您将提交的下一步此 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="6b521-p142">After the PST files have been encrypted and uploaded to the Azure storage location for your Office 365 organization, the next step is to create a comma separated value (CSV) file that specifies which user mailboxes the PST files will be imported to. You will submit this CSV file in the next step when you create a PST Import job.</span></span>
  
1. <span data-ttu-id="6b521-328">[下载 PST 导入映射文件的副本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。</span><span class="sxs-lookup"><span data-stu-id="6b521-328">[Download a copy of the PST Import mapping file](https://go.microsoft.com/fwlink/p/?LinkId=544717).</span></span> 
    
2. <span data-ttu-id="6b521-p143">打开或将 CSV 文件保存到您的本地计算机。下面的示例显示已完成的 PST 导入映射文件（在记事本中打开）。使用 Microsoft Excel 编辑 CSV 文件变得容易得多。</span><span class="sxs-lookup"><span data-stu-id="6b521-p143">Open or save the CSV file to your local computer. The following example shows a completed PST Import mapping file (opened in NotePad). It's much easier to use Microsoft Excel to edit the CSV file.</span></span>
    
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

    <span data-ttu-id="6b521-p144">标题行，CSV 文件的第一行中，列出 PST 导入服务将用于将 PST 文件导入到用户邮箱的参数。每个参数名称并用逗号分隔。在标题行下的各行代表 PST 文件导入到特定邮箱的参数值。对于每个要导入到用户邮箱的 PST 文件，您将需要一行。请务必映射文件中的占位符数据替换为实际数据。</span><span class="sxs-lookup"><span data-stu-id="6b521-p144">The first row, or header row, of the CSV file lists the parameters that will be used by the PST Import service to import the PST files to user mailboxes. Each parameter name is separated by a comma. Each row under the header row represents the parameter values for importing a PST file to a specific mailbox. You will need a row for each PST file that you want to import to a user mailbox. Be sure to replace the placeholder data in the mapping file with your actual data.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6b521-337">不要更改标题行中的任何内容，包括 SharePoint 参数；这些内容会在 PST 导入过程中被忽略。</span><span class="sxs-lookup"><span data-stu-id="6b521-337">Don't change anything in the header row, including the SharePoint parameters; they will be ignored during the PST Import process.</span></span> 
  
3. <span data-ttu-id="6b521-338">使用下表中的信息来填充附有所需信息的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="6b521-338">Use the information in the following table to populate the CSV file with the required information.</span></span>
    
    |<span data-ttu-id="6b521-339">**参数**</span><span class="sxs-lookup"><span data-stu-id="6b521-339">**Parameter**</span></span>|<span data-ttu-id="6b521-340">**说明**</span><span class="sxs-lookup"><span data-stu-id="6b521-340">**Description**</span></span>|<span data-ttu-id="6b521-341">**示例**</span><span class="sxs-lookup"><span data-stu-id="6b521-341">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `Workload` <br/> |<span data-ttu-id="6b521-p145">指定数据将导入到的 Office 365 服务。若要为用户邮箱导入 PST 文件，请使用`Exchange`。</span><span class="sxs-lookup"><span data-stu-id="6b521-p145">Specifies the Office 365 service that data will be imported to. To import PST files to user mailboxes, use  `Exchange`.  </span></span><br/> | `Exchange` <br/> |
    | `FilePath` <br/> |<span data-ttu-id="6b521-344">在您上载 PST 文件迁移到步骤 5 中的 Azure 的存储位置指定的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="6b521-344">Specifies the folder location in the Azure storage location that you uploaded the PST files to in Step 5.</span></span>  <br/>  <span data-ttu-id="6b521-p146">如果您没有在的网络 URL 中包括的可选子文件夹名称`/upload-dest:`参数在步骤 5 中，将此参数留空 CSV 文件中。如果包括子文件夹名称，则此参数中指定它。此参数的值是区分大小写。两种方法，在的值*不*包括"ingestiondata"`FilePath`参数。</span><span class="sxs-lookup"><span data-stu-id="6b521-p146">If you didn't include an optional subfolder name in the network URL in the  `/upload-dest:` parameter in Step 5, leave this parameter blank in the CSV file. If you included a subfolder name, specify it in this parameter. The value for this parameter is case sensitive. Either way,  *don't*  include "ingestiondata" in the value for the  `FilePath` parameter.  </span></span><br/> <br/><span data-ttu-id="6b521-p147">**重要：** 种情况的文件路径名称必须是相同的大小写，如果在 SAS URL 中包含的可选子文件夹名称使用`/upload-dest:`步骤 5 中的参数。例如，如果您使用`EncryptedPSTs`的子文件夹命名为在步骤 5 中，然后使用`encryptedpsts`的`FilePath`CSV 文件中的参数，PST 文件导入将失败。请务必在这两种情况下使用相同的大小写。</span><span class="sxs-lookup"><span data-stu-id="6b521-p147">**Important:** The case for the file path name must be the same case that you used if you included an optional subfolder name in the SAS URL in the  `/upload-dest:` parameter in Step 5. For example, if you used  `EncryptedPSTs` for the subfolder name in Step 5 and then use  `encryptedpsts` in the  `FilePath` parameter in CSV file, the import for the PST file will fail. Be sure to use the same case in both instances.</span></span>           |<span data-ttu-id="6b521-352">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="6b521-352">(leave blank)</span></span>  <br/> <span data-ttu-id="6b521-353">或</span><span class="sxs-lookup"><span data-stu-id="6b521-353">Or</span></span>  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |<span data-ttu-id="6b521-p148">指定将导入到用户邮箱的 PST 文件的名称。此参数的值是区分大小写。上载到 Azure 的存储位置的 PST 文件进行加密，因为`.pfile`扩展名添加到 PST 文件名。您必须添加`.pfile`中 CSV 文件的文件扩展名为 PST 的名称。</span><span class="sxs-lookup"><span data-stu-id="6b521-p148">Specifies the name of the PST file that will be imported to the user mailbox. The value for this parameter is case sensitive. Because the PST files that are uploaded to the Azure storage location are encrypted, a  `.pfile` extension is added to the PST filename. You must add the  `.pfile` extension to the name of the PST files in the CSV file.  </span></span><br/><br/> <span data-ttu-id="6b521-p149">**重要：** CSV 文件中的 PST 文件名称的大小写必须与已上载到在步骤 5 中的 Azure 的存储位置的 PST 文件相同。例如，如果您使用`annb.pst.pfile`中`Name`CSV 文件，但实际的 PST 文件的名称中的参数是`AnnB.pst`，该 PST 文件导入将失败。确保 CSV 文件中 PST 的名称，为实际的 PST 文件使用相同的大小写。</span><span class="sxs-lookup"><span data-stu-id="6b521-p149">**Important:** The case for the PST file name in the CSV file must be the same as the PST file that was uploaded to the Azure storage location in Step 5. For example, if you use  `annb.pst.pfile` in the  `Name` parameter in the CSV file, but the name of the actual PST file is  `AnnB.pst`, the import for that PST file will fail. Be sure that the name of the PST in the CSV file uses the same case as the actual PST file.</span></span>           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |<span data-ttu-id="6b521-361">指定要将 PST 文件导入到其中的邮箱的电子邮件地址。 </span><span class="sxs-lookup"><span data-stu-id="6b521-361">Specifies the email address of the mailbox that the PST file will be imported to.</span></span>  <br/> <span data-ttu-id="6b521-p150">若要导入非活动邮箱 PST 文件，您必须指定此参数的邮箱的邮箱 GUID。若要获取此 GUID，请运行以下 PowerShell 命令在 Exchange Online: Get-mailbox InactiveMailboxOnly<identity of inactive mailbox></span><span class="sxs-lookup"><span data-stu-id="6b521-p150">To import a PST file to an inactive mailbox, you have to specify the mailbox GUID for this parameter. To obtain this GUID, run the following PowerShell command in Exchange Online:  \`Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox></span></span> | <span data-ttu-id="6b521-364">FL Guid` <br/><br/> **Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-mailbox-<identity of active mailbox></span><span class="sxs-lookup"><span data-stu-id="6b521-364">FL Guid` <br/><br/> **Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox - <identity of active mailbox></span></span> | <span data-ttu-id="6b521-365">FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-mailbox- <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox</span><span class="sxs-lookup"><span data-stu-id="6b521-365">FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox</span></span> | <span data-ttu-id="6b521-366">FL Guid</span><span class="sxs-lookup"><span data-stu-id="6b521-366">FL Guid\`</span></span>           | `annb@contoso.onmicrosoft.com` <br/> <span data-ttu-id="6b521-367">或</span><span class="sxs-lookup"><span data-stu-id="6b521-367">Or</span></span>  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | <span data-ttu-id="6b521-p151">指定是否要将 PST 文件导入到用户的存档邮箱。有两个选项：</span><span class="sxs-lookup"><span data-stu-id="6b521-p151">Specifies whether or not to import the PST file to the user's archive mailbox. There are two options:  </span></span><br/> <span data-ttu-id="6b521-370">**FALSE**PST 文件导入到用户的主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="6b521-370">**FALSE** Imports the PST file to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="6b521-371">**TRUE**将 PST 文件导入到用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="6b521-371">**TRUE** Imports the PST file to the user's archive mailbox.</span></span>  <br/>  <span data-ttu-id="6b521-372">如果将此参数留空，PST 文件导入到用户的主邮箱。</span><span class="sxs-lookup"><span data-stu-id="6b521-372">If you leave this parameter blank, the PST file is imported to the user's primary mailbox.</span></span>  <br/><br/> <span data-ttu-id="6b521-373">**注意：** 若要 PST 文件导入到其主邮箱位于内部部署用户的基于云的存档邮箱中，只需指定此参数**为 TRUE** ，并指定用户的内部部署邮箱的电子邮件地址`Mailbox`参数。</span><span class="sxs-lookup"><span data-stu-id="6b521-373">**Note:** To import a PST file to a cloud-based archive mailbox for a user whose primary mailbox is on-premises, just specify **TRUE** for this parameter and specify the email address for the user's on-premises mailbox for the  `Mailbox` parameter.</span></span>           | `FALSE` <br/> <span data-ttu-id="6b521-374">或</span><span class="sxs-lookup"><span data-stu-id="6b521-374">Or</span></span>  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | <span data-ttu-id="6b521-375">指定 PST 文件导入到的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="6b521-375">Specifies the mailbox folder that the PST file is imported to.</span></span>  <br/>  <span data-ttu-id="6b521-376">如果将此参数留空，PST 将导入到新文件夹命名的**导入**位于 （相同级别的收件箱文件夹和其他默认邮箱文件夹） 的邮箱的根级别。</span><span class="sxs-lookup"><span data-stu-id="6b521-376">If you leave this parameter blank, the PST will be imported to a new folder named **Imported** located at the root level of the mailbox (the same level as the Inbox folder and the other default mailbox folders).</span></span>  <br/>  <span data-ttu-id="6b521-377">如果指定`/`，PST 文件中的项目在导入将直接在用户的收件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="6b521-377">If you specify  `/`, items in the PST file will be imported directly in to the user's Inbox folder.</span></span>  <br/>  <span data-ttu-id="6b521-p152">如果指定`/<foldername>`，PST 文件中的项目将导入到一个名为子*\<foldername\> * 。例如，如果您使用`/ImportedPst`，项目将导入到名为**ImportedPst**子文件夹。此子文件夹将位于用户的收件箱文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6b521-p152">If you specify  `/<foldername>`, items in the PST file will be imported to a subfolder named  *\<foldername\>*  . For example, if you used  `/ImportedPst`, items would be imported to a subfolder named **ImportedPst**. This subfolder will be located in the user's Inbox folder.  </span></span><br/><br/> <span data-ttu-id="6b521-381">**提示：** 考虑运行几个测试批次试验使用此参数，以便您可以确定要导入到 Pst 文件的最佳文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="6b521-381">**Tip:** Consider running a few test batches to experiment with this parameter so you can determine the best folder location to import PSTs files to.</span></span>           |<span data-ttu-id="6b521-382">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="6b521-382">(leave blank)</span></span>  <br/> <span data-ttu-id="6b521-383">或</span><span class="sxs-lookup"><span data-stu-id="6b521-383">Or</span></span>  <br/>  `/` <br/> <span data-ttu-id="6b521-384">或</span><span class="sxs-lookup"><span data-stu-id="6b521-384">Or</span></span>  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |<span data-ttu-id="6b521-p153">此可选参数指定要用于导入 PST 文件中的 ANSI 文件格式的代码页的数字值。此参数用于中文、 日语和朝鲜语 (CJK) 的组织中导入 PST 文件，因为这些语言通常用于双字节字符集 (DBCS) 字符编码。如果此参数不用于导入 PST 文件的邮箱文件夹名称中使用 DBCS 的语言，文件夹名称是通常会乱码后会在导入。有关受支持的值用于此参数的列表，请参阅[代码页标识符](https://go.microsoft.com/fwlink/p/?LinkId=328514)。</span><span class="sxs-lookup"><span data-stu-id="6b521-p153">This optional parameter specifies a numeric value for the code page to use for importing PST files in the ANSI file format. This parameter is used for importing PST files from Chinese, Japanese, and Korean (CJK) organizations because these languages typically use a double byte character set (DBCS) for character encoding. If this parameter isn't used to import PST files for languages that use DBCS for mailbox folder names, the folder names are often garbled after they're imported. For a list of supported values to use for this parameter, see [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).  </span></span><br/><br/> <span data-ttu-id="6b521-p154">**注意：** 如上文所述，这是一个可选参数，并且没有要包含在 CSV 文件中。或者，您可以将其包括并保留为空的一个或多个行。</span><span class="sxs-lookup"><span data-stu-id="6b521-p154">**Note:** As previously stated, this is an optional parameter and you don't have to include it in the CSV file. Or you can include it and leave the value blank for one or more rows.</span></span>           |<span data-ttu-id="6b521-391">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="6b521-391">(leave blank)</span></span>  <br/> <span data-ttu-id="6b521-392">或</span><span class="sxs-lookup"><span data-stu-id="6b521-392">Or</span></span>  <br/>  <span data-ttu-id="6b521-393">`932`（这是代码页标识符的 ANSI/OEM 日语）</span><span class="sxs-lookup"><span data-stu-id="6b521-393">`932` (which is the code page identifier for ANSI/OEM Japanese)</span></span>  <br/> |
    | `SPFileContainer` <br/> |<span data-ttu-id="6b521-394">对于 PST 导入，将该参数留空。 </span><span class="sxs-lookup"><span data-stu-id="6b521-394">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="6b521-395">不适用</span><span class="sxs-lookup"><span data-stu-id="6b521-395">Not applicable</span></span>  <br/> |
    | `SPManifestContainer` <br/> |<span data-ttu-id="6b521-396">对于 PST 导入，将该参数留空。 </span><span class="sxs-lookup"><span data-stu-id="6b521-396">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="6b521-397">不适用</span><span class="sxs-lookup"><span data-stu-id="6b521-397">Not applicable</span></span>  <br/> |
    | `SPSiteUrl` <br/> |<span data-ttu-id="6b521-398">对于 PST 导入，将该参数留空。 </span><span class="sxs-lookup"><span data-stu-id="6b521-398">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="6b521-399">不适用</span><span class="sxs-lookup"><span data-stu-id="6b521-399">Not applicable</span></span>  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a><span data-ttu-id="6b521-400">步骤 8：在 Office 365 中创建 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="6b521-400">Step 8: Create a PST Import job in Office 365</span></span>

<span data-ttu-id="6b521-p155">最后一步是创建 Office 365 中导入服务中的 PST 导入作业。如前所述，您将提交您在步骤 7 中创建的 PST 导入映射文件。导入服务创建新的作业后，将取消映射文件中使用的信息的加密和导入指定的用户邮箱的 PST 文件 （您上载到 Office 365 步骤 5 中）。</span><span class="sxs-lookup"><span data-stu-id="6b521-p155">The last step is to create the PST Import job in the Import service in Office 365. As previously explained, you will submit the PST Import mapping file that you created in Step 7. After you create the new job, the Import service will use the information in the mapping file to un-encrypt and import the PST files (that you uploaded to Office 365 in Step 5) to the specified user mailbox.</span></span> 
  
1. <span data-ttu-id="6b521-404">转到[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="6b521-404">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="6b521-405">登录到 Office 365 使用 Office 365 组织中的管理员帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="6b521-405">Sign in to Office 365 using the credentials for an administrator account in your Office 365 organization.</span></span>
    
3. <span data-ttu-id="6b521-406">在左窗格中，单击**数据管理**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="6b521-406">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
4. <span data-ttu-id="6b521-407">在**导入**页上，单击**转到导入服务**。</span><span class="sxs-lookup"><span data-stu-id="6b521-407">On the **Import** page, click **Go to the Import service**.</span></span>
    
5. <span data-ttu-id="6b521-408">在**到 Office 365 的导入数据**页上，单击**新建作业**![添加图标](media/ITPro-EAC-AddIcon.gif)，，然后单击**上载电子邮件 （PST 文件）**。</span><span class="sxs-lookup"><span data-stu-id="6b521-408">On the **Import data to Office 365** page, click **New job**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **Upload email messages (PST files)**.</span></span>
    
6. <span data-ttu-id="6b521-409">在**上载文件通过网络**页上单击**我已经完成了上载我文件**和**我有权访问映射文件**，选中框中，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6b521-409">On the **Upload files over the network** page, click the **I'm done uploading my files** and **I have access to the mapping file** check boxes, and then click **Next**.</span></span> 
    
7. <span data-ttu-id="6b521-410">为 PST 导入作业中，键入一个名称，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6b521-410">Type a name for the PST Import job, and then click **Next**.</span></span>
    
8. <span data-ttu-id="6b521-411">单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)选择在步骤 7 中创建的映射 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="6b521-411">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to select the PST Mapping file that you created in Step 7.</span></span> 
    
9. <span data-ttu-id="6b521-412">CSV 文件的名称出现在列表中后，选择它，然后单击**验证**以检查 CSV 文件中的错误。</span><span class="sxs-lookup"><span data-stu-id="6b521-412">After the name of the CSV file appears in the list, select it and then click **Validate** to check your CSV file for errors.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6b521-p156">与以前所述，PST 文件进行加密时，`.pfile`扩展追加到 PST 文件名。您必须添加`.pfile`中 CSV 文件的文件扩展名为 PST 的名称。否则，验证的 CSV 文件将失败。</span><span class="sxs-lookup"><span data-stu-id="6b521-p156">As previous explained, when the PST files are encrypted, a  `.pfile` extension is appended to the PST filename. You must add the  `.pfile` extension to the name of the PST files in the CSV file. If you don't, the validation of the CSV file will fail.</span></span> 
  
    <span data-ttu-id="6b521-p157">CSV 文件已成功验证创建 PST 导入作业。如果验证失败，请单击**状态**列中的链接**无效**。打开时的 PST 导入映射文件的副本，失败的文件中的各行的错误消息。</span><span class="sxs-lookup"><span data-stu-id="6b521-p157">The CSV file has to be successfully validated to create a PST Import job. If the validation fails, click the **Invalid** link in the **Status** column. A copy of your PST Import mapping file is opened, with a error message for each row in the file that failed.</span></span> 
    
10. <span data-ttu-id="6b521-419">当成功验证 PST 映射文件时，请阅读条款和条件文档，然后单击复选框。</span><span class="sxs-lookup"><span data-stu-id="6b521-419">When the PST mapping file is successfully validated, read the terms and conditions document, and then click the checkbox.</span></span>
    
11. <span data-ttu-id="6b521-420">单击**完成**以提交的作业。</span><span class="sxs-lookup"><span data-stu-id="6b521-420">Click **Finish** to submit the job.</span></span> 
    
    <span data-ttu-id="6b521-421">在**到 Office 365 的导入数据**页上的 PST 导入作业列表中显示该作业。</span><span class="sxs-lookup"><span data-stu-id="6b521-421">The job is displayed in the list of PST Import jobs on the **Import data to Office 365** page.</span></span> 
    
12. <span data-ttu-id="6b521-422">选择该作业，单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)要更新的详细信息窗格中显示的状态信息。</span><span class="sxs-lookup"><span data-stu-id="6b521-422">Select the job and click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the status information that's displayed in the details pane.</span></span> 
    
13. <span data-ttu-id="6b521-423">在详细信息窗格中，单击**查看详细信息**，以获取所选作业的最新状态。</span><span class="sxs-lookup"><span data-stu-id="6b521-423">In the details pane, click **View details** to get the latest status for the selected job.</span></span> 
 
## <a name="more-information"></a><span data-ttu-id="6b521-424">详细信息</span><span class="sxs-lookup"><span data-stu-id="6b521-424">More information</span></span>

- <span data-ttu-id="6b521-425">为什么到 Office 365 导入 PST 文件？</span><span class="sxs-lookup"><span data-stu-id="6b521-425">Why import PST files to Office 365?</span></span>
    
  - <span data-ttu-id="6b521-426">它是您组织的电子邮件迁移到 Office 365 的好方法。</span><span class="sxs-lookup"><span data-stu-id="6b521-426">It's a good way to migrate your organization's email to Office 365.</span></span>
    
  - <span data-ttu-id="6b521-427">通过允许您执行以下操作，有助于满足您的组织的合规性需求：</span><span class="sxs-lookup"><span data-stu-id="6b521-427">It helps address compliance needs of your organization by letting you:</span></span>
    
  - <span data-ttu-id="6b521-428">启用存档邮箱为用户提供额外的邮箱存储空间。</span><span class="sxs-lookup"><span data-stu-id="6b521-428">Enable archive mailboxes to give users additional mailbox storage space.</span></span>
    
  - <span data-ttu-id="6b521-429">将邮箱置于保留状态以保留内容。</span><span class="sxs-lookup"><span data-stu-id="6b521-429">Place mailboxes on hold to preserve content.</span></span>
    
  - <span data-ttu-id="6b521-430">使用 Microsoft 电子数据展示工具搜索邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="6b521-430">Use Microsoft eDiscovery tools to search for content in mailboxes.</span></span>
    
  - <span data-ttu-id="6b521-431">使用保留策略控制邮箱保留内容的时长。</span><span class="sxs-lookup"><span data-stu-id="6b521-431">Use retention policies to control how long mailbox content is retained.</span></span>
    
  - <span data-ttu-id="6b521-432">搜索 Office 365 审核日志中的邮箱相关的事件。</span><span class="sxs-lookup"><span data-stu-id="6b521-432">Search the Office 365 audit log for mailbox-related events.</span></span>
    
  - <span data-ttu-id="6b521-p158">它有助于防止数据丢失。PST 文件导入到 Office 365 邮箱继承而不是用户的计算机上存储数据的 Exchange Online 的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="6b521-p158">It helps protect against data loss. PST files that are imported to Office 365 mailboxes inherit the high availability features of Exchange Online, as opposed to storing the data on a user's computer.</span></span>
    
  - <span data-ttu-id="6b521-435">用户在任意设备上都可以使用数据，因为数据存储在云中。</span><span class="sxs-lookup"><span data-stu-id="6b521-435">The data is available to the user from all devices because it's stored in the cloud.</span></span>
    
- <span data-ttu-id="6b521-p159">下面是一个示例的键、 Id 和步骤 2、 3 和 4 中获得的 Url。此示例还包含 O365ImportTool.exe 工具进行加密中运行和上载 PST 文件到 Office 365 的命令的语法。请确保采取预防措施来保护这些只，如将保护密码或其他安全相关的信息。</span><span class="sxs-lookup"><span data-stu-id="6b521-p159">Here's an example of the keys, IDs, and URLs that are obtained in Steps 2, 3, and 4. This example also contains the syntax for the command that you run in the O365ImportTool.exe tool to encrypt and upload PST files to Office 365. Be sure to take precautions to protect these just like you would protect passwords or other security-related information.</span></span>
    
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

- <span data-ttu-id="6b521-p160">如前所述，Office 365 导入服务启用设置 （无限期的持续时间） PST 文件导入到邮箱后保留挂起状态。这意味着*RentionHoldEnabled*属性设置为`True`，以便将不会处理分配给邮箱的保留策略。这可以通过防止删除或较旧的消息进行存档的存档策略管理的新导入的邮件的邮箱所有者时间。下面是一些用于管理此保留挂起时可采取的步骤：</span><span class="sxs-lookup"><span data-stu-id="6b521-p160">As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RentionHoldEnabled*  property is set to  `True` so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold:</span></span> 
    
  - <span data-ttu-id="6b521-p161">在一段后的时间，则可以关闭保留挂起通过运行`Set-Mailbox -RetentionHoldEnabled $false`命令。有关说明，请参阅[就地保留邮箱保留](https://go.microsoft.com/fwlink/p/?LinkId=544749)。</span><span class="sxs-lookup"><span data-stu-id="6b521-p161">After a certain period of time, you can turn off the retention hold by running the  `Set-Mailbox -RetentionHoldEnabled $false` command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).</span></span>
    
  - <span data-ttu-id="6b521-p162">您可以配置保留挂起，以便它已关闭，以便将来一些日期。执行此操作通过运行`Set-Mailbox -EndDateForRetentionHold <date>`命令。例如，假设今天的日期是 2016 年 7 月 1，并且您希望保留保留在 30 天内已关闭，将运行以下命令： `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。在此方案中，将保留*RentionHoldEnabled*属性设置为`True`。有关详细信息，请参阅[Set-mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317)。</span><span class="sxs-lookup"><span data-stu-id="6b521-p162">You can configure the retention hold so that it's turned off on some date in the future. You do this by running the  `Set-Mailbox -EndDateForRetentionHold <date>` command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In this scenario, you would leave the  *RentionHoldEnabled*  property set to `True`. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).</span></span>
    
  - <span data-ttu-id="6b521-p163">您可以更改，以便不会立即删除或移动到用户的存档邮箱均已导入的旧项目分配给邮箱的保留策略的设置。例如，您无法加长删除或存档策略分配给邮箱的保留期限。在此方案中，则会关闭邮箱保留挂起后更改保留策略的设置。有关详细信息，请参阅[Office 365 组织中邮箱的存档和删除策略设置](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="6b521-p163">You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>

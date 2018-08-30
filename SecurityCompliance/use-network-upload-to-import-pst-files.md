---
title: 使用网络上载到 Office 365 导入您的组织 PST 文件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 管理员： 了解如何使用网络上载批量导入到 Office 365 中的用户邮箱的多个 PST 文件。
ms.openlocfilehash: c5bcaed9075939d098ac4bf9fbf4d8a94007232c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525156"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a><span data-ttu-id="ee1f8-103">使用网络上载到 Office 365 导入您的组织 PST 文件</span><span class="sxs-lookup"><span data-stu-id="ee1f8-103">Use network upload to import your organization PST files to Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="ee1f8-p101">本文是针对管理员。您试图将 PST 文件导入到您自己的邮箱？请参阅[导入电子邮件、 联系人和日历从 Outlook.pst 文件](https://go.microsoft.com/fwlink/p/?LinkID=785075)</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p101">This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)</span></span>
  
<span data-ttu-id="ee1f8-p102">以下是需要使用网络上载批量导入到 Office 365 邮箱的多个 PST 文件的分步说明。有关使用网络上载批量导入 PST 文件迁移到 Office 365 邮箱，请参阅[使用网络上载导入 PST 文件的常见问题](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files)的常见问题进行了问题。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p102">Here are the step-by-step instructions required to use network upload to bulk-import multiple PST files to Office 365 mailboxes. For frequently asked questions about using network upload to bulk-import PST files to Office 365 mailboxes, see [FAQs for using network upload to import PST files](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files).</span></span>
  
[<span data-ttu-id="ee1f8-109">步骤 1： 复制 SAS URL 并安装 Azure AzCopy</span><span class="sxs-lookup"><span data-stu-id="ee1f8-109">Step 1: Copy the SAS URL and install Azure AzCopy</span></span>](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[<span data-ttu-id="ee1f8-110">步骤 2： 将 PST 文件上载到 Office 365</span><span class="sxs-lookup"><span data-stu-id="ee1f8-110">Step 2: Upload your PST files to Office 365</span></span>](#step-2-upload-your-pst-files-to-office-365)

[<span data-ttu-id="ee1f8-111">（可选）步骤 3： 查看列表的 PST 文件上载到 Office 365</span><span class="sxs-lookup"><span data-stu-id="ee1f8-111">(Optional) Step 3: View a list of the PST files uploaded to Office 365</span></span>](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[<span data-ttu-id="ee1f8-112">步骤 4： 创建 PST 导入映射文件</span><span class="sxs-lookup"><span data-stu-id="ee1f8-112">Step 4: Create the PST Import mapping file</span></span>](#step-4-create-the-pst-import-mapping-file)

[<span data-ttu-id="ee1f8-113">步骤 5：在 Office 365 中创建 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="ee1f8-113">Step 5: Create a PST Import job in Office 365</span></span>](#step-5-create-a-pst-import-job-in-office-365)

[<span data-ttu-id="ee1f8-114">步骤 6： 筛选数据，并启动 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="ee1f8-114">Step 6: Filter data and start the PST Import job</span></span>](#step-6-filter-data-and-start-the-pst-import-job)

<span data-ttu-id="ee1f8-p103">请注意，您需要执行步骤 1 仅执行一次将 PST 文件导入到 Office 365 邮箱。执行这些步骤后，按照步骤 2 至步骤 6 每的次您想要上载并导入一批 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p103">Note that you have to perform Step 1 only once to import PST files to Office 365 mailboxes. After you perform these steps, follow Step 2 through Step 6 each time you want to upload and import a batch of PST files.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ee1f8-117">准备工作</span><span class="sxs-lookup"><span data-stu-id="ee1f8-117">Before you begin</span></span>
  
- <span data-ttu-id="ee1f8-p104">您必须为其分配导入导出邮箱角色在 Exchange Online 到 Office 365 邮箱导入 PST 文件。默认情况下，此角色不分配给任何角色组在 Exchange Online。您可以向组织管理角色组中添加邮箱导入导出角色。或者，您可以创建新的角色组、 分配的邮箱导入导出角色中，然后将自己添加为成员。有关详细信息，请参阅"添加角色向角色组"或"创建角色组"部分中[管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p104">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
    
    <span data-ttu-id="ee1f8-123">此外，若要创建导入作业 Office 365 安全性&amp;必须满足合规中心，下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="ee1f8-123">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
    
  - <span data-ttu-id="ee1f8-p105">您必须分配 Mail Recipients 角色在 Exchange Online。默认情况下，此角色分配给组织管理和 Recipient Management 角色组。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p105">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="ee1f8-126">或</span><span class="sxs-lookup"><span data-stu-id="ee1f8-126">Or</span></span>
    
  - <span data-ttu-id="ee1f8-127">您必须是 Office 365 组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-127">You have to be a global administrator in your Office 365 organization.</span></span>
    
  > [!TIP]
    > <span data-ttu-id="ee1f8-p106">请考虑在 Exchange Online 的专门用于将 PST 文件导入到 Office 365 中创建新的角色组。最小的导入 PST 文件所需的权限级别，将邮箱导入导出和 Mail Recipients 角色分配给新角色组中，，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p106">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
- <span data-ttu-id="ee1f8-p107">将 PST 文件导入到 Office 365 唯一受支持的方法是使用 Azure AzCopy 工具，如本主题中所述。不能使用 Azure 存储资源管理器上载直接到 Azure 存储区的 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p107">The only supported method for importing PST files to Office 365 is to use the Azure AzCopy tool, as described in this topic. You can't use the Azure Storage Explorer to upload PST files directly to the Azure storage area.</span></span>
    
- <span data-ttu-id="ee1f8-p108">您需要存储要导入到 Office 365 上的文件服务器或在组织中的共享的文件夹的 PST 文件。在步骤 2 中，您将运行 Azure AzCopy 工具将上载该文件服务器上存储或共享到 Office 365 的文件夹的 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p108">You need to store the PST files that you want to import to Office 365 on a file server or shared folder in your organization. In Step 2, you'll run the Azure AzCopy tool that will upload the PST files that are stored on this file server or shared folder to Office 365.</span></span>
    
- <span data-ttu-id="ee1f8-p109">此过程涉及复制并保存一份包含访问键的 URL。如果您想要查看上载到 Office 365 的 PST 文件的列表，在步骤 2 上载 PST 文件，并在步骤 3 中将使用此信息。请确保采取预防措施来保护此 URL，如将保护密码或其他安全相关的信息。例如受密码保护的 Microsoft Word 文档或加密的 USB 驱动器可能将其保存。请参阅此示例为[详细信息](#more-information)部分组合 URL 和密钥。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p109">This procedure involves copying and saving a copy of a URL that contains an access key. This information will be used in Step 2 to upload your PST files, and in Step 3 if you want to view a list of the PST files uploaded to Office 365. Be sure to take precautions to protect this URL like you would protect passwords or other security-related information. For example you might save it to a password-protected Microsoft Word document or to an encrypted USB drive. See the [More information](#more-information) section for an example of this combined URL and key.</span></span> 
    
- <span data-ttu-id="ee1f8-p110">您可以向 Office 365 中的非活动邮箱导入 PST 文件。执行此操作通过指定中的非活动邮箱的 GUID `Mailbox` PST 导入映射文件中的参数。有关此主题中的**说明**选项卡上，请参阅步骤 4。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p110">You can import PST files to an inactive mailbox in Office 365. You do this by specifying the GUID of the inactive mailbox in the  `Mailbox` parameter in the PST Import mapping file. See Step 4 on the **Instructions** tab in this topic for information.</span></span> 
    
- <span data-ttu-id="ee1f8-p111">在 Exchange 混合部署，您可以 PST 文件导入为其主邮箱位于内部部署用户的基于云的存档邮箱。通过执行以下 PST 导入映射文件中的执行此操作：</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p111">In an Exchange hybrid deployment, you can import PST files to a cloud-based archive mailbox for a user whose primary mailbox is on-premises. You do this by doing the following in the PST Import mapping file:</span></span>
    
  - <span data-ttu-id="ee1f8-144">指定用户的内部部署邮箱中的电子邮件地址`Mailbox`参数。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-144">Specify the email address for the user's on-premises mailbox in the  `Mailbox` parameter.</span></span> 
    
  - <span data-ttu-id="ee1f8-145">指定**TRUE**值在`IsArchive`参数。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-145">Specify the **TRUE** value in the  `IsArchive` parameter.</span></span> 
    
    <span data-ttu-id="ee1f8-146">有关详细信息，请参阅[步骤 4](#step-4-create-the-pst-import-mapping-file) 。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-146">See [Step 4](#step-4-create-the-pst-import-mapping-file) for more information.</span></span> 
    
- <span data-ttu-id="ee1f8-p112">PST 文件导入到 Office 365 邮箱后，设置为该邮箱保留挂起是无限期的持续时间内，打开的。这意味着关闭保留挂起或设置要关闭保留日期之前，将不会处理分配给邮箱的保留策略。为什么做的原因？如果旧导入到邮箱的邮件，它们可能被永久删除 （清除） 由于其保留期已过期基于配置为该邮箱的保留设置。将邮箱放在保留挂起将给邮箱所有者时间来管理这些新导入的邮件或授予时间更改邮箱的保留设置。请参阅有关管理保留挂起的建议本主题中的**详细信息**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p112">After PST files are imported to an Office 365 mailbox, the retention hold setting for the mailbox is turned on for an indefinite duration. This means that the retention policy assigned to the mailbox won't be processed until you turn off the retention hold or set a date to turn off the hold. Why do we do this? If messages imported to a mailbox are old, they might be permanently deleted (purged) because their retention period has expired based on the retention settings configured for the mailbox. Placing the mailbox on retention hold will give the mailbox owner time to manage these newly-imported messages or give you time to change the retention settings for the mailbox. See the **More info** tab in this topic for suggestions about managing the retention hold.</span></span> 
    
- <span data-ttu-id="ee1f8-p113">默认情况下，可以接收的 Office 365 邮箱的最大邮件大小为 35 MB。这是因为邮箱的*MaxReceiveSize*属性的默认值设置为 35 MB。但是，此限制的最大邮件接收 Office 365 中的大小为 150 MB。因此，如果导入 PST 文件包含大于 35 MB，我们将自动更改为 150 MB 的目标邮箱上*MaxReceiveSize*属性的值的导入 Office 365 服务的项。这将允许邮件 150 MB 要导入到用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p113">By default, the maximum message size that can be received by an Office 365 mailbox is 35 MB. That's because the default value for the  *MaxReceiveSize*  property for a mailbox is set to 35 MB. However, the limit for the maximum message receive size in Office 365 is 150 MB. So if you import a PST file that contains an item larger than 35 MB, the Office 365 Import service we will automatically change the value of the  *MaxReceiveSize*  property on the target mailbox to 150 MB. This allows messages up to 150 MB to be imported to user mailboxes.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="ee1f8-158">若要确定邮件接收大小为邮箱中，您可以运行此命令在 Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-158">To identify the message receive size for a mailbox, you can run this command in Exchange Online PowerShell:  `Get-Mailbox <user mailbox> | FL MaxReceiveSize`.</span></span> 

### <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a><span data-ttu-id="ee1f8-159">步骤 1： 复制 SAS URL 并安装 Azure AzCopy</span><span class="sxs-lookup"><span data-stu-id="ee1f8-159">Step 1: Copy the SAS URL and install Azure AzCopy</span></span>

<span data-ttu-id="ee1f8-p114">第一步是下载并安装 Azure AzCopy 工具，它是您将运行在步骤 2 到上载 PST 文件迁移到 Office 365 的工具。您还将为您的组织复制 SAS URL。此 URL 是 Microsoft 云的组织和共享访问签名 (SA) 键中的 Azure 存储位置的网络 URL 的组合。此项为您提供所需的权限将 PST 文件上载到 Azure 存储位置。请确保采取预防措施来保护 SAS URL。它是唯一的组织，并将在步骤 2 中使用。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p114">The first step is to download and install the Azure AzCopy tool, which is the tool that you'll run in Step 2 to upload PST files to Office 365. You'll also copy the SAS URL for your organization. This URL is a combination of the network URL for the Azure storage location in the Microsoft cloud for your organization and a Shared Access Signature (SAS) key. This key provides you with the necessary permissions to upload PST files to your Azure storage location. Be sure to take precautions to protect the SAS URL. It's unique to your organization and will be used in Step 2.</span></span>
  
 <span data-ttu-id="ee1f8-p115">**重要：** 我们建议您使用 Azure AzCopy 版本 7.1.0 使用网络导入 PST 文件上载方法。在下面的过程的步骤 6b 中下载版本 7.1.0。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p115">**Important:** We recommend that you use Azure AzCopy version 7.1.0 to import PST files by using the network upload method. Version 7.1.0 is downloaded in step 6b in the following procedure.</span></span> 
  
1. <span data-ttu-id="ee1f8-168">转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-168">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="ee1f8-169">在左侧窗格中的安全&amp;合规性中心，单击**数据调控** \> **导入**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-169">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
    <span data-ttu-id="ee1f8-p116">**注意：** 您需要分配适当的权限访问安全中的**导入**页上&amp;合规性中心。请参阅**开始之前**部分中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p116">**Note:** You have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center. See the **Before you begin** section for more information.</span></span> 
    
3. <span data-ttu-id="ee1f8-172">在**导入**页上单击![添加图标](media/ITPro-EAC-AddIcon.gif)**新建导入作业**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-172">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
    <span data-ttu-id="ee1f8-173">将显示导入作业向导。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-173">The import job wizard is displayed.</span></span>
    
4. <span data-ttu-id="ee1f8-p117">为 PST 导入作业中，键入一个名称，然后单击**下一步**。使用小写字母、 数字、 连字符和下划线。您无法使用大写字母或名称中包含空格。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p117">Type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="ee1f8-177">在**要上载或附带数据？** 页上，单击**上载数据**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-177">On the **Do you want to upload or ship data?** page, click **Upload your data** and then click **Next**.</span></span>
    
    ![单击上载以创建网络上载将数据导入作业](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. <span data-ttu-id="ee1f8-179">在**导入数据**页上，执行以下两项操作：</span><span class="sxs-lookup"><span data-stu-id="ee1f8-179">On the **Import data** page, do the following two things:</span></span> 
    
    ![复制 SAS URL 并下载导入数据页上的 Azure AzCopy 工具](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    <span data-ttu-id="ee1f8-p118">答： 在步骤 2 中，单击**显示网络上载 SAS URL**。显示 SAS URL 后，单击**复制到剪贴板**然后将其粘贴并将其保存到文件，以便您可以更高版本访问它。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p118">a. In step 2, click **Show network upload SAS URL**. After the SAS URL is displayed, click **Copy to clipboard** and then paste it and save it to a file so you can access it later.</span></span>
    
    <span data-ttu-id="ee1f8-p119">b.在步骤 3 中，单击**下载 Azure AzCopy**下载和安装 Azure AzCopy 工具。如上文所述，将下载版本 7.1.0。在弹出窗口中，单击**运行**以安装 AzCopy。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p119">b. In step 3, click **Download Azure AzCopy** to download and install the Azure AzCopy tool. As previously stated, version 7.1.0 will be downloaded. In the pop-up window, click **Run** to install AzCopy.</span></span> 
    
  <span data-ttu-id="ee1f8-188">**注意：** 您可以**导入数据**页将保持打开状态 （以防您需要再次复制 SAS URL），或单击**取消**以关闭它。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-188">**Note:** You can leave the **Import data** page open (in case you need to copy the SAS URL again) or click **Cancel** to close it.</span></span> 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a><span data-ttu-id="ee1f8-189">步骤 2： 将 PST 文件上载到 Office 365</span><span class="sxs-lookup"><span data-stu-id="ee1f8-189">Step 2: Upload your PST files to Office 365</span></span>

<span data-ttu-id="ee1f8-p120">现在您已准备好使用 AzCopy.exe 工具将 PST 文件上载到 Office 365。此工具上载，并将其存储在云中的 Microsoft Azure 的存储位置。如前所述，则上载到 PST 文件的 Azure 的存储位置位于同一区域 Microsoft 数据中心中您的 Office 365 组织所在的位置。若要完成此步骤，PST 文件必须位于文件共享或组织中的文件服务器。这就是在下面的过程的源目录。每次运行 AzCopy 工具，您可以指定一个不同的源目录。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p120">Now you're ready to use the AzCopy.exe tool to upload PST files to Office 365. This tool uploads and stores them in an Azure storage location in the Microsoft cloud. As previously explained, the Azure storage location that you upload your PST files to resides in the same regional Microsoft datacenter where your Office 365 organization is located. To complete this step, the PST files have to be located in a file share or file server in your organization. This is known as the source directory in the following procedure. Each time you run the AzCopy tool, you can specify a different source directory.</span></span> 
  
1. <span data-ttu-id="ee1f8-196">在您的本地计算机上打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-196">Open a Command Prompt on your local computer.</span></span>
    
2. <span data-ttu-id="ee1f8-p121">转到的目录 AzCopy.exe 工具在步骤 1 中的安装位置。如果您在默认位置安装该工具，请转到`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p121">Go to the directory where you installed the AzCopy.exe tool in Step 1. If you installed the tool in the default location, go to `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`.</span></span>
    
3. <span data-ttu-id="ee1f8-199">运行以下命令以将 PST 文件上载到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-199">Run the following command to upload the PST files to Office 365.</span></span>

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    <span data-ttu-id="ee1f8-p122">下表介绍参数以及它们所需的值。请注意您在上一步中获得该信息用于这些参数的值。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p122">The following table describes the parameters and their required values. Note that the information you obtained in the previous step is used in the values for these parameters.</span></span>
    
    |<span data-ttu-id="ee1f8-202">**参数**</span><span class="sxs-lookup"><span data-stu-id="ee1f8-202">**Parameter**</span></span>|<span data-ttu-id="ee1f8-203">**说明**</span><span class="sxs-lookup"><span data-stu-id="ee1f8-203">**Description**</span></span>|<span data-ttu-id="ee1f8-204">**示例**</span><span class="sxs-lookup"><span data-stu-id="ee1f8-204">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |<span data-ttu-id="ee1f8-205">指定包含 PST 文件将上载到 Office 365 组织中的源目录。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-205">Specifies the source directory in your organization that contains the PST files that will be uploaded to Office 365.</span></span>  <br/> <span data-ttu-id="ee1f8-206">请务必用双引号 (" ") 引住此参数的值。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-206">Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |<span data-ttu-id="ee1f8-207">步骤 1 中指定您获取的 SAS URL。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-207">Specifies the SAS URL that you obtained in Step 1.</span></span>  <br/> <span data-ttu-id="ee1f8-208">请务必用双引号 (" ") 引住此参数的值。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-208">Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> <span data-ttu-id="ee1f8-p123">**提示：**（可选）Azure 的存储位置上载到 PST 文件中，您可以指定子文件夹。通过添加 （之后"ingestiondata") 的子文件夹位置 SAS URL 中执行此操作。第一个示例不指定子文件夹;这意味着 Pst 将上载到根目录 （名为*ingestiondata* ） Azure 的存储位置。第二个示例上载到子文件夹 （名为*PSTFiles* ） 的 PST 文件的 Azure 的存储位置的根目录。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p123">**Tip:** (Optional) You can specify a subfolder in the Azure storage location to upload the PST files to. You do this by adding a subfolder location (after "ingestiondata") in the SAS URL. The first example doesn't specify a subfolder; that means the PSTs will be uploaded to the root (named  *ingestiondata*  ) of the Azure storage location. The second example uploads the PST files to a subfolder (named  *PSTFiles*  ) in the root of the Azure storage location.  </span></span><br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> <span data-ttu-id="ee1f8-213">或</span><span class="sxs-lookup"><span data-stu-id="ee1f8-213">Or</span></span>  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |<span data-ttu-id="ee1f8-p124">将详细状态消息输出到日志文件。默认情况下，详细日志文件名为 AzCopyVerbose.log，所在路径为 %LocalAppData%\Microsoft\Azure\AzCopy。如果对此选项指定现有的文件位置，则详细日志将被附加到该文件中。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p124">Outputs verbose status messages into a log file. By default, the verbose log file is named AzCopyVerbose.log in %LocalAppData%\Microsoft\Azure\AzCopy. If you specify an existing file location for this option, the verbose log will be appended to that file.</span></span>  <br/> <span data-ttu-id="ee1f8-217">请务必用双引号 (" ") 引住此参数的值。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-217">Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |<span data-ttu-id="ee1f8-218">此可选开关指定递归模式，以便 AzCopy 工具会将位于指定源目录中的子文件夹中的 Pst 文件复制`/Source:`参数。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-218">This optional switch specifies the recursive mode so that the AzCopy tool will copy PSTs files that are located in subfolders in the source directory that is specified by the  `/Source:` parameter.</span></span>  <br/> <span data-ttu-id="ee1f8-p125">**注意：** 如果包括此开关，子文件夹中的 PST 文件将 Azure 存储位置中具有不同文件路径名，他们正在上载后。您将需要在您在步骤 4 中创建的 CSV 文件中指定的确切文件路径名。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p125">**Note:** If you include this switch, PST files in subfolders will have a different file pathname in the Azure storage location after they're uploaded. You'll have to specify the exact file pathname in the CSV file that you create in Step 4.  </span></span><br/> | `/S` <br/> |
    | `/Y` <br/> |<span data-ttu-id="ee1f8-p126">此必需的开关允许使用只写 SAS 令牌，当您将 PST 文件上载到 Azure 存储位置。您在步骤 1 中获得 SAS URL (和指定的`/Dest:`参数) 是只写 SAS URL，因此，您必须包括此开关。请注意，只写 SAS URL 不会阻止您使用 Azure 存储浏览器查看上载到 Azure 存储位置的 PST 文件的列表。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p126">This required switch allows the use of write-only SAS tokens when you upload the PST files to the Azure storage location. The SAS URL you obtained in step 1 (and specified in  `/Dest:` parameter) is a write-only SAS URL, which is why you must include this switch. Note that a write-only SAS URL will not prevent you from using the Azure Storage Explorer to view a list of the PST files uploaded to the Azure storage location.  </span></span><br/> | `/Y` <br/> |
   
<span data-ttu-id="ee1f8-224">以下是对每个参数使用实际值的 AzCopy.exe 工具的语法示例：</span><span class="sxs-lookup"><span data-stu-id="ee1f8-224">Here's an example of the syntax for the AzCopy.exe tool using actual values for each parameter:</span></span>
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

<span data-ttu-id="ee1f8-p127">运行该命令后，显示的状态消息会显示对 PST 文件进行上载的进度。最终状态消息显示已成功上载的文件总数。 </span><span class="sxs-lookup"><span data-stu-id="ee1f8-p127">After you run the command, status messages are displayed that show the progress of uploading the PST files. A final status message shows the total number of files that were successfully uploaded.</span></span>
    
<span data-ttu-id="ee1f8-p128">**提示：** 在成功运行 AzCopy.exe 命令并确认所有参数都正确无误后，保存一份同一个复制信息的位置 （安全） 文件的命令行语法获取在步骤 1 中。然后可以复制并粘贴在命令提示符下每次您想要运行 AzCopy.exe 工具以将 PST 文件上载到 Office 365 的此命令。您可能需要更改的唯一值是为`/Source:`参数。这取决于源目录 PST 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p128">**Tip:** After you successfully run the AzCopy.exe command and verify that all the parameters are correct, save a copy of the command line syntax to the same (secured) file where you copied the information you obtained in Step 1. Then you can copy and paste this command in a Command Prompt each time that you want to run the AzCopy.exe tool to upload PST files to Office 365. The only value you might have to change are the ones for the  `/Source:` parameter. This depends on the source directory where the PST files are located.</span></span> 

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a><span data-ttu-id="ee1f8-231">（可选）步骤 3： 查看列表的 PST 文件上载到 Office 365</span><span class="sxs-lookup"><span data-stu-id="ee1f8-231">(Optional) Step 3: View a list of the PST files uploaded to Office 365</span></span>

<span data-ttu-id="ee1f8-p129">作为一个可选步骤，您可以安装和使用 Microsoft Azure 存储浏览器 （这是一个免费的开源工具） 若要查看已上载到 Azure blob PST 文件的列表。有两个理由，让您执行此操作：</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p129">As an optional step, you can install and use the Microsoft Azure Storage Explorer (which is a free, open source tool) to view the list of the PST files that you've uploaded to the Azure blob. There are two good reasons to do this:</span></span>
  
- <span data-ttu-id="ee1f8-234">验证 PST 文件从共享的文件夹或组织中的文件服务器已成功上载到 Azure 的 blob。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-234">Verify that PST files from the shared folder or file server in your organization were successfully uploaded to the Azure blob.</span></span>
    
- <span data-ttu-id="ee1f8-p130">验证每个 PST 文件上载到 Azure blob 的文件名 （和子文件夹路径名如果包括了一个）。正在创建 PST 映射文件的下一步，因为您有时必须指定的文件夹路径名和文件名为每个 PST 文件时，这是非常有用。验证这些名称，可帮助减少 PST 映射文件中的潜在错误。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p130">Verify the filename (and the subfolder pathname if you included one) for each PST file uploaded to the Azure blob. This is really helpful when you're creating the PST mapping file in the next step because you have to specify both the folder pathname and filename for each PST file. Verifying these names can help reduce potential errors in your PST mapping file.</span></span>
    
<span data-ttu-id="ee1f8-238">Microsoft Azure 存储 Explorer 正处于预览。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-238">The Microsoft Azure Storage Explorer is in Preview.</span></span>
  
 <span data-ttu-id="ee1f8-p131">**重要：** 不能使用 Azure 存储资源管理器上载或修改 PST 文件。将 PST 文件导入到 Office 365 唯一受支持的方法是使用 AzCopy。此外，您不能删除已上载到 Azure blob 的 PST 文件。如果尝试删除 PST 文件，您会收到了有关未获得所需的权限的错误。请注意自动从您 Azure 存储区删除所有 PST 文件。如果没有导入作业正在运行，则所有 PST 文件中的 * * ingestiondata * * 容器被删除 30 天后创建的最新的导入作业。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p131">**Important:** You can't use the Azure Storage Explorer to upload or modify PST files. The only supported method for importing PST files to Office 365 is to use AzCopy. Also, you can't delete PST files that you've uploaded to the Azure blob. If you try to delete a PST file, you'll receive an error about not having the required permissions. Note that all PST files are automatically deleted from your Azure storage area. If there are no import jobs in progress, then all PST files in the ** ingestiondata ** container are deleted 30 days after the most recent import job was created.</span></span> 
  
<span data-ttu-id="ee1f8-245">安装 Azure 存储浏览器并连接到 Azure 存储区：</span><span class="sxs-lookup"><span data-stu-id="ee1f8-245">To install the Azure Storage Explorer and connect to your Azure storage area:</span></span>
  
1. <span data-ttu-id="ee1f8-246">下载并安装[Microsoft Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-246">Download and install the [Microsoft Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span>
    
2. <span data-ttu-id="ee1f8-247">启动 Microsoft Azure 存储资源管理器，在左窗格中右键单击**存储帐户**，然后单击**连接到 Azure 存储**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-247">Start the Microsoft Azure Storage Explorer, right-click **Storage Accounts** in the left pane, and then click **Connect to Azure storage**.</span></span>
    
    ![右键单击存储帐户，然后单击连接到 Azure 存储](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. <span data-ttu-id="ee1f8-249">单击**使用共享的访问签名 (SA) URI 或连接字符串**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-249">Click **Use a shared access signature (SAS) URI or connection string** and click **Next**.</span></span>
    
4. <span data-ttu-id="ee1f8-250">单击**使用 SAS URI**，将在步骤 1 中的获取 SAS URL 粘贴到**URI**下的框，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-250">Click **Use a SAS URI**, paste the SAS URL that you obtained in Step 1 into the box under **URI**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="ee1f8-251">在**连接摘要**页中，您可以查看连接信息，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-251">On the **Connection summary** page, you can review the connection information, and then click **Connect**.</span></span>
    
    <span data-ttu-id="ee1f8-p132">打开**ingestiondata**容器;它包含您在步骤 2 中上载的 PST 文件。**Ingestiondata**容器位于**存储帐户**下\> **（SAS-Attached 服务）** \> **Blob 容器**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p132">The **ingestiondata** container is opened; it contains the PST files that you uploaded in Step 2. The **ingestiondata** container is located under **Storage Accounts** \> **(SAS-Attached Services)** \> **Blob Containers**.</span></span> 
    
    ![Azure 存储资源管理器显示你上载的 PST 文件的列表](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. <span data-ttu-id="ee1f8-p133">完成后使用 Microsoft Azure 存储浏览器，右键单击**ingestiondata**，，然后单击**分离**断开 Azure 存储区。否则，您会收到错误的下次尝试附加。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p133">When you're finished using the Microsoft Azure Storage Explorer, right-click **ingestiondata**, and then click **Detach** to disconnect from your Azure storage area. Otherwise, you'll receive an error the next time you try to attach.</span></span> 
    
    ![右键单击“引入”，然后单击“分离”以从 Azure 存储区域断开连接](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a><span data-ttu-id="ee1f8-258">步骤 4： 创建 PST 导入映射文件</span><span class="sxs-lookup"><span data-stu-id="ee1f8-258">Step 4: Create the PST Import mapping file</span></span>

<span data-ttu-id="ee1f8-p134">PST 文件已上载到 Office 365 组织的 Azure 存储位置后下, 一步是创建逗号分隔值 (CSV) 文件，指定 PST 文件将被导入到哪些用户邮箱。创建 PST 导入作业时，您将提交的下一步此 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p134">After the PST files have been uploaded to the Azure storage location for your Office 365 organization, the next step is to create a comma separated value (CSV) file that specifies which user mailboxes the PST files will be imported to. You'll submit this CSV file in the next step when you create a PST Import job.</span></span>
  
1. <span data-ttu-id="ee1f8-261">[下载 PST 导入映射文件的副本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-261">[Download a copy of the PST Import mapping file](https://go.microsoft.com/fwlink/p/?LinkId=544717).</span></span>
    
2. <span data-ttu-id="ee1f8-p135">打开或将 CSV 文件保存到您的本地计算机。下面的示例显示已完成的 PST 导入映射文件（在记事本中打开）。使用 Microsoft Excel 编辑 CSV 文件变得容易得多。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p135">Open or save the CSV file to your local computer. The following example shows a completed PST Import mapping file (opened in NotePad). It's much easier to use Microsoft Excel to edit the CSV file.</span></span>


    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,PSTFiles,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,PSTFiles,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```
    <span data-ttu-id="ee1f8-p136">标题行，CSV 文件的第一行中，列出 PST 导入服务将用于将 PST 文件导入到用户邮箱的参数。每个参数名称并用逗号分隔。在标题行下的各行代表 PST 文件导入到特定邮箱的参数值。对于每个要导入到用户邮箱的 PST 文件，您将需要一行。请务必映射文件中的占位符数据替换为实际数据。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p136">The first row, or header row, of the CSV file lists the parameters that will be used by the PST Import service to import the PST files to user mailboxes. Each parameter name is separated by a comma. Each row under the header row represents the parameter values for importing a PST file to a specific mailbox. You will need a row for each PST file that you want to import to a user mailbox. Be sure to replace the placeholder data in the mapping file with your actual data.</span></span>

   <span data-ttu-id="ee1f8-270">**注意：** 不更改包括 SharePoint 参数; 在标题行中的任何内容它们将 PST 导入过程中忽略。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-270">**Note:** Don't change anything in the header row, including the SharePoint parameters; they will be ignored during the PST Import process.</span></span> 

 3. <span data-ttu-id="ee1f8-271">使用下表中的信息来填充附有所需信息的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-271">Use the information in the following table to populate the CSV file with the required information.</span></span>


    |<span data-ttu-id="ee1f8-272">**参数**</span><span class="sxs-lookup"><span data-stu-id="ee1f8-272">**Parameter**</span></span>|<span data-ttu-id="ee1f8-273">**说明**</span><span class="sxs-lookup"><span data-stu-id="ee1f8-273">**Description**</span></span>|<span data-ttu-id="ee1f8-274">**示例**</span><span class="sxs-lookup"><span data-stu-id="ee1f8-274">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `Workload` <br/> |<span data-ttu-id="ee1f8-p137">指定数据将导入到的 Office 365 服务。若要为用户邮箱导入 PST 文件，请使用`Exchange`。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p137">Specifies the Office 365 service that data will be imported to. To import PST files to user mailboxes, use  `Exchange`.  </span></span><br/> | `Exchange` <br/> |
    | `FilePath` <br/> |<span data-ttu-id="ee1f8-277">在您上载 PST 文件迁移到在步骤 2 中的 Azure 的存储位置指定的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-277">Specifies the folder location in the Azure storage location that you uploaded the PST files to in Step 2.</span></span>  <br/> <span data-ttu-id="ee1f8-p138">如果您没有在 SAS URL 中包括的可选子文件夹名称`/Dest:`参数在步骤 2 中，将此参数留空 CSV 文件中。包含子文件夹名称，如果指定此参数中 （请参阅第二个示例）。此参数的值是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p138">If you didn't include an optional subfolder name in the SAS URL in the  `/Dest:` parameter in Step 2, leave this parameter blank in the CSV file. If you included a subfolder name, specify it in this parameter (see the second example). The value for this parameter is case sensitive.  </span></span><br/> <span data-ttu-id="ee1f8-281">两种方法，在的值*不*包括"ingestiondata"`FilePath`参数。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-281">Either way,  *don't*  include "ingestiondata" in the value for the  `FilePath` parameter.</span></span>  <br/><br/> <span data-ttu-id="ee1f8-p139">**重要：** 这种情况的文件路径名称必须使用如果您在 SAS URL 中包括的可选子文件夹名称的情况下相同`/Dest:`在步骤 2 中的参数。例如，如果您使用`PSTFiles`的子文件夹命名为在步骤 2 中，然后使用`pstfiles`的`FilePath`CSV 文件中的参数，PST 文件导入将失败。请务必在这两种情况下使用相同的大小写。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p139">**Important:** The case for the file path name must be the same as the case you used if you included an optional subfolder name in the SAS URL in the  `/Dest:` parameter in Step 2. For example, if you used  `PSTFiles` for the subfolder name in Step 2 and then use  `pstfiles` in the  `FilePath` parameter in CSV file, the import for the PST file will fail. Be sure to use the same case in both instances.  </span></span><br/> |<span data-ttu-id="ee1f8-285">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="ee1f8-285">(leave blank)</span></span>  <br/> <span data-ttu-id="ee1f8-286">或</span><span class="sxs-lookup"><span data-stu-id="ee1f8-286">Or</span></span>  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |<span data-ttu-id="ee1f8-p140">指定将导入到用户邮箱的 PST 文件的名称。此参数的值是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p140">Specifies the name of the PST file that will be imported to the user mailbox. The value for this parameter is case sensitive.  </span></span><br/> <br/><span data-ttu-id="ee1f8-p141">**重要：** CSV 文件中的 PST 文件名称的大小写必须与已上载到在步骤 2 中的 Azure 的存储位置的 PST 文件相同。例如，如果您使用`annb.pst`中`Name`CSV 文件，但实际的 PST 文件的名称中的参数是`AnnB.pst`，该 PST 文件导入将失败。确保 CSV 文件中 PST 的名称，为实际的 PST 文件使用相同的大小写。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p141">**Important:** The case for the PST file name in the CSV file must be the same as the PST file that was uploaded to the Azure storage location in Step 2. For example, if you use  `annb.pst` in the  `Name` parameter in the CSV file, but the name of the actual PST file is  `AnnB.pst`, the import for that PST file will fail. Be sure that the name of the PST in the CSV file uses the same case as the actual PST file.  </span></span><br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |<span data-ttu-id="ee1f8-p142">指定的邮箱的 PST 文件导入到的电子邮件地址。请注意，不能指定公用文件夹，因为 PST 导入服务不支持将 PST 文件导入到公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p142">Specifies the email address of the mailbox that the PST file will be imported to. Note that you can't specify a public folder because the PST Import Service doesn't support importing PST files to public folders.  </span></span><br/> <span data-ttu-id="ee1f8-p143">若要导入非活动邮箱 PST 文件，您必须指定此参数的邮箱的邮箱 GUID。若要获取此 GUID，请运行以下 PowerShell 命令在 Exchange Online: Get-mailbox <identity of inactive mailbox> -InactiveMailboxOnly</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p143">To import a PST file to an inactive mailbox, you have to specify the mailbox GUID for this parameter. To obtain this GUID, run the following PowerShell command in Exchange Online:  \`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly</span></span> | <span data-ttu-id="ee1f8-296">FL Guid` <br/> <br/>**Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-mailbox<identity of active mailbox></span><span class="sxs-lookup"><span data-stu-id="ee1f8-296">FL Guid` <br/> <br/>**Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox <identity of active mailbox></span></span> | <span data-ttu-id="ee1f8-297">FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox</span><span class="sxs-lookup"><span data-stu-id="ee1f8-297">FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox</span></span> | <span data-ttu-id="ee1f8-298">FL Guid。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-298">FL Guid\`.</span></span>  <br/> | `annb@contoso.onmicrosoft.com` <br/> <span data-ttu-id="ee1f8-299">或</span><span class="sxs-lookup"><span data-stu-id="ee1f8-299">Or</span></span>  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | <span data-ttu-id="ee1f8-p144">指定是否要将 PST 文件导入到用户的存档邮箱。有两个选项：</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p144">Specifies whether or not to import the PST file to the user's archive mailbox. There are two options:  </span></span><br/><br/><span data-ttu-id="ee1f8-302">**FALSE** -导入用户的主邮箱的 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-302">**FALSE** - Imports the PST file to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="ee1f8-p145">**TRUE** -将 PST 文件导入用户的存档邮箱。这假定[已启用用户的存档邮箱](enable-archive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p145">**TRUE** - Imports the PST file to the user's archive mailbox. This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). </span></span><br/><br/><span data-ttu-id="ee1f8-p146">如果将此参数设置为`TRUE`和用户的存档邮箱未启用，为该用户导入将失败。请注意，如果导入失败的一个用户 (因为其归档未启用，此属性设置为`TRUE`)，不会影响导入作业中的其他用户。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p146">If you set this parameter to  `TRUE` and the user's archive mailbox isn't enabled, the import for that user will fail. Note that if an import fails for one user (because their archive isn't enabled and this property is set to  `TRUE`), the other users in the import job won't be affected.  </span></span><br/>  <span data-ttu-id="ee1f8-307">如果将此参数留空，PST 文件导入到用户的主邮箱。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-307">If you leave this parameter blank, the PST file is imported to the user's primary mailbox.</span></span>  <br/> <br/><span data-ttu-id="ee1f8-308">**注意：** PST 文件导入到其主邮箱位于内部部署用户的基于云的存档邮箱中，只需指定`TRUE`为此参数指定用户的内部部署邮箱的电子邮件地址和`Mailbox`参数。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-308">**Note:** To import a PST file to a cloud-based archive mailbox for a user whose primary mailbox is on-premises, just specify  `TRUE` for this parameter and specify the email address for the user's on-premises mailbox for the  `Mailbox` parameter.</span></span>  <br/> | `FALSE` <br/> <span data-ttu-id="ee1f8-309">或</span><span class="sxs-lookup"><span data-stu-id="ee1f8-309">Or</span></span>  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | <span data-ttu-id="ee1f8-310">指定 PST 文件导入到的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-310">Specifies the mailbox folder that the PST file is imported to.</span></span>  <br/>  <span data-ttu-id="ee1f8-311">如果将此参数留空，PST 将导入到新文件夹命名的**导入**位于 （相同级别的收件箱文件夹和其他默认邮箱文件夹） 的邮箱的根级别。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-311">If you leave this parameter blank, the PST will be imported to a new folder named **Imported** located at the root level of the mailbox (the same level as the Inbox folder and the other default mailbox folders).</span></span>  <br/>  <span data-ttu-id="ee1f8-312">如果指定`/`，PST 文件中的项目在导入将直接在用户的收件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-312">If you specify  `/`, items in the PST file will be imported directly in to the user's Inbox folder.</span></span>  <br/><br/>  <span data-ttu-id="ee1f8-p147">如果指定`/<foldername>`，PST 文件中的项目将导入到一个名为文件夹*\<foldername\> * 。例如，如果您使用`/ImportedPst`，项目将导入到一个名为**ImportedPst**文件夹。此文件夹将位于收件箱文件夹相同级别的用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p147">If you specify  `/<foldername>`, items in the PST file will be imported to a folder named  *\<foldername\>*  . For example, if you use  `/ImportedPst`, items would be imported to a folder named **ImportedPst**. This folder will be located in the user's mailbox at the same level as the Inbox folder.  </span></span><br/><br/> <span data-ttu-id="ee1f8-316">**提示：** 考虑运行几个测试批次试验使用此参数，以便您可以确定要导入到 Pst 文件的最佳文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-316">**Tip:** Consider running a few test batches to experiment with this parameter so you can determine the best folder location to import PSTs files to.</span></span>  <br/> |<span data-ttu-id="ee1f8-317">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="ee1f8-317">(leave blank)</span></span>  <br/> <span data-ttu-id="ee1f8-318">或</span><span class="sxs-lookup"><span data-stu-id="ee1f8-318">Or</span></span>  <br/>  `/` <br/> <span data-ttu-id="ee1f8-319">或</span><span class="sxs-lookup"><span data-stu-id="ee1f8-319">Or</span></span>  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |<span data-ttu-id="ee1f8-p148">此可选参数指定要用于导入 PST 文件中的 ANSI 文件格式的代码页的数字值。此参数用于中文、 日语和朝鲜语 (CJK) 的组织中导入 PST 文件，因为这些语言通常用于双字节字符集 (DBCS) 字符编码。如果此参数不用于导入 PST 文件的邮箱文件夹名称中使用 DBCS 的语言，文件夹名称是通常会乱码后会在导入。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p148">This optional parameter specifies a numeric value for the code page to use for importing PST files in the ANSI file format. This parameter is used for importing PST files from Chinese, Japanese, and Korean (CJK) organizations because these languages typically use a double byte character set (DBCS) for character encoding. If this parameter isn't used to import PST files for languages that use DBCS for mailbox folder names, the folder names are often garbled after they're imported.  </span></span><br/><br/> <span data-ttu-id="ee1f8-323">有关受支持的值用于此参数的列表，请参阅[代码页标识符](https://go.microsoft.com/fwlink/p/?LinkId=328514)。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-323">For a list of supported values to use for this parameter, see [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).</span></span>  <br/> <br/><span data-ttu-id="ee1f8-p149">**注意：** 如上文所述，这是一个可选参数，并且没有要包含在 CSV 文件中。或者，您可以将其包括并保留为空的一个或多个行。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p149">**Note:** As previously stated, this is an optional parameter and you don't have to include it in the CSV file. Or you can include it and leave the value blank for one or more rows.  </span></span><br/> |<span data-ttu-id="ee1f8-326">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="ee1f8-326">(leave blank)</span></span>  <br/> <span data-ttu-id="ee1f8-327">或</span><span class="sxs-lookup"><span data-stu-id="ee1f8-327">Or</span></span>  <br/>  <span data-ttu-id="ee1f8-328">`932`（这是代码页标识符的 ANSI/OEM 日语）</span><span class="sxs-lookup"><span data-stu-id="ee1f8-328">`932` (which is the code page identifier for ANSI/OEM Japanese)</span></span>  <br/> |
    | `SPFileContainer` <br/> |<span data-ttu-id="ee1f8-329">对于 PST 导入，将该参数留空。 </span><span class="sxs-lookup"><span data-stu-id="ee1f8-329">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="ee1f8-330">不适用</span><span class="sxs-lookup"><span data-stu-id="ee1f8-330">Not applicable</span></span>  <br/> |
    | `SPManifestContainer` <br/> |<span data-ttu-id="ee1f8-331">对于 PST 导入，将该参数留空。 </span><span class="sxs-lookup"><span data-stu-id="ee1f8-331">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="ee1f8-332">不适用</span><span class="sxs-lookup"><span data-stu-id="ee1f8-332">Not applicable</span></span>  <br/> |
    | `SPSiteUrl` <br/> |<span data-ttu-id="ee1f8-333">对于 PST 导入，将该参数留空。 </span><span class="sxs-lookup"><span data-stu-id="ee1f8-333">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="ee1f8-334">不适用</span><span class="sxs-lookup"><span data-stu-id="ee1f8-334">Not applicable</span></span>  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a><span data-ttu-id="ee1f8-335">步骤 5：在 Office 365 中创建 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="ee1f8-335">Step 5: Create a PST Import job in Office 365</span></span>

<span data-ttu-id="ee1f8-p150">下一步是创建 Office 365 中导入服务中的 PST 导入作业。如前所述，您将提交您在步骤 4 中创建的 PST 导入映射文件。创建新的作业后，Office 365 分析 PST 文件中的数据，并使您能够筛选实际上获取导入到邮箱 PST 导入映射文件中指定的数据 （请参阅[步骤 6](#step-6-filter-data-and-start-the-pst-import-job)）。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p150">The next step is to create the PST Import job in the Import service in Office 365. As previously explained, you will submit the PST Import mapping file that you created in Step 4. After you create the new job, Office 365 analyzes the data in the PST files and then gives you an opportunity to filter the data that actually gets imported to the mailboxes specified in the PST import mapping file (see [Step 6](#step-6-filter-data-and-start-the-pst-import-job)).</span></span>
  
1. <span data-ttu-id="ee1f8-339">转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-339">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="ee1f8-340">在左侧窗格中的安全&amp;合规性中心，单击**数据调控**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-340">In the left pane of the Security &amp; Compliance Center, click **Data governance** and then click **Import**.</span></span>
    
3. <span data-ttu-id="ee1f8-341">在**导入**页上单击![添加图标](media/ITPro-EAC-AddIcon.gif)**新建导入作业**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-341">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
    <span data-ttu-id="ee1f8-p151">**注意：** 您需要分配访问安全性中的**导入**页的适当权限&amp;合规性中心，以创建新的导入作业。请参阅**开始之前**部分中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p151">**Note:** You have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center to create a new import job. See the **Before you begin** section for more information.</span></span> 
    
4. <span data-ttu-id="ee1f8-p152">为 PST 导入作业中，键入一个名称，然后单击**下一步**。使用小写字母、 数字、 连字符和下划线。您无法使用大写字母或名称中包含空格。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p152">Type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="ee1f8-347">在**要上载或附带数据？** 页上，单击**上载数据**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-347">On the **Do you want to upload or ship data?** page, click **Upload your data** and then click **Next**.</span></span>
    
    ![单击上载以创建网络上载将数据导入作业](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. <span data-ttu-id="ee1f8-349">在**导入数据**页上的步骤 4 中，单击**我已经完成了上载我文件**和**我有权访问映射文件**，选中框中，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-349">In step 4 on the **Import data** page, click the **I'm done uploading my files** and **I have access to the mapping file** check boxes, and then click **Next**.</span></span>
    
    ![单击在步骤 4 中的两个复选框](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. <span data-ttu-id="ee1f8-351">在**选择映射文件**页上，单击**选择映射文件**以提交您在步骤 4 中创建的 PST 导入映射文件。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-351">On the **Select the mapping file** page, click **Select mapping file** to submit the PST Import mapping file that you created in Step 4.</span></span> 
    
    ![单击选择映射文件以提交您创建的导入作业的 CSV 文件](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. <span data-ttu-id="ee1f8-353">后的 CSV 名称文件显示在**映射文件名称**下，单击**验证**检查 CSV 文件中的错误。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-353">After the name of the CSV file appears under **Mapping file name**, click **Validate** to check your CSV file for errors.</span></span> 
    
    ![单击验证检查 CSV 文件中的错误](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    <span data-ttu-id="ee1f8-p153">CSV 文件已成功验证创建 PST 导入作业。请注意成功验证后，更改文件名为绿色。如果验证失败，请单击**查看日志**链接。打开时验证错误报告，失败的文件中的各行的错误消息。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p153">The CSV file has to be successfully validated to create a PST Import job. Note the file name is changed to green after it's successfully validated. If the validation fails, click the **View log** link. A validation error report is opened, with a error message for each row in the file that failed.</span></span> 
    
9. <span data-ttu-id="ee1f8-359">在成功验证 PST 映射文件后，读取条款和条件的文档，，，然后单击复选框。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-359">After the PST mapping file is successfully validated, read the terms and conditions document, and then click the checkbox.</span></span>
    
10. <span data-ttu-id="ee1f8-360">单击**保存**以提交的作业，然后单击**关闭**后作业已成功创建。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-360">Click **Save** to submit the job, and then click **Close** after the job is successfully created.</span></span> 
    
    <span data-ttu-id="ee1f8-361">将显示状态弹出页，**正在进行分析**的状态，并在**导入**页上的列表中显示新的导入作业。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-361">A status flyout page is displayed, with a status of **Analysis in progress** and the new import job is displayed in the list on the **Import** page.</span></span> 
    
11. <span data-ttu-id="ee1f8-p154">单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)以更新**状态**列中显示的状态信息。当完成分析，并已准备好要导入数据时，状态更改为**完成分析**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p154">Click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the status information that's displayed in the **Status** column. When the analysis is complete and the data is ready to be imported, the status is changed to **Analysis completed**.</span></span>
    
    <span data-ttu-id="ee1f8-364">您可以单击导入作业以显示状态弹出页，其中包含有关导入作业状态等的映射文件中列出的每个 PST 文件的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-364">You can click the import job to display the status flyout page, which contains more detailed information about the import job such as the status of each PST file listed in the mapping file.</span></span>
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a><span data-ttu-id="ee1f8-365">步骤 6： 筛选数据，并启动 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="ee1f8-365">Step 6: Filter data and start the PST Import job</span></span>

<span data-ttu-id="ee1f8-p155">步骤 5 中创建导入作业后，Office 365 分析 PST 文件中的数据 （以安全方式） 标识的项目和 PST 文件中包含的其他消息类型的期限。在完成分析，并且已准备好导入数据，您可以选择要导入 PST 文件中包含的所有数据或可以修整通过设置控制哪些数据获取导入的筛选器导入的数据。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p155">After you create the import job in Step 5, Office 365 analyzes the data in the PST files (in a safe and secure manner) by identifying the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span>
  
1. <span data-ttu-id="ee1f8-368">在安全中的**导入**页上&amp;合规性中心，单击步骤 5 中创建的导入作业的**已准备好导入到 Office 365** 。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-368">On the **Import** page in the Security &amp; Compliance Center, click **Ready to import to Office 365** for the import job that you created in Step 5.</span></span> 
    
    ![单击您创建的导入作业旁边导入到 Office 365 准备](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    <span data-ttu-id="ee1f8-370">飞出页将显示有关 PST 文件的信息以及其他信息导入作业。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-370">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
2. <span data-ttu-id="ee1f8-371">在弹出页上，单击**导入到 Office 365**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-371">On the flyout page, click **Import to Office 365**.</span></span>
    
    <span data-ttu-id="ee1f8-p156">显示**筛选数据**页。它包含生成 Office 365，包括有关数据的期限对 PST 文件执行分析数据见解。此时，您可以选择要筛选的数据将导入或导入原样的所有数据。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p156">The **Filter your data** page is displayed. It contains the data insights resulting from the analysis performed on the PST files by Office 365, including information about the age of the data. At this point, you have the option to filter the data that will be imported or import all the data as is.</span></span> 
    
    ![您可以修整 PST 文件中的数据或导入的所有](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. <span data-ttu-id="ee1f8-376">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="ee1f8-376">Do one of the following:</span></span>
    
    <span data-ttu-id="ee1f8-p157">答： 来裁切导入的数据，请单击**是，我希望筛选其之前导入**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p157">a. To trim the data that you import, click **Yes, I want to filter it before importing**.</span></span>
    
    <span data-ttu-id="ee1f8-379">有关筛选 PST 文件中的数据，然后启动导入作业的详细分步说明，请参阅[筛选器数据导入 PST 文件迁移到 Office 365 时](filter-data-when-importing-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-379">For detailed step-by-step instructions about filtering the data in the PST files and then starting the import job, see [Filter data when importing PST files to Office 365](filter-data-when-importing-pst-files.md).</span></span>
    
    <span data-ttu-id="ee1f8-380">或</span><span class="sxs-lookup"><span data-stu-id="ee1f8-380">Or</span></span>
    
    <span data-ttu-id="ee1f8-p158">b.若要导入 PST 文件中的所有数据中,，单击**否，我想要导都入的所有内容，** 然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p158">b. To import all data in the PST files, click **No, I want to import everything,** and click **Next**.</span></span>
    
4. <span data-ttu-id="ee1f8-383">如果您选择要导入的所有数据，请单击都**导都入数据**以启动导都入作业。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-383">If you chose to import all the data, click **Import data** to start the import job.</span></span> 
    
    <span data-ttu-id="ee1f8-p159">导入作业的状态是**导入**页上的显示。单击![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)**刷新**以更新**状态**列中显示的状态信息。单击显示状态弹出页，显示状态信息正在导入每个 PST 文件导入作业。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p159">The status of the import job is display on the **Import** page. Click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status information that's displayed in the **Status** column. Click the import job to display the status flyout page, which displays status information about each PST file being imported.</span></span> 

## <a name="how-the-import-process-works"></a><span data-ttu-id="ee1f8-387">导入过程的工作原理</span><span class="sxs-lookup"><span data-stu-id="ee1f8-387">How the import process works</span></span>
  
<span data-ttu-id="ee1f8-p160">您可以使用网络上载选项和导入 Office 365 服务批量导入到用户邮箱的 PST 文件。网络上载意味着您在 Microsoft 云中的临时存储区上载 PST 文件。然后 Office 365 导入服务将复制的 PST 文件从存储区域到目标用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p160">You can use the network upload option and the Office 365 Import service to bulk-import PST files to user mailboxes. Network upload means that you upload the PST files a temporary storage area in the Microsoft cloud. Then the Office 365 Import service copies the PST files from the storage area to the target user mailboxes.</span></span>
  
<span data-ttu-id="ee1f8-391">以下是图和 PST 文件导入 Office 365 中的邮箱的网络上载过程的说明。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-391">Here's an illustration and description of the network upload process to import PST files to mailboxes in Office 365.</span></span>
  
![网络的工作流上载到 Office 365 导入 PST 文件的过程](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. <span data-ttu-id="ee1f8-p161">**下载 PST 导入工具和密钥对专用的 Azure 存储位置**-第一步是下载 Azure AzCopy 命令行工具和用于将 PST 文件上载到云中 Microsoft Azure 存储位置访问键。您获取这些从 Office 365 安全性**导入**页上&amp;合规性中心。键 （调用安全访问 (SA) 签名密钥、 到专用提供了上载 PST 文件所需的权限和安全 Azure 的存储位置。此访问键所特有的组织，并帮助防止未授权的访问到 PST 文件，它们上载到 Microsoft 云后。请注意到 Office 365 导入 PST 文件不需要组织拥有单独的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p161">**Download the PST import tool and key to private Azure storage location** - The first step is to download the Azure AzCopy command-line tool and an access key used to upload the PST files to an Azure storage location in the Microsoft cloud . You obtain these from the **Import** page in the Office 365 Security &amp; Compliance Center. The key (called a secure access signature (SAS) key, provides you with the necessary permissions to upload PST files to a private and secure Azure storage location. This access key is unique to your organization and helps prevent unauthorized access to your PST files after they're uploaded to the Microsoft cloud. Note that importing PST files to Office 365 doesn't require your organization to have a separate Azure subscription.</span></span> 
    
2. <span data-ttu-id="ee1f8-p162">**上载到 Azure 存储位置的 PST 文件**的下一步是使用 AzCopy.exe 工具 （步骤 1 中下载） 上载，并将 PST 文件存储在驻留在同一区域 Microsoft 数据中心中的 Azure 存储位置其中 Office 365组织所在。若要将它们上载，您希望导入到 Office 365 的 PST 文件必须位于文件共享或组织中的文件服务器。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p162">**Upload the PST files to the Azure storage location** - The next step is to use the AzCopy.exe tool (downloaded in step 1) to upload and store your PST files in an Azure storage location that resides in the same regional Microsoft datacenter where your Office 365 organization is located. To upload them, the PST files that you want to import to Office 365 have to be located in a file share or file server in your organization.</span></span>
    
    <span data-ttu-id="ee1f8-400">请注意，您可执行的用于查看 PST 文件的列表，它们上载到 Azure 存储位置后可选步骤。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-400">Note that there's an optional step that you can perform to view the list of PST files after they're uploaded to the Azure storage location.</span></span>
    
3. <span data-ttu-id="ee1f8-p163">**创建 PST 导入映射文件**-PST 文件已上载到 Azure 存储位置后下, 一步是创建指定哪些用户邮箱的 PST 文件将被导入以，请注意，可以是 PST 文件的以逗号分隔的值 (CSV) 文件 导入到用户的主邮箱或其存档邮箱。导入 Office 365 服务将使用该 CSV 文件中的信息导入 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p163">**Create a PST import mapping file** - After the PST files have been uploaded to the Azure storage location, the next step is to create a comma separated value (CSV) file that specifies which user mailboxes the PST files will be imported to, note that a PST file can be imported to a user's primary mailbox or their archive mailbox. The Office 365 Import service will use the information in the CSV file to import the PST files.</span></span>
    
4. <span data-ttu-id="ee1f8-p164">**创建 PST 导入作业**-下一步是在安全的**导入**页上创建 PST 导入作业&amp;合规性中心和提交上一步中创建的 PST 导入映射文件。创建导入作业后，Office 365 分析 PST 文件中的数据，并使您能够设置控制哪些数据获取实际导入 PST 导入映射文件中指定的邮箱的筛选器。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p164">**Create a PST import job** - The next step is to create a PST import job on the **Import** page in the Security &amp; Compliance Center and submit the PST import mapping file created in the previous step. After you create the import job, Office 365 analyzes the data in the PST files and then gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span> 
    
5. <span data-ttu-id="ee1f8-p165">**筛选器，将导入到邮箱的 PST 数据**-导入作业的创建和启动后，Office 365 分析 PST 文件中的数据 （安全、 可靠地） 通过确定项目和 PST 文件中包含的其他消息类型的期限.在完成分析，并且已准备好导入数据，您可以选择要导入 PST 文件中包含的所有数据或可以修整通过设置控制哪些数据获取导入的筛选器导入的数据。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p165">**Filter the PST data that will be imported to mailboxes** - After the import job is created and started, Office 365 analyzes the data in the PST files (safely and securely) by identifying the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span>
    
6. <span data-ttu-id="ee1f8-p166">**启动 PST 导入作业**-启动导入作业后，Office 365 使用的信息在 PST 导入映射文件从他 Azure 的存储位置的 Pst 文件导入到用户邮箱。有关 （包括有关正在导入每个 PST 文件） 导入作业的状态信息显示在安全中的**导入**页上&amp;合规性中心。完成导入作业后，此作业的状态设置为**完成**。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p166">**Start the PST import job** - After the import job is started, Office 365 uses the information in the PST import mapping file to import the PSTs files from the he Azure storage location to user mailboxes. Status information about the import job (including information about each PST file being imported) is displayed on the **Import** page in the Security &amp; Compliance Center. When the import job is finished, the status for the job is set to **Complete**.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="ee1f8-410">详细信息</span><span class="sxs-lookup"><span data-stu-id="ee1f8-410">More information</span></span>

- <span data-ttu-id="ee1f8-411">为什么到 Office 365 导入 PST 文件？</span><span class="sxs-lookup"><span data-stu-id="ee1f8-411">Why import PST files to Office 365?</span></span>
    
  - <span data-ttu-id="ee1f8-412">它是贵组织的存档消息数据导入到 Office 365 的好方法。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-412">It's a good way to import your organization's archival messaging data to Office 365.</span></span>
    
  - <span data-ttu-id="ee1f8-413">用户在任意设备上都可以使用数据，因为数据存储在云中。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-413">The data is available to the user from all devices because it's stored in the cloud.</span></span>
    
  - <span data-ttu-id="ee1f8-p167">允许您从 PST 文件导入应用于数据的 Office 365 合规性功能，从而帮助您的组织满足合规性需求。这包括：</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p167">It helps address compliance needs of your organization by letting you apply Office 365 compliance features to the data from the PST files that you imported. This includes:</span></span>
    
  - <span data-ttu-id="ee1f8-416">启用[存档邮箱](enable-archive-mailboxes.md)和[自动扩展存档](enable-unlimited-archiving.md)为用户提供其他邮箱空间来存储您导入的数据。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-416">Enabling [archive mailboxes](enable-archive-mailboxes.md) and [auto-expanding archiving](enable-unlimited-archiving.md) to give users additional mailbox storage space to store the data that you imported.</span></span> 
    
  - <span data-ttu-id="ee1f8-417">将邮箱置于[诉讼保留](https://go.microsoft.com/fwlink/?linkid=856286)保留您导入的数据。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-417">Placing mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) to retain the data that you imported.</span></span> 
    
  - <span data-ttu-id="ee1f8-418">使用 Microsoft[电子数据展示工具](search-for-content.md)搜索您导入的数据。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-418">Using Microsoft [eDiscovery tools](search-for-content.md) to search the data that you imported.</span></span> 
    
  - <span data-ttu-id="ee1f8-419">使用[Office 365 保留策略](retention-policies.md)来控制您导入的数据将保留多长时间，和要采取的保留期过后哪些操作。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-419">Using [Office 365 retention policies](retention-policies.md) to control how long the data that you imported will be retained, and what action to take after the retention period expires.</span></span> 
    
  - <span data-ttu-id="ee1f8-420">搜索[Office 365 审核日志](search-the-audit-log-in-security-and-compliance.md)的邮箱相关的事件的会影响您导入的数据。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-420">Searching the [Office 365 audit log](search-the-audit-log-in-security-and-compliance.md) for mailbox-related events that affect the data that you imported.</span></span> 
    
  - <span data-ttu-id="ee1f8-421">将数据导入到存档数据，出于合规性目的的[非活动邮箱](create-and-manage-inactive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-421">Importing data to [inactive mailboxes](create-and-manage-inactive-mailboxes.md) to archive data for compliance purposes.</span></span> 
    
  - <span data-ttu-id="ee1f8-422">使用[数据丢失预防策略](data-loss-prevention-policies.md)阻止敏感数据泄漏组织外部。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-422">Using [data loss prevention policies](data-loss-prevention-policies.md) to prevent sensitive data from leaking outside your organization.</span></span> 
  
- <span data-ttu-id="ee1f8-p168">下面是一个示例获取在步骤 1 中的共享访问签名 (SA) url。此示例还包含到上载 PST 文件迁移到 Office 365 中运行 AzCopy.exe 工具中的命令的语法。请确保采取预防措施来保护 SAS URL 像将保护密码或其他安全相关的信息。</span><span class="sxs-lookup"><span data-stu-id="ee1f8-p168">Here's an example of the Shared Access Signature (SAS) URL that's obtained in Step 1. This example also contains the syntax for the command that you run in the AzCopy.exe tool to upload PST files to Office 365. Be sure to take precautions to protect the SAS URL just like you would protect passwords or other security-related information.</span></span>

    ```
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
``

- As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RetentionHoldEnabled*  property is set to  `True` so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold: 
    
    - After a certain period of time, you can turn off the retention hold by running the  `Set-Mailbox -RetentionHoldEnabled $false` command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
   - You can configure the retention hold so that it's turned off on some date in the future. You do this by running the  `Set-Mailbox -EndDateForRetentionHold <date>` command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In this scenario, you would leave the  *RetentionHoldEnabled*  property set to  *True*  . For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    

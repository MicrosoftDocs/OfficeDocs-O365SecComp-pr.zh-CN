---
title: 将您的组织 PST 文件导入到 Office 365 的概述
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: 管理员： 了解如何在 Office 365 安全性使用的导入服务&amp;合规性中心以批量导入电子邮件数据 （PST 文件） 到 Exchange Online 中的用户邮箱。本主题提供了常见问题，并说明 PST 导入过程工作方式。
ms.openlocfilehash: 1cbe5627ffb906b6a87541f4c4582a2806562ca4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525702"
---
# <a name="overview-of-importing-your-organization-pst-files-to-office-365"></a><span data-ttu-id="71991-104">将您的组织 PST 文件导入到 Office 365 的概述</span><span class="sxs-lookup"><span data-stu-id="71991-104">Overview of importing your organization PST files to Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="71991-p102">本文是针对管理员。您试图将 PST 文件导入到您自己的邮箱？请参阅[导入电子邮件、 联系人和日历从 Outlook.pst 文件](https://go.microsoft.com/fwlink/p/?LinkID=785075)</span><span class="sxs-lookup"><span data-stu-id="71991-p102">This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)</span></span>

<span data-ttu-id="71991-p103">您可以在 Office 365 安全性使用导入服务&amp;合规性中心，以快速批量导入 PST 文件添加到 Office 365 组织中的 Exchange Online 邮箱。有两种方法可以 PST 文件导入到 Office 365:</span><span class="sxs-lookup"><span data-stu-id="71991-p103">You can use the Import service in the Office 365 Security &amp; Compliance Center to quickly bulk-import PST files to Exchange Online mailboxes in your Office 365 organization. There are two ways you can import PST files to Office 365:</span></span>
   
- <span data-ttu-id="71991-p104">**网络上载**![云上载](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png)-PST 文件上载到 Microsoft 云临时 Azure 存储位置在网络上。然后您可以使用导入 Office 365 服务到邮箱在 Office 365 组织中导入 PST 数据。</span><span class="sxs-lookup"><span data-stu-id="71991-p104">**Network upload** ![Cloud upload](media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - Upload the PST files over the network to a temporary Azure storage location in the Microsoft cloud. Then you use the Office 365 Import service to import the PST data to mailboxes in your Office 365 organization.</span></span> 

- <span data-ttu-id="71991-p105">**驱动器传送**![硬盘](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png)-将 PST 文件复制到 BitLocker 加密的硬盘，然后以物理方式提供给 Microsoft 的驱动器。当 Microsoft 收到的硬盘时，数据中心人员将数据上载到 Microsoft 云中的临时 Azure 存储位置。然后您可以使用 Office 365 导入服务到邮箱在 Office 365 组织中导入数据。</span><span class="sxs-lookup"><span data-stu-id="71991-p105">**Drive shipping** ![Hard disk](media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - Copy the PST files to a BitLocker-encrypted hard drive and then physically ship the drive to Microsoft. When Microsoft receives the hard drive, data center personnel upload the data to a temporary Azure storage location in the Microsoft cloud. Then you use the Office 365 Import service to import the data to mailboxes in your Office 365 organization.</span></span>

## <a name="step-by-step-instructions"></a><span data-ttu-id="71991-115">分步说明</span><span class="sxs-lookup"><span data-stu-id="71991-115">Step-by-step instructions</span></span>
  
<span data-ttu-id="71991-116">请参阅批量导入到 Office 365 组织的 PST 文件的详细分步说明的以下主题之一。</span><span class="sxs-lookup"><span data-stu-id="71991-116">See one of the following topics for detailed, step-by-step instructions for bulk-importing your organization's PST files to Office 365.</span></span> 
   
- [<span data-ttu-id="71991-117">使用网络上载将 PST 文件导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="71991-117">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)
- [<span data-ttu-id="71991-118">使用驱动器寄送，将 PST 文件导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="71991-118">Use drive shipping to import PST files to Office 365</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a><span data-ttu-id="71991-119">导入 PST 文件的工作原理</span><span class="sxs-lookup"><span data-stu-id="71991-119">How importing PST files works</span></span>

<span data-ttu-id="71991-p106">下面是一个图和完成 PST 导入过程的说明。下图显示主工作流并突出显示网络上载和传送方法的驱动器之间的差异。</span><span class="sxs-lookup"><span data-stu-id="71991-p106">Here's an illustration and description of the complete PST import process. The illustration shows the primary workflow and highlights the differences between the network upload and drive shipping methods.</span></span>
  
![PST 导入过程的工作流](media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. <span data-ttu-id="71991-p107">**下载 PST 导入工具和密钥对专用的 Azure 存储位置**-第一步是下载用于上载 PST 文件或将它们复制到硬盘驱动器上的工具和访问密钥。您获取这些从 Office 365 安全性**导入**页上&amp;合规性中心。该密钥将 PST 文件上载到专用和安全的 Azure 存储位置的必要权限中提供您 （或对于驱动器传送的 Microsoft 数据中心人员）。此访问键所特有的组织，并帮助防止未授权的访问到 PST 文件，它们上载到 Microsoft 云后。请注意到 Office 365 导入 PST 文件不需要组织拥有单独的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="71991-p107">**Download the PST import tools and key to private Azure storage location** - The first step is to download the tool and access key used to upload the PST files or copy them to a hard drive. You obtain these from the **Import** page in the Office 365 Security &amp; Compliance Center. The key provides you (or Microsoft data center personnel in the case of drive shipping) with the necessary permissions to upload PST files to a private and secure Azure storage location. This access key is unique to your organization and helps prevent unauthorized access to your PST files after they're uploaded to the Microsoft cloud. Note that importing PST files to Office 365 doesn't require your organization to have a separate Azure subscription.</span></span> 
    
2. <span data-ttu-id="71991-p108">**上载或复制 PST 文件**的下一步取决于您正在使用网络上载或驱动器传送导入 PST 文件。在这两种情况下，您将使用的工具和您在上一步中获得的安全存储键。</span><span class="sxs-lookup"><span data-stu-id="71991-p108">**Upload or copy the PST files** - The next step depends on whether you're using network upload or drive shipping to import PST files. In both cases, you'll use the tool and secure storage key that you obtained in the previous step.</span></span>
    
    - <span data-ttu-id="71991-p109">**网络上载**（在步骤 1 中下载） AzCopy.exe 工具用于上载，并将 PST 文件存储在云中的 Microsoft Azure 的存储位置。请注意上载到 PST 文件的 Azure 的存储位置驻留在同一区域 Microsoft 数据中心 Office 365 组织所在的位置。</span><span class="sxs-lookup"><span data-stu-id="71991-p109">**Network upload**The AzCopy.exe tool (downloaded in step 1) is used to upload and store your PST files in an Azure storage location in the Microsoft cloud. Note that the Azure storage location that you upload your PST files to resides in the same regional Microsoft datacenter where your Office 365 organization is located.</span></span> 
    
      <span data-ttu-id="71991-132">若要将它们上载，您希望导入到 Office 365 的 PST 文件必须位于文件共享或组织中的文件服务器。</span><span class="sxs-lookup"><span data-stu-id="71991-132">To upload them, the PST files that you want to import to Office 365 have to be located in a file share or file server in your organization.</span></span>
    
    - <span data-ttu-id="71991-p110">**驱动器传送**（在步骤 1 中下载） WAImportExport.exe 工具用于将 PST 文件复制到硬盘上。此工具的硬盘中使用 BitLocker 加密，然后将 Pst 复制到硬盘上。像网络上载您想要复制到硬盘上的 PST 文件必须位于文件共享或组织中的文件服务器。</span><span class="sxs-lookup"><span data-stu-id="71991-p110">**Drive shipping**The WAImportExport.exe tool (downloaded in step 1) is used to copy your PST files to the hard drive. This tool encrypts the hard drive with BitLocker and then copies the PSTs to the hard drive. Like network upload, the PST files that you want to copy to the hard drive have to be located in a file share or file server in your organization.</span></span>
    
3. <span data-ttu-id="71991-p111">**创建 PST 导入映射文件**-已上载到 Azure 存储位置或复制到硬盘驱动器 PST 文件后下, 一步是创建指定哪些用户邮箱 PST 文件将被导入到逗号分隔的值 (CSV) 文件 (和 PST 文件可以导入到用户的主邮箱或其存档邮箱）。导入 Office 365 服务将使用信息导入 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="71991-p111">**Create a PST import mapping file** - After the PST files have been uploaded to the Azure storage location or copied to a hard drive, the next step is to create a comma separated value (CSV) file that specifies which user mailboxes the PST files will be imported to (and a PST file can be imported to a user's primary mailbox or their archive mailbox). The Office 365 Import service will use the information to import the PST files.</span></span> 
    
4. <span data-ttu-id="71991-p112">**创建 PST 导入作业**-下一步是在安全的**导入**页上创建 PST 导入作业&amp;合规性中心和提交上一步中创建的 PST 导入映射文件。网络上载 （因为 PST 文件已上载到 Azure） Office 365 分析 PST 文件中的数据并使您能够设置控制哪些数据获取实际导入 PST 导入映射文件中指定的邮箱的筛选器。</span><span class="sxs-lookup"><span data-stu-id="71991-p112">**Create a PST import job** - The next step is to create a PST import job on the **Import** page in the Security &amp; Compliance Center and submit the PST import mapping file created in the previous step. For network upload (because the PST files have been uploaded to Azure) Office 365 analyzes the data in the PST files and then gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span> 
    
    <span data-ttu-id="71991-140">驱动器传送的一些其他内容发生在此过程中的点。</span><span class="sxs-lookup"><span data-stu-id="71991-140">For drive shipping, a few additional things happen at this point in the process.</span></span>
    
    - <span data-ttu-id="71991-141">物理附带硬盘连接到 Microsoft 数据中心 （Microsoft 数据中心的传送地址创建导入作业时显示）</span><span class="sxs-lookup"><span data-stu-id="71991-141">You physically ship the hard drive to a Microsoft data center (the shipping address for the Microsoft data center is displayed when the import job is created)</span></span>
    
    - <span data-ttu-id="71991-p113">当 Microsoft 收到的硬盘时，则数据中心人员将在硬盘驱动器上 Pst 文件上载到您的组织的 Azure 存储位置。如前所述，PST 文件上载到 Azure 存储位置位于同一区域 Microsoft 数据中心的 Office 365 组织所在的位置。</span><span class="sxs-lookup"><span data-stu-id="71991-p113">When Microsoft receives the hard drive, data center personnel will upload the PSTs files on the hard drive to the Azure storage location for your organization. As previously explained, your PST files are uploaded to a Azure storage location that resides in the same regional Microsoft datacenter where your Office 365 organization is located.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="71991-144">在硬盘驱动器上的 PST 文件上载到 Azure 7 至 10 个工作日后 Microsoft 接收硬盘中。</span><span class="sxs-lookup"><span data-stu-id="71991-144">The PST files on the hard drive are uploaded to Azure within 7 to 10 business days after Microsoft receives the hard drive.</span></span> 
  
      <span data-ttu-id="71991-145">像网络上载过程中，Office 365 然后分析 PST 文件中的数据，并使您能够设置控制哪些数据获取实际导入 PST 导入映射文件中指定的邮箱的筛选器。</span><span class="sxs-lookup"><span data-stu-id="71991-145">Like the network upload process, Office 365 then analyzes the data in the PST files and gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span>
    
    - <span data-ttu-id="71991-146">Microsoft 附带发回给您的硬盘。</span><span class="sxs-lookup"><span data-stu-id="71991-146">Microsoft ships the hard drive back to you.</span></span> 
    
5. <span data-ttu-id="71991-p114">**筛选器，将导入到邮箱的 PST 数据**-Office 365 创建导入作业后 （和之后的驱动器传送作业的 PST 文件上载到 Azure 的存储位置） （安全、 可靠地） 通过分析 PST 文件中的数据确定项目和 PST 文件中包含的其他消息类型的期限。在完成分析，并且已准备好导入数据，您可以选择要导入 PST 文件中包含的所有数据或可以修整通过设置控制哪些数据获取导入的筛选器导入的数据。</span><span class="sxs-lookup"><span data-stu-id="71991-p114">**Filter the PST data that will be imported to mailboxes** - After the import job is created (and after the PST files from a drive shipping job are uploaded to the Azure storage location) Office 365 analyzes the data in the PST files (safely and securely) by identifying the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
6. <span data-ttu-id="71991-p115">**启动 PST 导入作业**-启动导入作业后，Office 365 使用的信息在 PST 导入映射文件从他 Azure 的存储位置的 Pst 文件导入到用户邮箱。有关 （包括有关正在导入每个 PST 文件） 导入作业的状态信息显示在安全中的**导入**页上&amp;合规性中心。完成导入作业后，此作业的状态设置为**完成**。</span><span class="sxs-lookup"><span data-stu-id="71991-p115">**Start the PST import job** - After the import job is started, Office 365 uses the information in the PST import mapping file to import the PSTs files from the he Azure storage location to user mailboxes. Status information about the import job (including information about each PST file being imported) is displayed on the **Import** page in the Security &amp; Compliance Center. When the import job is finished, the status for the job is set to **Complete**.</span></span>
  
## <a name="why-import-email-data-to-office-365"></a><span data-ttu-id="71991-152">为什么将电子邮件数据导入 Office 365？</span><span class="sxs-lookup"><span data-stu-id="71991-152">Why import email data to Office 365?</span></span>

- <span data-ttu-id="71991-153">将 PST 文件导入到用户邮箱是一种方法将您的组织的电子邮件迁移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="71991-153">Importing PST files to user mailboxes is one way to migrate your organization's email to Office 365.</span></span>
    
- <span data-ttu-id="71991-p116">[智能导入](filter-data-when-importing-pst-files.md)功能可用于筛选实际上获取导入到的目标邮箱的 PST 文件中的项目。使能够剪裁通过设置筛选器的导入的数据来控制哪些数据获取导入。</span><span class="sxs-lookup"><span data-stu-id="71991-p116">You can use the [Intelligent Import](filter-data-when-importing-pst-files.md) feature to filter the items in PST files that actually get imported to the target mailboxes. This lets you trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
- <span data-ttu-id="71991-156">将电子邮件数据导入到 Office 365 帮助使您的组织满足合规性需求：</span><span class="sxs-lookup"><span data-stu-id="71991-156">Importing email data to Office 365 helps address compliance needs of your organization by letting you:</span></span>
    
  - <span data-ttu-id="71991-157">启用[存档邮箱](enable-archive-mailboxes.md)和[无限制存档](unlimited-archiving.md)为用户提供其他邮箱存储空间。</span><span class="sxs-lookup"><span data-stu-id="71991-157">Enable [archive mailboxes](enable-archive-mailboxes.md) and [unlimited archiving](unlimited-archiving.md) to give users additional mailbox storage space.</span></span> 
    
  - <span data-ttu-id="71991-158">将邮箱置于[诉讼保留](https://go.microsoft.com/fwlink/?linkid=841243)保留内容。</span><span class="sxs-lookup"><span data-stu-id="71991-158">Place mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=841243) to retain content.</span></span> 
    
  - <span data-ttu-id="71991-159">[内容搜索工具](content-search.md)用于搜索的邮箱内容。</span><span class="sxs-lookup"><span data-stu-id="71991-159">Use the [Content Search tool](content-search.md) to search for mailbox content.</span></span> 
    
  - <span data-ttu-id="71991-160">用您的组织的法律调查的管理[电子数据展示事例](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="71991-160">Use [eDiscovery cases](ediscovery-cases.md) to mange your organization's legal investigations</span></span> 
    
  - <span data-ttu-id="71991-161">在安全中使用[保留策略](retention-policies.md)&amp;合规性中心，以控制邮箱内容保留多长时间，然后删除内容保留期过后。</span><span class="sxs-lookup"><span data-stu-id="71991-161">Use [retention policies](retention-policies.md) in the Security &amp; Compliance Center to control how long mailbox content is retained, and then delete content after the retention period expires.</span></span> 
    
- <span data-ttu-id="71991-p117">将数据导入到 Office 365 帮助防止数据丢失。导入到 Office 365 的电子邮件数据中继承 Exchange Online 的高可用性的功能。</span><span class="sxs-lookup"><span data-stu-id="71991-p117">Importing data to Office 365 helps protect against data loss. Email data that's imported to Office 365 inherits the high availability features of Exchange Online.</span></span>
    
- <span data-ttu-id="71991-164">Office 365 中的电子邮件数据是可供用户从所有设备，因为存储在云中。</span><span class="sxs-lookup"><span data-stu-id="71991-164">Email data in Office 365 is available to users from all devices because it's stored in the cloud.</span></span>
    
## <a name="importing-sharepoint-data-to-office-365"></a><span data-ttu-id="71991-165">将 SharePoint 数据导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="71991-165">Importing SharePoint data to Office 365</span></span>

<span data-ttu-id="71991-p118">您还可以导入文件和文档对 SharePoint 网站和 OneDrive 帐户在 Office 365 组织中。有关详细信息，请参阅[上载到 SharePoint Online 使用 PowerShell cmdlet 在本地内容](https://docs.microsoft.com/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)。</span><span class="sxs-lookup"><span data-stu-id="71991-p118">You can also import files and documents to SharePoint sites and OneDrive accounts in your Office 365 organization. For more information, see [Upload on-premises content to SharePoint Online using PowerShell cmdlets](https://docs.microsoft.com/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets).</span></span>


## <a name="frequently-asked-questions-about-importing-pst-files-to-office-365"></a><span data-ttu-id="71991-168">有关将 PST 文件导入到 Office 365 常见问题</span><span class="sxs-lookup"><span data-stu-id="71991-168">Frequently asked questions about importing PST files to Office 365</span></span>
  
<span data-ttu-id="71991-169">以下是一些有关使用导入 Office 365 服务批量导入 PST 文件迁移到 Office 365 邮箱的常见问题。</span><span class="sxs-lookup"><span data-stu-id="71991-169">Here are some frequently asked questions about using the Office 365 Import service to bulk-import PST files to Office 365 mailboxes.</span></span> 
  
- [<span data-ttu-id="71991-170">使用网络上载以导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="71991-170">Using network upload to import PST files</span></span>](#using-network-upload-to-import-pst-files)
  
- [<span data-ttu-id="71991-171">使用驱动器传送导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="71991-171">Using drive shipping to import PST files</span></span>](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="71991-172">使用网络上载以导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="71991-172">Using network upload to import PST files</span></span>

 <span data-ttu-id="71991-173">**需要在 Office 365 导入服务中创建导入作业哪些权限？**</span><span class="sxs-lookup"><span data-stu-id="71991-173">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="71991-p119">您必须为其分配导入导出邮箱角色在 Exchange Online 到 Office 365 邮箱导入 PST 文件。默认情况下，此角色不分配给任何角色组在 Exchange Online。您可以向组织管理角色组中添加邮箱导入导出角色。或者，您可以创建新角色组、 分配的邮箱导入导出角色中，然后将自己或其他用户添加为成员。有关详细信息，请参阅"添加角色向角色组"或"创建角色组"部分[管理角色组在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)中。</span><span class="sxs-lookup"><span data-stu-id="71991-p119">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="71991-179">此外，若要创建导入作业 Office 365 安全性&amp;必须满足合规中心，下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="71991-179">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="71991-p120">您必须分配 Mail Recipients 角色在 Exchange Online。默认情况下，此角色分配给组织管理和 Recipient Management 角色组。</span><span class="sxs-lookup"><span data-stu-id="71991-p120">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="71991-182">或</span><span class="sxs-lookup"><span data-stu-id="71991-182">Or</span></span>
    
- <span data-ttu-id="71991-183">您必须是 Office 365 组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="71991-183">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="71991-p121">请考虑在 Exchange Online 的专门用于将 PST 文件导入到 Office 365 中创建新的角色组。最小的导入 PST 文件所需的权限级别，将邮箱导入导出和 Mail Recipients 角色分配给新角色组中，，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="71991-p121">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="71991-186">**在哪里网络上载可用**</span><span class="sxs-lookup"><span data-stu-id="71991-186">**Where is network upload available?**</span></span>
  
<span data-ttu-id="71991-p122">在美国、 加拿大、 巴西、 英国、 欧洲、 印度、 中国、 东南方向亚洲，日本、 韩国、 和澳大利亚是当前可用网络上载。网络上载很快就会提供在多个区域中。</span><span class="sxs-lookup"><span data-stu-id="71991-p122">Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="71991-189">**什么是使用网络上载导入 PST 文件的定价？**</span><span class="sxs-lookup"><span data-stu-id="71991-189">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="71991-190">使用网络上载以导入 PST 文件是免费的。</span><span class="sxs-lookup"><span data-stu-id="71991-190">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="71991-p123">这还意味着从 Azure 存储区删除 PST 文件后，他们正在不再显示在 Office 365 管理中心中的已完成的导入作业的文件列表中。虽然仍可能会导入作业列出在**导入到 Office 365 的数据**页上，查看旧导入作业的详细信息中可能为空的 PST 文件的列表。</span><span class="sxs-lookup"><span data-stu-id="71991-p123">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Office 365 admin center. Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="71991-193">**导入到 Office 365 支持哪些版本的 PST 文件格式？**</span><span class="sxs-lookup"><span data-stu-id="71991-193">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="71991-p124">有两个版本的 PST 文件格式： ANSI 和 Unicode。我们建议导入使用 Unicode PST 文件格式的文件。但是，使用 ANSI PST 文件格式，如使用双字节字符的语言的文件 (DBCS)，也可以导入到 Office 365。有关导入 ANSI PST 文件的详细信息，请参阅[使用网络上载以导入 PST 文件迁移到 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074)中的步骤 4。</span><span class="sxs-lookup"><span data-stu-id="71991-p124">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 4 in [Use network upload to import PST files to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).</span></span>
  
<span data-ttu-id="71991-198">此外，可以到 Office 365 导入 PST 文件从 Outlook 2007 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="71991-198">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="71991-199">**我将我的 PST 文件上载到 Azure 存储区后，长它们保存在 Azure 正在删除之前？**</span><span class="sxs-lookup"><span data-stu-id="71991-199">**After I upload my PST files to the Azure storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="71991-p125">如果您使用的网络上载方法来导入 PST 文件，您可以将它们上载到名为**ingestiondata**Azure blob 容器。如果没有导入作业正在进行**导入**页上的安全性&amp;合规性中心)，然后在 Azure 中**ingestiondata**容器中的所有 PST 文件将被都删除 30 天后在安全&amp;合规性中心。这还意味着您必须在安全中创建新的导入作业&amp;到 Azure 文件上载 PST 30 天内的合规性中心 （中所述步骤 5 中的网络上载说明）。</span><span class="sxs-lookup"><span data-stu-id="71991-p125">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**. If there are no import jobs in progress on the **Import** page in the Security &amp; Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security &amp; Compliance Center. That also means you have to create a new import job in the Security &amp; Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="71991-p126">这还意味着从 Azure 存储区删除 PST 文件后，他们正在不再显示在安全中完成导入作业的文件列表中&amp;合规性中心。尽管安全中的**导入**页上，系统可能仍列出导入作业&amp;合规中心的 PST 文件列表可能为空，当您查看旧导入作业的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71991-p126">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="71991-205">**导入到邮箱的 PST 文件需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="71991-205">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="71991-p127">这取决于您的网络的容量，但它通常采用的每个 tb 的数据上载到您的组织的 Azure 存储区的几个小时。PST 文件复制到 Azure 存储区域后，PST 文件导入到 Office 365 邮箱至少 24 GB 每日的速率。如果此速率，不能满足需要，可以考虑将电子邮件数据迁移到 Office 365 的其他方法。有关详细信息，请参阅[方法迁移到 Office 365 的多个电子邮件帐户](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。</span><span class="sxs-lookup"><span data-stu-id="71991-p127">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. After the PST files are copied to the Azure storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="71991-p128">如果不同 PST 文件导入到不同的目标邮箱，导入过程会发生并行;换句话说，每个邮箱 PST 对导入同时。同样，如果多个 PST 文件导入到的同一邮箱，它们将同时导入。</span><span class="sxs-lookup"><span data-stu-id="71991-p128">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="71991-212">**导入 PST 文件时有邮件大小限制吗？**</span><span class="sxs-lookup"><span data-stu-id="71991-212">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="71991-p129">是的。如果 PST 文件中包含大于 150 MB 邮箱项目，将在导入过程跳过项目。</span><span class="sxs-lookup"><span data-stu-id="71991-p129">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="71991-215">**邮件属性，例如当邮件已发送或接收，收件人和其他属性，PST 文件导入到 Office 365 邮箱时保留的列表？**</span><span class="sxs-lookup"><span data-stu-id="71991-215">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="71991-p130">是的。在导入过程不会更改原始消息元数据。</span><span class="sxs-lookup"><span data-stu-id="71991-p130">Yes. The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="71991-218">**是否有我想要导入到邮箱的 PST 文件的文件夹层次结构中的级别数限制？**</span><span class="sxs-lookup"><span data-stu-id="71991-218">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="71991-p131">是的。无法导入 PST 文件具有 300 或多个级别的嵌套文件夹。</span><span class="sxs-lookup"><span data-stu-id="71991-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="71991-221">**可以使用网络上载到 Office 365 中的非活动邮箱导入 PST 文件？**</span><span class="sxs-lookup"><span data-stu-id="71991-221">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="71991-222">是，此功能现已推出的。</span><span class="sxs-lookup"><span data-stu-id="71991-222">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="71991-223">**可以使用网络上载到联机存档邮箱的 Exchange 混合部署中导入 PST 文件？**</span><span class="sxs-lookup"><span data-stu-id="71991-223">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="71991-224">是，此功能现已推出的。</span><span class="sxs-lookup"><span data-stu-id="71991-224">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="71991-225">**可以使用网络上载到 Exchange Online 中公用文件夹中导入 PST 文件？**</span><span class="sxs-lookup"><span data-stu-id="71991-225">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="71991-226">否，您不能 PST 文件导入公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="71991-226">No, you can't import PST files to public folders.</span></span>
  
### <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="71991-227">使用驱动器传送导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="71991-227">Using drive shipping to import PST files</span></span>

 <span data-ttu-id="71991-228">**需要在 Office 365 导入服务中创建导入作业哪些权限？**</span><span class="sxs-lookup"><span data-stu-id="71991-228">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="71991-p132">您必须为其分配到 Office 365 邮箱导入 PST 文件导入导出邮箱角色。默认情况下，此角色不分配给任何角色组在 Exchange Online。您可以向组织管理角色组中添加邮箱导入导出角色。或者，您可以创建新角色组、 分配的邮箱导入导出角色中，然后将自己或其他用户添加为成员。有关详细信息，请参阅"添加角色向角色组"或"创建角色组"部分[管理角色组在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)中。</span><span class="sxs-lookup"><span data-stu-id="71991-p132">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="71991-234">此外，若要创建导入作业 Office 365 安全性&amp;必须满足合规中心，下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="71991-234">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="71991-p133">您必须分配 Mail Recipients 角色在 Exchange Online。默认情况下，此角色分配给组织管理和 Recipient Management 角色组。</span><span class="sxs-lookup"><span data-stu-id="71991-p133">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="71991-237">或</span><span class="sxs-lookup"><span data-stu-id="71991-237">Or</span></span>
    
- <span data-ttu-id="71991-238">您必须是 Office 365 组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="71991-238">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="71991-p134">请考虑在 Exchange Online 的专门用于将 PST 文件导入到 Office 365 中创建新的角色组。最小的导入 PST 文件所需的权限级别，将邮箱导入导出和 Mail Recipients 角色分配给新角色组中，，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="71991-p134">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="71991-241">**驱动器发运可用？**</span><span class="sxs-lookup"><span data-stu-id="71991-241">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="71991-p135">在美国、 加拿大、 巴西、 英国、 欧洲、 印度、 中国、 东南方向亚洲，日本、 韩国、 和澳大利亚驱动器传送是当前可用。驱动器传送很快就会提供在多个区域中。</span><span class="sxs-lookup"><span data-stu-id="71991-p135">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Drive shipping will be available in more regions soon.</span></span>
  
 <span data-ttu-id="71991-244">**哪些商业许可协议支持驱动器传送？**</span><span class="sxs-lookup"><span data-stu-id="71991-244">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="71991-p136">可通过 Microsoft 企业协议 (EA) 传送到 Office 365 导入 PST 文件的驱动器。驱动器传送不提供通过 Microsoft 产品和服务协议 (MPSA)。</span><span class="sxs-lookup"><span data-stu-id="71991-p136">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="71991-247">**什么是使用传送到 Office 365 导入 PST 文件的驱动器的定价？**</span><span class="sxs-lookup"><span data-stu-id="71991-247">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="71991-p137">若要使用驱动器传送到 Office 365 邮箱导入 PST 文件的成本是每 GB 的数据 2 美元。例如，如果附带包含 1,000 GB (1 TB) 的 PST 文件的硬盘驱动器，成本是 2,000 美元。您可以使用导入费用，合作伙伴。有关查找合作伙伴的信息，请参阅[查找您的 Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="71991-p137">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="71991-252">**驱动器传送的操作支持哪些类型的硬盘驱动器？**</span><span class="sxs-lookup"><span data-stu-id="71991-252">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="71991-p138">仅为 2.5 英寸固态驱动器 (Ssd) 或 2.5 或 3.5 英寸 SATA II/III 内部硬盘支持与 Office 365 导入服务一起使用。您可以使用硬盘最多 10 TB。导入作业将处理仅第一个数据卷上的硬盘中。必须使用 NTFS 格式化数据量。当数据复制到硬盘上，您可以将其直接使用 2.5 英寸 SSD 附加或 2.5 或 3.5 英寸 SATA II/III 连接器或可以附加外部使用外部 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III USB 适配器。</span><span class="sxs-lookup"><span data-stu-id="71991-p138">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="71991-p139">Office 365 导入服务不支持外部硬盘驱动器附带的内置的 USB 适配器。此外，不能使用内外部的硬盘驱动器上的大小写磁盘。请不要附带外部硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="71991-p139">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="71991-261">**单个导入作业可以提供多少硬盘驱动器？**</span><span class="sxs-lookup"><span data-stu-id="71991-261">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="71991-262">您可以提供 10 硬盘驱动器单个导入作业的最大值。</span><span class="sxs-lookup"><span data-stu-id="71991-262">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="71991-263">**我附带我硬盘后，如何长，转到 Microsoft 数据中心？**</span><span class="sxs-lookup"><span data-stu-id="71991-263">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="71991-p140">这取决于几件事，例如您接近 Microsoft 数据中心，您用于附带硬盘驱动器 （例如下, 一个工作日传递、 两天传递或度数送达） 哪种类型的传送选项。与大多数 shippers，您可以使用跟踪数跟踪您传递的状态。</span><span class="sxs-lookup"><span data-stu-id="71991-p140">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="71991-266">**我硬盘到达 Microsoft 数据中心后，如何长时间将我的 PST 文件上载到 Azure？**</span><span class="sxs-lookup"><span data-stu-id="71991-266">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="71991-p141">在 Microsoft 数据中心收到您的硬盘后，将花费多之间 7 至 10 个工作日将 PST 文件上载到您的组织的 Microsoft Azure 存储区。PST 文件将上载到名为 Azure blob 容器`ingestiondata`。</span><span class="sxs-lookup"><span data-stu-id="71991-p141">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Microsoft Azure storage area for your organization. The PST files will be uploaded to a Azure blob container named `ingestiondata`.</span></span> 
  
 <span data-ttu-id="71991-269">**导入到邮箱的 PST 文件需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="71991-269">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="71991-p142">PST 文件上载到 Azure 存储区后，Office 365 分析 PST 文件中的数据 （以安全方式） 来标识的项目和 PST 文件中包含的其他消息类型的期限。完成此分析后，您必须导入 PST 文件中的所有数据的选项或设置筛选器与控制哪些数据获取导入。开始导入作业后，PST 文件导入到 Office 365 邮箱至少 24 GB 每日的速率。如果此速率，不能满足需要，可以考虑将电子邮件数据导入到 Office 365 的其他方法。有关详细信息，请参阅[方法迁移到 Office 365 的多个电子邮件帐户](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。</span><span class="sxs-lookup"><span data-stu-id="71991-p142">After the PST files are uploaded to the Azure storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported. After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="71991-p143">如果不同 PST 文件导入到不同的目标邮箱，导入过程会发生并行;换句话说，每个邮箱 PST 对导入同时。同样，如果多个 PST 文件导入到的同一邮箱，它们将同时导入。</span><span class="sxs-lookup"><span data-stu-id="71991-p143">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="71991-277">**Microsoft 将我的 PST 文件上载到 Azure 后，长它们保存在 Azure 正在删除之前？**</span><span class="sxs-lookup"><span data-stu-id="71991-277">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="71991-278">您的组织的所有 PST 文件中的 Azure 的存储位置 (名为 blob 容器中`ingestiondata`)，将删除 30 天后在安全的**导入**页上创建的最新的导入作业&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="71991-278">All PST files in the Azure storage location for your organization (in blob container named `ingestiondata`), are deleted 30 days after the most recent import job was created on the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="71991-p144">这还意味着从 Azure 存储区删除 PST 文件后，他们正在不再显示在安全中完成导入作业的文件列表中&amp;合规性中心。尽管安全中的**导入**页上，系统可能仍列出导入作业&amp;合规中心的 PST 文件列表可能为空，当您查看旧导入作业的详细信息。</span><span class="sxs-lookup"><span data-stu-id="71991-p144">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="71991-281">**导入到 Office 365 支持哪些版本的 PST 文件格式？**</span><span class="sxs-lookup"><span data-stu-id="71991-281">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="71991-p145">有两个版本的 PST 文件格式： ANSI 和 Unicode。我们建议导入使用 Unicode PST 文件格式的文件。但是，使用 ANSI PST 文件格式，如使用双字节字符的语言的文件 (DBCS)，也可以导入到 Office 365。有关导入 ANSI PST 文件的详细信息，请参阅[使用传送导入到 Office 365 组织 PST 文件的驱动器](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步骤 3。</span><span class="sxs-lookup"><span data-stu-id="71991-p145">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import your organization PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="71991-286">此外，可以到 Office 365 导入 PST 文件从 Outlook 2007 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="71991-286">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="71991-287">**导入 PST 文件时有邮件大小限制吗？**</span><span class="sxs-lookup"><span data-stu-id="71991-287">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="71991-p146">是的。如果 PST 文件中包含大于 150 MB 邮箱项目，将在导入过程跳过项目。</span><span class="sxs-lookup"><span data-stu-id="71991-p146">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="71991-290">**邮件属性，例如当邮件已发送或接收，收件人和其他属性，PST 文件导入到 Office 365 邮箱时保留的列表？**</span><span class="sxs-lookup"><span data-stu-id="71991-290">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="71991-p147">是的。导入过程中未更改的原始消息元数据</span><span class="sxs-lookup"><span data-stu-id="71991-p147">Yes. The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="71991-293">**是否有我想要导入到邮箱的 PST 文件的文件夹层次结构中的级别数限制？**</span><span class="sxs-lookup"><span data-stu-id="71991-293">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="71991-p148">是的。无法导入 PST 文件具有 300 或多个级别的嵌套文件夹。</span><span class="sxs-lookup"><span data-stu-id="71991-p148">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="71991-296">**可以使用驱动器传送到 Office 365 中的非活动邮箱导入 PST 文件？**</span><span class="sxs-lookup"><span data-stu-id="71991-296">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="71991-297">是，此功能现已推出的。</span><span class="sxs-lookup"><span data-stu-id="71991-297">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="71991-298">**可以使用驱动器传送到联机存档邮箱的 Exchange 混合部署中导入 PST 文件？**</span><span class="sxs-lookup"><span data-stu-id="71991-298">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="71991-299">是，此功能现已推出的。</span><span class="sxs-lookup"><span data-stu-id="71991-299">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="71991-300">**可以使用驱动器传送到 Exchange Online 中公用文件夹中导入 PST 文件？**</span><span class="sxs-lookup"><span data-stu-id="71991-300">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="71991-301">否，您不能 PST 文件导入公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="71991-301">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="71991-302">**运回我之前，可以 Microsoft 擦除我硬盘驱动器上？**</span><span class="sxs-lookup"><span data-stu-id="71991-302">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="71991-p149">否，Microsoft 不能擦除之前传送它们返回到客户的硬盘驱动器。硬盘驱动器相同时它们接收由 Microsoft 它们所处的状态返回给您。</span><span class="sxs-lookup"><span data-stu-id="71991-p149">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="71991-305">**Microsoft 可以清除而不是传送给我我硬盘驱动器上？**</span><span class="sxs-lookup"><span data-stu-id="71991-305">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="71991-p150">否，Microsoft 能销毁硬盘驱动器。硬盘驱动器相同时它们接收由 Microsoft 它们所处的状态返回给您。</span><span class="sxs-lookup"><span data-stu-id="71991-p150">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="71991-308">**返回传送的操作支持哪些 courier 服务？**</span><span class="sxs-lookup"><span data-stu-id="71991-308">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="71991-p151">如果您在美国或欧洲客户，Microsoft 使用 FedEx 返回硬盘驱动器。对于所有其他区域，Microsoft 使用 DHL。</span><span class="sxs-lookup"><span data-stu-id="71991-p151">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="71991-311">**返回传送成本是什么？**</span><span class="sxs-lookup"><span data-stu-id="71991-311">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="71991-p152">返回传送成本有所不同，具体取决于您接近 Microsoft 数据中心的传送到硬盘空间。Microsoft 将 bill 返回您的硬盘您 FedEx 或 DHL 的帐户。返回传送的成本是您的责任。</span><span class="sxs-lookup"><span data-stu-id="71991-p152">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="71991-315">**可以使用自定义 courier 传送服务，如 FedEx 自定义的传送提供给 Microsoft 我硬盘驱动器上？**</span><span class="sxs-lookup"><span data-stu-id="71991-315">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="71991-316">是。</span><span class="sxs-lookup"><span data-stu-id="71991-316">Yes.</span></span>
  
 <span data-ttu-id="71991-317">**如果我必须附带我到另一个国家/地区的硬盘，还有什么我需要做？**</span><span class="sxs-lookup"><span data-stu-id="71991-317">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="71991-p153">向 Microsoft 附带的硬盘可能需要跨国际边框。如果是这样，您负责确保的硬盘和它包含的数据将导入和/或适用法律按照导出。前传送硬盘驱动器，请与您的顾问验证，您的驱动器和数据合法可以传送到指定的 Microsoft 数据中心。这将有助于确保它及时到达 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="71991-p153">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>

---
title: 还原 Office 365 中的非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 如果新员工或另一个用户需要访问非活动邮箱 Office 365 中的内容，您可以还原 （或合并） 到现有邮箱的非活动邮箱的内容。
ms.openlocfilehash: e0add2b63a48edc27795143324c83153b15dcf8c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524879"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="8211b-103">还原 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="8211b-103">Restore an inactive mailbox in Office 365</span></span>

<span data-ttu-id="8211b-p101">非活动邮箱 （这是一种软删除邮箱） 用于保留以前员工的电子邮件，他/她离开组织之后。如果另一个雇员承担离开员工职责，或者该员工返回到您的组织，有两种方式，您可以将非活动邮箱的内容提供给用户：</span><span class="sxs-lookup"><span data-stu-id="8211b-p101">An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization. If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span> 
  
- <span data-ttu-id="8211b-p102">**还原非活动邮箱** 如果另一名员工接替离职员工的工作职责，或者如果另一个用户需要访问非活动邮箱的内容，您可以将非活动邮箱的内容还原（或 合并）到某个现有邮箱。您还可以从非活动邮箱还原存档。还原后，非活动邮箱将保留，并仍保留为非活动状态。本主题介绍还原非活动邮箱的过程。</span><span class="sxs-lookup"><span data-stu-id="8211b-p102">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox. This topic describes the procedures for restoring an inactive mailbox.</span></span> 
    
- <span data-ttu-id="8211b-p103">**恢复非活动邮箱**如果离开的员工返回到您的组织，或者如果新员工加入才能离开员工职责，您可以恢复非活动邮箱的内容。此方法将非活动邮箱转换为新邮箱包含非活动邮箱的内容。将在恢复之后，非活动邮箱不再存在。有关分步步骤说明，请参阅[恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="8211b-p103">**Recover an inactive mailbox** If the departed employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox. This method converts the inactive mailbox to a new mailbox that contains the contents of the inactive mailbox. After it's recovered, the inactive mailbox no longer exists. For the step-by-step procedures, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
<span data-ttu-id="8211b-114">请参阅有关还原和恢复非活动邮箱之间的差异的详细信息此文章中的**详细信息**部分。</span><span class="sxs-lookup"><span data-stu-id="8211b-114">See the **More information** section in this article for more details about the differences between restoring and recovering an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="8211b-115">准备工作</span><span class="sxs-lookup"><span data-stu-id="8211b-115">Before you begin</span></span>

- <span data-ttu-id="8211b-p104">您需要使用 Exchange Online PowerShell 中还原非活动邮箱。不能使用 Exchange 管理员中心 (EAC)。有关分步说明，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="8211b-p104">You have to use Exchange Online PowerShell to restore an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
- <span data-ttu-id="8211b-119">运行以下命令在 Exchange Online PowerShell，可以获取组织中的非活动邮箱的标识信息。</span><span class="sxs-lookup"><span data-stu-id="8211b-119">Run the following command in Exchange Online PowerShell to get identity information for the inactive mailboxes in your organization.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     <span data-ttu-id="8211b-120">使用此命令返回的信息来还原特定的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="8211b-120">Use the information returned by this command to restore a specific inactive mailbox.</span></span>
    
- <span data-ttu-id="8211b-121">有关非活动邮箱的详细信息，请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="8211b-121">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="8211b-122">还原非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="8211b-122">Restore an inactive mailbox</span></span>

<span data-ttu-id="8211b-p105">将 **New-MailboxRestoreRequest** cmdlet 与  _SourceMailbox_ 和  _TargetMailbox_ 参数一起使用，将非活动邮箱的内容还原到现有邮箱。有关使用此 cmdlet 的详细信息，请参阅 [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298)。</span><span class="sxs-lookup"><span data-stu-id="8211b-p105">Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox. For more information about using this cmdlet, see [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).</span></span>
  
1. <span data-ttu-id="8211b-125">创建包含非活动邮箱的属性的变量。</span><span class="sxs-lookup"><span data-stu-id="8211b-125">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="8211b-p106">在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="8211b-p106">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="8211b-p107">将非活动邮箱的内容还原到现有邮箱。非活动邮箱（源邮箱）的内容将合并到现有邮箱（目标邮箱）中的相应文件夹。</span><span class="sxs-lookup"><span data-stu-id="8211b-p107">Restore the contents of the inactive mailbox to an existing mailbox. The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).</span></span>
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   <span data-ttu-id="8211b-p108">或者，可以指定要从非活动邮箱还原内容的目标邮箱中的顶级文件夹。如果指定的目标文件夹或目标文件夹结构在目标邮箱中不存在，将在还原过程中创建。</span><span class="sxs-lookup"><span data-stu-id="8211b-p108">Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox. If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process.</span></span> 
    
    <span data-ttu-id="8211b-132">本示例将邮箱项目和子文件夹从非活动邮箱复制到目标邮箱的顶级文件夹结构中一个名为"非活动邮箱"的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8211b-132">This example copies mailbox items and subfolders from an inactive mailbox to a folder named "Inactive Mailbox" in the top-level folder structure of the target mailbox.</span></span>
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a><span data-ttu-id="8211b-133">从非活动邮箱还原存档</span><span class="sxs-lookup"><span data-stu-id="8211b-133">Restore the archive from an inactive mailbox</span></span>

<span data-ttu-id="8211b-p109">如果非活动邮箱具有存档邮箱，您还可以将其还原到现有邮箱的存档邮箱。要从非活动邮箱还原存档，必须向用于还原非活动邮箱的命令添加  _SourceIsArchive_ 和  _TargetIsAchive_ 开关。</span><span class="sxs-lookup"><span data-stu-id="8211b-p109">If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox. To restore the archive from an inactive mailbox, you have to add the  _SourceIsArchive_ and  _TargetIsAchive_ switches to the command used to restore an inactive mailbox.</span></span> 
  
1. <span data-ttu-id="8211b-136">创建包含非活动邮箱的属性的变量。</span><span class="sxs-lookup"><span data-stu-id="8211b-136">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="8211b-p110">在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="8211b-p110">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="8211b-p111">将非活动邮箱的存档（源存档）内容还原到现有邮箱的存档（目标存档）。在此示例中，将源存档的内容复制到目标邮箱的存档中一个名为"非活动邮箱存档"的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8211b-p111">Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive). In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.</span></span>

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a><span data-ttu-id="8211b-141">详细信息</span><span class="sxs-lookup"><span data-stu-id="8211b-141">More information</span></span>

- <span data-ttu-id="8211b-p112">**恢复和恢复非活动邮箱之间的主要区别是什么？** 非活动邮箱恢复时，邮箱基本上转换到新邮箱，将保留内容和非活动邮箱文件夹结构，以及邮箱链接到新的用户帐户。中非活动邮箱的保留其恢复、 不再存在非活动邮箱，并对新邮箱中的内容所做的任何更改会影响最初的内容之后。相反，还原非活动邮箱时，内容是只被复制到另一个邮箱。非活动邮箱已保留且保持非活动邮箱。对目标邮箱中的内容所做的任何更改都不会影响原始内容保留在非活动邮箱。非活动邮箱仍可在 Office 365 安全性中使用[内容搜索工具](run-a-content-search-in-the-security-and-compliance-center.md)搜索&amp;合规性中心可在其内容还原到另一个邮箱，或者可以恢复或删除稍后发布。</span><span class="sxs-lookup"><span data-stu-id="8211b-p112">**What's the main difference between recovering and restoring an inactive mailbox?** When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox. The inactive mailbox can still be searched by using the [Content Search tool](run-a-content-search-in-the-security-and-compliance-center.md) in the Office 365 Security &amp; Compliance Center, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span> 
    
- <span data-ttu-id="8211b-p113">**如何查找非活动邮箱？** 要获取您组织中的非活动邮箱的列表，并显示可用于恢复非活动邮箱的信息，可以运行此命令。</span><span class="sxs-lookup"><span data-stu-id="8211b-p113">**How do you find inactive mailboxes?** To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.</span></span> 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- <span data-ttu-id="8211b-p114">**使用诉讼保留或 Office 365 的保留策略保留非活动邮箱内容。** 如果您想要保留状态的非活动邮箱恢复后，您可以将置于[诉讼保留状态](https://go.microsoft.com/fwlink/?linkid=856286)的目标邮箱或应用[Office 365 保留策略](retention-policies.md)，然后再还原非活动邮箱。他们正在还原到目标邮箱后，这将防止永久删除非活动邮箱中任何项目。</span><span class="sxs-lookup"><span data-stu-id="8211b-p114">**Use a Litigation Hold or Office 365 retention policy to retain inactive mailbox content.** If you want to retain the state of an inactive mailbox after it's restored, you can place the target mailbox on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) or apply an [Office 365 retention policy](retention-policies.md) before you restore the inactive mailbox. This will prevent the permanent deletion of any items from the inactive mailbox after they're restored to the target mailbox.</span></span> 
    
- <span data-ttu-id="8211b-p115">**启用保留挂起对目标邮箱，然后再还原非活动邮箱。** 由于可能旧从非活动邮箱的邮箱项目，可能会考虑启用保留挂起对目标邮箱，然后再还原非活动邮箱。时保留上保留的邮箱时，将不会处理分配给它的保留策略，直到删除该保留保留或直到保留保留期。这样的目标邮箱时间从非活动邮箱管理旧邮件的所有者。否则为将保留策略可能会删除旧项目 （或将项目移动到存档邮箱中，如果已启用） 的已到期基于上配置的目标邮箱的保留设置。有关详细信息，请参阅[就地保留邮箱保留在 Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300)。</span><span class="sxs-lookup"><span data-stu-id="8211b-p115">**Enable retention hold on the target mailbox before you restore an inactive mailbox.** Because mailbox items from an inactive mailbox could be old, you might consider enabling retention hold on the target mailbox before you restore an inactive mailbox. When you put a mailbox on retention hold, the retention policy that's assigned to it won't be processed until the retention hold is removed or until the retention hold period expires. This gives the owner of the target mailbox time to manage old messages from the inactive mailbox. Otherwise, the retention policy might delete old items (or move items to the archive mailbox, if it's enabled) that have expired based on the retention settings configured for the target mailbox. For more information, see [Place a mailbox on retention hold in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).</span></span>
    
- <span data-ttu-id="8211b-p116">**AllowLegacyDNMismatch 开关的作用是什么？** 在上述示例中还原非活动邮箱， **AllowLegacyDNMismatch**开关用于允许将非活动邮箱还原到不同的目标邮箱。在典型还原方案中，目标是还原内容源和目标邮箱所在的同一邮箱。因此，默认情况下**New-mailboxrestorerequest** cmdlet 会进行检查以确保源和目标邮箱上的**LegacyExchangeDN**属性的值相同。这有助于防止意外到错误的目标邮箱还原的源邮箱。如果您尝试不使用**AllowLegacyDNMismatch**开关还原非活动邮箱，如果源和目标邮箱具有不同的**LegacyExchangeDN**属性的值，该命令可能失败。</span><span class="sxs-lookup"><span data-stu-id="8211b-p116">**What does the AllowLegacyDNMismatch switch do?** In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox. In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox. So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same. This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox. If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.</span></span> 
    
- <span data-ttu-id="8211b-p117">**可以使用 New-MailboxRestoreRequest cmdlet 与其他参数实现非活动邮箱的其他还原方案。** 例如，您可以运行此命令，将非活动邮箱的存档还原到目标邮箱的主邮箱。</span><span class="sxs-lookup"><span data-stu-id="8211b-p117">**You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.** For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox.</span></span> 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  <span data-ttu-id="8211b-168">通过运行此命令，还可以将非活动的主邮箱还原到目标邮箱的存档中。</span><span class="sxs-lookup"><span data-stu-id="8211b-168">You can also restore the inactive primary mailbox into the archive of the target mailbox by running this command.</span></span>

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- <span data-ttu-id="8211b-p118">**TargetRootFolder 参数有什么作用？** 如前面所述，您可以使用 **TargetRootFolder** 参数指定将向其还原非活动邮箱内容的目标邮箱中文件夹结构顶部的一个文件夹（也称为 根）。如果不使用此参数，非活动邮箱中的邮箱项目将合并到目标邮箱相应的默认文件夹中，并在目标邮箱的根目录中重新创建自定义文件夹。下图重点说明不使用和使用 **TargetRootFolder** 参数的区别。</span><span class="sxs-lookup"><span data-stu-id="8211b-p118">**What does the TargetRootFolder parameter do?** As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox. If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox. The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.</span></span> 
    
    <span data-ttu-id="8211b-173">**不使用 TargetRootFolder 参数时目标邮箱中的文件夹层次结构**</span><span class="sxs-lookup"><span data-stu-id="8211b-173">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter isn't used**</span></span>
    
    ![不使用 TargetRootFolder 参数时的屏幕截图](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    <span data-ttu-id="8211b-175">**使用 TargetRootFolder 参数时目标邮箱中的文件夹层次结构**</span><span class="sxs-lookup"><span data-stu-id="8211b-175">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter is used**</span></span>
    
    ![使用 TargetRootFolder 参数时的屏幕截图](media/300da592-7323-48db-b8a4-07012259d113.png)

  


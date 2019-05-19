---
title: 在 Office 365 中还原非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 如果新员工或其他用户需要访问 Office 365 中非活动邮箱的内容, 则可以将非活动邮箱的内容还原 (或合并) 到现有邮箱。
ms.openlocfilehash: 6bd147296e4324c5f75ff808768f8899cf9b59fd
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157304"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="74c39-103">在 Office 365 中还原非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="74c39-103">Restore an inactive mailbox in Office 365</span></span>

<span data-ttu-id="74c39-104">非活动邮箱 (一种软删除的邮箱类型) 用于在离开组织后保留前一个员工的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="74c39-104">An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="74c39-105">如果另一名员工接替离职员工的工作职责，或者该员工回到您的组织，有两种方法可以将非活动邮箱的内容提供给用户：</span><span class="sxs-lookup"><span data-stu-id="74c39-105">If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span> 
  
- <span data-ttu-id="74c39-p102">**还原非活动邮箱** 如果另一名员工接替离职员工的工作职责，或者如果另一个用户需要访问非活动邮箱的内容，您可以将非活动邮箱的内容还原（或 合并）到某个现有邮箱。您还可以从非活动邮箱还原存档。还原后，非活动邮箱将保留，并仍保留为非活动状态。本主题介绍还原非活动邮箱的过程。</span><span class="sxs-lookup"><span data-stu-id="74c39-p102">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox. This topic describes the procedures for restoring an inactive mailbox.</span></span> 
    
- <span data-ttu-id="74c39-110">**恢复非活动邮箱** 如果离职的员工回到您的组织，或者如果某位新员工要接替离职员工的工作职责，则可以恢复非活动邮箱的内容。</span><span class="sxs-lookup"><span data-stu-id="74c39-110">**Recover an inactive mailbox** If the departed employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox.</span></span> <span data-ttu-id="74c39-111">此方法将非活动邮箱转换为包含非活动邮箱内容的新邮箱。</span><span class="sxs-lookup"><span data-stu-id="74c39-111">This method converts the inactive mailbox to a new mailbox that contains the contents of the inactive mailbox.</span></span> <span data-ttu-id="74c39-112">恢复后，非活动邮箱不再存在。</span><span class="sxs-lookup"><span data-stu-id="74c39-112">After it's recovered, the inactive mailbox no longer exists.</span></span> <span data-ttu-id="74c39-113">有关分步过程, 请参阅[在 Office 365 中恢复非活动邮箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="74c39-113">For the step-by-step procedures, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
<span data-ttu-id="74c39-114">有关还原和恢复非活动邮箱之间的差异的更多详细信息, 请参阅本文中的**详细信息**一节。</span><span class="sxs-lookup"><span data-stu-id="74c39-114">See the **More information** section in this article for more details about the differences between restoring and recovering an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="74c39-115">开始之前</span><span class="sxs-lookup"><span data-stu-id="74c39-115">Before you begin</span></span>

- <span data-ttu-id="74c39-116">您必须使用 Exchange Online PowerShell 来还原非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="74c39-116">You have to use Exchange Online PowerShell to restore an inactive mailbox.</span></span> <span data-ttu-id="74c39-117">不能使用 Exchange 管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="74c39-117">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="74c39-118">有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="74c39-118">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
- <span data-ttu-id="74c39-119">在 Exchange Online PowerShell 中运行以下命令, 以获取组织中非活动邮箱的标识信息。</span><span class="sxs-lookup"><span data-stu-id="74c39-119">Run the following command in Exchange Online PowerShell to get identity information for the inactive mailboxes in your organization.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     <span data-ttu-id="74c39-120">使用此命令返回的信息来还原特定的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="74c39-120">Use the information returned by this command to restore a specific inactive mailbox.</span></span>
    
- <span data-ttu-id="74c39-121">有关非活动邮箱的详细信息, 请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="74c39-121">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="74c39-122">还原非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="74c39-122">Restore an inactive mailbox</span></span>

<span data-ttu-id="74c39-p105">将 **New-MailboxRestoreRequest** cmdlet 与  _SourceMailbox_ 和  _TargetMailbox_ 参数一起使用，将非活动邮箱的内容还原到现有邮箱。有关使用此 cmdlet 的详细信息，请参阅 [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298)。</span><span class="sxs-lookup"><span data-stu-id="74c39-p105">Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox. For more information about using this cmdlet, see [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).</span></span>
  
1. <span data-ttu-id="74c39-125">创建包含非活动邮箱的属性的变量。</span><span class="sxs-lookup"><span data-stu-id="74c39-125">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="74c39-p106">在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="74c39-p106">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="74c39-p107">将非活动邮箱的内容还原到现有邮箱。非活动邮箱（源邮箱）的内容将合并到现有邮箱（目标邮箱）中的相应文件夹。</span><span class="sxs-lookup"><span data-stu-id="74c39-p107">Restore the contents of the inactive mailbox to an existing mailbox. The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).</span></span>
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   <span data-ttu-id="74c39-p108">或者，可以指定要从非活动邮箱还原内容的目标邮箱中的顶级文件夹。如果指定的目标文件夹或目标文件夹结构在目标邮箱中不存在，将在还原过程中创建。</span><span class="sxs-lookup"><span data-stu-id="74c39-p108">Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox. If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process.</span></span> 
    
    <span data-ttu-id="74c39-132">本示例将邮箱项目和子文件夹从非活动邮箱复制到目标邮箱的顶级文件夹结构中一个名为"非活动邮箱"的文件夹。</span><span class="sxs-lookup"><span data-stu-id="74c39-132">This example copies mailbox items and subfolders from an inactive mailbox to a folder named "Inactive Mailbox" in the top-level folder structure of the target mailbox.</span></span>
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a><span data-ttu-id="74c39-133">从非活动邮箱还原存档</span><span class="sxs-lookup"><span data-stu-id="74c39-133">Restore the archive from an inactive mailbox</span></span>

<span data-ttu-id="74c39-p109">如果非活动邮箱具有存档邮箱，您还可以将其还原到现有邮箱的存档邮箱。要从非活动邮箱还原存档，必须向用于还原非活动邮箱的命令添加  _SourceIsArchive_ 和  _TargetIsAchive_ 开关。</span><span class="sxs-lookup"><span data-stu-id="74c39-p109">If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox. To restore the archive from an inactive mailbox, you have to add the  _SourceIsArchive_ and  _TargetIsAchive_ switches to the command used to restore an inactive mailbox.</span></span> 
  
1. <span data-ttu-id="74c39-136">创建包含非活动邮箱的属性的变量。</span><span class="sxs-lookup"><span data-stu-id="74c39-136">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="74c39-p110">在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="74c39-p110">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="74c39-p111">将非活动邮箱的存档（源存档）内容还原到现有邮箱的存档（目标存档）。在此示例中，将源存档的内容复制到目标邮箱的存档中一个名为"非活动邮箱存档"的文件夹。</span><span class="sxs-lookup"><span data-stu-id="74c39-p111">Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive). In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.</span></span>

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a><span data-ttu-id="74c39-141">详细信息</span><span class="sxs-lookup"><span data-stu-id="74c39-141">More information</span></span>

- <span data-ttu-id="74c39-142">**恢复和还原非活动邮箱的主要区别是什么？**</span><span class="sxs-lookup"><span data-stu-id="74c39-142">**What's the main difference between recovering and restoring an inactive mailbox?**</span></span> <span data-ttu-id="74c39-143">恢复非活动邮箱时，邮箱基本上会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="74c39-143">When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account.</span></span> <span data-ttu-id="74c39-144">恢复后，非活动邮箱不再存在，并且对新邮箱中的内容所做的任何更改都会影响最初保留在非活动邮箱中内容。</span><span class="sxs-lookup"><span data-stu-id="74c39-144">After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox.</span></span> <span data-ttu-id="74c39-145">相反，还原非活动邮箱时，只是将内容复制到另一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="74c39-145">Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox.</span></span> <span data-ttu-id="74c39-146">非活动邮箱将保留，并且仍保留非活动状态。</span><span class="sxs-lookup"><span data-stu-id="74c39-146">The inactive mailbox is preserved and remains an inactive mailbox.</span></span> <span data-ttu-id="74c39-147">对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。</span><span class="sxs-lookup"><span data-stu-id="74c39-147">Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox.</span></span> <span data-ttu-id="74c39-148">仍然可以使用安全 & 合规中心中的[内容搜索工具](run-a-content-search-in-the-security-and-compliance-center.md)搜索非活动邮箱, 可以将其内容还原到另一个邮箱, 也可以在以后恢复或删除它。</span><span class="sxs-lookup"><span data-stu-id="74c39-148">The inactive mailbox can still be searched by using the [Content Search tool](run-a-content-search-in-the-security-and-compliance-center.md) in the Security & Compliance Center, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span> 
    
- <span data-ttu-id="74c39-p113">**如何查找非活动邮箱？** 要获取您组织中的非活动邮箱的列表，并显示可用于恢复非活动邮箱的信息，可以运行此命令。</span><span class="sxs-lookup"><span data-stu-id="74c39-p113">**How do you find inactive mailboxes?** To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.</span></span> 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- <span data-ttu-id="74c39-151">**使用诉讼保留或 Office 365 保留策略保留非活动邮箱内容。**</span><span class="sxs-lookup"><span data-stu-id="74c39-151">**Use a Litigation Hold or Office 365 retention policy to retain inactive mailbox content.**</span></span> <span data-ttu-id="74c39-152">如果要在还原非活动邮箱后保留该邮箱的状态, 可以在还原非活动邮箱之前将目标邮箱置于[诉讼保留](https://go.microsoft.com/fwlink/?linkid=856286)或应用[Office 365 保留策略](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="74c39-152">If you want to retain the state of an inactive mailbox after it's restored, you can place the target mailbox on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) or apply an [Office 365 retention policy](retention-policies.md) before you restore the inactive mailbox.</span></span> <span data-ttu-id="74c39-153">这样可以防止在将非活动邮箱还原到目标邮箱之后，永久删除非活动邮箱中的任何项目。</span><span class="sxs-lookup"><span data-stu-id="74c39-153">This will prevent the permanent deletion of any items from the inactive mailbox after they're restored to the target mailbox.</span></span> 
    
- <span data-ttu-id="74c39-154">**在还原非活动邮箱之前，在目标邮箱上启用保留挂起功能。**</span><span class="sxs-lookup"><span data-stu-id="74c39-154">**Enable retention hold on the target mailbox before you restore an inactive mailbox.**</span></span> <span data-ttu-id="74c39-155">由于非活动邮箱中的邮箱项目可能已过时，您可能会考虑在还原非活动邮箱之前在目标邮箱上启用保留挂起功能。</span><span class="sxs-lookup"><span data-stu-id="74c39-155">Because mailbox items from an inactive mailbox could be old, you might consider enabling retention hold on the target mailbox before you restore an inactive mailbox.</span></span> <span data-ttu-id="74c39-156">将邮箱置于保留挂起状态时，在移除保留挂起或保留挂起期到期之前，将不会处理向其分配的保留策略。</span><span class="sxs-lookup"><span data-stu-id="74c39-156">When you put a mailbox on retention hold, the retention policy that's assigned to it won't be processed until the retention hold is removed or until the retention hold period expires.</span></span> <span data-ttu-id="74c39-157">这使目标邮箱的所有者有时间管理非活动邮箱中的邮件。</span><span class="sxs-lookup"><span data-stu-id="74c39-157">This gives the owner of the target mailbox time to manage old messages from the inactive mailbox.</span></span> <span data-ttu-id="74c39-158">否则，保留策略可能会删除根据为目标邮箱配置的保留设置已到期的旧项目，或将项目移动到存档邮箱（如果已启用）中。</span><span class="sxs-lookup"><span data-stu-id="74c39-158">Otherwise, the retention policy might delete old items (or move items to the archive mailbox, if it's enabled) that have expired based on the retention settings configured for the target mailbox.</span></span> <span data-ttu-id="74c39-159">有关详细信息, 请参阅[在 Exchange Online 中将邮箱置于保留挂起](https://go.microsoft.com/fwlink/?linkid=856300)状态。</span><span class="sxs-lookup"><span data-stu-id="74c39-159">For more information, see [Place a mailbox on retention hold in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856300).</span></span>
    
- <span data-ttu-id="74c39-160">**AllowLegacyDNMismatch 开关有什么作用？**</span><span class="sxs-lookup"><span data-stu-id="74c39-160">**What does the AllowLegacyDNMismatch switch do?**</span></span> <span data-ttu-id="74c39-161">在前面还原非活动邮箱的示例中， **AllowLegacyDNMismatch** 开关用来允许将非活动邮箱还原到不同的目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="74c39-161">In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox.</span></span> <span data-ttu-id="74c39-162">在典型的还原方案中，目标是还原源邮箱和目标邮箱为同一个邮箱的内容。</span><span class="sxs-lookup"><span data-stu-id="74c39-162">In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox.</span></span> <span data-ttu-id="74c39-163">因此, 默认情况下, **new-mailboxrestorerequest** cmdlet 会进行检查以确保源邮箱和目标邮箱上的**LegacyExchangeDN**属性值相同。</span><span class="sxs-lookup"><span data-stu-id="74c39-163">So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same.</span></span> <span data-ttu-id="74c39-164">此检查可防止您将源邮箱意外还原到错误的目标邮箱中。</span><span class="sxs-lookup"><span data-stu-id="74c39-164">This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox.</span></span> <span data-ttu-id="74c39-165">如果您尝试在不使用 **AllowLegacyDNMismatch** 开关的情况下还原非活动邮箱，则当源邮箱和目标邮箱具有不同的 **LegacyExchangeDN** 属性值时，该命令可能会失败。</span><span class="sxs-lookup"><span data-stu-id="74c39-165">If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.</span></span> 
    
- <span data-ttu-id="74c39-p117">**可以使用 New-MailboxRestoreRequest cmdlet 与其他参数实现非活动邮箱的其他还原方案。** 例如，您可以运行此命令，将非活动邮箱的存档还原到目标邮箱的主邮箱。</span><span class="sxs-lookup"><span data-stu-id="74c39-p117">**You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.** For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox.</span></span> 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  <span data-ttu-id="74c39-168">通过运行此命令，还可以将非活动的主邮箱还原到目标邮箱的存档中。</span><span class="sxs-lookup"><span data-stu-id="74c39-168">You can also restore the inactive primary mailbox into the archive of the target mailbox by running this command.</span></span>

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- <span data-ttu-id="74c39-p118">**TargetRootFolder 参数有什么作用？** 如前面所述，您可以使用 **TargetRootFolder** 参数指定将向其还原非活动邮箱内容的目标邮箱中文件夹结构顶部的一个文件夹（也称为 根）。如果不使用此参数，非活动邮箱中的邮箱项目将合并到目标邮箱相应的默认文件夹中，并在目标邮箱的根目录中重新创建自定义文件夹。下图重点说明不使用和使用 **TargetRootFolder** 参数的区别。</span><span class="sxs-lookup"><span data-stu-id="74c39-p118">**What does the TargetRootFolder parameter do?** As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox. If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox. The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.</span></span> 
    
    <span data-ttu-id="74c39-173">**不使用 TargetRootFolder 参数时目标邮箱中的文件夹层次结构**</span><span class="sxs-lookup"><span data-stu-id="74c39-173">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter isn't used**</span></span>
    
    ![不使用 TargetRootFolder 参数时的屏幕截图](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    <span data-ttu-id="74c39-175">**使用 TargetRootFolder 参数时目标邮箱中的文件夹层次结构**</span><span class="sxs-lookup"><span data-stu-id="74c39-175">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter is used**</span></span>
    
    ![使用 TargetRootFolder 参数时的屏幕截图](media/300da592-7323-48db-b8a4-07012259d113.png)

  


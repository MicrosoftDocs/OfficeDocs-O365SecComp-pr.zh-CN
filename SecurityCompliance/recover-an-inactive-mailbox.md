---
title: 在 Office 365 中恢复非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: '如果以前的员工返回到您的组织, 或者如果雇用新员工来承担 departed 员工的工作职责, 则可以在 Office 365 中恢复非活动邮箱的内容。恢复非活动邮箱时, 会将其转换为新邮箱, 其中包含非活动邮箱的内容。 '
ms.openlocfilehash: f5c844b5841518f1aa74a122d4c43663ebcccd14
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295835"
---
# <a name="recover-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="81335-104">在 Office 365 中恢复非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="81335-104">Recover an inactive mailbox in Office 365</span></span>

<span data-ttu-id="81335-p102">非活动邮箱 (一种软删除的邮箱类型) 用于在离开组织后保留以前的员工的电子邮件。如果该员工返回到您的组织或其他员工承担前一个员工的工作职责, 则可以通过两种方法使非活动邮箱的内容对用户可用:</span><span class="sxs-lookup"><span data-stu-id="81335-p102">An inactive mailbox (which is a type of soft-deleted mailbox) is used to preserve a former employee's email after he or she leaves your organization. If that employee returns to your organization or if another employee takes on the job responsibilities of the former employee, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span> 
  
- <span data-ttu-id="81335-p103">**恢复非活动邮箱**如果以前的员工返回到您的组织, 或者雇用新员工来承担前一个员工的工作职责, 则可以恢复非活动邮箱的内容。此方法将非活动邮箱转换为一个新的活动邮箱, 其中包含非活动邮箱的内容。恢复后, 非活动邮箱将不再存在。本主题中的过程介绍了此方法。</span><span class="sxs-lookup"><span data-stu-id="81335-p103">**Recover an inactive mailbox** If the former employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the former employee, you can recover the contents of the inactive mailbox. This method converts the inactive mailbox to a new, active mailbox that contains the contents of the inactive mailbox. After it's recovered, the inactive mailbox no longer exists. The procedures in this topic describe this method.</span></span> 
    
- <span data-ttu-id="81335-p104">**还原非活动邮箱**如果其他员工承担前一个员工的工作职责, 或者如果其他用户需要访问非活动邮箱的内容, 则可以将非活动邮箱的内容还原 (或合并) 到现有邮箱。您还可以从非活动邮箱还原存档。有关此方法的过程, 请参阅[还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="81335-p104">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the former employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. For the procedures for this method, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
<span data-ttu-id="81335-114">有关恢复和还原非活动邮箱之间的差异的详细信息，以及恢复非活动邮箱后所发生情况的描述，请参阅[详细信息](recover-an-inactive-mailbox.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="81335-114">See the [More information](recover-an-inactive-mailbox.md#moreinfo) section for more details about the differences between recovering and restoring an inactive mailbox, and for a description of what happens when an inactive mailbox is recovered.</span></span>
  
> [!NOTE]
> <span data-ttu-id="81335-p105">我们推迟了创建新的就地保留的截止时间, 以使邮箱处于非活动状态。但在将来的某一时刻, 你将无法在 Exchange Online 中创建新的就地保留。在这段时间, 仅可使用诉讼保留和 Office 365 保留策略来创建非活动邮箱。但是, 仍将支持就地保留中的现有非活动邮箱, 并且可以继续管理非活动邮箱的就地保留。这包括更改就地保留的持续时间以及通过删除就地保留来永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="81335-p105">We've postponed the deadline for creating new In-Place Holds to make a mailbox inactive. But at some point in the future, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="81335-120">准备工作</span><span class="sxs-lookup"><span data-stu-id="81335-120">Before you begin</span></span>

- <span data-ttu-id="81335-p106">您必须使用 Exchange Online PowerShell 来还原非活动邮箱。您不能使用 Exchange 管理中心 (EAC)。有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="81335-p106">You have to use Exchange Online PowerShell to restore an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
- <span data-ttu-id="81335-124">运行以下命令获取组织中非活动邮箱的标识信息。</span><span class="sxs-lookup"><span data-stu-id="81335-124">Run the following command to get identity information for the inactive mailboxes in your organization.</span></span> 

    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    <span data-ttu-id="81335-125">使用此命令返回的信息来恢复特定的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="81335-125">Use the information returned by this command to recover a specific inactive mailbox.</span></span>
    
- <span data-ttu-id="81335-126">有关非活动邮箱的详细信息, 请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="81335-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="recover-an-inactive-mailbox"></a><span data-ttu-id="81335-127">恢复非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="81335-127">Recover an inactive mailbox</span></span>

<span data-ttu-id="81335-128">将**新邮箱**cmdlet 与*InactiveMailbox*参数一起使用可恢复非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="81335-128">Use the **New-Mailbox** cmdlet with the  *InactiveMailbox*  parameter to recover an inactive mailbox.</span></span> 
  
1. <span data-ttu-id="81335-129">创建包含非活动邮箱的属性的变量。</span><span class="sxs-lookup"><span data-stu-id="81335-129">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```
   
    > [!IMPORTANT]
    > <span data-ttu-id="81335-p107">在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="81335-p107">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="81335-p108">本示例使用在上一个命令中获取的属性, 并将非活动邮箱恢复为用户王小姐 Beebe 的活动邮箱。请确保为*Name*和*MicrosoftOnlineServicesID*参数指定的值在您的组织中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="81335-p108">This example uses the properties obtained in the previous command and recovers the inactive mailbox to an active mailbox for the user Ann Beebe. Be sure that the values specified for the  *Name*  and  *MicrosoftOnlineServicesID*  parameters are unique within your organization.</span></span> 

    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    <span data-ttu-id="81335-134">已恢复的非活动邮箱的主 SMTP 地址将与*MicrosoftOnlineServicesID*参数指定的值相同。</span><span class="sxs-lookup"><span data-stu-id="81335-134">The primary SMTP address for the recovered inactive mailbox will have the same value as the one specified by the  *MicrosoftOnlineServicesID*  parameter.</span></span> 
    
<span data-ttu-id="81335-p109">恢复非活动邮箱后，还将创建新的 Office 365 用户帐户。您必须通过分配许可证来激活此用户帐户。若要在 Office 365 管理中心中分配许可证，请参阅[为 Office 365 商业版分配或取消分配许可证](https://go.microsoft.com/fwlink/p/?LinkId=276798)。</span><span class="sxs-lookup"><span data-stu-id="81335-p109">After you recover an inactive mailbox, a new Office 365 user account is also created. You have to activate this user account by assigning a license. To assign a license in the Office 365 admin center, see [Assign or unassign licenses for Office 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=276798).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="81335-138">更多信息</span><span class="sxs-lookup"><span data-stu-id="81335-138">More information</span></span>

- <span data-ttu-id="81335-p110">**恢复和还原非活动邮箱的主要区别是什么？** 恢复非活动邮箱时，邮箱基本上会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。恢复后，非活动邮箱不再存在，并且对新邮箱中的内容所做的任何更改都会影响最初保留在非活动邮箱中内容。相反，还原非活动邮箱时，只是将内容复制到另一个邮箱。非活动邮箱将保留，并且仍保留非活动状态。对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。仍可以使用就地电子数据展示搜索非活动邮箱，可以将其内容还原到另一个邮箱，也可以在以后将其恢复或删除。</span><span class="sxs-lookup"><span data-stu-id="81335-p110">**What's the main difference between recovering and restoring an inactive mailbox?** When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox. The inactive mailbox can still be searched by using In-Place eDiscovery, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span> 
    
- <span data-ttu-id="81335-p111">**恢复非活动邮箱时，会发生什么情况？** 恢复非活动邮箱时，将发生以下事件：</span><span class="sxs-lookup"><span data-stu-id="81335-p111">**What happens when you recover an inactive mailbox?** When you recover an inactive mailbox, the following things occur:</span></span> 
    
  - <span data-ttu-id="81335-148">移除诉讼保留（如果已为非活动邮箱启用）。</span><span class="sxs-lookup"><span data-stu-id="81335-148">Litigation Hold (if it was enabled for the inactive mailbox) is removed.</span></span>
    
  - <span data-ttu-id="81335-p112">移除就地保留。这意味着将非活动邮箱作为源邮箱从任何就地保留或就地电子数据展示搜索中删除。</span><span class="sxs-lookup"><span data-stu-id="81335-p112">In-Place Holds are removed. This means that the inactive mailbox is removed as a source mailbox from any In-Place Hold or In-Place eDiscovery searches.</span></span> 
    
  - <span data-ttu-id="81335-151">非活动邮箱将从应用于它的任何 Office 365 保留策略中删除。</span><span class="sxs-lookup"><span data-stu-id="81335-151">The inactive mailbox is removed from any Office 365 retention policies that where applied to it.</span></span>
    
  - <span data-ttu-id="81335-p113">单个项目恢复期间（由 **RetainDeletedItemsFor** 邮箱属性定义）设置为 30 天。通常情况下，在 Exchange Online 中创建新邮箱时，此保留期设置为 14 天。将此值设置为最大值 30 天，可留出更多时间从非活动邮箱中恢复任何已永久删除（或清除）的数据。您也可以禁用单个项目恢复，或将单个项目恢复期设置为默认的 14 天。有关详细信息，请参阅 [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769)。</span><span class="sxs-lookup"><span data-stu-id="81335-p113">The single item recovery period (which is defined by the **RetainDeletedItemsFor** mailbox property) is set to 30 days. Typically, when a new mailbox is created in Exchange Online, this retention period is set to 14 days. Setting this to the maximum value of 30 days gives you more time to recover any data that's been permanently deleted (or purged) from the inactive mailbox. You can also disable single item recovery or set the single item recovery period back to the default of 14 days. For more information, see [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769).</span></span>
    
  - <span data-ttu-id="81335-p114">保留挂起已启用, 保留挂起持续时间设置为30天。这意味着, 分配给新邮箱的默认 Exchange 保留策略和任何组织范围或 Exchange 范围的 Office 365 保留策略将不会被处理30天。这将为返回的员工或已恢复的非活动邮箱时间的新所有者提供管理旧邮件的时间。否则, exchange 或 office 365 保留策略可能会删除旧邮箱项目 (或根据为 Exchange 或 Office 365 保留策略配置的设置, 将项目移至存档邮箱 (如果已启用)。30天后, 保留挂起会过期, **RetentionHoldEnabled**邮箱属性设置为**False**, 并且托管文件夹助理将开始处理分配给邮箱的策略。如果不需要此额外时间, 只需删除保留挂起即可。或者, 可以使用 "**设置邮箱-EndDateForRetentionHold** " 命令来增加保留挂起的持续时间。有关详细信息, 请参阅[将邮箱放在保留挂起](https://go.microsoft.com/fwlink/?linkid=856300)中。</span><span class="sxs-lookup"><span data-stu-id="81335-p114">Retention hold is enabled, and the retention hold duration is set to 30 days. This means that the default Exchange retention policy and any organization-wide or Exchange-wide Office 365 retention policies that are assigned to the new mailbox won't be processed for 30 days. This gives the returning employee or the new owner of the recovered inactive mailbox time to manage the old messages. Otherwise, the Exchange or Office 365 retention policy might delete old mailbox items (or move items to the archive mailbox, if it's enabled) that have expired based on the settings configured for the Exchange or Office 365 retention policies. After 30 days, the retention hold expires, the **RetentionHoldEnabled** mailbox property is set to **False**, and the Managed Folder Assistant starts processing the policies assigned to the mailbox. If you don't need this additional time, you can just remove the retention hold. Alternatively, you can increase the duration of the retention hold by using the **Set-Mailbox -EndDateForRetentionHold** command. For more information, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/?linkid=856300).</span></span>
    
- <span data-ttu-id="81335-p115">**如果需要保留非活动邮箱的原始状态, 请在恢复的邮箱上放置保留。** 若要防止新邮箱所有者或保留策略从已恢复的非活动邮箱中永久删除任何邮件, 可以将邮箱置于诉讼保留中。有关详细信息, 请参阅[将邮箱置于诉讼保留状态](https://go.microsoft.com/fwlink/?linkid=856286)。</span><span class="sxs-lookup"><span data-stu-id="81335-p115">**Put a hold on the recovered mailbox if you need to preserve the original state of the inactive mailbox.** To prevent the new mailbox owner or retention policy from permanently deleting any messages from the recovered inactive mailbox, you can place the mailbox on Litigation Hold For more information, see [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286).</span></span>
    
- <span data-ttu-id="81335-p116">在**恢复非活动邮箱时, 可以使用什么用户 ID？** 恢复非活动邮箱时, 为*MicrosoftOnlineServicesID*参数指定的值可能与与非活动邮箱关联的原始值不同。您还可以使用原始用户 ID。但如前面所述, 在恢复非活动邮箱时, 请确保用于*Name*和*MicrosoftOnlineServicesID*的值在组织内是唯一的。</span><span class="sxs-lookup"><span data-stu-id="81335-p116">**What user ID can you use when recovering an inactive mailbox?** When you recover an inactive mailbox, the value that you specify for the  *MicrosoftOnlineServicesID*  parameter can be different from the original one that was associated with the inactive mailbox. You can also use the original user ID. But as previously stated, make sure that the values used for  *Name*  and  *MicrosoftOnlineServicesID*  are unique within your organization when you recover the inactive mailbox.</span></span> 
    
- <span data-ttu-id="81335-p117">**如果非活动邮箱的邮箱保留期尚未过期该怎么办？** 如果非活动邮箱是在 30 天内进行软删除的，则不能使用 **New-Mailbox -InactiveMailbox** 命令对其进行恢复。您必须通过还原相应的 Office 365 用户帐户来恢复它。有关详细信息，请参阅 [删除或还原用户](https://go.microsoft.com/fwlink/p/?LinkId=279162)。</span><span class="sxs-lookup"><span data-stu-id="81335-p117">**What if the mailbox retention period for the inactive mailbox hasn't expired?** If an inactive mailbox was soft-deleted less than 30 days ago, you can't use the **New-Mailbox -InactiveMailbox** command to recover it. You have to recover it by restoring the corresponding Office 365 user account. For more information, see [Delete or restore users](https://go.microsoft.com/fwlink/p/?LinkId=279162).</span></span>
    
- <span data-ttu-id="81335-p118">**如何知道非活动邮箱的软删除邮箱保留期是否已过期？** 运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="81335-p118">**How do you know if the soft-deleted mailbox retention period for an inactive mailbox has expired?** Run the following command.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    <span data-ttu-id="81335-p119">如果不存在 **ExternalDirectoryObjectId** 属性的值，则说明邮箱保留期已过期，您可以通过运行 **New-Mailbox -InactiveMailbox** 命令恢复非活动邮箱。如果存在 **ExternalDirectoryObjectId** 属性的值，则说明软删除邮箱保留期尚未过期，您必须通过还原 Office 365 用户帐户来恢复邮箱。请参阅 [删除或还原用户](https://go.microsoft.com/fwlink/p/?LinkId=279162)。</span><span class="sxs-lookup"><span data-stu-id="81335-p119">If there isn't a value for the **ExternalDirectoryObjectId** property, the mailbox retention period has expired, and you can recover the inactive mailbox by running the **New-Mailbox -InactiveMailbox** command. If there is a value for the **ExternalDirectoryObjectId** property, the soft-deleted mailbox retention period hasn't expired and you have to recover the mailbox by restoring the Office 365 user account. See [Delete or restore users](https://go.microsoft.com/fwlink/p/?LinkId=279162)</span></span>
    
- <span data-ttu-id="81335-p120">**请考虑在恢复非活动邮箱后启用存档邮箱。** 这将允许返回的用户或新员工将旧邮件移动到存档邮箱。当保留挂起过期时, 作为分配给 Exchange Online 邮箱的默认 Exchange 保留策略的一部分的存档策略将把两年或更早的项目移动到存档邮箱中。如果不启用存档邮箱, 则两年以前的项目将保留在用户的主邮箱中。有关详细信息, 请参阅[在 Office 365 安全&amp;合规中心中启用存档邮箱](enable-archive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="81335-p120">**Consider enabling the archive mailbox after you recover an inactive mailbox.** This lets the returning user or new employee move old messages to the archive mailbox. And when the retention hold expires, the archive policy that is part of the default Exchange retention policy assigned to Exchange Online mailboxes will move items that are two years or older to the archive mailbox. If you don't enable the archive mailbox, items older than two years will remain in the user's primary mailbox. For more information, see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md).</span></span>
 
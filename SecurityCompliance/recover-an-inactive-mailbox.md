---
title: 恢复 Office 365 中的非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: '如果以前员工返回给您的组织，或新员工加入才能离开员工职责，您可以恢复 Office 365 中的非活动邮箱的内容。非活动邮箱恢复时，它会将其转换为新邮箱包含非活动邮箱的内容。 '
ms.openlocfilehash: dcc84e44454a75f8b4dac953599632d632f340b9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525962"
---
# <a name="recover-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="472b5-104">恢复 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="472b5-104">Recover an inactive mailbox in Office 365</span></span>

<span data-ttu-id="472b5-p102">非活动邮箱 （这是一种软删除邮箱） 用于保留以前员工的电子邮件，他/她离开组织之后。如果该员工返回给您的组织或另一个雇员承担前雇员的工作职责，有两种方式，您可以将非活动邮箱的内容提供给用户：</span><span class="sxs-lookup"><span data-stu-id="472b5-p102">An inactive mailbox (which is a type of soft-deleted mailbox) is used to preserve a former employee's email after he or she leaves your organization. If that employee returns to your organization or if another employee takes on the job responsibilities of the former employee, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span> 
  
- <span data-ttu-id="472b5-p103">**恢复非活动邮箱**如果以前的员工返回到您的组织，或者如果新员工加入执行前雇员的工作职责，您可以恢复非活动邮箱的内容。此方法将非活动邮箱转换为新的活动邮箱包含非活动邮箱的内容。将在恢复之后，非活动邮箱不再存在。本主题中的过程介绍了此方法。</span><span class="sxs-lookup"><span data-stu-id="472b5-p103">**Recover an inactive mailbox** If the former employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the former employee, you can recover the contents of the inactive mailbox. This method converts the inactive mailbox to a new, active mailbox that contains the contents of the inactive mailbox. After it's recovered, the inactive mailbox no longer exists. The procedures in this topic describe this method.</span></span> 
    
- <span data-ttu-id="472b5-p104">**还原非活动邮箱**如果另一个雇员承担的以前的员工的工作职责或另一个用户需要访问非活动邮箱的内容，您可以还原 （或合并） 到现有邮箱的非活动邮箱的内容。您还可以从非活动邮箱还原存档。此方法的过程，请参阅[还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="472b5-p104">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the former employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. For the procedures for this method, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
<span data-ttu-id="472b5-114">有关恢复和还原非活动邮箱之间的差异的详细信息，以及恢复非活动邮箱后所发生情况的描述，请参阅[详细信息](recover-an-inactive-mailbox.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="472b5-114">See the [More information](recover-an-inactive-mailbox.md#moreinfo) section for more details about the differences between recovering and restoring an inactive mailbox, and for a description of what happens when an inactive mailbox is recovered.</span></span>
  
> [!NOTE]
> <span data-ttu-id="472b5-p105">我们已推迟创建新的就地保留进行非活动邮箱的最后期限。但是，有时将来，您将无法创建新的就地保留在 Exchange Online。此时，仅诉讼保留和 Office 365 的保留策略可用于创建非活动邮箱。但是，仍会支持现有的非活动邮箱上就地保留的并且您可以继续管理非活动邮箱上就地保留。这包括更改的就地保留持续时间，并通过删除就地保留中永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="472b5-p105">We've postponed the deadline for creating new In-Place Holds to make a mailbox inactive. But at some point in the future, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="472b5-120">准备工作</span><span class="sxs-lookup"><span data-stu-id="472b5-120">Before you begin</span></span>

- <span data-ttu-id="472b5-p106">您需要使用 Exchange Online PowerShell 中还原非活动邮箱。不能使用 Exchange 管理员中心 (EAC)。有关分步说明，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="472b5-p106">You have to use Exchange Online PowerShell to restore an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span>
    
- <span data-ttu-id="472b5-124">运行以下命令获取组织中非活动邮箱的标识信息。</span><span class="sxs-lookup"><span data-stu-id="472b5-124">Run the following command to get identity information for the inactive mailboxes in your organization.</span></span> 

    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    <span data-ttu-id="472b5-125">使用此命令返回的信息来恢复特定的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="472b5-125">Use the information returned by this command to recover a specific inactive mailbox.</span></span>
    
- <span data-ttu-id="472b5-126">有关非活动邮箱的详细信息，请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="472b5-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="recover-an-inactive-mailbox"></a><span data-ttu-id="472b5-127">恢复非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="472b5-127">Recover an inactive mailbox</span></span>

<span data-ttu-id="472b5-128">使用**New-mailbox** cmdlet 与*InactiveMailbox*参数来恢复非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="472b5-128">Use the **New-Mailbox** cmdlet with the  *InactiveMailbox*  parameter to recover an inactive mailbox.</span></span> 
  
1. <span data-ttu-id="472b5-129">创建包含非活动邮箱的属性的变量。</span><span class="sxs-lookup"><span data-stu-id="472b5-129">Create a variable that contains the properties of the inactive mailbox.</span></span> 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```
   
    > [!IMPORTANT]
    > <span data-ttu-id="472b5-p107">在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="472b5-p107">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="472b5-p108">本示例使用在上一个命令中获得的属性，并恢复到 Ann Beebe 的用户活动邮箱的非活动邮箱。确保在您的组织内唯一的*名称*和*MicrosoftOnlineServicesID*参数指定的值。</span><span class="sxs-lookup"><span data-stu-id="472b5-p108">This example uses the properties obtained in the previous command and recovers the inactive mailbox to an active mailbox for the user Ann Beebe. Be sure that the values specified for the  *Name*  and  *MicrosoftOnlineServicesID*  parameters are unique within your organization.</span></span> 

    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    <span data-ttu-id="472b5-134">恢复的非活动邮箱的主 SMTP 地址会*MicrosoftOnlineServicesID*参数指定相同的值。</span><span class="sxs-lookup"><span data-stu-id="472b5-134">The primary SMTP address for the recovered inactive mailbox will have the same value as the one specified by the  *MicrosoftOnlineServicesID*  parameter.</span></span> 
    
<span data-ttu-id="472b5-p109">恢复非活动邮箱后，还将创建新的 Office 365 用户帐户。您必须通过分配许可证来激活此用户帐户。若要在 Office 365 管理中心中分配许可证，请参阅[为 Office 365 商业版分配或取消分配许可证](https://go.microsoft.com/fwlink/p/?LinkId=276798)。</span><span class="sxs-lookup"><span data-stu-id="472b5-p109">After you recover an inactive mailbox, a new Office 365 user account is also created. You have to activate this user account by assigning a license. To assign a license in the Office 365 admin center, see [Assign or unassign licenses for Office 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=276798).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="472b5-138">详细信息</span><span class="sxs-lookup"><span data-stu-id="472b5-138">More information</span></span>

- <span data-ttu-id="472b5-p110">**恢复和还原非活动邮箱的主要区别是什么？** 恢复非活动邮箱时，邮箱基本上会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。恢复后，非活动邮箱不再存在，并且对新邮箱中的内容所做的任何更改都会影响最初保留在非活动邮箱中内容。相反，还原非活动邮箱时，只是将内容复制到另一个邮箱。非活动邮箱将保留，并且仍保留非活动状态。对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。仍可以使用就地电子数据展示搜索非活动邮箱，可以将其内容还原到另一个邮箱，也可以在以后将其恢复或删除。</span><span class="sxs-lookup"><span data-stu-id="472b5-p110">**What's the main difference between recovering and restoring an inactive mailbox?** When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox. The inactive mailbox can still be searched by using In-Place eDiscovery, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span> 
    
- <span data-ttu-id="472b5-p111">**恢复非活动邮箱时，会发生什么情况？** 恢复非活动邮箱时，将发生以下事件：</span><span class="sxs-lookup"><span data-stu-id="472b5-p111">**What happens when you recover an inactive mailbox?** When you recover an inactive mailbox, the following things occur:</span></span> 
    
  - <span data-ttu-id="472b5-148">移除诉讼保留（如果已为非活动邮箱启用）。</span><span class="sxs-lookup"><span data-stu-id="472b5-148">Litigation Hold (if it was enabled for the inactive mailbox) is removed.</span></span>
    
  - <span data-ttu-id="472b5-p112">移除就地保留。这意味着将非活动邮箱作为源邮箱从任何就地保留或就地电子数据展示搜索中删除。</span><span class="sxs-lookup"><span data-stu-id="472b5-p112">In-Place Holds are removed. This means that the inactive mailbox is removed as a source mailbox from any In-Place Hold or In-Place eDiscovery searches.</span></span> 
    
  - <span data-ttu-id="472b5-151">从 Office 365 的任何保留策略中删除非活动邮箱，因为应用于它。</span><span class="sxs-lookup"><span data-stu-id="472b5-151">The inactive mailbox is removed from any Office 365 retention policies that where applied to it.</span></span>
    
  - <span data-ttu-id="472b5-p113">单个项目恢复期间（由 **RetainDeletedItemsFor** 邮箱属性定义）设置为 30 天。通常情况下，在 Exchange Online 中创建新邮箱时，此保留期设置为 14 天。将此值设置为最大值 30 天，可留出更多时间从非活动邮箱中恢复任何已永久删除（或清除）的数据。您也可以禁用单个项目恢复，或将单个项目恢复期设置为默认的 14 天。有关详细信息，请参阅 [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769)。</span><span class="sxs-lookup"><span data-stu-id="472b5-p113">The single item recovery period (which is defined by the **RetainDeletedItemsFor** mailbox property) is set to 30 days. Typically, when a new mailbox is created in Exchange Online, this retention period is set to 14 days. Setting this to the maximum value of 30 days gives you more time to recover any data that's been permanently deleted (or purged) from the inactive mailbox. You can also disable single item recovery or set the single item recovery period back to the default of 14 days. For more information, see [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769).</span></span>
    
  - <span data-ttu-id="472b5-p114">启用保留挂起时，并且保留保留持续时间设置为 30 天。这意味着，默认 Exchange 保留策略和任何组织范围内或 Exchange 范围内的 Office 365 已分配给新邮箱的保留策略不会处理 30 天。这使返回员工或新的已恢复的非活动邮箱时间的所有者管理旧邮件。否则为在 Exchange 或 Office 365 保留策略可能会删除旧的邮箱项目 （或将项目移动到存档邮箱中，如果已启用） 的已到期基于 Exchange 或 Office 365 保留策略配置的设置。30 天后保留挂起过期， **RetentionHoldEnabled** mailbox 属性设置为**False**，以及托管文件夹助理开始处理分配给邮箱的策略。如果您不需要此的更多时间，您可以只删除保留挂起。此外，您可以使用**Set-mailbox EndDateForRetentionHold**命令增加保留挂起的持续时间。有关详细信息，请参阅[就地保留邮箱保留](https://go.microsoft.com/fwlink/?linkid=856300)。</span><span class="sxs-lookup"><span data-stu-id="472b5-p114">Retention hold is enabled, and the retention hold duration is set to 30 days. This means that the default Exchange retention policy and any organization-wide or Exchange-wide Office 365 retention policies that are assigned to the new mailbox won't be processed for 30 days. This gives the returning employee or the new owner of the recovered inactive mailbox time to manage the old messages. Otherwise, the Exchange or Office 365 retention policy might delete old mailbox items (or move items to the archive mailbox, if it's enabled) that have expired based on the settings configured for the Exchange or Office 365 retention policies. After 30 days, the retention hold expires, the **RetentionHoldEnabled** mailbox property is set to **False**, and the Managed Folder Assistant starts processing the policies assigned to the mailbox. If you don't need this additional time, you can just remove the retention hold. Alternatively, you can increase the duration of the retention hold by using the **Set-Mailbox -EndDateForRetentionHold** command. For more information, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/?linkid=856300).</span></span>
    
- <span data-ttu-id="472b5-p115">**置于已恢复的邮箱的保留，如果您需要保留非活动邮箱的原始状态。** 若要防止新邮箱所有者或保留策略从已恢复的非活动邮箱中永久删除任何消息，您可以将邮箱置于诉讼保留的详细信息，请参阅[Place 上诉讼保留的邮箱](https://go.microsoft.com/fwlink/?linkid=856286)。</span><span class="sxs-lookup"><span data-stu-id="472b5-p115">**Put a hold on the recovered mailbox if you need to preserve the original state of the inactive mailbox.** To prevent the new mailbox owner or retention policy from permanently deleting any messages from the recovered inactive mailbox, you can place the mailbox on Litigation Hold For more information, see [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286).</span></span>
    
- <span data-ttu-id="472b5-p116">**哪些用户 ID 您可以使用恢复非活动邮箱时？** 非活动邮箱恢复时，为*MicrosoftOnlineServicesID*参数指定的值可以是不同于原始的非活动邮箱相关联。您还可以使用原始用户 id。但是，如前面所述，请确保非活动邮箱恢复时在您的组织内唯一用于*名称*和*MicrosoftOnlineServicesID*的值。</span><span class="sxs-lookup"><span data-stu-id="472b5-p116">**What user ID can you use when recovering an inactive mailbox?** When you recover an inactive mailbox, the value that you specify for the  *MicrosoftOnlineServicesID*  parameter can be different from the original one that was associated with the inactive mailbox. You can also use the original user ID. But as previously stated, make sure that the values used for  *Name*  and  *MicrosoftOnlineServicesID*  are unique within your organization when you recover the inactive mailbox.</span></span> 
    
- <span data-ttu-id="472b5-p117">**如果非活动邮箱的邮箱保留期尚未过期该怎么办？** 如果非活动邮箱是在 30 天内进行软删除的，则不能使用 **New-Mailbox -InactiveMailbox** 命令对其进行恢复。您必须通过还原相应的 Office 365 用户帐户来恢复它。有关详细信息，请参阅 [删除或还原用户](https://go.microsoft.com/fwlink/p/?LinkId=279162)。</span><span class="sxs-lookup"><span data-stu-id="472b5-p117">**What if the mailbox retention period for the inactive mailbox hasn't expired?** If an inactive mailbox was soft-deleted less than 30 days ago, you can't use the **New-Mailbox -InactiveMailbox** command to recover it. You have to recover it by restoring the corresponding Office 365 user account. For more information, see [Delete or restore users](https://go.microsoft.com/fwlink/p/?LinkId=279162).</span></span>
    
- <span data-ttu-id="472b5-p118">**如何知道非活动邮箱的软删除邮箱保留期是否已过期？** 运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="472b5-p118">**How do you know if the soft-deleted mailbox retention period for an inactive mailbox has expired?** Run the following command.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    <span data-ttu-id="472b5-p119">如果不存在 **ExternalDirectoryObjectId** 属性的值，则说明邮箱保留期已过期，您可以通过运行 **New-Mailbox -InactiveMailbox** 命令恢复非活动邮箱。如果存在 **ExternalDirectoryObjectId** 属性的值，则说明软删除邮箱保留期尚未过期，您必须通过还原 Office 365 用户帐户来恢复邮箱。请参阅 [删除或还原用户](https://go.microsoft.com/fwlink/p/?LinkId=279162)。</span><span class="sxs-lookup"><span data-stu-id="472b5-p119">If there isn't a value for the **ExternalDirectoryObjectId** property, the mailbox retention period has expired, and you can recover the inactive mailbox by running the **New-Mailbox -InactiveMailbox** command. If there is a value for the **ExternalDirectoryObjectId** property, the soft-deleted mailbox retention period hasn't expired and you have to recover the mailbox by restoring the Office 365 user account. See [Delete or restore users](https://go.microsoft.com/fwlink/p/?LinkId=279162)</span></span>
    
- <span data-ttu-id="472b5-p120">**考虑后恢复非活动邮箱启用存档邮箱。** 这样可以返回用户或新员工将旧邮件移动到存档邮箱。保留挂起过期时, 的存档策略的默认 Exchange 保留策略分配到 Exchange Online 邮箱移动两年的项目或较旧的存档邮箱到的一部分。如果不启用存档邮箱，两年以前的项目将保留在用户的主邮箱。有关详细信息，请参阅[Office 365 安全性启用存档邮箱&amp;合规性中心](enable-archive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="472b5-p120">**Consider enabling the archive mailbox after you recover an inactive mailbox.** This lets the returning user or new employee move old messages to the archive mailbox. And when the retention hold expires, the archive policy that is part of the default Exchange retention policy assigned to Exchange Online mailboxes will move items that are two years or older to the archive mailbox. If you don't enable the archive mailbox, items older than two years will remain in the user's primary mailbox. For more information, see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md).</span></span>
 
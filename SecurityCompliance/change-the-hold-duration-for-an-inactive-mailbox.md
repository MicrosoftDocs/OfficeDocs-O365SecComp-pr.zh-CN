---
title: 更改在 Office 365 中的非活动邮箱的保留持续时间
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Office 365 邮箱进行非活动状态后，您可以更改保持或 Office 365 分配给非活动邮箱的保留策略的持续时间。保留持续时间定义在可恢复项目文件夹保留多长时间的项目。
ms.openlocfilehash: 22bd9f9294b625a38d243f6235097d1aee437121
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525440"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="e4e8b-104">更改在 Office 365 中的非活动邮箱的保留持续时间</span><span class="sxs-lookup"><span data-stu-id="e4e8b-104">Change the hold duration for an inactive mailbox in Office 365</span></span>

<span data-ttu-id="e4e8b-p102">非活动邮箱用于保留以前员工的电子邮件，他/她离开组织之后。邮箱变为非活动状态时诉讼保留、 就地保留、 Office 365 保留策略，或保留与电子数据展示事例相关联的置于邮箱，并删除相应的 Office 365 用户帐户。非活动邮箱的内容将保留在邮箱发出，已处于非活动状态的保留项的持续时间。保留持续时间定义在可恢复项目文件夹保留多长时间的项目。保留持续时间过后可恢复邮件文件夹中的项，该项被永久删除 （清除） 从非活动邮箱。非活动邮箱后，您可以更改保持或 Office 365 分配给非活动邮箱的保留策略的持续时间。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p102">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization. A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, an Office 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding Office 365 user account is deleted. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. The hold duration defines how long items in the Recoverable Items folder are held. When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox. After a mailbox is made inactive, you can change the duration of the hold or Office 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e4e8b-p103">我们已推迟创建新的就地保留进行非活动邮箱的 2017 年 7 月 1，最后期限。但今年或早期明年，您将无法创建新的就地保留在 Exchange Online。此时，仅诉讼保留和 Office 365 的保留策略可用于创建非活动邮箱。但是，仍会支持现有的非活动邮箱上就地保留的并且您可以继续管理非活动邮箱上就地保留。这包括更改的就地保留持续时间，并通过删除就地保留中永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="e4e8b-116">准备工作</span><span class="sxs-lookup"><span data-stu-id="e4e8b-116">Before you begin</span></span>

- <span data-ttu-id="e4e8b-p104">您必须使用 Exchange Online PowerShell 中，若要更改的非活动邮箱诉讼保留的保留持续时间。不能使用 Exchange 管理员中心 (EAC)。但您可以使用 Exchange Online PowerShell 中或 EAC 若要更改保留持续时间的就地保留。您可以使用 Office 365 安全性&amp;合规性中心或安全&amp;合规性中心 PowerShell，可以更改的 Office 365 保留策略的保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p104">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox. You can't use the Exchange admin center (EAC). But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold. You can use the Office 365 Security &amp; Compliance Center or the Security &amp; Compliance Center PowerShell to change the hold duration for an Office 365 retention policy.</span></span>
    
- <span data-ttu-id="e4e8b-121">连接到 Exchange Online PowerShell 中或安全&amp;合规性中心 PowerShell 中，请参阅以下主题之一：</span><span class="sxs-lookup"><span data-stu-id="e4e8b-121">To connect to Exchange Online PowerShell or Security &amp; Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="e4e8b-122">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e4e8b-122">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [<span data-ttu-id="e4e8b-123">连接到 Office 365 安全性&amp;合规性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4e8b-123">Connect to Office 365 Security &amp; Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
- <span data-ttu-id="e4e8b-p105">请注意，包含与电子数据展示事例关联是无限期保留，这意味着没有可更改没有保留持续时间。不限次数或直到保留被删除，并删除非活动邮箱保留项。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p105">Note that holds associated with eDiscovery cases are infinite holds, which means there is no hold duration that can be changed. Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="e4e8b-126">有关非活动邮箱的详细信息，请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="e4e8b-127">第 1 步：识别非活动邮箱上设置的保留</span><span class="sxs-lookup"><span data-stu-id="e4e8b-127">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="e4e8b-128">由于不同类型的保留项或一个或多个 Office 365 保留策略可能放置在非活动邮箱中，第一步是确定在非活动邮箱保留。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-128">Because different types of holds or one or more Office 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="e4e8b-129">运行以下命令在 Exchange Online PowerShell，可以显示组织中的所有非活动邮箱的保留信息。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-129">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
<span data-ttu-id="e4e8b-p106">**LitigationHoldEnabled**属性的值为**True**指示非活动邮箱位于诉讼保留。如果就地保留电子数据展示保留，或 Office 365 保留策略放置在非活动邮箱，保留或保留策略的 GUID 显示为**InPlaceHolds**属性的值。例如，下面的示例显示 5 的非活动邮箱的结果。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p106">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold, eDiscovery hold, or Office 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property. For example, the following shows results for 5 inactive mailboxes.</span></span> 
  
||
|:-----|
|
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```
   
<span data-ttu-id="e4e8b-133">下表标识用于使每个邮箱处于非活动状态的五个不同的保留类型。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-133">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="e4e8b-134">**非活动邮箱**</span><span class="sxs-lookup"><span data-stu-id="e4e8b-134">**Inactive mailbox**</span></span>|<span data-ttu-id="e4e8b-135">**保留类型**</span><span class="sxs-lookup"><span data-stu-id="e4e8b-135">**Hold type**</span></span>|<span data-ttu-id="e4e8b-136">**如何标识非活动邮箱的保留项**</span><span class="sxs-lookup"><span data-stu-id="e4e8b-136">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e4e8b-137">Ann Beebe</span><span class="sxs-lookup"><span data-stu-id="e4e8b-137">Ann Beebe</span></span>  <br/> |<span data-ttu-id="e4e8b-138">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="e4e8b-138">Litigation Hold</span></span>  <br/> |<span data-ttu-id="e4e8b-139">*LitigationHoldEnabled*属性设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-139">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="e4e8b-140">Pilar Pinilla</span><span class="sxs-lookup"><span data-stu-id="e4e8b-140">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="e4e8b-141">就地保留</span><span class="sxs-lookup"><span data-stu-id="e4e8b-141">In-Place Hold</span></span>  <br/> |<span data-ttu-id="e4e8b-p107">*InPlaceHolds*属性将包含非活动邮箱置于就地保留的 GUID。您可以判断这是就地保留因为 ID 不以前缀开头。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p107">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox. You can tell this is an In-Place Hold because the ID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="e4e8b-144">您可以使用 Get-mailboxsearch InPlaceHoldIdentity<hold GUID></span><span class="sxs-lookup"><span data-stu-id="e4e8b-144">You can use the  \`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID></span></span> | <span data-ttu-id="e4e8b-145">FL 命令在 Exchange Online PowerShell 中获得非活动邮箱上的就地保留的信息。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-145">FL\` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="e4e8b-146">Mario Necaise</span><span class="sxs-lookup"><span data-stu-id="e4e8b-146">Mario Necaise</span></span>  <br/> |<span data-ttu-id="e4e8b-147">组织范围内安全中的 Office 365 保留策略&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="e4e8b-147">Organization-wide Office 365 retention policy in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="e4e8b-p108">*InPlaceHolds*属性为空。这指示的一个或多个组织范围或 （Exchange 范围） Office 365 保留策略应用于非活动邮箱。在这种情况下，您可以运行 Get-organizationconfig</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p108">The  *InPlaceHolds*  property is empty. This indicates that one or more organization-wide or (Exchange-wide) Office 365 retention policy is applied to the inactive mailbox. In this case, you can run the  \`Get-OrganizationConfig</span></span> | <span data-ttu-id="e4e8b-151">Select-object-ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.  <br/><br/> `Get RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="e4e8b-151">Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="e4e8b-152">FL 名称</span><span class="sxs-lookup"><span data-stu-id="e4e8b-152">FL Name\`</span></span><br/><br/>
|<span data-ttu-id="e4e8b-153">康 Olson</span><span class="sxs-lookup"><span data-stu-id="e4e8b-153">Carol Olson</span></span>  <br/> |<span data-ttu-id="e4e8b-154">Office 365 安全中的保留策略&amp;合规性中心于特定邮箱</span><span class="sxs-lookup"><span data-stu-id="e4e8b-154">Office 365 retention policy in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="e4e8b-p109">*InPlaceHolds*属性将包含 Office 365 保留策略应用于非活动邮箱的 GUID。您可以判断这是因为 GUID 开头应用于特定邮箱的保留策略`mbx`前缀。请注意，如果的保留策略应用于非活动邮箱 GUID 入门`skp`，指明的保留策略应用于 Skype 业务对话的前缀。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p109">The  *InPlaceHolds*  property contains the GUID of the Office 365 retention policy that's applied to the inactive mailbox. You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix. Note that if GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, that would indicate that the retention policy is applied to Skype for Business conversations.  </span></span><br/><br/> <span data-ttu-id="e4e8b-158">到标识 Office 365 应用于非活动邮箱的保留策略，运行以下命令在安全&amp;合规性中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-158">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.</span></span><br/><br/> <span data-ttu-id="e4e8b-159">Get RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="e4e8b-159">\`Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="e4e8b-160">FL 名称` <br/><br/>Be sure to remove the  `mbx` or  `skp 前缀当运行此命令。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-160">FL Name` <br/><br/>Be sure to remove the  `mbx` or  `skp\` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="e4e8b-161">当年 McMahon</span><span class="sxs-lookup"><span data-stu-id="e4e8b-161">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="e4e8b-162">在安全保留电子数据展示事例&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="e4e8b-162">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="e4e8b-p110">*InPlaceHolds*属性包含放置在非活动邮箱的电子数据展示案例保留项的 GUID。您可以判断这是电子数据展示案例保留，因为 GUID 开头`UniH`前缀。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p110">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="e4e8b-p111">您可以使用`Get-CaseHoldPolicy`cmdlet 中安全&amp;合规性中心 PowerShell，可以获取关于电子数据展示案例非活动邮箱的保留项关联的信息。例如，可以运行命令 Get CaseHoldPolicy<hold GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="e4e8b-p111">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with. For example, you can run the command  \`Get-CaseHoldPolicy <hold GUID without prefix></span></span> | <span data-ttu-id="e4e8b-167">FL 名称` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.  <br/><br/> `$CaseHold = Get CaseHoldPolicy <hold GUID without prefix> `<br/><br/> `Get ComplianceCase $CaseHold.CaseId</span><span class="sxs-lookup"><span data-stu-id="e4e8b-167">FL Name` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId</span></span> | <span data-ttu-id="e4e8b-168">FL 名称</span><span class="sxs-lookup"><span data-stu-id="e4e8b-168">FL Name\`</span></span><br/><br/><br/> <span data-ttu-id="e4e8b-p112">**注意：** 我们不建议使用电子数据展示保留为非活动邮箱。这是因为电子数据展示事例适用于特定的时间限制的情况下相关法律问题。有时，很可能会法律案件和保留与案例关联将被删除，将电子数据展示事例关闭 （或删除）。实际上，如果放置在非活动邮箱的保留电子数据展示事例，与相关联和释放保留项或关闭电子数据展示事例或将其删除，非活动邮箱将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p112">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted). In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="e4e8b-173">有关 Office 365 保留策略的详细信息，请参阅[Overview of 保留策略](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-173">For more information about Office 365 retention policies, see [Overview of retention policies](retention-policies.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="e4e8b-174">第 2 步：更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="e4e8b-174">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="e4e8b-175">在确定了非活动邮箱上设置的保留的类型（以及是否设置多个保留）后，下一步就要更改保留期了。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-175">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="e4e8b-176">更改诉讼保留的保留期</span><span class="sxs-lookup"><span data-stu-id="e4e8b-176">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="e4e8b-p113">下面是如何使用 Exchange Online PowerShell 中的非活动邮箱置于诉讼保留更改保留持续时间。不能使用 EAC。运行以下命令以更改保留持续时间。本示例中，保留持续时间变为无限期的时间。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p113">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox. You can't use the EAC. Run the following command to change the hold duration. In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="e4e8b-181">结果是无限期或直到保留被删除或保留持续时间更改为不同的值，将保留非活动邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-181">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="e4e8b-p114">标识非活动邮箱的最佳方式是使用**可分辨名称**或 **Exchange GUID** 值。使用下列值之一有助于避免意外指定错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p114">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="e4e8b-184">更改就地保留的保留期</span><span class="sxs-lookup"><span data-stu-id="e4e8b-184">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="e4e8b-185">您可以使用 EAC 或 Exchange Online PowerShell 中，若要更改保留持续时间的就地保留。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-185">You can use the EAC or Exchange Online PowerShell to change the hold duration for an In-Place Hold.</span></span> 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a><span data-ttu-id="e4e8b-186">使用 EAC 更改保留期</span><span class="sxs-lookup"><span data-stu-id="e4e8b-186">Use the EAC to change the hold duration</span></span>

1. <span data-ttu-id="e4e8b-p115">如果您知道您想要更改的就地保留的名称，请转到下一步。否则，运行以下命令以获取非活动邮箱置于就地保留的名称。使用您在[步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获得的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p115">If you know the name of the In-Place Hold that you want to change, go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="e4e8b-190">在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-190">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="e4e8b-191">选择您想要更改，就地保留，然后单击**编辑**![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-191">Select the In-Place Hold you want to change, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="e4e8b-192">编辑图标</span><span class="sxs-lookup"><span data-stu-id="e4e8b-192">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**.</span></span> 
    
5. <span data-ttu-id="e4e8b-193">。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-193">Do one of the following based on the current hold duration:</span></span>
    
1. <span data-ttu-id="e4e8b-194">在"就地电子数据展示和保留"属性页上，单击"就地保留"。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-194">Click **Hold indefinitely** to hold items for an unlimited period of time.</span></span> 
    
2. <span data-ttu-id="e4e8b-p116">单击要在特定时间保留项目的**指定天数保留项目相对于其接收日期**。键入您想要保留的项目的天数。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p116">Click **Specify number of days to hold items relative to their received date** to hold items for a specific period. Type the number of days that you want to hold items for.</span></span> 
    
    ![单击"指定自接收日期起保留邮件的天数"可以在特定的时间段内保留项目。](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. <span data-ttu-id="e4e8b-198">键入所需的项目保留天数。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-198">Click **Save**.</span></span>
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a><span data-ttu-id="e4e8b-199">使用 Exchange Online PowerShell 中更改保留持续时间</span><span class="sxs-lookup"><span data-stu-id="e4e8b-199">Use Exchange Online PowerShell to change the hold duration</span></span>

1. <span data-ttu-id="e4e8b-p117">如果您知道您想要更改的就地保留的名称，请转到下一步。否则，运行以下命令以获取非活动邮箱置于就地保留的名称。使用您在[步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获得的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p117">If you know the name of the In-Place Hold that you want to change, go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="e4e8b-p118">运行以下命令，更改保留期。在此示例中，更改后的保留期为 2,555 天（大约 7 年）。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p118">Run the following command to change the hold duration. In this example, the hold duration is changed to 2,555 days (approximately 7 years).</span></span> 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     <span data-ttu-id="e4e8b-205">运行以下命令，更改保留期。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-205">To change the hold duration to an unlimited period of time, use  _-ItemHoldPeriod unlimited_.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="e4e8b-206">详细信息</span><span class="sxs-lookup"><span data-stu-id="e4e8b-206">More information</span></span>

- <span data-ttu-id="e4e8b-p119">**如何计算非活动邮箱中项目的保留期？** 保留期从邮箱项目的接收或创建原始日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p119">**How is the hold duration calculated for an item in an inactive mailbox?** The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="e4e8b-p120">**保留持续时间过期时，会发生什么情况？** 保留持续时间过后可恢复邮件文件夹中的邮箱项，该项被永久删除 （清除） 从非活动邮箱。如果没有为非活动邮箱置于保留指定的持续时间，可恢复邮件文件夹中的项目永远不会被清除 （除非已更改为非活动邮箱的保留持续时间）。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p120">**What happens when the hold duration expires?** When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox. If there is no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="e4e8b-p121">**是仍在非活动邮箱上处理 Exchange 保留策略？** 如果 （邮件传递记录管理或 MRM，Exchange Online 中的功能） 的 Exchange 保留策略应用于邮箱已处于非活动状态时，将删除策略 （即配置**删除**保留操作的保留标记）继续在非活动邮箱上进行处理。这意味着用删除策略标记的项目移动到可恢复邮件文件夹保留期到期时。为某个项目的保留持续时间过期时，这些项目然后会清除从非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p121">**Is an Exchange retention policy still processed on inactive mailboxes?** If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox. That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires. Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="e4e8b-p122">相反，分配给非活动邮箱的保留策略中包含的所有存档策略（配置了 **MoveToArchive** 保留操作的保留标记）会遭到忽略。也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。这些项目不会移到存档邮箱或其中的“可恢复的项目”文件夹内。由于用户无法登录非活动邮箱，因此没有理由消耗数据中心资源来处理存档策略。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p122">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored. That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires. They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox. Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 
    
- <span data-ttu-id="e4e8b-p123">**若要检查新保留持续时间，请运行以下命令之一。** 第一个命令是诉讼保留;第二个是就地保留。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p123">**To check the new hold duration, run one of the following commands.** The first command is for Litigation Hold; the second is for In-Place Hold.</span></span> 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- <span data-ttu-id="e4e8b-p124">**像常规邮箱托管文件夹助理 (MFA) 还处理非活动邮箱。** 在 Exchange Online 中，MFA 每 7 天的大约一次处理邮箱。更改非活动邮箱的保留持续时间后，您可以使用**Start-managedfolderassistant** cmdlet 立即开始处理非活动邮箱的新保留持续时间。运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p124">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.** In Exchange Online, the MFA processes mailboxes approximately once every 7 days. After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox. Run the following command.</span></span> 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="e4e8b-p125">**如果大量的保留项被放置在非活动邮箱，并非所有保留项将显示 Guid。** 您可以运行以下命令以显示的所有 （除诉讼保留） 保留放置在非活动邮箱的 Guid。</span><span class="sxs-lookup"><span data-stu-id="e4e8b-p125">**If a lot of holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.** You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```

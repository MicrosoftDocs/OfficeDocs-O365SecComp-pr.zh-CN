---
title: 在 Office 365 中更改非活动邮箱的保留期
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: 在 Office 365 邮箱变为非活动状态后, 可以更改分配给非活动邮箱的保留或 Office 365 保留策略的持续时间。 保留期定义了"可恢复的项目"文件夹中的项目的保留持续时间。
ms.openlocfilehash: 7840131af3df32b8b8e5a0faa1b101f9ec8ef541
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155564"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="acb7c-104">在 Office 365 中更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="acb7c-104">Change the hold duration for an inactive mailbox in Office 365</span></span>

<span data-ttu-id="acb7c-105">非活动邮箱用于在离开组织后保留前一个员工的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="acb7c-105">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="acb7c-106">当诉讼保留、就地保留、Office 365 保留策略或与电子数据展示事例相关联的保留在邮箱中时, 邮箱将变为非活动状态, 并且相应的 Office 365 用户帐户将被删除。</span><span class="sxs-lookup"><span data-stu-id="acb7c-106">A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, an Office 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding Office 365 user account is deleted.</span></span> <span data-ttu-id="acb7c-107">非活动邮箱的内容会在邮箱处于非活动状态之前放置在邮箱保留期间的保留时间内进行保留。</span><span class="sxs-lookup"><span data-stu-id="acb7c-107">The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive.</span></span> <span data-ttu-id="acb7c-108">保留期定义了"可恢复的项目"文件夹中的项目的保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="acb7c-108">The hold duration defines how long items in the Recoverable Items folder are held.</span></span> <span data-ttu-id="acb7c-109">如果"可恢复的项目"文件夹中的项目的保留期过期，则此项目会从非活动邮箱中永久删除（清除）。</span><span class="sxs-lookup"><span data-stu-id="acb7c-109">When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox.</span></span> <span data-ttu-id="acb7c-110">将邮箱设为非活动状态后, 可以更改为非活动邮箱分配的保留或 Office 365 保留策略的持续时间。</span><span class="sxs-lookup"><span data-stu-id="acb7c-110">After a mailbox is made inactive, you can change the duration of the hold or Office 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="acb7c-111">我们推迟了最后期限，在 2017 年 7 月 1 后，仍可通过新建就地保留创建非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="acb7c-111">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive.</span></span> <span data-ttu-id="acb7c-112">But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="acb7c-112">But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="acb7c-113">在这段时间, 仅可使用诉讼保留和 Office 365 保留策略来创建非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="acb7c-113">At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox.</span></span> <span data-ttu-id="acb7c-114">不过，处于就地保留的现有非活动邮箱仍受支持，可以继续管理这些非活动邮箱的就地保留。</span><span class="sxs-lookup"><span data-stu-id="acb7c-114">However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes.</span></span> <span data-ttu-id="acb7c-115">这包括更改就地保留的持续时间，以及通过删除就地保留来永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="acb7c-115">This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="acb7c-116">开始之前</span><span class="sxs-lookup"><span data-stu-id="acb7c-116">Before you begin</span></span>

- <span data-ttu-id="acb7c-117">您必须使用 Exchange Online PowerShell 更改非活动邮箱上的诉讼保留的保留期。</span><span class="sxs-lookup"><span data-stu-id="acb7c-117">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox.</span></span> <span data-ttu-id="acb7c-118">不能使用 Exchange 管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="acb7c-118">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="acb7c-119">但您可以使用 Exchange Online PowerShell 或 EAC 更改就地保留的保留期。</span><span class="sxs-lookup"><span data-stu-id="acb7c-119">But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold.</span></span> <span data-ttu-id="acb7c-120">您可以使用安全与合规中心或 Security & 合规性中心 PowerShell 更改 Office 365 保留策略的保留期。</span><span class="sxs-lookup"><span data-stu-id="acb7c-120">You can use the security and compliance center or the Security & Compliance Center PowerShell to change the hold duration for an Office 365 retention policy.</span></span>
    
- <span data-ttu-id="acb7c-121">若要连接到 Exchange Online PowerShell 或 Security & 合规中心 PowerShell, 请参阅下列主题之一:</span><span class="sxs-lookup"><span data-stu-id="acb7c-121">To connect to Exchange Online PowerShell or Security & Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="acb7c-122">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="acb7c-122">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [<span data-ttu-id="acb7c-123">连接到 Office 365 Security& 合规性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="acb7c-123">Connect to Office 365 Security& Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
- <span data-ttu-id="acb7c-124">请注意, 与电子数据展示事例关联的保留是无限的, 这意味着没有可更改的保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="acb7c-124">Note that holds associated with eDiscovery cases are infinite holds, which means there is no hold duration that can be changed.</span></span> <span data-ttu-id="acb7c-125">项目永久保留, 或者在删除保留和删除非活动邮箱之前进行。</span><span class="sxs-lookup"><span data-stu-id="acb7c-125">Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="acb7c-126">有关非活动邮箱的详细信息, 请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="acb7c-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="acb7c-127">第 1 步：识别非活动邮箱上设置的保留</span><span class="sxs-lookup"><span data-stu-id="acb7c-127">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="acb7c-128">由于不同类型的保留或一个或多个 Office 365 保留策略可能放置在非活动邮箱上, 因此第一步是标识非活动邮箱上的保留。</span><span class="sxs-lookup"><span data-stu-id="acb7c-128">Because different types of holds or one or more Office 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="acb7c-129">在 Exchange Online PowerShell 中运行以下命令, 以显示组织中所有非活动邮箱的保留信息。</span><span class="sxs-lookup"><span data-stu-id="acb7c-129">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
<span data-ttu-id="acb7c-130">如果 **LitigationHoldEnabled** 属性的值为 **True** ，则表示非活动邮箱被置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="acb7c-130">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="acb7c-131">如果非活动邮箱上设置了就地保留、电子数据展示保留或 Office 365 保留策略, 则保留或保留策略的 GUID 将显示为**InPlaceHolds**属性的值。</span><span class="sxs-lookup"><span data-stu-id="acb7c-131">If an In-Place Hold, eDiscovery hold, or Office 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="acb7c-132">例如, 以下显示5个非活动邮箱的结果。</span><span class="sxs-lookup"><span data-stu-id="acb7c-132">For example, the following shows results for 5 inactive mailboxes.</span></span> 
  
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
   
<span data-ttu-id="acb7c-133">下表列出了用于将每个邮箱设为非活动状态的五种不同的保留类型。</span><span class="sxs-lookup"><span data-stu-id="acb7c-133">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="acb7c-134">**非活动邮箱**</span><span class="sxs-lookup"><span data-stu-id="acb7c-134">**Inactive mailbox**</span></span>|<span data-ttu-id="acb7c-135">**保留类型**</span><span class="sxs-lookup"><span data-stu-id="acb7c-135">**Hold type**</span></span>|<span data-ttu-id="acb7c-136">**如何标识非活动邮箱上的保留**</span><span class="sxs-lookup"><span data-stu-id="acb7c-136">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="acb7c-137">王小姐 Beebe</span><span class="sxs-lookup"><span data-stu-id="acb7c-137">Ann Beebe</span></span>  <br/> |<span data-ttu-id="acb7c-138">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="acb7c-138">Litigation Hold</span></span>  <br/> |<span data-ttu-id="acb7c-139">*LitigationHoldEnabled*属性设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="acb7c-139">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="acb7c-140">Pilar Pinilla</span><span class="sxs-lookup"><span data-stu-id="acb7c-140">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="acb7c-141">就地保留</span><span class="sxs-lookup"><span data-stu-id="acb7c-141">In-Place Hold</span></span>  <br/> |<span data-ttu-id="acb7c-142">*InPlaceHolds*属性包含非活动邮箱上设置的就地保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="acb7c-142">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="acb7c-143">您可以指示这是就地保留, 因为 ID 不以前缀开头。</span><span class="sxs-lookup"><span data-stu-id="acb7c-143">You can tell this is an In-Place Hold because the ID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="acb7c-144">您可以使用 Exchange `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Online PowerShell 中的命令来获取非活动邮箱的就地保留的相关信息。</span><span class="sxs-lookup"><span data-stu-id="acb7c-144">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="acb7c-145">Mario Necaise</span><span class="sxs-lookup"><span data-stu-id="acb7c-145">Mario Necaise</span></span>  <br/> |<span data-ttu-id="acb7c-146">Security & 合规中心中的组织范围内的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="acb7c-146">Organization-wide Office 365 retention policy in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="acb7c-147">*InPlaceHolds*属性为空。</span><span class="sxs-lookup"><span data-stu-id="acb7c-147">The  *InPlaceHolds*  property is empty.</span></span> <span data-ttu-id="acb7c-148">这表示一个或多个组织范围或 (Exchange wide) Office 365 保留策略应用于非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="acb7c-148">This indicates that one or more organization-wide or (Exchange-wide) Office 365 retention policy is applied to the inactive mailbox.</span></span> <span data-ttu-id="acb7c-149">在这种情况下, 您可以`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`在 Exchange Online PowerShell 中运行命令, 以获取组织范围内的 Office 365 保留策略的 guid 列表。</span><span class="sxs-lookup"><span data-stu-id="acb7c-149">In this case, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies.</span></span> <span data-ttu-id="acb7c-150">应用于 Exchange 邮箱的组织范围的保留策略的 GUID 以`mbx`前缀开头;例如`mbxa3056bb15562480fadb46ce523ff7b02`。</span><span class="sxs-lookup"><span data-stu-id="acb7c-150">The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <br/><span data-ttu-id="acb7c-151">若要标识应用于非活动邮箱的 Office 365 保留策略, 请在 Security & 合规性中心 PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="acb7c-151">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span>  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|<span data-ttu-id="acb7c-152">Carol Olson</span><span class="sxs-lookup"><span data-stu-id="acb7c-152">Carol Olson</span></span>  <br/> |<span data-ttu-id="acb7c-153">在应用于特定邮箱的 Security & 合规性中心中的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="acb7c-153">Office 365 retention policy in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="acb7c-154">*InPlaceHolds*属性包含应用于非活动邮箱的 Office 365 保留策略的 GUID。</span><span class="sxs-lookup"><span data-stu-id="acb7c-154">The  *InPlaceHolds*  property contains the GUID of the Office 365 retention policy that's applied to the inactive mailbox.</span></span> <span data-ttu-id="acb7c-155">您可以告诉这是应用于特定邮箱的保留策略, 因为 GUID 以`mbx`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="acb7c-155">You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="acb7c-156">请注意, 如果应用于非活动邮箱的保留策略的 GUID 是使用`skp`前缀启动的, 则表示该保留策略应用于 Skype for business 会话。</span><span class="sxs-lookup"><span data-stu-id="acb7c-156">Note that if GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, that would indicate that the retention policy is applied to Skype for Business conversations.</span></span>  <br/><br/> <span data-ttu-id="acb7c-157">若要标识应用于非活动邮箱的 Office 365 保留策略, 请在 Security & 合规性中心 PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="acb7c-157">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security & Compliance Center PowerShell.</span></span><br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/><span data-ttu-id="acb7c-158">运行此命令时, `mbx`请`skp`务必删除或前缀。</span><span class="sxs-lookup"><span data-stu-id="acb7c-158">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="acb7c-159">Abraham McMahon</span><span class="sxs-lookup"><span data-stu-id="acb7c-159">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="acb7c-160">安全 & 合规中心中的电子数据展示案例保留</span><span class="sxs-lookup"><span data-stu-id="acb7c-160">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="acb7c-161">*InPlaceHolds*属性包含非活动邮箱上所放置的电子数据展示事例保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="acb7c-161">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox.</span></span> <span data-ttu-id="acb7c-162">你可以告诉这是电子数据展示事例保留, 因为 GUID 以`UniH`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="acb7c-162">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="acb7c-163">您可以使用 Security `Get-CaseHoldPolicy` _AMP_ 合规性中心 PowerShell 中的 cmdlet 来获取有关非活动邮箱上保留的电子数据展示事例的相关信息。</span><span class="sxs-lookup"><span data-stu-id="acb7c-163">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with.</span></span> <span data-ttu-id="acb7c-164">例如, 您可以运行命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`以显示非活动邮箱上的事例保留的名称。</span><span class="sxs-lookup"><span data-stu-id="acb7c-164">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox.</span></span> <span data-ttu-id="acb7c-165">运行此命令时, `UniH`请务必删除前缀。</span><span class="sxs-lookup"><span data-stu-id="acb7c-165">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="acb7c-166">若要标识非活动邮箱上的保留的电子数据展示事例与关联, 请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="acb7c-166">To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.</span></span>  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> <span data-ttu-id="acb7c-167">**注意:** 建议不要对非活动邮箱使用电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="acb7c-167">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes.</span></span> <span data-ttu-id="acb7c-168">这是因为电子数据展示事例适用于与法律问题相关的特定的与时间绑定的情况。</span><span class="sxs-lookup"><span data-stu-id="acb7c-168">That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue.</span></span> <span data-ttu-id="acb7c-169">有时, 法律案例可能会结束, 与事例关联的保留将被删除, 并且电子数据展示事例将关闭 (或删除)。</span><span class="sxs-lookup"><span data-stu-id="acb7c-169">At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted).</span></span> <span data-ttu-id="acb7c-170">实际上, 如果在非活动邮箱上设置的保留与电子数据展示事例相关联, 并且已释放保留或电子数据展示事例关闭或删除, 则非活动邮箱将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="acb7c-170">In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="acb7c-171">有关 Office 365 保留策略的详细信息, 请参阅[保留策略概述](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="acb7c-171">For more information about Office 365 retention policies, see [Overview of retention policies](retention-policies.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="acb7c-172">第 2 步：更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="acb7c-172">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="acb7c-173">在确定了非活动邮箱上设置的保留的类型（以及是否设置多个保留）后，下一步就要更改保留期了。</span><span class="sxs-lookup"><span data-stu-id="acb7c-173">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="acb7c-174">更改诉讼保留的保留期</span><span class="sxs-lookup"><span data-stu-id="acb7c-174">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="acb7c-175">下面介绍了如何使用 Exchange Online PowerShell 更改非活动邮箱上的诉讼保留的保留期。</span><span class="sxs-lookup"><span data-stu-id="acb7c-175">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox.</span></span> <span data-ttu-id="acb7c-176">不能使用 EAC。</span><span class="sxs-lookup"><span data-stu-id="acb7c-176">You can't use the EAC.</span></span> <span data-ttu-id="acb7c-177">运行以下命令，更改保留期。</span><span class="sxs-lookup"><span data-stu-id="acb7c-177">Run the following command to change the hold duration.</span></span> <span data-ttu-id="acb7c-178">在此示例中，可将保留期更改为无限期。</span><span class="sxs-lookup"><span data-stu-id="acb7c-178">In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="acb7c-179">结果是非活动邮箱中的项目会无限期保留, 或者直到删除保留或保留持续时间更改为其他值。</span><span class="sxs-lookup"><span data-stu-id="acb7c-179">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="acb7c-p114">标识非活动邮箱的最佳方式是使用 **Distinguished Name** 或 **Exchange GUID** 值。 使用下列值之一有助于避免意外指定错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="acb7c-p114">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="acb7c-182">更改就地保留的保留期</span><span class="sxs-lookup"><span data-stu-id="acb7c-182">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="acb7c-183">您可以使用 EAC 或 Exchange Online PowerShell 更改就地保留的保留期。</span><span class="sxs-lookup"><span data-stu-id="acb7c-183">You can use the EAC or Exchange Online PowerShell to change the hold duration for an In-Place Hold.</span></span> 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a><span data-ttu-id="acb7c-184">使用 EAC 更改保留期</span><span class="sxs-lookup"><span data-stu-id="acb7c-184">Use the EAC to change the hold duration</span></span>

1. <span data-ttu-id="acb7c-185">如果您知道要更改的就地保留的名称，请转到下一步。</span><span class="sxs-lookup"><span data-stu-id="acb7c-185">If you know the name of the In-Place Hold that you want to change, go to the next step.</span></span> <span data-ttu-id="acb7c-186">如果不知道，请运行以下命令，获取非活动邮箱上设置的就地保留的名称。</span><span class="sxs-lookup"><span data-stu-id="acb7c-186">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox.</span></span> <span data-ttu-id="acb7c-187">使用您在[步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获取的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="acb7c-187">Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="acb7c-188">在 EAC 中，转到"合规管理"\*\*\*\*"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="acb7c-188">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="acb7c-189">选择要更改的就地保留, 然后单击 "**编辑** ![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)"。</span><span class="sxs-lookup"><span data-stu-id="acb7c-189">Select the In-Place Hold you want to change, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="acb7c-190">编辑图标</span><span class="sxs-lookup"><span data-stu-id="acb7c-190">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**.</span></span> 
    
5. <span data-ttu-id="acb7c-191">。</span><span class="sxs-lookup"><span data-stu-id="acb7c-191">Do one of the following based on the current hold duration:</span></span>
    
1. <span data-ttu-id="acb7c-192">在"就地电子数据展示和保留"属性页上，单击"就地保留"。</span><span class="sxs-lookup"><span data-stu-id="acb7c-192">Click **Hold indefinitely** to hold items for an unlimited period of time.</span></span> 
    
2. <span data-ttu-id="acb7c-193">单击 "**指定天数" 以相对于其接收日期保留项目**, 以保留特定时段内的项目。</span><span class="sxs-lookup"><span data-stu-id="acb7c-193">Click **Specify number of days to hold items relative to their received date** to hold items for a specific period.</span></span> <span data-ttu-id="acb7c-194">键入所需的项目保留天数。</span><span class="sxs-lookup"><span data-stu-id="acb7c-194">Type the number of days that you want to hold items for.</span></span> 
    
    ![单击"指定自接收日期起保留邮件的天数"可以在特定的时间段内保留项目。](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. <span data-ttu-id="acb7c-196">键入所需的项目保留天数。</span><span class="sxs-lookup"><span data-stu-id="acb7c-196">Click **Save**.</span></span>
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a><span data-ttu-id="acb7c-197">使用 Exchange Online PowerShell 更改保留期</span><span class="sxs-lookup"><span data-stu-id="acb7c-197">Use Exchange Online PowerShell to change the hold duration</span></span>

1. <span data-ttu-id="acb7c-198">如果您知道要更改的就地保留的名称，请转到下一步。</span><span class="sxs-lookup"><span data-stu-id="acb7c-198">If you know the name of the In-Place Hold that you want to change, go to the next step.</span></span> <span data-ttu-id="acb7c-199">如果不知道，请运行以下命令，获取非活动邮箱上设置的就地保留的名称。</span><span class="sxs-lookup"><span data-stu-id="acb7c-199">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox.</span></span> <span data-ttu-id="acb7c-200">使用您在[步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获取的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="acb7c-200">Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="acb7c-p118">使用您在第 1 步：识别非活动邮箱上设置的保留中获得的就地保留 GUID。 运行以下命令，更改保留期。在此示例中，更改后的保留期为 2,555 天（大约 7 年）。</span><span class="sxs-lookup"><span data-stu-id="acb7c-p118">Run the following command to change the hold duration. In this example, the hold duration is changed to 2,555 days (approximately 7 years).</span></span> 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     <span data-ttu-id="acb7c-203">运行以下命令，更改保留期。</span><span class="sxs-lookup"><span data-stu-id="acb7c-203">To change the hold duration to an unlimited period of time, use  _-ItemHoldPeriod unlimited_.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="acb7c-204">详细信息</span><span class="sxs-lookup"><span data-stu-id="acb7c-204">More information</span></span>

- <span data-ttu-id="acb7c-p119">\*\* \*\* 如何计算非活动邮箱中项目的保留期？保留期从邮箱项目的接收或创建原始日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="acb7c-p119">**How is the hold duration calculated for an item in an inactive mailbox?** The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="acb7c-p120">保留期从邮箱项目的接收或创建原始日期开始计算。 当保留期过期时，会怎么样？当"可恢复的项目"文件夹中邮箱项目的保留期过期时，系统会将此项目从非活动邮箱中永久删除（清除）。如果非活动邮箱上设置的保留没有指定的保留期，则"可恢复的项目"文件夹中的项目永远都不会清除（除非您更改非活动邮箱的保留期）。 当保留期过期时，会怎么样？</span><span class="sxs-lookup"><span data-stu-id="acb7c-p120">**What happens when the hold duration expires?** When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox. If there is no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="acb7c-210">**是否仍在非活动邮箱上处理 Exchange 保留策略？**</span><span class="sxs-lookup"><span data-stu-id="acb7c-210">**Is an Exchange retention policy still processed on inactive mailboxes?**</span></span> <span data-ttu-id="acb7c-211">如果将 Exchange 保留策略 (Exchange Online 中的邮件记录管理或 MRM) 应用于邮箱 (如果某个邮箱处于非活动状态), 则删除策略 (是使用**删除**保留操作配置的保留标记) 将继续在非活动邮箱上进行处理。</span><span class="sxs-lookup"><span data-stu-id="acb7c-211">If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox.</span></span> <span data-ttu-id="acb7c-212">也就是说，在保留期过期时，标记有删除策略的项目会移到“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="acb7c-212">That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires.</span></span> <span data-ttu-id="acb7c-213">当项目的保留期过期时，这些项目会从非活动邮箱中清除。</span><span class="sxs-lookup"><span data-stu-id="acb7c-213">Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="acb7c-p122">当项目的保留期过期时，这些项目会从非活动邮箱中清除。 相反，分配给非活动邮箱的保留策略中包含的所有存档策略（配置了 MoveToArchive 保留操作的保留标记）会遭到忽略。也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。这些项目不会移到存档邮箱或其中的"可恢复的项目"文件夹内。由于用户无法登录非活动邮箱，因此没有理由消耗数据中心资源来处理存档策略。 相反，分配给非活动邮箱的保留策略中包含的所有存档策略（配置了 MoveToArchive 保留操作的保留标记）会遭到忽略。 也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="acb7c-p122">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored. That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires. They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox. Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 
    
- <span data-ttu-id="acb7c-218">由于用户无法登录非活动邮箱，因此没有理由消耗数据中心资源来处理存档策略。</span><span class="sxs-lookup"><span data-stu-id="acb7c-218">**To check the new hold duration, run one of the following commands.**</span></span> <span data-ttu-id="acb7c-219">第一个命令适用于诉讼保留;第二个用于就地保留。</span><span class="sxs-lookup"><span data-stu-id="acb7c-219">The first command is for Litigation Hold; the second is for In-Place Hold.</span></span> 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- <span data-ttu-id="acb7c-p124">**托管文件夹助理 (MFA) 还会处理非活动邮箱，就像处理常规邮箱一样。** 在 Exchange Online 中，MFA 大约每 7 天处理一次邮箱。 更改非活动邮箱的保留期后，您可以使用 **Start-ManagedFolderAssistant** cmdlet 立即开始处理非活动邮箱的新保留期。 运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="acb7c-p124">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.** In Exchange Online, the MFA processes mailboxes approximately once every 7 days. After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox. Run the following command.</span></span> 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="acb7c-224">**如果非活动邮箱上放置了很多保留项, 则不会显示所有保留 Guid。**</span><span class="sxs-lookup"><span data-stu-id="acb7c-224">**If a lot of holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.**</span></span> <span data-ttu-id="acb7c-225">您可以运行以下命令来显示非活动邮箱上的所有保留项 (诉讼保留除外) 的 Guid。</span><span class="sxs-lookup"><span data-stu-id="acb7c-225">You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```

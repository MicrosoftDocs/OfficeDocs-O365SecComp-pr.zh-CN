---
title: 如何识别为 Exchange Online 邮箱设置的保留类型
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: 了解如何识别可在 Office 365 邮箱中放置的不同类型的保留。 这些保留类型包括诉讼保留、电子数据展示保留和 Office 365 保留策略。 您还可以确定是否已从组织范围的保留策略中排除了用户
ms.openlocfilehash: 47e7ffff1703c0de94f014dc18e249cc9775e3e2
ms.sourcegitcommit: 873c5bc0e6cd1ca3dfdb3a99a5371353b419311f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "36493153"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a><span data-ttu-id="5b13e-105">如何识别为 Exchange Online 邮箱设置的保留类型</span><span class="sxs-lookup"><span data-stu-id="5b13e-105">How to identify the type of hold placed on an Exchange Online mailbox</span></span>

<span data-ttu-id="5b13e-106">本文介绍如何确定在 Office 365 的 Exchange Online 邮箱中放置的保留。</span><span class="sxs-lookup"><span data-stu-id="5b13e-106">This article explains how to identify holds placed on Exchange Online mailboxes in Office 365.</span></span>

<span data-ttu-id="5b13e-107">Office 365 提供了多种方法, 使您的组织可以阻止邮箱内容被永久删除。</span><span class="sxs-lookup"><span data-stu-id="5b13e-107">Office 365 offers several ways that your organization can prevent mailbox content from being permanently deleted.</span></span> <span data-ttu-id="5b13e-108">这使您的组织可以保留内容以满足合规性管理法规或在法律和其他类型的调查过程中。</span><span class="sxs-lookup"><span data-stu-id="5b13e-108">This allows your organization to retain content to meet compliance regulations or during legal and other types of investigations.</span></span> <span data-ttu-id="5b13e-109">下面列出了 Office 365 中的保留功能 (也称为 "*保留*"):</span><span class="sxs-lookup"><span data-stu-id="5b13e-109">Here's a list of the retention features (also called *holds*) in Office 365:</span></span>

- <span data-ttu-id="5b13e-110">**[诉讼保留](create-a-litigation-hold.md):** 应用于 Exchange Online 中的用户邮箱的保留。</span><span class="sxs-lookup"><span data-stu-id="5b13e-110">**[Litigation Hold](create-a-litigation-hold.md):** Holds that are applied to user mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="5b13e-111">**[电子数据展示保留](ediscovery-cases.md#step-4-place-content-locations-on-hold):** 与安全与合规中心中的电子数据展示事例相关联的保留项。</span><span class="sxs-lookup"><span data-stu-id="5b13e-111">**[eDiscovery hold](ediscovery-cases.md#step-4-place-content-locations-on-hold):** Holds that are associated with an eDiscovery case in the security and compliance center.</span></span> <span data-ttu-id="5b13e-112">电子数据展示保留可应用于用户邮箱以及 Office 365 组和 Microsoft 团队对应的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b13e-112">eDiscovery holds can be applied to user mailboxes and to the corresponding mailbox for Office 365 Groups and Microsoft Teams.</span></span>

- <span data-ttu-id="5b13e-113">**[就地保留](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds):** 使用 exchange Online 中 Exchange 管理中心的就地电子数据展示 & 保留工具对用户邮箱应用的保留。</span><span class="sxs-lookup"><span data-stu-id="5b13e-113">**[In-Place Hold](https://docs.microsoft.com/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Holds that are applied to user mailboxes by using the In-Place eDiscovery & Hold tool in the Exchange admin center in Exchange Online.</span></span>

- <span data-ttu-id="5b13e-114">\*\* [Office 365 保留策略](retention-policies.md):\*\* 可以配置为保留 (或保留并删除) Exchange Online 中的用户邮箱中的内容, 以及 Office 365 组和 Microsoft 团队对应的邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="5b13e-114">**[Office 365 retention policies](retention-policies.md):** Can be configured to retain (or retain and then delete) content in user mailboxes in Exchange Online and in the corresponding mailbox for Office 365 Groups and Microsoft Teams.</span></span> <span data-ttu-id="5b13e-115">您还可以创建保留策略以保留 Skype for Business 对话, 这些会话存储在用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5b13e-115">You can also create a retention policy to retain Skype for Business Conversations, which are stored in user mailboxes.</span></span>

  <span data-ttu-id="5b13e-116">有两种类型的 Office 365 保留策略可分配给邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b13e-116">There are two types of Office 365 retention policies that can be assigned to mailboxes.</span></span>

    - <span data-ttu-id="5b13e-117">**特定位置保留策略:** 这些是分配给特定用户的内容位置的策略。</span><span class="sxs-lookup"><span data-stu-id="5b13e-117">**Specific location retention policies:** These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="5b13e-118">您可以使用 Exchange Online PowerShell 中的**邮箱获取**cmdlet 获取有关分配给特定邮箱的保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="5b13e-118">You use the **Get-Mailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific mailboxes.</span></span>

    - <span data-ttu-id="5b13e-119">**组织范围内的保留策略:** 这些是分配给组织中的所有内容位置的策略。</span><span class="sxs-lookup"><span data-stu-id="5b13e-119">**Organization-wide retention policies:** These are policies that are assigned to all content locations in your organization.</span></span> <span data-ttu-id="5b13e-120">您可以使用 Exchange Online PowerShell 中的**set-organizationconfig** cmdlet 来获取有关组织范围的保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="5b13e-120">You use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>
  <span data-ttu-id="5b13e-121">有关详细信息, 请参阅[Office 365 保留策略概述](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)中的 "将保留策略应用于整个组织或特定位置" 部分。</span><span class="sxs-lookup"><span data-stu-id="5b13e-121">For more information, see the "Applying a retention policy to an entire organization or specific locations" section in [Overview of Office 365 retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

- <span data-ttu-id="5b13e-122">**[Office 365 保留标签](labels.md):** 如果用户应用 Office 365 保留标签 (配置为保留内容或保留内容, 然后将内容删除) 到其邮箱中的*任何*文件夹或项目中, 则邮箱上的保留将放置在邮箱中, 就像邮箱是置于诉讼保留或分配到 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="5b13e-122">**[Office 365 retention labels](labels.md):** If a user applies an Office 365 retention label (one that's configured to retain content or retain and then delete content) to *any* folder or item in their mailbox, a hold is placed on the mailbox as if the mailbox was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span> <span data-ttu-id="5b13e-123">有关详细信息, 请参阅[保留邮箱处于保留状态, 因为已将保留标签应用于本文中的文件夹或项目](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)部分。</span><span class="sxs-lookup"><span data-stu-id="5b13e-123">For more information, see the [Identifying mailboxes on hold because a retention label has been applied to a folder or item](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) section in this article.</span></span>

<span data-ttu-id="5b13e-124">若要管理处于保留状态的邮箱, 您可能需要确定邮箱中放置的保留类型, 以便可以执行诸如更改保留持续时间、临时或永久删除保留或从 Office 365 保留策略中排除邮箱等任务。</span><span class="sxs-lookup"><span data-stu-id="5b13e-124">To manage mailboxes on hold, you may have to identify the type of hold that's placed on a mailbox so that you can perform tasks such as changing the hold duration, temporarily or permanently removing the hold, or excluding a mailbox from an Office 365 retention policy.</span></span> <span data-ttu-id="5b13e-125">在这些情况下, 第一步是确定邮箱上放置的保留类型。</span><span class="sxs-lookup"><span data-stu-id="5b13e-125">In these cases, the first step is to identify the type of hold placed on the mailbox.</span></span> <span data-ttu-id="5b13e-126">由于多个保留 (和不同类型的保留) 可以放置在单个邮箱上, 因此, 如果您想要删除或更改保留, 则必须标识邮箱中的所有保留项。</span><span class="sxs-lookup"><span data-stu-id="5b13e-126">And because multiple holds (and different types of holds) can be placed on a single mailbox, you have to identify all holds placed on a mailbox if you want to remove or change a hold.</span></span>

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a><span data-ttu-id="5b13e-127">步骤 1: 获取邮箱上放置的保留的 GUID</span><span class="sxs-lookup"><span data-stu-id="5b13e-127">Step 1: Obtain the GUID for holds placed on a mailbox</span></span>

<span data-ttu-id="5b13e-128">您可以在 Exchange Online PowerShell 中运行以下两个 cmdlet, 以获取邮箱中放置的保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5b13e-128">You can run the following two cmdlets in Exchange Online PowerShell to get the GUID of the holds that are placed on a mailbox.</span></span> <span data-ttu-id="5b13e-129">获取 GUID 后, 可以使用它来标识步骤2中的特定保留。</span><span class="sxs-lookup"><span data-stu-id="5b13e-129">After you obtain a GUID, you use it to identify the specific hold in Step 2.</span></span> <span data-ttu-id="5b13e-130">GUID 未标识诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="5b13e-130">A Litigation Hold isn't identified by a GUID.</span></span> <span data-ttu-id="5b13e-131">为邮箱启用或禁用诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="5b13e-131">Litigation Holds are either enabled or disabled for a mailbox.</span></span>

- <span data-ttu-id="5b13e-132">**获取邮箱:** 此 cmdlet 可用于确定是否对邮箱启用了诉讼保留, 并获取专门分配给邮箱的电子数据展示保留、就地保留和 Office 365 保留策略的 Guid。</span><span class="sxs-lookup"><span data-stu-id="5b13e-132">**Get-Mailbox:** Use this cmdlet to determine whether Litigation Hold is enabled for a mailbox and to get the GUIDs for eDiscovery holds, In-Place Holds, and Office 365 retention policies that are specifically assigned to a mailbox.</span></span> <span data-ttu-id="5b13e-133">此 cmdlet 的输出还将指示是否已从组织范围的保留策略中显式排除了邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b13e-133">The output of this cmdlet will also indicate if a mailbox has been explicitly excluded from an organization-wide retention policy.</span></span>

- <span data-ttu-id="5b13e-134">**Set-organizationconfig:** 此 cmdlet 可用于获取组织范围的保留策略的 Guid。</span><span class="sxs-lookup"><span data-stu-id="5b13e-134">**Get-OrganizationConfig:** Use this cmdlet to get the GUIDs for organization-wide retention policies.</span></span>

<span data-ttu-id="5b13e-135">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="5b13e-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

### <a name="get-mailbox"></a><span data-ttu-id="5b13e-136">Get-Mailbox</span><span class="sxs-lookup"><span data-stu-id="5b13e-136">Get-Mailbox</span></span>

<span data-ttu-id="5b13e-137">运行以下命令以获取有关保留和 Office 365 保留策略应用于邮箱的信息。</span><span class="sxs-lookup"><span data-stu-id="5b13e-137">Run the following command to get information about the holds and Office 365 retention policies applied to a mailbox.</span></span>

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="5b13e-138">如果 InPlaceHolds 属性中的值过多, 并且不是全部显示, 则可以运行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令将每个 GUID 显示在单独的行上。</span><span class="sxs-lookup"><span data-stu-id="5b13e-138">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="5b13e-139">下表介绍在运行 InPlaceHolds cmdlet 时, 如何根据\*\* 属性中的值标识不同类型的保留。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5b13e-139">The following table describes how to identify different types of holds based on the values in the *InPlaceHolds* property when you run the **Get-Mailbox** cmdlet.</span></span>


|<span data-ttu-id="5b13e-140">保留类型</span><span class="sxs-lookup"><span data-stu-id="5b13e-140">Hold type</span></span>  |<span data-ttu-id="5b13e-141">示例值</span><span class="sxs-lookup"><span data-stu-id="5b13e-141">Example value</span></span>  |<span data-ttu-id="5b13e-142">如何识别保留</span><span class="sxs-lookup"><span data-stu-id="5b13e-142">How to identify the hold</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="5b13e-143">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="5b13e-143">Litigation Hold</span></span>     |    `True`     |     <span data-ttu-id="5b13e-144">当*LitigationHoldEnabled*属性设置为`True`时, 将对邮箱启用诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="5b13e-144">Litigation Hold is enabled for a mailbox when the *LitigationHoldEnabled* property is set to `True`.</span></span>    |
|<span data-ttu-id="5b13e-145">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="5b13e-145">eDiscovery hold</span></span>     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   <span data-ttu-id="5b13e-146">*InPlaceHolds 属性*包含与安全与合规中心中的电子数据展示事例关联的任何保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5b13e-146">The *InPlaceHolds property* contains the GUID of any hold associated with an eDiscovery case in the security and compliance center.</span></span> <span data-ttu-id="5b13e-147">你可以告诉这是电子数据展示保留, 因为 GUID 以`UniH`前缀 (表示统一保留) 开头。</span><span class="sxs-lookup"><span data-stu-id="5b13e-147">You can tell this is an eDiscovery hold because the GUID starts with the `UniH` prefix (which denotes a Unified Hold).</span></span>      |
|<span data-ttu-id="5b13e-148">就地保留</span><span class="sxs-lookup"><span data-stu-id="5b13e-148">In-Place Hold</span></span>     |     `c0ba3ce811b6432a8751430937152491` <br/> <span data-ttu-id="5b13e-149">或</span><span class="sxs-lookup"><span data-stu-id="5b13e-149">or</span></span> <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     <span data-ttu-id="5b13e-150">*InPlaceHolds*属性包含邮箱中放置的就地保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5b13e-150">The *InPlaceHolds* property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="5b13e-151">您可以指示这是就地保留, 因为 GUID 既不以前缀开头, 也不以`cld`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="5b13e-151">You can tell this is an In-Place Hold because the GUID either doesn't start with a prefix or it starts with the `cld` prefix.</span></span>     |
|<span data-ttu-id="5b13e-152">专用于邮箱的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="5b13e-152">Office 365 retention policy specifically applied to the mailbox</span></span>     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> <span data-ttu-id="5b13e-153">或</span><span class="sxs-lookup"><span data-stu-id="5b13e-153">or</span></span> <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     <span data-ttu-id="5b13e-154">InPlaceHolds 属性包含应用于邮箱的任何特定位置保留策略的 Guid。</span><span class="sxs-lookup"><span data-stu-id="5b13e-154">The InPlaceHolds property contains GUIDs of any specific location retention policy that's applied to the mailbox.</span></span> <span data-ttu-id="5b13e-155">您可以确定保留策略, 因为 GUID 以`mbx`或`skp`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="5b13e-155">You can identify retention policies because the GUID starts with the `mbx` or the `skp` prefix.</span></span> <span data-ttu-id="5b13e-156">`skp`前缀指示将保留策略应用于用户邮箱中的 Skype for business 会话。</span><span class="sxs-lookup"><span data-stu-id="5b13e-156">The `skp` prefix indicates that the retention policy is applied to Skype for Business conversations in the user's mailbox.</span></span>    |
|<span data-ttu-id="5b13e-157">从组织范围的 Office 365 保留策略中排除</span><span class="sxs-lookup"><span data-stu-id="5b13e-157">Excluded from an organization-wide Office 365 retention policy</span></span>     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     <span data-ttu-id="5b13e-158">如果从组织范围的 Office 365 保留策略中排除了邮箱, 则从 InPlaceHolds 属性中排除的保留策略的 GUID 将显示在 "" 属性中, 并由`-mbx`前缀进行标识。</span><span class="sxs-lookup"><span data-stu-id="5b13e-158">If a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy the mailbox is excluded from is displayed in the InPlaceHolds property and is identified by the `-mbx` prefix.</span></span>    |

### <a name="get-organizationconfig"></a><span data-ttu-id="5b13e-159">Set-organizationconfig</span><span class="sxs-lookup"><span data-stu-id="5b13e-159">Get-OrganizationConfig</span></span>
<span data-ttu-id="5b13e-160">如果运行**邮箱**cmdlet 时, *InPlaceHolds*属性为空, 则仍可能会将一个或多个组织范围内的 Office 365 保留策略应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b13e-160">If the *InPlaceHolds* property is empty when you run the **Get-Mailbox** cmdlet, there still may be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span> <span data-ttu-id="5b13e-161">在 Exchange Online PowerShell 中运行以下命令, 获取组织范围内的 Office 365 保留策略的 Guid 列表。</span><span class="sxs-lookup"><span data-stu-id="5b13e-161">Run the following command in Exchange Online PowerShell to get a list of GUIDs for organization-wide Office 365 retention policies.</span></span>

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="5b13e-162">如果 InPlaceHolds 属性中的值过多, 并且不是全部显示, 则可以运行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令将每个 GUID 显示在单独的行上。</span><span class="sxs-lookup"><span data-stu-id="5b13e-162">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="5b13e-163">下表介绍了不同类型的组织范围的保留, 以及在运行**set-organizationconfig** cmdlet 时如何根据*InPlaceHolds*属性中包含的 guid 标识每种类型。</span><span class="sxs-lookup"><span data-stu-id="5b13e-163">The following table describes the different types of organization-wide holds and how to identify each type based on the GUIDs contained in *InPlaceHolds* property when you run the **Get-OrganizationConfig** cmdlet.</span></span>


|<span data-ttu-id="5b13e-164">保留类型</span><span class="sxs-lookup"><span data-stu-id="5b13e-164">Hold type</span></span>  |<span data-ttu-id="5b13e-165">示例值</span><span class="sxs-lookup"><span data-stu-id="5b13e-165">Example value</span></span>  |<span data-ttu-id="5b13e-166">说明</span><span class="sxs-lookup"><span data-stu-id="5b13e-166">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="5b13e-167">应用于 Exchange 邮箱、Exchange 公用文件夹和团队聊天的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="5b13e-167">Office 365 retention policies applied to Exchange mailboxes, Exchange public folders, and Teams chats</span></span>    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   <span data-ttu-id="5b13e-168">在 Microsoft 团队中应用于 Exchange 邮箱、Exchange 公用文件夹和1xN 聊天的组织范围内的保留策略由以`mbx`前缀开头的 guid 进行标识。</span><span class="sxs-lookup"><span data-stu-id="5b13e-168">Organization-wide retention policies applied to Exchange mailboxes, Exchange public folders, and 1xN chats in Microsoft Teams are identified by GUIDs that start with the `mbx` prefix.</span></span> <span data-ttu-id="5b13e-169">注意1xN 聊天存储在各个聊天参与者的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5b13e-169">Note 1xN chats are stored in the mailbox of the individual chat participants.</span></span>      |
|<span data-ttu-id="5b13e-170">应用于 Office 365 组和团队频道消息的 office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="5b13e-170">Office 365 retention policy applied to Office 365 Groups and Teams channel messages</span></span>     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    <span data-ttu-id="5b13e-171">在 Microsoft 团队中应用于 Office 365 组和频道消息的组织范围内的保留策略由以`grp`前缀开头的 guid 标识。</span><span class="sxs-lookup"><span data-stu-id="5b13e-171">Organization-wide retention policies applied to Office 365 groups and channel messages in Microsoft Teams are identified by GUIDs that start with the `grp` prefix.</span></span> <span data-ttu-id="5b13e-172">注释通道邮件存储在与 Microsoft 团队相关联的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5b13e-172">Note channel messages are stored in the group mailbox that is associated with a Microsoft Team.</span></span>     |

<span data-ttu-id="5b13e-173">有关应用于 Microsoft 团队的详细信息保留策略, 请参阅[保留策略](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)的 "团队位置" 一节概述。</span><span class="sxs-lookup"><span data-stu-id="5b13e-173">For more information retention policies applied to Microsoft Teams, see the "Teams location" section [Overview of retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a><span data-ttu-id="5b13e-174">了解保留策略的 InPlaceHolds 值的格式</span><span class="sxs-lookup"><span data-stu-id="5b13e-174">Understanding the format of the InPlaceHolds value for retention policies</span></span>

<span data-ttu-id="5b13e-175">除了将 InPlaceHolds 属性中的项目标识为 Office 365 保留策略的前缀 (mbx、skp 或 grp) 之外, 此值还包含一个标识为策略配置的保留操作类型的后缀。</span><span class="sxs-lookup"><span data-stu-id="5b13e-175">In addition to the prefix (mbx, skp, or grp) that identifies an item in the InPlaceHolds property as an Office 365 retention policy, the value also contains a suffix that identifies the type of retention action that's configured for the policy.</span></span> <span data-ttu-id="5b13e-176">例如, 在以下示例中, 操作后缀以粗体突出显示:</span><span class="sxs-lookup"><span data-stu-id="5b13e-176">For example, the action suffix is highlighted in bold type in the following examples:</span></span>

   <span data-ttu-id="5b13e-177">`skp127d7cf1076947929bf136b7a2a8c36f`**: 1**</span><span class="sxs-lookup"><span data-stu-id="5b13e-177">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span></span>

   <span data-ttu-id="5b13e-178">`mbx7cfb30345d454ac0a989ab3041051209`**: 2**</span><span class="sxs-lookup"><span data-stu-id="5b13e-178">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span></span>

   <span data-ttu-id="5b13e-179">`grp1a0a132ee8944501a4bb6a452ec31171`**: 3**</span><span class="sxs-lookup"><span data-stu-id="5b13e-179">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span></span>

<span data-ttu-id="5b13e-180">下表定义了三种可能的保留操作:</span><span class="sxs-lookup"><span data-stu-id="5b13e-180">The following table defines the three possible retention actions:</span></span>

|<span data-ttu-id="5b13e-181">值</span><span class="sxs-lookup"><span data-stu-id="5b13e-181">Value</span></span>  |<span data-ttu-id="5b13e-182">说明</span><span class="sxs-lookup"><span data-stu-id="5b13e-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="5b13e-183">**1**</span><span class="sxs-lookup"><span data-stu-id="5b13e-183">**1**</span></span>     | <span data-ttu-id="5b13e-184">指示保留策略已配置为删除项目。</span><span class="sxs-lookup"><span data-stu-id="5b13e-184">Indicates that the retention policy is configured to delete items.</span></span> <span data-ttu-id="5b13e-185">策略不会保留项目。</span><span class="sxs-lookup"><span data-stu-id="5b13e-185">The policy doesn't retain items.</span></span>        |
|<span data-ttu-id="5b13e-186">**双面**</span><span class="sxs-lookup"><span data-stu-id="5b13e-186">**2**</span></span>    |    <span data-ttu-id="5b13e-187">指示保留策略配置为保留项目。</span><span class="sxs-lookup"><span data-stu-id="5b13e-187">Indicates that the retention policy is configured to hold items.</span></span> <span data-ttu-id="5b13e-188">在保留期过期后, 策略不会删除项目。</span><span class="sxs-lookup"><span data-stu-id="5b13e-188">The policy doesn't delete items after the retention period expires.</span></span>     |
|<span data-ttu-id="5b13e-189">**第三章**</span><span class="sxs-lookup"><span data-stu-id="5b13e-189">**3**</span></span>     |   <span data-ttu-id="5b13e-190">指示保留策略配置为保留项目, 然后在保留期过期后将其删除。</span><span class="sxs-lookup"><span data-stu-id="5b13e-190">Indicates that the retention policy is configured to hold items and then delete them after the retention period expires.</span></span>      |

<span data-ttu-id="5b13e-191">有关保留操作的详细信息, 请参阅[保留策略概述](retention-policies.md#retaining-content-for-a-specific-period-of-time)中的 "在特定时间段内保留内容" 部分。</span><span class="sxs-lookup"><span data-stu-id="5b13e-191">For more information about retention actions, see the "Retaining content for a specific period of time" section in [Overview of retention policies](retention-policies.md#retaining-content-for-a-specific-period-of-time).</span></span>
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a><span data-ttu-id="5b13e-192">步骤 2: 使用 GUID 标识保留</span><span class="sxs-lookup"><span data-stu-id="5b13e-192">Step 2: Use the GUID to identify the hold</span></span>

<span data-ttu-id="5b13e-193">获取应用于邮箱的保留的 GUID 后, 下一步是使用该 GUID 标识保留。</span><span class="sxs-lookup"><span data-stu-id="5b13e-193">After you obtain the GUID for a hold that is applied to a mailbox, the next step is to use that GUID to identify the hold.</span></span> <span data-ttu-id="5b13e-194">以下各节介绍如何使用保留 GUID 标识保留的名称 (和其他信息)。</span><span class="sxs-lookup"><span data-stu-id="5b13e-194">The following sections show how to identify the name of the hold (and other information) by using the hold GUID.</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="5b13e-195">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="5b13e-195">eDiscovery holds</span></span>

<span data-ttu-id="5b13e-196">在 Security & 合规性中心 PowerShell 中运行以下命令, 以确定应用于邮箱的电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="5b13e-196">Run the following commands in Security & Compliance Center PowerShell to identify an eDiscovery hold that's applied to the mailbox.</span></span> <span data-ttu-id="5b13e-197">使用您在步骤1中确定的电子数据展示保留的 GUID (不包括 UniH 前缀)。</span><span class="sxs-lookup"><span data-stu-id="5b13e-197">Use the GUID (not including the UniH prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="5b13e-198">第一个命令创建包含有关保留的信息的变量。</span><span class="sxs-lookup"><span data-stu-id="5b13e-198">The first command creates a variable that contains information about the hold.</span></span> <span data-ttu-id="5b13e-199">在其他命令中使用此变量。</span><span class="sxs-lookup"><span data-stu-id="5b13e-199">This variable is used in the other commands.</span></span> <span data-ttu-id="5b13e-200">第二个命令显示与保留相关联的电子数据展示事例的名称。</span><span class="sxs-lookup"><span data-stu-id="5b13e-200">The second command displays the name of the eDiscovery case the hold is associated with.</span></span> <span data-ttu-id="5b13e-201">第三个命令显示保留的名称和应用保留的邮箱列表。</span><span class="sxs-lookup"><span data-stu-id="5b13e-201">The third command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

<span data-ttu-id="5b13e-202">若要连接到安全 & 合规性中心 PowerShell, 请参阅[connect To Security & 合规性中心 powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="5b13e-202">To connect to Security & Compliance Center PowerShell, see  [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

### <a name="in-place-holds"></a><span data-ttu-id="5b13e-203">就地保留</span><span class="sxs-lookup"><span data-stu-id="5b13e-203">In-Place Holds</span></span>

<span data-ttu-id="5b13e-204">在 Exchange Online PowerShell 中运行以下命令, 以确定应用于邮箱的就地保留。</span><span class="sxs-lookup"><span data-stu-id="5b13e-204">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's applied to the mailbox.</span></span> <span data-ttu-id="5b13e-205">对您在步骤1中标识的就地保留使用 GUID。</span><span class="sxs-lookup"><span data-stu-id="5b13e-205">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> <span data-ttu-id="5b13e-206">该命令将显示保留的名称和应用保留的邮箱列表。</span><span class="sxs-lookup"><span data-stu-id="5b13e-206">The command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
<span data-ttu-id="5b13e-207">如果就地保留的 GUID 以`cld`前缀开头, 请确保在运行前一个命令时包含前缀。</span><span class="sxs-lookup"><span data-stu-id="5b13e-207">If the GUID for the In-Place Hold starts with the `cld` prefix, be sure to include the prefix when running the previous command.</span></span>

### <a name="office-365-retention-policies"></a><span data-ttu-id="5b13e-208">Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="5b13e-208">Office 365 retention policies</span></span>

<span data-ttu-id="5b13e-209">在 Security & 合规中心 PowerShell 中运行以下命令, 以标识应用于邮箱的 Office 365 保留策略 (组织范围或特定位置)。</span><span class="sxs-lookup"><span data-stu-id="5b13e-209">Run the following command in Security & Compliance Center PowerShell to identity the Office 365 retention policy (organization-wide or specific location) that's applied to the mailbox.</span></span> <span data-ttu-id="5b13e-210">使用您在步骤1中标识的 GUID (不包括 mbx、skp 或 grp 前缀或操作后缀)。</span><span class="sxs-lookup"><span data-stu-id="5b13e-210">Use the GUID (not including the mbx, skp, or grp prefix or the action suffix) that you identified in Step 1.</span></span>

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a><span data-ttu-id="5b13e-211">由于已将保留标签应用于文件夹或项目, 因此标识邮箱处于保留状态</span><span class="sxs-lookup"><span data-stu-id="5b13e-211">Identifying mailboxes on hold because a retention label has been applied to a folder or item</span></span>

<span data-ttu-id="5b13e-212">只要用户应用配置为保留内容或保留内容的保留标签, 然后将内容删除到其邮箱中的任何文件夹或项目, *ComplianceTagHoldApplied*邮箱属性将设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="5b13e-212">Whenever a user applies a retention label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="5b13e-213">发生这种情况时, 邮箱被视为处于保留状态, 就像将其置于诉讼保留状态或分配到 Office 365 保留策略一样。</span><span class="sxs-lookup"><span data-stu-id="5b13e-213">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span> <span data-ttu-id="5b13e-214">当*ComplianceTagHoldApplied*属性设置为**True**时, 可能会出现以下情况:</span><span class="sxs-lookup"><span data-stu-id="5b13e-214">When the *ComplianceTagHoldApplied* property is set to **True**, the following things may occur:</span></span>

- <span data-ttu-id="5b13e-215">如果删除了邮箱或用户的 Office 365 用户帐户, 则邮箱将成为[非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="5b13e-215">If the mailbox or the user's Office 365 user account is deleted, the mailbox becomes an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span>
- <span data-ttu-id="5b13e-216">您无法禁用邮箱 (主邮箱或存档邮箱 (如果已启用)。</span><span class="sxs-lookup"><span data-stu-id="5b13e-216">You aren't able to disable the mailbox (either the primary mailbox or the archive mailbox, if it's enabled).</span></span>
- <span data-ttu-id="5b13e-217">邮箱中的项目可能会超过预期的保留时间。</span><span class="sxs-lookup"><span data-stu-id="5b13e-217">Items in the mailbox may be retained longer than expected.</span></span> <span data-ttu-id="5b13e-218">这是因为邮箱处于保留状态, 因此没有永久删除 (清除) 的邮件。</span><span class="sxs-lookup"><span data-stu-id="5b13e-218">This is because the mailbox is on hold and therefore no items are permanently deleted (purged).</span></span>

<span data-ttu-id="5b13e-219">若要查看*ComplianceTagHoldApplied*属性的值, 请在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="5b13e-219">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="5b13e-220">有关保留标签的详细信息, 请参阅[Office 365 的概述保留标签](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="5b13e-220">For more information about retention labels, see [Overview of Office 365 retention labels](labels.md).</span></span>

## <a name="managing-mailboxes-on-delay-hold"></a><span data-ttu-id="5b13e-221">在延迟保留时管理邮箱</span><span class="sxs-lookup"><span data-stu-id="5b13e-221">Managing mailboxes on delay hold</span></span>

<span data-ttu-id="5b13e-222">从邮箱中删除了任何类型的保留后, *DelayHoldApplied*邮箱属性的值将设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="5b13e-222">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="5b13e-223">下次托管文件夹助理处理邮箱并检测已删除保留时, 会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="5b13e-223">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold was removed.</span></span> <span data-ttu-id="5b13e-224">这称为*延迟保留*, 表示实际删除保留的延迟为30天, 以防止永久删除 (清除) 邮箱中的数据。</span><span class="sxs-lookup"><span data-stu-id="5b13e-224">This is called a *delay hold* and means that the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted (purged) from the mailbox.</span></span> <span data-ttu-id="5b13e-225">这使管理员有机会搜索或恢复在删除保留后将清除的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="5b13e-225">This gives admins an opportunity to search for or recover mailbox items that will be purged after the hold is removed.</span></span> <span data-ttu-id="5b13e-226">将延迟保留放在邮箱上时, 该邮箱仍被视为无限持续时间处于保留状态, 就像该邮箱处于诉讼保留状态一样。</span><span class="sxs-lookup"><span data-stu-id="5b13e-226">When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="5b13e-227">30天后, 延迟保留过期, Office 365 将自动尝试删除延迟保留 (通过将*DelayHoldApplied*属性设置为**False**), 以便删除保留。</span><span class="sxs-lookup"><span data-stu-id="5b13e-227">After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="5b13e-228">在*DelayHoldApplied*属性设置为**False**后, 在下一次托管文件夹助理处理邮箱时, 将清除标记为要删除的项目。</span><span class="sxs-lookup"><span data-stu-id="5b13e-228">After the *DelayHoldApplied* property to **False**, items that are marked for removal are purged the next time the mailbox is processed by the Managed Folder Assistant.</span></span>

<span data-ttu-id="5b13e-229">若要查看邮箱的*DelayHoldApplied*属性的值, 请在 Exchange Online PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="5b13e-229">To view the value for the *DelayHoldApplied* property for a mailbox, run the following command in Exchange Online PowerShell.</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="5b13e-230">若要在过期之前删除延迟保留, 可以在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="5b13e-230">To remove the delay hold before it expires, you can run the following command in Exchange Online PowerShell:</span></span> 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="5b13e-231">您必须在 Exchange Online 中向您分配 "合法保留" 角色, 才能使用*RemoveDelayHoldApplied*参数</span><span class="sxs-lookup"><span data-stu-id="5b13e-231">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter</span></span> 

<span data-ttu-id="5b13e-232">若要删除非活动邮箱的延迟保留, 请在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="5b13e-232">To remove the delay hold on an inactive mailbox, run the following command in Exchange Online PowerShell:</span></span>

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> <span data-ttu-id="5b13e-233">在上一命令中指定非活动邮箱的最佳方法是使用其可分辨名称或 Exchange GUID 值。</span><span class="sxs-lookup"><span data-stu-id="5b13e-233">The best way to specify an inactive mailbox in the previous command is to use its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="5b13e-234">使用下列值之一有助于避免意外指定错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b13e-234">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="5b13e-235">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5b13e-235">Next steps</span></span>

<span data-ttu-id="5b13e-236">在确定了应用于邮箱的保留后, 可以执行一些任务, 如更改保留的持续时间、临时或永久删除保留或从 Office 365 保留策略中排除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b13e-236">After you identify the holds that are applied to a mailbox, you can perform tasks such as changing the duration of the hold, temporarily or permanently removing the hold, or excluding an inactive mailbox from an Office 365 retention policy.</span></span> <span data-ttu-id="5b13e-237">有关执行与保留相关的任务的详细信息, 请参阅下列主题之一:</span><span class="sxs-lookup"><span data-stu-id="5b13e-237">For more information about performing tasks related to holds, see the one of the following topics:</span></span>

- <span data-ttu-id="5b13e-238">在 Security & 合规中心 PowerShell 中运行[new-retentioncompliancepolicy-AddExchangeLocationException \<user 邮箱>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)命令, 以从组织范围内的 Office 365 保留策略中排除邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b13e-238">Run the [Set-RetentionCompliancePolicy -AddExchangeLocationException \<user mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) command in Security & Compliance Center PowerShell to exclude a mailbox from an organization-wide Office 365 retention policy.</span></span> <span data-ttu-id="5b13e-239">此命令仅可用于*ExchangeLocation*属性值等于`All`的保留策略。</span><span class="sxs-lookup"><span data-stu-id="5b13e-239">This command can only be used for retention policies where the value for the *ExchangeLocation* property equals `All`.</span></span>

- <span data-ttu-id="5b13e-240">在 Exchange Online PowerShell 中运行[ExcludeFromOrgHolds \<不带前缀或后缀>命令中的设置邮箱-保留 GUID](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) , 以从组织范围内的 Office 365 保留策略中排除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b13e-240">Run the [Set-Mailbox -ExcludeFromOrgHolds \<hold GUID without prefix or suffix>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide Office 365 retention policy.</span></span>

- [<span data-ttu-id="5b13e-241">在 Office 365 中更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="5b13e-241">Change the hold duration for an inactive mailbox in Office 365</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="5b13e-242">删除 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="5b13e-242">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

- [<span data-ttu-id="5b13e-243">删除保留状态云邮箱的“可恢复的项目”文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="5b13e-243">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)

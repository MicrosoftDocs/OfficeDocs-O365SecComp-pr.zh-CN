---
title: 如何识别为 Exchange Online 邮箱设置的保留类型
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: 了解如何识别的不同类型的保留，可以放在 Office 365 邮箱。保留的这些类型包括诉讼保留、 电子数据展示保留和 Office 365 保留策略。您还可以确定是否用户已从组织范围内保留策略中排除
ms.openlocfilehash: 1572b34d3f9abef2fb922fc9b01d1f5a27fcdf7b
ms.sourcegitcommit: e4ebef6aaf756eefb86c9f3a602cf75f5d344271
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026509"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a><span data-ttu-id="c4330-105">如何识别为 Exchange Online 邮箱设置的保留类型</span><span class="sxs-lookup"><span data-stu-id="c4330-105">How to identify the type of hold placed on an Exchange Online mailbox</span></span>

<span data-ttu-id="c4330-106">本文介绍如何标识放置在 Office 365 中的 Exchange Online 邮箱的保留项。</span><span class="sxs-lookup"><span data-stu-id="c4330-106">This article explains how to identify holds placed on Exchange Online mailboxes in Office 365.</span></span>

<span data-ttu-id="c4330-p102">Office 365 提供多种方式的组织可以防止邮箱内容被永久删除。这将允许组织保留内容以满足合规性将或法律或其他类型的调查的持续时间。下面是在 Office 365 中的保留功能 （也称为*保留*） 的列表：</span><span class="sxs-lookup"><span data-stu-id="c4330-p102">Office 365 offers a number of ways that your organization can prevent mailbox content from being permanently deleted. This allows your organization to retain content to meet compliance regulars or for the duration of legal or other types of investigations. Here's a list of the retention features (also called *holds*) in Office 365:</span></span>

- <span data-ttu-id="c4330-110">**诉讼保留**-于 Exchange Online 中的用户邮箱的保留项。</span><span class="sxs-lookup"><span data-stu-id="c4330-110">**Litigation Hold** - Holds that are applied to user mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="c4330-p103">**电子数据展示保留**-与安全性和合规性中心中的电子数据展示事例关联的保留项。电子数据展示保留项可以为 Office 365 组和 Microsoft 团队对用户邮箱和相应的邮箱应用。</span><span class="sxs-lookup"><span data-stu-id="c4330-p103">**eDiscovery hold** - Holds that are associated with an eDiscovery case in the Security & Compliance Center. eDiscovery holds can be applied to user mailboxes, and on the corresponding mailbox for Office 365 Groups and Microsoft Teams.</span></span>

- <span data-ttu-id="c4330-113">**就地保留**— 通过使用在 Exchange 管理中心中的就地电子数据展示和保留工具应用于用户邮箱的保留中心在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c4330-113">**In-Place Hold** - Holds that are applied to user mailboxes by using the In-Place eDiscovery & Hold tool in the Exchange admin center in Exchange Online.</span></span>

- <span data-ttu-id="c4330-p104">**Office 365 保留策略**-Office 365 组和 Microsoft 团队保留用户邮箱和相应的邮箱中 Exchange Online 中的内容。您可以创建保留策略进行业务对话，存储在用户邮箱中保留 Skype。</span><span class="sxs-lookup"><span data-stu-id="c4330-p104">**Office 365 retention policy** - Retains content in user mailboxes in Exchange Online and in the corresponding mailbox for Office 365 Groups and Microsoft Teams. You can create a retention policy retains Skype for Business Conversations, which are stored in user mailboxes.</span></span>

  <span data-ttu-id="c4330-116">有两种类型的 Office 365 可以分配给邮箱的保留策略。</span><span class="sxs-lookup"><span data-stu-id="c4330-116">There are two types of Office 365 retention policies that can be assigned to mailboxes.</span></span>

    - <span data-ttu-id="c4330-p105">**特定位置保留策略**-这是分配给特定用户的内容位置策略。在 Exchange Online PowerShell 中使用**Get-mailbox** cmdlet，以获取有关分配给特定邮箱的保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="c4330-p105">**Specific location retention policies** - These are policies that are assigned to the content locations of specific users. You use the **Get-Mailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific mailboxes.</span></span>

    - <span data-ttu-id="c4330-p106">**组织范围内保留策略**-这是分配给您的组织中的所有内容位置策略。在 Exchange Online PowerShell 中使用**Get-organizationconfig** cmdlet，以获取有关组织范围内保留策略的信息。有关详细信息，请参阅[Office 365 概述保留策略](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)中的"将保留策略应用于整个组织或特定位置"一节。</span><span class="sxs-lookup"><span data-stu-id="c4330-p106">**Organization-wide retention policies** - These are policies that are assigned to all content locations in your organization. You use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies. For more information, see the "Applying a retention policy to an entire organization or specific locations" section in [Overview of Office 365 retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

- <span data-ttu-id="c4330-p107">**Office 365 保留标签**-如果用户将 Office 365 保留标签 （一个配置为保留内容或保留，然后删除内容） 应用于*任何*文件夹或项目中保留其邮箱置于邮箱就像邮箱已置于诉讼保留或分配给 Office 365 保留策略。有关详细信息，请参阅本文中的[标识邮箱保留因为文件夹或项目已应用保留标签](#identifying-mailboxes-on-hold-because-a-label-has-been-applied-to-a-folder-or-item)一节。</span><span class="sxs-lookup"><span data-stu-id="c4330-p107">**Office 365 retention labels** - If a user applies an Office 365 retention label (one that's configured to retain content or retain and then delete content) to *any* folder or item in their mailbox, a hold is placed on the mailbox just as if the mailbox was placed on Litigation Hold or assigned to an Office 365 retention policy. For more information, see the [Identifying mailboxes on hold because a retention label has been applied to a folder or item](#identifying-mailboxes-on-hold-because-a-label-has-been-applied-to-a-folder-or-item) section in this article.</span></span>

<span data-ttu-id="c4330-p108">若要管理邮箱置于保留状态，您可能需要确定上，以便您可以执行任务，如更改保留持续时间、 临时或永久删除保留项，或从 Office 365 保留策略中排除邮箱置于邮箱的保留项的类型。在这些情况下，第一步是确定邮箱置于保留项的类型。因为可以对单个邮箱放置多个保留 （和不同类型的保留），您必须确定置于邮箱，如果您想要删除或更改这些保留项的所有保留项。</span><span class="sxs-lookup"><span data-stu-id="c4330-p108">To manage mailboxes on hold, you may have to identify the type of hold that's placed on a mailbox so that you can perform tasks such as changing the hold duration, temporarily or permanently removing the hold, or excluding a mailbox from a Office 365 retention policy. In these cases, the first step is to identify the type of hold placed on the mailbox. And because multiple holds (and different types of holds) can be placed on a single mailbox, you'll have to identify all holds placed on a mailbox if you want to remove or change those holds.</span></span>

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a><span data-ttu-id="c4330-127">步骤 1： 获取保留项的 GUID 置于邮箱</span><span class="sxs-lookup"><span data-stu-id="c4330-127">Step 1: Obtaining the GUID for holds placed on a mailbox</span></span>

<span data-ttu-id="c4330-p109">在 Exchange Online PowerShell 中获取对邮箱置于保留项的 GUID，可以运行以下两个 cmdlet。获取 GUID 后，您使用它来标识在步骤 2 中的特定保留项。请注意，诉讼保留未被标识的 GUID。诉讼保留项是启用或禁用的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c4330-p109">You can run the following two cmdlets in Exchange Online PowerShell to get the GUID of the holds that are placed on a mailbox. After you obtain a GUID, you use it to identify the specific hold in Step 2. Note that Litigation Holds are not identified by a GUID. Litigation Holds are either enabled or disabled for a mailbox.</span></span>

- <span data-ttu-id="c4330-p110">**Get-mailbox** -使用此 cmdlet，以确定是否诉讼保留的邮箱启用以及获取 Guid 电子数据展示保留、 就地保留，和 Office 365 专门分配给某个邮箱的保留策略。此 cmdlet 的输出将还指示邮箱是否已明确排除从组织范围内保留策略。</span><span class="sxs-lookup"><span data-stu-id="c4330-p110">**Get-Mailbox** - Use this cmdlet to determine whether Litigation Hold is enabled for a mailbox and to get the GUIDs for eDiscovery holds, In-Place Holds, and Office 365 retention policies that are specifically assigned to a mailbox. The output of this cmdlet will also indicate if a mailbox has been explicitly excluded from an organization-wide retention policy.</span></span>

- <span data-ttu-id="c4330-134">**Get-organizationconfig** -使用此 cmdlet 可获取的组织范围内保留策略的 Guid。</span><span class="sxs-lookup"><span data-stu-id="c4330-134">**Get-OrganizationConfig** - Use this cmdlet to get the GUIDs for organization-wide retention policies.</span></span>

<span data-ttu-id="c4330-135">要连接到 Exchange Online PowerShell 中，请参阅[Connect to Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="c4330-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

### <a name="get-mailbox"></a><span data-ttu-id="c4330-136">Get-Mailbox</span><span class="sxs-lookup"><span data-stu-id="c4330-136">Get-Mailbox</span></span>

<span data-ttu-id="c4330-137">运行以下命令以获取有关保留和 Office 365 保留策略应用于邮箱的信息。</span><span class="sxs-lookup"><span data-stu-id="c4330-137">Run the following command to get information about the holds and Office 365 retention policies applied to a mailbox.</span></span>

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="c4330-138">如果 InPlaceHolds 属性中有太多值而不是全部显示，则可以运行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令单独占一行上显示每个 GUID。</span><span class="sxs-lookup"><span data-stu-id="c4330-138">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="c4330-139">下表介绍了如何确定不同类型的保留项运行**Get-mailbox** cmdlet 时基于*InPlaceHolds*属性中的值。</span><span class="sxs-lookup"><span data-stu-id="c4330-139">The following table describes how to identify different types of holds based on the values in the *InPlaceHolds* property when you run the **Get-Mailbox** cmdlet.</span></span>


|<span data-ttu-id="c4330-140">保留类型</span><span class="sxs-lookup"><span data-stu-id="c4330-140">Hold type</span></span>  |<span data-ttu-id="c4330-141">示例值</span><span class="sxs-lookup"><span data-stu-id="c4330-141">Example value</span></span>  |<span data-ttu-id="c4330-142">如何标识保留项</span><span class="sxs-lookup"><span data-stu-id="c4330-142">How to identify the hold</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c4330-143">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="c4330-143">Litigation Hold</span></span>     |    `True`     |     <span data-ttu-id="c4330-144">如果*LitigationHoldEnabled*属性设置为诉讼保留的邮箱启用`True`。</span><span class="sxs-lookup"><span data-stu-id="c4330-144">Litigation Hold is enabled for a mailbox if the *LitigationHoldEnabled* property is set to `True`.</span></span>    |
|<span data-ttu-id="c4330-145">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="c4330-145">eDiscovery hold</span></span>     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   <span data-ttu-id="c4330-p111">*InPlaceHolds 属性*包含与电子数据展示事例中安全性和合规性中心关联任何保留项的 GUID。您可以判断这是电子数据展示保留，因为 GUID 开头`UniH`前缀 （这表示统一保留）。</span><span class="sxs-lookup"><span data-stu-id="c4330-p111">The *InPlaceHolds property* contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center. You can tell this is an eDiscovery hold because the GUID starts with the `UniH` prefix (which denotes a Unified Hold).</span></span>      |
|<span data-ttu-id="c4330-148">就地保留</span><span class="sxs-lookup"><span data-stu-id="c4330-148">In-Place Hold</span></span>     |     `c0ba3ce811b6432a8751430937152491` <br/> <span data-ttu-id="c4330-149">或</span><span class="sxs-lookup"><span data-stu-id="c4330-149">or</span></span> <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     <span data-ttu-id="c4330-p112">*InPlaceHolds*属性将包含邮箱置于就地保留的 GUID。您可以判断这是就地保留 GUID 也不会以前缀开头或使用启动，因为`cld`前缀。</span><span class="sxs-lookup"><span data-stu-id="c4330-p112">The *InPlaceHolds* property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID either doesn't start with a prefix or it starts with the `cld` prefix.</span></span>     |
|<span data-ttu-id="c4330-152">Office 365 专门应用于邮箱的保留策略</span><span class="sxs-lookup"><span data-stu-id="c4330-152">Office 365 retention policy specifically applied to the mailbox</span></span>     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> <span data-ttu-id="c4330-153">或</span><span class="sxs-lookup"><span data-stu-id="c4330-153">or</span></span> <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     <span data-ttu-id="c4330-p113">InPlaceHolds 属性将包含任何特定位置的保留策略应用于邮箱的 Guid。您可以标识保留策略，因为 GUID 开头`mbx`或`skp`前缀。`skp`前缀表明到 Skype 应用保留策略的用户的邮箱中的业务对话。</span><span class="sxs-lookup"><span data-stu-id="c4330-p113">The InPlaceHolds property contains GUIDs of any specific location retention policy that's applied to the mailbox. You can identify retention policies because the GUID starts with the `mbx` or the `skp` prefix. The `skp` prefix indicates that the retention policy is applied to Skype for Business conversations in the user's mailbox.</span></span>    |
|<span data-ttu-id="c4330-157">从组织范围内的 Office 365 保留策略中排除</span><span class="sxs-lookup"><span data-stu-id="c4330-157">Excluded from an organization-wide Office 365 retention policy</span></span>     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     <span data-ttu-id="c4330-158">如果从组织范围内的 Office 365 保留策略中排除邮箱，从排除邮箱的保留策略的 GUID InPlaceHolds 属性中显示，并由`-mbx`前缀。</span><span class="sxs-lookup"><span data-stu-id="c4330-158">If a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy the mailbox is excluded from is displayed in the InPlaceHolds property and is identified by the `-mbx` prefix.</span></span>    |

### <a name="get-organizationconfig"></a><span data-ttu-id="c4330-159">Get-organizationconfig</span><span class="sxs-lookup"><span data-stu-id="c4330-159">Get-OrganizationConfig</span></span>
<span data-ttu-id="c4330-p114">如果运行**Get-mailbox** cmdlet 时， *InPlaceHolds*属性为空，仍可能存在一个或多个组织范围内 Office 365 保留策略应用于邮箱。运行以下命令在 Exchange Online PowerShell，可以获取 Guid 的列表用于组织范围内的 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="c4330-p114">If the *InPlaceHolds* property is empty when you run the **Get-Mailbox** cmdlet, there still may be one or more organization-wide Office 365 retention policies applied to the mailbox. Run the following command in Exchange Online PowerShell to get a list of GUIDs for organization-wide Office 365 retention policies.</span></span>

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="c4330-162">如果 InPlaceHolds 属性中有太多值而不是全部显示，则可以运行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令单独占一行上显示每个 GUID。</span><span class="sxs-lookup"><span data-stu-id="c4330-162">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="c4330-163">下表介绍不同类型的组织范围内保留项以及如何确定每种类型基于运行**Get-organizationconfig** cmdlet 时*InPlaceHolds*属性中包含的 Guid。</span><span class="sxs-lookup"><span data-stu-id="c4330-163">The following table describes the different types of organization-wide holds and how to identify each type based on the GUIDs contained in *InPlaceHolds* property when you run the **Get-OrganizationConfig** cmdlet.</span></span>


|<span data-ttu-id="c4330-164">保留类型</span><span class="sxs-lookup"><span data-stu-id="c4330-164">Hold type</span></span>  |<span data-ttu-id="c4330-165">示例值</span><span class="sxs-lookup"><span data-stu-id="c4330-165">Example value</span></span>  |<span data-ttu-id="c4330-166">说明</span><span class="sxs-lookup"><span data-stu-id="c4330-166">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c4330-167">Office 365 的保留策略应用于 Exchange 邮箱、 Exchange 公用文件夹和团队聊天</span><span class="sxs-lookup"><span data-stu-id="c4330-167">Office 365 retention policies applied to Exchange mailboxes, Exchange public folders, and Teams chats</span></span>    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   <span data-ttu-id="c4330-p115">组织范围内保留策略应用于 Exchange 邮箱，Exchange 公用文件夹和来开始的 Guid 标识 1xN 聊天中的 Microsoft 团队`mbx`前缀。请注意，1xN 聊天存储在单个聊天参与者的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c4330-p115">Organization-wide retention policies applied to Exchange mailboxes, Exchange public folders, and 1xN chats in Microsoft Teams are identified by GUIDs that start with the `mbx` prefix. Note that 1xN chats are stored in the mailbox of the individual chat participants.</span></span>      |
|<span data-ttu-id="c4330-170">Office 365 的保留策略应用于 Office 365 组和团队通道邮件</span><span class="sxs-lookup"><span data-stu-id="c4330-170">Office 365 retention policy applied to Office 365 Groups and Teams channel messages</span></span>     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    <span data-ttu-id="c4330-p116">由开头的 Guid 标识组织范围内保留策略应用于 Office 365 组和 Microsoft 团队中的通道邮件`grp`前缀。请注意，通道消息存储在与 Microsoft 团队相关联的组邮箱。</span><span class="sxs-lookup"><span data-stu-id="c4330-p116">Organization-wide retention policies applied to Office 365 groups and channel messages in Microsoft Teams are identified by GUIDs that start with the `grp` prefix. Note that channel messages are stored in the group mailbox that is associated with a Microsoft Team.</span></span>     |

<span data-ttu-id="c4330-173">有关详细信息保留策略应用于的 Microsoft 团队，请参阅"团队位置"部分[的保留策略概述](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。</span><span class="sxs-lookup"><span data-stu-id="c4330-173">For more information retention policies applied to Microsoft Teams, see the "Teams location" section [Overview of retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a><span data-ttu-id="c4330-174">了解保留策略的 InPlaceHolds 值的格式</span><span class="sxs-lookup"><span data-stu-id="c4330-174">Understanding the format of the InPlaceHolds value for retention policies</span></span>

<span data-ttu-id="c4330-p117">前缀 （mbx、 skp 或组） 的标识为 Office 365 保留策略的 InPlaceHolds 属性中的项目，除了值还包含后缀标识配置策略的保留操作的类型。例如，下面的示例中以粗体突出显示的操作后缀：</span><span class="sxs-lookup"><span data-stu-id="c4330-p117">In addition to the prefix (mbx, skp, or grp) that identifies an item in the InPlaceHolds property as an Office 365 retention policy, the value also contains a suffix that identifies the type of retention action that's configured for the policy. For example, the action suffix is highlighted in bold type in the following examples:</span></span>

   <span data-ttu-id="c4330-177">`skp127d7cf1076947929bf136b7a2a8c36f`**: 1**</span><span class="sxs-lookup"><span data-stu-id="c4330-177">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span></span>

   <span data-ttu-id="c4330-178">`mbx7cfb30345d454ac0a989ab3041051209`**: 2**</span><span class="sxs-lookup"><span data-stu-id="c4330-178">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span></span>

   <span data-ttu-id="c4330-179">`grp1a0a132ee8944501a4bb6a452ec31171`**: 3**</span><span class="sxs-lookup"><span data-stu-id="c4330-179">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span></span>

<span data-ttu-id="c4330-180">下表定义的三种可能的保留期操作：</span><span class="sxs-lookup"><span data-stu-id="c4330-180">The following table defines the three possible retention actions:</span></span>

|<span data-ttu-id="c4330-181">值</span><span class="sxs-lookup"><span data-stu-id="c4330-181">Value</span></span>  |<span data-ttu-id="c4330-182">说明</span><span class="sxs-lookup"><span data-stu-id="c4330-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c4330-183">**1**</span><span class="sxs-lookup"><span data-stu-id="c4330-183">**1**</span></span>     | <span data-ttu-id="c4330-184">指示保留策略配置为删除的项目;策略不会保留的项目。</span><span class="sxs-lookup"><span data-stu-id="c4330-184">Indicates the retention policy is configured to delete items; the policy doesn't retain items.</span></span>        |
|<span data-ttu-id="c4330-185">**2**</span><span class="sxs-lookup"><span data-stu-id="c4330-185">**2**</span></span>    |    <span data-ttu-id="c4330-186">指示保留策略已配置为容纳项目;保留期过后，策略不会删除项目。</span><span class="sxs-lookup"><span data-stu-id="c4330-186">Indicates the retention policy is configured to hold items; the policy doesn't delete items after the retention period expires.</span></span>     |
|<span data-ttu-id="c4330-187">**3**</span><span class="sxs-lookup"><span data-stu-id="c4330-187">**3**</span></span>     |   <span data-ttu-id="c4330-188">指示保留策略配置为保留项目，然后再删除它们的保留期过后。</span><span class="sxs-lookup"><span data-stu-id="c4330-188">Indicates the retention policy is configured to hold items and then delete them after the retention period expires.</span></span>      |

<span data-ttu-id="c4330-189">有关保留操作的详细信息，请参阅[Overview of 保留策略](retention-policies.md#retaining-content-for-a-specific-period-of-time)中的"在特定时间内的保留内容"部分。</span><span class="sxs-lookup"><span data-stu-id="c4330-189">For more information about retention actions, see the "Retaining content for a specific period of time" section in [Overview of retention policies](retention-policies.md#retaining-content-for-a-specific-period-of-time).</span></span>
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a><span data-ttu-id="c4330-190">步骤 2： 使用 GUID 标识保留项</span><span class="sxs-lookup"><span data-stu-id="c4330-190">Step 2: Using the GUID to identify the hold</span></span>

<span data-ttu-id="c4330-p118">获取应用于邮箱的保留 GUID 后下, 一步是使用该 GUID 标识保留项。使用保留 GUID，以下各节显示如何标识保留项 （和其他信息） 的名称。</span><span class="sxs-lookup"><span data-stu-id="c4330-p118">After you obtain the GUID for a hold that is applied to a mailbox, the next step is to use that GUID to identify the hold. The following sections show how to identify the name of the hold (and other information) by using the hold GUID.</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="c4330-193">电子数据展示保留项</span><span class="sxs-lookup"><span data-stu-id="c4330-193">eDiscovery holds</span></span>

<span data-ttu-id="c4330-p119">若要确定应用于邮箱的电子数据展示保留的安全性和合规性中心 PowerShell 中运行以下命令。使用电子数据展示的 GUID （不包括 UniH 前缀） 保留在步骤 1 中确定。第一个命令创建变量包含保留; 有关信息在其他命令中使用此变量。第二个命令显示与保留电子数据展示事例的名称。第三个命令显示保留项的名称和保留应用于邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="c4330-p119">Run the following commands in Security & Compliance Center PowerShell to identify an eDiscovery hold that's applied to the mailbox. Use the GUID (not including the UniH prefix) for the eDiscovery hold that you identified in Step 1. The first command creates a variable that contains information about the hold; this variable is used in the other commands. The second command displays the name of the eDiscovery case the hold is associated with. The third command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

<span data-ttu-id="c4330-199">若要连接到安全性和合规性中心 PowerShell，请参阅[连接到 Office 365 安全性和合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="c4330-199">To connect to Security & Compliance Center PowerShell, see  [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

### <a name="in-place-holds"></a><span data-ttu-id="c4330-200">就地保留</span><span class="sxs-lookup"><span data-stu-id="c4330-200">In-Place Holds</span></span>

<span data-ttu-id="c4330-p120">在 Exchange Online PowerShell 中标识应用于邮箱就地保留中运行以下命令。使用您在步骤 1 中确定的就地保留的 GUID。该命令显示的保留项的名称和保留应用于邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="c4330-p120">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's applied to the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1. The command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
<span data-ttu-id="c4330-204">请注意，如果 GUID 的就地保留开头`cld`前缀，请确保包含前缀，运行上述命令时。</span><span class="sxs-lookup"><span data-stu-id="c4330-204">Note that if the GUID for the In-Place Hold starts with the `cld` prefix, be sure to include the prefix when running the previous command.</span></span>

### <a name="office-365-retention-policies"></a><span data-ttu-id="c4330-205">Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="c4330-205">Office 365 retention policies</span></span>

<span data-ttu-id="c4330-p121">运行以下命令安全性和合规性中心 PowerShell 中标识应用于邮箱的 Office 365 保留策略 （组织范围内或特定位置）。使用您在步骤 1 中确定的 GUID （不包括 mbx、 skp 或组前缀或的操作后缀）。</span><span class="sxs-lookup"><span data-stu-id="c4330-p121">Run the following command in Security & Compliance Center PowerShell to identity the Office 365 retention policy (organization-wide or specific location) that's applied to the mailbox. Use the GUID (not including the mbx, skp, or grp prefix or the action suffix) that you identified in Step 1.</span></span>

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a><span data-ttu-id="c4330-208">标识邮箱保留因为文件夹或项目已应用保留标签</span><span class="sxs-lookup"><span data-stu-id="c4330-208">Identifying mailboxes on hold because a retention label has been applied to a folder or item</span></span>

<span data-ttu-id="c4330-p122">只要用户应用保留标签配置保留内容或保留，然后删除任何文件夹或其邮箱中的项目的内容，则将*ComplianceTagHoldApplied* mailbox 属性设置为**True**。这种情况下，邮箱被认为保持状态，就像它置于诉讼保留或分配给 Office 365 保留策略。当*ComplianceTagHoldApplied*属性设置为**True**时，可能会发生以下操作：</span><span class="sxs-lookup"><span data-stu-id="c4330-p122">Whenever a user applies a retention label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**. When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy. When the *ComplianceTagHoldApplied* property is set to **True**, the following things may occur:</span></span>

- <span data-ttu-id="c4330-212">如果删除邮箱或用户的 Office 365 用户帐户，邮箱将变为[非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c4330-212">If the mailbox or the user's Office 365 user account is deleted, the mailbox becomes an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span>
- <span data-ttu-id="c4330-213">您将无法禁用 （主邮箱或存档邮箱，如果已启用） 的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c4330-213">You won't be able to disable the mailbox (either the primary mailbox or the archive mailbox, if it's enabled).</span></span>
- <span data-ttu-id="c4330-p123">可能比预期更长时间保留的邮箱中的项目。这是因为邮箱是置于保持状态，因此任何项目将被永久删除 （清除）。</span><span class="sxs-lookup"><span data-stu-id="c4330-p123">Items in the mailbox may be retained longer than expected. This is because the mailbox is on hold and therefore no items will be permanently deleted (purged).</span></span>

<span data-ttu-id="c4330-216">若要查看*ComplianceTagHoldApplied*属性的值，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c4330-216">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="c4330-217">有关保留标签的详细信息，请参阅[Office 365 概述保留标签](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="c4330-217">For more information about retention labels, see [Overview of Office 365 retention labels](labels.md).</span></span>

## <a name="managing-mailboxes-on-delay-hold"></a><span data-ttu-id="c4330-218">管理邮箱延迟保留</span><span class="sxs-lookup"><span data-stu-id="c4330-218">Managing mailboxes on delay hold</span></span>

<span data-ttu-id="c4330-p124">从邮箱中删除任何类型的保留项后， *DelayHoldApplied*邮箱属性的值设置为**True**。托管文件夹助理处理邮箱和检测已删除保留在下次出现此情况。这称为*延迟保留*，意味着 30 天，以防止被永久删除数据延迟，实际的保留项的删除 （清除） 从邮箱。这使管理员能够搜索或恢复将被清除后保留被实际删除的邮箱项目。延迟保留邮箱置于，当邮箱是仍可保持不受限制的持续时间，作为邮箱是否在诉讼保留。30 天后过期延迟保留，和 Office 365 将自动尝试删除延迟保留 （通过将*DelayHoldApplied*属性设置为**False**），以便将实际删除保留。之后将*DelayHoldApplied*属性设为**False**，标记为删除的项目将被清除的下次由托管文件夹助理处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="c4330-p124">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**. This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed. This is called a *delay hold* and means that the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted (purged) from the mailbox. This gives admins an opportunity to search for or recover mailbox items that will be purged after the hold is actually removed. When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold. After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold will be actually removed. After the *DelayHoldApplied* property to **False**, items that are marked for removal will be purged the next time the mailbox is processed by the Managed Folder Assistant.</span></span>

<span data-ttu-id="c4330-226">若要查看邮箱的*DelayHoldApplied*属性的值，请在 Exchange Online PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="c4330-226">To view the value for the *DelayHoldApplied* property for a mailbox, run the following command in Exchange Online PowerShell.</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="c4330-227">若要在过期之前，请删除延迟保留，可以在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c4330-227">To remove the delay hold before it expires, you can run the following command in Exchange Online PowerShell:</span></span> 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="c4330-228">请注意，您必须将分配给法律挂起角色在 Exchange Online 使用*RemoveDelayHoldApplied*参数</span><span class="sxs-lookup"><span data-stu-id="c4330-228">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter</span></span> 

<span data-ttu-id="c4330-229">若要删除非活动邮箱上的延迟保留项，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c4330-229">To remove the delay hold on an inactive mailbox, run the following command in Exchange Online PowerShell:</span></span>

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> <span data-ttu-id="c4330-p125">在上一命令中指定非活动邮箱的最佳方式是使用其可分辨名称或 Exchange GUID 值。使用下列值之一有助于防止意外指定错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c4330-p125">The best way to specify an inactive mailbox in the previous command is to use its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="c4330-232">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c4330-232">Next steps</span></span>

<span data-ttu-id="c4330-p126">确定应用于邮箱的保留项后，您可以执行任务更改的保留项的持续时间临时或永久删除保留项，如或 Office 365 保留策略，对于从策略中排除非活动邮箱。有关执行到保留项相关的任务的详细信息，请参阅以下主题之一：</span><span class="sxs-lookup"><span data-stu-id="c4330-p126">After you identify the holds that are applied to a mailbox, you can perform tasks such as changing the duration of the hold, temporarily or permanently removing the hold, or in the case of Office 365 retention policies, excluding an inactive mailbox from the policy. For more information about performing tasks related to holds, see the one of the following topics:</span></span>

- <span data-ttu-id="c4330-p127">运行[集 RetentionCompliancePolicy AddExchangeLocationException\<用户邮箱 >](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)中排除的组织范围内的 Office 365 保留策略的邮箱的安全性和合规性中心 PowerShell 命令。请注意，此命令可仅用于保留策略其中*ExchangeLocation*属性的值等于`All`。</span><span class="sxs-lookup"><span data-stu-id="c4330-p127">Run the [Set-RetentionCompliancePolicy -AddExchangeLocationException \<user mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) command in Security & Compliance Center PowerShell to exclude a mailbox from an organization-wide Office 365 retention policy. Note that this command can only be used for retention policies where the value for the *ExchangeLocation* property equals `All`.</span></span>

- <span data-ttu-id="c4330-237">运行[Set-mailbox ExcludeFromOrgHolds\<前缀或后缀不保留 GUID >](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)命令在 Exchange Online PowerShell 中排除的组织范围内的 Office 365 保留策略的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="c4330-237">Run the [Set-Mailbox -ExcludeFromOrgHolds \<hold GUID without prefix or suffix>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide Office 365 retention policy.</span></span>

- [<span data-ttu-id="c4330-238">更改在 Office 365 中的非活动邮箱的保留持续时间</span><span class="sxs-lookup"><span data-stu-id="c4330-238">Change the hold duration for an inactive mailbox in Office 365</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="c4330-239">删除 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="c4330-239">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

- [<span data-ttu-id="c4330-240">删除保留状态云邮箱的“可恢复的项目”文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="c4330-240">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)

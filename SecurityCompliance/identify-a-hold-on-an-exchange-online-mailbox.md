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
ms.openlocfilehash: d24e51bca0e3d290f110b1ab40f3ee9ae7993678
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525670"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a><span data-ttu-id="7ffca-102">如何识别为 Exchange Online 邮箱设置的保留类型</span><span class="sxs-lookup"><span data-stu-id="7ffca-102">How to identify the type of hold placed on an Exchange Online mailbox</span></span>

<span data-ttu-id="7ffca-103">本文介绍如何标识放置在 Office 365 中的 Exchange Online 邮箱的保留项。</span><span class="sxs-lookup"><span data-stu-id="7ffca-103">This article explains how to identify holds placed on Exchange Online mailboxes in Office 365.</span></span>

<span data-ttu-id="7ffca-p101">Office 365 提供多种方式的组织可以防止邮箱内容被永久删除。这将允许组织保留内容以满足合规性将或法律或其他类型的调查的持续时间。下面是在 Office 365 中的保留功能 （也称为保留项） 的列表：</span><span class="sxs-lookup"><span data-stu-id="7ffca-p101">Office 365 offers a number of ways that your organization can prevent mailbox content from being permanently deleted. This allows your organization to retain content to meet compliance regulars or for the duration of legal or other types of investigations. Here's a list of the retention features (also called holds) in Office 365:</span></span>

- <span data-ttu-id="7ffca-107">**诉讼保留**-于 Exchange Online 中的用户邮箱的保留项。</span><span class="sxs-lookup"><span data-stu-id="7ffca-107">**Litigation Hold** - Holds that are applied to user mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="7ffca-p102">**电子数据展示保留**-与安全性和合规性中心中的电子数据展示事例关联的保留项。电子数据展示保留项可以为 Office 365 组和 Microsoft 团队对用户邮箱和相应的邮箱应用。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p102">**eDiscovery hold** - Holds that are associated with an eDiscovery case in the Security & Compliance Center. eDiscovery holds can be applied to user mailboxes, and on the corresponding mailbox for Office 365 Groups and Microsoft Teams.</span></span>

- <span data-ttu-id="7ffca-110">**就地保留**— 通过使用在 Exchange 管理中心中的就地电子数据展示和保留工具应用于用户邮箱的保留中心在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7ffca-110">**In-Place Hold** - Holds that are applied to user mailboxes by using the In-Place eDiscovery & Hold tool in the Exchange admin center in Exchange Online.</span></span>

- <span data-ttu-id="7ffca-p103">**Office 365 保留策略**-Office 365 组和 Microsoft 团队保留用户邮箱和相应的邮箱中 Exchange Online 中的内容。您可以创建保留策略进行业务对话，存储在用户邮箱中保留 Skype。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p103">**Office 365 retention policy** - Retains content in user mailboxes in Exchange Online and in the corresponding mailbox for Office 365 Groups and Microsoft Teams. You can create a retention policy retains Skype for Business Conversations, which are stored in user mailboxes.</span></span>

  <span data-ttu-id="7ffca-113">有两种类型的 Office 365 可以分配给邮箱的保留策略。</span><span class="sxs-lookup"><span data-stu-id="7ffca-113">There are two types of Office 365 retention policies that can be assigned to mailboxes.</span></span>

    - <span data-ttu-id="7ffca-p104">**特定位置保留策略**-这是分配给特定用户的内容位置策略。在 Exchange Online PowerShell 中使用 Get-mailbox cmdlet，以获取有关分配给特定邮箱的保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p104">**Specific location retention policies** - These are policies that are assigned to the content locations of specific users. You use the Get-Mailbox cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific mailboxes.</span></span>

    - <span data-ttu-id="7ffca-p105">**组织范围内保留策略**-这是分配给您的组织中的所有内容位置策略。在 Exchange Online PowerShell 中使用 Get-organizationconfig cmdlet，以获取有关组织范围内保留策略的信息。有关详细信息，请参阅 Office 365 概述保留策略中的"将保留策略应用于整个组织或特定位置"一节。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p105">**Organization-wide retention policies** - These are policies that are assigned to all content locations in your organization. You use the Get-OrganizationConfig cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies. For more information, see the "Applying a retention policy to an entire organization or specific locations" section in Overview of Office 365 retention policies.</span></span>

<span data-ttu-id="7ffca-p106">若要管理邮箱置于保留状态，您可能需要确定上，以便您可以执行任务，如更改保留持续时间、 临时或永久删除保留项，或从 Office 365 保留策略中排除邮箱置于邮箱的保留项的类型。在这些情况下，第一步是确定邮箱置于保留项的类型。因为可以对单个邮箱放置多个保留 （和不同类型的保留），您必须确定置于邮箱，如果您想要删除或更改这些保留项的所有保留项。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p106">To manage mailboxes on hold, you may have to identify the type of hold that's placed on a mailbox so that you can perform tasks such as changing the hold duration, temporarily or permanently removing the hold, or excluding a mailbox from a Office 365 retention policy. In these cases, the first step is to identify the type of hold placed on the mailbox. And because multiple holds (and different types of holds) can be placed on a single mailbox, you'll have to identify all holds placed on a mailbox if you want to remove or change those holds.</span></span>

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a><span data-ttu-id="7ffca-122">步骤 1： 获取保留项的 GUID 置于邮箱</span><span class="sxs-lookup"><span data-stu-id="7ffca-122">Step 1: Obtaining the GUID for holds placed on a mailbox</span></span>

<span data-ttu-id="7ffca-p107">在 Exchange Online PowerShell 中获取对邮箱置于保留项的 GUID，可以运行以下两个 cmdlet。获取 GUID 后，您使用它来标识在步骤 2 中的特定保留项。请注意，诉讼保留未被标识的 GUID。诉讼保留项是启用或禁用的邮箱。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p107">You can run the following two cmdlets in Exchange Online PowerShell to get the GUID of the holds that are placed on a mailbox. After you obtain a GUID, you use it to identify the specific hold in Step 2. Note that Litigation Holds are not identified by a GUID. Litigation Holds are either enabled or disabled for a mailbox.</span></span>

- <span data-ttu-id="7ffca-p108">**Get-mailbox** -使用此 cmdlet，以确定是否诉讼保留的邮箱启用以及获取 Guid 电子数据展示保留、 就地保留，和 Office 365 专门分配给某个邮箱的保留策略。此 cmdlet 的输出将还指示邮箱是否已明确排除从组织范围内保留策略。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p108">**Get-Mailbox** - Use this cmdlet to determine whether Litigation Hold is enabled for a mailbox and to get the GUIDs for eDiscovery holds, In-Place Holds, and Office 365 retention policies that are specifically assigned to a mailbox. The output of this cmdlet will also indicate if a mailbox has been explicitly excluded from an organization-wide retention policy.</span></span>

- <span data-ttu-id="7ffca-129">**Get-organizationconfig** -使用此 cmdlet 可获取的组织范围内保留策略的 Guid。</span><span class="sxs-lookup"><span data-stu-id="7ffca-129">**Get-OrganizationConfig** - Use this cmdlet to get the GUIDs for organization-wide retention policies.</span></span>

<span data-ttu-id="7ffca-130">要连接到 Exchange Online PowerShell 中，请参阅[Connect to Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="7ffca-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

### <a name="get-mailbox"></a><span data-ttu-id="7ffca-131">Get-Mailbox</span><span class="sxs-lookup"><span data-stu-id="7ffca-131">Get-Mailbox</span></span>

<span data-ttu-id="7ffca-132">运行以下命令以获取有关保留和 Office 365 保留策略应用于邮箱的信息。</span><span class="sxs-lookup"><span data-stu-id="7ffca-132">Run the following command to get information about the holds and Office 365 retention policies applied to a mailbox.</span></span>

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="7ffca-133">如果 InPlaceHolds 属性中有太多值而不是全部显示，则可以运行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令单独占一行上显示每个 GUID。</span><span class="sxs-lookup"><span data-stu-id="7ffca-133">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="7ffca-134">下表介绍了如何确定不同类型的保留项运行**Get-mailbox** cmdlet 时基于*InPlaceHolds*属性中的值。</span><span class="sxs-lookup"><span data-stu-id="7ffca-134">The following table describes how to identify different types of holds based on the values in the *InPlaceHolds* property when you run the **Get-Mailbox** cmdlet.</span></span>


|<span data-ttu-id="7ffca-135">保留类型</span><span class="sxs-lookup"><span data-stu-id="7ffca-135">Hold type</span></span>  |<span data-ttu-id="7ffca-136">示例值</span><span class="sxs-lookup"><span data-stu-id="7ffca-136">Example value</span></span>  |<span data-ttu-id="7ffca-137">如何标识保留项</span><span class="sxs-lookup"><span data-stu-id="7ffca-137">How to identify the hold</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7ffca-138">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="7ffca-138">Litigation Hold</span></span>     |    `True`     |     <span data-ttu-id="7ffca-139">如果*LitigationHoldEnabled*属性设置为诉讼保留的邮箱启用`True`。</span><span class="sxs-lookup"><span data-stu-id="7ffca-139">Litigation Hold is enabled for a mailbox if the *LitigationHoldEnabled* property is set to `True`.</span></span>    |
|<span data-ttu-id="7ffca-140">电子数据展示保留</span><span class="sxs-lookup"><span data-stu-id="7ffca-140">eDiscovery hold</span></span>     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   <span data-ttu-id="7ffca-p109">*InPlaceHolds 属性*包含与电子数据展示事例中安全性和合规性中心关联任何保留项的 GUID。您可以判断这是电子数据展示保留，因为 GUID 开头`UniH`前缀 （这表示统一保留）。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p109">The *InPlaceHolds property* contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center. You can tell this is an eDiscovery hold because the GUID starts with the `UniH` prefix (which denotes a Unified Hold).</span></span>      |
|<span data-ttu-id="7ffca-143">就地保留</span><span class="sxs-lookup"><span data-stu-id="7ffca-143">In-Place Hold</span></span>     |     `c0ba3ce811b6432a8751430937152491` <br/> <span data-ttu-id="7ffca-144">或</span><span class="sxs-lookup"><span data-stu-id="7ffca-144">or</span></span> <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     <span data-ttu-id="7ffca-p110">*InPlaceHolds*属性将包含邮箱置于就地保留的 GUID。您可以判断这是就地保留 GUID 也不会以前缀开头或使用启动，因为`cld`前缀。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p110">The *InPlaceHolds* property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID either doesn't start with a prefix or it starts with the `cld` prefix.</span></span>     |
|<span data-ttu-id="7ffca-147">Office 365 专门应用于邮箱的保留策略</span><span class="sxs-lookup"><span data-stu-id="7ffca-147">Office 365 retention policy specifically applied to the mailbox</span></span>     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> <span data-ttu-id="7ffca-148">或</span><span class="sxs-lookup"><span data-stu-id="7ffca-148">or</span></span> <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     <span data-ttu-id="7ffca-p111">InPlaceHolds 属性将包含任何特定位置的保留策略应用于邮箱的 Guid。您可以标识保留策略，因为 GUID 开头`mbx`或`skp`前缀。`skp`前缀表明到 Skype 应用保留策略的用户的邮箱中的业务对话。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p111">The InPlaceHolds property contains GUIDs of any specific location retention policy that's applied to the mailbox. You can identify retention policies because the GUID starts with the `mbx` or the `skp` prefix. The `skp` prefix indicates that the retention policy is applied to Skype for Business conversations in the user's mailbox.</span></span>    |
|<span data-ttu-id="7ffca-152">从组织范围内的 Office 365 保留策略中排除</span><span class="sxs-lookup"><span data-stu-id="7ffca-152">Excluded from an organization-wide Office 365 retention policy</span></span>     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     <span data-ttu-id="7ffca-153">如果从组织范围内的 Office 365 保留策略中排除邮箱，从排除邮箱的保留策略的 GUID InPlaceHolds 属性中显示，并由`-mbx`前缀。</span><span class="sxs-lookup"><span data-stu-id="7ffca-153">If a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy the mailbox is excluded from is displayed in the InPlaceHolds property and is identified by the `-mbx` prefix.</span></span>    |

### <a name="get-organizationconfig"></a><span data-ttu-id="7ffca-154">Get-organizationconfig</span><span class="sxs-lookup"><span data-stu-id="7ffca-154">Get-OrganizationConfig</span></span>
<span data-ttu-id="7ffca-p112">如果运行**Get-mailbox** cmdlet 时， *InPlaceHolds*属性为空，仍可能存在一个或多个组织范围内 Office 365 保留策略应用于邮箱。运行以下命令在 Exchange Online PowerShell，可以获取 Guid 的列表用于组织范围内的 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p112">If the *InPlaceHolds* property is empty when you run the **Get-Mailbox** cmdlet, there still may be one or more organization-wide Office 365 retention policies applied to the mailbox. Run the following command in Exchange Online PowerShell to get a list of GUIDs for organization-wide Office 365 retention policies.</span></span>

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="7ffca-157">如果 InPlaceHolds 属性中有太多值而不是全部显示，则可以运行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令单独占一行上显示每个 GUID。</span><span class="sxs-lookup"><span data-stu-id="7ffca-157">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="7ffca-158">下表介绍不同类型的组织范围内保留项以及如何确定每种类型基于运行**Get-organizationconfig** cmdlet 时*InPlaceHolds*属性中包含的 Guid。</span><span class="sxs-lookup"><span data-stu-id="7ffca-158">The following table describes the different types of organization-wide holds and how to identify each type based on the GUIDs contained in *InPlaceHolds* property when you run the **Get-OrganizationConfig** cmdlet.</span></span>


|<span data-ttu-id="7ffca-159">保留类型</span><span class="sxs-lookup"><span data-stu-id="7ffca-159">Hold type</span></span>  |<span data-ttu-id="7ffca-160">示例值</span><span class="sxs-lookup"><span data-stu-id="7ffca-160">Example value</span></span>  |<span data-ttu-id="7ffca-161">描述</span><span class="sxs-lookup"><span data-stu-id="7ffca-161">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7ffca-162">Office 365 的保留策略应用于 Exchange 邮箱、 Exchange 公用文件夹和团队聊天</span><span class="sxs-lookup"><span data-stu-id="7ffca-162">Office 365 retention policies applied to Exchange mailboxes, Exchange public folders, and Teams chats</span></span>    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   <span data-ttu-id="7ffca-p113">组织范围内保留策略应用于 Exchange 邮箱，Exchange 公用文件夹和来开始的 Guid 标识 1xN 聊天中的 Microsoft 团队`mbx`前缀。请注意，1xN 聊天存储在单个聊天参与者的邮箱。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p113">Organization-wide retention policies applied to Exchange mailboxes, Exchange public folders, and 1xN chats in Microsoft Teams are identified by GUIDs that start with the `mbx` prefix. Note that 1xN chats are stored in the mailbox of the individual chat participants.</span></span>      |
|<span data-ttu-id="7ffca-165">Office 365 的保留策略应用于 Office 365 组和团队通道邮件</span><span class="sxs-lookup"><span data-stu-id="7ffca-165">Office 365 retention policy applied to Office 365 Groups and Teams channel messages</span></span>     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    <span data-ttu-id="7ffca-p114">由开头的 Guid 标识组织范围内保留策略应用于 Office 365 组和 Microsoft 团队中的通道邮件`grp`前缀。请注意，通道消息存储在与 Microsoft 团队相关联的组邮箱。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p114">Organization-wide retention policies applied to Office 365 groups and channel messages in Microsoft Teams are identified by GUIDs that start with the `grp` prefix. Note that channel messages are stored in the group mailbox that is associated with a Microsoft Team.</span></span>     |

<span data-ttu-id="7ffca-168">有关详细信息保留策略应用于的 Microsoft 团队，请参阅"团队位置"部分[的保留策略概述](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。</span><span class="sxs-lookup"><span data-stu-id="7ffca-168">For more information retention policies applied to Microsoft Teams, see the "Teams location" section [Overview of retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a><span data-ttu-id="7ffca-169">了解保留策略的 InPlaceHolds 值的格式</span><span class="sxs-lookup"><span data-stu-id="7ffca-169">Understanding the format of the InPlaceHolds value for retention policies</span></span>

<span data-ttu-id="7ffca-p115">前缀 （mbx、 skp 或组） 的标识为 Office 365 保留策略的 InPlaceHolds 属性中的项目，除了值还包含后缀标识配置策略的保留操作的类型。例如，下面的示例中以粗体突出显示的操作后缀：</span><span class="sxs-lookup"><span data-stu-id="7ffca-p115">In addition to the prefix (mbx, skp, or grp) that identifies an item in the InPlaceHolds property as an Office 365 retention policy, the value also contains a suffix that identifies the type of retention action that's configured for the policy. For example, the action suffix is highlighted in bold type in the following examples:</span></span>

   <span data-ttu-id="7ffca-172">`skp127d7cf1076947929bf136b7a2a8c36f`**: 1**</span><span class="sxs-lookup"><span data-stu-id="7ffca-172">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span></span>

   <span data-ttu-id="7ffca-173">`mbx7cfb30345d454ac0a989ab3041051209`**: 2**</span><span class="sxs-lookup"><span data-stu-id="7ffca-173">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span></span>

   <span data-ttu-id="7ffca-174">`grp1a0a132ee8944501a4bb6a452ec31171`**: 3**</span><span class="sxs-lookup"><span data-stu-id="7ffca-174">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span></span>

<span data-ttu-id="7ffca-175">下表定义的三种可能的保留期操作：</span><span class="sxs-lookup"><span data-stu-id="7ffca-175">The following table defines the three possible retention actions:</span></span>

|<span data-ttu-id="7ffca-176">值</span><span class="sxs-lookup"><span data-stu-id="7ffca-176">Value</span></span>  |<span data-ttu-id="7ffca-177">描述</span><span class="sxs-lookup"><span data-stu-id="7ffca-177">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="7ffca-178">**1**</span><span class="sxs-lookup"><span data-stu-id="7ffca-178">**1**</span></span>     | <span data-ttu-id="7ffca-179">指示保留策略配置为删除的项目;策略不会保留的项目。</span><span class="sxs-lookup"><span data-stu-id="7ffca-179">Indicates the retention policy is configured to delete items; the policy doesn't retain items.</span></span>        |
|<span data-ttu-id="7ffca-180">**2**</span><span class="sxs-lookup"><span data-stu-id="7ffca-180">**2**</span></span>    |    <span data-ttu-id="7ffca-181">指示保留策略已配置为容纳项目;保留期过后，策略不会删除项目。</span><span class="sxs-lookup"><span data-stu-id="7ffca-181">Indicates the retention policy is configured to hold items; the policy doesn't delete items after the retention period expires.</span></span>     |
|<span data-ttu-id="7ffca-182">**3**</span><span class="sxs-lookup"><span data-stu-id="7ffca-182">**3**</span></span>     |   <span data-ttu-id="7ffca-183">指示保留策略配置为保留项目，然后再删除它们的保留期过后。</span><span class="sxs-lookup"><span data-stu-id="7ffca-183">Indicates the retention policy is configured to hold items and then delete them after the retention period expires.</span></span>      |

<span data-ttu-id="7ffca-184">有关保留操作的详细信息，请参阅[Overview of 保留策略](retention-policies.md#retaining-content-for-a-specific-period-of-time)中的"在特定时间内的保留内容"部分。</span><span class="sxs-lookup"><span data-stu-id="7ffca-184">For more information about retention actions, see the "Retaining content for a specific period of time" section in [Overview of retention policies](retention-policies.md#retaining-content-for-a-specific-period-of-time).</span></span>
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a><span data-ttu-id="7ffca-185">步骤 2： 使用 GUID 标识保留项</span><span class="sxs-lookup"><span data-stu-id="7ffca-185">Step 2: Using the GUID to identify the hold</span></span>

<span data-ttu-id="7ffca-p116">获取应用于邮箱的保留 GUID 后下, 一步是使用该 GUID 标识保留项。使用保留 GUID，以下各节显示如何标识保留项 （和其他信息） 的名称。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p116">After you obtain the GUID for a hold that is applied to a mailbox, the next step is to use that GUID to identify the hold. The following sections show how to identify the name of the hold (and other information) by using the hold GUID.</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="7ffca-188">电子数据展示保留项</span><span class="sxs-lookup"><span data-stu-id="7ffca-188">eDiscovery holds</span></span>

<span data-ttu-id="7ffca-p117">若要确定应用于邮箱的电子数据展示保留的安全性和合规性中心 PowerShell 中运行以下命令。使用电子数据展示的 GUID （不包括 UniH 前缀） 保留在步骤 1 中确定。第一个命令创建变量包含保留; 有关信息在其他命令中使用此变量。第二个命令显示与保留电子数据展示事例的名称。第三个命令显示保留项的名称和保留应用于邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p117">Run the following commands in Security & Compliance Center PowerShell to identify an eDiscovery hold that's applied to the mailbox. Use the GUID (not including the UniH prefix) for the eDiscovery hold that you identified in Step 1. The first command creates a variable that contains information about the hold; this variable is used in the other commands. The second command displays the name of the eDiscovery case the hold is associated with. The third command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

<span data-ttu-id="7ffca-194">若要连接到安全性和合规性中心 PowerShell，请参阅[连接到 Office 365 安全性和合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="7ffca-194">To connect to Security & Compliance Center PowerShell, see  [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

### <a name="in-place-holds"></a><span data-ttu-id="7ffca-195">就地保留</span><span class="sxs-lookup"><span data-stu-id="7ffca-195">In-Place Holds</span></span>

<span data-ttu-id="7ffca-p118">在 Exchange Online PowerShell 中标识应用于邮箱就地保留中运行以下命令。使用您在步骤 1 中确定的就地保留的 GUID。该命令显示的保留项的名称和保留应用于邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p118">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's applied to the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1. The command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
<span data-ttu-id="7ffca-199">请注意，如果 GUID 的就地保留开头`cld`前缀，请确保包含前缀，运行上述命令时。</span><span class="sxs-lookup"><span data-stu-id="7ffca-199">Note that if the GUID for the In-Place Hold starts with the `cld` prefix, be sure to include the prefix when running the previous command.</span></span>

### <a name="office-365-retention-policies"></a><span data-ttu-id="7ffca-200">Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="7ffca-200">Office 365 retention policies</span></span>

<span data-ttu-id="7ffca-p119">运行以下命令安全性和合规性中心 PowerShell 中标识应用于邮箱的 Office 365 保留策略 （组织范围内或特定位置）。使用您在步骤 1 中确定的 GUID （不包括 mbx、 skp 或组前缀或的操作后缀）。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p119">Run the following command in Security & Compliance Center PowerShell to identity the Office 365 retention policy (organization-wide or specific location) that's applied to the mailbox. Use the GUID (not including the mbx, skp, or grp prefix or the action suffix) that you identified in Step 1.</span></span>

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="next-steps"></a><span data-ttu-id="7ffca-203">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7ffca-203">Next steps</span></span>

<span data-ttu-id="7ffca-p120">确定应用于邮箱的保留项后，您可以执行任务更改的保留项的持续时间临时或永久删除保留项，如或 Office 365 保留策略，对于从策略中排除非活动邮箱。有关执行到保留项相关的任务的详细信息，请参阅以下主题之一：</span><span class="sxs-lookup"><span data-stu-id="7ffca-p120">After you identify the holds that are applied to a mailbox, you can perform tasks such as changing the duration of the hold, temporarily or permanently removing the hold, or in the case of Office 365 retention policies, excluding an inactive mailbox from the policy. For more information about performing tasks related to holds, see the one of the following topics:</span></span>

- <span data-ttu-id="7ffca-p121">运行[集 RetentionCompliancePolicy AddExchangeLocationException\<用户邮箱 >](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)中排除的组织范围内的 Office 365 保留策略的邮箱的安全性和合规性中心 PowerShell 命令。请注意，此命令可仅用于保留策略其中*ExchangeLocation*属性的值等于`All`。</span><span class="sxs-lookup"><span data-stu-id="7ffca-p121">Run the [Set-RetentionCompliancePolicy -AddExchangeLocationException \<user mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) command in Security & Compliance Center PowerShell to exclude a mailbox from an organization-wide Office 365 retention policy. Note that this command can only be used for retention policies where the value for the *ExchangeLocation* property equals `All`.</span></span>

- <span data-ttu-id="7ffca-208">运行[Set-mailbox ExcludeFromOrgHolds\<前缀或后缀不保留 GUID >](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)命令在 Exchange Online PowerShell 中排除的组织范围内的 Office 365 保留策略的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="7ffca-208">Run the [Set-Mailbox -ExcludeFromOrgHolds \<hold GUID without prefix or suffix>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide Office 365 retention policy.</span></span>

- [<span data-ttu-id="7ffca-209">更改在 Office 365 中的非活动邮箱的保留持续时间</span><span class="sxs-lookup"><span data-stu-id="7ffca-209">Change the hold duration for an inactive mailbox in Office 365</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="7ffca-210">删除 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="7ffca-210">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

- [<span data-ttu-id="7ffca-211">删除保留状态云邮箱的“可恢复的项目”文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="7ffca-211">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)

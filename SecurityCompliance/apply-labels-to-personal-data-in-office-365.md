---
title: 向 Office 365 中的个人数据应用标签
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何使用 Office 标签作为 GDPR 保护计划的一部分。
ms.openlocfilehash: e31cd420fe476ace8031fc2c6e52158762814c7a
ms.sourcegitcommit: ef27da3ea5340d6e7a2eaa1288e2e005ef8e4788
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2019
ms.locfileid: "30789427"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a><span data-ttu-id="194ba-103">向 Office 365 中的个人数据应用标签</span><span class="sxs-lookup"><span data-stu-id="194ba-103">Apply labels to personal data in Office 365</span></span>

 <span data-ttu-id="194ba-104">如果你使用分类标签作为 GDPR 保护计划的一部分，请使用此主题。</span><span class="sxs-lookup"><span data-stu-id="194ba-104">Use this topic if you are using classification labels as part of your GDPR protection plan.</span></span> 

<span data-ttu-id="194ba-105">如果要在 Office 365 中使用标签保护个人数据，Microsoft 建议你开始使用[保留标签](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="194ba-105">If you are using labels for protection of personal data in Office 365, Microsoft recommends you start with [retention labels](labels.md).</span></span> <span data-ttu-id="194ba-106">借助保留标签，你可以：</span><span class="sxs-lookup"><span data-stu-id="194ba-106">With retention labels, you can:</span></span>
- <span data-ttu-id="194ba-107">使用“高级数据治理”根据敏感信息类型或其他条件自动应用标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-107">Use Advanced Data Governance to automatically apply labels based on sensitive information types or other criteria.</span></span>
-  <span data-ttu-id="194ba-108">使用具有数据丢失防护的保留标签来应用保护。</span><span class="sxs-lookup"><span data-stu-id="194ba-108">Use retention labels with data loss prevention to apply protection.</span></span> 
- <span data-ttu-id="194ba-109">在电子数据展示和内容搜索中使用标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-109">Use labels with eDiscovery and Content Search.</span></span> 
- <span data-ttu-id="194ba-110">通过 Cloud App Security 使用标签和敏感信息类型来监控驻留在其他 SaaS 应用中的个人数据。</span><span class="sxs-lookup"><span data-stu-id="194ba-110">Use both labels and sensitive information types with Cloud App Security to monitor personal data that resides in other SaaS apps.</span></span>

<span data-ttu-id="194ba-111">目前建议使用[敏感度标签](sensitivity-labels.md)为本地和其他云服务及提供程序中的文件应用标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-111">[Sensitivity labels](sensitivity-labels.md) are currently recommended for applying labels to files on premises and in other cloud services and providers.</span></span> <span data-ttu-id="194ba-112">对于在 Office 365 中需要通过 Azure 信息保护 (AIP) 加密来保护数据的文件（如商业机密文件），也建议使用这些标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-112">These are also recommended for files in Office 365 that require Azure Information Protection (AIP) encryption for data protection, such as trade secret files.</span></span>

<span data-ttu-id="194ba-113">目前，对于 Office 365 中包含受 GDPR 约束的数据的文件，建议不要使用 Azure 信息保护来应用加密。</span><span class="sxs-lookup"><span data-stu-id="194ba-113">At this time, using Azure Information Protection to apply Azure RMS encryption is not recommended for files in Office 365 with data that is subject to the GDPR. Office 365 services currently cannot read into RMS-encrypted files. Therefore, the service can’t find sensitive data in these files.</span></span> <span data-ttu-id="194ba-114">Office 365 服务目前无法读入 AIP 加密的文件。</span><span class="sxs-lookup"><span data-stu-id="194ba-114">Office 365 services currently cannot read into AIP-encrypted files.</span></span> <span data-ttu-id="194ba-115">因此，该服务无法在这些文件中找到敏感数据。</span><span class="sxs-lookup"><span data-stu-id="194ba-115">Therefore, the service can’t find sensitive data in these files.</span></span>

<span data-ttu-id="194ba-116">敏感度标签可以应用于 Exchange Online 中的邮件，并且这些标签可与 Office 365 数据丢失防护功能一起使用。</span><span class="sxs-lookup"><span data-stu-id="194ba-116">Sensitivity labels can be applied to mail in Exchange Online and these labels work with Office 365 data loss prevention.</span></span> 

![Office 365 标签和 Azure 信息保护标签](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)


<span data-ttu-id="194ba-118">在此图中：</span><span class="sxs-lookup"><span data-stu-id="194ba-118">In the illustration:</span></span>

-   <span data-ttu-id="194ba-119">在 SharePoint Online 和 OneDrive for Business 中为个人数据、严格监管的文件和商业机密文件使用保留标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-119">Use Office 365 labels for personal data and for highly regulated & trade secret files in SharePoint Online and OneDrive for Business.</span></span>

-   <span data-ttu-id="194ba-120">为严格监管的文件和商业机密文件、Exchange Online 电子邮件、其他 SaaS 服务中的文件、本地数据中心内的文件以及其他云提供程序中的文件使用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-120">Use Azure Information Protection (AIP) labels for highly regulated & trade secret files, Exchange Online email, files in other SaaS services, files in on-premises datacenters, and files in other cloud providers.</span></span>


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a><span data-ttu-id="194ba-121">在 Microsoft 365 中使用保留标签和敏感信息类型进行信息保护</span><span class="sxs-lookup"><span data-stu-id="194ba-121">Use Office labels and sensitive information types across Microsoft 365 for information protection</span></span>

<span data-ttu-id="194ba-122">下图显示了如何在标签策略、数据丢失防护策略和 Cloud App Security 策略中使用保留标签和敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="194ba-122">The following illustration shows how Office labels and sensitive information types can be used in label policies, data loss prevention policies, and with Cloud App Security policies.</span></span>

![Office 标签和敏感信息类型](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="194ba-124">为便于访问，下表提供了上图中的相同示例。</span><span class="sxs-lookup"><span data-stu-id="194ba-124">For accessibility, the following table provides the same examples in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="194ba-125"><strong>分类元素</strong></span><span class="sxs-lookup"><span data-stu-id="194ba-125"><strong>Classification elements</strong></span></span></th>
<th align="left"><span data-ttu-id="194ba-126"><strong>标签策略 — 2 个示例</strong></span><span class="sxs-lookup"><span data-stu-id="194ba-126"><strong>Label policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="194ba-127"><strong>数据丢失防护策略 — 2 个示例</strong></span><span class="sxs-lookup"><span data-stu-id="194ba-127"><strong>Data loss prevention policies — 2 examples</strong></span></span></th>
<th align="left"><span data-ttu-id="194ba-128"><strong>适用于所有 SaaS 应用的 Cloud App Security 策略 — 1 个示例</strong></span><span class="sxs-lookup"><span data-stu-id="194ba-128"><strong>Cloud App Security policies for all SaaS apps — 1 example</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="194ba-129">保留标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-129">Retention labels</span></span> <span data-ttu-id="194ba-130">示例：个人、公共、客户数据、人力资源数据、机密、高度机密</span><span class="sxs-lookup"><span data-stu-id="194ba-130">Office labels. Examples: Personal, Public, Customer data, HR data, Confidential, Highly confidential</span></span></td>
<td align="left"><p><span data-ttu-id="194ba-p105">自动将此标签 . . .</span><span class="sxs-lookup"><span data-stu-id="194ba-p105">Auto apply this label . . .</span></span></p>
<p><span data-ttu-id="194ba-134">客户数据</span><span class="sxs-lookup"><span data-stu-id="194ba-134">Customer data</span></span></p>
<p><span data-ttu-id="194ba-p106">. . . 应用于与这些敏感信息类型匹配的文档 . . .</span><span class="sxs-lookup"><span data-stu-id="194ba-p106">. . . to documents that match these sensitive information types . . .</span></span></p>
<p><span data-ttu-id="194ba-141">&lt;敏感信息类型示例列表&gt;</span><span class="sxs-lookup"><span data-stu-id="194ba-141">&lt;list of example sensitive information types&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="194ba-p107">将此保护 . . .</span><span class="sxs-lookup"><span data-stu-id="194ba-p107">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="194ba-145">&lt;定义保护&gt;</span><span class="sxs-lookup"><span data-stu-id="194ba-145">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="194ba-p108">. . . 应用于带此标签的文档 . . .</span><span class="sxs-lookup"><span data-stu-id="194ba-p108">. . . to documents with this label . . .</span></span></p>
<p><span data-ttu-id="194ba-152">客户数据</span><span class="sxs-lookup"><span data-stu-id="194ba-152">Customer data</span></span></p></td>
<td align="left"><p><span data-ttu-id="194ba-p109">在以下情况下发出警报：当批准的 SaaS 应用中的带这些属性的文件 . . .</span><span class="sxs-lookup"><span data-stu-id="194ba-p109">Alert when files with these attributes . . .</span></span></p>
<p><span data-ttu-id="194ba-156">&lt;预定义的 PII 属性或自定义表达式&gt;</span><span class="sxs-lookup"><span data-stu-id="194ba-156">&lt;predefined PII attribute -or- custom expression&gt;</span></span></p>
<p><span data-ttu-id="194ba-p110">. . . 被共享到组织外部时</span><span class="sxs-lookup"><span data-stu-id="194ba-p110">. . . in any sanctioned SaaS app are shared outside the organization</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="194ba-p111">敏感信息类型示例：比利时国家/地区号码、信用卡号、克罗地亚身份证号、芬兰国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="194ba-p111">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</span></span></td>
<td align="left"><p><span data-ttu-id="194ba-p112">发布这些标签，以便用户手动将 . . .</span><span class="sxs-lookup"><span data-stu-id="194ba-p112">Publish these labels for users to manually apply . . .</span></span></p>
<p><span data-ttu-id="194ba-166">&lt;选择标签&gt;</span><span class="sxs-lookup"><span data-stu-id="194ba-166">&lt;select labels&gt;</span></span></p>
<p><span data-ttu-id="194ba-p113">. . . 应用于这些位置 . . .</span><span class="sxs-lookup"><span data-stu-id="194ba-p113">. . . to these locations . . .</span></span></p>
<p><span data-ttu-id="194ba-173">&lt;所有位置或选择特定位置&gt;</span><span class="sxs-lookup"><span data-stu-id="194ba-173">&lt;all locations or choose specific locations&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="194ba-p114">将此保护 . . .</span><span class="sxs-lookup"><span data-stu-id="194ba-p114">Apply this protection . . .</span></span></p>
<p><span data-ttu-id="194ba-177">&lt;定义保护&gt;</span><span class="sxs-lookup"><span data-stu-id="194ba-177">&lt;define protection&gt;</span></span></p>
<p><span data-ttu-id="194ba-p115">. . . 应用于与这些敏感信息类型匹配的文档&gt;</span><span class="sxs-lookup"><span data-stu-id="194ba-p115">. . . to documents that match these sensitive information types&gt;</span></span></p></td>
<td align="left"><span data-ttu-id="194ba-182">注意：Cloud App Security 中即将推出的属性包括 Office 365 敏感信息类型和 Office 365 及 Azure 信息保护中的统一标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-182">Note: Attributes coming soon to Cloud App Security include Office 365 sensitive information types and Unified labels across Office 365 and Azure Information Protection.</span></span></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a><span data-ttu-id="194ba-183">设置自动应用标签策略的优先级</span><span class="sxs-lookup"><span data-stu-id="194ba-183">Prioritize auto-apply label policies</span></span>

<span data-ttu-id="194ba-p116">对于受 GDPR 制约的个人数据，Microsoft 建议使用为环境策展的敏感信息类型自动应用标签。请务必精心设计和谨慎测试自动应用标签策略，以确保实现预期目标行为。</span><span class="sxs-lookup"><span data-stu-id="194ba-p116">For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.</span></span>

<span data-ttu-id="194ba-p117">创建自动应用策略的顺序以及用户是否也会应用这些标签，这两点会影响结果。因此，请务必认真规划策略的展示。以下是需要注意的事项。</span><span class="sxs-lookup"><span data-stu-id="194ba-p117">The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it is important to carefully plan the roll-out. Here’s what you need to know.</span></span>

### <a name="one-label-at-a-time"></a><span data-ttu-id="194ba-188">一次使用一个标签</span><span class="sxs-lookup"><span data-stu-id="194ba-188">One label at a time</span></span>

<span data-ttu-id="194ba-189">对一个文档只能分配一个标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-189">You can only assign one label to a document.</span></span>

### <a name="older-auto-apply-policies-win"></a><span data-ttu-id="194ba-190">旧的自动应用策略优先</span><span class="sxs-lookup"><span data-stu-id="194ba-190">Older auto-apply policies win</span></span>

<span data-ttu-id="194ba-p118">如果有多个分配自动应用标签的规则且内容符合多个规则的条件，将分配最旧的规则的标签。因此，配置标签策略前请务必先认真进行规划。如果组织需要更改标签策略的优先级，需要删除这些策略，然后重新创建策略。</span><span class="sxs-lookup"><span data-stu-id="194ba-p118">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it is important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they will need to delete and recreate them.</span></span>

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a><span data-ttu-id="194ba-194">用户手动应用的标签优先于自动应用的标签</span><span class="sxs-lookup"><span data-stu-id="194ba-194">Manual user-applied labels trump auto-applied labels</span></span>

<span data-ttu-id="194ba-p119">用户手动应用的标签优先于自动应用的标签。自动应用策略无法替换用户已应用的标签。用户可以替换自动应用的标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-p119">Manual user applied labels trump auto-applied labels. Auto-apply policies cannot replace a label that is already applied by a user. Users can replace labels that are auto-applied.</span></span>

### <a name="auto-assigned-labels-can-be-updated"></a><span data-ttu-id="194ba-198">可以更新自动分配的标签</span><span class="sxs-lookup"><span data-stu-id="194ba-198">Auto-assigned labels can be updated</span></span>

<span data-ttu-id="194ba-199">可以通过更加新的标签策略或通过更新现有策略来更新自动分配的标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-199">Auto-assigned labels can be updated by either newer label policies or by updates to existing policies.</span></span>

<span data-ttu-id="194ba-200">确保使用标签的计划包括以下事项：</span><span class="sxs-lookup"><span data-stu-id="194ba-200">Be sure your plan for implementing labels includes:</span></span>

-   <span data-ttu-id="194ba-201">设置自动应用策略创建顺序的优先级。</span><span class="sxs-lookup"><span data-stu-id="194ba-201">Prioritizing the order that auto-apply policies are created.</span></span>

-   <span data-ttu-id="194ba-p120">预留足够的时间，以便可以在展示标签供用户手动应用前自动应用这些标签。标签应用于符合条件的所有内容最多可能需要 7 天。</span><span class="sxs-lookup"><span data-stu-id="194ba-p120">Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.</span></span>

### <a name="example-priority-for-creating-the-auto-apply-policies"></a><span data-ttu-id="194ba-204">用于创建自动应用策略的优先级示例</span><span class="sxs-lookup"><span data-stu-id="194ba-204">Example priority for creating the auto-apply policies</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="194ba-205"><strong>标签</strong></span><span class="sxs-lookup"><span data-stu-id="194ba-205"><strong>Labels</strong></span></span></th>
<th align="left"><span data-ttu-id="194ba-206"><strong>创建自动应用策略的优先级顺序</strong></span><span class="sxs-lookup"><span data-stu-id="194ba-206"><strong>Priority order to create auto-apply policies</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="194ba-207">人力资源 — 员工数据</span><span class="sxs-lookup"><span data-stu-id="194ba-207">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="194ba-208">1</span><span class="sxs-lookup"><span data-stu-id="194ba-208">-1</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="194ba-209">客户数据</span><span class="sxs-lookup"><span data-stu-id="194ba-209">Customer Data</span></span></td>
<td align="left"><span data-ttu-id="194ba-210">2</span><span class="sxs-lookup"><span data-stu-id="194ba-210">2.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="194ba-211">高度机密</span><span class="sxs-lookup"><span data-stu-id="194ba-211">Highly Confidential</span></span></td>
<td align="left"><span data-ttu-id="194ba-212">3</span><span class="sxs-lookup"><span data-stu-id="194ba-212">3.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="194ba-213">人力资源 — 薪资数据</span><span class="sxs-lookup"><span data-stu-id="194ba-213">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="194ba-214">4</span><span class="sxs-lookup"><span data-stu-id="194ba-214">4.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="194ba-215">机密</span><span class="sxs-lookup"><span data-stu-id="194ba-215">Confidential</span></span></td>
<td align="left"><span data-ttu-id="194ba-216">5</span><span class="sxs-lookup"><span data-stu-id="194ba-216">5.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="194ba-217">公开</span><span class="sxs-lookup"><span data-stu-id="194ba-217">Public</span></span></td>
<td align="left"><span data-ttu-id="194ba-218">6</span><span class="sxs-lookup"><span data-stu-id="194ba-218">6.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="194ba-219">个人</span><span class="sxs-lookup"><span data-stu-id="194ba-219">Personal</span></span></td>
<td align="left"><span data-ttu-id="194ba-220">无自动应用策略</span><span class="sxs-lookup"><span data-stu-id="194ba-220">No auto-apply policy</span></span></td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a><span data-ttu-id="194ba-221">创建标签和自动应用标签策略</span><span class="sxs-lookup"><span data-stu-id="194ba-221">Create labels and auto-apply label policies</span></span>

<span data-ttu-id="194ba-222">在安全与合规中心中创建标签和策略。</span><span class="sxs-lookup"><span data-stu-id="194ba-222">Create labels and policies in the Security & Compliance Center.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="194ba-223"><strong>步骤</strong></span><span class="sxs-lookup"><span data-stu-id="194ba-223"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="194ba-224"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="194ba-224"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="194ba-225">向合规性团队成员提供权限。</span><span class="sxs-lookup"><span data-stu-id="194ba-225">Give permissions to members of your compliance team.</span></span></p></td>
<td align="left"><p><span data-ttu-id="194ba-p121">创建标签的合规性团队成员需要使用安全与合规中心的权限。请转到安全与合规中心中的“权限”，然后修改符合性管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="194ba-p121">Members of your compliance team who will create labels need permissions to use the Security &amp; Compliance Center. Go to Permissions in Security and Compliance Center and modify the members of the Compliance Administrator group.</span></span></p>
<p><span data-ttu-id="194ba-228">请参阅<a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">向用户授予对 Office 365 安全与合规中心的访问权限</a>。</span><span class="sxs-lookup"><span data-stu-id="194ba-228">See <a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">Give users access to the Office 365 Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="194ba-229">创建保留标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-229">Create retention labels.</span></span></p></td>
<td align="left"><span data-ttu-id="194ba-230">转到安全与合规中心的“分类”，选择“保留标签”，然后为你的环境创建标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-230">Go to Classifications in Security and Compliance Center, choose Labels, and create the labels for your environment.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="194ba-231">为标签创建自动应用策略。</span><span class="sxs-lookup"><span data-stu-id="194ba-231">Create auto-apply policies for labels.</span></span></p></td>
<td align="left"><span data-ttu-id="194ba-p122">转到安全与合规中心中的“分类”，选择“标签策略”，然后为自动应用标签创建策略。请务必按优先级顺序创建这些策略。</span><span class="sxs-lookup"><span data-stu-id="194ba-p122">Go to Classification in Security and Compliance Center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="194ba-234">下图显示了如何为客户数据标签创建自动应用策略。</span><span class="sxs-lookup"><span data-stu-id="194ba-234">The following illustration shows how to create an auto-apply label for the Customer data label.</span></span>

![创建和应用客户数据标签](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="194ba-236">在此图中：</span><span class="sxs-lookup"><span data-stu-id="194ba-236">In the illustration:</span></span>

-   <span data-ttu-id="194ba-237">创建了“客户数据”标签。</span><span class="sxs-lookup"><span data-stu-id="194ba-237">The “Customer data” label is created.</span></span>

-   <span data-ttu-id="194ba-238">列出了针对 GDPR 的所需敏感信息类型：比利时国家/地区号码、信用卡号码、克罗地亚身份证号、芬兰国家/地区身份证号码。</span><span class="sxs-lookup"><span data-stu-id="194ba-238">The desired sensitive information types for GDPR are listed: Belgium National Number, Credit Card Number, Croatia Identity Card Number, Finland National ID.</span></span>

-   <span data-ttu-id="194ba-239">创建自动应用策略，将标签“客户数据”分配给包括添加到策略的敏感信息类型之一的任何文件。</span><span class="sxs-lookup"><span data-stu-id="194ba-239">Create an auto-apply policy assigns the label “Customer data” to any file that includes one of the sensitive information types that you add to the policy.</span></span>

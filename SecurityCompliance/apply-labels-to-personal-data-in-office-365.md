---
title: 向 Office 365 中的个人数据应用标签
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
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
ms.openlocfilehash: 518e5352861242bfbf9220f876edcb4b616493df
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598248"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a>向 Office 365 中的个人数据应用标签

 如果你使用分类标签作为 GDPR 保护计划的一部分，请使用此主题。 

如果要在 Office 365 中使用标签保护个人数据，Microsoft 建议你开始使用[保留标签](labels.md)。 借助保留标签，你可以：
- 使用“高级数据治理”根据敏感信息类型或其他条件自动应用标签。
- 使用具有数据丢失防护的保留标签来应用保护。 
- 在电子数据展示和内容搜索中使用标签。 

Cloud App Security 当前不支持保留标签，但你可以通过 Cloud App Security 使用 Office 365 敏感信息，以监控驻留在其他 SaaS 应用上的个人数据。

目前建议使用[敏感度标签](sensitivity-labels.md)为本地和其他云服务及提供程序中的文件应用标签。 同时建议将这些标签用于 Office 365 中需要 Azure 信息保护加密来保护数据的文件，例如贸易机密文件。

目前，对于 Office 365 中包含受 GDPR 约束的数据的文件，建议不要使用 Azure 信息保护来应用加密。 Office 365 服务目前无法读入 AIP 加密的文件。 因此，该服务无法在这些文件中找到敏感数据。

保留标签可以应用于 Exchange Online 中的邮件，并且这些标签可与 Office 365 数据丢失防护功能一起使用。 

![Office 365 标签和 Azure 信息保护标签](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)


在此图中：

-   在 SharePoint Online 和 OneDrive for Business 中为个人数据、严格监管的文件和商业机密文件使用保留标签。
-   可以通过 Cloud App Security 在 Office 365 中使用 Office 365 敏感信息类型，以监控驻留在其他 SaaS 应用中的个人数据。
-   为严格监管的文件和商业机密文件、Exchange Online 电子邮件、其他 SaaS 服务中的文件、本地数据中心内的文件以及其他云提供程序中的文件使用敏感度标签。


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a>在 Microsoft 365 中使用保留标签和敏感信息类型进行信息保护

下图显示了如何在标签策略、数据丢失防护策略和 Cloud App Security 策略中使用保留标签和敏感信息类型。

![Office 标签和敏感信息类型](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

为便于访问，下表提供了上图中的相同示例。

<table>
<thead>
<tr class="header">
<th align="left"><strong>分类元素</strong></th>
<th align="left"><strong>标签策略 — 2 个示例</strong></th>
<th align="left"><strong>数据丢失防护策略 — 2 个示例</strong></th>
<th align="left"><strong>适用于所有 SaaS 应用的 Cloud App Security 策略 — 1 个示例</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">保留标签。 示例：个人、公共、客户数据、人力资源数据、机密、高度机密</td>
<td align="left"><p>自动将此标签 . . .</p>
<p>客户数据</p>
<p>. . . 应用于与这些敏感信息类型匹配的文档 . . .</p>
<p>&lt;敏感信息类型示例列表&gt;</p></td>
<td align="left"><p>将此保护 . . .</p>
<p>&lt;定义保护&gt;</p>
<p>. . . 应用于带此标签的文档 . . .</p>
<p>客户数据</p></td>
<td align="left"><p>在以下情况下发出警报：当批准的 SaaS 应用中的带这些属性的文件 . . .</p>
<p>选择一个或多个属性：预定义的 PII 属性、Office 365 敏感信息类型、敏感性标签 (AIP)、自定义表达式</p>
<p>。 。 。 （组织外部共享的任何批准 SaaS 应用中）</p><p>注释：保留标签当前在 Cloud App Security 中不受支持。</td>
</tr>
<tr class="even">
<td align="left">敏感信息类型示例：比利时国家/地区号码、信用卡号、克罗地亚身份证号、芬兰国家/地区身份证号码</td>
<td align="left"><p>发布这些标签，以便用户手动将 . . .</p>
<p>&lt;选择标签&gt;</p>
<p>. . . 应用于这些位置 . . .</p>
<p>&lt;所有位置或选择特定位置&gt;</p></td>
<td align="left"><p>将此保护 . . .</p>
<p>&lt;定义保护&gt;</p>
<p>. . . 应用于与这些敏感信息类型匹配的文档&gt;</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a>设置自动应用标签策略的优先级

对于受 GDPR 制约的个人数据，Microsoft 建议使用为环境策展的敏感信息类型自动应用标签。请务必精心设计和谨慎测试自动应用标签策略，以确保实现预期目标行为。

创建自动应用策略的顺序以及用户是否也会应用这些标签，这两点会影响结果。因此，请务必认真规划策略的展示。以下是需要注意的事项。

### <a name="one-label-at-a-time"></a>一次使用一个标签

对一个文档只能分配一个标签。

### <a name="older-auto-apply-policies-win"></a>旧的自动应用策略优先

如果有多个分配自动应用标签的规则且内容符合多个规则的条件，将分配最旧的规则的标签。因此，配置标签策略前请务必先认真进行规划。如果组织需要更改标签策略的优先级，需要删除这些策略，然后重新创建策略。

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a>用户手动应用的标签优先于自动应用的标签

用户手动应用的标签优先于自动应用的标签。自动应用策略无法替换用户已应用的标签。用户可以替换自动应用的标签。

### <a name="auto-assigned-labels-can-be-updated"></a>可以更新自动分配的标签

可以通过更加新的标签策略或通过更新现有策略来更新自动分配的标签。

确保使用标签的计划包括以下事项：

-   设置自动应用策略创建顺序的优先级。

-   预留足够的时间，以便可以在展示标签供用户手动应用前自动应用这些标签。标签应用于符合条件的所有内容最多可能需要 7 天。

### <a name="example-priority-for-creating-the-auto-apply-policies"></a>用于创建自动应用策略的优先级示例

<table>
<thead>
<tr class="header">
<th align="left"><strong>标签</strong></th>
<th align="left"><strong>创建自动应用策略的优先级顺序</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">人力资源 — 员工数据</td>
<td align="left">1</td>
</tr>
<tr class="even">
<td align="left">客户数据</td>
<td align="left">2</td>
</tr>
<tr class="odd">
<td align="left">高度机密</td>
<td align="left">3</td>
</tr>
<tr class="even">
<td align="left">人力资源 — 薪资数据</td>
<td align="left">4</td>
</tr>
<tr class="odd">
<td align="left">机密</td>
<td align="left">5</td>
</tr>
<tr class="even">
<td align="left">公开</td>
<td align="left">6</td>
</tr>
<tr class="odd">
<td align="left">个人</td>
<td align="left">无自动应用策略</td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a>创建标签和自动应用标签策略

在安全中心或合规中心中创建标签和策略。

<table>
<thead>
<tr class="header">
<th align="left"><strong>步骤</strong></th>
<th align="left"><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>向合规性团队成员提供权限。</p></td>
<td align="left"><p>将创建标签的合规性团队成员需要使用安全中心和/或合规中心的权限。请转到安全中心或合规中心中的“权限”，然后修改合规性管理员组的成员。</p>
<p>请参阅<a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">为用户授予访问安全中心和/或合规中心的权限</a>。</p></td>
</tr>
<tr class="even">
<td align="left"><p>创建保留标签。</p></td>
<td align="left">转到安全中心或合规中心中的“分类”，选择“保留标签”，然后为你的环境创建标签。</td>
</tr>
<tr class="odd">
<td align="left"><p>为标签创建自动应用策略。</p></td>
<td align="left">转到安全中心或合规中心中的“分类”，选择“标签策略”，然后为自动应用标签创建策略。请务必按优先级顺序创建这些策略。</td>
</tr>
</tbody>
</table>

下图显示了如何为客户数据标签创建自动应用策略。

![创建和应用客户数据标签](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

在此图中：

-   创建了“客户数据”标签。

-   列出了针对 GDPR 的所需敏感信息类型：比利时国家/地区号码、信用卡号码、克罗地亚身份证号、芬兰国家/地区身份证号码。

-   创建自动应用策略，将标签“客户数据”分配给包括添加到策略的敏感信息类型之一的任何文件。

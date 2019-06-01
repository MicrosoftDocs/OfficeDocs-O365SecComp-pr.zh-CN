---
title: 信息屏障策略的属性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用本文作为对可在信息屏障策略中使用的各种属性的参考。
ms.openlocfilehash: e72e37950442974897de479c7c11f0053a578d1c
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668280"
---
# <a name="attributes-for-information-barrier-policies-preview"></a>信息屏障策略的属性 (预览)

Azure Active Directory 中的某些属性可用于分段用户。 然后, 将段用作信息屏障策略的筛选器。 例如, 您可以使用**部门**按组织中的部门定义用户的分段 (假设没有一个员工同时适用于两个部门)。 

本文提供可使用的属性的列表。 若要了解有关信息障碍的详细信息, 请参阅以下资源:
- [信息障碍 (预览)](information-barriers.md)
- [为 Microsoft 团队中的信息障碍定义策略 (预览)](information-barriers-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>如何在信息屏障策略中使用属性

本文中列出的属性可用于定义 (或编辑) 用户的各个部分。 在信息屏障策略中, 段用作参数 (UserGroupFilter), 如以下示例所示:

|示例  |Cmdlet  |
|---------|---------|
|使用部门属性定义名为 Segment1 的段     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
|使用 MemberOf 属性定义名为 SegmentA 的段 (假定此属性包含组名称, 例如 "BlueGroup")     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
|使用 ExtensionAttribute1 定义名为 DayTraders 的段 (假设此属性包含职务, 如 "DayTrader")|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

在定义段时, 请对所有段使用相同的属性。 例如, 如果使用*部门*定义一些分段, 则使用*部门*定义所有分段。 请勿使用使用*MemberOf*的*部门*和其他部门定义某些分段。 请确保您的段不重叠;应将每个用户仅分配给一个分段。 

若要了解详细信息, 请参阅[使用 PowerShell 定义分段](information-barriers-policies.md#define-segments-using-powershell)。

## <a name="reference"></a>参考

下表列出了可用于信息障碍的属性。

|Azure Active Directory 属性名称 (LDAP 显示名称)  |Exchange 属性名称  |
|---------|---------|
|合著       | 合著        |
|Company     |公司         |
|Department     |Department         |
|ExtensionAttribute1 |CustomAttribute1  |
|ExtensionAttribute2 |CustomAttribute2  |
|ExtensionAttribute3 |CustomAttribute3  |
|ExtensionAttribute4 |CustomAttribute4  |
|ExtensionAttribute5 |CustomAttribute5  |
|ExtensionAttribute6 |CustomAttribute6  |
|ExtensionAttribute7 |CustomAttribute7  |
|ExtensionAttribute8 |CustomAttribute8  |
|ExtensionAttribute9 |CustomAttribute9  |
|ExtensionAttribute10 |CustomAttribute10  |
|ExtensionAttribute11 |CustomAttribute11  |
|ExtensionAttribute12 |CustomAttribute12  |
|ExtensionAttribute13 |CustomAttribute13  |
|ExtensionAttribute14 |CustomAttribute14  |
|ExtensionAttribute15 |CustomAttribute15  |
|MSExchExtensionCustomAttribute1 |ExtensionCustomAttribute1 |
|MSExchExtensionCustomAttribute2 |ExtensionCustomAttribute2 |
|MSExchExtensionCustomAttribute3 |ExtensionCustomAttribute3 |
|MSExchExtensionCustomAttribute4 |ExtensionCustomAttribute4 |
|MSExchExtensionCustomAttribute5 |ExtensionCustomAttribute5 |
|MailNickname |别名 |
|PhysicalDeliveryOfficeName |Office |
|PostalCode |PostalCode |
|ProxyAddresses |EmailAddresses |
|StreetAddress |StreetAddress |
|TargetAddress |ExternalEmailAddress |
|UsageLocation |UsageLocation |
|UserPrincipalName  |UserPrincipalName  |
|邮件   |WindowsEmailAddress    |
|说明    |说明    |
|MemberOf   |MemberOfGroup  |

## <a name="related-topics"></a>相关主题

[为 Microsoft 团队中的信息障碍定义策略 (预览)](information-barriers-policies.md)

[解决信息障碍 (预览)](information-barriers-troubleshooting.md)

[信息障碍 (预览)](information-barriers.md)




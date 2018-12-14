---
title: 对敏感信息的新 Office 365 邮件加密策略
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 12/13/2018
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 新 Office 365 邮件加密的策略的敏感信息。
ms.openlocfilehash: 180050d1bf9303f6d29bc126e66ac53211c2fb34
ms.sourcegitcommit: 3aae959ea1ac5ef61a9942c681d334831e6b6038
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2018
ms.locfileid: "27271088"
---
# <a name="new-office-365-message-encryption-policy-for-sensitive-information"></a>对敏感信息的新 Office 365 邮件加密策略

我们将创建一个新的自动策略将应用于所有电子邮件包含敏感信息和的组织外部发送的 Office 365 邮件加密的 Office 365 租户中。此新的 Exchange 邮件流规则将自动创建在 Office 365 租户，以便将默认情况下保护您的组织。

## <a name="how-will-this-work"></a>如何将此工作？

您的组织将在 Office 365 邮件中心通知您在您的租户中将在其创建此自动策略日期收到通知。将为您提供至少 30 天通知，并且必须将以退出选项。您可能要退出可能的方案，如果您已扫描的敏感类型的第三方数据丢失防护解决方案。

## <a name="new-policy-details"></a>新策略的详细信息

将您将自动加密转与组织外部的电子邮件的组织中创建一个新的 Exchange 邮件流规则*仅加密*如果它们包含下列敏感信息类型的策略：

- ABA 银行代号
- 信用卡号
- 药品实施机构 (DEA) 号码
- 美国 / 英国护照号码
- 美国银行帐号
- 美国单独的纳税人标识号 (ITIN)
- 美国社会保险号 (SSN)

> [!Note]
> 精确敏感类型可能由您组织的区域设置不同，并将传送邮件中心通知中。

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>需要执行的操作，此更改准备的什么？

不需要更新或修改任何现有的 Office 365 配置设置，此新的更改之前。但是，您可能要更新任何适用的最终用户文档和准备在此更改组织中的人员的培训资料。

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a>如何将此更改表示审核日志中？

此活动审核，并且可供客户。 操作 ' 新建 TransportRule'，下面是示例审核条目中安全性和合规性中心的审核日志搜索的代码段：

|     |
| --- |
| *{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345"，"RecordType": 1，"ResultStatus":"True"，"UserKey":"Microsoft 运算符"、"UserType": 3，"版本": 1，"工作负荷":"Exchange"、"ClientIP":"123.456.147.68:17584"，"ObjectId":""，"UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"名称":"组织"，"值":"123456 221 d-12346"{"名称":"ApplyRightsProtectionTemplate"，"值":"加密"}，{"名称":"Name"，"值":"加密 （外出框规则） 的出站敏感电子邮件"}，{"名称":"MessageContainsDataClassifications"等。*
 |

## <a name="how-do-i-opt-out"></a>我如何退出？

如果您想要选择退出此更改，请按照以下步骤：

1. 以全局管理员角色具有的用户连接到[Exchange Online PowerShell 中](https://aka.ms/exopowershell)。
2.  身份验证后运行下面的代码：

    ```
    Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
    ```

## <a name="how-do-i-disable-the-automatic-policy"></a>如何禁用自动策略？

如果您未选择退出此更改，并且已创建 Exchange 邮件规则，您可以[禁用相应的规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)，转到**邮件流** > **规则**中 Exchange 管理员中心 (EAC) 和禁用规则"*加密出站敏感的电子邮件 （外出框规则）*"。

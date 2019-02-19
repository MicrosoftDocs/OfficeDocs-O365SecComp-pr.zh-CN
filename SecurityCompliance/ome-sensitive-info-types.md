---
title: 适用于敏感信息的 Office 365 邮件加密策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/31/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '摘要: 敏感信息类型的 Office 365 邮件加密策略现已可用。'
ms.openlocfilehash: e2a72ee85ca65a2fe8ae1543979b51915ff0a88f
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2019
ms.locfileid: "29696196"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a>适用于敏感信息的 Office 365 邮件加密策略

Update (1/30/19): 在10月 2018, 我们使用一个较小的客户示例来了解, 我们能否通过基于某些敏感信息类型自动加密敏感电子邮件来简化保护工作。根据此示例中的积极反馈, 我们决定在12月2018的租户中扩展到更广泛的租户配置文件。在将下一阶段传递给选择租户后, 我们会听取你的反馈意见, 并确定具有更复杂的环境的客户更谨慎地实施规则, 因此我们可以调整我们的计划。

如果您的组织是在2019年1月15日的开始阶段选择的, 我们将不会推出自动策略。相反, 我们在本文中提供了有关如何完成向后进行部署的说明。请继续阅读, 了解如何操作。

||
|:-----|
|本文是有关 Office 365 邮件加密的更多系列文章的一部分。本文适用于管理员和 ITPros。如果只是查找有关发送或接收加密邮件的信息, 请参阅[Office 365 邮件加密 (OME)](ome.md)中的文章列表, 并找到最符合您的需求的文章。 |
||

## <a name="how-to-create-the-sensitive-information-type-policy-for-your-tenant"></a>如何为租户创建敏感信息类型策略

您可以使用 Exchange 邮件流规则或 Office 365 数据丢失防护 (DLP) 创建敏感信息类型策略。若要创建 exchange 邮件流规则, 可以使用 exchange 管理中心 (EAC) 或 PowerShell。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a>使用 EAC 中的邮件流规则创建策略

登录到 Exchange 管理中心 (EAC), 然后转到 "**邮件流** > **规则**"。根据邮件或附件中存在的某些关键字或敏感信息类型, 创建应用 Office 365 邮件加密的规则。

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a>使用 PowerShell 中的邮件流规则创建策略

在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。使用 get-irmconfiguration 和 TransporRule cmdlet 创建策略。

### <a name="example-mail-flow-rule-created-with-powershell"></a>使用 PowerShell 创建的邮件流规则示例

在 PowerShell 中运行以下命令创建一个 Exchange 邮件流规则, 以便在电子邮件或其附件包含以下** 敏感信息时自动对传出组织外部的电子邮件进行加密策略信息类型:

- ABA 传送号码
- 信用卡号
- 药品实施代理 (DEA) 号码
- 美国/英国护照号码
- 美国银行帐户编号
- 美国单独的纳税人标识号 (ITIN)
- 美国社会保险号 (SSN)

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a>收件人如何访问附件

邮件加密后, 收件人在访问并打开其加密电子邮件后, 将对附件具有不受限制的访问权限。

## <a name="to-prepare-for-this-change"></a>准备进行此更改

您可能需要更新任何适用的最终用户文档和培训材料, 以便为组织中的人员提供此更改的准备。根据需要, 与您的用户共享这些 Office 365 邮件加密资源:

- [在 Outlook for PC 中发送、查看和回复加密邮件](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [office 365 Essentials 视频: office 邮件加密](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a>在审核日志中查看这些更改

此活动将被审核, 并可用于 Office 365 管理员。该操作是 "new-transportrule" 和安全 & 合规性中心的 "审核日志搜索" 中的示例审核条目的代码段:

|     |
| --- |
| *{"CreationTime": "2018-11-28T23:35:01", "Id": "a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c", "Operation": "New-new-transportrule", "OrganizationId": "123456-221d-12345", "RecordType": 1, "ResultStatus": "True", "UserKey": "Microsoft Operator", "UserType ": 3," Version ": 1," 工作负荷 ":" Exchange "," ClientIP ":" 123.456.147.68: 17584 "," ObjectId ":" "," UserId ":" Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso, .onmicrosoft "," OriginatingServer ":" CY4PR13MBXXXX (15.20.1382.008) "," 参数 ": {" name ":" Organization "," Value ":" 221d-12346 "{" name ":" ApplyRightsProtectionTemplate "," value ":" 加密 "}, {" name ":" name "," value ":" 加密出站敏感电子邮件 (开箱规则) "}, {" 名称 ":"MessageContainsDataClassifications ".。。如此.* |
| |

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a>禁用或自定义敏感信息类型策略

创建 exchange 邮件流规则后, 可以通过转到 exchange 管理中心 (EAC) 中的**邮件流** > **规则**来[禁用或编辑规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule), 并禁用该规则 "*对出站敏感电子邮件进行加密" ("开箱即用" 规则)*".

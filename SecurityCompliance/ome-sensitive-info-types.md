---
title: 适用于敏感信息的 Office 365 邮件加密策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/31/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '摘要: 敏感信息类型的 Office 365 邮件加密策略现已可用。'
ms.openlocfilehash: 99cb7a9f94c9cf4036c11b74a5208ddf0e819ceb
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213974"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="2da5c-103">适用于敏感信息的 Office 365 邮件加密策略</span><span class="sxs-lookup"><span data-stu-id="2da5c-103">Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="2da5c-p101">Update (1/30/19): 在10月 2018, 我们使用一个较小的客户示例来了解, 我们能否通过基于某些敏感信息类型自动加密敏感电子邮件来简化保护工作。根据此示例中的积极反馈, 我们决定在12月2018的租户中扩展到更广泛的租户配置文件。在将下一阶段传递给选择租户后, 我们会听取你的反馈意见, 并确定具有更复杂的环境的客户更谨慎地实施规则, 因此我们可以调整我们的计划。</span><span class="sxs-lookup"><span data-stu-id="2da5c-p101">Update (1/30/19): In October 2018, we worked with a small sample of customers to understand if we can simplify protection by automatically encrypting sensitive emails based on certain sensitive information types. Based on positive feedback from this sample, we decided to expand to a more diverse profile of tenants in December 2018. After communicating the next roll-out to select tenants, we listened to your feedback and determined that customers with more complex environments wanted to implement the rules more cautiously, and we are therefore adjusting our plans.</span></span>

<span data-ttu-id="2da5c-p102">如果您的组织是在2019年1月15日的开始阶段选择的, 我们将不会推出自动策略。相反, 我们在本文中提供了有关如何完成向后进行部署的说明。请继续阅读, 了解如何操作。</span><span class="sxs-lookup"><span data-stu-id="2da5c-p102">If your organization was selected for the roll-out starting January 15, 2019, we will not roll out the automatic policy. Instead, we are providing instructions in this article on how you can complete the roll-out yourselves. Keep reading to find out how.</span></span>

||
|:-----|
|<span data-ttu-id="2da5c-p103">本文是有关 Office 365 邮件加密的更多系列文章的一部分。本文适用于管理员和 ITPros。如果只是查找有关发送或接收加密邮件的信息, 请参阅[Office 365 邮件加密 (OME)](ome.md)中的文章列表, 并找到最符合您的需求的文章。</span><span class="sxs-lookup"><span data-stu-id="2da5c-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="how-to-create-the-sensitive-information-type-policy-for-your-tenant"></a><span data-ttu-id="2da5c-113">如何为租户创建敏感信息类型策略</span><span class="sxs-lookup"><span data-stu-id="2da5c-113">How to create the sensitive information type policy for your tenant</span></span>

<span data-ttu-id="2da5c-p104">您可以使用 Exchange 邮件流规则或 Office 365 数据丢失防护 (DLP) 创建敏感信息类型策略。若要创建 exchange 邮件流规则, 可以使用 exchange 管理中心 (EAC) 或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2da5c-p104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create the sensitive information type policy. To create an Exchange mail flow rule you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="2da5c-116">使用 EAC 中的邮件流规则创建策略</span><span class="sxs-lookup"><span data-stu-id="2da5c-116">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="2da5c-p105">登录到 Exchange 管理中心 (EAC), 然后转到 "**邮件流** > **规则**"。根据邮件或附件中存在的某些关键字或敏感信息类型, 创建应用 Office 365 邮件加密的规则。</span><span class="sxs-lookup"><span data-stu-id="2da5c-p105">Sign-in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**. There, create a rule that applies Office 365 Message Encryption based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="2da5c-119">使用 PowerShell 中的邮件流规则创建策略</span><span class="sxs-lookup"><span data-stu-id="2da5c-119">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="2da5c-p106">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。使用 get-irmconfiguration 和 TransporRule cmdlet 创建策略。</span><span class="sxs-lookup"><span data-stu-id="2da5c-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell). Use the Set-IRMConfiguration and New-TransporRule cmdlets to create the policy.</span></span>

### <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="2da5c-123">使用 PowerShell 创建的邮件流规则示例</span><span class="sxs-lookup"><span data-stu-id="2da5c-123">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="2da5c-124">在 PowerShell 中运行以下命令创建一个 Exchange 邮件流规则, 以便在电子邮件或其附件包含以下\*\* 敏感信息时自动对传出组织外部的电子邮件进行加密策略信息类型:</span><span class="sxs-lookup"><span data-stu-id="2da5c-124">Running the following commands in PowerShell create an Exchange mail flow rule that automatically encrypts emails going outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="2da5c-125">ABA 传送号码</span><span class="sxs-lookup"><span data-stu-id="2da5c-125">ABA routing number</span></span>
- <span data-ttu-id="2da5c-126">信用卡号</span><span class="sxs-lookup"><span data-stu-id="2da5c-126">Credit card Number</span></span>
- <span data-ttu-id="2da5c-127">药品实施代理 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="2da5c-127">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="2da5c-p107">美国/英国护照号码</span><span class="sxs-lookup"><span data-stu-id="2da5c-p107">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="2da5c-130">美国银行帐户编号</span><span class="sxs-lookup"><span data-stu-id="2da5c-130">U.S. bank account number</span></span>
- <span data-ttu-id="2da5c-131">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="2da5c-131">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="2da5c-132">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="2da5c-132">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="2da5c-133">收件人如何访问附件</span><span class="sxs-lookup"><span data-stu-id="2da5c-133">How recipients access attachments</span></span>

<span data-ttu-id="2da5c-134">邮件加密后, 收件人在访问并打开其加密电子邮件后, 将对附件具有不受限制的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2da5c-134">Once a message is encrypted, recipients will have unrestricted access to attachments once they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="2da5c-135">准备进行此更改</span><span class="sxs-lookup"><span data-stu-id="2da5c-135">To prepare for this change</span></span>

<span data-ttu-id="2da5c-p108">您可能需要更新任何适用的最终用户文档和培训材料, 以便为组织中的人员提供此更改的准备。根据需要, 与您的用户共享这些 Office 365 邮件加密资源:</span><span class="sxs-lookup"><span data-stu-id="2da5c-p108">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change. Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="2da5c-138">在 Outlook for PC 中发送、查看和回复加密邮件</span><span class="sxs-lookup"><span data-stu-id="2da5c-138">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="2da5c-139">office 365 Essentials 视频: office 邮件加密</span><span class="sxs-lookup"><span data-stu-id="2da5c-139">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="2da5c-140">在审核日志中查看这些更改</span><span class="sxs-lookup"><span data-stu-id="2da5c-140">View these changes in the Audit log</span></span>

<span data-ttu-id="2da5c-p109">此活动将被审核, 并可用于 Office 365 管理员。该操作是 "new-transportrule" 和安全 & 合规性中心的 "审核日志搜索" 中的示例审核条目的代码段:</span><span class="sxs-lookup"><span data-stu-id="2da5c-p109">This activity is audited and is available to Office 365 administrators. The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="2da5c-143">*{"CreationTime": "2018-11-28T23:35:01", "Id": "a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c", "Operation": "New-new-transportrule", "OrganizationId": "123456-221d-12345", "RecordType": 1, "ResultStatus": "True", "UserKey": "Microsoft Operator", "UserType ": 3," Version ": 1," 工作负荷 ":" Exchange "," ClientIP ":" 123.456.147.68: 17584 "," ObjectId ":" "," UserId ":" Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso, .onmicrosoft "," OriginatingServer ":" CY4PR13MBXXXX (15.20.1382.008) "," 参数 ": {" name ":" Organization "," Value ":" 221d-12346 "{" name ":" ApplyRightsProtectionTemplate "," value ":" 加密 "}, {" name ":" name "," value ":" 加密出站敏感电子邮件 (开箱规则) "}, {" 名称 ":"MessageContainsDataClassifications ".。。如此.*</span><span class="sxs-lookup"><span data-stu-id="2da5c-143">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span> |
| |

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="2da5c-144">禁用或自定义敏感信息类型策略</span><span class="sxs-lookup"><span data-stu-id="2da5c-144">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="2da5c-145">创建 exchange 邮件流规则后, 可以通过转到 exchange 管理中心 (EAC) 中的**邮件流** > **规则**来[禁用或编辑规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule), 并禁用该规则 "*对出站敏感电子邮件进行加密" ("开箱即用" 规则)*".</span><span class="sxs-lookup"><span data-stu-id="2da5c-145">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>

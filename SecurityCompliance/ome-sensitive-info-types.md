---
title: 使用 Office 365 邮件加密为组织创建敏感信息类型策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: '摘要: 敏感信息类型的 Office 365 邮件加密策略。'
ms.openlocfilehash: d74712798ba9d46614b5fc916e4b1ce111582304
ms.sourcegitcommit: 73f1db241c0686020167d43442e7b07a2199ea3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "36658118"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a><span data-ttu-id="ac438-103">使用 Office 365 邮件加密为组织创建敏感信息类型策略</span><span class="sxs-lookup"><span data-stu-id="ac438-103">Create a sensitive information type policy for your organization using Office 365 Message Encryption</span></span>

<span data-ttu-id="ac438-104">您可以使用 Exchange 邮件流规则或 Office 365 数据丢失防护 (DLP) 来创建包含 Office 365 邮件加密的敏感信息类型策略。</span><span class="sxs-lookup"><span data-stu-id="ac438-104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="ac438-105">若要创建 Exchange 邮件流规则, 可以使用 Exchange 管理中心 (EAC) 或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ac438-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="ac438-106">使用 EAC 中的邮件流规则创建策略</span><span class="sxs-lookup"><span data-stu-id="ac438-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="ac438-107">登录到 Exchange 管理中心 (EAC), 然后转到 "**邮件流** > **规则**"。</span><span class="sxs-lookup"><span data-stu-id="ac438-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="ac438-108">在 "规则" 页上, 创建应用 Office 365 邮件加密的规则。</span><span class="sxs-lookup"><span data-stu-id="ac438-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="ac438-109">您可以基于条件 (例如, 邮件或附件中存在某些关键字或敏感信息类型) 创建规则。</span><span class="sxs-lookup"><span data-stu-id="ac438-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="ac438-110">使用 PowerShell 中的邮件流规则创建策略</span><span class="sxs-lookup"><span data-stu-id="ac438-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="ac438-111">使用在 Office 365 组织中具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ac438-111">Use a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="ac438-112">有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="ac438-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="ac438-113">使用 Get-irmconfiguration 和 New-transportrule cmdlet 创建策略。</span><span class="sxs-lookup"><span data-stu-id="ac438-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

### <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="ac438-114">使用 PowerShell 创建的邮件流规则示例</span><span class="sxs-lookup"><span data-stu-id="ac438-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="ac438-115">在 PowerShell 中运行以下命令, 以创建一个 Exchange 邮件流规则, 该规则可在电子邮件或其附件包含以下敏感信息时自动对在组织外部发送的电子邮件进行加密 (*仅加密策略)* 各种</span><span class="sxs-lookup"><span data-stu-id="ac438-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="ac438-116">ABA 传送号码</span><span class="sxs-lookup"><span data-stu-id="ac438-116">ABA routing number</span></span>
- <span data-ttu-id="ac438-117">信用卡号</span><span class="sxs-lookup"><span data-stu-id="ac438-117">Credit card Number</span></span>
- <span data-ttu-id="ac438-118">药品实施代理 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="ac438-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="ac438-119">美国/英国</span><span class="sxs-lookup"><span data-stu-id="ac438-119">U.S. / U.K.</span></span> <span data-ttu-id="ac438-120">passport number</span><span class="sxs-lookup"><span data-stu-id="ac438-120">passport number</span></span>
- <span data-ttu-id="ac438-121">美国银行帐户编号</span><span class="sxs-lookup"><span data-stu-id="ac438-121">U.S. bank account number</span></span>
- <span data-ttu-id="ac438-122">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="ac438-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="ac438-123">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="ac438-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="ac438-124">有关详细信息, 请参阅[get-irmconfiguration](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps)和[new-transportrule](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="ac438-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps) and [New-TransportRule](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="ac438-125">收件人如何访问附件</span><span class="sxs-lookup"><span data-stu-id="ac438-125">How recipients access attachments</span></span>

<span data-ttu-id="ac438-126">在 Office 365 对邮件进行加密后, 收件人在访问并打开其加密电子邮件时可以不受限制地访问附件。</span><span class="sxs-lookup"><span data-stu-id="ac438-126">After Office 365 encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="ac438-127">准备进行此更改</span><span class="sxs-lookup"><span data-stu-id="ac438-127">To prepare for this change</span></span>

<span data-ttu-id="ac438-128">您可能需要更新任何适用的最终用户文档和培训材料, 以便为组织中的人员提供此更改的准备。</span><span class="sxs-lookup"><span data-stu-id="ac438-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="ac438-129">根据需要, 与您的用户共享这些 Office 365 邮件加密资源:</span><span class="sxs-lookup"><span data-stu-id="ac438-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="ac438-130">在 Outlook for PC 中发送、查看和回复加密邮件</span><span class="sxs-lookup"><span data-stu-id="ac438-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="ac438-131">Office 365 Essentials 视频: Office 邮件加密</span><span class="sxs-lookup"><span data-stu-id="ac438-131">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="ac438-132">在审核日志中查看这些更改</span><span class="sxs-lookup"><span data-stu-id="ac438-132">View these changes in the Audit log</span></span>

<span data-ttu-id="ac438-133">Office 365 审核此活动并使其可用于 Office 365 管理员。</span><span class="sxs-lookup"><span data-stu-id="ac438-133">Office 365 audits this activity and makes it available to Office 365 administrators.</span></span> <span data-ttu-id="ac438-134">该操作是 "New-transportrule" 和安全 & 合规性中心的审核日志搜索中的示例审核条目的代码片段如下所示:</span><span class="sxs-lookup"><span data-stu-id="ac438-134">The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="ac438-135">禁用或自定义敏感信息类型策略</span><span class="sxs-lookup"><span data-stu-id="ac438-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="ac438-136">创建 exchange 邮件流规则后, 可以通过转到 exchange 管理中心 (EAC) 中的**邮件流** > **规则**来[禁用或编辑规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule), 并禁用该规则 "*对出站敏感电子邮件进行加密" ("开箱即用" 规则)*".</span><span class="sxs-lookup"><span data-stu-id="ac438-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>

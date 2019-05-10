---
title: 使用 Office 365 邮件加密为组织创建敏感信息类型策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
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
ms.openlocfilehash: 44966303ec7c58fdd82f733e1922073de848cf73
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834831"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a><span data-ttu-id="c0fed-103">使用 Office 365 邮件加密为组织创建敏感信息类型策略</span><span class="sxs-lookup"><span data-stu-id="c0fed-103">Create a sensitive information type policy for your organization using Office 365 Message Encryption</span></span>

<span data-ttu-id="c0fed-104">您可以使用 Exchange 邮件流规则或 Office 365 数据丢失防护 (DLP) 来创建包含 Office 365 邮件加密的敏感信息类型策略。</span><span class="sxs-lookup"><span data-stu-id="c0fed-104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="c0fed-105">若要创建 Exchange 邮件流规则, 可以使用 Exchange 管理中心 (EAC) 或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c0fed-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="c0fed-106">使用 EAC 中的邮件流规则创建策略</span><span class="sxs-lookup"><span data-stu-id="c0fed-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="c0fed-107">登录到 Exchange 管理中心 (EAC), 然后转到 "**邮件流** > **规则**"。</span><span class="sxs-lookup"><span data-stu-id="c0fed-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="c0fed-108">在 "规则" 页上, 创建应用 Office 365 邮件加密的规则。</span><span class="sxs-lookup"><span data-stu-id="c0fed-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="c0fed-109">您可以基于条件 (例如, 邮件或附件中存在某些关键字或敏感信息类型) 创建规则。</span><span class="sxs-lookup"><span data-stu-id="c0fed-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="c0fed-110">使用 PowerShell 中的邮件流规则创建策略</span><span class="sxs-lookup"><span data-stu-id="c0fed-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="c0fed-111">使用在 Office 365 组织中具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="c0fed-111">Use a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="c0fed-112">有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="c0fed-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="c0fed-113">使用 Get-irmconfiguration 和 New-transportrule cmdlet 创建策略。</span><span class="sxs-lookup"><span data-stu-id="c0fed-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

### <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="c0fed-114">使用 PowerShell 创建的邮件流规则示例</span><span class="sxs-lookup"><span data-stu-id="c0fed-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="c0fed-115">在 PowerShell 中运行以下命令, 以创建一个 Exchange 邮件流规则, 该规则可在电子邮件或其附件包含以下敏感信息时自动对在组织外部发送的电子邮件进行加密 (*仅加密策略)* 各种</span><span class="sxs-lookup"><span data-stu-id="c0fed-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="c0fed-116">ABA 传送号码</span><span class="sxs-lookup"><span data-stu-id="c0fed-116">ABA routing number</span></span>
- <span data-ttu-id="c0fed-117">信用卡号</span><span class="sxs-lookup"><span data-stu-id="c0fed-117">Credit card Number</span></span>
- <span data-ttu-id="c0fed-118">药品实施代理 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="c0fed-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="c0fed-119">美国/英国</span><span class="sxs-lookup"><span data-stu-id="c0fed-119">U.S. / U.K.</span></span> <span data-ttu-id="c0fed-120">passport number</span><span class="sxs-lookup"><span data-stu-id="c0fed-120">passport number</span></span>
- <span data-ttu-id="c0fed-121">美国银行帐户编号</span><span class="sxs-lookup"><span data-stu-id="c0fed-121">U.S. bank account number</span></span>
- <span data-ttu-id="c0fed-122">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="c0fed-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="c0fed-123">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="c0fed-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentsForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="c0fed-124">收件人如何访问附件</span><span class="sxs-lookup"><span data-stu-id="c0fed-124">How recipients access attachments</span></span>

<span data-ttu-id="c0fed-125">在 Office 365 对邮件进行加密后, 收件人在访问并打开其加密电子邮件时可以不受限制地访问附件。</span><span class="sxs-lookup"><span data-stu-id="c0fed-125">After Office 365 encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="c0fed-126">准备进行此更改</span><span class="sxs-lookup"><span data-stu-id="c0fed-126">To prepare for this change</span></span>

<span data-ttu-id="c0fed-127">您可能需要更新任何适用的最终用户文档和培训材料, 以便为组织中的人员提供此更改的准备。</span><span class="sxs-lookup"><span data-stu-id="c0fed-127">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="c0fed-128">根据需要, 与您的用户共享这些 Office 365 邮件加密资源:</span><span class="sxs-lookup"><span data-stu-id="c0fed-128">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="c0fed-129">在 Outlook for PC 中发送、查看和回复加密邮件</span><span class="sxs-lookup"><span data-stu-id="c0fed-129">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="c0fed-130">Office 365 Essentials 视频: Office 邮件加密</span><span class="sxs-lookup"><span data-stu-id="c0fed-130">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="c0fed-131">在审核日志中查看这些更改</span><span class="sxs-lookup"><span data-stu-id="c0fed-131">View these changes in the Audit log</span></span>

<span data-ttu-id="c0fed-132">Office 365 审核此活动并使其可用于 Office 365 管理员。</span><span class="sxs-lookup"><span data-stu-id="c0fed-132">Office 365 audits this activity and makes it available to Office 365 administrators.</span></span> <span data-ttu-id="c0fed-133">该操作是 "New-transportrule" 和安全 & 合规性中心的 "审核日志搜索" 中的示例审核条目的代码段:</span><span class="sxs-lookup"><span data-stu-id="c0fed-133">The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="c0fed-134">禁用或自定义敏感信息类型策略</span><span class="sxs-lookup"><span data-stu-id="c0fed-134">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="c0fed-135">创建 exchange 邮件流规则后, 可以通过转到 exchange 管理中心 (EAC) 中的**邮件流** > **规则**来[禁用或编辑规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule), 并禁用该规则 "*对出站敏感电子邮件进行加密" ("开箱即用" 规则)*".</span><span class="sxs-lookup"><span data-stu-id="c0fed-135">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>

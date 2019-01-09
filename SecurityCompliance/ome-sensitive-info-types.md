---
title: 对敏感信息的新 Office 365 邮件加密策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/7/2019
ROBOTS: NOINDEX, NOFOLLOW
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 自动应用于 Office 365 邮件加密策略向所有租户推出的敏感信息类型。
ms.openlocfilehash: f5996707d1cafe8dc1bf90856878de0a4fb7b77b
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "27752080"
---
# <a name="office-365-message-encryption-policy-for-sensitive-information"></a><span data-ttu-id="d288c-103">Office 365 邮件加密敏感信息策略</span><span class="sxs-lookup"><span data-stu-id="d288c-103">Office 365 Message Encryption policy for sensitive information</span></span>

<span data-ttu-id="d288c-p101">我们将创建一个新的自动策略将应用于所有电子邮件包含敏感信息和的组织外部发送的 Office 365 邮件加密的 Office 365 租户中。此新的 Exchange 邮件流规则将自动创建在 Office 365 租户，以便将默认情况下保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="d288c-p101">We will be creating a new automatic policy in Office 365 tenants that will apply Office 365 Message Encryption to all emails that contain sensitive information and that are being sent outside your organization. This new Exchange mail flow rule will be automatically created in your Office 365 tenant so that your organization will be protected by default.</span></span>

## <a name="when-to-expect-the-update-for-your-tenant"></a><span data-ttu-id="d288c-106">预计您的租户的更新</span><span class="sxs-lookup"><span data-stu-id="d288c-106">When to expect the update for your tenant</span></span>

<span data-ttu-id="d288c-p102">您的组织将在 Office 365 邮件中心通知您在您的租户中将在其创建此自动策略日期收到通知。将为您提供至少 30 天通知，并且必须将以退出选项。您可能要退出可能的方案，如果您已扫描的敏感类型的第三方数据丢失防护解决方案。更高版本中这篇文章提供了有关如何选择退出的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="d288c-p102">Your organization will receive a notification in the Office 365 Message Center notifying you the date on which this automatic policy will be created in your tenant. You will be given at least a 30-day notice and you will also have the option to opt-out. A scenario in which you may want to potentially opt out is if you have a 3rd-party Data Loss Prevention solution that already scans for sensitive types. More details on how to opt-out are available later in this article.</span></span>

## <a name="sensitive-information-type-policy-details"></a><span data-ttu-id="d288c-110">敏感信息类型策略的详细信息</span><span class="sxs-lookup"><span data-stu-id="d288c-110">Sensitive information type policy details</span></span>

<span data-ttu-id="d288c-111">Exchange 邮件流规则将创建组织中的将自动加密转与组织外部的电子邮件*仅加密*如果它们包含下列敏感信息类型的策略：</span><span class="sxs-lookup"><span data-stu-id="d288c-111">An Exchange mail flow rule will be created in your organization that will automatically encrypt emails going outside your organization with the *Encrypt-Only* policy if they contain the following sensitive information types:</span></span>

- <span data-ttu-id="d288c-112">ABA 银行代号</span><span class="sxs-lookup"><span data-stu-id="d288c-112">ABA routing number</span></span>
- <span data-ttu-id="d288c-113">信用卡号</span><span class="sxs-lookup"><span data-stu-id="d288c-113">Credit card Number</span></span>
- <span data-ttu-id="d288c-114">药品实施机构 (DEA) 号码</span><span class="sxs-lookup"><span data-stu-id="d288c-114">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="d288c-p103">美国 / 英国护照号码</span><span class="sxs-lookup"><span data-stu-id="d288c-p103">U.S. / U.K. passport number</span></span>
- <span data-ttu-id="d288c-117">美国银行帐号</span><span class="sxs-lookup"><span data-stu-id="d288c-117">U.S. bank account number</span></span>
- <span data-ttu-id="d288c-118">美国单独的纳税人标识号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="d288c-118">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="d288c-119">美国社会保险号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="d288c-119">U.S. Social Security Number (SSN)</span></span>

> [!Note]
> <span data-ttu-id="d288c-120">精确敏感类型可能由您组织的区域设置不同，并将传送邮件中心通知中。</span><span class="sxs-lookup"><span data-stu-id="d288c-120">The exact sensitive types may differ by your organization’s locale and will be communicated in the Message Center notification.</span></span>

## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="d288c-121">需要执行的操作，此更改准备的什么？</span><span class="sxs-lookup"><span data-stu-id="d288c-121">What do I need to do to prepare for this change?</span></span>

<span data-ttu-id="d288c-p104">不需要更新或修改任何现有的 Office 365 配置设置，此新的更改之前。但是，您可能要更新任何适用的最终用户文档和准备在此更改组织中的人员的培训资料。与根据用户共享这些 Office 365 邮件加密资源：</span><span class="sxs-lookup"><span data-stu-id="d288c-p104">You do not have to update or modify any existing Office 365 configuration settings prior to this new change. However, you may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change. Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="d288c-125">发送、 查看和回复加密邮件在 Outlook 中的 PC</span><span class="sxs-lookup"><span data-stu-id="d288c-125">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="d288c-126">Office 365 Essentials 视频： Office 邮件加密</span><span class="sxs-lookup"><span data-stu-id="d288c-126">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="how-will-this-change-be-represented-in-the-audit-log"></a><span data-ttu-id="d288c-127">如何将此更改表示审核日志中？</span><span class="sxs-lookup"><span data-stu-id="d288c-127">How will this change be represented in the Audit log?</span></span>

<span data-ttu-id="d288c-p105">此活动审核，并且可供客户。 操作 ' 新建 TransportRule'，下面是示例审核条目中安全性和合规性中心的审核日志搜索的代码段：</span><span class="sxs-lookup"><span data-stu-id="d288c-p105">This activity is audited and is available to customers.  The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

|     |
| --- |
| <span data-ttu-id="d288c-130">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345"，"RecordType": 1，"ResultStatus":"True"，"UserKey":"Microsoft 运算符"、"UserType": 3，"版本": 1，"工作负荷":"Exchange"、"ClientIP":"123.456.147.68:17584"，"ObjectId":""，"UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"名称":"组织"，"值":"123456 221 d-12346"{"名称":"ApplyRightsProtectionTemplate"，"值":"加密"}，{"名称":"Name"，"值":"加密 （外出框规则） 的出站敏感电子邮件"}，{"名称":"MessageContainsDataClassifications"等。*</span><span class="sxs-lookup"><span data-stu-id="d288c-130">*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*</span></span>
 |

## <a name="how-do-i-opt-out"></a><span data-ttu-id="d288c-131">我如何退出？</span><span class="sxs-lookup"><span data-stu-id="d288c-131">How do I opt-out?</span></span>

<span data-ttu-id="d288c-132">如果您想要选择退出此更改，请按照以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d288c-132">If you would like to opt-out of this change, please follow these steps:</span></span>

1. <span data-ttu-id="d288c-p106">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，请启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="d288c-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>
2. <span data-ttu-id="d288c-135">运行 Set-irmconfiguration cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d288c-135">Run the Set-IRMConfiguration cmdlet as follows:</span></span>

   ```
   Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
   ```

## <a name="how-do-i-disable-the-automatic-policy"></a><span data-ttu-id="d288c-136">如何禁用自动策略？</span><span class="sxs-lookup"><span data-stu-id="d288c-136">How do I disable the automatic policy?</span></span>

<span data-ttu-id="d288c-137">如果您未选择退出此更改，并且已创建 Exchange 邮件规则，您可以[禁用相应的规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)，转到**邮件流** > **规则**中 Exchange 管理员中心 (EAC) 和禁用规则"*加密出站敏感的电子邮件 （外出框规则）*"。</span><span class="sxs-lookup"><span data-stu-id="d288c-137">If you didn’t opt-out of this change and the Exchange mail rule has already been created, you can [disable the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>

---
title: Office 365 高级邮件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Office 365 中的高级邮件加密帮助组织通过 Office 365 web 门户向加密电子邮件过期并撤销访问权限, 从而帮助组织满足其合规性义务。
ms.openlocfilehash: 5559a2bca4cd804cfcfdf547146eeb416252ca5f
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834901"
---
# <a name="office-365-advanced-message-encryption"></a><span data-ttu-id="a0c28-103">Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="a0c28-103">Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="a0c28-104">Office 365 高级邮件加密在特定订阅中的 Office 365 邮件加密的顶层可用。</span><span class="sxs-lookup"><span data-stu-id="a0c28-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="a0c28-105">[Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)e5、Office 365 企业版 E5 和 Office 365 教育版 A5 中包含高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="a0c28-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="a0c28-106">如果您的组织有一个不包含 Office 365 高级邮件加密的 Office 365 订阅, 则可以将高级邮件加密作为加载项进行购买, 使其具有高级合规性 SKU 的 E5 合规性。</span><span class="sxs-lookup"><span data-stu-id="a0c28-106">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="a0c28-107">Office 365 中的高级邮件加密帮助客户满足法规遵从性义务, 这些要求对外部收件人和其加密电子邮件的访问权限要求更灵活的控制。</span><span class="sxs-lookup"><span data-stu-id="a0c28-107">Advanced Message Encryption in Office 365 helps customers meet compliance obligations that require more flexible controls over external recipients and their access to encrypted emails.</span></span> <span data-ttu-id="a0c28-108">使用 Office 365 中的高级邮件加密, 可以控制使用自动策略在组织外共享的敏感电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a0c28-108">With Advanced Message Encryption in Office 365, you can control sensitive emails shared outside the organization with automatic policies.</span></span> <span data-ttu-id="a0c28-109">您可以配置这些策略以标识敏感信息类型 (如 PII、财务或运行状况 Id), 也可以使用关键字来增强保护。</span><span class="sxs-lookup"><span data-stu-id="a0c28-109">You configure these policies to identify sensitive information types such as PII, Financial, or Health IDs, or you can use keywords to enhance protection.</span></span> <span data-ttu-id="a0c28-110">配置策略后, 您可以使用自定义品牌的电子邮件模板对策略进行配对, 然后添加一个到期日期, 以对符合该策略的电子邮件进行更多控制。</span><span class="sxs-lookup"><span data-stu-id="a0c28-110">Once you've configured the policies, you pair policies with custom branded email templates and then add an expiration date for extra control of emails that fit the policy.</span></span> <span data-ttu-id="a0c28-111">此外, 管理员可以随时撤销对邮件的访问权限, 从而进一步控制在外部通过安全 web 门户访问的加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a0c28-111">Also, admins can further control encrypted emails accessed externally through a secure web portal by revoking access to the mail at any time.</span></span>

<span data-ttu-id="a0c28-112">您只能撤销和设置发送给外部收件人的电子邮件的到期日期。</span><span class="sxs-lookup"><span data-stu-id="a0c28-112">You can only revoke and set an expiration date for emails sent to external recipients.</span></span>

<span data-ttu-id="a0c28-113">使用 Office 365 高级邮件加密时, 无论您何时应用自定义品牌打造模板, Office 365 都会对适合您应用该模板的邮件流规则的电子邮件应用包装。</span><span class="sxs-lookup"><span data-stu-id="a0c28-113">With Office 365 Advanced Message Encryption, anytime you apply a custom branding template, Office 365 applies a wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="a0c28-114">您只能撤消邮件并将到期日期应用到用户通过门户接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="a0c28-114">You can only revoke messages and apply expiration dates to messages that users receive through the portal.</span></span> <span data-ttu-id="a0c28-115">也就是说, 应用了自定义品牌打造模板的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a0c28-115">In other words, email that has a custom branding template applied.</span></span>

## <a name="get-started-with-office-365-advanced-message-encryption"></a><span data-ttu-id="a0c28-116">开始使用 Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="a0c28-116">Get started with Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="a0c28-117">下列主题介绍了如何设置和使用高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="a0c28-117">The following topics describe how you set up and use Advanced Message Encryption.</span></span>

<span data-ttu-id="a0c28-118">您的组织必须具有包含 Office 365 高级邮件加密的订阅。</span><span class="sxs-lookup"><span data-stu-id="a0c28-118">Your organization must have a subscription that includes Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="a0c28-119">有关受支持订阅的详细信息, 请参阅[邮件策略和合规性服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="a0c28-119">For detailed information about supported subscriptions, see the [Message policy and compliance service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

<span data-ttu-id="a0c28-120">如果尚未设置 Office 365 邮件加密, 请参阅[设置新的 office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c28-120">If you do not have Office 365 Message Encryption set up already, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="a0c28-121">[为通过 Office 365 高级邮件加密加密的电子邮件设置到期日期](ome-advanced-expiration.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c28-121">[Set an expiration date for email encrypted by Office 365 Advanced Message Encryption](ome-advanced-expiration.md).</span></span> <span data-ttu-id="a0c28-122">使用自动策略控制在组织外部共享的敏感电子邮件, 从而通过将安全 web 门户转到加密电子邮件来实现访问权限, 从而增强保护。</span><span class="sxs-lookup"><span data-stu-id="a0c28-122">Control sensitive emails shared outside the organization with automatic policies that enhance protection by expiring access through a secure web portal to encrypted emails.</span></span>

<span data-ttu-id="a0c28-123">[撤消由 Office 365 高级邮件加密加密的电子邮件](revoke-ome-encrypted-mail.md)。</span><span class="sxs-lookup"><span data-stu-id="a0c28-123">[Revoke email encrypted by Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md).</span></span> <span data-ttu-id="a0c28-124">控制在组织外共享的敏感电子邮件, 并通过将访问安全的 web 门户转到加密电子邮件来增强保护。</span><span class="sxs-lookup"><span data-stu-id="a0c28-124">Control sensitive emails shared outside the organization and enhance protection by revoking access through a secure web portal to encrypted emails.</span></span>  
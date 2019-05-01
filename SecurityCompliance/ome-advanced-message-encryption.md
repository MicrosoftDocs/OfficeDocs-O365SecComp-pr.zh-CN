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
description: office 365 中的高级邮件加密帮助组织通过 Office 365 web 门户对加密电子邮件的访问权限过期并撤消访问权限, 从而帮助组织满足其合规性义务。
ms.openlocfilehash: a775803a8d2678441f319c0145e96e7d19c26f7e
ms.sourcegitcommit: 8eb3cb4ec45ae0bb75fde249e35c4bc3d263b84f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506707"
---
# <a name="office-365-advanced-message-encryption"></a><span data-ttu-id="72884-103">Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="72884-103">Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="72884-104">office 365 高级邮件加密在特定订阅中的 office 365 邮件加密的顶层可用。</span><span class="sxs-lookup"><span data-stu-id="72884-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="72884-105">[Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)e5、office 365 企业版 e5 和 Office 365 教育版 A5 中包含高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="72884-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="72884-106">如果您的组织有一个不包含 office 365 高级邮件加密的 office 365 订阅, 则可以将高级邮件加密作为加载项进行购买, 使其具有高级合规性 SKU 的 E5 合规性。</span><span class="sxs-lookup"><span data-stu-id="72884-106">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="72884-107">本文是有关[Office 365 邮件加密](ome.md)的更多系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="72884-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="72884-108">Office 365 中的高级邮件加密帮助客户满足法规遵从性义务, 这些要求对外部收件人和其加密电子邮件的访问权限要求更灵活的控制。</span><span class="sxs-lookup"><span data-stu-id="72884-108">Advanced Message Encryption in Office 365 helps customers meet compliance obligations that require more flexible controls over external recipients and their access to encrypted emails.</span></span> <span data-ttu-id="72884-109">使用 Office 365 中的高级邮件加密, 可以控制使用自动策略在组织外共享的敏感电子邮件。</span><span class="sxs-lookup"><span data-stu-id="72884-109">With Advanced Message Encryption in Office 365, you can control sensitive emails shared outside the organization with automatic policies.</span></span> <span data-ttu-id="72884-110">您可以配置这些策略以标识敏感信息类型 (如 PII、财务或运行状况 id), 也可以使用关键字来增强保护。</span><span class="sxs-lookup"><span data-stu-id="72884-110">You configure these policies to identify sensitive information types such as PII, Financial, or Health IDs, or you can use keywords to enhance protection.</span></span> <span data-ttu-id="72884-111">配置策略后, 您可以使用自定义品牌的电子邮件模板对策略进行配对, 然后为符合该策略的电子邮件添加其他控件的到期日期。</span><span class="sxs-lookup"><span data-stu-id="72884-111">Once you've configured the policies, you pair policies with a custom branded email templates and then add an expiration date for additional control for emails that fit the policy.</span></span> <span data-ttu-id="72884-112">此外, 管理员可以随时撤销对邮件的访问权限, 从而进一步控制在外部通过安全 web 门户访问的加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="72884-112">Additionally, admins can further control encrypted emails accessed externally through a secure web portal by revoking access to the mail at any time.</span></span>

<span data-ttu-id="72884-113">您只能为发送给外部收件人的电子邮件设置过期日期和吊销。</span><span class="sxs-lookup"><span data-stu-id="72884-113">You can only set an expiration for and revoke emails  sent to external recipients.</span></span>

<span data-ttu-id="72884-114">使用 office 365 高级邮件加密时, 无论何时应用自定义品牌打造, Office 365 都会将包装应用于与应用该模板的邮件流规则相适应的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="72884-114">With Office 365 Advanced Message Encryption, any time you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="72884-115">此外, 只有在使用自定义品牌的情况下, 才能使用过期。</span><span class="sxs-lookup"><span data-stu-id="72884-115">In addition, expiration can only be used if custom branding is used.</span></span> <span data-ttu-id="72884-116">只能撤消通过门户接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="72884-116">You can only revoke messages that are received through the portal.</span></span>

## <a name="get-started-with-office-365-advanced-message-encryption"></a><span data-ttu-id="72884-117">开始使用 Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="72884-117">Get started with Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="72884-118">下列主题介绍了如何设置和使用高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="72884-118">The following topics describe how you set up and use Advanced Message Encryption.</span></span>

<span data-ttu-id="72884-119">您的组织必须具有包含 Office 365 高级邮件加密的订阅。</span><span class="sxs-lookup"><span data-stu-id="72884-119">Your organization must have a subscription that includes Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="72884-120">有关受支持订阅的详细信息, 请参阅[邮件策略和合规性服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="72884-120">For detailed information about supported subscriptions, see the [Message policy and compliance service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

<span data-ttu-id="72884-121">设置新的 Office 365 邮件加密功能 (如果尚未设置) 以利用高级邮件加密功能, 这些功能在外部共享的加密邮件顶部提供了增强保护。</span><span class="sxs-lookup"><span data-stu-id="72884-121">Set up the new Office 365 Message Encryption capabilities if they are not already set up to leverage Advanced Message Encryption capabilities which provide added protection on top of encrypted messages shared externally.</span></span> <span data-ttu-id="72884-122">如果没有设置 office 365 邮件加密, 请参阅[设置新的 office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="72884-122">If you do not have Office 365 Message Encryption set up, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="72884-123">[为通过 Office 365 高级邮件加密加密的电子邮件设置到期日期](ome-advanced-expiration.md)。</span><span class="sxs-lookup"><span data-stu-id="72884-123">[Set an expiration date for email encrypted by Office 365 Advanced Message Encryption](ome-advanced-expiration.md).</span></span> <span data-ttu-id="72884-124">使用自动策略控制在组织外部共享的敏感电子邮件, 从而通过将安全 web 门户转到加密电子邮件来实现访问权限, 从而增强保护。</span><span class="sxs-lookup"><span data-stu-id="72884-124">Control sensitive emails shared outside the organization with automatic policies that enhance protection by expiring access through a secure web portal to encrypted emails.</span></span>

<span data-ttu-id="72884-125">[撤消由 Office 365 高级邮件加密加密的电子邮件](revoke-ome-encrypted-mail.md)。</span><span class="sxs-lookup"><span data-stu-id="72884-125">[Revoke email encrypted by Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md).</span></span> <span data-ttu-id="72884-126">控制在组织外共享的敏感电子邮件, 并通过将访问安全的 web 门户转到加密电子邮件来增强保护。</span><span class="sxs-lookup"><span data-stu-id="72884-126">Control sensitive emails shared outside the organization and enhance protection by revoking access through a secure web portal to encrypted emails.</span></span>  
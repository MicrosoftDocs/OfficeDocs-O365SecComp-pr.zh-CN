---
title: 在 Exchange Online 中修复错误代码为 5.7.7 xx 的电子邮件传递问题
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/11/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 了解如何在 Exchange Online 中修复错误代码为 5.7.7 xx 的电子邮件问题 (阻止发送邮件的租户)。
ms.openlocfilehash: d55bc1f8a051a7f9932528a75aac8f1efa18911c
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599328"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a><span data-ttu-id="8e29d-103">在 Exchange Online 中修复错误代码为 5.7.7 xx 的电子邮件传递问题</span><span class="sxs-lookup"><span data-stu-id="8e29d-103">Fix email delivery issues for error code 5.7.7xx in Exchange Online</span></span>

<span data-ttu-id="8e29d-104">本主题介绍在未送达报告 (也称为 "NDR"、"退回邮件"、"传递状态通知" 或 "DSN") 中看到状态代码 550 5.7.7 xx 时可以执行的操作。</span><span class="sxs-lookup"><span data-stu-id="8e29d-104">This topic describes what you can do if you see status code 550 5.7.7xx in a non-delivery report (also known as an NDR, bounce message, delivery status notification, or DSN).</span></span> <span data-ttu-id="8e29d-105">当你的租户受到限制以单向方式发送电子邮件时, 你将看到此自动通知。</span><span class="sxs-lookup"><span data-stu-id="8e29d-105">You'll see this automated notification when your tenant is restricted from sending email in one way or another.</span></span> <span data-ttu-id="8e29d-106">这些错误代码通常将为705或750。</span><span class="sxs-lookup"><span data-stu-id="8e29d-106">These error codes will usually come in as 705 or 750.</span></span>

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a><span data-ttu-id="8e29d-107">5.7.705: 租户已超出阈值限制: 需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="8e29d-107">5.7.705: Tenant has exceeded threshold restriction: What you need to know</span></span>

<span data-ttu-id="8e29d-108">如果你的租户受到威胁, 内部发件人可以在你尝试发送邮件时看到此 NDR。</span><span class="sxs-lookup"><span data-stu-id="8e29d-108">Internal senders could see this NDR whenever you try to send mail if your tenant was compromised.</span></span> <span data-ttu-id="8e29d-109">当你的租户中的大多数流量检测到可疑并导致阻止了租户的发送能力时, 这通常会 occus。</span><span class="sxs-lookup"><span data-stu-id="8e29d-109">This usually occus when the majority of traffic from your tenant has been detected as suspicious and has resulted in a ban on sending ability for the tenant.</span></span> <span data-ttu-id="8e29d-110">如果您的用户从 Office 365 发送大量批量邮件, 也会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="8e29d-110">This can also occur if your users send an large amount of bulk mail from Office 365.</span></span> <span data-ttu-id="8e29d-111">如服务说明中所述, 需要发送合法批量商业电子邮件的 Exchange Online 客户 (例如, 客户新闻稿) 应使用专门用于这些服务的第三方提供商。</span><span class="sxs-lookup"><span data-stu-id="8e29d-111">As stated in the service description, Exchange Online customers who need to send legitimate bulk commercial email (for example, customer newsletters) should use third-party providers that specialize in these services.</span></span>

<span data-ttu-id="8e29d-112">一旦您的用户作为一个租户, 通过该服务发送一定数量的可疑邮件, 则在解决问题之前, 可以阻止所有用户发送任何邮件。</span><span class="sxs-lookup"><span data-stu-id="8e29d-112">Once your users collectively, as a tenant, send a certain amount of suspicious mail through the service, all users can be prevented from sending any mail until the problem is fixed.</span></span> <span data-ttu-id="8e29d-113">用户将收到一个未送达报告 (NDR), 其中指出:</span><span class="sxs-lookup"><span data-stu-id="8e29d-113">Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="8e29d-114">550 5.7.705 访问被拒绝, 租户已超出阈值</span><span class="sxs-lookup"><span data-stu-id="8e29d-114">550 5.7.705 Access denied, tenant has exceeded threshold</span></span>

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a><span data-ttu-id="8e29d-115">5.7.750: 未注册的域电子邮件限制: 您需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="8e29d-115">5.7.750: Unregistered Domain Email restriction: What you need to know</span></span>

<span data-ttu-id="8e29d-116">Office 365 允许租户通过 Exchange Online Protection (EOP) 中继某些邮件。</span><span class="sxs-lookup"><span data-stu-id="8e29d-116">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP).</span></span> <span data-ttu-id="8e29d-117">一种受支持的示例是, 当用户拥有 Office 365 邮箱, 而其他人向其发送电子邮件, 但电子邮件转发已配置为返回到用户的外部邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e29d-117">One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox.</span></span> <span data-ttu-id="8e29d-118">这在教育环境中最常见, 在这种情况下, 学生希望利用个人电子邮件界面, 但仍会收到与学校相关的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8e29d-118">This is most common in education environments where students want to leverage their personal email interface but still get emails related to school.</span></span> <span data-ttu-id="8e29d-119">另一个示例是当客户处于混合方案中, 并且具有从 EOP 发送电子邮件的本地服务器时。</span><span class="sxs-lookup"><span data-stu-id="8e29d-119">Another example is when customers are in a hybrid scenario and have on-premises servers that send email out of EOP.</span></span>

### <a name="problems-with-unregistered-domains"></a><span data-ttu-id="8e29d-120">未注册域的问题</span><span class="sxs-lookup"><span data-stu-id="8e29d-120">Problems with unregistered domains</span></span>

<span data-ttu-id="8e29d-121">问题是, 在本地服务器受到威胁时, 最终会将大量垃圾邮件转发给 EOP。</span><span class="sxs-lookup"><span data-stu-id="8e29d-121">The problem is when on-premises servers get compromised and end up relaying a large volume of spam out of EOP.</span></span> <span data-ttu-id="8e29d-122">在几乎所有情况下, 都设置了正确的连接器, 但电子邮件是从未注册 (也称为 "未设置的域") 发送的。</span><span class="sxs-lookup"><span data-stu-id="8e29d-122">In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains.</span></span> <span data-ttu-id="8e29d-123">Office 365 确实允许未注册的域中包含合理的邮件, 但应该为您计划发送的每个域在管理中心中配置一个接受域。</span><span class="sxs-lookup"><span data-stu-id="8e29d-123">Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="8e29d-124">一旦受到威胁, 租户将被阻止为未注册的域发送出站邮件。</span><span class="sxs-lookup"><span data-stu-id="8e29d-124">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains.</span></span> <span data-ttu-id="8e29d-125">用户将收到一个未送达报告 (NDR), 其中指出:</span><span class="sxs-lookup"><span data-stu-id="8e29d-125">Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="8e29d-126">550 5.7.750 服务不可用。</span><span class="sxs-lookup"><span data-stu-id="8e29d-126">550 5.7.750 Service unavailable.</span></span> <span data-ttu-id="8e29d-127">阻止从未注册的域发送的客户端</span><span class="sxs-lookup"><span data-stu-id="8e29d-127">Client blocked from sending from unregistered domains</span></span>

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="8e29d-128">如何取消阻止租户以便再次发送</span><span class="sxs-lookup"><span data-stu-id="8e29d-128">How to unblocking tenant in order to send again</span></span>

<span data-ttu-id="8e29d-129">如果您的租户被阻止发送电子邮件, 则需要执行以下几项操作:</span><span class="sxs-lookup"><span data-stu-id="8e29d-129">There are several things you need to do if your tenant get blocked for sending email:</span></span>

1. <span data-ttu-id="8e29d-130">请确保在 Microsoft 365 管理中心内注册所有域。</span><span class="sxs-lookup"><span data-stu-id="8e29d-130">Make sure that you register all of your domains in Microsoft 365 admin center.</span></span> <span data-ttu-id="8e29d-131">可在[此处](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)找到详细信息。</span><span class="sxs-lookup"><span data-stu-id="8e29d-131">More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="8e29d-132">查找异常连接器。</span><span class="sxs-lookup"><span data-stu-id="8e29d-132">Look for unusual connectors.</span></span> <span data-ttu-id="8e29d-133">恶意参与者通常会在 Office 365 租户中创建新的入站连接器以发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="8e29d-133">Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam.</span></span> <span data-ttu-id="8e29d-134">可在[此处](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)找到有关检查连接器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8e29d-134">More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="8e29d-135">锁定你的本地服务器, 并确保其不会受到威胁。</span><span class="sxs-lookup"><span data-stu-id="8e29d-135">Lock down your on-premises servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="8e29d-136">此处涉及许多因素, 尤其是当它们是第三方服务器时。</span><span class="sxs-lookup"><span data-stu-id="8e29d-136">There are many factors involved here, especially if these are third-party servers.</span></span> <span data-ttu-id="8e29d-137">无论如何, 您都需要能够确认离开服务器的所有邮件都是合法的。</span><span class="sxs-lookup"><span data-stu-id="8e29d-137">Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="8e29d-138">完成后, 你将需要致电 Microsoft 支持部门, 让你的租户不再被阻止, 以从未注册的域中再次发送。</span><span class="sxs-lookup"><span data-stu-id="8e29d-138">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.</span></span>  <span data-ttu-id="8e29d-139">提供错误代码很有帮助, 但您需要证明您的环境是安全的, 并且不会再次发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="8e29d-139">Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again.</span></span> <span data-ttu-id="8e29d-140">可在[此处](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)找到有关打开支持案例的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8e29d-140">More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="8e29d-141">详细信息</span><span class="sxs-lookup"><span data-stu-id="8e29d-141">For more information</span></span>

[<span data-ttu-id="8e29d-142">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="8e29d-142">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="8e29d-143">Office 365 中的电子邮件未送达报告</span><span class="sxs-lookup"><span data-stu-id="8e29d-143">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="8e29d-144">配置邮箱的电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="8e29d-144">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="8e29d-145">如何设置多功能设备或应用程序以使用 Office 365 发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="8e29d-145">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="8e29d-146">[在 Exchange Online 中管理接受的域](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="8e29d-146">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

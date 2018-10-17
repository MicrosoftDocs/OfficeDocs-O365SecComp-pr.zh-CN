---
title: 未注册的域的电子邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: 如果您发送大量未注册的域的电子邮件，则运行获取阻止您的电子邮件的风险。阅读此文，了解详细信息。
ms.openlocfilehash: 30d7887be0429195380f2c4ae1a328904dffd69c
ms.sourcegitcommit: 6d72cdb882b93edf6dfddb5ff2e6d8a16e2fa0bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25596725"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="12a33-104">未注册域电子邮件： 您需要知道</span><span class="sxs-lookup"><span data-stu-id="12a33-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="12a33-p102">Office 365 允许租户中继某些消息通过 Exchange Online Protection (EOP)。如果用户拥有 Office 365 邮箱和外部的某人发送电子邮件但，以便它返回到用户的外部邮箱配置邮件转发，应为此一个受支持的示例。这是最常见教育环境学生要利用其个人电子邮件界面，但仍可获得与学校相关的电子邮件中。时的用户在混合方案，并已发送电子邮件 EOP 出的本地服务器，另一个示例。</span><span class="sxs-lookup"><span data-stu-id="12a33-p102">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP). One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox. This is most common in education environments where students want to leverage their personal email interface but still get emails related to school. Another example is when customers are in a hybrid scenario and have on-premise servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="12a33-109">未注册域问题</span><span class="sxs-lookup"><span data-stu-id="12a33-109">Problems with unregistered domains</span></span>

<span data-ttu-id="12a33-p103">内部服务器获取威胁和最终中继大量的 EOP 出垃圾邮件时出现问题。几乎在所有情况下，右连接器设置但正在从未注册，也称为取消设置，域发送电子邮件。Office 365 允许一定的邮件来自未注册的域，但应在每个域发送外出您计划在管理中心中配置接受域。</span><span class="sxs-lookup"><span data-stu-id="12a33-p103">The problem is when on-premise servers get compromised and end up relaying a large volume of spam out of EOP. In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains. Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="12a33-p104">一旦威胁，租户将阻止发送出站邮件未注册的域。用户将收到未送达报告 (NDR) 的状态：</span><span class="sxs-lookup"><span data-stu-id="12a33-p104">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains. Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="12a33-p105">550 5.7.750 服务不可用。阻止来自未注册的域发送的客户端</span><span class="sxs-lookup"><span data-stu-id="12a33-p105">550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="12a33-117">取消阻止租户以再次发送</span><span class="sxs-lookup"><span data-stu-id="12a33-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="12a33-118">有几种方法需要获取阻止来自未注册的域发送时如何操作：</span><span class="sxs-lookup"><span data-stu-id="12a33-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="12a33-p106">请确保您注册您的域的所有 Office 365 管理中心中。可以找到更多信息[此处](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="12a33-p106">Make sure that you register all of your domains in Office 365 admin center. More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="12a33-p107">特殊的连接线的外观。通常，恶意参与者将在 Office 365 租户发送垃圾邮件中创建新的入站的连接器。可以找到检查您连接器的详细信息[此处](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="12a33-p107">Look for unusual connectors. Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam. More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="12a33-124">锁定的本地服务器，并确保它们不泄漏。</span><span class="sxs-lookup"><span data-stu-id="12a33-124">Lock down your on-premise servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="12a33-p108">有许多因素涉及到在这里，尤其是这些是第三方服务器。无论，您将需要能确认合法保留您的服务器的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="12a33-p108">There are many factors involved here, especially if these are third-party servers. Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="12a33-p109">完成后，您将需要呼叫 Microsoft 支持联系，以获取您取消再次从未注册的域发送的租户。 提供的错误代码是非常有用，但您将需要证明安全的环境，不会在再次发送垃圾邮件。打开支持案例的详细信息可以找到[此处](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)。</span><span class="sxs-lookup"><span data-stu-id="12a33-p109">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.  Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again. More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="12a33-130">详细信息</span><span class="sxs-lookup"><span data-stu-id="12a33-130">For more information</span></span>

[<span data-ttu-id="12a33-131">Office 365 email anti-spam protection</span><span class="sxs-lookup"><span data-stu-id="12a33-131">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="12a33-132">Office 365 中的电子邮件未送达报告</span><span class="sxs-lookup"><span data-stu-id="12a33-132">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="12a33-133">配置邮箱的电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="12a33-133">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="12a33-134">如何设置多功能设备或应用程序以使用 Office 365 发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="12a33-134">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="12a33-135">[管理接受域在 Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="12a33-135">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

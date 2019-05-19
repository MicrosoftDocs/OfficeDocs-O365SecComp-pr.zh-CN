---
title: 未注册的域电子邮件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/17/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 如果您发送大量未注册的域电子邮件, 则可能会导致电子邮件被阻止。 阅读本文以了解详细信息。
ms.openlocfilehash: 207b71ab7e144af9709e7485d61c936e07271a11
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156294"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a><span data-ttu-id="6b4ff-104">未注册的域电子邮件: 需要了解的内容</span><span class="sxs-lookup"><span data-stu-id="6b4ff-104">Unregistered Domain Email: What you need to know</span></span>

<span data-ttu-id="6b4ff-105">Office 365 允许租户通过 Exchange Online Protection (EOP) 中继某些邮件。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-105">Office 365 allows for tenants to relay some messages through Exchange Online Protection (EOP).</span></span> <span data-ttu-id="6b4ff-106">一种受支持的示例是, 当用户拥有 Office 365 邮箱, 而其他人向其发送电子邮件, 但电子邮件转发已配置为返回到用户的外部邮箱。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-106">One supported example of this would be when users have an Office 365 mailbox and someone external sends them email but email forwarding is configured so that it goes back out to the user's external mailbox.</span></span> <span data-ttu-id="6b4ff-107">这在教育环境中最常见, 在这种情况下, 学生希望利用个人电子邮件界面, 但仍会收到与学校相关的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-107">This is most common in education environments where students want to leverage their personal email interface but still get emails related to school.</span></span> <span data-ttu-id="6b4ff-108">另一个示例是当客户处于混合方案中, 并且具有从 EOP 发送电子邮件的本地服务器时。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-108">Another example is when customers are in a hybrid scenario and have on-premises servers that send email out of EOP.</span></span>

## <a name="problems-with-unregistered-domains"></a><span data-ttu-id="6b4ff-109">未注册域的问题</span><span class="sxs-lookup"><span data-stu-id="6b4ff-109">Problems with unregistered domains</span></span>

<span data-ttu-id="6b4ff-110">问题是, 在本地服务器受到威胁时, 最终会将大量垃圾邮件转发给 EOP。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-110">The problem is when on-premises servers get compromised and end up relaying a large volume of spam out of EOP.</span></span> <span data-ttu-id="6b4ff-111">在几乎所有情况下, 都设置了正确的连接器, 但电子邮件是从未注册 (也称为 "未设置的域") 发送的。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-111">In almost all cases, the right connectors are set up but email is being sent from unregistered, also known as unprovisioned, domains.</span></span> <span data-ttu-id="6b4ff-112">Office 365 确实允许未注册的域中包含合理的邮件, 但应该为您计划发送的每个域在管理中心中配置一个接受域。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-112">Office 365 does allow a reasonable amount of mail to come from unregistered domains, but an Accepted Domain should be configured in the Admin Center for each domain you plan on sending out of.</span></span>

<span data-ttu-id="6b4ff-113">一旦受到威胁, 租户将被阻止为未注册的域发送出站邮件。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-113">Once compromised, tenants will be prevented from sending outbound mail for unregistered domains.</span></span> <span data-ttu-id="6b4ff-114">用户将收到一个未送达报告 (NDR), 其中指出:</span><span class="sxs-lookup"><span data-stu-id="6b4ff-114">Users will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="6b4ff-115">550 5.7.750 服务不可用。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-115">550 5.7.750 Service unavailable.</span></span> <span data-ttu-id="6b4ff-116">阻止从未注册的域发送的客户端</span><span class="sxs-lookup"><span data-stu-id="6b4ff-116">Client blocked from sending from unregistered domains</span></span>

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="6b4ff-117">取消阻止租户以便再次发送</span><span class="sxs-lookup"><span data-stu-id="6b4ff-117">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="6b4ff-118">如果阻止从未注册的域发送, 需要执行以下几项操作:</span><span class="sxs-lookup"><span data-stu-id="6b4ff-118">There are several things you need to do if you get blocked for sending from unregistered domains:</span></span>

1. <span data-ttu-id="6b4ff-119">请确保在 Microsoft 365 管理中心内注册所有域。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-119">Make sure that you register all of your domains in Microsoft 365 admin center.</span></span> <span data-ttu-id="6b4ff-120">可在[此处](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)找到详细信息。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-120">More information can be found [here](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

2. <span data-ttu-id="6b4ff-121">查找异常连接器。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-121">Look for unusual connectors.</span></span> <span data-ttu-id="6b4ff-122">恶意参与者通常会在 Office 365 租户中创建新的入站连接器以发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-122">Malicious actors will often create new inbound connectors in your Office 365 tenant to send spam.</span></span> <span data-ttu-id="6b4ff-123">可在[此处](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)找到有关检查连接器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-123">More information on checking your connectors can be found [here](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps).</span></span> 

3. <span data-ttu-id="6b4ff-124">锁定你的本地服务器, 并确保其不会受到威胁。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-124">Lock down your on-premises servers and ensure that they are not compromised.</span></span>

> [!TIP]
> <span data-ttu-id="6b4ff-125">此处涉及许多因素, 尤其是当它们是第三方服务器时。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-125">There are many factors involved here, especially if these are third-party servers.</span></span> <span data-ttu-id="6b4ff-126">无论如何, 您都需要能够确认离开服务器的所有邮件都是合法的。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-126">Regardless, you will need to be able confirm that  all mail leaving your servers are legitimate.</span></span>

4. <span data-ttu-id="6b4ff-127">完成后, 你将需要致电 Microsoft 支持部门, 让你的租户不再被阻止, 以从未注册的域中再次发送。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-127">Once done, you will need to call Microsoft Support and ask to get your tenant unblocked to send from unregistered domains again.</span></span>  <span data-ttu-id="6b4ff-128">提供错误代码很有帮助, 但您需要证明您的环境是安全的, 并且不会再次发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-128">Providing the error code is helpful, but you will need to prove that your environment is secured and that spam will not be sent again.</span></span> <span data-ttu-id="6b4ff-129">可在[此处](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)找到有关打开支持案例的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-129">More information on opening a support case can be found [here](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="6b4ff-130">详细信息</span><span class="sxs-lookup"><span data-stu-id="6b4ff-130">For more information</span></span>

[<span data-ttu-id="6b4ff-131">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="6b4ff-131">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="6b4ff-132">Office 365 中的电子邮件未送达报告</span><span class="sxs-lookup"><span data-stu-id="6b4ff-132">Email non-delivery reports in Office 365</span></span>](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[<span data-ttu-id="6b4ff-133">配置邮箱的电子邮件转发</span><span class="sxs-lookup"><span data-stu-id="6b4ff-133">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="6b4ff-134">如何设置多功能设备或应用程序以使用 Office 365 发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="6b4ff-134">How to set up a multifunction device or application to send email using Office 365</span></span>](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

<span data-ttu-id="6b4ff-135">[在 Exchange Online 中管理接受的域](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="6b4ff-135">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

---
title: Office 365 中的邮件流智能
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 管理员可以了解有关与 Office 365 （也称为邮件流智能） 中使用连接器的邮件传递相关联的错误代码。
ms.openlocfilehash: 9f27dfd4c265eb62028d68c27764183202692ef4
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "28327084"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="2f55a-103">Office 365 中的邮件流智能</span><span class="sxs-lookup"><span data-stu-id="2f55a-103">Mail flow intelligence in Office 365</span></span>

<span data-ttu-id="2f55a-p101">通常情况下，您可以使用连接器以将从 Office 365 组织的电子邮件路由到内部部署电子邮件环境。您可能还使用连接器路由邮件从 Office 365 合作伙伴组织。时 Office 365 无法传送连接器通过这些消息，它们是在 Office 365 中排队。Office 365 将继续 48 小时重试关于每封邮件的传递。48 小时内，将过期排队的消息，并将向未送达报告 （也称为 NDR 或弹跳消息） 的原始发件人返回邮件。</span><span class="sxs-lookup"><span data-stu-id="2f55a-p101">Typically, you use a connector to route email messages from your Office 365 organization to your on-premises email environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. Office 365 will continue to retry delivery for each message for 48 hours. After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="2f55a-p102">Office 365 将生成一个错误，不能使用连接器传递一条消息。本主题中描述的最常见的错误和他们的解决方案。统称未送达发送的邮件通过连接器的队列和通知错误称为_邮件流智能_。</span><span class="sxs-lookup"><span data-stu-id="2f55a-p102">Office 365 generates an error when a message can't be delivered by using a connector. The most common errors and their solutions are described in this topic. Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="2f55a-112">错误代码： 450 4.4.312 DNS 查询失败</span><span class="sxs-lookup"><span data-stu-id="2f55a-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="2f55a-p103">通常，此错误表示 Office 365 尝试连接到连接器，但要查找失败的智能主机的 IP 地址的 DNS 查询中指定的智能主机。此错误可能的原因是：</span><span class="sxs-lookup"><span data-stu-id="2f55a-p103">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed. The possible causes for this error are:</span></span>

- <span data-ttu-id="2f55a-115">没有与您的域的 DNS 托管服务 （维护您的域的权威页面的名称服务器方） 问题。</span><span class="sxs-lookup"><span data-stu-id="2f55a-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="2f55a-116">您的域最近已过期的因此无法检索 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="2f55a-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="2f55a-117">最近更改您的域的 MX 记录，和 Office 365 DNS 服务器仍具有以前缓存为您的域的 DNS 信息。</span><span class="sxs-lookup"><span data-stu-id="2f55a-117">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="2f55a-118">如何解决错误代码 450 4.4.312？</span><span class="sxs-lookup"><span data-stu-id="2f55a-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="2f55a-119">使用 DNS 托管服务以找出并修复您的域的问题。</span><span class="sxs-lookup"><span data-stu-id="2f55a-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="2f55a-120">如果错误是从合作伙伴组织 （例如，第三方云服务提供商），请联系同伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="2f55a-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="2f55a-121">错误代码： 450 4.4.315 连接超时</span><span class="sxs-lookup"><span data-stu-id="2f55a-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="2f55a-p104">通常，这意味着 Office 365 无法连接到目标电子邮件服务器。错误详细信息将说明该问题。例如：</span><span class="sxs-lookup"><span data-stu-id="2f55a-p104">Typically, this means Office 365 can't connect to the destination email server. The error details will explain the problem. For example:</span></span>

- <span data-ttu-id="2f55a-125">您的内部部署电子邮件服务器已关闭。</span><span class="sxs-lookup"><span data-stu-id="2f55a-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="2f55a-126">没有错误连接符的智能主机设置，以便 Office 365 尝试连接到错误的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2f55a-126">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="2f55a-127">如何解决错误代码 450 4.4.315？</span><span class="sxs-lookup"><span data-stu-id="2f55a-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="2f55a-p105">找出哪些方案适用于您，并进行必要的纠正。例如，如果邮件流工作正常，并且您没有更改连接器设置，则需要检查您的内部部署电子邮件环境如果服务器已关闭，或者是否存在已对网络基础结构的任何更改 （例如，您已更改 internet 服务提供商，因此您现在有不同的 IP 地址）。</span><span class="sxs-lookup"><span data-stu-id="2f55a-p105">Find out which scenario applies to you, and make the necessary corrections. For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="2f55a-130">如果错误是从合作伙伴组织 （例如，第三方云服务提供商），请联系同伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="2f55a-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="2f55a-131">错误代码： 450 4.4.316 连接拒绝</span><span class="sxs-lookup"><span data-stu-id="2f55a-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="2f55a-p106">通常，此错误表示 Office 365 时其尝试连接到目标电子邮件服务器遇到连接错误。此错误的可能原因是您的防火墙阻止连接从 Office 365 IP 地址。或者，此错误可能是设计使然如果您已完全迁移您的内部部署到 Office 365 电子邮件系统，并关闭内部部署电子邮件环境。</span><span class="sxs-lookup"><span data-stu-id="2f55a-p106">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination email server. A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses. Or, this error might be by design if you've completely migrated your on-premises email system to Office 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="2f55a-135">如何解决错误代码 450 4.4.316？</span><span class="sxs-lookup"><span data-stu-id="2f55a-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="2f55a-p107">如果您有邮箱的本地环境中，您需要修改防火墙设置，以允许从 TCP 端口 25 上的 Office 365 IP 地址连接到内部部署电子邮件服务器。Office 365 IP 地址的列表，请参阅[Office 365 Url 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2f55a-p107">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises email servers. For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span></span>

- <span data-ttu-id="2f55a-p108">如果没有更多邮件应传递到内部部署环境中，请**立即修复**的通知中单击以便 Office 365 可以立即拒绝具有无效收件人的邮件。这将降低无效收件人，可能会影响普通邮件传递超出贵组织的配额的风险。或者，您可以使用以下说明手动修复问题：</span><span class="sxs-lookup"><span data-stu-id="2f55a-p108">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="2f55a-141">Office 365 中的[Exchange 管理中心 (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) ，禁用或删除的连接器，可从 Office 365 的电子邮件传递到内部部署电子邮件环境：</span><span class="sxs-lookup"><span data-stu-id="2f55a-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disable or delete the connector that delivers email from Office 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="2f55a-142">在 EAC 中，转到**邮件流** \> **连接器**。</span><span class="sxs-lookup"><span data-stu-id="2f55a-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="2f55a-143">选择**Office 365**中的**从**值连接器和**贵组织的电子邮件服务器**中的**到**值，然后执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="2f55a-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="2f55a-144">通过单击**删除**删除连接器![删除图标](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="2f55a-144">Delete the connector by clicking **Delete** ![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="2f55a-145">通过单击**编辑**禁用连接器![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)和取消选中，则**将其打开**。</span><span class="sxs-lookup"><span data-stu-id="2f55a-145">Disable the connector by clicking **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="2f55a-p109">更改与内部部署电子邮件环境从**内部中继**到**权威**相关联的 Office 365 中的接受的域。有关说明，请参阅[管理接受域在 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428)。</span><span class="sxs-lookup"><span data-stu-id="2f55a-p109">Change the accepted domain in Office 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**. For instructions, see [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span></span>

  <span data-ttu-id="2f55a-p110">**注意**： 通常情况下，这些更改将一小时 30 分钟之间才会生效。一个小时后，确认您不再收到错误。</span><span class="sxs-lookup"><span data-stu-id="2f55a-p110">**Note**: Typically, these changes take between 30 minutes and one hour to take effect. After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="2f55a-150">如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="2f55a-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="2f55a-151">错误代码： 450 4.4.317 无法连接到远程服务器</span><span class="sxs-lookup"><span data-stu-id="2f55a-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="2f55a-p111">通常情况下，此错误表示 Office 365 连接到目标电子邮件服务器，但服务器响应即时错误，或者不满足连接要求。错误详细信息将说明该问题。例如：</span><span class="sxs-lookup"><span data-stu-id="2f55a-p111">Typically, this error means Office 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements. The error details will explain the problem. For example:</span></span>

- <span data-ttu-id="2f55a-155">目标电子邮件服务器响应一个"服务不可用"错误，指示服务器不能维护与 Office 365 的通信。</span><span class="sxs-lookup"><span data-stu-id="2f55a-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>

- <span data-ttu-id="2f55a-156">连接器配置为要求 TLS，但目标电子邮件服务器不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="2f55a-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="2f55a-157">如何解决错误代码 450 4.4.317？</span><span class="sxs-lookup"><span data-stu-id="2f55a-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="2f55a-158">验证的 TLS 设置和您的内部部署电子邮件服务器上的证书和连接器上的 TLS 设置。</span><span class="sxs-lookup"><span data-stu-id="2f55a-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="2f55a-159">如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="2f55a-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="2f55a-160">错误代码： 450 4.4.318 连接已关闭突然</span><span class="sxs-lookup"><span data-stu-id="2f55a-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="2f55a-p112">通常，此错误表示 Office 365 通信时遇到困难与内部部署电子邮件环境，以便连接已断开。此错误可能的原因是：</span><span class="sxs-lookup"><span data-stu-id="2f55a-p112">Typically, this error means Office 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped. The possible causes for this error are:</span></span>

- <span data-ttu-id="2f55a-163">防火墙使用 SMTP 包检查规则，并且这些规则不能正常工作。</span><span class="sxs-lookup"><span data-stu-id="2f55a-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="2f55a-164">您的内部部署电子邮件服务器不正确 （对于示例、 服务挂起、 崩溃或系统资源不足），导致超时的服务器的工作，并关闭与 Office 365 的连接。</span><span class="sxs-lookup"><span data-stu-id="2f55a-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>

- <span data-ttu-id="2f55a-165">没有您的内部部署环境与 Office 365 之间的网络问题。</span><span class="sxs-lookup"><span data-stu-id="2f55a-165">There are network issues between your on-premises environment and Office 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="2f55a-166">如何解决错误代码 450 4.4.318？</span><span class="sxs-lookup"><span data-stu-id="2f55a-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="2f55a-167">找出哪些方案适用于您，并进行必要的纠正。</span><span class="sxs-lookup"><span data-stu-id="2f55a-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="2f55a-168">如果问题由您的内部部署环境与 Office 365 之间的网络问题，请与您的网络团队解决问题。</span><span class="sxs-lookup"><span data-stu-id="2f55a-168">If the problem is caused by network issues between your on-premises environment and Office 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="2f55a-169">如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="2f55a-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="2f55a-170">错误代码： 450 4.7.320 证书验证失败</span><span class="sxs-lookup"><span data-stu-id="2f55a-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="2f55a-p113">通常，此错误表示 Office 365 尝试验证目标电子邮件服务器的证书时遇到错误。错误详细信息将解释错误。例如：</span><span class="sxs-lookup"><span data-stu-id="2f55a-p113">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination email server. The error details will explain the error. For example:</span></span>

- <span data-ttu-id="2f55a-174">证书过期</span><span class="sxs-lookup"><span data-stu-id="2f55a-174">Certificate expired</span></span>

- <span data-ttu-id="2f55a-175">证书主题不匹配</span><span class="sxs-lookup"><span data-stu-id="2f55a-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="2f55a-176">证书不再有效</span><span class="sxs-lookup"><span data-stu-id="2f55a-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="2f55a-177">如何解决错误代码 450 4.7.320？</span><span class="sxs-lookup"><span data-stu-id="2f55a-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="2f55a-178">修复证书或连接器上的设置，以便队列中的 Office 365 中的邮件发送。</span><span class="sxs-lookup"><span data-stu-id="2f55a-178">Fix the certificate or the settings on the connector so that queued messages in Office 365 can be delivered.</span></span>

- <span data-ttu-id="2f55a-179">如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="2f55a-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="2f55a-180">其他错误代码</span><span class="sxs-lookup"><span data-stu-id="2f55a-180">Other error codes</span></span>

<span data-ttu-id="2f55a-p114">Office 365 时遇到困难邮件传递到您的内部部署或合作伙伴电子邮件服务器。使用错误的**目标服务器**信息检查您的环境中的问题或修改连接器，如果没有配置错误。</span><span class="sxs-lookup"><span data-stu-id="2f55a-p114">Office 365 is having difficulty delivering messages to your on-premises or partner email server. Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 

<span data-ttu-id="2f55a-183">如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="2f55a-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

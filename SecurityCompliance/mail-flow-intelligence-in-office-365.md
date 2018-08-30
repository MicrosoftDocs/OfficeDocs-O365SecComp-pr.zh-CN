---
title: Office 365 中的邮件流智能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/27/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: '通常，使用连接器路由邮件从 Office 365 组织到本地邮件环境。您可能还使用连接器路由邮件从 Office 365 合作伙伴组织。时 Office 365 无法传送连接器通过这些消息，它们是在 Office 365 中排队。 '
ms.openlocfilehash: 4effbb783d6ba8f3b33d0aed446e031193d2f2a3
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002714"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="a0e56-105">Office 365 中的邮件流智能</span><span class="sxs-lookup"><span data-stu-id="a0e56-105">Mail flow intelligence in Office 365</span></span>
  
<span data-ttu-id="a0e56-p102">通常，使用连接器路由邮件从 Office 365 组织到本地邮件环境。您可能还使用连接器路由邮件从 Office 365 合作伙伴组织。时 Office 365 无法传送连接器通过这些消息，它们是在 Office 365 中排队。Office 365 将继续 48 小时重试关于每封邮件的传递。48 小时内，将过期排队的消息，并将向未送达报告 （也称为 NDR 或弹跳消息） 的原始发件人返回邮件。</span><span class="sxs-lookup"><span data-stu-id="a0e56-p102">Typically, you use a connector to route messages from your Office 365 organization to your on-premises messaging environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. Office 365 will continue to retry delivery for each message for 48 hours. After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>
  
<span data-ttu-id="a0e56-p103">Office 365 将生成一个错误，不能使用连接器传递一条消息。本主题中描述的最常见的错误和他们的解决方案。统称未送达发送的邮件通过连接器的队列和通知错误称为邮件流智能。</span><span class="sxs-lookup"><span data-stu-id="a0e56-p103">Office 365 generates an error when a message can't be delivered by using a connector. The most common errors and their solutions are described in this topic. Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as mailflow intelligence.</span></span>
  
 <span data-ttu-id="a0e56-114">**目录**</span><span class="sxs-lookup"><span data-stu-id="a0e56-114">**Contents**</span></span>
  
- [<span data-ttu-id="a0e56-115">错误代码： 450 4.4.312 DNS 查询失败</span><span class="sxs-lookup"><span data-stu-id="a0e56-115">Error code: 450 4.4.312 DNS query failed</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44312)
    
- [<span data-ttu-id="a0e56-116">错误代码： 450 4.4.315 连接超时</span><span class="sxs-lookup"><span data-stu-id="a0e56-116">Error code: 450 4.4.315 Connection timed out</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44315)
    
- [<span data-ttu-id="a0e56-117">错误代码： 450 4.4.316 连接拒绝</span><span class="sxs-lookup"><span data-stu-id="a0e56-117">Error code: 450 4.4.316 Connection refused</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44316)
    
- [<span data-ttu-id="a0e56-118">错误代码： 450 4.4.317 无法连接到远程服务器</span><span class="sxs-lookup"><span data-stu-id="a0e56-118">Error code: 450 4.4.317 Cannot connect to remote server</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44317)
    
- [<span data-ttu-id="a0e56-119">错误代码： 450 4.4.318 连接已关闭突然</span><span class="sxs-lookup"><span data-stu-id="a0e56-119">Error code: 450 4.4.318 Connection was closed abruptly</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44318)
    
- [<span data-ttu-id="a0e56-120">错误代码： 450 4.7.320 证书验证失败</span><span class="sxs-lookup"><span data-stu-id="a0e56-120">Error code: 450 4.7.320 Certificate validation failed</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode47320)
    
## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="a0e56-121">错误代码： 450 4.4.312 DNS 查询失败</span><span class="sxs-lookup"><span data-stu-id="a0e56-121">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="a0e56-p104">此错误通常意味着 Office 365 尝试连接到智能主机指定在连接器，但是 DNS 查询，以查找智能主机的 IP 地址失败。此错误可能的原因是：</span><span class="sxs-lookup"><span data-stu-id="a0e56-p104">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host IP addresses failed. The possible causes for this error are:</span></span>
  
- <span data-ttu-id="a0e56-124">没有与您的域的 DNS 托管服务 （维护您的域的权威页面的名称服务器方） 问题。</span><span class="sxs-lookup"><span data-stu-id="a0e56-124">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>
    
- <span data-ttu-id="a0e56-125">您的域最近已过期的因此无法检索 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="a0e56-125">Your domain has recently expired, so the MX record can't be retrieved.</span></span>
    
- <span data-ttu-id="a0e56-126">最近更改您的域的 MX 记录，和 Office 365 DNS 服务器仍具有以前缓存为您的域的 DNS 信息。</span><span class="sxs-lookup"><span data-stu-id="a0e56-126">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>
    
<span data-ttu-id="a0e56-127">您需要通过使用您的 DNS 托管服务修复 DNS 问题。</span><span class="sxs-lookup"><span data-stu-id="a0e56-127">You need to fix the DNS issue by working with your DNS hosting service.</span></span>
  
<span data-ttu-id="a0e56-128">如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="a0e56-128">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="a0e56-129">错误代码： 450 4.4.315 连接超时</span><span class="sxs-lookup"><span data-stu-id="a0e56-129">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="a0e56-p105">通常，这意味着 Office 365 无法连接到目标消息服务器。错误详细信息将说明该问题。例如：</span><span class="sxs-lookup"><span data-stu-id="a0e56-p105">Typically, this means Office 365 can't connect to the destination messaging server. The error details will explain the problem. For example:</span></span>
  
- <span data-ttu-id="a0e56-133">您的内部部署邮件服务器已关闭。</span><span class="sxs-lookup"><span data-stu-id="a0e56-133">Your on-premises messaging server is down.</span></span>
    
- <span data-ttu-id="a0e56-134">没有错误连接符的智能主机设置，以便 Office 365 尝试连接到错误的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a0e56-134">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>
    
<span data-ttu-id="a0e56-p106">找出哪些方案适用于您，并进行必要的纠正。例如，如果邮件流工作正常，并且您没有更改连接器设置，则需要检查您的内部部署邮件环境如果服务器已关闭，或者是否存在已对网络基础结构的任何更改 （例如，您已更改 Internet 服务提供商，因此您现在有不同的 IP 地址）。</span><span class="sxs-lookup"><span data-stu-id="a0e56-p106">Find out which scenario applies to you, and make the necessary corrections. For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises messaging environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed Internet service providers, so you now have different IP addresses).</span></span>
  
<span data-ttu-id="a0e56-137">如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="a0e56-137">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="a0e56-138">错误代码： 450 4.4.316 连接拒绝</span><span class="sxs-lookup"><span data-stu-id="a0e56-138">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="a0e56-p107">通常，此错误表示 Office 365 时其尝试连接到目标消息服务器遇到连接错误。此错误的可能原因是您的防火墙阻止连接从 Office 365 IP 地址。或者，如果您已完全迁移您的内部部署邮件系统到 Office 365 并关闭内部部署此错误可能是设计使然邮件环境。</span><span class="sxs-lookup"><span data-stu-id="a0e56-p107">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination messaging server. A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses. Or, this error might be by design if you've completely migrated your on-premises messaging system to Office 365 and shut down your on-premises messaging environment..</span></span>
  
- <span data-ttu-id="a0e56-p108">如果内部部署环境中拥有邮箱，则需要修改防火墙设置以允许从 TCP 端口 25 上的 Office 365 IP 地址连接到内部部署邮件服务器。Office 365 IP 地址的列表，请参阅[Office 365 Url 和 IP 地址范围](https://go.microsoft.com/fwlink/p/?linkid=228887)。</span><span class="sxs-lookup"><span data-stu-id="a0e56-p108">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises messaging servers. For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?linkid=228887).</span></span>
    
- <span data-ttu-id="a0e56-p109">如果没有更多邮件应传递到内部部署环境中，请**立即修复**的通知中单击以便 Office 365 可以立即拒绝具有无效收件人的邮件。这将降低无效收件人，可能会影响普通邮件传递超出贵组织的配额的风险。或者，您可以使用以下说明手动修复问题：</span><span class="sxs-lookup"><span data-stu-id="a0e56-p109">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span> 
    
  - <span data-ttu-id="a0e56-p110">禁用或删除连接器从 Office 365 到内部部署环境： Office 365 管理中心\>**管理中心** \> **Exchange** \> **邮件流** \> **连接器**\>选择连接器与**Office 365**中的**从**值和**为**值**贵组织的电子邮件服务器**。通过单击**删除**删除连接器![删除图标](media/ITPro-EAC-DeleteIcon.gif)，或通过单击**编辑**禁用连接器![编辑图标](media/ITPro-EAC-EditIcon.gif)和取消选中，则**将其打开**。</span><span class="sxs-lookup"><span data-stu-id="a0e56-p110">Disable or delete the connector from Office 365 to your on-premises environment: Office 365 admin center \> **Admin centers** \> **Exchange** \> **Mail flow** \> **Connectors** \> select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server**. Delete the connector by clicking **Delete**![Delete icon](media/ITPro-EAC-DeleteIcon.gif), or disable the connector by clicking **Edit** ![Edit icon](media/ITPro-EAC-EditIcon.gif) and unchecking **Turn it on**.</span></span>
    
  - <span data-ttu-id="a0e56-p111">更改您的内部部署与相关联的 Office 365 中的接受的域从**内部中继**到**权威**的邮件环境。有关说明，请参阅[Exchange Online 中管理接受域](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a0e56-p111">Change the accepted domain in Office 365 that's associated with your on-premises messaging environment from **Internal Relay** to **Authoritative**. For instructions, see [Manage Accepted Domains in Exchange Online](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx).</span></span>
    
    <span data-ttu-id="a0e56-p112">**注意**： 通常情况下，这些更改将一小时 30 分钟之间才会生效。一个小时后，确认您不再收到错误。</span><span class="sxs-lookup"><span data-stu-id="a0e56-p112">**Note**: Typically, these changes take between 30 minutes and one hour to take effect. After one hour, verify that you no longer receive the error.</span></span>
    
<span data-ttu-id="a0e56-153">如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="a0e56-153">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="a0e56-154">错误代码： 450 4.4.317 无法连接到远程服务器</span><span class="sxs-lookup"><span data-stu-id="a0e56-154">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="a0e56-p113">通常情况下，此错误表示 Office 365 连接到目标消息服务器上，但服务器响应即时错误，或者不满足连接要求。错误详细信息将说明该问题。例如：</span><span class="sxs-lookup"><span data-stu-id="a0e56-p113">Typically, this error means Office 365 connected to the destination messaging server, but the server responded with an immediate error, or doesn't meet the connection requirements. The error details will explain the problem. For example:</span></span>
  
- <span data-ttu-id="a0e56-158">目标消息服务器响应一个"服务不可用"错误，指示服务器不能维护与 Office 365 的通信。</span><span class="sxs-lookup"><span data-stu-id="a0e56-158">The destination messaging server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>
    
- <span data-ttu-id="a0e56-159">连接器配置为要求 TLS，但目标消息服务器不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="a0e56-159">The connector is configured to require TLS, but the destination messaging server doesn't support TLS.</span></span>
    
<span data-ttu-id="a0e56-160">验证的 TLS 设置和您的内部部署上的证书消息服务器和连接器上的 TLS 设置。</span><span class="sxs-lookup"><span data-stu-id="a0e56-160">Verify the TLS settings and certificates on your on-premises messaging servers, and the TLS settings on the connector.</span></span>
  
<span data-ttu-id="a0e56-161">如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="a0e56-161">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="a0e56-162">错误代码： 450 4.4.318 连接已关闭突然</span><span class="sxs-lookup"><span data-stu-id="a0e56-162">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="a0e56-p114">此错误通常意味着 Office 365 通信时遇到困难与本地邮件环境，以便连接已断开。此错误可能的原因是：</span><span class="sxs-lookup"><span data-stu-id="a0e56-p114">Typically, this error means Office 365 is having difficulty communicating with your on-premises messaging environment, so the connection was dropped. The possible causes for this error are:</span></span>
  
- <span data-ttu-id="a0e56-165">防火墙使用 SMTP 包检查规则，并且这些规则不能正常工作。</span><span class="sxs-lookup"><span data-stu-id="a0e56-165">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>
    
- <span data-ttu-id="a0e56-166">您的内部部署邮件服务器不正确 （如服务挂起、 崩溃或系统资源不足） 工作，导致超时的服务器并关闭该连接到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a0e56-166">Your on-premises messaging server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>
    
- <span data-ttu-id="a0e56-p115">没有您的内部部署环境与 Office 365 之间的网络问题。如果问题仍然存在，请与您的网络团队解决问题。</span><span class="sxs-lookup"><span data-stu-id="a0e56-p115">There are network issues between your on-premises environment and Office 365. If the problem persists, contact your network team to troubleshoot the issue.</span></span>
    
<span data-ttu-id="a0e56-169">找出哪些方案适用于您，并进行必要的纠正。</span><span class="sxs-lookup"><span data-stu-id="a0e56-169">Find out which scenario applies to you, and make the necessary corrections.</span></span>
  
<span data-ttu-id="a0e56-170">如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="a0e56-170">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="a0e56-171">错误代码： 450 4.7.320 证书验证失败</span><span class="sxs-lookup"><span data-stu-id="a0e56-171">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="a0e56-p116">通常，此错误表示 Office 365 尝试验证目标消息服务器的证书时遇到错误。错误详细信息将解释错误。例如：</span><span class="sxs-lookup"><span data-stu-id="a0e56-p116">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination messaging server. The error details will explain the error. For example:</span></span>
  
- <span data-ttu-id="a0e56-175">证书过期</span><span class="sxs-lookup"><span data-stu-id="a0e56-175">Certificate expired</span></span>
    
- <span data-ttu-id="a0e56-176">证书主题不匹配</span><span class="sxs-lookup"><span data-stu-id="a0e56-176">Certificate subject mismatch</span></span>
    
- <span data-ttu-id="a0e56-177">证书不再有效</span><span class="sxs-lookup"><span data-stu-id="a0e56-177">Certificate is no longer valid</span></span>
    
<span data-ttu-id="a0e56-178">请修复证书或连接器，以便在 Office 365can 排队的邮件传递。</span><span class="sxs-lookup"><span data-stu-id="a0e56-178">Please fix the certificate or the connector so that queued messages in Office 365can be delivered.</span></span>
  
<span data-ttu-id="a0e56-179">如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="a0e56-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="other-error-codes"></a><span data-ttu-id="a0e56-180">其他错误代码</span><span class="sxs-lookup"><span data-stu-id="a0e56-180">Other error codes</span></span>

<span data-ttu-id="a0e56-p117">Office 365 时遇到困难到您的内部部署或消息服务器的合作伙伴提供消息。使用错误的**目标服务器**信息检查您的环境中的问题或修改连接器，如果没有配置错误。</span><span class="sxs-lookup"><span data-stu-id="a0e56-p117">Office 365 is having difficulty delivering messages to your on-premises or partner messaging server. Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 
  
<span data-ttu-id="a0e56-183">如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="a0e56-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  


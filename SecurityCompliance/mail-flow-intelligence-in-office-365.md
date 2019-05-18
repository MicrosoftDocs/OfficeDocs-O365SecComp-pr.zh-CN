---
title: Office 365 中的邮件流智能
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 管理员可以了解与使用 Office 365 中的连接器 (也称为 "邮件流智能") 关联的邮件传递的错误代码。
ms.openlocfilehash: 224940b84480b694188bd3047829d4896cc2584e
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155864"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="d443a-103">Office 365 中的邮件流智能</span><span class="sxs-lookup"><span data-stu-id="d443a-103">Mail flow intelligence in Office 365</span></span>

<span data-ttu-id="d443a-104">通常情况下, 使用连接器将来自 Office 365 组织的电子邮件路由到本地电子邮件环境。</span><span class="sxs-lookup"><span data-stu-id="d443a-104">Typically, you use a connector to route email messages from your Office 365 organization to your on-premises email environment.</span></span> <span data-ttu-id="d443a-105">您还可以使用连接器将邮件从 Office 365 路由到合作伙伴组织。</span><span class="sxs-lookup"><span data-stu-id="d443a-105">You might also use a connector to route messages from Office 365 to a partner organization.</span></span> <span data-ttu-id="d443a-106">当 Office 365 无法通过连接器传递这些邮件时, 它们将在 Office 365 中排队。</span><span class="sxs-lookup"><span data-stu-id="d443a-106">When Office 365 can't deliver these messages via the connector, they're queued in Office 365.</span></span> <span data-ttu-id="d443a-107">Office 365 将继续为每封邮件重新尝试传递48个小时。</span><span class="sxs-lookup"><span data-stu-id="d443a-107">Office 365 will continue to retry delivery for each message for 48 hours.</span></span> <span data-ttu-id="d443a-108">在48小时后, 排队的邮件将会过期, 并在未送达报告 (也称为 "NDR" 或 "退回邮件") 中将邮件返回给原始发件人。</span><span class="sxs-lookup"><span data-stu-id="d443a-108">After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="d443a-109">当无法使用连接器传递邮件时, Office 365 将生成错误。</span><span class="sxs-lookup"><span data-stu-id="d443a-109">Office 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="d443a-110">本主题中介绍了最常见的错误及其解决方案。</span><span class="sxs-lookup"><span data-stu-id="d443a-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="d443a-111">通过连接器发送的未送达邮件的排队和通知错误称为 "_邮件流智能_"。</span><span class="sxs-lookup"><span data-stu-id="d443a-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="d443a-112">错误代码: 450 4.4.312 DNS 查询失败</span><span class="sxs-lookup"><span data-stu-id="d443a-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="d443a-113">通常情况下, 此错误意味着 Office 365 尝试连接到连接器中指定的智能主机, 但用于查找智能主机 IP 地址的 DNS 查询失败。</span><span class="sxs-lookup"><span data-stu-id="d443a-113">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="d443a-114">此错误可能的原因是:</span><span class="sxs-lookup"><span data-stu-id="d443a-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="d443a-115">您的域的 DNS 托管服务 (为您的域维护权威名称服务器的一方) 存在问题。</span><span class="sxs-lookup"><span data-stu-id="d443a-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="d443a-116">你的域最近已过期, 因此无法检索 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="d443a-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="d443a-117">您的域的 MX 记录最近已更改, 并且 Office 365 DNS 服务器仍有以前为您的域缓存的 DNS 信息。</span><span class="sxs-lookup"><span data-stu-id="d443a-117">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="d443a-118">如何修复错误代码 450 4.4.312？</span><span class="sxs-lookup"><span data-stu-id="d443a-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="d443a-119">使用 DNS 托管服务识别和修复您的域的问题。</span><span class="sxs-lookup"><span data-stu-id="d443a-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="d443a-120">如果错误来自你的合作伙伴组织 (例如, 第三方云服务提供商), 请联系你的合作伙伴以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="d443a-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="d443a-121">错误代码: 450 4.4.315 连接超时</span><span class="sxs-lookup"><span data-stu-id="d443a-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="d443a-122">通常情况下, 这意味着 Office 365 无法连接到目标电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="d443a-122">Typically, this means Office 365 can't connect to the destination email server.</span></span> <span data-ttu-id="d443a-123">错误详细信息将对问题进行说明。</span><span class="sxs-lookup"><span data-stu-id="d443a-123">The error details will explain the problem.</span></span> <span data-ttu-id="d443a-124">例如：</span><span class="sxs-lookup"><span data-stu-id="d443a-124">For example:</span></span>

- <span data-ttu-id="d443a-125">您的内部部署电子邮件服务器已关闭。</span><span class="sxs-lookup"><span data-stu-id="d443a-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="d443a-126">连接器的智能主机设置中存在错误, 因此 Office 365 将尝试连接到错误的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d443a-126">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="d443a-127">如何修复错误代码 450 4.4.315？</span><span class="sxs-lookup"><span data-stu-id="d443a-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="d443a-128">查找适用于您的方案, 并进行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="d443a-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="d443a-129">例如, 如果邮件流已正常运行, 并且您尚未更改连接器设置, 则需要检查本地电子邮件环境以查看服务器是否已关闭, 或者是否对网络基础结构进行了任何更改 (例如,你已更改 internet 服务提供商, 因此你现在具有不同的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d443a-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="d443a-130">如果错误来自你的合作伙伴组织 (例如, 第三方云服务提供商), 请联系你的合作伙伴以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="d443a-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="d443a-131">错误代码: 450 4.4.316 连接被拒绝</span><span class="sxs-lookup"><span data-stu-id="d443a-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="d443a-132">通常情况下, 此错误意味着 Office 365 在尝试连接到目标电子邮件服务器时遇到连接错误。</span><span class="sxs-lookup"><span data-stu-id="d443a-132">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="d443a-133">此错误可能的原因是防火墙阻止了来自 Office 365 IP 地址的连接。</span><span class="sxs-lookup"><span data-stu-id="d443a-133">A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses.</span></span> <span data-ttu-id="d443a-134">或者, 如果已将本地电子邮件系统完全迁移到 Office 365 并关闭了本地电子邮件环境, 则可能会设计此错误。</span><span class="sxs-lookup"><span data-stu-id="d443a-134">Or, this error might be by design if you've completely migrated your on-premises email system to Office 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="d443a-135">如何修复错误代码 450 4.4.316？</span><span class="sxs-lookup"><span data-stu-id="d443a-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="d443a-136">如果您的本地环境中有邮箱, 您需要修改防火墙设置, 以允许从 TCP 端口25上的 Office 365 IP 地址连接到您的本地电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="d443a-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="d443a-137">有关 Office 365 IP 地址的列表, 请参阅[office 365 url 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d443a-137">For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span></span>

- <span data-ttu-id="d443a-138">如果不应将更多的邮件传递到您的本地环境, 请单击警报中的 "**立即修复**", 以便 Office 365 可以立即拒绝具有无效收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="d443a-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="d443a-139">这将降低组织的配额对无效收件人的配额造成的风险, 这可能会影响正常的邮件传递。</span><span class="sxs-lookup"><span data-stu-id="d443a-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="d443a-140">或者, 您可以使用以下说明手动修复问题:</span><span class="sxs-lookup"><span data-stu-id="d443a-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="d443a-141">在 Office 365 的[Exchange 管理中心 (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center)中, 禁用或删除将电子邮件从 office 365 传递到本地电子邮件环境的连接器:</span><span class="sxs-lookup"><span data-stu-id="d443a-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disable or delete the connector that delivers email from Office 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="d443a-142">在 EAC 中, 转到 "**邮件流** \> **连接器**"。</span><span class="sxs-lookup"><span data-stu-id="d443a-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="d443a-143">选择 "**发件人**" 值为 " **Office 365** " 的连接器, 然后选择 "**到**" 值**您组织的电子邮件服务器**, 然后执行以下步骤之一:</span><span class="sxs-lookup"><span data-stu-id="d443a-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="d443a-144">通过单击 "**删除** ![删除" 图标删除连接器](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="d443a-144">Delete the connector by clicking **Delete** ![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="d443a-145">通过单击 "**编辑** ![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) " 和 "取消选中" 禁用连接器以将**其关闭**。</span><span class="sxs-lookup"><span data-stu-id="d443a-145">Disable the connector by clicking **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="d443a-146">将与本地电子邮件环境关联的 Office 365 中的 "接受域" 从 "**内部中继**" 更改为 "**权威**"。</span><span class="sxs-lookup"><span data-stu-id="d443a-146">Change the accepted domain in Office 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="d443a-147">有关说明, 请参阅[在 Exchange Online 中管理接受的域](https://go.microsoft.com/fwlink/p/?linkid=785428)。</span><span class="sxs-lookup"><span data-stu-id="d443a-147">For instructions, see [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span></span>

  <span data-ttu-id="d443a-148">**注意**: 通常情况下, 这些更改需要30分钟到1小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="d443a-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="d443a-149">一小时后, 验证您是否不再收到该错误。</span><span class="sxs-lookup"><span data-stu-id="d443a-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="d443a-150">如果错误来自你的合作伙伴组织 (例如, 第三方云服务提供商), 你需要联系合作伙伴以解决问题。</span><span class="sxs-lookup"><span data-stu-id="d443a-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="d443a-151">错误代码: 450 4.4.317 无法连接到远程服务器</span><span class="sxs-lookup"><span data-stu-id="d443a-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="d443a-152">通常情况下, 此错误意味着连接到目标电子邮件服务器的 Office 365, 但服务器响应时出现即时错误, 或者不符合连接要求。</span><span class="sxs-lookup"><span data-stu-id="d443a-152">Typically, this error means Office 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="d443a-153">错误详细信息将对问题进行说明。</span><span class="sxs-lookup"><span data-stu-id="d443a-153">The error details will explain the problem.</span></span> <span data-ttu-id="d443a-154">例如：</span><span class="sxs-lookup"><span data-stu-id="d443a-154">For example:</span></span>

- <span data-ttu-id="d443a-155">目标电子邮件服务器响应 "服务不可用" 错误, 指示服务器无法维护与 Office 365 的通信。</span><span class="sxs-lookup"><span data-stu-id="d443a-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>

- <span data-ttu-id="d443a-156">连接器配置为需要 TLS, 但目标电子邮件服务器不支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="d443a-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="d443a-157">如何修复错误代码 450 4.4.317？</span><span class="sxs-lookup"><span data-stu-id="d443a-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="d443a-158">验证本地电子邮件服务器上的 TLS 设置和证书, 以及连接器上的 TLS 设置。</span><span class="sxs-lookup"><span data-stu-id="d443a-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="d443a-159">如果错误来自你的合作伙伴组织 (例如, 第三方云服务提供商), 你需要联系合作伙伴以解决问题。</span><span class="sxs-lookup"><span data-stu-id="d443a-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="d443a-160">错误代码: 450 4.4.318 连接突然关闭</span><span class="sxs-lookup"><span data-stu-id="d443a-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="d443a-161">通常情况下, 此错误意味着 Office 365 在与您的本地电子邮件环境通信时遇到困难, 因此断开连接。</span><span class="sxs-lookup"><span data-stu-id="d443a-161">Typically, this error means Office 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="d443a-162">此错误可能的原因是:</span><span class="sxs-lookup"><span data-stu-id="d443a-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="d443a-163">您的防火墙使用 SMTP 数据包检查规则, 这些规则不能正常运行。</span><span class="sxs-lookup"><span data-stu-id="d443a-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="d443a-164">您的内部部署电子邮件服务器不能正常运行 (例如, 服务挂起、崩溃或系统资源不足), 这会导致服务器超时并关闭与 Office 365 的连接。</span><span class="sxs-lookup"><span data-stu-id="d443a-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>

- <span data-ttu-id="d443a-165">您的本地环境和 Office 365 之间存在网络问题。</span><span class="sxs-lookup"><span data-stu-id="d443a-165">There are network issues between your on-premises environment and Office 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="d443a-166">如何修复错误代码 450 4.4.318？</span><span class="sxs-lookup"><span data-stu-id="d443a-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="d443a-167">查找适用于您的方案, 并进行必要的更正。</span><span class="sxs-lookup"><span data-stu-id="d443a-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="d443a-168">如果问题是由于您的本地环境和 Office 365 之间的网络问题导致的, 请联系网络团队以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="d443a-168">If the problem is caused by network issues between your on-premises environment and Office 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="d443a-169">如果错误来自你的合作伙伴组织 (例如, 第三方云服务提供商), 你需要联系合作伙伴以解决问题。</span><span class="sxs-lookup"><span data-stu-id="d443a-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="d443a-170">错误代码: 450 4.7.320 证书验证失败</span><span class="sxs-lookup"><span data-stu-id="d443a-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="d443a-171">通常情况下, 此错误意味着 Office 365 在尝试验证目标电子邮件服务器的证书时遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d443a-171">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="d443a-172">错误详细信息将对错误进行说明。</span><span class="sxs-lookup"><span data-stu-id="d443a-172">The error details will explain the error.</span></span> <span data-ttu-id="d443a-173">例如：</span><span class="sxs-lookup"><span data-stu-id="d443a-173">For example:</span></span>

- <span data-ttu-id="d443a-174">证书已过期</span><span class="sxs-lookup"><span data-stu-id="d443a-174">Certificate expired</span></span>

- <span data-ttu-id="d443a-175">证书主题不匹配</span><span class="sxs-lookup"><span data-stu-id="d443a-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="d443a-176">证书已不再有效</span><span class="sxs-lookup"><span data-stu-id="d443a-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="d443a-177">如何修复错误代码 450 4.7.320？</span><span class="sxs-lookup"><span data-stu-id="d443a-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="d443a-178">修复了连接器上的证书或设置, 以便可以传递 Office 365 中的排队邮件。</span><span class="sxs-lookup"><span data-stu-id="d443a-178">Fix the certificate or the settings on the connector so that queued messages in Office 365 can be delivered.</span></span>

- <span data-ttu-id="d443a-179">如果错误来自你的合作伙伴组织 (例如, 第三方云服务提供商), 你需要联系合作伙伴以解决问题。</span><span class="sxs-lookup"><span data-stu-id="d443a-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="d443a-180">其他错误代码</span><span class="sxs-lookup"><span data-stu-id="d443a-180">Other error codes</span></span>

<span data-ttu-id="d443a-181">Office 365 在将邮件传递到内部部署或合作伙伴电子邮件服务器时遇到困难。</span><span class="sxs-lookup"><span data-stu-id="d443a-181">Office 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="d443a-182">使用错误中的**目标服务器**信息来检查环境中的问题, 如果存在配置错误, 则修改连接器。</span><span class="sxs-lookup"><span data-stu-id="d443a-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 

<span data-ttu-id="d443a-183">如果错误来自你的合作伙伴组织 (例如, 第三方云服务提供商), 你需要联系合作伙伴以解决问题。</span><span class="sxs-lookup"><span data-stu-id="d443a-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

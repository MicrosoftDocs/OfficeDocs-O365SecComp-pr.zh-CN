---
title: Office 365 如何验证发件人地址以防止仿冒
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: '为了帮助防止网络钓鱼, Office 365 和 Outlook.com 现在要求来自: 地址的 RFC 合规性。'
ms.openlocfilehash: 39c9898a31c715487f3bc934ad0986e9a7b3679d
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599128"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="9383e-103">Office 365 如何验证发件人地址以防止仿冒</span><span class="sxs-lookup"><span data-stu-id="9383e-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="9383e-104">Office 365 和 Outlook.com 电子邮件帐户会收到越来越多的网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="9383e-104">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="9383e-105">一种可仿冒者使用的技术是发送其发件人: 地址值不符合[RFC 5322](https://tools.ietf.org/html/rfc5322)的邮件。</span><span class="sxs-lookup"><span data-stu-id="9383e-105">One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="9383e-106">"发件人:" 地址也称为 "5322.from 地址"。</span><span class="sxs-lookup"><span data-stu-id="9383e-106">The From: address is also called the 5322.From address.</span></span> <span data-ttu-id="9383e-107">为了帮助阻止此类型的网络钓鱼, Office 365 和 Outlook.com 要求服务收到的邮件包括符合 RFC 的 From: address, 如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="9383e-107">To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9383e-108">本文中的信息要求您对电子邮件地址的常规格式有一个基本的了解。</span><span class="sxs-lookup"><span data-stu-id="9383e-108">The information in this article requires you to have a basic understanding of the general format of email addresses.</span></span> <span data-ttu-id="9383e-109">有关详细信息, 请参阅[rfc 5322](https://tools.ietf.org/html/rfc5322) (尤其是3.2.3、3.4 和 3.4.1)、 [Rfc 5321](https://tools.ietf.org/html/rfc5321)以及[rfc 3696](https://tools.ietf.org/html/rfc3696)。</span><span class="sxs-lookup"><span data-stu-id="9383e-109">For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696).</span></span> <span data-ttu-id="9383e-110">本文介绍了5322.from 地址的策略实施。</span><span class="sxs-lookup"><span data-stu-id="9383e-110">This article is about policy enforcement for the 5322.From address.</span></span> <span data-ttu-id="9383e-111">本文不介绍5321的5321.Mailfrom 地址。</span><span class="sxs-lookup"><span data-stu-id="9383e-111">This article is not about the 5321.MailFrom address.</span></span> 
  
<span data-ttu-id="9383e-112">遗憾的是, 在 Internet 上仍有一些旧的电子邮件服务器会继续发送 "合法" 电子邮件, 这些邮件缺少或格式不正确的发件人: 地址。</span><span class="sxs-lookup"><span data-stu-id="9383e-112">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address.</span></span> <span data-ttu-id="9383e-113">如果您定期收到使用这些旧系统的组织发来的电子邮件, 则鼓励这些组织更新其邮件服务器以遵守新式安全标准。</span><span class="sxs-lookup"><span data-stu-id="9383e-113">If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>
  
<span data-ttu-id="9383e-114">Microsoft 将开始在2017年11月9日开始推出本文所述策略的实施。</span><span class="sxs-lookup"><span data-stu-id="9383e-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="9383e-115">Office 365 如何强制使用有效的 From: 地址来防止网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="9383e-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="9383e-116">Office 365 正在改变它在收到的邮件中强制使用 From: address 的方式, 以便更好地保护您免受网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="9383e-116">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks.</span></span> <span data-ttu-id="9383e-117">本文内容：</span><span class="sxs-lookup"><span data-stu-id="9383e-117">In this article:</span></span>
  
- [<span data-ttu-id="9383e-118">所有邮件都必须包含有效的发件人: 地址</span><span class="sxs-lookup"><span data-stu-id="9383e-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="9383e-119">"发件人: 地址" 的格式 (如果不包含显示名称)</span><span class="sxs-lookup"><span data-stu-id="9383e-119">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [<span data-ttu-id="9383e-120">"发件人: 地址" 的格式 (如果包含显示名称)</span><span class="sxs-lookup"><span data-stu-id="9383e-120">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [<span data-ttu-id="9383e-121">有效和无效发件人的其他示例: addresses</span><span class="sxs-lookup"><span data-stu-id="9383e-121">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)
    
- [<span data-ttu-id="9383e-122">禁止自动答复您的自定义域, 而无需中断 "发件人:" 策略</span><span class="sxs-lookup"><span data-stu-id="9383e-122">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [<span data-ttu-id="9383e-123">替代 Office 365 发件人: 地址强制策略</span><span class="sxs-lookup"><span data-stu-id="9383e-123">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)
    
- [<span data-ttu-id="9383e-124">阻止和防止 cybercrimes 在 Office 365 中的其他方法</span><span class="sxs-lookup"><span data-stu-id="9383e-124">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)
    
<span data-ttu-id="9383e-125">代表其他用户发送邮件不受此更改的影响, 有关详细信息, 请阅读 Terry Zink 的博客 "[我们是什么？当我们引用电子邮件的 ' 发件人 '？" 时, 这是什么意思？](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)。</span><span class="sxs-lookup"><span data-stu-id="9383e-125">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>
  
### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="9383e-126">所有邮件都必须包含有效的发件人: 地址</span><span class="sxs-lookup"><span data-stu-id="9383e-126">All messages must include a valid From: address</span></span>
<span data-ttu-id="9383e-127"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="9383e-127"></span></span>

<span data-ttu-id="9383e-128">某些自动消息在发送时不包括发件人: 地址。</span><span class="sxs-lookup"><span data-stu-id="9383e-128">Some automated messages don't include a From: address when they are sent.</span></span> <span data-ttu-id="9383e-129">过去, 当 Office 365 或 Outlook.com 收到不含发件人: 地址的邮件时, 该服务会将以下默认的 "发件人" 地址添加到邮件中, 以便其可交付结果如下:</span><span class="sxs-lookup"><span data-stu-id="9383e-129">In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>
  
```
From: <>
```

<span data-ttu-id="9383e-130">从2017年11月9日开始, Office 365 将对其数据中心和邮件服务器进行更改, 这将强制实施一个新规则, 在该规则中, Office 365 或 Outlook.com 不再接受邮件地址 (如果邮件没有发件人: 地址)。</span><span class="sxs-lookup"><span data-stu-id="9383e-130">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com.</span></span> <span data-ttu-id="9383e-131">相反, Office 365 接收到的所有邮件都必须已经包含有效的 From: address。</span><span class="sxs-lookup"><span data-stu-id="9383e-131">Instead, all messages received by Office 365 must already contain a valid From: address.</span></span> <span data-ttu-id="9383e-132">否则, 邮件将被发送到 Outlook.com 和 Office 365 中的 "垃圾邮件" 或 "已删除邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9383e-132">Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span> 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="9383e-133">语法概述: From: address for Office 365 的有效格式</span><span class="sxs-lookup"><span data-stu-id="9383e-133">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="9383e-134"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="9383e-134"></span></span>

<span data-ttu-id="9383e-135">"发件人: 地址" 的值的格式是在几个 Rfc 中详细定义的。</span><span class="sxs-lookup"><span data-stu-id="9383e-135">The format for the value of the From: address is defined in detail across several RFCs.</span></span> <span data-ttu-id="9383e-136">寻址方面有很多变化, 可视为有效或无效。</span><span class="sxs-lookup"><span data-stu-id="9383e-136">There are many variations on addressing and what may be considered valid or invalid.</span></span> <span data-ttu-id="9383e-137">为了使其简单, Microsoft 建议使用以下格式和定义:</span><span class="sxs-lookup"><span data-stu-id="9383e-137">To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>
  
```
From: "displayname " <emailaddress >
```

<span data-ttu-id="9383e-138">其中：</span><span class="sxs-lookup"><span data-stu-id="9383e-138">Where:</span></span>
  
- <span data-ttu-id="9383e-139">Optional *displayname*是描述电子邮件地址所有者的短语。</span><span class="sxs-lookup"><span data-stu-id="9383e-139">(Optional)  *displayname*  is a phrase that describes the owner of the email address.</span></span> <span data-ttu-id="9383e-140">例如, 这可能是用户友好的名称, 用于描述发件人的名称, 而不是邮箱的名称。</span><span class="sxs-lookup"><span data-stu-id="9383e-140">For example, this might be a more user-friendly name to describe the sender than the name of the mailbox.</span></span> <span data-ttu-id="9383e-141">可选择使用显示名称。</span><span class="sxs-lookup"><span data-stu-id="9383e-141">Using a display name is optional.</span></span> <span data-ttu-id="9383e-142">但是, 如果您选择使用显示名称, Microsoft 建议您始终将其括在引号中, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="9383e-142">However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span> 
    
- <span data-ttu-id="9383e-143">需要 *emailaddress*由以下内容组成:</span><span class="sxs-lookup"><span data-stu-id="9383e-143">(Required)  *emailaddress*  is made up of:</span></span> 
    
  ```
  local-part @domain
  ```

    <span data-ttu-id="9383e-144">其中：</span><span class="sxs-lookup"><span data-stu-id="9383e-144">Where:</span></span>
    
  - <span data-ttu-id="9383e-145">需要 *local-part*是标识与地址关联的邮箱的字符串。</span><span class="sxs-lookup"><span data-stu-id="9383e-145">(Required)  *local-part*  is a string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="9383e-146">这在域中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9383e-146">This is unique within the domain.</span></span> <span data-ttu-id="9383e-147">邮箱所有者的用户名或 GUID 通常用作本地部分的值。</span><span class="sxs-lookup"><span data-stu-id="9383e-147">Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span> 
    
  - <span data-ttu-id="9383e-148">需要 *domain*是邮件服务器的完全限定域名 (FQDN), 该域名托管由电子邮件地址的本地部分标识的邮箱。</span><span class="sxs-lookup"><span data-stu-id="9383e-148">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span> 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="9383e-149">"发件人: 地址" 的格式 (如果不包含显示名称)</span><span class="sxs-lookup"><span data-stu-id="9383e-149">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="9383e-150"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="9383e-150"></span></span>

<span data-ttu-id="9383e-151">格式正确的 "发件人:" 地址不包含显示名称仅包含一个电子邮件地址, 带有或不带尖括号。</span><span class="sxs-lookup"><span data-stu-id="9383e-151">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets.</span></span> <span data-ttu-id="9383e-152">Microsoft 建议您不要用空格分隔尖括号。</span><span class="sxs-lookup"><span data-stu-id="9383e-152">Microsoft recommends that you do not separate the angle brackets with spaces.</span></span> <span data-ttu-id="9383e-153">此外, 在电子邮件地址后不要包含任何内容。</span><span class="sxs-lookup"><span data-stu-id="9383e-153">In addition, don't include anything after the email address.</span></span>
  
<span data-ttu-id="9383e-154">下面的示例是有效的:</span><span class="sxs-lookup"><span data-stu-id="9383e-154">The following examples are valid:</span></span>
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="9383e-155">下面的示例是有效的, 但建议您不要这样做, 因为尖括号和电子邮件地址之间包含空格:</span><span class="sxs-lookup"><span data-stu-id="9383e-155">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>
  
```
From: < sender@contoso.com >
```

<span data-ttu-id="9383e-156">下面的示例是无效的, 因为它在电子邮件地址后包含文本:</span><span class="sxs-lookup"><span data-stu-id="9383e-156">The following example is invalid because it contains text after the email address:</span></span>
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="9383e-157">"发件人: 地址" 的格式 (如果包含显示名称)</span><span class="sxs-lookup"><span data-stu-id="9383e-157">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="9383e-158"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="9383e-158"></span></span>

<span data-ttu-id="9383e-159">对于 "发件人:" 包含显示名称值的地址, 下列规则适用:</span><span class="sxs-lookup"><span data-stu-id="9383e-159">For From: addresses that include a value for the display name, the following rules apply:</span></span>
  
- <span data-ttu-id="9383e-160">如果发件人地址包含显示名称, 并且显示名称中包含逗号, 则显示名称必须用引号括起来。</span><span class="sxs-lookup"><span data-stu-id="9383e-160">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks.</span></span> <span data-ttu-id="9383e-161">例如：</span><span class="sxs-lookup"><span data-stu-id="9383e-161">For example:</span></span>
    
    <span data-ttu-id="9383e-162">下面的示例是有效的:</span><span class="sxs-lookup"><span data-stu-id="9383e-162">The following example is valid:</span></span>
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="9383e-163">以下示例无效:</span><span class="sxs-lookup"><span data-stu-id="9383e-163">The following example is not valid:</span></span>
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="9383e-164">如果显示名称包含逗号因 RFC 5322 而无效, 则不将显示名称括在引号中。</span><span class="sxs-lookup"><span data-stu-id="9383e-164">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>
    
    <span data-ttu-id="9383e-165">作为最佳实践, 无论显示名称中是否有逗号, 都会在显示名称两边加上引号。</span><span class="sxs-lookup"><span data-stu-id="9383e-165">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>
    
- <span data-ttu-id="9383e-166">如果发件人地址包含显示名称, 则电子邮件地址必须括在尖括号中。</span><span class="sxs-lookup"><span data-stu-id="9383e-166">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>
    
    <span data-ttu-id="9383e-167">作为一种最佳做法, Microsoft 强烈建议您在显示名称和电子邮件地址之间插入空格。</span><span class="sxs-lookup"><span data-stu-id="9383e-167">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="9383e-168">有效和无效发件人的其他示例: addresses</span><span class="sxs-lookup"><span data-stu-id="9383e-168">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="9383e-169"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="9383e-169"></span></span>

- <span data-ttu-id="9383e-170">有效</span><span class="sxs-lookup"><span data-stu-id="9383e-170">Valid:</span></span>
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="9383e-171">无效。</span><span class="sxs-lookup"><span data-stu-id="9383e-171">Invalid.</span></span> <span data-ttu-id="9383e-172">电子邮件地址不带尖括号括起来:</span><span class="sxs-lookup"><span data-stu-id="9383e-172">The email address is not enclosed with angle brackets:</span></span>
    
  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="9383e-173">有效, 但不建议使用。</span><span class="sxs-lookup"><span data-stu-id="9383e-173">Valid, but not recommended.</span></span> <span data-ttu-id="9383e-174">显示名称不在引号中。</span><span class="sxs-lookup"><span data-stu-id="9383e-174">The display name is not in quotes.</span></span> <span data-ttu-id="9383e-175">最佳做法是, 始终在显示名称两边加上引号:</span><span class="sxs-lookup"><span data-stu-id="9383e-175">As a best practice, always put quotation marks around the display name:</span></span>
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="9383e-176">无效。</span><span class="sxs-lookup"><span data-stu-id="9383e-176">Invalid.</span></span> <span data-ttu-id="9383e-177">所有内容均括在引号内, 而不只是显示名称:</span><span class="sxs-lookup"><span data-stu-id="9383e-177">Everything is enclosed within quotation marks, not just the display name:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="9383e-178">无效。</span><span class="sxs-lookup"><span data-stu-id="9383e-178">Invalid.</span></span> <span data-ttu-id="9383e-179">电子邮件地址周围没有尖括号:</span><span class="sxs-lookup"><span data-stu-id="9383e-179">There are no angle brackets around the email address:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="9383e-180">无效。</span><span class="sxs-lookup"><span data-stu-id="9383e-180">Invalid.</span></span> <span data-ttu-id="9383e-181">显示名称和左尖括号之间没有空格:</span><span class="sxs-lookup"><span data-stu-id="9383e-181">There is no space between the display name and left angle bracket:</span></span>
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="9383e-182">无效。</span><span class="sxs-lookup"><span data-stu-id="9383e-182">Invalid.</span></span> <span data-ttu-id="9383e-183">在右引号周围的显示名称和左尖括号之间没有空格。</span><span class="sxs-lookup"><span data-stu-id="9383e-183">There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="9383e-184">禁止自动答复您的自定义域, 而无需中断 "发件人:" 策略</span><span class="sxs-lookup"><span data-stu-id="9383e-184">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="9383e-185"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="9383e-185"></span></span>

<span data-ttu-id="9383e-186">使用新的 From: policy 强制, 您无法再使用: \< \>禁止显示自动答复。</span><span class="sxs-lookup"><span data-stu-id="9383e-186">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies.</span></span> <span data-ttu-id="9383e-187">相反, 您需要为您的自定义域设置空的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="9383e-187">Instead, you need to set up a null MX record for your custom domain.</span></span>
  
<span data-ttu-id="9383e-188">邮件交换器 (MX) 记录是 DNS 中的一条资源记录, 用于标识为您的域接收邮件的邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="9383e-188">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain.</span></span> <span data-ttu-id="9383e-189">自动答复 (和所有答复) 自然会被隐含, 因为没有任何已发布的地址发送到响应服务器可以向其发送邮件。</span><span class="sxs-lookup"><span data-stu-id="9383e-189">Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>
  
<span data-ttu-id="9383e-190">为自定义域设置空 MX 记录时:</span><span class="sxs-lookup"><span data-stu-id="9383e-190">When you set up a null MX record for your custom domain:</span></span>
  
- <span data-ttu-id="9383e-191">选择要向其发送不接受 (接收) 电子邮件的邮件的域。</span><span class="sxs-lookup"><span data-stu-id="9383e-191">Choose a domain from which to send messages that doesn't accept (receive) email.</span></span> <span data-ttu-id="9383e-192">例如, 如果您的主域是 contoso.com, 则可以选择 noreply.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="9383e-192">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>
    
- <span data-ttu-id="9383e-193">为您的域设置空的 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="9383e-193">Set up the null MX record for your domain.</span></span> <span data-ttu-id="9383e-194">空的 MX 记录包含一个点, 例如:</span><span class="sxs-lookup"><span data-stu-id="9383e-194">A null MX record consists of a single dot, for example:</span></span>
    
  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="9383e-195">有关发布空 MX 的详细信息, 请参阅[RFC 7505](https://tools.ietf.org/html/rfc7505)。</span><span class="sxs-lookup"><span data-stu-id="9383e-195">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="9383e-196">替代 Office 365 发件人: 地址强制策略</span><span class="sxs-lookup"><span data-stu-id="9383e-196">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="9383e-197"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="9383e-197"></span></span>

<span data-ttu-id="9383e-198">完成新策略的操作后, 您只能通过使用下列方法之一, 对从 Office 365 接收的入站邮件绕过此策略:</span><span class="sxs-lookup"><span data-stu-id="9383e-198">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span> 
  
- <span data-ttu-id="9383e-199">IP 允许列表</span><span class="sxs-lookup"><span data-stu-id="9383e-199">IP allow lists</span></span>
    
- <span data-ttu-id="9383e-200">Exchange Online 邮件流规则</span><span class="sxs-lookup"><span data-stu-id="9383e-200">Exchange Online mail flow rules</span></span>
    
<span data-ttu-id="9383e-201">Microsoft 强烈建议您不要覆盖 From: policy 的强制执行。</span><span class="sxs-lookup"><span data-stu-id="9383e-201">Microsoft strongly recommends against overriding the enforcement of the From: policy.</span></span> <span data-ttu-id="9383e-202">覆盖此策略可能会增加组织暴露给垃圾邮件、网络钓鱼和其他 cybercrimes 的风险。</span><span class="sxs-lookup"><span data-stu-id="9383e-202">Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>
  
<span data-ttu-id="9383e-203">您无法覆盖在 Office 365 中发送的出站邮件的此策略。</span><span class="sxs-lookup"><span data-stu-id="9383e-203">You cannot override this policy for outbound mail you send in Office 365.</span></span> <span data-ttu-id="9383e-204">此外, Outlook.com 不允许覆盖任何种类, 即使支持也是如此。</span><span class="sxs-lookup"><span data-stu-id="9383e-204">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span> 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="9383e-205">阻止和防止 cybercrimes 在 Office 365 中的其他方法</span><span class="sxs-lookup"><span data-stu-id="9383e-205">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="9383e-206"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="9383e-206"></span></span>

<span data-ttu-id="9383e-207">若要详细了解如何在 cybercrimes (如网络钓鱼、垃圾邮件、数据泄露和其他威胁) 上加强组织, 请参阅[Office 365 的安全性最佳实践](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3)。</span><span class="sxs-lookup"><span data-stu-id="9383e-207">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9383e-208">相关主题</span><span class="sxs-lookup"><span data-stu-id="9383e-208">Related Topics</span></span>

[<span data-ttu-id="9383e-209">退信消息和 EOP</span><span class="sxs-lookup"><span data-stu-id="9383e-209">Backscatter messages and EOP</span></span>](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  


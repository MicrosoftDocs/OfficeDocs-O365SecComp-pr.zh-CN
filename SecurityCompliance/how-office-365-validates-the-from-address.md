---
title: Office 365 如何验证发件人地址以防止网络钓鱼
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
description: 为了帮助防止网络钓鱼，Office 365 和 Outlook.com 现在需要 RFC 法规遵从性从： 地址。
ms.openlocfilehash: 562e08aa54cb6544beccb6f0e8760735f67b834b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524844"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="e4963-103">Office 365 如何验证发件人地址以防止网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="e4963-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="e4963-p101">Office 365 和 Outlook.com 电子邮件帐户接收越来越多的网络钓鱼攻击。网络钓鱼者使用的一种方法是发送邮件的发件人具有值： 不符合[RFC 5322](https://tools.ietf.org/html/rfc5322)的地址。从： 地址也称为 5322.From 地址。为了帮助防止此类型的网络钓鱼，Office 365 和 Outlook.com 需要邮件服务收到包含符合 RFC 从： 解决这篇文章中所述。</span><span class="sxs-lookup"><span data-stu-id="e4963-p101">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks. One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322). The From: address is also called the 5322.From address. To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4963-p102">本文中的信息，需要具有基本了解电子邮件地址的一般格式。有关详细信息，请参阅[RFC 5322](https://tools.ietf.org/html/rfc5322) （特别是部分 3.2.3、 3.4、 和 3.4.1）、 [RFC 5321](https://tools.ietf.org/html/rfc5321)，以及[RFC 3696](https://tools.ietf.org/html/rfc3696)。本文是有关策略实施，5322.From 地址。本文不是有关 5321.MailFrom 地址。</span><span class="sxs-lookup"><span data-stu-id="e4963-p102">The information in this article requires you to have a basic understanding of the general format of email addresses. For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696). This article is about policy enforcement for the 5322.From address. This article is not about the 5321.MailFrom address.</span></span> 
  
<span data-ttu-id="e4963-p103">很遗憾，还有仍继续发送"合法"电子邮件已缺少某些旧的电子邮件服务器在 Internet 上或从格式不正确： 地址。如果您经常使用这些旧系统的组织中收到电子邮件，鼓励这些组织要更新其邮件服务器，以符合现代安全标准。</span><span class="sxs-lookup"><span data-stu-id="e4963-p103">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address. If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>
  
<span data-ttu-id="e4963-114">Microsoft 将开始推出上 2017 年 11 月 9，本文中所述的策略的实施。</span><span class="sxs-lookup"><span data-stu-id="e4963-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="e4963-115">Office 365 如何强制从一个有效的使用： 地址阻止网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="e4963-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="e4963-p104">Office 365 正在更改的方式，它强制使用 From： 为了更好的接收的消息中的地址保护您从网络钓鱼攻击。本文内容：</span><span class="sxs-lookup"><span data-stu-id="e4963-p104">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks. In this article:</span></span>
  
- [<span data-ttu-id="e4963-118">所有邮件都必须都包括从有效： 地址</span><span class="sxs-lookup"><span data-stu-id="e4963-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="e4963-119">所有邮件都必须都包括从有效： 地址</span><span class="sxs-lookup"><span data-stu-id="e4963-119">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [<span data-ttu-id="e4963-120">从的格式： 如果不包括的显示名称的地址</span><span class="sxs-lookup"><span data-stu-id="e4963-120">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [<span data-ttu-id="e4963-121">从的格式： 地址如果包括的显示名称</span><span class="sxs-lookup"><span data-stu-id="e4963-121">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [<span data-ttu-id="e4963-122">有效和从无效的其他示例： 地址</span><span class="sxs-lookup"><span data-stu-id="e4963-122">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)
    
- [<span data-ttu-id="e4963-123">禁止对您的自定义域的自动答复，而不会破坏 From： 策略</span><span class="sxs-lookup"><span data-stu-id="e4963-123">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [<span data-ttu-id="e4963-124">Office 365 中重写： 地址实施策略</span><span class="sxs-lookup"><span data-stu-id="e4963-124">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)
    
- [<span data-ttu-id="e4963-125">防止和抵御犯罪 Office 365 中的其他方法</span><span class="sxs-lookup"><span data-stu-id="e4963-125">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)
    
<span data-ttu-id="e4963-126">代表另一个用户发送不受此更改的详细信息，阅读 Terry Zink 博客"[这意味着什么呢时我们统称其发件人电子邮件？](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)"。</span><span class="sxs-lookup"><span data-stu-id="e4963-126">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>
  
### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="e4963-127">所有邮件都必须都包括从有效： 地址</span><span class="sxs-lookup"><span data-stu-id="e4963-127">All messages must include a valid From: address</span></span>
<span data-ttu-id="e4963-128"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="e4963-128"></span></span>

<span data-ttu-id="e4963-p105">某些自动的邮件不包括 From： 地址发送时。在过去，Office 365 或 Outlook.com 时收到消息，而不从： 地址，该服务添加从下面的默认： 地址以使其可交付结果的消息：</span><span class="sxs-lookup"><span data-stu-id="e4963-p105">Some automated messages don't include a From: address when they are sent. In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>
  
```
From: <>
```

<span data-ttu-id="e4963-p106">启动 2017 年 11 月 9，Office 365 将推出更改到其数据中心和邮件服务器，其中将强制实施新规则其中 From 的情况下消息： 地址将无法再接受通过 Office 365 或 Outlook.com。而是接收的 Office 365 的所有邮件必须已经都包含有效从： 地址。否则，消息将发送到 Outlook.com 和 Office 365 中的垃圾邮件或已删除邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4963-p106">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com. Instead, all messages received by Office 365 must already contain a valid From: address. Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span> 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="e4963-134">语法概述： 发件人的有效格式： Office 365 的地址</span><span class="sxs-lookup"><span data-stu-id="e4963-134">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="e4963-135"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="e4963-135"></span></span>

<span data-ttu-id="e4963-p107">从值的格式： 详细跨多个 Rfc 定义地址。有许多变体寻址和内容可能被视为有效或无效。若要保留简单，Microsoft 建议您使用以下格式和定义：</span><span class="sxs-lookup"><span data-stu-id="e4963-p107">The format for the value of the From: address is defined in detail across several RFCs. There are many variations on addressing and what may be considered valid or invalid. To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>
  
```
From: "displayname " <emailaddress >
```

<span data-ttu-id="e4963-139">其中：</span><span class="sxs-lookup"><span data-stu-id="e4963-139">Where:</span></span>
  
- <span data-ttu-id="e4963-p108">（可选） *displayname*是一个短语描述的所有者的电子邮件地址。例如，这可能是邮箱的一个更为用户友好名称，以描述发件人。使用的显示名称是可选的。但是，如果您选择要使用的显示名称，Microsoft 建议，则始终将它引号括起来如下所示。</span><span class="sxs-lookup"><span data-stu-id="e4963-p108">(Optional)  *displayname*  is a phrase that describes the owner of the email address. For example, this might be a more user-friendly name to describe the sender than the name of the mailbox. Using a display name is optional. However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span> 
    
- <span data-ttu-id="e4963-144">（必需） *emailaddress*组成：</span><span class="sxs-lookup"><span data-stu-id="e4963-144">(Required)  *emailaddress*  is made up of:</span></span> 
    
  ```
  local-part @domain
  ```

    <span data-ttu-id="e4963-145">其中：</span><span class="sxs-lookup"><span data-stu-id="e4963-145">Where:</span></span>
    
  - <span data-ttu-id="e4963-p109">（必需） *本地部分*是一个字符串，标识与地址关联的邮箱。这是唯一域中。通常，邮箱所有者的用户名或 GUID 用于为值本地部分。</span><span class="sxs-lookup"><span data-stu-id="e4963-p109">(Required)  *local-part*  is a string that identifies the mailbox associated with the address. This is unique within the domain. Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span> 
    
  - <span data-ttu-id="e4963-149">（必需） *域*是承载本地一部分的电子邮件地址所标识的邮箱的邮件服务器的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e4963-149">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span> 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="e4963-150">从的格式： 如果不包括的显示名称的地址</span><span class="sxs-lookup"><span data-stu-id="e4963-150">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="e4963-151"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="e4963-151"></span></span>

<span data-ttu-id="e4963-p110">从格式正确 A： 不包括的显示名称的地址包括只有单个电子邮件地址使用或不尖括号。Microsoft 建议您不要用空格分隔尖括号。此外，不包括任何内容后的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e4963-p110">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets. Microsoft recommends that you do not separate the angle brackets with spaces. In addition, don't include anything after the email address.</span></span>
  
<span data-ttu-id="e4963-155">下面的示例是有效的：</span><span class="sxs-lookup"><span data-stu-id="e4963-155">The following examples are valid:</span></span>
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="e4963-156">下面的示例是有效的但不是建议包含尖括号和电子邮件地址之间的空格，因此：</span><span class="sxs-lookup"><span data-stu-id="e4963-156">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>
  
```
From: < sender@contoso.com >
```

<span data-ttu-id="e4963-157">下面的示例无效，因为它包含文本后的电子邮件地址：</span><span class="sxs-lookup"><span data-stu-id="e4963-157">The following example is invalid because it contains text after the email address:</span></span>
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="e4963-158">从的格式： 地址如果包括的显示名称</span><span class="sxs-lookup"><span data-stu-id="e4963-158">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="e4963-159"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="e4963-159"></span></span>

<span data-ttu-id="e4963-160">有关从： 包括的显示名称的值的地址，则适用以下规则：</span><span class="sxs-lookup"><span data-stu-id="e4963-160">For From: addresses that include a value for the display name, the following rules apply:</span></span>
  
- <span data-ttu-id="e4963-p111">如果发件人地址中包含的显示名称，并显示名称包括逗号，然后的显示名称必须括在引号内。例如：</span><span class="sxs-lookup"><span data-stu-id="e4963-p111">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks. For example:</span></span>
    
    <span data-ttu-id="e4963-163">下面的示例是有效的：</span><span class="sxs-lookup"><span data-stu-id="e4963-163">The following example is valid:</span></span>
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="e4963-164">下面的示例无效：</span><span class="sxs-lookup"><span data-stu-id="e4963-164">The following example is not valid:</span></span>
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="e4963-165">不在引号内封闭的显示名称，如果该显示名称中包含逗号根据 RFC 5322 无效。</span><span class="sxs-lookup"><span data-stu-id="e4963-165">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>
    
    <span data-ttu-id="e4963-166">作为最佳实践，无论的显示名称周围的 put 的引号是否存在为逗号中的显示名称。</span><span class="sxs-lookup"><span data-stu-id="e4963-166">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>
    
- <span data-ttu-id="e4963-167">如果发件人地址中包含的显示名称，然后尖括号必须括起来的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e4963-167">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>
    
    <span data-ttu-id="e4963-168">作为最佳实践，Microsoft 强烈建议您插入间距的显示名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e4963-168">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="e4963-169">有效和从无效的其他示例： 地址</span><span class="sxs-lookup"><span data-stu-id="e4963-169">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="e4963-170"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e4963-170"></span></span>

- <span data-ttu-id="e4963-171">有效：</span><span class="sxs-lookup"><span data-stu-id="e4963-171">Valid:</span></span>
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="e4963-p112">无效。使用尖括号不包含的电子邮件地址：</span><span class="sxs-lookup"><span data-stu-id="e4963-p112">Invalid. The email address is not enclosed with angle brackets:</span></span>
    
  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="e4963-p113">有效的但不是建议这样做。显示名称不在引号中。作为最佳实践，始终加引号的显示名称：</span><span class="sxs-lookup"><span data-stu-id="e4963-p113">Valid, but not recommended. The display name is not in quotes. As a best practice, always put quotation marks around the display name:</span></span>
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="e4963-p114">无效。所有内容括在引号内，而不仅仅是的显示名称：</span><span class="sxs-lookup"><span data-stu-id="e4963-p114">Invalid. Everything is enclosed within quotation marks, not just the display name:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="e4963-p115">无效。有无尖括号周围的电子邮件地址：</span><span class="sxs-lookup"><span data-stu-id="e4963-p115">Invalid. There are no angle brackets around the email address:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="e4963-p116">无效。没有之间的显示名称和左的尖括号空间：</span><span class="sxs-lookup"><span data-stu-id="e4963-p116">Invalid. There is no space between the display name and left angle bracket:</span></span>
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="e4963-p117">无效。结束 quotation mark 周围的显示名称和左的尖括号之间没有空间。</span><span class="sxs-lookup"><span data-stu-id="e4963-p117">Invalid. There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="e4963-185">禁止对您的自定义域的自动答复，而不会破坏 From： 策略</span><span class="sxs-lookup"><span data-stu-id="e4963-185">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="e4963-186"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="e4963-186"></span></span>

<span data-ttu-id="e4963-p118">与从新： 策略实施，您不能再使用从： \< \>禁止自动答复。相反，您需要设置您的自定义域的 null MX 记录。</span><span class="sxs-lookup"><span data-stu-id="e4963-p118">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies. Instead, you need to set up a null MX record for your custom domain.</span></span>
  
<span data-ttu-id="e4963-p119">邮件交换器 (MX) 记录是标识接收为您的域的邮件的邮件服务器的 DNS a 资源记录。因为没有响应的服务器可以向其发送消息的已发布地址自然禁止自动答复 （和所有回复）。</span><span class="sxs-lookup"><span data-stu-id="e4963-p119">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain. Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>
  
<span data-ttu-id="e4963-191">当您设置为空的 MX 记录为您的自定义域：</span><span class="sxs-lookup"><span data-stu-id="e4963-191">When you set up a null MX record for your custom domain:</span></span>
  
- <span data-ttu-id="e4963-p120">选择一个域从其发送消息的不接受 （接收） 电子邮件。例如，如果您的主要域是 contoso.com，您可能选择 noreply.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e4963-p120">Choose a domain from which to send messages that doesn't accept (receive) email. For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>
    
- <span data-ttu-id="e4963-p121">设置为您的域为空的 MX 记录。空的 MX 记录包含的一个点，例如：</span><span class="sxs-lookup"><span data-stu-id="e4963-p121">Set up the null MX record for your domain. A null MX record consists of a single dot, for example:</span></span>
    
  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="e4963-196">关于发布空的 MX 的详细信息，请参阅[RFC 7505](https://tools.ietf.org/html/rfc7505)。</span><span class="sxs-lookup"><span data-stu-id="e4963-196">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="e4963-197">Office 365 中重写： 地址实施策略</span><span class="sxs-lookup"><span data-stu-id="e4963-197">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="e4963-198"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="e4963-198"></span></span>

<span data-ttu-id="e4963-199">利用新策略的滚动完成后，仅可以跳过此策略使用下列方法之一接收来自 Office 365 的入站邮件：</span><span class="sxs-lookup"><span data-stu-id="e4963-199">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span> 
  
- <span data-ttu-id="e4963-200">IP 允许列表</span><span class="sxs-lookup"><span data-stu-id="e4963-200">IP allow lists</span></span>
    
- <span data-ttu-id="e4963-201">Exchange Online 邮件流规则</span><span class="sxs-lookup"><span data-stu-id="e4963-201">Exchange Online mail flow rules</span></span>
    
<span data-ttu-id="e4963-p122">Microsoft 强烈建议针对替代 From 实施： 策略。覆盖此策略可以增加暴露垃圾邮件和网络钓鱼，其他犯罪贵组织的风险。</span><span class="sxs-lookup"><span data-stu-id="e4963-p122">Microsoft strongly recommends against overriding the enforcement of the From: policy. Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>
  
<span data-ttu-id="e4963-p123">不能重写为 Office 365 中发送的出站邮件此策略。此外，Outlook.com 将不允许覆盖任何种类的即使通过支持。</span><span class="sxs-lookup"><span data-stu-id="e4963-p123">You cannot override this policy for outbound mail you send in Office 365. In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span> 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="e4963-206">防止和抵御犯罪 Office 365 中的其他方法</span><span class="sxs-lookup"><span data-stu-id="e4963-206">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="e4963-207"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="e4963-207"></span></span>

<span data-ttu-id="e4963-208">有关如何可以增强您的组织免受犯罪网络钓鱼等的详细信息，发送垃圾邮件、 数据泄露和其他威胁，请参阅[Office 365 的安全性最佳实践](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3)。</span><span class="sxs-lookup"><span data-stu-id="e4963-208">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e4963-209">相关主题</span><span class="sxs-lookup"><span data-stu-id="e4963-209">Related Topics</span></span>

[<span data-ttu-id="e4963-210">退信消息和 EOP</span><span class="sxs-lookup"><span data-stu-id="e4963-210">Backscatter messages and EOP</span></span>](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  


---
title: 使用除名门户来将自己从 Office 365 阻止的发件人名单中删除
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
description: 当您尝试向其电子邮件地址位于 Office 365 中的收件人发送电子邮件时，是否收到一条错误消息？如果您认为不应该会收到错误消息，则可以使用除名门户将自己从 Office 365 阻止的发件人名单中删除。
ms.openlocfilehash: 18ec4956b8d37308e7ec35c8fc28f24d36cd2763
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598428"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a><span data-ttu-id="619b8-104">使用除名门户将自己从 Office 365 阻止的发件人名单中删除</span><span class="sxs-lookup"><span data-stu-id="619b8-104">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>

<span data-ttu-id="619b8-p102">当您尝试向其电子邮件地址位于 Office 365 中的收件人发送电子邮件时，是否收到一条错误消息？如果您认为不应该会收到错误消息，则可以使用除名门户将自己从 Office 365 阻止的发件人名单中删除。</span><span class="sxs-lookup"><span data-stu-id="619b8-p102">Are you getting an error message when you try to send an email to a recipient whose email address is in Office 365? If you think you should not be receiving the error message, you can use the delist portal to remove yourself from the Office 365 blocked senders list.</span></span>
  
## <a name="what-is-the-office-365-blocked-senders-list"></a><span data-ttu-id="619b8-107">什么是 Office 365 阻止的发件人名单？</span><span class="sxs-lookup"><span data-stu-id="619b8-107">What is the Office 365 blocked senders list?</span></span>

<span data-ttu-id="619b8-p103">Microsoft 使用阻止的发件人名单来防止其客户遭受垃圾邮件、欺诈和网络钓鱼网站的攻击。您的邮件服务器的 IP 地址就是邮件服务器用来在 Internet 上标识自己的地址，由于以下各种原因之一，IP 地址被标记为 Office 365 的一个潜在威胁。当 Office 365 将该 IP 地址添加到列表中时，它会阻止该 IP 地址与通过我们数据中心我的所有客户进行任何进一步的通信。</span><span class="sxs-lookup"><span data-stu-id="619b8-p103">Microsoft uses the blocked senders list to protect its customers from spam, spoofing, and phishing attacks. Your mail server's IP address, that is, the address your mail server uses to identify itself on the Internet, was tagged as a potential threat to Office 365 for one of a variety of reasons. When Office 365 adds the IP address to the list, it prevents all further communication between the IP address and any of our customers through our datacenters.</span></span>
  
<span data-ttu-id="619b8-111">在您收到包含类似于以下错误的邮件回复时，您就知道自己已被添加到该列表中：</span><span class="sxs-lookup"><span data-stu-id="619b8-111">You will know you have been added to the list when you receive a response to a mail message that includes an error that looks something like this:</span></span>
  
> <span data-ttu-id="619b8-112">550 5.7.606-649 访问被拒绝, 禁止发送 IP [_ip 地址_];若要请求从此列表中删除, https://sender.office.com/请访问并按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="619b8-112">550 5.7.606-649 Access denied, banned sending IP [_IP address_]; To request removal from this list please visit https://sender.office.com/ and follow the directions.</span></span> <span data-ttu-id="619b8-113">有关详细信息, 请参阅[Office 365 中的电子邮件未送达报告](http://go.microsoft.com/fwlink/?LinkID=526653)。</span><span class="sxs-lookup"><span data-stu-id="619b8-113">For more information please see [Email non-delivery reports in Office 365](http://go.microsoft.com/fwlink/?LinkID=526653).</span></span>
  
<span data-ttu-id="619b8-114">其中  _IP address_ 是邮件服务器在其上运行的计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="619b8-114">where  _IP address_ is the IP address of the computer on which the mail server runs.</span></span> 
  
### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a><span data-ttu-id="619b8-115">若要使用 Office 365 除名门户来将自己从阻止的发件人名单中删除</span><span class="sxs-lookup"><span data-stu-id="619b8-115">To use the Office 365 delist portal to remove yourself from the blocked senders list</span></span>

1. <span data-ttu-id="619b8-116">在 Web 浏览器中，请转至 [https://sender.office.com](https://sender.office.com)。</span><span class="sxs-lookup"><span data-stu-id="619b8-116">In a web browser, go to [https://sender.office.com](https://sender.office.com).</span></span>
    
2. <span data-ttu-id="619b8-p105">按照页面上的说明执行操作。请确保您使用收到错误消息的电子邮件地址，以及错误消息中指定的 IP 地址。每次访问只能输入一个电子邮件地址和一个 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="619b8-p105">Follow the instructions on the page. Ensure that you use the email address to which the error message was sent, and the IP address that is specified in the error message. You can only enter one email address and one IP address per visit.</span></span>
    
3. <span data-ttu-id="619b8-120">Click **Submit**.</span><span class="sxs-lookup"><span data-stu-id="619b8-120">Click **Submit**.</span></span>
    
    <span data-ttu-id="619b8-121">门户会向您提供的电子邮件地址发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="619b8-121">The portal sends an email to the email address that you supply.</span></span> <span data-ttu-id="619b8-122">电子邮件的外观如下所示: ![通过除名门户提交请求时收到的电子邮件的屏幕截图](media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span><span class="sxs-lookup"><span data-stu-id="619b8-122">The email will look something like the following: ![Screenshot of email received when you submit a request through the delist portal](media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)</span></span>
  
4. <span data-ttu-id="619b8-123">单击除名门户发送给您的电子邮件中的确认链接。</span><span class="sxs-lookup"><span data-stu-id="619b8-123">Click the confirmation link in the email sent to you by the delisting portal.</span></span>
    
    <span data-ttu-id="619b8-124">这将使您返回到除名门户。</span><span class="sxs-lookup"><span data-stu-id="619b8-124">This brings you back to the delist portal.</span></span>
    
5. <span data-ttu-id="619b8-125">In the delist portal, click **Delist IP**.</span><span class="sxs-lookup"><span data-stu-id="619b8-125">In the delist portal, click **Delist IP**.</span></span>
    
    <span data-ttu-id="619b8-p107">从阻止的发件人名单中删除 IP 地址后，来自该 IP 地址的电子邮件将发送给使用 Office 365 的收件人。因此，请确保您确信从该 IP 地址发送的电子邮件不会被滥用或恶意攻击。否则，可能会再次阻止该 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="619b8-p107">After the IP address is removed from the blocked senders list, email messages from that IP address will be delivered to recipients who use Office 365. So, make sure you're confident that email sent from that IP address won't be abusive or malicious; otherwise, the IP address might be blocked again.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="619b8-128">在删除限制之前, 可能需要长达24小时或结果相差很大。</span><span class="sxs-lookup"><span data-stu-id="619b8-128">It may take up to 24 hours or results can vary widely before restrictions are removed.</span></span>
    
<span data-ttu-id="619b8-129">阅读有关[如何防止在 office 365 中将真实电子邮件标记为垃圾](prevent-email-from-being-marked-as-spam.md )邮件并[控制 office 365 中的出站垃圾](outbound-spam-controls.md)邮件的信息, 以防止 IP 被列入黑名单。</span><span class="sxs-lookup"><span data-stu-id="619b8-129">Read about [How to prevent real email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md ) and [Controlling outbound spam in Office 365](outbound-spam-controls.md) to prevent IP from being blacklisted.</span></span>

---
title: 发件人被阻止发送出站垃圾邮件时的示例通知
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
description: 当发件人由于发送出站垃圾邮件而被服务阻止时，您配置出站垃圾邮件策略时指定的域管理员将收到如下所示的通知电子邮件：
ms.openlocfilehash: c9954d3ea16582a66185d574bcb5fc8a1aeebbf9
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027459"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a><span data-ttu-id="f0ab6-103">发件人被阻止发送出站垃圾邮件时的示例通知</span><span class="sxs-lookup"><span data-stu-id="f0ab6-103">Sample notification when a sender is blocked sending outbound spam</span></span>

<span data-ttu-id="f0ab6-104">当发件人由于发送出站垃圾邮件而被服务阻止时，您[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)时指定的域管理员将收到如下所示的通知电子邮件：</span><span class="sxs-lookup"><span data-stu-id="f0ab6-104">When a sender is blocked from the service due to sending outbound spam, the domain admin specified when you [Configure the outbound spam policy](configure-the-outbound-spam-policy.md) will receive a notification email similar to the following:</span></span> 
  
 <span data-ttu-id="f0ab6-105">**发件人地址：** spamalerts@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f0ab6-105">**Sender address:** spamalerts@microsoft.com</span></span> 
  
 <span data-ttu-id="f0ab6-106">**主题：** 出站垃圾邮件通知 - \<  *帐户名称*  \> 被阻止发送出站邮件</span><span class="sxs-lookup"><span data-stu-id="f0ab6-106">**Subject:** Outbound spam notification - \<  *account name*  \> blocked from sending outbound mail</span></span> 
  
 <span data-ttu-id="f0ab6-107">**正文：** 这是从 Exchange Online Protection 垃圾邮件分析系统自动的答复。</span><span class="sxs-lookup"><span data-stu-id="f0ab6-107">**Body:** This is an automated reply from the Exchange Online Protection Spam Analysis System.</span></span> 
  
<span data-ttu-id="f0ab6-p101">因为我们已检测到大量电子邮件标记为垃圾邮件或其他可疑的行为，来自您的组织，您是正在联系。下面的电子邮件帐户已被阻止发送电子邮件 （他们仍可以接收电子邮件）：</span><span class="sxs-lookup"><span data-stu-id="f0ab6-p101">You are being contacted because we have detected high volumes of email marked as spam, or other suspicious behavior, originating from your organization. The following email accounts have been blocked from sending email (they can still receive email):</span></span>
  
<span data-ttu-id="f0ab6-110">\< *帐户名*  \></span><span class="sxs-lookup"><span data-stu-id="f0ab6-110">\< *account name*  \></span></span> 
  
<span data-ttu-id="f0ab6-p102">很可能已泄露此电子邮件帐户。请按照以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f0ab6-p102">It is likely that this email account has been compromised. Please follow these steps:</span></span>
  
1. <span data-ttu-id="f0ab6-113">解决此问题在由您端：</span><span class="sxs-lookup"><span data-stu-id="f0ab6-113">Resolve this issue on your side by:</span></span>
    
  - <span data-ttu-id="f0ab6-114">更改帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="f0ab6-114">Changing the password of the account.</span></span>
    
  - <span data-ttu-id="f0ab6-115">正在确定帐户遭到破坏的情况。</span><span class="sxs-lookup"><span data-stu-id="f0ab6-115">Determining how the account was compromised.</span></span>
    
  - <span data-ttu-id="f0ab6-116">采取预防措施以确保不能在再次利用此漏洞。</span><span class="sxs-lookup"><span data-stu-id="f0ab6-116">Taking precautions to ensure that this vulnerability will not be exploited again.</span></span>
    
  - <span data-ttu-id="f0ab6-117">确认您的出站邮件队列已被清除所有的其余部分消息的数目。</span><span class="sxs-lookup"><span data-stu-id="f0ab6-117">Confirming that your outbound mail queue has been cleared of all offending messages.</span></span>
    
2. <span data-ttu-id="f0ab6-118">使用您正则联系人通道，请联系 Microsoft 支持。</span><span class="sxs-lookup"><span data-stu-id="f0ab6-118">Contact Microsoft support by using your regular contact channel.</span></span>
    
3. <span data-ttu-id="f0ab6-119">介绍您已阻止发送邮件的用户以及问题已经处理了。</span><span class="sxs-lookup"><span data-stu-id="f0ab6-119">Explain that you have a user that is blocked from sending mail and that the problem has been dealt with.</span></span>
    
4. <span data-ttu-id="f0ab6-120">代理将创建支持票证，从而与您提供并升级其具有电子邮件地址或取消阻止的域的信息。</span><span class="sxs-lookup"><span data-stu-id="f0ab6-120">The agent will create a support ticket with the information that you provide and escalate it to have the email address or domain unblocked.</span></span>
    
5. <span data-ttu-id="f0ab6-121">地址已被取消之后，待处理的任何其他问题，您将与他人进行联系和取消阻止接收通知。</span><span class="sxs-lookup"><span data-stu-id="f0ab6-121">After the address has been unblocked, and pending no other issues, you will be contacted and alerted to the unblocking.</span></span>
    
<span data-ttu-id="f0ab6-122">感谢您帮助我们控制有害的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f0ab6-122">Thank you for assisting us in controlling unwanted email.</span></span>
  
<span data-ttu-id="f0ab6-123">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f0ab6-123">Exchange Online Protection.</span></span>
  
<span data-ttu-id="f0ab6-124">\*\*注意 - 本电子邮件由无人监控的地址发送，请勿回复\*\*</span><span class="sxs-lookup"><span data-stu-id="f0ab6-124">\*\*NOTE - Please do not respond to this email as it is sent from an unmonitored address\*\*</span></span>
  
> [!TIP]
> <span data-ttu-id="f0ab6-125">您还可以与通过在[帮助和支持 eop](eop/help-and-support-for-eop.md)选项的支持。</span><span class="sxs-lookup"><span data-stu-id="f0ab6-125">You can also contact support via the options documented at [Help and support for EOP](eop/help-and-support-for-eop.md).</span></span> 
  


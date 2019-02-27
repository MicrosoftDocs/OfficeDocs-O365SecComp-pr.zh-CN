---
title: 发件人被阻止发送出站垃圾邮件时的示例通知
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 当发件人由于发送出站垃圾邮件而被服务阻止时，您配置出站垃圾邮件策略时指定的域管理员将收到如下所示的通知电子邮件：
ms.openlocfilehash: 94af965505f7541600a6cd7937ae881226a2ac79
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275472"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a><span data-ttu-id="c052e-103">发件人被阻止发送出站垃圾邮件时的示例通知</span><span class="sxs-lookup"><span data-stu-id="c052e-103">Sample notification when a sender is blocked sending outbound spam</span></span>

<span data-ttu-id="c052e-104">当发件人由于发送出站垃圾邮件而被服务阻止时，您[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)时指定的域管理员将收到如下所示的通知电子邮件：</span><span class="sxs-lookup"><span data-stu-id="c052e-104">When a sender is blocked from the service due to sending outbound spam, the domain admin specified when you [Configure the outbound spam policy](configure-the-outbound-spam-policy.md) will receive a notification email similar to the following:</span></span> 
  
 <span data-ttu-id="c052e-105">**发件人地址:** spamalerts@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c052e-105">**Sender address:** spamalerts@microsoft.com</span></span> 
  
 <span data-ttu-id="c052e-106">**主题：** 出站垃圾邮件通知 - \<  *帐户名称*  \> 被阻止发送出站邮件</span><span class="sxs-lookup"><span data-stu-id="c052e-106">**Subject:** Outbound spam notification - \<  *account name*  \> blocked from sending outbound mail</span></span> 
  
 <span data-ttu-id="c052e-107">**正文:** 这是 Exchange Online Protection 垃圾邮件分析系统的自动答复。</span><span class="sxs-lookup"><span data-stu-id="c052e-107">**Body:** This is an automated reply from the Exchange Online Protection Spam Analysis System.</span></span> 
  
<span data-ttu-id="c052e-p101">正在联系你, 因为我们检测到大量的电子邮件被标记为垃圾邮件, 或来自你的组织的其他可疑行为。已阻止以下电子邮件帐户发送电子邮件 (他们仍可接收电子邮件):</span><span class="sxs-lookup"><span data-stu-id="c052e-p101">You are being contacted because we have detected high volumes of email marked as spam, or other suspicious behavior, originating from your organization. The following email accounts have been blocked from sending email (they can still receive email):</span></span>
  
<span data-ttu-id="c052e-110">\< *帐户名*  \></span><span class="sxs-lookup"><span data-stu-id="c052e-110">\< *account name*  \></span></span> 
  
<span data-ttu-id="c052e-p102">可能是此电子邮件帐户已泄露。请按照以下步骤操作:</span><span class="sxs-lookup"><span data-stu-id="c052e-p102">It is likely that this email account has been compromised. Please follow these steps:</span></span>
  
1. <span data-ttu-id="c052e-113">在以下位置解决此问题:</span><span class="sxs-lookup"><span data-stu-id="c052e-113">Resolve this issue on your side by:</span></span>
    
  - <span data-ttu-id="c052e-114">更改帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="c052e-114">Changing the password of the account.</span></span>
    
  - <span data-ttu-id="c052e-115">确定帐户的泄露方式。</span><span class="sxs-lookup"><span data-stu-id="c052e-115">Determining how the account was compromised.</span></span>
    
  - <span data-ttu-id="c052e-116">采取预防措施以确保不会再次利用此漏洞。</span><span class="sxs-lookup"><span data-stu-id="c052e-116">Taking precautions to ensure that this vulnerability will not be exploited again.</span></span>
    
  - <span data-ttu-id="c052e-117">确认您的出站邮件队列已清除所有有问题的邮件。</span><span class="sxs-lookup"><span data-stu-id="c052e-117">Confirming that your outbound mail queue has been cleared of all offending messages.</span></span>
    
2. <span data-ttu-id="c052e-118">使用您的常规联系人频道联系 Microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="c052e-118">Contact Microsoft support by using your regular contact channel.</span></span>
    
3. <span data-ttu-id="c052e-119">说明您的用户已被阻止发送邮件, 并且问题已被处理。</span><span class="sxs-lookup"><span data-stu-id="c052e-119">Explain that you have a user that is blocked from sending mail and that the problem has been dealt with.</span></span>
    
4. <span data-ttu-id="c052e-120">代理将使用您提供的信息创建支持票证, 并将其升级以使电子邮件地址或域解除阻止。</span><span class="sxs-lookup"><span data-stu-id="c052e-120">The agent will create a support ticket with the information that you provide and escalate it to have the email address or domain unblocked.</span></span>
    
5. <span data-ttu-id="c052e-121">在地址被取消阻止且未挂起任何其他问题之后, 将联系并提醒您解除阻止。</span><span class="sxs-lookup"><span data-stu-id="c052e-121">After the address has been unblocked, and pending no other issues, you will be contacted and alerted to the unblocking.</span></span>
    
<span data-ttu-id="c052e-122">感谢你帮助我们控制不需要的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c052e-122">Thank you for assisting us in controlling unwanted email.</span></span>
  
<span data-ttu-id="c052e-123">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c052e-123">Exchange Online Protection.</span></span>
  
<span data-ttu-id="c052e-124">\*\*注意 - 本电子邮件由无人监控的地址发送，请勿回复\*\*</span><span class="sxs-lookup"><span data-stu-id="c052e-124">\*\*NOTE - Please do not respond to this email as it is sent from an unmonitored address\*\*</span></span>
  
> [!TIP]
> <span data-ttu-id="c052e-125">您还可以通过[帮助和支持 EOP](eop/help-and-support-for-eop.md)中记录的选项联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="c052e-125">You can also contact support via the options documented at [Help and support for EOP](eop/help-and-support-for-eop.md).</span></span> 
  


---
title: 发件人被阻止发送出站垃圾邮件时的示例通知
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 当发件人由于发送出站垃圾邮件而被服务阻止时，您配置出站垃圾邮件策略时指定的域管理员将收到如下所示的通知电子邮件：
ms.openlocfilehash: 04d8bde8e9cadd3525191a5bee7d368229e85056
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260970"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a><span data-ttu-id="ac678-103">发件人被阻止发送出站垃圾邮件时的示例通知</span><span class="sxs-lookup"><span data-stu-id="ac678-103">Sample notification when a sender is blocked sending outbound spam</span></span>

<span data-ttu-id="ac678-104">当发件人由于发送出站垃圾邮件而被服务阻止时，您[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)时指定的域管理员将收到如下所示的通知电子邮件：</span><span class="sxs-lookup"><span data-stu-id="ac678-104">When a sender is blocked from the service due to sending outbound spam, the domain admin specified when you [Configure the outbound spam policy](configure-the-outbound-spam-policy.md) will receive a notification email similar to the following:</span></span> 
  
 <span data-ttu-id="ac678-105">**发件人地址:** spamalerts@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ac678-105">**Sender address:** spamalerts@microsoft.com</span></span> 
  
 <span data-ttu-id="ac678-106">**主题：** 出站垃圾邮件通知 - \<  *帐户名称*  \> 被阻止发送出站邮件</span><span class="sxs-lookup"><span data-stu-id="ac678-106">**Subject:** Outbound spam notification - \<  *account name*  \> blocked from sending outbound mail</span></span> 
  
 <span data-ttu-id="ac678-107">**正文:** 这是 Exchange Online Protection 垃圾邮件分析系统的自动答复。</span><span class="sxs-lookup"><span data-stu-id="ac678-107">**Body:** This is an automated reply from the Exchange Online Protection Spam Analysis System.</span></span> 
  
<span data-ttu-id="ac678-108">我们联系您是因为我们检测到从您组织发出的大量电子邮件标记为垃圾邮件或存在其他可疑行为。</span><span class="sxs-lookup"><span data-stu-id="ac678-108">You are being contacted because we have detected high volumes of email marked as spam, or other suspicious behavior, originating from your organization.</span></span> <span data-ttu-id="ac678-109">已阻止以下电子邮件帐户发送电子邮件 (他们仍可接收电子邮件):</span><span class="sxs-lookup"><span data-stu-id="ac678-109">The following email accounts have been blocked from sending email (they can still receive email):</span></span>
  
<span data-ttu-id="ac678-110">\< *帐户名*  \></span><span class="sxs-lookup"><span data-stu-id="ac678-110">\< *account name*  \></span></span> 
  
<span data-ttu-id="ac678-111">很可能此电子邮件帐户已受到威胁。</span><span class="sxs-lookup"><span data-stu-id="ac678-111">It is likely that this email account has been compromised.</span></span> <span data-ttu-id="ac678-112">请按照以下步骤操作:</span><span class="sxs-lookup"><span data-stu-id="ac678-112">Please follow these steps:</span></span>
  
1. <span data-ttu-id="ac678-113">在以下位置解决此问题:</span><span class="sxs-lookup"><span data-stu-id="ac678-113">Resolve this issue on your side by:</span></span>
    
  - <span data-ttu-id="ac678-114">更改帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="ac678-114">Changing the password of the account.</span></span>
    
  - <span data-ttu-id="ac678-115">确定帐户的泄露方式。</span><span class="sxs-lookup"><span data-stu-id="ac678-115">Determining how the account was compromised.</span></span>
    
  - <span data-ttu-id="ac678-116">采取预防措施以确保不会再次利用此漏洞。</span><span class="sxs-lookup"><span data-stu-id="ac678-116">Taking precautions to ensure that this vulnerability will not be exploited again.</span></span>
    
  - <span data-ttu-id="ac678-117">确认您的出站邮件队列已清除所有有问题的邮件。</span><span class="sxs-lookup"><span data-stu-id="ac678-117">Confirming that your outbound mail queue has been cleared of all offending messages.</span></span>
    
2. <span data-ttu-id="ac678-118">使用您的常规联系人频道联系 Microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="ac678-118">Contact Microsoft support by using your regular contact channel.</span></span>
    
3. <span data-ttu-id="ac678-119">说明您的用户已被阻止发送邮件, 并且问题已被处理。</span><span class="sxs-lookup"><span data-stu-id="ac678-119">Explain that you have a user that is blocked from sending mail and that the problem has been dealt with.</span></span>
    
4. <span data-ttu-id="ac678-120">代理将使用您提供的信息创建支持票证, 并将其升级以使电子邮件地址或域解除阻止。</span><span class="sxs-lookup"><span data-stu-id="ac678-120">The agent will create a support ticket with the information that you provide and escalate it to have the email address or domain unblocked.</span></span>
    
5. <span data-ttu-id="ac678-121">在地址被取消阻止且未挂起任何其他问题之后, 将联系并提醒您解除阻止。</span><span class="sxs-lookup"><span data-stu-id="ac678-121">After the address has been unblocked, and pending no other issues, you will be contacted and alerted to the unblocking.</span></span>
    
<span data-ttu-id="ac678-122">感谢你帮助我们控制不需要的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ac678-122">Thank you for assisting us in controlling unwanted email.</span></span>
  
<span data-ttu-id="ac678-123">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ac678-123">Exchange Online Protection.</span></span>
  
<span data-ttu-id="ac678-124">\*\*注意 - 本电子邮件由无人监控的地址发送，请勿回复\*\*</span><span class="sxs-lookup"><span data-stu-id="ac678-124">\*\*NOTE - Please do not respond to this email as it is sent from an unmonitored address\*\*</span></span>
  
> [!TIP]
> <span data-ttu-id="ac678-125">您还可以通过[帮助和支持 EOP](eop/help-and-support-for-eop.md)中记录的选项联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="ac678-125">You can also contact support via the options documented at [Help and support for EOP](eop/help-and-support-for-eop.md).</span></span> 
  


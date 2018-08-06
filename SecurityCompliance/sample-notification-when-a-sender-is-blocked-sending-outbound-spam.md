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
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a>发件人被阻止发送出站垃圾邮件时的示例通知

当发件人由于发送出站垃圾邮件而被服务阻止时，您[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)时指定的域管理员将收到如下所示的通知电子邮件： 
  
 **发件人地址：** spamalerts@microsoft.com 
  
 **主题：** 出站垃圾邮件通知 - \<  *帐户名称*  \> 被阻止发送出站邮件 
  
 **正文：** 这是从 Exchange Online Protection 垃圾邮件分析系统自动的答复。 
  
因为我们已检测到大量电子邮件标记为垃圾邮件或其他可疑的行为，来自您的组织，您是正在联系。下面的电子邮件帐户已被阻止发送电子邮件 （他们仍可以接收电子邮件）：
  
\< *帐户名*  \> 
  
很可能已泄露此电子邮件帐户。请按照以下步骤：
  
1. 解决此问题在由您端：
    
  - 更改帐户的密码。
    
  - 正在确定帐户遭到破坏的情况。
    
  - 采取预防措施以确保不能在再次利用此漏洞。
    
  - 确认您的出站邮件队列已被清除所有的其余部分消息的数目。
    
2. 使用您正则联系人通道，请联系 Microsoft 支持。
    
3. 介绍您已阻止发送邮件的用户以及问题已经处理了。
    
4. 代理将创建支持票证，从而与您提供并升级其具有电子邮件地址或取消阻止的域的信息。
    
5. 地址已被取消之后，待处理的任何其他问题，您将与他人进行联系和取消阻止接收通知。
    
感谢您帮助我们控制有害的电子邮件。
  
Exchange Online Protection
  
\*\*注意 - 本电子邮件由无人监控的地址发送，请勿回复\*\*
  
> [!TIP]
> 您还可以与通过在[帮助和支持 eop](eop/help-and-support-for-eop.md)选项的支持。 
  


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
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a>发件人被阻止发送出站垃圾邮件时的示例通知

当发件人由于发送出站垃圾邮件而被服务阻止时，您[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)时指定的域管理员将收到如下所示的通知电子邮件： 
  
 **发件人地址:** spamalerts@microsoft.com 
  
 **主题：** 出站垃圾邮件通知 - \<  *帐户名称*  \> 被阻止发送出站邮件 
  
 **正文:** 这是 Exchange Online Protection 垃圾邮件分析系统的自动答复。 
  
我们联系您是因为我们检测到从您组织发出的大量电子邮件标记为垃圾邮件或存在其他可疑行为。 已阻止以下电子邮件帐户发送电子邮件 (他们仍可接收电子邮件):
  
\< *帐户名*  \> 
  
很可能此电子邮件帐户已受到威胁。 请按照以下步骤操作:
  
1. 在以下位置解决此问题:
    
  - 更改帐户的密码。
    
  - 确定帐户的泄露方式。
    
  - 采取预防措施以确保不会再次利用此漏洞。
    
  - 确认您的出站邮件队列已清除所有有问题的邮件。
    
2. 使用您的常规联系人频道联系 Microsoft 支持部门。
    
3. 说明您的用户已被阻止发送邮件, 并且问题已被处理。
    
4. 代理将使用您提供的信息创建支持票证, 并将其升级以使电子邮件地址或域解除阻止。
    
5. 在地址被取消阻止且未挂起任何其他问题之后, 将联系并提醒您解除阻止。
    
感谢你帮助我们控制不需要的电子邮件。
  
Exchange Online Protection
  
\*\*注意 - 本电子邮件由无人监控的地址发送，请勿回复\*\*
  
> [!TIP]
> 您还可以通过[帮助和支持 EOP](eop/help-and-support-for-eop.md)中记录的选项联系支持人员。 
  


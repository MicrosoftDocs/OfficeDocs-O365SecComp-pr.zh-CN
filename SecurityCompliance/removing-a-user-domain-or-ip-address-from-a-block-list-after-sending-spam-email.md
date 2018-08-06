---
title: 发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/20/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: 如果用户从为垃圾邮件分类的 Office 365 持续发送电子邮件，它们将阻止发送任何详细消息。
ms.openlocfilehash: ce52ddfd96b582911bb519c15bbfe90351946db8
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026329"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址

如果用户从为垃圾邮件分类的 Office 365 持续发送电子邮件，它们将阻止发送任何详细消息。 
  
当发件人阻止发送电子邮件消息时，他们将收到未送达报告 （NDR 或无法发送邮件的电子邮件），提供有关所必须采取取消阻止自己的步骤的特定信息。
  
不仅可以通过服务，而特定网站域，阻止各个用户，还会阻止 IP 地址。在某些情况下，域或网站可以被添加到阻止列表只是因为它们出现在垃圾邮件。为 Office 365 管理中心中，您可以尝试获取用户、 网站、 域和从第三方阻止列表删除 IP 地址。使用本主题底部表中的链接联系，每个第三方，然后按照说明进行操作。如果 Office 365 外部的某个人无法将邮件发送给您的 Office 365 帐户，其帐户可能外部阻止发件人列表上已结束。Office 365 以外的用户可以尝试通过使用[自助服务除名门户](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx)中将自己删除被阻止的发件人名单。
  
您可以配置出站垃圾邮件设置，以便在 Office 365 用户阻止发送为垃圾邮件分类的电子邮件时获取 anotification。解决用户邮箱的问题后，您可以删除的阻止的发件人。
  
## <a name="unblock-a-blocked-office-365-email-account"></a>解除对被阻止的 Office 365 电子邮件帐户的阻止

完成 Exchange 管理员中心 (EAC) 中的此任务。有关 EAC 的详细信息，请查看[Exchange 管理员中心在 Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md) 。 
  
> [!NOTE]
> 只有在 Exchange Online 的 EAC 中才能看到操作中心。 
  
1. 在 EAC 中，导航到**保护** \> **操作中心**。
    
    ![导航至 Exchange 管理中心的操作中心。](media/9bbf0844-7b34-4a86-a2b7-8c7e9c8519a3.png)
  
2. 选择**搜索**图标，然后输入阻止用户的 SMTP 地址。 
    
    ![在操作中心搜索受阻止的用户](media/f931b5a0-7115-4d95-9f6f-b403436031ba.png)
  
3. 在说明窗格中，单击**取消阻止客户**。 
    
    ![在操作中心取消阻止用户](media/c5d5b1b9-8416-45aa-9631-881e94d1d056.png)
  
4. 单击**是**以确认更改。 
    
> [!NOTE]
> 没有帐户可以取消由租户管理员的次数限制如果已超出限制的用户，将显示一条错误消息。若要取消阻止用户的联系人支持。 
  
## <a name="third-party-block-lists"></a>第三方阻止列表

|**列表名称**|**除名门户**|**详细信息**|
|:-----|:-----|:-----|
|URIBL  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[URIBL 网站](https://uribl.com/) <br/> |
|SURBL  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[介绍 SURBL URI 信誉数据](http://www.surbl.org/) <br/> |
|Spamhaus   <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[了解 DNSBL 筛选](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|invaluement  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[invaluement 反垃圾邮件列表](http://dnsbl.invaluement.com/) <br/> |
|Phishtank  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[PhishTank 常见问题](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> Exchange Online Protection 还使用第三方阻止列表的垃圾邮件筛选。 
   
## <a name="for-more-information"></a>详细信息

[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)
  
[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)

[使用除名门户来将自己从 Office 365 阻止的发件人名单中删除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  


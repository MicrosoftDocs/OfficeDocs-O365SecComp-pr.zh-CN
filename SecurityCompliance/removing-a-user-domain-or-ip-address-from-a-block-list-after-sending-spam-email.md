---
title: 发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: 如果用户从为垃圾邮件分类的 Office 365 持续发送电子邮件，它们将阻止发送任何详细消息。
ms.openlocfilehash: 3f3130bec3cde4cdc1343a0140a9013deacfc519
ms.sourcegitcommit: d85fc77cba3a17d5ddf215e2f506f61b499e0cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "23839106"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址

如果用户从为垃圾邮件分类的 Office 365 持续发送电子邮件，它们将阻止发送任何详细消息。 
  
当发件人阻止发送电子邮件消息时，他们将收到未送达报告 （NDR 或无法发送邮件的电子邮件），提供有关所必须采取取消阻止自己的步骤的特定信息。
  
不仅可以通过服务，而特定网站域，阻止各个用户，还会阻止 IP 地址。在某些情况下，域或网站可以被添加到阻止列表只是因为它们出现在垃圾邮件。为 Office 365 管理中心中，您可以尝试获取用户、 网站、 域和从第三方阻止列表删除 IP 地址。使用本主题底部表中的链接联系，每个第三方，然后按照说明进行操作。如果 Office 365 外部的某个人无法将邮件发送给您的 Office 365 帐户，其帐户可能外部阻止发件人列表上已结束。Office 365 以外的用户可以尝试通过使用[自助服务除名门户](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx)中将自己删除被阻止的发件人名单。
  
您可以配置出站垃圾邮件设置，以便在 Office 365 用户阻止发送为垃圾邮件分类的电子邮件时获取 anotification。解决用户邮箱的问题后，您可以删除的阻止的发件人。
  
## <a name="unblock-a-blocked-office-365-email-account"></a>解除对被阻止的 Office 365 电子邮件帐户的阻止

完成此任务中的 Office 365 安全性和合规性中心 (SCC)。有关 SCC 的详细信息[转到 Office 365 安全性和合规性中心](go-to-the-securitycompliance-center.md)。

1. 使用具有 Office 365 全局管理员权限，登录到 Office 365 安全性和合规性中心和在左侧列表中，展开**威胁管理**，选择**查看**，然后选择**受限的工作或学校帐户用户**。
    
    > [!TIP]
    > 若要直接转到安全中的**受限制的用户**页上&amp;合规性中心，使用以下 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. 此页将包含已被阻止发送到组织外部的邮件的用户列表。 查找的用户要在**取消阻止**删除限制，然后单击。

3. 单击**是**以确认更改。 
    
> [!NOTE]
> 没有帐户可以取消由租户管理员的次数限制如果已超出限制的用户，将显示一条错误消息。然后，您将需要联系支持取消阻止用户。 
  
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
  

  


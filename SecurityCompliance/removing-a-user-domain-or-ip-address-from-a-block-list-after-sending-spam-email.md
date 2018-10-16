---
title: 发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/16/2018
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
ms.openlocfilehash: 295d92fc6a1cd26783b18304a2d119d2ea0d7f1f
ms.sourcegitcommit: b164d4af65709133e0b512a4327a70fae13a974d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "25577061"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址

如果用户从为垃圾邮件分类的 Office 365 持续发送电子邮件，它们将阻止发送任何详细消息。用户将列在作为错误出站发件人的服务，并将接收未送达报告 (NDR) 的状态：

- 无法将发送消息，因为您未被识别为有效的发件人。最常见原因是您的电子邮件地址可疑的垃圾邮件的发送和已不再允许发送组织外部的邮件。与电子邮件管理员联系以寻求帮助。 远程服务器返回 550 5.1.8 访问被拒绝，错误的出站发件人

您可以配置出站垃圾邮件策略设置，以便在 Office 365 用户阻止发送电子邮件时收到通知。解决用户邮箱的问题后，您可以删除的阻止的发件人。
  
## <a name="unblock-a-blocked-office-365-email-account"></a>解除对被阻止的 Office 365 电子邮件帐户的阻止

完成此任务中的 Office 365 安全性和合规性中心 (SCC)。有关 SCC 的详细信息[转到 Office 365 安全性和合规性中心](go-to-the-securitycompliance-center.md)。

1. 使用具有 Office 365 全局管理员权限，登录到 Office 365 安全性和合规性中心和在左侧列表中，展开**威胁管理**，选择**查看**，然后选择**受限的工作或学校帐户用户**。
    
    > [!TIP]
    > 若要直接转到**受限制的用户**页上 （之前被称为操作中心） 中的安全&amp;合规性中心，使用以下 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. 此页将包含已被阻止发送到组织外部的邮件的用户列表。 查找想要在删除限制，然后单击它在**取消阻止**用户。

3. 单击**是**以确认更改。 
    
> [!NOTE]
> 没有帐户可以取消由租户管理员的次数限制如果已超出限制的用户，将显示一条错误消息。然后，您将需要联系支持取消阻止用户。
  
## <a name="third-party-block-lists"></a>第三方阻止列表

Exchange Online Protection 还使用第三方阻止列表来帮助在垃圾邮件筛选决策。可以添加用户、 网站、 域和 IP 地址阻止列表仅为显示在垃圾邮件。为 Office 365 管理中心中，您应尝试获取如果属于您从第三方列表提供程序中删除这些对象。

> [!NOTE]
> 如果 Office 365 外部的某个人无法将邮件发送给您的 Office 365 帐户，其帐户可能在外部的阻止发件人列表。Office 365 以外的用户可以尝试使用[自助服务除名门户](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)删除本身。 

## <a name="for-more-information"></a>详细信息

[响应受到攻击的电子邮件帐户](responding-to-a-compromised-email-account.md)

[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)
  
[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)

  

  


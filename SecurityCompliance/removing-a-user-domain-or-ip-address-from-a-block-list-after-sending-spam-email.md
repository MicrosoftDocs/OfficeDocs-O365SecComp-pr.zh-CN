---
title: 发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/01/2018
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
ms.openlocfilehash: 6f6f4504a9c79463aadc21f2eaeadcd769e8b151
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614396"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址

如果用户从为垃圾邮件分类的 Office 365 持续发送电子邮件，它们将阻止发送任何详细消息。用户将列在作为错误出站发件人的服务，并将接收未送达报告 (NDR) 的状态：

- 无法将发送消息，因为您未被识别为有效的发件人。最常见原因是您的电子邮件地址可疑的垃圾邮件的发送和已不再允许发送组织外部的邮件。与电子邮件管理员联系以寻求帮助。 远程服务器返回 550 5.1.8 访问被拒绝，错误的出站发件人

租户管理员还将收到通知，指出发送任何多出站消息限制了用户。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？
<a name="sectionSection0"> </a>

估计完成时间：5 分钟
  
您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅"反垃圾邮件[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的条目。

也可以通过远程 PowerShell 执行以下过程。使用 Get-BlockedSenderAddress cmdlet 可获取受限的用户和删除-BlockedSenderAddress 删除限制的列表。若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?linkid=396554)。

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>删除被阻止的 Office 365 电子邮件帐户的限制

完成此任务中 Office 365 安全性 & 合规性中心 (SCC)。有关 SCC 的详细信息[转到 Office 365 安全性 & 合规性中心](go-to-the-securitycompliance-center.md)。您需要是**组织管理**或**安全管理员**角色组中，才能执行这些功能。有关 SCC 角色组的详细信息[转到 Office 365 安全性 & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。

1. 使用具有 Office 365 全局管理员权限，登录到 Office 365 安全性和合规性中心和在左侧列表中，展开**威胁管理**，选择**查看**，然后选择**受限的工作或学校帐户用户**。
    
    > [!TIP]
    > 若要直接转到**受限制的用户**页上 （之前被称为操作中心） 中的安全&amp;合规性中心，使用以下 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. 此页将包含已被阻止发送到组织外部的邮件的用户列表。 查找想要在删除限制，然后单击它在**取消阻止**用户。

3. 单击**是**以确认更改。 
    
> [!NOTE]
> 没有帐户可以取消由租户管理员的次数限制如果已超出限制的用户，将显示一条错误消息。然后，您将需要联系支持取消阻止用户。</br></br> 可能需要用户未被阻止之前 1 小时。
  
## <a name="third-party-block-lists"></a>第三方阻止列表

Exchange Online Protection 还使用第三方阻止列表来帮助在垃圾邮件筛选决策。可以添加用户、 网站、 域和 IP 地址阻止列表仅为显示在垃圾邮件。为 Office 365 管理中心中，您应尝试获取如果属于您从第三方列表提供程序中删除这些对象。

> [!NOTE]
> 如果 Office 365 外部的某个人无法将邮件发送给您的 Office 365 帐户，其帐户可能在外部的阻止发件人列表。Office 365 以外的用户可以尝试使用[自助服务除名门户](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)删除本身。 

## <a name="for-more-information"></a>更多信息

[响应受到攻击的电子邮件帐户](responding-to-a-compromised-email-account.md)

[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)
  
[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)

[Office 365 安全 & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)

  


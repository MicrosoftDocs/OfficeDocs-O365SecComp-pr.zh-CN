---
title: 发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址
ms.author: tracyp
author: MSFTTracyP
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
ms.collection:
- M365-security-compliance
description: 如果用户连续发送来自被分类为垃圾邮件的 Office 365 的电子邮件, 则会阻止发送更多的邮件。
ms.openlocfilehash: 870e5eabca9e799dfca1e99846a5bfe845f65df4
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275932"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址

如果用户连续发送来自被分类为垃圾邮件的 Office 365 的电子邮件, 则会阻止发送更多的邮件。用户将在服务中列为错误的出站发件人, 并将收到一份状态为的未送达报告 (NDR):

- 无法传递你的邮件, 因为你未被识别为有效发件人。导致此问题的最常见原因是, 您的电子邮件地址怀疑发送垃圾邮件, 并且不再允许它在您的组织外部发送邮件。请联系你的电子邮件管理员以获取帮助。 远程服务器返回 "550 5.1.8 访问被拒绝, 错误的出站发件人"

租户管理员还会收到一条警报, 指示用户已受到限制, 无法发送任何更多的出站邮件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？
<a name="sectionSection0"> </a>

估计完成时间：5 分钟
  
您需要先分配权限, 然后才能执行此过程或过程。若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的 "反垃圾邮件" 条目。

还可以通过远程 PowerShell 执行以下过程。使用 BlockedSenderAddress cmdlet 获取受限制的用户列表, 并删除-BlockedSenderAddress 以删除限制。若要了解如何使用 Windows PowerShell 连接到 exchange online, 请参阅[连接到 exchange online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>删除对被阻止的 Office 365 电子邮件帐户的限制

您可以在 Office 365 Security & 合规中心 (SCC) 中完成此任务。有关 SCC 的更多详细信息,[请转到 Office 365 安全 & 合规中心](go-to-the-securitycompliance-center.md)。必须在 "**组织管理**" 或 "**安全管理员**" 角色组中, 才能执行这些功能。有关 SCC 角色组的详细信息,[请转到 Office 365 安全 & 合规中心中的 "权限"](permissions-in-the-security-and-compliance-center.md) 。

1. 使用具有 office 365 全局管理员权限的工作或学校帐户登录到 office 365 安全性和合规性中心, 并在左侧的列表中展开 "**威胁管理**", 选择 "**查看**", 然后选择 "**受限"用户**。
    
    > [!TIP]
    > 若要直接转到安全&amp;合规性中心中的 "**受限用户**" 页 (以前称为 "操作中心"), 请使用以下 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. 此页面将包含已阻止向组织外部发送邮件的用户的列表。 查找要删除限制的用户, 然后单击 "**取消阻止**"。

3. 单击 **"是"** 确认更改。 
    
> [!NOTE]
> 限制某个帐户可被租户管理员取消阻止的次数。如果超过了用户的限制, 将显示一条错误消息。你将需要联系支持人员以取消阻止用户。<br/><br/> 在用户取消阻止之前, 可能需要长达1小时。
  
## <a name="third-party-block-lists"></a>第三方阻止列表

Exchange Online Protection 还使用第三方阻止列表来帮助在垃圾邮件筛选中做出决定。可以将用户、网站、域和 IP 地址添加到阻止列表中, 只是在垃圾邮件中显示。作为 Office 365 管理员, 如果用户属于您, 应尝试从第三方列表提供程序中删除这些对象。

> [!NOTE]
> 如果 office 365 外部的人员无法向您的 Office 365 帐户发送邮件, 则其帐户可能位于外部阻止发件人列表中。Office 365 之外的用户可以尝试使用[自助服务除名门户](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)删除自己。 

## <a name="for-more-information"></a>更多信息

[响应已泄露的电子邮件帐户](responding-to-a-compromised-email-account.md)

[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)
  
[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)

[Office 365 安全 & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)

  


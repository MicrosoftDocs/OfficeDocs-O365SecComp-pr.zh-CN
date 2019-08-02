---
title: 配置出站垃圾邮件策略
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/10/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 如果您使用出站垃圾邮件筛选来发送出站电子邮件，那么将始终启用该服务，从而保护使用此服务的组织及其目标收件人。
ms.openlocfilehash: 2bf2f8c7292bee4d1e89249bcec5c74a4b5d38c9
ms.sourcegitcommit: bc25ea19c0b6d318751eadc4f27902b0054d5e2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "36054650"
---
# <a name="configure-the-outbound-spam-policy"></a>配置出站垃圾邮件策略

如果您使用出站垃圾邮件筛选来发送出站电子邮件，那么将始终启用该服务，从而保护使用此服务的组织及其目标收件人。与入站筛选类似，出站垃圾邮件筛选由连接筛选和内容筛选构成，但出站筛选设置无法配置。如果出站邮件确定为垃圾邮件，则会通过高风险传送池进行路由，这会降低正常出站 IP 池添加到阻止列表的可能性。如果客户继续通过该服务发送出站垃圾邮件，其邮件的发送将受到阻止。尽管无法禁用或更改出站垃圾邮件筛选，但您可以通过默认出站垃圾邮件策略来配置几个全公司的出站垃圾邮件设置。 
  
以下视频显示了如何配置出站垃圾邮件策略：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
> [!NOTE]
> 为了获得最佳的筛选结果, 应在正确的设置中使用上述视频中的内容, 并熟悉[Office 365 中的出站垃圾邮件控件](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？
<a name="sectionSection0"> </a>

估计完成时间：5 分钟
  
您必须先获得权限，然后才能执行此过程或多个过程。 若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的 "反垃圾邮件" 条目。 
  
若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
  
还可以通过远程 PowerShell 执行以下过程。 使用[HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) cmdlet 可查看您的设置, 以及用于编辑出站垃圾邮件策略设置的[HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) 。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection, 请参阅[连接到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a>使用 EAC 编辑默认出站垃圾邮件策略
<a name="sectionSection1"> </a>

使用以下步骤编辑默认出站垃圾邮件策略：
  
### <a name="to-configure-the-default-outbound-spam-policy"></a>要配置默认出站垃圾邮件策略

1. 在 Exchange 管理中心 (EAC) 中, 导航到 "**保护** \> **出站垃圾邮件**", 然后双击默认策略。
    
2. 选择 "**出站垃圾邮件首**选项" 菜单选项。 
    
3. 选中以下与出站邮件有关的复选框，然后在显示的输入框中指定关联的电子邮件地址或地址（如果这些地址解析为有效 SMTP 目标，则它们可能是通讯组列表）：
    
1. 将**所有可疑的出站电子邮件的副本发送到以下电子邮件地址或地址**。 这些是筛选器标记为垃圾邮件的邮件（无论 SCL 分级）。 它们未被筛选器拒绝，但是将通过高风险传输工具路由。 用分号分隔多个地址。 请注意，指定的收件人将作为密件抄送 (Bcc) 地址接收邮件（"发件人"和"收件人"字段是原始的发件人和收件人）。
    
2. **当发件人被阻止发送出站垃圾邮件时, 向以下电子邮件地址发送通知**。 用分号分隔多个地址。
    
    当大量垃圾邮件源自特定用户时，该用户将被禁止发送电子邮件。使用该设置指定的域管理员将收到该用户的出站邮件被阻止的通知。若要查看此通知的样式，请参阅[发件人被阻止发送出站垃圾邮件时的示例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)。有关重新启用的详细信息，请参阅[Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx)。
    
4. 单击“保存”****。 右侧窗格中将会显示默认策略设置的摘要。
    
## <a name="for-more-information"></a>详细信息
<a name="sectionSection2"> </a>

[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)
  
[反垃圾邮件保护常见问题](anti-spam-protection-faq.md)
  


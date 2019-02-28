---
title: 如何减少 Office 365 中的垃圾邮件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
description: 了解有助于减少 Office 365 中垃圾邮件的最常用方法。
ms.openlocfilehash: 0cc07d543618b154570231dcf1d45b39cfe20fec
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295505"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>如何减少 Office 365 中的垃圾邮件

 **你是否在 Office 365 中收到过多的垃圾邮件？请执行以下操作。**
  
我们强烈建议你[使用报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)报告误报邮件，帮助我们改进筛选器。此外，你可以将邮件*作为附件*转发至 junk@office365.microsoft.com 或 phish@office365.microsoft.com（如果是钓鱼邮件）。

>[警告] 如果你认为邮件是垃圾邮件且它位于“垃圾邮件”文件夹中，则这没有问题。如果完全不想在邮箱中看到该邮件，则应更改反垃圾邮件策略以隔离该邮件。有关隔离邮件的更多信息，请参阅[在 Office 365 中隔离电子邮件](quarantine-email-messages.md)。

## <a name="fixing-allowed-spam"></a>修复允许的垃圾邮件

我们经常看到客户因配置不正确而使垃圾邮件出现在收件箱中。其中最常见的是在传输规则中将域配置为绕过筛选器或者列出允许/安全发件人列表中的域。不推荐这样做，因为这些本应视为垃圾邮件的邮件会跳过垃圾邮件筛选。  

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a>其他垃圾邮件过多常见原因的解决方案

为了让你免受过多垃圾邮件的烦恼，Exchange Online Protection (EOP) 要求管理员必须完成一些任务。如果你不是 Office 365 租户的管理员，且收到过多垃圾邮件，建议你与管理员一起完成这些任务。如果不愿意这样做，可跳至用户部分。
  
### <a name="for-admins"></a>对于管理员

- **让 DNS 记录指向 Office 365**：所有域的邮件交换器 (MX) DNS 记录都必须指向 Office 365，且只能指向 Office 365，这样 EOP 才能提供最佳保护。请参阅[在管理 DNS 记录时为 Office 365 创建 DNS 记录](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)。
    
- **对所有邮箱都启用垃圾邮件规则**：默认情况下，垃圾邮件筛选操作设为“将邮件移至‘垃圾邮件’文件夹”****。如果这是当前首选的垃圾邮件策略操作，[还必须对所有邮箱都启用垃圾邮件规则](https://support.office.com/zh-CN/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。若要检查是否已完成此任务，可对一个或多个邮箱运行 Get-MailboxJunkEmailConfiguration cmdlet。例如，若要检查是否已对所有邮箱都启用垃圾邮件规则，可运行下面的命令：Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}。
    
    在输出结果中，“Enable”属性应设置为 True。如果设置为 False，可运行 Set-MailboxJunkEmailConfiguration，将它更改为 True。
    
- **在本地 Exchange Server 中创建邮件流规则**：如果使用的是 Exchange Online Protection，但邮箱位于本地 Exchange Server 中，必须在本地 Exchange Server 中创建几个邮件流规则。请参阅[面向仅使用 EOP 的客户的说明](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150))。
    
- **将大量电子邮件标记为“垃圾邮件”**：大量电子邮件是指用户已申请，但仍不想接收的电子邮件。在邮件头中的 X-Microsoft-Antispam 头内，找到 BCL（大量邮件可信度）属性。如果 BCL 值低于垃圾邮件筛选器中设置的阈值，建议调整阈值，以将这些类型的大量邮件标记为“垃圾邮件”。用户对[大量电子邮件的处理方式](https://docs.microsoft.com/zh-CN/office365/SecurityCompliance/bulk-complaint-level-values)的容忍度和偏好不同。可创建因用户偏好而异的不同策略或规则。 
    
- **立即阻止发件人**：如果需要立即阻止发件人，可按电子邮件地址、域或 IP 地址进行阻止。请参阅[使用 Office 365 垃圾邮件筛选器阻止垃圾邮件以避免出现漏报问题](create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365.md#use-the-eac-to-create-a-transport-rule-that-blocks-messages-sent-from-a-domain-or-user)。最终用户允许列表中的项可替代管理员设置的阻止操作。
    
- **为用户启用“举报邮件”加载项**：强烈建议[为用户启用“举报邮件”加载项](enable-the-report-message-add-in.md)。作为管理员，还可以查看用户发送的反馈，并使用任意模式来调整可能导致问题出现的任何设置。
    
### <a name="for-users"></a>对于用户

- **启用垃圾邮件规则并检查允许列表**：检查垃圾邮件操作规则是否已启用，并检查发件人或发件人的域是否未在你个人的允许列表中被设为规避筛选。访问这些设置的最佳方法是，转到[“阻止或允许”（垃圾邮件设置）](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)中。还可以在其中选择阻止发件人的电子邮件地址或域。
    
- **向 Microsoft 举报垃圾邮件**：按照[使用“举报邮件”加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)中的说明操作，向 Microsoft 举报垃圾邮件。此外，还可以向 junk@office365.microsoft.com 发送邮件，并附加要举报的一个或多个邮件。
    
    **重要提示**：如果未以附件形式转发邮件，头就会丢失，导致我们无法改进在 Office 365 中的垃圾邮件筛选。 
    
- **取消订阅大量电子邮件**：如果你申请的邮件（新闻稿、产品公告等）包含来自声誉良好的源的取消订阅链接，建议你直接取消订阅。Office 365 通常不会将这些邮件视为垃圾邮件。你也可以选择阻止发件人，或让管理员更改为将所有大量邮件视为垃圾邮件。

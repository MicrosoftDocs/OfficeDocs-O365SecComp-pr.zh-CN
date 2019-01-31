---
title: 如何减少 Office 365 中的垃圾邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
description: 了解有助于减少 Office 365 中垃圾邮件的最常用方法。
ms.openlocfilehash: 6dbcfa27c5ecbec6b6d1ab0bec298f45e867c4b3
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614406"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>如何减少 Office 365 中的垃圾邮件

 **你是否在 Office 365 中收到过多的垃圾邮件？请执行以下操作。**
  
Office 365 中的许多垃圾邮件问题都可以这样解决：[查看电子邮件的邮件头](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)，并确定哪里出错。你需要查找名为 X-Forefront-Antispam-Report 的标头。

  如果它包含字符串 SFV:NSPM，表明 Exchange Online Protection (EOP) 扫描了邮件，并认为它不是垃圾邮件。如果你不同意，这称为漏报，强烈建议你[使用报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，帮助我们改进我们的过滤器。

  如果你在标头中没有看到此值，可能表明邮件未通过垃圾邮件扫描，或存在导致邮件被忽略的配置问题。在这种情况下，请参考以下信息。 
  
可详细了解[反垃圾邮件的邮件头](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)。

## <a name="solutions-to-common-causes-of-getting-too-much-spam"></a>垃圾邮件过多的常见原因的解决方案

为了让你免受过多垃圾邮件的烦恼，Exchange Online Protection (EOP) 要求管理员必须完成一些任务。如果你不是 Office 365 租户的管理员，且收到过多垃圾邮件，建议你与管理员一起完成这些任务。如果不愿意这样做，可跳至用户部分。
  
### <a name="for-admins"></a>对于管理员

- **让 DNS 记录指向 Office 365**：所有域的邮件交换器 (MX) DNS 记录都必须指向 Office 365，且只能指向 Office 365，这样 EOP 才能提供最佳保护。请参阅[在管理 DNS 记录时为 Office 365 创建 DNS 记录](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)。
    
- **对所有邮箱都启用垃圾邮件规则**：默认情况下，垃圾邮件筛选操作设为“将邮件移至‘垃圾邮件’文件夹”****。如果这是当前首选的垃圾邮件策略操作，[还必须对所有邮箱都启用垃圾邮件规则](https://support.office.com/zh-CN/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。若要检查是否已完成此任务，可对一个或多个邮箱运行 Get-MailboxJunkEmailConfiguration cmdlet。例如，若要检查是否已对所有邮箱都启用垃圾邮件规则，可运行下面的命令：Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}。
    
    在输出结果中，“Enable”属性应设置为 True。如果设置为 False，可运行 Set-MailboxJunkEmailConfiguration，将它更改为 True。
    
- **检查邮件流规则和安全列表**：检查本应标记为“垃圾邮件”的邮件的邮件头。在 X-Forefront-Antispam-Report 头中找到 SCL 属性。如果 SCL 值为 -1，表明邮件已被列入安全列表，并规避了 EOP 垃圾邮件筛选。调查邮件流规则、允许列表和收件人的允许的发件人名单。参阅[以 Office 365 企业版管理员的身份发现和修复电子邮件传递问题](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6)也很有帮助，其中详细介绍了为什么邮件的 SCL 值为 -1。 
    
- **在本地 Exchange Server 中创建邮件流规则**：如果使用的是 Exchange Online Protection，但邮箱位于本地 Exchange Server 中，必须在本地 Exchange Server 中创建几个邮件流规则。请参阅[面向仅使用 EOP 的客户的说明](https://technet.microsoft.com/library/ms.exch.eac.EditAntispamPolicy_SpamAction%28EXCHG.150%29.aspx?v=15.20.548.14&amp;l=1&amp;s=BPOS_S_E15_0)。
    
- **将大量电子邮件标记为“垃圾邮件”**：大量电子邮件是指用户已申请，但仍不想接收的电子邮件。在邮件头中的 X-Microsoft-Antispam 头内，找到 BCL（大量邮件可信度）属性。如果 BCL 值低于垃圾邮件筛选器中设置的阈值，建议调整阈值，以将这些类型的大量邮件标记为“垃圾邮件”。用户对[大量电子邮件的处理方式](https://docs.microsoft.com/zh-CN/office365/SecurityCompliance/bulk-complaint-level-values)的容忍度和偏好不同。可创建因用户偏好而异的不同策略或规则。 
    
- **立即阻止发件人**：如果需要立即阻止发件人，可按电子邮件地址、域或 IP 地址进行阻止。请参阅[使用 Office 365 垃圾邮件筛选器阻止垃圾邮件以避免出现漏报问题](block-email-spam-to-prevent-false-negatives.md)。最终用户允许列表中的项可替代管理员设置的阻止操作。
    
- **为用户启用“举报邮件”加载项**：强烈建议[为用户启用“举报邮件”加载项](enable-the-report-message-add-in.md)。作为管理员，还可以查看用户发送的反馈，并使用任意模式来调整可能导致问题出现的任何设置。
    
### <a name="for-users"></a>对于用户

- **启用垃圾邮件规则并检查允许列表**：检查垃圾邮件操作规则是否已启用，并检查发件人或发件人的域是否未在你个人的允许列表中被设为规避筛选。访问这些设置的最佳方法是，转到[“阻止或允许”（垃圾邮件设置）](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)中。还可以在其中选择阻止发件人的电子邮件地址或域。
    
- **向 Microsoft 举报垃圾邮件**：按照[使用“举报邮件”加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)中的说明操作，向 Microsoft 举报垃圾邮件。此外，还可以向 junk@office365.microsoft.com 发送邮件，并附加要举报的一个或多个邮件。
    
    **重要提示**：如果未以附件形式转发邮件，头就会丢失，导致我们无法改进在 Office 365 中的垃圾邮件筛选。 
    
- **取消订阅大量电子邮件**：如果你申请的邮件（新闻稿、产品公告等）包含来自声誉良好的源的取消订阅链接，建议你直接取消订阅。Office 365 通常不会将这些邮件视为垃圾邮件。你也可以选择阻止发件人，或让管理员更改为将所有大量邮件视为垃圾邮件。

---
title: 如何避免在 Office 365 中发生误报
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 了解如何避免在 Office 365 中发生误报和将真实电子邮件标记为“垃圾邮件”。
ms.openlocfilehash: baf3fa52f34107ad82c392b52295d35a7e0002c4
ms.sourcegitcommit: bc25ea19c0b6d318751eadc4f27902b0054d5e2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "36054670"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a>如何避免在 Office 365 中将真实电子邮件标记为“垃圾邮件”

 **真实电子邮件是否在 Office 365 中被标记为“垃圾邮件”？试试本文中介绍的方法吧。**
  
如果发生误报，则应使用[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)将此邮件报告给 Microsoft。此外，还可以使用[提交资源管理器](admin-submission.md)提交邮件。
    
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a>确定邮件被标记为“垃圾邮件”的原因

Office 365 中的许多垃圾邮件问题都可以这样解决：[查看电子邮件的邮件头](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)，并确定哪里出错。你需要查找名为 X-Forefront-Antispam-Report 的标头。你可以[详细了解反垃圾邮件的邮件头](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)。
  
在邮件头中查找以下头和值。
  
### <a name="x-forefront-antispam-report"></a>X-Forefront-Antispam-Report

- **SFV:SPM** 指明邮件被 EOP 垃圾邮件筛选器标记为“垃圾邮件”。 

- **SFV:BLK**：指明邮件被标记为“垃圾邮件”，因为发送地址位于收件人的阻止的发件人名单中。 
    
- **SFV:SKS**：指明邮件在经内容筛选器筛选前就已被标记为“垃圾邮件”。这可能包含邮件流规则（也称为传输规则），它将邮件标记为“垃圾邮件”。运行邮件跟踪，以确定是否触发了可能已设置高垃圾邮件可信度 (SCL) 的邮件流规则。 
    
- **SFV:SKB**：指明邮件被标记为“垃圾邮件”，因为它符合垃圾邮件筛选器策略中的阻止列表。 
    
- 
  **SFV:BULK**：指明 x-microsoft-antispam 头中的大量邮件可信度 (BCL) 值高于已为内容筛选器设置的大量邮件阈值。大量电子邮件是指用户已申请，但仍不想接收的电子邮件。在邮件头中的 X-Microsoft-Antispam 头内，找到 BCL（大量邮件可信度）属性。如果 BCL 值低于垃圾邮件筛选器中设置的阈值，建议调整阈值，以将这些类型的大量邮件标记为“垃圾邮件”。用户对[大量电子邮件的处理方式](https://docs.microsoft.com/zh-CN/office365/SecurityCompliance/bulk-complaint-level-values)的容忍度和偏好不同。可创建因用户偏好而异的不同策略或规则。
    
- **CAT:SPOOF** 或 **CAT:PHISH**：指明邮件可能存在欺骗行为。也就是说，无法验证邮件来源，来源可疑。如果有效，发件人需要确保已正确配置 SPF 和 DKIM。请检查 Authentication-Results 头，以获取更多信息。尽管难以让所有发件人都使用正确的电子邮件身份验证方法，但规避这些检查极为危险，最容易导致泄漏发生。 
    
### <a name="x-customspam"></a>x-customspam

- 此头指明邮件被标记为“垃圾邮件”，因为垃圾邮件筛选器中的[高级垃圾邮件选项之一已启用](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx)。建议使用默认设置，除非你确实需要这些功能。 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a>垃圾邮件过多的其他原因的解决方案

为了提高工作效率，Exchange Online Protection (EOP) 要求管理员必须完成一些任务。如果你不是 Office 365 租户的管理员，且收到过多垃圾邮件，建议你与管理员一起完成这些任务。如果不愿意这样做，可跳至用户部分。
  
### <a name="for-admins"></a>对于管理员

- **让 DNS 记录指向 Office 365**：所有域的邮件交换器 (MX) DNS 记录都必须指向 Office 365，且只能指向 Office 365，这样 EOP 才能提供保护。如果 MX 没有指向 Office 365，EOP 就不会为用户提供垃圾邮件筛选服务。若要使用其他服务或设备为域提供垃圾邮件筛选服务，应考虑在 EOP 中禁用垃圾邮件保护。为此，可创建将 SCL 值设为 -1 的邮件流规则。如果稍后决定使用 EOP，请务必删除邮件流规则。 
    
- **为用户开启报告邮件加载项** 我们强烈建议[为用户启用报告邮件加载项](enable-the-report-message-add-in.md)。

- **使用[提交资源管理器](admin-submission.md)** 管理员现在可以使用文件或网络邮件 ID、URL 和 Microsoft 在 Office 365 中扫描的文件发送电子邮件。 作为管理员，你还可以查看用户发送的反馈，并使用任何模式对可能导致问题的任何设置进行调整。

- 
  **确保用户在发送和接收电子邮件的允许限制范围内[，如](https://docs.microsoft.com/zh-CN/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)这篇文章**所述。

 - **仔细检查批量级别**，如[这篇文章](bulk-complaint-level-values.md)所规定
    
### <a name="for-users"></a>对于用户
    
- **创建安全发件人列表** 用户可以在 [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) 或 [Outlook 网页版](https://go.microsoft.com/fwlink/p/?LinkId=294862)中将受信任的发件人地址添加到安全发件人列表中。若要在 Outlook 网页版中开始使用，请选择“**设置**”![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \>“**选项**”\>“**组织或允许**”。下图所示为向安全发件人列表添加内容的示例。
  
![在 Outlook 网页版中添加安全发件人](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
EOP 将会指定用户的安全发件人和收件人，但不是安全域。无论该域是已添加到 Outlook 网页版中还是已添加到 Outlook 并使用 Directory Sync 进行同步，情况均是如此。

- **在 Outlook 中禁用 SmartScreen 筛选**：如果使用的是旧版 Outlook 桌面客户端，则你应禁用 SmartScreen 筛选功能（此功能已终止）。如果启用，可能会导致误报。如果运行的是更新后的桌面 Outlook 客户端，无需遵守此要求。

## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a>疑难解答：即便 EOP 已将邮件标记为“非垃圾邮件”，邮件还是出现在“垃圾邮件”文件夹中

如果用户在 Outlook 中启用了“仅限安全列表：仅来自安全发件人列表或安全收件人列表的人员或域的邮件将传送至收件箱”，则所有电子邮件均会投递至某个发件人的垃圾邮件文件夹，除非该发件人位于收件人的安全发件人列表上。无论 EOP 是否已将邮件标记为“非垃圾邮件”，或者已在 EOP 中设立将邮件标记为“非垃圾邮件”的规则，情况均会如此。
  
可以按照 [Outlook：禁用垃圾邮件 UI 和筛选机制的策略设置](https://support.microsoft.com/en-us/kb/2180568)中的说明，为 Outlook 用户禁用“仅限安全列表”选项。
  
如果在 Outlook 网页版中查看邮件，则其中显示的黄色安全提示指示邮件位于垃圾邮件文件夹中，因为该发件人不在收件人的安全发件人列表中。
  
如果查看邮件头，则其中可能包含戳记 SFV:SKN（IP 允许或 ETR 允许）或 SFV:NSPM（非垃圾邮件），但邮件仍位于用户的垃圾邮件文件夹中。如果邮件头中没有任何内容，则表示用户已启用“仅限安全列表”选项。这是因为用户在 Outlook 中设置的“仅限安全列表”选项将会覆盖 EOP 设置。 
  
 **查证为何来自某个安全发件人的邮件在邮件头中被标记为“非垃圾邮件”，但仍出现在用户的垃圾邮件文件夹中**
  
1. 若要了解如何连接到 Exchange Online PowerShell，请查阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。 
    
2. 运行以下命令，以查看用户的垃圾邮件配置设置：
    
  ```Powershell
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

- 如果 TrustedListsOnly 已设为 True，则这意味着此设置已启用
- 如果 ContactsTrusted 已设为 True，则这意味着用户信任联系人和安全发件人
- TrustedSendersAndDomains 将列出用户的安全发件人列表中的内容


## <a name="eop-only-customers-use-directory-synchronization"></a>仅限 EOP 客户：使用目录同步

如果为仅限 EOP 客户，即，你已订阅 EOP 服务以用于本地 (Exchange) 单子邮件服务器，则应使用目录同步功能将用户设置与该服务同步。这样做可确保 EOP 接受你的安全发件人列表。有关更多信息，请参阅[在 EOP 中管理邮件用户](https://go.microsoft.com/fwlink/?LinkId=534098)中的“使用目录同步管理邮件用户”。

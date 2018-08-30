---
title: 防止电子邮件被标记为 Office 365 和 Exchange Online Protection 中的垃圾邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 74aaade0-efc0-46ac-b949-f2d1d59256fa
description: Office 365 管理员可以阻止好的电子邮件标记为垃圾邮件的发送到隔离为误报提示。自定义安全列表和其他选项，以防止好的电子邮件标记为垃圾邮件。
ms.openlocfilehash: 42b27d237592e95e6d175ab335959bc82269c0f7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524890"
---
# <a name="prevent-email-from-being-marked-as-spam-in-office-365-and-exchange-online-protection"></a>防止电子邮件被标记为 Office 365 和 Exchange Online Protection 中的垃圾邮件

使用适当的访问凭据的 Exchange Online 或 Exchange Online Protection (EOP) 管理员可以使用以下步骤以帮助确保通过服务旅行一封电子邮件未标记为垃圾邮件。
  
很遗憾了合法的良好电子邮件，隔离或阻止垃圾邮件和隔离文件夹中登录。可以使用安全发件人列表或邮件流规则以绕过垃圾邮件筛选，防止良好的电子邮件获取标记为垃圾邮件。当错误地将邮件标记为垃圾邮件垃圾邮件筛选器时，它具有调用误报。Office 365 垃圾邮件筛选器还提供了一些最终用户可以以帮助阻止误报自定义的选项。
  
如果您正在寻找帮助假负邮件，即垃圾邮件的获取时它不应，签出[垃圾邮件与 Office 365 垃圾邮件筛选器以阻止假负问题阻止电子邮件](block-email-spam-to-prevent-false-negatives.md)中的提示。
  
## <a name="eop-only-customers-use-directory-synchronization"></a>仅 EOP 客户： 使用目录同步

EOP 是基于云的电子邮件筛选服务，可帮助保护您的组织免受垃圾邮件和恶意软件。如果您有 Office 365 中的邮箱，它们是自动受 EOP，因为它是服务的一部分。 
  
如果您仅 EOP 客户，即，与您的本地 Exchange 服务器订阅到使用的 EOP 服务，您应使用目录同步同步服务的用户设置。这样可确保您安全发件人列表将由 EOP。有关详细信息，请参阅[Manage Mail Users in EOP](https://go.microsoft.com/fwlink/?LinkId=534098)中的"使用目录同步管理邮件用户"。
  
## <a name="prevent-false-positive-email-by-using-the-connection-filters-ip-allow-list"></a>阻止 false 正电子邮件使用连接筛选器的 IP 允许列表

如果您发现发件人的电子邮件总是移动到您的组织中的垃圾邮件文件夹，您可以将电子邮件发件人的 IP 地址添加到连接筛选器 IP 允许列表。通常，这样可以防止在 false 正响应此发件人为组织内的所有收件人。例外情况是当用户启用选项"安全仅列出： 只有来自人员或域安全发件人列表或安全收件人列表的邮件将传递到收件箱"在 Outlook 中不会将该发件人添加到安全发件人列表。重写该选项的信息，请参阅[疑难解答： 一条消息，该怎么办垃圾文件夹中即使 EOP 标记为非垃圾邮件邮件](prevent-email-from-being-marked-as-spam-0.md#TroubleshootingJunkEOPNonSpam)。
  
 **若要将 IP 地址添加到您的连接筛选器的 IP 允许列表**
  
1. 获取来自您希望允许的发件人发送的消息标头。[邮件标头分析器](https://go.microsoft.com/fwlink/p/?LinkId=306583)中所述，您可以将从您的邮件客户端如 Outlook 或 Outlook Web 上的执行此操作。
    
2. 手动搜索关注 CIP 标签在 X Forefront 反垃圾邮件报表页眉或使用[远程连接分析器](https://testconnectivity.microsoft.com/?tabid=mha)**消息分析器**选项卡的 IP 地址。
    
3. 添加 IP IP 地址允许通过"使用 EAC 编辑默认连接筛选器策略"中的步骤中[配置连接筛选器策略](https://go.microsoft.com/fwlink/?LinkId=534132)的列表。
    
## <a name="prevent-false-positive-email-by-configuring-spam-filter-policies"></a>通过配置垃圾邮件筛选器策略阻止 false 正电子邮件

您可以添加到允许列表的域或单个电子邮件地址，方法是中[配置垃圾邮件筛选器策略](https://go.microsoft.com/fwlink/?LinkID=534136)的步骤。
  
## <a name="review-your-advanced-spam-filter-policies"></a>查看您的高级垃圾邮件筛选器策略

如果您有特殊限制设置中的垃圾邮件筛选器策略，例如，如果您已阻止整个域，则应查看这些检查如果它们可能导致误报。请参阅[配置垃圾邮件筛选器策略](https://go.microsoft.com/fwlink/?LinkId=534136)，并关闭其他[高级垃圾邮件筛选选项](https://go.microsoft.com/fwlink/?LinkId=534137)可能会导致邮件标记为垃圾邮件。 
  
## <a name="help-your-end-users-create-a-safe-sender-list-to-prevent-good-email-from-being-marked-as-spam"></a>帮助最终用户创建安全发件人列表来阻止好的电子邮件标记为垃圾邮件
<a name="BKMK_email-user-help-safelist"> </a>

告知用户从其信任到其安全发件人列表中[Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065)或[Outlook Web 上](https://go.microsoft.com/fwlink/p/?LinkId=294862)的发件人添加地址。若要开始在 Web 上的 Outlook 中，选择**设置**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **选项** \> **阻止或允许**。下图显示将内容添加到安全发件人列表的示例。
  
![在 Outlook Web App 中添加安全发件人](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
EOP 也会授予用户安全发件人和收件人，但不是安全的域。这为 true，无论是通过在 Web 上，Outlook 添加还是在 Outlook 中添加域，并使用目录同步同步。
  
## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a>疑难解答： 一条消息，该怎么办垃圾文件夹中即使 EOP 标记为非垃圾邮件的邮件
<a name="TroubleshootingJunkEOPNonSpam"> </a>

如果您的用户可以在 Outlook 中启用了"安全仅列出： 来自人员或域的安全发件人列表或安全收件人列表的仅邮件将传递到收件箱"，然后所有电子邮件将转到垃圾邮件文件夹的发件人除非发件人位于 recipient 的安全发件人列表。这将发生无论 EOP 将邮件标记为非垃圾邮件，还是已将 EOP 中的某个规则设置为标记为非垃圾邮件。
  
您可以通过中的说明禁用 Outlook 用户的仅安全列表选项[Outlook： 策略设置禁用垃圾电子邮件用户界面和筛选机制](https://support.microsoft.com/en-us/kb/2180568)。
  
如果在 Web 上的 Outlook 中查看邮件时，将会指示邮件位于垃圾邮件文件夹，因为发件人在收件人的安全发件人列表不是一个黄色安全提示。
  
如果您查看邮件的标头，它可能包括戳 SFV:SKN （IP 允许或 ETR 允许） 或 SFV:NSPM （非垃圾邮件），但该消息仍处于用户的垃圾邮件文件夹。有，该值指示用户具有"仅安全列表"已启用邮件头中为 nothing。这是因为设置在 Outlook 中的用户的"仅安全列表"选项将覆盖的 EOP 设置。 
  
 **若要验证为什么来自安全发件人的邮件标记为非垃圾邮件邮件头，但仍结束中用户的垃圾文件夹中**
  
1. 若要了解如何连接到 Exchange Online PowerShell 中，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?LinkId=396554)。 
    
2. 运行以下命令以查看用户的垃圾邮件配置设置：
    
  ```
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

    如果 TrustedListsOnly 设置为 True，则表明已启用此设置。如果 ContactsTrusted 设置为 True，则意味着用户信任联系人和安全发件人。TrustedSendersAndDomains 列出用户的安全发件人列表的内容。
    
## <a name="still-need-help"></a>仍需要帮助？
<a name="TroubleshootingJunkEOPNonSpam"> </a>

[![从 Office 365 社区论坛获取帮助](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![管理员：登录并创建一个服务请求](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![管理员：电话支持](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  
## <a name="see-also"></a>另请参阅
<a name="TroubleshootingJunkEOPNonSpam"> </a>

[垃圾邮件筛选器的概述](https://support.office.com/article/5AE3EA8E-CF41-4FA0-B02A-3B96E21DE089)
  
[阻止或允许 （垃圾邮件设置）](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)
  
[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](block-email-spam-to-prevent-false-negatives.md)


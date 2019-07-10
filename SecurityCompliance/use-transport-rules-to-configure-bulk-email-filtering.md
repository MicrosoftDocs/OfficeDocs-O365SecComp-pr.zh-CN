---
title: 使用邮件流规则在 Exchange Online Protection 中配置批量电子邮件筛选
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用 Exchange Online Protection 中的邮件流规则进行批量电子邮件筛选。
ms.openlocfilehash: 185a1174ba3e0d400926b03c073feb100f8e812d
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600785"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>使用邮件流规则在 Exchange Online Protection 中配置批量电子邮件筛选

您可以使用默认的垃圾邮件内容筛选器策略针对垃圾邮件和批量电子设置公司范围的内容筛选器。请查看[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)和 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) 以了解如何设置内容筛选器策略。 
  
如果您想要更多的选项筛选批量邮件, 则可以创建邮件流规则 (也称为传输规则), 以搜索批量电子邮件中经常找到的文本模式或短语。 任何包含这些特征的邮件将被标记为垃圾邮件。 使用这些规则有助于减少组织收到的垃圾批量电子邮件数量。

> [!IMPORTANT]
> 在创建已记录的邮件流规则之前, 我们建议您先阅读[垃圾邮件和批量电子邮件之间的区别](what-s-the-difference-between-junk-email-and-bulk-email.md)和[批量投诉级别值](bulk-complaint-level-values.md)之间的区别。<br>下面的步骤为您的整个组织将邮件标记为垃圾邮件。但是，您可以添加其他条件，以仅将这些规则应用于组织中的特定收件人。通过这种方式，主动批量电子邮件筛选设置可应用于具有高度针对性的一些用户，同时又不影响其余用户（主要接收其注册的批量电子邮件）。 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>创建邮件流规则, 以根据文本模式筛选批量电子邮件

1. 在 Exchange 管理中心 (EAC) 中，转到“邮件流”****\>“规则”****。
    
2. 单击 "**添加** !["](media/ITPro-EAC-AddIcon.gif) "添加" 图标, 然后选择 "**创建新规则**"。
    
3. 指定规则名称。
    
4. 单击“更多选项”****。 在 "**应用此规则**" 下, 选择 **"主题" 或 "正文** \> "**主题或正文与这些文本模式相匹配**。
    
5. 在 "**指定词语或短语**" 对话框中, 添加以下通常在批量电子邮件中找到的正则表达式 (一次一个), 然后在完成后单击 **"确定"** : 
    
   - `If you are unable to view the content of this email\, please`
    
   - `\>(safe )?unsubscribe( here)?\</a\>`
    
   - `If you do not wish to receive further communications like this\, please`
    
   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
    
   - `To stop receiving these+emails\:http\://`
    
   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
    
   - `no longer (wish )?(to )?(be sent|receive) w+ email`
    
   - `If you are unable to view the content of this email\, please click here`
    
   - `To ensure you receive (your daily deals|our e-?mails)\, add`
    
   - `If you no longer wish to receive these emails`
    
   - `to change your (subscription preferences|preferences or unsubscribe)`
    
   - `click (here to|the) unsubscribe`
    
   上述列表不是批量电子邮件中找到的一组详尽的正则表达式;可以根据需要添加或删除更多内容。 但是，它是一个很好的起点。<br>在邮件从用于在 ASCII 文本中的 SMTP 服务器之间传输二进制邮件的 MIME 内容传输编码方法解码*之后*, 将在邮件中的主题或其他标头字段中搜索单词或文本模式。 不能使用条件或例外来搜索邮件中主题或其他头字段的原始（通常为 Base64）编码值。 
    
6. 在 "**执行以下操作**" 下, 选择 "**修改邮件属性** \> **" "设置垃圾邮件可信度 (SCL)"**。
    
7. 在“指定 SCL”**** 对话框中，将 SCL 设置为“5”****、“6”**** 或“9”****，然后单击“确定”****。
    
   将 SCL 设置为 5 或 6 会执行“垃圾邮件”**** 操作，而将 SCL 设置为 9 会执行“高可信度垃圾邮件”**** 操作，如内容筛选策略中所配置。 该服务将执行内容筛选策略中设置的操作。 默认操作是将邮件传递到收件人的垃圾邮件文件夹，但是可能会配置不同的操作，如[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中所述。
    
   如果配置的操作是隔离邮件, 而不是将其发送到收件人的 "垃圾邮件" 文件夹, 则邮件将作为邮件流规则的匹配项发送到管理员隔离区, 并且不会在最终用户垃圾邮件隔离中或通过最终用户使用垃圾邮件通知。 
  
   有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。
    
8. 保存规则。
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>创建邮件流规则以根据短语筛选批量电子邮件

1. In the EAC, go to **Mail flow** \> **Rules**.
    
2. 单击 "**添加** !["](media/ITPro-EAC-AddIcon.gif) "添加" 图标, 然后选择 "**创建新规则**"。
    
3. 指定规则名称。
    
4. 单击“更多选项”****。 在 "在**以下情况应用此规则**" 下, 选择 **"主题" 或 "正文** \> "**主题或正文包含以下任何词语**。
    
5. 在 "**指定词语或短语**" 对话框中, 添加以下在批量电子邮件中常用的短语, 一次添加一个, 然后在完成后单击 **"确定"** : 
    
   - `to change your preferences or unsubscribe`
    
   - `Modify email preferences or unsubscribe`
    
   - `This is a promotional email`
    
   - `You are receiving this email because you requested a subscription`
    
   - `click here to unsubscribe`
    
   - `You have received this email because you are subscribed`
    
   - `If you no longer wish to receive our email newsletter`
    
   - `to unsubscribe from this newsletter`
    
   - `If you have trouble viewing this email`
    
   - `This is an advertisement`
    
   - `you would like to unsubscribe or change your`
    
   - `view this email as a webpage`
    
   - `You are receiving this email because you are subscribed`
    
   此列表不是批量电子邮件中找到的一组详尽的短语。可以根据需要添加或删除更多内容。 但是，它是一个很好的起点。
    
6. 在 "**执行以下操作**" 下, 选择 "**修改邮件属性** \> **" "设置垃圾邮件可信度 (SCL)"**。
    
7. 在“指定 SCL”**** 对话框中，将 SCL 设置为“5”****、“6”**** 或“9”****，然后单击“确定”****。
    
   将 SCL 设置为 5 或 6 会执行“垃圾邮件”**** 操作，而将 SCL 设置为 9 会执行“高可信度垃圾邮件”**** 操作，如内容筛选策略中所配置。 该服务将执行内容筛选策略中设置的操作。 默认操作是将邮件传递到收件人的垃圾邮件文件夹，但是可能会配置不同的操作，如[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中所述。
    
   如果配置的操作是隔离邮件, 而不是将其发送到收件人的 "垃圾邮件" 文件夹, 则邮件将作为邮件流规则的匹配项发送到管理员隔离区, 并且不会在最终用户垃圾邮件隔离中或通过最终用户使用垃圾邮件通知。 
  
   有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。

8. 保存规则。

## <a name="for-more-information"></a>详细信息

[垃圾邮件和批量邮件之间有什么差异？](what-s-the-difference-between-junk-email-and-bulk-email.md)

[批量投诉级别值](bulk-complaint-level-values.md)

[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)

[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)

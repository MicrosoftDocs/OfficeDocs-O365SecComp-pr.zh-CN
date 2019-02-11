---
title: 使用邮件流规则配置 Exchange Online Protection 中筛选批量电子邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: 管理员可以了解如何使用 Exchange Online Protection 中的邮件流规则，以筛选批量电子邮件。
ms.openlocfilehash: ce95872d3d80436dce4c62037caea9a5f735726d
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "27382803"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>使用邮件流规则配置 Exchange Online Protection 中筛选批量电子邮件

您可以使用默认的垃圾邮件内容筛选器策略针对垃圾邮件和批量电子设置公司范围的内容筛选器。请查看[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)和 [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) 以了解如何设置内容筛选器策略。 
  
如果需要更多选项以筛选批量邮件，您可以创建邮件流规则 （也称作传输规则） 搜索的文本模式或批量电子邮件中常见的短语。包含这些特征任何邮件将被标记为垃圾邮件。使用这些规则可帮助减少您的组织接收的多余的垃圾电子邮件的量。
  
**注意**：

- 创建邮件流规则记录本主题之前，我们建议您先阅读[垃圾邮件和批量邮件之间的区别是什么？](what-s-the-difference-between-junk-email-and-bulk-email.md)和[批量投诉级别值](bulk-complaint-level-values.md)。 
  
- 下面的步骤为您的整个组织将邮件标记为垃圾邮件。但是，您可以添加其他条件，以仅将这些规则应用于组织中的特定收件人。通过这种方式，主动批量电子邮件筛选设置可应用于具有高度针对性的一些用户，同时又不影响其余用户（主要接收其注册的批量电子邮件）。 
  
### <a name="create-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>创建要筛选批量电子邮件根据文本模式的邮件流规则

1. 在 Exchange 管理员中心 (EAC) 中，转到**邮件流** \> **规则**。
    
2. 单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后选择**创建新规则**。
    
3. 指定规则名称。
    
4. 单击**更多选项**。在**以下情况应用此规则**，请选择**主题或正文** \> **主题或正文匹配这些文本模式**。
    
5. 在**指定词语或短语**对话框中，添加以下正则表达式通常在批量电子邮件，一次一台中找到和完成后单击**确定**: 
    
   - 如果您将无法查看此电子邮件的内容\,请
    
   - \\>(安全 )?取消订阅( 此处)?\\</a\\>
    
   - 如果您不希望接收类似进一步 communications\,请
    
   - \\<img height\="?1"? width\="?1"? src\=.?http\://
    
   - 若要停止接收 这些\s+电子邮件\:http\://
    
   - 若要取消订阅 \w+ (e\-?信件|e?-?邮件|新闻稿)
    
   - 不再 (愿望 )?(以 )?(发送|接收) \w+ 电子邮件
    
   - 如果您将无法查看此电子邮件的内容\,，请单击此处
    
   - 若要确保收到 (您每日 deals | 我们 e ?mails)\,添加
    
   - 如果您不希望再接收这些电子邮件
    
   - 若要更改您的 (订阅首选项|首选项或取消订阅)
    
   - 单击 (此处可|该) 取消订阅
    
   **注意**：

   - 在以上列表不是详尽组批量电子邮件; 中找到的正则表达式可以添加或删除根据需要的详细信息。但是，它是很好的起点。
    
   - 搜索单词或主题中的文本模式或消息中的其他标头字段发生从编码方法用来将二进制邮件 ASCII 文本中的 SMTP 服务器之间传输的 MIME 内容传输解码*后*邮件。不能使用条件或例外的原始搜索 (通常是 Base64) 编码的主题或消息中的其他标头字段的值。 
    
6. 在**执行以下操作**，下选择**修改邮件属性** \> **将垃圾邮件可信度 (SCL) 设置**。
    
7. 在**指定 SCL**对话框中，将 SCL 设置为**5**、 **6**或**9**，并单击**确定**。
    
   将 SCL 设置为 5 或 6 只**垃圾邮件**操作，同时设置到 9 的 SCL**高可信度垃圾邮件**操作，如内容筛选器策略中配置。服务将执行的操作中的内容筛选器策略设置。默认操作是将邮件传递到收件人的垃圾邮件文件夹，但可以配置不同的操作，如[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中所述。
    
   > [!NOTE]
   > 为邮件流规则匹配项，并将不可用最终用户垃圾邮件隔离邮箱中或通过最终用户，邮件如果您配置的操作是隔离邮件，而不是将其发送给收件人的垃圾邮件文件夹，发送到管理员隔离垃圾邮件通知。 
  
   有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。
    
8. 保存规则。
    
### <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>创建筛选批量电子邮件根据短语的邮件流规则

1. 在 EAC 中，转到**邮件流** \> **规则**。
    
2. 单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后选择**创建新规则**。
    
3. 指定规则名称。
    
4. 单击**更多选项**。在**以下情况应用此规则**，请选择**主题或正文** \> **主题或正文中包含以下任何词语**。
    
5. 在**指定词语或短语**对话框中，添加以下短语通常在批量电子邮件，一次一台中找到和完成后单击**确定**: 
    
   - 更改首选项或取消订阅
    
   - 修改电子邮件首选项或取消订阅
    
   - 这是一封促销电子邮件
    
   - 由于您申请了订阅，因此向您发送此电子邮件
    
   - 单击此处可取消订阅
    
   - 由于您进行了订阅，因此向您发送了此电子邮件
    
   - 如果您不再希望收到我们的电子邮件新闻稿
    
   - 取消订阅此新闻稿
    
   - 如果您在查看此电子邮件时遇到问题
    
   - 这是一个广告
    
   - 您想取消订阅或更改
    
   - 以网页形式查看此电子邮件
    
   - 由于您进行了订阅，因此向您发送此电子邮件
    
   **注意**： 同样，此列表不是详尽套批量电子邮件; 中找到的短语可以添加或删除根据需要的详细信息。但是，它是很好的起点。
    
6. 在**执行以下操作**，下选择**修改邮件属性** \> **将垃圾邮件可信度 (SCL) 设置**。
    
7. 在**指定 SCL**对话框中，将 SCL 设置为**5**、 **6**或**9**，并单击**确定**。
    
   将 SCL 设置为 5 或 6 只**垃圾邮件**操作，同时设置到 9 的 SCL**高可信度垃圾邮件**操作，如内容筛选器策略中配置。服务将执行的操作中的内容筛选器策略设置。默认操作是将邮件传递到收件人的垃圾邮件文件夹，但可以配置不同的操作，如[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中所述。
    
   > [!NOTE]
   > 为邮件流规则匹配项，并将不可用最终用户垃圾邮件隔离邮箱中或通过最终用户，邮件如果您配置的操作是隔离邮件，而不是将其发送给收件人的垃圾邮件文件夹，发送到管理员隔离垃圾邮件通知。 
  
   有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。

8. 保存规则。

## <a name="for-more-information"></a>详细信息

[垃圾邮件和批量邮件之间有什么差异？](what-s-the-difference-between-junk-email-and-bulk-email.md)

[批量投诉级别值](bulk-complaint-level-values.md)

[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)

[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)

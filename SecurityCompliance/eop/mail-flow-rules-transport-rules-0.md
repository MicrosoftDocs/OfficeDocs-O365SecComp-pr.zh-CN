---
title: Exchange Online Protection 中的邮件流规则 (传输规则)
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/29/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: 可以使用邮件流规则 (传输规则) 识别通过 Office 365 组织传递的邮件并对其执行操作。
ms.openlocfilehash: b64e31490c557a1a13728d5ece67294c68856cdd
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599608"
---
# <a name="mail-flow-rules-transport-rules-in-exchange-online-protection"></a>Exchange Online Protection 中的邮件流规则 (传输规则)

可以使用邮件流规则（也称为传输规则）识别通过 Office 365 组织进行传递的邮件并对其进行操作。邮件流规则与 Outlook 和 Web 上的 Outlook 中提供的收件箱规则类似。主要区别在于邮件流规则在邮件传输过程中对其进行操作，而不是在邮件传递到邮箱后进行操作。邮件流规则包含更丰富的条件、例外和操作集，让你能灵活实现多种类型的邮件策略。
  
本文介绍了邮件流规则的组件及其工作方式。
  
有关创建、复制和管理邮件流规则的步骤, 请参阅**管理邮件流规则**。 可以选择强制实施每个规则、只是测试规则，或测试每个规则并通知发件人。 若要了解有关测试选项的详细信息, 请参阅**Test a mail flow rule** And **Policy 诀窍**。
  
有关与邮件流规则匹配的邮件的摘要和详细信息报告，请参阅**使用 Office 365 中的邮件保护报告查看关于恶意软件、垃圾邮件和规则检测的数据**。
  
若要通过使用邮件流规则实现特定的邮件策略，请参阅下列主题：
  
- [使用邮件流规则检查 Office 365 中的邮件附件](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)
    
- [设置 Office 365 企业版中的加密](https://support.office.com/article/e86fc991-0161-4f01-9c1c-d25e87733d06)
    
- [Office 365 中的组织范围内的邮件免责声明、签名、页脚或邮件头](http://technet.microsoft.com/library/29ac61c2-77f1-4071-b14e-8cc64e3e76ba.aspx)
    
- [使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)](../use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)
    
- [在 Office 365 中创建阻止发件人列表](../create-block-sender-lists-in-office-365.md)
    
- [通过 Exchange Online Protection 中的文件附件阻止功能降低恶意软件的威胁](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)
    
- [为加密或解密电子邮件定义规则](https://go.microsoft.com/fwlink/p/?Linkid=402846)
    
以下视频演示了如何设置 Exchange Online Protection 中的邮件流规则。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]
  
## <a name="mail-flow-rule-components"></a>邮件流规则组件

邮件流规则由条件、例外、操作和属性组成：
  
- **条件** 用于标识要将操作应用到的邮件。一些条件检查邮件头字段（例如"收件人"、"发件人"或"抄送"字段）。其他条件检查邮件属性（例如邮件主题、正文、附件、邮件大小或邮件分类）。大多数条件要求你指定比较运算符（例如等于、不等于或包含）以及要匹配的值。如果没有条件或例外，规则将应用到所有邮件。 
    
    有关 Exchange Online Protection 中的邮件流规则条件的详细信息, 请参阅[mail flow rule 条件 and 例外 (谓词) 在 Exchange online 中。](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。
    
- **例外** 选择性地识别操作不应应用到的邮件。条件中可用的相同邮件标识符同样在例外中可用。例外会覆盖条件并阻止规则操作应用于邮件，即使邮件匹配所有配置的条件也是如此。 
    
- **操作** 指定对匹配规则中的条件而不匹配任何例外的邮件执行哪些操作。有许多可用操作，例如拒绝、删除或重定向邮件、添加其他收件人、在邮件主题中添加前缀或在邮件正文中插入免责声明。 
    
    有关 Exchange Online Protection 中可用的邮件流规则操作的详细信息, 请参阅[Exchange Online protection 中的邮件流规则操作](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)。
    
- **属性** 指定条件、例外和操作之外的其他规则设置。例如，应何时应用规则、是否强制实施或测试规则，以及规则可用的时间段。 
    
     有关详细信息，请参阅本主题中的 [邮件流规则属性](mail-flow-rules-transport-rules-0.md#Properties)部分。 
    
### <a name="multiple-conditions-exceptions-and-actions"></a>多个条件、例外和操作

下表显示了在规则中处理的多个条件、条件值、例外和操作。
  
|**组件**|**逻辑**|**Comments**|
|:-----|:-----|:-----|
|注释  <br/> |AND  <br/> |邮件必须匹配该规则的所有条件。如果需要匹配一个条件或另一个条件，请对每个条件使用不同的规则。例如，如果要为带有附件的邮件和包含指定文本的邮件添加相同的免责声明，请为每个条件创建一个规则。在 EAC 中，你可以轻松地复制规则。  <br/> |
|邮件必须匹配该规则的所有条件。如果需要匹配一个条件或另一个条件，请对每个条件使用不同的规则。例如，如果您要为带有附件的邮件和内容匹配某个模式的邮件添加相同的免责声明，请为每个条件创建一个规则。您可以轻松地复制规则。  <br/> |OR  <br/> |一些条件允许你指定多个值。邮件必须匹配任一（并非全部）指定值。例如，如果电子邮件的主题为 Stock price information，并且 **主题包含这些词中的任一个**条件被配置为匹配单词 Contoso 或 stock，则符合该条件，因为主题中至少包含指定值中的一个。  <br/> |
|一些条件允许您指定多个值。如果一个条件允许输入多个值，则邮件必须与为该条件指定的任何值匹配。例如，如果电子邮件的主题为股价信息，并且主题包含这些词中的任一个条件被配置为匹配词 Contoso 或 stock，则符合该条件，因为主题中至少包含条件值中的一个。  <br/> |OR  <br/> |如果邮件匹配任何例外，则操作不会应用到邮件。该邮件不需要匹配所有例外。  <br/> |
|如果邮件匹配任何例外，则不会执行操作。邮件不需要匹配所有例外。  <br/> |AND  <br/> |匹配规则条件的邮件获取规则中指定的所有操作。例如，如果选择了操作" **在邮件主题前面追加**"和" **将收件人添加到密件抄送框**"，则两种操作都将应用至邮件。  <br/> 匹配规则的条件的邮件会获取规则中指定的所有操作。例如，如果选择了操作“在邮件主题前面追加”和“添加收件人到密件抄送框”，两种操作都将应用至邮件。该邮件将在邮件主题的前面添加指定的字符串作为前缀，并且指定的收件人将添加为密件抄送收件人。<br/> 还可以为规则设置操作，以便在应用该规则时，后续规则不会应用至邮件。  <br/> |
   
### <a name="mail-flow-rule-properties"></a>邮件流规则属性
<a name="Properties"> </a>

下表介绍了邮件流规则中所提供的规则属性。
  
|**EAC 中的属性名称**|**PowerShell 中的参数名称**|**说明**|
|:-----|:-----|:-----|
|**优先级** <br/> | _Priority_ <br/> |指示规则应用于邮件的顺序。默认优先级基于规则创建的先后顺序（较早规则的优先级高于较新规则的优先级，先处理具有较高优先级的规则，然后再处理具有较低优先级的规则）。    <br/> 通过在规则列表中上移或下移规则可更改 EAC 中规则的优先级。在 PowerShell中，可设置优先级编号（0 表示最高优先级）。    <br/> 例如，如果有一个拒绝包含信用卡号码的邮件的规则，还有一个需要批准的规则，你希望拒绝规则先发生，并停止应用其他规则。  |
|**模式** <br/> | _Mode_ <br/> |可以指定是否让规则立即处理邮件，或是否在不影响邮件传递（启用或不启用数据丢失防护或 DLP 策略提示）的情况下测试规则。  <br/> 策略提示在 Outlook 或 Web 上的 Outlook 中显示简短说明，该说明可提供有关邮件创建者可能违反策略的信息。有关详细信息，请参阅 **Policy Tips** 。  <br/> 有关模式的详细信息，请参阅 **Test a mail flow rule** 。  <br/> |
|**在以下日期激活此规则** <br/> **在以下日期停用此规则** <br/> | _ActivationDate_ <br/>  _ExpiryDate_ <br/> |指定启用该规则的日期范围。  <br/> |
|选中或未选中 **On** 复选框  <br/> |新规则： _New-TransportRule_ cmdlet 中的  **Enabled** 参数。  <br/> 现有规则：使用 **Enable-TransportRule** 或 **Disable-TransportRule** cmdlet。  <br/> 该值显示在规则的 **State** 属性中。  <br/> |可以创建一个禁用规则，并在准备测试它时将其启用。或者，在不删除该规则的情况下将其禁用，以保留设置。  <br/> |
|**如果规则处理未完成，则延迟邮件** <br/> | _RuleErrorAction_ <br/> |如果无法完成规则处理，可以指定邮件的处理方式。默认情况下，系统将忽略该规则，但可以选择重新提交邮件进行处理。  <br/> |
|**匹配邮件中的发件人地址** <br/> | _SenderAddressLocation_ <br/> |如果规则使用检查发件人的电子邮件地址的条件或例外，则可以在邮件标头、 邮件信封或同时在两者中查找该值。  <br/> |
|**停止处理更多规则** <br/> | _SenderAddressLocation_ <br/> |这是一种规则操作，但它看起来像 EAC 中的属性。你可以选择在规则处理完某个邮件后，停止向邮件应用其他规则。  <br/> |
|**注释** <br/> | _Comments_ <br/> |可以输入有关规则的描述性注释。  <br/> |
   
## <a name="how-mail-flow-rules-are-applied-to-messages"></a>如何将邮件流规则应用于邮件

All messages that flow through your organization are evaluated against the enabled mail flow rules in your organization. Rules are processed in the order listed on the **Mail flow** \> **Rules** page in EAC, or based on the corresponding  _Priority_ parameter value in the PowerShell. 
  
每个规则还提供在规则匹配时停止处理其他规则的选项。此设置对于匹配多个邮件流规则中条件的邮件而言非常重要（想要哪个规则应用于邮件？全部？还是一个？）。
  
### <a name="differences-in-processing-based-on-message-type"></a>基于消息类型的处理的差异

通过组织进行传递的邮件有几种类型。下表显示了哪些邮件类型可以通过邮件流规则进行处理。
  
****

|**消息类型**|**是否可以应用规则？**|
|:-----|:-----|
|**常规邮件** 包含单个富文本格式 (RTF)、HTML、纯文本邮件正文、多部分或备用的邮件正文集的邮件。  <br/> |是  <br/> |
|**Office 365 邮件加密 ** 邮件通过 Office 365 中的 Office 365 邮件加密 进行加密。有关详细信息，请参阅 [Office 365 邮件加密](https://go.microsoft.com/fwlink/p/?LinkId=392525)。  <br/> |规则可始终根据检查这些标头的条件来访问信封头并处理邮件。  <br/> 对于检查或修改加密邮件内容的规则，需要验证是否启用了传输解密（强制或可选；默认为可选）。有关详细信息，请参阅 [Enable or disable transport decryption](https://go.microsoft.com/fwlink/p/?linkid=848060)（启用或禁用传输解密）。  <br/> 还可以创建规则，自动解密加密邮件。有关详细信息，请参阅[为加密或解密电子邮件定义规则](https://go.microsoft.com/fwlink/p/?Linkid=402846)。  <br/> |
|**S/MIME 加密邮件** <br/> |规则仅可根据检查这些标头的条件来访问信封头并处理邮件。  <br/> 无法处理具有需要检查邮件内容的条件的规则或可以修改邮件内容的操作。  <br/> |
|**RMS 保护的邮件** 应用 Active Directory Rights Management Services (AD RMS) 或 Azure 权限管理 (RMS) 策略的邮件。  <br/> |规则可始终根据检查这些标头的条件来访问信封头并处理邮件。  <br/> 对于检查或修改 RMS 保护的邮件内容的规则，需要验证是否启用了传输解密（强制或可选；默认为可选）。有关详细信息，请参阅 [Enable or disable transport decryption](https://go.microsoft.com/fwlink/p/?linkid=848060)（启用或禁用传输解密）。  <br/> |
|**已明文签名的邮件** 已签名但未加密的邮件。  <br/> |是  <br/> |
|**UM 邮件** 由统一消息服务创建或处理的邮件，如语音邮件、传真、未接来电通知以及使用 Microsoft Outlook Voice Access 创建或转发的邮件。  <br/> |是  <br/> |
|**匿名邮件** 由匿名发件人发送的邮件。  <br/> |是  <br/> |
|**读取报告** 为响应发件人的阅读回执请求而生成的报告。读取报告具有邮件类别  `IPM.Note*.MdnRead` 或  `IPM.Note*.MdnNotRead`。  <br/> |是  <br/> |
   
## <a name="what-else-should-i-know"></a>我还应该知道些什么？

- 在 Exchange Online Protection 中, 规则的**Version**或**RuleVersion**属性值并不重要。 
    
- 在创建或修改邮件流规则后, 最长可能需要30分钟才能将新的或更新的规则应用于邮件。
    
## <a name="for-more-information"></a>详细信息
  
[使用邮件流规则在 Exchange Online 中检查邮件附件](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)
  
[Office 365 中的电子邮件加密](https://support.office.com/article/c0d87cbe-6d65-4c03-88ad-5216ea5564e8)
  
[日记、传输和收件箱规则限制](https://go.microsoft.com/fwlink/p/?LinkId=324584)

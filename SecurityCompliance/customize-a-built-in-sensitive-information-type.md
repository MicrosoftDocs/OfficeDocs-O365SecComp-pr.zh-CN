---
title: 自定义内置敏感信息类型
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/25/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2164ce3d-4d64-4283-b6b1-b81fbe835e8e
description: 在内容中查找敏感信息时，需要在规则中描述相应信息。数据丢失防护 (DLP) 包含最常见敏感信息类型对应的规则，可供立即使用。若要使用这些规则，必须将它们添加到策略中。你可能会发现，需要调整这些内置规则，才能满足组织的特定需求。为此，请创建自定义敏感信息类型。本主题介绍了如何将包含现有规则集合的 XML 文件自定义为，检测更广泛的潜在信用卡信息。
ms.openlocfilehash: e0a2751ff8d89e664343e91937713af6af74264f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525061"
---
# <a name="customize-a-built-in-sensitive-information-type"></a>自定义内置敏感信息类型

在内容中查找敏感信息时，需要在*规则*中描述相应信息。数据丢失防护 (DLP) 包含最常见敏感信息类型对应的规则，可供立即使用。若要使用这些规则，必须将它们添加到策略中。你可能会发现，需要调整这些内置规则，才能满足组织的特定需求。为此，请创建自定义敏感信息类型。本主题介绍了如何将包含现有规则集合的 XML 文件自定义为，检测更广泛的潜在信用卡信息。 
  
可以参考本示例，自定义其他内置敏感信息类型。有关默认敏感信息类型和 XML 定义的列表，请参阅[敏感信息类型查找什么](what-the-sensitive-information-types-look-for.md)。 
  
## <a name="export-the-xml-file-of-the-current-rules"></a>导出当前规则的 XML 文件

必须[通过远程 PowerShell 连接到安全与合规中心](https://go.microsoft.com/fwlink/?linkid=799771)，才能导出 XML。
  
1. 在 PowerShell 中，键入下面的代码，以在屏幕上显示组织的规则。如果还没有创建你自己的规则，就只会看到标记为“Microsoft 规则包”默认内置规则。
    
     `Get-DlpSensitiveInformationTypeRulePackage`
    
2. 键入下面的代码，将组织的规则存储到变量中。存储到变量中的规则稍后可供轻松使用，因为它的格式适用于远程 PowerShell 命令。
    
     `$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage`
    
3. 键入下面的代码，生成包含所有这些数据的格式标准的 XML 文件。（`Set-content` 属于将 XML 写入文件的 cmdlet。） 
    
     `Set-Content -path "C:\custompath\exportedRules.xml" -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection`
    
    > [!IMPORTANT]
    > 请务必使用规则包实际存储到的文件位置。`C:\custompath\` 是占位符。 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a>在 XML 中查找要修改的规则

上面的 cmdlet 导出了整个*规则集合*，其中包括我们提供的默认规则。接下来，需要专门查找要修改的“信用卡号”规则。 
  
1. 使用文本编辑器打开在上一部分中导出的 XML 文件。
    
2. 向下滚动到 `<Rules>` 标记，这是包含 DLP 规则的部分的开头。（由于这个 XML 文件包含整个规则集合的信息，因此需要滚动略过顶部的其他信息，才能到规则部分。） 
    
3. 查找 *Func_credit_card*，以找到“信用卡号”规则定义。（在 XML 中，规则名称不得包含空格，因此空格通常被替换为下划线字符。规则名称有时会采用缩写形式。例如，“美国身份证号”规则采用缩写名称“SSN”。“信用卡号”规则 XML 应如下面的代码示例所示。 
    
  ```
  <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
         patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
         <IdMatch idRef="Func_credit_card" />
          <Any minMatches="1">
            <Match idRef="Keyword_cc_verification" />
            <Match idRef="Keyword_cc_name" />
            <Match idRef="Func_expiration_date" />
          </Any>
        </Pattern>
      </Entity>
  ```

现在您已在 XML 中找到信用卡号规则定义，您可以自定义规则的 XML 以满足您的需求。（要刷新 XML 定义，请参阅本主题结尾的[术语表](#term-glossary)。） 
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a>修改 XML 并新建敏感信息类型

首先，需要新建敏感信息类型，因为无法直接修改默认规则。不过，如[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)中所述，可对自定义敏感信息类型执行各种操作。为简单起见，本示例仅删除确证性证据，并向“信用卡号”规则添加关键字。
  
所有 XML 规则定义基于以下通用模板构建。您需要在模板中复制和粘贴信用卡号定义，修改某些值（请注意以下示例中的".. ." 占位符），然后将修改后的 XML 作为可用于策略的新规则进行上载。
  
```
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
   <!-- Paste the Credit Card Number rule definition here.--> 
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

现在，您的 XML 应该如下所示。因为规则包和规则使用它们的唯一 GUID 表示，您需要生成两个 GUID：一个用于规则包，一个用于替换信用卡号规则的 GUID。（以下代码示例中实体 ID 的 GUID 用于我们的内置规则定义，您需将其替换为新的 GUID。）有多种方法可以生成 GUID，但您可以通过键入 **[guid]::NewGuid()** ，在 PowerShell 中轻松生成 GUID。 
  
```
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f"> 
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a>从敏感信息类型中删除确证性证据要求

至此，已有可上传到安全与合规中心的新敏感信息类型，下一步是让规则更具体化。请将规则修改为，仅查找传递校验和的 16 位数，无需发现其他（确证性）证据（例如，关键字）。为此，需要删除查找确证性证据的 XML 部分。确证性证据对减少误报非常有用，因为信用卡号附近通常有特定的关键字或到期日期。如果删除确证性证据，还应降低 `confidenceLevel`（在本示例中为 85），以调整所找到信用卡号的可信度。
  
```
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a>查找组织专用关键字

你可能还是需要规定确证性证据，只不过需要其他关键字罢了，或许也想要更改在何处查找确证性证据。可调整 `patternsProximity`，以扩展或收缩 16 位数条件两边的确证性证据窗口。若要添加你自己的关键字，需要定义关键字列表，并在规则中引用此列表。下面的 XML 添加关键字“公司卡”和“Contoso 卡”，这样任何在距离信用卡号 150 个字符内包含这些短语的邮件都会被标识为包含信用卡号。 
  
```
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a>上传规则

要上载您的规则，需执行以下操作：
  
1. 使用 Unicode 编码将其另存为 .xml 文件。这一点很重要，因为如果文件使用其他编码保存，将无法正常运行。
    
2. [使用远程 PowerShell 连接到安全与合规中心](https://go.microsoft.com/fwlink/?linkid=799771)。
    
3. 在 PowerShell 中，键入下面的代码。
    
     `New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)`（）。
    
    > [!IMPORTANT]
    > 请务必使用规则包实际存储到的文件位置。`C:\custompath\` 是占位符。 
  
4. 若要确认，请先键入“Y”，再按 Enter****。
    
5. 键入 `Get-DlpSensitiveInformationType`，以验证新规则是否已获上传（此时应显示规则名称）。
    
必须将规则添加到 DLP 策略中，才能开始使用新规则检测敏感信息。若要了解如何将规则添加到策略中，请参阅[使用模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)。
  
## <a name="term-glossary"></a>术语表

下面您在此过程中遇到的术语的定义。
  
|**术语**|**定义**|
|:-----|:-----|
|实体  <br/> |实体是我们称为敏感信息类型的项目，例如信用卡号。每个实体都有一个唯一的 GUID 作为其 ID。如果您复制 GUID 并在 XML 中搜索它，您将找到 XML 规则定义以及该 XML 规则的所有本地化翻译。您也可以通过查找翻译的 GUID 并搜索该 GUID 来查找此定义。  <br/> |
|函数  <br/> |XML 文件引用 `Func_credit_card`，这是用代码编译而成的函数。函数用于运行复杂的正则表达式，并验证校验和是否符合内置规则。由于这是发生在代码中，因此一些变量不会显示在 XML 文件中。<br/> |
|IdMatch  <br/> |这是模式尝试要匹配的标识符（例如，信用卡号）。可参阅[实体规则](https://support.office.com/article/c4ab8707-0839-4855-9390-3dbcb43475a7.aspx#dlp-entity)，详细了解此标识符和 `Match` 标记。<br/> |
|关键字列表  <br/> |XML 文件还引用 `keyword_cc_verification` 和 `keyword_cc_name`，这是要在实体的 `patternsProximity` 范围内匹配的关键字列表。这些关键字暂不显示在 XML 中。<br/> |
|模式  <br/> |模式包含敏感类型所查找内容的列表。这包括关键字、regex 和内部函数（执行验证校验和之类的任务）。敏感信息类型可能具有多个模式，每个模式均具有唯一的可信度。这在创建敏感信息类型时非常有用：当它找到确定证据时，返回高可信度；当未找到确定证据时，则返回较低的可信度。  <br/> |
|模式可信度  <br/> |这是指 DLP 引擎找到匹配的可信度。如果满足模式的要求，则可信度与模式匹配有关。这是当您使用 Exchange 传输规则 (ETR) 时应考虑的可信度衡量标准。  <br/> |
|patternsProximity  <br/> |`patternsProximity` 是指在查找信用卡号模式时，在与信用卡号多近的范围内查找确证性证据。  <br/> |
|recommendedConfidence  <br/> |这是建议用于此规则的可信度。建议可信度适用于实体和关联。对于实体，永远不会根据模式的 `confidenceLevel` 评估此数值。它只是帮助你在需要时选择可信度的建议。对于关联，模式的 `confidenceLevel` 必须高于 `recommendedConfidence` 数值，才能调用 ETR 操作。`recommendedConfidence` 是调用操作的 ETR 使用的默认可信度。如果需要，可根据模式的可信度来手动更改要调用的 ETR。<br/> |
   
## <a name="for-more-information"></a>更多信息

- [敏感信息类型查找什么](what-the-sensitive-information-types-look-for.md)
    
- [创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)
    
- [数据丢失防护策略概述](data-loss-prevention-policies.md)
    


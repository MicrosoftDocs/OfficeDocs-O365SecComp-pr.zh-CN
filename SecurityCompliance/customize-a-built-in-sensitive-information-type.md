---
title: 自定义内置敏感信息类型
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 在内容中查找敏感信息时，需要在规则中描述相应信息。数据丢失防护 (DLP) 包含最常见敏感信息类型对应的规则，可供立即使用。若要使用这些规则，必须将它们添加到策略中。你可能会发现，需要调整这些内置规则，才能满足组织的特定需求。为此，请创建自定义敏感信息类型。本主题介绍了如何将包含现有规则集合的 XML 文件自定义为，检测更广泛的潜在信用卡信息。
ms.openlocfilehash: 8a621e3f1b24a8cea9cd263e44dc2def8a8b95b7
ms.sourcegitcommit: a6f046f1529b0515f4f0e918a19ec83f4138b871
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2019
ms.locfileid: "35587101"
---
# <a name="customize-a-built-in-sensitive-information-type"></a><span data-ttu-id="72fb1-107">自定义内置敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="72fb1-107">Customize a built-in sensitive information type</span></span>

<span data-ttu-id="72fb1-p102">在内容中查找敏感信息时，需要在*规则*中描述相应信息。数据丢失防护 (DLP) 包含最常见敏感信息类型对应的规则，可供立即使用。若要使用这些规则，必须将它们添加到策略中。你可能会发现，需要调整这些内置规则，才能满足组织的特定需求。为此，请创建自定义敏感信息类型。本主题介绍了如何将包含现有规则集合的 XML 文件自定义为，检测更广泛的潜在信用卡信息。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p102">When looking for sensitive information in content, you need to describe that information in what's called a  *rule*  . Data loss prevention (DLP) includes rules for the most-common sensitive information types that you can use right away. To use these rules, you have to include them in a policy. You might find that you want to adjust these built-in rules to meet your organization's specific needs, and you can do that by creating a custom sensitive information type. This topic shows you how to customize the XML file that contains the existing rule collection to detect a wider range of potential credit-card information.</span></span> 
  
<span data-ttu-id="72fb1-p103">可以参考本示例，自定义其他内置敏感信息类型。有关默认敏感信息类型和 XML 定义的列表，请参阅[敏感信息类型查找什么](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p103">You can take this example and apply it to other built-in sensitive information types. For a list of default sensitive information types and XML definitions, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span> 
  
## <a name="export-the-xml-file-of-the-current-rules"></a><span data-ttu-id="72fb1-115">导出当前规则的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="72fb1-115">Export the XML file of the current rules</span></span>

<span data-ttu-id="72fb1-116">必须[通过远程 PowerShell 连接到安全与合规中心](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)，才能导出 XML。</span><span class="sxs-lookup"><span data-stu-id="72fb1-116">To export the XML, you need to [connect to the Security and Compliance Center via Remote PowerShell.](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="72fb1-p104">在 PowerShell 中，键入下面的代码，以在屏幕上显示组织的规则。如果还没有创建你自己的规则，就只会看到标记为“Microsoft 规则包”默认内置规则。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p104">In the PowerShell, type the following to display your organization's rules on screen. If you haven't created your own, you'll only see the default, built-in rules, labeled "Microsoft Rule Package."</span></span>
    
     `Get-DlpSensitiveInformationTypeRulePackage`
    
2. <span data-ttu-id="72fb1-p105">键入下面的代码，将组织的规则存储到变量中。存储到变量中的规则稍后可供轻松使用，因为它的格式适用于远程 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p105">Store your organization's rules in a in a variable by typing the following. Storing something in a variable makes it easily available later in a format that works for remote PowerShell commands.</span></span>
    
     `$ruleCollections = Get-DlpSensitiveInformationTypeRulePackage`
    
3. <span data-ttu-id="72fb1-p106">键入下面的代码，生成包含所有这些数据的格式标准的 XML 文件。（`Set-content` 属于将 XML 写入文件的 cmdlet。）</span><span class="sxs-lookup"><span data-stu-id="72fb1-p106">Make a formatted XML file with all that data by typing the following. ( `Set-content` is the part of the cmdlet that writes the XML to the file.)</span></span> 
    
     `Set-Content -path "C:\custompath\exportedRules.xml" -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection`
    
    > [!IMPORTANT]
    > <span data-ttu-id="72fb1-p107">请务必使用规则包实际存储到的文件位置。`C:\custompath\` 是占位符。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p107">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a><span data-ttu-id="72fb1-125">在 XML 中查找要修改的规则</span><span class="sxs-lookup"><span data-stu-id="72fb1-125">Find the rule that you want to modify in the XML</span></span>

<span data-ttu-id="72fb1-p108">上面的 cmdlet 导出了整个*规则集合*，其中包括我们提供的默认规则。接下来，需要专门查找要修改的“信用卡号”规则。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p108">The cmdlets above exported the entire  *rule collection*  , which includes the default rules we provide. Next you'll need to look specifically for the Credit Card Number rule that you want to modify.</span></span> 
  
1. <span data-ttu-id="72fb1-128">使用文本编辑器打开在上一部分中导出的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="72fb1-128">Use a text editor to open the XML file that you exported in the previous section.</span></span>
    
2. <span data-ttu-id="72fb1-p109">向下滚动到 `<Rules>` 标记，这是包含 DLP 规则的部分的开头。（由于这个 XML 文件包含整个规则集合的信息，因此需要滚动略过顶部的其他信息，才能到规则部分。）</span><span class="sxs-lookup"><span data-stu-id="72fb1-p109">Scroll down to the  `<Rules>` tag, which is the start of the section that contains the DLP rules. (Because this XML file contains the information for the entire rule collection, it contains other information at the top that you need to scroll past to get to the rules.)</span></span> 
    
3. <span data-ttu-id="72fb1-p110">查找 *Func_credit_card*，以找到“信用卡号”规则定义。（在 XML 中，规则名称不得包含空格，因此空格通常被替换为下划线字符。规则名称有时会采用缩写形式。例如，“美国身份证号”规则采用缩写名称“SSN”。“信用卡号”规则 XML 应如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p110">Look for  *Func_credit_card*  to find the Credit Card Number rule definition. (In the XML, rule names can't contain spaces, so the spaces are usually replaced with underscores, and rule names are sometimes abbreviated. An example of this is the U.S. Social Security number rule, which is abbreviated "SSN." The Credit Card Number rule XML should look like the following code sample.</span></span> 
    
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

<span data-ttu-id="72fb1-p111">现在您已在 XML 中找到信用卡号规则定义，您可以自定义规则的 XML 以满足您的需求。（要刷新 XML 定义，请参阅本主题结尾的[术语表](#term-glossary)。）</span><span class="sxs-lookup"><span data-stu-id="72fb1-p111">Now that you have located the Credit Card Number rule definition in the XML, you can customize the rule's XML to meet your needs. (For a refresher on the XML definitions, see the [Term glossary](#term-glossary) at the end of this topic.)</span></span> 
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a><span data-ttu-id="72fb1-137">修改 XML 并新建敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="72fb1-137">Modify the XML and create a new sensitive information type</span></span>

<span data-ttu-id="72fb1-p112">首先，需要新建敏感信息类型，因为无法直接修改默认规则。如[使用安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)中所述，可对自定义敏感信息类型执行各种操作。为简单起见，此示例仅删除确证性证据，并向“信用卡号”规则添加关键字。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p112">First, you need to create a new sensitive information type because you can't directly modify the default rules. You can do a wide variety of things with custom sensitive information types, which are outlined in [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). For this example, we'll keep it simple and only remove corroborative evidence and add keywords to the Credit Card Number rule.</span></span>
  
<span data-ttu-id="72fb1-p113">所有 XML 规则定义基于以下通用模板构建。您需要在模板中复制和粘贴信用卡号定义，修改某些值（请注意以下示例中的".. ." 占位符），然后将修改后的 XML 作为可用于策略的新规则进行上载。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p113">All XML rule definitions are built on the following general template. You need to copy and paste the Credit Card Number definition XML in the template, modify some values (notice the ". . ." placeholders in the following example), and then upload the modified XML as a new rule that can be used in policies.</span></span>
  
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

<span data-ttu-id="72fb1-p114">现在，您的 XML 应该如下所示。因为规则包和规则使用它们的唯一 GUID 表示，您需要生成两个 GUID：一个用于规则包，一个用于替换信用卡号规则的 GUID。（以下代码示例中实体 ID 的 GUID 用于我们的内置规则定义，您需将其替换为新的 GUID。）有多种方法可以生成 GUID，但您可以通过键入 **[guid]::NewGuid()** ，在 PowerShell 中轻松生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p114">Now, you have something that looks similar to the following XML. Because rule packages and rules are identified by their unique GUIDs, you need to generate two GUIDs: one for the rule package and one to replace the GUID for the Credit Card Number rule. (The GUID for the entity ID in the following code sample is the one for our built-in rule definition, which you need to replace with a new one.) There are several ways to generate GUIDs, but you can do it easily in PowerShell by typing **[guid]::NewGuid()**.</span></span> 
  
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

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a><span data-ttu-id="72fb1-149">从敏感信息类型中删除确证性证据要求</span><span class="sxs-lookup"><span data-stu-id="72fb1-149">Remove the corroborative evidence requirement from a sensitive information type</span></span>

<span data-ttu-id="72fb1-p115">至此，已有可上传到安全与合规中心的新敏感信息类型，下一步是让规则更具体化。请将规则修改为，仅查找传递校验和的 16 位数，无需发现其他（确证性）证据（例如，关键字）。为此，需要删除查找确证性证据的 XML 部分。确证性证据对减少误报非常有用，因为信用卡号附近通常有特定的关键字或到期日期。如果删除确证性证据，还应降低 `confidenceLevel`（在本示例中为 85），以调整所找到信用卡号的可信度。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p115">Now that you have a new sensitive information type that you're able to upload to the Security &amp; Compliance Center, the next step is to make the rule more specific. Modify the rule so that it only looks for a 16-digit number that passes the checksum but doesn't require additional (corroborative) evidence (for example keywords). To do this, you need to remove the part of the XML that looks for corroborative evidence. Corroborative evidence is very helpful in reducing false positives because usually there are certain keywords or an expiration date near the credit card number. If you remove that evidence, you should also adjust how confident you are that you found a credit card number by lowering the  `confidenceLevel`, which is 85 in the example.</span></span>
  
```
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a><span data-ttu-id="72fb1-155">查找组织专用关键字</span><span class="sxs-lookup"><span data-stu-id="72fb1-155">Look for keywords that are specific to your organization</span></span>

<span data-ttu-id="72fb1-p116">你可能还是需要规定确证性证据，只不过需要其他关键字罢了，或许也想要更改在何处查找确证性证据。可调整 `patternsProximity`，以扩展或收缩 16 位数条件两边的确证性证据窗口。若要添加你自己的关键字，需要定义关键字列表，并在规则中引用此列表。下面的 XML 添加关键字“公司卡”和“Contoso 卡”，这样任何在距离信用卡号 150 个字符内包含这些短语的邮件都会被标识为包含信用卡号。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p116">You might want to require corroborative evidence but want different or additional keywords, and perhaps you want to change where to look for that evidence. You can adjust the  `patternsProximity` to expand or shrink the window for corroborative evidence around the 16-digit number. To add your own keywords, you need to define a keyword list and reference it within your rule. The following XML adds the keywords "company card" and "Contoso card" so that any message that contains those phrases within 150 characters of a credit card number will be identified as a credit card number.</span></span> 
  
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

## <a name="upload-your-rule"></a><span data-ttu-id="72fb1-160">上传规则</span><span class="sxs-lookup"><span data-stu-id="72fb1-160">Upload your rule</span></span>

<span data-ttu-id="72fb1-161">要上载您的规则，需执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="72fb1-161">To upload your rule, you need to do the following.</span></span>
  
1. <span data-ttu-id="72fb1-p117">使用 Unicode 编码将其另存为 .xml 文件。这一点很重要，因为如果文件使用其他编码保存，将无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p117">Save it as an .xml file with Unicode encoding. This is important because the rule won't work if the file is saved with a different encoding.</span></span>
    
2. <span data-ttu-id="72fb1-164">[使用远程 PowerShell 连接到安全与合规中心](https://go.microsoft.com/fwlink/?linkid=799771)。</span><span class="sxs-lookup"><span data-stu-id="72fb1-164">[Connect to the Security and Compliance Center via Remote PowerShell.](https://go.microsoft.com/fwlink/?linkid=799771)</span></span>
    
3. <span data-ttu-id="72fb1-165">在 PowerShell 中，键入下面的代码。</span><span class="sxs-lookup"><span data-stu-id="72fb1-165">In the PowerShell, type the following.</span></span>
    
     <span data-ttu-id="72fb1-166">`New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)`（）。</span><span class="sxs-lookup"><span data-stu-id="72fb1-166">`New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)`.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="72fb1-p118">请务必使用规则包实际存储到的文件位置。`C:\custompath\` 是占位符。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p118">Make sure that you use the file location where your rule pack is actually stored.  `C:\custompath\` is a placeholder.</span></span> 
  
4. <span data-ttu-id="72fb1-169">若要确认，请先键入“Y”，再按 Enter\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="72fb1-169">To confirm, type Y, and then press **Enter**.</span></span>
    
5. <span data-ttu-id="72fb1-170">键入 `Get-DlpSensitiveInformationType`，以验证新规则是否已获上传（此时应显示规则名称）。</span><span class="sxs-lookup"><span data-stu-id="72fb1-170">Verify that your new rule was uploaded by typing  `Get-DlpSensitiveInformationType`, which now displays the name of your rule.</span></span>
    
<span data-ttu-id="72fb1-p119">必须将规则添加到 DLP 策略中，才能开始使用新规则检测敏感信息。若要了解如何将规则添加到策略中，请参阅[使用模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p119">To start using the new rule to detect sensitive information, you need to add the rule to a DLP policy. To learn how to add the rule to a policy, see [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md).</span></span>
  
## <a name="term-glossary"></a><span data-ttu-id="72fb1-173">术语表</span><span class="sxs-lookup"><span data-stu-id="72fb1-173">Term glossary</span></span>

<span data-ttu-id="72fb1-174">下面您在此过程中遇到的术语的定义。</span><span class="sxs-lookup"><span data-stu-id="72fb1-174">These are the definitions for the terms you encountered during this procedure.</span></span>
  
|<span data-ttu-id="72fb1-175">**术语**</span><span class="sxs-lookup"><span data-stu-id="72fb1-175">**Term**</span></span>|<span data-ttu-id="72fb1-176">**定义**</span><span class="sxs-lookup"><span data-stu-id="72fb1-176">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="72fb1-177">实体</span><span class="sxs-lookup"><span data-stu-id="72fb1-177">Entity</span></span>|<span data-ttu-id="72fb1-p120">实体是我们称为敏感信息类型的项目，例如信用卡号。每个实体都有一个唯一的 GUID 作为其 ID。如果您复制 GUID 并在 XML 中搜索它，您将找到 XML 规则定义以及该 XML 规则的所有本地化翻译。您也可以通过查找翻译的 GUID 并搜索该 GUID 来查找此定义。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p120">Entities are what we call sensitive information types, such as credit card numbers. Each entity has a unique GUID as its ID. If you copy a GUID and search for it in the XML, you'll find the XML rule definition and all the localized translations of that XML rule. You can also find this definition by locating the GUID for the translation and then searching for that GUID.</span></span>|
|<span data-ttu-id="72fb1-182">函数</span><span class="sxs-lookup"><span data-stu-id="72fb1-182">Functions</span></span>|<span data-ttu-id="72fb1-p121">XML 文件引用 `Func_credit_card`，这是用代码编译而成的函数。函数用于运行复杂的正则表达式，并验证校验和是否符合内置规则。由于这是发生在代码中，因此一些变量不会显示在 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p121">The XML file references  `Func_credit_card`, which is a function in compiled code. Functions are used to run complex regexes and verify that checksums match for our built-in rules.) Because this happens in the code, some of the variables don't appear in the XML file.</span></span>|
|<span data-ttu-id="72fb1-185">IdMatch</span><span class="sxs-lookup"><span data-stu-id="72fb1-185">IdMatch</span></span>|<span data-ttu-id="72fb1-186">这是尝试匹配的模式的标识符，例如信用卡号。</span><span class="sxs-lookup"><span data-stu-id="72fb1-186">This is the identifier that the pattern is to trying to match—for example, a credit card number.</span></span>|
|<span data-ttu-id="72fb1-187">关键字列表</span><span class="sxs-lookup"><span data-stu-id="72fb1-187">Keyword lists</span></span>|<span data-ttu-id="72fb1-p122">XML 文件还引用 `keyword_cc_verification` 和 `keyword_cc_name`，这是要在实体的 `patternsProximity` 范围内匹配的关键字列表。这些关键字暂不显示在 XML 中。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p122">The XML file also references  `keyword_cc_verification` and  `keyword_cc_name`, which are lists of keywords from which we are looking for matches within the  `patternsProximity` for the entity. These aren't currently displayed in the XML.</span></span>|
|<span data-ttu-id="72fb1-190">模式</span><span class="sxs-lookup"><span data-stu-id="72fb1-190">Pattern</span></span>|<span data-ttu-id="72fb1-p123">模式包含敏感类型所查找内容的列表。这包括关键字、regex 和内部函数（执行验证校验和之类的任务）。敏感信息类型可能具有多个模式，每个模式均具有唯一的可信度。这在创建敏感信息类型时非常有用：当它找到确定证据时，返回高可信度；当未找到确定证据时，则返回较低的可信度。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p123">The pattern contains the list of what the sensitive type is looking for. This includes keywords, regexes, and internal functions (that perform tasks like verifying checksums). Sensitive information types can have multiple patterns with unique confidences. This is useful when creating a sensitive information type that returns a high confidence if corroborative evidence is found and a lower confidence if little or no corroborative evidence is found.</span></span>|
|<span data-ttu-id="72fb1-195">模式可信度</span><span class="sxs-lookup"><span data-stu-id="72fb1-195">Pattern confidenceLevel</span></span>|<span data-ttu-id="72fb1-p124">这是指 DLP 引擎找到匹配的可信度。如果满足模式的要求，则可信度与模式匹配有关。这是当您使用 Exchange 邮件流规则（也称为传输规则）时应考虑的可信度衡量标准。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p124">This is the level of confidence that the DLP engine found a match. This level of confidence is associated with a match for the pattern if the pattern's requirements are met. This is the confidence measure you should consider when using Exchange mail flow rules (also known as transport rules).</span></span>|
|<span data-ttu-id="72fb1-199">patternsProximity</span><span class="sxs-lookup"><span data-stu-id="72fb1-199">patternsProximity</span></span>|<span data-ttu-id="72fb1-200">`patternsProximity` 是指在查找信用卡号模式时，在与信用卡号多近的范围内查找确证性证据。</span><span class="sxs-lookup"><span data-stu-id="72fb1-200">When we find what looks like a credit card number pattern,  `patternsProximity` is the proximity around that number where we'll look for corroborative evidence.</span></span>|
|<span data-ttu-id="72fb1-201">recommendedConfidence</span><span class="sxs-lookup"><span data-stu-id="72fb1-201">recommendedConfidence</span></span>|<span data-ttu-id="72fb1-p125">这是建议用于此规则的可信度。建议可信度适用于实体和关联。对于实体，永远不会根据模式的 `confidenceLevel` 评估此数值。它只是帮助你在需要时选择可信度的建议。对于关联，模式的 `confidenceLevel` 必须高于 `recommendedConfidence` 数值，才能调用邮件流规则操作。`recommendedConfidence` 是调用操作的邮件流规则使用的默认可信度。如果需要，可根据模式的可信度来手动更改要调用的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="72fb1-p125">This is the confidence level we recommend for this rule. The recommended confidence applies to entities and affinities. For entities, this number is never evaluated against the  `confidenceLevel` for the pattern. It's merely a suggestion to help you choose a confidence level if you want to apply one. For affinities, the  `confidenceLevel` of the pattern must be higher than the  `recommendedConfidence` number for a mail flow rule action to be invoked. The  `recommendedConfidence` is the default confidence level used in mail flow rules that invokes an action. If you want, you can manually change the mail flow rule to be invoked based off the pattern's confidence level, instead.</span></span>|
   
## <a name="for-more-information"></a><span data-ttu-id="72fb1-209">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="72fb1-209">For more information</span></span>

- [<span data-ttu-id="72fb1-210">敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="72fb1-210">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="72fb1-211">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="72fb1-211">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    
- [<span data-ttu-id="72fb1-212">数据丢失防护策略概述</span><span class="sxs-lookup"><span data-stu-id="72fb1-212">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    


---
title: EU 税标识号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟税务识别号敏感信息类型时, 应查找什么。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: f851cce4be70fd41c24a7876d97c452f0a738eda
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213822"
---
# <a name="eu-tax-identification-number"></a>EU 税标识号

本主题介绍了数据丢失防护 (DLP) 策略在检测到欧盟纳税标识号 (TIN) 敏感信息类型时的查找内容。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
  
## <a name="austria"></a>奥地利

### <a name="format"></a>格式

9个数字, 带可选连字符和正斜线
  
### <a name="pattern"></a>模式

9个带可选连字符和正斜线的数字:
  
-  两位数字 
    
- 一个连字符（可选）
    
- 三位数字
    
- 正斜杠（可选）
    
- 四位数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_austria_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_austria_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_austria_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsaustriaeutaxfilenumber"></a>Keywords_austria_eu_tax_file_number

税号
  
多种
  
税务登记编号
  
tax id

  
st.nr。
  
steuernummer
  
## <a name="belgium"></a>比利时

### <a name="format"></a>格式

11个数字, 无空格和分隔符
  
### <a name="pattern"></a>模式

11 个数字：
  
- 两位数字
    
- "0" 或 "1"
    
- 一位数字
    
- "0" 或 "1" 或 "2" 或 "3" 
    
- 六个数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>Definition

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_belgium_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_belgium_eu_tax_file_number`的关键字。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsbelgiumeutaxfilenumber"></a>Keywords_belgium_eu_tax_file_number

税号
  
国家注册号码
  
税务登记编号
  
tax id

  
\n\n
  
\n\n
  
numéro de registre 国
  
numéro d'identification fiscale
  
## <a name="bulgaria"></a>保加利亚

### <a name="format"></a>格式

10个数字, 无空格和分隔符
  
### <a name="pattern"></a>模式

10 个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_bulgaria_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_bulgaria_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_bulgaria_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsbulgariaeutaxfilenumber"></a>Keywords_bulgaria_eu_tax_file_number

bucn
  
统一的民事号码
  
bucn #
  
uniformcivilnumber #
  
统一的民事 id
  
统一的民事无
  
egn
  
保加利亚语统一民事号码
  
uniformcivilno #
  
egn #
  
униформгражданскиномер
  
униформ id
  
униформграждански id
  
униформгражданскине
  
## <a name="croatia"></a>克罗地亚

### <a name="format"></a>格式

11个不带空格或分隔符的数字
  
### <a name="pattern"></a>模式

11 个数字：
  
- 10个数字, 随机选择
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_croatia_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_croatia_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_croatia_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordscroatiaeutaxfilenumber"></a>Keywords_croatia_eu_tax_file_number

税号
  
税种
  
tax id

  
排列
  
排列
  
porezni broj
  
## <a name="cyprus"></a>塞浦路斯

### <a name="format"></a>格式

指定模式中的八个数字和一个字母
  
### <a name="pattern"></a>模式

八个数字和一个字母:
  
-  一个 "0" 
    
- 七个数字 
    
- 一个字母 (不区分大小写)
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_cyprus_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_cyprus_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_cyprus_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordscypruseutaxfilenumber"></a>Keywords_cyprus_eu_tax_file_number

税号
  
税种
  
tax id

  
税标识代码
  
和
  
和
  
αριθμόςφορολογικούμητρώου
  
φορολογικήταυτότητα
  
κωδικόςφορολογικούμητρώου
  
## <a name="czech-republic"></a>捷克共和国

### <a name="format"></a>格式

9个或10个数字, 带可选反斜杠
  
### <a name="pattern"></a>模式

9个或10个数字, 可选 backslashl:
  
- 六位数字 
    
- 反斜杠 (可选)
    
- 三个或四个数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>Definition

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_czech_republic_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_czech_republic_eu_tax_file_number`的关键字。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsczechrepubliceutaxfilenumber"></a>Keywords_czech_republic_eu_tax_file_number

税号
  
税种
  
tax id

  
个人号码
  
daňovéčíslo
  
osobníčíslo
  
## <a name="denmark"></a>丹麦

### <a name="format"></a>格式

10个数字, 包含连字符
  
### <a name="pattern"></a>模式

包含 hyphenl 的10个数字:
  
-  与出生日期对应的6个数字 (DDMMYY) 
    
- 一个连字符 
    
- 与序列号对应的四个数字, 其中第一个数字对应于出生世纪, 最后一个数字对应于个人的性别 (对于男为奇数, 甚至对于母版)
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_denmark_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_denmark_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_denmark_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsdenmarkeutaxfilenumber"></a>Keywords_denmark_eu_tax_file_number

税号
  
税种
  
tax id

  
cpr 编号
  
cpr #
  
skat nummer
  
skat id
  
## <a name="estonia"></a>爱沙尼亚

### <a name="format"></a>格式

11个不带空格或分隔符的数字
  
### <a name="pattern"></a>模式

11 个数字：
  
-  一种与性别和世纪相对应的数字, 其中奇数表示男, 偶数表示女, 如下所示: 1, 2 代表19世纪;3, 4 表示20世纪;对于21世纪, 为 5, 6 
    
- 与出生日期对应的6个数字 (YYMMDD)
    
- 三个数字, 对应于将出生在同一日期的人员组成的序列号
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_estonia_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_estonia_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_estonia_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsestoniaeutaxfilenumber"></a>Keywords_estonia_eu_tax_file_number

税号
  
税种
  
tax id

  
个人代码
  
maksunumber
  
maksu id
  
isikukood
  
## <a name="finland"></a>芬兰

### <a name="format"></a>格式

一个11字符组合的数字、字母、加号和减号
  
### <a name="pattern"></a>模式

一个11个字符的数字、字母和加号和减号的组合:
  
- 六位数字
    
- 以下之一: 加号、减号或字母 "a" (不区分大小写), 其中加号表示介于1800-1899 之间, 负号表示在1900-1999 之间, 而 "a" 表示出生2000和之后
    
- 三位数字
    
- 一个字母或一个数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_finland_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_finland_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_finland_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsfinlandeutaxfilenumber"></a>Keywords_finland_eu_tax_file_number

identification number

  
个人 id
  
标识号码
  
芬兰国家/地区 id 号
  
personalidnumber #
  
国家/地区标识号
  
id 号
  
国家/地区 id 编号。
  
国家/地区 id 号
  
id 号
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
ainutlaatuinen henkilökohtainen tunnus
  
identiteetti numero
  
suomen kansallinen henkilötunnus
  
henkilötunnusnumero #
  
kansallisen tunnistenumero
  
tunnusnumero
  
kansallinen tunnus numero
  
## <a name="france"></a>法国

### <a name="format"></a>格式

13位数的个人和九个数字的实体
  
### <a name="pattern"></a>模式

适用于个人的13个数字:
  
- 一个数字, 必须为0、1、2或3
    
- 12 个数字
    
9个图元数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_france_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_france_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_france_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsfranceeutaxfilenumber"></a>Keywords_france_eu_tax_file_number

税标识号
  
税号
  
tax id

  
numéro d'identification fiscale
  
## <a name="germany"></a>德国

### <a name="format"></a>格式

11个数字, 无空格和分隔符
  
### <a name="pattern"></a>模式

11位数字:
  
-  10位数字 
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_germany_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_germany_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_germany_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsgermanyeutaxfilenumber"></a>Keywords_germany_eu_tax_file_number

税号
  
纳税编号
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税标识号
  
税号标识号。
  
steuernummer
  
steuer id
  
steueridentifikationsnummer
  
## <a name="greece"></a>希腊

### <a name="format"></a>格式

9个数字, 不带空格和分隔符
  
### <a name="pattern"></a>模式

九个数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>Definition

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_greece_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_greece_eu_tax_file_number`的关键字。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsgreeceeutaxfilenumber"></a>Keywords_greece_eu_tax_file_number

afm
  
tin

  
税号编号
  
税号编号
  
税标识号
  
税务注册表号
  
税务注册表号
  
afm
  
锡
  
taxidno #
  
taxregistryno #
  
αριθμόςφορολογικούμητρώου
  
aφμ
  
aφμαριθμός
  
φορολογικούμητρώουνο。
  
τοναριθμόφορολογικούμητρώου
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

10个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

10位数字:
  
-  一个必须为 "8" 的数字 
    
- 与日期01/01/1867 之间的天数对应的五个数字和个人的出生日期
    
- 三个数字, 对应于通过机会区分在同一天的人所生成的数字
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_hungary_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_hungary_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_hungary_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordshungaryeutaxfilenumber"></a>Keywords_hungary_eu_tax_file_number

匈牙利语税号标识号
  
匈牙利纳税人标识号
  
税务 id 号
  
vat 号码
  
税务主管机构编号
  
税号纳税标识号
  
taxidnumber #
  
锡
  
hungatiantin #
  
税号标识编号
  
taxidno #
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>Ireland

### <a name="format"></a>格式

七位数字后跟一个不带空格或分隔符的字母
  
### <a name="pattern"></a>模式

七位数字后跟一个字母:
  
-  七个数字  
    
- 一个字母 (不区分大小写)
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_ireland_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_ireland_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_ireland_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsirelandeutaxfilenumber"></a>Keywords_ireland_eu_tax_file_number

公共服务编号
  
个人公开服务编号
  
pps no
  
个人服务编号
  
pps 服务否
  
ppsno #
  
爱尔兰 pps 否
  
publicserviceno #
  
个人公开服务号码
  
uimhir phearsanta seirbhíse poiblí
  
pps uimh
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>意大利

### <a name="format"></a>格式

指定模式中的16个字母和数字
  
### <a name="pattern"></a>模式

16个字母和数字:
  
-  与系列名称中的前三个辅音对应的三个字母 
    
- 与名字中的第一个、第三个和第四个辅音对应的三个字母
    
- 与出生年份的最后一个数字对应的两个数字
    
- 一个与出生月份相对应的数字 (字母按字母顺序使用), 但仅使用字母 A 到 E、H、L、M、P、R 和 T (因此, 一月为 a, 10 月为 r)
    
- 两个数字, 对应于出生月份中的某一天, 其中40将添加到偶数的出生日, 以区别于奇数
    
- 与某人出生的 municipality 特定的区号相对应的四个数字 (国家/地区代码用于外国国家/地区)
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_italy_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_italy_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_italy_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsitalyeutaxfilenumber"></a>Keywords_italy_eu_tax_file_number

税号
  
纳税编号
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
会计代码
  
codice fiscale
  
## <a name="latvia"></a>拉脱维亚

### <a name="format"></a>格式

11个不带空格或分隔符的数字
  
### <a name="pattern"></a>模式

指定模式中的11位数
  
-  六个数字, 对应于出生日期 (DDMMYY) 
    
- 一个与 "出生世纪" 相对应的数字, 其中 "0" 对应于19世纪, "1" 对应于20世纪, "2" 对应于21世纪。
    
- 四位数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_latvia_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_latvia_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_latvia_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordslatviaeutaxfilenumber"></a>Keywords_latvia_eu_tax_file_number

税号
  
纳税编号
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税标识号
  
税号标识号。
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

11位数, 不含空格或分隔符
  
### <a name="pattern"></a>模式

11 个数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_lithuania_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_lithuania_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_lithuania_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordslithuaniaeutaxfilenumber"></a>Keywords_lithuania_eu_tax_file_number

税号
  
纳税编号
  
税号 (无 #)
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税标识号
  
税号标识号。
  
mokesčių id
  
mokesčių numeris
  
mokesčių identifikavimas numeris
  
## <a name="luxemburg"></a>Luxemburg

### <a name="format"></a>格式

13个不带空格或分隔符的数字
  
### <a name="pattern"></a>模式

13 个数字：
  
-  11 个数字 
    
- 两个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_luxemburg_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_luxemburg_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_luxemburg_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsluxemburgeutaxfilenumber"></a>Keywords_luxemburg_eu_tax_file_number

税号
  
纳税编号
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税标识号
  
税号标识号。
  
steuernummer
  
steuer id
  
steueridentifikationsnummer
  
## <a name="malta"></a>马耳他

### <a name="format"></a>格式

对于马耳他 nationals: 7 位数和指定模式中的一个字母
  
非马耳他语 nationals 和马耳他语实体: 9 个数字
  
### <a name="pattern"></a>模式

马耳他 nationals: 7 个数字和一个字母
  
-  七个数字  
    
- 一个字母 (不区分大小写)
    
非马耳他语 nationals 和马耳他语实体: 9 个数字
  
-  九个数字 
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>Definition

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_malta_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_malta_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_malta_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsmaltaeutaxfilenumber"></a>Keywords_malta_eu_tax_file_number

税号
  
纳税编号
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
税标识号
  
税号标识号。
  
numru tat-taxxa
  
id tat-taxxa
  
numru ta "identifikazzjoni tat-taxxa
  
## <a name="netherlands"></a>荷兰

### <a name="format"></a>格式

9个数字, 不带空格或分隔符
  
### <a name="pattern"></a>模式

九个数字 
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_netherlands_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_netherlands_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_netherlands_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsnetherlandseutaxfilenumber"></a>Keywords_netherlands_eu_tax_file_number

荷兰税标识号
  
荷兰税务标识
  
netherland 的税标识号
  
netherland 的税标识
  
税标识号
  
荷兰税号
  
荷兰纳税标识号
  
tax id

  
税号 #
  
税号
  
税号 (无 #)
  
税种
  
tin

  
锡
  
荷属安的纳税人标识号
  
netherland 的纳税人标识号
  
荷兰语 belasting identificatienummer
  
identificatienummer van belasting
  
identificatienummer belasting
  
荷兰语 belasting identificatie
  
荷兰语 belasting id nummer
  
荷兰语 belastingnummer
  
btw nummer
  
nederlandse belasting identificatie
  
## <a name="poland"></a>波兰

### <a name="format"></a>格式

不带空格或分隔符的11个数字
  
### <a name="pattern"></a>模式

11位数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_poland_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_poland_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_poland_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordspolandeutaxfilenumber"></a>Keywords_poland_eu_tax_file_number

税号
  
纳税编号
  
taxno #
  
taxnumber #
  
taxnumber
  
nip
  
nip #
  
tax id

  
税号 #
  
nip id
  
nip id #
  
税标识号
  
税号标识号。
  
vat 号码
  
vat 编号
  
vatno #
  
vat id
  
vat id #
  
器 identyfikacji podatkowej
  
polski 器 identyfikacji podatkowej
  
numeridentyfikacjipodatkowej #
  
## <a name="portugal"></a>葡萄牙

### <a name="format"></a>格式

9个不带空格或分隔符的数字
  
### <a name="pattern"></a>模式

九个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_portugal_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_portugal_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_portugal_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsportugaleutaxfilenumber"></a>Keywords_portugal_eu_tax_file_number

税号
  
纳税编号
  
taxno #
  
taxnumber #
  
taxnumber
  
\n\n
  
\n\n
  
numero 会计
  
número de identificação 会计
  
## <a name="romania"></a>罗马尼亚

### <a name="format"></a>格式

13个不带空格或分隔符的数字
  
### <a name="pattern"></a>模式

13 位数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>Definition

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_romania_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_romania_eu_tax_file_number`的关键字。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsromaniaeutaxfilenumber"></a>Keywords_romania_eu_tax_file_number

tax id

  
税务 id 号
  
税文件编号
  


tax file number
  
免税
  
税号
  
taxid #
  
taxno #
  
id-ul taxei
  
numărul de identificare fiscală
  
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

10个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

10 个数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>Definition

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_slovakia_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_slovakia_eu_tax_file_number`的关键字。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsslovakiaeutaxfilenumber"></a>Keywords_slovakia_eu_tax_file_number

tax id

  
税务 id 号
  
纳税人 id
  
tin 编号
  
斯洛伐克纳税人标识号 id
  
tin

  
税文件编号
  


tax file number
  
免税
  
税号
  
taxid #
  
taxno #
  
daňové identifikačnéčíslo
  
daňovéčíslo
  
daňovéčíslo súboru
  
## <a name="slovenia"></a>斯诺文尼亚

### <a name="format"></a>格式

8位数, 不含空格或分隔符
  
### <a name="pattern"></a>模式

八个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_slovenia_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_slovenia_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_slovenia_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordssloveniaeutaxfilenumber"></a>Keywords_slovenia_eu_tax_file_number

tax id

  
税务 id 号
  
纳税人 id
  
tin 编号
  
斯洛文尼亚纳税人标识号 id
  
tin

  
税文件编号
  


tax file number
  
免税
  
税号
  
taxid #
  
taxno #
  
identifikacijska številka davka
  
davčna številka
  
številka davčne datoteke
  
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

七个或8个数字以及指定模式中的一个或两个字母
  
### <a name="pattern"></a>模式

具有西班牙国家标识卡片的西班牙语自然人:
  
-  八个数字 
    
- 一个大写字母 (区分大小写) 
    
不包含西班牙国家的非居民 Spaniards 国家标识卡片
  
- 一个大写字母 "L" (区分大小写)
    
- 七个数字 
    
- 一个大写字母 (区分大小写) 
    
在没有西班牙国内身份证的14年年龄下的居民 Spaniards:
  
- 一个大写字母 "K" (区分大小写)
    
-  七个数字  
    
- 一个大写字母 (区分大小写)
    
带有 Foreigner 标识号的 Foreigners
  
- 一个大写的字母, 为 "X"、"Y" 或 "Z" (区分大小写) 
    
- 七个数字 
    
- 一个大写字母 (区分大小写) 
    
没有 Foreigner 标识号的 Foreigners
  
- 一个大写的字母 "M" (区分大小写) 
    
- 七个数字 
    
- 一个大写字母 (区分大小写) 
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_spain_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_spain_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_spain_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsspaineutaxfilenumber"></a>Keywords_spain_eu_tax_file_number

tax id

  
税务 id 号
  
cif id
  
cif no
  
西班牙语 cif id
  
cif
  
税文件编号
  
西班牙语 cif 号码
  


tax file number
  
西班牙语 cif no
  
免税
  
税号
  
taxid #
  
taxno #
  
cifid #
  
spanishcifid #
  
spanishcifno #
  
número de contribuyente
  
número de impuesto corporativo
  
número de identificación 会计
  
cif número
  
cifnúmero #
  
## <a name="sweden"></a>瑞典

### <a name="format"></a>格式

10个数字和指定模式中的符号
  
### <a name="pattern"></a>模式

10个数字和一个符号:
  
-  与出生日期对应的6个数字 (YYMMDD) 
    
- 加号、减号或反斜杠
    
- 在以下位置使标识号唯一的三个数字: 
    
  - 对于在1990之前发出的号码, 第七和第八位数字标识出生的县或外部人
    
  - 第九个位置中的数字表示为奇数或甚至是女的性别
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_sweden_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_sweden_eu_tax_file_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_sweden_eu_tax_file_number`找到与该模式匹配的内容。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsswedeneutaxfilenumber"></a>Keywords_sweden_eu_tax_file_number

tax id

  
税号编号
  
税务 id 号
  
tax identification

  
纳税标识号
  
纳税编号
  
税种
  
taxid #
  
税文件
  
税文件编号
  
个人 id 号
  
skatt id nummer
  
skatt identifikation
  
personnummer
  
## <a name="uk"></a>英国

### <a name="format"></a>格式

唯一的纳税人参考 (UTR):10 个数字, 无空格和分隔符
  
国家保险业号码 (NINO): 有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "英国国家保险业号码 (NINO)" 一节。
  
### <a name="pattern"></a>模式

唯一的纳税人引用 (UTR):10 个数字
  
国家保险业号码 (NINO): 有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "英国国家保险业号码 (NINO)" 一节。
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_uk_eu_tax_file_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_uk_eu_tax_file_number`的关键字。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsukeutaxfilenumber"></a>Keywords_uk_eu_tax_file_number

tax id

  
税号编号
  
税务 id 号
  
tax identification

  
纳税标识号
  
纳税编号
  
税种
  
taxid #
  
税文件
  
税文件编号
  
## <a name="see-also"></a>另请参阅

[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)


---
title: 欧盟国家身份证号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护（DLP）策略检测到欧盟国家身份证的敏感信息类型时，会对其进行查找。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: b784b7509eed899f9f03db96ee5e827b9bf70d2e
ms.sourcegitcommit: ff370e93b792204547694139ef99bc0848304570
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2019
ms.locfileid: "36852744"
---
# <a name="eu-national-identification-number"></a>欧盟国家身份证号

本主题介绍当数据丢失防护（DLP）策略检测到欧盟国家身份证的敏感信息类型时，会对其进行查找。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
  
## <a name="austria"></a>奥地利

### <a name="format"></a>Format

字母、数字和特殊字符的24个字符的组合
  
### <a name="pattern"></a>模式

24个字符：
  
-  22个字母（不区分大小写）、数字、反斜杠、正斜杠或加号 
    
- 两个字母（不区分大小写）、数字、反斜杠、正斜杠、加号或等号
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_austria_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_austria_eu_national_id_card`的关键字。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

奥地利身份证号码
  
国家/地区身份证号码
  
标识号码
  
national id
  
personalausweis republik österreich
  
## <a name="belgium"></a>比利时

有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "比利时国家数" 一节。
  
## <a name="bulgaria"></a>保加利亚语

### <a name="format"></a>Format

10个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

10个数字，无空格和分隔符
  
-  与出生日期对应的6个数字（YYMMDD） 
    
- 与出生顺序对应的两个数字
    
- 与性别对应的一位数字：男的偶数位和用于女的奇数位
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_bulgaria_national_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_bulgaria_national_number`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_bulgaria_national_number`找到与该模式匹配的内容。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_bulgaria_national_number"></a>Keywords_bulgaria_national_number

egn
  
egn#
  
保加利亚语国家/地区号码
  
国家/地区号码
  
social security number
  
nationalnumber#
  
ssn#
  
ssn
  
nationalnumber
  
bnn#
  
bnn
  
个人 id 号
  
personalidnumber#
  
единен граждански номер
  
edinen grazhdanski nomer
  
егн
  
егн#
  
## <a name="croatia"></a>克罗地亚

有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)部分中的 "克罗地亚恒等号码" 一节。
  
## <a name="cyprus"></a>塞浦路斯

### <a name="format"></a>Format

10个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

 10位数字 
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_cyprus_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_cyprus_eu_national_id_card`的关键字。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

id 卡号
  
national identification number
  
个人 id 号
  
标识卡号
  
ταυτοτητασ
  
## <a name="czech-republic"></a>捷克共和国

有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "捷克国家身份证号码" 一节。
  
## <a name="denmark"></a>丹麦

有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "丹麦个人识别码" 一节。
  
## <a name="estonia"></a>爱沙尼亚

### <a name="format"></a>Format

11个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

11 个数字：
  
- 一种数字，对应于性别和出生世纪（奇数号男，甚至是数字女; 1-2：19世纪; 3-4：20世纪; 5-6：21世纪）
    
- 六个数字，对应于出生日期（YYMMDD）
    
- 三个数字，对应于将出生在同一日期的人员组成的序列号
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_estonia_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_estonia_eu_national_id_card`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_estonia_eu_national_id_card`找到与该模式匹配的内容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

个人标识代码
  
个人标识号
  
national identification number
  
国家/地区号码
  
个人 id 号
  
personalidnumber#
  
ik
  
isikukood
  
id-kaart
  
## <a name="finland"></a>芬兰

有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰国 ID" 一节。
  
## <a name="france"></a>法国

有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国国家 ID 卡（CNI）" 一节。
  
## <a name="germany"></a>德国

有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国身份证号码" 一节。
  
## <a name="greece"></a>希腊

有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "希腊国家 ID 卡" 一节。
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>Format

11 个数字
  
### <a name="pattern"></a>模式

11 个数字：
  
-  一种与性别对应的数字（1--男，2-母，其他号码也适用于在两个公民前出生的公民的1900或公民） 
    
- 与出生日期对应的6个数字（YYMMDD）
    
- 与序列号对应的三个数字
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_hungary_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_hungary_eu_national_id_card`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_hungary_eu_national_id_card`找到与该模式匹配的内容。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

个人标识号
  
identification number
  
个人 id 号
  
személyazonosító igazolvány
  
## <a name="ireland"></a>爱尔兰

### <a name="format"></a>Format

指定模式中的字母、数字和空格的九个字符的组合
  
### <a name="pattern"></a>模式

指定模式中的字母、数字和空格的九个字符的组合
  
从01年1月2013到现在：
  
-  七个数字  
    
- 一个校验位
    
- 一个空格或大写的字母 "W" （区分大小写）
    
在01月1日之前1月2013：
  
-  七个数字  
    
- 一个校验位
    
- 一个空格或大写字母（区分大小写）
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数找到与该模式匹配的内容。
    
- 找到了中的关键字。
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数找到与该模式匹配的内容。
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

个人公开服务号码
  
pps no
  
收入和社会保险电话号码
  
rsi no
  
个人标识号
  
identification number
  
个人 id 号
  
uimhir phearsanta seirbhíse poiblí
  
uimh. psp
  
## <a name="italy"></a>意大利

### <a name="format"></a>Format

在指定模式中，由16个字符组成的字母和数字的组合
  
### <a name="pattern"></a>模式

字母和数字的16个字符的组合：
  
- 与系列名称中的前三个辅音对应的三个字母
    
- 与名字中的第一个、第三个和第四个辅音对应的三个字母
    
- 与出生年份的最后一个数字对应的两个数字
    
- 一个与出生月份的字母对应的字母–字母按字母顺序使用，但仅使用字母 A 到 E、H、L、M、P、R 和 T （因此，一月为 A，10月为 R）
    
- 与出生月份的某一天对应的两个数字，为了区分 genders，40已添加到女性的出生日。
    
- 与专用于 municipality 的区域代码相对应的四个数字（国家/地区内的国家/地区代码适用于外国国家）
    
- 一个奇偶校验数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_italy_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_italy_eu_national_id_card`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_italy_eu_national_id_card`找到与该模式匹配的内容。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

个人代码
  
个人代码编号
  
个人证书号码
  
会计代码
  
personalcodeno#
  
个人 id 号
  
个人 id 代码
  
codice personale
  
numero certificato personale
  
numero personale
  
numero id personale
  
codice id personale
  
codice fiscale
  
## <a name="latvia"></a>拉脱维亚

### <a name="format"></a>Format

11位数字和指定格式的连字符
  
### <a name="pattern"></a>模式

11个数字和一个连字符：
  
-  与出生日期对应的6个数字（DDMMYY） 
    
- 一个连字符 
    
- 一个数字，对应于出生世纪（"0" 表示19世纪，"1" 表示20世纪，"2" 表示21世纪）
    
- 四个数字，随机生成
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_latvia_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_latvia_eu_national_id_card`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_latvia_eu_national_id_card`找到与该模式匹配的内容。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

个人代码
  
个人代码编号
  
个人证书号码
  
personalcodeno#
  
个人 id 号
  
个人 id 代码
  
角色 kods
  
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>Format

11个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

11个数字，不含空格和分隔符：
  
- 一个与人的性别和出生世纪对应的数字
    
-  与出生日期对应的6个数字（YYMMDD） 
    
- 与出生日期的序列号对应的三个数字
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_lithuania_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_lithuania_eu_national_id_card`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_lithuania_eu_national_id_card`找到与该模式匹配的内容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

个人数字代码
  
唯一标识号
  
公民服务号码
  
唯一标识号
  
uniqueidentityno#
  
个人代码。
  
asmeninis skaitmeninis kodas
  
unikalus identifikavimo numeris
  
piliečio paslaugos numeris
  
unikalus identifikavimo kodas
  
asmens kodas.
  
## <a name="luxemburg"></a>Luxemburg

### <a name="format"></a>Format

11个数字，无空格和分隔符
  
### <a name="pattern"></a>模式

11 个数字
  
- 一个与人的性别和出生世纪对应的数字
    
-  与出生日期对应的6个数字（YYMMDD） 
    
- 与出生日期的序列号对应的三个数字
    
- 一个校验位
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_luxemburg_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_luxemburg_eu_national_id_card`的关键字。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

个人 id
  
个人 id 号
  
personalidno#
  
唯一 id 号
  
personalidnumber#
  
唯一 id 键
  
个人 id 代码
  
uniqueidkey#
  
单个代码
  
个人 id
  
eindeutige id-nummer
  
eindeutige id
  
id personnelle
  
numéro d'identification 人员
  
idpersonnelle#
  
persönliche identifikationsnummer
  
eindeutigeid#
  
## <a name="malta"></a>马耳他

### <a name="format"></a>Format

七位数字后跟一个字母
  
### <a name="pattern"></a>模式

七位数字后跟一个字母：
  
-  七个数字  
    
- 一个大写字母（区分大小写）
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_malta_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_malta_eu_national_id_card`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_malta_eu_national_id_card`找到与该模式匹配的内容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

个人数字代码
  
唯一标识号
  
公民服务号码
  
唯一标识号
  
uniqueidentityno#
  
kodiċi numerali personali
  
numru ta "identifikazzjoni uniku
  
numru tas-servizz taċ-ċittadin
  
numru ta "identità uniku
  
## <a name="netherlands"></a>荷兰

### <a name="format"></a>Format

9个数字，不带空格或分隔符
  
### <a name="pattern"></a>模式

九个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_netherlands_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中的关键字。
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_netherlands_eu_national_id_card`找到与该模式匹配的内容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

个人数字代码
  
唯一标识号
  
公民服务号码
  
唯一标识号
  
uniqueidentityno#
  
bsn
  
bsn#
  
persoonlijke numerieke 代码
  
uniek identificatienummer
  
burgerservicenummer
  
uniek identiteitsnummer
  
## <a name="poland"></a>波兰

有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰国家 ID （PESEL）" 一节。
  
## <a name="portugal"></a>葡萄牙

有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "葡萄牙公民卡片号" 部分。
  
## <a name="romania"></a>罗马尼亚

### <a name="format"></a>Format

13位数，不含空格和分隔符
  
### <a name="pattern"></a>模式

13 位数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_romania_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_romania_eu_national_id_card`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_romania_eu_national_id_card`找到与该模式匹配的内容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

个人数字代码
  
唯一标识号
  
cnp
  
cnp#
  
针
  
针#
  
保险号
  
insurancenumber#
  
唯一标识号
  
uniqueidentityno#
  
付款的个人数字
  
货到 identificare 个人
  
货到付款 unic identificare
  
număr 个人 unic
  
număr identitate
  
număr identificare 个人
  
număridentitate#
  
codnumericpersonal#
  
numărpersonalunic#
  
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>Format

10个数字，包含一个反斜杠
  
### <a name="pattern"></a>模式

10个数字，包含一个反斜杠：
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_slovakia_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_slovakia_eu_national_id_card`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_slovakia_eu_national_id_card`找到与该模式匹配的内容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

出生号码
  
national identification number
  
个人标识号
  
social security number
  
nationalnumber#
  
ssn#
  
ssn
  
国家/地区号码
  
个人 id 号
  
personalidnumber#
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="slovenia"></a>斯洛文尼亚

### <a name="format"></a>Format

13位数，不含空格或分隔符
  
### <a name="pattern"></a>模式

指定模式中的13个数字：
  
-  与出生日期（DDMMLLL）对应的七位数，其中 "LLL" 对应于出生年份的后三个数字 
    
- 与出生区域对应的两个数字
    
- 三个数字，对应于出生在同一天的人的性别和序列号组合（000-499 的男和500-999 的女）
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_slovenia_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_slovenia_eu_national_id_card`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_slovenia_eu_national_id_card`找到与该模式匹配的内容。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

个人数字代码
  
唯一标识号
  
唯一注册号码
  
唯一标识号
  
uniqueidentityno#
  
唯一的主公民号码
  
edinstvena identifikacijska številka
  
uniqueidentityno#
  
edinstvena številka glavnega državljana
  
emšo
  
## <a name="spain"></a>西班牙

### <a name="format"></a>Format

8位数，后跟一个字符
  
### <a name="pattern"></a>模式

8位数，后跟一个字符
  
- 八个数字
    
- 一个数字或字母（不区分大小写）
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_spain_eu_national_id_card`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_spain_eu_national_id_card"`的关键字。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

dni
  
national identification number
  
国家/地区身份证号码
  
保险号
  
个人标识号
  
国家标识
  
个人标识编号
  
唯一标识号
  
nationalidno#
  
uniqueid#
  
dni#
  
nationalid#
  
nie#
  
nie
  
nienúmero#
  
nie número
  
documento nacional de identidad
  
identidad único
  
número nacional identidad
  
dni número
  
dninúmero#
  
identidadúnico#
  
## <a name="sweden"></a>瑞典

有关详细信息，请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典国家 ID" 一节。
  
## <a name="see-also"></a>另请参阅

[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)


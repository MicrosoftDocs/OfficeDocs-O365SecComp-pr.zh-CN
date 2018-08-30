---
title: 欧盟 National 标识号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 2ea971bf-9434-4b61-b825-2bbd28ae6064
description: 本主题演示数据丢失防护 (DLP) 策略检测到的欧盟国家/地区标识号敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
ms.openlocfilehash: 29d2126b937ff46039284a74eb2a84f2ebbacb41
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525345"
---
# <a name="eu-national-identification-number"></a>欧盟 National 标识号

本主题演示数据丢失防护 (DLP) 策略检测到的欧盟国家/地区标识号敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
  
## <a name="austria"></a>奥地利

### <a name="format"></a>格式

字母、 数字和特殊字符的 24 个字符组合
  
### <a name="pattern"></a>模式

24 个字符：
  
-  22 （不区分大小写） 的字母、 数字、 反斜杠、 正斜杠或加号 
    
- （不区分大小写） 的两个字母、 数字、 反斜杠、 正斜杠、 加号或等号
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_austria_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_austria_eu_national_id_card`找到。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsaustriaeunationalidcard"></a>Keywords_austria_eu_national_id_card

奥地利标识号
  
国家/地区的 identity 号码
  
标识号
  

national id
  
personalausweis republik österreich
  
## <a name="belgium"></a>比利时

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"比利时国家/地区号码"。
  
## <a name="bulgaria"></a>保加利亚

### <a name="format"></a>格式

没有空格和分隔符的 10 位数字
  
### <a name="pattern"></a>模式

没有空格和分隔符的 10 位数字
  
-  对应于出生日期 (YYMMDD) 的 6 个数字 
    
- 出生顺序对应的两位数
    
- 对应于性别的一位数： 偶数位男性和女性为奇数数字
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_bulgaria_national_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_bulgaria_national_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_bulgaria_national_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsbulgarianationalnumber"></a>Keywords_bulgaria_national_number

egn
  
egn #
  
保加利亚语的国家/地区号码
  
国家/地区号码
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
nationalnumber
  
bnn #
  
bnn
  
个人标识号
  
personalidnumber #
  
ЕДИНЕН ГРАЖДАНСКИ НОМЕР
  
edinen grazhdanski nomer
  
ЕГН
  
ЕГН #
  
## <a name="croatia"></a>克罗地亚

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"克罗地亚标识号"。
  
## <a name="cyprus"></a>塞浦路斯

### <a name="format"></a>格式

没有空格和分隔符的 10 位数字
  
### <a name="pattern"></a>模式

 10 位数字 
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_cyprus_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_cyprus_eu_national_id_card`找到。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordscypruseunationalidcard"></a>Keywords_cyprus_eu_national_id_card

身份证号码
  
国家/地区标识号
  
个人标识号
  
身份证号码
  
ΤΑΥΤΟΤΗΤΑΣ
  
## <a name="czech-republic"></a>捷克共和国

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"捷克语国家/地区的 Identity 号码"。
  
## <a name="denmark"></a>丹麦

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"丹麦个人识别号"。
  
## <a name="estonia"></a>爱沙尼亚

### <a name="format"></a>格式

没有空格和分隔符 11 位数字
  
### <a name="pattern"></a>模式

11 个数字：
  
- 对应于性别和出生的 century 的一位数 (奇数号码男性、 偶数女; 1-2: 19 century; 3-4: 20 世纪; 5-6: 21 世纪)
    
- 对应于 (YYMMDD) 出生日期的 6 个数字
    
- 对应于分隔人员在相同日期出生日期序列号的三个数字
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_estonia_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_estonia_eu_national_id_card`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_estonia_eu_national_id_card`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsestoniaeunationalidcard"></a>Keywords_estonia_eu_national_id_card

个人识别码代码
  
个人识别号
  
国家/地区标识号
  
国家/地区号码
  
个人标识号
  
personalidnumber #
  
ik
  
isikukood
  
id kaart
  
## <a name="finland"></a>芬兰

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"芬兰国家/地区 ID"。
  
## <a name="france"></a>法国

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"法国国家 ID 卡 (CNI)"。
  
## <a name="germany"></a>德国

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"德国身份证编号"。
  
## <a name="greece"></a>希腊

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"希腊国家 ID 卡"。
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

11 个数字
  
### <a name="pattern"></a>模式

11 个数字：
  
-  对应于性别 （1-插头 2 女性、 其他号码也是可行市民出生日期之前 1900年或与双公民市民的） 的一位数 
    
- 对应于出生日期 (YYMMDD) 的 6 个数字
    
- 三个转成序列号对应的数字
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_hungary_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_hungary_eu_national_id_card`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_hungary_eu_national_id_card`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordshungaryeunationalidcard"></a>Keywords_hungary_eu_national_id_card

个人识别号
  
identification number

  
个人标识号
  
személyazonosító igazolvány
  
## <a name="ireland"></a>Ireland

### <a name="format"></a>格式

字母、 数字和空间以指定的模式的九个字符组合
  
### <a name="pattern"></a>模式

字母、 数字和空间以指定的模式的九个字符组合
  
从到现在为止的 01 2013 年 1 月：
  
-  七个数字  
    
- 一个检查数字
    
- 一个空格或大写字母"W"（区分大小写）
    
之前 01 2013 年 1 月：
  
-  七个数字  
    
- 一个检查数字
    
- 一个空格或大写字母 （区分大小写）
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数查找与模式匹配的内容。
    
- 从关键字是找到。
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数查找与模式匹配的内容。
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsirelandeunationalidcard"></a>Keywords_ireland_eu_national_id_card

个人公共服务号码
  
pps 没有
  
收入和社会保险号码
  
rsi 没有
  
个人识别号
  
identification number

  
个人标识号
  
uimhir phearsanta seirbhíse poiblí
  
uimh。psp
  
## <a name="italy"></a>意大利

### <a name="format"></a>格式

字母和指定的模式中数字位数的 16 个字符组合
  
### <a name="pattern"></a>模式

16 个字符字母和数字的组合：
  
- 对应于系列名称中的前三个辅音的三个字母
    
- 对应于第一、 第三个和第四个的三个字母辅音中第一个名称
    
- 两位数的最后一个对应出生年份的数字
    
- 举行的出生对应于的字母的一个字母 — 字母使用以字母顺序列出，但仅字母 A 到 E、 H、 L、 M、 P、 R T 到使用 （即年 1 月是 A 和年 10 月为 R）
    
- 对应于的出生日期的两位数 — 为了区分 gender，40 添加到女性出生日期
    
- 对应于特定于此人出生上级主管机构区号的四位数字 （国家/地区范围代码使用外的国家/地区）
    
- 奇偶校验的一位数
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_italy_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_italy_eu_national_id_card`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_italy_eu_national_id_card`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsitalyeunationalidcard"></a>Keywords_italy_eu_national_id_card

个人代码
  
个人代码编号
  
个人证书号
  
会计代码
  
personalcodeno #
  
个人标识号
  
个人 id 代码
  
codice personale
  
numero certificato personale
  
numero personale
  
numero id personale
  
codice id personale
  
codice fiscale
  
## <a name="italy"></a>意大利

### <a name="format"></a>格式

11 位数字并且以指定格式连字符
  
### <a name="pattern"></a>模式

11 位数字和连字符：
  
-  对应于出生日期月日的 6 个数字 
    
- 一个连字符 
    
- 对应于出生 （19 century"0"、"1"的 20 世纪和"2"的 21 世纪） century 的一位数
    
- 四位数字，随机生成
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_latvia_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_latvia_eu_national_id_card`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_latvia_eu_national_id_card`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordslatviaeunationalidcard"></a>Keywords_latvia_eu_national_id_card

个人代码
  
个人代码编号
  
个人证书号
  
personalcodeno #
  
个人标识号
  
个人 id 代码
  
角色 kods
  
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

没有空格和分隔符 11 位数字
  
### <a name="pattern"></a>模式

没有空格和分隔符 11 位数字：
  
- 对应于此人的性别和出生的 century 的一位数
    
-  对应于出生日期 (YYMMDD) 的 6 个数字 
    
- 出生日期序列号对应的三个数字
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_lithuania_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_lithuania_eu_national_id_card`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_lithuania_eu_national_id_card`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordslithuaniaeunationalidcard"></a>Keywords_lithuania_eu_national_id_card

个人数字代码
  
唯一标识号
  
公民服务号码
  
唯一标识号码
  
uniqueidentityno #
  
个人代码。
  
asmeninis skaitmeninis kodas
  
unikalus identifikavimo numeris
  
piliečio paslaugos numeris
  
unikalus identifikavimo kodas
  
asmens kodas。
  
## <a name="luxemburg"></a>卢森堡

### <a name="format"></a>格式

没有空格和分隔符 11 位数字
  
### <a name="pattern"></a>模式

11 个数字
  
- 对应于此人的性别和出生的 century 的一位数
    
-  对应于出生日期 (YYMMDD) 的 6 个数字 
    
- 出生日期序列号对应的三个数字
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_luxemburg_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_luxemburg_eu_national_id_card`找到。 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsluxemburgeunationalidcard"></a>Keywords_luxemburg_eu_national_id_card

个人 id
  
个人标识号
  
personalidno #
  
唯一 id 号
  
personalidnumber #
  
唯一 id 键
  
个人 id 代码
  
uniqueidkey #
  
单个代码
  
单个 id
  
eindeutige id nummer
  
eindeutige id
  
id personnelle
  
numéro d'identification 人员
  
idpersonnelle #
  
persönliche identifikationsnummer
  
eindeutigeid #
  
## <a name="malta"></a>马耳他

### <a name="format"></a>格式

七位数字后跟一个字母
  
### <a name="pattern"></a>模式

七位数字后跟一个字母：
  
-  七个数字  
    
- 一个大写字母 （区分大小写）
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_malta_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_malta_eu_national_id_card`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_malta_eu_national_id_card`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsmaltaeunationalidcard"></a>Keywords_malta_eu_national_id_card

个人数字代码
  
唯一标识号
  
公民服务号码
  
唯一标识号码
  
uniqueidentityno #
  
kodiċi numerali personali
  
numru 选项卡 identifikazzjoni uniku
  
numru tas servizz taċ ċittadin
  
numru 选项卡 identità uniku
  
## <a name="netherlands"></a>荷兰

### <a name="format"></a>格式

不含空格或分隔符的九个数字
  
### <a name="pattern"></a>模式

九个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_netherlands_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字是找到。
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_netherlands_eu_national_id_card`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsnetherlandseunationalidcard"></a>Keywords_netherlands_eu_national_id_card

个人数字代码
  
唯一标识号
  
公民服务号码
  
唯一标识号码
  
uniqueidentityno #
  
bsn
  
bsn #
  
persoonlijke numerieke 代码
  
uniek identificatienummer
  
burgerservicenummer
  
uniek identiteitsnummer
  
## <a name="poland"></a>波兰

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"波兰国家/地区 ID (PESEL)"。
  
## <a name="portugal"></a>葡萄牙

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"葡萄牙公民卡号"。
  
## <a name="romania"></a>罗马尼亚

### <a name="format"></a>格式

13 没有空格和分隔符的数字
  
### <a name="pattern"></a>模式

13 位数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_romania_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_romania_eu_national_id_card`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_romania_eu_national_id_card`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsromaniaeunationalidcard"></a>Keywords_romania_eu_national_id_card

个人数字代码
  
唯一标识号
  
cnp
  
cnp #
  
固定
  
pin #
  
保险号
  
insurancenumber #
  
唯一标识号码
  
uniqueidentityno #
  
cod 数值个人
  
货 identificare 个人到付款
  
cod unic identificare
  
număr 个人 unic
  
număr identitate
  
număr identificare 个人
  
număridentitate #
  
codnumericpersonal #
  
numărpersonalunic #
  
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

包含一个反斜杠 10 位数字
  
### <a name="pattern"></a>模式

包含一个反斜杠 10 位数字：
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_slovakia_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_slovakia_eu_national_id_card`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_slovakia_eu_national_id_card`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsslovakiaeunationalidcard"></a>Keywords_slovakia_eu_national_id_card

出生号码
  
国家/地区标识号
  
个人识别号
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
国家/地区号码
  
个人标识号
  
personalidnumber #
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="slovenia"></a>斯诺文尼亚

### <a name="format"></a>格式

不含空格或分隔符 13 数字
  
### <a name="pattern"></a>模式

在指定的模式的 13 数字：
  
-  对应于出生日期 (DDMMLLL)，其中，"LLL"对应于上次出生一年中的三个数字的七个数字 
    
- 对应于出生的区域的两位数
    
- 人员在同一天 (000-499 插孔) 和女性为 500-999 出生日期对应的性别和序列号组合的三个数字
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_slovenia_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_slovenia_eu_national_id_card`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_slovenia_eu_national_id_card`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordssloveniaeunationalidcard"></a>Keywords_slovenia_eu_national_id_card

个人数字代码
  
唯一标识号
  
注册的唯一编号
  
唯一标识号码
  
uniqueidentityno #
  
唯一的主公民号码
  
edinstvena identifikacijska številka
  
uniqueidentityno #
  
edinstvena številka glavnega državljana
  
emšo
  
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

一个字符后跟七位数字
  
### <a name="pattern"></a>模式

一个字符后跟七位数字
  
- 七个数字 
    
- 一个数字或字母 （不区分大小写）
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_spain_eu_national_id_card`查找与模式匹配的内容。 
    
- 从关键字`Keywords_spain_eu_national_id_card"`找到。 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsspaineunationalidcard"></a>Keywords_spain_eu_national_id_card

dni
  
国家/地区标识号
  
国家/地区的 identity 号码
  
保险号
  
个人识别号
  
国家/地区的标识
  
个人标识无
  
唯一标识号码
  
nationalidno #
  
uniqueid #
  
dni #
  
nationalid #
  
nie #
  
nie
  
nienúmero #
  
nie número
  
documento nacional de identidad
  
identidad único
  
número nacional identidad
  
dni número
  
dninúmero #
  
identidadúnico #
  
## <a name="sweden"></a>瑞典

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"瑞典国家/地区 ID"。
  
## <a name="see-also"></a>另请参阅

[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)


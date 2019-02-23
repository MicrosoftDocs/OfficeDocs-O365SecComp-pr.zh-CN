---
title: 欧盟社会安全号码或等效 ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟社会保险号码或等效 ID 敏感信息类型时, 将会查找什么。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: abcefb6930e9c02d2f32d84b65accfecf1e20d95
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216522"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>欧盟社会安全号码或等效 ID

本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟社会保险号码 (SSN) 或等效 ID 敏感信息类型时, 会查找什么内容。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
  
## <a name="austria"></a>奥地利

### <a name="format"></a>格式

以指定格式表示的10个数字
  
### <a name="pattern"></a>模式

10 个数字：
  
-  与序列号对应的三个数字 
    
- 一个校验位
    
- 与出生日期对应的6个数字 (DDMMYY)
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_austria_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_austria_eu_ssn_or_equivalent`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_austria_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsaustriaeussnorequivalent"></a>Keywords_austria_eu_ssn_or_equivalent

社会保障号
  
social security number

  

social security code
  
保险号
  
奥地利 ssn
  
ssn
  
ssn
  
保险费代码
  
保险代码 #
  
socialsecurityno #
  
sozialversicherungsnummer
  
soziale sicherheit kein
  
versicherungsnummer
  
## <a name="belgium"></a>比利时

### <a name="format"></a>格式

11位数, 不含空格或分隔符
  
### <a name="pattern"></a>模式

11 个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_belgium_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_belgium_eu_ssn_or_equivalent`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_belgium_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsbelgiumeussnorequivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

比利时国家/地区号码
  
国家/地区号码
  
social security number

  
nationalnumber #
  
ssn
  
ssn
  
nationalnumber
  
bnn #
  
bnn
  
个人 id 号
  
personalidnumber #
  
numéro 国家
  
numéro de sécurité

  
numéro d'assuré
  
identifiant 国家
  
identifiantnational #
  
numéronational #
  
## <a name="croatia"></a>克罗地亚

### <a name="format"></a>格式

11个数字, 无空格和分隔符
  
### <a name="pattern"></a>模式

 11 个数字： 
  
-  10位数字 
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_croatia_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_croatia_eu_ssn_or_equivalent`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_croatia_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordscroatiaeussnorequivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

个人标识号
  
主公民号码
  
国家/地区标识号
  
social security number

  
nationalnumber #
  
ssn
  
ssn
  
nationalnumber
  
bnn #
  
bnn
  
个人 id 号
  
personalidnumber #
  
oib
  
osobni identifikacijski broj
  
## <a name="czech-republic"></a>捷克共和国

### <a name="format"></a>格式

指定模式中的10个数字和一个反斜杠
  
### <a name="pattern"></a>模式

10个数字和一个反斜杠:
  
- 与出生日期对应的6个数字 (YYMMDD): 
    
- 反斜杠
    
- 与一个序列号相对应的三个数字, 用于分隔出生于同一日期的人员
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_czech_republic_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_czech_republic_eu_ssn_or_equivalent`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_czech_republic_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsczechrepubliceussnorequivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

出生号码
  
国家/地区标识号
  
个人标识号
  
social security number

  
nationalnumber #
  
ssn
  
ssn
  
国家/地区号码
  
个人 id 号
  
personalidnumber #
  
rč
  
rodnéčíslo
  
rodne cislo
  
## <a name="denmark"></a>丹麦

### <a name="format"></a>格式

指定模式中的10个数字和一个连字符
  
### <a name="pattern"></a>模式

10个数字和一个连字符:
  
- 与出生日期对应的6个数字 (DDMMYY) 
    
- 一个连字符 
    
- 与序列号对应的四个数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_denmark_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_denmark_eu_ssn_or_equivalent`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_denmark_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsdenmarkeussnorequivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

个人标识号
  
国家/地区标识号
  
social security number

  
nationalnumber #
  
ssn
  
ssn
  
国家/地区号码
  
个人 id 号
  
personalidnumber #
  
cpr-nummer
  
personnummer
  
## <a name="finland"></a>芬兰

### <a name="format"></a>格式

指定格式的11个字符的组合
  
### <a name="pattern"></a>模式

指定格式的11个字符的组合:
  
-  六位数字 
    
- 以下任一实例:
    
  - 加号符号
    
  - 负号
    
  - 字母 "A" (不区分大小写)
    
- 三位数字
    
- 一个字母或一个数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_finland_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_finland_eu_ssn_or_equivalent`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_finland_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsfinlandeussnorequivalent"></a>Keywords_finland_eu_ssn_or_equivalent

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
  
hetu
  
## <a name="france"></a>法国

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "华北社会安全号码 (INSEE)" 一节。
  
## <a name="germany"></a>德国

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国身份证号码" 一节。
  
## <a name="greece"></a>希腊

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "希腊国家 ID 卡" 一节。
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

9个数字, 不带空格和分隔符
  
### <a name="pattern"></a>模式

九个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_hungary_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_hungary_eu_ssn_or_equivalent`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_hungary_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordshungaryeussnorequivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

匈牙利语社会安全号码
  
social security number

  
socialsecuritynumber #
  
hssn #
  
socialsecuritynno
  
hssn
  
taj
  
taj #
  
ssn
  
ssn
  
社会保障号
  
áfa
  
közösségi adószám
  
általános forgalmi adó szám
  
hozzáadottérték adó
  
áfa szám
  
magyar áfa szám
  
## <a name="portugal"></a>葡萄牙

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "葡萄牙公民卡片号" 部分。
  
## <a name="spain"></a>西班牙

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "西班牙社会安全号码 (SSN)" 一节。
  
## <a name="sweden"></a>瑞典

### <a name="format"></a>格式

12个数字, 不含空格和分隔符
  
### <a name="pattern"></a>模式

12 个数字：
  
-  与出生日期对应的8位数字 (YYYYMMDD) 
    
- 与序列号对应的三个数字, 其中: 
    
  - 序列号中的最后一个数字指示在为 "男" 分配一个奇数号码时的性别, 以及一个 "女" 的偶数号码。
    
  - 最多 1990, 将序列号 corresponded 分配给在其中, 号码持有者出生或 (如果在1947之前出生) 的县 (根据纳税记录, 在年1月1日, 使用特殊代码 (通常为第七个数字) 的特殊代码 (通常为9号)immigrants 
    
- 一个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_sweden_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_sweden_eu_ssn_or_equivalent`的关键字。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_sweden_eu_ssn_or_equivalent`找到与该模式匹配的内容。 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>关键字

#### <a name="keywordsswedeneussnorequivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

个人 id 号
  
identification number

  
个人 id 否
  
identity no
  
标识否
  
个人标识编号
  
personnummer id
  
personligt id-nummer
  
unikt id-nummer
  
personnummer
  
identifikationsnumret
  
personnummer #
  
identifikationsnumret #
  
## <a name="see-also"></a>另请参阅

[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)


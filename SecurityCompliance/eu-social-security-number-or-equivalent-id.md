---
title: 欧盟社会保险号或等效 ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: 本主题演示数据丢失防护 (DLP) 策略检测到的欧盟社会保险号或等效 ID 敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
ms.openlocfilehash: 6f1027dcfb648ed937b8180d74d4bc6348dab650
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525285"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>欧盟社会保险号或等效 ID

本主题演示数据丢失防护 (DLP) 策略检测到的欧盟社会保险号码 (SSN) 或等效 ID 敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
  
## <a name="austria"></a>奥地利

### <a name="format"></a>格式

10 位数字以指定格式
  
### <a name="pattern"></a>模式

10 个数字：
  
-  三个转成序列号对应的数字 
    
- 一个检查数字
    
- 对应于出生日期月日的 6 个数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_austria_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
- 从关键字`Keywords_austria_eu_ssn_or_equivalent`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_austria_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsaustriaeussnorequivalent"></a>Keywords_austria_eu_ssn_or_equivalent

社会保障没有
  
social security number

  

social security code
  
保险号
  
奥地利 ssn
  
ssn #
  
ssn
  
保险代码
  
保险代码 #
  
socialsecurityno #
  
sozialversicherungsnummer
  
soziale sicherheit kein
  
versicherungsnummer
  
## <a name="belgium"></a>比利时

### <a name="format"></a>格式

不含空格或分隔符 11 位数字
  
### <a name="pattern"></a>模式

11 个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_belgium_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
- 从关键字`Keywords_belgium_eu_ssn_or_equivalent`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_belgium_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsbelgiumeussnorequivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

比利时国家/地区号码
  
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
  
numéro 国家/地区
  
numéro de sécurité

  
numéro d'assuré
  
identifiant 国家/地区
  
identifiantnational #
  
numéronational #
  
## <a name="croatia"></a>克罗地亚

### <a name="format"></a>格式

没有空格和分隔符 11 位数字
  
### <a name="pattern"></a>模式

 11 个数字： 
  
-  10 位数字 
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_croatia_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
- 从关键字`Keywords_croatia_eu_ssn_or_equivalent`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_croatia_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordscroatiaeussnorequivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

个人识别号
  
主公民号码
  
国家/地区标识号
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
nationalnumber
  
bnn #
  
bnn
  
个人标识号
  
personalidnumber #
  
oib
  
osobni identifikacijski broj
  
## <a name="czech-republic"></a>捷克共和国

### <a name="format"></a>格式

10 位数字和反斜杠中指定的模式
  
### <a name="pattern"></a>模式

10 位数字和反斜杠：
  
- 对应于出生日期 (YYMMDD) 的 6 个数字： 
    
- 反斜杠
    
- 与用于分隔人员在相同日期出生日期序列号对应的三个数字
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_czech_republic_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
- 从关键字`Keywords_czech_republic_eu_ssn_or_equivalent`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_czech_republic_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsczechrepubliceussnorequivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

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
  
## <a name="denmark"></a>丹麦

### <a name="format"></a>格式

10 位数字和连字符中指定的模式
  
### <a name="pattern"></a>模式

10 位数字和连字符：
  
- 对应于出生日期月日的 6 个数字 
    
- 一个连字符 
    
- 四位数字对应序列号
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_denmark_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
- 从关键字`Keywords_denmark_eu_ssn_or_equivalent`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_denmark_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsdenmarkeussnorequivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

个人识别号
  
国家/地区标识号
  
social security number

  
nationalnumber #
  
ssn #
  
ssn
  
国家/地区号码
  
个人标识号
  
personalidnumber #
  
cpr nummer
  
personnummer
  
## <a name="finland"></a>芬兰

### <a name="format"></a>格式

以指定格式 11 个字符组合
  
### <a name="pattern"></a>模式

以指定格式 11 个字符组合：
  
-  六位数字 
    
- 一个实例下列选项之一：
    
  - Plus 符号
    
  - 减号
    
  - 字母"A"（不区分大小写）
    
- 三位数字
    
- 一个字母或一位数
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_finland_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
- 从关键字`Keywords_finland_eu_ssn_or_equivalent`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_finland_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsfinlandeussnorequivalent"></a>Keywords_finland_eu_ssn_or_equivalent

identification number

  
个人 id
  
标识号
  
芬兰国家/地区 id 号
  
personalidnumber #
  
国家/地区标识号
  
id 号
  
国家/地区 id 没有。
  
国家/地区 id 号
  
id 没有
  
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

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"法国社会保险号 (INSEE)"。
  
## <a name="germany"></a>德国

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"德国身份证编号"。
  
## <a name="greece"></a>希腊

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"希腊国家 ID 卡"。
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

没有空格和分隔符的九个数字
  
### <a name="pattern"></a>模式

九个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_hungary_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
- 从关键字`Keywords_hungary_eu_ssn_or_equivalent`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_hungary_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordshungaryeussnorequivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

匈牙利语社会保险号码
  
social security number

  
socialsecuritynumber #
  
hssn #
  
socialsecuritynno
  
hssn
  
泰姬陵
  
泰姬陵 #
  
ssn
  
ssn #
  
社会保障没有
  
áfa
  
közösségi adószám
  
általános forgalmi adó szám
  
hozzáadottérték adó
  
áfa szám
  
magyar áfa szám
  
## <a name="portugal"></a>葡萄牙

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"葡萄牙公民卡号"。
  
## <a name="spain"></a>西班牙

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"西班牙社会保险号码 (SSN)"。
  
## <a name="sweden"></a>瑞典

### <a name="format"></a>格式

没有空格和分隔符的 12 个数字
  
### <a name="pattern"></a>模式

12 个数字：
  
-  八个数字对应于出生日期 （年月日） 
    
- 三个转成序列号对应的数字位置： 
    
  - 序列号中的最后一位指示通过分配的奇数的男性和女性为偶数的性别
    
  - 过去 1990，分配的序列号通过信到县或其中出生号码的持有者 （如果出生日期之前 1947年） 其中他/她具有已生活，根据税费记录 1947，年 1 月 1，与特殊代码 (通常为 7 位数字 9) 的移民 
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_sweden_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
- 从关键字`Keywords_sweden_eu_ssn_or_equivalent`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_sweden_eu_ssn_or_equivalent`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsswedeneussnorequivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

个人标识号
  
identification number

  
个人 id 没有
  
标识无
  
标识无
  
个人标识号没有
  
personnummer id
  
personligt id nummer
  
unikt id nummer
  
personnummer
  
identifikationsnumret
  
personnummer #
  
identifikationsnumret #
  
## <a name="see-also"></a>另请参阅

[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)


---
title: 欧盟纳税标识号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: 本主题演示数据丢失防护 (DLP) 策略检测到的欧盟纳税标识号敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
ms.openlocfilehash: 5192496b393d15fd6d063e09c9bfe1cb3dd7e2dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525378"
---
# <a name="eu-tax-identification-number"></a>欧盟纳税标识号

本主题演示数据丢失防护 (DLP) 策略检测到的欧盟税费识别号码 （会议） 敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
  
## <a name="austria"></a>奥地利

### <a name="format"></a>格式

可选连字符与正斜杠九个数字
  
### <a name="pattern"></a>模式

可选连字符与正斜杠的九个数字：
  
-  两位数字 
    
- 一个连字符（可选）
    
- 三位数字
    
- 正斜杠（可选）
    
- 四位数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_austria_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_austria_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_austria_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsaustriaeutaxfilenumber"></a>Keywords_austria_eu_tax_file_number

税号
  
号码
  
税费登记号码
  
tax id

  
st.nr。
  
steuernummer
  
## <a name="belgium"></a>比利时

### <a name="format"></a>格式

没有空格和分隔符 11 位数字
  
### <a name="pattern"></a>模式

11 个数字：
  
- 两位数字
    
- "0"或者"1"
    
- 一位数字
    
- "0"或"1"或"2"或者"3" 
    
- 六个数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_belgium_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_belgium_eu_tax_file_number`找到。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsbelgiumeutaxfilenumber"></a>Keywords_belgium_eu_tax_file_number

税号
  
国家/地区的注册号码
  
税费登记号码
  
tax id

  
n 如果
  
n 如果 #
  
numéro de registre 国家/地区
  
numéro d'identification fiscale
  
## <a name="bulgaria"></a>保加利亚

### <a name="format"></a>格式

没有空格和分隔符的 10 位数字
  
### <a name="pattern"></a>模式

10 个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_bulgaria_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_bulgaria_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_bulgaria_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsbulgariaeutaxfilenumber"></a>Keywords_bulgaria_eu_tax_file_number

bucn
  
统一民事号码
  
bucn #
  
uniformcivilnumber #
  
统一民事 id
  
统一民事否
  
egn
  
保加利亚语统一民事号码
  
uniformcivilno #
  
egn #
  
УНИФОРМ ГРАЖДАНСКИ НОМЕР
  
Униформ id
  
Униформ граждански id
  
УНИФОРМ ГРАЖДАНСКИ НЕ
  
## <a name="croatia"></a>克罗地亚

### <a name="format"></a>格式

不得含有空格或分隔符 11 位数字
  
### <a name="pattern"></a>模式

11 个数字：
  
- 10 位数字，随机选择
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_croatia_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_croatia_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_croatia_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordscroatiaeutaxfilenumber"></a>Keywords_croatia_eu_tax_file_number

税号
  
税费
  
tax id

  
oid
  
oid #
  
porezni broj
  
## <a name="cyprus"></a>塞浦路斯

### <a name="format"></a>格式

八个数字和指定的模式中的一个字母
  
### <a name="pattern"></a>模式

八个数字和一个字母：
  
-  "0" 
    
- 七个数字 
    
- 一个字母 （不区分大小写）
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_cyprus_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_cyprus_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_cyprus_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordscypruseutaxfilenumber"></a>Keywords_cyprus_eu_tax_file_number

税号
  
税费
  
tax id

  
税费标识代码
  
tic
  
tic #
  
ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ
  
ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
## <a name="czech-republic"></a>捷克共和国

### <a name="format"></a>格式

使用可选的反斜杠 9 或 10 个数字
  
### <a name="pattern"></a>模式

使用可选 backslashl 9 或 10 位数字：
  
- 六位数字 
    
- 反斜杠 （可选）
    
- 三个或四个数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_czech_republic_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_czech_republic_eu_tax_file_number`找到。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsczechrepubliceutaxfilenumber"></a>Keywords_czech_republic_eu_tax_file_number

税号
  
税费
  
tax id

  
个人号码
  
daňové číslo
  
osobní číslo
  
## <a name="denmark"></a>丹麦

### <a name="format"></a>格式

包含连字符的 10 位数字
  
### <a name="pattern"></a>模式

包含 hyphenl 10 位数字：
  
-  对应于出生日期月日的 6 个数字 
    
- 一个连字符 
    
- 对应的第一个数字对应的出生 century 的顺序号的四位数字的最后一位对应的个人性别 （男性和甚至女性奇数页）
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_denmark_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_denmark_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_denmark_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsdenmarkeutaxfilenumber"></a>Keywords_denmark_eu_tax_file_number

税号
  
税费
  
tax id

  
cpr 号码
  
cpr #
  
skat nummer
  
skat id
  
## <a name="estonia"></a>爱沙尼亚

### <a name="format"></a>格式

不得含有空格或分隔符 11 位数字
  
### <a name="pattern"></a>模式

11 个数字：
  
-  有一个对应于性别和出生其中奇数指示男性和偶数指示女性，如下所示的 century 的数字： 1，2 代表 19 世纪;3、 4 20 世纪;5、 6 21 世纪和 
    
- 对应于出生日期 (YYMMDD) 的 6 个数字
    
- 对应于分隔人员在相同日期出生日期序列号的三个数字
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_estonia_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_estonia_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_estonia_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsestoniaeutaxfilenumber"></a>Keywords_estonia_eu_tax_file_number

税号
  
税费
  
tax id

  
个人代码
  
maksunumber
  
maksu id
  
isikukood
  
## <a name="finland"></a>芬兰

### <a name="format"></a>格式

字母数字 11 个字符组成，和加号和减号
  
### <a name="pattern"></a>模式

字母数字 11 个字符组成，和加号和减号：
  
- 六位数字
    
- 以下项之一： 加号、 减号或其中加号表示的字母"A"（不区分大小写） 之间 1800年 1899年出生减号登录出生日期之间的表示 1900年-1999年和"A"表示出生 2000年和之后
    
- 三位数字
    
- 一个字母或一个号码
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_finland_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_finland_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_finland_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsfinlandeutaxfilenumber"></a>Keywords_finland_eu_tax_file_number

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
  
## <a name="france"></a>法国

### <a name="format"></a>格式

为个人和实体的九个数字 13 数字
  
### <a name="pattern"></a>模式

对于个人的 13 数字：
  
- 必须是 0、 1、 2 或 3 的一位数
    
- 12 个数字
    
实体的九个数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_france_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_france_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_france_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsfranceeutaxfilenumber"></a>Keywords_france_eu_tax_file_number

纳税标识号
  
税号
  
tax id

  
numéro d'identification fiscale
  
## <a name="germany"></a>德国

### <a name="format"></a>格式

没有空格和分隔符 11 位数字
  
### <a name="pattern"></a>模式

11 位数字：
  
-  10 位数字 
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_germany_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_germany_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_germany_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsgermanyeutaxfilenumber"></a>Keywords_germany_eu_tax_file_number

税号
  
税费否。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
纳税标识号
  
不纳税标识。
  
steuernummer
  
steuer id
  
steueridentifikationsnummer
  
## <a name="greece"></a>希腊

### <a name="format"></a>格式

没有空格和分隔符的九个数字
  
### <a name="pattern"></a>模式

九个数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_greece_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_greece_eu_tax_file_number`找到。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsgreeceeutaxfilenumber"></a>Keywords_greece_eu_tax_file_number

afm
  
tin

  
不税费 id。
  
不税费 id
  
纳税标识号
  
税务注册表编号
  
不税费注册表。
  
afm #
  
会议 #
  
taxidno #
  
taxregistryno #
  
ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
aφμ
  
aφμ αριθμός
  
ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ。
  
ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ
  
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

不得含有空格或分隔符的 10 位数字
  
### <a name="pattern"></a>模式

10 位数字：
  
-  必须是"8"的一位数 
    
- 对应于日期之间的天数的五个数字 01/01/1867年和各出生日期
    
- 生成的可能性区分出生在同一天的个人号码所对应的三个数字
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_hungary_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_hungary_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_hungary_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordshungaryeutaxfilenumber"></a>Keywords_hungary_eu_tax_file_number

匈牙利语纳税标识号
  
匈牙利语会议
  
税号
  
增值税编号
  
不税费证书颁发机构
  
税号税费标识
  
taxidnumber #
  
会议 #
  
hungatiantin #
  
不税费标识
  
taxidno #
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>Ireland

### <a name="format"></a>格式

七位数字后跟不得含有空格或分隔符号
  
### <a name="pattern"></a>模式

接一个字母的七个数字：
  
-  七个数字  
    
- 一个字母 （不区分大小写）
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_ireland_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_ireland_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_ireland_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsirelandeutaxfilenumber"></a>Keywords_ireland_eu_tax_file_number

公共服务没有
  
个人公共服务没有
  
pps 没有
  
个人服务否
  
pps service 否
  
ppsno #
  
爱尔兰 pps 没有
  
publicserviceno #
  
个人公共服务号码
  
uimhir phearsanta seirbhíse poiblí
  
pps uimh
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>意大利

### <a name="format"></a>格式

16 字母和指定的模式中的数字
  
### <a name="pattern"></a>模式

16 字母和数字：
  
-  对应于系列名称中的前三个辅音的三个字母 
    
- 对应于第一、 第三个和第四个的三个字母辅音中第一个名称
    
- 两位数的最后一个对应出生年份的数字
    
- 对应于出生月份的一位数 — 字母使用以字母顺序列出，但仅字母 A 到 E、 H、 L、 M、 P、 R T 到使用 （即年 1 月是 A 和年 10 月为 R）
    
- 对应于出生 40 其中添加到的女生从男生区分出生日期的月的天的两位数
    
- 对应于特定于此人出生上级主管机构区号的四位数字 — 外的国家/地区使用范围内的国家/地区代码
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_italy_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_italy_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_italy_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsitalyeutaxfilenumber"></a>Keywords_italy_eu_tax_file_number

税号
  
税费否。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
会计代码
  
codice fiscale
  
## <a name="latvia"></a>拉脱维亚

### <a name="format"></a>格式

不得含有空格或分隔符 11 位数字
  
### <a name="pattern"></a>模式

11 位数字中指定的模式
  
-  对应于月日出生日期的 6 个数字 
    
- 对应于出生其中"0"对应于 19 century、"1"对应于 20 世纪和"2"对应于 21 世纪 century 的一位数
    
- 四位数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_latvia_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_latvia_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_latvia_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordslatviaeutaxfilenumber"></a>Keywords_latvia_eu_tax_file_number

税号
  
税费否。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
纳税标识号
  
不纳税标识。
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

不含空格或分隔符 11 位数字
  
### <a name="pattern"></a>模式

11 个数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_lithuania_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_lithuania_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_lithuania_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordslithuaniaeutaxfilenumber"></a>Keywords_lithuania_eu_tax_file_number

税号
  
税费否。
  
税费无 #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
纳税标识号
  
不纳税标识。
  
mokesčių id
  
mokesčių numeris
  
mokesčių identifikavimas numeris
  
## <a name="luxemburg"></a>卢森堡

### <a name="format"></a>格式

13 不得含有空格或分隔符的数字
  
### <a name="pattern"></a>模式

13 个数字：
  
-  11 个数字 
    
- 两个校验位
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_luxemburg_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_luxemburg_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_luxemburg_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsluxemburgeutaxfilenumber"></a>Keywords_luxemburg_eu_tax_file_number

税号
  
税费否。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
纳税标识号
  
不纳税标识。
  
steuernummer
  
steuer id
  
steueridentifikationsnummer
  
## <a name="malta"></a>马耳他

### <a name="format"></a>格式

为马耳他公民： 7 位数字和指定的模式中的一个字母
  
非马耳他公民和马耳他实体： 9 位
  
### <a name="pattern"></a>模式

马耳他公民： 7 位数字和一个字母
  
-  七个数字  
    
- 一个字母 （不区分大小写）
    
非马耳他公民和马耳他实体： 9 位
  
-  九个数字 
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_malta_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_malta_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_malta_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsmaltaeutaxfilenumber"></a>Keywords_malta_eu_tax_file_number

税号
  
税费否。
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id

  
taxid #
  
纳税标识号
  
不纳税标识。
  
numru tat taxxa
  
id tat taxxa
  
numru 选项卡 identifikazzjoni tat taxxa
  
## <a name="netherlands"></a>荷兰

### <a name="format"></a>格式

不含空格或分隔符的九个数字
  
### <a name="pattern"></a>模式

九个数字 
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_netherlands_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_netherlands_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_netherlands_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsnetherlandseutaxfilenumber"></a>Keywords_netherlands_eu_tax_file_number

荷兰纳税标识号
  
荷兰税标识
  
荷属安的纳税标识号
  
荷属安的税费标识
  
纳税标识号
  
荷兰税务 id
  
荷兰税务标识号
  
tax id

  
税费 id #
  
税号
  
税费无 #
  
税费 #
  
tin

  
会议 #
  
荷兰会议
  
荷属安的会议
  
nederlands belasting identificatienummer
  
identificatienummer van belasting
  
identificatienummer belasting
  
nederlands belasting identificatie
  
nederlands belasting id nummer
  
nederlands belastingnummer
  
顺便说一下 nummer
  
nederlandse belasting identificatie
  
## <a name="poland"></a>波兰

### <a name="format"></a>格式

不得含有空格或分隔符 11 个数字
  
### <a name="pattern"></a>模式

11 个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_poland_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_poland_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_poland_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordspolandeutaxfilenumber"></a>Keywords_poland_eu_tax_file_number

税号
  
税费否。
  
taxno #
  
taxnumber #
  
taxnumber
  
nip
  
nip #
  
tax id

  
税费 id #
  
nip id
  
nip id #
  
纳税标识号
  
不纳税标识。
  
增值税编号
  
增值税否。
  
vatno #
  
增值税 id
  
增值税 id #
  
个数 identyfikacji podatkowej
  
polski 个数 identyfikacji podatkowej
  
numeridentyfikacjipodatkowej #
  
## <a name="portugal"></a>葡萄牙

### <a name="format"></a>格式

不得含有空格或分隔符的九个数字
  
### <a name="pattern"></a>模式

九个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_portugal_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_portugal_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_portugal_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsportugaleutaxfilenumber"></a>Keywords_portugal_eu_tax_file_number

税号
  
税费否。
  
taxno #
  
taxnumber #
  
taxnumber
  
n 如果
  
n 如果 #
  
会计 numero
  
número de identificação 会计
  
## <a name="romania"></a>罗马尼亚

### <a name="format"></a>格式

13 不得含有空格或分隔符的数字
  
### <a name="pattern"></a>模式

13 位数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_romania_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_romania_eu_tax_file_number`找到。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsromaniaeutaxfilenumber"></a>Keywords_romania_eu_tax_file_number

tax id

  
税号
  
不税费文件
  


tax file number
  
税费否
  
税号
  
taxid #
  
taxno #
  
id ul taxei
  
numărul de identificare fiscală
  
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

不得含有空格或分隔符的 10 位数字
  
### <a name="pattern"></a>模式

10 个数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_slovakia_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_slovakia_eu_tax_file_number`找到。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsslovakiaeutaxfilenumber"></a>Keywords_slovakia_eu_tax_file_number

tax id

  
税号
  
锡 id
  
锡否
  
斯洛伐克语锡 id
  
tin

  
不税费文件
  


tax file number
  
税费否
  
税号
  
taxid #
  
taxno #
  
daňové identifikačné číslo
  
daňové číslo
  
daňové číslo súboru
  
## <a name="slovenia"></a>斯诺文尼亚

### <a name="format"></a>格式

不得含有空格或分隔符的八个数字
  
### <a name="pattern"></a>模式

八个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_slovenia_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_slovenia_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_slovenia_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordssloveniaeutaxfilenumber"></a>Keywords_slovenia_eu_tax_file_number

tax id

  
税号
  
锡 id
  
锡否
  
斯洛文尼亚语锡 id
  
tin

  
不税费文件
  


tax file number
  
税费否
  
税号
  
taxid #
  
taxno #
  
identifikacijska številka davka
  
davčna številka
  
Številka davčne datoteke
  
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

七个或八个数字和指定的模式中的一个或两个字母
  
### <a name="pattern"></a>模式

西班牙国家/地区身份证与西班牙语自然人员：
  
-  八个数字 
    
- 一个大写字母 （区分大小写） 
    
西班牙国家/地区身份证不非居民 Spaniards
  
- 一个大写字母"L"（区分大小写）
    
- 七个数字 
    
- 一个大写字母 （区分大小写） 
    
14 年不西班牙国家/地区身份证岁驻留 Spaniards:
  
- 一个大写字母"K"（区分大小写）
    
-  七个数字  
    
- 一个大写字母 （区分大小写）
    
与 Foreigner 标识号外国人
  
- 一个大写字母的字母"X"、"Y"或"Z"（区分大小写） 
    
- 七个数字 
    
- 一个大写字母 （区分大小写） 
    
外国人不 Foreigner 标识号
  
- 一个大写字母的"M"（区分大小写） 
    
- 七个数字 
    
- 一个大写字母 （区分大小写） 
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_spain_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_spain_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_spain_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsspaineutaxfilenumber"></a>Keywords_spain_eu_tax_file_number

tax id

  
税号
  
cif id
  
cif 没有
  
西班牙语 cif id
  
cif
  
不税费文件
  
西班牙语 cif 号码
  


tax file number
  
西班牙语 cif 没有
  
税费否
  
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

10 位数字和中指定的模式的符号
  
### <a name="pattern"></a>模式

10 位数字和一个符号：
  
-  对应于出生日期 (YYMMDD) 的 6 个数字 
    
- 加号、 减号或反斜杠
    
- 进行标识的三个数字数字唯一位置： 
    
  - 对于之前 1990年颁发的数字，第七个和第八个数字标识出生或 foreign-born 人员的县
    
  - 第九个位置中的数字的任一奇数男性或甚至女性指示性别
    
- 一个检查数字
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_sweden_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_sweden_eu_tax_file_number`找到。 
    
在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_sweden_eu_tax_file_number`查找与模式匹配的内容。 
    
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

### <a name="keywords"></a>Keywords

#### <a name="keywordsswedeneutaxfilenumber"></a>Keywords_sweden_eu_tax_file_number

tax id

  
不税费 id。
  
税号
  
tax identification

  
税费标识 #
  
税费否。
  
税费 #
  
taxid #
  
税费文件
  
不税费文件。
  
个人标识号
  
skatt id nummer
  
skatt identifikation
  
personnummer
  
## <a name="uk"></a>英国

### <a name="format"></a>格式

没有空格和分隔符的唯一纳税人引用 (UTR): 10 位数字
  
国家保险号码 (NINO): 有关详细信息，请参阅"英国 National 保险号码 (NINO)"部分中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)。
  
### <a name="pattern"></a>模式

唯一纳税人引用 (UTR): 10 位数字
  
国家保险号码 (NINO): 有关详细信息，请参阅"英国 National 保险号码 (NINO)"部分中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)。
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 该函数`Func_uk_eu_tax_file_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_uk_eu_tax_file_number`找到。 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Keywords

#### <a name="keywordsukeutaxfilenumber"></a>Keywords_uk_eu_tax_file_number

tax id

  
不税费 id。
  
税号
  
tax identification

  
税费标识 #
  
税费否。
  
税费 #
  
taxid #
  
税费文件
  
不税费文件。
  
## <a name="see-also"></a>另请参阅

[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)


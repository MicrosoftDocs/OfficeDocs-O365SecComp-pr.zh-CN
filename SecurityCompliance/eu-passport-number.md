---
title: EU 护照号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟护照号敏感信息类型时, 应查找什么内容。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: 3ab92e87607f41cffa8c15f1179a4eef5369cb29
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410927"
---
# <a name="eu-passport-number"></a>EU 护照号码

本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟护照号敏感信息类型时, 应查找什么内容。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
  
## <a name="austria"></a>奥地利

### <a name="format"></a>格式

一个字母后跟一个可选空格和七个数字
  
### <a name="pattern"></a>模式

一个字母、七个数字和一个空格的组合:
  
- 一个字母（不区分大小写）
    
- 一个空格 (可选)
    
- 七个数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_austria_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_austria_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_austria_eu_passport_number**|
|:-----|
|passport number  <br/> 奥地利护照号码  <br/> 护照号  <br/> reisepass  <br/> österreichisch reisepass  <br/> |
   
## <a name="belgium"></a>比利时

### <a name="format"></a>格式

两个字母后跟六个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母, 后跟六个数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_belgium_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_belgium_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_belgium_eu_passport_number**|
|:-----|
|passport number  <br/> 比利时护照号码  <br/> 护照号  <br/> paspoort  <br/> paspoortnummer  <br/> reisepass kein  <br/> reisepass  <br/> |
   
## <a name="bulgaria"></a>保加利亚语

### <a name="format"></a>格式

9个数字, 不带空格和分隔符
  
### <a name="pattern"></a>模式

 九个数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_bulgaria_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_bulgaria_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_bulgaria_eu_passport_number**|
|:-----|
|passport number  <br/> 保加利亚语护照号码  <br/> 护照号  <br/> номернапаспорта  <br/> |
   
## <a name="croatia"></a>克罗地亚

### <a name="format"></a>格式

9个数字, 不带空格和分隔符
  
### <a name="pattern"></a>模式

 九个数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_croatia_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_croatia_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_croatia_eu_passport_number**|
|:-----|
|passport number  <br/> 克罗地亚护照号码  <br/> 护照号  <br/> broj putovnice  <br/> |
   
## <a name="cyprus"></a>塞浦路斯

### <a name="format"></a>格式

一个字母后跟6-8 个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

一个字母后跟6到8个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_cyprus_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_cyprus_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_cyprus_eu_passport_number**|
|:-----|
|passport number  <br/> 塞浦路斯护照号码  <br/> 护照号  <br/> αριθμόδιαβατηρίου  <br/> |
   
## <a name="czech-republic"></a>捷克共和国

### <a name="format"></a>格式

8位数, 不含空格或分隔符
  
### <a name="pattern"></a>模式

8位数, 不含空格或分隔符
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_czech_republic_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_czech_republic_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_czech_republic_eu_passport_number**|
|:-----|
|passport number  <br/> 捷克语护照号码  <br/> 护照号  <br/> cestovní pas  <br/> pas  <br/> |
   
## <a name="denmark"></a>丹麦

### <a name="format"></a>格式

9个数字, 不带空格和分隔符
  
### <a name="pattern"></a>模式

 九个数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_denmark_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_denmark_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_denmark_eu_passport_number**|
|:-----|
|passport number  <br/> 丹麦护照号码  <br/> 护照号  <br/> pas  <br/> pasnummer  <br/> |
   
## <a name="estonia"></a>爱沙尼亚

### <a name="format"></a>格式

一个字母后跟七个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

一个字母后跟七个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_estonia_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_estonia_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_estonia_eu_passport_number**|
|:-----|
|passport number  <br/> 爱沙尼亚语护照号码  <br/> 护照号  <br/> eesti kodaniku pass  <br/> |
   
## <a name="finland"></a>芬兰

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰护照号码" 一节。
  
## <a name="france"></a>法国

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国护照号码" 一节。
  
## <a name="germany"></a>德国

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国护照号码" 一节。
  
## <a name="greece"></a>希腊

### <a name="format"></a>格式

两个字母后跟七个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母后跟七个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_greece_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_greece_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_greece_eu_passport_number**|
|:-----|
|passport number  <br/> 希腊护照号码  <br/> 护照号  <br/> διαβατηριο  <br/> |
   
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

两个字母后跟6个或7个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母后跟六个或七个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_hungary_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_hungary_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_hungary_eu_passport_number**|
|:-----|
|passport number  <br/> 匈牙利语护照号码  <br/> 护照号  <br/> útlevél száma  <br/> |
   
## <a name="ireland"></a>Ireland

### <a name="format"></a>格式

两个字母或数字后跟七个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母或数字, 后跟七个数字:
  
- 两位数字或字母（不区分大小写）
    
- 七个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_ireland_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_ireland_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_ireland_eu_passport_number**|
|:-----|
|passport number  <br/> 爱尔兰护照号码  <br/> 护照号  <br/> pas  <br/> 登记卡  <br/> passeport  <br/> passeport numero  <br/> |
   
## <a name="italy"></a>意大利

### <a name="format"></a>格式

两个字母或数字后跟七个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母或数字, 后跟七个数字:
  
- 两位数字或字母（不区分大小写）
    
- 七个数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_italy_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_italy_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_italy_eu_passport_number**|
|:-----|
|意大利护照号码  <br/> repubblica italiana passaporto  <br/> passaporto  <br/> passaporto italiana  <br/> passport number  <br/> italiana passaporto numero  <br/> passaporto numero  <br/> numéro passeport italien  <br/> numéro passeport  <br/> |
   
## <a name="latvia"></a>拉脱维亚

### <a name="format"></a>格式

两个字母或数字后跟七个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母或数字, 后跟七个数字:
  
- 两位数字或字母（不区分大小写）
    
- 七个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_latvia_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_latvia_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_latvia_eu_passport_number**|
|:-----|
|passport number  <br/> 拉脱维亚语护照号码  <br/> 护照号  <br/> pase numurs  <br/> |
   
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

八个数字或字母不带空格或分隔符
  
### <a name="pattern"></a>模式

八个数字或字母 (不区分大小写)
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_lithuania_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_lithuania_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_lithuania_eu_passport_number**|
|:-----|
|passport number  <br/> lithunian 护照号码  <br/> 护照号  <br/> paso numeris  <br/> |
   
## <a name="luxemburg"></a>Luxemburg

### <a name="format"></a>格式

八个数字或字母不带空格或分隔符
  
### <a name="pattern"></a>模式

八个数字或字母 (不区分大小写)
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_nation_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_nation_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_nation_eu_passport_number**|
|:-----|
|passport number  <br/> 拉脱维亚语护照号码  <br/> 护照号  <br/> passnummer  <br/> |
   
## <a name="malta"></a>Malta（马耳他）

### <a name="format"></a>格式

七位数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

 七个数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_malta_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_malta_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_malta_eu_passport_number**|
|:-----|
|passport number  <br/> 马耳他护照号码  <br/> 护照号  <br/> numru tal-passaport  <br/> |
   
## <a name="netherlands"></a>荷兰

### <a name="format"></a>格式

九个字母或数字, 不带空格或分隔符
  
### <a name="pattern"></a>模式

九个字母或数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_netherlands_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_netherlands_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_netherlands_eu_passport_number**|
|:-----|
|荷兰护照号码  <br/> passport number  <br/> 荷兰护照号码  <br/> nederlanden paspoort nummer  <br/> paspoort  <br/> nederlanden paspoortnummer  <br/> paspoortnummer  <br/> |
   
## <a name="poland"></a>波兰

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰 Passport 号码" 一节。
  
## <a name="portugal"></a>葡萄牙

### <a name="format"></a>格式

一个字母后跟六个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

一个字母后跟六个数字:
  
- 一个字母（不区分大小写）
    
- 六个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_portugal_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_portugal_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_portugal_eu_passport_number**|
|:-----|
|passport number  <br/> 葡萄牙语护照号码  <br/> 护照号  <br/> número do passaporte  <br/> |
   
## <a name="romania"></a>罗马尼亚

### <a name="format"></a>格式

八个或9个数字, 不含空格和分隔符
  
### <a name="pattern"></a>模式

8或9个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_romania_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_romania_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_romania_eu_passport_number**|
|:-----|
|passport number  <br/> 罗马尼亚护照号码  <br/> 护照号  <br/> numărul pașaportului  <br/> |
   
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

一个数字或字母后跟七个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

一个数字或字母 (不区分大小写) 后跟七个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_slovakia_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_slovakia_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_slovakia_eu_passport_number**|
|:-----|
|passport number  <br/> 斯洛伐克护照号码  <br/> 护照号  <br/> číslo pasu  <br/> |
   
## <a name="slovenia"></a>斯洛文尼亚

### <a name="format"></a>格式

两个字母后跟七个数字, 不含空格或分隔符
  
### <a name="pattern"></a>模式

两个字母后跟七个数字:
  
- 字母 "P"
    
- 一个大写字母
    
- 七个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_slovenia_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_slovenia_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_slovenia_eu_passport_number**|
|:-----|
|passport number  <br/> 斯洛文尼亚护照号码  <br/> 护照号  <br/> številka potnega lista  <br/> |
   
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

八个或九个字符的字母和数字的组合, 不带空格或分隔符
  
### <a name="pattern"></a>模式

字母和数字的八个或九个字符的组合:
  
-  两位数字或字母 
    
- 一个数字或字母 (可选)
    
- 六个数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_spain_eu_passport_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_spain_eu_passport_number`的关键字。 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_spain_eu_passport_number**|
|:-----|
|登记卡  <br/> 西班牙护照  <br/> 护照书籍  <br/> passport number  <br/> 护照号  <br/> libreta pasaporte  <br/> número pasaporte  <br/> 西班牙 pasaporte  <br/> pasaporte  <br/> |
   
## <a name="sweden"></a>瑞典

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典护照号码" 一节。
  
## <a name="uk"></a>英国

有关详细信息, 请参阅 "美国/英国" 一节。 "Passport 号码", 在[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中。
  
## <a name="see-also"></a>另请参阅

[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)


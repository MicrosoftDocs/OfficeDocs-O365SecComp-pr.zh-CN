---
title: 欧盟护照号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: 本主题演示数据丢失防护 (DLP) 策略检测到的欧盟护照号码敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
ms.openlocfilehash: 7a7fc1ff826aab4096c46535686eb0fd68173c6f
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "25840321"
---
# <a name="eu-passport-number"></a>欧盟护照号码

本主题演示数据丢失防护 (DLP) 策略检测到的欧盟护照号码敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
  
## <a name="austria"></a>奥地利

### <a name="format"></a>格式

可选的空间和七位数字后跟一个字母
  
### <a name="pattern"></a>模式

一个字母、 七个数字和一个空格的组合：
  
- 一个字母（不区分大小写）
    
- 一个空格 （可选）
    
- 七个数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_austria_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_austria_eu_passport_number`找到。 
    
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
|护照号码  <br/> 奥地利护照号码  <br/> passport 没有  <br/> reisepass  <br/> österreichisch reisepass  <br/> |
   
## <a name="belgium"></a>比利时

### <a name="format"></a>格式

不得含有空格或分隔符六位数字后跟两个字母
  
### <a name="pattern"></a>模式

两个字母和包含 6 位数字后跟
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_belgium_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_belgium_eu_passport_number`找到。 
    
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
|护照号码  <br/> 比利时护照号码  <br/> passport 没有  <br/> paspoort  <br/> paspoortnummer  <br/> reisepass kein  <br/> reisepass  <br/> |
   
## <a name="bulgaria"></a>保加利亚

### <a name="format"></a>格式

没有空格和分隔符的九个数字
  
### <a name="pattern"></a>模式

 九个数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_bulgaria_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_bulgaria_eu_passport_number`找到。 
    
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
|护照号码  <br/> 保加利亚护照号码  <br/> passport 没有  <br/> НОМЕР НА ПАСПОРТА  <br/> |
   
## <a name="croatia"></a>克罗地亚

### <a name="format"></a>格式

没有空格和分隔符的九个数字
  
### <a name="pattern"></a>模式

 九个数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_croatia_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_croatia_eu_passport_number`找到。 
    
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
|护照号码  <br/> 克罗地亚语护照号码  <br/> passport 没有  <br/> broj putovnice  <br/> |
   
## <a name="cyprus"></a>塞浦路斯

### <a name="format"></a>格式

不得含有空格或分隔符 6-8 位数字后跟一个字母
  
### <a name="pattern"></a>模式

6 到 8 位数字后跟一个字母
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_cyprus_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_cyprus_eu_passport_number`找到。 
    
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
|护照号码  <br/> 塞浦路斯护照号码  <br/> passport 没有  <br/> ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ  <br/> |
   
## <a name="czech-republic"></a>捷克共和国

### <a name="format"></a>格式

八个不含空格或分隔符的数字
  
### <a name="pattern"></a>模式

八个不含空格或分隔符的数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_czech_republic_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_czech_republic_eu_passport_number`找到。 
    
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
|护照号码  <br/> 捷克护照号码  <br/> passport 没有  <br/> cestovní pas  <br/> pas  <br/> |
   
## <a name="denmark"></a>丹麦

### <a name="format"></a>格式

没有空格和分隔符的九个数字
  
### <a name="pattern"></a>模式

 九个数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_denmark_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_denmark_eu_passport_number`找到。 
    
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
|护照号码  <br/> 丹麦语护照号码  <br/> passport 没有  <br/> pas  <br/> pasnummer  <br/> |
   
## <a name="estonia"></a>爱沙尼亚

### <a name="format"></a>格式

不得含有空格或分隔符的七位数字后跟一个字母
  
### <a name="pattern"></a>模式

七位数字后跟一个字母
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_estonia_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_estonia_eu_passport_number`找到。 
    
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
|护照号码  <br/> 爱沙尼亚护照号码  <br/> passport 没有  <br/> eesti kodaniku 传递  <br/> |
   
## <a name="finland"></a>芬兰

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"芬兰护照号码"。
  
## <a name="france"></a>法国

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"法国护照号码"。
  
## <a name="germany"></a>德国

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"德国护照号码"。
  
## <a name="greece"></a>希腊

### <a name="format"></a>格式

不得含有空格或分隔符的七位数字后跟两个字母
  
### <a name="pattern"></a>模式

两个字母后跟七个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_greece_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_greece_eu_passport_number`找到。 
    
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
|护照号码  <br/> 希腊语护照号码  <br/> passport 没有  <br/> ΔΙΑΒΑΤΗΡΙΟ  <br/> |
   
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

不得含有空格或分隔符的六个或七位数字后跟两个字母
  
### <a name="pattern"></a>模式

六个或七位数字后跟两个字母
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_hungary_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_hungary_eu_passport_number`找到。 
    
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
|护照号码  <br/> 匈牙利语护照号码  <br/> passport 没有  <br/> útlevél száma  <br/> |
   
## <a name="ireland"></a>Ireland

### <a name="format"></a>格式

两个字母或数字后跟不得含有空格或分隔符的七位数字
  
### <a name="pattern"></a>模式

两个字母或数字后跟七位数字：
  
- 两位数字或字母（不区分大小写）
    
- 七个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_ireland_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_ireland_eu_passport_number`找到。 
    
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
|护照号码  <br/> 爱尔兰护照号码  <br/> passport 没有  <br/> pas  <br/> passport  <br/> passeport  <br/> passeport numero  <br/> |
   
## <a name="italy"></a>意大利

### <a name="format"></a>格式

两个字母或数字后跟不得含有空格或分隔符的七位数字
  
### <a name="pattern"></a>模式

两个字母或数字后跟七位数字：
  
- 两位数字或字母（不区分大小写）
    
- 七个数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_italy_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_italy_eu_passport_number`找到。 
    
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
|意大利护照号码  <br/> repubblica italiana passaporto  <br/> passaporto  <br/> passaporto italiana  <br/> 护照号码  <br/> italiana passaporto numero  <br/> passaporto numero  <br/> numéro passeport italien  <br/> numéro passeport  <br/> |
   
## <a name="latvia"></a>拉脱维亚

### <a name="format"></a>格式

两个字母或数字后跟不得含有空格或分隔符的七位数字
  
### <a name="pattern"></a>模式

两个字母或数字后跟七位数字：
  
- 两位数字或字母（不区分大小写）
    
- 七个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_latvia_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_latvia_eu_passport_number`找到。 
    
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
|护照号码  <br/> 拉脱维亚护照号码  <br/> passport 没有  <br/> pase numurs  <br/> |
   
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

八个数字或字母不得含有空格或分隔符
  
### <a name="pattern"></a>模式

八个数字或字母 （不区分大小写）
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_lithuania_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_lithuania_eu_passport_number`找到。 
    
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
|护照号码  <br/> lithunian 护照号码  <br/> passport 没有  <br/> paso numeris  <br/> |
   
## <a name="luxemburg"></a>卢森堡

### <a name="format"></a>格式

八个数字或字母不得含有空格或分隔符
  
### <a name="pattern"></a>模式

八个数字或字母 （不区分大小写）
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_nation_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_nation_eu_passport_number`找到。 
    
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
|护照号码  <br/> 拉脱维亚护照号码  <br/> passport 没有  <br/> passnummer  <br/> |
   
## <a name="malta"></a>马耳他

### <a name="format"></a>格式

不含空格或分隔符的七位数字
  
### <a name="pattern"></a>模式

 七个数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_malta_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_malta_eu_passport_number`找到。 
    
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
|护照号码  <br/> 马耳他护照号码  <br/> passport 没有  <br/> numru tal passaport  <br/> |
   
## <a name="netherlands"></a>荷兰

### <a name="format"></a>格式

九个字母或数字不得含有空格或分隔符
  
### <a name="pattern"></a>模式

九个字母或数字
  
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_netherlands_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_netherlands_eu_passport_number`找到。 
    
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
|荷兰语护照号码  <br/> 护照号码  <br/> 荷兰护照号码  <br/> nederlanden paspoort nummer  <br/> paspoort  <br/> nederlanden paspoortnummer  <br/> paspoortnummer  <br/> |
   
## <a name="poland"></a>波兰

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"波兰护照号码"。
  
## <a name="portugal"></a>葡萄牙

### <a name="format"></a>格式

不得含有空格或分隔符六位数字后跟一个字母
  
### <a name="pattern"></a>模式

包含 6 位数字后跟一个字母：
  
- 一个字母（不区分大小写）
    
- 六个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_portugal_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_portugal_eu_passport_number`找到。 
    
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
|护照号码  <br/> 葡萄牙语护照号码  <br/> passport 没有  <br/> número 执行 passaporte  <br/> |
   
## <a name="romania"></a>罗马尼亚

### <a name="format"></a>格式

八个或九个没有空格和分隔符的数字
  
### <a name="pattern"></a>模式

八个或九个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_romania_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_romania_eu_passport_number`找到。 
    
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
|护照号码  <br/> 罗马尼亚语护照号码  <br/> passport 没有  <br/> numărul pașaportului  <br/> |
   
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

一个数字或字母不得含有空格或分隔符的七位数字后跟
  
### <a name="pattern"></a>模式

一个数字或字母 （不区分大小写） 七位数字后跟
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_slovakia_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_slovakia_eu_passport_number`找到。 
    
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
|护照号码  <br/> 斯洛伐克语护照号码  <br/> passport 没有  <br/> Číslo pasu  <br/> |
   
## <a name="slovenia"></a>斯诺文尼亚

### <a name="format"></a>格式

不得含有空格或分隔符的七位数字后跟两个字母
  
### <a name="pattern"></a>模式

七位数字后跟两个字母：
  
- 字母"P"
    
- 一个大写字母
    
- 七个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_slovenia_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_slovenia_eu_passport_number`找到。 
    
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
|护照号码  <br/> 斯洛文尼亚语护照号码  <br/> passport 没有  <br/> Številka potnega 可变  <br/> |
   
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

字母或数字，没有空格或分隔符的八个字符或九个字符组合
  
### <a name="pattern"></a>模式

字母和数字的八个字符或九个字符组合：
  
-  两个数字或字母 
    
- 一个数字或字母 （可选）
    
- 六个数字
    
### <a name="checksum"></a>校验和

不适用
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_spain_eu_passport_number`查找与模式匹配的内容。 
    
- 从关键字`Keywords_spain_eu_passport_number`找到。 
    
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
|passport  <br/> 西班牙 passport  <br/> passport 书籍  <br/> 护照号码  <br/> passport 没有  <br/> libreta pasaporte  <br/> número pasaporte  <br/> españa pasaporte  <br/> pasaporte  <br/> |
   
## <a name="sweden"></a>瑞典

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"瑞典护照号码"。
  
## <a name="uk"></a>英国

有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"美国/英国护照号码"。
  
## <a name="see-also"></a>另请参阅

[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)


---
title: 欧盟驾驶执照号码
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟驱动程序的敏感信息类型时, 应查找什么内容。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: 86be7b52aed7581fd62ab595ac2c4b63ab33aab3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217742"
---
# <a name="eu-drivers-license-number"></a>欧盟驾驶执照号码

本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟驱动程序的敏感信息类型时, 应查找什么内容。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
  
## <a name="austria"></a>奥地利

### <a name="format"></a>格式

8位数, 不含空格和分隔符
  
### <a name="pattern"></a>模式

八个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_austria_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_austria_eu_driver's_license_number`的关键字。 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a>关键字

| |
|**Keywords_austria_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> 驾驶许可证  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/>  驾驶执照号码  <br/> dlno #  <br/> fuhrerschein  <br/> fuhrerschein republik osterreich  <br/> |
   
## <a name="belgium"></a>比利时

### <a name="format"></a>格式

10个数字, 不含空格和分隔符
  
### <a name="pattern"></a>模式

10 个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_belgium_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_belgium_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>关键字

| |
|**Keywords__belgium_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> dlno #  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> führerscheinnummer  <br/> fuhrerscheinnummer  <br/> fuehrerscheinnummer  <br/> führerschein-nr-nr  <br/> fuehrerschein-Nr  <br/> fuehrerschein-nr  <br/> |
   
## <a name="bulgaria"></a>保加利亚

### <a name="format"></a>格式

9个数字, 不带空格和分隔符
  
### <a name="pattern"></a>模式

九个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_bulgaria_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_bulgaria_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a>关键字

| |
|**Keywords_bulgaria_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> свидетелствозауправлениенампс  <br/> свидетелствозауправлениенамоторнопревозносредство  <br/> сумпс  <br/> шофьорскакнижка  <br/> |
   
## <a name="croatia"></a>克罗地亚

### <a name="format"></a>格式

8位数, 不含空格和分隔符
  
### <a name="pattern"></a>模式

八个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_croatia_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_croatia_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>关键字

| |
|**Keywords_croatia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> vozačka dozvola  <br/> |
   
## <a name="cyprus"></a>塞浦路斯

### <a name="format"></a>格式

12个数字, 不含空格和分隔符
  
### <a name="pattern"></a>模式

12 个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_cyprus_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_cyprus_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_cyprus_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> άδειαοδήγησης  <br/> |
   
## <a name="czech-republic"></a>捷克共和国

### <a name="format"></a>格式

两个字母后跟六个数字
  
### <a name="pattern"></a>模式

八个字母和数字:
  
- 两个字母 (不区分大小写)
    
- 一个空格（可选） 
    
- 六个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_czech_republic_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_czech_republic_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>关键字

| |
|**Keywords_czech_republic_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> řidičský prúkaz  <br/> |
   
## <a name="denmark"></a>丹麦

### <a name="format"></a>格式

8位数, 不含空格和分隔符
  
### <a name="pattern"></a>模式

八个数字
  
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_denmark_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_denmark_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>关键字

| |
|**Keywords_denmark_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> kørekort  <br/> kørekortnummer  <br/> |
   
## <a name="estonia"></a>爱沙尼亚

### <a name="format"></a>格式

两个字母后跟六个数字
  
### <a name="pattern"></a>模式

两个字母和六个数字:
  
-  字母 "ET" (不区分大小写) 
    
- 六个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_estonia_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_estonia_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_estonia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶执照号码  <br/> dlno #  <br/> 
permis de conduire  <br/> |
   
## <a name="finland"></a>芬兰

### <a name="format"></a>格式

10 个数字，包含连字符
  
### <a name="pattern"></a>模式

10个数字, 包含连字符:
  
-  六位数字 
    
- 连字符
    
-  四位数字 
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_finland_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_finland_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_finland_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> ajokortti  <br/> |
   
## <a name="france"></a>法国

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国驾 License 号码" 一节。
  
## <a name="germany"></a>德国

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德语驱动程序号码" 一节。
  
## <a name="greece"></a>希腊

### <a name="format"></a>格式

9个数字, 不带空格和分隔符
  
### <a name="pattern"></a>模式

 九个数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_greece_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_greece_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_greece_eu_driver's_license_number**|
|:-----|
|dlL  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> δειαοδήγησης  <br/> Adeia odigisis  <br/> |
   
## <a name="hungary"></a>匈牙利

### <a name="format"></a>格式

两个字母后跟六个数字
  
### <a name="pattern"></a>模式

两个字母和六个数字:
  
-  两个字母 (不区分大小写) 
    
- 六个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_hungary_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_hungary_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_hungary_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> vezetoi engedely  <br/> |
   
## <a name="ireland"></a>Ireland

### <a name="format"></a>格式

6位数, 后跟四个字母
  
### <a name="pattern"></a>模式

6位数字和四个字母:
  
- 六位数字
    
- 四个字母 (不区分大小写)
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_ireland_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_ireland_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_ireland_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> ceadúnas tiomána  <br/> |
   
## <a name="italy"></a>意大利

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "意大利驾驶执照号码" 一节。
  
## <a name="latvia"></a>拉脱维亚

### <a name="format"></a>格式

三个字母后跟六个数字
  
### <a name="pattern"></a>模式

三个字母和六个数字:
  
-  三个字母 (不区分大小写) 
    
- 六个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_latvia_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_latvia_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_latvia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> autovadītāja apliecība  <br/> |
   
## <a name="lithuania"></a>立陶宛

### <a name="format"></a>格式

8位数, 不含空格和分隔符
  
### <a name="pattern"></a>模式

 八个数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_lithuania_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_lithuania_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_lithuania_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> vairuotojo pažymėjimas  <br/> |
   
## <a name="luxemburg"></a>Luxemburg

### <a name="format"></a>格式

6位数, 不含空格和分隔符
  
### <a name="pattern"></a>模式

 六个数字 
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_luxemburg_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_luxemburg_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_luxemburg_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> fahrerlaubnis  <br/> |
   
## <a name="malta"></a>马耳他

### <a name="format"></a>格式

两个字符与指定模式中的六个数字的组合
  
### <a name="pattern"></a>模式

两个字符和六个数字的组合:
  
- 两个字符 (数字或字母, 而不区分大小写)
    
- 一个空格（可选） 
    
- 三个数字 
    
- 一个空格（可选） 
    
- 三位数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_malta_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_malta_eu_driver's_license_number`的关键字。 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_malta_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> liċenzja tas-sewqan  <br/> |
   
## <a name="netherlands"></a>荷兰

### <a name="format"></a>格式

10个数字, 不含空格和分隔符
  
### <a name="pattern"></a>模式

10 个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_netherlands_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_netherlands_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_netherlands_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> 
permis de conduire  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> |
   
## <a name="poland"></a>波兰

### <a name="format"></a>格式

14位数, 包含2个正斜杠
  
### <a name="pattern"></a>模式

14位数和2正斜杠:
  
-  五位数字 
    
- 一个正斜杠 
    
- 两位数字
    
- 一个正斜杠 
    
- 七个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_poland_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_poland_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_poland_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> prawo jazdy  <br/> |
   
## <a name="portugal"></a>葡萄牙

### <a name="format"></a>格式

两个字母后跟指定模式中的七个数字
  
### <a name="pattern"></a>模式

两个字母后跟七个包含特殊字符的数字:
  
-  两个字母 (不区分大小写) 
    
- 一个连字符 
    
- 六位数字
    
- 一个空格
    
- 一个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_portugal_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_portugal_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_portugal_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> carteira de motorista  <br/> |
   
## <a name="romania"></a>罗马尼亚

### <a name="format"></a>格式

一个字符后跟八个数字
  
### <a name="pattern"></a>模式

一个字符后跟八个数字:
  
-  一个字母 (不区分大小写) 或数字 
    
- 八个数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_romania_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_romania_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_romania_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> permis de conducere  <br/> |
   
## <a name="slovakia"></a>斯洛伐克

### <a name="format"></a>格式

一个字符后跟七个数字
  
### <a name="pattern"></a>模式

一个字符后跟七个数字
  
- 一个字母 (不区分大小写) 或数字
    
-  七个数字 
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_slovakia_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_slovakia_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_slovakia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> vodičský preukaz  <br/> |
   
## <a name="slovenia"></a>斯诺文尼亚

### <a name="format"></a>格式

9个数字, 不带空格和分隔符
  
### <a name="pattern"></a>模式

九个数字
  
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_slovenia_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_slovenia_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_slovenia_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> vozniško dovoljenje  <br/> |
   
## <a name="spain"></a>西班牙

### <a name="format"></a>格式

8位数, 后跟一个字符
  
### <a name="pattern"></a>模式

8位数, 后跟一个字符:
  
-  八个数字 
    
- 一个数字或字母 (不区分大小写)
    
### <a name="checksum"></a>校验和

是
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 函数`Func_spain_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_spain_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>关键字

| |
|**Keywords_spain_eu_driver's_license_number**|
|:-----|
|dlno #  <br/> dl#  <br/> 驱动程序许可证。  <br/> 驱动程序许可证  <br/> driver license  <br/> drivers licence  <br/> drivers license  <br/> 驾驶许可证  <br/> driver's license  <br/> driving licence
  <br/> 驾驶执照  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证编号  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> 促进允许  <br/> 驾驶允许号码  <br/> permiso de conducción  <br/> permiso conducción  <br/> número licencia conducir  <br/> número de carnet de conducir  <br/> número carnet conducir  <br/> licencia conducir  <br/> número de permiso de conducir  <br/> número de permiso conducir  <br/> número permiso conducir  <br/> permiso conducir  <br/> licencia de manejo  <br/> el carnet de conducir  <br/> carnet conducir  <br/> |
   
## <a name="sweden"></a>瑞典

### <a name="format"></a>格式

10个数字, 包含连字符
  
### <a name="pattern"></a>模式

10位数, 包含连字符:
  
-  六位数字 
    
- 连字符
    
- 四位数字
    
### <a name="checksum"></a>校验和

否
  
### <a name="definition"></a>定义

在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：
  
- 正则表达式`Regex_sweden_eu_driver's_license_number`找到与该模式匹配的内容。 
    
- 找到了中`Keywords_sweden_eu_driver's_license_number`的关键字。 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>关键字

| |
|**Keywords_sweden_eu_driver's_license_number**|
|:-----|
|dl#  <br/> driver license  <br/> 驱动程序许可证编号  <br/> 驱动程序许可证  <br/> 驱动程序许可证。  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> 驾驶执照号码  <br/> 驾驶许可证编号  <br/> 驾驶执照号码  <br/> dlno #  <br/> körkort  <br/> |
   
## <a name="uk"></a>英国

有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)部分的 "英国驾 License 号码" 一节。
  
## <a name="see-also"></a>另请参阅

[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)


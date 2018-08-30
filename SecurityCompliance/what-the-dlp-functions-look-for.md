---
title: DLP 函数查找的内容
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: 敏感信息类型以特定模式查找和协作通过确保正确的格式、 强制实施校验和、 和在寻找相关关键字或其他信息。此功能的一些由内部函数执行。本主题介绍这些函数查找，以帮助您了解预定义的敏感信息类型的工作方式。
ms.openlocfilehash: 510f98e2b4e1d2480550f11026cf445be6ffc931
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013756"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 函数查找的内容

数据丢失防护 (DLP) 包括敏感信息类型，如信用卡号和欧盟借记卡号，可供您在您的 DLP 策略中使用。这些敏感信息类型需要特定的模式，并通过确保正确的格式、强制执行校验和以及查找相关的关键字或其他信息来进行确认。此功能的部分功能由内部函数执行。例如，信用卡号的敏感信息类型使用函数查找日期格式（如到期日期），以帮助证实某个数字是信用卡号。
  
本主题说明这些函数查找的内容，帮助您了解预定义的敏感信息类型的工作方式。有关详细信息，请参阅[What the sensitive information types look for](what-the-sensitive-information-types-look-for.md)。
  
## <a name="funcusdate"></a>Func_us_date

此函数查找美国中常用的格式的日期这包括格式"月/日/年"，"月-日-年"和"月日年"。不区分大小写的名称或个月的缩写。 
  
示例：
  
- 2016 年 12 月 2日，
    
- 2016 年 12 月 2 日
    
- 十进制 02 2016
    
- 2016 年 12/2
    
- 12/02/16
    
- 十进制-2-2016
    
- 12-2-16
    
可接受的月份名称：
  
- 英语
    
  - 年 1 月、 年 2 月，march、 April、 may，年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月，年 12 月
    
  - 1 月 2 月 3 月时间可能 6 年 7 月 8 月 9 月 10 月 11 月年 12 月。
    
## <a name="funceudate"></a>Func_eu_date

此函数查找欧盟（和美国以外的大多数地方）常用格式的日期。这包括格式“日/月/年”、“日-月-年”和“日月年”。月份的名称或缩写不区分大小写。
  
示例：
  
- 2 年 12 月 2016
    
- 02 dec 2016
    
- 2 年 12 月 16 日
    
- 2/12/2016
    
- 02/12/16
    
- 2016 年年 12 月 2 日
    
- 2-12-16
    
可接受的月份名称：
  
- 英语
    
  - 年 1 月、 年 2 月，march、 April、 may，年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月，年 12 月
    
  - 1 月 2 月 3 月时间可能 6 年 7 月 8 月 9 月 10 月 11 月年 12 月。
    
- 荷兰语
    
  - januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December
    
  - jan 日 maart apr mei jun 日年 8 月 sep sept oct okt 11 月和 dec
    
- 法语
    
  - janvier、 février、 mars、 avril、 这里、 juin juillet、 août、 septembre、 octobre、 novembre、 décembre
    
  - janv。févr。mars avril 这里 juin juil。août sept。10 月 11 月。déc。
    
- 德语
    
  - jänuar，februar，märz，年 4 月、 这里 juni juli，年 8 月、 年 9 月，oktober，年 11 月，dezember
    
  - Jan。 / Jän。2 月 März 时间这里 Juni Juli 8 月 9 月 Okt。11 月 Dez。
    
- 意大利语
    
  - gennaio、 febbraio、 marzo、 aprile、 maggio、 giugno、 luglio、 agosto、 settembre、 ottobre、 novembre、 dicembre
    
  - genn。febbr。mar。apr。magg。giugno luglio ag。设置。ott。11 月。词典。
    
- 葡萄牙语
    
  - janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev mar abr 这里 jun 日以前出 11 月 dez 设置
    
- 西班牙语
    
  - enero、 febrero、 marzo、 abril、 mayo 一起构建、 junio、 julio、 agosto、 septiembre、 octubre、 noviembre、 diciembre
    
  - enero 日。marzo abr.mayo 一起构建时间日。agosto 9 月/组。10 月 11 月。词典。
    
## <a name="funceudate1-deprecated"></a>Func_eu_date1（已弃用）

> [!NOTE]
> 此功能已被弃用，因为它支持仅葡萄牙语月份名称，现在包括在`Func_eu_date`上面的函数。 
  
此函数查找葡萄牙语中常用的格式的日期。此函数的格式是相同`Func_eu_date`、 都会仅在使用的语言。
  
示例：
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez 2016
    
- 2-12-16
    
可接受的月份名称：
  
- 葡萄牙语
    
  - janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev mar abr 这里 jun 日以前出 11 月 dez 设置
    
## <a name="funceudate2-deprecated"></a>Func_eu_date2（已弃用）

> [!NOTE]
> 此功能已被弃用，因为它支持仅荷兰语月份名称，现在包括在`Func_eu_date`上面的函数。 
  
此函数会查找具有荷兰语中常用的格式的日期。此函数的格式是相同`Func_eu_date`、 都会仅在使用的语言。
  
示例：
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei 2016
    
- 2-12-16
    
可接受的月份名称：
  
- 荷兰语
    
  - januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December
    
  - jan 日 maart apr mei jun 日年 8 月 sep sept oct okt 11 月和 dec
    
## <a name="funcexpirationdate"></a>Func_expiration_date

此函数查找常用 credit 和借记卡卡，排除天以月应用的格式的日期。此函数将匹配"月/年"，"月-年"，"[月份名称] 年"和"[月份缩写] 年"的格式的日期。不区分大小写的名称或个月的缩写。
  
示例
  
- MM/YY -- 例如，01/11 或 1/11
    
- MM/YYYY -- 例如，01/2011 或 1/2011
    
- MM-YY -- 例如，01-22 或 1-11
    
- MM-YYYY -- 例如，01-2000 或 1-2000
    
以下格式支持 YY 或 YYYY：
  
- Month-YYYY -- 例如，Jan-2010、january-2010、Jan-10 或 january-10
    
- Month YYYY -- 例如，january 2010、Jan 2010、january 10 或 Jan 10
    
- MonthYYYY -- 例如，january2010、Jan2010、january10 或 Jan10
    
- Month/YYYY-例如，"年 1 月/2010"或"Jan/2010"或"年 1 月/10"和"Jan/10"
    
可接受的月份名称：
  
- 英语
    
  - 年 1 月、 年 2 月，march、 April、 may，年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月，年 12 月
    
  - 一月二月 Mar 四月可能 6 年 7 月年 8 月 Sept Oct 11 月年 12 月
    
## <a name="funcusaddress"></a>Func_us_address

此函数查找美国州名或邮政缩写，后跟有效的邮政编码，就像在邮政地址中使用那样。邮政编码必须是与美国州名或缩写关联的正确邮政编码之一。不能用标点符号或字母分隔美国州名和邮政编码。
  
示例：
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    


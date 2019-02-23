---
title: DLP 函数查找的内容
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: 敏感信息类型查找特定模式, 并通过确保正确的格式设置、强制校验和来查找相关的关键字或其他信息来 corroborate。其中一些功能是由内部函数执行的。本主题说明这些函数查找的内容, 以帮助您了解预定义的敏感信息类型的工作原理。
ms.openlocfilehash: 55c740e892e92902b368b2dcf7b0999cbc60f3ed
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219352"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 函数查找的内容

数据丢失防护 (DLP) 包括敏感信息类型，如信用卡号和欧盟借记卡号，可供您在您的 DLP 策略中使用。这些敏感信息类型需要特定的模式，并通过确保正确的格式、强制执行校验和以及查找相关的关键字或其他信息来进行确认。此功能的部分功能由内部函数执行。例如，信用卡号的敏感信息类型使用函数查找日期格式（如到期日期），以帮助证实某个数字是信用卡号。
  
本主题说明这些函数查找的内容，帮助您了解预定义的敏感信息类型的工作方式。有关详细信息，请参阅[What the sensitive information types look for](what-the-sensitive-information-types-look-for.md)。
  
## <a name="funcusdate"></a>Func_us_date

此函数以美国常用格式查找日期这包括格式 "月/日/年"、"月-日-年" 和 "年月日"。月份的名称或缩写不区分大小写。 
  
示例：
  
- 2016年12月2日
    
- 2016年12月2日
    
- dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
可接受的月份名称：
  
- 英语
    
  - 一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月
    
  - 2003年4月4日. 5 月4月6月11月11月11月4日。
    
## <a name="funceudate"></a>Func_eu_date

此函数查找欧盟（和美国以外的大多数地方）常用格式的日期。这包括格式“日/月/年”、“日-月-年”和“日月年”。月份的名称或缩写不区分大小写。
  
示例：
  
- 2 Dec 2016
    
- 02年12月2016
    
- 2 Dec 16
    
- 2/12/2016
    
- 02/12/16
    
- 2016年12月2日
    
- 2-12-16
    
可接受的月份名称：
  
- 英语
    
  - 一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月
    
  - 2003年4月4日. 5 月4月6月11月11月11月4日。
    
- 荷兰语
    
  - januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December
    
  - 2004年1月1月 maart 日 mei 年9月8日9月9日 okt 年11月
    
- 法语
    
  - janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre
    
  - janv。févr。火星 avril mai juin juil。août 9 月。11月11日。déc。
    
- 德语
    
  - jänuar、februar、märz、四月、mai、juni juli、八月、九月、oktober、十一月、dezember
    
  - Jan./Jän。2003年 März 年4月 Juni Juli, Okt。Dez 年11月。
    
- 意大利语
    
  - gennaio、febbraio、marzo、aprile、maggio、giugno、luglio、agosto、settembre、ottobre、novembre、dicembre
    
  - genn。febbr。mar.四月.magg。giugno luglio ag。设置.ott。年11月.home.dic.
    
- 葡萄牙语
    
  - janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev mar abr mai 06 年6月前设置11月 dez
    
- 西班牙语
    
  - enero、febrero、marzo、abril、mayo、junio、julio、agosto、septiembre、octubre、noviembre、diciembre
    
  - enero 2003 年2月。marzo mayo 07 年6月 abr。agosto/set。11月11日。home.dic.
    
## <a name="funceudate1-deprecated"></a>Func_eu_date1（已弃用）

> [!NOTE]
> 此函数已被弃用, 因为它仅支持包含在上述`Func_eu_date`函数中的葡萄牙月名称。 
  
此函数使用葡萄牙语中常用的格式查找日期。此函数`Func_eu_date`的格式与使用的语言不同。
  
示例：
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
可接受的月份名称：
  
- 葡萄牙语
    
  - janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev mar abr mai 06 年6月前设置11月 dez
    
## <a name="funceudate2-deprecated"></a>Func_eu_date2（已弃用）

> [!NOTE]
> 此函数已被弃用, 因为它仅支持荷兰月份名称, 这些名称现在包含`Func_eu_date`在上述函数中。 
  
此函数查找在荷兰语中常用的格式的日期。此函数`Func_eu_date`的格式与使用的语言不同。
  
示例：
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
可接受的月份名称：
  
- 荷兰语
    
  - januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December
    
  - 2004年1月1月 maart 日 mei 年9月8日9月9日 okt 年11月
    
## <a name="funcexpirationdate"></a>Func_expiration_date

此函数查找信用卡和借记卡常用格式的日期, 其中不包括月份的天数。此函数将以 "月/年"、"月-年"、"[月 name] year" 和 "[月缩写] 年" 的格式匹配日期。月份的名称或缩写不区分大小写。
  
示例
  
- MM/YY -- 例如，01/11 或 1/11
    
- MM/YYYY -- 例如，01/2011 或 1/2011
    
- MM-YY -- 例如，01-22 或 1-11
    
- MM-YYYY -- 例如，01-2000 或 1-2000
    
以下格式支持 YY 或 YYYY：
  
- Month-YYYY -- 例如，Jan-2010、january-2010、Jan-10 或 january-10
    
- Month YYYY -- 例如，january 2010、Jan 2010、january 10 或 Jan 10
    
- MonthYYYY -- 例如，january2010、Jan2010、january10 或 Jan10
    
- Month/YYYY-例如, "一月/2010" 或 "jan/2010" 或 "一月/10" 或 "jan/10"
    
可接受的月份名称：
  
- 英语
    
  - 一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月
    
  - 2004年2月3月4月5月8日12月8月8日
    
## <a name="funcusaddress"></a>Func_us_address

此函数查找美国州名或邮政缩写，后跟有效的邮政编码，就像在邮政地址中使用那样。邮政编码必须是与美国州名或缩写关联的正确邮政编码之一。不能用标点符号或字母分隔美国州名和邮政编码。
  
示例：
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    


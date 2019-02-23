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
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="0cca2-105">DLP 函数查找的内容</span><span class="sxs-lookup"><span data-stu-id="0cca2-105">What the DLP functions look for</span></span>

<span data-ttu-id="0cca2-p102">数据丢失防护 (DLP) 包括敏感信息类型，如信用卡号和欧盟借记卡号，可供您在您的 DLP 策略中使用。这些敏感信息类型需要特定的模式，并通过确保正确的格式、强制执行校验和以及查找相关的关键字或其他信息来进行确认。此功能的部分功能由内部函数执行。例如，信用卡号的敏感信息类型使用函数查找日期格式（如到期日期），以帮助证实某个数字是信用卡号。</span><span class="sxs-lookup"><span data-stu-id="0cca2-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="0cca2-p103">本主题说明这些函数查找的内容，帮助您了解预定义的敏感信息类型的工作方式。有关详细信息，请参阅[What the sensitive information types look for](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="0cca2-p103">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work. For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="0cca2-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="0cca2-112">Func_us_date</span></span>

<span data-ttu-id="0cca2-p104">此函数以美国常用格式查找日期这包括格式 "月/日/年"、"月-日-年" 和 "年月日"。月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0cca2-p104">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ". The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="0cca2-115">示例：</span><span class="sxs-lookup"><span data-stu-id="0cca2-115">Examples:</span></span>
  
- <span data-ttu-id="0cca2-116">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="0cca2-116">December 2, 2016</span></span>
    
- <span data-ttu-id="0cca2-117">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="0cca2-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="0cca2-118">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-118">dec 02 2016</span></span>
    
- <span data-ttu-id="0cca2-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-119">12/2/2016</span></span>
    
- <span data-ttu-id="0cca2-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="0cca2-120">12/02/16</span></span>
    
- <span data-ttu-id="0cca2-121">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="0cca2-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="0cca2-122">12-2-16</span></span>
    
<span data-ttu-id="0cca2-123">可接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="0cca2-123">Accepted month names:</span></span>
  
- <span data-ttu-id="0cca2-124">英语</span><span class="sxs-lookup"><span data-stu-id="0cca2-124">English</span></span>
    
  - <span data-ttu-id="0cca2-125">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="0cca2-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="0cca2-126">2003年4月4日. 5 月4月6月11月11月11月4日。</span><span class="sxs-lookup"><span data-stu-id="0cca2-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="0cca2-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="0cca2-127">Func_eu_date</span></span>

<span data-ttu-id="0cca2-p105">此函数查找欧盟（和美国以外的大多数地方）常用格式的日期。这包括格式“日/月/年”、“日-月-年”和“日月年”。月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0cca2-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="0cca2-132">示例：</span><span class="sxs-lookup"><span data-stu-id="0cca2-132">Examples:</span></span>
  
- <span data-ttu-id="0cca2-133">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="0cca2-134">02年12月2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-134">02 dec 2016</span></span>
    
- <span data-ttu-id="0cca2-135">2 Dec 16</span><span class="sxs-lookup"><span data-stu-id="0cca2-135">2 Dec 16</span></span>
    
- <span data-ttu-id="0cca2-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-136">2/12/2016</span></span>
    
- <span data-ttu-id="0cca2-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="0cca2-137">02/12/16</span></span>
    
- <span data-ttu-id="0cca2-138">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="0cca2-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="0cca2-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="0cca2-139">2-12-16</span></span>
    
<span data-ttu-id="0cca2-140">可接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="0cca2-140">Accepted month names:</span></span>
  
- <span data-ttu-id="0cca2-141">英语</span><span class="sxs-lookup"><span data-stu-id="0cca2-141">English</span></span>
    
  - <span data-ttu-id="0cca2-142">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="0cca2-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="0cca2-143">2003年4月4日. 5 月4月6月11月11月11月4日。</span><span class="sxs-lookup"><span data-stu-id="0cca2-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="0cca2-144">荷兰语</span><span class="sxs-lookup"><span data-stu-id="0cca2-144">Dutch</span></span>
    
  - <span data-ttu-id="0cca2-145">januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December</span><span class="sxs-lookup"><span data-stu-id="0cca2-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="0cca2-146">2004年1月1月 maart 日 mei 年9月8日9月9日 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="0cca2-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="0cca2-147">法语</span><span class="sxs-lookup"><span data-stu-id="0cca2-147">French</span></span>
    
  - <span data-ttu-id="0cca2-148">janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre</span><span class="sxs-lookup"><span data-stu-id="0cca2-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="0cca2-p106">janv。févr。火星 avril mai juin juil。août 9 月。11月11日。déc。</span><span class="sxs-lookup"><span data-stu-id="0cca2-p106">janv. févr. mars avril mai juin juil. août sept. oct. nov. déc.</span></span>
    
- <span data-ttu-id="0cca2-156">德语</span><span class="sxs-lookup"><span data-stu-id="0cca2-156">German</span></span>
    
  - <span data-ttu-id="0cca2-157">jänuar、februar、märz、四月、mai、juni juli、八月、九月、oktober、十一月、dezember</span><span class="sxs-lookup"><span data-stu-id="0cca2-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="0cca2-p107">Jan./Jän。2003年 März 年4月 Juni Juli, Okt。Dez 年11月。</span><span class="sxs-lookup"><span data-stu-id="0cca2-p107">Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span></span>
    
- <span data-ttu-id="0cca2-161">意大利语</span><span class="sxs-lookup"><span data-stu-id="0cca2-161">Italian</span></span>
    
  - <span data-ttu-id="0cca2-162">gennaio、febbraio、marzo、aprile、maggio、giugno、luglio、agosto、settembre、ottobre、novembre、dicembre</span><span class="sxs-lookup"><span data-stu-id="0cca2-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="0cca2-p108">genn。febbr。mar.四月.magg。giugno luglio ag。设置.ott。年11月.home.dic.</span><span class="sxs-lookup"><span data-stu-id="0cca2-p108">genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.</span></span>
    
- <span data-ttu-id="0cca2-173">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="0cca2-173">Portuguese</span></span>
    
  - <span data-ttu-id="0cca2-174">janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="0cca2-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="0cca2-175">jan fev mar abr mai 06 年6月前设置11月 dez</span><span class="sxs-lookup"><span data-stu-id="0cca2-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="0cca2-176">西班牙语</span><span class="sxs-lookup"><span data-stu-id="0cca2-176">Spanish</span></span>
    
  - <span data-ttu-id="0cca2-177">enero、febrero、marzo、abril、mayo、junio、julio、agosto、septiembre、octubre、noviembre、diciembre</span><span class="sxs-lookup"><span data-stu-id="0cca2-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="0cca2-p109">enero 2003 年2月。marzo mayo 07 年6月 abr。agosto/set。11月11日。home.dic.</span><span class="sxs-lookup"><span data-stu-id="0cca2-p109">enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="0cca2-186">Func_eu_date1（已弃用）</span><span class="sxs-lookup"><span data-stu-id="0cca2-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="0cca2-187">此函数已被弃用, 因为它仅支持包含在上述`Func_eu_date`函数中的葡萄牙月名称。</span><span class="sxs-lookup"><span data-stu-id="0cca2-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="0cca2-p110">此函数使用葡萄牙语中常用的格式查找日期。此函数`Func_eu_date`的格式与使用的语言不同。</span><span class="sxs-lookup"><span data-stu-id="0cca2-p110">This function looks for a date in the format commonly used in Portuguese. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="0cca2-190">示例：</span><span class="sxs-lookup"><span data-stu-id="0cca2-190">Examples:</span></span>
  
- <span data-ttu-id="0cca2-191">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="0cca2-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-192">02 dez 2016</span></span>
    
- <span data-ttu-id="0cca2-193">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="0cca2-193">2 Dez 16</span></span>
    
- <span data-ttu-id="0cca2-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-194">2/12/2016</span></span>
    
- <span data-ttu-id="0cca2-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="0cca2-195">02/12/16</span></span>
    
- <span data-ttu-id="0cca2-196">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="0cca2-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="0cca2-197">2-12-16</span></span>
    
<span data-ttu-id="0cca2-198">可接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="0cca2-198">Accepted month names:</span></span>
  
- <span data-ttu-id="0cca2-199">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="0cca2-199">Portuguese</span></span>
    
  - <span data-ttu-id="0cca2-200">janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="0cca2-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="0cca2-201">jan fev mar abr mai 06 年6月前设置11月 dez</span><span class="sxs-lookup"><span data-stu-id="0cca2-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="0cca2-202">Func_eu_date2（已弃用）</span><span class="sxs-lookup"><span data-stu-id="0cca2-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="0cca2-203">此函数已被弃用, 因为它仅支持荷兰月份名称, 这些名称现在包含`Func_eu_date`在上述函数中。</span><span class="sxs-lookup"><span data-stu-id="0cca2-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="0cca2-p111">此函数查找在荷兰语中常用的格式的日期。此函数`Func_eu_date`的格式与使用的语言不同。</span><span class="sxs-lookup"><span data-stu-id="0cca2-p111">This function looks for a date in the format commonly used in Dutch. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="0cca2-206">示例：</span><span class="sxs-lookup"><span data-stu-id="0cca2-206">Examples:</span></span>
  
- <span data-ttu-id="0cca2-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="0cca2-208">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-208">02 mei 2016</span></span>
    
- <span data-ttu-id="0cca2-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="0cca2-209">2 Mei 16</span></span>
    
- <span data-ttu-id="0cca2-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-210">2/12/2016</span></span>
    
- <span data-ttu-id="0cca2-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="0cca2-211">02/12/16</span></span>
    
- <span data-ttu-id="0cca2-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="0cca2-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="0cca2-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="0cca2-213">2-12-16</span></span>
    
<span data-ttu-id="0cca2-214">可接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="0cca2-214">Accepted month names:</span></span>
  
- <span data-ttu-id="0cca2-215">荷兰语</span><span class="sxs-lookup"><span data-stu-id="0cca2-215">Dutch</span></span>
    
  - <span data-ttu-id="0cca2-216">januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December</span><span class="sxs-lookup"><span data-stu-id="0cca2-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="0cca2-217">2004年1月1月 maart 日 mei 年9月8日9月9日 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="0cca2-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="0cca2-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="0cca2-218">Func_expiration_date</span></span>

<span data-ttu-id="0cca2-p112">此函数查找信用卡和借记卡常用格式的日期, 其中不包括月份的天数。此函数将以 "月/年"、"月-年"、"[月 name] year" 和 "[月缩写] 年" 的格式匹配日期。月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0cca2-p112">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months. This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="0cca2-222">示例</span><span class="sxs-lookup"><span data-stu-id="0cca2-222">Examples:</span></span>
  
- <span data-ttu-id="0cca2-223">MM/YY -- 例如，01/11 或 1/11</span><span class="sxs-lookup"><span data-stu-id="0cca2-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="0cca2-224">MM/YYYY -- 例如，01/2011 或 1/2011</span><span class="sxs-lookup"><span data-stu-id="0cca2-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="0cca2-225">MM-YY -- 例如，01-22 或 1-11</span><span class="sxs-lookup"><span data-stu-id="0cca2-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="0cca2-226">MM-YYYY -- 例如，01-2000 或 1-2000</span><span class="sxs-lookup"><span data-stu-id="0cca2-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="0cca2-227">以下格式支持 YY 或 YYYY：</span><span class="sxs-lookup"><span data-stu-id="0cca2-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="0cca2-228">Month-YYYY -- 例如，Jan-2010、january-2010、Jan-10 或 january-10</span><span class="sxs-lookup"><span data-stu-id="0cca2-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="0cca2-229">Month YYYY -- 例如，january 2010、Jan 2010、january 10 或 Jan 10</span><span class="sxs-lookup"><span data-stu-id="0cca2-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="0cca2-230">MonthYYYY -- 例如，january2010、Jan2010、january10 或 Jan10</span><span class="sxs-lookup"><span data-stu-id="0cca2-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="0cca2-231">Month/YYYY-例如, "一月/2010" 或 "jan/2010" 或 "一月/10" 或 "jan/10"</span><span class="sxs-lookup"><span data-stu-id="0cca2-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="0cca2-232">可接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="0cca2-232">Accepted month names:</span></span>
  
- <span data-ttu-id="0cca2-233">英语</span><span class="sxs-lookup"><span data-stu-id="0cca2-233">English</span></span>
    
  - <span data-ttu-id="0cca2-234">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="0cca2-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="0cca2-235">2004年2月3月4月5月8日12月8月8日</span><span class="sxs-lookup"><span data-stu-id="0cca2-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="0cca2-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="0cca2-236">Func_us_address</span></span>

<span data-ttu-id="0cca2-p113">此函数查找美国州名或邮政缩写，后跟有效的邮政编码，就像在邮政地址中使用那样。邮政编码必须是与美国州名或缩写关联的正确邮政编码之一。不能用标点符号或字母分隔美国州名和邮政编码。</span><span class="sxs-lookup"><span data-stu-id="0cca2-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="0cca2-240">示例：</span><span class="sxs-lookup"><span data-stu-id="0cca2-240">Examples:</span></span>
  
- <span data-ttu-id="0cca2-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="0cca2-241">Washington 98052</span></span>
    
- <span data-ttu-id="0cca2-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="0cca2-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="0cca2-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="0cca2-243">WA 98052</span></span>
    
- <span data-ttu-id="0cca2-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="0cca2-244">WA 98052-9998</span></span>
    


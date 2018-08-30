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
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="2b421-105">DLP 函数查找的内容</span><span class="sxs-lookup"><span data-stu-id="2b421-105">What the DLP functions look for</span></span>

<span data-ttu-id="2b421-p102">数据丢失防护 (DLP) 包括敏感信息类型，如信用卡号和欧盟借记卡号，可供您在您的 DLP 策略中使用。这些敏感信息类型需要特定的模式，并通过确保正确的格式、强制执行校验和以及查找相关的关键字或其他信息来进行确认。此功能的部分功能由内部函数执行。例如，信用卡号的敏感信息类型使用函数查找日期格式（如到期日期），以帮助证实某个数字是信用卡号。</span><span class="sxs-lookup"><span data-stu-id="2b421-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="2b421-p103">本主题说明这些函数查找的内容，帮助您了解预定义的敏感信息类型的工作方式。有关详细信息，请参阅[What the sensitive information types look for](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="2b421-p103">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work. For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="2b421-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="2b421-112">Func_us_date</span></span>

<span data-ttu-id="2b421-p104">此函数查找美国中常用的格式的日期这包括格式"月/日/年"，"月-日-年"和"月日年"。不区分大小写的名称或个月的缩写。</span><span class="sxs-lookup"><span data-stu-id="2b421-p104">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ". The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="2b421-115">示例：</span><span class="sxs-lookup"><span data-stu-id="2b421-115">Examples:</span></span>
  
- <span data-ttu-id="2b421-116">2016 年 12 月 2日，</span><span class="sxs-lookup"><span data-stu-id="2b421-116">December 2, 2016</span></span>
    
- <span data-ttu-id="2b421-117">2016 年 12 月 2 日</span><span class="sxs-lookup"><span data-stu-id="2b421-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="2b421-118">十进制 02 2016</span><span class="sxs-lookup"><span data-stu-id="2b421-118">dec 02 2016</span></span>
    
- <span data-ttu-id="2b421-119">2016 年 12/2</span><span class="sxs-lookup"><span data-stu-id="2b421-119">12/2/2016</span></span>
    
- <span data-ttu-id="2b421-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="2b421-120">12/02/16</span></span>
    
- <span data-ttu-id="2b421-121">十进制-2-2016</span><span class="sxs-lookup"><span data-stu-id="2b421-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="2b421-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="2b421-122">12-2-16</span></span>
    
<span data-ttu-id="2b421-123">可接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="2b421-123">Accepted month names:</span></span>
  
- <span data-ttu-id="2b421-124">英语</span><span class="sxs-lookup"><span data-stu-id="2b421-124">English</span></span>
    
  - <span data-ttu-id="2b421-125">年 1 月、 年 2 月，march、 April、 may，年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月，年 12 月</span><span class="sxs-lookup"><span data-stu-id="2b421-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="2b421-126">1 月 2 月 3 月时间可能 6 年 7 月 8 月 9 月 10 月 11 月年 12 月。</span><span class="sxs-lookup"><span data-stu-id="2b421-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="2b421-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="2b421-127">Func_eu_date</span></span>

<span data-ttu-id="2b421-p105">此函数查找欧盟（和美国以外的大多数地方）常用格式的日期。这包括格式“日/月/年”、“日-月-年”和“日月年”。月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="2b421-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="2b421-132">示例：</span><span class="sxs-lookup"><span data-stu-id="2b421-132">Examples:</span></span>
  
- <span data-ttu-id="2b421-133">2 年 12 月 2016</span><span class="sxs-lookup"><span data-stu-id="2b421-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="2b421-134">02 dec 2016</span><span class="sxs-lookup"><span data-stu-id="2b421-134">02 dec 2016</span></span>
    
- <span data-ttu-id="2b421-135">2 年 12 月 16 日</span><span class="sxs-lookup"><span data-stu-id="2b421-135">2 Dec 16</span></span>
    
- <span data-ttu-id="2b421-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="2b421-136">2/12/2016</span></span>
    
- <span data-ttu-id="2b421-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="2b421-137">02/12/16</span></span>
    
- <span data-ttu-id="2b421-138">2016 年年 12 月 2 日</span><span class="sxs-lookup"><span data-stu-id="2b421-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="2b421-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="2b421-139">2-12-16</span></span>
    
<span data-ttu-id="2b421-140">可接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="2b421-140">Accepted month names:</span></span>
  
- <span data-ttu-id="2b421-141">英语</span><span class="sxs-lookup"><span data-stu-id="2b421-141">English</span></span>
    
  - <span data-ttu-id="2b421-142">年 1 月、 年 2 月，march、 April、 may，年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月，年 12 月</span><span class="sxs-lookup"><span data-stu-id="2b421-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="2b421-143">1 月 2 月 3 月时间可能 6 年 7 月 8 月 9 月 10 月 11 月年 12 月。</span><span class="sxs-lookup"><span data-stu-id="2b421-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="2b421-144">荷兰语</span><span class="sxs-lookup"><span data-stu-id="2b421-144">Dutch</span></span>
    
  - <span data-ttu-id="2b421-145">januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December</span><span class="sxs-lookup"><span data-stu-id="2b421-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="2b421-146">jan 日 maart apr mei jun 日年 8 月 sep sept oct okt 11 月和 dec</span><span class="sxs-lookup"><span data-stu-id="2b421-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="2b421-147">法语</span><span class="sxs-lookup"><span data-stu-id="2b421-147">French</span></span>
    
  - <span data-ttu-id="2b421-148">janvier、 février、 mars、 avril、 这里、 juin juillet、 août、 septembre、 octobre、 novembre、 décembre</span><span class="sxs-lookup"><span data-stu-id="2b421-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="2b421-p106">janv。févr。mars avril 这里 juin juil。août sept。10 月 11 月。déc。</span><span class="sxs-lookup"><span data-stu-id="2b421-p106">janv. févr. mars avril mai juin juil. août sept. oct. nov. déc.</span></span>
    
- <span data-ttu-id="2b421-156">德语</span><span class="sxs-lookup"><span data-stu-id="2b421-156">German</span></span>
    
  - <span data-ttu-id="2b421-157">jänuar，februar，märz，年 4 月、 这里 juni juli，年 8 月、 年 9 月，oktober，年 11 月，dezember</span><span class="sxs-lookup"><span data-stu-id="2b421-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="2b421-p107">Jan。 / Jän。2 月 März 时间这里 Juni Juli 8 月 9 月 Okt。11 月 Dez。</span><span class="sxs-lookup"><span data-stu-id="2b421-p107">Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span></span>
    
- <span data-ttu-id="2b421-161">意大利语</span><span class="sxs-lookup"><span data-stu-id="2b421-161">Italian</span></span>
    
  - <span data-ttu-id="2b421-162">gennaio、 febbraio、 marzo、 aprile、 maggio、 giugno、 luglio、 agosto、 settembre、 ottobre、 novembre、 dicembre</span><span class="sxs-lookup"><span data-stu-id="2b421-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="2b421-p108">genn。febbr。mar。apr。magg。giugno luglio ag。设置。ott。11 月。词典。</span><span class="sxs-lookup"><span data-stu-id="2b421-p108">genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.</span></span>
    
- <span data-ttu-id="2b421-173">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="2b421-173">Portuguese</span></span>
    
  - <span data-ttu-id="2b421-174">janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="2b421-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="2b421-175">jan fev mar abr 这里 jun 日以前出 11 月 dez 设置</span><span class="sxs-lookup"><span data-stu-id="2b421-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="2b421-176">西班牙语</span><span class="sxs-lookup"><span data-stu-id="2b421-176">Spanish</span></span>
    
  - <span data-ttu-id="2b421-177">enero、 febrero、 marzo、 abril、 mayo 一起构建、 junio、 julio、 agosto、 septiembre、 octubre、 noviembre、 diciembre</span><span class="sxs-lookup"><span data-stu-id="2b421-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="2b421-p109">enero 日。marzo abr.mayo 一起构建时间日。agosto 9 月/组。10 月 11 月。词典。</span><span class="sxs-lookup"><span data-stu-id="2b421-p109">enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="2b421-186">Func_eu_date1（已弃用）</span><span class="sxs-lookup"><span data-stu-id="2b421-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="2b421-187">此功能已被弃用，因为它支持仅葡萄牙语月份名称，现在包括在`Func_eu_date`上面的函数。</span><span class="sxs-lookup"><span data-stu-id="2b421-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="2b421-p110">此函数查找葡萄牙语中常用的格式的日期。此函数的格式是相同`Func_eu_date`、 都会仅在使用的语言。</span><span class="sxs-lookup"><span data-stu-id="2b421-p110">This function looks for a date in the format commonly used in Portuguese. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="2b421-190">示例：</span><span class="sxs-lookup"><span data-stu-id="2b421-190">Examples:</span></span>
  
- <span data-ttu-id="2b421-191">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="2b421-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="2b421-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="2b421-192">02 dez 2016</span></span>
    
- <span data-ttu-id="2b421-193">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="2b421-193">2 Dez 16</span></span>
    
- <span data-ttu-id="2b421-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="2b421-194">2/12/2016</span></span>
    
- <span data-ttu-id="2b421-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="2b421-195">02/12/16</span></span>
    
- <span data-ttu-id="2b421-196">2-Dez 2016</span><span class="sxs-lookup"><span data-stu-id="2b421-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="2b421-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="2b421-197">2-12-16</span></span>
    
<span data-ttu-id="2b421-198">可接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="2b421-198">Accepted month names:</span></span>
  
- <span data-ttu-id="2b421-199">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="2b421-199">Portuguese</span></span>
    
  - <span data-ttu-id="2b421-200">janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="2b421-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="2b421-201">jan fev mar abr 这里 jun 日以前出 11 月 dez 设置</span><span class="sxs-lookup"><span data-stu-id="2b421-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="2b421-202">Func_eu_date2（已弃用）</span><span class="sxs-lookup"><span data-stu-id="2b421-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="2b421-203">此功能已被弃用，因为它支持仅荷兰语月份名称，现在包括在`Func_eu_date`上面的函数。</span><span class="sxs-lookup"><span data-stu-id="2b421-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="2b421-p111">此函数会查找具有荷兰语中常用的格式的日期。此函数的格式是相同`Func_eu_date`、 都会仅在使用的语言。</span><span class="sxs-lookup"><span data-stu-id="2b421-p111">This function looks for a date in the format commonly used in Dutch. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="2b421-206">示例：</span><span class="sxs-lookup"><span data-stu-id="2b421-206">Examples:</span></span>
  
- <span data-ttu-id="2b421-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="2b421-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="2b421-208">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="2b421-208">02 mei 2016</span></span>
    
- <span data-ttu-id="2b421-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="2b421-209">2 Mei 16</span></span>
    
- <span data-ttu-id="2b421-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="2b421-210">2/12/2016</span></span>
    
- <span data-ttu-id="2b421-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="2b421-211">02/12/16</span></span>
    
- <span data-ttu-id="2b421-212">2-Mei 2016</span><span class="sxs-lookup"><span data-stu-id="2b421-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="2b421-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="2b421-213">2-12-16</span></span>
    
<span data-ttu-id="2b421-214">可接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="2b421-214">Accepted month names:</span></span>
  
- <span data-ttu-id="2b421-215">荷兰语</span><span class="sxs-lookup"><span data-stu-id="2b421-215">Dutch</span></span>
    
  - <span data-ttu-id="2b421-216">januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December</span><span class="sxs-lookup"><span data-stu-id="2b421-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="2b421-217">jan 日 maart apr mei jun 日年 8 月 sep sept oct okt 11 月和 dec</span><span class="sxs-lookup"><span data-stu-id="2b421-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="2b421-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="2b421-218">Func_expiration_date</span></span>

<span data-ttu-id="2b421-p112">此函数查找常用 credit 和借记卡卡，排除天以月应用的格式的日期。此函数将匹配"月/年"，"月-年"，"[月份名称] 年"和"[月份缩写] 年"的格式的日期。不区分大小写的名称或个月的缩写。</span><span class="sxs-lookup"><span data-stu-id="2b421-p112">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months. This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="2b421-222">示例</span><span class="sxs-lookup"><span data-stu-id="2b421-222">Examples:</span></span>
  
- <span data-ttu-id="2b421-223">MM/YY -- 例如，01/11 或 1/11</span><span class="sxs-lookup"><span data-stu-id="2b421-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="2b421-224">MM/YYYY -- 例如，01/2011 或 1/2011</span><span class="sxs-lookup"><span data-stu-id="2b421-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="2b421-225">MM-YY -- 例如，01-22 或 1-11</span><span class="sxs-lookup"><span data-stu-id="2b421-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="2b421-226">MM-YYYY -- 例如，01-2000 或 1-2000</span><span class="sxs-lookup"><span data-stu-id="2b421-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="2b421-227">以下格式支持 YY 或 YYYY：</span><span class="sxs-lookup"><span data-stu-id="2b421-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="2b421-228">Month-YYYY -- 例如，Jan-2010、january-2010、Jan-10 或 january-10</span><span class="sxs-lookup"><span data-stu-id="2b421-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="2b421-229">Month YYYY -- 例如，january 2010、Jan 2010、january 10 或 Jan 10</span><span class="sxs-lookup"><span data-stu-id="2b421-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="2b421-230">MonthYYYY -- 例如，january2010、Jan2010、january10 或 Jan10</span><span class="sxs-lookup"><span data-stu-id="2b421-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="2b421-231">Month/YYYY-例如，"年 1 月/2010"或"Jan/2010"或"年 1 月/10"和"Jan/10"</span><span class="sxs-lookup"><span data-stu-id="2b421-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="2b421-232">可接受的月份名称：</span><span class="sxs-lookup"><span data-stu-id="2b421-232">Accepted month names:</span></span>
  
- <span data-ttu-id="2b421-233">英语</span><span class="sxs-lookup"><span data-stu-id="2b421-233">English</span></span>
    
  - <span data-ttu-id="2b421-234">年 1 月、 年 2 月，march、 April、 may，年 6 月、 年 7 月、 年 8 月、 年 9 月、 年 10 月、 年 11 月，年 12 月</span><span class="sxs-lookup"><span data-stu-id="2b421-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="2b421-235">一月二月 Mar 四月可能 6 年 7 月年 8 月 Sept Oct 11 月年 12 月</span><span class="sxs-lookup"><span data-stu-id="2b421-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="2b421-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="2b421-236">Func_us_address</span></span>

<span data-ttu-id="2b421-p113">此函数查找美国州名或邮政缩写，后跟有效的邮政编码，就像在邮政地址中使用那样。邮政编码必须是与美国州名或缩写关联的正确邮政编码之一。不能用标点符号或字母分隔美国州名和邮政编码。</span><span class="sxs-lookup"><span data-stu-id="2b421-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="2b421-240">示例：</span><span class="sxs-lookup"><span data-stu-id="2b421-240">Examples:</span></span>
  
- <span data-ttu-id="2b421-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="2b421-241">Washington 98052</span></span>
    
- <span data-ttu-id="2b421-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="2b421-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="2b421-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="2b421-243">WA 98052</span></span>
    
- <span data-ttu-id="2b421-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="2b421-244">WA 98052-9998</span></span>
    


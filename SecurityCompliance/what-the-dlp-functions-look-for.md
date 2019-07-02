---
title: DLP 函数查找的内容
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 敏感信息类型查找特定模式, 并通过确保正确的格式设置、强制校验和来查找相关的关键字或其他信息来 corroborate。 其中一些功能是由内部函数执行的。 本主题说明这些函数查找的内容, 以帮助您了解预定义的敏感信息类型的工作原理。
ms.openlocfilehash: 044920a7ff28ffc1c4338a642bc130ee07ef7264
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077998"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="a6fb9-105">DLP 函数查找的内容</span><span class="sxs-lookup"><span data-stu-id="a6fb9-105">What the DLP functions look for</span></span>

<span data-ttu-id="a6fb9-106">数据丢失防护 (DLP) 包括敏感信息类型, 如信用卡号和欧盟借记卡号, 可供您在 DLP 策略中使用。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-106">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="a6fb9-107">这些敏感信息类型查找特定模式, 并通过确保正确的格式设置、强制校验和来查找相关的关键字或其他信息来 corroborate。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-107">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="a6fb9-108">其中一些功能是由内部函数执行的。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-108">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="a6fb9-109">例如, 信用卡号敏感信息类型使用函数查找类似于到期日期的日期, 以帮助 corroborate 号码是信用卡号。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-109">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="a6fb9-110">本主题说明这些函数查找的内容, 以帮助您了解预定义的敏感信息类型的工作原理。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="a6fb9-111">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-111">For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="a6fb9-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="a6fb9-112">Func_us_date</span></span>

<span data-ttu-id="a6fb9-113">此函数以美国常用格式查找日期这包括格式 "月/日/年"、"月-日-年" 和 "年月日"。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="a6fb9-114">月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="a6fb9-115">示例：</span><span class="sxs-lookup"><span data-stu-id="a6fb9-115">Examples:</span></span>
  
- <span data-ttu-id="a6fb9-116">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="a6fb9-116">December 2, 2016</span></span>
    
- <span data-ttu-id="a6fb9-117">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="a6fb9-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="a6fb9-118">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-118">dec 02 2016</span></span>
    
- <span data-ttu-id="a6fb9-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-119">12/2/2016</span></span>
    
- <span data-ttu-id="a6fb9-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="a6fb9-120">12/02/16</span></span>
    
- <span data-ttu-id="a6fb9-121">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="a6fb9-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="a6fb9-122">12-2-16</span></span>
    
<span data-ttu-id="a6fb9-123">接受的月份名称:</span><span class="sxs-lookup"><span data-stu-id="a6fb9-123">Accepted month names:</span></span>
  
- <span data-ttu-id="a6fb9-124">英语</span><span class="sxs-lookup"><span data-stu-id="a6fb9-124">English</span></span>
    
  - <span data-ttu-id="a6fb9-125">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="a6fb9-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="a6fb9-126">2003年4月4日. 5 月4月6月11月11月11月4日。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="a6fb9-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="a6fb9-127">Func_eu_date</span></span>

<span data-ttu-id="a6fb9-128">此函数查找欧盟常用格式的日期</span><span class="sxs-lookup"><span data-stu-id="a6fb9-128">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="a6fb9-129">(以及美国以外的大多数位置)。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-129">(and most places outside the U.S.).</span></span> <span data-ttu-id="a6fb9-130">这包括格式 "日/月/年"、"日-月-年" 和 "年月日"。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-130">This includes the formats "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="a6fb9-131">月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-131">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="a6fb9-132">示例：</span><span class="sxs-lookup"><span data-stu-id="a6fb9-132">Examples:</span></span>
  
- <span data-ttu-id="a6fb9-133">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="a6fb9-134">02年12月2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-134">02 dec 2016</span></span>
    
- <span data-ttu-id="a6fb9-135">2 Dec 16</span><span class="sxs-lookup"><span data-stu-id="a6fb9-135">2 Dec 16</span></span>
    
- <span data-ttu-id="a6fb9-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-136">2/12/2016</span></span>
    
- <span data-ttu-id="a6fb9-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="a6fb9-137">02/12/16</span></span>
    
- <span data-ttu-id="a6fb9-138">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="a6fb9-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="a6fb9-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="a6fb9-139">2-12-16</span></span>
    
<span data-ttu-id="a6fb9-140">接受的月份名称:</span><span class="sxs-lookup"><span data-stu-id="a6fb9-140">Accepted month names:</span></span>
  
- <span data-ttu-id="a6fb9-141">英语</span><span class="sxs-lookup"><span data-stu-id="a6fb9-141">English</span></span>
    
  - <span data-ttu-id="a6fb9-142">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="a6fb9-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="a6fb9-143">2003年4月4日. 5 月4月6月11月11月11月4日。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="a6fb9-144">荷兰语</span><span class="sxs-lookup"><span data-stu-id="a6fb9-144">Dutch</span></span>
    
  - <span data-ttu-id="a6fb9-145">januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="a6fb9-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="a6fb9-146">2004年1月1月 maart 日 mei 年9月8日9月9日 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="a6fb9-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="a6fb9-147">法语</span><span class="sxs-lookup"><span data-stu-id="a6fb9-147">French</span></span>
    
  - <span data-ttu-id="a6fb9-148">janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre</span><span class="sxs-lookup"><span data-stu-id="a6fb9-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="a6fb9-149">janv.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-149">janv.</span></span> <span data-ttu-id="a6fb9-150">févr.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-150">févr.</span></span> <span data-ttu-id="a6fb9-151">火星 avril mai juin juil。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-151">mars avril mai juin juil.</span></span> <span data-ttu-id="a6fb9-152">août 9 月。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-152">août sept.</span></span> <span data-ttu-id="a6fb9-153">2008.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-153">oct.</span></span> <span data-ttu-id="a6fb9-154">年11月.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-154">nov.</span></span> <span data-ttu-id="a6fb9-155">déc.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-155">déc.</span></span>
    
- <span data-ttu-id="a6fb9-156">德语</span><span class="sxs-lookup"><span data-stu-id="a6fb9-156">German</span></span>
    
  - <span data-ttu-id="a6fb9-157">jänuar、februar、märz、四月、mai、juni juli、八月、九月、oktober、十一月、dezember</span><span class="sxs-lookup"><span data-stu-id="a6fb9-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="a6fb9-158">Jan./Jän。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-158">Jan./Jän.</span></span> <span data-ttu-id="a6fb9-159">2003年 März 年4月 Juni Juli, Okt。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="a6fb9-160">Dez 年11月。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="a6fb9-161">意大利语</span><span class="sxs-lookup"><span data-stu-id="a6fb9-161">Italian</span></span>
    
  - <span data-ttu-id="a6fb9-162">gennaio、febbraio、marzo、aprile、maggio、giugno、luglio、agosto、settembre、ottobre、novembre、dicembre</span><span class="sxs-lookup"><span data-stu-id="a6fb9-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="a6fb9-163">genn.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-163">genn.</span></span> <span data-ttu-id="a6fb9-164">febbr.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-164">febbr.</span></span> <span data-ttu-id="a6fb9-165">mar.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-165">mar.</span></span> <span data-ttu-id="a6fb9-166">四月.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-166">apr.</span></span> <span data-ttu-id="a6fb9-167">magg.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-167">magg.</span></span> <span data-ttu-id="a6fb9-168">giugno luglio ag。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-168">giugno luglio ag.</span></span> <span data-ttu-id="a6fb9-169">设置.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-169">sett.</span></span> <span data-ttu-id="a6fb9-170">ott.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-170">ott.</span></span> <span data-ttu-id="a6fb9-171">年11月.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-171">nov.</span></span> <span data-ttu-id="a6fb9-172">home.dic.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-172">dic.</span></span>
    
- <span data-ttu-id="a6fb9-173">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="a6fb9-173">Portuguese</span></span>
    
  - <span data-ttu-id="a6fb9-174">里约热内卢、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="a6fb9-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="a6fb9-175">jan fev mar abr mai 06 年6月前设置11月 dez</span><span class="sxs-lookup"><span data-stu-id="a6fb9-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="a6fb9-176">西班牙语</span><span class="sxs-lookup"><span data-stu-id="a6fb9-176">Spanish</span></span>
    
  - <span data-ttu-id="a6fb9-177">enero、febrero、marzo、abril、mayo、junio、julio、agosto、septiembre、octubre、noviembre、diciembre</span><span class="sxs-lookup"><span data-stu-id="a6fb9-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="a6fb9-178">enero 2003 年2月。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-178">enero feb.</span></span> <span data-ttu-id="a6fb9-179">marzo abr。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-179">marzo abr.</span></span> <span data-ttu-id="a6fb9-180">mayo 06。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-180">mayo jun.</span></span> <span data-ttu-id="a6fb9-181">年7月.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-181">jul.</span></span> <span data-ttu-id="a6fb9-182">agosto/set。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-182">agosto sept./set.</span></span> <span data-ttu-id="a6fb9-183">2008.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-183">oct.</span></span> <span data-ttu-id="a6fb9-184">年11月.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-184">nov.</span></span> <span data-ttu-id="a6fb9-185">home.dic.</span><span class="sxs-lookup"><span data-stu-id="a6fb9-185">dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="a6fb9-186">Func_eu_date1 (已弃用)</span><span class="sxs-lookup"><span data-stu-id="a6fb9-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="a6fb9-187">此函数已被弃用, 因为它仅支持包含在上述`Func_eu_date`函数中的葡萄牙月名称。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="a6fb9-188">此函数使用葡萄牙语中常用的格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="a6fb9-189">此函数`Func_eu_date`的格式与使用的语言不同。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="a6fb9-190">示例：</span><span class="sxs-lookup"><span data-stu-id="a6fb9-190">Examples:</span></span>
  
- <span data-ttu-id="a6fb9-191">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="a6fb9-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-192">02 dez 2016</span></span>
    
- <span data-ttu-id="a6fb9-193">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="a6fb9-193">2 Dez 16</span></span>
    
- <span data-ttu-id="a6fb9-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-194">2/12/2016</span></span>
    
- <span data-ttu-id="a6fb9-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="a6fb9-195">02/12/16</span></span>
    
- <span data-ttu-id="a6fb9-196">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="a6fb9-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="a6fb9-197">2-12-16</span></span>
    
<span data-ttu-id="a6fb9-198">接受的月份名称:</span><span class="sxs-lookup"><span data-stu-id="a6fb9-198">Accepted month names:</span></span>
  
- <span data-ttu-id="a6fb9-199">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="a6fb9-199">Portuguese</span></span>
    
  - <span data-ttu-id="a6fb9-200">里约热内卢、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="a6fb9-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="a6fb9-201">jan fev mar abr mai 06 年6月前设置11月 dez</span><span class="sxs-lookup"><span data-stu-id="a6fb9-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="a6fb9-202">Func_eu_date2 (已弃用)</span><span class="sxs-lookup"><span data-stu-id="a6fb9-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="a6fb9-203">此函数已被弃用, 因为它仅支持荷兰月份名称, 这些名称现在包含`Func_eu_date`在上述函数中。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="a6fb9-204">此函数查找在荷兰语中常用的格式的日期。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="a6fb9-205">此函数`Func_eu_date`的格式与使用的语言不同。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="a6fb9-206">示例：</span><span class="sxs-lookup"><span data-stu-id="a6fb9-206">Examples:</span></span>
  
- <span data-ttu-id="a6fb9-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="a6fb9-208">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-208">02 mei 2016</span></span>
    
- <span data-ttu-id="a6fb9-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="a6fb9-209">2 Mei 16</span></span>
    
- <span data-ttu-id="a6fb9-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-210">2/12/2016</span></span>
    
- <span data-ttu-id="a6fb9-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="a6fb9-211">02/12/16</span></span>
    
- <span data-ttu-id="a6fb9-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="a6fb9-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="a6fb9-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="a6fb9-213">2-12-16</span></span>
    
<span data-ttu-id="a6fb9-214">接受的月份名称:</span><span class="sxs-lookup"><span data-stu-id="a6fb9-214">Accepted month names:</span></span>
  
- <span data-ttu-id="a6fb9-215">荷兰语</span><span class="sxs-lookup"><span data-stu-id="a6fb9-215">Dutch</span></span>
    
  - <span data-ttu-id="a6fb9-216">januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="a6fb9-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="a6fb9-217">2004年1月1月 maart 日 mei 年9月8日9月9日 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="a6fb9-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="a6fb9-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="a6fb9-218">Func_expiration_date</span></span>

<span data-ttu-id="a6fb9-219">此函数查找信用卡和借记卡常用格式的日期, 其中不包括月份的天数。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="a6fb9-220">此函数将以 "月/年"、"月-年"、"[月 name] year" 和 "[月缩写] 年" 的格式匹配日期。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="a6fb9-221">月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="a6fb9-222">示例：</span><span class="sxs-lookup"><span data-stu-id="a6fb9-222">Examples:</span></span>
  
- <span data-ttu-id="a6fb9-223">MM/YY--例如, 01/11 或1/11</span><span class="sxs-lookup"><span data-stu-id="a6fb9-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="a6fb9-224">MM/YYYY--例如, 01/2011 或1/2011</span><span class="sxs-lookup"><span data-stu-id="a6fb9-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="a6fb9-225">MM-YY--例如, 01-22 或1-11</span><span class="sxs-lookup"><span data-stu-id="a6fb9-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="a6fb9-226">MM--例如, 01-2000 或1-2000</span><span class="sxs-lookup"><span data-stu-id="a6fb9-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="a6fb9-227">以下格式支持 YY 或 YYYY:</span><span class="sxs-lookup"><span data-stu-id="a6fb9-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="a6fb9-228">年月日-例如,。Jan-2010 或一月-2010 或 Jan-10 或一月-10</span><span class="sxs-lookup"><span data-stu-id="a6fb9-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="a6fb9-229">年月日-例如, "一月 2010" 或 "Jan 2010" 或 "Jan 10" 或 "Jan 10"</span><span class="sxs-lookup"><span data-stu-id="a6fb9-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="a6fb9-230">MonthYYYY-例如, "january2010" 或 "Jan2010" 或 "january10" 或 "Jan10"</span><span class="sxs-lookup"><span data-stu-id="a6fb9-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="a6fb9-231">Month/YYYY-例如, "一月/2010" 或 "Jan/2010" 或 "一月/10" 或 "Jan/10"</span><span class="sxs-lookup"><span data-stu-id="a6fb9-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="a6fb9-232">接受的月份名称:</span><span class="sxs-lookup"><span data-stu-id="a6fb9-232">Accepted month names:</span></span>
  
- <span data-ttu-id="a6fb9-233">英语</span><span class="sxs-lookup"><span data-stu-id="a6fb9-233">English</span></span>
    
  - <span data-ttu-id="a6fb9-234">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="a6fb9-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="a6fb9-235">2004年2月3月4月5月8日12月8月8日</span><span class="sxs-lookup"><span data-stu-id="a6fb9-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="a6fb9-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="a6fb9-236">Func_us_address</span></span>

<span data-ttu-id="a6fb9-237">此函数查找美国的状态名称或邮政缩写, 后跟有效的邮政编码, 就像在邮政地址中使用一样。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-237">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses.</span></span> <span data-ttu-id="a6fb9-238">邮政编码必须是与美国省/市/自治区名称或缩写相关联的正确邮政编码之一。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-238">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="a6fb9-239">美国省/市/自治区名称和邮政编码不能由标点符号或字母分隔。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-239">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="a6fb9-240">示例：</span><span class="sxs-lookup"><span data-stu-id="a6fb9-240">Examples:</span></span>
  
- <span data-ttu-id="a6fb9-241">华盛顿98052</span><span class="sxs-lookup"><span data-stu-id="a6fb9-241">Washington 98052</span></span>
    
- <span data-ttu-id="a6fb9-242">华盛顿98052-9998</span><span class="sxs-lookup"><span data-stu-id="a6fb9-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="a6fb9-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="a6fb9-243">WA 98052</span></span>
    
- <span data-ttu-id="a6fb9-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="a6fb9-244">WA 98052-9998</span></span>
    


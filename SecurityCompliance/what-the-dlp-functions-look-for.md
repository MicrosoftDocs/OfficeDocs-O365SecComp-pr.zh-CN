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
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 敏感信息类型查找特定模式, 并通过确保正确的格式设置、强制校验和来查找相关的关键字或其他信息来 corroborate。 其中一些功能是由内部函数执行的。 本主题说明这些函数查找的内容, 以帮助您了解预定义的敏感信息类型的工作原理。
ms.openlocfilehash: f64a4f174483b2aa57520991dcf85d13515074fb
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454964"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="029a8-105">DLP 函数查找的内容</span><span class="sxs-lookup"><span data-stu-id="029a8-105">What the DLP functions look for</span></span>

<span data-ttu-id="029a8-106">数据丢失防护 (DLP) 包括敏感信息类型, 如信用卡号和欧盟借记卡号, 可供您在 DLP 策略中使用。</span><span class="sxs-lookup"><span data-stu-id="029a8-106">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="029a8-107">这些敏感信息类型查找特定模式, 并通过确保正确的格式设置、强制校验和来查找相关的关键字或其他信息来 corroborate。</span><span class="sxs-lookup"><span data-stu-id="029a8-107">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="029a8-108">其中一些功能是由内部函数执行的。</span><span class="sxs-lookup"><span data-stu-id="029a8-108">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="029a8-109">例如, 信用卡号敏感信息类型使用函数查找类似于到期日期的日期, 以帮助 corroborate 号码是信用卡号。</span><span class="sxs-lookup"><span data-stu-id="029a8-109">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="029a8-110">本主题说明这些函数查找的内容, 以帮助您了解预定义的敏感信息类型的工作原理。</span><span class="sxs-lookup"><span data-stu-id="029a8-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="029a8-111">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="029a8-111">For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="029a8-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="029a8-112">Func_us_date</span></span>

<span data-ttu-id="029a8-113">此函数以美国常用格式查找日期这包括格式 "月/日/年"、"月-日-年" 和 "年月日"。</span><span class="sxs-lookup"><span data-stu-id="029a8-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="029a8-114">月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="029a8-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="029a8-115">示例：</span><span class="sxs-lookup"><span data-stu-id="029a8-115">Examples:</span></span>
  
- <span data-ttu-id="029a8-116">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="029a8-116">December 2, 2016</span></span>
    
- <span data-ttu-id="029a8-117">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="029a8-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="029a8-118">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="029a8-118">dec 02 2016</span></span>
    
- <span data-ttu-id="029a8-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="029a8-119">12/2/2016</span></span>
    
- <span data-ttu-id="029a8-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="029a8-120">12/02/16</span></span>
    
- <span data-ttu-id="029a8-121">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="029a8-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="029a8-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="029a8-122">12-2-16</span></span>
    
<span data-ttu-id="029a8-123">接受的月份名称:</span><span class="sxs-lookup"><span data-stu-id="029a8-123">Accepted month names:</span></span>
  
- <span data-ttu-id="029a8-124">英语</span><span class="sxs-lookup"><span data-stu-id="029a8-124">English</span></span>
    
  - <span data-ttu-id="029a8-125">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="029a8-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="029a8-126">2003年4月4日. 5 月4月6月11月11月11月4日。</span><span class="sxs-lookup"><span data-stu-id="029a8-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="029a8-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="029a8-127">Func_eu_date</span></span>

<span data-ttu-id="029a8-128">此函数查找欧盟常用格式的日期</span><span class="sxs-lookup"><span data-stu-id="029a8-128">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="029a8-129">(以及美国以外的大多数位置)。</span><span class="sxs-lookup"><span data-stu-id="029a8-129">(and most places outside the U.S.).</span></span> <span data-ttu-id="029a8-130">这包括格式 "日/月/年"、"日-月-年" 和 "年月日"。</span><span class="sxs-lookup"><span data-stu-id="029a8-130">This includes the formats "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="029a8-131">月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="029a8-131">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="029a8-132">示例：</span><span class="sxs-lookup"><span data-stu-id="029a8-132">Examples:</span></span>
  
- <span data-ttu-id="029a8-133">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="029a8-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="029a8-134">02年12月2016</span><span class="sxs-lookup"><span data-stu-id="029a8-134">02 dec 2016</span></span>
    
- <span data-ttu-id="029a8-135">2 Dec 16</span><span class="sxs-lookup"><span data-stu-id="029a8-135">2 Dec 16</span></span>
    
- <span data-ttu-id="029a8-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="029a8-136">2/12/2016</span></span>
    
- <span data-ttu-id="029a8-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="029a8-137">02/12/16</span></span>
    
- <span data-ttu-id="029a8-138">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="029a8-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="029a8-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="029a8-139">2-12-16</span></span>
    
<span data-ttu-id="029a8-140">接受的月份名称:</span><span class="sxs-lookup"><span data-stu-id="029a8-140">Accepted month names:</span></span>
  
- <span data-ttu-id="029a8-141">英语</span><span class="sxs-lookup"><span data-stu-id="029a8-141">English</span></span>
    
  - <span data-ttu-id="029a8-142">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="029a8-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="029a8-143">2003年4月4日. 5 月4月6月11月11月11月4日。</span><span class="sxs-lookup"><span data-stu-id="029a8-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="029a8-144">荷兰语</span><span class="sxs-lookup"><span data-stu-id="029a8-144">Dutch</span></span>
    
  - <span data-ttu-id="029a8-145">januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="029a8-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="029a8-146">2004年1月1月 maart 日 mei 年9月8日9月9日 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="029a8-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="029a8-147">法语</span><span class="sxs-lookup"><span data-stu-id="029a8-147">French</span></span>
    
  - <span data-ttu-id="029a8-148">janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre</span><span class="sxs-lookup"><span data-stu-id="029a8-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="029a8-149">janv。</span><span class="sxs-lookup"><span data-stu-id="029a8-149">janv.</span></span> <span data-ttu-id="029a8-150">févr。</span><span class="sxs-lookup"><span data-stu-id="029a8-150">févr.</span></span> <span data-ttu-id="029a8-151">火星 avril mai juin juil。</span><span class="sxs-lookup"><span data-stu-id="029a8-151">mars avril mai juin juil.</span></span> <span data-ttu-id="029a8-152">août 9 月。</span><span class="sxs-lookup"><span data-stu-id="029a8-152">août sept.</span></span> <span data-ttu-id="029a8-153">2008.</span><span class="sxs-lookup"><span data-stu-id="029a8-153">oct.</span></span> <span data-ttu-id="029a8-154">年11月.</span><span class="sxs-lookup"><span data-stu-id="029a8-154">nov.</span></span> <span data-ttu-id="029a8-155">déc。</span><span class="sxs-lookup"><span data-stu-id="029a8-155">déc.</span></span>
    
- <span data-ttu-id="029a8-156">德语</span><span class="sxs-lookup"><span data-stu-id="029a8-156">German</span></span>
    
  - <span data-ttu-id="029a8-157">jänuar、februar、märz、四月、mai、juni juli、八月、九月、oktober、十一月、dezember</span><span class="sxs-lookup"><span data-stu-id="029a8-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="029a8-158">Jan./Jän。</span><span class="sxs-lookup"><span data-stu-id="029a8-158">Jan./Jän.</span></span> <span data-ttu-id="029a8-159">2003年 März 年4月 Juni Juli, Okt。</span><span class="sxs-lookup"><span data-stu-id="029a8-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="029a8-160">Dez 年11月。</span><span class="sxs-lookup"><span data-stu-id="029a8-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="029a8-161">意大利语</span><span class="sxs-lookup"><span data-stu-id="029a8-161">Italian</span></span>
    
  - <span data-ttu-id="029a8-162">gennaio、febbraio、marzo、aprile、maggio、giugno、luglio、agosto、settembre、ottobre、novembre、dicembre</span><span class="sxs-lookup"><span data-stu-id="029a8-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="029a8-163">genn。</span><span class="sxs-lookup"><span data-stu-id="029a8-163">genn.</span></span> <span data-ttu-id="029a8-164">febbr。</span><span class="sxs-lookup"><span data-stu-id="029a8-164">febbr.</span></span> <span data-ttu-id="029a8-165">mar.</span><span class="sxs-lookup"><span data-stu-id="029a8-165">mar.</span></span> <span data-ttu-id="029a8-166">四月.</span><span class="sxs-lookup"><span data-stu-id="029a8-166">apr.</span></span> <span data-ttu-id="029a8-167">magg。</span><span class="sxs-lookup"><span data-stu-id="029a8-167">magg.</span></span> <span data-ttu-id="029a8-168">giugno luglio ag。</span><span class="sxs-lookup"><span data-stu-id="029a8-168">giugno luglio ag.</span></span> <span data-ttu-id="029a8-169">设置.</span><span class="sxs-lookup"><span data-stu-id="029a8-169">sett.</span></span> <span data-ttu-id="029a8-170">ott。</span><span class="sxs-lookup"><span data-stu-id="029a8-170">ott.</span></span> <span data-ttu-id="029a8-171">年11月.</span><span class="sxs-lookup"><span data-stu-id="029a8-171">nov.</span></span> <span data-ttu-id="029a8-172">home.dic.</span><span class="sxs-lookup"><span data-stu-id="029a8-172">dic.</span></span>
    
- <span data-ttu-id="029a8-173">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="029a8-173">Portuguese</span></span>
    
  - <span data-ttu-id="029a8-174">里约热内卢、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="029a8-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="029a8-175">jan fev mar abr mai 06 年6月前设置11月 dez</span><span class="sxs-lookup"><span data-stu-id="029a8-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="029a8-176">西班牙语</span><span class="sxs-lookup"><span data-stu-id="029a8-176">Spanish</span></span>
    
  - <span data-ttu-id="029a8-177">enero、febrero、marzo、abril、mayo、junio、julio、agosto、septiembre、octubre、noviembre、diciembre</span><span class="sxs-lookup"><span data-stu-id="029a8-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="029a8-178">enero 2003 年2月。</span><span class="sxs-lookup"><span data-stu-id="029a8-178">enero feb.</span></span> <span data-ttu-id="029a8-179">marzo abr。</span><span class="sxs-lookup"><span data-stu-id="029a8-179">marzo abr.</span></span> <span data-ttu-id="029a8-180">mayo 06。</span><span class="sxs-lookup"><span data-stu-id="029a8-180">mayo jun.</span></span> <span data-ttu-id="029a8-181">年7月.</span><span class="sxs-lookup"><span data-stu-id="029a8-181">jul.</span></span> <span data-ttu-id="029a8-182">agosto/set。</span><span class="sxs-lookup"><span data-stu-id="029a8-182">agosto sept./set.</span></span> <span data-ttu-id="029a8-183">2008.</span><span class="sxs-lookup"><span data-stu-id="029a8-183">oct.</span></span> <span data-ttu-id="029a8-184">年11月.</span><span class="sxs-lookup"><span data-stu-id="029a8-184">nov.</span></span> <span data-ttu-id="029a8-185">home.dic.</span><span class="sxs-lookup"><span data-stu-id="029a8-185">dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="029a8-186">Func_eu_date1 (已弃用)</span><span class="sxs-lookup"><span data-stu-id="029a8-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="029a8-187">此函数已被弃用, 因为它仅支持包含在上述`Func_eu_date`函数中的葡萄牙月名称。</span><span class="sxs-lookup"><span data-stu-id="029a8-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="029a8-188">此函数使用葡萄牙语中常用的格式查找日期。</span><span class="sxs-lookup"><span data-stu-id="029a8-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="029a8-189">此函数`Func_eu_date`的格式与使用的语言不同。</span><span class="sxs-lookup"><span data-stu-id="029a8-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="029a8-190">示例：</span><span class="sxs-lookup"><span data-stu-id="029a8-190">Examples:</span></span>
  
- <span data-ttu-id="029a8-191">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="029a8-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="029a8-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="029a8-192">02 dez 2016</span></span>
    
- <span data-ttu-id="029a8-193">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="029a8-193">2 Dez 16</span></span>
    
- <span data-ttu-id="029a8-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="029a8-194">2/12/2016</span></span>
    
- <span data-ttu-id="029a8-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="029a8-195">02/12/16</span></span>
    
- <span data-ttu-id="029a8-196">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="029a8-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="029a8-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="029a8-197">2-12-16</span></span>
    
<span data-ttu-id="029a8-198">接受的月份名称:</span><span class="sxs-lookup"><span data-stu-id="029a8-198">Accepted month names:</span></span>
  
- <span data-ttu-id="029a8-199">葡萄牙语</span><span class="sxs-lookup"><span data-stu-id="029a8-199">Portuguese</span></span>
    
  - <span data-ttu-id="029a8-200">里约热内卢、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="029a8-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="029a8-201">jan fev mar abr mai 06 年6月前设置11月 dez</span><span class="sxs-lookup"><span data-stu-id="029a8-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="029a8-202">Func_eu_date2 (已弃用)</span><span class="sxs-lookup"><span data-stu-id="029a8-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="029a8-203">此函数已被弃用, 因为它仅支持荷兰月份名称, 这些名称现在包含`Func_eu_date`在上述函数中。</span><span class="sxs-lookup"><span data-stu-id="029a8-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="029a8-204">此函数查找在荷兰语中常用的格式的日期。</span><span class="sxs-lookup"><span data-stu-id="029a8-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="029a8-205">此函数`Func_eu_date`的格式与使用的语言不同。</span><span class="sxs-lookup"><span data-stu-id="029a8-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="029a8-206">示例：</span><span class="sxs-lookup"><span data-stu-id="029a8-206">Examples:</span></span>
  
- <span data-ttu-id="029a8-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="029a8-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="029a8-208">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="029a8-208">02 mei 2016</span></span>
    
- <span data-ttu-id="029a8-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="029a8-209">2 Mei 16</span></span>
    
- <span data-ttu-id="029a8-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="029a8-210">2/12/2016</span></span>
    
- <span data-ttu-id="029a8-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="029a8-211">02/12/16</span></span>
    
- <span data-ttu-id="029a8-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="029a8-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="029a8-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="029a8-213">2-12-16</span></span>
    
<span data-ttu-id="029a8-214">接受的月份名称:</span><span class="sxs-lookup"><span data-stu-id="029a8-214">Accepted month names:</span></span>
  
- <span data-ttu-id="029a8-215">荷兰语</span><span class="sxs-lookup"><span data-stu-id="029a8-215">Dutch</span></span>
    
  - <span data-ttu-id="029a8-216">januari、februari、maart、四月、mei、juni、juli、augustus、九月、ocktober、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="029a8-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="029a8-217">2004年1月1月 maart 日 mei 年9月8日9月9日 okt 年11月</span><span class="sxs-lookup"><span data-stu-id="029a8-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="029a8-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="029a8-218">Func_expiration_date</span></span>

<span data-ttu-id="029a8-219">此函数查找信用卡和借记卡常用格式的日期, 其中不包括月份的天数。</span><span class="sxs-lookup"><span data-stu-id="029a8-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="029a8-220">此函数将以 "月/年"、"月-年"、"[月 name] year" 和 "[月缩写] 年" 的格式匹配日期。</span><span class="sxs-lookup"><span data-stu-id="029a8-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="029a8-221">月份的名称或缩写不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="029a8-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="029a8-222">示例：</span><span class="sxs-lookup"><span data-stu-id="029a8-222">Examples:</span></span>
  
- <span data-ttu-id="029a8-223">MM/YY--例如, 01/11 或1/11</span><span class="sxs-lookup"><span data-stu-id="029a8-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="029a8-224">MM/YYYY--例如, 01/2011 或1/2011</span><span class="sxs-lookup"><span data-stu-id="029a8-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="029a8-225">MM-YY--例如, 01-22 或1-11</span><span class="sxs-lookup"><span data-stu-id="029a8-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="029a8-226">MM--例如, 01-2000 或1-2000</span><span class="sxs-lookup"><span data-stu-id="029a8-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="029a8-227">以下格式支持 YY 或 YYYY:</span><span class="sxs-lookup"><span data-stu-id="029a8-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="029a8-228">年月日-例如,。Jan-2010 或一月-2010 或 Jan-10 或一月-10</span><span class="sxs-lookup"><span data-stu-id="029a8-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="029a8-229">年月日-例如, "一月 2010" 或 "jan 2010" 或 "jan 10" 或 "jan 10"</span><span class="sxs-lookup"><span data-stu-id="029a8-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="029a8-230">MonthYYYY-例如, "january2010" 或 "Jan2010" 或 "january10" 或 "Jan10"</span><span class="sxs-lookup"><span data-stu-id="029a8-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="029a8-231">Month/YYYY-例如, "一月/2010" 或 "jan/2010" 或 "一月/10" 或 "jan/10"</span><span class="sxs-lookup"><span data-stu-id="029a8-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="029a8-232">接受的月份名称:</span><span class="sxs-lookup"><span data-stu-id="029a8-232">Accepted month names:</span></span>
  
- <span data-ttu-id="029a8-233">英语</span><span class="sxs-lookup"><span data-stu-id="029a8-233">English</span></span>
    
  - <span data-ttu-id="029a8-234">一月份、二月、三月份、四月、六月、六月、七月、八月、九月、十月、十一月、十二月</span><span class="sxs-lookup"><span data-stu-id="029a8-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="029a8-235">2004年2月3月4月5月8日12月8月8日</span><span class="sxs-lookup"><span data-stu-id="029a8-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="029a8-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="029a8-236">Func_us_address</span></span>

<span data-ttu-id="029a8-237">此函数查找美国的状态名称或邮政缩写, 后跟有效的邮政编码, 就像在邮政地址中使用一样。</span><span class="sxs-lookup"><span data-stu-id="029a8-237">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses.</span></span> <span data-ttu-id="029a8-238">邮政编码必须是与美国省/市/自治区名称或缩写相关联的正确邮政编码之一。</span><span class="sxs-lookup"><span data-stu-id="029a8-238">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="029a8-239">美国省/市/自治区名称和邮政编码不能由标点符号或字母分隔。</span><span class="sxs-lookup"><span data-stu-id="029a8-239">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="029a8-240">示例：</span><span class="sxs-lookup"><span data-stu-id="029a8-240">Examples:</span></span>
  
- <span data-ttu-id="029a8-241">华盛顿98052</span><span class="sxs-lookup"><span data-stu-id="029a8-241">Washington 98052</span></span>
    
- <span data-ttu-id="029a8-242">华盛顿98052-9998</span><span class="sxs-lookup"><span data-stu-id="029a8-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="029a8-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="029a8-243">WA 98052</span></span>
    
- <span data-ttu-id="029a8-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="029a8-244">WA 98052-9998</span></span>
    


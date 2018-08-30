---
title: 欧盟 National 标识号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 2ea971bf-9434-4b61-b825-2bbd28ae6064
description: 本主题演示数据丢失防护 (DLP) 策略检测到的欧盟国家/地区标识号敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。
ms.openlocfilehash: 29d2126b937ff46039284a74eb2a84f2ebbacb41
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525345"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="8099c-104">欧盟 National 标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-104">EU National Identification Number</span></span>

<span data-ttu-id="8099c-p102">本主题演示数据丢失防护 (DLP) 策略检测到的欧盟国家/地区标识号敏感信息类型时的寻找。此敏感信息类型定义不同的模式、 关键字和每个国家/地区其他证据。</span><span class="sxs-lookup"><span data-stu-id="8099c-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="8099c-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="8099c-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="8099c-108">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-108">Format</span></span>

<span data-ttu-id="8099c-109">字母、 数字和特殊字符的 24 个字符组合</span><span class="sxs-lookup"><span data-stu-id="8099c-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-110">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-110">Pattern</span></span>

<span data-ttu-id="8099c-111">24 个字符：</span><span class="sxs-lookup"><span data-stu-id="8099c-111">24 characters:</span></span>
  
-  <span data-ttu-id="8099c-112">22 （不区分大小写） 的字母、 数字、 反斜杠、 正斜杠或加号</span><span class="sxs-lookup"><span data-stu-id="8099c-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="8099c-113">（不区分大小写） 的两个字母、 数字、 反斜杠、 正斜杠、 加号或等号</span><span class="sxs-lookup"><span data-stu-id="8099c-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8099c-114">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-114">Checksum</span></span>

<span data-ttu-id="8099c-115">不适用</span><span class="sxs-lookup"><span data-stu-id="8099c-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-116">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-116">Definition</span></span>

<span data-ttu-id="8099c-117">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-118">正则表达式`Regex_austria_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-119">从关键字`Keywords_austria_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-120">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-120">Keywords</span></span>

#### <a name="keywordsaustriaeunationalidcard"></a><span data-ttu-id="8099c-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="8099c-122">奥地利标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-122">austrian identity number</span></span>
  
<span data-ttu-id="8099c-123">国家/地区的 identity 号码</span><span class="sxs-lookup"><span data-stu-id="8099c-123">national identity number</span></span>
  
<span data-ttu-id="8099c-124">标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-124">identity number</span></span>
  
<span data-ttu-id="8099c-125">
national id</span><span class="sxs-lookup"><span data-stu-id="8099c-125">national id</span></span>
  
<span data-ttu-id="8099c-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="8099c-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="8099c-127">比利时</span><span class="sxs-lookup"><span data-stu-id="8099c-127">Belgium</span></span>

<span data-ttu-id="8099c-128">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"比利时国家/地区号码"。</span><span class="sxs-lookup"><span data-stu-id="8099c-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="8099c-129">保加利亚</span><span class="sxs-lookup"><span data-stu-id="8099c-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="8099c-130">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-130">Format</span></span>

<span data-ttu-id="8099c-131">没有空格和分隔符的 10 位数字</span><span class="sxs-lookup"><span data-stu-id="8099c-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-132">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-132">Pattern</span></span>

<span data-ttu-id="8099c-133">没有空格和分隔符的 10 位数字</span><span class="sxs-lookup"><span data-stu-id="8099c-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="8099c-134">对应于出生日期 (YYMMDD) 的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="8099c-135">出生顺序对应的两位数</span><span class="sxs-lookup"><span data-stu-id="8099c-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="8099c-136">对应于性别的一位数： 偶数位男性和女性为奇数数字</span><span class="sxs-lookup"><span data-stu-id="8099c-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="8099c-137">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="8099c-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8099c-138">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-138">Checksum</span></span>

<span data-ttu-id="8099c-139">是</span><span class="sxs-lookup"><span data-stu-id="8099c-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-140">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-140">Definition</span></span>

<span data-ttu-id="8099c-141">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-142">该函数`Func_bulgaria_national_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-143">从关键字`Keywords_bulgaria_national_number`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="8099c-144">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-145">该函数`Func_bulgaria_national_number`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-146">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-146">Keywords</span></span>

#### <a name="keywordsbulgarianationalnumber"></a><span data-ttu-id="8099c-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="8099c-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="8099c-148">egn</span><span class="sxs-lookup"><span data-stu-id="8099c-148">egn</span></span>
  
<span data-ttu-id="8099c-149">egn #</span><span class="sxs-lookup"><span data-stu-id="8099c-149">egn#</span></span>
  
<span data-ttu-id="8099c-150">保加利亚语的国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="8099c-150">bulgarian national number</span></span>
  
<span data-ttu-id="8099c-151">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="8099c-151">national number</span></span>
  
<span data-ttu-id="8099c-152">social security number
</span><span class="sxs-lookup"><span data-stu-id="8099c-152">social security number</span></span>
  
<span data-ttu-id="8099c-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="8099c-153">nationalnumber#</span></span>
  
<span data-ttu-id="8099c-154">ssn #</span><span class="sxs-lookup"><span data-stu-id="8099c-154">ssn#</span></span>
  
<span data-ttu-id="8099c-155">ssn</span><span class="sxs-lookup"><span data-stu-id="8099c-155">ssn</span></span>
  
<span data-ttu-id="8099c-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="8099c-156">nationalnumber</span></span>
  
<span data-ttu-id="8099c-157">bnn #</span><span class="sxs-lookup"><span data-stu-id="8099c-157">bnn#</span></span>
  
<span data-ttu-id="8099c-158">bnn</span><span class="sxs-lookup"><span data-stu-id="8099c-158">bnn</span></span>
  
<span data-ttu-id="8099c-159">个人标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-159">personal id number</span></span>
  
<span data-ttu-id="8099c-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="8099c-160">personalidnumber#</span></span>
  
<span data-ttu-id="8099c-161">ЕДИНЕН ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="8099c-161">единен граждански номер</span></span>
  
<span data-ttu-id="8099c-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="8099c-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="8099c-163">ЕГН</span><span class="sxs-lookup"><span data-stu-id="8099c-163">егн</span></span>
  
<span data-ttu-id="8099c-164">ЕГН #</span><span class="sxs-lookup"><span data-stu-id="8099c-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="8099c-165">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="8099c-165">Croatia</span></span>

<span data-ttu-id="8099c-166">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"克罗地亚标识号"。</span><span class="sxs-lookup"><span data-stu-id="8099c-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="8099c-167">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="8099c-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="8099c-168">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-168">Format</span></span>

<span data-ttu-id="8099c-169">没有空格和分隔符的 10 位数字</span><span class="sxs-lookup"><span data-stu-id="8099c-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-170">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-170">Pattern</span></span>

 <span data-ttu-id="8099c-171">10 位数字</span><span class="sxs-lookup"><span data-stu-id="8099c-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8099c-172">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-172">Checksum</span></span>

<span data-ttu-id="8099c-173">不适用</span><span class="sxs-lookup"><span data-stu-id="8099c-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-174">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-174">Definition</span></span>

<span data-ttu-id="8099c-175">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-176">正则表达式`Regex_cyprus_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-177">从关键字`Keywords_cyprus_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-178">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-178">Keywords</span></span>

#### <a name="keywordscypruseunationalidcard"></a><span data-ttu-id="8099c-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="8099c-180">身份证号码</span><span class="sxs-lookup"><span data-stu-id="8099c-180">id card number</span></span>
  
<span data-ttu-id="8099c-181">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-181">national identification number</span></span>
  
<span data-ttu-id="8099c-182">个人标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-182">personal id number</span></span>
  
<span data-ttu-id="8099c-183">身份证号码</span><span class="sxs-lookup"><span data-stu-id="8099c-183">identity card number</span></span>
  
<span data-ttu-id="8099c-184">ΤΑΥΤΟΤΗΤΑΣ</span><span class="sxs-lookup"><span data-stu-id="8099c-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="8099c-185">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="8099c-185">Czech Republic</span></span>

<span data-ttu-id="8099c-186">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"捷克语国家/地区的 Identity 号码"。</span><span class="sxs-lookup"><span data-stu-id="8099c-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="8099c-187">丹麦</span><span class="sxs-lookup"><span data-stu-id="8099c-187">Denmark</span></span>

<span data-ttu-id="8099c-188">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"丹麦个人识别号"。</span><span class="sxs-lookup"><span data-stu-id="8099c-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="8099c-189">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="8099c-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="8099c-190">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-190">Format</span></span>

<span data-ttu-id="8099c-191">没有空格和分隔符 11 位数字</span><span class="sxs-lookup"><span data-stu-id="8099c-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-192">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-192">Pattern</span></span>

<span data-ttu-id="8099c-193">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="8099c-193">11 digits:</span></span>
  
- <span data-ttu-id="8099c-194">对应于性别和出生的 century 的一位数 (奇数号码男性、 偶数女; 1-2: 19 century; 3-4: 20 世纪; 5-6: 21 世纪)</span><span class="sxs-lookup"><span data-stu-id="8099c-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="8099c-195">对应于 (YYMMDD) 出生日期的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="8099c-196">对应于分隔人员在相同日期出生日期序列号的三个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="8099c-197">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="8099c-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8099c-198">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-198">Checksum</span></span>

<span data-ttu-id="8099c-199">是</span><span class="sxs-lookup"><span data-stu-id="8099c-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-200">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-200">Definition</span></span>

<span data-ttu-id="8099c-201">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-202">该函数`Func_estonia_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-203">从关键字`Keywords_estonia_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="8099c-204">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-205">该函数`Func_estonia_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-206">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-206">Keywords</span></span>

#### <a name="keywordsestoniaeunationalidcard"></a><span data-ttu-id="8099c-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="8099c-208">个人识别码代码</span><span class="sxs-lookup"><span data-stu-id="8099c-208">personal identification code</span></span>
  
<span data-ttu-id="8099c-209">个人识别号</span><span class="sxs-lookup"><span data-stu-id="8099c-209">personal identification number</span></span>
  
<span data-ttu-id="8099c-210">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-210">national identification number</span></span>
  
<span data-ttu-id="8099c-211">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="8099c-211">national number</span></span>
  
<span data-ttu-id="8099c-212">个人标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-212">personal id number</span></span>
  
<span data-ttu-id="8099c-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="8099c-213">personalidnumber#</span></span>
  
<span data-ttu-id="8099c-214">ik</span><span class="sxs-lookup"><span data-stu-id="8099c-214">ik</span></span>
  
<span data-ttu-id="8099c-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="8099c-215">isikukood</span></span>
  
<span data-ttu-id="8099c-216">id kaart</span><span class="sxs-lookup"><span data-stu-id="8099c-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="8099c-217">芬兰</span><span class="sxs-lookup"><span data-stu-id="8099c-217">Finland</span></span>

<span data-ttu-id="8099c-218">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"芬兰国家/地区 ID"。</span><span class="sxs-lookup"><span data-stu-id="8099c-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="8099c-219">法国</span><span class="sxs-lookup"><span data-stu-id="8099c-219">France</span></span>

<span data-ttu-id="8099c-220">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"法国国家 ID 卡 (CNI)"。</span><span class="sxs-lookup"><span data-stu-id="8099c-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="8099c-221">德国</span><span class="sxs-lookup"><span data-stu-id="8099c-221">Germany</span></span>

<span data-ttu-id="8099c-222">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"德国身份证编号"。</span><span class="sxs-lookup"><span data-stu-id="8099c-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="8099c-223">希腊</span><span class="sxs-lookup"><span data-stu-id="8099c-223">Greece</span></span>

<span data-ttu-id="8099c-224">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"希腊国家 ID 卡"。</span><span class="sxs-lookup"><span data-stu-id="8099c-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="8099c-225">匈牙利</span><span class="sxs-lookup"><span data-stu-id="8099c-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="8099c-226">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-226">Format</span></span>

<span data-ttu-id="8099c-227">11 个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-228">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-228">Pattern</span></span>

<span data-ttu-id="8099c-229">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="8099c-229">11 digits:</span></span>
  
-  <span data-ttu-id="8099c-230">对应于性别 （1-插头 2 女性、 其他号码也是可行市民出生日期之前 1900年或与双公民市民的） 的一位数</span><span class="sxs-lookup"><span data-stu-id="8099c-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="8099c-231">对应于出生日期 (YYMMDD) 的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="8099c-232">三个转成序列号对应的数字</span><span class="sxs-lookup"><span data-stu-id="8099c-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="8099c-233">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="8099c-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8099c-234">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-234">Checksum</span></span>

<span data-ttu-id="8099c-235">是</span><span class="sxs-lookup"><span data-stu-id="8099c-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-236">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-236">Definition</span></span>

<span data-ttu-id="8099c-237">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-238">该函数`Func_hungary_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-239">从关键字`Keywords_hungary_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="8099c-240">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-241">该函数`Func_hungary_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-242">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-242">Keywords</span></span>

#### <a name="keywordshungaryeunationalidcard"></a><span data-ttu-id="8099c-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="8099c-244">个人识别号</span><span class="sxs-lookup"><span data-stu-id="8099c-244">personal identification number</span></span>
  
<span data-ttu-id="8099c-245">identification number
</span><span class="sxs-lookup"><span data-stu-id="8099c-245">identification number</span></span>
  
<span data-ttu-id="8099c-246">个人标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-246">personal id number</span></span>
  
<span data-ttu-id="8099c-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="8099c-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="8099c-248">Ireland</span><span class="sxs-lookup"><span data-stu-id="8099c-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="8099c-249">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-249">Format</span></span>

<span data-ttu-id="8099c-250">字母、 数字和空间以指定的模式的九个字符组合</span><span class="sxs-lookup"><span data-stu-id="8099c-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-251">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-251">Pattern</span></span>

<span data-ttu-id="8099c-252">字母、 数字和空间以指定的模式的九个字符组合</span><span class="sxs-lookup"><span data-stu-id="8099c-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="8099c-253">从到现在为止的 01 2013 年 1 月：</span><span class="sxs-lookup"><span data-stu-id="8099c-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="8099c-254">七个数字 </span><span class="sxs-lookup"><span data-stu-id="8099c-254">Seven digits</span></span> 
    
- <span data-ttu-id="8099c-255">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="8099c-255">One check digit</span></span>
    
- <span data-ttu-id="8099c-256">一个空格或大写字母"W"（区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8099c-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="8099c-257">之前 01 2013 年 1 月：</span><span class="sxs-lookup"><span data-stu-id="8099c-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="8099c-258">七个数字 </span><span class="sxs-lookup"><span data-stu-id="8099c-258">Seven digits</span></span> 
    
- <span data-ttu-id="8099c-259">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="8099c-259">One check digit</span></span>
    
- <span data-ttu-id="8099c-260">一个空格或大写字母 （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8099c-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8099c-261">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-261">Checksum</span></span>

<span data-ttu-id="8099c-262">是</span><span class="sxs-lookup"><span data-stu-id="8099c-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-263">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-263">Definition</span></span>

<span data-ttu-id="8099c-264">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-265">该函数查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="8099c-266">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-266">A keyword from is found.</span></span>
    
<span data-ttu-id="8099c-267">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-268">该函数查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-268">The function finds content that matches the pattern.</span></span>
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-269">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-269">Keywords</span></span>

#### <a name="keywordsirelandeunationalidcard"></a><span data-ttu-id="8099c-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="8099c-271">个人公共服务号码</span><span class="sxs-lookup"><span data-stu-id="8099c-271">personal public service number</span></span>
  
<span data-ttu-id="8099c-272">pps 没有</span><span class="sxs-lookup"><span data-stu-id="8099c-272">pps no</span></span>
  
<span data-ttu-id="8099c-273">收入和社会保险号码</span><span class="sxs-lookup"><span data-stu-id="8099c-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="8099c-274">rsi 没有</span><span class="sxs-lookup"><span data-stu-id="8099c-274">rsi no</span></span>
  
<span data-ttu-id="8099c-275">个人识别号</span><span class="sxs-lookup"><span data-stu-id="8099c-275">personal identification number</span></span>
  
<span data-ttu-id="8099c-276">identification number
</span><span class="sxs-lookup"><span data-stu-id="8099c-276">identification number</span></span>
  
<span data-ttu-id="8099c-277">个人标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-277">personal id number</span></span>
  
<span data-ttu-id="8099c-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="8099c-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="8099c-p103">uimh。psp</span><span class="sxs-lookup"><span data-stu-id="8099c-p103">uimh. psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="8099c-281">意大利</span><span class="sxs-lookup"><span data-stu-id="8099c-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="8099c-282">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-282">Format</span></span>

<span data-ttu-id="8099c-283">字母和指定的模式中数字位数的 16 个字符组合</span><span class="sxs-lookup"><span data-stu-id="8099c-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-284">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-284">Pattern</span></span>

<span data-ttu-id="8099c-285">16 个字符字母和数字的组合：</span><span class="sxs-lookup"><span data-stu-id="8099c-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="8099c-286">对应于系列名称中的前三个辅音的三个字母</span><span class="sxs-lookup"><span data-stu-id="8099c-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="8099c-287">对应于第一、 第三个和第四个的三个字母辅音中第一个名称</span><span class="sxs-lookup"><span data-stu-id="8099c-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="8099c-288">两位数的最后一个对应出生年份的数字</span><span class="sxs-lookup"><span data-stu-id="8099c-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="8099c-289">举行的出生对应于的字母的一个字母 — 字母使用以字母顺序列出，但仅字母 A 到 E、 H、 L、 M、 P、 R T 到使用 （即年 1 月是 A 和年 10 月为 R）</span><span class="sxs-lookup"><span data-stu-id="8099c-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="8099c-290">对应于的出生日期的两位数 — 为了区分 gender，40 添加到女性出生日期</span><span class="sxs-lookup"><span data-stu-id="8099c-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="8099c-291">对应于特定于此人出生上级主管机构区号的四位数字 （国家/地区范围代码使用外的国家/地区）</span><span class="sxs-lookup"><span data-stu-id="8099c-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="8099c-292">奇偶校验的一位数</span><span class="sxs-lookup"><span data-stu-id="8099c-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8099c-293">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-293">Checksum</span></span>

<span data-ttu-id="8099c-294">是</span><span class="sxs-lookup"><span data-stu-id="8099c-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-295">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-295">Definition</span></span>

<span data-ttu-id="8099c-296">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-297">该函数`Func_italy_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-298">从关键字`Keywords_italy_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="8099c-299">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-300">该函数`Func_italy_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-301">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-301">Keywords</span></span>

#### <a name="keywordsitalyeunationalidcard"></a><span data-ttu-id="8099c-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="8099c-303">个人代码</span><span class="sxs-lookup"><span data-stu-id="8099c-303">personal code</span></span>
  
<span data-ttu-id="8099c-304">个人代码编号</span><span class="sxs-lookup"><span data-stu-id="8099c-304">personal code number</span></span>
  
<span data-ttu-id="8099c-305">个人证书号</span><span class="sxs-lookup"><span data-stu-id="8099c-305">personal certificate number</span></span>
  
<span data-ttu-id="8099c-306">会计代码</span><span class="sxs-lookup"><span data-stu-id="8099c-306">fiscal code</span></span>
  
<span data-ttu-id="8099c-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="8099c-307">personalcodeno#</span></span>
  
<span data-ttu-id="8099c-308">个人标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-308">personal id number</span></span>
  
<span data-ttu-id="8099c-309">个人 id 代码</span><span class="sxs-lookup"><span data-stu-id="8099c-309">personal id code</span></span>
  
<span data-ttu-id="8099c-310">codice personale</span><span class="sxs-lookup"><span data-stu-id="8099c-310">codice personale</span></span>
  
<span data-ttu-id="8099c-311">numero certificato personale</span><span class="sxs-lookup"><span data-stu-id="8099c-311">numero certificato personale</span></span>
  
<span data-ttu-id="8099c-312">numero personale</span><span class="sxs-lookup"><span data-stu-id="8099c-312">numero personale</span></span>
  
<span data-ttu-id="8099c-313">numero id personale</span><span class="sxs-lookup"><span data-stu-id="8099c-313">numero id personale</span></span>
  
<span data-ttu-id="8099c-314">codice id personale</span><span class="sxs-lookup"><span data-stu-id="8099c-314">codice id personale</span></span>
  
<span data-ttu-id="8099c-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="8099c-315">codice fiscale</span></span>
  
## <a name="italy"></a><span data-ttu-id="8099c-316">意大利</span><span class="sxs-lookup"><span data-stu-id="8099c-316">Italy</span></span>

### <a name="format"></a><span data-ttu-id="8099c-317">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-317">Format</span></span>

<span data-ttu-id="8099c-318">11 位数字并且以指定格式连字符</span><span class="sxs-lookup"><span data-stu-id="8099c-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-319">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-319">Pattern</span></span>

<span data-ttu-id="8099c-320">11 位数字和连字符：</span><span class="sxs-lookup"><span data-stu-id="8099c-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="8099c-321">对应于出生日期月日的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="8099c-322">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="8099c-322">A hyphen</span></span>
    
- <span data-ttu-id="8099c-323">对应于出生 （19 century"0"、"1"的 20 世纪和"2"的 21 世纪） century 的一位数</span><span class="sxs-lookup"><span data-stu-id="8099c-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="8099c-324">四位数字，随机生成</span><span class="sxs-lookup"><span data-stu-id="8099c-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8099c-325">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-325">Checksum</span></span>

<span data-ttu-id="8099c-326">是</span><span class="sxs-lookup"><span data-stu-id="8099c-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-327">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-327">Definition</span></span>

<span data-ttu-id="8099c-328">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-329">该函数`Func_latvia_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-330">从关键字`Keywords_latvia_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="8099c-331">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-332">该函数`Func_latvia_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-333">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-333">Keywords</span></span>

#### <a name="keywordslatviaeunationalidcard"></a><span data-ttu-id="8099c-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="8099c-335">个人代码</span><span class="sxs-lookup"><span data-stu-id="8099c-335">personal code</span></span>
  
<span data-ttu-id="8099c-336">个人代码编号</span><span class="sxs-lookup"><span data-stu-id="8099c-336">personal code number</span></span>
  
<span data-ttu-id="8099c-337">个人证书号</span><span class="sxs-lookup"><span data-stu-id="8099c-337">personal certificate number</span></span>
  
<span data-ttu-id="8099c-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="8099c-338">personalcodeno#</span></span>
  
<span data-ttu-id="8099c-339">个人标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-339">personal id number</span></span>
  
<span data-ttu-id="8099c-340">个人 id 代码</span><span class="sxs-lookup"><span data-stu-id="8099c-340">personal id code</span></span>
  
<span data-ttu-id="8099c-341">角色 kods</span><span class="sxs-lookup"><span data-stu-id="8099c-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="8099c-342">立陶宛</span><span class="sxs-lookup"><span data-stu-id="8099c-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="8099c-343">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-343">Format</span></span>

<span data-ttu-id="8099c-344">没有空格和分隔符 11 位数字</span><span class="sxs-lookup"><span data-stu-id="8099c-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-345">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-345">Pattern</span></span>

<span data-ttu-id="8099c-346">没有空格和分隔符 11 位数字：</span><span class="sxs-lookup"><span data-stu-id="8099c-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="8099c-347">对应于此人的性别和出生的 century 的一位数</span><span class="sxs-lookup"><span data-stu-id="8099c-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="8099c-348">对应于出生日期 (YYMMDD) 的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="8099c-349">出生日期序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="8099c-350">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="8099c-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8099c-351">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-351">Checksum</span></span>

<span data-ttu-id="8099c-352">是</span><span class="sxs-lookup"><span data-stu-id="8099c-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-353">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-353">Definition</span></span>

<span data-ttu-id="8099c-354">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-355">该函数`Func_lithuania_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-356">从关键字`Keywords_lithuania_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="8099c-357">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-358">该函数`Func_lithuania_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-359">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-359">Keywords</span></span>

#### <a name="keywordslithuaniaeunationalidcard"></a><span data-ttu-id="8099c-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="8099c-361">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="8099c-361">personal numeric code</span></span>
  
<span data-ttu-id="8099c-362">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-362">unique identification number</span></span>
  
<span data-ttu-id="8099c-363">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="8099c-363">citizen service number</span></span>
  
<span data-ttu-id="8099c-364">唯一标识号码</span><span class="sxs-lookup"><span data-stu-id="8099c-364">unique identity number</span></span>
  
<span data-ttu-id="8099c-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="8099c-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="8099c-366">个人代码。</span><span class="sxs-lookup"><span data-stu-id="8099c-366">personal code.</span></span>
  
<span data-ttu-id="8099c-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="8099c-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="8099c-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="8099c-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="8099c-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="8099c-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="8099c-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="8099c-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="8099c-371">asmens kodas。</span><span class="sxs-lookup"><span data-stu-id="8099c-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="8099c-372">卢森堡</span><span class="sxs-lookup"><span data-stu-id="8099c-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="8099c-373">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-373">Format</span></span>

<span data-ttu-id="8099c-374">没有空格和分隔符 11 位数字</span><span class="sxs-lookup"><span data-stu-id="8099c-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-375">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-375">Pattern</span></span>

<span data-ttu-id="8099c-376">11 个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-376">11 digits</span></span>
  
- <span data-ttu-id="8099c-377">对应于此人的性别和出生的 century 的一位数</span><span class="sxs-lookup"><span data-stu-id="8099c-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="8099c-378">对应于出生日期 (YYMMDD) 的 6 个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="8099c-379">出生日期序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="8099c-380">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="8099c-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8099c-381">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-381">Checksum</span></span>

<span data-ttu-id="8099c-382">不适用</span><span class="sxs-lookup"><span data-stu-id="8099c-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-383">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-383">Definition</span></span>

<span data-ttu-id="8099c-384">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-385">正则表达式`Regex_luxemburg_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-386">从关键字`Keywords_luxemburg_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-387">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-387">Keywords</span></span>

#### <a name="keywordsluxemburgeunationalidcard"></a><span data-ttu-id="8099c-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="8099c-389">个人 id</span><span class="sxs-lookup"><span data-stu-id="8099c-389">personal id</span></span>
  
<span data-ttu-id="8099c-390">个人标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-390">personal id number</span></span>
  
<span data-ttu-id="8099c-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="8099c-391">personalidno#</span></span>
  
<span data-ttu-id="8099c-392">唯一 id 号</span><span class="sxs-lookup"><span data-stu-id="8099c-392">unique id number</span></span>
  
<span data-ttu-id="8099c-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="8099c-393">personalidnumber#</span></span>
  
<span data-ttu-id="8099c-394">唯一 id 键</span><span class="sxs-lookup"><span data-stu-id="8099c-394">unique id key</span></span>
  
<span data-ttu-id="8099c-395">个人 id 代码</span><span class="sxs-lookup"><span data-stu-id="8099c-395">personal id code</span></span>
  
<span data-ttu-id="8099c-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="8099c-396">uniqueidkey#</span></span>
  
<span data-ttu-id="8099c-397">单个代码</span><span class="sxs-lookup"><span data-stu-id="8099c-397">individual code</span></span>
  
<span data-ttu-id="8099c-398">单个 id</span><span class="sxs-lookup"><span data-stu-id="8099c-398">individual id</span></span>
  
<span data-ttu-id="8099c-399">eindeutige id nummer</span><span class="sxs-lookup"><span data-stu-id="8099c-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="8099c-400">eindeutige id</span><span class="sxs-lookup"><span data-stu-id="8099c-400">eindeutige id</span></span>
  
<span data-ttu-id="8099c-401">id personnelle</span><span class="sxs-lookup"><span data-stu-id="8099c-401">id personnelle</span></span>
  
<span data-ttu-id="8099c-402">numéro d'identification 人员</span><span class="sxs-lookup"><span data-stu-id="8099c-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="8099c-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="8099c-403">idpersonnelle#</span></span>
  
<span data-ttu-id="8099c-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="8099c-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="8099c-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="8099c-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="8099c-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="8099c-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="8099c-407">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-407">Format</span></span>

<span data-ttu-id="8099c-408">七位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="8099c-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-409">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-409">Pattern</span></span>

<span data-ttu-id="8099c-410">七位数字后跟一个字母：</span><span class="sxs-lookup"><span data-stu-id="8099c-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="8099c-411">七个数字 </span><span class="sxs-lookup"><span data-stu-id="8099c-411">Seven digits</span></span> 
    
- <span data-ttu-id="8099c-412">一个大写字母 （区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8099c-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8099c-413">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-413">Checksum</span></span>

<span data-ttu-id="8099c-414">不适用</span><span class="sxs-lookup"><span data-stu-id="8099c-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-415">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-415">Definition</span></span>

<span data-ttu-id="8099c-416">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-417">正则表达式`Regex_malta_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-418">从关键字`Keywords_malta_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="8099c-419">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-420">正则表达式`Regex_malta_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-421">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-421">Keywords</span></span>

#### <a name="keywordsmaltaeunationalidcard"></a><span data-ttu-id="8099c-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="8099c-423">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="8099c-423">personal numeric code</span></span>
  
<span data-ttu-id="8099c-424">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-424">unique identification number</span></span>
  
<span data-ttu-id="8099c-425">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="8099c-425">citizen service number</span></span>
  
<span data-ttu-id="8099c-426">唯一标识号码</span><span class="sxs-lookup"><span data-stu-id="8099c-426">unique identity number</span></span>
  
<span data-ttu-id="8099c-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="8099c-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="8099c-428">kodiċi numerali personali</span><span class="sxs-lookup"><span data-stu-id="8099c-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="8099c-429">numru 选项卡 identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="8099c-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="8099c-430">numru tas servizz taċ ċittadin</span><span class="sxs-lookup"><span data-stu-id="8099c-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="8099c-431">numru 选项卡 identità uniku</span><span class="sxs-lookup"><span data-stu-id="8099c-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="8099c-432">荷兰</span><span class="sxs-lookup"><span data-stu-id="8099c-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="8099c-433">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-433">Format</span></span>

<span data-ttu-id="8099c-434">不含空格或分隔符的九个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-435">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-435">Pattern</span></span>

<span data-ttu-id="8099c-436">九个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8099c-437">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-437">Checksum</span></span>

<span data-ttu-id="8099c-438">是</span><span class="sxs-lookup"><span data-stu-id="8099c-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-439">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-439">Definition</span></span>

<span data-ttu-id="8099c-440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-441">该函数`Func_netherlands_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-442">从关键字是找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-442">A keyword from is found.</span></span>
    
<span data-ttu-id="8099c-443">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-444">该函数`Func_netherlands_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-445">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-445">Keywords</span></span>

#### <a name="keywordsnetherlandseunationalidcard"></a><span data-ttu-id="8099c-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="8099c-447">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="8099c-447">personal numeric code</span></span>
  
<span data-ttu-id="8099c-448">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-448">unique identification number</span></span>
  
<span data-ttu-id="8099c-449">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="8099c-449">citizen service number</span></span>
  
<span data-ttu-id="8099c-450">唯一标识号码</span><span class="sxs-lookup"><span data-stu-id="8099c-450">unique identity number</span></span>
  
<span data-ttu-id="8099c-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="8099c-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="8099c-452">bsn</span><span class="sxs-lookup"><span data-stu-id="8099c-452">bsn</span></span>
  
<span data-ttu-id="8099c-453">bsn #</span><span class="sxs-lookup"><span data-stu-id="8099c-453">bsn#</span></span>
  
<span data-ttu-id="8099c-454">persoonlijke numerieke 代码</span><span class="sxs-lookup"><span data-stu-id="8099c-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="8099c-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="8099c-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="8099c-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="8099c-456">burgerservicenummer</span></span>
  
<span data-ttu-id="8099c-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="8099c-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="8099c-458">波兰</span><span class="sxs-lookup"><span data-stu-id="8099c-458">Poland</span></span>

<span data-ttu-id="8099c-459">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"波兰国家/地区 ID (PESEL)"。</span><span class="sxs-lookup"><span data-stu-id="8099c-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="8099c-460">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="8099c-460">Portugal</span></span>

<span data-ttu-id="8099c-461">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"葡萄牙公民卡号"。</span><span class="sxs-lookup"><span data-stu-id="8099c-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="8099c-462">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="8099c-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="8099c-463">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-463">Format</span></span>

<span data-ttu-id="8099c-464">13 没有空格和分隔符的数字</span><span class="sxs-lookup"><span data-stu-id="8099c-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-465">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-465">Pattern</span></span>

<span data-ttu-id="8099c-466">13 位数字</span><span class="sxs-lookup"><span data-stu-id="8099c-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8099c-467">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-467">Checksum</span></span>

<span data-ttu-id="8099c-468">是</span><span class="sxs-lookup"><span data-stu-id="8099c-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-469">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-469">Definition</span></span>

<span data-ttu-id="8099c-470">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-471">该函数`Func_romania_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-472">从关键字`Keywords_romania_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="8099c-473">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-474">该函数`Func_romania_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-475">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-475">Keywords</span></span>

#### <a name="keywordsromaniaeunationalidcard"></a><span data-ttu-id="8099c-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="8099c-477">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="8099c-477">personal numeric code</span></span>
  
<span data-ttu-id="8099c-478">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-478">unique identification number</span></span>
  
<span data-ttu-id="8099c-479">cnp</span><span class="sxs-lookup"><span data-stu-id="8099c-479">cnp</span></span>
  
<span data-ttu-id="8099c-480">cnp #</span><span class="sxs-lookup"><span data-stu-id="8099c-480">cnp#</span></span>
  
<span data-ttu-id="8099c-481">固定</span><span class="sxs-lookup"><span data-stu-id="8099c-481">pin</span></span>
  
<span data-ttu-id="8099c-482">pin #</span><span class="sxs-lookup"><span data-stu-id="8099c-482">pin#</span></span>
  
<span data-ttu-id="8099c-483">保险号</span><span class="sxs-lookup"><span data-stu-id="8099c-483">insurance number</span></span>
  
<span data-ttu-id="8099c-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="8099c-484">insurancenumber#</span></span>
  
<span data-ttu-id="8099c-485">唯一标识号码</span><span class="sxs-lookup"><span data-stu-id="8099c-485">unique identity number</span></span>
  
<span data-ttu-id="8099c-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="8099c-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="8099c-487">cod 数值个人</span><span class="sxs-lookup"><span data-stu-id="8099c-487">cod numeric personal</span></span>
  
<span data-ttu-id="8099c-488">货 identificare 个人到付款</span><span class="sxs-lookup"><span data-stu-id="8099c-488">cod identificare personal</span></span>
  
<span data-ttu-id="8099c-489">cod unic identificare</span><span class="sxs-lookup"><span data-stu-id="8099c-489">cod unic identificare</span></span>
  
<span data-ttu-id="8099c-490">număr 个人 unic</span><span class="sxs-lookup"><span data-stu-id="8099c-490">număr personal unic</span></span>
  
<span data-ttu-id="8099c-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="8099c-491">număr identitate</span></span>
  
<span data-ttu-id="8099c-492">număr identificare 个人</span><span class="sxs-lookup"><span data-stu-id="8099c-492">număr identificare personal</span></span>
  
<span data-ttu-id="8099c-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="8099c-493">număridentitate#</span></span>
  
<span data-ttu-id="8099c-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="8099c-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="8099c-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="8099c-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="8099c-496">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="8099c-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="8099c-497">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-497">Format</span></span>

<span data-ttu-id="8099c-498">包含一个反斜杠 10 位数字</span><span class="sxs-lookup"><span data-stu-id="8099c-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-499">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-499">Pattern</span></span>

<span data-ttu-id="8099c-500">包含一个反斜杠 10 位数字：</span><span class="sxs-lookup"><span data-stu-id="8099c-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8099c-501">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-501">Checksum</span></span>

<span data-ttu-id="8099c-502">是</span><span class="sxs-lookup"><span data-stu-id="8099c-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-503">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-503">Definition</span></span>

<span data-ttu-id="8099c-504">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-505">该函数`Func_slovakia_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-506">从关键字`Keywords_slovakia_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="8099c-507">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-508">该函数`Func_slovakia_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-509">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-509">Keywords</span></span>

#### <a name="keywordsslovakiaeunationalidcard"></a><span data-ttu-id="8099c-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="8099c-511">出生号码</span><span class="sxs-lookup"><span data-stu-id="8099c-511">birth number</span></span>
  
<span data-ttu-id="8099c-512">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-512">national identification number</span></span>
  
<span data-ttu-id="8099c-513">个人识别号</span><span class="sxs-lookup"><span data-stu-id="8099c-513">personal identification number</span></span>
  
<span data-ttu-id="8099c-514">social security number
</span><span class="sxs-lookup"><span data-stu-id="8099c-514">social security number</span></span>
  
<span data-ttu-id="8099c-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="8099c-515">nationalnumber#</span></span>
  
<span data-ttu-id="8099c-516">ssn #</span><span class="sxs-lookup"><span data-stu-id="8099c-516">ssn#</span></span>
  
<span data-ttu-id="8099c-517">ssn</span><span class="sxs-lookup"><span data-stu-id="8099c-517">ssn</span></span>
  
<span data-ttu-id="8099c-518">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="8099c-518">national number</span></span>
  
<span data-ttu-id="8099c-519">个人标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-519">personal id number</span></span>
  
<span data-ttu-id="8099c-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="8099c-520">personalidnumber#</span></span>
  
<span data-ttu-id="8099c-521">rč</span><span class="sxs-lookup"><span data-stu-id="8099c-521">rč</span></span>
  
<span data-ttu-id="8099c-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="8099c-522">rodné číslo</span></span>
  
<span data-ttu-id="8099c-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="8099c-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="8099c-524">斯诺文尼亚</span><span class="sxs-lookup"><span data-stu-id="8099c-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="8099c-525">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-525">Format</span></span>

<span data-ttu-id="8099c-526">不含空格或分隔符 13 数字</span><span class="sxs-lookup"><span data-stu-id="8099c-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-527">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-527">Pattern</span></span>

<span data-ttu-id="8099c-528">在指定的模式的 13 数字：</span><span class="sxs-lookup"><span data-stu-id="8099c-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="8099c-529">对应于出生日期 (DDMMLLL)，其中，"LLL"对应于上次出生一年中的三个数字的七个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="8099c-530">对应于出生的区域的两位数</span><span class="sxs-lookup"><span data-stu-id="8099c-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="8099c-531">人员在同一天 (000-499 插孔) 和女性为 500-999 出生日期对应的性别和序列号组合的三个数字</span><span class="sxs-lookup"><span data-stu-id="8099c-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="8099c-532">一个检查数字</span><span class="sxs-lookup"><span data-stu-id="8099c-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8099c-533">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-533">Checksum</span></span>

<span data-ttu-id="8099c-534">是</span><span class="sxs-lookup"><span data-stu-id="8099c-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-535">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-535">Definition</span></span>

<span data-ttu-id="8099c-536">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-537">该函数`Func_slovenia_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-538">从关键字`Keywords_slovenia_eu_national_id_card`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="8099c-539">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-540">该函数`Func_slovenia_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-541">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-541">Keywords</span></span>

#### <a name="keywordssloveniaeunationalidcard"></a><span data-ttu-id="8099c-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="8099c-543">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="8099c-543">personal numeric code</span></span>
  
<span data-ttu-id="8099c-544">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-544">unique identification number</span></span>
  
<span data-ttu-id="8099c-545">注册的唯一编号</span><span class="sxs-lookup"><span data-stu-id="8099c-545">unique registration number</span></span>
  
<span data-ttu-id="8099c-546">唯一标识号码</span><span class="sxs-lookup"><span data-stu-id="8099c-546">unique identity number</span></span>
  
<span data-ttu-id="8099c-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="8099c-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="8099c-548">唯一的主公民号码</span><span class="sxs-lookup"><span data-stu-id="8099c-548">unique master citizen number</span></span>
  
<span data-ttu-id="8099c-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="8099c-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="8099c-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="8099c-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="8099c-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="8099c-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="8099c-552">emšo</span><span class="sxs-lookup"><span data-stu-id="8099c-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="8099c-553">西班牙</span><span class="sxs-lookup"><span data-stu-id="8099c-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="8099c-554">格式</span><span class="sxs-lookup"><span data-stu-id="8099c-554">Format</span></span>

<span data-ttu-id="8099c-555">一个字符后跟七位数字</span><span class="sxs-lookup"><span data-stu-id="8099c-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8099c-556">模式</span><span class="sxs-lookup"><span data-stu-id="8099c-556">Pattern</span></span>

<span data-ttu-id="8099c-557">一个字符后跟七位数字</span><span class="sxs-lookup"><span data-stu-id="8099c-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="8099c-558">七个数字 </span><span class="sxs-lookup"><span data-stu-id="8099c-558">Seven digits</span></span>
    
- <span data-ttu-id="8099c-559">一个数字或字母 （不区分大小写）</span><span class="sxs-lookup"><span data-stu-id="8099c-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8099c-560">校验和</span><span class="sxs-lookup"><span data-stu-id="8099c-560">Checksum</span></span>

<span data-ttu-id="8099c-561">不适用</span><span class="sxs-lookup"><span data-stu-id="8099c-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8099c-562">定义</span><span class="sxs-lookup"><span data-stu-id="8099c-562">Definition</span></span>

<span data-ttu-id="8099c-563">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8099c-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8099c-564">正则表达式`Regex_spain_eu_national_id_card`查找与模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8099c-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8099c-565">从关键字`Keywords_spain_eu_national_id_card"`找到。</span><span class="sxs-lookup"><span data-stu-id="8099c-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8099c-566">Keywords</span><span class="sxs-lookup"><span data-stu-id="8099c-566">Keywords</span></span>

#### <a name="keywordsspaineunationalidcard"></a><span data-ttu-id="8099c-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="8099c-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="8099c-568">dni</span><span class="sxs-lookup"><span data-stu-id="8099c-568">dni</span></span>
  
<span data-ttu-id="8099c-569">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="8099c-569">national identification number</span></span>
  
<span data-ttu-id="8099c-570">国家/地区的 identity 号码</span><span class="sxs-lookup"><span data-stu-id="8099c-570">national identity number</span></span>
  
<span data-ttu-id="8099c-571">保险号</span><span class="sxs-lookup"><span data-stu-id="8099c-571">insurance number</span></span>
  
<span data-ttu-id="8099c-572">个人识别号</span><span class="sxs-lookup"><span data-stu-id="8099c-572">personal identification number</span></span>
  
<span data-ttu-id="8099c-573">国家/地区的标识</span><span class="sxs-lookup"><span data-stu-id="8099c-573">national identity</span></span>
  
<span data-ttu-id="8099c-574">个人标识无</span><span class="sxs-lookup"><span data-stu-id="8099c-574">personal identity no</span></span>
  
<span data-ttu-id="8099c-575">唯一标识号码</span><span class="sxs-lookup"><span data-stu-id="8099c-575">unique identity number</span></span>
  
<span data-ttu-id="8099c-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="8099c-576">nationalidno#</span></span>
  
<span data-ttu-id="8099c-577">uniqueid #</span><span class="sxs-lookup"><span data-stu-id="8099c-577">uniqueid#</span></span>
  
<span data-ttu-id="8099c-578">dni #</span><span class="sxs-lookup"><span data-stu-id="8099c-578">dni#</span></span>
  
<span data-ttu-id="8099c-579">nationalid #</span><span class="sxs-lookup"><span data-stu-id="8099c-579">nationalid#</span></span>
  
<span data-ttu-id="8099c-580">nie #</span><span class="sxs-lookup"><span data-stu-id="8099c-580">nie#</span></span>
  
<span data-ttu-id="8099c-581">nie</span><span class="sxs-lookup"><span data-stu-id="8099c-581">nie</span></span>
  
<span data-ttu-id="8099c-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="8099c-582">nienúmero#</span></span>
  
<span data-ttu-id="8099c-583">nie número</span><span class="sxs-lookup"><span data-stu-id="8099c-583">nie número</span></span>
  
<span data-ttu-id="8099c-584">documento nacional de identidad</span><span class="sxs-lookup"><span data-stu-id="8099c-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="8099c-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="8099c-585">identidad único</span></span>
  
<span data-ttu-id="8099c-586">número nacional identidad</span><span class="sxs-lookup"><span data-stu-id="8099c-586">número nacional identidad</span></span>
  
<span data-ttu-id="8099c-587">dni número</span><span class="sxs-lookup"><span data-stu-id="8099c-587">dni número</span></span>
  
<span data-ttu-id="8099c-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="8099c-588">dninúmero#</span></span>
  
<span data-ttu-id="8099c-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="8099c-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="8099c-590">瑞典</span><span class="sxs-lookup"><span data-stu-id="8099c-590">Sweden</span></span>

<span data-ttu-id="8099c-591">有关详细信息，请参阅中[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)的部分"瑞典国家/地区 ID"。</span><span class="sxs-lookup"><span data-stu-id="8099c-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8099c-592">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8099c-592">See also</span></span>

[<span data-ttu-id="8099c-593">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="8099c-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)


---
title: 欧盟国家身份证号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 2ea971bf-9434-4b61-b825-2bbd28ae6064
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟国家身份证的敏感信息类型时, 会对其进行查找。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: 9a85fd6954f39de348874e03268a2e19ae47366c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220632"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="49321-104">欧盟国家身份证号</span><span class="sxs-lookup"><span data-stu-id="49321-104">EU National Identification Number</span></span>

<span data-ttu-id="49321-p102">本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟国家身份证的敏感信息类型时, 会对其进行查找。此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="49321-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="49321-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="49321-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="49321-108">格式</span><span class="sxs-lookup"><span data-stu-id="49321-108">Format</span></span>

<span data-ttu-id="49321-109">字母、数字和特殊字符的24个字符的组合</span><span class="sxs-lookup"><span data-stu-id="49321-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-110">模式</span><span class="sxs-lookup"><span data-stu-id="49321-110">Pattern</span></span>

<span data-ttu-id="49321-111">24个字符:</span><span class="sxs-lookup"><span data-stu-id="49321-111">24 characters:</span></span>
  
-  <span data-ttu-id="49321-112">22个字母 (不区分大小写)、数字、反斜杠、正斜杠或加号</span><span class="sxs-lookup"><span data-stu-id="49321-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="49321-113">两个字母 (不区分大小写)、数字、反斜杠、正斜杠、加号或等号</span><span class="sxs-lookup"><span data-stu-id="49321-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49321-114">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-114">Checksum</span></span>

<span data-ttu-id="49321-115">不适用</span><span class="sxs-lookup"><span data-stu-id="49321-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-116">Definition</span><span class="sxs-lookup"><span data-stu-id="49321-116">Definition</span></span>

<span data-ttu-id="49321-117">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-118">正则表达式`Regex_austria_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-119">找到了中`Keywords_austria_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49321-120">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-120">Keywords</span></span>

#### <a name="keywordsaustriaeunationalidcard"></a><span data-ttu-id="49321-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="49321-122">奥地利身份证号码</span><span class="sxs-lookup"><span data-stu-id="49321-122">austrian identity number</span></span>
  
<span data-ttu-id="49321-123">国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="49321-123">national identity number</span></span>
  
<span data-ttu-id="49321-124">标识号码</span><span class="sxs-lookup"><span data-stu-id="49321-124">identity number</span></span>
  
<span data-ttu-id="49321-125">
national id</span><span class="sxs-lookup"><span data-stu-id="49321-125">national id</span></span>
  
<span data-ttu-id="49321-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="49321-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="49321-127">比利时</span><span class="sxs-lookup"><span data-stu-id="49321-127">Belgium</span></span>

<span data-ttu-id="49321-128">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "比利时国家数" 一节。</span><span class="sxs-lookup"><span data-stu-id="49321-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="49321-129">保加利亚</span><span class="sxs-lookup"><span data-stu-id="49321-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="49321-130">格式</span><span class="sxs-lookup"><span data-stu-id="49321-130">Format</span></span>

<span data-ttu-id="49321-131">10个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="49321-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-132">模式</span><span class="sxs-lookup"><span data-stu-id="49321-132">Pattern</span></span>

<span data-ttu-id="49321-133">10个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="49321-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="49321-134">与出生日期对应的6个数字 (YYMMDD)</span><span class="sxs-lookup"><span data-stu-id="49321-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="49321-135">与出生顺序对应的两个数字</span><span class="sxs-lookup"><span data-stu-id="49321-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="49321-136">与性别对应的一位数字: 男的偶数位和用于女的奇数位</span><span class="sxs-lookup"><span data-stu-id="49321-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="49321-137">一个校验位</span><span class="sxs-lookup"><span data-stu-id="49321-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49321-138">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-138">Checksum</span></span>

<span data-ttu-id="49321-139">是</span><span class="sxs-lookup"><span data-stu-id="49321-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-140">定义</span><span class="sxs-lookup"><span data-stu-id="49321-140">Definition</span></span>

<span data-ttu-id="49321-141">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-142">函数`Func_bulgaria_national_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-143">找到了中`Keywords_bulgaria_national_number`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="49321-144">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-145">函数`Func_bulgaria_national_number`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="49321-146">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-146">Keywords</span></span>

#### <a name="keywordsbulgarianationalnumber"></a><span data-ttu-id="49321-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="49321-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="49321-148">egn</span><span class="sxs-lookup"><span data-stu-id="49321-148">egn</span></span>
  
<span data-ttu-id="49321-149">egn #</span><span class="sxs-lookup"><span data-stu-id="49321-149">egn#</span></span>
  
<span data-ttu-id="49321-150">保加利亚语国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="49321-150">bulgarian national number</span></span>
  
<span data-ttu-id="49321-151">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="49321-151">national number</span></span>
  
<span data-ttu-id="49321-152">social security number
</span><span class="sxs-lookup"><span data-stu-id="49321-152">social security number</span></span>
  
<span data-ttu-id="49321-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="49321-153">nationalnumber#</span></span>
  
<span data-ttu-id="49321-154">ssn</span><span class="sxs-lookup"><span data-stu-id="49321-154">ssn#</span></span>
  
<span data-ttu-id="49321-155">ssn</span><span class="sxs-lookup"><span data-stu-id="49321-155">ssn</span></span>
  
<span data-ttu-id="49321-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="49321-156">nationalnumber</span></span>
  
<span data-ttu-id="49321-157">bnn #</span><span class="sxs-lookup"><span data-stu-id="49321-157">bnn#</span></span>
  
<span data-ttu-id="49321-158">bnn</span><span class="sxs-lookup"><span data-stu-id="49321-158">bnn</span></span>
  
<span data-ttu-id="49321-159">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="49321-159">personal id number</span></span>
  
<span data-ttu-id="49321-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="49321-160">personalidnumber#</span></span>
  
<span data-ttu-id="49321-161">единенгражданскиномер</span><span class="sxs-lookup"><span data-stu-id="49321-161">единен граждански номер</span></span>
  
<span data-ttu-id="49321-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="49321-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="49321-163">егн</span><span class="sxs-lookup"><span data-stu-id="49321-163">егн</span></span>
  
<span data-ttu-id="49321-164">егн #</span><span class="sxs-lookup"><span data-stu-id="49321-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="49321-165">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="49321-165">Croatia</span></span>

<span data-ttu-id="49321-166">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)部分中的 "克罗地亚恒等号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="49321-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="49321-167">塞浦路斯</span><span class="sxs-lookup"><span data-stu-id="49321-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="49321-168">格式</span><span class="sxs-lookup"><span data-stu-id="49321-168">Format</span></span>

<span data-ttu-id="49321-169">10个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="49321-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-170">模式</span><span class="sxs-lookup"><span data-stu-id="49321-170">Pattern</span></span>

 <span data-ttu-id="49321-171">10位数字</span><span class="sxs-lookup"><span data-stu-id="49321-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="49321-172">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-172">Checksum</span></span>

<span data-ttu-id="49321-173">不适用</span><span class="sxs-lookup"><span data-stu-id="49321-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-174">Definition</span><span class="sxs-lookup"><span data-stu-id="49321-174">Definition</span></span>

<span data-ttu-id="49321-175">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-176">正则表达式`Regex_cyprus_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-177">找到了中`Keywords_cyprus_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49321-178">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-178">Keywords</span></span>

#### <a name="keywordscypruseunationalidcard"></a><span data-ttu-id="49321-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="49321-180">id 卡号</span><span class="sxs-lookup"><span data-stu-id="49321-180">id card number</span></span>
  
<span data-ttu-id="49321-181">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="49321-181">national identification number</span></span>
  
<span data-ttu-id="49321-182">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="49321-182">personal id number</span></span>
  
<span data-ttu-id="49321-183">标识卡号</span><span class="sxs-lookup"><span data-stu-id="49321-183">identity card number</span></span>
  
<span data-ttu-id="49321-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="49321-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="49321-185">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="49321-185">Czech Republic</span></span>

<span data-ttu-id="49321-186">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "捷克国家身份证号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="49321-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="49321-187">丹麦</span><span class="sxs-lookup"><span data-stu-id="49321-187">Denmark</span></span>

<span data-ttu-id="49321-188">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "丹麦个人识别码" 一节。</span><span class="sxs-lookup"><span data-stu-id="49321-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="49321-189">爱沙尼亚</span><span class="sxs-lookup"><span data-stu-id="49321-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="49321-190">格式</span><span class="sxs-lookup"><span data-stu-id="49321-190">Format</span></span>

<span data-ttu-id="49321-191">11个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="49321-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-192">模式</span><span class="sxs-lookup"><span data-stu-id="49321-192">Pattern</span></span>

<span data-ttu-id="49321-193">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="49321-193">11 digits:</span></span>
  
- <span data-ttu-id="49321-194">一种数字, 对应于性别和出生世纪 (奇数号男, 甚至是数字女; 1-2:19 世纪; 3-4:20 世纪; 5-6:21 世纪)</span><span class="sxs-lookup"><span data-stu-id="49321-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="49321-195">六个数字, 对应于出生日期 (YYMMDD)</span><span class="sxs-lookup"><span data-stu-id="49321-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="49321-196">三个数字, 对应于将出生在同一日期的人员组成的序列号</span><span class="sxs-lookup"><span data-stu-id="49321-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="49321-197">一个校验位</span><span class="sxs-lookup"><span data-stu-id="49321-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49321-198">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-198">Checksum</span></span>

<span data-ttu-id="49321-199">是</span><span class="sxs-lookup"><span data-stu-id="49321-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-200">定义</span><span class="sxs-lookup"><span data-stu-id="49321-200">Definition</span></span>

<span data-ttu-id="49321-201">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-202">函数`Func_estonia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-203">找到了中`Keywords_estonia_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="49321-204">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-205">函数`Func_estonia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="49321-206">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-206">Keywords</span></span>

#### <a name="keywordsestoniaeunationalidcard"></a><span data-ttu-id="49321-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="49321-208">个人标识代码</span><span class="sxs-lookup"><span data-stu-id="49321-208">personal identification code</span></span>
  
<span data-ttu-id="49321-209">个人标识号</span><span class="sxs-lookup"><span data-stu-id="49321-209">personal identification number</span></span>
  
<span data-ttu-id="49321-210">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="49321-210">national identification number</span></span>
  
<span data-ttu-id="49321-211">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="49321-211">national number</span></span>
  
<span data-ttu-id="49321-212">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="49321-212">personal id number</span></span>
  
<span data-ttu-id="49321-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="49321-213">personalidnumber#</span></span>
  
<span data-ttu-id="49321-214">ik</span><span class="sxs-lookup"><span data-stu-id="49321-214">ik</span></span>
  
<span data-ttu-id="49321-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="49321-215">isikukood</span></span>
  
<span data-ttu-id="49321-216">id-kaart</span><span class="sxs-lookup"><span data-stu-id="49321-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="49321-217">芬兰</span><span class="sxs-lookup"><span data-stu-id="49321-217">Finland</span></span>

<span data-ttu-id="49321-218">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "芬兰国 ID" 一节。</span><span class="sxs-lookup"><span data-stu-id="49321-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="49321-219">法国</span><span class="sxs-lookup"><span data-stu-id="49321-219">France</span></span>

<span data-ttu-id="49321-220">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "法国国家 ID 卡 (CNI)" 一节。</span><span class="sxs-lookup"><span data-stu-id="49321-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="49321-221">德国</span><span class="sxs-lookup"><span data-stu-id="49321-221">Germany</span></span>

<span data-ttu-id="49321-222">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国身份证号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="49321-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="49321-223">希腊</span><span class="sxs-lookup"><span data-stu-id="49321-223">Greece</span></span>

<span data-ttu-id="49321-224">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "希腊国家 ID 卡" 一节。</span><span class="sxs-lookup"><span data-stu-id="49321-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="49321-225">匈牙利</span><span class="sxs-lookup"><span data-stu-id="49321-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="49321-226">格式</span><span class="sxs-lookup"><span data-stu-id="49321-226">Format</span></span>

<span data-ttu-id="49321-227">11 个数字</span><span class="sxs-lookup"><span data-stu-id="49321-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-228">模式</span><span class="sxs-lookup"><span data-stu-id="49321-228">Pattern</span></span>

<span data-ttu-id="49321-229">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="49321-229">11 digits:</span></span>
  
-  <span data-ttu-id="49321-230">一种与性别对应的数字 (1--男, 2-母, 其他号码也适用于在两个公民前出生的公民的1900或公民)</span><span class="sxs-lookup"><span data-stu-id="49321-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="49321-231">与出生日期对应的6个数字 (YYMMDD)</span><span class="sxs-lookup"><span data-stu-id="49321-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="49321-232">与序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="49321-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="49321-233">一个校验位</span><span class="sxs-lookup"><span data-stu-id="49321-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49321-234">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-234">Checksum</span></span>

<span data-ttu-id="49321-235">是</span><span class="sxs-lookup"><span data-stu-id="49321-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-236">定义</span><span class="sxs-lookup"><span data-stu-id="49321-236">Definition</span></span>

<span data-ttu-id="49321-237">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-238">函数`Func_hungary_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-239">找到了中`Keywords_hungary_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="49321-240">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-241">函数`Func_hungary_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="49321-242">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-242">Keywords</span></span>

#### <a name="keywordshungaryeunationalidcard"></a><span data-ttu-id="49321-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="49321-244">个人标识号</span><span class="sxs-lookup"><span data-stu-id="49321-244">personal identification number</span></span>
  
<span data-ttu-id="49321-245">identification number
</span><span class="sxs-lookup"><span data-stu-id="49321-245">identification number</span></span>
  
<span data-ttu-id="49321-246">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="49321-246">personal id number</span></span>
  
<span data-ttu-id="49321-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="49321-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="49321-248">Ireland</span><span class="sxs-lookup"><span data-stu-id="49321-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="49321-249">格式</span><span class="sxs-lookup"><span data-stu-id="49321-249">Format</span></span>

<span data-ttu-id="49321-250">指定模式中的字母、数字和空格的九个字符的组合</span><span class="sxs-lookup"><span data-stu-id="49321-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-251">模式</span><span class="sxs-lookup"><span data-stu-id="49321-251">Pattern</span></span>

<span data-ttu-id="49321-252">指定模式中的字母、数字和空格的九个字符的组合</span><span class="sxs-lookup"><span data-stu-id="49321-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="49321-253">从01年1月2013到现在:</span><span class="sxs-lookup"><span data-stu-id="49321-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="49321-254">七个数字 </span><span class="sxs-lookup"><span data-stu-id="49321-254">Seven digits</span></span> 
    
- <span data-ttu-id="49321-255">一个校验位</span><span class="sxs-lookup"><span data-stu-id="49321-255">One check digit</span></span>
    
- <span data-ttu-id="49321-256">一个空格或大写的字母 "W" (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="49321-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="49321-257">在01月1日之前1月 2013:</span><span class="sxs-lookup"><span data-stu-id="49321-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="49321-258">七个数字 </span><span class="sxs-lookup"><span data-stu-id="49321-258">Seven digits</span></span> 
    
- <span data-ttu-id="49321-259">一个校验位</span><span class="sxs-lookup"><span data-stu-id="49321-259">One check digit</span></span>
    
- <span data-ttu-id="49321-260">一个空格或大写字母 (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="49321-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49321-261">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-261">Checksum</span></span>

<span data-ttu-id="49321-262">是</span><span class="sxs-lookup"><span data-stu-id="49321-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-263">定义</span><span class="sxs-lookup"><span data-stu-id="49321-263">Definition</span></span>

<span data-ttu-id="49321-264">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-265">函数找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="49321-266">找到了中的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-266">A keyword from is found.</span></span>
    
<span data-ttu-id="49321-267">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-268">函数找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-268">The function finds content that matches the pattern.</span></span>
    
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

### <a name="keywords"></a><span data-ttu-id="49321-269">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-269">Keywords</span></span>

#### <a name="keywordsirelandeunationalidcard"></a><span data-ttu-id="49321-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="49321-271">个人公开服务号码</span><span class="sxs-lookup"><span data-stu-id="49321-271">personal public service number</span></span>
  
<span data-ttu-id="49321-272">pps no</span><span class="sxs-lookup"><span data-stu-id="49321-272">pps no</span></span>
  
<span data-ttu-id="49321-273">收入和社会保险电话号码</span><span class="sxs-lookup"><span data-stu-id="49321-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="49321-274">rsi no</span><span class="sxs-lookup"><span data-stu-id="49321-274">rsi no</span></span>
  
<span data-ttu-id="49321-275">个人标识号</span><span class="sxs-lookup"><span data-stu-id="49321-275">personal identification number</span></span>
  
<span data-ttu-id="49321-276">identification number
</span><span class="sxs-lookup"><span data-stu-id="49321-276">identification number</span></span>
  
<span data-ttu-id="49321-277">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="49321-277">personal id number</span></span>
  
<span data-ttu-id="49321-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="49321-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="49321-p103">uimh。psp</span><span class="sxs-lookup"><span data-stu-id="49321-p103">uimh. psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="49321-281">意大利</span><span class="sxs-lookup"><span data-stu-id="49321-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="49321-282">格式</span><span class="sxs-lookup"><span data-stu-id="49321-282">Format</span></span>

<span data-ttu-id="49321-283">在指定模式中, 由16个字符组成的字母和数字的组合</span><span class="sxs-lookup"><span data-stu-id="49321-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-284">模式</span><span class="sxs-lookup"><span data-stu-id="49321-284">Pattern</span></span>

<span data-ttu-id="49321-285">字母和数字的16个字符的组合:</span><span class="sxs-lookup"><span data-stu-id="49321-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="49321-286">与系列名称中的前三个辅音对应的三个字母</span><span class="sxs-lookup"><span data-stu-id="49321-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="49321-287">与名字中的第一个、第三个和第四个辅音对应的三个字母</span><span class="sxs-lookup"><span data-stu-id="49321-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="49321-288">与出生年份的最后一个数字对应的两个数字</span><span class="sxs-lookup"><span data-stu-id="49321-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="49321-289">一个与出生月份的字母对应的字母–字母按字母顺序使用, 但仅使用字母 A 到 E、H、L、M、P、R 和 T (因此, 一月为 a, 10 月为 r)</span><span class="sxs-lookup"><span data-stu-id="49321-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="49321-290">与出生月份的某一天对应的两个数字, 为了区分 genders, 40 已添加到女性的出生日。</span><span class="sxs-lookup"><span data-stu-id="49321-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="49321-291">与专用于 municipality 的区域代码相对应的四个数字 (国家/地区内的国家/地区代码适用于外国国家)</span><span class="sxs-lookup"><span data-stu-id="49321-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="49321-292">一个奇偶校验数字</span><span class="sxs-lookup"><span data-stu-id="49321-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49321-293">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-293">Checksum</span></span>

<span data-ttu-id="49321-294">是</span><span class="sxs-lookup"><span data-stu-id="49321-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-295">定义</span><span class="sxs-lookup"><span data-stu-id="49321-295">Definition</span></span>

<span data-ttu-id="49321-296">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-297">函数`Func_italy_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-298">找到了中`Keywords_italy_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="49321-299">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-300">函数`Func_italy_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="49321-301">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-301">Keywords</span></span>

#### <a name="keywordsitalyeunationalidcard"></a><span data-ttu-id="49321-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="49321-303">个人代码</span><span class="sxs-lookup"><span data-stu-id="49321-303">personal code</span></span>
  
<span data-ttu-id="49321-304">个人代码编号</span><span class="sxs-lookup"><span data-stu-id="49321-304">personal code number</span></span>
  
<span data-ttu-id="49321-305">个人证书号码</span><span class="sxs-lookup"><span data-stu-id="49321-305">personal certificate number</span></span>
  
<span data-ttu-id="49321-306">会计代码</span><span class="sxs-lookup"><span data-stu-id="49321-306">fiscal code</span></span>
  
<span data-ttu-id="49321-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="49321-307">personalcodeno#</span></span>
  
<span data-ttu-id="49321-308">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="49321-308">personal id number</span></span>
  
<span data-ttu-id="49321-309">个人 id 代码</span><span class="sxs-lookup"><span data-stu-id="49321-309">personal id code</span></span>
  
<span data-ttu-id="49321-310">codice personale</span><span class="sxs-lookup"><span data-stu-id="49321-310">codice personale</span></span>
  
<span data-ttu-id="49321-311">numero certificato personale</span><span class="sxs-lookup"><span data-stu-id="49321-311">numero certificato personale</span></span>
  
<span data-ttu-id="49321-312">numero personale</span><span class="sxs-lookup"><span data-stu-id="49321-312">numero personale</span></span>
  
<span data-ttu-id="49321-313">numero id personale</span><span class="sxs-lookup"><span data-stu-id="49321-313">numero id personale</span></span>
  
<span data-ttu-id="49321-314">codice id personale</span><span class="sxs-lookup"><span data-stu-id="49321-314">codice id personale</span></span>
  
<span data-ttu-id="49321-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="49321-315">codice fiscale</span></span>
  
## <a name="italy"></a><span data-ttu-id="49321-316">意大利</span><span class="sxs-lookup"><span data-stu-id="49321-316">Italy</span></span>

### <a name="format"></a><span data-ttu-id="49321-317">格式</span><span class="sxs-lookup"><span data-stu-id="49321-317">Format</span></span>

<span data-ttu-id="49321-318">11位数字和指定格式的连字符</span><span class="sxs-lookup"><span data-stu-id="49321-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-319">模式</span><span class="sxs-lookup"><span data-stu-id="49321-319">Pattern</span></span>

<span data-ttu-id="49321-320">11个数字和一个连字符:</span><span class="sxs-lookup"><span data-stu-id="49321-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="49321-321">与出生日期对应的6个数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="49321-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="49321-322">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="49321-322">A hyphen</span></span>
    
- <span data-ttu-id="49321-323">一个数字, 对应于出生世纪 ("0" 表示19世纪, "1" 表示20世纪, "2" 表示21世纪)</span><span class="sxs-lookup"><span data-stu-id="49321-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="49321-324">四个数字, 随机生成</span><span class="sxs-lookup"><span data-stu-id="49321-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49321-325">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-325">Checksum</span></span>

<span data-ttu-id="49321-326">是</span><span class="sxs-lookup"><span data-stu-id="49321-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-327">定义</span><span class="sxs-lookup"><span data-stu-id="49321-327">Definition</span></span>

<span data-ttu-id="49321-328">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-329">函数`Func_latvia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-330">找到了中`Keywords_latvia_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="49321-331">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-332">函数`Func_latvia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="49321-333">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-333">Keywords</span></span>

#### <a name="keywordslatviaeunationalidcard"></a><span data-ttu-id="49321-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="49321-335">个人代码</span><span class="sxs-lookup"><span data-stu-id="49321-335">personal code</span></span>
  
<span data-ttu-id="49321-336">个人代码编号</span><span class="sxs-lookup"><span data-stu-id="49321-336">personal code number</span></span>
  
<span data-ttu-id="49321-337">个人证书号码</span><span class="sxs-lookup"><span data-stu-id="49321-337">personal certificate number</span></span>
  
<span data-ttu-id="49321-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="49321-338">personalcodeno#</span></span>
  
<span data-ttu-id="49321-339">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="49321-339">personal id number</span></span>
  
<span data-ttu-id="49321-340">个人 id 代码</span><span class="sxs-lookup"><span data-stu-id="49321-340">personal id code</span></span>
  
<span data-ttu-id="49321-341">角色 kods</span><span class="sxs-lookup"><span data-stu-id="49321-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="49321-342">立陶宛</span><span class="sxs-lookup"><span data-stu-id="49321-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="49321-343">格式</span><span class="sxs-lookup"><span data-stu-id="49321-343">Format</span></span>

<span data-ttu-id="49321-344">11个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="49321-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-345">模式</span><span class="sxs-lookup"><span data-stu-id="49321-345">Pattern</span></span>

<span data-ttu-id="49321-346">11个数字, 不含空格和分隔符:</span><span class="sxs-lookup"><span data-stu-id="49321-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="49321-347">一个与人的性别和出生世纪对应的数字</span><span class="sxs-lookup"><span data-stu-id="49321-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="49321-348">与出生日期对应的6个数字 (YYMMDD)</span><span class="sxs-lookup"><span data-stu-id="49321-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="49321-349">与出生日期的序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="49321-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="49321-350">一个校验位</span><span class="sxs-lookup"><span data-stu-id="49321-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49321-351">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-351">Checksum</span></span>

<span data-ttu-id="49321-352">是</span><span class="sxs-lookup"><span data-stu-id="49321-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-353">定义</span><span class="sxs-lookup"><span data-stu-id="49321-353">Definition</span></span>

<span data-ttu-id="49321-354">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-355">函数`Func_lithuania_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-356">找到了中`Keywords_lithuania_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="49321-357">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-358">函数`Func_lithuania_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="49321-359">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-359">Keywords</span></span>

#### <a name="keywordslithuaniaeunationalidcard"></a><span data-ttu-id="49321-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="49321-361">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="49321-361">personal numeric code</span></span>
  
<span data-ttu-id="49321-362">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="49321-362">unique identification number</span></span>
  
<span data-ttu-id="49321-363">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="49321-363">citizen service number</span></span>
  
<span data-ttu-id="49321-364">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="49321-364">unique identity number</span></span>
  
<span data-ttu-id="49321-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="49321-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="49321-366">个人代码。</span><span class="sxs-lookup"><span data-stu-id="49321-366">personal code.</span></span>
  
<span data-ttu-id="49321-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="49321-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="49321-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="49321-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="49321-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="49321-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="49321-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="49321-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="49321-371">asmens kodas。</span><span class="sxs-lookup"><span data-stu-id="49321-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="49321-372">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="49321-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="49321-373">格式</span><span class="sxs-lookup"><span data-stu-id="49321-373">Format</span></span>

<span data-ttu-id="49321-374">11个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="49321-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-375">模式</span><span class="sxs-lookup"><span data-stu-id="49321-375">Pattern</span></span>

<span data-ttu-id="49321-376">11 个数字</span><span class="sxs-lookup"><span data-stu-id="49321-376">11 digits</span></span>
  
- <span data-ttu-id="49321-377">一个与人的性别和出生世纪对应的数字</span><span class="sxs-lookup"><span data-stu-id="49321-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="49321-378">与出生日期对应的6个数字 (YYMMDD)</span><span class="sxs-lookup"><span data-stu-id="49321-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="49321-379">与出生日期的序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="49321-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="49321-380">一个校验位</span><span class="sxs-lookup"><span data-stu-id="49321-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49321-381">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-381">Checksum</span></span>

<span data-ttu-id="49321-382">不适用</span><span class="sxs-lookup"><span data-stu-id="49321-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-383">Definition</span><span class="sxs-lookup"><span data-stu-id="49321-383">Definition</span></span>

<span data-ttu-id="49321-384">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-385">正则表达式`Regex_luxemburg_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-386">找到了中`Keywords_luxemburg_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49321-387">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-387">Keywords</span></span>

#### <a name="keywordsluxemburgeunationalidcard"></a><span data-ttu-id="49321-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="49321-389">个人 id</span><span class="sxs-lookup"><span data-stu-id="49321-389">personal id</span></span>
  
<span data-ttu-id="49321-390">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="49321-390">personal id number</span></span>
  
<span data-ttu-id="49321-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="49321-391">personalidno#</span></span>
  
<span data-ttu-id="49321-392">唯一 id 号</span><span class="sxs-lookup"><span data-stu-id="49321-392">unique id number</span></span>
  
<span data-ttu-id="49321-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="49321-393">personalidnumber#</span></span>
  
<span data-ttu-id="49321-394">唯一 id 键</span><span class="sxs-lookup"><span data-stu-id="49321-394">unique id key</span></span>
  
<span data-ttu-id="49321-395">个人 id 代码</span><span class="sxs-lookup"><span data-stu-id="49321-395">personal id code</span></span>
  
<span data-ttu-id="49321-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="49321-396">uniqueidkey#</span></span>
  
<span data-ttu-id="49321-397">单个代码</span><span class="sxs-lookup"><span data-stu-id="49321-397">individual code</span></span>
  
<span data-ttu-id="49321-398">个人 id</span><span class="sxs-lookup"><span data-stu-id="49321-398">individual id</span></span>
  
<span data-ttu-id="49321-399">eindeutige id-nummer</span><span class="sxs-lookup"><span data-stu-id="49321-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="49321-400">eindeutige id</span><span class="sxs-lookup"><span data-stu-id="49321-400">eindeutige id</span></span>
  
<span data-ttu-id="49321-401">id personnelle</span><span class="sxs-lookup"><span data-stu-id="49321-401">id personnelle</span></span>
  
<span data-ttu-id="49321-402">numéro d'identification 人员</span><span class="sxs-lookup"><span data-stu-id="49321-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="49321-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="49321-403">idpersonnelle#</span></span>
  
<span data-ttu-id="49321-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="49321-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="49321-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="49321-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="49321-406">马耳他</span><span class="sxs-lookup"><span data-stu-id="49321-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="49321-407">格式</span><span class="sxs-lookup"><span data-stu-id="49321-407">Format</span></span>

<span data-ttu-id="49321-408">七位数字后跟一个字母</span><span class="sxs-lookup"><span data-stu-id="49321-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-409">模式</span><span class="sxs-lookup"><span data-stu-id="49321-409">Pattern</span></span>

<span data-ttu-id="49321-410">七位数字后跟一个字母:</span><span class="sxs-lookup"><span data-stu-id="49321-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="49321-411">七个数字 </span><span class="sxs-lookup"><span data-stu-id="49321-411">Seven digits</span></span> 
    
- <span data-ttu-id="49321-412">一个大写字母 (区分大小写)</span><span class="sxs-lookup"><span data-stu-id="49321-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49321-413">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-413">Checksum</span></span>

<span data-ttu-id="49321-414">不适用</span><span class="sxs-lookup"><span data-stu-id="49321-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-415">Definition</span><span class="sxs-lookup"><span data-stu-id="49321-415">Definition</span></span>

<span data-ttu-id="49321-416">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-417">正则表达式`Regex_malta_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-418">找到了中`Keywords_malta_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="49321-419">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 65% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-420">正则表达式`Regex_malta_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="49321-421">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-421">Keywords</span></span>

#### <a name="keywordsmaltaeunationalidcard"></a><span data-ttu-id="49321-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="49321-423">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="49321-423">personal numeric code</span></span>
  
<span data-ttu-id="49321-424">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="49321-424">unique identification number</span></span>
  
<span data-ttu-id="49321-425">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="49321-425">citizen service number</span></span>
  
<span data-ttu-id="49321-426">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="49321-426">unique identity number</span></span>
  
<span data-ttu-id="49321-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="49321-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="49321-428">kodiċi numerali personali</span><span class="sxs-lookup"><span data-stu-id="49321-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="49321-429">numru ta "identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="49321-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="49321-430">numru tas-servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="49321-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="49321-431">numru ta "identità uniku</span><span class="sxs-lookup"><span data-stu-id="49321-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="49321-432">荷兰</span><span class="sxs-lookup"><span data-stu-id="49321-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="49321-433">格式</span><span class="sxs-lookup"><span data-stu-id="49321-433">Format</span></span>

<span data-ttu-id="49321-434">9个数字, 不带空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="49321-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-435">模式</span><span class="sxs-lookup"><span data-stu-id="49321-435">Pattern</span></span>

<span data-ttu-id="49321-436">九个数字</span><span class="sxs-lookup"><span data-stu-id="49321-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49321-437">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-437">Checksum</span></span>

<span data-ttu-id="49321-438">是</span><span class="sxs-lookup"><span data-stu-id="49321-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-439">定义</span><span class="sxs-lookup"><span data-stu-id="49321-439">Definition</span></span>

<span data-ttu-id="49321-440">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-441">函数`Func_netherlands_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-442">找到了中的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-442">A keyword from is found.</span></span>
    
<span data-ttu-id="49321-443">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-444">函数`Func_netherlands_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="49321-445">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-445">Keywords</span></span>

#### <a name="keywordsnetherlandseunationalidcard"></a><span data-ttu-id="49321-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="49321-447">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="49321-447">personal numeric code</span></span>
  
<span data-ttu-id="49321-448">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="49321-448">unique identification number</span></span>
  
<span data-ttu-id="49321-449">公民服务号码</span><span class="sxs-lookup"><span data-stu-id="49321-449">citizen service number</span></span>
  
<span data-ttu-id="49321-450">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="49321-450">unique identity number</span></span>
  
<span data-ttu-id="49321-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="49321-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="49321-452">bsn</span><span class="sxs-lookup"><span data-stu-id="49321-452">bsn</span></span>
  
<span data-ttu-id="49321-453">bsn</span><span class="sxs-lookup"><span data-stu-id="49321-453">bsn#</span></span>
  
<span data-ttu-id="49321-454">persoonlijke numerieke 代码</span><span class="sxs-lookup"><span data-stu-id="49321-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="49321-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="49321-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="49321-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="49321-456">burgerservicenummer</span></span>
  
<span data-ttu-id="49321-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="49321-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="49321-458">波兰</span><span class="sxs-lookup"><span data-stu-id="49321-458">Poland</span></span>

<span data-ttu-id="49321-459">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "波兰国家 ID (PESEL)" 一节。</span><span class="sxs-lookup"><span data-stu-id="49321-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="49321-460">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="49321-460">Portugal</span></span>

<span data-ttu-id="49321-461">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "葡萄牙公民卡片号" 部分。</span><span class="sxs-lookup"><span data-stu-id="49321-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="49321-462">罗马尼亚</span><span class="sxs-lookup"><span data-stu-id="49321-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="49321-463">格式</span><span class="sxs-lookup"><span data-stu-id="49321-463">Format</span></span>

<span data-ttu-id="49321-464">13位数, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="49321-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-465">模式</span><span class="sxs-lookup"><span data-stu-id="49321-465">Pattern</span></span>

<span data-ttu-id="49321-466">13 位数字</span><span class="sxs-lookup"><span data-stu-id="49321-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49321-467">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-467">Checksum</span></span>

<span data-ttu-id="49321-468">是</span><span class="sxs-lookup"><span data-stu-id="49321-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-469">定义</span><span class="sxs-lookup"><span data-stu-id="49321-469">Definition</span></span>

<span data-ttu-id="49321-470">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-471">函数`Func_romania_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-472">找到了中`Keywords_romania_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="49321-473">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-474">函数`Func_romania_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="49321-475">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-475">Keywords</span></span>

#### <a name="keywordsromaniaeunationalidcard"></a><span data-ttu-id="49321-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="49321-477">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="49321-477">personal numeric code</span></span>
  
<span data-ttu-id="49321-478">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="49321-478">unique identification number</span></span>
  
<span data-ttu-id="49321-479">cnp</span><span class="sxs-lookup"><span data-stu-id="49321-479">cnp</span></span>
  
<span data-ttu-id="49321-480">cnp #</span><span class="sxs-lookup"><span data-stu-id="49321-480">cnp#</span></span>
  
<span data-ttu-id="49321-481">固定</span><span class="sxs-lookup"><span data-stu-id="49321-481">pin</span></span>
  
<span data-ttu-id="49321-482">针</span><span class="sxs-lookup"><span data-stu-id="49321-482">pin#</span></span>
  
<span data-ttu-id="49321-483">保险号</span><span class="sxs-lookup"><span data-stu-id="49321-483">insurance number</span></span>
  
<span data-ttu-id="49321-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="49321-484">insurancenumber#</span></span>
  
<span data-ttu-id="49321-485">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="49321-485">unique identity number</span></span>
  
<span data-ttu-id="49321-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="49321-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="49321-487">付款的个人数字</span><span class="sxs-lookup"><span data-stu-id="49321-487">cod numeric personal</span></span>
  
<span data-ttu-id="49321-488">货到 identificare 个人</span><span class="sxs-lookup"><span data-stu-id="49321-488">cod identificare personal</span></span>
  
<span data-ttu-id="49321-489">货到付款 unic identificare</span><span class="sxs-lookup"><span data-stu-id="49321-489">cod unic identificare</span></span>
  
<span data-ttu-id="49321-490">număr 个人 unic</span><span class="sxs-lookup"><span data-stu-id="49321-490">număr personal unic</span></span>
  
<span data-ttu-id="49321-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="49321-491">număr identitate</span></span>
  
<span data-ttu-id="49321-492">număr identificare 个人</span><span class="sxs-lookup"><span data-stu-id="49321-492">număr identificare personal</span></span>
  
<span data-ttu-id="49321-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="49321-493">număridentitate#</span></span>
  
<span data-ttu-id="49321-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="49321-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="49321-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="49321-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="49321-496">斯洛伐克</span><span class="sxs-lookup"><span data-stu-id="49321-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="49321-497">格式</span><span class="sxs-lookup"><span data-stu-id="49321-497">Format</span></span>

<span data-ttu-id="49321-498">10个数字, 包含一个反斜杠</span><span class="sxs-lookup"><span data-stu-id="49321-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-499">模式</span><span class="sxs-lookup"><span data-stu-id="49321-499">Pattern</span></span>

<span data-ttu-id="49321-500">10个数字, 包含一个反斜杠:</span><span class="sxs-lookup"><span data-stu-id="49321-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="49321-501">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-501">Checksum</span></span>

<span data-ttu-id="49321-502">是</span><span class="sxs-lookup"><span data-stu-id="49321-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-503">定义</span><span class="sxs-lookup"><span data-stu-id="49321-503">Definition</span></span>

<span data-ttu-id="49321-504">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-505">函数`Func_slovakia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-506">找到了中`Keywords_slovakia_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="49321-507">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-508">函数`Func_slovakia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="49321-509">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-509">Keywords</span></span>

#### <a name="keywordsslovakiaeunationalidcard"></a><span data-ttu-id="49321-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="49321-511">出生号码</span><span class="sxs-lookup"><span data-stu-id="49321-511">birth number</span></span>
  
<span data-ttu-id="49321-512">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="49321-512">national identification number</span></span>
  
<span data-ttu-id="49321-513">个人标识号</span><span class="sxs-lookup"><span data-stu-id="49321-513">personal identification number</span></span>
  
<span data-ttu-id="49321-514">social security number
</span><span class="sxs-lookup"><span data-stu-id="49321-514">social security number</span></span>
  
<span data-ttu-id="49321-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="49321-515">nationalnumber#</span></span>
  
<span data-ttu-id="49321-516">ssn</span><span class="sxs-lookup"><span data-stu-id="49321-516">ssn#</span></span>
  
<span data-ttu-id="49321-517">ssn</span><span class="sxs-lookup"><span data-stu-id="49321-517">ssn</span></span>
  
<span data-ttu-id="49321-518">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="49321-518">national number</span></span>
  
<span data-ttu-id="49321-519">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="49321-519">personal id number</span></span>
  
<span data-ttu-id="49321-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="49321-520">personalidnumber#</span></span>
  
<span data-ttu-id="49321-521">rč</span><span class="sxs-lookup"><span data-stu-id="49321-521">rč</span></span>
  
<span data-ttu-id="49321-522">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="49321-522">rodné číslo</span></span>
  
<span data-ttu-id="49321-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="49321-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="49321-524">斯诺文尼亚</span><span class="sxs-lookup"><span data-stu-id="49321-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="49321-525">格式</span><span class="sxs-lookup"><span data-stu-id="49321-525">Format</span></span>

<span data-ttu-id="49321-526">13位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="49321-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-527">模式</span><span class="sxs-lookup"><span data-stu-id="49321-527">Pattern</span></span>

<span data-ttu-id="49321-528">指定模式中的13个数字:</span><span class="sxs-lookup"><span data-stu-id="49321-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="49321-529">与出生日期 (DDMMLLL) 对应的七位数, 其中 "LLL" 对应于出生年份的后三个数字</span><span class="sxs-lookup"><span data-stu-id="49321-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="49321-530">与出生区域对应的两个数字</span><span class="sxs-lookup"><span data-stu-id="49321-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="49321-531">三个数字, 对应于出生在同一天的人的性别和序列号组合 (000-499 的男和500-999 的女)</span><span class="sxs-lookup"><span data-stu-id="49321-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="49321-532">一个校验位</span><span class="sxs-lookup"><span data-stu-id="49321-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49321-533">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-533">Checksum</span></span>

<span data-ttu-id="49321-534">是</span><span class="sxs-lookup"><span data-stu-id="49321-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-535">定义</span><span class="sxs-lookup"><span data-stu-id="49321-535">Definition</span></span>

<span data-ttu-id="49321-536">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-537">函数`Func_slovenia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-538">找到了中`Keywords_slovenia_eu_national_id_card`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="49321-539">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-540">函数`Func_slovenia_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="49321-541">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-541">Keywords</span></span>

#### <a name="keywordssloveniaeunationalidcard"></a><span data-ttu-id="49321-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="49321-543">个人数字代码</span><span class="sxs-lookup"><span data-stu-id="49321-543">personal numeric code</span></span>
  
<span data-ttu-id="49321-544">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="49321-544">unique identification number</span></span>
  
<span data-ttu-id="49321-545">唯一注册号码</span><span class="sxs-lookup"><span data-stu-id="49321-545">unique registration number</span></span>
  
<span data-ttu-id="49321-546">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="49321-546">unique identity number</span></span>
  
<span data-ttu-id="49321-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="49321-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="49321-548">唯一的主公民号码</span><span class="sxs-lookup"><span data-stu-id="49321-548">unique master citizen number</span></span>
  
<span data-ttu-id="49321-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="49321-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="49321-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="49321-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="49321-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="49321-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="49321-552">emšo</span><span class="sxs-lookup"><span data-stu-id="49321-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="49321-553">西班牙</span><span class="sxs-lookup"><span data-stu-id="49321-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="49321-554">格式</span><span class="sxs-lookup"><span data-stu-id="49321-554">Format</span></span>

<span data-ttu-id="49321-555">七位数字后跟一个字符</span><span class="sxs-lookup"><span data-stu-id="49321-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="49321-556">模式</span><span class="sxs-lookup"><span data-stu-id="49321-556">Pattern</span></span>

<span data-ttu-id="49321-557">七位数字后跟一个字符</span><span class="sxs-lookup"><span data-stu-id="49321-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="49321-558">七个数字 </span><span class="sxs-lookup"><span data-stu-id="49321-558">Seven digits</span></span>
    
- <span data-ttu-id="49321-559">一个数字或字母 (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="49321-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="49321-560">校验和</span><span class="sxs-lookup"><span data-stu-id="49321-560">Checksum</span></span>

<span data-ttu-id="49321-561">不适用</span><span class="sxs-lookup"><span data-stu-id="49321-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="49321-562">Definition</span><span class="sxs-lookup"><span data-stu-id="49321-562">Definition</span></span>

<span data-ttu-id="49321-563">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="49321-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="49321-564">正则表达式`Regex_spain_eu_national_id_card`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="49321-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="49321-565">找到了中`Keywords_spain_eu_national_id_card"`的关键字。</span><span class="sxs-lookup"><span data-stu-id="49321-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="49321-566">关键字</span><span class="sxs-lookup"><span data-stu-id="49321-566">Keywords</span></span>

#### <a name="keywordsspaineunationalidcard"></a><span data-ttu-id="49321-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="49321-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="49321-568">dni</span><span class="sxs-lookup"><span data-stu-id="49321-568">dni</span></span>
  
<span data-ttu-id="49321-569">国家/地区标识号</span><span class="sxs-lookup"><span data-stu-id="49321-569">national identification number</span></span>
  
<span data-ttu-id="49321-570">国家/地区身份证号码</span><span class="sxs-lookup"><span data-stu-id="49321-570">national identity number</span></span>
  
<span data-ttu-id="49321-571">保险号</span><span class="sxs-lookup"><span data-stu-id="49321-571">insurance number</span></span>
  
<span data-ttu-id="49321-572">个人标识号</span><span class="sxs-lookup"><span data-stu-id="49321-572">personal identification number</span></span>
  
<span data-ttu-id="49321-573">国家标识</span><span class="sxs-lookup"><span data-stu-id="49321-573">national identity</span></span>
  
<span data-ttu-id="49321-574">个人标识编号</span><span class="sxs-lookup"><span data-stu-id="49321-574">personal identity no</span></span>
  
<span data-ttu-id="49321-575">唯一标识号</span><span class="sxs-lookup"><span data-stu-id="49321-575">unique identity number</span></span>
  
<span data-ttu-id="49321-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="49321-576">nationalidno#</span></span>
  
<span data-ttu-id="49321-577">uniqueid</span><span class="sxs-lookup"><span data-stu-id="49321-577">uniqueid#</span></span>
  
<span data-ttu-id="49321-578">dni</span><span class="sxs-lookup"><span data-stu-id="49321-578">dni#</span></span>
  
<span data-ttu-id="49321-579">nationalid #</span><span class="sxs-lookup"><span data-stu-id="49321-579">nationalid#</span></span>
  
<span data-ttu-id="49321-580">nie #</span><span class="sxs-lookup"><span data-stu-id="49321-580">nie#</span></span>
  
<span data-ttu-id="49321-581">nie</span><span class="sxs-lookup"><span data-stu-id="49321-581">nie</span></span>
  
<span data-ttu-id="49321-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="49321-582">nienúmero#</span></span>
  
<span data-ttu-id="49321-583">nie número</span><span class="sxs-lookup"><span data-stu-id="49321-583">nie número</span></span>
  
<span data-ttu-id="49321-584">documento nacional de identidad</span><span class="sxs-lookup"><span data-stu-id="49321-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="49321-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="49321-585">identidad único</span></span>
  
<span data-ttu-id="49321-586">número nacional identidad</span><span class="sxs-lookup"><span data-stu-id="49321-586">número nacional identidad</span></span>
  
<span data-ttu-id="49321-587">dni número</span><span class="sxs-lookup"><span data-stu-id="49321-587">dni número</span></span>
  
<span data-ttu-id="49321-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="49321-588">dninúmero#</span></span>
  
<span data-ttu-id="49321-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="49321-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="49321-590">瑞典</span><span class="sxs-lookup"><span data-stu-id="49321-590">Sweden</span></span>

<span data-ttu-id="49321-591">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "瑞典国家 ID" 一节。</span><span class="sxs-lookup"><span data-stu-id="49321-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="49321-592">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49321-592">See also</span></span>

[<span data-ttu-id="49321-593">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="49321-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)


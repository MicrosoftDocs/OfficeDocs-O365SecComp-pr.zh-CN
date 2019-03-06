---
title: 欧盟社会安全号码或等效 ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟社会保险号码或等效 ID 敏感信息类型时, 将会查找什么。 此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。
ms.openlocfilehash: c0c808eafa52209c79f3b4e8a2113f587fd8a771
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410797"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="8a506-104">欧盟社会安全号码或等效 ID</span><span class="sxs-lookup"><span data-stu-id="8a506-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="8a506-105">本主题介绍当数据丢失防护 (DLP) 策略检测到欧盟社会保险号码 (SSN) 或等效 ID 敏感信息类型时, 会查找什么内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="8a506-106">此敏感信息类型为每个国家/地区定义不同的模式、关键字和其他证据。</span><span class="sxs-lookup"><span data-stu-id="8a506-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="8a506-107">奥地利</span><span class="sxs-lookup"><span data-stu-id="8a506-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="8a506-108">格式</span><span class="sxs-lookup"><span data-stu-id="8a506-108">Format</span></span>

<span data-ttu-id="8a506-109">以指定格式表示的10个数字</span><span class="sxs-lookup"><span data-stu-id="8a506-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8a506-110">模式</span><span class="sxs-lookup"><span data-stu-id="8a506-110">Pattern</span></span>

<span data-ttu-id="8a506-111">10 个数字：</span><span class="sxs-lookup"><span data-stu-id="8a506-111">10 digits:</span></span>
  
-  <span data-ttu-id="8a506-112">与序列号对应的三个数字</span><span class="sxs-lookup"><span data-stu-id="8a506-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="8a506-113">一个校验位</span><span class="sxs-lookup"><span data-stu-id="8a506-113">One check digit</span></span>
    
- <span data-ttu-id="8a506-114">与出生日期对应的6个数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="8a506-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8a506-115">校验和</span><span class="sxs-lookup"><span data-stu-id="8a506-115">Checksum</span></span>

<span data-ttu-id="8a506-116">是</span><span class="sxs-lookup"><span data-stu-id="8a506-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8a506-117">定义</span><span class="sxs-lookup"><span data-stu-id="8a506-117">Definition</span></span>

<span data-ttu-id="8a506-118">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-119">函数`Func_austria_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8a506-120">找到了中`Keywords_austria_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8a506-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="8a506-121">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-122">函数`Func_austria_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8a506-123">关键字</span><span class="sxs-lookup"><span data-stu-id="8a506-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="8a506-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="8a506-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="8a506-125">社会保障号</span><span class="sxs-lookup"><span data-stu-id="8a506-125">social security no</span></span>
  
<span data-ttu-id="8a506-126">social security number</span><span class="sxs-lookup"><span data-stu-id="8a506-126">social security number</span></span>
  
<span data-ttu-id="8a506-127">social security code</span><span class="sxs-lookup"><span data-stu-id="8a506-127">social security code</span></span>
  
<span data-ttu-id="8a506-128">保险号</span><span class="sxs-lookup"><span data-stu-id="8a506-128">insurance number</span></span>
  
<span data-ttu-id="8a506-129">奥地利 ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-129">austrian ssn</span></span>
  
<span data-ttu-id="8a506-130">ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-130">ssn#</span></span>
  
<span data-ttu-id="8a506-131">ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-131">ssn</span></span>
  
<span data-ttu-id="8a506-132">保险费代码</span><span class="sxs-lookup"><span data-stu-id="8a506-132">insurance code</span></span>
  
<span data-ttu-id="8a506-133">保险代码 #</span><span class="sxs-lookup"><span data-stu-id="8a506-133">insurance code#</span></span>
  
<span data-ttu-id="8a506-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="8a506-134">socialsecurityno#</span></span>
  
<span data-ttu-id="8a506-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a506-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="8a506-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="8a506-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="8a506-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="8a506-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="8a506-138">比利时</span><span class="sxs-lookup"><span data-stu-id="8a506-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="8a506-139">格式</span><span class="sxs-lookup"><span data-stu-id="8a506-139">Format</span></span>

<span data-ttu-id="8a506-140">11位数, 不含空格或分隔符</span><span class="sxs-lookup"><span data-stu-id="8a506-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8a506-141">模式</span><span class="sxs-lookup"><span data-stu-id="8a506-141">Pattern</span></span>

<span data-ttu-id="8a506-142">11 个数字</span><span class="sxs-lookup"><span data-stu-id="8a506-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8a506-143">校验和</span><span class="sxs-lookup"><span data-stu-id="8a506-143">Checksum</span></span>

<span data-ttu-id="8a506-144">是</span><span class="sxs-lookup"><span data-stu-id="8a506-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8a506-145">定义</span><span class="sxs-lookup"><span data-stu-id="8a506-145">Definition</span></span>

<span data-ttu-id="8a506-146">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-147">函数`Func_belgium_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8a506-148">找到了中`Keywords_belgium_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8a506-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="8a506-149">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-150">函数`Func_belgium_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8a506-151">关键字</span><span class="sxs-lookup"><span data-stu-id="8a506-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="8a506-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="8a506-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="8a506-153">比利时国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="8a506-153">belgian national number</span></span>
  
<span data-ttu-id="8a506-154">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="8a506-154">national number</span></span>
  
<span data-ttu-id="8a506-155">social security number</span><span class="sxs-lookup"><span data-stu-id="8a506-155">social security number</span></span>
  
<span data-ttu-id="8a506-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="8a506-156">nationalnumber#</span></span>
  
<span data-ttu-id="8a506-157">ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-157">ssn#</span></span>
  
<span data-ttu-id="8a506-158">ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-158">ssn</span></span>
  
<span data-ttu-id="8a506-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="8a506-159">nationalnumber</span></span>
  
<span data-ttu-id="8a506-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="8a506-160">bnn#</span></span>
  
<span data-ttu-id="8a506-161">bnn</span><span class="sxs-lookup"><span data-stu-id="8a506-161">bnn</span></span>
  
<span data-ttu-id="8a506-162">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="8a506-162">personal id number</span></span>
  
<span data-ttu-id="8a506-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="8a506-163">personalidnumber#</span></span>
  
<span data-ttu-id="8a506-164">numéro 国家</span><span class="sxs-lookup"><span data-stu-id="8a506-164">numéro national</span></span>
  
<span data-ttu-id="8a506-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="8a506-165">numéro de sécurité</span></span>
  
<span data-ttu-id="8a506-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="8a506-166">numéro d'assuré</span></span>
  
<span data-ttu-id="8a506-167">identifiant 国家</span><span class="sxs-lookup"><span data-stu-id="8a506-167">identifiant national</span></span>
  
<span data-ttu-id="8a506-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="8a506-168">identifiantnational#</span></span>
  
<span data-ttu-id="8a506-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="8a506-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="8a506-170">克罗地亚</span><span class="sxs-lookup"><span data-stu-id="8a506-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="8a506-171">格式</span><span class="sxs-lookup"><span data-stu-id="8a506-171">Format</span></span>

<span data-ttu-id="8a506-172">11个数字, 无空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="8a506-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8a506-173">模式</span><span class="sxs-lookup"><span data-stu-id="8a506-173">Pattern</span></span>

 <span data-ttu-id="8a506-174">11 个数字：</span><span class="sxs-lookup"><span data-stu-id="8a506-174">11 digits:</span></span> 
  
-  <span data-ttu-id="8a506-175">10位数字</span><span class="sxs-lookup"><span data-stu-id="8a506-175">Ten digits</span></span> 
    
- <span data-ttu-id="8a506-176">一个校验位</span><span class="sxs-lookup"><span data-stu-id="8a506-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8a506-177">校验和</span><span class="sxs-lookup"><span data-stu-id="8a506-177">Checksum</span></span>

<span data-ttu-id="8a506-178">是</span><span class="sxs-lookup"><span data-stu-id="8a506-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8a506-179">定义</span><span class="sxs-lookup"><span data-stu-id="8a506-179">Definition</span></span>

<span data-ttu-id="8a506-180">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-181">函数`Func_croatia_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8a506-182">找到了中`Keywords_croatia_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8a506-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="8a506-183">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-184">函数`Func_croatia_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8a506-185">关键字</span><span class="sxs-lookup"><span data-stu-id="8a506-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="8a506-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="8a506-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="8a506-187">个人标识号</span><span class="sxs-lookup"><span data-stu-id="8a506-187">personal identification number</span></span>
  
<span data-ttu-id="8a506-188">主公民号码</span><span class="sxs-lookup"><span data-stu-id="8a506-188">master citizen number</span></span>
  
<span data-ttu-id="8a506-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="8a506-189">national identification number</span></span>
  
<span data-ttu-id="8a506-190">social security number</span><span class="sxs-lookup"><span data-stu-id="8a506-190">social security number</span></span>
  
<span data-ttu-id="8a506-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="8a506-191">nationalnumber#</span></span>
  
<span data-ttu-id="8a506-192">ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-192">ssn#</span></span>
  
<span data-ttu-id="8a506-193">ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-193">ssn</span></span>
  
<span data-ttu-id="8a506-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="8a506-194">nationalnumber</span></span>
  
<span data-ttu-id="8a506-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="8a506-195">bnn#</span></span>
  
<span data-ttu-id="8a506-196">bnn</span><span class="sxs-lookup"><span data-stu-id="8a506-196">bnn</span></span>
  
<span data-ttu-id="8a506-197">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="8a506-197">personal id number</span></span>
  
<span data-ttu-id="8a506-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="8a506-198">personalidnumber#</span></span>
  
<span data-ttu-id="8a506-199">oib</span><span class="sxs-lookup"><span data-stu-id="8a506-199">oib</span></span>
  
<span data-ttu-id="8a506-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="8a506-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="8a506-201">捷克共和国</span><span class="sxs-lookup"><span data-stu-id="8a506-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="8a506-202">格式</span><span class="sxs-lookup"><span data-stu-id="8a506-202">Format</span></span>

<span data-ttu-id="8a506-203">指定模式中的10个数字和一个反斜杠</span><span class="sxs-lookup"><span data-stu-id="8a506-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8a506-204">模式</span><span class="sxs-lookup"><span data-stu-id="8a506-204">Pattern</span></span>

<span data-ttu-id="8a506-205">10个数字和一个反斜杠:</span><span class="sxs-lookup"><span data-stu-id="8a506-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="8a506-206">与出生日期对应的6个数字 (YYMMDD):</span><span class="sxs-lookup"><span data-stu-id="8a506-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="8a506-207">反斜杠</span><span class="sxs-lookup"><span data-stu-id="8a506-207">A backslash</span></span>
    
- <span data-ttu-id="8a506-208">与一个序列号相对应的三个数字, 用于分隔出生于同一日期的人员</span><span class="sxs-lookup"><span data-stu-id="8a506-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="8a506-209">一个校验位</span><span class="sxs-lookup"><span data-stu-id="8a506-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8a506-210">校验和</span><span class="sxs-lookup"><span data-stu-id="8a506-210">Checksum</span></span>

<span data-ttu-id="8a506-211">是</span><span class="sxs-lookup"><span data-stu-id="8a506-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8a506-212">定义</span><span class="sxs-lookup"><span data-stu-id="8a506-212">Definition</span></span>

<span data-ttu-id="8a506-213">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-214">函数`Func_czech_republic_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8a506-215">找到了中`Keywords_czech_republic_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8a506-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="8a506-216">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-217">函数`Func_czech_republic_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8a506-218">关键字</span><span class="sxs-lookup"><span data-stu-id="8a506-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="8a506-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="8a506-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="8a506-220">出生号码</span><span class="sxs-lookup"><span data-stu-id="8a506-220">birth number</span></span>
  
<span data-ttu-id="8a506-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="8a506-221">national identification number</span></span>
  
<span data-ttu-id="8a506-222">个人标识号</span><span class="sxs-lookup"><span data-stu-id="8a506-222">personal identification number</span></span>
  
<span data-ttu-id="8a506-223">social security number</span><span class="sxs-lookup"><span data-stu-id="8a506-223">social security number</span></span>
  
<span data-ttu-id="8a506-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="8a506-224">nationalnumber#</span></span>
  
<span data-ttu-id="8a506-225">ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-225">ssn#</span></span>
  
<span data-ttu-id="8a506-226">ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-226">ssn</span></span>
  
<span data-ttu-id="8a506-227">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="8a506-227">national number</span></span>
  
<span data-ttu-id="8a506-228">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="8a506-228">personal id number</span></span>
  
<span data-ttu-id="8a506-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="8a506-229">personalidnumber#</span></span>
  
<span data-ttu-id="8a506-230">rč</span><span class="sxs-lookup"><span data-stu-id="8a506-230">rč</span></span>
  
<span data-ttu-id="8a506-231">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="8a506-231">rodné číslo</span></span>
  
<span data-ttu-id="8a506-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="8a506-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="8a506-233">丹麦</span><span class="sxs-lookup"><span data-stu-id="8a506-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="8a506-234">格式</span><span class="sxs-lookup"><span data-stu-id="8a506-234">Format</span></span>

<span data-ttu-id="8a506-235">指定模式中的10个数字和一个连字符</span><span class="sxs-lookup"><span data-stu-id="8a506-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8a506-236">模式</span><span class="sxs-lookup"><span data-stu-id="8a506-236">Pattern</span></span>

<span data-ttu-id="8a506-237">10个数字和一个连字符:</span><span class="sxs-lookup"><span data-stu-id="8a506-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="8a506-238">与出生日期对应的6个数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="8a506-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="8a506-239">一个连字符 </span><span class="sxs-lookup"><span data-stu-id="8a506-239">A hyphen</span></span>
    
- <span data-ttu-id="8a506-240">与序列号对应的四个数字</span><span class="sxs-lookup"><span data-stu-id="8a506-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8a506-241">校验和</span><span class="sxs-lookup"><span data-stu-id="8a506-241">Checksum</span></span>

<span data-ttu-id="8a506-242">是</span><span class="sxs-lookup"><span data-stu-id="8a506-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8a506-243">定义</span><span class="sxs-lookup"><span data-stu-id="8a506-243">Definition</span></span>

<span data-ttu-id="8a506-244">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-245">函数`Func_denmark_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8a506-246">找到了中`Keywords_denmark_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8a506-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="8a506-247">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-248">函数`Func_denmark_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8a506-249">关键字</span><span class="sxs-lookup"><span data-stu-id="8a506-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="8a506-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="8a506-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="8a506-251">个人标识号</span><span class="sxs-lookup"><span data-stu-id="8a506-251">personal identification number</span></span>
  
<span data-ttu-id="8a506-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="8a506-252">national identification number</span></span>
  
<span data-ttu-id="8a506-253">social security number</span><span class="sxs-lookup"><span data-stu-id="8a506-253">social security number</span></span>
  
<span data-ttu-id="8a506-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="8a506-254">nationalnumber#</span></span>
  
<span data-ttu-id="8a506-255">ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-255">ssn#</span></span>
  
<span data-ttu-id="8a506-256">ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-256">ssn</span></span>
  
<span data-ttu-id="8a506-257">国家/地区号码</span><span class="sxs-lookup"><span data-stu-id="8a506-257">national number</span></span>
  
<span data-ttu-id="8a506-258">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="8a506-258">personal id number</span></span>
  
<span data-ttu-id="8a506-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="8a506-259">personalidnumber#</span></span>
  
<span data-ttu-id="8a506-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="8a506-260">cpr-nummer</span></span>
  
<span data-ttu-id="8a506-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="8a506-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="8a506-262">芬兰</span><span class="sxs-lookup"><span data-stu-id="8a506-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="8a506-263">格式</span><span class="sxs-lookup"><span data-stu-id="8a506-263">Format</span></span>

<span data-ttu-id="8a506-264">指定格式的11个字符的组合</span><span class="sxs-lookup"><span data-stu-id="8a506-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8a506-265">模式</span><span class="sxs-lookup"><span data-stu-id="8a506-265">Pattern</span></span>

<span data-ttu-id="8a506-266">指定格式的11个字符的组合:</span><span class="sxs-lookup"><span data-stu-id="8a506-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="8a506-267">六位数字</span><span class="sxs-lookup"><span data-stu-id="8a506-267">Six digits</span></span> 
    
- <span data-ttu-id="8a506-268">以下任一实例:</span><span class="sxs-lookup"><span data-stu-id="8a506-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="8a506-269">加号符号</span><span class="sxs-lookup"><span data-stu-id="8a506-269">Plus symbol</span></span>
    
  - <span data-ttu-id="8a506-270">负号</span><span class="sxs-lookup"><span data-stu-id="8a506-270">Minus symbol</span></span>
    
  - <span data-ttu-id="8a506-271">字母 "A" (不区分大小写)</span><span class="sxs-lookup"><span data-stu-id="8a506-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="8a506-272">三位数字</span><span class="sxs-lookup"><span data-stu-id="8a506-272">Three digits</span></span>
    
- <span data-ttu-id="8a506-273">一个字母或一个数字</span><span class="sxs-lookup"><span data-stu-id="8a506-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8a506-274">校验和</span><span class="sxs-lookup"><span data-stu-id="8a506-274">Checksum</span></span>

<span data-ttu-id="8a506-275">是</span><span class="sxs-lookup"><span data-stu-id="8a506-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8a506-276">定义</span><span class="sxs-lookup"><span data-stu-id="8a506-276">Definition</span></span>

<span data-ttu-id="8a506-277">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-278">函数`Func_finland_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8a506-279">找到了中`Keywords_finland_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8a506-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="8a506-280">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-281">函数`Func_finland_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8a506-282">关键字</span><span class="sxs-lookup"><span data-stu-id="8a506-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="8a506-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="8a506-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="8a506-284">identification number</span><span class="sxs-lookup"><span data-stu-id="8a506-284">identification number</span></span>
  
<span data-ttu-id="8a506-285">个人 id</span><span class="sxs-lookup"><span data-stu-id="8a506-285">personal id</span></span>
  
<span data-ttu-id="8a506-286">标识号码</span><span class="sxs-lookup"><span data-stu-id="8a506-286">identity number</span></span>
  
<span data-ttu-id="8a506-287">芬兰国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="8a506-287">finnish national id number</span></span>
  
<span data-ttu-id="8a506-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="8a506-288">personalidnumber#</span></span>
  
<span data-ttu-id="8a506-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="8a506-289">national identification number</span></span>
  
<span data-ttu-id="8a506-290">id 号</span><span class="sxs-lookup"><span data-stu-id="8a506-290">id number</span></span>
  
<span data-ttu-id="8a506-291">国家/地区 id 编号。</span><span class="sxs-lookup"><span data-stu-id="8a506-291">national id no.</span></span>
  
<span data-ttu-id="8a506-292">国家/地区 id 号</span><span class="sxs-lookup"><span data-stu-id="8a506-292">national id number</span></span>
  
<span data-ttu-id="8a506-293">id 号</span><span class="sxs-lookup"><span data-stu-id="8a506-293">id no</span></span>
  
<span data-ttu-id="8a506-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="8a506-294">tunnistenumero</span></span>
  
<span data-ttu-id="8a506-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="8a506-295">henkilötunnus</span></span>
  
<span data-ttu-id="8a506-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="8a506-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="8a506-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="8a506-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="8a506-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="8a506-298">identiteetti numero</span></span>
  
<span data-ttu-id="8a506-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="8a506-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="8a506-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="8a506-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="8a506-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="8a506-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="8a506-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="8a506-302">tunnusnumero</span></span>
  
<span data-ttu-id="8a506-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="8a506-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="8a506-304">hetu</span><span class="sxs-lookup"><span data-stu-id="8a506-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="8a506-305">法国</span><span class="sxs-lookup"><span data-stu-id="8a506-305">France</span></span>

<span data-ttu-id="8a506-306">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "华北社会安全号码 (INSEE)" 一节。</span><span class="sxs-lookup"><span data-stu-id="8a506-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="8a506-307">德国</span><span class="sxs-lookup"><span data-stu-id="8a506-307">Germany</span></span>

<span data-ttu-id="8a506-308">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "德国身份证号码" 一节。</span><span class="sxs-lookup"><span data-stu-id="8a506-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="8a506-309">希腊</span><span class="sxs-lookup"><span data-stu-id="8a506-309">Greece</span></span>

<span data-ttu-id="8a506-310">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "希腊国家 ID 卡" 一节。</span><span class="sxs-lookup"><span data-stu-id="8a506-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="8a506-311">匈牙利</span><span class="sxs-lookup"><span data-stu-id="8a506-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="8a506-312">格式</span><span class="sxs-lookup"><span data-stu-id="8a506-312">Format</span></span>

<span data-ttu-id="8a506-313">9个数字, 不带空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="8a506-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8a506-314">模式</span><span class="sxs-lookup"><span data-stu-id="8a506-314">Pattern</span></span>

<span data-ttu-id="8a506-315">九个数字</span><span class="sxs-lookup"><span data-stu-id="8a506-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8a506-316">校验和</span><span class="sxs-lookup"><span data-stu-id="8a506-316">Checksum</span></span>

<span data-ttu-id="8a506-317">是</span><span class="sxs-lookup"><span data-stu-id="8a506-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8a506-318">定义</span><span class="sxs-lookup"><span data-stu-id="8a506-318">Definition</span></span>

<span data-ttu-id="8a506-319">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-320">函数`Func_hungary_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8a506-321">找到了中`Keywords_hungary_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8a506-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="8a506-322">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-323">函数`Func_hungary_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8a506-324">关键字</span><span class="sxs-lookup"><span data-stu-id="8a506-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="8a506-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="8a506-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="8a506-326">匈牙利语社会安全号码</span><span class="sxs-lookup"><span data-stu-id="8a506-326">hungarian social security number</span></span>
  
<span data-ttu-id="8a506-327">social security number</span><span class="sxs-lookup"><span data-stu-id="8a506-327">social security number</span></span>
  
<span data-ttu-id="8a506-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="8a506-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="8a506-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="8a506-329">hssn#</span></span>
  
<span data-ttu-id="8a506-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="8a506-330">socialsecuritynno</span></span>
  
<span data-ttu-id="8a506-331">hssn</span><span class="sxs-lookup"><span data-stu-id="8a506-331">hssn</span></span>
  
<span data-ttu-id="8a506-332">taj</span><span class="sxs-lookup"><span data-stu-id="8a506-332">taj</span></span>
  
<span data-ttu-id="8a506-333">taj #</span><span class="sxs-lookup"><span data-stu-id="8a506-333">taj#</span></span>
  
<span data-ttu-id="8a506-334">ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-334">ssn</span></span>
  
<span data-ttu-id="8a506-335">ssn</span><span class="sxs-lookup"><span data-stu-id="8a506-335">ssn#</span></span>
  
<span data-ttu-id="8a506-336">社会保障号</span><span class="sxs-lookup"><span data-stu-id="8a506-336">social security no</span></span>
  
<span data-ttu-id="8a506-337">áfa</span><span class="sxs-lookup"><span data-stu-id="8a506-337">áfa</span></span>
  
<span data-ttu-id="8a506-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="8a506-338">közösségi adószám</span></span>
  
<span data-ttu-id="8a506-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="8a506-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="8a506-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="8a506-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="8a506-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="8a506-341">áfa szám</span></span>
  
<span data-ttu-id="8a506-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="8a506-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="8a506-343">葡萄牙</span><span class="sxs-lookup"><span data-stu-id="8a506-343">Portugal</span></span>

<span data-ttu-id="8a506-344">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "葡萄牙公民卡片号" 部分。</span><span class="sxs-lookup"><span data-stu-id="8a506-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="8a506-345">西班牙</span><span class="sxs-lookup"><span data-stu-id="8a506-345">Spain</span></span>

<span data-ttu-id="8a506-346">有关详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)中的 "西班牙社会安全号码 (SSN)" 一节。</span><span class="sxs-lookup"><span data-stu-id="8a506-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="8a506-347">瑞典</span><span class="sxs-lookup"><span data-stu-id="8a506-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="8a506-348">格式</span><span class="sxs-lookup"><span data-stu-id="8a506-348">Format</span></span>

<span data-ttu-id="8a506-349">12个数字, 不含空格和分隔符</span><span class="sxs-lookup"><span data-stu-id="8a506-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8a506-350">模式</span><span class="sxs-lookup"><span data-stu-id="8a506-350">Pattern</span></span>

<span data-ttu-id="8a506-351">12 个数字：</span><span class="sxs-lookup"><span data-stu-id="8a506-351">12 digits:</span></span>
  
-  <span data-ttu-id="8a506-352">与出生日期对应的8位数字 (YYYYMMDD)</span><span class="sxs-lookup"><span data-stu-id="8a506-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="8a506-353">与序列号对应的三个数字, 其中:</span><span class="sxs-lookup"><span data-stu-id="8a506-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="8a506-354">序列号中的最后一个数字指示在为 "男" 分配一个奇数号码时的性别, 以及一个 "女" 的偶数号码。</span><span class="sxs-lookup"><span data-stu-id="8a506-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="8a506-355">最多 1990, 将序列号 corresponded 分配给在其中, 号码持有者出生或 (如果在1947之前出生) 的县 (根据纳税记录, 在年1月1日, 使用特殊代码 (通常为第七个数字) 的特殊代码 (通常为9号)immigrants</span><span class="sxs-lookup"><span data-stu-id="8a506-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="8a506-356">一个校验位</span><span class="sxs-lookup"><span data-stu-id="8a506-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8a506-357">校验和</span><span class="sxs-lookup"><span data-stu-id="8a506-357">Checksum</span></span>

<span data-ttu-id="8a506-358">是</span><span class="sxs-lookup"><span data-stu-id="8a506-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8a506-359">定义</span><span class="sxs-lookup"><span data-stu-id="8a506-359">Definition</span></span>

<span data-ttu-id="8a506-360">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 85% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-361">函数`Func_sweden_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8a506-362">找到了中`Keywords_sweden_eu_ssn_or_equivalent`的关键字。</span><span class="sxs-lookup"><span data-stu-id="8a506-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="8a506-363">在 300 个字符的相似度内，如果出现以下情况，DLP 策略 75% 确信它检测到这种类型的敏感信息：</span><span class="sxs-lookup"><span data-stu-id="8a506-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8a506-364">函数`Func_sweden_eu_ssn_or_equivalent`找到与该模式匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="8a506-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8a506-365">关键字</span><span class="sxs-lookup"><span data-stu-id="8a506-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="8a506-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="8a506-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="8a506-367">个人 id 号</span><span class="sxs-lookup"><span data-stu-id="8a506-367">personal id number</span></span>
  
<span data-ttu-id="8a506-368">identification number</span><span class="sxs-lookup"><span data-stu-id="8a506-368">identification number</span></span>
  
<span data-ttu-id="8a506-369">个人 id 否</span><span class="sxs-lookup"><span data-stu-id="8a506-369">personal id no</span></span>
  
<span data-ttu-id="8a506-370">identity no</span><span class="sxs-lookup"><span data-stu-id="8a506-370">identity no</span></span>
  
<span data-ttu-id="8a506-371">标识否</span><span class="sxs-lookup"><span data-stu-id="8a506-371">identification no</span></span>
  
<span data-ttu-id="8a506-372">个人标识编号</span><span class="sxs-lookup"><span data-stu-id="8a506-372">personal identification no</span></span>
  
<span data-ttu-id="8a506-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="8a506-373">personnummer id</span></span>
  
<span data-ttu-id="8a506-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="8a506-374">personligt id-nummer</span></span>
  
<span data-ttu-id="8a506-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="8a506-375">unikt id-nummer</span></span>
  
<span data-ttu-id="8a506-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="8a506-376">personnummer</span></span>
  
<span data-ttu-id="8a506-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="8a506-377">identifikationsnumret</span></span>
  
<span data-ttu-id="8a506-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="8a506-378">personnummer#</span></span>
  
<span data-ttu-id="8a506-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="8a506-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8a506-380">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a506-380">See also</span></span>

[<span data-ttu-id="8a506-381">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="8a506-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)


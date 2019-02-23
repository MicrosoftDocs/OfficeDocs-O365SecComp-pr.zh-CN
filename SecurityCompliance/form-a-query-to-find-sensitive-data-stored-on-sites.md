---
title: 创建查询以查找存储在站点上的敏感数据
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3019fbc5-7f15-4972-8d0e-dc182dc7f836
description: 使用 SharePoint Online 中的数据丢失防护 (DLP), 您可以发现在整个租户中包含敏感数据的文档。在发现文档之后, 可以使用文档所有者来保护数据。本主题可帮助您形成查询以搜索敏感数据。
ms.openlocfilehash: 3dc1081d4627f1a26c50eed84f733c31a3f6c194
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217232"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a><span data-ttu-id="7b918-105">创建查询以查找存储在站点上的敏感数据</span><span class="sxs-lookup"><span data-stu-id="7b918-105">Form a query to find sensitive data stored on sites</span></span>

<span data-ttu-id="7b918-p102">用户通常会将敏感数据 (如信用卡号、社会保险号码或个人) 存储在其网站上, 并且随着时间的推移, 这会使组织面临数据丢失的重大风险。网站上存储的文档 (包括 OneDrive for business 网站) 可以与组织外部的人员共享, 而不能访问该信息。使用 SharePoint Online 中的数据丢失防护 (DLP), 您可以发现在整个租户中包含敏感数据的文档。在发现文档之后, 可以使用文档所有者来保护数据。本主题可帮助您形成查询以搜索敏感数据。</span><span class="sxs-lookup"><span data-stu-id="7b918-p102">Users often store sensitive data, such as credit card numbers, social security numbers, or personal, on their sites, and over time this can expose an organization to significant risk of data loss. Documents stored on sites—including OneDrive for Business sites—could be shared with people outside the organization who shouldn't have access to the information. With data loss prevention (DLP) in SharePoint Online, you can discover documents that contain sensitive data throughout your tenant. After discovering the documents, you can work with the document owners to protect the data. This topic can help you form a query to search for sensitive data.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7b918-111">电子发现、电子数据展示和 DLP 是需要[SharePoint Online 计划 2](https://go.microsoft.com/fwlink/?LinkId=510080)的高级功能。</span><span class="sxs-lookup"><span data-stu-id="7b918-111">Electronic discovery, or eDiscovery, and DLP are premium features that require [SharePoint Online Plan 2](https://go.microsoft.com/fwlink/?LinkId=510080).</span></span> 
  
## <a name="forming-a-basic-dlp-query"></a><span data-ttu-id="7b918-112">创建一个基本的 DLP 查询</span><span class="sxs-lookup"><span data-stu-id="7b918-112">Forming a basic DLP query</span></span>

<span data-ttu-id="7b918-p103">共有三个部分组成基本的 DLP 查询: SensitiveType、count range 和置信度范围。如下图所示, **SensitiveType: "\<\>type"** 是必需的, 并且\*\*|\<计数范围\> **和**|\<可信度范围\> \*\*都是可选的。</span><span class="sxs-lookup"><span data-stu-id="7b918-p103">There are three parts that make up a basic DLP query: SensitiveType, count range, and confidence range. As illustrated in the following graphic, **SensitiveType:"\<type\>"** is required, and both**|\<count range\>** and**|\<confidence range\>** are optional.</span></span> 
  
![示例查询分为必需和可选两种](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a><span data-ttu-id="7b918-116">敏感类型 - 必填</span><span class="sxs-lookup"><span data-stu-id="7b918-116">Sensitive type - required</span></span>

<span data-ttu-id="7b918-p104">那么, 每个部分是什么？SharePoint DLP 查询通常以属性`SensitiveType:"`和信息类型名称从[敏感信息类型的清单](https://go.microsoft.com/fwlink/?LinkID=509999)中开始, 并以进行结尾。 `"`您还可以使用为您的组织创建的[自定义敏感信息类型](create-a-custom-sensitive-information-type.md)的名称。例如, 您可能查找包含信用卡号的文档。在这种情况下, 您可以使用以下格式: `SensitiveType:"Credit Card Number"`由于未包含计数范围或置信度范围, 因此查询将返回检测到信用卡号的每个文档。这是您可以运行的最简单的查询, 它将返回最多结果。请注意, 敏感类型的拼写和间距都很重要。</span><span class="sxs-lookup"><span data-stu-id="7b918-p104">So what is each part? SharePoint DLP queries typically begin with the property  `SensitiveType:"` and an information type name from the [sensitive information types inventory](https://go.microsoft.com/fwlink/?LinkID=509999), and end with a  `"`. You can also use the name of a [custom sensitive information type](create-a-custom-sensitive-information-type.md) that you created for your organization. For example, you might be looking for documents that contain credit card numbers. In such an instance, you'd use the following format:  `SensitiveType:"Credit Card Number"`. Because you didn't include count range or confidence range, the query returns every document in which a credit card number is detected. This is the simplest query that you can run, and it returns the most results. Keep in mind that the spelling and spacing of the sensitive type matters.</span></span> 
  
### <a name="ranges---optional"></a><span data-ttu-id="7b918-125">范围 - 选填</span><span class="sxs-lookup"><span data-stu-id="7b918-125">Ranges - optional</span></span>

<span data-ttu-id="7b918-p105">接下来的两个部分都是范围, 因此让我们快速检查区域的外观。在 SharePoint DLP 查询中, 基本范围由两个用两个句点隔开的数字表示, 如下所示`[number]..[number]`:。例如, 如果`10..20`使用, 则该范围将捕获10到20之间的数字。本主题中介绍了许多不同的范围组合和几种组合。</span><span class="sxs-lookup"><span data-stu-id="7b918-p105">Both of the next two parts are ranges, so let's quickly examine what a range looks like. In SharePoint DLP queries, a basic range is represented by two numbers separated by two periods, which looks like this:  `[number]..[number]`. For instance, if  `10..20` is used, that range would capture numbers from 10 through 20. There are many different range combinations and several are covered in this topic.</span></span> 
  
<span data-ttu-id="7b918-p106">让我们将一个计数范围添加到查询中。您可以使用计数范围定义文档在包含在查询结果中之前需要包含的敏感信息的发生次数。例如, 如果您希望查询仅返回正好包含五个信用卡号的文档, 请使用以下命令: `SensitiveType:"Credit Card Number|5"`。计数范围还可以帮助您确定带来高风险的文档。例如, 您的组织可能会考虑具有五个或更多信用卡号码的文档高风险。若要查找符合此条件的文档, 请使用以下查询`SensitiveType:"Credit Card Number|5.."`:或者, 您可以使用以下查询查找具有5个或更少信用卡号码的文档`SensitiveType:"Credit Card Number|..5"`:。</span><span class="sxs-lookup"><span data-stu-id="7b918-p106">Let's add a count range to the query. You can use count range to define the number of occurrences of sensitive information a document needs to contain before it's included in the query results. For example, if you want your query to return only documents that contain exactly five credit card numbers, use this:  `SensitiveType:"Credit Card Number|5"`. Count range can also help you identify documents that pose high degrees of risk. For example, your organization might consider documents with five or more credit card numbers a high risk. To find documents fitting this criterion, you would use this query:  `SensitiveType:"Credit Card Number|5.."`. Alternatively, you can find documents with five or fewer credit card numbers by using this query:  `SensitiveType:"Credit Card Number|..5"`.</span></span> 
  
#### <a name="confidence-range"></a><span data-ttu-id="7b918-137">置信区间</span><span class="sxs-lookup"><span data-stu-id="7b918-137">Confidence range</span></span>

<span data-ttu-id="7b918-p107">最后, 置信区间是检测到的敏感类型实际上是一个匹配的置信度。置信度范围的值的工作方式类似于计数范围。您可以在不包含计数范围的情况下形成查询。例如, 若要搜索具有任意数量信用卡号的文档, 只要可信度范围为 85% 或更高, 就可以使用此查询: `SensitiveType:"Credit Card Number|*|85.."`。</span><span class="sxs-lookup"><span data-stu-id="7b918-p107">Finally, confidence range is the level of confidence that the detected sensitive type is actually a match. The values for confidence range work similarly to count range. You can form a query without including a count range. For example, to search for documents with any number of credit card numbers—as long as the confidence range is 85 percent or higher—you would use this query:  `SensitiveType:"Credit Card Number|*|85.."`.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7b918-p108">星号 ( `*`) 是一个代表任何值有效的通配符。可以在计数区域或置信区间`*`(而不是敏感类型) 中使用通配符 ()。</span><span class="sxs-lookup"><span data-stu-id="7b918-p108">The asterisk ( `*`) is a wildcard character that means any value works. You can use the wildcard character ( `*`) either in the count range or in the confidence range, but not in a sensitive type.</span></span> 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a><span data-ttu-id="7b918-144">电子数据展示中心可用的其他查询属性和搜索运算符</span><span class="sxs-lookup"><span data-stu-id="7b918-144">Additional query properties and search operators available in the eDiscovery Center</span></span>

<span data-ttu-id="7b918-p109">SharePoint 中的 DLP 还引入了 LastSensitiveContentScan 属性, 此属性可帮助您搜索在特定时间范围内扫描的文件。有关`LastSensitiveContentScan`属性的查询示例, 请参阅下一节中的[复杂查询示例](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries)。</span><span class="sxs-lookup"><span data-stu-id="7b918-p109">DLP in SharePoint also introduces the LastSensitiveContentScan property, which can help you search for files scanned within a specific timeframe. For query examples with the  `LastSensitiveContentScan` property, see the [Examples of complex queries](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries) in the next section.</span></span> 
  
<span data-ttu-id="7b918-p110">您不仅可以使用特定于 DLP 的属性来创建查询, 还可以使用标准的 SharePoint 电子数据展示搜索`Author`属性`FileExtension`(如或)。您可以使用运算符生成复杂查询。有关可用属性和运算符的列表, 请参阅[Using Search properties and operators with eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093)博客文章。</span><span class="sxs-lookup"><span data-stu-id="7b918-p110">You can use not only DLP-specific properties to create a query, but also standard SharePoint eDiscovery search properties such as  `Author` or  `FileExtension`. You can use operators to build complex queries. For the list of available properties and operators, see the [Using Search Properties and Operators with eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093) blog post.</span></span> 
  
## <a name="examples-of-complex-queries"></a><span data-ttu-id="7b918-150">示例</span><span class="sxs-lookup"><span data-stu-id="7b918-150">Examples of complex queries</span></span>

<span data-ttu-id="7b918-151">下面的示例使用不同的敏感类型、属性和运算符来说明如何优化查询以准确查找您要查找的内容。</span><span class="sxs-lookup"><span data-stu-id="7b918-151">The following examples use different sensitive types, properties, and operators to illustrate how you can refine your queries to find exactly what you're looking for.</span></span>
  
|<span data-ttu-id="7b918-152">**Query**</span><span class="sxs-lookup"><span data-stu-id="7b918-152">**Query**</span></span>|<span data-ttu-id="7b918-153">**说明**</span><span class="sxs-lookup"><span data-stu-id="7b918-153">**Explanation**</span></span>|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |<span data-ttu-id="7b918-p111">该名称可能看起来很奇怪, 因为它很长, 但它是该敏感类型的正确名称。请务必使用[敏感信息类型清单](https://go.microsoft.com/fwlink/?LinkID=509999)中的确切名称。您还可以使用为您的组织创建的[自定义敏感信息类型](create-a-custom-sensitive-information-type.md)的名称。</span><span class="sxs-lookup"><span data-stu-id="7b918-p111">The name might seem strange because it's so long, but it's the correct name for that sensitive type. Make sure to use exact names from the [sensitive information types inventory](https://go.microsoft.com/fwlink/?LinkID=509999). You can also use the name of a [custom sensitive information type](create-a-custom-sensitive-information-type.md) that you created for your organization.  </span></span><br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |<span data-ttu-id="7b918-p112">这将返回至少有一个与敏感类型 "信用卡号码" 匹配的文档。每个区域的值分别是各自的最小值和最大值。编写此查询的更简单的方法`SensitiveType:"Credit Card Number"`是, 但其中有什么有趣之处？</span><span class="sxs-lookup"><span data-stu-id="7b918-p112">This returns documents with at least one match to the sensitive type "Credit Card Number." The values for each range are the respective minimum and maximum values. A simpler way to write this query is  `SensitiveType:"Credit Card Number"`, but where's the fun in that?  </span></span><br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |<span data-ttu-id="7b918-160">这将返回5-25 年8月11日至8月13日 (2018) 从8月11日扫描的包含信用卡号的文档。</span><span class="sxs-lookup"><span data-stu-id="7b918-160">This returns documents with 5-25 credit card numbers that were scanned from August 11, 2018 through August 13, 2018.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |<span data-ttu-id="7b918-p113">这将返回5-25 年8月11日至8月13日 (2018) 从8月11日扫描的包含信用卡号的文档。具有 .xlsx 扩展名的文件不包含在查询结果中。 `FileExtension`是可以包含在查询中的多个属性之一。有关详细信息, 请参阅将[搜索属性和运算符与电子数据展示结合使用](https://go.microsoft.com/fwlink/?LinkId=510093)。</span><span class="sxs-lookup"><span data-stu-id="7b918-p113">This returns documents with 5-25 credit card numbers that were scanned from August 11, 2018 through August 13, 2018. Files with an XLSX extension aren't included in the query results.  `FileExtension` is one of many properties that you can include in a query. For more information, see [Using Search Properties and Operators with eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093).  </span></span><br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |<span data-ttu-id="7b918-165">这将返回包含信用卡号或社会保障号的文档。</span><span class="sxs-lookup"><span data-stu-id="7b918-165">This returns documents that contain either a credit card number or a social security number.</span></span>  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a><span data-ttu-id="7b918-166">示例</span><span class="sxs-lookup"><span data-stu-id="7b918-166">Examples of queries to avoid</span></span>

<span data-ttu-id="7b918-p114">并非所有查询都具有相同的创建。下表提供了在 SharePoint 中不能使用 DLP 的查询示例并介绍了原因。</span><span class="sxs-lookup"><span data-stu-id="7b918-p114">Not all queries are created equal. The following table gives examples of queries that don't work with DLP in SharePoint and describes why.</span></span>
  
|<span data-ttu-id="7b918-169">**不支持的查询**</span><span class="sxs-lookup"><span data-stu-id="7b918-169">**Unsupported query**</span></span>|<span data-ttu-id="7b918-170">**原因**</span><span class="sxs-lookup"><span data-stu-id="7b918-170">**Reason**</span></span>|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |<span data-ttu-id="7b918-171">必须至少添加一个数值。</span><span class="sxs-lookup"><span data-stu-id="7b918-171">You must add at least one number.</span></span>  <br/> |
| `SensitiveType:"NotARule"` <br/> |<span data-ttu-id="7b918-p115">"NotARule" 不是有效的敏感类型名称。仅在 DLP 查询中的[敏感信息类型](https://go.microsoft.com/fwlink/?LinkID=509999)中的名称可供使用。</span><span class="sxs-lookup"><span data-stu-id="7b918-p115">"NotARule" isn't a valid sensitive type name. Only names in the [sensitive information types inventory](https://go.microsoft.com/fwlink/?LinkID=509999) work in DLP queries.  </span></span><br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |<span data-ttu-id="7b918-174">0不是有效的范围中的最小值或最大值。</span><span class="sxs-lookup"><span data-stu-id="7b918-174">Zero isn't valid as either the minimum value or the maximum value in a range.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |<span data-ttu-id="7b918-p116">可能很难看到, 但在 "信用卡" 和 "卡片" 之间有额外的空白, 这会导致查询无效。从[敏感信息类型的清单](https://go.microsoft.com/fwlink/?LinkID=509999)中使用精确敏感类型名称。</span><span class="sxs-lookup"><span data-stu-id="7b918-p116">It's might be difficult to see, but there's extra white space between "Credit" and "Card" that makes the query invalid. Use exact sensitive type names from the [sensitive information types inventory](https://go.microsoft.com/fwlink/?LinkID=509999).  </span></span><br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |<span data-ttu-id="7b918-177">两个句点部分不应由空格分隔。</span><span class="sxs-lookup"><span data-stu-id="7b918-177">The two-period portion shouldn't be separated by a space.</span></span>  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |<span data-ttu-id="7b918-178">管道分隔符过多 (</span><span class="sxs-lookup"><span data-stu-id="7b918-178">There are too many pipe delimiters (</span></span>|<span data-ttu-id="7b918-p117">).请改为遵循以下格式:`SensitiveType: "Credit Card Number|1..|80.."`</span><span class="sxs-lookup"><span data-stu-id="7b918-p117">). Follow this format instead: `SensitiveType: "Credit Card Number|1..|80.."`</span></span> <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |<span data-ttu-id="7b918-p118">因为可信度值表示百分比, 所以它们不能超过100。改为选择一个介于1到100之间的数字。</span><span class="sxs-lookup"><span data-stu-id="7b918-p118">Because confidence values represent a percentage, they can't exceed 100. Choose a number from 1 through 100 instead.</span></span>  <br/> |
   
## <a name="for-more-information"></a><span data-ttu-id="7b918-183">更多信息</span><span class="sxs-lookup"><span data-stu-id="7b918-183">For more information</span></span>

[<span data-ttu-id="7b918-184">敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="7b918-184">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
  
[<span data-ttu-id="7b918-185">在 Office 365 安全&amp;合规中心中运行内容搜索</span><span class="sxs-lookup"><span data-stu-id="7b918-185">Run a Content Search in the Office 365 Security &amp; Compliance Center</span></span>](run-a-content-search-in-the-security-and-compliance-center.md)
  
[<span data-ttu-id="7b918-186">内容搜索的关键字查询和搜索条件</span><span class="sxs-lookup"><span data-stu-id="7b918-186">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
  


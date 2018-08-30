---
title: 查看数据丢失防护报告
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 41eb4324-c513-4fa5-91c8-8fbd8aaba83b
description: 与 Office 365 中的 DLP 报告，您可以快速查看 DLP 策略匹配、 重写或误报; 的数请参阅是否他们正在向上或向下随时间推移趋势;以不同方式; 筛选报表和通过选择在图表上线上的某个点查看其他详细信息。
ms.openlocfilehash: 379e66fc3f2611cf338739d030c2b1d48e7416d8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013906"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="a95de-103">查看数据丢失防护报告</span><span class="sxs-lookup"><span data-stu-id="a95de-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="a95de-p101">创建数据丢失防护 (DLP) 策略后，您需要确认他们正在使用为您应和帮助您保持兼容。使用 DLP 报告 Office 365 安全性&amp;合规性中心，您可以快速查看：</span><span class="sxs-lookup"><span data-stu-id="a95de-p101">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant. With the DLP reports in the Office 365 Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="a95de-p102">**DLP 策略匹配**此报表显示一段时间的 DLP 策略匹配的计数。您可以按日期、 位置、 策略或操作筛选报告。您可以使用此报告：</span><span class="sxs-lookup"><span data-stu-id="a95de-p102">**DLP policy matches** This report shows the count of DLP policy matches over time. You can filter the report by date, location, policy, or action. You can use this report to:</span></span> 
    
  - <span data-ttu-id="a95de-p103">调整或优化您的 DLP 策略，当您在测试模式下运行它们。您可以查看匹配内容的特定规则。</span><span class="sxs-lookup"><span data-stu-id="a95de-p103">Tune or refine your DLP policies as you run them in test mode. You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="a95de-111">重点关注特定的时间段，并了解峰值和发展趋势的原因。</span><span class="sxs-lookup"><span data-stu-id="a95de-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="a95de-112">发现违反组织的 DLP 策略的业务流程。</span><span class="sxs-lookup"><span data-stu-id="a95de-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="a95de-113">通过查看操作应用于的内容，了解 DLP 策略的任何业务影响。</span><span class="sxs-lookup"><span data-stu-id="a95de-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="a95de-114">通过显示该策略的匹配结果，验证该策略是否遵守特定 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="a95de-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="a95de-115">查看最多的用户的列表，并重复用户分配给您的组织中的事件。</span><span class="sxs-lookup"><span data-stu-id="a95de-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="a95de-116">查看组织中的顶部的敏感信息类型列表。</span><span class="sxs-lookup"><span data-stu-id="a95de-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="a95de-p104">**DLP 事件**此报告还会显示策略匹配随时间推移，如策略匹配报告。但是，策略匹配规则级别; 报表显示匹配项例如，如果电子邮件匹配三个不同的规则，该策略匹配报表显示三个不同行项。相比之下，事件报告将显示匹配项级别;例如，如果电子邮件匹配三个不同的规则，事件报告将显示的内容的单个行项。</span><span class="sxs-lookup"><span data-stu-id="a95de-p104">**DLP incidents** This report also shows policy matches over time, like the policy matches report. However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items. By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="a95de-p105">由于不同聚合报告计数，策略匹配报告是更好的匹配标识与特定规则和微调 DLP 策略。事件报告是内容的用于标识特定片段 DLP 策略有问题的更好。</span><span class="sxs-lookup"><span data-stu-id="a95de-p105">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies. The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="a95de-p106">**DLP 误报和覆盖**如果您的 DLP 策略允许用户将其重写或报告为误报，此报告显示随时间这种情况下的计数。您可以按日期、 位置或策略筛选报告。您可以使用此报告：</span><span class="sxs-lookup"><span data-stu-id="a95de-p106">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time. You can filter the report by date, location, or policy. You can use this report to:</span></span> 
    
  - <span data-ttu-id="a95de-125">调整或通过查看哪些策略会引发大量误报优化您的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="a95de-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="a95de-126">查看用户提交的时它们通过覆盖该策略解析策略提示的理由。</span><span class="sxs-lookup"><span data-stu-id="a95de-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="a95de-127">发现与通过承担大量的用户的有效业务流程的 DLP 策略冲突将重写。</span><span class="sxs-lookup"><span data-stu-id="a95de-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="a95de-p107">所有 DLP 报告可以都显示的最新的四个月的时间段中的数据。最新的数据可能需要 24 小时要显示在报告中。</span><span class="sxs-lookup"><span data-stu-id="a95de-p107">All DLP reports can show data from the most recent four-month time period. The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="a95de-130">您可以安全中找到这些报告&amp;合规性中心\>**报告** \> **仪表板**。</span><span class="sxs-lookup"><span data-stu-id="a95de-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![DLP 策略匹配报告](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="a95de-132">查看由重写为用户提交理由</span><span class="sxs-lookup"><span data-stu-id="a95de-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="a95de-133">如果您的 DLP 策略允许用户覆盖它，您可以使用误报以及如何重写报表以查看策略提示中的用户提交的文本。</span><span class="sxs-lookup"><span data-stu-id="a95de-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![理由字段中的 DLP 误报和覆盖报告的详细信息](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="a95de-135">执行上见解和建议的操作</span><span class="sxs-lookup"><span data-stu-id="a95de-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="a95de-136">报告可显示见解和建议，您可以单击红色的警告图标以查看有关潜在问题的详细信息并采取可能补救措施。</span><span class="sxs-lookup"><span data-stu-id="a95de-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![单击以查看详细信息和要执行的操作的真知灼见图标](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="a95de-138">查找适用于 DLP 报告 cmdlet</span><span class="sxs-lookup"><span data-stu-id="a95de-138">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="a95de-139">要用于安全的大部分 cmdlet&amp;合规性中心，您需要：</span><span class="sxs-lookup"><span data-stu-id="a95de-139">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="a95de-140">连接到 Office 365 安全性&amp;合规性中心使用远程 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a95de-140">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="a95de-141">使用下列任一[Office 365 安全性&amp;合规性中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="a95de-141">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="a95de-p108">但是，DLP 报告需要拉跨 Office 365，包括 Exchange Online 中的数据。因此，DLP 报告的 cmdlet 是在 Exchange Online Powershell 中可用 — 不在安全&amp;合规性中心 Powershell。因此，若要使用 DLP 报告 cmdlet，您需要：</span><span class="sxs-lookup"><span data-stu-id="a95de-p108">However, DLP reports need pull data from across Office 365, including Exchange Online. For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell. Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="a95de-145">Connect to Exchange Online using remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="a95de-145">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="a95de-146">使用这些 cmdlet 的任何 DLP 报告：</span><span class="sxs-lookup"><span data-stu-id="a95de-146">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="a95de-147">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="a95de-147">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="a95de-148">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="a95de-148">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    


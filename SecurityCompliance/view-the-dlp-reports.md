---
title: 查看数据丢失防护报告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 使用 Office 365 中的 dlp 报告, 您可以快速查看 dlp 策略匹配、覆盖或误报的数量;查看它们是按时间趋势上升还是下降;以不同的方式筛选报表;并在图表上的某一行上选择一个点, 以查看其他详细信息。
ms.openlocfilehash: 447245f945bd777f56cca71320a72a9d9dd8720e
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2019
ms.locfileid: "30639019"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="cf72f-103">查看数据丢失防护报告</span><span class="sxs-lookup"><span data-stu-id="cf72f-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="cf72f-104">创建数据丢失防护 (DLP) 策略后, 您需要验证它们是否按预期工作, 并帮助您保持合规性。</span><span class="sxs-lookup"><span data-stu-id="cf72f-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="cf72f-105">在 Office 365 安全&amp;合规中心中使用 DLP 报告, 您可以快速查看:</span><span class="sxs-lookup"><span data-stu-id="cf72f-105">With the DLP reports in the Office 365 Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="cf72f-106">**DLP 策略匹配**此报告显示一段时间内 DLP 策略匹配项的计数。</span><span class="sxs-lookup"><span data-stu-id="cf72f-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="cf72f-107">您可以按日期、位置、策略或操作筛选报告。</span><span class="sxs-lookup"><span data-stu-id="cf72f-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="cf72f-108">您可以使用此报告执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="cf72f-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="cf72f-109">在测试模式下运行 DLP 策略时对其进行调整或优化。</span><span class="sxs-lookup"><span data-stu-id="cf72f-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="cf72f-110">您可以查看与内容匹配的特定规则。</span><span class="sxs-lookup"><span data-stu-id="cf72f-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="cf72f-111">重点关注特定的时间段，并了解峰值和发展趋势的原因。</span><span class="sxs-lookup"><span data-stu-id="cf72f-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="cf72f-112">发现违反组织的 DLP 策略的业务流程。</span><span class="sxs-lookup"><span data-stu-id="cf72f-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="cf72f-113">通过查看应用于内容的操作来了解 DLP 策略的任何业务影响。</span><span class="sxs-lookup"><span data-stu-id="cf72f-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="cf72f-114">通过显示该策略的匹配结果，验证该策略是否遵守特定 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="cf72f-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="cf72f-115">查看最常用用户的列表, 并重复在您的组织中参与事件的用户。</span><span class="sxs-lookup"><span data-stu-id="cf72f-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="cf72f-116">查看组织中的最高敏感信息类型的列表。</span><span class="sxs-lookup"><span data-stu-id="cf72f-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="cf72f-117">**DLP 事件**此报告还显示策略匹配一段时间, 如策略匹配报告。</span><span class="sxs-lookup"><span data-stu-id="cf72f-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="cf72f-118">但是, 策略匹配报告将显示规则级别的匹配项;例如, 如果电子邮件符合三个不同的规则, 则策略匹配报告将显示三个不同的行项目。</span><span class="sxs-lookup"><span data-stu-id="cf72f-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="cf72f-119">相比之下, 事件报告在项目级别显示匹配项;例如, 如果电子邮件与三个不同的规则匹配, 则事件报告将显示该内容的单个行项目。</span><span class="sxs-lookup"><span data-stu-id="cf72f-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="cf72f-120">由于报告计数的聚合方式不同, 因此策略匹配报告可更好地识别与特定规则的匹配项, 并精确优化 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="cf72f-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="cf72f-121">事件报告更适合标识对 DLP 策略存在问题的特定内容片段。</span><span class="sxs-lookup"><span data-stu-id="cf72f-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="cf72f-122">**DLP 误报和重写**如果您的 DLP 策略允许用户覆盖它或报告误报, 则此报告将显示一段时间内此类实例的计数。</span><span class="sxs-lookup"><span data-stu-id="cf72f-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="cf72f-123">您可以按日期、位置或策略筛选报告。</span><span class="sxs-lookup"><span data-stu-id="cf72f-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="cf72f-124">您可以使用此报告执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="cf72f-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="cf72f-125">通过查看哪些策略会导致大量误报来调整或优化 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="cf72f-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="cf72f-126">查看用户通过覆盖策略解析策略提示时提交的理由。</span><span class="sxs-lookup"><span data-stu-id="cf72f-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="cf72f-127">通过提供大量用户覆盖来发现 DLP 策略与有效业务流程发生冲突的位置。</span><span class="sxs-lookup"><span data-stu-id="cf72f-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="cf72f-128">所有 DLP 报告都可以显示最近四个月的时间段内的数据。</span><span class="sxs-lookup"><span data-stu-id="cf72f-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="cf72f-129">最新的数据可能需要长达24小时才能显示在报告中。</span><span class="sxs-lookup"><span data-stu-id="cf72f-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="cf72f-130">您&amp;可以在安全合规性中心\> **报告** \> **仪表板**中找到这些报告。</span><span class="sxs-lookup"><span data-stu-id="cf72f-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![DLP 策略匹配报告](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="cf72f-132">查看用户为替代而提交的理由</span><span class="sxs-lookup"><span data-stu-id="cf72f-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="cf72f-133">如果你的 DLP 策略允许用户覆盖它, 则可以使用误报和覆盖报告查看用户在策略提示中提交的文本。</span><span class="sxs-lookup"><span data-stu-id="cf72f-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![DLP 误报和重写报告详细信息中的调整字段](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="cf72f-135">对见解和建议采取措施</span><span class="sxs-lookup"><span data-stu-id="cf72f-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="cf72f-136">报告可以显示见解和建议, 在其中可以单击红色警告图标以查看有关潜在问题的详细信息, 并采取可能的补救措施。</span><span class="sxs-lookup"><span data-stu-id="cf72f-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![单击见解图标可查看详细信息和要执行的操作](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="cf72f-138">DLP 报告的权限</span><span class="sxs-lookup"><span data-stu-id="cf72f-138">Permissions for DLP reports</span></span>

<span data-ttu-id="cf72f-139">若要在 Security & 合规性中心中查看 DLP 报告, 您必须分配:</span><span class="sxs-lookup"><span data-stu-id="cf72f-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="cf72f-140">Exchange 管理中心中的**安全读者**角色。</span><span class="sxs-lookup"><span data-stu-id="cf72f-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="cf72f-141">默认情况下, 将此角色分配给 Exchange 管理中心中的 "组织管理" 和 "安全读者" 角色组。</span><span class="sxs-lookup"><span data-stu-id="cf72f-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="cf72f-142">Security & 合规性中心中**仅查看 DLP 合规性管理**角色。</span><span class="sxs-lookup"><span data-stu-id="cf72f-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="cf72f-143">默认情况下, 将此角色分配给安全 & 合规中心中的合规性管理员、组织管理、安全管理员和安全读者角色组。</span><span class="sxs-lookup"><span data-stu-id="cf72f-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="cf72f-144">Exchange 管理中心中的 "**仅查看收件人**" 角色。</span><span class="sxs-lookup"><span data-stu-id="cf72f-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="cf72f-145">默认情况下, 将此角色分配给 Exchange 管理中心中的合规性管理、组织管理和仅查看组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="cf72f-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="cf72f-146">查找 DLP 报告的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="cf72f-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="cf72f-147">若要将大多数 cmdlet 用于安全&amp;合规性中心, 您需要执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="cf72f-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="cf72f-148">使用远程 PowerShell 连接到 Office 365 安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="cf72f-148">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="cf72f-149">使用这些[Office 365 安全&amp;合规中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)中的任何一个</span><span class="sxs-lookup"><span data-stu-id="cf72f-149">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="cf72f-150">但是, DLP 报告需要跨 Office 365 请求获取数据, 包括 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="cf72f-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="cf72f-151">因此, DLP 报告的 cmdlet 在 Exchange Online powershell 中可用, 而不在安全&amp;合规中心 powershell 中。</span><span class="sxs-lookup"><span data-stu-id="cf72f-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="cf72f-152">因此, 若要使用 DLP 报告的 cmdlet, 需要执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="cf72f-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="cf72f-153">Connect to Exchange Online using remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf72f-153">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="cf72f-154">为 DLP 报告使用以下任一 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cf72f-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="cf72f-155">get-dlpdetectionsreport</span><span class="sxs-lookup"><span data-stu-id="cf72f-155">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [<span data-ttu-id="cf72f-156">get-dlpdetailreport</span><span class="sxs-lookup"><span data-stu-id="cf72f-156">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    


---
title: 监督报表
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2a762db5-e1c9-4c09-aa8e-bef49ce97209
description: 使用监督报告以查看的电子邮件需要合规性查看以及谁应执行它。
ms.openlocfilehash: e18d083c0aad8be945c628516e593462da8e3898
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525002"
---
# <a name="supervision-reports"></a><span data-ttu-id="ab563-103">监督报表</span><span class="sxs-lookup"><span data-stu-id="ab563-103">Supervision reports</span></span>

<span data-ttu-id="ab563-p101">监督策略定义其组织中的通信需要审阅的合规性，以及谁将执行这些 reviews （英文）。使用监督报表查看级别的策略和审阅者的查看活动。对于每个策略，您还可以查看活动的当前状态查看 live 统计信息。[了解更多有关监督策略](configure-supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ab563-p101">Supervision policies define which communications in your organization need review for compliance, and who will perform those reviews. Use the supervision reports to see the review activity at the policy and reviewer level. For each policy, you can also view live statistics on the current state of review activity. [Learn more about supervision policies ](configure-supervision-policies.md) .</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ab563-p102">使用监督策略要求对您的组织的 Office 365 E5 订阅。如果您不具有该计划，并且想要尝试监督，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="ab563-p102">Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ab563-110">您可以使用监督报告：</span><span class="sxs-lookup"><span data-stu-id="ab563-110">You can use the supervision reports to:</span></span>
  
- <span data-ttu-id="ab563-111">验证您的策略都按预期工作。</span><span class="sxs-lookup"><span data-stu-id="ab563-111">Verify that your policies are working as you intended.</span></span> 
    
- <span data-ttu-id="ab563-112">找出多少封电子邮件将被标识进行审阅。</span><span class="sxs-lookup"><span data-stu-id="ab563-112">Find out how many emails are being identified for review.</span></span>
    
- <span data-ttu-id="ab563-p103">找出多少封电子邮件不符合以及哪些传递审阅。此信息可帮助您决定是否要调整您的策略或更改审阅者的人数。</span><span class="sxs-lookup"><span data-stu-id="ab563-p103">Find out how many emails aren't compliant and which ones are passing review. This information can help you decide whether to fine-tune your policies or change the number of reviewers.</span></span>
    
## <a name="view-the-supervision-report"></a><span data-ttu-id="ab563-115">查看监督报告</span><span class="sxs-lookup"><span data-stu-id="ab563-115">View the Supervision report</span></span>

1. <span data-ttu-id="ab563-116">登录到[安全&amp;合规性中心](https://protection.office.com/)使用您有权查看监督报告的 Office 365 组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="ab563-116">Sign into the [Security &amp; Compliance Center](https://protection.office.com/) using the credentials for an admin account in your Office 365 organization that has permissions to view supervision reports..</span></span> 
    
2. <span data-ttu-id="ab563-p104">转到**报告** \> **仪表板**。您将看到监督的报告小部件和其他报告您有权访问。</span><span class="sxs-lookup"><span data-stu-id="ab563-p104">Go to **Reports** \> **Dashboard**. You'll see a reporting widget for supervision and other reports you have access to.</span></span>
    
3. <span data-ttu-id="ab563-119">单击要打开详细的报告页上的**监督**构件。</span><span class="sxs-lookup"><span data-stu-id="ab563-119">Click the **Supervision** widget to open the detailed report page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="ab563-p105">如果您不能访问**报告**页上，检查您监督审阅角色组的成员[进行监督在组织中可用](configure-supervision-policies.md#SRavailable)中所述。要包含在此角色组，可以创建和管理监督策略并运行报告。</span><span class="sxs-lookup"><span data-stu-id="ab563-p105">If you aren't able to access the **Reports** page, check that you're a member of the Supervisory Review role group, as described in [Make supervision available in your organization](configure-supervision-policies.md#SRavailable). Being included in this role group lets you create and manage supervision polices and run the report.</span></span> 
  
## <a name="how-to-use-the-report"></a><span data-ttu-id="ab563-122">如何使用报告</span><span class="sxs-lookup"><span data-stu-id="ab563-122">How to use the report</span></span>

<span data-ttu-id="ab563-p106">当监督策略识别电子邮件进行审阅时，电子邮件传递到审阅者的监督文件夹中 Outlook 和 Outlook web 应用程序。此报告列出了在审阅过程中每个阶段每项策略的名称和通信数目。</span><span class="sxs-lookup"><span data-stu-id="ab563-p106">When a supervision policy identifies an email for review, the email is delivered to the reviewer's Supervision folder in Outlook and Outlook web app. This report lists each policy's name and the number of communications at each stage in the review process.</span></span>
  
<span data-ttu-id="ab563-125">使用报告：</span><span class="sxs-lookup"><span data-stu-id="ab563-125">Use the report to:</span></span>
  
- <span data-ttu-id="ab563-126">查看数据的所有或特定的策略。</span><span class="sxs-lookup"><span data-stu-id="ab563-126">View data for all or specific policies.</span></span>
    
- <span data-ttu-id="ab563-127">查看按 （如符合、 Questionable 等） 的标记类型、 审阅者或消息类型分组的数据。</span><span class="sxs-lookup"><span data-stu-id="ab563-127">View data grouped by tag type (such as Compliant, Questionable, etc.), reviewer, or message type.</span></span>
    
- <span data-ttu-id="ab563-128">将数据导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="ab563-128">Export data to a CSV file.</span></span>
    
- <span data-ttu-id="ab563-129">筛选上查看活动日期、 标记类型、 审阅者、 消息类型基于的数据。</span><span class="sxs-lookup"><span data-stu-id="ab563-129">Filter data based on review activity date, tag type, reviewer, message type.</span></span>
    
<span data-ttu-id="ab563-130">下面是您可能会看到**标记类型**列中的值的细分。</span><span class="sxs-lookup"><span data-stu-id="ab563-130">Here's a breakdown of the values you might see in the **Tag type** column.</span></span> 
  
|<span data-ttu-id="ab563-131">**标记类型**</span><span class="sxs-lookup"><span data-stu-id="ab563-131">**Tag type**</span></span>|<span data-ttu-id="ab563-132">**含义**</span><span class="sxs-lookup"><span data-stu-id="ab563-132">**What it means**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ab563-133">未检查</span><span class="sxs-lookup"><span data-stu-id="ab563-133">Not Reviewed</span></span>  <br/> |<span data-ttu-id="ab563-p107">尚未评审的电子邮件数。这些电子邮件正在等待审阅在 Outlook 中的审阅者的监督文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ab563-p107">The number of emails that have not been reviewed yet. These emails are awaiting review in the reviewer's supervision folder in Outlook.</span></span>  <br/> |
|<span data-ttu-id="ab563-136">符合标准</span><span class="sxs-lookup"><span data-stu-id="ab563-136">Compliant</span></span>  <br/> |<span data-ttu-id="ab563-p108">电子邮件数审核和标记为兼容。需要没有进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="ab563-p108">The number of emails reviewed and marked as compliant. No further action is needed.</span></span>  <br/> |
|<span data-ttu-id="ab563-139">可疑</span><span class="sxs-lookup"><span data-stu-id="ab563-139">Questionable</span></span>  <br/> |<span data-ttu-id="ab563-p109">电子邮件数审核和标记可疑。这会作为一个标志;其他审阅人可以帮助检查电子邮件是否需要合规性的调查。</span><span class="sxs-lookup"><span data-stu-id="ab563-p109">The number of emails reviewed and marked questionable. This acts as a flag; other reviewers can help check whether an email needs investigation for compliance.</span></span>  <br/> |
|<span data-ttu-id="ab563-142">不兼容 （活动）</span><span class="sxs-lookup"><span data-stu-id="ab563-142">Non-Compliant (Active)</span></span>  <br/> |<span data-ttu-id="ab563-143">当前正在调查审阅者的不符合电子邮件数。</span><span class="sxs-lookup"><span data-stu-id="ab563-143">The number of non-compliant emails that reviewers are currently investigating.</span></span>  <br/> |
|<span data-ttu-id="ab563-144">不兼容 （解析）</span><span class="sxs-lookup"><span data-stu-id="ab563-144">Non-Compliant (Resolved)</span></span>  <br/> |<span data-ttu-id="ab563-145">不兼容的电子邮件的审阅者调查和解析数。</span><span class="sxs-lookup"><span data-stu-id="ab563-145">The number of non-compliant emails that reviewers investigated and resolved.</span></span>  <br/> |
   
## <a name="more-details"></a><span data-ttu-id="ab563-146">更多详细信息</span><span class="sxs-lookup"><span data-stu-id="ab563-146">More details</span></span>

- <span data-ttu-id="ab563-147">将出现在此报告中之前，必须首先设置监督策略。</span><span class="sxs-lookup"><span data-stu-id="ab563-147">Supervision policies must first be provisioned before they will appear in this report.</span></span>
    
- <span data-ttu-id="ab563-p110">如果删除了策略，仍显示历史数据。但是，它们显示为"非存在策略，"和**导出**函数不可用。</span><span class="sxs-lookup"><span data-stu-id="ab563-p110">If policies are deleted, historical data is still shown. However, they're indicated as a "Non-existent policy", and the **Export** function isn't available.</span></span> 
    
- <span data-ttu-id="ab563-p111">如果报表不显示任何数据，默认情况下，则可能是因为当前日期范围没有要显示的数据。在这些情况下，使用**筛选器**控件更改的日期范围。</span><span class="sxs-lookup"><span data-stu-id="ab563-p111">If the report doesn't show any data by default, it might be because the current date range doesn't have any data to show. In these cases, use the **Filters** control to change the date range.</span></span> 
    


---
title: Office 365 安全功能分数
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/25/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: 想知道如何安全组织真的是 Office 365 中？安全分数此处以帮助。安全分数分析基于您的正则活动和 Office 365 中的安全设置的组织的安全性，并分配分数。
ms.openlocfilehash: bc0379e40b09e63e5fded1b1a289d40c306def91
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29559085"
---
# <a name="office-365-secure-score"></a><span data-ttu-id="0d015-105">Office 365 安全功能分数</span><span class="sxs-lookup"><span data-stu-id="0d015-105">Office 365 Secure Score</span></span>

<span data-ttu-id="0d015-p102">**摘要**想知道如何安全组织真的是 Office 365 中？安全分数此处以帮助。安全分数分析基于您的正则活动和 Office 365 中的安全设置的组织的安全性，并分配分数。阅读这篇文章，获取安全分数和如何使用它的概述。</span><span class="sxs-lookup"><span data-stu-id="0d015-p102">**Summary** Ever wonder how secure your organization really is in Office 365? Secure Score is here to help. Secure Score analyzes your organization's security  based on your regular activities and security settings in Office 365, and assigns a score. Read this article to get an overview of Secure Score and how you can use it.</span></span>
  
## <a name="how-to-get-to-secure-score"></a><span data-ttu-id="0d015-110">如何获取安全分数</span><span class="sxs-lookup"><span data-stu-id="0d015-110">How to get to Secure Score</span></span>

<span data-ttu-id="0d015-111">如果您的组织具有订阅包含[Office 365 企业版](https://docs.microsoft.com/office365/enterprise/)、 [Microsoft 365 企业版](https://docs.microsoft.com/microsoft-365/business/)或 Office 365 企业高级版，并且您[所需的权限](#required-permissions)，则可以通过访问查看贵组织的安全分数[https://securescore.office.com](https://securescore.office.com).</span><span class="sxs-lookup"><span data-stu-id="0d015-111">If your organization has a subscription that includes [Office 365 Enterprise](https://docs.microsoft.com/office365/enterprise/), [Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/business/), or Office 365 Business Premium, and you have the [necessary permissions](#required-permissions), you can view your organization's secure score by visiting [https://securescore.office.com](https://securescore.office.com).</span></span> 

<span data-ttu-id="0d015-112">此外，您可以访问安全 & 合规性中心 ([https://protection.office.com](https://protection.office.com))，将在其中找到您当前的分数为您提供一个安全分数构件。</span><span class="sxs-lookup"><span data-stu-id="0d015-112">Alternatively, you can visit the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), where you'll find a Secure Score widget that provides you with your current score.</span></span>

![安全分数小部件](media/SecureScoreWidget-o365.png)

<span data-ttu-id="0d015-114">小部件包含将向安全分数仪表板的链接。</span><span class="sxs-lookup"><span data-stu-id="0d015-114">The widget includes a link to your Secure Score dashboard.</span></span>

![安全分数仪表板](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a><span data-ttu-id="0d015-116">如何工作</span><span class="sxs-lookup"><span data-stu-id="0d015-116">How it works</span></span>

<span data-ttu-id="0d015-p103">安全分数确定哪些然后您将 （如 OneDrive、 SharePoint 和 Exchange） 的 Office 365 服务比较您的设置和到由 Microsoft 建立一个比较基准的活动。您将获取的分数，具体取决于您的组织也对齐是与安全性最佳实践。您还将建议上以提高组织的分数可采取的步骤。</span><span class="sxs-lookup"><span data-stu-id="0d015-p103">Secure Score determines what Office 365 services you're using (such as OneDrive, SharePoint, and Exchange) then compares your settings and activities to a baseline established by Microsoft. You'll get a score based on how well aligned your organization is with security best practices. You'll also get recommendations on steps you can take to improve your organization's score.</span></span> 
  
![在 Office 365 安全分数工具的操作队列](media/SecureScore-ActionsToTake.png)
  
<span data-ttu-id="0d015-p104">安全分数计算您根据您购买的服务的分数。例如，如果仅购买 Exchange Online 的计划，您不被计分 SharePoint Online 的安全功能。分数的分母，为是适用于您购买的产品的控件的所有比较基准的总数。分子是为其所有控件的已完成或部分已完成的操作，以满足该控件的总和。</span><span class="sxs-lookup"><span data-stu-id="0d015-p104">Secure Score calculates your score based on the services you purchased. For example, if you only purchased an Exchange Online plan, you won't be scored for SharePoint Online security features. The denominator of the score is the sum of all the baselines for the controls that apply to the products you purchased. The numerator is the sum of all the controls for which you completed, or partially completed, the actions to fulfill that control.</span></span>

<span data-ttu-id="0d015-125">展开要了解有关什么步骤，它将帮助保护，从您的威胁和多少 points 您分数会增加后遵循建议的操作。</span><span class="sxs-lookup"><span data-stu-id="0d015-125">Expand an action to learn about what steps to take, the threats it'll help protect you from, and how many points your score will increase once you follow the recommendation.</span></span>
  
![在 Office 365 安全分数工具扩展的操作](media/SecureScore-DetailedActionToTake.png)
  
<span data-ttu-id="0d015-127">若要对贵组织的安全性，请参阅您的操作的影响，选择**分数分析器**选项卡，并查看历史记录。</span><span class="sxs-lookup"><span data-stu-id="0d015-127">To see the impact of your actions on your organization's security, select the **Score Analyzer** tab and review your history.</span></span> 
  
![Office 365 安全分数工具分数分析器选项卡](media/SecureScore-ScoreAnalyzer-7days.png)
  
<span data-ttu-id="0d015-129">下面的图表中，您将看到分数和操作的列表，按类别。</span><span class="sxs-lookup"><span data-stu-id="0d015-129">Below the chart, you'll see a list of scores and actions by category.</span></span> 
  
![图表显示所选数据点分数分析器选项卡](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
<span data-ttu-id="0d015-131">您可以执行的您的组织，如 **[不对评分]** 是标记的操作，但因为它们不连接到安全分数，不对评分。</span><span class="sxs-lookup"><span data-stu-id="0d015-131">Actions that are labeled as **[Not Scored]** are ones you can perform for your organization, but because they are not connected to Secure Score, they are not scored.</span></span>  

<span data-ttu-id="0d015-p105">上**分数分析器**页上，单击某一天，数据点，然后向下滚动到的已完成并不完整的操作，以找出哪些该天的更改，请参阅。分数计算每一天 (大约 1:00 PST) 一次。如果您更改了测量操作，分数将自动更新一天。计 48 小时才能反映您分数的更改。</span><span class="sxs-lookup"><span data-stu-id="0d015-p105">On the **Score Analyzer** page, click a data point for a specific day, then scroll down to see the completed and incomplete actions for that day to find out what changed. The score is calculated once per day (around 1:00 AM PST). If you make a change to a measured action, the score will automatically update the next day. It takes up to 48 hours for a change to be reflected in your score.</span></span>

<span data-ttu-id="0d015-p106">安全分数不 express 绝对的度量单位的方式可能要获取破坏。它表示您采用可以偏移正在看见的风险的功能的范围。没有服务都无法保证，您将不违反，和安全分数不应视为以任何方式保证。</span><span class="sxs-lookup"><span data-stu-id="0d015-p106">Secure Score does not express an absolute measure of how likely you are to get breached. It expresses the extent to which you have adopted features that can offset the risk of being breached. No service can guarantee that you will not be breached, and the Secure Score should not be interpreted as a guarantee in any way.</span></span>
 
## <a name="how-secure-score-helps"></a><span data-ttu-id="0d015-139">如何帮助保护分数</span><span class="sxs-lookup"><span data-stu-id="0d015-139">How Secure Score helps</span></span>

<span data-ttu-id="0d015-p107">安全分数，有助于提高组织的安全状况 （其中许多您已购买，但可能不知道的） 的 Office 365 中使用的内置安全功能。若要了解有关这些功能可帮助您放心，您采取右步骤保护您的组织免受威胁。</span><span class="sxs-lookup"><span data-stu-id="0d015-p107">With Secure Score, you can help improve your organization's security posture by using the built-in security features in Office 365 (many of which you already purchased but might not be aware of). Learning more about these features can help give you peace of mind that you're taking the right steps to protect your organization from threats.</span></span>
  
<span data-ttu-id="0d015-p108">但不只是为其相信我们所说。使用安全分数客户已看到其分数增加 5 次比客户不使用它。（及其分数增加对应于在组织中使用的安全功能）。</span><span class="sxs-lookup"><span data-stu-id="0d015-p108">But don't just take our word for it. Customers who are using Secure Score have seen their score increase five times more than customers who aren't using it. (The increase in their score corresponds with the security features being used in their organizations.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="0d015-p109">安全分数不 express 绝对的度量单位的方式可能要获取破坏。它表示您采用控件可以偏移正在看见的风险的程度。没有服务都无法保证，您将不违反，和安全分数不应视为以任何方式保证。</span><span class="sxs-lookup"><span data-stu-id="0d015-p109">Secure Score does not express an absolute measure of how likely you are to get breached. It expresses the extent to which you have adopted controls which can offset the risk of being breached. No service can guarantee that you will not be breached, and Secure Score should not be interpreted as a guarantee in any way.</span></span> 
  
## <a name="required-permissions"></a><span data-ttu-id="0d015-148">必需的权限</span><span class="sxs-lookup"><span data-stu-id="0d015-148">Required permissions</span></span>

<span data-ttu-id="0d015-149">若要查看和使用安全分数仪表板，您必须为分配 Azure Active Directory 中的以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="0d015-149">In order to view and use your Secure Score dashboard, you must be assigned one of the following roles in Azure Active Directory:</span></span>
- <span data-ttu-id="0d015-150">全局管理员</span><span class="sxs-lookup"><span data-stu-id="0d015-150">Global Administrator</span></span>
- <span data-ttu-id="0d015-151">帐务管理员</span><span class="sxs-lookup"><span data-stu-id="0d015-151">Billing Administrator</span></span>
- <span data-ttu-id="0d015-152">用户管理员</span><span class="sxs-lookup"><span data-stu-id="0d015-152">User Administrator</span></span>
- <span data-ttu-id="0d015-153">密码管理员</span><span class="sxs-lookup"><span data-stu-id="0d015-153">Password Administrator</span></span>
- <span data-ttu-id="0d015-154">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="0d015-154">Security Administrator</span></span>
- <span data-ttu-id="0d015-155">安全读者</span><span class="sxs-lookup"><span data-stu-id="0d015-155">Security Reader</span></span>
- <span data-ttu-id="0d015-156">Exchange 管理员</span><span class="sxs-lookup"><span data-stu-id="0d015-156">Exchange Administrator</span></span>
- <span data-ttu-id="0d015-157">SharePoint 管理员</span><span class="sxs-lookup"><span data-stu-id="0d015-157">SharePoint Administrator</span></span>

 <span data-ttu-id="0d015-158">未分配管理员角色的用户将无法访问 Secure 分数。</span><span class="sxs-lookup"><span data-stu-id="0d015-158">Users who aren't assigned an admin role won't be able to access Secure Score.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0d015-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="0d015-159">Related topics</span></span>

[<span data-ttu-id="0d015-160">安全仪表板概述 （英文)</span><span class="sxs-lookup"><span data-stu-id="0d015-160">Security dashboard overview</span></span>](security-dashboard.md)

[<span data-ttu-id="0d015-161">我订阅了哪些产品？</span><span class="sxs-lookup"><span data-stu-id="0d015-161">What subscription do I have?</span></span>](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)
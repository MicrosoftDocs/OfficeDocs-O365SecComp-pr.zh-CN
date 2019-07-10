---
title: 启用报表消息加载项
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 03/26/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何为单个用户或您的整个组织启用 Outlook 和 web 上的 outlook 和 Outlook 网页版报告消息外接程序。
ms.openlocfilehash: 2c1fe3afd52afed17327a4ad2a5a493721b541fd
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599968"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="9d62f-103">启用报表消息加载项</span><span class="sxs-lookup"><span data-stu-id="9d62f-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="9d62f-104">Outlook 和 web 上的 Outlook 的报告邮件外接程序与[Outlook 垃圾邮件筛选器](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)并不完全相同, 但这两者都可用于将电子邮件标记为垃圾邮件、非垃圾邮件或网络钓鱼尝试。</span><span class="sxs-lookup"><span data-stu-id="9d62f-104">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt.</span></span> <span data-ttu-id="9d62f-105">不同之处在于, Outlook 和 web 上的 Outlook 的报告邮件外接程序会通知 Microsoft misclassified 电子邮件, 而 Outlook 垃圾邮件筛选器用于组织用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9d62f-105">The difference is, the Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span> 

## <a name="overview"></a><span data-ttu-id="9d62f-106">概述</span><span class="sxs-lookup"><span data-stu-id="9d62f-106">Overview</span></span>

<span data-ttu-id="9d62f-107">Outlook 和 web 上的 Outlook 的报告消息外接程序使用户能够轻松地向 Microsoft 及其子公司报告 misclassified 电子邮件 (无论是安全还是恶意)。</span><span class="sxs-lookup"><span data-stu-id="9d62f-107">The Report Message add-in for Outlook and Outlook on the web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="9d62f-108">Microsoft 使用这些提交改进电子邮件保护技术的有效性。</span><span class="sxs-lookup"><span data-stu-id="9d62f-108">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="9d62f-109">此外, 如果您的组织使用的是[Office 365 高级威胁防护计划 1](office-365-atp.md)或[计划 2](office-365-ti.md), 则报告消息外接程序会为您组织的安全团队提供可用于查看和更新安全策略的有用信息。</span><span class="sxs-lookup"><span data-stu-id="9d62f-109">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="9d62f-110">例如, 假设有人将大量邮件报告为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="9d62f-110">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="9d62f-111">[安全仪表板](security-dashboard.md)和其他报告中的此信息图面。</span><span class="sxs-lookup"><span data-stu-id="9d62f-111">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="9d62f-112">组织的安全团队可以使用此信息指示可能需要更新的反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="9d62f-112">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="9d62f-113">或者, 如果用户使用报告邮件外接程序报告大量被标记为垃圾邮件的邮件, 则组织的安全团队可能需要调整[反垃圾邮件策略](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9d62f-113">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="9d62f-114">报告邮件外接程序适用于 Office 365 订阅和以下产品:</span><span class="sxs-lookup"><span data-stu-id="9d62f-114">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="9d62f-115">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="9d62f-115">Outlook on the web</span></span>
 - <span data-ttu-id="9d62f-116">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="9d62f-116">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="9d62f-117">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9d62f-117">Outlook 2016</span></span>
 - <span data-ttu-id="9d62f-118">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="9d62f-118">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="9d62f-119">Outlook 包含在 Office 365 专业增强版中</span><span class="sxs-lookup"><span data-stu-id="9d62f-119">Outlook included with Office 365 ProPlus</span></span>

<span data-ttu-id="9d62f-120">您的现有 web 浏览器应该能够满足报告消息外接程序的需要。但是, 如果您注意到加载项不可用或无法按预期工作, 请尝试使用不同的浏览器。</span><span class="sxs-lookup"><span data-stu-id="9d62f-120">Your existing web browser should suffice for the Report Message add-in to work; however, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>
  
<span data-ttu-id="9d62f-121">如果您是单个用户, 则可以[为自己启用报告邮件加载项](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="9d62f-121">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="9d62f-122">如果您是 Office 365 全局管理员或 Exchange Online 管理员, 并且将 Exchange 配置为使用 OAuth 身份验证, 则可以[为您的组织启用报告消息外接程序](#get-and-enable-the-report-message-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="9d62f-122">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="9d62f-123">现在, 可以通过[集中部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)使用报告消息加载项。</span><span class="sxs-lookup"><span data-stu-id="9d62f-123">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="9d62f-124">获取自己的报告邮件外接程序</span><span class="sxs-lookup"><span data-stu-id="9d62f-124">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="9d62f-125">在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)中, 搜索[报告邮件外接程序](https://appsource.microsoft.com/product/office/wa104381180)。</span><span class="sxs-lookup"><span data-stu-id="9d62f-125">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="9d62f-126">选择 "**立即获取**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-126">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="9d62f-127">![报告消息-立即获取](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-127">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="9d62f-128">查看使用条款和隐私策略。</span><span class="sxs-lookup"><span data-stu-id="9d62f-128">Review the terms of use and privacy policy.</span></span> <span data-ttu-id="9d62f-129">然后选择" **继续**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-129">Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="9d62f-130">使用你的工作或学校帐户 (用于商业用途) 或你的 Microsoft 帐户 (供个人使用) 登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9d62f-130">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="9d62f-131">安装并启用加载项后, 您将看到以下图标:</span><span class="sxs-lookup"><span data-stu-id="9d62f-131">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="9d62f-132">在 Outlook 中, 图标如下所示:</span><span class="sxs-lookup"><span data-stu-id="9d62f-132">In Outlook, the icon looks like this:</span></span> <br/> ![报告邮件外接程序图标 (适用于 Outlook)](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="9d62f-134">在 web 上的 Outlook (以前称为 Outlook Web App) 中, 图标如下所示:</span><span class="sxs-lookup"><span data-stu-id="9d62f-134">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span><br/>![Outlook 网页报告邮件加载项图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="9d62f-136">作为下一步, 了解如何[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="9d62f-136">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="9d62f-137">为您的组织获取并启用报告邮件外接程序</span><span class="sxs-lookup"><span data-stu-id="9d62f-137">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d62f-138">若要完成此任务, 您必须是 Office 365 全局管理员或 Exchange Online 管理员。</span><span class="sxs-lookup"><span data-stu-id="9d62f-138">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span> <span data-ttu-id="9d62f-139">此外, 必须将 Exchange 配置为使用 OAuth 身份验证以了解详细信息, 请参阅[exchange 要求 (加载项的集中部署)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="9d62f-139">In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span> 

1. <span data-ttu-id="9d62f-140">转到 Microsoft 365 管理中心中的 "[服务 & 外接程序" 页面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="9d62f-140">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="9d62f-141">![新 Microsoft 365 管理中心中的 "服务和外接程序" 页](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-141">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="9d62f-142">选择 " **+ 部署外接端"**。</span><span class="sxs-lookup"><span data-stu-id="9d62f-142">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="9d62f-143">![选择 "部署加载项"](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-143">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="9d62f-144">在 "**新建外接端**" 屏幕中, 查看信息, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-144">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="9d62f-145">![新加载项详细信息](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-145">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="9d62f-146">选择 **"我想从 Office 应用商店添加外接程序**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-146">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="9d62f-147">![我想要添加新的外接程序](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-147">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="9d62f-148">搜索**报告消息**, 并在结果列表中的**报告邮件外接程序**旁边, 选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-148">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span><br/><span data-ttu-id="9d62f-149">![搜索报告消息, 然后选择 "添加"](media/NewAddInScreen3.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-149">![Search for Report Message and then choose Add](media/NewAddInScreen3.png)</span></span><br/>
    
6. <span data-ttu-id="9d62f-150">在 "**报告邮件**" 屏幕上, 查看信息, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-150">On the **Report Message** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="9d62f-151">![报告消息详细信息](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-151">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="9d62f-152">指定 Outlook 的用户默认设置, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-152">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="9d62f-153">![为 Outlook 报告邮件的默认设置](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-153">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="9d62f-154">指定要获取报告邮件加载项的收件人, 然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-154">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="9d62f-155">![谁可以获取报告邮件加载项](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-155">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="9d62f-156">建议[设置一个规则, 以获取用户报告的电子](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="9d62f-156">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="9d62f-157">根据您在设置加载项时选择的内容 (上面的步骤 7-8), 贵组织中的人员将会看到[报告消息外接程序](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="9d62f-157">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available.</span></span> <span data-ttu-id="9d62f-158">你组织中的人员将看到以下图标:</span><span class="sxs-lookup"><span data-stu-id="9d62f-158">People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="9d62f-159">在 Outlook 中, 图标如下所示:</span><span class="sxs-lookup"><span data-stu-id="9d62f-159">In Outlook, the icon looks like this:</span></span> <br/> ![报告邮件外接程序图标 (适用于 Outlook)](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="9d62f-161">在 web 上的 Outlook 中, 图标如下所示:</span><span class="sxs-lookup"><span data-stu-id="9d62f-161">In Outlook on the web, the icon looks like this:</span></span><br/>![Outlook 网页报告邮件加载项图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="9d62f-163">当您通知用户有关报告邮件加载项时, 请包含[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的链接。</span><span class="sxs-lookup"><span data-stu-id="9d62f-163">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="9d62f-164">设置一个规则, 以获取用户报告的电子邮件的副本</span><span class="sxs-lookup"><span data-stu-id="9d62f-164">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d62f-165">您必须是 Exchange Online 管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="9d62f-165">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="9d62f-166">您可以设置一个规则, 以获取由组织中的用户报告的电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="9d62f-166">You can set up a rule to get a copy of email messages reported by users in your organization.</span></span> <span data-ttu-id="9d62f-167">为组织下载并启用报告邮件外接程序后, 可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9d62f-167">You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="9d62f-168">在 Exchange 管理中心中, 选择 "**邮件流** \> **规则**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-168">In the Exchange admin center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="9d62f-169">选择**+** \> "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-169">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="9d62f-170">在 "**名称**" 框中, 键入一个名称, 如 "提交"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-170">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="9d62f-171">在 "在**以下情况应用此规则**" 列表中, 选择**收件人地址包括 ...**。</span><span class="sxs-lookup"><span data-stu-id="9d62f-171">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="9d62f-172">在 "**指定字词或短语**" 屏幕中`junk@office365.microsoft.com` , `phish@office365.microsoft.com`添加和, 然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="9d62f-172">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="9d62f-173">![指定规则的垃圾邮件和网络钓鱼电子邮件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-173">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="9d62f-174">在 "**执行以下操作 ...** " 列表中, 选择 **"将邮件密件抄送给 ...**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-174">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="9d62f-175">添加全局管理员、安全管理员和/或安全阅读者, 这些读者应收到用户报告给 Microsoft 的每封电子邮件的副本, 然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="9d62f-175">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="9d62f-176">![添加全局或安全管理员以接收每个报告的邮件的副本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-176">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="9d62f-177">选择 "**使用严重性级别审核此规则**", 然后选择 "**中**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-177">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="9d62f-178">在 "**为此规则选择模式**" 下, 选择 "**强制**"。</span><span class="sxs-lookup"><span data-stu-id="9d62f-178">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="9d62f-179">![设置一个规则以获取每个报告的邮件的副本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-179">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="9d62f-180">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9d62f-180">Choose **Save**.</span></span> 
    
<span data-ttu-id="9d62f-181">在适当的情况下, 当组织中的某人使用报告邮件加载项报告电子邮件时, 全局管理员、安全管理员和/或安全读者将收到该邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="9d62f-181">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message.</span></span> <span data-ttu-id="9d62f-182">此信息可以让你设置或调整策略, 如[Office 365 ATP 安全链接](atp-safe-links.md)策略或[反垃圾邮件](anti-spam-protection.md)设置。</span><span class="sxs-lookup"><span data-stu-id="9d62f-182">This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="9d62f-183">了解如何使用报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="9d62f-183">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="9d62f-184">请参阅[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="9d62f-184">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="9d62f-185">查看或编辑报告邮件外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="9d62f-185">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="9d62f-186">您可以在 "[服务" & "外接程序" 页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)上查看和编辑报告邮件外接程序的默认设置。</span><span class="sxs-lookup"><span data-stu-id="9d62f-186">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9d62f-187">若要完成此任务, 您必须是 Office 365 全局管理员或 Exchange Online 管理员。</span><span class="sxs-lookup"><span data-stu-id="9d62f-187">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="9d62f-188">转到 Microsoft 365 管理中心中的 "[服务 & 外接程序" 页面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="9d62f-188">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="9d62f-189">![新 Microsoft 365 管理中心中的 "服务和外接程序" 页](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="9d62f-189">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="9d62f-190">查找并选择报告邮件加载项。</span><span class="sxs-lookup"><span data-stu-id="9d62f-190">Find and select the Report Message add-in.</span></span><br/>![查找并选择报告邮件加载项](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="9d62f-192">在 "报告邮件" 屏幕上, 查看并编辑适用于您的组织的设置。</span><span class="sxs-lookup"><span data-stu-id="9d62f-192">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![报告邮件外接程序的设置](media/EditReportMessageAddIn.png)<br/> 

## <a name="related-topics"></a><span data-ttu-id="9d62f-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="9d62f-194">Related topics</span></span>

[<span data-ttu-id="9d62f-195">使用报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="9d62f-195">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="9d62f-196">查看安全&amp;合规性中心中的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="9d62f-196">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="9d62f-197">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="9d62f-197">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="9d62f-198">在安全&amp;合规中心中使用资源管理器</span><span class="sxs-lookup"><span data-stu-id="9d62f-198">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  


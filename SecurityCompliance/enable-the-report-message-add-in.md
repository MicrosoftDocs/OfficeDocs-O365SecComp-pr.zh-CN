---
title: 启用报告消息加载项
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/18/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 了解如何为单个用户或您的整个组织启用 outlook 和 web 上的 outlook 和 outlook 网页版报告消息外接程序。
ms.openlocfilehash: 48bd8937622588bbf5a1e07b9d4341e937c5cf7f
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217382"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="02aaa-103">启用报告消息加载项</span><span class="sxs-lookup"><span data-stu-id="02aaa-103">Enable the Report Message add-in</span></span>

## <a name="overview"></a><span data-ttu-id="02aaa-104">概述</span><span class="sxs-lookup"><span data-stu-id="02aaa-104">Overview</span></span>

<span data-ttu-id="02aaa-p101">outlook 和 web 上的 outlook 的报告消息外接程序使用户能够轻松地向 Microsoft 及其子公司报告 misclassified 电子邮件 (无论是安全还是恶意)。Microsoft 使用这些提交改进电子邮件保护技术的有效性。此外, 如果您的组织使用的是[office 365 高级威胁防护](office-365-atp.md)或[office 365 威胁智能](office-365-ti.md), 报告邮件加载项将为您组织的安全团队提供可用于查看和更新的有用信息。安全策略。</span><span class="sxs-lookup"><span data-stu-id="02aaa-p101">The Report Message add-in for Outlook and Outlook on the web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies. In addition, if your organization is using [Office 365 Advanced Threat Protection](office-365-atp.md) or [Office 365 Threat Intelligence](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="02aaa-p102">例如, 假设有人将大量邮件报告为网络钓鱼。[安全仪表板](security-dashboard.md)和其他报告中的此信息图面。组织的安全团队可以使用此信息指示可能需要更新的反网络钓鱼策略。或者, 如果用户使用报告邮件外接程序报告大量被标记为垃圾邮件的邮件, 则组织的安全团队可能需要调整[反垃圾邮件策略](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="02aaa-p102">For example, suppose that people are reporting a lot of messages as phishing. This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports. Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated. Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="02aaa-112">报告邮件外接程序适用于 Office 365 订阅和以下产品:</span><span class="sxs-lookup"><span data-stu-id="02aaa-112">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="02aaa-113">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="02aaa-113">Outlook on the web</span></span>
 - <span data-ttu-id="02aaa-114">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="02aaa-114">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="02aaa-115">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="02aaa-115">Outlook 2016</span></span>
 - <span data-ttu-id="02aaa-116">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="02aaa-116">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="02aaa-117">Outlook 包含在 Office 365 专业增强版中</span><span class="sxs-lookup"><span data-stu-id="02aaa-117">Outlook included with Office 365 ProPlus</span></span>

> [!NOTE]
> <span data-ttu-id="02aaa-p103">outlook 和 web 上的 outlook 的报告邮件外接程序与[outlook 垃圾邮件筛选器](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)并不完全相同, 但这两者都可用于将电子邮件标记为垃圾邮件、非垃圾邮件或网络钓鱼尝试。outlook 和 web 上的 outlook 相关的报告邮件外接程序会通知 Microsoft misclassified 电子邮件, 而 outlook 垃圾邮件筛选器用于组织用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="02aaa-p103">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/Overview-of-the-Junk-Email-Filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt. The Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span> 
  
<span data-ttu-id="02aaa-120">如果您是单个用户, 则可以[为自己启用报告邮件加载项](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="02aaa-120">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="02aaa-p104">如果您是 Office 365 全局管理员或 exchange Online 管理员, 并且将 exchange 配置为使用 OAuth 身份验证, 则可以[为您的组织启用报告消息外接程序](#get-and-enable-the-report-message-add-in-for-your-organization)。现在, 可以通过[集中部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)使用报告消息加载项。</span><span class="sxs-lookup"><span data-stu-id="02aaa-p104">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization). The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="02aaa-123">获取自己的报告邮件外接程序</span><span class="sxs-lookup"><span data-stu-id="02aaa-123">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="02aaa-124">在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)中, 搜索[报告邮件外接程序](https://appsource.microsoft.com/product/office/wa104381180)。</span><span class="sxs-lookup"><span data-stu-id="02aaa-124">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="02aaa-125">选择 "**立即获取**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-125">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="02aaa-126">![报告消息-立即获取](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-126">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="02aaa-p105">查看使用条款和隐私策略。然后选择 "**继续**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-p105">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="02aaa-129">使用你的工作或学校帐户 (用于商业用途) 或你的 Microsoft 帐户 (供个人使用) 登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="02aaa-129">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="02aaa-130">安装并启用加载项后, 您将看到以下图标:</span><span class="sxs-lookup"><span data-stu-id="02aaa-130">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="02aaa-131">在 Outlook 中, 图标如下所示:</span><span class="sxs-lookup"><span data-stu-id="02aaa-131">In Outlook, the icon looks like this:</span></span> <br/> ![报告邮件外接程序图标 (适用于 Outlook)](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="02aaa-133">在 web 上的 Outlook (以前称为 Outlook web App) 中, 图标如下所示:</span><span class="sxs-lookup"><span data-stu-id="02aaa-133">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span><br/>![Outlook 网页报告邮件加载项图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="02aaa-135">作为下一步, 了解如何[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="02aaa-135">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="02aaa-136">为您的组织获取并启用报告邮件外接程序</span><span class="sxs-lookup"><span data-stu-id="02aaa-136">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02aaa-p106">若要完成此任务, 您必须是 Office 365 全局管理员或 Exchange Online 管理员。此外, 必须将 Exchange 配置为使用 OAuth 身份验证以了解详细信息, 请参阅[exchange 要求 (加载项的集中部署)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements)。</span><span class="sxs-lookup"><span data-stu-id="02aaa-p106">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task. In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span></span> 

1. <span data-ttu-id="02aaa-139">转到 Microsoft 365 管理中心中的 "[服务 & 外接程序" 页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="02aaa-139">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="02aaa-140">![新 Microsoft 365 管理中心中的 "服务和外接程序" 页](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-140">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="02aaa-141">选择 " **+ 部署外接端"**。</span><span class="sxs-lookup"><span data-stu-id="02aaa-141">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="02aaa-142">![选择 "部署加载项"](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-142">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="02aaa-143">在 "**新建外接端**" 屏幕中, 查看信息, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-143">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="02aaa-144">![新加载项详细信息](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-144">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="02aaa-145">选择 **"我想从 Office 应用商店添加外接程序**", 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-145">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="02aaa-146">![我想要添加新的外接程序](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-146">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="02aaa-147">搜索**报告消息**, 并在结果列表中的**报告邮件外接程序**旁边, 选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-147">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span><br/><span data-ttu-id="02aaa-148">![搜索报告消息, 然后选择 "添加"](media/NewAddInScreen3.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-148">![Search for Report Message and then choose Add](media/NewAddInScreen3.png)</span></span><br/>
    
6. <span data-ttu-id="02aaa-149">在 "**报告邮件**" 屏幕上, 查看信息, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-149">On the **Report Message** screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="02aaa-150">![报告消息详细信息](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-150">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="02aaa-151">指定 Outlook 的用户默认设置, 然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-151">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="02aaa-152">![为 Outlook 报告邮件的默认设置](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-152">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="02aaa-153">指定要获取报告邮件加载项的收件人, 然后选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-153">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="02aaa-154">![谁可以获取报告邮件加载项](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-154">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="02aaa-155">建议[设置一个规则, 以获取用户报告的电子](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="02aaa-155">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="02aaa-p107">根据您在设置加载项时选择的内容 (上面的步骤 7-8), 贵组织中的人员将会看到[报告消息外接程序](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。你组织中的人员将看到以下图标:</span><span class="sxs-lookup"><span data-stu-id="02aaa-p107">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available. People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="02aaa-158">在 Outlook 中, 图标如下所示:</span><span class="sxs-lookup"><span data-stu-id="02aaa-158">In Outlook, the icon looks like this:</span></span> <br/> ![报告邮件外接程序图标 (适用于 Outlook)](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="02aaa-160">在 web 上的 Outlook 中, 图标如下所示:</span><span class="sxs-lookup"><span data-stu-id="02aaa-160">In Outlook on the web, the icon looks like this:</span></span><br/>![Outlook 网页报告邮件加载项图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

> [!TIP]
> <span data-ttu-id="02aaa-162">当您通知用户有关报告邮件加载项时, 请包含[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)的链接。</span><span class="sxs-lookup"><span data-stu-id="02aaa-162">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="02aaa-163">设置一个规则, 以获取用户报告的电子邮件的副本</span><span class="sxs-lookup"><span data-stu-id="02aaa-163">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02aaa-164">您必须是 Exchange Online 管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="02aaa-164">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="02aaa-p108">您可以设置一个规则, 以获取由组织中的用户报告的电子邮件的副本。为组织下载并启用报告邮件外接程序后, 可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="02aaa-p108">You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="02aaa-167">在 Exchange 管理中心中, 选择 "**邮件流** \> **规则**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-167">In the Exchange Admin Center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="02aaa-168">选择**+** \> "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-168">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="02aaa-169">在 "**名称**" 框中, 键入一个名称, 如 "提交"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-169">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="02aaa-170">在 "在**以下情况应用此规则**" 列表中, 选择**收件人地址包括 ...**。</span><span class="sxs-lookup"><span data-stu-id="02aaa-170">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="02aaa-171">在 "**指定字词或短语**" 屏幕中`junk@office365.microsoft.com` , `phish@office365.microsoft.com`添加和, 然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="02aaa-171">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="02aaa-172">![指定规则的垃圾邮件和网络钓鱼电子邮件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-172">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="02aaa-173">在 "**执行以下操作 ...** " 列表中, 选择 **"将邮件密件抄送给 ...**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-173">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="02aaa-174">添加全局管理员、安全管理员和/或安全阅读者, 这些读者应收到用户报告给 Microsoft 的每封电子邮件的副本, 然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="02aaa-174">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="02aaa-175">![添加全局或安全管理员以接收每个报告的邮件的副本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-175">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="02aaa-176">选择 "**使用严重性级别审核此规则**", 然后选择 "**中**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-176">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="02aaa-177">在 "**为此规则选择模式**" 下, 选择 "**强制**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-177">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="02aaa-178">![设置一个规则以获取每个报告的邮件的副本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-178">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="02aaa-179">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="02aaa-179">Choose **Save**.</span></span> 
    
<span data-ttu-id="02aaa-p109">在适当的情况下, 当组织中的某人使用报告邮件加载项报告电子邮件时, 全局管理员、安全管理员和/或安全读者将收到该邮件的副本。此信息可以让你设置或调整策略, 如[Office 365 ATP 安全链接](atp-safe-links.md)策略或[反垃圾邮件](anti-spam-protection.md)设置。</span><span class="sxs-lookup"><span data-stu-id="02aaa-p109">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="02aaa-182">了解如何使用报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="02aaa-182">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="02aaa-183">请参阅[使用报告邮件加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="02aaa-183">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="02aaa-184">查看或编辑报告邮件外接程序的设置</span><span class="sxs-lookup"><span data-stu-id="02aaa-184">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="02aaa-185">您可以查看和编辑 "[服务 & 外接程序" 页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)上的 "报告邮件" 外接程序的默认设置。</span><span class="sxs-lookup"><span data-stu-id="02aaa-185">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="02aaa-186">若要完成此任务, 您必须是 Office 365 全局管理员或 Exchange Online 管理员。</span><span class="sxs-lookup"><span data-stu-id="02aaa-186">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="02aaa-187">转到 Microsoft 365 管理中心中的 "[服务 & 外接程序" 页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)。</span><span class="sxs-lookup"><span data-stu-id="02aaa-187">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span><br/><span data-ttu-id="02aaa-188">![新 Microsoft 365 管理中心中的 "服务和外接程序" 页](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="02aaa-188">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="02aaa-189">查找并选择报告邮件加载项。</span><span class="sxs-lookup"><span data-stu-id="02aaa-189">Find and select the Report Message add-in.</span></span><br/>![查找并选择报告邮件加载项](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="02aaa-191">在 "报告邮件" 屏幕上, 查看并编辑适用于您的组织的设置。</span><span class="sxs-lookup"><span data-stu-id="02aaa-191">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![报告邮件外接程序的设置](media/EditReportMessageAddIn.png)<br/> 
  
## <a name="related-topics"></a><span data-ttu-id="02aaa-193">相关主题</span><span class="sxs-lookup"><span data-stu-id="02aaa-193">Related topics</span></span>

[<span data-ttu-id="02aaa-194">使用报告邮件加载项</span><span class="sxs-lookup"><span data-stu-id="02aaa-194">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="02aaa-195">查看安全&amp;合规性中心中的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="02aaa-195">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="02aaa-196">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="02aaa-196">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="02aaa-197">在安全&amp;合规中心中使用资源管理器</span><span class="sxs-lookup"><span data-stu-id="02aaa-197">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  


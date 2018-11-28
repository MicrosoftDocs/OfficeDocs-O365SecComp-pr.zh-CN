---
title: 启用报告消息加载项
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/19/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: 了解如何启用报告消息加载项的 Outlook 和 Outlook web，为各个用户或您的整个组织上。
ms.openlocfilehash: f35899d3f0be9ee07cb6dae5c5fec40395948340
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706366"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="e8cf4-103">启用报告消息加载项</span><span class="sxs-lookup"><span data-stu-id="e8cf4-103">Enable the Report Message add-in</span></span>

## <a name="overview"></a><span data-ttu-id="e8cf4-104">概述</span><span class="sxs-lookup"><span data-stu-id="e8cf4-104">Overview</span></span>

<span data-ttu-id="e8cf4-p101">报告消息外接程序 Outlook 和在 Web 上的 Outlook 中，使人们能够轻松地分类的电子邮件安全还是恶意，向 Microsoft 和报告或其关联公司进行分析。Microsoft 使用这些提交来提高效率的电子邮件保护技术。此外，如果您的组织使用[Office 365 高级威胁保护](office-365-atp.md)或[Office 365 威胁智能](office-365-ti.md)，报告消息外接程序提供了有用的信息，它们可用于查看和更新组织的安全工作组安全策略。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-p101">The Report Message add-in for Outlook and Outlook on the Web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies. In addition, if your organization is using [Office 365 Advanced Threat Protection](office-365-atp.md) or [Office 365 Threat Intelligence](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="e8cf4-p102">例如，假设人员包括报告很多为网络钓鱼邮件。在[安全仪表板](security-dashboard.md)和其他报表中此信息曲面。贵组织的安全工作组可以使用此信息，以指示防钓鱼策略可能需要更新。或者，如果人员报告大量使用报告消息加载项已标记为垃圾邮件为非垃圾邮件的邮件，贵组织的安全工作组可能需要调整[反垃圾邮件策略](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-p102">For example, suppose that people are reporting a lot of messages as phishing. This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports. Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated. Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="e8cf4-112">报告消息外接程序适用于 Office 365 订阅和以下产品：</span><span class="sxs-lookup"><span data-stu-id="e8cf4-112">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="e8cf4-113">在 Web 上的 outlook</span><span class="sxs-lookup"><span data-stu-id="e8cf4-113">Outlook on the Web</span></span>
 - <span data-ttu-id="e8cf4-114">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="e8cf4-114">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="e8cf4-115">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e8cf4-115">Outlook 2016</span></span>
 - <span data-ttu-id="e8cf4-116">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="e8cf4-116">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="e8cf4-117">包含 Office 365 ProPlus 的 outlook</span><span class="sxs-lookup"><span data-stu-id="e8cf4-117">Outlook included with Office 365 ProPlus</span></span>
  
<span data-ttu-id="e8cf4-118">如果您是单个用户，您还可以[启用报告消息外接程序自己](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="e8cf4-p103">如果您是 Office 365 全局管理员或 Exchange Online 管理员，并且 Exchange 配置为使用 OAuth 身份验证，则可以[启用报告消息外接程序为您的组织](#get-and-enable-the-report-message-add-in-for-your-organization)。报表消息加载项是现在可通过[集中部署](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-p103">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization). The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="e8cf4-121">获取外接程序为自己的报告邮件</span><span class="sxs-lookup"><span data-stu-id="e8cf4-121">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="e8cf4-122">在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)，搜索的[邮件报告加载项](https://appsource.microsoft.com/product/office/wa104381180)。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-122">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="e8cf4-123">选择**获取 IT 现在**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-123">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="e8cf4-124">![报告消息-立即获取](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-124">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="e8cf4-p104">查看相应条款的使用和隐私策略。然后选择**继续**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-p104">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="e8cf4-127">登录到 Office 365 电子邮件使用您的工作或学校 （供业务使用） 的帐户或您的 Microsoft 帐户 （供个人使用）。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-127">Sign in to your Office 365 email using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    
<span data-ttu-id="e8cf4-128">外接程序是安装并启用后，您将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="e8cf4-128">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="e8cf4-129">在 Outlook 中图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8cf4-129">In Outlook the icon looks like this:</span></span> <br/> ![Outlook 报表消息外接程序图标](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="e8cf4-131">在 Outlook Web App 中图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8cf4-131">In Outlook Web App the icon looks like this:</span></span><br/>![Outlook Web 报告消息外接程序图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

<span data-ttu-id="e8cf4-133">下一步，以了解如何[使用报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-133">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="e8cf4-134">获取和报告消息外接程序为组织启用</span><span class="sxs-lookup"><span data-stu-id="e8cf4-134">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8cf4-p105">您必须是 Office 365 全局管理员或 Exchange Online 管理员才能完成此任务。此外，Exchange 必须配置为使用 OAuth 身份验证以了解详细信息，请参阅[Exchange 要求 （集中部署的加载项）](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements)。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-p105">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task. In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins&view=o365-worldwide#exchange-requirements).</span></span> 

1. <span data-ttu-id="e8cf4-137">转到[服务和外接程序页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)在新的 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-137">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the new Microsoft 365 admin center.</span></span><br/><span data-ttu-id="e8cf4-138">![服务和加载项在新的 Microsoft 365 管理中心页](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-138">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/> 
    
2. <span data-ttu-id="e8cf4-139">选择 **+ 部署外接程序**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-139">Choose **+ Deploy Add-in**.</span></span><br/><span data-ttu-id="e8cf4-140">![选择外接程序部署](media/ServicesAddIns-ChooseDeployAddIn.png)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-140">![Choose Deploy Add-In](media/ServicesAddIns-ChooseDeployAddIn.png)</span></span><br/> 
    
3. <span data-ttu-id="e8cf4-141">在新加载项屏幕中，查看信息，，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-141">In the New Add-In screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="e8cf4-142">![新的外接程序详细信息](media/NewAddInScreen1.png)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-142">![New Add-In details](media/NewAddInScreen1.png)</span></span><br/>
    
4. <span data-ttu-id="e8cf4-143">选择**我希望外接程序从 Office 商店添加**，，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-143">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span><br/><span data-ttu-id="e8cf4-144">![我想要添加新加载项](media/NewAddInScreen2.png)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-144">![I want to add an new Add-In](media/NewAddInScreen2.png)</span></span><br/> 
    
5. <span data-ttu-id="e8cf4-145">搜索报告消息，并在结果，旁边报告消息加载项列表中，选择添加。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-145">Search for Report Message, and in the list of results, next to the Report Message Add-In, choose Add.</span></span><br/>![搜索报告消息，然后选择添加](media/NewAddInScreen3.png)<br/>
    
6. <span data-ttu-id="e8cf4-147">在报告消息屏幕上，查看信息，，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-147">On the Report Message screen, review the information, and then choose **Next**.</span></span><br/><span data-ttu-id="e8cf4-148">![报告邮件详细信息](media/ReportMessageAdd-InNewScreen4.png)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-148">![Report Message details](media/ReportMessageAdd-InNewScreen4.png)</span></span><br/>

7. <span data-ttu-id="e8cf4-149">指定 Outlook 用户默认设置，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-149">Specify the user default settings for Outlook, and  then choose **Next**.</span></span><br/><span data-ttu-id="e8cf4-150">![报告用于 Outlook 的邮件默认设置](media/ReportMessageOptionsScreen5.png)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-150">![Report Message default settings for Outlook](media/ReportMessageOptionsScreen5.png)</span></span><br/>

8. <span data-ttu-id="e8cf4-151">指定谁报告消息外接程序，，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-151">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span> <br/><span data-ttu-id="e8cf4-152">![谁将报告消息外接程序](media/ReportMessageOptionsScreen6.png)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-152">![Who gets the Report Message add-in](media/ReportMessageOptionsScreen6.png)</span></span><br/>

> [!TIP]
> <span data-ttu-id="e8cf4-153">我们建议[设置规则来获取一份报告的用户的电子邮件](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-153">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)</span></span>

<span data-ttu-id="e8cf4-p106">根据您选择使用向导，在组织中的人员将具有[报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)可用。您的组织中的人员将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="e8cf4-p106">Depending on what you selected using the wizard, people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available. People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="e8cf4-156">在 Outlook 中图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8cf4-156">In Outlook the icon looks like this:</span></span> <br/> ![Outlook 报表消息外接程序图标](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="e8cf4-158">在 Outlook Web App 中图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8cf4-158">In Outlook Web App the icon looks like this:</span></span><br/>![Outlook Web 报告消息外接程序图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="e8cf4-160">设置规则来获取一份报告的用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="e8cf4-160">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8cf4-161">您必须是 Exchange Online 管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-161">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="e8cf4-p107">您可以设置规则，若要获取的电子邮件组织中的用户报告的副本。在下载并为组织启用报告消息外接程序后执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-p107">You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="e8cf4-164">在 Exchange 管理中心中，选择**邮件流** \> **规则**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-164">In the Exchange Admin Center, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="e8cf4-165">选择**+** \> **创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-165">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="e8cf4-166">在**名称**框中，键入一个名称，例如提交。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-166">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="e8cf4-167">在**以下情况应用此规则**列表中，选择**在收件人地址包括...**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-167">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="e8cf4-168">在**指定词语或短语**屏幕中，添加`junk@office365.microsoft.com`和`phish@office365.microsoft.com`，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-168">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span><br/><span data-ttu-id="e8cf4-169">![指定规则的垃圾邮件和网络钓鱼电子邮件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-169">![Specify the junk and phish email addresses for the rule](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)</span></span><br/>
  
6. <span data-ttu-id="e8cf4-170">在 **...请执行以下**列表中，选择**密件抄送邮件到...**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-170">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="e8cf4-171">添加的全局管理员、 安全管理员和/或安全读者用户应收到人员报告给 Microsoft，每个电子邮件的副本，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-171">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span><br/><span data-ttu-id="e8cf4-172">![添加全局或安全管理员以接收报告的每封邮件的副本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-172">![Add a global or security administrator to receive a copy of each reported message](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)</span></span><br/>
  
8. <span data-ttu-id="e8cf4-173">选择**审核严重性级别与此规则**，然后选择**中等**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-173">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="e8cf4-174">在**选择此规则的模式**，下选择**强制**。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-174">Under **Choose a mode for this rule**, choose **Enforce**.</span></span><br/><span data-ttu-id="e8cf4-175">![设置规则来获取每个报告的邮件的副本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-175">![Set up a rule to get a copy of each reported message](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)</span></span><br/>
  
10. <span data-ttu-id="e8cf4-176">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-176">Choose **Save**.</span></span> 
    
<span data-ttu-id="e8cf4-p108">与就地此规则，当您的组织中的某人报告电子邮件的邮件报告加载项，使用您的全局管理员、 安全管理员和/或安全读者将收到该邮件的副本。这些信息使您可以设置或调整策略，如[Office 365 ATP 安全链接](atp-safe-links.md)策略。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-p108">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies.</span></span> 

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="e8cf4-179">查看或编辑报告消息加载项的设置</span><span class="sxs-lookup"><span data-stu-id="e8cf4-179">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="e8cf4-180">您可以查看和编辑的报表消息加载项[服务和加载项的页面](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)中的默认设置。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-180">You can review and edit the default settings for the Report Message Add-In in the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e8cf4-181">您必须是 Office 365 全局管理员或 Exchange Online 管理员才能完成此任务。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-181">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="e8cf4-182">转到[服务和外接程序页](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)在新的 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-182">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the new Microsoft 365 admin center.</span></span><br/><span data-ttu-id="e8cf4-183">![服务和加载项在新的 Microsoft 365 管理中心页](media/ServicesAddInsPageNewM365AdminCenter.png)</span><span class="sxs-lookup"><span data-stu-id="e8cf4-183">![Services and Add-Ins page in the new Microsoft 365 Admin Center](media/ServicesAddInsPageNewM365AdminCenter.png)</span></span><br/>

2. <span data-ttu-id="e8cf4-184">查找并选择报表消息加载项。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-184">Find and select the Report Message Add-In.</span></span><br/>![查找并选择报告消息外接程序](media/FindReportMessageAddIn.png)<br/> 
    
3. <span data-ttu-id="e8cf4-186">在报告消息屏幕上，查看和编辑根据您的组织的设置。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-186">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span><br/>![设置报告消息加载项](media/EditReportMessageAddIn.png)<br/> 

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="e8cf4-188">了解如何使用报告消息外接程序</span><span class="sxs-lookup"><span data-stu-id="e8cf4-188">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="e8cf4-189">请参阅[使用报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="e8cf4-189">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e8cf4-190">相关主题</span><span class="sxs-lookup"><span data-stu-id="e8cf4-190">Related topics</span></span>

[<span data-ttu-id="e8cf4-191">使用报告消息外接程序</span><span class="sxs-lookup"><span data-stu-id="e8cf4-191">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="e8cf4-192">查看安全中的电子邮件安全报告&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="e8cf4-192">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="e8cf4-193">Office 365 高级威胁保护的视图报告</span><span class="sxs-lookup"><span data-stu-id="e8cf4-193">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="e8cf4-194">在安全中使用资源管理器&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="e8cf4-194">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  


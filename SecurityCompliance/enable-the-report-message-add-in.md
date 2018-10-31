---
title: 启用报告消息加载项
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/18/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: 了解如何启用报告消息加载项的 Outlook 和 Outlook web，为各个用户或您的整个组织上。
ms.openlocfilehash: 8c9853c78a42d6eecd0989475ef8f0a44345f812
ms.sourcegitcommit: ceb70ea863d8b97afea077a04fc7ec612b870695
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25857260"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="5c9aa-103">启用报告消息加载项</span><span class="sxs-lookup"><span data-stu-id="5c9aa-103">Enable the Report Message add-in</span></span>

## <a name="overview"></a><span data-ttu-id="5c9aa-104">概述</span><span class="sxs-lookup"><span data-stu-id="5c9aa-104">Overview</span></span>

<span data-ttu-id="5c9aa-p101">报告消息外接程序 Outlook 和在 Web 上的 Outlook 中，使人们能够轻松地分类的电子邮件安全还是恶意，向 Microsoft 和报告或其关联公司进行分析。Microsoft 使用这些提交来提高效率的电子邮件保护技术。此外，如果您的组织使用[Office 365 高级威胁保护](office-365-atp.md)或[Office 365 威胁智能](office-365-ti.md)，报告消息外接程序提供了有用的信息，它们可用于查看和更新组织的安全工作组安全策略。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-p101">The Report Message add-in for Outlook and Outlook on the Web enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis. Microsoft uses these submissions to improve the effectiveness of email protection technologies. In addition, if your organization is using [Office 365 Advanced Threat Protection](office-365-atp.md) or [Office 365 Threat Intelligence](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span> 

<span data-ttu-id="5c9aa-p102">例如，假设人员包括报告很多为网络钓鱼邮件。在[安全仪表板](security-dashboard.md)和其他报表中此信息曲面。贵组织的安全工作组可以使用此信息，以指示防钓鱼策略可能需要更新。或者，如果人员报告大量使用报告消息加载项已标记为垃圾邮件为非垃圾邮件的邮件，贵组织的安全工作组可能需要调整[反垃圾邮件策略](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-p102">For example, suppose that people are reporting a lot of messages as phishing. This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports. Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated. Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-the-anti-spam-policies.md).</span></span> 

<span data-ttu-id="5c9aa-112">报告消息外接程序适用于 Office 365 订阅和以下产品：</span><span class="sxs-lookup"><span data-stu-id="5c9aa-112">The Report Message add-in works with your Office 365 subscription and the following products:</span></span>
 - <span data-ttu-id="5c9aa-113">在 Web 上的 outlook</span><span class="sxs-lookup"><span data-stu-id="5c9aa-113">Outlook on the Web</span></span>
 - <span data-ttu-id="5c9aa-114">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="5c9aa-114">Outlook 2013 SP1</span></span>
 - <span data-ttu-id="5c9aa-115">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5c9aa-115">Outlook 2016</span></span>
 - <span data-ttu-id="5c9aa-116">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="5c9aa-116">Outlook 2016 for Mac</span></span>
 - <span data-ttu-id="5c9aa-117">包含 Office 365 ProPlus 的 outlook</span><span class="sxs-lookup"><span data-stu-id="5c9aa-117">Outlook included with Office 365 ProPlus</span></span>
  
<span data-ttu-id="5c9aa-118">如果您是单个用户，您还可以[启用报告消息外接程序自己](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span> 
  
<span data-ttu-id="5c9aa-119">如果您的 Exchange Online 管理员，您还可以[启用报告消息外接程序为您的组织](#get-and-enable-the-report-message-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-119">If you're an Exchange Online administrator, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span>
    
## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="5c9aa-120">获取外接程序为自己的报告邮件</span><span class="sxs-lookup"><span data-stu-id="5c9aa-120">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="5c9aa-121">在[Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)，搜索的[邮件报告加载项](https://appsource.microsoft.com/product/office/wa104381180)。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-121">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>
    
2. <span data-ttu-id="5c9aa-122">选择**获取 IT 现在**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-122">Choose **GET IT NOW**.</span></span><br/><span data-ttu-id="5c9aa-123">![报告消息-立即获取](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="5c9aa-123">![Report Message - Get It Now](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
3. <span data-ttu-id="5c9aa-p103">查看相应条款的使用和隐私策略。然后选择**继续**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-p103">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
4. <span data-ttu-id="5c9aa-126">登录到 Office 365 电子邮件使用您的工作或学校 （供业务使用） 的帐户或您的 Microsoft 帐户 （供个人使用）。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-126">Sign in to your Office 365 email using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>
    

<span data-ttu-id="5c9aa-127">外接程序是安装并启用后，您将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="5c9aa-127">After the add-in is installed and enabled, you'll see the following icons:</span></span> 

- <span data-ttu-id="5c9aa-128">在 Outlook 中图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="5c9aa-128">In Outlook the icon looks like this:</span></span> <br/> ![Outlook 报表消息外接程序图标](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="5c9aa-130">在 Outlook Web App 中图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="5c9aa-130">In Outlook Web App the icon looks like this:</span></span><br/>![Outlook Web 报告消息外接程序图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

<span data-ttu-id="5c9aa-132">下一步，以了解如何[使用报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-132">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="5c9aa-133">获取和报告消息外接程序为组织启用</span><span class="sxs-lookup"><span data-stu-id="5c9aa-133">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c9aa-134">您必须是 Office 365 全局管理员或 Exchange Online 管理员才能完成此任务。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-134">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>

1. <span data-ttu-id="5c9aa-135">转到[https://portal.office.com](https://portal.office.com)和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-135">Go to [https://portal.office.com](https://portal.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="5c9aa-136">选择**管理**以转到管理中心。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-136">Choose **Admin** to go to the Admin center.</span></span> 
    
3. <span data-ttu-id="5c9aa-137">选择**管理中心** \> **Exchange**转到 Exchange 管理员中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-137">Choose **Admin centers** \> **Exchange** to go to the Exchange admin center (EAC).</span></span> 
    
4. <span data-ttu-id="5c9aa-138">选择**组织** \> **外接程序**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-138">Choose **organization** \> **add-ins**.</span></span> 
    
5. <span data-ttu-id="5c9aa-139">选择**+**  > **从 Office 商店添加**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-139">Choose **+** > **Add from the Office Store**.</span></span><br/><span data-ttu-id="5c9aa-140">![选择从 Office 商店添加](media/EAC-Org-AddFromOfficeStore.png)</span><span class="sxs-lookup"><span data-stu-id="5c9aa-140">![Choose Add from the Office Store](media/EAC-Org-AddFromOfficeStore.png)</span></span><br/><span data-ttu-id="5c9aa-141">这将在 web 浏览器中打开 Office 应用商店。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-141">This opens the Office Store in your web browser.</span></span>
    
6. <span data-ttu-id="5c9aa-142">搜索报告消息。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-142">Search for Report Message.</span></span><br/>![搜索报告邮件](media/ReportMessageSearchOfficeStore.png)<br/>
    
7. <span data-ttu-id="5c9aa-144">在**应用程序**列表中，选择**报告消息**，然后选择**获取 IT**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-144">In the **Apps** list, select **Report Message**, and then choose **GET IT NOW**.</span></span><br/><span data-ttu-id="5c9aa-145">![选择 GET 现在 IT](media/ReportMessageGETITNOW.png)</span><span class="sxs-lookup"><span data-stu-id="5c9aa-145">![Choose GET IT NOW](media/ReportMessageGETITNOW.png)</span></span><br/> 
    
8. <span data-ttu-id="5c9aa-p104">查看相应条款的使用和隐私策略。然后选择**继续**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-p104">Review the terms of use and privacy policy. Then choose **Continue**.</span></span> 
    
    ![单击继续以接受条款和隐私策略](media/ReportMessageTermsAndConditions.png)
  
9. <span data-ttu-id="5c9aa-p105">将打开一个向导可帮助您配置报告消息加载项查看信息，并选择**下一步**继续。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-p105">A wizard opens to help you configure the Report Message add-in. Review the information, and choose **Next** to continue.</span></span><br/><span data-ttu-id="5c9aa-151">![报告 Office 365 消息外接程序向导](media/ReportMessageAdminInstallUI.png)</span><span class="sxs-lookup"><span data-stu-id="5c9aa-151">![Report Message add-in wizard for Office 365](media/ReportMessageAdminInstallUI.png)</span></span><br/> 

10. <span data-ttu-id="5c9aa-152">指定您希望用户能够为邮件报告加载项的默认设置。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-152">Specify the default setting you want users to have for the Report Message add-in.</span></span><br/>![指定邮件报告加载项的默认的设置](media/ReportMessageUserOptionsAdminsSet.png)<br/>
    
11. <span data-ttu-id="5c9aa-154">指定谁报告消息外接程序。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-154">Specify who gets the Report Message add-in.</span></span> <br/>![指定谁报告消息外接程序](media/ReportMessageChooseWhoGetsItAdminSettings.png)<br/>

12. <span data-ttu-id="5c9aa-156">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-156">Choose **Save**.</span></span> <br/>
> [!TIP]
> <span data-ttu-id="5c9aa-157">我们建议[设置规则来获取一份报告的用户的电子邮件](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)</span><span class="sxs-lookup"><span data-stu-id="5c9aa-157">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)</span></span>

<span data-ttu-id="5c9aa-p106">根据您选择使用向导，在组织中的人员将具有[报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)可用。您的组织中的人员将看到以下图标：</span><span class="sxs-lookup"><span data-stu-id="5c9aa-p106">Depending on what you selected using the wizard, people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available. People in your organization will see the following icons:</span></span> 

- <span data-ttu-id="5c9aa-160">在 Outlook 中图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="5c9aa-160">In Outlook the icon looks like this:</span></span> <br/> ![Outlook 报表消息外接程序图标](media/OutlookReportMessageIcon.png)<br/>
- <span data-ttu-id="5c9aa-162">在 Outlook Web App 中图标如下所示：</span><span class="sxs-lookup"><span data-stu-id="5c9aa-162">In Outlook Web App the icon looks like this:</span></span><br/>![Outlook Web 报告消息外接程序图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="5c9aa-164">设置规则来获取一份报告的用户的电子邮件</span><span class="sxs-lookup"><span data-stu-id="5c9aa-164">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c9aa-165">您必须是 Exchange Online 管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-165">You must be an Exchange Online Administrator to perform this task.</span></span>
  
<span data-ttu-id="5c9aa-p107">您可以设置规则，若要获取的电子邮件组织中的用户报告的副本。在下载并为组织启用报告消息外接程序后执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-p107">You can set up a rule to get a copy of email messages reported by users in your organization. You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>
  
1. <span data-ttu-id="5c9aa-168">在 EAC 中，选择**邮件流** \> **规则**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-168">In the EAC, choose **mail flow** \> **rules**.</span></span> 
    
2. <span data-ttu-id="5c9aa-169">选择**+** \> **创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-169">Choose **+** \> **Create a new rule**.</span></span> 
    
3. <span data-ttu-id="5c9aa-170">在**名称**框中，键入一个名称，例如提交。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-170">In the **Name** box, type a name, such as Submissions.</span></span>
    
4. <span data-ttu-id="5c9aa-171">在**以下情况应用此规则**列表中，选择**在收件人地址包括...**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-171">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span> 
    
5. <span data-ttu-id="5c9aa-172">在**指定词语或短语**屏幕中，添加 junk@office365.microsoft.com 和 phish@office365.microsoft.com，，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-172">In the **specify words or phrases** screen, add junk@office365.microsoft.com and phish@office365.microsoft.com, and then choose **OK**.</span></span> 
    
    ![指定规则的垃圾邮件和网络钓鱼电子邮件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)
  
6. <span data-ttu-id="5c9aa-174">在 **...请执行以下**列表中，选择**密件抄送邮件到...**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-174">In the **Do the following...** list, choose **Bcc the message to...**.</span></span> 
    
7. <span data-ttu-id="5c9aa-175">添加的全局管理员、 安全管理员和/或安全读者用户应收到人员报告给 Microsoft，每个电子邮件的副本，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-175">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span> 
    
    ![添加全局或安全管理员以接收报告的每封邮件的副本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)
  
8. <span data-ttu-id="5c9aa-177">选择**审核严重性级别与此规则**，然后选择**中等**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-177">Select **Audit this rule with severity level**, and choose **Medium**.</span></span> 
    
9. <span data-ttu-id="5c9aa-178">在**选择此规则的模式**，下选择**强制**。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-178">Under **Choose a mode for this rule**, choose **Enforce**.</span></span> 
    
    ![设置规则来获取每个报告的邮件的副本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)
  
10. <span data-ttu-id="5c9aa-180">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-180">Choose **Save**.</span></span> 
    
<span data-ttu-id="5c9aa-p108">与就地此规则，当您的组织中的某人报告电子邮件的邮件报告加载项，使用您的全局管理员、 安全管理员和/或安全读者将收到该邮件的副本。这些信息使您可以设置或调整策略，如[Office 365 ATP 安全链接](atp-safe-links.md)策略。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-p108">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message. This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies.</span></span> 

## <a name="review-or-edit-the-default-settings-for-the-report-message-add-in"></a><span data-ttu-id="5c9aa-183">查看或编辑报告消息加载项的默认设置</span><span class="sxs-lookup"><span data-stu-id="5c9aa-183">Review or edit the default settings for the Report Message add-in</span></span>

<span data-ttu-id="5c9aa-184">您可以查看和编辑报告消息外接程序使用管理中心的默认设置。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-184">You can review and edit the default settings for the Report Message add-in using the Admin Center.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5c9aa-185">您必须是 Office 365 全局管理员或 Exchange Online 管理员才能完成此任务。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-185">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>
    
1. <span data-ttu-id="5c9aa-p109">如果已为您的组织只安装报告消息外接程序，您已将在服务和外接程序页。否则为请转[此处](https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns)和 Office 365 中使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-p109">If you've just installed the Report Message add-in for your organization, you'll already be on the Services & add-ins page. Otherwise, go [here](https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns) and sign in using your work or school account for Office 365.</span></span>

2. <span data-ttu-id="5c9aa-188">搜索**报告消息**，然后选择它。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-188">Search for **Report Message**, and then select it.</span></span><br/><span data-ttu-id="5c9aa-189">![服务和 Office 365 的加载项](media/ReportMessage-o365servicesaddins.png)</span><span class="sxs-lookup"><span data-stu-id="5c9aa-189">![Services and add-ins for Office 365](media/ReportMessage-o365servicesaddins.png)</span></span><br/> 
    
3. <span data-ttu-id="5c9aa-190">将打开窗格显示在部署过程中选择要报告消息加载项的设置。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-190">A pane opens that displays the settings that were selected for the Report Message add-in during deployment.</span></span><br/>![设置报告消息加载项](media/ReportMessage-reviewaddinsettings.png)<br/> 

4. <span data-ttu-id="5c9aa-192">查看，如果需要为报告消息外接程序，编辑设置，然后保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-192">Review and if needed, edit settings for the Report Message add-in, and then save your changes.</span></span>
    
## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="5c9aa-193">了解如何使用报告消息外接程序</span><span class="sxs-lookup"><span data-stu-id="5c9aa-193">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="5c9aa-194">请参阅[使用报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="5c9aa-194">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5c9aa-195">相关主题</span><span class="sxs-lookup"><span data-stu-id="5c9aa-195">Related topics</span></span>

[<span data-ttu-id="5c9aa-196">使用报告消息外接程序</span><span class="sxs-lookup"><span data-stu-id="5c9aa-196">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[<span data-ttu-id="5c9aa-197">查看安全中的电子邮件安全报告&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="5c9aa-197">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="5c9aa-198">Office 365 高级威胁保护的视图报告</span><span class="sxs-lookup"><span data-stu-id="5c9aa-198">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="5c9aa-199">在安全中使用资源管理器&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="5c9aa-199">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)
  


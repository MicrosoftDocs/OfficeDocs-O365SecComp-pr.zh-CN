---
title: 发送电子邮件通知并显示 DLP 策略的策略提示
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: '策略提示是当有人使用与 DLP 策略冲突的内容时显示的通知或警告。 您可以使用电子邮件通知和策略提示来提高知名度并帮助人们了解组织的策略。 您还可以为用户提供替代策略的选项, 以便它们不会被阻止, 如果他们具有有效的业务需求, 或者如果策略检测到误报也是如此。 '
ms.openlocfilehash: 487d3704b471b10ec876b0df3022d33d13583763
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077358"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a><span data-ttu-id="96ce6-105">发送电子邮件通知并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="96ce6-105">Send email notifications and show policy tips for DLP policies</span></span>

<span data-ttu-id="96ce6-106">数据丢失防护 (DLP) 策略可用于跨 Office 365 识别、监视和保护敏感信息。</span><span class="sxs-lookup"><span data-stu-id="96ce6-106">You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365.</span></span> <span data-ttu-id="96ce6-107">您希望组织中使用这些敏感信息的人员保持与您的 DLP 策略兼容, 但不希望在不必要的情况下阻止他们完成其工作。</span><span class="sxs-lookup"><span data-stu-id="96ce6-107">You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done.</span></span> <span data-ttu-id="96ce6-108">这是电子邮件通知和策略提示可以提供帮助的情况。</span><span class="sxs-lookup"><span data-stu-id="96ce6-108">This is where email notifications and policy tips can help.</span></span>
  
![消息栏在 Excel 2016 中显示策略提示](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="96ce6-110">策略提示是当有人使用与 DLP 策略冲突的内容 (例如, 包含个人身份信息 (PII) 的 OneDrive for Business 网站上的 Excel 工作簿等内容) 时显示的通知或警告。与外部用户共享。</span><span class="sxs-lookup"><span data-stu-id="96ce6-110">A policy tip is a notification or warning that appears when someone is working with content that conflicts with a DLP policy—for example, content like an Excel workbook on a OneDrive for Business site that contains personally identifiable information (PII) and is shared with an external user.</span></span>
  
<span data-ttu-id="96ce6-111">您可以使用电子邮件通知和策略提示来提高知名度并帮助人们了解组织的策略。</span><span class="sxs-lookup"><span data-stu-id="96ce6-111">You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies.</span></span> <span data-ttu-id="96ce6-112">您还可以为用户提供替代策略的选项, 以便它们不会被阻止, 如果他们具有有效的业务需求, 或者如果策略检测到误报也是如此。</span><span class="sxs-lookup"><span data-stu-id="96ce6-112">You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.</span></span>
  
<span data-ttu-id="96ce6-113">在 Office 365 安全&amp;合规中心中, 当您创建 DLP 策略时, 您可以将用户通知配置为:</span><span class="sxs-lookup"><span data-stu-id="96ce6-113">In the Office 365 Security &amp; Compliance Center, when you create a DLP policy, you can configure the user notifications to:</span></span>
  
- <span data-ttu-id="96ce6-114">向你选择的可描述问题的人员发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="96ce6-114">Send an email notification to the people you choose that describes the issue.</span></span>
    
- <span data-ttu-id="96ce6-115">显示与 DLP 策略冲突的内容的策略提示:</span><span class="sxs-lookup"><span data-stu-id="96ce6-115">Display a policy tip for content that conflicts with the DLP policy:</span></span>
    
  - <span data-ttu-id="96ce6-116">对于 web 上的 Outlook 和 Outlook 2013 及更高版本中的电子邮件, 策略提示将显示在撰写邮件的收件人上方的邮件的顶部。</span><span class="sxs-lookup"><span data-stu-id="96ce6-116">For email in Outlook on the web and Outlook 2013 and later, the policy tip appears at the top of a message above the recipients while the message is being composed.</span></span>
    
  - <span data-ttu-id="96ce6-117">对于 OneDrive for business 帐户或 SharePoint Online 网站中的文档, 策略提示由显示在项目上的警告图标指示。</span><span class="sxs-lookup"><span data-stu-id="96ce6-117">For documents in a OneDrive for Business account or SharePoint Online site, the policy tip is indicated by a warning icon that appears on the item.</span></span> <span data-ttu-id="96ce6-118">若要查看详细信息, 可以选择一个项目, 然后在\*\*\*\*![页面的右上角](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png)选择 "信息信息窗格" 图标以打开 "详细信息" 窗格。</span><span class="sxs-lookup"><span data-stu-id="96ce6-118">To view more information, you can select an item and then choose **Information**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane.</span></span> 
    
  - <span data-ttu-id="96ce6-119">对于存储在 DLP 策略中包含的 OneDrive for business 网站或 SharePoint Online 网站上的 Excel 2016、PowerPoint 2016 和 Word 2016 文档, 策略提示将显示在消息栏和 Backstage 视图 ("**文件**" 菜单\> **信息**)。</span><span class="sxs-lookup"><span data-stu-id="96ce6-119">For Excel 2016, PowerPoint 2016, and Word 2016 documents that are stored on a OneDrive for Business site or SharePoint Online site that's included in the DLP policy, the policy tip appears on the Message Bar and the Backstage view ( **File** menu \> **Info**).</span></span>
    
## <a name="add-user-notifications-to-a-dlp-policy"></a><span data-ttu-id="96ce6-120">向 DLP 策略添加用户通知</span><span class="sxs-lookup"><span data-stu-id="96ce6-120">Add user notifications to a DLP policy</span></span>

<span data-ttu-id="96ce6-121">创建 DLP 策略时, 电子邮件通知和策略提示都是 "**用户通知**" 部分的一部分。</span><span class="sxs-lookup"><span data-stu-id="96ce6-121">When you create a DLP policy, both email notifications and policy tips are part of the **User notifications** section.</span></span> 
  
1. <span data-ttu-id="96ce6-122">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="96ce6-122">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="96ce6-123">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="96ce6-123">Sign in to Office 365 using your work or school account.</span></span> <span data-ttu-id="96ce6-124">现在你已处于 Office 365 安全&amp;合规中心。</span><span class="sxs-lookup"><span data-stu-id="96ce6-124">You're now in the Office 365 Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="96ce6-125">在安全&amp;合规\>中心左侧导航\> **数据丢失防护** \> **策略** \>中,**创建一个策略**。</span><span class="sxs-lookup"><span data-stu-id="96ce6-125">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    !["创建策略" 按钮](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="96ce6-127">选择保护您\> **接下来**需要的敏感信息类型的 DLP 策略模板。</span><span class="sxs-lookup"><span data-stu-id="96ce6-127">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="96ce6-128">若要从空模板开始, 请选择 "**自** \> **定义策略** \> "**下一步**。</span><span class="sxs-lookup"><span data-stu-id="96ce6-128">To start with an empty template, choose **Custom** \> **Custom policy** \> **Next**.</span></span>
    
5. <span data-ttu-id="96ce6-129">将策略\>命名为**Next**。</span><span class="sxs-lookup"><span data-stu-id="96ce6-129">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="96ce6-130">若要选择要保护 DLP 策略的位置, 请执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="96ce6-130">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="96ce6-131">选择\> **下一步\*\*\*\*中的 "Office 365 中的所有位置"** 。</span><span class="sxs-lookup"><span data-stu-id="96ce6-131">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="96ce6-132">选择 "**让我选择** \> **下一处**的特定位置"。</span><span class="sxs-lookup"><span data-stu-id="96ce6-132">Choose **Let me choose specific locations** \> **Next**.</span></span>
    
    <span data-ttu-id="96ce6-133">若要包括或排除整个位置 (如所有 Exchange 电子邮件或所有 OneDrive 帐户), 请打开或关闭该位置的**状态**。</span><span class="sxs-lookup"><span data-stu-id="96ce6-133">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="96ce6-134">若要仅包含特定的 SharePoint 网站或 OneDrive 帐户, 请将**状态**切换到 "打开", 然后单击 "**包括**" 下的链接以选择 "特定网站或帐户"。</span><span class="sxs-lookup"><span data-stu-id="96ce6-134">To include only specific SharePoint sites or OneDrive accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span> 
    
7. <span data-ttu-id="96ce6-135">选择 "**使用高级设置** \> "**下一步**。</span><span class="sxs-lookup"><span data-stu-id="96ce6-135">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="96ce6-136">选择 " **+ 新建规则**"。</span><span class="sxs-lookup"><span data-stu-id="96ce6-136">Choose **+ New rule**.</span></span>
    
9. <span data-ttu-id="96ce6-137">在规则编辑器中的 "**用户通知**" 下, 切换状态 "开启"。</span><span class="sxs-lookup"><span data-stu-id="96ce6-137">In the rule editor, under **User notifications**, switch the status on.</span></span>
    
    ![规则编辑器的用户通知部分](media/47705927-c60b-4054-a072-ab914f33d15d.png)
  
## <a name="options-for-configuring-email-notifications"></a><span data-ttu-id="96ce6-139">用于配置电子邮件通知的选项</span><span class="sxs-lookup"><span data-stu-id="96ce6-139">Options for configuring email notifications</span></span>

<span data-ttu-id="96ce6-140">对于 DLP 策略中的每个规则，您可以：</span><span class="sxs-lookup"><span data-stu-id="96ce6-140">For each rule in a DLP policy, you can:</span></span>
  
- <span data-ttu-id="96ce6-p106">将通知发送给您选择的人员。这些人员可以包含内容的所有者、最后一次修改内容的人员、存储内容的网站所有者或特定用户。</span><span class="sxs-lookup"><span data-stu-id="96ce6-p106">Send the notification to the people you choose. These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.</span></span>
    
- <span data-ttu-id="96ce6-143">使用 HTML 或标记自定义通知中包含的文本。</span><span class="sxs-lookup"><span data-stu-id="96ce6-143">Customize the text that's included in the notification by using HTML or tokens.</span></span> <span data-ttu-id="96ce6-144">有关详细信息, 请参阅下面的部分。</span><span class="sxs-lookup"><span data-stu-id="96ce6-144">See the section below for more information.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="96ce6-145">电子邮件通知只能发送给各个收件人, 而不是组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="96ce6-145">Email notifications can be sent only to individual recipients—not groups or distribution lists.</span></span> <span data-ttu-id="96ce6-146">只有新内容才会触发电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="96ce6-146">Only new content will trigger an email notification.</span></span> <span data-ttu-id="96ce6-147">编辑现有内容将触发策略提示，但不会触发电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="96ce6-147">Editing existing content will trigger policy tips but not an email notification.</span></span> 
  
![电子邮件通知选项](media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a><span data-ttu-id="96ce6-149">默认电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="96ce6-149">Default email notification</span></span>

<span data-ttu-id="96ce6-150">通知包含以所执行的操作开头的主题行, 例如 "通知"、"邮件被阻止" 或 "拒绝访问" 文档。</span><span class="sxs-lookup"><span data-stu-id="96ce6-150">Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents.</span></span> <span data-ttu-id="96ce6-151">如果通知与文档有关, 则通知邮件正文包含一个链接, 该链接将转到文档存储的网站并打开文档的策略提示, 您可以在其中解决任何问题 (请参阅下面关于策略提示的部分)。</span><span class="sxs-lookup"><span data-stu-id="96ce6-151">If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips).</span></span> <span data-ttu-id="96ce6-152">如果通知是关于邮件的通知, 则通知将包含与 DLP 策略匹配的邮件附件。</span><span class="sxs-lookup"><span data-stu-id="96ce6-152">If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.</span></span>
  
![消息通知](media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
<span data-ttu-id="96ce6-p110">默认情况下，通知显示类似于网站上以下项的文本。通知文本针对每个规则单独配置，因此根据匹配的规则，显示的文本有所不同。</span><span class="sxs-lookup"><span data-stu-id="96ce6-p110">By default, notifications display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="96ce6-156">**如果 DLP 策略规则也是如此...**</span><span class="sxs-lookup"><span data-stu-id="96ce6-156">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="96ce6-157">**然后, SharePoint 或 OneDrive for business 文档的默认通知如下所说 .。。**</span><span class="sxs-lookup"><span data-stu-id="96ce6-157">**Then the default notification for SharePoint or OneDrive for Business documents says this…**</span></span>|<span data-ttu-id="96ce6-158">**然后, Outlook 邮件的默认通知说 .。。**</span><span class="sxs-lookup"><span data-stu-id="96ce6-158">**Then the default notification for Outlook messages says this…**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="96ce6-159">发送通知但不允许替代</span><span class="sxs-lookup"><span data-stu-id="96ce6-159">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="96ce6-160">此项与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-160">This item conflicts with a policy in your organization.</span></span>  <br/> |<span data-ttu-id="96ce6-161">您的电子邮件与组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-161">Your email message conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="96ce6-162">阻止访问，发送通知，并允许重写</span><span class="sxs-lookup"><span data-stu-id="96ce6-162">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="96ce6-163">此项与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-163">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="96ce6-164">如果不解决此冲突, 则可能会阻止对此文件的访问。</span><span class="sxs-lookup"><span data-stu-id="96ce6-164">If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |<span data-ttu-id="96ce6-165">您的电子邮件与组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-165">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="96ce6-166">邮件未传递给所有收件人。</span><span class="sxs-lookup"><span data-stu-id="96ce6-166">The message wasn't delivered to all recipients.</span></span>  <br/> |
|<span data-ttu-id="96ce6-167">阻止访问，并向发送通知</span><span class="sxs-lookup"><span data-stu-id="96ce6-167">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="96ce6-p113">此项与您的组织中的策略相冲突。除非是项目的所有者、最后一次修改内容的用户以及网站集主管理员，否则其他人对此项目的访问将受到阻止。</span><span class="sxs-lookup"><span data-stu-id="96ce6-p113">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |<span data-ttu-id="96ce6-170">您的电子邮件与组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-170">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="96ce6-171">邮件未传递给所有收件人。</span><span class="sxs-lookup"><span data-stu-id="96ce6-171">The message wasn't delivered to all recipients.</span></span>  <br/> |
   
### <a name="custom-email-notification"></a><span data-ttu-id="96ce6-172">自定义电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="96ce6-172">Custom email notification</span></span>

<span data-ttu-id="96ce6-173">您可以创建自定义电子邮件通知, 而不是将默认电子邮件通知发送给最终用户或管理员。</span><span class="sxs-lookup"><span data-stu-id="96ce6-173">You can create a custom email notification instead of sending the default email notification to your end users or admins.</span></span> <span data-ttu-id="96ce6-174">自定义电子邮件通知支持 HTML, 且具有5000个字符的限制。</span><span class="sxs-lookup"><span data-stu-id="96ce6-174">The custom email notification supports HTML and has a 5,000-character limit.</span></span> <span data-ttu-id="96ce6-175">您可以使用 HTML 在通知中包含图像、格式和其他品牌打造。</span><span class="sxs-lookup"><span data-stu-id="96ce6-175">You can use HTML to include images, formatting, and other branding in the notification.</span></span>
  
<span data-ttu-id="96ce6-176">您还可以使用以下令牌帮助自定义电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="96ce6-176">You can also use the following tokens to help customize the email notification.</span></span> <span data-ttu-id="96ce6-177">这些令牌是由发送的通知中的特定信息替换的变量。</span><span class="sxs-lookup"><span data-stu-id="96ce6-177">These tokens are variables that are replaced by specific information in the notification that's sent.</span></span>

|<span data-ttu-id="96ce6-178">**标记**</span><span class="sxs-lookup"><span data-stu-id="96ce6-178">**Token**</span></span>|<span data-ttu-id="96ce6-179">**说明**</span><span class="sxs-lookup"><span data-stu-id="96ce6-179">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="96ce6-180">%%AppliedActions%%</span><span class="sxs-lookup"><span data-stu-id="96ce6-180">%%AppliedActions%%</span></span>  <br/> |<span data-ttu-id="96ce6-181">应用于内容的操作。</span><span class="sxs-lookup"><span data-stu-id="96ce6-181">The actions applied to the content.</span></span>  <br/> |
|<span data-ttu-id="96ce6-182">%% ContentURL%%</span><span class="sxs-lookup"><span data-stu-id="96ce6-182">%%ContentURL%%</span></span>  <br/> |<span data-ttu-id="96ce6-183">SharePoint Online 网站或 OneDrive for business 网站上的文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="96ce6-183">The URL of the document on the SharePoint Online site or OneDrive for Business site.</span></span>  <br/> |
|<span data-ttu-id="96ce6-184">%%MatchedConditions%%</span><span class="sxs-lookup"><span data-stu-id="96ce6-184">%%MatchedConditions%%</span></span>  <br/> |<span data-ttu-id="96ce6-185">内容所匹配的条件。</span><span class="sxs-lookup"><span data-stu-id="96ce6-185">The conditions that were matched by the content.</span></span> <span data-ttu-id="96ce6-186">使用此令牌可告知用户可能存在的内容问题。</span><span class="sxs-lookup"><span data-stu-id="96ce6-186">Use this token to inform people of possible issues with the content.</span></span>  <br/> |
   
![显示令牌显示位置的通知消息](media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a><span data-ttu-id="96ce6-188">用于配置策略提示的选项</span><span class="sxs-lookup"><span data-stu-id="96ce6-188">Options for configuring policy tips</span></span>

<span data-ttu-id="96ce6-189">对于 DLP 策略中的每个规则，您可以配置策略提示用于：</span><span class="sxs-lookup"><span data-stu-id="96ce6-189">For each rule in a DLP policy, you can configure policy tips to:</span></span>
  
- <span data-ttu-id="96ce6-190">简单地通知该用户此项内容与 DLP 策略相冲突，以便用户可以执行相应的操作来解决此冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-190">Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict.</span></span> <span data-ttu-id="96ce6-191">您可以使用默认文本 (请参阅下表) 或输入有关您的组织的特定策略的自定义文本。</span><span class="sxs-lookup"><span data-stu-id="96ce6-191">You can use the default text (see the tables below) or enter custom text about your organization's specific policies.</span></span>
    
- <span data-ttu-id="96ce6-192">允许用户替换 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="96ce6-192">Allow the person to override the DLP policy.</span></span> <span data-ttu-id="96ce6-193">（可选） 您可以：</span><span class="sxs-lookup"><span data-stu-id="96ce6-193">Optionally, you can:</span></span>
    
  - <span data-ttu-id="96ce6-194">要求用户输入替换该策略的业务理由。</span><span class="sxs-lookup"><span data-stu-id="96ce6-194">Require the person to enter a business justification for overriding the policy.</span></span> <span data-ttu-id="96ce6-195">将记录此信息, 您可以在安全&amp;合规性中心的 "**报告**" 部分的 "DLP 报告" 中查看此信息。</span><span class="sxs-lookup"><span data-stu-id="96ce6-195">This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center.</span></span> 
    
  - <span data-ttu-id="96ce6-p121">允许用户报告误报并替换 DLP 策略。此信息还被记录下来用于报告，以便您可以使用误报来微调您的规则。</span><span class="sxs-lookup"><span data-stu-id="96ce6-p121">Allow the person to report a false positive and override the DLP policy. This information is also logged for reporting, so that you can use false positives to fine tune your rules.</span></span>
    
![策略提示选项](media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
<span data-ttu-id="96ce6-199">例如, 您可以将 DLP 策略应用于检测个人身份信息 (PII) 的 OneDrive for Business 网站, 并且此策略具有三个规则:</span><span class="sxs-lookup"><span data-stu-id="96ce6-199">For example, you may have a DLP policy applied to OneDrive for Business sites that detects personally identifiable information (PII), and this policy has three rules:</span></span>
  
1. <span data-ttu-id="96ce6-p122">第一个规则：如果在文档中检测到包含此敏感信息的实例少于五个，并且该文档与组织内部的人员共享，则“发送通知”\*\*\*\* 操作将显示策略提示。对于策略提示，无需提供任何替换选项，因为此规则只是通知相关人员，但不会阻止访问。</span><span class="sxs-lookup"><span data-stu-id="96ce6-p122">First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip. For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access.</span></span> 
    
2. <span data-ttu-id="96ce6-202">第二个规则：如果在文档中检测到包含此敏感信息的实例多于五个，并且该文档与组织内部的人员共享，则“阻止访问内容”\*\*\*\* 操作将限制文件权限，并且“发送通知”\*\*\*\* 操作会允许用户通过提供业务理由来替换该规则中的操作。</span><span class="sxs-lookup"><span data-stu-id="96ce6-202">Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification.</span></span> <span data-ttu-id="96ce6-203">您的组织的业务有时需要内部人员共享 PII 数据, 并且您不希望您的 DLP 策略阻止此工作。</span><span class="sxs-lookup"><span data-stu-id="96ce6-203">Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work.</span></span> 
    
3. <span data-ttu-id="96ce6-p124">第三个规则：如果在文档中检测到包含此敏感信息的实例多于五个，并且该文档与组织外部的人员共享，则“阻止访问内容”\*\*\*\* 操作将限制文件权限，并且“发送通知”\*\*\*\* 操作将不允许用户替换该规则中的操作，因为该信息是与外部共享的。决不允许您组织中的用户在组织外部共享 PII 数据。</span><span class="sxs-lookup"><span data-stu-id="96ce6-p124">Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally. Under no circumstances should people in your organization be allowed to share PII data outside the organization.</span></span> 
    
<span data-ttu-id="96ce6-206">以下几点有助于您对使用策略提示替换规则的理解：</span><span class="sxs-lookup"><span data-stu-id="96ce6-206">Here are some fine points to understand about using a policy tip to override a rule:</span></span>
  
- <span data-ttu-id="96ce6-207">替代的选项是 "按规则", 它将覆盖规则中的所有操作 (发送不能覆盖的通知除外)。</span><span class="sxs-lookup"><span data-stu-id="96ce6-207">The option to override is per rule, and it overrides all of the actions in the rule (except sending a notification, which can't be overridden).</span></span>
    
- <span data-ttu-id="96ce6-208">可以将内容与 DLP 策略中的多个规则相匹配, 但只会显示来自最严格的最高优先级规则的策略提示。</span><span class="sxs-lookup"><span data-stu-id="96ce6-208">It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown.</span></span> <span data-ttu-id="96ce6-209">例如，阻止访问内容的规则所提供的策略提示比起只是发送通知的规则所提供的策略提示，前者的显示优先级高于后者。</span><span class="sxs-lookup"><span data-stu-id="96ce6-209">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="96ce6-210">这会让用户看不到策略提示的级联方式。</span><span class="sxs-lookup"><span data-stu-id="96ce6-210">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="96ce6-211">如果限制最严格的规则中的策略提示允许用户替换规则，那么替换此规则还会替换与此内容相匹配的所有其他规则。</span><span class="sxs-lookup"><span data-stu-id="96ce6-211">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a><span data-ttu-id="96ce6-212">OneDrive for Business 网站或 SharePoint Online 网站上的策略提示</span><span class="sxs-lookup"><span data-stu-id="96ce6-212">Policy tips on OneDrive for Business sites and SharePoint Online sites</span></span>

<span data-ttu-id="96ce6-213">当 OneDrive for business 网站或 SharePoint Online 网站上的文档与 DLP 策略中的规则相匹配, 并且该规则使用策略提示时, 策略提示会在文档中显示特殊图标:</span><span class="sxs-lookup"><span data-stu-id="96ce6-213">When a document on a OneDrive for Business site or SharePoint Online site matches a rule in a DLP policy, and that rule uses policy tips, the policy tips display special icons on the document:</span></span>
  
1. <span data-ttu-id="96ce6-214">如果该规则发送有关该文件的通知，则会显示警告图标。</span><span class="sxs-lookup"><span data-stu-id="96ce6-214">If the rule sends a notification about the file, the warning icon appears.</span></span>
    
2. <span data-ttu-id="96ce6-215">如果该规则阻止访问该文档，则会显示阻止图标。</span><span class="sxs-lookup"><span data-stu-id="96ce6-215">If the rule blocks access to the document, the blocked icon appears.</span></span>
    
![OneDrive 帐户中文档上的策略提示图标](media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
<span data-ttu-id="96ce6-217">若要对文档执行操作, 您可以选择一个项目\> 。在页面的右上](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png)角选择 "**信息**![信息" 窗格图标, 以打开 "详细信息\> " 窗格**视图策略提示**。</span><span class="sxs-lookup"><span data-stu-id="96ce6-217">To take action on a document, you can select an item \> choose **Information**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane \> **View policy tip**.</span></span>
  
<span data-ttu-id="96ce6-218">策略提示会列出问题及其内容，如果对策略提示配置了这些选项，则您可以选择“解决”\*\*\*\*，然后选择“替换”\*\*\*\* 策略提示或“报告”\*\*\*\* 误报。</span><span class="sxs-lookup"><span data-stu-id="96ce6-218">The policy tip lists the issues with the content, and if the policy tips are configured with these options, you can choose **Resolve**, and then **Override** the policy tip or **Report** a false positive.</span></span> 
  
![显示策略提示的信息窗格](media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![具有重写选项的策略提示](media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
<span data-ttu-id="96ce6-p126">将 DLP 策略同步到网站，并定期以异步方式根据这些策略对内容进行评估，因此，您创建 DLP 策略的时间与开始看到策略提示的时间之间可能出现短暂的延迟。类似延迟还有可能出现在从您解决或替换策略提示到网站的文档上的图标消失的这段时间里。</span><span class="sxs-lookup"><span data-stu-id="96ce6-p126">DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips. There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.</span></span>
  
### <a name="default-text-for-policy-tips-on-sites"></a><span data-ttu-id="96ce6-223">网站上的策略提示的默认文本</span><span class="sxs-lookup"><span data-stu-id="96ce6-223">Default text for policy tips on sites</span></span>

<span data-ttu-id="96ce6-p127">默认情况下，策略提示显示在网站上类似于以下项的文本。通知文本针对每个规则单独配置，因此根据匹配的规则，显示的文本有所不同。</span><span class="sxs-lookup"><span data-stu-id="96ce6-p127">By default, policy tips display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="96ce6-226">**如果 DLP 策略规则也是如此...**</span><span class="sxs-lookup"><span data-stu-id="96ce6-226">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="96ce6-227">**然后默认策略提示的说明如下...**</span><span class="sxs-lookup"><span data-stu-id="96ce6-227">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="96ce6-228">发送通知但不允许替代</span><span class="sxs-lookup"><span data-stu-id="96ce6-228">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="96ce6-229">此项与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-229">This item conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="96ce6-230">阻止访问，发送通知，并允许重写</span><span class="sxs-lookup"><span data-stu-id="96ce6-230">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="96ce6-231">此项与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-231">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="96ce6-232">如果不解决此冲突, 则可能会阻止对此文件的访问。</span><span class="sxs-lookup"><span data-stu-id="96ce6-232">If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |
|<span data-ttu-id="96ce6-233">阻止访问，并向发送通知</span><span class="sxs-lookup"><span data-stu-id="96ce6-233">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="96ce6-p129">此项与您的组织中的策略相冲突。除非是项目的所有者、最后一次修改内容的用户以及网站集主管理员，否则其他人对此项目的访问将受到阻止。</span><span class="sxs-lookup"><span data-stu-id="96ce6-p129">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a><span data-ttu-id="96ce6-236">网站上的策略提示的自定义文本</span><span class="sxs-lookup"><span data-stu-id="96ce6-236">Custom text for policy tips on sites</span></span>

<span data-ttu-id="96ce6-237">您可以独立于电子邮件通知自定义策略提示的文本。</span><span class="sxs-lookup"><span data-stu-id="96ce6-237">You can customize the text for policy tips separately from the email notification.</span></span> <span data-ttu-id="96ce6-238">与电子邮件通知的自定义文本不同 (请参阅上文) 时, 策略提示的自定义文本不接受 HTML 或标记。</span><span class="sxs-lookup"><span data-stu-id="96ce6-238">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span></span> <span data-ttu-id="96ce6-239">相反, 策略提示的自定义文本是纯文本, 只有256个字符的限制。</span><span class="sxs-lookup"><span data-stu-id="96ce6-239">Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a><span data-ttu-id="96ce6-240">Outlook 网页和 Outlook 2013 及更高版本中的策略提示</span><span class="sxs-lookup"><span data-stu-id="96ce6-240">Policy tips in Outlook on the web and Outlook 2013 and later</span></span>

<span data-ttu-id="96ce6-241">在 web 上的 Outlook 和 Outlook 2013 及更高版本中撰写新电子邮件时, 如果添加了与 DLP 策略中的规则匹配的内容, 并且该规则使用策略提示, 则会看到策略提示。</span><span class="sxs-lookup"><span data-stu-id="96ce6-241">When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips.</span></span> <span data-ttu-id="96ce6-242">在撰写邮件时, 策略提示将显示在邮件顶部的收件人上方。</span><span class="sxs-lookup"><span data-stu-id="96ce6-242">The policy tip appears at the top of the message, above the recipients, while the message is being composed.</span></span>
  
![正在撰写的邮件顶部的策略提示](media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
<span data-ttu-id="96ce6-244">策略提示可用于敏感信息是显示在邮件正文、主题行中还是邮件附件中, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="96ce6-244">Policy tips work whether the sensitive information appears in the message body, subject line, or even a message attachment as shown here.</span></span>
  
![显示附件与 DLP 策略冲突的策略提示](media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
<span data-ttu-id="96ce6-246">如果将策略提示配置为允许替代, 则可以选择 "**显示详细信息** \> **" 替代** \> "输入业务理由" 或报告\> "误报肯定**替代**"。</span><span class="sxs-lookup"><span data-stu-id="96ce6-246">If the policy tips are configured to allow override, you can choose **Show Details** \> **Override** \> enter a business justification or report a false positive \> **Override**.</span></span>
  
![邮件中的策略提示已展开为显示覆盖选项](media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![您可以在其中覆盖策略提示的策略提示对话框](media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
<span data-ttu-id="96ce6-249">请注意, 在将敏感信息添加到电子邮件时, 在添加敏感信息和显示策略提示之间可能存在延迟。</span><span class="sxs-lookup"><span data-stu-id="96ce6-249">Note that when you add sensitive information to an email, there may be latency between when the sensitive information is added and when the policy tip appears.</span></span>

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a><span data-ttu-id="96ce6-250">Outlook 2013 及更高版本支持仅显示某些条件的策略提示</span><span class="sxs-lookup"><span data-stu-id="96ce6-250">Outlook 2013 and later supports showing policy tips for only some conditions</span></span>

<span data-ttu-id="96ce6-251">目前, Outlook 2013 及更高版本支持仅显示这些条件的策略提示:</span><span class="sxs-lookup"><span data-stu-id="96ce6-251">Currently, Outlook 2013 and later supports showing policy tips only for these conditions:</span></span>

- <span data-ttu-id="96ce6-252">内容包含</span><span class="sxs-lookup"><span data-stu-id="96ce6-252">Content contains</span></span>
- <span data-ttu-id="96ce6-253">共享内容</span><span class="sxs-lookup"><span data-stu-id="96ce6-253">Content is shared</span></span>

<span data-ttu-id="96ce6-254">我们目前正在努力为其他条件显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="96ce6-254">We're currently working on support for showing policy tips for additional conditions.</span></span> <span data-ttu-id="96ce6-255">具体包括：</span><span class="sxs-lookup"><span data-stu-id="96ce6-255">These include:</span></span>

- <span data-ttu-id="96ce6-256">无法扫描任何电子邮件附件的内容</span><span class="sxs-lookup"><span data-stu-id="96ce6-256">Any email attachment's content could not be scanned</span></span>
- <span data-ttu-id="96ce6-257">任何电子邮件附件的内容未完成扫描</span><span class="sxs-lookup"><span data-stu-id="96ce6-257">Any email attachment's content didn't complete scanning</span></span>
- <span data-ttu-id="96ce6-258">附件文件扩展名为</span><span class="sxs-lookup"><span data-stu-id="96ce6-258">Attachment file extension is</span></span>
- <span data-ttu-id="96ce6-259">附件受密码保护</span><span class="sxs-lookup"><span data-stu-id="96ce6-259">Attachment is password protected</span></span>
- <span data-ttu-id="96ce6-260">Document 属性为</span><span class="sxs-lookup"><span data-stu-id="96ce6-260">Document property is</span></span>
- <span data-ttu-id="96ce6-261">收件人域为</span><span class="sxs-lookup"><span data-stu-id="96ce6-261">Recipient domain is</span></span>
- <span data-ttu-id="96ce6-262">发件人 IP 地址为</span><span class="sxs-lookup"><span data-stu-id="96ce6-262">Sender IP address is</span></span>

<span data-ttu-id="96ce6-263">请注意, 所有这些条件在 Outlook 中都有效, 在这里, 它们将与内容相匹配, 并对内容强制实施保护操作。</span><span class="sxs-lookup"><span data-stu-id="96ce6-263">Note that all of these conditions work in Outlook, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="96ce6-264">但尚不支持向用户显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="96ce6-264">But showing policy tips to users is not yet supported.</span></span>
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="96ce6-265">Exchange 管理中心中的策略提示与 Office 365 安全&amp;合规中心</span><span class="sxs-lookup"><span data-stu-id="96ce6-265">Policy tips in the Exchange admin center vs. the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="96ce6-266">策略提示可使用在 Exchange 管理中心中创建的 DLP 策略和邮件流规则, 或使用在 Office 365 安全&amp;合规中心中创建的 dlp 策略, 但不能同时使用这两种策略。</span><span class="sxs-lookup"><span data-stu-id="96ce6-266">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Office 365 Security &amp; Compliance Center, but not both.</span></span> <span data-ttu-id="96ce6-267">这是因为这些策略存储在不同的位置, 但策略提示只能从一个位置进行绘制。</span><span class="sxs-lookup"><span data-stu-id="96ce6-267">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="96ce6-268">如果已在 Exchange 管理中心中配置了策略提示, 则在 Office 365 安全&amp;合规中心中配置的任何策略提示都不会显示在 outlook 网页和 outlook 2013 及更高版本的 outlook 中, 直到您关闭 Exchange 中的提示。管理中心。</span><span class="sxs-lookup"><span data-stu-id="96ce6-268">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Office 365 Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="96ce6-269">这样可确保当前的 Exchange 邮件流规则 (也称为传输规则) 在您选择切换到 "Office 365 安全&amp;合规中心" 之前仍有效。</span><span class="sxs-lookup"><span data-stu-id="96ce6-269">This ensures that your current Exchange mail flow rules (also known as transport rules) will continue to work until you choose to switch over to the Office 365 Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="96ce6-270">请注意, 虽然策略提示只能从一个位置进行绘制, 但总是发送电子邮件通知, 即使您在 Office 365 安全&amp;合规中心和 Exchange 管理中心中使用的是 DLP 策略也是如此。</span><span class="sxs-lookup"><span data-stu-id="96ce6-270">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Office 365 Security &amp; Compliance Center and the Exchange admin center.</span></span>
  
### <a name="default-text-for-policy-tips-in-email"></a><span data-ttu-id="96ce6-271">电子邮件中的策略提示的默认文本</span><span class="sxs-lookup"><span data-stu-id="96ce6-271">Default text for policy tips in email</span></span>

<span data-ttu-id="96ce6-272">默认情况下, 策略提示显示类似于电子邮件的以下文本。</span><span class="sxs-lookup"><span data-stu-id="96ce6-272">By default, policy tips display text similar to the following for email.</span></span>

|<span data-ttu-id="96ce6-273">**如果 DLP 策略规则也是如此...**</span><span class="sxs-lookup"><span data-stu-id="96ce6-273">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="96ce6-274">**然后默认策略提示的说明如下...**</span><span class="sxs-lookup"><span data-stu-id="96ce6-274">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="96ce6-275">发送通知但不允许替代</span><span class="sxs-lookup"><span data-stu-id="96ce6-275">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="96ce6-276">您的电子邮件与组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-276">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="96ce6-277">阻止访问，发送通知，并允许重写</span><span class="sxs-lookup"><span data-stu-id="96ce6-277">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="96ce6-278">您的电子邮件与组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-278">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="96ce6-279">阻止访问，并向发送通知</span><span class="sxs-lookup"><span data-stu-id="96ce6-279">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="96ce6-280">您的电子邮件与组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-280">Your email conflicts with a policy in your organization.</span></span>  <br/> |
   
## <a name="policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="96ce6-281">Excel 2016、PowerPoint 2016 和 Word 2016 中的策略提示</span><span class="sxs-lookup"><span data-stu-id="96ce6-281">Policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="96ce6-p136">当用户在桌面版本的 Excel 2016、PowerPoint 2016 和 Word 2016 中使用敏感内容时，策略提示可以实时通知用户，告知内容与 DLP 策略之间发生冲突。这要求：</span><span class="sxs-lookup"><span data-stu-id="96ce6-p136">When people work with sensitive content in the desktop versions of Excel 2016, PowerPoint 2016, and Word 2016, policy tips can notify them in real time that the content conflicts with a DLP policy. This requires that:</span></span>
  
- <span data-ttu-id="96ce6-284">Office 文档存储在 OneDrive for Business 网站或 SharePoint Online 网站上。</span><span class="sxs-lookup"><span data-stu-id="96ce6-284">The Office document is stored on a OneDrive for Business site or SharePoint Online site.</span></span>
    
- <span data-ttu-id="96ce6-285">该网站包含在配置为使用策略提示的 DLP 策略中。</span><span class="sxs-lookup"><span data-stu-id="96ce6-285">The site is included in a DLP policy that's configured to use policy tips.</span></span>
    
<span data-ttu-id="96ce6-286">这些 Office 2016 桌面程序将自动从 Office 365 中直接同步 DLP 策略, 然后扫描您的文档以确保它们不会与您的 DLP 策略冲突并实时显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="96ce6-286">These Office 2016 desktop programs automatically sync DLP policies directly from Office 365, and then scan your documents to ensure that they don't conflict with your DLP policies and display policy tips in real time.</span></span>
  
<span data-ttu-id="96ce6-287">根据您在 DLP 策略中对策略提示的配置方式，用户可以选择忽略策略提示、使用或不使用业务理由替换策略或报告误报。</span><span class="sxs-lookup"><span data-stu-id="96ce6-287">Depending on how you configure the policy tips in the DLP policy, people can choose to simply ignore the policy tip, override the policy with or without a business justification, or report a false positive.</span></span>
  
<span data-ttu-id="96ce6-288">在消息栏上显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="96ce6-288">Policy tips appear on the Message Bar.</span></span>
  
![消息栏在 Excel 2016 中显示策略提示](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="96ce6-290">策略提示也显示在 Backstage 视图（“文件”\*\*\*\* 选项卡上）中。</span><span class="sxs-lookup"><span data-stu-id="96ce6-290">And policy tips also appear in the Backstage view (on the **File** tab).</span></span> 
  
![Backstage 在 Excel 2016 中显示策略提示](media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
<span data-ttu-id="96ce6-292">如果对 DLP 策略中的策略提示配置了这些选项，您可以选择“解决”\*\*\*\* 以“替换”\*\*\*\* 策略提示或“报告”\*\*\*\* 误报。</span><span class="sxs-lookup"><span data-stu-id="96ce6-292">If policy tips in the DLP policy are configured with these options, you can choose **Resolve** to **Override** a policy tip or **Report** a false positive.</span></span> 
  
![Excel 2016 Backstage 中的策略提示选项](media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
<span data-ttu-id="96ce6-p137">在每一个这些 Office 2016 桌面程序中，用户可以选择关闭策略提示。如果已关闭，则只是简单通知的策略提示将不会显示在消息栏或 Backstage 视图（“文件”\*\*\*\* 选项卡上）上。但是，仍会显示有关阻止和替换的策略提示，并且仍将收到电子邮件通知。此外，关闭策略提示并不会将文档从任何已对其应用的 DLP 策略中予以免除。</span><span class="sxs-lookup"><span data-stu-id="96ce6-p137">In each of these Office 2016 desktop programs, people can choose to turn off policy tips. If turned off, policy tips that are simple notifications will not appear on the Message Bar or Backstage view (on the **File** tab). However, policy tips about blocking and overriding will still appear, and they will still receive the email notification. In addition, turning off policy tips does not exempt the document from any DLP policies that have been applied to it.</span></span> 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="96ce6-298">Excel 2016、PowerPoint 2016 和 Word 2016 中的策略提示的默认文本</span><span class="sxs-lookup"><span data-stu-id="96ce6-298">Default text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="96ce6-p138">默认情况下，策略提示将在打开文档的消息栏和 Backstage 视图中显示类似于以下的文本。通知文本针对每个规则单独配置，因此根据匹配的规则，显示的文本有所不同。</span><span class="sxs-lookup"><span data-stu-id="96ce6-p138">By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="96ce6-301">**如果 DLP 策略规则也是如此...**</span><span class="sxs-lookup"><span data-stu-id="96ce6-301">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="96ce6-302">**然后默认策略提示的说明如下...**</span><span class="sxs-lookup"><span data-stu-id="96ce6-302">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="96ce6-303">发送通知但不允许替代</span><span class="sxs-lookup"><span data-stu-id="96ce6-303">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="96ce6-304">此文件与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-304">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="96ce6-305">有关详细信息, 请转到 "**文件**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="96ce6-305">Go to the **File** menu for more information.</span></span>  <br/> |
|<span data-ttu-id="96ce6-306">阻止访问，发送通知，并允许重写</span><span class="sxs-lookup"><span data-stu-id="96ce6-306">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="96ce6-307">此文件与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-307">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="96ce6-308">如果不解决此冲突, 则可能会阻止对此文件的访问。</span><span class="sxs-lookup"><span data-stu-id="96ce6-308">If you don't resolve this conflict, access to this file might be blocked.</span></span> <span data-ttu-id="96ce6-309">有关详细信息, 请转到 "**文件**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="96ce6-309">Go to the **File** menu for more information.</span></span>  <br/> |
|<span data-ttu-id="96ce6-310">阻止访问，并向发送通知</span><span class="sxs-lookup"><span data-stu-id="96ce6-310">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="96ce6-311">此文件与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="96ce6-311">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="96ce6-312">如果不解决此冲突, 则可能会阻止对此文件的访问。</span><span class="sxs-lookup"><span data-stu-id="96ce6-312">If you don't resolve this conflict, access to this file might be blocked.</span></span> <span data-ttu-id="96ce6-313">有关详细信息, 请转到 "**文件**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="96ce6-313">Go to the **File** menu for more information.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="96ce6-314">Excel 2016、PowerPoint 2016 和 Word 2016 中的策略提示的自定义文本</span><span class="sxs-lookup"><span data-stu-id="96ce6-314">Custom text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="96ce6-315">您可以独立于电子邮件通知自定义策略提示的文本。</span><span class="sxs-lookup"><span data-stu-id="96ce6-315">You can customize the text for policy tips separately from the email notification.</span></span> <span data-ttu-id="96ce6-316">与电子邮件通知的自定义文本不同 (请参阅上文) 时, 策略提示的自定义文本不接受 HTML 或标记。</span><span class="sxs-lookup"><span data-stu-id="96ce6-316">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span></span> <span data-ttu-id="96ce6-317">相反, 策略提示的自定义文本是纯文本, 只有256个字符的限制。</span><span class="sxs-lookup"><span data-stu-id="96ce6-317">Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="96ce6-318">更多信息</span><span class="sxs-lookup"><span data-stu-id="96ce6-318">More information</span></span>

- [<span data-ttu-id="96ce6-319">数据丢失防护策略概述</span><span class="sxs-lookup"><span data-stu-id="96ce6-319">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="96ce6-320">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="96ce6-320">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="96ce6-321">创建 DLP 策略来保护具有 FCI 或其他属性的文档</span><span class="sxs-lookup"><span data-stu-id="96ce6-321">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="96ce6-322">DLP 策略模板包含的内容</span><span class="sxs-lookup"><span data-stu-id="96ce6-322">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="96ce6-323">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="96ce6-323">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    


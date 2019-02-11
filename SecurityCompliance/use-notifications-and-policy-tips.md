---
title: 发送电子邮件通知和显示策略提示的 DLP 策略
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 87496bc5-9601-4473-8021-cb05c71369c1
description: '策略提示通知或某人正在使用的内容与某个 DLP 策略的冲突时出现的警告。您可以使用电子邮件通知和策略提示提高关注度和帮助了解有关您组织的策略的人员。您也可以的为用户选择重写策略，以便它们不将被阻止如果他们有有效的业务需要或策略检测误报。 '
ms.openlocfilehash: 78247a283b2a3b8d581a8b27fe0bf124ed46b222
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "25803993"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a><span data-ttu-id="fe872-105">发送电子邮件通知和显示策略提示的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="fe872-105">Send email notifications and show policy tips for DLP policies</span></span>

<span data-ttu-id="fe872-p102">数据丢失防护 (DLP) 策略可用于标识、 监视和跨 Office 365 保护敏感信息。您想要在组织中使用人员保持符合您的 DLP 策略，此敏感信息，但不希望阻止其不必要地完成其工作。这是可帮助电子邮件通知和策略提示。</span><span class="sxs-lookup"><span data-stu-id="fe872-p102">You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365. You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done. This is where email notifications and policy tips can help.</span></span>
  
![消息栏在 Excel 2016 中显示策略提示](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="fe872-110">策略提示为一个通知或某人正在使用冲突与某个 DLP 策略的内容时出现的警告 — 例如，Excel 工作簿上的 OneDrive for Business 站点的包含个人身份信息 (PII)，如内容与外部用户共享。</span><span class="sxs-lookup"><span data-stu-id="fe872-110">A policy tip is a notification or warning that appears when someone is working with content that conflicts with a DLP policy—for example, content like an Excel workbook on a OneDrive for Business site that contains personally identifiable information (PII) and is shared with an external user.</span></span>
  
<span data-ttu-id="fe872-p103">您可以使用电子邮件通知和策略提示提高关注度和帮助了解有关您组织的策略的人员。您也可以的为用户选择重写策略，以便它们不将被阻止如果他们有有效的业务需要或策略检测误报。</span><span class="sxs-lookup"><span data-stu-id="fe872-p103">You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies. You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.</span></span>
  
<span data-ttu-id="fe872-113">Office 365 安全性&amp;合规性中心，您创建的 DLP 策略时，您可以配置向用户通知:</span><span class="sxs-lookup"><span data-stu-id="fe872-113">In the Office 365 Security &amp; Compliance Center, when you create a DLP policy, you can configure the user notifications to:</span></span>
  
- <span data-ttu-id="fe872-114">发送的电子邮件通知的人员您选择的描述问题。</span><span class="sxs-lookup"><span data-stu-id="fe872-114">Send an email notification to the people you choose that describes the issue.</span></span>
    
- <span data-ttu-id="fe872-115">显示策略提示的 DLP 策略与冲突的内容：</span><span class="sxs-lookup"><span data-stu-id="fe872-115">Display a policy tip for content that conflicts with the DLP policy:</span></span>
    
  - <span data-ttu-id="fe872-116">为 web 和 Outlook 2013 及更高版本上的 Outlook 中的电子邮件，策略提示的顶端显示上方收件人的邮件正在撰写邮件时。</span><span class="sxs-lookup"><span data-stu-id="fe872-116">For email in Outlook on the web and Outlook 2013 and later, the policy tip appears at the top of a message above the recipients while the message is being composed.</span></span>
    
  - <span data-ttu-id="fe872-p104">Onedrive for Business 帐户或 SharePoint Online 网站的文档，对项目将显示一个警告图标表示策略提示。若要查看的详细信息，您可以选择一个项目，然后选择**信息**![信息窗格中图标](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png)中要打开详细信息窗格的页面的右上角。</span><span class="sxs-lookup"><span data-stu-id="fe872-p104">For documents in a OneDrive for Business account or SharePoint Online site, the policy tip is indicated by a warning icon that appears on the item. To view more information, you can select an item and then choose **Information**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane.</span></span> 
    
  - <span data-ttu-id="fe872-119">Excel 2016、 PowerPoint 2016 和存储在 OneDrive for Business 站点或 DLP 策略中包括的 SharePoint Online 站点的 Word 2016 文档，策略提示出现在消息栏和 Backstage 视图 (**文件**菜单\> **Info**)。</span><span class="sxs-lookup"><span data-stu-id="fe872-119">For Excel 2016, PowerPoint 2016, and Word 2016 documents that are stored on a OneDrive for Business site or SharePoint Online site that's included in the DLP policy, the policy tip appears on the Message Bar and the Backstage view ( **File** menu \> **Info**).</span></span>
    
## <a name="add-user-notifications-to-a-dlp-policy"></a><span data-ttu-id="fe872-120">将用户通知添加到 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="fe872-120">Add user notifications to a DLP policy</span></span>

<span data-ttu-id="fe872-121">创建 DLP 策略时，电子邮件通知和策略提示是**用户通知**节的一部分。</span><span class="sxs-lookup"><span data-stu-id="fe872-121">When you create a DLP policy, both email notifications and policy tips are part of the **User notifications** section.</span></span> 
  
1. <span data-ttu-id="fe872-122">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="fe872-122">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="fe872-p105">登录到 Office 365 使用工作或学校帐户。您现在正在使用的 Office 365 安全性&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="fe872-p105">Sign in to Office 365 using your work or school account. You're now in the Office 365 Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="fe872-125">安全中&amp;合规性中心\>左侧导航栏\>**数据丢失防护** \> **策略** \> **+ 创建策略**。</span><span class="sxs-lookup"><span data-stu-id="fe872-125">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![创建策略按钮](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="fe872-127">选择保护的所需的敏感信息类型的 DLP 策略模板\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fe872-127">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="fe872-128">要启动与一个空的模板，选择**自定义** \> **自定义策略** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="fe872-128">To start with an empty template, choose **Custom** \> **Custom policy** \> **Next**.</span></span>
    
5. <span data-ttu-id="fe872-129">策略命名\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="fe872-129">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="fe872-130">若要选择您想要保护的 DLP 策略的位置，请执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="fe872-130">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="fe872-131">选择**Office 365 中的所有位置** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="fe872-131">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="fe872-132">选择**让我选择特定位置** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="fe872-132">Choose **Let me choose specific locations** \> **Next**.</span></span>
    
    <span data-ttu-id="fe872-133">若要包括或排除整个的位置，如所有 Exchange 电子邮件或所有 OneDrive 帐户，切换**状态**的位置打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="fe872-133">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="fe872-134">要包括仅限特定的 SharePoint 网站或 OneDrive 帐户上，切换到**状态**，然后单击**Include**以便选择特定的网站或帐户下的链接。</span><span class="sxs-lookup"><span data-stu-id="fe872-134">To include only specific SharePoint sites or OneDrive accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span> 
    
7. <span data-ttu-id="fe872-135">选择**使用高级设置** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="fe872-135">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="fe872-136">选择 **+ 新建规则**。</span><span class="sxs-lookup"><span data-stu-id="fe872-136">Choose **+ New rule**.</span></span>
    
9. <span data-ttu-id="fe872-137">在规则编辑器中，在**用户通知**，下切换的状态。</span><span class="sxs-lookup"><span data-stu-id="fe872-137">In the rule editor, under **User notifications**, switch the status on.</span></span>
    
    ![规则编辑器的用户通知部分](media/47705927-c60b-4054-a072-ab914f33d15d.png)
  
## <a name="options-for-configuring-email-notifications"></a><span data-ttu-id="fe872-139">用于配置电子邮件通知的选项</span><span class="sxs-lookup"><span data-stu-id="fe872-139">Options for configuring email notifications</span></span>

<span data-ttu-id="fe872-140">对于 DLP 策略中的每个规则，您可以：</span><span class="sxs-lookup"><span data-stu-id="fe872-140">For each rule in a DLP policy, you can:</span></span>
  
- <span data-ttu-id="fe872-p106">将通知发送给您选择的人员。这些人员可以包含内容的所有者、最后一次修改内容的人员、存储内容的网站所有者或特定用户。</span><span class="sxs-lookup"><span data-stu-id="fe872-p106">Send the notification to the people you choose. These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.</span></span>
    
- <span data-ttu-id="fe872-p107">自定义通知中使用 HTML 或令牌包含的文本。请参阅下方的详细信息部分。</span><span class="sxs-lookup"><span data-stu-id="fe872-p107">Customize the text that's included in the notification by using HTML or tokens. See the section below for more information.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="fe872-p108">仅为单个收件人可以发送电子邮件通知 — 不组或通讯组列表。> 新的内容将触发的电子邮件通知。编辑现有的内容将触发策略提示，但不是的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="fe872-p108">Email notifications can be sent only to individual recipients—not groups or distribution lists. >  Only new content will trigger an email notification. Editing existing content will trigger policy tips but not an email notification.</span></span> 
  
![电子邮件通知选项](media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a><span data-ttu-id="fe872-149">默认电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="fe872-149">Default email notification</span></span>

<span data-ttu-id="fe872-p109">通知的文档的电子邮件，或"阻止访问"具有主题行的开头的操作，如"通知"，"阻止邮件"。如果文档有关的通知，通知邮件正文包含其中该文档的存储，并打开文档，策略提示的网站的链接如果您可以解决任何问题 （请参阅下面有关策略提示的部分）。如果通知是关于一条消息，通知包括匹配 DLP 策略的邮件作为附件。</span><span class="sxs-lookup"><span data-stu-id="fe872-p109">Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents. If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips). If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.</span></span>
  
![消息通知](media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
<span data-ttu-id="fe872-p110">默认情况下，通知显示类似于网站上以下项的文本。通知文本针对每个规则单独配置，因此根据匹配的规则，显示的文本有所不同。</span><span class="sxs-lookup"><span data-stu-id="fe872-p110">By default, notifications display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="fe872-156">**如果 DLP 策略规则也是如此...**</span><span class="sxs-lookup"><span data-stu-id="fe872-156">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="fe872-157">**然后默认通知针对 SharePoint 或 OneDrive for Business 文档指出此...**</span><span class="sxs-lookup"><span data-stu-id="fe872-157">**Then the default notification for SharePoint or OneDrive for Business documents says this…**</span></span>|<span data-ttu-id="fe872-158">**然后 Outlook 邮件的默认通知指示此...**</span><span class="sxs-lookup"><span data-stu-id="fe872-158">**Then the default notification for Outlook messages says this…**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fe872-159">发送通知，但不允许覆盖</span><span class="sxs-lookup"><span data-stu-id="fe872-159">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="fe872-160">此项与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="fe872-160">This item conflicts with a policy in your organization.</span></span>  <br/> |<span data-ttu-id="fe872-161">与您的组织中的某个策略您电子邮件消息冲突。</span><span class="sxs-lookup"><span data-stu-id="fe872-161">Your email message conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="fe872-162">阻止访问，发送通知，并允许重写</span><span class="sxs-lookup"><span data-stu-id="fe872-162">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="fe872-p111">与您的组织中的某个策略，此项冲突。如果您没有解决此冲突，可能会阻止对此文件的访问。</span><span class="sxs-lookup"><span data-stu-id="fe872-p111">This item conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |<span data-ttu-id="fe872-p112">与您的组织中的某个策略您电子邮件消息冲突。邮件无法传递给所有收件人。</span><span class="sxs-lookup"><span data-stu-id="fe872-p112">Your email message conflicts with a policy in your organization. The message wasn't delivered to all recipients.</span></span>  <br/> |
|<span data-ttu-id="fe872-167">阻止访问，并向发送通知</span><span class="sxs-lookup"><span data-stu-id="fe872-167">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="fe872-p113">此项与您的组织中的策略相冲突。除非是项目的所有者、最后一次修改内容的用户以及网站集主管理员，否则其他人对此项目的访问将受到阻止。</span><span class="sxs-lookup"><span data-stu-id="fe872-p113">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |<span data-ttu-id="fe872-p114">与您的组织中的某个策略您电子邮件消息冲突。邮件无法传递给所有收件人。</span><span class="sxs-lookup"><span data-stu-id="fe872-p114">Your email message conflicts with a policy in your organization. The message wasn't delivered to all recipients.</span></span>  <br/> |
   
### <a name="custom-email-notification"></a><span data-ttu-id="fe872-172">自定义电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="fe872-172">Custom email notification</span></span>

<span data-ttu-id="fe872-p115">您可以创建自定义电子邮件通知而不是默认电子邮件通知发送到您的最终用户或管理员。自定义电子邮件通知支持 HTML 具有 5,000 个字符的限制。您可以使用 HTML 包括图像、 格式和其他通知中的品牌。</span><span class="sxs-lookup"><span data-stu-id="fe872-p115">You can create a custom email notification instead of sending the default email notification to your end users or admins. The custom email notification supports HTML and has a 5,000-character limit. You can use HTML to include images, formatting, and other branding in the notification.</span></span>
  
<span data-ttu-id="fe872-p116">您可以使用以下标记以帮助自定义电子邮件通知。这些令牌是替换为所发送的通知中的特定信息的变量。</span><span class="sxs-lookup"><span data-stu-id="fe872-p116">You can also use the following tokens to help customize the email notification. These tokens are variables that are replaced by specific information in the notification that's sent.</span></span>

|<span data-ttu-id="fe872-178">**令牌**</span><span class="sxs-lookup"><span data-stu-id="fe872-178">**Token**</span></span>|<span data-ttu-id="fe872-179">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe872-179">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe872-180">%Appliedactions%%</span><span class="sxs-lookup"><span data-stu-id="fe872-180">%%AppliedActions%%</span></span>  <br/> |<span data-ttu-id="fe872-181">应用于内容的操作。</span><span class="sxs-lookup"><span data-stu-id="fe872-181">The actions applied to the content.</span></span>  <br/> |
|<span data-ttu-id="fe872-182">%Contenturl%%</span><span class="sxs-lookup"><span data-stu-id="fe872-182">%%ContentURL%%</span></span>  <br/> |<span data-ttu-id="fe872-183">业务网站上的 SharePoint Online 网站或 OneDrive 文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="fe872-183">The URL of the document on the SharePoint Online site or OneDrive for Business site.</span></span>  <br/> |
|<span data-ttu-id="fe872-184">%Matchedconditions%%</span><span class="sxs-lookup"><span data-stu-id="fe872-184">%%MatchedConditions%%</span></span>  <br/> |<span data-ttu-id="fe872-p117">由内容都匹配条件。使用此标记以通知的内容可能出现的问题的人员。</span><span class="sxs-lookup"><span data-stu-id="fe872-p117">The conditions that were matched by the content. Use this token to inform people of possible issues with the content.</span></span>  <br/> |
   
![通知消息显示标记的显示位置](media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a><span data-ttu-id="fe872-188">用于配置策略提示的选项</span><span class="sxs-lookup"><span data-stu-id="fe872-188">Options for configuring policy tips</span></span>

<span data-ttu-id="fe872-189">对于 DLP 策略中的每个规则，您可以配置策略提示用于：</span><span class="sxs-lookup"><span data-stu-id="fe872-189">For each rule in a DLP policy, you can configure policy tips to:</span></span>
  
- <span data-ttu-id="fe872-p118">只需通知的人内容冲突与某个 DLP 策略，以便他们可以执行的操作来解决冲突。您可以使用的默认文本 （请参阅下表） 或输入有关贵组织的特定策略的自定义文本。</span><span class="sxs-lookup"><span data-stu-id="fe872-p118">Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict. You can use the default text (see the tables below) or enter custom text about your organization's specific policies.</span></span>
    
- <span data-ttu-id="fe872-p119">允许用户替换 DLP 策略。（可选） 您可以：</span><span class="sxs-lookup"><span data-stu-id="fe872-p119">Allow the person to override the DLP policy. Optionally, you can:</span></span>
    
  - <span data-ttu-id="fe872-p120">需要输入覆盖该策略的业务理由的人员。记录此信息和您在 DLP 报告中的安全**报告**部分可以查看它&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="fe872-p120">Require the person to enter a business justification for overriding the policy. This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center.</span></span> 
    
  - <span data-ttu-id="fe872-p121">允许用户报告误报并替换 DLP 策略。此信息还被记录下来用于报告，以便您可以使用误报来微调您的规则。</span><span class="sxs-lookup"><span data-stu-id="fe872-p121">Allow the person to report a false positive and override the DLP policy. This information is also logged for reporting, so that you can use false positives to fine tune your rules.</span></span>
    
![策略提示选项](media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
<span data-ttu-id="fe872-199">例如，您可以检测到个人身份信息 (PII) 的 DLP 策略应用到 OneDrive for Business 站点，该策略有三个规则：</span><span class="sxs-lookup"><span data-stu-id="fe872-199">For example, you may have a DLP policy applied to OneDrive for Business sites that detects personally identifiable information (PII), and this policy has three rules:</span></span>
  
1. <span data-ttu-id="fe872-p122">首先规则：**发送通知**的操作文档中检测到少于五台此敏感信息实例和文档共享与组织内部的人员，如果显示策略提示。策略提示，没有替代选项是必需的这是因为此规则是只需通知人员并不会阻止访问。</span><span class="sxs-lookup"><span data-stu-id="fe872-p122">First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip. For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access.</span></span> 
    
2. <span data-ttu-id="fe872-p123">第二个规则： 如果大于文档中检测到五个实例，此敏感信息和文档共享与组织内部的人员，**阻止访问内容**操作限制文件和**的权限发送通知**操作使用户能够替代此规则中的操作提供的业务理由。有时，贵组织的业务要求内部的人员共享 PII 数据，并且您无需您的 DLP 策略阻止此项工作。</span><span class="sxs-lookup"><span data-stu-id="fe872-p123">Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification. Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work.</span></span> 
    
3. <span data-ttu-id="fe872-p124">第 3 个规则： 如果大于文档中检测到五个实例，此敏感信息和文档共享与组织外部的人员，**阻止访问内容**操作限制文件和**的权限发送通知**操作都不允许覆盖此规则中的操作，因为外部共享信息的人员。在任何情况下应在组织中的人员允许共享 PII 组织外部的数据。</span><span class="sxs-lookup"><span data-stu-id="fe872-p124">Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally. Under no circumstances should people in your organization be allowed to share PII data outside the organization.</span></span> 
    
<span data-ttu-id="fe872-206">以下几点有助于您对使用策略提示替换规则的理解：</span><span class="sxs-lookup"><span data-stu-id="fe872-206">Here are some fine points to understand about using a policy tip to override a rule:</span></span>
  
- <span data-ttu-id="fe872-207">若要覆盖的选项是每个规则，以及重写的所有操作中的规则 （除发送通知，不能重写）。</span><span class="sxs-lookup"><span data-stu-id="fe872-207">The option to override is per rule, and it overrides all of the actions in the rule (except sending a notification, which can't be overridden).</span></span>
    
- <span data-ttu-id="fe872-p125">可能为内容匹配 DLP 策略，请在多个规则，但仅从最严格、 最高优先级规则的策略提示将会显示。例如，从规则阻止访问内容将显示通过策略提示从只发送通知的规则的策略提示。这将阻止用户查看策略提示的级联方式。</span><span class="sxs-lookup"><span data-stu-id="fe872-p125">It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown. For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification. This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="fe872-211">如果限制最严格的规则中的策略提示允许用户替换规则，那么替换此规则还会替换与此内容相匹配的所有其他规则。</span><span class="sxs-lookup"><span data-stu-id="fe872-211">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a><span data-ttu-id="fe872-212">OneDrive for Business 网站或 SharePoint Online 网站上的策略提示</span><span class="sxs-lookup"><span data-stu-id="fe872-212">Policy tips on OneDrive for Business sites and SharePoint Online sites</span></span>

<span data-ttu-id="fe872-213">时 OneDrive for Business 站点或 SharePoint Online 站点上的文档匹配 DLP 策略中的某个规则，该规则使用策略提示策略提示将显示文档的特殊图标：</span><span class="sxs-lookup"><span data-stu-id="fe872-213">When a document on a OneDrive for Business site or SharePoint Online site matches a rule in a DLP policy, and that rule uses policy tips, the policy tips display special icons on the document:</span></span>
  
1. <span data-ttu-id="fe872-214">如果该规则发送有关该文件的通知，则会显示警告图标。</span><span class="sxs-lookup"><span data-stu-id="fe872-214">If the rule sends a notification about the file, the warning icon appears.</span></span>
    
2. <span data-ttu-id="fe872-215">如果该规则阻止访问该文档，则会显示阻止图标。</span><span class="sxs-lookup"><span data-stu-id="fe872-215">If the rule blocks access to the document, the blocked icon appears.</span></span>
    
![在文档中的 OneDrive 帐户策略提示图标](media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
<span data-ttu-id="fe872-217">对文档执行操作，您可以选择一个项目\>选择**信息**![信息窗格中图标](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png)要打开详细信息窗格的页面的右上角中\>**视图策略提示**。</span><span class="sxs-lookup"><span data-stu-id="fe872-217">To take action on a document, you can select an item \> choose **Information**![Information pane icon](media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane \> **View policy tip**.</span></span>
  
<span data-ttu-id="fe872-218">策略提示列出内容，问题并如果用这些选项配置的策略提示，则可以选择**解决**，然后**覆盖**策略提示或**报告**误报。</span><span class="sxs-lookup"><span data-stu-id="fe872-218">The policy tip lists the issues with the content, and if the policy tips are configured with these options, you can choose **Resolve**, and then **Override** the policy tip or **Report** a false positive.</span></span> 
  
![信息窗格中显示策略提示](media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![具有重写选项的策略提示](media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
<span data-ttu-id="fe872-p126">将 DLP 策略同步到网站，并定期以异步方式根据这些策略对内容进行评估，因此，您创建 DLP 策略的时间与开始看到策略提示的时间之间可能出现短暂的延迟。类似延迟还有可能出现在从您解决或替换策略提示到网站的文档上的图标消失的这段时间里。</span><span class="sxs-lookup"><span data-stu-id="fe872-p126">DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips. There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.</span></span>
  
### <a name="default-text-for-policy-tips-on-sites"></a><span data-ttu-id="fe872-223">网站上的策略提示的默认文本</span><span class="sxs-lookup"><span data-stu-id="fe872-223">Default text for policy tips on sites</span></span>

<span data-ttu-id="fe872-p127">默认情况下，策略提示显示在网站上类似于以下项的文本。通知文本针对每个规则单独配置，因此根据匹配的规则，显示的文本有所不同。</span><span class="sxs-lookup"><span data-stu-id="fe872-p127">By default, policy tips display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="fe872-226">**如果 DLP 策略规则也是如此...**</span><span class="sxs-lookup"><span data-stu-id="fe872-226">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="fe872-227">**然后默认策略提示的说明如下...**</span><span class="sxs-lookup"><span data-stu-id="fe872-227">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe872-228">发送通知，但不允许覆盖</span><span class="sxs-lookup"><span data-stu-id="fe872-228">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="fe872-229">此项与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="fe872-229">This item conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="fe872-230">阻止访问，发送通知，并允许重写</span><span class="sxs-lookup"><span data-stu-id="fe872-230">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="fe872-p128">与您的组织中的某个策略，此项冲突。如果您没有解决此冲突，可能会阻止对此文件的访问。</span><span class="sxs-lookup"><span data-stu-id="fe872-p128">This item conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |
|<span data-ttu-id="fe872-233">阻止访问，并向发送通知</span><span class="sxs-lookup"><span data-stu-id="fe872-233">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="fe872-p129">此项与您的组织中的策略相冲突。除非是项目的所有者、最后一次修改内容的用户以及网站集主管理员，否则其他人对此项目的访问将受到阻止。</span><span class="sxs-lookup"><span data-stu-id="fe872-p129">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a><span data-ttu-id="fe872-236">自定义网站上的策略提示文本</span><span class="sxs-lookup"><span data-stu-id="fe872-236">Custom text for policy tips on sites</span></span>

<span data-ttu-id="fe872-p130">您可以自定义电子邮件通知中的单独的策略提示的文本。像电子邮件通知 （请参阅以上部分） 的自定义文本，自定义策略提示文本不接受 HTML 或标记。而是自定义策略提示的文本是仅与 256 个字符限制的纯文本。</span><span class="sxs-lookup"><span data-stu-id="fe872-p130">You can customize the text for policy tips separately from the email notification. Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens. Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a><span data-ttu-id="fe872-240">在 web 上的 Outlook 和 Outlook 2013 及更高版本中的策略提示</span><span class="sxs-lookup"><span data-stu-id="fe872-240">Policy tips in Outlook on the web and Outlook 2013 and later</span></span>

<span data-ttu-id="fe872-p131">在撰写 web 上的 Outlook 和 Outlook 2013 中的新电子邮件和更高版本，您将看到策略提示，如果您要添加在 DLP 策略中，规则相匹配的内容并该规则使用策略提示。正在撰写邮件时，策略提示将出现在邮件收件人，上面的顶部。</span><span class="sxs-lookup"><span data-stu-id="fe872-p131">When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips. The policy tip appears at the top of the message, above the recipients, while the message is being composed.</span></span>
  
![顶部的邮件所构成的策略提示](media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
<span data-ttu-id="fe872-244">策略提示工作是否敏感信息显示在邮件正文、 主题行或甚至邮件附件，如下所示。</span><span class="sxs-lookup"><span data-stu-id="fe872-244">Policy tips work whether the sensitive information appears in the message body, subject line, or even a message attachment as shown here.</span></span>
  
![显示附件冲突与某个 DLP 策略的策略提示](media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
<span data-ttu-id="fe872-246">如果策略提示配置为允许覆盖，则可以选择**显示详细信息** \> **重写**\>输入的业务理由或报告误报\>**重写**。</span><span class="sxs-lookup"><span data-stu-id="fe872-246">If the policy tips are configured to allow override, you can choose **Show Details** \> **Override** \> enter a business justification or report a false positive \> **Override**.</span></span>
  
![展开以显示替代选项的邮件中的策略提示](media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![其中，可以覆盖策略提示的策略提示对话框](media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
<span data-ttu-id="fe872-249">请注意，当您将敏感信息添加到电子邮件，可能有之间添加敏感信息时，显示策略提示的时的延迟。</span><span class="sxs-lookup"><span data-stu-id="fe872-249">Note that when you add sensitive information to an email, there may be latency between when the sensitive information is added and when the policy tip appears.</span></span>

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a><span data-ttu-id="fe872-250">Outlook 2013 及更高版本支持仅某些条件显示策略提示</span><span class="sxs-lookup"><span data-stu-id="fe872-250">Outlook 2013 and later supports showing policy tips for only some conditions</span></span>

<span data-ttu-id="fe872-251">目前，Outlook 2013 及更高版本支持仅对这些条件的显示策略提示：</span><span class="sxs-lookup"><span data-stu-id="fe872-251">Currently, Outlook 2013 and later supports showing policy tips only for these conditions:</span></span>

- <span data-ttu-id="fe872-252">内容包含</span><span class="sxs-lookup"><span data-stu-id="fe872-252">Content contains</span></span>
- <span data-ttu-id="fe872-253">共享内容</span><span class="sxs-lookup"><span data-stu-id="fe872-253">Content is shared</span></span>

<span data-ttu-id="fe872-p132">我们当前正在使用的显示其他条件的策略提示的支持。这些工具包括：</span><span class="sxs-lookup"><span data-stu-id="fe872-p132">We're currently working on support for showing policy tips for additional conditions. These include:</span></span>

- <span data-ttu-id="fe872-256">不会扫描任何电子邮件附件的内容</span><span class="sxs-lookup"><span data-stu-id="fe872-256">Any email attachment's content could not be scanned</span></span>
- <span data-ttu-id="fe872-257">任何电子邮件附件的内容未完成扫描</span><span class="sxs-lookup"><span data-stu-id="fe872-257">Any email attachment's content didn't complete scanning</span></span>
- <span data-ttu-id="fe872-258">附件的文件扩展名</span><span class="sxs-lookup"><span data-stu-id="fe872-258">Attachment file extension is</span></span>
- <span data-ttu-id="fe872-259">附件采用密码保护</span><span class="sxs-lookup"><span data-stu-id="fe872-259">Attachment is password protected</span></span>
- <span data-ttu-id="fe872-260">文档属性</span><span class="sxs-lookup"><span data-stu-id="fe872-260">Document property is</span></span>
- <span data-ttu-id="fe872-261">收件人的域</span><span class="sxs-lookup"><span data-stu-id="fe872-261">Recipient domain is</span></span>
- <span data-ttu-id="fe872-262">发件人的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="fe872-262">Sender IP address is</span></span>

<span data-ttu-id="fe872-p133">请注意，所有这些条件在 Outlook 中，它们将在其中匹配内容和强制执行内容保护措施。但向用户显示策略提示尚不支持。</span><span class="sxs-lookup"><span data-stu-id="fe872-p133">Note that all of these conditions work in Outlook, where they will match content and enforce protective actions on content. But showing policy tips to users is not yet supported.</span></span>
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="fe872-265">在 Exchange 管理中心与 Office 365 安全性的策略提示&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="fe872-265">Policy tips in the Exchange Admin Center vs. the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="fe872-p134">策略提示可使用 DLP 策略的工作和邮件流规则在 Exchange 管理中心，或在 Office 365 安全性中创建的 DLP 策略创建&amp;合规性中心，但不是能同时。这是因为这些策略存储在不同的位置，但只能从单个位置可以绘制策略提示。</span><span class="sxs-lookup"><span data-stu-id="fe872-p134">Policy tips can work either with DLP policies and mail flow rules created in the Exchange Admin Center, or with DLP policies created in the Office 365 Security &amp; Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="fe872-p135">如果您已在 Exchange 管理中心，任何您在 Office 365 安全性中配置的策略提示配置策略提示&amp;合规性中心不会显示给用户在 web 上的 Outlook 和 Outlook 2013 及更高，直到关闭 Exchange 中的提示管理中心。这样可确保您当前的 Exchange 传输规则将继续工作之前您选择切换到 Office 365 安全性&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="fe872-p135">If you've configured policy tips in the Exchange Admin Center, any policy tips that you configure in the Office 365 Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange Admin Center. This ensures that your current Exchange transport rules will continue to work until you choose to switch over to the Office 365 Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="fe872-270">请注意，只能从一个位置，可以绘制策略提示时发送电子邮件通知始终发送，即使您在 Office 365 安全性使用 DLP 策略&amp;合规性中心和 Exchange Admin Center。</span><span class="sxs-lookup"><span data-stu-id="fe872-270">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Office 365 Security &amp; Compliance Center and the Exchange Admin Center.</span></span>
  
### <a name="default-text-for-policy-tips-in-email"></a><span data-ttu-id="fe872-271">电子邮件中的策略提示的默认文本</span><span class="sxs-lookup"><span data-stu-id="fe872-271">Default text for policy tips in email</span></span>

<span data-ttu-id="fe872-272">默认情况下，策略提示显示类似于以下的电子邮件的文本。</span><span class="sxs-lookup"><span data-stu-id="fe872-272">By default, policy tips display text similar to the following for email.</span></span>

|<span data-ttu-id="fe872-273">**如果 DLP 策略规则也是如此...**</span><span class="sxs-lookup"><span data-stu-id="fe872-273">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="fe872-274">**然后默认策略提示的说明如下...**</span><span class="sxs-lookup"><span data-stu-id="fe872-274">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe872-275">发送通知，但不允许覆盖</span><span class="sxs-lookup"><span data-stu-id="fe872-275">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="fe872-276">与您的组织中的某个策略您电子邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="fe872-276">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="fe872-277">阻止访问，发送通知，并允许重写</span><span class="sxs-lookup"><span data-stu-id="fe872-277">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="fe872-278">与您的组织中的某个策略您电子邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="fe872-278">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="fe872-279">阻止访问，并向发送通知</span><span class="sxs-lookup"><span data-stu-id="fe872-279">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="fe872-280">与您的组织中的某个策略您电子邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="fe872-280">Your email conflicts with a policy in your organization.</span></span>  <br/> |
   
## <a name="policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="fe872-281">Excel 2016、PowerPoint 2016 和 Word 2016 中的策略提示</span><span class="sxs-lookup"><span data-stu-id="fe872-281">Policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="fe872-p136">当用户在桌面版本的 Excel 2016、PowerPoint 2016 和 Word 2016 中使用敏感内容时，策略提示可以实时通知用户，告知内容与 DLP 策略之间发生冲突。这要求：</span><span class="sxs-lookup"><span data-stu-id="fe872-p136">When people work with sensitive content in the desktop versions of Excel 2016, PowerPoint 2016, and Word 2016, policy tips can notify them in real time that the content conflicts with a DLP policy. This requires that:</span></span>
  
- <span data-ttu-id="fe872-284">Office 文档存储在 OneDrive for Business 网站或 SharePoint Online 网站上。</span><span class="sxs-lookup"><span data-stu-id="fe872-284">The Office document is stored on a OneDrive for Business site or SharePoint Online site.</span></span>
    
- <span data-ttu-id="fe872-285">包含网站中配置为使用策略提示的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="fe872-285">The site is included in a DLP policy that's configured to use policy tips.</span></span>
    
<span data-ttu-id="fe872-286">这些 Office 2016 桌面程序自动同步直接从 Office 365 的 DLP 策略，然后扫描文档，以确保它们不会与您的 DLP 策略冲突且实时显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="fe872-286">These Office 2016 desktop programs automatically sync DLP policies directly from Office 365, and then scan your documents to ensure that they don't conflict with your DLP policies and display policy tips in real time.</span></span>
  
<span data-ttu-id="fe872-287">根据您在 DLP 策略中对策略提示的配置方式，用户可以选择忽略策略提示、使用或不使用业务理由替换策略或报告误报。</span><span class="sxs-lookup"><span data-stu-id="fe872-287">Depending on how you configure the policy tips in the DLP policy, people can choose to simply ignore the policy tip, override the policy with or without a business justification, or report a false positive.</span></span>
  
<span data-ttu-id="fe872-288">在消息栏上显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="fe872-288">Policy tips appear on the Message Bar.</span></span>
  
![消息栏在 Excel 2016 中显示策略提示](media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
<span data-ttu-id="fe872-290">和策略提示也会显示在 Backstage 视图中 （在**文件**选项卡）。</span><span class="sxs-lookup"><span data-stu-id="fe872-290">And policy tips also appear in the Backstage view (on the **File** tab).</span></span> 
  
![Backstage 在 Excel 2016 中显示策略提示](media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
<span data-ttu-id="fe872-292">如果策略提示使用这些选项配置了 DLP 策略，则可以选择**解决\*\*\*\*覆盖**策略提示或**报告**误报。</span><span class="sxs-lookup"><span data-stu-id="fe872-292">If policy tips in the DLP policy are configured with these options, you can choose **Resolve** to **Override** a policy tip or **Report** a false positive.</span></span> 
  
![Excel 2016 Backstage 中的策略提示选项](media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
<span data-ttu-id="fe872-p137">在每个这些 Office 2016 桌面程序，用户可以选择关闭策略提示。如果关闭，策略提示的简单通知不会显示在消息栏或 Backstage 视图中 （在**文件**选项卡）。但是，仍会显示有关阻止和替代策略提示，并且它们仍将接收电子邮件通知。此外，关闭策略提示不免除已向其应用的任何 DLP 策略的文档。</span><span class="sxs-lookup"><span data-stu-id="fe872-p137">In each of these Office 2016 desktop programs, people can choose to turn off policy tips. If turned off, policy tips that are simple notifications will not appear on the Message Bar or Backstage view (on the **File** tab). However, policy tips about blocking and overriding will still appear, and they will still receive the email notification. In addition, turning off policy tips does not exempt the document from any DLP policies that have been applied to it.</span></span> 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="fe872-298">Excel 2016、PowerPoint 2016 和 Word 2016 中的策略提示的默认文本</span><span class="sxs-lookup"><span data-stu-id="fe872-298">Default text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="fe872-p138">默认情况下，策略提示将在打开文档的消息栏和 Backstage 视图中显示类似于以下的文本。通知文本针对每个规则单独配置，因此根据匹配的规则，显示的文本有所不同。</span><span class="sxs-lookup"><span data-stu-id="fe872-p138">By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="fe872-301">**如果 DLP 策略规则也是如此...**</span><span class="sxs-lookup"><span data-stu-id="fe872-301">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="fe872-302">**然后默认策略提示的说明如下...**</span><span class="sxs-lookup"><span data-stu-id="fe872-302">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe872-303">发送通知，但不允许覆盖</span><span class="sxs-lookup"><span data-stu-id="fe872-303">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="fe872-p139">此文件与您的组织中的某个策略冲突。转到**文件**菜单的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe872-p139">This file conflicts with a policy in your organization. Go to the **File** menu for more information.  </span></span><br/> |
|<span data-ttu-id="fe872-306">阻止访问，发送通知，并允许重写</span><span class="sxs-lookup"><span data-stu-id="fe872-306">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="fe872-p140">此文件与您的组织中的某个策略冲突。如果您没有解决此冲突，可能会阻止对此文件的访问。转到**文件**菜单的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe872-p140">This file conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked. Go to the **File** menu for more information.  </span></span><br/> |
|<span data-ttu-id="fe872-310">阻止访问，并向发送通知</span><span class="sxs-lookup"><span data-stu-id="fe872-310">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="fe872-p141">此文件与您的组织中的某个策略冲突。如果您没有解决此冲突，可能会阻止对此文件的访问。转到**文件**菜单的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe872-p141">This file conflicts with a policy in your organization. If you don't resolve this conflict, access to this file might be blocked. Go to the **File** menu for more information.  </span></span><br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="fe872-314">Excel 2016、 PowerPoint 2016 和 Word 2016 中的自定义文本策略提示</span><span class="sxs-lookup"><span data-stu-id="fe872-314">Custom text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="fe872-p142">您可以自定义电子邮件通知中的单独的策略提示的文本。像电子邮件通知 （请参阅以上部分） 的自定义文本，自定义策略提示文本不接受 HTML 或标记。而是自定义策略提示的文本是仅与 256 个字符限制的纯文本。</span><span class="sxs-lookup"><span data-stu-id="fe872-p142">You can customize the text for policy tips separately from the email notification. Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens. Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="fe872-318">更多信息</span><span class="sxs-lookup"><span data-stu-id="fe872-318">More information</span></span>

- [<span data-ttu-id="fe872-319">数据丢失防护策略概述</span><span class="sxs-lookup"><span data-stu-id="fe872-319">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="fe872-320">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="fe872-320">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="fe872-321">创建 DLP 策略来保护具有 FCI 或其他属性的文档</span><span class="sxs-lookup"><span data-stu-id="fe872-321">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="fe872-322">DLP 策略模板包含的内容</span><span class="sxs-lookup"><span data-stu-id="fe872-322">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="fe872-323">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="fe872-323">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    


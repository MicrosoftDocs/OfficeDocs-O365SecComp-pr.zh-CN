---
title: 使用邮件流规则来查看用户向 Microsoft 报告的内容
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: 您可以创建 Exchange 传输规则以防止用户将电子邮件发送给 Microsoft 进行分析和在您自己的安全过程中使用它们
ms.openlocfilehash: 92acabe133ef154d880104c20aeed7572ea87d41
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002618"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="52048-103">使用邮件流规则来查看用户向 Microsoft 报告的内容</span><span class="sxs-lookup"><span data-stu-id="52048-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="52048-p101">有多种方法可以将 false 的误报和假负邮件向 Microsoft 发送进行分析。作为管理员，您可以使用邮件流规则以查看哪些用户向 Microsoft 报告垃圾邮件、 非垃圾邮件和网络钓鱼诈骗。有关详细信息，请参阅[提交垃圾邮件和非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。相反，您可以创建 Exchange 传输规则以防止用户将电子邮件发送给 Microsoft 进行分析和在您自己的安全过程中使用它们。</span><span class="sxs-lookup"><span data-stu-id="52048-p101">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis. As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Conversely, you can create an Exchange Transport rule to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="52048-108">在开始之前，需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="52048-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="52048-109">估计完成时间：5 分钟</span><span class="sxs-lookup"><span data-stu-id="52048-109">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="52048-p102">您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Messaging 策略和遵从性 permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的"传输规则"条目和[客户端和移动设备权限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)主题中的"Outlook Web App 邮箱策略"条目。</span><span class="sxs-lookup"><span data-stu-id="52048-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook Web App mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span> 
  
<span data-ttu-id="52048-112">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="52048-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="52048-113">使用 EAC 创建查看用户手动垃圾、 网络钓鱼和非垃圾邮件报告的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="52048-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="52048-114">在 EAC 中，导航到**邮件流** \> **规则**。</span><span class="sxs-lookup"><span data-stu-id="52048-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="52048-115">单击![添加图标](media/ITPro-EAC-AddIcon.gif)，然后选择**创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="52048-115">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="52048-116">为该规则指定一个名称，然后单击**更多选项**。</span><span class="sxs-lookup"><span data-stu-id="52048-116">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="52048-117">在**以下情况应用此规则**，选择**收件人**，然后选择**地址中包含以下任何词语**。</span><span class="sxs-lookup"><span data-stu-id="52048-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>
    
5. <span data-ttu-id="52048-118">在**指定词语或短语**框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="52048-118">In the **specify words or phrases** box, do the following:</span></span> 
    - <span data-ttu-id="52048-p103">键入`abuse@messaging.microsoft.com`，然后单击![添加图标](media/ITPro-EAC-AddIcon.gif)，然后键入`junk@office365.microsoft.com`，然后单击![添加图标](media/ITPro-EAC-AddIcon.gif)。这些电子邮件地址用于提交假负邮件给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="52048-p103">Type `abuse@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). These email addresses are used to submit false negative messages to Microsoft.</span></span>
    - <span data-ttu-id="52048-p104">键入`phish@office365.microsoft.com`，然后单击![添加图标](media/ITPro-EAC-AddIcon.gif)。此电子邮件地址用于提交错过网络钓鱼邮件提交给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="52048-p104">Type `phish@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). This email address is used to submit missed phishing messages to Microsoft.</span></span>
    - <span data-ttu-id="52048-p105">键入`false_positive@messaging.microsoft.com`，然后单击![添加图标](media/ITPro-EAC-AddIcon.gif)，然后键入`not_junk@office365.microsoft.com`，然后单击![添加图标](media/ITPro-EAC-AddIcon.gif)。这些电子邮件地址用于提交误报邮件给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="52048-p105">Type `false_positive@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `not_junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). These email addresses are used to submit false positive messages to Microsoft.</span></span>
    - <span data-ttu-id="52048-125">单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="52048-125">Click **ok**.</span></span>
    
6. <span data-ttu-id="52048-126">在下，**执行以下操作**，选择**密件抄送邮件到...** ，然后，然后选择其中您想要的邮箱接收邮件。</span><span class="sxs-lookup"><span data-stu-id="52048-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span> 
    
7. <span data-ttu-id="52048-p106">如果您愿意，您可以选择审核规则、 测试规则，在特定时间段，激活规则和其他选择。我们建议测试一段之前您强制执行规则。请参阅[邮件流规则的过程](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)。</span><span class="sxs-lookup"><span data-stu-id="52048-p106">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span> 
    
8. <span data-ttu-id="52048-p107">单击**保存**按钮保存规则。显示在列表中的规则。</span><span class="sxs-lookup"><span data-stu-id="52048-p107">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="52048-132">创建和强制执行规则后，从您的组织发送到指定的电子邮件地址的任何邮件将复制到指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="52048-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
  


---
title: 使用邮件流规则来查看用户向 Microsoft 报告的内容
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 您可以创建 Exchange 传输规则, 以防止用户将电子邮件发送给 Microsoft 进行分析并在自己的安全过程中使用它们。
ms.openlocfilehash: 5838b05327858cbad3c530674153989c173f4048
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275982"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="5b9ea-103">使用邮件流规则来查看用户向 Microsoft 报告的内容</span><span class="sxs-lookup"><span data-stu-id="5b9ea-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="5b9ea-p101">有多种方法可以将误报和漏报邮件发送给 Microsoft 进行分析。作为管理员, 您可以使用邮件流规则查看用户以垃圾邮件、非垃圾邮件和网络钓鱼诈骗的形式向 Microsoft 报告的内容。有关详细信息, 请参阅[将垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。相反, 您可以创建 Exchange 传输规则, 以防止用户将电子邮件发送给 Microsoft 进行分析并在自己的安全过程中使用它们。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-p101">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis. As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Conversely, you can create an Exchange Transport rule to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5b9ea-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="5b9ea-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="5b9ea-109">估计完成时间：5 分钟</span><span class="sxs-lookup"><span data-stu-id="5b9ea-109">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="5b9ea-p102">您需要先分配权限, 然后才能执行此过程或过程。若要查看所需的权限, 请参阅[邮件策略和合规性权限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的 "传输规则" 条目和 "[客户端和移动设备权限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)" 主题中的 "Outlook on the web 邮箱策略" 条目。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook on the web mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span> 
  
<span data-ttu-id="5b9ea-112">若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="5b9ea-113">使用 EAC 创建邮件流规则, 以查看用户的 "手动垃圾邮件"、"网络钓鱼" 和 "非垃圾邮件" 报告</span><span class="sxs-lookup"><span data-stu-id="5b9ea-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="5b9ea-114">在 EAC 中, 导航到 "**邮件流** \> "**规则**。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="5b9ea-115">单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-115">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="5b9ea-116">为该规则命名, 然后单击 "**更多选项**"。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-116">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="5b9ea-117">在 "在**以下情况应用此规则**" 下, 选择收件人, 然后选择 **"** **地址" 包含这些词语中的任何一个**。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>
    
5. <span data-ttu-id="5b9ea-118">在 "**指定字词或短语**" 框中, 执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="5b9ea-118">In the **specify words or phrases** box, do the following:</span></span> 
    - <span data-ttu-id="5b9ea-p103">键入`abuse@messaging.microsoft.com` , 然后单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后`junk@office365.microsoft.com`键入并单击!["添加](media/ITPro-EAC-AddIcon.gif)图标"。这些电子邮件地址用于向 Microsoft 提交假负邮件。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-p103">Type `abuse@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). These email addresses are used to submit false negative messages to Microsoft.</span></span>
    - <span data-ttu-id="5b9ea-p104">键入`phish@office365.microsoft.com` , 然后单击!["添加](media/ITPro-EAC-AddIcon.gif)图标"。此电子邮件地址用于将错过的网络钓鱼邮件提交给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-p104">Type `phish@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). This email address is used to submit missed phishing messages to Microsoft.</span></span>
    - <span data-ttu-id="5b9ea-p105">键入`false_positive@messaging.microsoft.com` , 然后单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后`not_junk@office365.microsoft.com`键入并单击!["添加](media/ITPro-EAC-AddIcon.gif)图标"。这些电子邮件地址用于向 Microsoft 提交误报邮件。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-p105">Type `false_positive@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `not_junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif). These email addresses are used to submit false positive messages to Microsoft.</span></span>
    - <span data-ttu-id="5b9ea-125">单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-125">Click **ok**.</span></span>
    
6. <span data-ttu-id="5b9ea-126">在 "**执行以下操作**" 下, 选择 **"将邮件密件抄送给 ...** ", 然后选择您想要在其中接收邮件的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span> 
    
7. <span data-ttu-id="5b9ea-p106">如果你愿意, 可以选择审核规则、测试规则、在特定时间段内激活规则, 以及进行其他选择。建议在强制执行规则之前对其进行测试。请参阅[邮件流规则的过程](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-p106">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span> 
    
8. <span data-ttu-id="5b9ea-p107">单击 "**保存**" 按钮以保存该规则。它将显示在规则列表中。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-p107">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="5b9ea-132">创建并强制执行规则后, 从您的组织发送到指定电子邮件地址的任何邮件都将被复制到指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5b9ea-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
  


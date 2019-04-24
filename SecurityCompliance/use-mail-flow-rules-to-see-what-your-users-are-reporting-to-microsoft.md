---
title: 使用邮件流规则来查看用户向 Microsoft 报告的内容
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 您可以创建 Exchange 邮件流规则, 以防止用户将电子邮件发送给 Microsoft 进行分析并在自己的安全过程中使用它们。
ms.openlocfilehash: 3552899c2fb471624234625331492edcd8421da6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264274"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="8c896-103">使用邮件流规则来查看用户向 Microsoft 报告的内容</span><span class="sxs-lookup"><span data-stu-id="8c896-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="8c896-104">您可以使用多种方法将假负和误报邮件发送给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="8c896-104">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis.</span></span> <span data-ttu-id="8c896-105">作为管理员, 您可以使用邮件流规则查看用户以垃圾邮件、非垃圾邮件和网络钓鱼诈骗的形式向 Microsoft 报告的内容。</span><span class="sxs-lookup"><span data-stu-id="8c896-105">As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams.</span></span> <span data-ttu-id="8c896-106">有关详细信息, 请参阅[将垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="8c896-106">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> <span data-ttu-id="8c896-107">相反, 您可以创建 Exchange 邮件流规则 (也称为传输规则), 以阻止用户将电子邮件发送给 Microsoft 进行分析, 并在自己的安全过程中使用它们。</span><span class="sxs-lookup"><span data-stu-id="8c896-107">Conversely, you can create an Exchange mail flow rule (also known as a transport rule) to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8c896-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="8c896-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="8c896-109">估计完成时间：5 分钟</span><span class="sxs-lookup"><span data-stu-id="8c896-109">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="8c896-110">您必须先获得权限，然后才能执行此过程或多个过程。</span><span class="sxs-lookup"><span data-stu-id="8c896-110">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="8c896-111">若要查看所需的权限, 请参阅邮件[策略和合规性权限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的 "邮件流规则" 条目和 "[客户端和移动设备权限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)" 主题中的 "Outlook on the web 邮箱策略" 条目。</span><span class="sxs-lookup"><span data-stu-id="8c896-111">To see what permissions you need, see the "Mail flow rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook on the web mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span> 
  
<span data-ttu-id="8c896-112">若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="8c896-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="8c896-113">使用 EAC 创建邮件流规则, 以查看用户的 "手动垃圾邮件"、"网络钓鱼" 和 "非垃圾邮件" 报告</span><span class="sxs-lookup"><span data-stu-id="8c896-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="8c896-114">在 EAC 中, 导航到 "**邮件流** \> "**规则**。</span><span class="sxs-lookup"><span data-stu-id="8c896-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="8c896-115">单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="8c896-115">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="8c896-116">为该规则命名，然后单击“更多选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8c896-116">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="8c896-117">在“应用此规则的条件”\*\*\*\* 下，选择“收件人”\*\*\*\*，然后选择“地址包含这些词语中的任意词语”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8c896-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>
    
5. <span data-ttu-id="8c896-118">在“指定词语或短语”\*\*\*\* 框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8c896-118">In the **specify words or phrases** box, do the following:</span></span> 
    - <span data-ttu-id="8c896-119">键入`abuse@messaging.microsoft.com` , 然后单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后`junk@office365.microsoft.com`键入并单击!["添加](media/ITPro-EAC-AddIcon.gif)图标"。</span><span class="sxs-lookup"><span data-stu-id="8c896-119">Type `abuse@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="8c896-120">这些电子邮件地址用于向 Microsoft 提交假负邮件。</span><span class="sxs-lookup"><span data-stu-id="8c896-120">These email addresses are used to submit false negative messages to Microsoft.</span></span>
    - <span data-ttu-id="8c896-121">键入`phish@office365.microsoft.com` , 然后单击!["添加](media/ITPro-EAC-AddIcon.gif)图标"。</span><span class="sxs-lookup"><span data-stu-id="8c896-121">Type `phish@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="8c896-122">此电子邮件地址用于将错过的网络钓鱼邮件提交给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="8c896-122">This email address is used to submit missed phishing messages to Microsoft.</span></span>
    - <span data-ttu-id="8c896-123">键入`false_positive@messaging.microsoft.com` , 然后单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后`not_junk@office365.microsoft.com`键入并单击!["添加](media/ITPro-EAC-AddIcon.gif)图标"。</span><span class="sxs-lookup"><span data-stu-id="8c896-123">Type `false_positive@messaging.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then type `not_junk@office365.microsoft.com` and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="8c896-124">这些电子邮件地址用于向 Microsoft 提交误报邮件。</span><span class="sxs-lookup"><span data-stu-id="8c896-124">These email addresses are used to submit false positive messages to Microsoft.</span></span>
    - <span data-ttu-id="8c896-125">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8c896-125">Click **ok**.</span></span>
    
6. <span data-ttu-id="8c896-126">在 "**执行以下操作**" 下, 选择 **"将邮件密件抄送给 ...** ", 然后选择您想要在其中接收邮件的邮箱。</span><span class="sxs-lookup"><span data-stu-id="8c896-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span> 
    
7. <span data-ttu-id="8c896-127">如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。</span><span class="sxs-lookup"><span data-stu-id="8c896-127">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="8c896-128">我们建议首先在一段时间内测试规则，然后再强制应用。</span><span class="sxs-lookup"><span data-stu-id="8c896-128">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="8c896-129">请参阅[邮件流规则的过程](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)。</span><span class="sxs-lookup"><span data-stu-id="8c896-129">See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span> 
    
8. <span data-ttu-id="8c896-130">单击“保存”\*\*\*\* 按钮以保存规则。</span><span class="sxs-lookup"><span data-stu-id="8c896-130">Click the **save** button to save the rule.</span></span> <span data-ttu-id="8c896-131">它会出现在您的规则列表中。</span><span class="sxs-lookup"><span data-stu-id="8c896-131">It appears in your list of rules.</span></span> 
    
<span data-ttu-id="8c896-132">创建并强制执行规则后, 从您的组织发送到指定电子邮件地址的任何邮件都将被复制到指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="8c896-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
  


---
title: Office 365 中的管理员提交, O365 报送, Office 365 垃圾邮件问题, O365 false 负数, 提交在 office 365 中的网络钓鱼, 提交电子邮件以便进行扫描, 在 Office 365 中提交可疑电子邮件, 扫描邮件, 让 Microsoft 扫描网络钓鱼, 使用 microsoft 扫描进行垃圾邮件, 提交电子邮件、提交电子邮件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 了解如何将可疑电子邮件、可疑的网络钓鱼邮件、垃圾邮件和其他可能有害的邮件、Url 和文件从 Office 365 租户提交到 Microsoft 进行扫描。
ms.openlocfilehash: 5a909e8b587e2a1265c1b2afbd5e063d46a04e2c
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230946"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="e046e-103">如何将可疑的垃圾邮件、网络钓鱼、Url 和文件提交到 Microsoft for Office 365 扫描</span><span class="sxs-lookup"><span data-stu-id="e046e-103">How to submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="e046e-104">管理员可以通过使用文件或网络邮件 ID、Url 和文件来通过 Microsoft Office 365 中的扫描来发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e046e-104">Admins can send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span> <span data-ttu-id="e046e-105">"更新的提交" 部分仍包括用户报告的消息, 并可供使用 EOP 的所有客户使用。</span><span class="sxs-lookup"><span data-stu-id="e046e-105">The updated submissions section still includes user reported messages and available to all customers using EOP.</span></span>

<span data-ttu-id="e046e-106">当您提交电子邮件时, 您将获得可能允许传入的电子邮件进入租户的任何策略的信息, 以及对邮件中的任何 Url 和附件的检查。</span><span class="sxs-lookup"><span data-stu-id="e046e-106">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="e046e-107">可能允许邮件的策略包括单个用户的安全发件人列表以及租户级策略 (如 ETR 规则)。</span><span class="sxs-lookup"><span data-stu-id="e046e-107">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as ETR rules.</span></span> 

## <a name="how-to-submit-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="e046e-108">如何将内容提交到 Microsoft for Office 365 扫描</span><span class="sxs-lookup"><span data-stu-id="e046e-108">How to submit content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="e046e-109">若要将内容提交给 Microsoft, 请单击 "提交" 页面左上角的 "**新建提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e046e-109">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="e046e-110">将显示页面右侧的浮出控件, 其中包含用于提交电子邮件、URL 或文件的选项。</span><span class="sxs-lookup"><span data-stu-id="e046e-110">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span> 

### <a name="submit-an-email-to-microsoft"></a><span data-ttu-id="e046e-111">向 Microsoft 提交电子邮件</span><span class="sxs-lookup"><span data-stu-id="e046e-111">Submit an email to Microsoft</span></span>
![电子邮件提交示例](media/submission-flyout-email.PNG)
1. <span data-ttu-id="e046e-113">若要提交电子邮件, 请选择 "**电子邮件**", 并指定电子邮件**网络邮件 ID**或上载电子邮件文件。</span><span class="sxs-lookup"><span data-stu-id="e046e-113">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span> 

2. <span data-ttu-id="e046e-114">指定您想要运行策略检查的收件人。</span><span class="sxs-lookup"><span data-stu-id="e046e-114">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="e046e-115">策略检查将确定电子邮件是否因用户或租户级别策略而绕过扫描。</span><span class="sxs-lookup"><span data-stu-id="e046e-115">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span> 

3. <span data-ttu-id="e046e-116">指定是否应阻止电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e046e-116">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="e046e-117">如果应阻止该电子邮件, 请指定是否应将其阻止为垃圾邮件、网络钓鱼或恶意软件。</span><span class="sxs-lookup"><span data-stu-id="e046e-117">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="e046e-118">如果您不确定可能的类型, 请使用您的最佳 judgement。</span><span class="sxs-lookup"><span data-stu-id="e046e-118">If you are not sure what type it might be, use your best judgement.</span></span>  

* <span data-ttu-id="e046e-119">如果由于提交策略而绕过筛选器, 你将看到有关该策略的信息。</span><span class="sxs-lookup"><span data-stu-id="e046e-119">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

* <span data-ttu-id="e046e-120">如果筛选器由于一个或多个策略而被绕过, 扫描将在几分钟内完成。</span><span class="sxs-lookup"><span data-stu-id="e046e-120">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="e046e-121">您将通过单击状态链接来查看有关提交的其他信息。</span><span class="sxs-lookup"><span data-stu-id="e046e-121">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="e046e-122">这包括策略检查结果和重新扫描判定结果。</span><span class="sxs-lookup"><span data-stu-id="e046e-122">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="e046e-123">注意这不会再次通过 Office 365 ATP 完全筛选堆栈运行电子邮件, 但会根据邮件、URL 或文件的某些属性运行部分重新扫描。</span><span class="sxs-lookup"><span data-stu-id="e046e-123">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span> 

4. <span data-ttu-id="e046e-124">单击 "**提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e046e-124">Click the **Submit** button.</span></span>

### <a name="submit-a-url-to-microsoft"></a><span data-ttu-id="e046e-125">向 Microsoft 提交 URL</span><span class="sxs-lookup"><span data-stu-id="e046e-125">Submit a URL to Microsoft</span></span>
![电子邮件提交示例](media/submission-url-flyout.png)
1. <span data-ttu-id="e046e-127">若要提交 URL, 请从浮出控件中选择**url** 。</span><span class="sxs-lookup"><span data-stu-id="e046e-127">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="e046e-128">键入完整 URL, 包括协议 (**https://**)。</span><span class="sxs-lookup"><span data-stu-id="e046e-128">Type in the full URL including the protocol (**https://**).</span></span> 

* <span data-ttu-id="e046e-129">如果您选择了 "**应该已经过筛选**", 请指定 URL 是否为网络钓鱼或恶意软件。</span><span class="sxs-lookup"><span data-stu-id="e046e-129">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="e046e-130">单击 "**提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e046e-130">Click the **Submit** button.</span></span> 


### <a name="submit-a-file-to-microsoft"></a><span data-ttu-id="e046e-131">将文件提交给 Microsoft</span><span class="sxs-lookup"><span data-stu-id="e046e-131">Submit a file to Microsoft</span></span>
![电子邮件提交示例](media/submission-file-flyout.PNG)
1. <span data-ttu-id="e046e-133">若要提交文件, 请从浮出控件中选择**文件**, 并上载要扫描的文件。</span><span class="sxs-lookup"><span data-stu-id="e046e-133">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span> 

2. <span data-ttu-id="e046e-134">单击 "**提交**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e046e-134">Click the **Submit** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e046e-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="e046e-135">Related topics</span></span>

[<span data-ttu-id="e046e-136">Office 365 高级威胁防护计划2</span><span class="sxs-lookup"><span data-stu-id="e046e-136">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="e046e-137">防御 Office 365 中的威胁</span><span class="sxs-lookup"><span data-stu-id="e046e-137">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="e046e-138">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="e046e-138">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  


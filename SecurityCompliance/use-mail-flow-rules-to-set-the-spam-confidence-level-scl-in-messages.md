---
title: 使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
description: 您可以创建传输规则来设置电子邮件的垃圾邮件可信度 (SCL)。SCL 是判断某个邮件在多大程度上是垃圾邮件的衡量手段。"垃圾邮件"是未经请求的（并且通常是不必要的）电子邮件。根据 SCL 评级的不同，该服务对邮件采取不同的操作。例如，您可能想要使从您组织内部人员发送的邮件规避垃圾邮件内容筛选，因为您相信从内部同事发送的邮件并非垃圾邮件。使用传输规则设置邮件的 SCL 值可提高您处理垃圾邮件的控制能力。
ms.openlocfilehash: 7abd0d1881374b1f2a4bd32ee480445f7683d1b3
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002891"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="e4a56-108">使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)</span><span class="sxs-lookup"><span data-stu-id="e4a56-108">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="e4a56-p102">您可以创建传输规则来设置电子邮件的垃圾邮件可信度 (SCL)。SCL 是判断某个邮件在多大程度上是垃圾邮件的衡量手段。"垃圾邮件"是未经请求的（并且通常是不必要的）电子邮件。根据 SCL 评级的不同，该服务对邮件采取不同的操作。例如，您可能想要使从您组织内部人员发送的邮件规避垃圾邮件内容筛选，因为您相信从内部同事发送的邮件并非垃圾邮件。使用传输规则设置邮件的 SCL 值可提高您处理垃圾邮件的控制能力。</span><span class="sxs-lookup"><span data-stu-id="e4a56-p102">You can create a transport rule that sets the spam confidence level (SCL) of an email message. The SCL is a measure of how likely a message is to be spam. Spam is unsolicited (and typically unwanted) email messages. The service takes different action on a message depending on its SCL rating. For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam. Using transport rules to set the SCL value of a message gives you increased control in handling spam.</span></span> 
  
 <span data-ttu-id="e4a56-115">**在开始之前，您需要知道什么？**</span><span class="sxs-lookup"><span data-stu-id="e4a56-115">**What do you need to know before you begin?**</span></span>
  
- <span data-ttu-id="e4a56-116">估计完成该过程的时间：10 分钟。</span><span class="sxs-lookup"><span data-stu-id="e4a56-116">Estimated time to complete this procedure: 10 minutes.</span></span>
    
- <span data-ttu-id="e4a56-p103">您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)或[功能在 EOP 中的权限](eop/feature-permissions-in-eop.md)中的"传输规则"条目。</span><span class="sxs-lookup"><span data-stu-id="e4a56-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) or [Feature permissions in EOP](eop/feature-permissions-in-eop.md).</span></span> 
    
- <span data-ttu-id="e4a56-119">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="e4a56-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
### <a name="to-create-a-transport-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="e4a56-120">创建设置邮件的 SCL 的传输规则</span><span class="sxs-lookup"><span data-stu-id="e4a56-120">To create a transport rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="e4a56-121">在 Exchange 管理员中心 (EAC) 中，选择**邮件流** \> **规则**。</span><span class="sxs-lookup"><span data-stu-id="e4a56-121">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="e4a56-122">选择**新建**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后选择**创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="e4a56-122">Choose **New**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="e4a56-123">指定规则名称。</span><span class="sxs-lookup"><span data-stu-id="e4a56-123">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="e4a56-124">选择**更多选项**，并在**以下情况应用此规则**，指定将触发的操作，您将设置为此规则 （这是设置 SCL 值） 的条件。</span><span class="sxs-lookup"><span data-stu-id="e4a56-124">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>
    
    <span data-ttu-id="e4a56-125">例如，您可以设置**发件人** \> **是内部/外部**，然后**选择发件人位置**对话框中，在选择**组织内部**，并选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="e4a56-125">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span></br>
    <span data-ttu-id="e4a56-126">![选择发件人位置](media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="e4a56-126">![Select sender location](media/EOP-ETR-SetSCL-1.jpg)</span></span>
  
5. <span data-ttu-id="e4a56-127">在**执行以下操作**，下选择**修改邮件属性** \> **将垃圾邮件可信度 (SCL) 设置**。</span><span class="sxs-lookup"><span data-stu-id="e4a56-127">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
  
6. <span data-ttu-id="e4a56-128">**指定 SCL**对话框中，选择下列值之一，然后选择**确定**:</span><span class="sxs-lookup"><span data-stu-id="e4a56-128">In the **specify SCL** dialog box, select one of the following values, and choose **ok**:</span></span>
    
  - <span data-ttu-id="e4a56-129">**绕过垃圾邮件筛选**-的 SCL 为-1，这意味着内容筛选不会执行此设置。</span><span class="sxs-lookup"><span data-stu-id="e4a56-129">**Bypass spam filtering** - This sets the SCL to -1, which means that content filtering won't be performed.</span></span> 
    
  - <span data-ttu-id="e4a56-130">**0-4** -将 SCL 设置为下列值之一时，邮件都将传递到其他处理的内容筛选器。</span><span class="sxs-lookup"><span data-stu-id="e4a56-130">**0-4** - When you set the SCL to one of these values, the message will be passed along to the content filter for additional processing.</span></span> 
    
  - <span data-ttu-id="e4a56-p104">将应用**5、 6** -当您将 SCL 设置为其中一个值，适用的内容筛选器策略中指定的**垃圾邮件**的操作。默认情况下操作是将邮件发送到收件人的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4a56-p104">**5, 6** - When you set the SCL to one of these values, the action specified for **Spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
  - <span data-ttu-id="e4a56-p105">将应用**7-9** -当您将 SCL 设置为其中一个值，适用的内容筛选器策略中指定的**高可信度垃圾邮件**的操作。默认情况下操作是将邮件发送到收件人的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4a56-p105">**7-9** - When you set the SCL to one of these values, the action specified for **High confidence spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
    <span data-ttu-id="e4a56-p106">有关如何配置内容筛选器策略的详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="e4a56-p106">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
7. <span data-ttu-id="e4a56-137">指定该规则的其他属性，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="e4a56-137">Specify additional properties for the rule, and choose **save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e4a56-138">有关可以为此规则选择或指定的其他属性的详细信息，请参阅[Use the EAC to create a transport rule](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC)。</span><span class="sxs-lookup"><span data-stu-id="e4a56-138">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create a transport rule](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC).</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e4a56-139">您如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="e4a56-139">How do you know this worked?</span></span>

<span data-ttu-id="e4a56-p107">若要验证此过程正常工作，向您的组织内的某人发送一封电子邮件，并验证对邮件执行的操作按预期方式。例如，如果**将垃圾邮件可信度 (SCL) 设置**为**绕过垃圾邮件筛选**，然后邮件应发送给指定的收件人的收件箱。但是，如果**将垃圾邮件可信度 (SCL) 设置**为**9**，以及您适用的内容筛选器策略的**高可信度垃圾邮件**操作是将邮件移动到垃圾邮件文件夹，然后邮件应发送到指定收件人的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="e4a56-p107">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected. For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox. However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span> 
  


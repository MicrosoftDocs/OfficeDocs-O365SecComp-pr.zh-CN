---
title: 使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online Protection 中设置邮件的 SCL。
ms.openlocfilehash: e07b90ab1ab004c39ef36b2aa744ca87120c11fe
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692741"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="c8dfb-103">使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)</span><span class="sxs-lookup"><span data-stu-id="c8dfb-103">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="c8dfb-104">您可以创建邮件流规则 (也称为传输规则), 以设置电子邮件的垃圾邮件可信度 (SCL)。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-104">You can create a mail flow rule (also known as a transport rule) that sets the spam confidence level (SCL) of an email message.</span></span> <span data-ttu-id="c8dfb-105">SCL 是判断某个邮件在多大程度上是垃圾邮件的衡量手段。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-105">The SCL is a measure of how likely a message is to be spam.</span></span> <span data-ttu-id="c8dfb-106">"垃圾邮件"是未经请求的（并且通常是不必要的）电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-106">Spam is unsolicited (and typically unwanted) email messages.</span></span> <span data-ttu-id="c8dfb-107">根据 SCL 评级的不同，该服务对邮件采取不同的操作。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-107">The service takes different action on a message depending on its SCL rating.</span></span> <span data-ttu-id="c8dfb-108">例如，您可能想要使从您组织内部人员发送的邮件规避垃圾邮件内容筛选，因为您相信从内部同事发送的邮件并非垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-108">For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam.</span></span> <span data-ttu-id="c8dfb-109">使用邮件流规则设置邮件的 SCL 值为您提供了对处理垃圾邮件的更多控制。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-109">Using mail flow rules to set the SCL value of a message gives you increased control in handling spam.</span></span> 
  
 <span data-ttu-id="c8dfb-110">**在开始之前，您需要知道什么？**</span><span class="sxs-lookup"><span data-stu-id="c8dfb-110">**What do you need to know before you begin?**</span></span>
  
- <span data-ttu-id="c8dfb-111">估计完成该过程的时间：10 分钟。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-111">Estimated time to complete this procedure: 10 minutes.</span></span>
    
- <span data-ttu-id="c8dfb-112">您必须先获得权限，然后才能执行此过程或多个过程。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-112">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="c8dfb-113">若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)或 EOP 中的[功能权限](eop/feature-permissions-in-eop.md)中的 "邮件流规则" 条目。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-113">To see what permissions you need, see the "Mail flow rules" entry in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) or [Feature permissions in EOP](eop/feature-permissions-in-eop.md).</span></span> 
    
- <span data-ttu-id="c8dfb-114">若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="c8dfb-115">创建设置邮件 SCL 的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="c8dfb-115">To create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="c8dfb-116">在 Exchange 管理中心 (EAC) 中, 选择 "**邮件流** \> **规则**"。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-116">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="c8dfb-117">选择 "**新建**!["](media/ITPro-EAC-AddIcon.gif)"添加" 图标, 然后选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-117">Choose **New**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="c8dfb-118">指定规则名称。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-118">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="c8dfb-119">选择 "**更多选项**", 然后在 "在**以下情况应用此规则**" 下, 指定将触发要为此规则设置的操作 (即设置 SCL 值) 的条件。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-119">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>
    
    <span data-ttu-id="c8dfb-120">例如, 您可以将**发件人** \> **设置为 "内部/外部**", 然后在 "**选择发件人位置**" 对话框中, 选择**组织内部**, 然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-120">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span><br/>
    <span data-ttu-id="c8dfb-121">![选择发件人位置](media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="c8dfb-121">![Select sender location](media/EOP-ETR-SetSCL-1.jpg)</span></span>
  
5. <span data-ttu-id="c8dfb-122">在 "**执行以下操作**" 下, 选择 "**修改邮件属性** \> **" "设置垃圾邮件可信度 (SCL)"**。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-122">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
  
6. <span data-ttu-id="c8dfb-123">在“指定 SCL”\*\*\*\* 对话框中，选择以下值之一，然后选择“确定”\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="c8dfb-123">In the **specify SCL** dialog box, select one of the following values, and choose **ok**:</span></span>
    
  - <span data-ttu-id="c8dfb-124">**绕过垃圾邮件筛选**-这会将 SCL 设置为-1, 这意味着不会执行内容筛选。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-124">**Bypass spam filtering** - This sets the SCL to -1, which means that content filtering won't be performed.</span></span> 
    
  - <span data-ttu-id="c8dfb-125">**0-4** -当您将 SCL 设置为这些值之一时, 邮件将被传递到内容筛选器进行其他处理。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-125">**0-4** - When you set the SCL to one of these values, the message will be passed along to the content filter for additional processing.</span></span> 
    
  - <span data-ttu-id="c8dfb-126">**5, 6** -当您将 SCL 设置为这些值之一时, 将应用在适用的内容筛选器策略中为**垃圾邮件**指定的操作。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-126">**5, 6** - When you set the SCL to one of these values, the action specified for **Spam** in the applicable content filter policies will be applied.</span></span> <span data-ttu-id="c8dfb-127">默认情况下，该操作是将邮件发送至收件人的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-127">By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
  - <span data-ttu-id="c8dfb-128">**7-9** -当您将 SCL 设置为这些值之一时, 将应用为适用的内容筛选器策略中的**高可信度垃圾邮件**指定的操作。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-128">**7-9** - When you set the SCL to one of these values, the action specified for **High confidence spam** in the applicable content filter policies will be applied.</span></span> <span data-ttu-id="c8dfb-129">默认情况下，该操作是将邮件发送至收件人的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-129">By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
    <span data-ttu-id="c8dfb-p105">有关如何配置内容筛选器策略的详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-p105">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
7. <span data-ttu-id="c8dfb-132">指定该规则的其他属性，并选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-132">Specify additional properties for the rule, and choose **save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c8dfb-133">有关可以为此规则选择或指定的其他属性的详细信息, 请参阅[使用 EAC 创建邮件流规则](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-133">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c8dfb-134">您如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="c8dfb-134">How do you know this worked?</span></span>

<span data-ttu-id="c8dfb-135">要验证此步骤是否能正常工作，请发送电子邮件至组织中的某位同事，并验证是否对该邮件执行预期的操作。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-135">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="c8dfb-136">例如, 如果**将垃圾邮件可信度 (SCL) 设置**为 "**绕过垃圾邮件筛选**", 则应将邮件发送到指定收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-136">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="c8dfb-137">但是, 如果**将垃圾邮件可信度 (SCL) 设置**为**9**, 并且适用的内容筛选器策略的**高可信度垃圾邮件**操作是将邮件移动到 "垃圾邮件" 文件夹, 则应将邮件发送到指定的收件人的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c8dfb-137">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span> 
  


---
title: 在 Exchange Online 中配置最终用户垃圾邮件通知
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
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: 您可以为适用于域的默认公司范围的垃圾邮件筛选器策略或自定义垃圾邮件筛选器策略配置最终用户垃圾邮件通知。
ms.openlocfilehash: ea2994a3f772b407a35be2d64e8afcc639d24f31
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214492"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="81e98-103">在 Exchange Online 中配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="81e98-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81e98-p101">本主题适用于正在保护云托管邮箱的 Exchange Online 客户。Exchange Online Protection (EOP) 保护本地邮箱的独立客户应阅读以下主题:[在 EOP 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="81e98-p101">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes. Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="81e98-p102">您可以为适用于域的默认公司范围的垃圾邮件筛选器策略或自定义垃圾邮件筛选器策略配置最终用户垃圾邮件通知。启用最终用户垃圾邮件通知可让最终用户自行管理自己的垃圾邮件隔离邮件。最终用户垃圾邮件通知不能与应用于用户或组的策略一起使用, 也不能用于有例外的策略。</span><span class="sxs-lookup"><span data-stu-id="81e98-p102">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="81e98-p103">最终用户垃圾邮件通知包含最终用户在您所配置的时间段（您可以指定一个介于 1 到 15 天之间的值）内收到的所有垃圾邮件隔离邮件的列表。您还可以配置通知邮件的编写语言。</span><span class="sxs-lookup"><span data-stu-id="81e98-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="81e98-111">收到通知邮件后, 最终用户可以从以下选项中进行选择:</span><span class="sxs-lookup"><span data-stu-id="81e98-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="81e98-112">如果要在执行操作之前预览内容或标题, 请**预览**邮件。</span><span class="sxs-lookup"><span data-stu-id="81e98-112">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

<span data-ttu-id="81e98-113">如果要在执行操作之前查看设备上的邮件和附件 (如果有), 请**下载**邮件。</span><span class="sxs-lookup"><span data-stu-id="81e98-113">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

<span data-ttu-id="81e98-114">如果邮件不是垃圾邮件, 并且您希望 Office 365 将邮件发送到您的邮箱, 则**释放**。</span><span class="sxs-lookup"><span data-stu-id="81e98-114">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="81e98-p104">**发布 &** 如果邮件不是垃圾邮件, 并且您希望 Office 365 将发件人添加到安全发件人和收件人列表中, 以供将来的电子邮件。请注意, 您的管理员可能有其他组织范围的允许/阻止配置替代安全发件人列表。</span><span class="sxs-lookup"><span data-stu-id="81e98-p104">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails. Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

<span data-ttu-id="81e98-117">**发布 & 报告**, 如果邮件不是垃圾邮件, 并且您想要将邮件发送到您的邮箱并将其报告给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="81e98-117">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

<span data-ttu-id="81e98-118">如果您希望 Office 365 将发件人添加到阻止发件人列表, 则**阻止**。</span><span class="sxs-lookup"><span data-stu-id="81e98-118">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="81e98-119">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="81e98-119">What do you need to know before you begin?</span></span>

<span data-ttu-id="81e98-120">估计完成时间：2 分钟</span><span class="sxs-lookup"><span data-stu-id="81e98-120">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="81e98-p105">您需要先分配权限, 然后才能执行此过程或过程。若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的 "反垃圾邮件" 条目。</span><span class="sxs-lookup"><span data-stu-id="81e98-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="81e98-123">若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="81e98-123">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="81e98-124">使用 EAC 配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="81e98-124">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="81e98-125">在 Exchange 管理中心 (EAC) 中, 导航到 "**保护** \> **垃圾邮件筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="81e98-125">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="81e98-126">选择要为其启用最终用户垃圾邮件通知的垃圾邮件筛选器策略 (默认情况下禁用)。</span><span class="sxs-lookup"><span data-stu-id="81e98-126">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="81e98-127">在右侧窗格中显示策略的摘要信息的位置, 单击 "**配置最终用户垃圾邮件通知**" 链接。</span><span class="sxs-lookup"><span data-stu-id="81e98-127">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="81e98-128">在随后出现的对话框中，您可以配置以下选项：</span><span class="sxs-lookup"><span data-stu-id="81e98-128">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="81e98-p106">**启用最终用户垃圾邮件通知**选中此复选框, 以便为此策略启用最终用户垃圾邮件通知。(相反, 如果启用此策略, 则可以清除此复选框, 以便为此策略禁用最终用户垃圾邮件通知。)</span><span class="sxs-lookup"><span data-stu-id="81e98-p106">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="81e98-p107">**每隔 (天) 发送最终用户垃圾邮件通知**指定发送最终用户垃圾邮件通知的频率。默认值为3天。可以指定1到15天。例如, 如果指定7天, 则通知将在过去7天内发送到垃圾邮件隔离的所有邮件的列表中包含为该用户预定的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="81e98-p107">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="81e98-135">**通知语言**使用下拉列表, 选择为此策略编写最终用户垃圾邮件通知所使用的语言。</span><span class="sxs-lookup"><span data-stu-id="81e98-135">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="81e98-p108">单击 "**保存**"。在右侧窗格中将显示垃圾邮件筛选器策略设置的摘要, 包括您的最终用户垃圾邮件通知设置。</span><span class="sxs-lookup"><span data-stu-id="81e98-p108">Click **save**. A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="81e98-p109">最终用户垃圾邮件通知将仅适用于启用的垃圾邮件筛选器策略。> 最终用户垃圾邮件通知每天仅发送一次。无法保证任何特定客户的通知传递时间, 并且不可配置。</span><span class="sxs-lookup"><span data-stu-id="81e98-p109">End-user spam notifications will only be functional for spam filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="81e98-p110">**提示:** 如果要在完全实现最终用户垃圾邮件通知之前将其发送给一组有限的用户, 请创建自定义垃圾邮件筛选器策略, 为用户驻留的域启用最终用户垃圾邮件通知。然后, 在 EAC 中的 "**邮件流\>规则**" 下, 创建一个传输规则以阻止来自 quarantine@messaging.microsoft.com (发送通知的电子邮件地址) 的邮件, 其中包含要接收通知的用户的例外。下面的图像是一个为来自 domain Contoso.com 的两个用户 (SaraD 和 AlexD) 创建异常的示例:</span><span class="sxs-lookup"><span data-stu-id="81e98-p110">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a transport rule to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![测试最终用户垃圾邮件通知的传输规则](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="81e98-145">详细信息</span><span class="sxs-lookup"><span data-stu-id="81e98-145">For more information</span></span>

[<span data-ttu-id="81e98-146">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="81e98-146">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  

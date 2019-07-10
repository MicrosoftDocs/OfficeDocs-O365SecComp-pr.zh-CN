---
title: 在 Exchange Online 中配置最终用户垃圾邮件通知
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: 您可以为适用于域的默认公司范围的垃圾邮件筛选器策略或自定义垃圾邮件筛选器策略配置最终用户垃圾邮件通知。
ms.openlocfilehash: ce63fae7749f716b7fdd00c72b207ba5b57a8d65
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600188"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="75869-103">在 Exchange Online 中配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="75869-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75869-104">该主题适用于希望保护在云中托管的邮箱的 Exchange Online 客户。</span><span class="sxs-lookup"><span data-stu-id="75869-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="75869-105">Exchange Online Protection (EOP) 保护本地邮箱的独立客户应阅读以下主题:[在 EOP 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="75869-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="75869-106">您可以为适用于域的默认公司范围的垃圾邮件筛选器策略或自定义垃圾邮件筛选器策略配置最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="75869-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies that are applied to domains.</span></span> <span data-ttu-id="75869-107">启用最终用户垃圾邮件通知邮件可以使您的最终用户自己管理自己的垃圾邮件隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="75869-107">Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages.</span></span> <span data-ttu-id="75869-108">最终用户垃圾邮件通知无法与应用于用户、组的策略或有例外情况的策略一起使用。</span><span class="sxs-lookup"><span data-stu-id="75869-108">End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="75869-p103">最终用户垃圾邮件通知包含最终用户在您所配置的时间段（您可以指定一个介于 1 到 15 天之间的值）内收到的所有垃圾邮件隔离邮件的列表。您还可以配置通知邮件的编写语言。</span><span class="sxs-lookup"><span data-stu-id="75869-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="75869-111">收到通知邮件后, 最终用户可以从以下选项中进行选择:</span><span class="sxs-lookup"><span data-stu-id="75869-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="75869-112">如果要在执行操作之前预览内容或标题, 请**预览**邮件。</span><span class="sxs-lookup"><span data-stu-id="75869-112">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

<span data-ttu-id="75869-113">如果要在执行操作之前查看设备上的邮件和附件 (如果有), 请**下载**邮件。</span><span class="sxs-lookup"><span data-stu-id="75869-113">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

<span data-ttu-id="75869-114">如果邮件不是垃圾邮件, 并且您希望 Office 365 将邮件发送到您的邮箱, 则**释放**。</span><span class="sxs-lookup"><span data-stu-id="75869-114">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="75869-115">如果邮件不是垃圾邮件, 并且您希望 Office 365 将发件人添加到安全发件人和收件人列表中, 请**释放 & 允许发件人**列表中的其他电子邮件。</span><span class="sxs-lookup"><span data-stu-id="75869-115">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails.</span></span> <span data-ttu-id="75869-116">请注意, 您的管理员可能有其他组织范围的允许/阻止配置替代安全发件人列表。</span><span class="sxs-lookup"><span data-stu-id="75869-116">Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

<span data-ttu-id="75869-117">如果邮件不是垃圾邮件, 并且您想要将邮件发送到您的邮箱并将其报告给 Microsoft 进行分析, 请**释放 & 报告**。</span><span class="sxs-lookup"><span data-stu-id="75869-117">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

<span data-ttu-id="75869-118">如果您希望 Office 365 将发件人添加到阻止发件人列表, 则**阻止**。</span><span class="sxs-lookup"><span data-stu-id="75869-118">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="75869-119">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="75869-119">What do you need to know before you begin?</span></span>

<span data-ttu-id="75869-120">估计完成时间：2 分钟</span><span class="sxs-lookup"><span data-stu-id="75869-120">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="75869-121">您必须先获得权限，然后才能执行此过程或多个过程。</span><span class="sxs-lookup"><span data-stu-id="75869-121">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="75869-122">若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的 "反垃圾邮件" 条目。</span><span class="sxs-lookup"><span data-stu-id="75869-122">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="75869-123">若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="75869-123">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="75869-124">使用 EAC 配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="75869-124">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="75869-125">在 Exchange 管理中心 (EAC) 中, 导航到 "**保护** \> **垃圾邮件筛选器**"。</span><span class="sxs-lookup"><span data-stu-id="75869-125">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="75869-126">选择要为其启用最终用户垃圾邮件通知的垃圾邮件筛选器策略 (默认情况下禁用)。</span><span class="sxs-lookup"><span data-stu-id="75869-126">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="75869-127">在显示您的策略摘要信息的右窗格中，单击“配置最终用户垃圾邮件通知”\*\*\*\* 链接。</span><span class="sxs-lookup"><span data-stu-id="75869-127">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="75869-128">在随后出现的对话框中，您可以配置以下选项：</span><span class="sxs-lookup"><span data-stu-id="75869-128">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="75869-129">**启用最终用户垃圾邮件通知**选中此复选框, 以便为此策略启用最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="75869-129">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy.</span></span> <span data-ttu-id="75869-130">）</span><span class="sxs-lookup"><span data-stu-id="75869-130">(Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="75869-131">**每隔 (天) 发送最终用户垃圾邮件通知**指定发送最终用户垃圾邮件通知的频率。</span><span class="sxs-lookup"><span data-stu-id="75869-131">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications.</span></span> <span data-ttu-id="75869-132">默认值为 3 天。</span><span class="sxs-lookup"><span data-stu-id="75869-132">The default is 3 days.</span></span> <span data-ttu-id="75869-133">您可以指定一个介于 1 到 15 天之间的值。</span><span class="sxs-lookup"><span data-stu-id="75869-133">You can specify between 1 and 15 days.</span></span> <span data-ttu-id="75869-134">例如，如果您指定 7 天，则该通知将包括在过去 7 天内预期发送给该用户但实际发送到垃圾邮件隔离邮箱的所有邮件列表。</span><span class="sxs-lookup"><span data-stu-id="75869-134">If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="75869-135">**通知语言**使用下拉列表, 选择为此策略编写最终用户垃圾邮件通知所使用的语言。</span><span class="sxs-lookup"><span data-stu-id="75869-135">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="75869-136">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="75869-136">Click **save**.</span></span> <span data-ttu-id="75869-137">在右侧窗格中将显示垃圾邮件筛选器策略设置的摘要, 包括您的最终用户垃圾邮件通知设置。</span><span class="sxs-lookup"><span data-stu-id="75869-137">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="75869-138">最终用户垃圾邮件通知将仅适用于启用的垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="75869-138">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="75869-139">>  每天只发送一次最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="75869-139">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="75869-140">无法保证和配置任何特定客户的通知发送时间。</span><span class="sxs-lookup"><span data-stu-id="75869-140">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="75869-141">**提示:** 如果要在完全实现最终用户垃圾邮件通知之前将其发送给一组有限的用户, 请创建自定义垃圾邮件筛选器策略, 为用户驻留的域启用最终用户垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="75869-141">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="75869-142">然后, 在 EAC 中的 "**邮件流\>规则**" 下, 创建邮件流规则 (也称为 "传输规则"), 以阻止来自 quarantine@messaging.microsoft.com 的邮件 (发送通知的电子邮件地址), 并对所需的用户例外。以接收通知。</span><span class="sxs-lookup"><span data-stu-id="75869-142">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="75869-143">下图是为 Contoso.com 域中的两个用户（SaraD 和 AlexD）创建一个异常的示例：</span><span class="sxs-lookup"><span data-stu-id="75869-143">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![测试最终用户垃圾邮件通知的传输规则](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="75869-145">详细信息</span><span class="sxs-lookup"><span data-stu-id="75869-145">For more information</span></span>

[<span data-ttu-id="75869-146">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="75869-146">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  

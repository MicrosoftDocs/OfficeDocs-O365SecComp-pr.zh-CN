---
title: Exchange Online 中配置最终用户垃圾邮件通知
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
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
description: 您可以针对默认的公司范围内内容筛选器策略或应用于域的自定义内容筛选器策略配置最终用户垃圾邮件通知。
ms.openlocfilehash: e29cc850b7f91ed4ec963a8e52e40a0044fa7f6c
ms.sourcegitcommit: 234a22c61859133ed5e7988a9551a569781518a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23875804"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="e9e87-103">Exchange Online 中配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="e9e87-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9e87-p101">本主题适用于 Exchange Online 客户正在保护云托管的邮箱。正在保护内部部署邮箱的 Exchange Online Protection (EOP) 独立客户应改为阅读以下主题：[在 EOP 中的配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="e9e87-p101">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes. Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="e9e87-p102">您可以针对默认的公司范围内内容筛选器策略或应用于域的自定义内容筛选器策略配置最终用户垃圾邮件通知。启用最终用户垃圾邮件通知邮件可以使您的最终用户自己管理自己的垃圾邮件隔离邮件。最终用户垃圾邮件通知无法与应用于用户、组的策略或有例外情况的策略一起使用。</span><span class="sxs-lookup"><span data-stu-id="e9e87-p102">You can configure end-user spam notifications for the default company-wide content filter policy or for custom content filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="e9e87-p103">最终用户垃圾邮件通知包含最终用户在您所配置的时间段（您可以指定一个介于 1 到 15 天之间的值）内收到的所有垃圾邮件隔离邮件的列表。您还可以配置通知邮件的编写语言。</span><span class="sxs-lookup"><span data-stu-id="e9e87-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="e9e87-111">在收到一封通知邮件，最终用户可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="e9e87-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="e9e87-112">**预览**邮件如果您想要预览的内容或之前采取操作的标头。</span><span class="sxs-lookup"><span data-stu-id="e9e87-112">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

<span data-ttu-id="e9e87-113">**下载**如果您想要在您的设备之前采取操作时，（如果有） 查看消息和附件的邮件。</span><span class="sxs-lookup"><span data-stu-id="e9e87-113">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

<span data-ttu-id="e9e87-114">**版本**如果邮件不是垃圾邮件，并且您希望 Office 365 邮件发送给您的邮箱。</span><span class="sxs-lookup"><span data-stu-id="e9e87-114">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="e9e87-p104">**发行版和允许的发件人**如果邮件不是垃圾邮件，并且您希望 Office 365 将发件人添加到您的安全发件人和将来的电子邮件的收件人列表。请记住，您的管理员可能必须覆盖安全发件人列表的其他组织范围允许/阻止配置。</span><span class="sxs-lookup"><span data-stu-id="e9e87-p104">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails. Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

<span data-ttu-id="e9e87-117">**发布和报告**、 如果邮件不是垃圾邮件和您想要将邮件发送到您的邮箱并将其报告给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="e9e87-117">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

<span data-ttu-id="e9e87-118">**阻止**如果您希望 Office 365 将发件人添加到阻止的发件人列表。</span><span class="sxs-lookup"><span data-stu-id="e9e87-118">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e9e87-119">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="e9e87-119">What do you need to know before you begin?</span></span>

<span data-ttu-id="e9e87-120">估计完成时间：2 分钟</span><span class="sxs-lookup"><span data-stu-id="e9e87-120">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="e9e87-p105">您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的"反垃圾邮件"条目。</span><span class="sxs-lookup"><span data-stu-id="e9e87-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="e9e87-123">若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="e9e87-123">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="e9e87-124">使用 EAC 配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="e9e87-124">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="e9e87-125">在 Exchange 管理员中心 (EAC) 中，导航到**保护** \> **内容筛选器**。</span><span class="sxs-lookup"><span data-stu-id="e9e87-125">In the Exchange admin center (EAC), navigate to **Protection** \> **Content filter**.</span></span>
    
2. <span data-ttu-id="e9e87-126">选择您想要启用最终用户垃圾邮件通知（默认禁用）的内容筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="e9e87-126">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="e9e87-127">在右窗格中，其中显示有关您的策略的摘要信息，请单击**配置最终用户垃圾邮件通知**链接。</span><span class="sxs-lookup"><span data-stu-id="e9e87-127">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="e9e87-128">在随后出现的对话框中，您可以配置以下选项：</span><span class="sxs-lookup"><span data-stu-id="e9e87-128">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="e9e87-p106">**启用最终用户垃圾邮件通知**选中此复选框以启用此策略的最终用户垃圾邮件通知。（相反，如果启用此策略，则您可以清除此复选框以禁用此策略的最终用户垃圾邮件通知。）</span><span class="sxs-lookup"><span data-stu-id="e9e87-p106">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="e9e87-p107">**发送最终用户垃圾邮件通知每 （天）** 指定频率发送最终用户垃圾邮件通知。默认值为 3 天。您可以指定介于 1 到 15 天之间。如果您指定为 7 天，例如，通知将包含的所有邮件发送到垃圾邮件隔离改为在过去 7 天内供该用户的列表。</span><span class="sxs-lookup"><span data-stu-id="e9e87-p107">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="e9e87-135">**通知语言**使用下拉列表，选择编写此策略的最终用户垃圾邮件通知的语言。</span><span class="sxs-lookup"><span data-stu-id="e9e87-135">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="e9e87-p108">单击**保存**。在右窗格中显示的内容筛选器策略设置，包括您的最终用户垃圾邮件通知设置摘要。</span><span class="sxs-lookup"><span data-stu-id="e9e87-p108">Click **save**. A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="e9e87-p109">最终用户垃圾邮件通知只对已启用的内容筛选器策略可用。 >  每天只发送一次最终用户垃圾邮件通知。无法保证和配置任何特定客户的通知发送时间。</span><span class="sxs-lookup"><span data-stu-id="e9e87-p109">End-user spam notifications will only be functional for content filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="e9e87-p110">**提示：** 如果您想要通过完全实现它们之前将其发送到一组有限的用户来测试最终用户垃圾邮件通知，创建自定义内容筛选器策略，用户驻留在其中的域的最终用户垃圾邮件通知。然后，在 EAC 中，在**邮件流\>规则**，创建传输规则阻止邮件从 quarantine@messaging.microsoft.com （发送通知的电子邮件地址） 与您想要接收通知的用户的例外。下图是从域 Contoso.com 创建两个用户 （SaraD 和 AlexD） 的异常的示例：</span><span class="sxs-lookup"><span data-stu-id="e9e87-p110">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a transport rule to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![测试最终用户垃圾邮件通知的传输规则](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="e9e87-145">详细信息</span><span class="sxs-lookup"><span data-stu-id="e9e87-145">For more information</span></span>

[<span data-ttu-id="e9e87-146">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="e9e87-146">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  

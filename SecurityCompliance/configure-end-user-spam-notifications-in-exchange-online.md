---
title: Exchange Online 中配置最终用户垃圾邮件通知
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
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
description: 您可以针对默认的公司范围内内容筛选器策略或应用于域的自定义内容筛选器策略配置最终用户垃圾邮件通知。
ms.openlocfilehash: da370497f78d7f253276c908061a9a80e2f74938
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002737"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="3d397-103">Exchange Online 中配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="3d397-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d397-p101">本主题适用于 Exchange Online 客户正在保护云托管的邮箱。正在保护内部部署邮箱的 Exchange Online Protection (EOP) 独立客户应改为阅读以下主题：[在 EOP 中的配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="3d397-p101">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes. Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="3d397-p102">您可以针对默认的公司范围内内容筛选器策略或应用于域的自定义内容筛选器策略配置最终用户垃圾邮件通知。启用最终用户垃圾邮件通知邮件可以使您的最终用户自己管理自己的垃圾邮件隔离邮件。最终用户垃圾邮件通知无法与应用于用户、组的策略或有例外情况的策略一起使用。</span><span class="sxs-lookup"><span data-stu-id="3d397-p102">You can configure end-user spam notifications for the default company-wide content filter policy or for custom content filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="3d397-p103">最终用户垃圾邮件通知包含最终用户在您所配置的时间段（您可以指定一个介于 1 到 15 天之间的值）内收到的所有垃圾邮件隔离邮件的列表。您还可以配置通知邮件的编写语言。</span><span class="sxs-lookup"><span data-stu-id="3d397-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="3d397-111">在收到通知邮件后，最终用户可以通过单击将垃圾电子邮件移动至收件箱，或将垃圾电子邮件报告为"非垃圾邮件"，在这种情况下，该邮件会被发送至 Microsoft 垃圾邮件分析团队。</span><span class="sxs-lookup"><span data-stu-id="3d397-111">After receiving a notification message, end users can click to move the spam email to their inbox, or report the spam email as Not Junk, in which case it will be sent to the Microsoft Spam Analysis Team.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3d397-112">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="3d397-112">What do you need to know before you begin?</span></span>

<span data-ttu-id="3d397-113">估计完成时间：2 分钟</span><span class="sxs-lookup"><span data-stu-id="3d397-113">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="3d397-p104">您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的"反垃圾邮件"条目。</span><span class="sxs-lookup"><span data-stu-id="3d397-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="3d397-116">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="3d397-116">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="3d397-117">使用 EAC 配置最终用户垃圾邮件通知</span><span class="sxs-lookup"><span data-stu-id="3d397-117">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="3d397-118">在 Exchange 管理员中心 (EAC) 中，导航到**保护** \> **内容筛选器**。</span><span class="sxs-lookup"><span data-stu-id="3d397-118">In the Exchange admin center (EAC), navigate to **Protection** \> **Content filter**.</span></span>
    
2. <span data-ttu-id="3d397-119">选择您想要启用最终用户垃圾邮件通知（默认禁用）的内容筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="3d397-119">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="3d397-120">在右窗格中，其中显示有关您的策略的摘要信息，请单击**配置最终用户垃圾邮件通知**链接。</span><span class="sxs-lookup"><span data-stu-id="3d397-120">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="3d397-121">在随后出现的对话框中，您可以配置以下选项：</span><span class="sxs-lookup"><span data-stu-id="3d397-121">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="3d397-p105">**启用最终用户垃圾邮件通知**选中此复选框以启用此策略的最终用户垃圾邮件通知。（相反，如果启用此策略，则您可以清除此复选框以禁用此策略的最终用户垃圾邮件通知。）</span><span class="sxs-lookup"><span data-stu-id="3d397-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="3d397-p106">**发送最终用户垃圾邮件通知每 （天）** 指定频率发送最终用户垃圾邮件通知。默认值为 3 天。您可以指定介于 1 到 15 天之间。如果您指定为 7 天，例如，通知将包含的所有邮件发送到垃圾邮件隔离改为在过去 7 天内供该用户的列表。</span><span class="sxs-lookup"><span data-stu-id="3d397-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="3d397-128">**通知语言**使用下拉列表，选择编写此策略的最终用户垃圾邮件通知的语言。</span><span class="sxs-lookup"><span data-stu-id="3d397-128">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="3d397-p107">单击**保存**。在右窗格中显示的内容筛选器策略设置，包括您的最终用户垃圾邮件通知设置摘要。</span><span class="sxs-lookup"><span data-stu-id="3d397-p107">Click **save**. A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="3d397-p108">最终用户垃圾邮件通知只对已启用的内容筛选器策略可用。 >  每天只发送一次最终用户垃圾邮件通知。无法保证和配置任何特定客户的通知发送时间。</span><span class="sxs-lookup"><span data-stu-id="3d397-p108">End-user spam notifications will only be functional for content filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="3d397-p109">**提示：** 如果您想要通过完全实现它们之前将其发送到一组有限的用户来测试最终用户垃圾邮件通知，创建自定义内容筛选器策略，用户驻留在其中的域的最终用户垃圾邮件通知。然后，在 EAC 中，在**邮件流\>规则**，创建传输规则阻止邮件从 quarantine@messaging.microsoft.com （发送通知的电子邮件地址） 与您想要接收通知的用户的例外。下图是从域 Contoso.com 创建两个用户 （SaraD 和 AlexD） 的异常的示例：</span><span class="sxs-lookup"><span data-stu-id="3d397-p109">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a transport rule to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![测试最终用户垃圾邮件通知的传输规则](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="3d397-138">详细信息</span><span class="sxs-lookup"><span data-stu-id="3d397-138">For more information</span></span>

[<span data-ttu-id="3d397-139">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="3d397-139">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
---
title: 队列警报和队列
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理员可以在 Office 365 Security & 合规中心的邮件流仪表板中了解队列通知和队列。
ms.openlocfilehash: 642aa672cda124873eb0b2ca8e9294e64325f55d
ms.sourcegitcommit: fec1010e405f14e792d650aee0312b78fced3343
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2019
ms.locfileid: "30720302"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="6cf23-103">队列警报和队列</span><span class="sxs-lookup"><span data-stu-id="6cf23-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="6cf23-104">队列通知</span><span class="sxs-lookup"><span data-stu-id="6cf23-104">Queue alerts</span></span>

<span data-ttu-id="6cf23-105">当无法使用连接器从 Office 365 组织向本地或合作伙伴电子邮件服务器发送邮件时, 邮件将在 Office 365 中排队。</span><span class="sxs-lookup"><span data-stu-id="6cf23-105">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365.</span></span> <span data-ttu-id="6cf23-106">导致出现此情况的常见示例为:</span><span class="sxs-lookup"><span data-stu-id="6cf23-106">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="6cf23-107">连接器配置不正确。</span><span class="sxs-lookup"><span data-stu-id="6cf23-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="6cf23-108">本地环境中的网络或防火墙发生变化。</span><span class="sxs-lookup"><span data-stu-id="6cf23-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="6cf23-109">Office 365 将继续重试传递48小时。</span><span class="sxs-lookup"><span data-stu-id="6cf23-109">Office 365 will continue to retry to delivery for 48 hours.</span></span> <span data-ttu-id="6cf23-110">在48小时后, 邮件将会过期, 并将返回到未送达报告 (也称为 "ndr" 或 "退回邮件") 中的发件人。</span><span class="sxs-lookup"><span data-stu-id="6cf23-110">After 48 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="6cf23-111">如果已排队的电子邮件数量超过了预定义的阈值 (默认值为2000邮件), 则在**最近通知**的邮件流仪表板中将提供这些通知, 并且管理员将收到电子邮件通知 (为其备用电子邮件地址).</span><span class="sxs-lookup"><span data-stu-id="6cf23-111">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address).</span></span> <span data-ttu-id="6cf23-112">若要配置警报阈值、每日通知限制和/或通知收件人, 请参阅下面的 "**自定义队列通知**" 部分。</span><span class="sxs-lookup"><span data-stu-id="6cf23-112">To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![在 Office 365 安全 & 合规中心的邮件流仪表板的 "最近的通知" 区域中对警报进行排队](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="6cf23-114">自定义队列通知</span><span class="sxs-lookup"><span data-stu-id="6cf23-114">Customize queue alerts</span></span>

<span data-ttu-id="6cf23-115">邮件流 insights 创建名为 "邮件" 的通知策略已**延迟**(以下示例屏幕截图中的 "**发送电子邮件通知**" 复选框), 它位于**警报** \> **警报策略**中。</span><span class="sxs-lookup"><span data-stu-id="6cf23-115">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**.</span></span> <span data-ttu-id="6cf23-116">您可以通过单击策略来修改阈值并通知收件人。</span><span class="sxs-lookup"><span data-stu-id="6cf23-116">You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![通知导航](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="6cf23-118">你将看到一个新的策略信息叶片, 现在可以单击 "**编辑策略**"。</span><span class="sxs-lookup"><span data-stu-id="6cf23-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![编辑策略 ](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="6cf23-120">信息边栏将更改为 "**编辑策略**"。</span><span class="sxs-lookup"><span data-stu-id="6cf23-120">The information blade will change to the **Edit Policy**.</span></span> <span data-ttu-id="6cf23-121">您现在可以更改通知电子邮件的收件人、每天发送的通知数的限制以及触发警报的最小阈值 (200 或更多)。</span><span class="sxs-lookup"><span data-stu-id="6cf23-121">You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![编辑策略边栏](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="6cf23-123">队列警报详细信息</span><span class="sxs-lookup"><span data-stu-id="6cf23-123">Queue alert details</span></span>

<span data-ttu-id="6cf23-124">单击警报时, 警报详细信息将显示在浮出控件窗格中。</span><span class="sxs-lookup"><span data-stu-id="6cf23-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![在 Office 365 安全 & 合规中心的邮件流仪表板的 "最近的通知" 区域中选择队列通知](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![Office 365 Security & 合规中心中的队列警报详细信息浮出控件](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="6cf23-127">您可以单击警报详细信息中的 "**查看队列**", 在新的飞出窗格中查看队列详细信息、问题和指向可用修复程序的链接。</span><span class="sxs-lookup"><span data-stu-id="6cf23-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![Office 365 Security & 合规中心中的队列警报详细信息浮出控件](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![查看警报详细信息中的队列](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="6cf23-130">队列</span><span class="sxs-lookup"><span data-stu-id="6cf23-130">Queues</span></span>

<span data-ttu-id="6cf23-131">即使排队邮件量未超过阈值, 仍可以使用邮件流仪表板的 "**队列**" 区域查看已排入超过1小时的邮件。</span><span class="sxs-lookup"><span data-stu-id="6cf23-131">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour.</span></span> <span data-ttu-id="6cf23-132">您可以使用 "**队列**" 区域来监视已排队的邮件数 (值为0表示邮件流正常), 并在队列中的邮件数变得过大之前执行操作。</span><span class="sxs-lookup"><span data-stu-id="6cf23-132">You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![Office 365 Security & 合规中心中的邮件流仪表板中的队列](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="6cf23-134">单击**队列**中已排队的邮件数时, 将在弹出窗口中显示有关如何修复问题的队列详细信息和指南 (在队列警报的详细信息中单击 "**查看队列**" 后出现的同一浮出控件)。</span><span class="sxs-lookup"><span data-stu-id="6cf23-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![队列详细信息](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a><span data-ttu-id="6cf23-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cf23-136">See also</span></span>

<span data-ttu-id="6cf23-137">有关邮件流仪表板中的其他邮件流见解的详细信息, 请参阅[Security & 合规性中心中的邮件流见解](mail-flow-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="6cf23-137">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights.md).</span></span>

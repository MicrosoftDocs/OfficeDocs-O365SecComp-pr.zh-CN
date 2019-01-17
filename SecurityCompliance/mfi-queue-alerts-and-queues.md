---
title: 通知队列和队列
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理员可以在 Office 365 安全性 & 合规性中心中的邮件流仪表板了解有关队列通知和队列。
ms.openlocfilehash: fe750e32136af095bb0ccff8544306db76a7a667
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685349"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="7fa92-103">通知队列和队列</span><span class="sxs-lookup"><span data-stu-id="7fa92-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="7fa92-104">队列通知</span><span class="sxs-lookup"><span data-stu-id="7fa92-104">Queue alerts</span></span>

<span data-ttu-id="7fa92-p101">无法将消息从 Office 365 组织发送给您的内部部署时或合作伙伴使用连接器的电子邮件服务器，在 Office 365 中排队邮件。此条件会导致的常见示例包括：</span><span class="sxs-lookup"><span data-stu-id="7fa92-p101">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365. Common examples that cause this condition are:</span></span>

- <span data-ttu-id="7fa92-107">连接器配置不正确。</span><span class="sxs-lookup"><span data-stu-id="7fa92-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="7fa92-108">内部部署环境中已网络或防火墙的更改。</span><span class="sxs-lookup"><span data-stu-id="7fa92-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="7fa92-p102">Office 365 将继续进行重试传递到 48 小时。48 小时后邮件将过期，并将返回未送达报告中的发件人 (也称为 Ndr 或弹跳消息)。</span><span class="sxs-lookup"><span data-stu-id="7fa92-p102">Office 365 will continue to retry to delivery for 48 hours. After 48 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="7fa92-p103">如果排队的电子邮件卷超过预定义的阈值 （默认值为 2000年消息），可在**最近的通知**，在邮件流仪表板中的通知，并且管理员将收到 （到其替代电子邮件地址） 的电子邮件通知.若要配置的警报阈值，每日通知限制，和/或收件人的通知，请参阅下面的**自定义队列通知**部分。</span><span class="sxs-lookup"><span data-stu-id="7fa92-p103">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address). To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![Office 365 安全性 & 合规性中心中的邮件流仪表板的最新通知区域中的队列通知](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="7fa92-114">自定义队列通知</span><span class="sxs-lookup"><span data-stu-id="7fa92-114">Customize queue alerts</span></span>

<span data-ttu-id="7fa92-p104">邮件流见解创建命名**邮件已被延迟**（**发送电子邮件通知**复选框的示例屏幕截图下方） 在**通知**中找到的警报策略\>**警报策略**。您可以通过单击在策略中修改的阈值和通知收件人。</span><span class="sxs-lookup"><span data-stu-id="7fa92-p104">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**. You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![通知导航](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="7fa92-118">您将看到新的策略信息刀片，您现在可以单击**编辑策略**。</span><span class="sxs-lookup"><span data-stu-id="7fa92-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![编辑策略 ](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="7fa92-p105">信息刀片将更改为**编辑策略**。现在，您可以更改通知的电子邮件发送每日和最小阈值触发通知 （200 个或多个） 的通知数的限制的收件人。</span><span class="sxs-lookup"><span data-stu-id="7fa92-p105">The information blade will change to the **Edit Policy**. You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![编辑策略刀片](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="7fa92-123">队列警报的详细信息</span><span class="sxs-lookup"><span data-stu-id="7fa92-123">Queue alert details</span></span>

<span data-ttu-id="7fa92-124">当您单击该通知时，警报的详细信息将出现在弹出窗格。</span><span class="sxs-lookup"><span data-stu-id="7fa92-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![在 Office 365 安全性 & 合规性中心中的邮件流仪表板的最新通知区域中选择队列通知](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![在 Office 365 安全性 & 合规性中心队列警报的详细信息弹出](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="7fa92-127">您可以单击**查看队列**中警报的详细信息，请参阅队列详细信息、 问题和新弹出窗格中的可用修补程序的链接。</span><span class="sxs-lookup"><span data-stu-id="7fa92-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![在 Office 365 安全性 & 合规性中心队列警报的详细信息弹出](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![查看队列中的警报的详细信息](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="7fa92-130">队列</span><span class="sxs-lookup"><span data-stu-id="7fa92-130">Queues</span></span>

<span data-ttu-id="7fa92-p106">即使排队的消息音量不起作用超过了阈值，您仍可以使用**队列**区域中的邮件流仪表板查看已排队等待一小时以上的邮件。**队列**区域可用于监视 （值 0 表示邮件流是确定） 的排队消息的数目和排队的消息数变得太大之前执行操作。</span><span class="sxs-lookup"><span data-stu-id="7fa92-p106">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour. You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![Office 365 安全性 & 合规性中心中的邮件流仪表板中的队列](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="7fa92-134">当您单击的**队列**，队列详细信息中排队消息数和如何解决此问题的指导将出现在弹出窗格 （之后单击**查看队列**队列警报的详细信息中显示同一弹出）。</span><span class="sxs-lookup"><span data-stu-id="7fa92-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![队列的详细信息](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

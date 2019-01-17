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
# <a name="queue-alerts-and-queues"></a>通知队列和队列

## <a name="queue-alerts"></a>队列通知

无法将消息从 Office 365 组织发送给您的内部部署时或合作伙伴使用连接器的电子邮件服务器，在 Office 365 中排队邮件。此条件会导致的常见示例包括：

- 连接器配置不正确。

- 内部部署环境中已网络或防火墙的更改。

Office 365 将继续进行重试传递到 48 小时。48 小时后邮件将过期，并将返回未送达报告中的发件人 (也称为 Ndr 或弹跳消息)。

如果排队的电子邮件卷超过预定义的阈值 （默认值为 2000年消息），可在**最近的通知**，在邮件流仪表板中的通知，并且管理员将收到 （到其替代电子邮件地址） 的电子邮件通知.若要配置的警报阈值，每日通知限制，和/或收件人的通知，请参阅下面的**自定义队列通知**部分。

![Office 365 安全性 & 合规性中心中的邮件流仪表板的最新通知区域中的队列通知](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a>自定义队列通知

邮件流见解创建命名**邮件已被延迟**（**发送电子邮件通知**复选框的示例屏幕截图下方） 在**通知**中找到的警报策略\>**警报策略**。您可以通过单击在策略中修改的阈值和通知收件人。

![通知导航](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

您将看到新的策略信息刀片，您现在可以单击**编辑策略**。

![编辑策略 ](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

信息刀片将更改为**编辑策略**。现在，您可以更改通知的电子邮件发送每日和最小阈值触发通知 （200 个或多个） 的通知数的限制的收件人。

![编辑策略刀片](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a>队列警报的详细信息

当您单击该通知时，警报的详细信息将出现在弹出窗格。

![在 Office 365 安全性 & 合规性中心中的邮件流仪表板的最新通知区域中选择队列通知](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![在 Office 365 安全性 & 合规性中心队列警报的详细信息弹出](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

您可以单击**查看队列**中警报的详细信息，请参阅队列详细信息、 问题和新弹出窗格中的可用修补程序的链接。

![在 Office 365 安全性 & 合规性中心队列警报的详细信息弹出](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![查看队列中的警报的详细信息](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a>队列

即使排队的消息音量不起作用超过了阈值，您仍可以使用**队列**区域中的邮件流仪表板查看已排队等待一小时以上的邮件。**队列**区域可用于监视 （值 0 表示邮件流是确定） 的排队消息的数目和排队的消息数变得太大之前执行操作。

![Office 365 安全性 & 合规性中心中的邮件流仪表板中的队列](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

当您单击的**队列**，队列详细信息中排队消息数和如何解决此问题的指导将出现在弹出窗格 （之后单击**查看队列**队列警报的详细信息中显示同一弹出）。

![队列的详细信息](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

---
title: 队列警报和队列
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理员可以在 Office 365 Security & 合规中心的邮件流仪表板中了解队列通知和队列。
ms.openlocfilehash: 45c03ae8d5f646c4514b19669ca83b3eac561f68
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220792"
---
# <a name="queue-alerts-and-queues"></a>队列警报和队列

## <a name="queue-alerts"></a>队列通知

当无法使用连接器从 Office 365 组织向本地或合作伙伴电子邮件服务器发送邮件时, 邮件将在 Office 365 中排队。导致出现此情况的常见示例为:

- 连接器配置不正确。

- 本地环境中的网络或防火墙发生变化。

Office 365 将继续重试传递48小时。在48小时后, 邮件将会过期, 并将返回到未送达报告 (也称为 "ndr" 或 "退回邮件") 中的发件人。

如果已排队的电子邮件数量超过了预定义的阈值 (默认值为2000邮件), 则在**最近通知**的邮件流仪表板中将提供这些通知, 并且管理员将收到电子邮件通知 (为其备用电子邮件地址).若要配置警报阈值、每日通知限制和/或通知收件人, 请参阅下面的 "**自定义队列通知**" 部分。

![在 Office 365 安全 & 合规中心的邮件流仪表板的 "最近的通知" 区域中对警报进行排队](media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a>自定义队列通知

邮件流 insights 创建名为 "邮件" 的通知策略已**延迟**(以下示例屏幕截图中的 "**发送电子邮件通知**" 复选框), 它位于**警报** \> **警报策略**中。您可以通过单击策略来修改阈值并通知收件人。

![通知导航](media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

你将看到一个新的策略信息叶片, 现在可以单击 "**编辑策略**"。

![编辑策略 ](media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

信息边栏将更改为 "**编辑策略**"。您现在可以更改通知电子邮件的收件人、每天发送的通知数的限制以及触发警报的最小阈值 (200 或更多)。

![编辑策略边栏](media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a>队列警报详细信息

单击警报时, 警报详细信息将显示在浮出控件窗格中。

![在 Office 365 安全 & 合规中心的邮件流仪表板的 "最近的通知" 区域中选择队列通知](media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![Office 365 Security & 合规中心中的队列警报详细信息浮出控件](media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

您可以单击警报详细信息中的 "**查看队列**", 在新的飞出窗格中查看队列详细信息、问题和指向可用修复程序的链接。

![Office 365 Security & 合规中心中的队列警报详细信息浮出控件](media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![查看警报详细信息中的队列](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a>队列

即使排队邮件量未超过阈值, 仍可以使用邮件流仪表板的 "**队列**" 区域查看已排入超过1小时的邮件。您可以使用 "**队列**" 区域来监视已排队的邮件数 (值为0表示邮件流正常), 并在队列中的邮件数变得过大之前执行操作。

![Office 365 Security & 合规中心中的邮件流仪表板中的队列](media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

单击**队列**中已排队的邮件数时, 将在弹出窗口中显示有关如何修复问题的队列详细信息和指南 (在队列警报的详细信息中单击 "**查看队列**" 后出现的同一浮出控件)。

![队列详细信息](media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

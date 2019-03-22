---
title: 不接受的域报告
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理员可以在 "Office 365 安全 & 合规中心" 的 "邮件流" 仪表板中了解不接受的域报告。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: f7fc54a4b1d31d724a95c5d8540b95034effbab4
ms.sourcegitcommit: fec1010e405f14e792d650aee0312b78fced3343
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2019
ms.locfileid: "30722777"
---
# <a name="non-accepted-domain-report"></a><span data-ttu-id="cc208-103">不接受的域报告</span><span class="sxs-lookup"><span data-stu-id="cc208-103">Non-accepted domain report</span></span>

> [!NOTE]
> <span data-ttu-id="cc208-104">本主题中所述的功能尚未部署到所有 Office 365 组织中, 可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="cc208-104">The features described in this topic haven't been deployed to all Office 365 organizations, and are subject to change.</span></span>

<span data-ttu-id="cc208-105">与**发件人域**洞察力类似,**不接受的域**洞察力可识别来自内部部署电子邮件组织的邮件, 但发件人的域不会配置为 Office 365 组织中的接受域。</span><span class="sxs-lookup"><span data-stu-id="cc208-105">Similar to the **Sender domain** insight, the **Non-accepted domain** insight identifies messages from your on-premises email organization, but the sender's domain isn't configured as an accepted domain in your Office 365 organization.</span></span>

<span data-ttu-id="cc208-106">如果我们有数据来证明这些邮件的目的是恶意的, 则 Office 365 可能会限制这些邮件。</span><span class="sxs-lookup"><span data-stu-id="cc208-106">Office 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="cc208-107">因此, 重要的是要了解所发生的情况并解决问题。</span><span class="sxs-lookup"><span data-stu-id="cc208-107">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

!["Office 365 Security & 合规中心" 的 "邮件流" 仪表板中的 "不接受的域" 报告](media/non-accepted-domain-report-selected.png)

<span data-ttu-id="cc208-109">当您单击小组件时, 将转到完整报告。</span><span class="sxs-lookup"><span data-stu-id="cc208-109">When you click on the widget, you're taken to the full report.</span></span> <span data-ttu-id="cc208-110">在完整报告中, 您可以单击 "**查看详细信息**" 以查看表中的信息, 如下图所示:</span><span class="sxs-lookup"><span data-stu-id="cc208-110">In the full report, where you can click **View details** to view the information in a table as shown in the following diagram:</span></span>

![不接受的域中的查看详细信息表报告](media/non-accepted-domain-report-view-details.png)

<span data-ttu-id="cc208-112">当您选择表中的一行时, 飞出的内容将显示更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="cc208-112">When you select a row in the table, a flyout will show you more details.</span></span> <span data-ttu-id="cc208-113">您可以单击 "**查看示例消息**" 来查看一些已确定的邮件。</span><span class="sxs-lookup"><span data-stu-id="cc208-113">You can click **view sample messages** to see some of the identified messages.</span></span>

![在 "不接受的域" 报告的详细信息表中选择一行。](media/non-accepted-domain-report-select-row-in-table.png)

## <a name="see-also"></a><span data-ttu-id="cc208-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc208-115">See also</span></span>

<span data-ttu-id="cc208-116">有关邮件流仪表板中的其他邮件流见解的详细信息, 请参阅[Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="cc208-116">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>

---
title: 顶级域邮件流状态见解
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解安全 & 合规性中心的邮件流仪表板中的顶层域邮件流状态洞察力。
ms.openlocfilehash: c339769c65b2b1cec3d187873e71e5f1e283ccc7
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158644"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="90e4a-103">顶级域邮件流状态见解</span><span class="sxs-lookup"><span data-stu-id="90e4a-103">Top domain mail flow status insight</span></span>

<span data-ttu-id="90e4a-104">**顶级域邮件流状态**洞察力为您的组织的域提供了邮件流的当前状态。</span><span class="sxs-lookup"><span data-stu-id="90e4a-104">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="90e4a-105">此洞察力可帮助您识别和解决遇到***邮件流影响***问题的域 (例如, 无法接收外部电子邮件), 尤其是域过期或包含不正确的 MX 记录的域。</span><span class="sxs-lookup"><span data-stu-id="90e4a-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Security & 合规性中心的邮件流仪表板中的顶级域流状态洞察力](media/domain-mail-flow-status-selected.png)

<span data-ttu-id="90e4a-107">当您单击真知灼见中的 "**查看详细信息**" 时, 将显示一个弹出项, 显示每个域的状态的详细信息。</span><span class="sxs-lookup"><span data-stu-id="90e4a-107">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="90e4a-108">域的绿色复选标记表示当前的 MX 记录 (当您浏览到邮件流见解仪表板时) 与我们记录的值相匹配, 并且在过去的两个小时内, 该域已收到电子邮件。</span><span class="sxs-lookup"><span data-stu-id="90e4a-108">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="90e4a-109">域中的红色 x 表示 MX 记录已更改, 并且在过去6个小时内没有收到此域的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="90e4a-109">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="90e4a-110">这可能表明你的域已过期, 或者 MX 记录已被错误更新。</span><span class="sxs-lookup"><span data-stu-id="90e4a-110">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="90e4a-111">请与你的域注册机构或 DNS 托管服务核实域是否已过期, 或者域的 MX 记录是否不正确。</span><span class="sxs-lookup"><span data-stu-id="90e4a-111">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![顶级域流状态洞察力中的详细信息浮出控件](media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a><span data-ttu-id="90e4a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90e4a-113">See also</span></span>

<span data-ttu-id="90e4a-114">有关邮件流仪表板中的其他邮件流见解的详细信息, 请参阅[Security _AMP_ 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="90e4a-114">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>

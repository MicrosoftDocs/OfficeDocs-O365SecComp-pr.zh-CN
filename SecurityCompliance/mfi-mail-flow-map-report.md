---
title: 邮件流映射报告
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解安全 & 合规性中心的邮件流仪表板中的邮件流映射报告。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: bd05ff5cb78adb9dd89dbe3f69c2c3a78d2b1df9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252410"
---
# <a name="mail-flow-map-report"></a><span data-ttu-id="129c3-103">邮件流映射报告</span><span class="sxs-lookup"><span data-stu-id="129c3-103">Mail flow map report</span></span>

> [!NOTE]
> <span data-ttu-id="129c3-104">本主题中所述的功能尚未部署到所有 Office 365 组织中, 可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="129c3-104">The features described in this topic haven't been deployed to all Office 365 organizations, and are subject to change.</span></span>

<span data-ttu-id="129c3-105">此报告提供有关邮件通过 Office 365 组织的流的见解。</span><span class="sxs-lookup"><span data-stu-id="129c3-105">This report gives insights as to how mail flows through your Office 365 organization.</span></span> <span data-ttu-id="129c3-106">您可以使用此信息来了解模式、确定异常, 并在出现问题时解决问题。</span><span class="sxs-lookup"><span data-stu-id="129c3-106">You can use this information to learn patterns, identify anomalies, and fix issues as they arise.</span></span>

![Security & 合规性中心的邮件流仪表板中的邮件流映射报告](media/mail-flow-map-selected.png)

## <a name="mail-flow-map-widget"></a><span data-ttu-id="129c3-108">邮件流映射小部件</span><span class="sxs-lookup"><span data-stu-id="129c3-108">Mail flow map widget</span></span>

<span data-ttu-id="129c3-109">默认情况下, 邮件流地图显示前一天的高级别邮件流模式。</span><span class="sxs-lookup"><span data-stu-id="129c3-109">By default, the mail flow map shows the high level mail flow pattern from the previous day.</span></span> <span data-ttu-id="129c3-110">您可以在不同的天使用左箭头和右箭头。</span><span class="sxs-lookup"><span data-stu-id="129c3-110">You can use the left and right arrows for different days.</span></span> <span data-ttu-id="129c3-111">将鼠标光标悬停在报告中的每个区域上将显示从 Office 365 组织到和的邮件量, 如下图所示:</span><span class="sxs-lookup"><span data-stu-id="129c3-111">Hovering your mouse cursor over each area in the report will show the volume of mail to and from your Office 365 organization as shown in the following diagram:</span></span>

![邮件流映射小组件中的向左和向右箭头](media/mail-flow-map-widget.png)

## <a name="overview"></a><span data-ttu-id="129c3-113">概述</span><span class="sxs-lookup"><span data-stu-id="129c3-113">Overview</span></span>

<span data-ttu-id="129c3-114">单击 "**邮件流地图**" 小部件将转到**邮件流地图**报告。</span><span class="sxs-lookup"><span data-stu-id="129c3-114">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span> <span data-ttu-id="129c3-115">您可以在此处查看更详细的报告级别, 可以单击 "查看详细信息表" 以查看详细数据。</span><span class="sxs-lookup"><span data-stu-id="129c3-115">Here you can see more granular level of report, you can click View details table to see detailed data.</span></span> <span data-ttu-id="129c3-116">您还可以通过单击 "请求报告" 下载详细报告。</span><span class="sxs-lookup"><span data-stu-id="129c3-116">You can also download the detailed report by clicking Request report.</span></span>

![邮件流映射报告中的概述视图](media/mail-flow-map-overview.png)

## <a name="details"></a><span data-ttu-id="129c3-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="129c3-118">Details</span></span>

<span data-ttu-id="129c3-119">默认情况下, "将**数据显示**" 设置为 "值**概述**"。</span><span class="sxs-lookup"><span data-stu-id="129c3-119">By default, **Show data for** is set to the value **Overview**.</span></span> <span data-ttu-id="129c3-120">当您单击下拉下拉箭头并选择 "**详细信息**" 时, 视图将切换到域级详细信息。</span><span class="sxs-lookup"><span data-stu-id="129c3-120">When you click on the drop down and select **Detail**, the view switches to the domain level detail.</span></span>

![在邮件流映射报告中选择 "在概述视图中显示数据中的详细信息"](media/mail-flow-map-select-detail.png)

<span data-ttu-id="129c3-122">将列出最上面的发件人和收件人域, 其余部分将放置在**其他**人中, 如下图所示:</span><span class="sxs-lookup"><span data-stu-id="129c3-122">The top sender and recipient domains are listed, and the rest will be put in **Others** as shown in the following diagrams:</span></span>

![邮件流映射报告中的详细信息视图](media/mail-flow-map-detail.png)

## <a name="related-insights"></a><span data-ttu-id="129c3-124">相关见解</span><span class="sxs-lookup"><span data-stu-id="129c3-124">Related insights</span></span>

<span data-ttu-id="129c3-125">如果可用, 相关的见解将显示在邮件流映射的下面 (例如, 发件人域洞察力或邮件循环见解)。</span><span class="sxs-lookup"><span data-stu-id="129c3-125">Related insights are shown beneath the Mail flow map if they're available (for example, the Sender domain insight or the Mail loop insight).</span></span>

## <a name="see-also"></a><span data-ttu-id="129c3-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="129c3-126">See also</span></span>

<span data-ttu-id="129c3-127">有关邮件流仪表板中的其他邮件流见解的详细信息, 请参阅[Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="129c3-127">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
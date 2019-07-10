---
title: SMTP 身份验证客户端报表
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解安全 & 合规性中心的邮件流仪表板中的 SMTP 身份验证客户端报告。
ms.openlocfilehash: 21d2446bd7441f17c2371186d098118c6403de0c
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598128"
---
# <a name="smtp-auth-clients-report"></a><span data-ttu-id="95cdc-103">SMTP 身份验证客户端报表</span><span class="sxs-lookup"><span data-stu-id="95cdc-103">SMTP Auth clients report</span></span>

<span data-ttu-id="95cdc-104">**Smtp auth 客户端**报告突出显示了组织中的用户或系统帐户对 SMTP 身份验证客户端提交协议的使用。</span><span class="sxs-lookup"><span data-stu-id="95cdc-104">The **SMTP Auth clients** report highlights the use of the SMTP Auth client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="95cdc-105">此旧协议 (使用终结点 smtp.office365.com) 仅提供基本身份验证, 并且容易被受攻击帐户用来发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="95cdc-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span>  <span data-ttu-id="95cdc-106">此报告允许您检查异常活动。</span><span class="sxs-lookup"><span data-stu-id="95cdc-106">This report allows you to check for unusual activity.</span></span> <span data-ttu-id="95cdc-107">它还显示了使用 SMTP 身份验证的客户端或设备的 TLS 使用数据。</span><span class="sxs-lookup"><span data-stu-id="95cdc-107">It also shows the TLS usage data for clients or devices using SMTP Auth.</span></span>

<span data-ttu-id="95cdc-108">"邮件流" 仪表板中显示的小部件指示最近7天内已使用 SMTP 身份验证协议的用户或服务帐户的数量。</span><span class="sxs-lookup"><span data-stu-id="95cdc-108">The widget that's shown in the Mail Flow dashboard indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![SMTP 身份验证客户端在安全 & 合规性中心中的邮件流仪表板中报告](media/smtp-auth-clients-report-selected.png)

<span data-ttu-id="95cdc-110">单击小组件将打开一个浮出控件, 该浮出控件可提供上一周的 TLS 使用情况和卷的聚合视图。</span><span class="sxs-lookup"><span data-stu-id="95cdc-110">Clicking on the widget opens a flyout that provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![SMTP Auth 客户端报告中的浮出控件](media/smtp-auth-clients-flyout.png)

<span data-ttu-id="95cdc-112">当您单击**SMTP Auth 客户端报告**链接时, 您将看到两个主要数据透视和两个数据视图。</span><span class="sxs-lookup"><span data-stu-id="95cdc-112">When you click on the **SMTP Auth Clients Report** link, you'll see two main data pivots and two data views.</span></span> <span data-ttu-id="95cdc-113">数据透视是**发送卷**和 TLS 的**使用情况**。</span><span class="sxs-lookup"><span data-stu-id="95cdc-113">The data pivots are the **Sending Volume** and **TLS Usage**.</span></span> <span data-ttu-id="95cdc-114">数据视图是图表和详细信息表。</span><span class="sxs-lookup"><span data-stu-id="95cdc-114">The data views are the chart and the details table.</span></span>

<span data-ttu-id="95cdc-115">**发送卷**视图显示在指定时间范围内使用 SMTP 身份验证发送的邮件数。</span><span class="sxs-lookup"><span data-stu-id="95cdc-115">The **Sending Volume** view shows the number of messages that were sent using SMTP Auth for the specified time range.</span></span> <span data-ttu-id="95cdc-116">您可以通过单击 "**筛选器**" 来调整该区域。</span><span class="sxs-lookup"><span data-stu-id="95cdc-116">You can adjust the range by clicking **Filters**.</span></span> <span data-ttu-id="95cdc-117">图表按发件人域进行组织。</span><span class="sxs-lookup"><span data-stu-id="95cdc-117">The chart is organized by sender domain.</span></span> <span data-ttu-id="95cdc-118">通过在 "**显示数据**" 下拉下拉箭头中选择域, 可以查看每个域的单独数据。</span><span class="sxs-lookup"><span data-stu-id="95cdc-118">You can see separate data for each domain by selecting the domain in the **Show data for** drop down.</span></span>

![在 SMTP Auth 客户端报告中发送卷](media/smtp-auth-clients-report-sending-volume.png)

<span data-ttu-id="95cdc-120">您可以通过单击 "**查看详细**信息" 表来查看有关这些发件人及其邮件计数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="95cdc-120">You can view detailed information about the senders and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="95cdc-121">若要返回图表, 请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="95cdc-121">To return to the chart, click **View report**.</span></span>

![SMTP Auth 客户端报告中用于发送卷的详细信息表](media/smtp-auth-clients-report-details-sending-volume.png)

<span data-ttu-id="95cdc-123">由于即将弃用的 TLS 1.0 和 TLS 1.1 在 Office 365 中, **Tls 使用**透视非常重要。</span><span class="sxs-lookup"><span data-stu-id="95cdc-123">The **TLS Usage** pivot is important due to the upcoming deprecation of TLS1.0 and TLS1.1 in Office 365.</span></span> <span data-ttu-id="95cdc-124">如果您的旧设备和应用程序仅能够将 TLS 1.0 与 SMTP Auth 一起使用, 则这些设备和应用程序将无法发送电子邮件。此数据透视允许你识别仍在使用旧版 TLS 的用户和系统帐户并对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="95cdc-124">Many legacy devices and applications will be unable to send email if they are only capable of using TLS1.0 with SMTP Auth. This pivot allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

![SMTP Auth 客户端报告中的 TLS 用法](media/smtp-auth-clients-report-tls-usage.png)

<span data-ttu-id="95cdc-126">可以通过单击 "**查看详细**信息" 表, 查看有关这些发件人、使用 SMTP 身份验证的 TLS 版本以及邮件数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="95cdc-126">You can view detailed information about the senders, the versions of TLS they are using with SMTP Auth, and their message counts by clicking **View details table**.</span></span> <span data-ttu-id="95cdc-127">若要返回图表, 请单击 "**查看报告**"。</span><span class="sxs-lookup"><span data-stu-id="95cdc-127">To return to the chart, click **View report**.</span></span>

<span data-ttu-id="95cdc-128">您还可以通过单击 "请求报告" 下载报告的更详细的版本。</span><span class="sxs-lookup"><span data-stu-id="95cdc-128">You can also download a more detailed version of the report by clicking Request report.</span></span>

![SMTP Auth 客户端报告中 TLS 用法的详细信息表](media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a><span data-ttu-id="95cdc-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95cdc-130">See also</span></span>

<span data-ttu-id="95cdc-131">有关邮件流仪表板中的其他邮件流见解的详细信息, 请参阅[Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="95cdc-131">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>

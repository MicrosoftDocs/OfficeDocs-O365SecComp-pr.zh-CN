---
title: 安全 & 合规性中心中的邮件流见解
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理员可以了解有关安全 & 合规性中心中的邮件流仪表板。
ms.openlocfilehash: 481815430a91413cc96b92c074bd2d62771751ee
ms.sourcegitcommit: 25fb33a1f8b2844fde15f6c03db2936c610824e0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28685344"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="26868-103">安全 & 合规性中心中的邮件流见解</span><span class="sxs-lookup"><span data-stu-id="26868-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="26868-104">管理员可以使用邮件流仪表板中安全 & 合规性中心发现趋势，见解并执行修复与 Office 365 组织中的邮件流相关的问题的操作。</span><span class="sxs-lookup"><span data-stu-id="26868-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their Office 365 organization.</span></span>

<span data-ttu-id="26868-105">见解、 报告和邮件流仪表板中可用的小部件是：</span><span class="sxs-lookup"><span data-stu-id="26868-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="26868-106">出站和入站邮件流</span><span class="sxs-lookup"><span data-stu-id="26868-106">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="26868-107">通知队列和队列</span><span class="sxs-lookup"><span data-stu-id="26868-107">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="26868-108">自动转发邮件报告</span><span class="sxs-lookup"><span data-stu-id="26868-108">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="26868-109">邮件循环洞察</span><span class="sxs-lookup"><span data-stu-id="26868-109">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="26868-110">慢的邮件流规则洞察</span><span class="sxs-lookup"><span data-stu-id="26868-110">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="26868-111">查看邮件流仪表板所需的权限</span><span class="sxs-lookup"><span data-stu-id="26868-111">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="26868-112">邮件流仪表板可供：</span><span class="sxs-lookup"><span data-stu-id="26868-112">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="26868-113">**Office 365 全局管理员**角色的成员。</span><span class="sxs-lookup"><span data-stu-id="26868-113">Members of the **Office 365 global administrator** role.</span></span>

- <span data-ttu-id="26868-114">**Office 365 Exchange 管理员**角色的成员。</span><span class="sxs-lookup"><span data-stu-id="26868-114">Members of **Office 365 Exchange administrator** role.</span></span>

- <span data-ttu-id="26868-p101">安全 & 合规性中心中的**邮件流管理员角色**的成员。如果此角色显式分配给不是全局管理员或 Exchange 管理员角色的成员的用户：</span><span class="sxs-lookup"><span data-stu-id="26868-p101">Members of the **Mail flow administrator role** in the Security & Compliance Center. If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="26868-117">用户必须登录到直接在安全 & 合规性中心[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="26868-117">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="26868-118">用户才会对邮件流仪表板的只读权限。</span><span class="sxs-lookup"><span data-stu-id="26868-118">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="26868-119">用户不会有权访问 Office 365 管理门户。</span><span class="sxs-lookup"><span data-stu-id="26868-119">The user won't have access to the Office 365 admin portal.</span></span>

<span data-ttu-id="26868-120">有关 Office 365 全局管理员角色的详细信息，请参阅[有关 Office 365 管理员角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="26868-120">For more information about the Office 365 global administrator role, see [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

<span data-ttu-id="26868-121">有关将安全 & 合规性中心角色分配给用户的信息，请参阅[授予用户对安全 & 合规中心的访问](https://support.office.com/article/2cfce2c8-20c5-47f9-afc4-24b059c1bd76)。</span><span class="sxs-lookup"><span data-stu-id="26868-121">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](https://support.office.com/article/2cfce2c8-20c5-47f9-afc4-24b059c1bd76).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="26868-122">在哪里可以找到邮件流仪表板</span><span class="sxs-lookup"><span data-stu-id="26868-122">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="26868-123">转到安全 & 合规性中心，网址为[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="26868-123">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="26868-124">展开**邮件流**，然后选择**仪表板**。</span><span class="sxs-lookup"><span data-stu-id="26868-124">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![Office 365 安全性 & 合规性中心中的邮件流仪表板](media/f32f5c0a-ea32-4e47-a477-d070405d4ae8.png)

---
title: 安全与合规中心内的邮件流见解
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理员可以了解安全 & 合规性中心中的邮件流仪表板。
ms.openlocfilehash: 80aa6b773d63b6c98293fa2787d38ad393e67b37
ms.sourcegitcommit: e05e83212e7ca4e84f2ddb0de0297895b995338d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "33868620"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a><span data-ttu-id="d4124-103">安全与合规中心内的邮件流见解</span><span class="sxs-lookup"><span data-stu-id="d4124-103">Mail flow insights in the Security & Compliance Center</span></span>

<span data-ttu-id="d4124-104">管理员可以使用安全 & 合规中心中的邮件流仪表板来发现趋势、见解并采取措施解决与 Office 365 组织中的邮件流相关的问题。</span><span class="sxs-lookup"><span data-stu-id="d4124-104">Admins can use mail flow dashboard in the Security & Compliance Center to discover trends, insights and take actions to fix issues related to mail flow in their Office 365 organization.</span></span>

<span data-ttu-id="d4124-105">邮件流仪表板中提供的见解、报告和小部件为:</span><span class="sxs-lookup"><span data-stu-id="d4124-105">The insights, reports, and widgets that are available in the mail flow dashboard are:</span></span>

- [<span data-ttu-id="d4124-106">邮件流映射报告</span><span class="sxs-lookup"><span data-stu-id="d4124-106">Mail flow map report</span></span>](mfi-mail-flow-map-report.md)

- [<span data-ttu-id="d4124-107">域邮件流状态洞察力</span><span class="sxs-lookup"><span data-stu-id="d4124-107">Domain mail flow status insight</span></span>](mfi-domain-mail-flow-status-insight.md)

- [<span data-ttu-id="d4124-108">SMTP 身份验证客户端报告</span><span class="sxs-lookup"><span data-stu-id="d4124-108">SMTP Auth clients report</span></span>](mfi-smtp-auth-clients-report.md)

- [<span data-ttu-id="d4124-109">发件人域洞察力</span><span class="sxs-lookup"><span data-stu-id="d4124-109">Sender domain insight</span></span>](mfi-sender-domain-insight.md)

- [<span data-ttu-id="d4124-110">未送达报告</span><span class="sxs-lookup"><span data-stu-id="d4124-110">Non-delivery report</span></span>](mfi-non-delivery-report.md)

- [<span data-ttu-id="d4124-111">不接受的域报告</span><span class="sxs-lookup"><span data-stu-id="d4124-111">Non-accepted domain report</span></span>](mfi-non-accepted-domain-report.md)

- [<span data-ttu-id="d4124-112">入站和出站邮件流</span><span class="sxs-lookup"><span data-stu-id="d4124-112">Outbound and inbound mail flow</span></span>](mfi-outbound-and-inbound-mail-flow.md)

- [<span data-ttu-id="d4124-113">队列警报和队列</span><span class="sxs-lookup"><span data-stu-id="d4124-113">Queue alerts and Queues</span></span>](mfi-queue-alerts-and-queues.md)

- [<span data-ttu-id="d4124-114">自动转发的消息报告</span><span class="sxs-lookup"><span data-stu-id="d4124-114">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)

- [<span data-ttu-id="d4124-115">邮件循环见解</span><span class="sxs-lookup"><span data-stu-id="d4124-115">Mail loop insight</span></span>](mfi-mail-loop-insight.md)

- [<span data-ttu-id="d4124-116">慢邮件流规则见解</span><span class="sxs-lookup"><span data-stu-id="d4124-116">Slow mail flow rules insight</span></span>](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a><span data-ttu-id="d4124-117">查看邮件流仪表板所需的权限</span><span class="sxs-lookup"><span data-stu-id="d4124-117">Permissions required to view the mail flow dashboard</span></span>

<span data-ttu-id="d4124-118">邮件流仪表板可用于:</span><span class="sxs-lookup"><span data-stu-id="d4124-118">The mail flow dashboard is available to:</span></span>

- <span data-ttu-id="d4124-119">**Office 365 全局管理员**角色的成员。</span><span class="sxs-lookup"><span data-stu-id="d4124-119">Members of the **Office 365 global administrator** role.</span></span>

- <span data-ttu-id="d4124-120">**Office 365 Exchange 管理员**角色的成员。</span><span class="sxs-lookup"><span data-stu-id="d4124-120">Members of **Office 365 Exchange administrator** role.</span></span>

- <span data-ttu-id="d4124-121">Security & 合规性中心中**邮件流管理员角色**的成员。</span><span class="sxs-lookup"><span data-stu-id="d4124-121">Members of the **Mail flow administrator role** in the Security & Compliance Center.</span></span> <span data-ttu-id="d4124-122">如果此角色被明确分配给不是全局管理员或 Exchange 管理员角色成员的用户:</span><span class="sxs-lookup"><span data-stu-id="d4124-122">If this role is explicitly assigned to a user who isn't a member of the global administrator or Exchange administrator roles:</span></span>

  - <span data-ttu-id="d4124-123">用户必须直接登录到 Security & 合规性中心[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="d4124-123">The user must log in to the Security & Compliance Center directly at [https://protection.office.com](https://protection.office.com).</span></span>

  - <span data-ttu-id="d4124-124">用户将只具有对邮件流仪表板的只读权限。</span><span class="sxs-lookup"><span data-stu-id="d4124-124">The user will only have read-only permission to the mail flow dashboard.</span></span>

  - <span data-ttu-id="d4124-125">用户将无法访问 Office 365 管理门户。</span><span class="sxs-lookup"><span data-stu-id="d4124-125">The user won't have access to the Office 365 admin portal.</span></span>

<span data-ttu-id="d4124-126">有关 Office 365 全局管理员角色的详细信息, 请参阅[关于 office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="d4124-126">For more information about the Office 365 global administrator role, see [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="d4124-127">有关为用户分配安全 & 合规中心角色的信息, 请参阅[为用户提供对 Security _AMP_ 合规性中心的访问权限](https://docs.microsoft.com/office365/securitycompliance/grant-access-to-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="d4124-127">For information on assigning Security & Compliance Center roles to users, see [Give users access to the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/grant-access-to-the-security-and-compliance-center).</span></span>

## <a name="where-to-find-the-mail-flow-dashboard"></a><span data-ttu-id="d4124-128">在何处查找邮件流仪表板</span><span class="sxs-lookup"><span data-stu-id="d4124-128">Where to find the mail flow dashboard</span></span>

1. <span data-ttu-id="d4124-129">转到安全 & 合规中心, 网址[https://protection.office.com](https://protection.office.com)为。</span><span class="sxs-lookup"><span data-stu-id="d4124-129">Go to the Security & Compliance Center at [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="d4124-130">展开 "**邮件流**", 然后选择 "**仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="d4124-130">Expand **Mail flow** and then select **Dashboard**.</span></span>

   ![Office 365 安全 & 合规中心中的邮件流仪表板](media/mail-flow-dashboard-v2.png)

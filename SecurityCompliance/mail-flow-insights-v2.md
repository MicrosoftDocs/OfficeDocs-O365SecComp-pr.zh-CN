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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4af35fea640c1f4c43464d1adf2e4a9f3b4f780d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252102"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>安全与合规中心内的邮件流见解

> [!NOTE]
> 本主题中所述的功能尚未部署到所有 Office 365 组织中, 可能会发生更改。

管理员可以使用安全 & 合规中心中的邮件流仪表板来发现趋势、见解并采取措施解决与 Office 365 组织中的邮件流相关的问题。

邮件流仪表板中提供的见解、报告和小部件为:

- [邮件流映射报告](mfi-mail-flow-map-report.md)(此报告是新报告, 目前正在部署到 Office 365 中。)

- [域邮件流状态洞察力](mfi-domain-mail-flow-status-insight.md)(此洞察力是新增的, 目前正在部署到 Office 365 中。)

- [SMTP 身份验证客户端报告](mfi-smtp-auth-clients-report.md)(此报告是新报告, 目前正在部署到 Office 365 中。)

- [发件人域洞察力](mfi-sender-domain-insight.md)(此洞察力是新增的, 目前正在部署到 Office 365 中。)

- [未送达报告](mfi-non-delivery-report.md)(此报告是新报告, 目前正在部署到 Office 365 中。)

- [不接受的域报告](mfi-non-accepted-domain-report.md)(此报告是新报告, 目前正在部署到 Office 365 中。)

- [入站和出站邮件流](mfi-outbound-and-inbound-mail-flow.md)

- [队列警报和队列](mfi-queue-alerts-and-queues.md)

- [自动转发的消息报告](mfi-auto-forwarded-messages-report.md)

- [邮件循环见解](mfi-mail-loop-insight.md)

- [慢邮件流规则见解](mfi-slow-mail-flow-rules-insight.md)

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>查看邮件流仪表板所需的权限

邮件流仪表板可用于:

- **Office 365 全局管理员**角色的成员。

- **Office 365 Exchange 管理员**角色的成员。

- Security & 合规性中心中**邮件流管理员角色**的成员。 如果此角色被明确分配给不是全局管理员或 Exchange 管理员角色成员的用户:

  - 用户必须直接登录到 Security & 合规性中心[https://protection.office.com](https://protection.office.com)。

  - 用户将只具有对邮件流仪表板的只读权限。

  - 用户将无法访问 Office 365 管理门户。

有关 office 365 全局管理员角色的详细信息, 请参阅[关于 office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)。

有关为用户分配安全 & 合规中心角色的信息, 请参阅[为用户提供对 Security & 合规性中心的访问权限](https://docs.microsoft.com/office365/securitycompliance/grant-access-to-the-security-and-compliance-center)。

## <a name="where-to-find-the-mail-flow-dashboard"></a>在何处查找邮件流仪表板

1. 转到安全 & 合规中心, 网址[https://protection.office.com](https://protection.office.com)为。

2. 展开 "**邮件流**", 然后选择 "**仪表板**"。

   ![Office 365 安全 & 合规中心中的邮件流仪表板](media/mail-flow-dashboard-v2.png)

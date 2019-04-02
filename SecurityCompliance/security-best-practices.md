---
title: Office 365 的安全最佳做法
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 通过遵循这些建议的最佳实践, 最大程度地降低数据泄露或泄露帐户的潜能。
ms.openlocfilehash: bd4b911cd5972b7d6dc9b55c17e375d326b1d571
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026333"
---
# <a name="security-best-practices-for-office-365"></a>Office 365 的安全最佳做法

通过遵循这些建议的最佳实践, 最大程度地降低数据泄露或泄露帐户的潜能。
  
本文包含最佳实践的快速列表。 有关设置安全性的更深入的分析和信息, 请参阅[Office 365 安全路线图: 前30天、90天和之后的主要优先级](security-roadmap.md)。 在这篇文章中, 您将根据实际攻击的调查查找信息, 其中我们的主要 Microsoft Office 365 cybersecurity 专家为如何评估风险和实现最关键的安全性、合规性和信息提供了指导保护 Office 365 租户的保护控制。 您将了解如何对威胁进行优先级划分, 将威胁转换为技术策略, 然后采用系统化的方法来实现功能和控制。
  
## <a name="use-office-365-secure-score"></a>使用 Office 365 安全分数

安全得分是一种安全分析工具, 它建议您可以执行哪些操作以进一步降低风险。 安全分数查看 Office 365 设置和活动, 并将它们与 Microsoft 建立的基准进行比较。 你将根据最佳安全实践的对齐方式获得分数。 若要详细了解如何获取安全得分并使用它来提高 office 365 组织的安全性, 请参阅[简介 office 365 安全分数](office-365-secure-score.md)。
  
想要试用安全分数？
  
使用已分配了 office 365[关于 office 365 管理员角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)角色的工作或学校帐户,[登录到 Office 365](https://www.office.com/signin)。
  
在上[https://SecureScore.office.com](https://SecureScore.office.com)访问安全分数。
  
## <a name="use-multi-factor-authentication-mfa"></a>使用多重身份验证 (MFA)

通过在正确输入密码后, 通过请求用户在智能手机上确认电话呼叫、短信或应用程序通知, MFA 向强密码策略添加了一层额外的保护。 在进行 MFA 时, 即使用户的密码受到威胁, Office 365 用户帐户仍会受到保护以防未经授权的访问。 帐户受到保护, 因为在满足其他挑战之前, 不向帐户授予访问权限。 已泄露或被盗的密码不足。
  
- [规划 Office 365 部署的多因素身份验证](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)

- [为 Office 365 用户设置多重身份验证](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)

## <a name="use-office-365-cloud-app-security"></a>使用 Office 365 云应用安全

根据您的业务需求来设置策略, 以跟踪异常活动并对其执行操作。 设置与 Office 365 云应用安全有关的通知, 以便管理员可以查看异常或风险的用户活动, 如下载大量数据、多次失败的登录尝试或来自未知或危险的 IP 地址的登录。 对于具有 Office 365 企业版 E5 计划的组织, 可以立即开始使用 office 365 云应用安全。 如果你有一个不同的企业计划, 则可以将 Office 365 云应用安全作为加载项进行购买。
  
- [O365 云应用安全概述](office-365-cas-overview.md)

- [启用 Office 365 云应用安全](turn-on-office-365-cas.md)

## <a name="secure-mail-flow"></a>安全邮件流

在 Exchange Online Protection 中实现丰富的功能集, 并更好地保证每封电子邮件的发件人的身份, 并防止通过电子邮件传输的未知恶意软件、病毒和恶意 url。
  
- 为您的组织配置[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)策略。

- 了解并使用[安全附件和安全链接的高级威胁防护](https://technet.microsoft.com/library/mt148491.aspx)。

- 向[你的组织添加反恶意软件保护](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx)。

- 了解并为用户启用[Office 365 中电子邮件中的安全提示](safety-tips-in-office-365.md)。

- 如果您在 Office 365 中为您的组织使用自定义域, 请设置 SPF、DKIM 和 DMARC 以验证您的组织发送的邮件并帮助防止欺骗:

  - [在 Office 365 中设置 SPF 以帮助防止欺骗](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。

  - [使用 DKIM 验证从 Office 365 中的自定义域发送的出站电子邮件](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。

  - [使用 DMARC 验证 Office 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。

## <a name="enable-mailbox-audit-logging"></a>启用邮箱审核日志记录

在 Office 365 中会自动为你启用一些审核日志记录;但是, 邮箱审核日志记录在默认情况下不会启用。 您可以使用 Exchange Online PowerShell 为 Office 365 中的所有用户邮箱启用审核日志记录。 有关信息, 请参阅[在 Office 365 中启用邮箱审核](https://go.microsoft.com/fwlink/p/?LinkID=626109)。
  
启用审核日志记录后, 可以[在 Office 365 安全&amp;合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md), 以查明登录到用户邮箱的用户、已发送的邮件以及邮箱所有者、委派用户执行的其他活动或管理员。 有关默认情况下包含在 Office 365 审核日志中的邮箱活动的列表, 请参阅[Exchange 邮箱活动](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities)。
  
有关您可以使用审核日志执行的其他操作的信息, 如更改在审核日志中保存条目的时间量, 请参阅[Exchange 2016 中的邮箱审核日志记录](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx)。
  
## <a name="configure-data-loss-prevention-dlp"></a>配置数据丢失防护 (DLP)

DLP 允许您标识敏感数据, 并创建有助于防止用户意外或有意地共享数据的策略。 DLP 在 Office 365 中工作, 包括 Exchange online、SharePoint online 和 OneDrive, 以便您的用户在不中断其工作流的情况下保持合规性。 有关详细信息，请参阅[数据丢失防护策略概述](data-loss-prevention-policies.md)。
  
## <a name="use-customer-lockbox"></a>使用客户密码箱

作为 Office 365 管理员，您可以使用客户锁箱来控制 Microsoft 技术支持工程师在帮助会话期间访问您数据的方式。 如果工程师需要访问您的数据以进行故障排除和解决问题，那么您可以使用客户锁箱批准或拒绝该访问请求。 如果你批准它, 则工程师可以访问数据。 每个请求都有过期时间，一旦问题得以解决，即关闭请求并吊销该访问权限。 客户密码箱包含在 office 365 企业版 E5 计划中, 也可以使用任何其他 Office 365 企业版计划购买单独的订阅。 有关信息, 请参阅[Office 365 客户密码箱请求](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2)。
  
## <a name="try-it-yourself"></a>亲自试用
<a name="SecureScore"> </a>

在将其采用生产环境之前, 请参阅在 Office 365 试用订阅中工作的这些安全功能。
  
- [创建 Office 365 试用订阅](https://technet.microsoft.com/library/mt736406.aspx)

- [为用户帐户配置和测试 MFA](https://technet.microsoft.com/library/mt492459.aspx)

- [配置和测试 Office 365 云应用安全性以通知您全局管理活动](https://technet.microsoft.com/library/mt757250.aspx)

- [配置和测试可疑电子邮件的 ATP](https://technet.microsoft.com/library/mt490479.aspx)

- 在上述每个步骤中检查试用版订阅的[Office 365 安全分数](https://securescore.office.com/)
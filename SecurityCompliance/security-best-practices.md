---
title: Office 365 的安全最佳做法
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
description: 通过遵循这些建议的最佳实践数据违反或受到攻击的帐户的可能性降到最低。
ms.openlocfilehash: 245302af0b08a4ee8183345fc386fe47985c93dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525966"
---
# <a name="security-best-practices-for-office-365"></a>Office 365 的安全最佳做法

通过遵循这些建议的最佳实践数据违反或受到攻击的帐户的可能性降到最低。
  
本文包含最佳实践快速的列表。有关更多深入分析和安全设置的信息，请参阅[Office 365 安全路线图： Top 优先级的前 30 天，90 天及其他认证实战](security-roadmap.md)。在这篇文章，您将发现信息基于现实世界攻击的调查其中我们顶部的 Microsoft Office 365 网络安全专家将提供指导如何评估风险和实现最重要的安全、 遵从性和信息保护控制来保护您的 Office 365 租户。您将了解如何设置优先级威胁、 到技术战略翻译威胁，然后到实现功能和控件使系统的方法。
  
## <a name="use-office-365-secure-score"></a>使用 Office 365 安全分数

安全 Score 是一个安全分析工具，建议您可以以进一步降低风险。安全分数查看您的 Office 365 设置和活动，并对它们进行比较到由 Microsoft 建立一个比较基准。您将获取基于您在与最佳安全做法如何对齐的分数。有关如何获取安全分数和使用它来提高 Office 365 组织的安全性的详细信息，请参阅[介绍 Office 365 安全分数](office-365-secure-score.md)。
  
要试用安全分数？
  
使用工作或学校帐户已分配的[有关 Office 365 管理员角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)的 Office 365 角色，[登录到 Office 365](https://www.office.com/signin)。
  
访问安全分数在[https://SecureScore.office.com](https://SecureScore.office.com)。
  
## <a name="use-multi-factor-authentication-mfa"></a>使用多因素身份验证 (MFA)

MFA 通过要求用户确认电话呼叫、 短信或其智能电话上正确输入自己的密码后应用程序通知向强密码策略额外的保护程序。就地 MFA，与 Office 365 用户帐户仍然会保护针对未经授权的访问，即使用户的密码受到威胁。帐户受到保护，因为后已满足其他质询没有向之前帐户授予访问。受到攻击或被盗密码不就足够了。
  
- [规划多因素身份验证的 Office 365 部署](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [设置多因素身份验证的 Office 365 用户](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## <a name="use-office-365-cloud-app-security"></a>使用 Office 365 云应用程序安全性

将基于您的业务需求，以便跟踪异常活动和对其执行操作的策略设置。设置与 Office 365 云应用程序安全性的通知，以便管理员可以查看异常或 risky 用户活动，如下载大量数据，多失败尝试登录时或登录从一个未知或危险的 IP 地址。对于与 Office 365 企业 E5 计划的组织，您可以立即开始使用 Office 365 云应用程序安全性。如果您有不同的企业计划，您可以作为购买 Office 365 云应用程序安全性。
  
- [O365 云应用程序安全性概述](office-365-cas-overview.md)
    
- [开启 Office 365 云应用安全](turn-on-office-365-cas.md)
    
## <a name="secure-mail-flow"></a>安全邮件流

通过电子邮件传输的实现富客户端功能集 in Exchange Online Protection 和获得更好的保证有关每个电子邮件、 发件人的标识和防御未知的恶意软件、 病毒和恶意 Url。
  
- 配置您的组织的[Office 365 电子邮件防垃圾邮件保护](anti-spam-protection.md)策略。 
    
- 了解有关的信息，然后使用[高级的威胁保护安全的附件和安全的链接](https://technet.microsoft.com/library/mt148491.aspx)。
    
- [添加到您的组织的反恶意软件保护](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx)。
    
- 了解并为用户启用[Office 365 中的电子邮件中的安全提示](safety-tips-in-office-365.md)。 
    
- 若要验证您的组织发送的邮件，并有助于防止欺骗，如果您使用的自定义域名 Office 365 中的组织，将设置 SPF、 DKIM，和 DMARC:
    
  - [设置 Office 365 为了帮助防止欺骗中的 SPF](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx)。
    
  - [使用 DKIM 验证从您在 Office 365 中的自定义域发送出站电子邮件](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx)。
    
  - [使用 DMARC 用于验证 Office 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。
    
## <a name="enable-mailbox-audit-logging"></a>启用邮箱审核日志记录

某些审核日志记录将自动为您启用在 Office 365;但是，邮箱审核日志记录不会默认情况下。使用 Exchange Online PowerShell 中启用了 Office 365 中的所有用户邮箱的审核日志记录。有关信息，请参阅[启用邮箱审核 Office 365 中](https://go.microsoft.com/fwlink/p/?LinkID=626109)。
  
启用后可以审核日志记录您[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)以找出用户已登录到您的用户邮箱，发送消息，并由邮箱所有者、 委派用户执行其他活动或管理员。包含 Office 365 中的邮箱活动的列表默认情况下审核日志，请参阅[Exchange 邮箱活动](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities)。
  
可以使用审核日志执行其他操作的信息，如更改的时间，可以将项保存在审核日志，请参阅[邮箱审核日志记录中 Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx)。
  
## <a name="configure-data-loss-prevention-dlp"></a>配置数据丢失防护 (DLP)

DLP 允许您确定敏感数据，并创建策略，以防止用户无意或有意共享数据。DLP 适用于跨 Office 365，以便用户可以保持兼容不中断其工作流的情况包括 Exchange Online、 SharePoint Online 和 OneDrive。有关详细信息，请参阅[Overview of 数据丢失预防策略](data-loss-prevention-policies.md)。
  
## <a name="use-customer-lockbox"></a>使用客户密码箱

作为 Office 365 管理员，您可以使用客户密码箱控制 Microsoft 支持工程师帮助会话期间访问您的数据的方式。在其中工程师需要访问数据以排除和修复问题的情况下，客户密码箱允许您批准或拒绝访问请求。如果您批准其工程师可以访问的数据。每个请求具有过期时间，一旦解决问题，关闭请求和访问权限被吊销。客户密码箱包含在 Office 365 企业版 5 计划中，或您可以购买与任何其他 Office 365 企业计划单独的订阅。有关信息，请参阅[Office 365 客户密码箱请求](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2)。
  
## <a name="try-it-yourself"></a>亲自试用
<a name="SecureScore"> </a>

请参阅 Office 365 试用版订阅之前采用它们在生产中使用这些安全功能。
  
- [创建 Office 365 试用版订阅](https://technet.microsoft.com/library/mt736406.aspx)
    
- [配置和测试 MFA 用户帐户](https://technet.microsoft.com/library/mt492459.aspx)
    
- [配置和测试 Office 365 云应用程序安全性，通知您的全局管理员活动](https://technet.microsoft.com/library/mt757250.aspx)
    
- [配置和测试 ATP 可疑的电子邮件](https://technet.microsoft.com/library/mt490479.aspx)
    
- 检查每个上述步骤您的试用[Office 365 安全分数](https://securescore.office.com/) 
    


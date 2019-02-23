---
title: Office 365 安全与合规中心中的报告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: '使用 Office 365 安全 & 合规中心获取您的 SharePoint online 和 Exchange online 组织的各种报告, 以及 Azure Active Directory 报告。  '
ms.openlocfilehash: 5f3e510aaacd82095cf502acd5609a204e738bd3
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223541"
---
# <a name="reports-in-the-office-365-security--compliance-center"></a>Office 365 安全与合规中心中的报告

您可以使用 Office 365 Security & 合规中心中的 "**查看报告**" 页快速访问您的 SharePoint online 和 Exchange Online 组织的审核报告。您还可以从 "**查看报告**" 页访问 azure Active Directory (AD) 用户登录报告、用户活动报告和 azure AD 审核日志。这是因为付费 Office 365 订阅包括对 Microsoft Azure 的免费订阅。首次尝试访问这些 Azure 报告时, 您必须完成一次性注册过程。 
  
> [!TIP]
> 若要查看有关 office 365 组织中的活动的其他报告, 请参阅[office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。 
  
 **开始之前**
  
您需要以下权限以查看安全 & 合规性中心中的报告。
  
- 您必须在 Exchange 管理中心 (EAC) 中分配 "安全读者" 角色, 才能在 Security & 合规性中心查看报告。默认情况下, 将此角色分配给 EAC 中的 "组织管理" 和 "安全读者" 角色组。
    
- 必须在 security & 合规性中心中向您分配 "仅查看 dlp 合规性管理" 角色, 才能在 security & 合规性中心中查看 DLP 报告。默认情况下, 将此角色分配给安全 & 合规中心中的合规性管理员、组织管理、安全管理员和安全读者角色组。

- 此外, 您还必须分配到 eac 中的 "仅查看收件人" 角色, 才能查看 eac 中的 DLP 报告。默认情况下, 将此角色分配给 EAC 中的合规性管理、组织管理和仅查看组织管理角色组。
  
 **若要打开 Security & 合规中心中的 "查看报告" 页, 请执行以下操作:**
  
1. 转到 [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)。
    
2. 使用 office 365 组织中的用户帐户的凭据登录 Office 365。
    
在 "**查看报告**" 页上, 您可以查看以下报告类型: 
  
- [EOP 中的审核报告](#auditing-reports)
- [监察审核报告](#supervisory-review-report)
- [数据丢失防护报告](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>审核报告

下表介绍了 Security & 合规性中心的 "**查看报告**" 页上的 "**审核**" 部分中的报告。 
  
|**报表**|**说明**|
|:-----|:-----|
|**Office 365 审核日志报告** <br/> |您可以在 office 365 组织中搜索用户和管理员活动的 office 365 审核日志。此报告包含 Exchange online、SharePoint online、OneDrive for business 和 Azure Active Directory (这是 Office 365 的目录服务) 中的 "用户和管理员活动" 条目。有关详细信息, 请参阅[在 Office 365 安全 & 合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。<br/> |
|**Azure AD 报告** <br/> |若要查找 Office 365 组织中的异常或可疑登录活动, 您可以使用 Microsoft Azure 中的登录和活动报告。您还可以在 Azure AD 审核日志中查看事件。若要在 Azure 中查看报告, 只需单击 "**查看 azure AD 报告**"。有关详细信息, 请参阅:<br/><br/>[在 Office 365 中使用免费的 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)。 <br/> [查看您的访问和使用情况报告](http://go.microsoft.com/fwlink/p/?LinkId=506902)。  <br/> |
|**Exchange 审核报告** <br/> | 您可以使用 Office 365 中的审核功能来跟踪组织管理员对 Exchange Online 配置所做的更改。由 Microsoft 数据中心管理员或委派管理员对 Exchange Online 组织所做的更改也会记录下来。对于 Exchange Online, 管理员审核日志记录在默认情况下处于启用状态, 因此您无需执行任何操作即可将其打开。Exchange Online 还提供了邮箱审核日志记录功能, 使您能够跟踪邮箱所有者以外的邮箱对邮箱的访问。对于要跟踪非所有者访问的每个邮箱, 您必须启用邮箱审核日志记录。<br/>  对于管理员和邮箱审核日志记录, 您可以运行审核报告查看审核日志条目。您还可以导出邮箱和管理员审核日志, 这些日志将在附加到电子邮件的 XML 文件中的24小时内发送给您。<br/><br/>有关导出审核日志的详细信息, 请参阅:  <br/><br/> [导出邮箱审核日志](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [查看和导出数据中心管理员审核日志](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [搜索角色组更改或管理员审核日志](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Exchange 审核报告](http://go.microsoft.com/fwlink/p/?LinkID=395232)。  <br/> |
   
## <a name="supervisory-review-report"></a>监察审核报告

使用监管审核报告, 您可以查看组织中所有监管审核策略的状态。有关详细信息, 请参阅为[您的组织配置监管审核策略](configure-supervision-policies.md)。
  
## <a name="data-loss-prevention-reports"></a>数据丢失防护报告

数据丢失防护 (DLP) 报告包含有关已应用于内容的 DLP 策略和规则的信息, 这些信息包含 Office 365 组织中的敏感数据。您还可以将报告配置为显示基于您的 dlp 策略和规则的 dlp 操作的相关信息。有关详细信息, 请参阅[查看报告以了解数据丢失防护](view-the-dlp-reports.md)。

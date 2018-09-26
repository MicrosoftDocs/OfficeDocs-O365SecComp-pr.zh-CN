---
title: Reports in Office 365 安全性&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/1/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: '使用 Office 365 安全性&amp;合规性中心以获取 SharePoint Online 和 Exchange Online 组织的各种报告以及 Azure Active Directory 报告。  '
ms.openlocfilehash: 019ccc49352db1aaf392287f62fa63f66913e293
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038335"
---
# <a name="reports-in-the-office-365-security-amp-compliance-center"></a>Reports in Office 365 安全性&amp;合规性中心

在 Office 365 安全性，可以使用**查看报告**页上&amp;合规性中心，以快速访问 SharePoint Online 和 Exchange Online 组织的审核报告。您还可以访问 Azure Active Directory (AD) 用户注册报告，用户活动报告，并从**查看报告**页上的 Azure AD 审核日志。这是因为您的付费的 Office 365 订阅包括对 Microsoft Azure 的免费订阅。第一次尝试访问这些 Azure 报告，您将需要完成一次性注册过程。 
  
> [!TIP]
> 若要在 Office 365 组织中查看有关活动的其他报告，请参阅[Office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。 
  
 **开始之前**
  
您需要以下权限才能安全中查看报告&amp;合规性中心。
  
- 您需要分配 Exchange 管理员中心 (EAC) 安全中查看报告中的安全读者角色&amp;合规性中心。默认情况下，此角色分配给在 EAC 中的组织管理和安全读者角色组。
    
- 您必须为其分配安全中的 DLP 合规性管理角色&amp;合规性中心安全中查看 DLP 报告 （和 DLP 策略）&amp;合规性中心。默认情况下，此角色分配给安全中的合规性管理员、 组织管理和安全管理员角色组&amp;合规性中心。
    
此外，您将需要在 EAC 中查看 DLP 报告 （和 DLP 策略） 的数据丢失防护角色分配在 EAC 中。默认情况下，此角色分配给在 EAC 中的合规性管理和组织管理角色组。
  
 **在安全中打开查看报告页&amp;合规性中心：**
  
1. 转到 [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)。
    
2. 登录到 Office 365 使用的 Office 365 组织中的用户帐户的凭据。
    
在**查看报告**页上，您可以查看以下类型的报告： 
  
- [EOP 中的审核报告](#auditing-reports)
- [监督审阅报告](#supervisory-review-report)
- [数据丢失防护报告](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>审核报告

下表介绍在安全中的**查看报告**页上的**审核**部分报告&amp;合规性中心。 
  
|**报告**|**说明**|
|:-----|:-----|
|**Office 365 审核日志报告** <br/> |您可以在 Office 365 组织中搜索用户和管理活动的 Office 365 审核日志。报告中包含条目用户和管理活动中 Exchange Online、 SharePoint Online 的 OneDrive for Business 和 Azure Active Directory，这是 Office 365 的目录服务。有关详细信息，请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。<br/> |
|**Azure AD 报告** <br/> |若要查找的不寻常或可疑登录活动 Office 365 组织中，可以使用登录和活动 Microsoft Azure 中的报告。您还可以查看事件中的 Azure AD 审核日志。若要在 Azure 中查看报告，只需单击**查看 Azure AD 的报告**。有关详细信息，请参阅：<br/><br/>[使用您在 Office 365 中可用的 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)。 <br/> [查看您访问和使用情况的报告](http://go.microsoft.com/fwlink/p/?LinkId=506902)。  <br/> |
|**Exchange 审核报告** <br/> | 可以使用 Office 365 中的审核功能跟踪对 Exchange Online 配置组织的管理员所做的更改。此外会记录由 Microsoft 数据中心管理员或委派管理员对 Exchange Online 组织所做更改。Exchange online，管理员审核日志记录默认情况下，启用，所以您无需执行任何操作即可将其打开。Exchange Online 还提供了邮箱审核日志记录，让您通过邮箱所有者以外的某个人跟踪对邮箱的访问。您必须启用邮箱审核日志记录要跟踪非所有者访问的每个邮箱。<br/>  管理和邮箱审核日志记录，您可以运行审核报告，来查看审核日志条目。您还可以导出邮箱和管理员审核日志，发送到您在 24 小时内附加到电子邮件的 XML 文件中。<br/><br/>有关导出审核日志的详细信息，请参阅：  <br/><br/> [导出邮箱审核日志](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [查看和导出数据中心管理员审核日志](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [搜索角色组更改或管理员审核日志](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Exchange 审核报告](http://go.microsoft.com/fwlink/p/?LinkID=395232)。  <br/> |
   
## <a name="supervisory-review-report"></a>监督审阅报告

使用监督查看报表，您可以在组织中查看所有监督审阅策略的状态。有关详细信息，请参阅[Configure 监督查看为您的组织的策略](configure-supervision-policies.md)。
  
## <a name="data-loss-prevention-reports"></a>数据丢失防护报告

数据丢失防护 (DLP) 报告包含有关 DLP 策略的信息，并且已应用于内容的规则包含 Office 365 组织中的敏感数据。您还可以配置报表以显示有关已根据您的 DLP 策略和规则的 DLP 操作的信息。有关详细信息，请参阅[查看的报告的数据丢失防护](view-the-dlp-reports.md)。

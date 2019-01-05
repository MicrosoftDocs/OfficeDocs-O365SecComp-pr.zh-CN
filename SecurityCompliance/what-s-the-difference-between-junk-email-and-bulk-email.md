---
title: 垃圾邮件和批量邮件之间有什么差异？
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/7/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
description: 客户有时 askwhat 的垃圾邮件和批量邮件之间的区别？本主题的目的是来解释差并提供有关 Exchange Online 和 Exchange Online Protection (EOP) 中对两者可用的不同选项的信息。
ms.openlocfilehash: ea3f27bdd9ec2aa586dd55139825fc90390ca736
ms.sourcegitcommit: b4e69c54c7bf405d37dfeadc5611803bea9554e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/04/2019
ms.locfileid: "27733298"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>垃圾邮件和批量邮件之间有什么差异？

客户有时会询问"垃圾邮件和批量邮件之间有什么差异？"本主题的目地是说明差异，并提供关于适用于 Exchange Online 和 Exchange Online Protection (EOP) 的不同选项的信息。
  
 **什么是垃圾邮件？**
  
垃圾邮件是经服务筛选的未经请求的（并且通常是不必要的）电子邮件。默认情况下，服务根据发送 IP 地址的信誉拒绝垃圾邮件。但是，如果邮件通过 IP 检查，但内容筛选器将其归为垃圾邮件，那么该邮件将会被发送到预期收件人的"垃圾邮件"文件夹。 
  
> [!NOTE]
> [配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中所述，对内容经过筛选的邮件执行的操作是通过 Exchange 管理员中心 (EAC) 中的内容筛选器策略配置的。此外，如果您不同意与垃圾邮件分类，您可以报告您考虑要垃圾邮件或非垃圾邮件向 Microsoft 多种方式[提交垃圾邮件、 非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)中所述的邮件。 
  
 **什么是批量邮件？**
  
批量邮件也称为灰色邮件，是一种更难分类的电子邮件。垃圾邮件是一种持续性的威胁，而批量邮件通常包含广告或营销信息，不太可能重复向您发送。某些用户希望接收批量邮件，并且他们实际上可能是有意注册以接收这些邮件，而其他用户则可能会将这些类型的邮件视为垃圾邮件。例如，某些用户希望接收来自 Contoso Corporation 的广告电子邮件或参加即将举行的网络安全相关会议的邀请，而其他用户则将此类电子邮件视为垃圾邮件。
  
## <a name="how-to-manage-bulk-email"></a>如何管理批量邮件

确定如何管理批量邮件并非轻而易举之事，因为如果将批量邮件归为垃圾邮件，那么希望接收这类邮件的用户可能会提出投诉，并将其提交为错误标记为垃圾邮件的误报（非垃圾邮件）邮件。另一方面，如果允许发送所有批量邮件，那么不希望接收这类邮件的用户可能会提出投诉，并将其提交为错误发送到其收件箱的漏报垃圾邮件（假负）。
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>在内容筛选器策略中启用批量邮件敏感度控件

根据您的公司在批量电子邮件的策略，管理员可以选择分配批量电子邮件的阈值。可以通过在 EAC 中的内容筛选器策略配置设置。签出[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)的步骤。您可以从 1-9，其中 1 将标记为垃圾邮件，大多数批量电子邮件，并 9 允许大多数批量电子邮件传送选择的阈值设置。服务然后执行配置的操作，例如将邮件发送到收件人的垃圾邮件文件夹。 
  


---
title: 关闭 Outlook web 上的报告的垃圾邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
description: 为 Office 365 管理员，您可以关闭功能的报告电子邮件的人员为垃圾邮件。
ms.openlocfilehash: 8ee5ff87408b80c443e4cf950ce49f624096becb
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272037"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>关闭 Outlook web 上的报告的垃圾邮件

使用 web 垃圾电子邮件报告选项，在 Outlook 中[报告垃圾邮件和网络钓鱼诈骗在 web 上的 Outlook 中](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)所述的分析，可以向 Microsoft 发送垃圾、 网络钓鱼和非垃圾邮件。如果您不想要使用这些选项，管理员可以将其关闭通过[Set-owamailboxpolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，需要知道什么？
<a name="sectionSection0"> </a>

- 估计完成时间：5 分钟
    
- 您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Outlook Web App permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp)主题中的"Outlook Web App 邮箱策略"条目。 
    
- 在运行关闭垃圾邮件报告所需的 cmdlet 之前，它可能有助于查看的[Get-owamailboxpolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx)和[Set-owamailboxpolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)主题中的参考信息。 
    
## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>关闭垃圾，欺诈和非垃圾邮件向 Microsoft 报告
<a name="sectionSection1"> </a>

首先，运行以下 cmdlet 来获取要针对其关闭报告的虚拟目录：
  
```
Get-OwaMailboxPolicy -Identity <parameter>
```

下一步，运行以下 cmdlet 来关闭向 Microsoft 报告垃圾邮件和非垃圾邮件：
  
```
Set-OwaMailboxPolicy -Identity <parameter> -ReportJunkEmailEnabled $false
```

例如，以下 cmdlet 将关闭针对虚拟目录 Contoso\owa 的报告：
  
```
Set-OwaMailboxPolicy -Identity Default -ReportJunkEmailEnabled $false
```

## <a name="how-do-you-know-this-worked"></a>您如何知道这有效？
<a name="sectionSection2"> </a>

运行 Get-owamailboxpolicy 检查参数值，并然后访问 web 上的 Outlook 并验证报告垃圾，网络钓鱼和非垃圾邮件选项不可用。您仍将能够将邮件标记为垃圾邮件，欺诈和非垃圾邮件，但您无法将其报告。 
  


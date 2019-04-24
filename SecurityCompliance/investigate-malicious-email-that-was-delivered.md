---
title: 查找并调查已传递的恶意电子邮件 (Office 365 威胁调查和响应
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 了解如何使用威胁调查和响应功能查找和调查恶意电子邮件。
ms.openlocfilehash: d19833a5d2acf69b79cca7e58c5796d967337c9f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254612"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a>查找并调查提供的恶意电子邮件 (Office 365 高级威胁防护计划 2)

[Office 365 高级威胁防护计划 2](office-365-ti.md)使您能够调查让您的用户面临风险的活动, 并采取措施来保护您的组织。 例如, 如果您是组织的安全团队的一部分, 则可以查找并调查传递给用户的可疑电子邮件。 可以使用[威胁资源管理器](get-started-with-ti.md#threat-explorer)执行此操作。
  
> [!IMPORTANT]
> office 365 威胁智能现已成为 office 365 高级威胁防护计划 2, 以及其他威胁防护功能。 若要了解详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。
  
## <a name="before-you-begin"></a>开始之前 .。。

请确保满足以下要求：
  
- 您的组织具有[office 365 高级威胁防护计划 2](office-365-ti.md) , 并[将许可证分配给 Office 365 for business 中的用户](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
    
- 为你的组织启用了[Office 365 审核日志记录](turn-audit-log-search-on-or-off.md)。 
    
- 您的组织具有为反垃圾邮件、反恶意软件、反网络钓鱼等定义的策略。 请参阅[Office 365 高级威胁防护](office-365-atp.md)。
    
- 您是 Office 365 全局管理员, 或者您具有安全管理员或在安全&amp;合规中心中分配的搜索和清除角色。 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。
    
## <a name="dealing-with-suspicious-emails"></a>处理可疑电子邮件

恶意攻击者可能会向你的用户发送邮件, 以尝试对其凭据进行网络钓鱼并获取对公司机密的访问权限! 为避免这种情况, 应使用 Office 365 提供的威胁防护服务, 包括 Exchange Online protection 和高级威胁防护。 但是, 有时攻击者可能会向包含 url 的用户发送邮件, 并在稍后使该 url 指向恶意内容 (恶意软件等)。 或者, 您可能会发现您的组织中的某个用户已受到威胁, 而该用户受到威胁时, 攻击者使用该帐户向公司中的其他用户发送电子邮件。 在清理这两个方案的过程中, 您可能需要从用户收件箱中删除电子邮件。 在这种情况下, 您可以利用威胁资源管理器查找和删除这些电子邮件!
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>查找并删除已传递的可疑电子邮件

> [!TIP]
> [威胁资源管理器](get-started-with-ti.md#threat-explorer)(也称为 "资源管理器") 是一种功能强大的报表, 可用于多种用途, 如查找和删除邮件、标识恶意电子邮件发件人的 IP 地址或启动事件以进行进一步调查。 下面的过程重点介绍如何使用资源管理器查找和删除收件人邮箱中的恶意电子邮件。 
  
1. 请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。 这会将您带到&amp;安全合规中心。 
    
2. 在左侧导航中, 选择 "**威胁管理** \> **资源管理器**"。
    
3. 在 "视图" 菜单中, 选择 "**所有电子邮件**"。<br/>![使用 "视图" 菜单在电子邮件和内容报告之间进行选择](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. 请注意报告中显示的标签, 如 "已**交货**"、"**未知**" 或 "已**传递到垃圾邮件**"。<br/>![显示所有电子邮件的数据的威胁资源管理器](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(根据对组织的电子邮件执行的操作, 可能会看到其他标签, 如 "已**阻止**" 或 "**已替换**"。)
    
5. 在报告中, 选择 "已**传递**" 以仅查看在用户收件箱中结束的电子邮件。<br/>![单击 "传递给垃圾邮件" 将从视图中删除该数据](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. 在图表下方, 查看图表下方的**电子邮件**列表。<br/>![在图表下方, 查看检测到的电子邮件的列表](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. 在列表中, 选择一个项目以查看有关该电子邮件的更多详细信息。 例如, 您可以单击 "主题" 行来查看有关发件人、收件人、附件和其他类似电子邮件的信息。<br/>![您可以查看有关项目的其他信息, 包括详细信息和任何附件](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. 查看有关电子邮件的信息后, 选择列表中的一个或多个项目以激活 **+ 操作**。
    
9. 使用 **+ 操作**列表应用操作, 例如**移到 "已删除**邮件"。 这将从收件人邮箱中删除所选邮件。<br/>![当您选择一个或多个电子邮件时, 可以从多个可用的操作中进行选择](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a>相关主题

[Office 365 高级威胁防护计划2](office-365-ti.md)
  
[防御 Office 365 中的威胁](protect-against-threats.md)
  
[查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)
  


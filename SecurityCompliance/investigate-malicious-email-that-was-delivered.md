---
title: 查找并调查已传递的恶意电子邮件 (Office 365 威胁调查和响应
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
audience: ITPro
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
ms.openlocfilehash: febcf6704b1ba9dc23bf4e698715fb4b929b998b
ms.sourcegitcommit: d3b2bffa8af5f19d97fe9771068c80705b890e85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2019
ms.locfileid: "35414802"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a>查找并调查提供的恶意电子邮件 (Office 365 高级威胁防护计划 2)

[Office 365 高级威胁防护功能](office-365-atp.md)使您能够调查让用户面临风险的活动, 并采取措施来保护您的组织。 例如, 如果您是组织的安全团队的一部分, 则可以查找并调查传递给用户的可疑电子邮件。 可以使用[威胁资源管理器 (或实时检测)](threat-explorer.md)执行此操作。
  
## <a name="before-you-begin"></a>开始之前 .。。

请确保满足以下要求：
  
- 您的组织具有[Office 365 高级威胁防护](office-365-atp.md)(plan 1 或 plan 2), 并将[许可证分配给用户](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。
    
- 为你的组织启用了[Office 365 审核日志记录](turn-audit-log-search-on-or-off.md)。 
    
- 您的组织具有为反垃圾邮件、反恶意软件、反网络钓鱼等定义的策略。 请参阅防御[Office 365 中的威胁](protect-against-threats.md)。
    
- 您是 Office 365 全局管理员, 或者您具有安全管理员或在安全&amp;合规中心中分配的搜索和清除角色。 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。
    
## <a name="dealing-with-suspicious-emails"></a>处理可疑电子邮件

恶意攻击者可能会向你的用户发送邮件, 以尝试对其凭据进行网络钓鱼并获取对公司机密的访问权限! 为避免这种情况, 应使用 Office 365 中的威胁防护服务, 包括[Exchange Online protection](eop/exchange-online-protection-overview.md)和[高级威胁防护](office-365-atp.md)。 但是, 有时攻击者可能会向包含 URL 的用户发送邮件, 并在稍后使该 URL 指向恶意内容 (恶意软件等)。 或者, 您可能会发现您的组织中的某个用户已受到威胁, 而该用户受到威胁时, 攻击者使用该帐户向公司中的其他用户发送电子邮件。 在清理这两个方案的过程中, 您可能需要从用户收件箱中删除电子邮件。 在这种情况下, 您可以利用[威胁浏览器 (或实时检测)](threat-explorer.md)来查找和删除这些电子邮件!

## <a name="where-re-routed-emails-are-located-after-actions-are-taken"></a>在执行操作后, 重新路由的电子邮件位于何处

威胁资源管理器实时检测已在 "传递" 状态下添加了 "传递操作" 和 "送达位置" 字段。 这将使您的电子邮件土地的更完整的了解。 此更改的目标部分是使搜索更易于进行安全操作人员, 但最终结果是了解问题电子邮件的位置。

传递状态现已分为两列:

- **传递操作**-此电子邮件的状态是什么？
- **送达位置**-此电子邮件的路由结果

传递操作是由于现有策略或检测而导致对电子邮件执行的操作。 以下是电子邮件可能执行的操作:

1. **传递**–将电子邮件传递到用户的收件箱或文件夹, 用户可以直接访问它。
2. **Junked** –将电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹, 并且用户可以访问其 "垃圾邮件" 或 "已删除" 文件夹中的电子邮件。
3. 已**阻止**–任何已隔离、失败或已丢弃的电子邮件。 用户完全无法访问它!
4. **已替换**–所有恶意附件都被替换为 .txt 文件的电子邮件, 这些文件的状态为 "恶意附件"。
 
"送达位置" 显示运行送达后的策略和检测结果。 它已链接到传递操作。 添加此字段是为了深入了解在发现问题邮件时所采取的操作。 以下是送达位置的可能值:

1. **收件箱或文件夹**–电子邮件位于收件箱或文件夹中 (根据您的电子邮件规则)。
2. **本地或外部**–邮箱在云上不存在, 但在本地。
3. **垃圾邮件文件夹**–在用户的 "垃圾邮件" 文件夹中的电子邮件。
4. "**已删除**邮件" 文件夹–用户的 "已删除邮件" 文件夹中的电子邮件。
5. **隔离**–隔离中的电子邮件, 并且不在用户的邮箱中。
6. **失败**–电子邮件无法访问邮箱。
7. **丢弃**–电子邮件在邮件流中的某个位置丢失。
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>查找并删除已传递的可疑电子邮件

> [!TIP]
> 威胁资源管理器 (有时称为资源管理器) 是一种功能强大的报告, 可用于多种用途, 如查找和删除邮件、标识恶意电子邮件发件人的 IP 地址或启动事件以进行进一步调查。 下面的过程重点介绍如何使用资源管理器查找和删除收件人邮箱中的恶意电子邮件。

若要查看对前一个传递状态字段的更改 (现在为传递操作和送达位置), 请执行以下操作: 

1. 请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。 这会将您带到&amp;安全合规中心。 
    
2. 在左侧导航中, 选择 "**威胁管理** \> **资源管理器**"。
<!--Comment>
![Threat Explorer with Delivery Action and Delivery Location fields.](media/ThreatExFields.PNG)

    
3. In the View menu, choose **All email**.<br/>![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.<br/>![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only emails that ended up in users' inboxes.<br/>![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.<br/>![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.<br/>![You can view additional information about an item, including details and any attachments](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.<br/>![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
-->
## <a name="related-topics"></a>相关主题

[Office 365 高级威胁防护计划2](office-365-ti.md)
  
[防御 Office 365 中的威胁](protect-against-threats.md)
  
[查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)
  


---
title: 查找并调查 Office 365 中提供的恶意电子邮件
keywords: TIMailData-Inline，安全事件，事件，ATP PowerShell，电子邮件恶意软件，已损坏的用户，电子邮件网络钓鱼诈骗，电子邮件恶意软件，读取电子邮件头，读取邮件头，打开电子邮件头
ms.author: deniseb
author: denisebmsft
manager: dansimp
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
ms.openlocfilehash: a57e72c74a7b2f819ecee7fbf604795e4a094693
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761678"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-in-office-365"></a>查找并调查 Office 365 中提供的恶意电子邮件

[Office 365 高级威胁防护](office-365-atp.md)使您能够调查将组织中的人员面临风险的活动，并采取措施保护组织。 例如，如果您是组织的安全团队的一部分，则可以查找并调查已传递的可疑电子邮件。 可以使用[威胁资源管理器（或实时检测）](threat-explorer.md)执行此操作。
  
## <a name="before-you-begin"></a>开始之前 .。。

请确保满足以下要求：
  
- 您的组织具有[Office 365 高级威胁防护](office-365-atp.md)，并将[许可证分配给用户](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。
    
- 为你的组织启用了[Office 365 审核日志记录](turn-audit-log-search-on-or-off.md)。 
    
- 您的组织具有为反垃圾邮件、反恶意软件、反网络钓鱼等定义的策略。 请参阅防御[Office 365 中的威胁](protect-against-threats.md)。
    
- 您是 Office 365 全局管理员，或者您具有安全管理员或在安全&amp;合规中心中分配的搜索和清除角色。 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。 对于某些操作，还必须分配新的预览角色。 

#### <a name="preview-role-permissions"></a>预览角色权限

若要执行某些操作（如查看邮件头或下载电子邮件内容），您必须具有一个名为*Preview*的新角色，并将其添加到另一个相应的 Office 365 角色组。 下表阐明了所需的角色和权限。

|活动  |角色组 |是否需要预览角色？  |
|---------|---------|---------|
|使用威胁浏览器（和实时检测）分析威胁     |Office 365 全局管理员 <br> Security Administrator <br> 安全读者     | 否   |
|使用威胁资源管理器（和实时检测）查看电子邮件的邮件头，以及预览和下载隔离的电子邮件    |Office 365 全局管理员 <br> Security Administrator <br>安全读者   |       否  |
|使用威胁浏览器查看邮件头并下载传递给邮箱的电子邮件     |Office 365 全局管理员 <br>Security Administrator <br> 安全读者 <br> 预览   |   是      |

> [!NOTE]
> *预览*是一个角色，而不是角色组;必须将预览角色添加到 Office 365 的现有角色组中。 Office 365 全局管理员角色分配有 Microsoft 365 管理中心（[https://admin.microsoft.com](https://admin.microsoft.com)），安全管理员和安全读者角色是在 Office 365 安全 & 合规中心（[https://protection.office.com](https://protection.office.com)）中分配的。 若要了解有关角色和权限的详细信息，请参阅[Office 365 Security & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>查找并删除已传递的可疑电子邮件

威胁资源管理器是一种功能强大的报告，可用于多种用途，如查找和删除邮件、标识恶意电子邮件发件人的 IP 地址或启动事件以进行进一步调查。 下面的过程重点介绍如何使用资源管理器查找和删除收件人邮箱中的恶意电子邮件。

1. 请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。 这会将您带到&amp;安全合规中心。 
    
2. 在左侧导航中，选择 "**威胁管理** \> **资源管理器**"。

    ![具有 "传递操作" 和 "送达位置" 字段的资源管理器。](media/ThreatExFields.PNG)

    您可能会注意到 "新建**特殊操作**" 列。 此功能旨在告诉管理员处理电子邮件的结果。 可以在与**传递操作**和**传递位置**相同的位置访问 "**特殊操作**" 列。 在威胁资源管理器的电子邮件日程表结束时，可能会更新特殊操作，这是旨在使求职体验更适合管理员的新功能。

3. 若要查看电子邮件日程表，请单击电子邮件的主题，然后单击 "**电子邮件日程表**"。 （它显示在面板上的其他标题中，如**摘要**或**详细信息**。）

    打开电子邮件日程表后，您应该会看到一个表，告诉您该邮件的传递后事件。 对于没有对电子邮件的进一步事件的情况，您应该会看到原始传递的单个事件，该事件指出**了类似于****网络钓鱼**等判定的结果。 该选项卡还具有导出整个电子邮件时间线的选项，此操作将导出该选项卡上的所有详细信息，以及有关电子邮件的详细信息（如主题、发件人、收件人、网络和邮件 ID 等）。

    电子邮件日程表在随机时减少，因为检查不同位置的时间较少，以尝试了解自电子邮件到达后发生的事件。 当电子邮件上的多个事件发生时，或在同一时间结束时，这些事件将显示在 "日程表" 视图中。 
    
    在 "**特殊操作**" 列中捕获对您的邮件执行送达后发生的一些事件。 将电子邮件时间线中的信息与在送达电子邮件后进行的特殊操作组合在一起，管理员可以深入了解其策略的工作方式，即最后路由电子邮件的方式，在某些情况下，最终评估是什么。 

4. 在 "**视图**" 菜单中，选择 "**所有电子邮件**"。

    ![使用 "视图" 菜单在电子邮件和内容报告之间进行选择](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    请注意报告中显示的标签，如 "已**交货**"、"**未知**" 或 "已**传递到垃圾邮件**"。

    ![显示所有电子邮件的数据的威胁资源管理器](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    （根据对组织的电子邮件执行的操作，可能会看到其他标签，如 "已**阻止**" 或 "**已替换**"。）
    
6. 在报告中，选择 "已**传递**" 以仅查看在用户收件箱中最后结束的电子邮件。

    ![单击 "传递给垃圾邮件" 将从视图中删除该数据](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
7. 在图表下方，查看图表下方的**电子邮件**列表。

    ![在图表下方，查看检测到的电子邮件的列表](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
8. 在列表中，选择一个项目以查看有关该电子邮件的更多详细信息。 例如，您可以单击 "主题" 行来查看有关发件人、收件人、附件和其他类似电子邮件的信息。

    ![您可以查看有关项目的其他信息](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
9. 查看有关电子邮件的信息后，选择列表中的一个或多个项目以激活 **+ 操作**。
    
10. 使用 **+ 操作**列表应用操作，例如**移到 "已删除**邮件"。 这将从收件人邮箱中删除所选邮件。

    ![当您选择一个或多个电子邮件时，可以从多个可用的操作中进行选择](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## <a name="dealing-with-suspicious-email-messages"></a>处理可疑电子邮件

恶意攻击者可能会向组织中的人员发送邮件，以尝试对其凭据进行网络钓鱼并获取对公司机密的访问权限。 为了帮助防止这种情况，请使用 Office 365 中的威胁防护服务，包括[Exchange Online protection](eop/exchange-online-protection-overview.md)和[高级威胁防护](office-365-atp.md)。 但是，偶尔会发生攻击者发送包含仅指向恶意内容（如恶意软件）的链接（URL）的电子邮件。 或者，您可能会发现组织中的某个人已受到威胁，而他们受到威胁时，攻击者使用其帐户向组织中的其他人发送电子邮件。 在处理上述任一情况的过程中，您可以从用户收件箱中删除可疑电子邮件。 若要执行此操作，可以使用[威胁资源管理器](threat-explorer.md)。

## <a name="finding-re-routed-email-messages-after-actions-are-taken"></a>在执行操作后查找重新路由的电子邮件

威胁资源管理器为安全操作团队提供调查可疑电子邮件所需的详细信息。 您的安全操作团队可以执行以下操作：

- [查看电子邮件头并下载电子邮件正文](#view-the-email-headers-and-download-the-email-body) 

- [检查传递操作和位置](#check-the-delivery-action-and-location)

- [查看你的电子邮件的日程表](#view-the-timeline-of-your-email)

### <a name="view-the-email-headers-and-download-the-email-body"></a>查看电子邮件头并下载电子邮件正文

在威胁资源管理器中，预览电子邮件头和下载电子邮件正文的能力是强大的功能。 必须分配适当的[权限](permissions-in-the-security-and-compliance-center.md)。 请参阅[预览角色权限](#preview-role-permissions)。

若要访问您的邮件头和电子邮件下载选项，请按照以下步骤操作： 

1. 请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。 这会将您带到&amp;安全合规中心。 
    
2. 在左侧导航中，选择 "**威胁管理** \> **资源管理器**"。

3. 单击 "威胁资源管理器" 表中的主题。 

    这将打开浮出控件，同时定位页眉预览和电子邮件下载链接。

    ![在页面上具有下载和预览链接的威胁资源管理器浮出控件。](media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> 此功能不会显示在用户邮箱中从未找到的电子邮件，如果删除电子邮件或传递失败，则可能会发生这种情况。 在从用户邮箱中删除电子邮件的情况下，管理员会看到 "找不到邮件" 错误消息。

### <a name="check-the-delivery-action-and-location"></a>检查传递操作和位置

在[威胁资源管理器（和实时检测）](threat-explorer.md)中，您现在具有**传递操作**列和 "**传递位置**" 列，而不是以前的 "**传递状态**" 列。 这将导致您的电子邮件位于何处的更完整的图片。 此更改的目标部分是使搜索更易于进行安全操作，但最终结果是，快速了解问题电子邮件的位置。

传递状态现已分为两列：

- **传递操作**-此电子邮件的状态是什么？

- **送达位置**-此电子邮件的路由结果

传递操作是由于现有策略或检测而导致对电子邮件执行的操作。 以下是电子邮件可能执行的操作：

- **传递**–将电子邮件传递到用户的收件箱或文件夹，用户可以直接访问它。

- **Junked** –将电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹，并且用户可以访问其 "垃圾邮件" 或 "已删除" 文件夹中的电子邮件。

- 已**阻止**–隔离、失败或丢弃的任何电子邮件。 （这是用户完全无法访问的。）

- **已替换**–所有恶意附件都被替换为 .txt 文件的电子邮件，这些文件的状态为 "恶意附件"。
 
"送达位置" 显示运行送达后的策略和检测结果。 它已链接到传递操作。 添加此字段是为了深入了解在发现问题邮件时所采取的操作。 以下是送达位置的可能值：

- **收件箱或文件夹**–电子邮件位于收件箱或文件夹中（根据您的电子邮件规则）。

- **本地或外部**–邮箱在云上不存在，但在本地。

- **垃圾邮件文件夹**–电子邮件位于用户的垃圾邮件文件夹中。

- "**已删除邮件" 文件夹**–电子邮件位于用户的 "已删除邮件" 文件夹中。

- **隔离**–隔离的电子邮件，而不是用户邮箱中的电子邮件。

- **失败**–电子邮件无法访问邮箱。

- **丢弃**–电子邮件在邮件流中的某个位置丢失。

### <a name="view-the-timeline-of-your-email"></a>查看你的电子邮件的日程表
  
**电子邮件日程表**是威胁资源管理器中的一个字段，可使您的安全操作团队更轻松地使用查找。 当电子邮件上的多个事件同时发生或在同一时间结束时，这些事件将显示在 "日程表" 视图中。 在 "**特殊操作**" 列中捕获到电子邮件的传递后发生的一些事件。 将电子邮件的时间线中的信息与所执行的任何特殊操作组合在一起，可使管理员深入了解策略和威胁处理（例如邮件路由的位置，在某些情况下，在某些情况下，最终评估是什么）。
  
## <a name="related-topics"></a>相关主题

[Office 365 高级威胁防护](office-365-ti.md)
  
[防御 Office 365 中的威胁](protect-against-threats.md)
  
[查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)
  


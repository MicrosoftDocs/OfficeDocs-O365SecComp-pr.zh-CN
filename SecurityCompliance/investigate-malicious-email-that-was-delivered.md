---
title: 查找并调查恶意电子邮件已送达 （Office 365 威胁智能）
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/6/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
description: 了解如何使用威胁智能来查找和调查恶意电子邮件。
ms.openlocfilehash: 9d63bd69e11bca4bc76fa6d6d00a429ed1aac508
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525237"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-threat-intelligence"></a>查找并调查恶意电子邮件已送达 （Office 365 威胁智能）

[Office 365 威胁智能](office-365-ti.md)可以调查您的用户处于风险，采取措施来保护您的组织的活动。例如，如果您是组织的安全工作组的一部分，您可以查找和调查的可疑邮件已送达您的用户。您可以使用[威胁资源管理器](get-started-with-ti.md#threat-explorer)来执行此操作。
  
> [!NOTE]
> Office 365 威胁智能是在 Office 365 企业 E5 中可用。如果您的组织使用的另一个 Office 365 企业版订阅，可以作为购买 Office 365 威胁智能。(作为全局管理员，在 Office 365 管理中心中，选择**帐单** \> **添加订阅**。)有关详细信息，请参阅[Office 365 平台服务说明： Office 365 安全性&amp;合规性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[购买或编辑企业的 Office 365 的加载项](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。 
  
## <a name="before-you-begin"></a>开始之前...

请确保满足以下要求：
  
- 您的组织具有[Office 365 威胁智能](office-365-ti.md)和[分配给为企业的 Office 365 中的用户的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。
    
- [Office 365 审核日志记录](turn-audit-log-search-on-or-off.md)处于打开状态为您的组织。 
    
- 贵组织拥有的反垃圾邮件、 反恶意软件、 防钓鱼等定义的策略。请参阅[威胁管理 Office 365 安全性&amp;合规性中心](threat-management.md)。
    
- 您是 Office 365 全局管理员，或您具有安全管理员或分配安全中搜索和清除角色&amp;合规性中心。请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。
    
## <a name="dealing-with-suspicious-emails"></a>处理可疑的电子邮件

恶意攻击者可能将邮件发送到您的用户尝试和网络钓鱼诈骗其凭据，并可以访问您的公司机密 ！为了防止此，您应使用提供的 Office 365，包括 Exchange Online Protection 和高级威胁保护威胁保护服务。但是，有攻击者可以向您包含 URL 的用户发送邮件并仅更高版本上对恶意内容 （恶意软件等） 的 URL 点时的时间。此外，您可能会发现晚已泄露您组织内的用户，和时该用户已泄露，攻击者使用该帐户向公司中的其他用户发送电子邮件。作为清理这两种方案的一部分，您可能要从用户收件箱中删除电子邮件。在以下情况下，您可以利用威胁资源管理器中，找到并删除这些邮件 ！
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>查找并删除可疑的已发送的电子邮件

> [!TIP]
> [威胁资源管理器](get-started-with-ti.md#threat-explorer)（也称为资源管理器） 是一个强大的报表，可以提供多种用途，如查找和删除邮件、 标识恶意电子邮件发件人的 IP 地址或启动进一步调查事件。下面的过程重点介绍使用资源管理器查找并从收件人邮箱删除恶意电子邮件。 
  
1. 转到[https://protection.office.com](https://protection.office.com)和 Office 365 中使用您的工作或学校帐户登录。您将转到安全&amp;合规性中心。 
    
2. 在左侧导航窗格中，选择**威胁管理** \> **资源管理器**。
    
3. 在视图菜单中，选择**所有电子邮件**。
    
    ![使用视图菜单选择之间电子邮件和内容的报告](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. 请注意报表，如**传递**、**未知**，或**传递到垃圾**中显示的标签。
    
    ![威胁资源管理器中显示的所有电子邮件的数据](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
  
    （具体取决于您的组织的电子邮件所采取的操作，您可能会看到更多标签，如**已阻止**或**取代**。）
    
5. 在报表中，选择以查看仅用户的收件箱中的最后的电子邮件已**传递**。 
    
    ![单击"传递到垃圾邮件"从视图中删除该数据](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. 图表，下方查看位于图表下方的**电子邮件**列表。 
    
    ![图表，下方查看检测到的电子邮件的列表](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. 在列表中，选择一个项目以查看有关该电子邮件的详细信息。例如，您可以单击以查看信息发件人、 收件人、 附件和其他类似的电子邮件的主题行。
    
    ![您可以查看关于该项，包括详细信息和任何附件的其他信息](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. 查看有关电子邮件的信息后, 激活 **+ 操作**列表中选择一个或多个项目。
    
9. 使用 **+ 操作**列表中应用操作，如**移动到已删除**项目。这将从收件人的邮箱中删除选定的邮件。 
    
    ![选择一个或多个电子邮件时，您可以从几个可用操作](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a>相关主题

[Office 365 威胁智能](office-365-ti.md)
  
[Office 365 中的威胁防护](protect-against-threats.md)
  
[Office 365 高级威胁保护的视图报告](view-reports-for-atp.md)
  


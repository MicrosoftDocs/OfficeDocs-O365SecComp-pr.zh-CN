---
title: 查看安全中的电子邮件安全报告&amp;合规性中心
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
description: 了解如何查找和使用电子邮件安全报告为您的组织与 Office 365 企业版。电子邮件安全报告可安全中&amp;合规性中心。
ms.openlocfilehash: ea5d60393809ef924d51435b695062fe51e772bd
ms.sourcegitcommit: e0c6f99d5514d8da8a70d9bd3616d1a1c0851254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2018
ms.locfileid: "25552390"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a>查看安全中的电子邮件安全报告&amp;合规性中心

安全中可用的各种电子邮件安全报告&amp;合规性中心，以帮助您查看 Office 365 中的反垃圾邮件和反恶意软件功能如何保护您的组织。如果您拥有[所需的权限](#what-permissions-are-needed-to-view-these-reports)，则可以安全中查看这些报告&amp;，转到**报告**的合规性中心\>**仪表板**。
  
![安全&amp;合规性中心仪表板可帮助您看到正常高级威胁保护](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
您的电子邮件安全报告包括：
  
- [威胁保护状态报告](view-email-security-reports.md#tps)（新） ！ 
    
- [恶意软件检测报告](view-email-security-reports.md#maldet)
    
- [顶部的恶意软件报告](#top-malware-report)
    
- [顶部的发件人和收件人报告](view-email-security-reports.md#topsenders)
    
- [欺骗邮件报告](#spoof-mail-report)
    
- [垃圾邮件检测报告](#spam-detections-report)
    
- [发送和接收电子邮件报告](view-email-security-reports.md#sentreceivedemail)
    
- [用户报告的邮件报告](view-email-security-reports.md#userreported)（新） ！ 
    
## <a name="threat-protection-status-report-new"></a>威胁 （新） ！ 的保护状态报告

新的**威胁保护状态**报告是显示的已检测和阻止的 Exchange Online Protection 恶意电子邮件的智能报告。此报表显示有关标识为恶意软件或网络钓鱼尝试的电子邮件的信息。 

> [!NOTE]
> 威胁保护状态报告是适用于[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); 客户但是，ATP 客户威胁保护状态报告中显示的信息将可能包含比 EOP 客户可能会看到不同的数据。例如，EOP 客户可以查看关于恶意软件检测到的电子邮件，但不是[SharePoint Online、 OneDrive 或的 Microsoft 团队中检测到恶意文件](atp-for-spo-odb-and-teams.md)的信息，ATP 特定功能的信息。（[有关 ATP 报告详细了解](view-reports-for-atp.md)。）
  
若要查看此报告中，安全中&amp;合规性中心中，转到**报告** \> **仪表板** \> **威胁保护状态**。
  
![威胁保护状态报告](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
当您首次打开威胁保护状态报告时，报告将显示数据的过去七天默认设置。但是，您可以单击**筛选器**，更改为 90 天的详细信息的日期范围。用于查看的有效性和影响组织的 Exchange Online Protection 功能，以及长期趋势分析此报告。 
  
![威胁保护状态报告筛选器](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
您还可以选择是否要查看的电子邮件标识为恶意数据，电子邮件标识为网络钓鱼尝试或电子邮件标识为包含恶意软件。
  
![威胁保护状态报表视图选项](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a>恶意软件检测报告

**恶意软件检测**报告将显示多少传入和传出邮件检测为包含恶意软件为您的组织。 
  
若要查看此报告中，安全中&amp;合规性中心中，转到**报告** \> **仪表板** \> **恶意软件检测**。
  
![恶意软件检测报告示例](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
类似于其他报表，如威胁保护状态报告，报表显示数据的过去七天默认情况下。但是，您可以选择要更改的日期范围的**筛选器**。 
  
## <a name="top-malware-report"></a>顶部的恶意软件报告

**顶部恶意软件**报告将显示的各种通过 Exchange Online 中检测到的恶意软件。 
  
若要查看此报告中，安全中&amp;合规性中心中，转到**报告** \> **仪表板** \> **顶部恶意软件**。
  
![SCC-EOP 流行恶意软件](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
当鼠标悬停在楔入饼图图表中时，您可以看到的一种恶意软件和多少邮件检测为具有该恶意软件的名称。
  
单击 （或点击） 报表以在新浏览器窗口中，您可以在哪里找到报告的更详细的视图中打开它。
  
![此报表显示顶部恶意软件检测到您的组织](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
下面的图表中，您将看到检测到恶意软件和消息数量为具有该恶意软件检测到的列表。
  
## <a name="top-senders-and-recipients-report"></a>顶部的发件人和收件人报告

**前发件人和收件人**报告是显示在顶部的电子邮件发件人饼图。 
  
若要查看此报告中，安全中&amp;合规性中心中，转到**报告** \> **仪表板** \> **前发件人和收件人**。
  
![若要查看此报告中，安全中&amp;合规性中心中，转到报告\>仪表板\>前发件人和收件人](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
当鼠标悬停在楔入饼图图表中时，您可以看到发送或接收邮件的计数。
  
单击 （或点击） 报表以在新浏览器窗口中，您可以在哪里找到报告的更详细的视图中打开它。
  
使用**显示的数据**列表选择是否查看数据的顶级发件人、 接收器、 垃圾邮件收件人和垃圾邮件收件人。您还可以查看者收到的高级威胁保护由检测到恶意软件。 
  
![使用显示数据的列表，以查看特定信息](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
下面的图表，您将看到用户的主要电子邮件发件人或收件人已，以及发送或接收的给定的时间段邮件的计数。
  
## <a name="spoof-mail-report"></a>欺骗邮件报告

**欺骗邮件**报告将显示多少欺骗邮件检测到，，其中，哪些已被视为"好"（欺骗邮件完成合法的业务原因）。 
  
若要查看此报告中，安全中&amp;合规性中心中，转到**报告** \> **仪表板** \> **欺骗邮件**。
  
![若要查看此报告中，安全中&amp;合规性中心中，转到报告\>仪表板\>欺骗邮件](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
当鼠标悬停在一天在图表中时，您可以看到多少欺骗邮件一起提供。
  
单击 （或点击） 报表以在新浏览器窗口中，您可以在哪里找到报告的更详细的视图中打开它。
  
## <a name="spam-detections-report"></a>垃圾邮件检测报告

**垃圾邮件检测**报告将显示阻止的 Exchange Online 的所有垃圾邮件内容。 
  
若要查看此报告中，安全中&amp;合规性中心中，转到**报告** \> **仪表板** \> **垃圾邮件检测**。
  
![若要查看此报告中，安全中&amp;合规性中心中，转到报告\>仪表板\>EOP 垃圾邮件检测](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
当鼠标悬停在一天在图表中时，您可以看到多少项目已阻止该天，以及如何根据这些项目进行分类。例如，您可以看到多少垃圾邮件已筛选，和项数来自已阻止的 Internet 协议 (IP) 地址。
  
单击 （或点击） 报表以在新浏览器窗口中，您可以在哪里找到报告的更详细的视图中打开它。
  
![垃圾邮件检测报告告诉您多少垃圾邮件已被阻止或筛选](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
下面的图表中，您将看到检测到的垃圾邮件项目的列表。选择一个项目以查看其他信息，如入站或出站垃圾邮件项是否、 邮件 ID、 和其收件人。
  
## <a name="sent-and-received-email-report"></a>发送和接收电子邮件报告

**发送和接收电子邮件**报告是智能报表的显示信息传入和传出电子邮件，其中包括垃圾邮件检测、 恶意软件和电子邮件标识为"良好"。 
  
若要查看此报告中，安全中&amp;合规性中心中，转到**报告** \> **仪表板** \> **发送和接收电子邮件**。
  
![若要查看此报告中，安全中&amp;合规性中心中，转到报告\>仪表板\>发送和接收电子邮件](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
当鼠标悬停在一天在图表中时，您可以看到多少邮件发自中，并根据这些邮件进行分类。例如，您可以看到多少邮件检测为包含恶意软件、 和多少已标识为垃圾邮件。
  
单击 （或点击） 报表以在新浏览器窗口中，您可以在哪里找到报告的更详细的视图中打开它。
  
**按**列表可用于查看由类型或方向 （传入和传出） 的信息。 
  
![使用中断下的列表中查看信息类型或方向](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
下面的图表，您将看到电子邮件类别，例如**GoodMail**、 **SpamContentFiltered**，等的列表。选择要查看其他信息，如的恶意软件、 所采取的操作和是否电子邮件类别的传入或传出。
  
![此报告将向您介绍有关反恶意软件、 反垃圾邮件和其他邮件检测](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report-new"></a>用户报告的邮件报告 （新） ！

**用户报告的邮件**报告将显示有关用户报告为垃圾邮件、 网络钓鱼诈骗或良好的邮件使用[邮件报告加载项](enable-the-report-message-add-in.md)的电子邮件的信息。
  
为每个邮件，包括传递原因，这样的垃圾邮件策略异常或为组织配置的邮件流规则提供了详细信息。若要查看详细信息，在用户报告列表中，选择一个项目，然后查看**摘要**和**详细信息**选项卡上的信息。 
  
![User-Reported 邮件报告将显示尝试标记为垃圾、 不是垃圾邮件或网络钓鱼邮件用户。](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
若要查看此报告中，安全中&amp;合规性中心中，执行下列选项之一：
  
- 转到**威胁管理** \> **仪表板** \> **用户报告的邮件**。
    
- 转到**威胁管理** \> **审阅** \> **用户报告的邮件**。
    
![安全中&amp;合规性中心中，选择威胁管理\>审阅\>用户报告的邮件](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> 为了让用户报告的邮件报告正常工作，为您的 Office 365 环境**必须打开审核日志记录**。这通常是具有审核日志角色分配在 Exchange Online 的人。有关详细信息，请参阅[打开或关闭，打开 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a>查看这些报告需要哪些权限？

为了查看和使用本文中所述的电子邮件安全报告，您必须具有安全中分配相应角色&amp;合规性中心和 Exchange Admin Center。
  
|**角色组**|**其中分配**|**了解更多**|
|:-----|:-----|:-----|
| 以下各项之一：  <br/><br/>-组织管理  <br/>--安全管理员  <br/>--安全读者  <br/> |安全&amp;合规性中心  <br/> |[Office 365 安全性权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md) <br/> |
| 以下各项之一：  <br/><br/>-组织管理  <br/>-仅查看组织管理  <br/>-View-Only Recipients 角色  <br/>-合规性管理  <br/> |Exchange 管理中心  <br/> |[Exchange Online 中的功能权限](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a>如果报表不显示数据？

如果您不会在报表中看到数据，请仔细检查您的策略设置正确。若要了解详细信息，请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。
  
## <a name="related-topics"></a>相关主题

[Office 365 反垃圾邮件保护](anti-spam-protection.md)
  
[报告和 Office 365 安全性见解&amp;合规性中心](reports-and-insights-in-security-and-compliance.md)
  
[在安全中创建报表的计划&amp;合规性中心](create-a-schedule-for-a-report.md)
  
[设置和下载安全中的自定义报表&amp;合规性中心](set-up-and-download-a-custom-report.md)
  


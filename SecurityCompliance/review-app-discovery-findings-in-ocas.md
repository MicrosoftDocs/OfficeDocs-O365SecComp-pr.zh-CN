---
title: 查看 Office 365 云应用安全中的应用发现结果
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
ms.assetid: aac65513-e75e-4c82-a668-9a6604dd9f9d
description: 查看高级安全管理中的应用程序发现报告可帮助您了解有关如何在组织中的人员使用云应用程序的详细信息。您已创建应用程序发现报告使用从防火墙和代理日志文件后，查看应用程序发现仪表板中的结果。
ms.openlocfilehash: ddf3826f5aac9d3c837cf66f1b97b4650df70f32
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706256"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a>查看 Office 365 云应用安全中的应用发现结果
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|使用率 ***|
|:-----|:-----|:-----|:-----|
|[启动评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |在这里 ！  <br/> [后续步骤](#next-steps) <br/> |
   
云发现仪表板适用于组织的 web 流量日志，以提供有关云应用程序使用率的详细的信息。如果您的全局管理员、 安全管理员或安全读者，并且您的组织已[创建应用程序发现 Office 365 云应用程序安全性的报告](create-app-discovery-reports-in-ocas.md)，您可以使用云发现仪表板深入了解如何在人员您组织使用 Office 365 和其他云应用程序。（云发现仪表板。 也称为工作效率应用程序发现）
  
 **从年 3 月 2018年云发现仪表板将具有的新功能**的更加轻松地查看有关您的组织中的用户如何使用 Office 365 和其他应用程序的详细的信息。 
  
![已更新，云发现仪表板](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a>转到云发现仪表板

1. 转到[https://protection.office.com](https://protection.office.com)和 Office 365 中使用您的工作或学校帐户登录。(您将转到安全&amp;合规性中心。) 
    
2. 安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。<br/>（如果尚未启用 Office 365 云应用程序安全性，并且已[打开 Office 365 云应用程序安全性](turn-on-office-365-cas.md)的全局管理员）。
    
3. 选择**转到 Office 365 云应用程序安全性**。
    
4. 转到**发现** \> **云发现仪表板**。
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a>请参阅您最多的用户、 IP 地址、 应用程序，以及风险级别

云发现仪表板为您提供了一览 overview of apps 中您的组织、 任何打开的警报、 最多的用户和风险级别与 Office 365 一起使用。
  
![云发现 dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. 在**仪表板**选项卡，查看组织中的概述部分中的总体云应用程序使用屏幕的顶部。 
    
2. 请参阅**Office 365 类别**组织中使用的应用程序。 
    
3. 查看**Discovered 应用程序**小部件，若要查看用法的 Office 365 和此视图中的其他应用程序。 
    
4. 查看**最多用户**和**顶部 IP 地址**小部件来标识那些使用 Office 365 和云组织中最多的应用程序。 
    
5. 请参阅人正在使用的应用程序在何处按地理位置使用的**应用程序总部位置**映射。 
    
6. 上方的映射区域中，看看的**风险级别**overview 中发现的应用程序的风险分数。您可以查看由相同的组和类别的**Discovered 应用程序**区域中使用的风险。例如，您可以看到多少中每个分组的通信是从高、 中型或低风险应用程序。 
    
## <a name="dive-deeper-into-the-information"></a>深入信息

您可以使用云发现更深入地介绍一下在应用程序、 子域、 IP 地址和用户。
  
1. 在云发现仪表板，选择**Discovered 应用程序**选项卡。 
    
2. 使用筛选器部分可以查看按名称、 类别、 使用率级别或上次查看的日期的应用程序。
    
3. 在结果列表中，悬停按应用程序名称以显示**查看子域**链接。<br/> ![将鼠标悬停旁边显示一个链接，用于查看子域的详细信息的应用程序](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)<br/>将显示所选应用程序的详细的信息。
    
4. 若要查看有关 IP 地址的详细信息，请选择**IP 地址**选项卡。<br/>![云发现显示 IP 地址的详细的信息](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)<br/>在结果列表中，选择单个 IP 地址以查看更多详细的信息。
    
5. 若要查看有关组织内的 Office 365 用户的详细信息，请选择**用户**选项卡。<br/>![云发现-用户信息](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)
  
## <a name="exclude-entities"></a>排除实体

为了重点关注更具体的信息，您可以排除特定系统用户或 IP 地址。
  
1. 选择**设置** \> **云发现设置**。
    
2. 选择**排除实体**。
    
3. 选择**排除的用户**或**排除的 IP 地址**。
    
4. 指定的用户或 IP 地址，并在**注释**框中，键入有关为什么您不包括这些用户或 IP 地址的信息。 
    
5. 选择" **添加**"。
    
## <a name="next-steps"></a>后续步骤

- [查看并通知对其执行操作](review-office-365-cas-alerts.md)
    
- [创建应用程序发现报告](create-app-discovery-reports-in-ocas.md)
    
- 查看您[的 Office 365 云应用程序安全性的使用率活动](utilization-activities-for-ocas.md)
    


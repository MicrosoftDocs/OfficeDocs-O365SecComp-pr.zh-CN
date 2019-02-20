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
description: 查看 Office 365 中的应用程序发现报告云应用安全可帮助您了解有关组织中的人员如何使用云应用的详细信息。在使用防火墙和代理中的日志文件创建应用程序发现报告之后, 请在应用发现仪表板中查看结果。
ms.openlocfilehash: fa5ab7c6cd734feb26878cf1a97f7ce708aa1478
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087331"
---
# <a name="review-app-discovery-findings-in-office-365-cloud-app-security"></a>查看 Office 365 云应用安全中的应用发现结果
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|[开始评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |你在这里!  <br/> [后续步骤](#next-steps) <br/> |
   
云发现仪表板可与组织的 web 流量日志配合使用, 以提供有关云应用使用情况的详细信息。如果您是全局管理员、安全管理员或安全读者, 并且您的组织已[在 Office 365 Cloud app security 中创建了应用程序发现报告](create-app-discovery-reports-in-ocas.md), 则可以使用云发现仪表板深入了解您的人员如何组织使用的是 Office 365 和其他云应用。(云发现仪表板也称为 "生产应用程序发现"。)
  
 通过云发现仪表板, 可以查看有关组织中的人员如何使用 Office 365 和其他应用程序的详细信息。 
  
![云发现仪表板已更新](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
     
## <a name="go-to-the-cloud-discovery-dashboard"></a>转到云发现仪表板

1. 转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。
    
2. 转到 "**发现** \> **云发现" 仪表板**。
    
## <a name="see-your-top-users-ip-addresses-apps-and-risk-levels"></a>查看您的首要用户、IP 地址、应用程序和风险级别

云发现仪表板为您提供了有关在组织中使用 Office 365 的应用、任何打开的警报、顶级用户和风险级别的概览。
  
![云 Discovery dashboaard](media/06696946-fbdf-4781-b5b8-2ac074fcb2a1.png)
  
1. 在 "**仪表板**" 选项卡上, 在屏幕顶部的 "概述" 部分中查看您的组织中的整体云应用程序使用情况。 
    
2. 有关在组织中使用的应用程序, 请参阅**Office 365 类别**。 
    
3. 查看 "已**发现的应用程序**" 小部件, 以查看此视图中的 Office 365 和其他应用程序的使用情况。 
    
4. 查看 "**顶级用户**和**首要 IP 地址**" 小部件, 以确定使用组织中最多的 Office 365 和云应用的用户。 
    
5. 使用**应用总部位置**映射查看用户使用的应用程序的位置。 
    
6. 在 "地图" 区域上方, 查看发现的应用在**风险级别**概述中的风险分数。您可以通过在**发现的应用程序**区域中使用的相同组和类别查看风险。例如, 您可以查看每个分组中的流量来自高、中或低风险的应用程序。 
    
## <a name="dive-deeper-into-the-information"></a>深入了解信息

您可以使用云发现深入了解应用、子域、IP 地址和用户。
  
1. 在 "云发现" 仪表板中, 选择 "**发现的应用**" 选项卡。 
    
2. 使用 "筛选器" 部分按名称、类别、使用级别或上次查看日期查看应用程序。
    
3. 在结果列表中, 悬停在应用程序名称旁边以显示 "**查看子域**" 链接。<br/> ![悬停在某个应用旁边, 以显示用于查看子域详细信息的链接](media/4a212215-8a2c-46fd-9ef9-89e4064658a6.png)<br/>将显示有关所选应用程序的详细信息。
    
4. 若要查看有关 IP 地址的详细信息, 请选择 " **ip 地址**" 选项卡。<br/>![云发现显示有关 IP 地址的详细信息](media/0c742bf6-da9e-4d22-8656-a27a5007d5d5.png)<br/>在结果列表中, 选择单个 IP 地址以查看更详细的信息。
    
5. 若要查看组织中的 Office 365 用户的详细信息, 请选择 "**用户**" 选项卡。<br/>![云发现-用户信息](media/2d9c2d85-01e6-4057-8020-d9a68f26bbac.png)
  
## <a name="exclude-entities"></a>排除实体

您可以排除某些系统用户或 IP 地址, 以便重点关注更多特定信息。
  
1. 选择 "**设置** \> **云发现设置**"。
    
2. 选择 "**排除实体**"。
    
3. 选择 "已**排除的用户**" 或 "已排除的**IP 地址**"。
    
4. 指定用户或 ip 地址, 并在 "**注释**" 框中键入有关排除这些用户或 ip 地址的原因的信息。 
    
5. 选择" **添加**"。
    
## <a name="next-steps"></a>后续步骤

- [查看警报并对其执行操作](review-office-365-cas-alerts.md)
    
- [创建应用发现报告](create-app-discovery-reports-in-ocas.md)
    
- 查看[Office 365 云应用安全性的利用率活动](utilization-activities-for-ocas.md)
    


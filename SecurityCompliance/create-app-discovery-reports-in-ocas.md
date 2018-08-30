---
title: 使用 Office 365 云应用安全创建应用发现报告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: 使用 Office 365 云应用程序安全性，您可以了解在组织中的用户如何使用 Office 365 和其他应用程序创建报告。
ms.openlocfilehash: 6842912f42072e21608955bde5250f0774c7bba4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524823"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a>使用 Office 365 云应用安全创建应用发现报告

Office 365 高级安全管理现在是 Office 365 云应用程序安全性。
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|使用率 ***|
|:-----|:-----|:-----|:-----|
|[启动评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |在这里 ！  <br/> [后续步骤](#next-steps) <br/> |
   
Office 365 云应用程序安全性帮助全局管理员、 安全管理员和安全读者深入了解在组织中的人员将云服务。例如，您可以看到用户在其中存储并对文档协作和多少数据上载到应用程序或服务的 Office 365 以外。
  
要生成应用程序发现报告，您手动上载 web 流量日志文件从您的防火墙和代理，然后 Office 365 云应用程序安全性分析并分析报表的那些文件。
  
> [!NOTE]
> 您必须是全局管理员、 安全管理员或安全读者才能执行本文中描述的任务。若要了解详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="create-a-report-with-app-discovery"></a>使用应用程序发现创建报表

要创建应用程序发现报告，请确定您想要已经分析，请选择日志文件，然后请求报告的日志文件的供应商数据源。
  
> [!NOTE]
> 使用包括高峰流量时段，若要使用的最佳表示获取组织中的 web 流量日志文件。 
  
1. 收集您的[web 流量日志和 Office 365 云应用程序安全性的数据源](web-traffic-logs-and-data-sources-for-ocas.md)。
    
2. 转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。 
    
3. 安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。
    
4. 选择**转到 Office 365 云应用程序安全性**。
    
5. 选择**发现** \> **创建新报表**。
    
    ![在 Office 365 CAS 门户中，选择发现](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
6. 指定的名称和说明为您的报表，然后选择**数据源**列表中的 web 流量日志的数据源。 
    
    ![在 O365 CAS 中，选择发现\>创建新报表](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)
  
    > [!NOTE]
    > 如果未列出您想要使用的数据源，您可以请求将添加它。选择**其他**的**数据源**，然后键入您要上载的数据源的名称。我们将查看日志，并让您了解是否我们添加对它生成的数据源的支持。 
  
7. 浏览到您收集的日志文件的位置，然后选择文件。所选报表的数据源必须已生成的日志文件。
    
8. 单击**创建**以启动报表创建过程。 
    
9. 若要查看的报表的状态，请单击**管理快照报告**。报表准备就绪后，您将看到**查看报告**选项。 
    
## <a name="next-steps"></a>后续步骤

- [查看并通知对其执行操作](review-office-365-cas-alerts.md)
    
- [查看 Office 365 云应用安全中的应用发现结果](review-app-discovery-findings-in-ocas.md)
    
- 查看您[的 Office 365 云应用程序安全性的使用率活动](utilization-activities-for-ocas.md)
    


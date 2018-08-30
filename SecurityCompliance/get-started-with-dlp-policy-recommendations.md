---
title: 开始使用 DLP 策略建议
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/7/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2ea4459b-cb13-4ce2-b9d1-0619316df88c
description: 此驱动洞察建议可帮助您保护敏感内容安全时有存储，并且由告知您时没有中的可能间隙共享 Office 365 中的组织 DLP 策略覆盖范围。您将看到此建议在主页上的安全&amp;合规性中心，如果文档包含任何前五个最常见的敏感信息类型，但不受保护的 DLP 策略。
ms.openlocfilehash: 842387397b9b95d236660c5809174c2b356cf14a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525949"
---
# <a name="get-started-with-dlp-policy-recommendations"></a>开始使用 DLP 策略建议

此驱动洞察建议可帮助您保护敏感内容安全时有存储，并且由告知您时没有中的可能间隙共享 Office 365 中的组织 DLP 策略覆盖范围。您将看到此建议的安全**主页**页上&amp;合规性中心，如果文档包含任何前五个最常见的敏感信息类型，但不受保护的数据丢失防护 (DLP) 策略。 
  
您可以使用此小部件快速中只需单击或两个，创建自定义的 DLP 策略，并创建此 DLP 策略后，可完全自定义。请注意，如果您看不到开始时，建议您尝试单击 **+ 详细**底部的**为您的推荐**部分。 
  
![名为不受保护敏感信息的小部件](media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a>创建建议的 DLP 策略

当小部件显示无保护敏感信息时，请底部快速创建 DLP 策略选择**开始**。 
  
若要帮助保护敏感信息，此 DLP 策略：
  
- 检测何时 Exchange、 SharePoint 和 OneDrive 包含不受保护的敏感信息类型之一中的内容与组织外部的人员共享。
    
- 生成详细的活动报告，以便您可以跟踪人员与组织外部的人员共享内容和他们是何时等内容。您可以使用[DLP 报告](view-the-dlp-reports.md)和[审核日志数据](search-the-audit-log-in-security-and-compliance.md)(其中**活动** = **DLP**) 以查看此信息。
    
您还可以选择具有 DLP 策略：
  
- 请向您发送事件报告电子邮件时用户与组织外部的人员共享了大量此敏感信息。
    
- 将其他用户添加到电子邮件事件报告。
    
- 显示策略提示，在尝试与组织外部的人员共享此敏感信息时向用户发送的电子邮件通知。有关这些选项的详细信息，请参阅[发送电子邮件通知和显示策略提示的 DLP 策略](use-notifications-and-policy-tips.md)。
    
如果您想要稍后更改这些选项，您可以在创建后编辑 DLP 策略。例如，使策略包含敏感信息的内容共享甚至阻止人员通过更严格最初-请参阅下一节。
  
![小部件设置名为不受保护敏感信息](media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a>编辑建议的 DLP 策略

小部件用于创建 DLP 策略后，该策略将显示在**数据丢失防护**下的安全**策略**页上&amp;合规性中心。 
  
默认情况下，该策略名为**系统共享敏感信息的建议策略**。此策略可完全自定义，任何，从头开始创建您自己的 DLP 策略相同。例如，如果您决定不打开事件报告和策略提示，使用小部件时，可以始终编辑策略，并在任何时候打开这些选项。
  
![共享敏感信息的建议策略的系统](media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>小部件时执行，不显示

名为**不受保护敏感信息**小部件将显示在**主页**页的安全**为您的推荐**部分&amp;合规性中心。 
  
此小部件时才显示：
  
- 过去 30 天内检测 SharePoint 或 OneDrive 中包含任何内容的五个最常见类型的敏感信息的新文档。
    
- 现有 DLP 策略不已受保护的敏感信息。
    
与不同不断地进行扫描数据的 DLP 策略，此建议扫描的 DLP 策略覆盖您到大约每 48 小时，因此上载新内容后，可能需要两天显示的建议。
  
最后，小部件用于创建建议的 DLP 策略后，将从**主页**页消失小部件。 
  


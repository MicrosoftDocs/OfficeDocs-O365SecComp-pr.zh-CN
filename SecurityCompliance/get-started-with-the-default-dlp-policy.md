---
title: 开始使用默认 DLP 策略
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/10/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
description: 您甚至创建第一个数据丢失防护 (DLP) 策略之前，DLP 帮助保护您的敏感信息与默认策略。此默认策略和敏感内容安全的电子邮件或文档包含 credit 卡片号码时通知您已与您的组织外部的某个人共享其建议 （如下所示） 帮助保留。
ms.openlocfilehash: 1b522a2c04e72353970ef5dfcd62183023a01994
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526067"
---
# <a name="get-started-with-the-default-dlp-policy"></a>开始使用默认 DLP 策略

您甚至创建第一个数据丢失防护 (DLP) 策略之前，DLP 帮助保护您的敏感信息与默认策略。此默认策略和敏感内容安全的电子邮件或文档包含 credit 卡片号码时通知您已与您的组织外部的某个人共享其建议 （如下所示） 帮助保留。您将看到此建议的安全**主页**页上&amp;合规性中心。 
  
您可以使用此小部件若要快速查看何时以及共享多少敏感信息，然后优化中只需单击一两的默认 DLP 策略。因为它是完全可自定义，您还可以随时编辑默认 DLP 策略。请注意，如果您看不到开始时，建议您尝试单击 **+ 详细**底部的**为您的推荐**部分。 
  
![小部件名为进一步保护共享的内容](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>查看报告，并优化默认 DLP 策略

当小部件显示用户具有与组织外部的人员共享敏感信息时，请选择底部**优化 DLP 策略**。 
  
详细的报告将显示过去 30 天中的时间和方式共享已包含信用卡号的内容量。注意规则匹配项可能需要 48 小时小部件中显示。
  
若要帮助保护敏感信息，默认 DLP 策略：
  
- 检测何时 Exchange、 SharePoint 和包含至少一个信用卡号的 OneDrive 中的内容与组织外部的人员共享。
    
- 显示策略提示，并在尝试与组织外部的人员共享此敏感信息时向用户发送的电子邮件通知。有关这些选项的详细信息，请参阅[发送电子邮件通知和显示策略提示的 DLP 策略](use-notifications-and-policy-tips.md)。
    
- 生成详细的活动报告，以便您可以跟踪人员与组织外部的人员共享内容和他们是何时等内容。您可以使用[DLP 报告](view-the-dlp-reports.md)和[审核日志数据](search-the-audit-log-in-security-and-compliance.md)(其中**活动** = **DLP**) 以查看此信息。
    
若要快速细化默认 DLP 策略，您可以选择已：
  
- 请向您发送事件报告电子邮件时用户与组织外部的人员共享此敏感信息。
    
- 将其他用户添加到电子邮件事件报告。
    
- 阻止对包含敏感信息的内容的访问，但允许用户重写并共享或发送如果需。
    
有关事件报告或限制访问的详细信息，请参阅[Overview of 数据丢失预防策略](data-loss-prevention-policies.md)。
  
如果您想要稍后更改这些选项，您可以编辑默认随时-DLP 策略，请参阅下一节。
  
![设置小部件名为进一步保护共享的内容](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>编辑默认 DLP 策略

此策略名为**默认的 Office 365 DLP 策略**，并显示在**策略**页的安全**数据丢失防护**下方&amp;合规性中心。 
  
此策略可完全自定义，任何，从头开始创建您自己的 DLP 策略相同。您还可以关闭或删除策略，以便用户无法再接收策略提示或发送电子邮件通知。
  
![名为默认的 Office 365 DLP 策略的 DLP 策略](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>小部件时执行，不显示

名为**进一步保护共享的内容**小部件将显示在**主页**页的安全**为您的推荐**部分&amp;合规性中心。 
  
此小部件时才显示：
  
- 安全中有无数据丢失预防策略&amp;合规性中心或 Exchange Admin Center。此小部件旨在帮助您开始使用 DLP，因此它不出现如果您已有 DLP 策略。
    
- 已与您的组织在过去 30 天内外部的某个人共享内容包含至少一个信用卡。
    
注意规则匹配项可能需要 48 小时可对小部件，因此检测到外部共享的敏感信息后，可能需要两天显示的建议。
  
最后，小部件用于优化默认 DLP 策略后，将从**主页**页消失小部件。 
  


---
title: 开始使用 DLP 策略建议
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/7/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 此深入了解驱动的建议可帮助你的组织在 Office 365 中存储和共享敏感内容时保持安全, 方法是在 DLP 策略覆盖范围中存在可能的差距时通知你。 如果您的文档包含任何最常用的五种类型&amp;的敏感信息, 但不受 DLP 策略保护, 您将在安全合规中心的主页上看到此建议。
ms.openlocfilehash: ed1140a4f5e09a21aa358564992acd97cd006ba8
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410817"
---
# <a name="get-started-with-dlp-policy-recommendations"></a>开始使用 DLP 策略建议

此深入了解驱动的建议可帮助你的组织在 Office 365 中存储和共享敏感内容时保持安全, 方法是在 DLP 策略覆盖范围中存在可能的差距时通知你。 如果您的文档包含任何最**** 常见类型的敏感信息&amp; , 但不受数据丢失防护 (DLP) 策略保护, 则您将在安全合规中心的主页上看到此建议。 
  
您可以使用此小组件快速创建自定义的 dlp 策略, 只需单击一次或两次, 然后在创建此 DLP 策略后, 即可完全自定义。 请注意, 如果最初看不到建议, 请尝试在 "**建议为你**" 部分的底部单击 " **+ 更多**"。 
  
![名为不受保护的敏感信息的小部件](media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a>创建建议的 DLP 策略

当小组件显示未受保护的敏感信息时, 请选择底部的 "**入门**" 以快速创建 DLP 策略。 
  
为帮助保护敏感信息, 此 DLP 策略:
  
- 检测在 Exchange、SharePoint 和 OneDrive 中包含其中一种不受保护的敏感信息类型的内容与组织外部人员共享的时间。
    
- 生成详细的活动报告, 以便您可以跟踪与组织外部的人员共享内容以及他们何时执行的操作。 您可以使用[DLP 报告](view-the-dlp-reports.md)和[审核日志数据](search-the-audit-log-in-security-and-compliance.md)(其中**活动** = **DLP**) 查看此信息。
    
您还可以选择拥有 DLP 策略:
  
- 当用户与组织外部的人员共享大量这些敏感信息时, 向您发送事件报告电子邮件。
    
- 将其他用户添加到电子邮件事件报告中。
    
- 显示策略提示, 并在用户尝试与组织外部的人员共享此敏感信息时向用户发送电子邮件通知。 有关这些选项的详细信息, 请参阅[发送电子邮件通知和显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)。
    
如果以后要更改这些选项, 您可以在创建 DLP 策略后对其进行编辑。 例如, 即使阻止用户在第一处共享包含敏感信息的内容, 也可以使策略更具限制性-请参阅下一节。
  
![名为不受保护的敏感信息的小部件的设置](media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a>编辑建议的 DLP 策略

使用小部件创建 DLP 策略后, 该策略将显示在安全&amp;合规中心的 "**策略**" 页上的 "**数据丢失防护**" 下。 
  
默认情况下, 该策略被命名为 "**系统建议" 策略以共享敏感信息**。 此策略可完全自定义, 与你从头开始创建的任何 DLP 策略相同。 例如, 如果您决定在使用小组件时不启用事件报告和策略提示, 则可以随时编辑策略并启用这些选项。
  
![系统建议的共享敏感信息的策略](media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>小组件何时出现且不显示

名为 "未**受保护的敏感信息**" 的小部件将显示在安全&amp;合规中心**主页**的 "**建议的用户**" 部分中。 
  
仅在以下情况时显示此小组件:
  
- 在最近30天内, SharePoint 或 OneDrive 中检测到包含五种最常见类型的敏感信息的新文档。
    
- 该敏感信息尚未受到现有 DLP 策略的保护。
    
与不断扫描数据的 dlp 策略不同, 此建议扫描 dlp 策略覆盖范围中大约每隔48小时的间隔, 因此, 在上载新内容后, 可能需要长达两天的时间才能显示建议。
  
最后, 在使用小部件创建建议的 DLP 策略后, 该小部件将从**主页**中消失。 
  


---
title: DLP 方式之间的安全&amp;合规性中心和 Exchange 管理中心
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 了解如何在安全的 DLP&amp;合规中心的工作方式与 Exchange 管理员中心中的 DLP 和传输规则一起。
ms.openlocfilehash: bc7494f504c2c0ffa668562d6e64b9f29992e24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525681"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a>DLP 方式之间的安全&amp;合规性中心和 Exchange 管理中心

在 Office 365 中，您可以创建两个不同的管理中心中的数据丢失防护 (DLP) 策略：
  
- 在**安全&amp;合规性中心**，您可以创建单个 DLP 策略，以帮助保护 SharePoint、 OneDrive 和 Exchange 中的内容。如果可能，我们建议您创建 DLP 策略。有关详细信息，请参阅[安全中的 DLP&amp;合规性中心](data-loss-prevention-policies.md)。
    
- 在**Exchange 管理中心**中，您可以创建 DLP 策略来帮助保护仅在 Exchange 中的内容。此策略可以使用 Exchange 传输规则，因此必须处理电子邮件到特定的更多选项。有关详细信息，请参阅[Exchange Admin Center 中的 DLP](https://go.microsoft.com/fwlink/?linkid=852311)。
    
DLP 策略中这些管理员创建中心工作并排-本主题介绍如何。
  
![安全性和合规性中心以及 Exchange Admin Center 中的 DLP 页面](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a>如何在安全的 DLP&amp;合规中心的工作方式与 Exchange 管理员中心中的 DLP 和传输规则一起

在安全中创建的 DLP 策略后&amp;合规性中心，策略部署到所有策略中包括的位置。如果该策略包括 Exchange Online，该策略的那里同步和实施中在 Exchange 管理中心中创建的 DLP 策略的方式完全相同。 
  
如果您已在 Exchange 管理中心创建 DLP 策略，这些策略将继续工作并排在安全中创建的电子邮件的任何策略&amp;合规性中心。但请注意，在 Exchange 管理中心中创建的规则优先。首先，处理所有 Exchange 传输规则和 DLP 规则从安全的然后&amp;都处理合规性中心。
  
这意味着：
  
- 通过 Exchange 传输规则阻止的邮件不会扫描在安全中创建的 DLP 规则&amp;合规性中心。
    
- 如果 Exchange 传输规则以修改中一种方法，使它在安全性 DLP 策略匹配的邮件&amp;合规性中心-例如添加外部用户-然后 DLP 规则将检测这并根据需要强制执行策略。
    
使用"stop 处理"操作的 Exchange 传输规则不会影响 DLP 处理的注意安全中的规则而且&amp;合规性中心-将仍然处理它们。
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a>策略提示安全中&amp;与 Exchange 管理员中心的合规性中心

策略提示可使用 DLP 策略的工作和邮件流规则在 Exchange 管理中心，或在安全中创建的 DLP 策略创建&amp;合规性中心，但不是能同时。这是因为这些策略存储在不同的位置，但只能从单个位置可以绘制策略提示。
  
如果您已在 Exchange 管理中心，任何安全中配置的策略提示配置策略提示&amp;合规性中心将不会显示向 web 上的 Outlook 和 Outlook 2013 和之前关闭 Exchange 管理中心中的提示，更高版本中的用户。这样可确保您当前的 Exchange 传输规则将继续工作之前您选择切换到安全&amp;合规性中心。
  
请注意，只能从一个位置，可以绘制策略提示时发送电子邮件通知始终发送，即使您正在使用中的安全性的 DLP 策略&amp;合规性中心和 Exchange Admin Center。
  


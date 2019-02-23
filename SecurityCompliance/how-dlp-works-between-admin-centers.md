---
title: DLP 在安全&amp;合规中心和 Exchange 管理中心之间如何工作
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 了解安全&amp;合规性中心中的 dlp 如何在 Exchange 管理中心中使用 dlp 和传输规则。
ms.openlocfilehash: 531a45308594d03dc219f50d989a08236b8b5e20
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215642"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a>DLP 在安全&amp;合规中心和 Exchange 管理中心之间如何工作

在 Office 365 中, 可以在两个不同的管理中心中创建数据丢失防护 (DLP) 策略:
  
- 在**安全&amp;合规性中心**中, 可以创建一个 DLP 策略来帮助保护 SharePoint、OneDrive 和 Exchange 中的内容。如果可能, 我们建议您在此处创建 DLP 策略。有关详细信息, 请参阅[安全&amp;合规性中心中的 DLP](data-loss-prevention-policies.md)。
    
- 在**exchange 管理中心**中, 可以创建 DLP 策略来帮助保护仅在 Exchange 中的内容。此策略可以使用 Exchange 传输规则, 因此它具有更多特定于处理电子邮件的选项。有关详细信息, 请参阅[Exchange 管理中心中的 DLP](https://go.microsoft.com/fwlink/?linkid=852311)。
    
在这些管理中心创建的 DLP 策略并排工作-本主题说明了如何操作。
  
![安全与合规中心和 Exchange 管理中心中的 DLP 页面](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a>安全&amp;合规中心中的 dlp 如何在 Exchange 管理中心中处理 dlp 和传输规则

在安全&amp;合规中心中创建 DLP 策略后, 该策略将部署到策略中包含的所有位置。如果策略包括 exchange Online, 则策略的同步方式与 exchange 管理中心内创建的 DLP 策略完全相同。 
  
如果您在 Exchange 管理中心中创建了 DLP 策略, 这些策略将继续与您在安全&amp;合规中心中创建的电子邮件的任何策略并排工作。但请注意, 在 Exchange 管理中心中创建的规则优先。将首先处理所有 Exchange 传输规则, 然后处理来自安全&amp;合规性中心的 DLP 规则。
  
这意味着:
  
- Exchange 传输规则阻止的邮件不会通过安全&amp;合规中心中创建的 DLP 规则进行扫描。
    
- 如果 Exchange 传输规则以使其与安全&amp;合规中心中的 DLP 策略匹配的方式 (例如添加外部用户) 修改邮件, 则 DLP 规则将检测此问题并根据需要强制实施策略。
    
另请注意, 使用 "停止处理" 操作的 Exchange 传输规则不会影响安全&amp;合规中心中的 DLP 规则处理, 它们仍将被处理。
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a>安全&amp;合规性中心与 Exchange 管理中心中的策略提示

策略提示可使用在 Exchange 管理中心中创建的 dlp 策略和邮件流规则, 或使用在安全&amp;合规性中心中创建的 dlp 策略, 但不能同时使用这两种策略。这是因为这些策略存储在不同的位置, 但策略提示只能从一个位置进行绘制。
  
如果已在 exchange 管理中心中配置了策略提示, 则在安全&amp;合规中心中配置的任何策略提示都不会显示在 web 上的 outlook 和 outlook 2013 及更高版本中的用户, 直到您在 Exchange 管理中心中关闭提示。这样可确保您在选择切换到安全&amp;合规中心之前, 当前的 Exchange 传输规则将继续有效。
  
请注意, 虽然策略提示只能从一个位置进行绘制, 但总是会发送电子邮件通知, 即使您在安全&amp;合规中心和 Exchange 管理中心中使用的是 DLP 策略也是如此。
  


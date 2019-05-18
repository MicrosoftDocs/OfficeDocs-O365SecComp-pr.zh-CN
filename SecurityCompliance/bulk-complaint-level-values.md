---
title: 批量投诉级别值
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 批量邮件群发程序因其发送模式、内容创建以及列表获取做法的不同而不同。 一些是合理的批量邮件群发程序，可以将所需的邮件和相关内容发送到它们的订阅者。 这些邮件使收件人产生少量抱怨。 其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。 为了区分这些类型的批量邮件群发程序，会为批量邮件群发程序中的邮件分配批量投诉级别 (BCL) 评级。 BCL 评级范围介于 1 到 9 之间，这取决于批量邮件群发程序产生抱怨的可能性大小。 BCL 评级为 9 的发件人可能使收件人产生许多抱怨，而 BCL 评级为 3 的发件人产生许多抱怨的可能性较小。 Microsoft 使用内部和第三方源识别批量邮件，并确定适当的 BCL。 此评级显示在每封邮件的"X-Microsoft-Antispam"标头中。 有关此邮件头的详细信息，请参阅反垃圾邮件邮件头。
ms.openlocfilehash: 490823f045e2e3fcf6b537d9717ab12abc323da6
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152124"
---
# <a name="bulk-complaint-level-values"></a>批量投诉级别值

批量邮件群发程序因其发送模式、内容创建以及列表获取做法的不同而不同。 一些是合理的批量邮件群发程序，可以将所需的邮件和相关内容发送到它们的订阅者。 这些邮件使收件人产生少量抱怨。 其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。 为了区分这些类型的批量邮件群发程序，会为批量邮件群发程序中的邮件分配批量投诉级别 (BCL) 评级。 BCL 评级范围介于 1 到 9 之间，这取决于批量邮件群发程序产生抱怨的可能性大小。 BCL 评级为 9 的发件人可能使收件人产生许多抱怨，而 BCL 评级为 3 的发件人产生许多抱怨的可能性较小。 Microsoft 使用内部和第三方源识别批量邮件，并确定适当的 BCL。 此分级在每封邮件的**X-Microsoft 反垃圾**邮件头中公开。 有关此邮件头的详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。 
  
通过按照[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中的步骤操作，您可以使用 BCL 值设置您组织所需的批量筛选级别。
  
未来会添加更多的 BCL 值并将包含在此处。下表列出并描述了当前正在使用的 BCL 值。
  
|||
|:-----|:-----|
|**BCL 值** <br/> |**说明** <br/> |
|0  <br/> |邮件不是由批量发件人发送。  <br/> |
|1, 2, 3  <br/> |邮件来自于产生少量抱怨的批量发件人。  <br/> |
|4, 5, 6, 7  <br/> |邮件来自于产生各种各样的抱怨的批量发件人。  <br/> |
|8, 9  <br/> |邮件来自于产生大量抱怨的批量发件人。  <br/> |
   


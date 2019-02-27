---
title: 批量投诉级别值
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 批量邮件群发程序因其发送模式、内容创建以及列表获取做法的不同而不同。一些是合理的批量邮件群发程序，可以将所需的邮件和相关内容发送到它们的订阅者。这些邮件使收件人产生少量抱怨。其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。为了区分这些类型的批量邮件群发程序，会为批量邮件群发程序中的邮件分配批量投诉级别 (BCL) 评级。BCL 评级范围介于 1 到 9 之间，这取决于批量邮件群发程序产生抱怨的可能性大小。BCL 评级为 9 的发件人可能使收件人产生许多抱怨，而 BCL 评级为 3 的发件人产生许多抱怨的可能性较小。Microsoft 使用内部和第三方源识别批量邮件，并确定适当的 BCL。此评级显示在每封邮件的"X-Microsoft-Antispam"标头中。有关此邮件头的详细信息，请参阅反垃圾邮件邮件头。
ms.openlocfilehash: a948e90ba436dcfdb78df856e090983e6015bb0a
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276012"
---
# <a name="bulk-complaint-level-values"></a>批量投诉级别值

批量发件用户的发送模式、内容创建和列表获取实践各不相同。有些是极大批量邮件程序, 可向订阅者发送带有相关内容的所需邮件。这些邮件会生成来自收件人的少数投诉。其他批量邮件发件人发送与垃圾邮件相似的未经请求的邮件, 并生成来自收件人的许多投诉。若要区分这些类型的批量邮件, 批量邮件发件人的邮件被分配了一个批量投诉级别 (BCL) 评级。BCL 评级范围为1到 9, 具体取决于批量邮件发件人生成投诉的可能性。评级为9的发件人很可能会生成来自收件人的多个投诉, 而 bcl 3 的评级不可能生成许多投诉。Microsoft 使用内部和第三方源来标识批量邮件, 并确定相应的 BCL。此分级在每封邮件的**X-Microsoft 反垃圾**邮件头中公开。有关此邮件头的详细信息, 请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。 
  
通过按照[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中的步骤操作，您可以使用 BCL 值设置您组织所需的批量筛选级别。
  
未来会添加更多的 BCL 值并将包含在此处。下表列出并描述了当前正在使用的 BCL 值。
  
|||
|:-----|:-----|
|**BCL 值** <br/> |**说明** <br/> |
|0  <br/> |邮件不是由批量发件人发送。  <br/> |
|1, 2, 3  <br/> |邮件来自于产生少量抱怨的批量发件人。  <br/> |
|4, 5, 6, 7  <br/> |邮件来自于产生各种各样的抱怨的批量发件人。  <br/> |
|8, 9  <br/> |邮件来自于产生大量抱怨的批量发件人。  <br/> |
   


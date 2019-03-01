---
title: 垃圾邮件可信度
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: 当对电子邮件进行垃圾邮件筛选时，将为该邮件分配一个垃圾邮件得分。该得分将被映射到单个垃圾邮件可信度 (SCL) 分级，并标记在 X 标头中。此项服务将基于 SCL 分级的垃圾邮件可信度解释对邮件采取操作。下表显示了筛选器如何解释不同的 SCL 分级，以及为每个分级的入站邮件所采取的默认操作。
ms.openlocfilehash: e7e8e29a7c3d4a3f09d674f72a400d27746e9081
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341243"
---
# <a name="spam-confidence-levels"></a>垃圾邮件可信度

当对电子邮件进行垃圾邮件筛选时，将为该邮件分配一个垃圾邮件得分。该得分将被映射到单个垃圾邮件可信度 (SCL) 分级，并标记在 X 标头中。此项服务将基于 SCL 分级的垃圾邮件可信度解释对邮件采取操作。下表显示了筛选器如何解释不同的 SCL 分级，以及为每个分级的入站邮件所采取的默认操作。
  
|**SCL 分级**|**垃圾邮件可信度解释**|**默认操作**|
|:-----|:-----|:-----|
|-1|来自安全发件人、安全收件人或安全列表 IP 地址 (受信任合作伙伴) 的非垃圾邮件。|将邮件传递到收件人的收件箱。|
|0, 1|非垃圾邮件, 因为邮件已被扫描并确定为干净。|将邮件传递到收件人的收件箱。|
|5, 6|垃圾邮件|将邮件传递到收件人的垃圾邮件文件夹。|
|7、8、9|可信度高的垃圾邮件|将邮件传递到收件人的垃圾邮件文件夹。|
   
> [!TIP]
> 该服务不设置 SCL 等级2、3、4、7和8。scl 分级为5或6被认为是可疑的垃圾邮件, 而 scl 分级为9的垃圾邮件不会被视为特定的垃圾邮件。可以通过 Exchange 管理中心中的内容筛选器策略来配置垃圾邮件和高可信度垃圾邮件的不同操作。有关详细信息, 请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。您还可以使用邮件流规则 (也称为传输规则) 来设置符合特定条件的邮件的 SCL 分级, 如[使用邮件流规则在邮件中设置垃圾邮件可信度 (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)中所述。如果使用邮件流规则将 SCL 设置为7、8或 9, 则邮件将被视为高可信度垃圾邮件。 
  
||
|:-----|
|![LinkedIn Learning 短图标](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **刚开始接触 Office 365？**         发现 LinkedIn Learning 向 **Office 365 admins and IT pros**提供的免费视频课程。|
   


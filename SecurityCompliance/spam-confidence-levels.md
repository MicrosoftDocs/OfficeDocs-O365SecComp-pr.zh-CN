---
title: 垃圾邮件可信度
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
description: 当对电子邮件进行垃圾邮件筛选时，将为该邮件分配一个垃圾邮件得分。该得分将被映射到单个垃圾邮件可信度 (SCL) 分级，并标记在 X 标头中。此项服务将基于 SCL 分级的垃圾邮件可信度解释对邮件采取操作。下表显示了筛选器如何解释不同的 SCL 分级，以及为每个分级的入站邮件所采取的默认操作。
ms.openlocfilehash: cd33f440828761ab8cb496d9eff07288d974514c
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026279"
---
# <a name="spam-confidence-levels"></a>垃圾邮件可信度

当对电子邮件进行垃圾邮件筛选时，将为该邮件分配一个垃圾邮件得分。该得分将被映射到单个垃圾邮件可信度 (SCL) 分级，并标记在 X 标头中。此项服务将基于 SCL 分级的垃圾邮件可信度解释对邮件采取操作。下表显示了筛选器如何解释不同的 SCL 分级，以及为每个分级的入站邮件所采取的默认操作。
  
|**SCL 分级**|**垃圾邮件可信度解释**|**默认操作**|
|:-----|:-----|:-----|
|-1  <br/> |来自白名单、安全收件人或安全列表 IP 地址（受信任的合作伙伴）的非垃圾邮件  <br/> |将邮件传递到收件人的收件箱。  <br/> |
|0, 1  <br/> |非垃圾邮件，因为已扫描该邮件并确定为安全  <br/> |将邮件传递到收件人的收件箱。  <br/> |
|5, 6  <br/> | 垃圾邮件  <br/> |将邮件传递到收件人的垃圾邮件文件夹。  <br/> |
|7、 8、 9  <br/> |可信度高的垃圾邮件  <br/> |将邮件传递到收件人的垃圾邮件文件夹。  <br/> |
   
> [!TIP]
> 服务未设置 SCL 分级的 2、 3、 4、 7 和 8。Scl 为 5 或 6 被视为可疑的垃圾邮件，则某些不是比 SCL 分级 9，被认为是某些垃圾邮件的垃圾邮件。可以通过您在 Exchange 管理中心中的内容筛选器策略配置不同的垃圾邮件和高可信度垃圾邮件的操作。有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。您还可以设置中[使用的邮件流规则设置垃圾邮件可信度 (SCL) 在消息中的](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)所述使用传输规则符合特定条件的邮件的 scl。如果您使用传输规则设置 SCL 7、 8 或 9 的邮件将被视为高可信度垃圾邮件。 
  
||
|:-----|
|![LinkedIn Learning 短图标](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **刚开始接触 Office 365？**         发现 LinkedIn Learning 向 **Office 365 admins and IT pros**提供的免费视频课程。 |
   


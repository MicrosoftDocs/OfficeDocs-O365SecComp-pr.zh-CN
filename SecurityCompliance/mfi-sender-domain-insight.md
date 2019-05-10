---
title: 修复发件人域洞察力
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解安全 & 合规性中心的邮件流仪表板中的修复发件人域洞察力。
ms.openlocfilehash: a285a1c744ca540cc58b9408b4ee31e768f89479
ms.sourcegitcommit: e05e83212e7ca4e84f2ddb0de0297895b995338d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "33868560"
---
# <a name="fix-sender-domain-insight"></a>修复发件人域洞察力

Office 365 需要从内部本地电子邮件环境发送到 Office 365 的邮件, 以满足特定的安全条件:

- 您已在 Office 365 中创建了一个入站连接器, 以通过使用源 IP 地址或证书验证从您的内部部署电子邮件服务器的 SMTP 连接。

- 您已将本地电子邮件服务器配置为通过 Office 365 将电子邮件中继到外部世界。

- 在您的配置中, 下列陈述中的一条为真:

  - 发件人的电子邮件域在您的 Office 365 组织中注册。 有关详细信息, 请参阅在 Office 365 中添加域。

  - 您的内部部署电子邮件服务器配置为使用证书向 Office 365 发送电子邮件, 该证书包含或完全匹配您在 Office 365 中注册的域名, 并且已在 Office 365 中创建了一个基于证书的连接器, 该连接器具有域. 

不符合条件的邮件将不会被组织到组织中, 并且可能会被拒绝。

**Fix sender domain**真知灼见显示从本地环境中不符合条件的电子邮件, 可帮助您识别本地电子邮件环境中可能受到危害的计算机和用户帐户, 并帮助您采取修正操作。

![Security & 合规性中心的邮件流仪表板中的修复发件人域洞察力](media/sender-domain-insight-selected.png)

当您单击 "**查看详细信息**" 时, 会转到另一个小部件, 其中包含更多详细信息, 如下图中所示:

![修复发件人域洞察力中的详细信息小部件](media/sender-domain-view-details.png)

你将看到用于将邮件传递到 Office 365 的入站连接器。 您还可以单击 "**查看示例邮件 id** " 以查看从您的本地电子邮件环境中发送的邮件的详细信息。 由于这些邮件是由 Office 365 拒绝的, 因此不能使用邮件跟踪, 但可以使用示例邮件 id 来跟踪本地电子邮件环境中的邮件。

![查看修补发件人域洞察力中的示例邮件 id](media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中的其他邮件流见解的详细信息, 请参阅[Security _AMP_ 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。

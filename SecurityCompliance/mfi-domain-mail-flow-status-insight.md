---
title: 顶级域邮件流状态洞察力
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解 Office 365 Security & 合规性中心的邮件流仪表板中的顶层域邮件流状态洞察力。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 04aa986982465a4c66fbf99f517fb34622d65e19
ms.sourcegitcommit: fec1010e405f14e792d650aee0312b78fced3343
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2019
ms.locfileid: "30722774"
---
# <a name="top-domain-mail-flow-status-insight"></a>顶级域邮件流状态洞察力

> [!NOTE]
> 本主题中所述的功能尚未部署到所有 Office 365 组织中, 可能会发生更改。

**顶级域邮件流状态**洞察力为您的组织的域提供了邮件流的当前状态。 此洞察力可帮助您识别和解决遇到***邮件流影响***问题的域 (例如, 无法接收外部电子邮件), 尤其是域过期或包含不正确的 MX 记录的域。

![Office 365 Security & 合规中心的邮件流仪表板中的顶级域流状态洞察力](media/domain-mail-flow-status-selected.png)

当您单击真知灼见中的 "**查看详细信息**" 时, 将显示一个弹出项, 显示每个域的状态的详细信息。

域的绿色复选标记表示当前的 MX 记录 (当您浏览到邮件流见解仪表板时) 与我们记录的值相匹配, 并且在过去的两个小时内, 该域已收到电子邮件。

域中的红色 x 表示 MX 记录已更改, 并且在过去6个小时内没有收到此域的电子邮件。 这可能表明你的域已过期, 或者 MX 记录已被错误更新。 请与你的域注册机构或 DNS 托管服务核实域是否已过期, 或者域的 MX 记录是否不正确。

![顶级域流状态洞察力中的详细信息浮出控件](media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中的其他邮件流见解的详细信息, 请参阅[Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。
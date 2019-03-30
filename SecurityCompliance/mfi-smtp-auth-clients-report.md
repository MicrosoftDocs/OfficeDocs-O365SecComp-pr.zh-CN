---
title: SMTP 身份验证客户端报告
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: 管理员可以了解安全 & 合规性中心的邮件流仪表板中的 SMTP 身份验证客户端报告。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b6698345a89edf52e4ee14cea144cb88ff080583
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "30998705"
---
# <a name="smtp-auth-clients-report"></a>SMTP 身份验证客户端报告

> [!NOTE]
> 本主题中所述的功能尚未部署到所有 Office 365 组织中, 可能会发生更改。

**smtp auth 客户端**报告突出显示了组织中的用户或系统帐户对 SMTP 身份验证客户端提交协议的使用。 此旧协议 (使用终结点 smtp.office365.com) 仅提供基本身份验证, 并且容易被受攻击帐户用来发送电子邮件。  此报告允许您检查异常活动。 它还显示了使用 SMTP 身份验证的客户端或设备的 TLS 使用数据。

"邮件流" 仪表板中显示的小部件指示最近7天内已使用 SMTP 身份验证协议的用户或服务帐户的数量。

![SMTP 身份验证客户端在安全 & 合规性中心中的邮件流仪表板中报告](media/smtp-auth-clients-report-selected.png)

单击小组件将打开一个浮出控件, 该浮出控件可提供上一周的 TLS 使用情况和卷的聚合视图。

![SMTP Auth 客户端报告中的浮出控件](media/smtp-auth-clients-flyout.png)

当您单击**SMTP Auth 客户端报告**链接时, 您将看到两个主要数据透视和两个数据视图。 数据透视是**发送卷**和 TLS 的**使用情况**。 数据视图是图表和详细信息表。

**发送卷**视图显示在指定时间范围内使用 SMTP 身份验证发送的邮件数。 您可以通过单击 "**筛选器**" 来调整该区域。 图表按发件人域进行组织。 通过在 "**显示数据**" 下拉下拉箭头中选择域, 可以查看每个域的单独数据。

![在 SMTP Auth 客户端报告中发送卷](media/smtp-auth-clients-report-sending-volume.png)

您可以通过单击 "**查看详细**信息" 表来查看有关这些发件人及其邮件计数的详细信息。 若要返回图表, 请单击 "**查看报告**"。

![SMTP Auth 客户端报告中用于发送卷的详细信息表](media/smtp-auth-clients-report-details-sending-volume.png)

由于即将弃用的 tls 1.0 和 tls 1.1 在 Office 365 中, **tls 使用**透视非常重要。 如果您的旧设备和应用程序仅能够将 tls 1.0 与 SMTP Auth 一起使用, 则这些设备和应用程序将无法发送电子邮件。此数据透视允许你识别仍在使用旧版 TLS 的用户和系统帐户并对其执行操作。

![SMTP Auth 客户端报告中的 TLS 用法](media/smtp-auth-clients-report-tls-usage.png)

可以通过单击 "**查看详细**信息" 表, 查看有关这些发件人、使用 SMTP 身份验证的 TLS 版本以及邮件数的详细信息。 若要返回图表, 请单击 "**查看报告**"。

您还可以通过单击 "请求报告" 下载报告的更详细的版本。

![SMTP Auth 客户端报告中 TLS 用法的详细信息表](media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中的其他邮件流见解的详细信息, 请参阅[Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。

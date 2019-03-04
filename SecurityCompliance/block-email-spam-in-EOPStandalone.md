---
title: 在独立 EOP 中阻止垃圾邮件
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: laurawi
ms.date: 2/25/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: da21c0b6-e8f0-4cc8-af2e-5029a9433d59
ms.collection:
- M365-security-compliance
description: 用于帮助阻止垃圾邮件误报的独立 EOP 管理员文档
ms.openlocfilehash: 598f63bba4be32c6c664db83126b40c5fae159a0
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341813"
---
## <a name="customize-the-office-365-anti-spam-filter-with-these-settings"></a>为 Office 365 反垃圾邮件筛选器自定义这些设置

管理员可使用多个 Office 365 垃圾邮件筛选器设置，以避免将垃圾邮件发送到用户收件箱。如果你采用本文列出的设置，Office 365 垃圾邮件筛选器将能更好地阻止垃圾邮件，并避免出现漏报邮件。在这种情况下，漏报是指垃圾邮件发送到用户收件箱。
  
### <a name="block-ip-addresses-with-a-connection-filter"></a>使用连接筛选器阻止 IP 地址

通过将发件人 IP 地址添加到连接筛选器 IP 阻止列表，自定义 Office 365 垃圾邮件筛选器：
  
1. 按照[邮件头分析器](https://go.microsoft.com/fwlink/p/?LinkId=306583)中所述，获取要在邮件客户端（如 Outlook 或 Outlook 网页版，先前称为 Outlook Web App）中阻止的邮件的邮件头。
    
2. 在 X-Forefront-Antispam-Report 头中，使用[邮件头分析器](https://testconnectivity.microsoft.com/?tabid=mha)或手动搜索 CIP 标记后面的 IP 地址。 
    
3. 按照[配置连接筛选器策略](https://technet.microsoft.com/zh-CN/library/jj200718%28v=exchg.150%29.aspx)中的“使用 EAC 编辑默认连接筛选器策略”步骤操作，将此 IP 地址添加到 IP 阻止列表。
    
### <a name="block-bulk-mail-with-mail-flow-rules-transport-rules-or-the-spam-filter"></a>使用邮件流规则（也称为传输规则）或垃圾邮件筛选器阻止大量邮件

垃圾邮件主要是大量邮件（例如，新闻稿或促销邮件）吗？可以在[使用邮件流规则配置批量电子邮件筛选](use-transport-rules-to-configure-bulk-email-filtering.md)的情况下自定义 Office 365 垃圾邮件筛选器，也可以启用垃圾邮件筛选器[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)中的“**大量邮件**”设置。在 Exchange 管理中心内，首先依次单击“**保护**”\>“**内容筛选器**”，再双击要调整的筛选器策略。单击“**垃圾邮件和大量邮件操作**”以调整设置，如下所示。 
  
![在 Exchange Online 中设置大量邮件筛选器](media/a45095c2-269d-45b8-a76c-999b5e78da68.png)
  
### <a name="block-email-spam-using-spam-filter-block-lists"></a>使用垃圾邮件筛选器阻止列表阻止垃圾邮件

[配置垃圾邮件筛选器策略](https://technet.microsoft.com/zh-CN/library/jj200684%28v=exchg.150%29.aspx)，以将发件人地址或域分别添加到垃圾邮件筛选器中的发件人阻止列表或域阻止列表。发送自垃圾邮件筛选器阻止列表中发件人或域的电子邮件会被标记为“垃圾邮件”。 
  
## <a name="email-users-can-also-help-ensure-that-false-negative-and-email-spam-is-blocked-with-office-365-spam-filter"></a>电子邮件用户还可有助于确保通过 Office 365 垃圾邮件筛选器避免漏报和阻止垃圾邮件

如果让用户在 [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) 或 [Outlook 网页版](https://go.microsoft.com/fwlink/p/?LinkId=294862)中将垃圾邮件发件人地址添加到阻止的发件人名单中，将有助于 Office 365 反垃圾邮件筛选器避免漏报并阻止垃圾邮件。在 Outlook 网页版中，首先依次单击“**设置**”\>“**选项**”\>“**阻止或允许**”，再将地址添加到“**阻止的发件人**”名单中，如下所示。 
  
![在 Outlook 网页版中阻止发件人](media/fdf51381-2527-4819-ac2a-5dff84d2a36d.png)
  
> [!NOTE]
> 若要详细了解允许列表，请参阅[允许列表和阻止的发件人名单 FAQ](https://technet.microsoft.com/zh-CN/library/dn133608%28v=exchg.150%29.aspx)。 
  
## <a name="eop-only-customers-set-up-directory-synchronization"></a>仅限 EOP 客户：设置目录同步

通过目录同步与服务同步用户设置可确保使用阻止的发件人名单，有助于避免漏报垃圾邮件。有关详细信息，请参阅“在 EOP 中管理邮件用户”中的“使用目录同步管理邮件用户”。
  
## <a name="eop-only-customers-who-are-not-using-directory-synchronization"></a>仅使用 EOP 的客户：不使用目录同步

EOP 旨在使用用户的允许列表和阻止的发件人名单，前提是此类信息已与服务共享。如果你是使用 Outlook 的 EOP 客户，但未配置目录同步来将用户同步到 Office 365，仍可使用阻止的发件人名单来阻止邮件传递到用户收件箱。不过，在以下情况下，可能需要设置一些 Exchange 邮件流规则：
  
- 如果邮件通过 EOP 接受常规垃圾邮件筛选，然后传递到本地 Exchange 服务器，并且 EOP 指定的垃圾邮件裁定结果为 SCL 1-4（非垃圾邮件），那么用户在本地的阻止的发件人名单就会替代 EOP 垃圾邮件筛选器裁定结果，并将邮件传递到“垃圾邮件”文件夹。
    
- 如果将 EOP 中的邮件指定为 SCL -1 的依据为 Exchange 邮件流规则，或因为 IP 地址或域位于允许列表中，那么 SCL 会通过连接器传播到本地 Exchange 服务器。在这种情况下，不会强制执行用户的阻止的发件人名单。若要更改此设置，可创建将 SCL 设置为 0 的本地邮件流规则。这样一来，Outlook 便能强制执行用户在本地的阻止的发件人名单。
    
**将邮件流规则设置为使用阻止的发件人名单阻止邮件传递到用户收件箱的具体步骤**
  
1. 在本地服务器中打开 Exchange 命令行管理程序。若要了解如何在本地 Exchange 组织中打开命令行管理程序，请参阅[打开 Exchange 命令行管理程序](https://technet.microsoft.com/library/dd638134%28v=exchg.160%29.aspx)。
    
2. 运行下面的命令，将已经过内容筛选的垃圾邮件路由到“垃圾邮件”文件夹，以更新所有标记有 SCL -1 的邮件的 SCL：
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SCL:-1" -SetSCL 0
  ```

    由于本地 Exchange 服务器中的 SCL 为 0，因此虽然非垃圾邮件会传递到用户收件箱，但用户在本地的阻止的发件人名单仍能将非垃圾邮件发送到“垃圾邮件”文件夹。如果在 EOP 中使用的是垃圾邮件隔离，用户的安全列表中的发件人仍可能会被标识为垃圾邮件发件人并遭隔离。不过，如果在本地邮箱中使用的是“垃圾邮件”文件夹，仍允许将允许列表中发件人发送的邮件传递到收件箱。

> [!WARNING]
> 如果使用邮件流规则将 SCL 值更改为 0（或除 -1 以外的任何值），将会对邮件应用所有 Outlook 垃圾邮件选项。也就是说，将使用阻止的发件人名单和安全列表。但同时也意味着，客户端垃圾邮件筛选处理流程可能会将阻止的发件人名单或安全列表中没有的地址发送的邮件标记为“垃圾邮件”。若要让 Outlook 处理阻止的发件人名单和安全列表，但不使用客户端垃圾邮件筛选器，必须将 Outlook 垃圾邮件选项设置为“无自动筛选”。虽然“无自动筛选”是最新版 Outlook 中的默认选项，但你也应确认此设置是否已就位，以确保不向邮件应用客户端垃圾邮件筛选器。作为管理员，可以按照 [Outlook：用于禁用垃圾邮件 UI 和筛选机制的策略设置](https://support.microsoft.com/zh-CN/kb/2180568)中的说明操作，强制禁用 Outlook 垃圾邮件筛选。
  
## <a name="see-also"></a>另请参阅

[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)
  
[使用安全列表或其他技术避免出现标记为“垃圾邮件”的误报电子邮件](prevent-email-from-being-marked-as-spam.md)

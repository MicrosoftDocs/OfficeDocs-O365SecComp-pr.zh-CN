---
title: 使用 Office 365 垃圾邮件筛选器阻止垃圾邮件以避免出现漏报问题
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: da21c0b6-e8f0-4cc8-af2e-5029a9433d59
description: 本文介绍了设置 Office 365 垃圾邮件筛选器以阻止垃圾邮件并避免出现漏报邮件的技巧。管理员使用 Office 365 反垃圾邮件筛选是为了避免将垃圾邮件发送到用户收件箱。
ms.openlocfilehash: 3502215dba4097d0643501dd089ec3fe94575c87
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525296"
---
# <a name="block-email-spam-with-the-office-365-spam-filter-to-prevent-false-negative-issues"></a>使用 Office 365 垃圾邮件筛选器阻止垃圾邮件以避免出现漏报问题

Exchange Online Protection (EOP) 是一项基于云的电子邮件筛选服务，有助于保护组织免受垃圾邮件和恶意软件威胁。如果你在 Office 365 中有邮箱，它们已默认受 EOP 保护。 
  
你可调整 Office 365 垃圾邮件筛选器，以帮助确保阻止垃圾邮件。这样有助于避免出现漏报问题，即允许垃圾邮件发送到用户收件箱。作为 Exchange Online 或 Exchange Online Protection (EOP) 管理员，请按照以下步骤操作来调整 Office 365 反垃圾邮件筛选器，以避免将垃圾邮件传递到用户收件箱。
  
## <a name="customize-the-office-365-anti-spam-filter-with-these-settings"></a>为 Office 365 反垃圾邮件筛选器自定义这些设置

管理员可使用多个 Office 365 垃圾邮件筛选器设置，以避免将垃圾邮件发送到用户收件箱。如果你采用本文列出的设置，Office 365 垃圾邮件筛选器将能更好地阻止垃圾邮件，并避免出现漏报邮件。在这种情况下，漏报是指垃圾邮件发送到用户收件箱。
  
### <a name="block-ip-addresses-with-a-connection-filter"></a>使用连接筛选器阻止 IP 地址

通过将发件人 IP 地址添加到连接筛选器 IP 阻止列表，自定义 Office 365 垃圾邮件筛选器：
  
1. 按照[邮件头分析器](https://go.microsoft.com/fwlink/p/?LinkId=306583)中所述，获取要在邮件客户端（如 Outlook 或 Outlook Web App）中阻止的邮件的邮件头。
    
2. 在 X-Forefront-Antispam-Report 头中，使用[邮件头分析器](https://testconnectivity.microsoft.com/?tabid=mha)或手动搜索 CIP 标记后面的 IP 地址。 
    
3. 按照[配置连接筛选器策略](https://technet.microsoft.com/zh-CN/library/jj200718%28v=exchg.150%29.aspx)中的“使用 EAC 编辑默认连接筛选器策略”步骤操作，将此 IP 地址添加到 IP 阻止列表。
    
### <a name="block-bulk-mail-with-transport-rules-or-the-spam-filter"></a>使用传输规则或垃圾邮件筛选器阻止大量邮件

垃圾邮件主要是大量邮件（例如，新闻稿或促销邮件）吗？可以在[使用传输规则主动筛选批量电子邮件](https://technet.microsoft.com/zh-CN/library/dn720438%28v=exchg.150%29.aspx)的情况下自定义 Office 365 垃圾邮件筛选器，也可以启用垃圾邮件筛选器[高级垃圾邮件筛选选项](https://technet.microsoft.com/zh-CN/library/jj200750%28v=exchg.150%29.aspx)中的“大量邮件”**** 设置。在 Exchange 管理中心内，首先依次单击“保护”****\>“内容筛选器”****，再双击要调整的筛选器策略。单击“垃圾邮件和大量邮件操作”**** 以调整设置，如下所示。 
  
![在 Exchange Online 中设置大量邮件筛选器](media/a45095c2-269d-45b8-a76c-999b5e78da68.png)
  
### <a name="block-email-spam-using-spam-filter-block-lists"></a>使用垃圾邮件筛选器阻止列表阻止垃圾邮件

[配置垃圾邮件筛选器策略](https://technet.microsoft.com/zh-CN/library/jj200684%28v=exchg.150%29.aspx)，以将发件人地址或域分别添加到垃圾邮件筛选器中的发件人阻止列表或域阻止列表。发送自垃圾邮件筛选器阻止列表中发件人或域的电子邮件会被标记为“垃圾邮件”。 
  
### <a name="advanced-spam-filtering-options"></a>高级垃圾邮件筛选选项

[配置垃圾邮件筛选器策略](https://technet.microsoft.com/zh-CN/library/jj200684%28v=exchg.150%29.aspx)，并启用其他[高级垃圾邮件筛选选项](https://technet.microsoft.com/zh-CN/library/jj200750%28v=exchg.150%29.aspx)。
  
有关适用于整个组织的更多垃圾邮件设置，请参阅[使用安全列表或其他技术避免出现标记为“垃圾邮件”的误报电子邮件](prevent-email-from-being-marked-as-spam-0.md)。如果你拥有管理员级控制权，并且希望避免误报，便会发现这非常有用。
  
## <a name="email-users-can-also-help-ensure-that-false-negative-and-email-spam-is-blocked-with-office-365-spam-filter"></a>电子邮件用户还可有助于确保通过 Office 365 垃圾邮件筛选器避免漏报和阻止垃圾邮件

如果让用户在 [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) 或 [Outlook Web App](https://go.microsoft.com/fwlink/p/?LinkId=294862) 中将垃圾邮件发件人地址添加到阻止的发件人名单中，将有助于 Office 365 反垃圾邮件筛选器避免漏报并阻止垃圾邮件。在 Outlook Web App 中，首先依次单击“设置”****\>“选项”****“阻止或允许”\>****，再将地址添加到“阻止的发件人名单”**** 中，如下所示。 
  
![在 Outlook Web App 中阻止发件人](media/fdf51381-2527-4819-ac2a-5dff84d2a36d.png)
  
> [!NOTE]
> 若要详细了解允许列表，请参阅[允许列表和阻止的发件人名单 FAQ](https://technet.microsoft.com/zh-CN/library/dn133608%28v=exchg.150%29.aspx)。 
  
本分部中的前几段落仅适用于使用 EOP 作为本地电子邮件系统保护服务，或在混合电子邮件部署中使用 EOP 的客户。若要详细了解 EOP，请参阅 [Exchange Online Protection 主页](https://products.office.com/zh-CN/exchange/exchange-email-security-spam-protection)。
  
## <a name="eop-only-customers-set-up-the-office-365-spam-filter-to-block-email-spam"></a>仅使用 EOP 的客户：设置 Office 365 垃圾邮件筛选器以阻止垃圾邮件

对于仅使用 EOP 且有本地邮箱的客户：如果为默认操作“将邮件移至‘垃圾邮件’文件夹”设置垃圾邮件筛选器，请按照“确保将垃圾邮件路由到每个用户的‘垃圾邮件’文件夹中”的必要步骤操作。我们已尝试简化此操作，不仅在单独的主题中提供了 Exchange 命令行管理程序命令，还链接到更多有关如何开始使用命令行管理程序的常规信息。
  
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
<a name="BKMK_please_comment"> </a>

[Office 365 反垃圾邮件保护](anti-spam-protection.md)
  
[使用安全列表或其他技术避免出现标记为“垃圾邮件”的误报电子邮件](prevent-email-from-being-marked-as-spam-0.md)
  


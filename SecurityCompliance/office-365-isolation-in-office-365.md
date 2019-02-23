---
title: office 365 中的 office 365 隔离和访问控制
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '摘要: Office 365 的各种应用程序中的隔离和访问控制说明。'
ms.openlocfilehash: 734c92a6f3185a25faf9aade1ba235444ed762da
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216852"
---
# <a name="isolation-and-access-control-in-office-365"></a>Office 365 中的隔离和访问控制

Azure Active Directory 和 Office 365 使用高度复杂的数据模型, 其中包括数十个服务、数百个实体、数以千计的关系以及成千上万个属性 (实体、关系和属性通常是特定于应用程序的)。在较高级别, Azure Active Directory 和服务目录是租户和收件人的容器, 它们使用基于状态的复制协议保持同步。除了 Azure Active directory 中保留的目录信息外, 每个服务还有自己的目录服务基础结构 (例如, Exchange Online 目录服务、SharePoint Online 目录服务等)。 
 
![Office 365 租户数据同步](media/office-365-isolation-tenant-data-sync.png)

在此模型中, 没有一个目录数据源。每个单独的数据段都由特定系统拥有, 但没有一个系统保存所有数据。Office 365 服务与 Azure Active Directory 合作, 以实现数据模型。Azure Active Directory 是共享数据的 "真实系统", 它通常是每个服务通常使用的小数据和静态数据。Office 365 和 Azure Active Directory 中使用的联合模型提供了数据的共享视图。

Office 365 同时使用物理存储和 Azure 云存储。exchange online (包括 exchange online Protection) 和 Skype for business 将自己的存储用于客户数据。SharePoint Online 利用其 SQL Server 存储和 Azure 存储, 这就需要在存储级别额外隔离客户数据。

## <a name="exchange-online"></a>Exchange Online
Exchange Online 将客户数据存储在托管在名为邮箱数据库的可扩展存储引擎 (ESE) 数据库中的邮箱中。这包括用户邮箱、链接邮箱、共享邮箱和公用文件夹邮箱。用户邮箱还可能包括已保存的 Skype for business 内容, 如对话历史记录。用户邮箱内容包括电子邮件和电子邮件附件、日历和忙/闲信息、联系人、任务、便笺、组和推断数据。

Exchange Online 中的每个邮箱数据库包含来自多个租户的邮箱。所有邮箱都由授权代码保护, 包括在租赁内。与 Exchange 的本地部署一样, 默认情况下, 仅分配的用户可以访问邮箱。保护邮箱的访问控制列表 (ACL) 包含在租户级别通过 Azure Active Directory 进行身份验证的标识。给定租户的邮箱限制为针对该租户的身份验证提供程序进行身份验证, 其中仅包含来自该租户的用户。属于 TenantA 的内容无法以任何方式通过 TenantB 中的用户获取, 除非 TenantA 明确批准。

## <a name="skype-for-business"></a>Skype for Business
Skype for business 将数据存储在多个位置:
- 包含连接终结点、租户 id、拨号计划、漫游设置、状态状态、联系人列表等的用户和帐户信息存储在 Skype for business Active Directory 服务器以及各种 skype for business 数据库中。台.如果为用户启用了这两个产品或 Skype for business 服务器 (如果用户不是这样), 则联系人列表存储在用户的 Exchange Online 邮箱中。Skype for business 数据库服务器不按租户分区, 但通过 RBAC 强制实施多租户数据隔离。
- 会议内容 (如在 Skype for business 会议中上载的内容用户) 存储在分布式文件系统共享上。此外, 还可以在 Exchange Online 中存档此内容, 并启用存档功能。DFS 共享不按每个租户进行分区, 但内容通过 acl 加以保护, 并且通过 RBAC 强制实施多租户。
- 呼叫详细信息记录 (如呼叫历史记录、im 会话、应用程序共享、im 历史记录等) 也可以存储在 Exchange Online 中, 但大多数呼叫详细信息记录临时存储在呼叫详细信息记录 (CDR) 服务器上。不对每个租户对内容进行分区, 但通过 RBAC 强制实施了多租户。

## <a name="sharepoint-online"></a>SharePoint Online
SharePoint Online 独有的几种独立的机制可提供数据隔离。SharePoint Online 将对象存储为应用程序数据库中的抽象代码。例如, 当用户将文件上传到 SharePoint Online 时, 会反汇编该文件并将其转换为应用程序代码, 并将其存储在多个数据库的多个表中。

如果用户可以直接访问包含数据的存储, 则不会将内容 interpretable 到 SharePoint Online 之外的人或任何系统。这些机制包括安全访问控制和属性。如上所述, 所有 SharePoint Online 资源均由授权代码和 RBAC 策略 (包括租赁内的) 进行保护。保护资源的访问控制列表 (ACL) 包含在租户级别进行身份验证的标识。与 Exchange online 一样, 在 SharePoint online 中, 给定租户的数据仅限于针对该租户的身份验证提供程序进行身份验证, 其中仅包含来自该租户的用户。

除了 acl 之外, 指定身份验证提供程序 (即租户特定的 Azure Active Directory) 的租户级别属性只写入一次, 并且在设置后不能更改。为租户设置身份验证提供程序租户属性后, 将无法使用公开给租户的任何 api 对其进行更改。

每个租户还使用唯一的*SubscriptionId* 。所有客户网站均由租户拥有, 并向其分配了一个对租户唯一的*SubscriptionId* 。网站上的*SubscriptionId*属性只写入一次, 且不能更改。将网站分配给租户后, 将无法在以后使用内容存储 API 将其移动到其他租户。*SubscriptionId*也是用于为身份验证提供程序创建安全作用域并与租户相关联的密钥。

SharePoint Online 使用 SQL Server 和 Azure 存储来存储内容。在 SQL 级别, 内容存储区的分区键为*SiteId*。运行 SQL 查询时, SharePoint Online 将使用已验证为租户级*SubscriptionId*检查的一部分的*SiteId* 。

SharePoint Online 将文件二进制 blob (例如, 文件流) 存储在 Microsoft Azure 中。每个 SharePoint Online 场都有自己的 Microsoft Azure 帐户, 保存在 Azure 中的所有 blob 都使用存储在 SQL 内容存储中的密钥进行单独加密。加密密钥不会直接暴露给最终用户, 并通过授权层在代码中受到保护。最后, SharePoint Online 在适当的位置进行实时监控, 以在 HTTP 请求读取或写入多个租户的数据时进行检测。为此, 它将根据正在访问的资源的*subscriptionid*跟踪请求标识的*subscriptionid* 。访问多个租户的资源的请求永远不应在最终用户发生。但在多租户环境中, 服务请求可能会发生这种情况。例如, 搜索爬网程序一次性提取整个数据库的内容更改。这通常涉及在单个服务请求中查询多个租户的网站, 这是出于提高效率的原因而完成的。

---
title: Office 365 隔离和 Office 365 中的访问控制
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 在 Office 365 的各种应用程序内的隔离和访问控制的说明。
ms.openlocfilehash: c1989bc546df357740ea963a1a241dfa14557931
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525956"
---
# <a name="isolation-and-access-control-in-office-365"></a>Office 365 中的隔离和访问控制

Azure Active Directory 和 Office 365 使用非常复杂的数据模型包括数以万计的服务，数百个实体，数千个关系和数以万计的属性 （entities、 关系和属性通常是特定于应用程序）。在高级别 Azure Active Directory 和服务目录的租户和收件人，容器，并且保留在同步使用基于状态的复制协议。除了保留在 Azure Active Directory 中的目录信息，每个服务还有自己目录服务基础结构 （例如，Exchange Online 的目录服务、 SharePoint Online Directory Services 等）。 
 
![Office 365 租户数据同步](media/office-365-isolation-tenant-data-sync.png)

在此模型中，没有目录数据的任何单个源。由特定系统，拥有每个单独的数据，但没有单个系统包含的所有数据。Office 365 服务配合 Azure Active Directory 认识到数据模型。Azure Active Directory 是共享数据，这通常是通常使用每种服务的小型和静态数据真实性的"系统"。使用 Office 365 和 Azure Active Directory 中的联合的模型提供的数据的共享的视图。

Office 365 使用物理存储和 Azure 云存储。Exchange Online （包括 Exchange Online Protection） 和 Skype for Business 使用自己存储客户数据。SharePoint Online 利用其 SQL Server 存储和 Azure 存储，这需要附加隔离存储级别的客户数据的需要。

## <a name="exchange-online"></a>Exchange Online
Exchange Online 存储位于名为邮箱数据库的可扩展存储引擎 (ESE) 数据库中的邮箱内的客户数据。这包括用户邮箱、 链接的邮箱、 共享的邮箱和公用文件夹邮箱。用户邮箱可能还包括保存的 Skype 的业务内容，例如对话历史记录。用户邮箱内容包括电子邮件和电子邮件附件、 日历和忙/闲信息、 联系人、 任务、 注释、 组和推断数据。

在 Exchange Online 内的每个邮箱数据库包含从多个租户的邮箱。授权代码，包括租赁中保护所有邮箱。为在本地部署的 Exchange，默认情况下仅分配的用户具有访问权限到邮箱。保护邮箱访问控制列表 (ACL) 包含进行身份验证由租户级别的 Azure Active Directory 标识。给定租户的邮箱被限制为经过身份验证针对该租户的身份验证提供程序，其中包括从该租户的唯一用户的标识。属于 TenantA 内容无法以任何方式获得用户在 TenantB，除非明确批准 TenantA。

## <a name="skype-for-business"></a>Skype for Business
Skype for Business 多种位置中存储数据：
- 对于业务 Active Directory 服务器，Skype 中以及在各种 Skype 业务数据库存储用户和帐户信息，其中包括连接终结点，租户 Id、 拨号计划，漫游设置、 状态、 联系人列表等服务器。如果为用户启用对这两种产品，或在 Skype 上的业务服务器如果用户不是，联系人列表存储在用户的 Exchange Online 邮箱。Skype 业务数据库服务器的不分区每个租户，但通过 RBAC 强制执行多租户隔离的数据。
- 会议内容，如内容的用户在过程中上载 Skype 业务会议，存储在分布式文件系统共享上。提供启用存档，也可以在 Exchange Online 存档此内容。DFS 共享不是已分区的每个租户，但内容安全的 Acl，通过 RBAC 强制执行多租户。
- 呼叫详细记录，它是活动历史记录，如呼叫历史记录、 IM 会话、 应用程序共享、 IM 历史记录等，也可以存储在 Exchange Online 中，但大多数呼叫详细记录暂时存储在呼叫详细信息记录 (CDR) 服务器上。内容未分区每租户，但通过 RBAC 强制执行多租户。

## <a name="sharepoint-online"></a>SharePoint Online
有几种独立机制 to SharePoint Online 提供能够隔离数据的唯一。SharePoint Online 作为抽象代码中应用程序数据库存储对象。例如，当用户将文件上载到 SharePoint Online，该文件是反汇编和翻译应用程序代码和跨多个数据库存储在多个表中。

如果用户无法直接访问包含数据的存储，不会解释到 human 或任何系统之外的 SharePoint Online 内容。这些机制包括安全访问控制和属性。如上所述，SharePoint Online 的所有资源都受的授权代码和 RBAC 策略，包括租赁中。保护资源的访问控制列表 (ACL) 包含在租户级别进行身份验证的标识。与 Exchange Online 中，在 SharePoint Online 中，给定租户数据仅限于经过身份验证针对该租户的身份验证提供程序，其中包括从该租户的唯一用户的标识。

除了 Acl，指定的身份验证提供程序 （它是租户特定的 Azure Active Directory），租户级别属性写入一次，并设置后，无法更改。身份验证提供程序租户属性设置为租户后，就无法更改使用向租户公开任何 Api。

唯一*SubscriptionId*还用于每个租户。所有客户网站拥有的租户，且已分配给租户的唯一*SubscriptionId* 。网站上的*SubscriptionId*属性写入一次，且不能更改。一旦网站已分配给租户，它不能移动到不同租户更高版本使用的内容存储 API。*SubscriptionId*也是用于创建身份验证提供程序安全作用域和绑定到租户密钥。

SharePoint Online 的内容存储使用 SQL Server 和 Azure 存储。SQL 级别内容存储的分区密钥是*SiteId*。运行时 SQL 查询，SharePoint Online 使用*SiteId*已被确认为租户级*SubscriptionId*检查的一部分。

SharePoint Online Microsoft Azure 中存储文件二进制 blob （例如，文件流）。SharePoint Online 的每个场都有其自己的 Microsoft Azure 帐户并保存在 Azure 中的所有 blob 分别使用 SQL 内容存储中存储的密钥进行都加密。加密密钥不直接暴露最终用户，并在代码中由授权层保护。最后，SharePoint Online 的已就绪为检测何时 HTTP 请求读取或写入数据的多个租户的实时监视。这是资源的通过跟踪对要访问*SubscriptionId*请求标识*SubscriptionId* 。访问多个租户的资源的请求应永远不会发生的最终用户。它可以上述发生在多租户环境中，服务请求。例如，搜索爬网程序将所有同时提取内容更改的整个数据库。这通常涉及到查询中的单个服务请求，其完成为提高效率的多个租户的网站。

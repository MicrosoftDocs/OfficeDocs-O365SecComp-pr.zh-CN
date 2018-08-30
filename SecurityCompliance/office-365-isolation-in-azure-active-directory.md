---
title: Office 365 隔离和 Azure Active Directory 中的访问控制
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
description: 摘要： 如何在 Azure Active Directory 中工作的隔离和访问控制。
ms.openlocfilehash: db4fa0d026c6c608f09252c65bf1e0de5354f68c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525932"
---
# <a name="isolation-and-access-control-in-azure-active-directory"></a>Azure Active Directory 中的隔离和访问控制

Azure Active Directory 旨在承载多个租户，以通过逻辑数据隔离高度安全的方式。Azure Active Directory 访问权将由授权层网关。Azure Active Directory 隔离客户使用为安全边界租户容器，以便无法访问或受到共同租户内容保护客户的内容。由 Azure Active Directory 授权层执行三个检查：
- Azure Active Directory 租户访问是否启用主体？
- 访问此租户中的数据是否启用主体？
- 为授权类型的请求的数据访问此租户中的主体的角色？

没有应用程序、 用户、 服务器或服务可以访问而在合适的身份验证和令牌或证书的 Azure Active Directory。如果它们不带有正确的凭据，则会拒绝请求。

有效 Azure Active Directory 承载自己受保护的容器，与策略和权限和单独拥有且由租户管理该容器内中每个租户。
 
![Azure 容器](media/office-365-isolation-azure-container.png)

租户容器的概念是深老旧所有层，一直到永久存储区的门户网站从目录服务中。多个 Azure Active Directory 租户元数据存储在同一个物理磁盘上，即使没有之间关系之外的目录服务，又由租户管理员定义的内容的容器。可以有无直接连接到 Azure Active Directory 存储从任何请求的应用程序或服务，而不经由授权层的第一个。

在下面的示例中，Contoso 和 Fabrikam 都有单独的专用容器和即使这些容器可能共享某些的相同的基础结构，如服务器和存储，他们仍保持分离和彼此，隔离的网关层的授权和访问控制。
 
![Azure 专用的容器](media/office-365-isolation-azure-dedicated-containers.png)

此外，在 Azure Active Directory，可以执行从没有应用程序组件，并且不可能一个租户来强制破坏其他租户的完整性、 访问加密密钥的另一个租户，或从服务器中读取原始数据。

默认情况下 Azure Active Directory 禁止颁发其他租户中的标识的所有操作。在 Azure Active Directory 中通过基于声明的访问控制逻辑隔离每个租户。读取和写入的数据的范围限定为租户容器和一个内部抽象层和基于角色的访问控制 (RBAC) 图层，一起强制实施安全边界为租户网关的目录。每个目录数据访问请求处理由这些层和 Office 365 中的每个访问请求监察通过上面的逻辑。

Azure Active Directory 具有北美、 美国政府、 欧盟，德国和万维网分区。租户位于单个分区，并且分区可以包含多个租户。用户离开抽象是分区信息。给定的分区 （包括中的所有租户） 复制到多个数据中心。租户的分区选择了基于租户 （例如，国家/地区代码） 的属性。使用专用密钥加密机密和每个分区中的其他敏感信息。创建新的分区时，会自动生成密钥。

Azure Active Directory 系统功能是对每个用户会话的唯一实例。此外，Azure Active Directory 使用加密技术提供的共享的系统资源在网络级别以防止未经授权和意外传输的信息隔离。

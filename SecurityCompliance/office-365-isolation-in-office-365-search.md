---
title: Office 365 搜索中的 office 365 租户隔离
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
description: 摘要： 在 Office 365 搜索租户隔离的说明。
ms.openlocfilehash: cc73f3c157ffd20b3891a6b7c58e7d0b2adf4e55
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524802"
---
# <a name="tenant-isolation-in-office-365-search"></a>Office 365 搜索中的租户隔离
SharePoint Online 搜索使用租户分离模型来平衡防护信息泄漏租户之间的共享的数据结构的效率。使用此模型，我们将防止搜索功能：
- 返回包含文档中的其他租户的查询结果
- 公开足够查询结果中的信息熟练用户无法推断其他租户的信息
- 显示架构或从另一个租户的设置
- 混合分析处理租户或错误租户中的存储结果之间的信息
- 使用从另一个租户的词典条目

对于每个租户数据类型，我们使用一个或多个层保护在代码中以防止意外泄漏的信息。最重要的数据具有保护，以确保单个缺陷不会导致实际或察觉到信息泄露的大多数层。

## <a name="tenant-separation-for-the-search-index"></a>搜索索引的的租户分离
搜索索引存储在托管索引组件的服务器的磁盘上和租户共享索引文件。租户的索引的文档都能看到仅对该租户的查询。三个独立的机制以防止信息泄露：
- 租户 ID 筛选
- 租户 ID 术语前添加前缀
- ACL 检查

所有三种机制者必须失败的搜索以返回到错误的租户的文档。

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>租户 ID 筛选和前添加前缀的租户 ID 术语
搜索前缀编入与租户 ID 全文本索引中每个术语例如，术语"*foo*"编制索引的租户 ID 为"*123*"后，全文本索引中的条目是"*123foo。*"

每个查询转换为包含使用此过程称为租户 ID 筛选的租户 ID。例如，"*foo*"查询转换为"<*guid*>。*foo*和*tenantID*: <*guid*>"，其中 <*guid*> 表示执行查询的租户。此查询转换中每个索引节点并查询和内容都不处理影响。因为的租户 ID 添加到每个查询时，无法通过查看在最佳匹配中一个租户排名推断其他租户中的术语的频率。

租户 ID 术语前添加前缀，发生此事件仅在全文本索引。上市的搜索，例如"*标题： foo*"，转到综合搜索索引其中术语不作为前缀的租户 id。而是作为前缀上市的搜索具有字段名称。例如，"*标题： foo*"查询转换为"*fields.title:foo AND fields.tenantID*: <*guid*>。"术语的频率影响的综合搜索索引中的命中的排名，因为没有必要的租户隔离由术语前添加前缀。对于"*标题： foo*"像上市搜索，租户内容分离取决于按查询转换筛选的租户 ID。

## <a name="document-access-control-list-checks"></a>文档访问控制列表检查
搜索控制对通过搜索索引中保存的 Acl 的文档的访问。每个项目编制索引使用特殊 ACL 字段中的术语集。ACL 字段包含每个组或用户可以查看文档的一个术语。每个查询进行了补充的访问控制项 (ACE) 条款，一个用于每个身份验证的用户所属的组的列表。

例如，"<*guid*> 类似查询。*foo 和 tenantID*: <*guid*>"变为:"<*guid*>。*foo 和 tenantID*: <*guid*> *AND* (*docACL:*<*ace1*> *OR docACL*: <*ace2*> *OR docACL*: <*ace3*> *...*)"

由于用户和组标识符，因此 Ace 是唯一的这提供了一个额外的之间的文档只对某些用户可见的租户的安全级别。相同是特殊"之外的任何用户外部用户"这种情况 ACE 为租户中的常规用户授予访问权限。但由于为"任何人"Ace 都是相同的所有租户，为公共文档的租户分离取决于在租户 ID 筛选。拒绝 Ace 也支持。查询扩充添加与拒绝 ACE 匹配时，会从结果中删除文档的子句。

在 Exchange Online 搜索索引分区上而不是与 SharePoint Online 的租户 ID (订阅 ID) 的单个用户的邮箱的邮箱 ID。分区的机制等同于 SharePoint Online，但没有任何 ACL 筛选。

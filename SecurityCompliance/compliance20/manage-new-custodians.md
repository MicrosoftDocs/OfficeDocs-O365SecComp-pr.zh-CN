---
title: 在高级电子数据展示 （预览） 情况下管理管理员
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 742f6bc35b67071fba528e6a0ce543ecc6915762
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607489"
---
# <a name="managing-custodians-in-an-advanced-ediscovery-preview-case"></a>在高级电子数据展示 （预览） 情况下管理管理员

管理员选项卡包含情况下的所有管理员可排序的列表。向用例添加管理员后，将自动从 Azure Active Directory 中收集有关每个 custodian 的详细信息。

## <a name="viewing-custodian-details"></a>查看 custodian 详细信息

管理员添加到案例并从**管理员**选项卡上的列表中选择后，将显示弹出页包含 custodian 详细信息。从此处，您可以查看与该 custodian 相关的所有详细信息。飞出页包含以下字段：

- 联系人信息

  - **显示名称**： custodian 通讯簿中显示的名称。这通常是名字的 custodian，中间的初始和最后一个名称的组合。
  - **邮件/SMTP**: custodian，例如，jeff@contoso.onmicrosoft.com 的 SMTP 地址。  
  - **标题**： custodian 的职务。
  - **部门**： custodian 适用于该部门的名称。
  - **管理器**： 管理员管理器。指定的经理将收到此 custodian 任何升级通信。
  
- 位置信息

  - **市/县**： custodian 所在的市/县。
  - **状态**： 在地址 custodian/自治区。
  - **国家/地区**： custodian 所在; 国家/地区例如，"美国"或"英国"。
  - **Office**： 的业务 custodian 就地的办公室位置。

- 案例信息

  - **挂起状态**： 指示是否已 custodian 置于保持状态。 
  - **通信状态**： 指示是否已被 custodian 颁发保留通知。如果管理员已发布一条通知，然后这将被标记为*已发布*。如果管理员不发出通知，则将此状态*未发布*。 
  - **状态**： 这种情况内 custodian 的状态。如果管理员是仍处于保持状态的大小写，这将处于*活动状态*。如果管理员已从案例，其状态将更改为*发布*。 

- 处理状态

  - **索引状态**： 指示深入索引作业的状态。  
  - **索引上次更新时间**： 指示上次触发深入索引作业时的日期戳。
  - **数据源**： 显示的邮箱、 网站和团队已选定为 custodian 的计数。

## <a name="updating-a-custodian"></a>更新管理员

随着案例进展，您可能会发现可能会出现与特定 custodian & 相关的其他数据源您的案例。在其他情况下，您可能要删除已审阅并视为不相关的特定数据源。

若要更新管理员和所选的数据源：

1. 从**电子数据展示 > 高级电子数据展示 (Preview)** 中选择现有用例。
  
2. 情况下，单击**管理员**选项卡。
  
3. 从列表中选择 custodian(s)，单击**编辑源**。
  
4. 通过单击**选择数据源**中更新 Exchange 和 OneDrive 位置的选择。
  
5. 添加或删除工作组、 SharePoint、 或 Exchange 邮箱映射用户通过单击**选择其他数据源**。有关如何可以映射数据源到管理员的详细信息，请参阅[的高级电子数据展示 (Preview) 中添加管理员案例](add-custodians-to-case.md)。
  
6. 若要更新的 custodian 保留状态，单击**位置监控保留**，和启用或禁用管理员保留项。

> [!TIP]
> 您可以选择多个管理员执行批量操作，如重新编制索引、 释放，或编辑一的管理员。

## <a name="resolving-custodian-processing-errors"></a>处理 custodian 处理错误

在大多数法律工作流中，管理员添加的特定调查之后, 将搜索的用户的数据子集。由于大文件大小或可能已损坏，管理员的数据源中的某些项目可能部分索引。使用高级电子数据展示 （预览） 深度索引功能，这些部分索引的项可以自动修正通过重新爬网并重新编制索引按需型这些项。 

当管理员添加到种情况下时，他们的数据将自动"深度编制"，从而允许用户离开这些部分编制索引的位置，而不必下载、 修正和重新运行搜索之外 Office 365 中的项目。生命周期内种情况下，用户可能修正项目或给定 custodian 添加新数据源。这可能需要将更新的 Custodian 索引。 

若要部分触发地址重新索引进程的索引项：

1. 转到**电子数据展示 > 高级电子数据展示 （预览）** 并选择一个现有的情况。

2. 情况下，单击**管理员选项卡**。 

3. 选择需要重新编制索引，custodian(s)，然后单击在弹出上的**更新索引**。

4. 单击**管理员**选项卡上的**索引作业状态**列中的链接来检查 custodian 索引的状态。  

5. 在**作业**选项卡上，还可以跟踪重新索引进程的状态。

有关重新索引和补救部分索引项的详细信息，请参阅[处理高级电子数据展示 (Preview) 中的错误的修复](processing-data-for-case.md)。

## <a name="releasing-a-custodian-from-a-case"></a>释放从案例管理员

管理员年发布的情况下，种情况下关闭、 custodian 不再义务保留内容的情况下，或当管理员将被视为不再可能相关到特定 case。 

如果保留通知已发布后，管理员释放时，将向管理员发送发行说明。此外，还将删除任何监控保留的已发布的管理员。

如果管理员发出保持无提示他们已未发出任何合法保留通知，任何监控保留的已发布的管理员将被删除。  

发布管理员： 

1.  转到**管理员**选项卡。

2.  从列表中选择 custodian 和弹出页上，单击**版本管理员**。

    在**管理员**选项卡上 custodian 的状态设置为**发布**和**挂起状态**弹出上更改为**非活动**。 

> [!TIP]
> 管理员将同时中可能涉及几个合法保留案件。当管理员从案例释放时，保存和其他案件通知不会受到影响。

## <a name="related-information"></a>相关信息

 - Active Directory 中的用户属性 
 - [修正处理错误时出现的错误](error-remediation.md) 
 - [处理通信](managing-custodian-communications.md)

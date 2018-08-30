---
title: 处置评审概述
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d0c6095b-bfee-4906-a2c7-89c2d7f411c1
description: 在创建时保持在原有的 Office 365 中的内容的标签，您可以选择触发处置回顾末尾的保留期。
ms.openlocfilehash: c0a2933f597c9b314ac4ce2e72de9619fac90082
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013716"
---
# <a name="overview-of-disposition-reviews"></a>处置评审概述

当内容到达其保留期结束时，有几个原因为什么您可能想要查看的内容来确定是否它可安全删除 （"释放"）。例如，您可能需要：
  
- 挂起发生诉讼或审核相关的内容的删除 （"处置"）。
    
- 如果该内容研究或历史记录的值，请从处置列表中存档存储中删除内容。
    
- 将不同的保留期分配到内容，如果原始策略临时或临时解决方案。
    
- 返回到客户端的内容或转接到另一个组织。
    
在创建时保持在原有的 Office 365 中的内容的标签，您可以选择触发处置回顾末尾的保留期。处置回顾： 中
  
- 您选择的人接收电子邮件通知他们拥有要查看内容。这些审阅者可以是单个用户、 通讯组或安全组或 Office 365 组。请注意，在每周的基础上，会发送通知。
    
- 审阅者转到安全的**处置**页&amp;合规性中心以查看内容。 
    
- 对于每个文档审阅者可以：
    
  - 应用不同的标签。
    
  - 扩展其保留期。
    
  - 永久删除它。
    
- 审阅者可以查看挂起或历史处置情况，并将该列表导出为.csv 文件。
    
请注意该处置评审需要的 Office 365 企业 E5 订阅。
  
处置回顾可以在 Exchange 邮箱、 SharePoint 网站、 OneDrive 帐户和 Office 365 组包含内容。仅在审阅者选择要永久删除内容后，则删除等待处置回顾这些位置中的内容。
  
![处置页](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a>通过创建一个标签处置审阅设置

这是设置处置审阅的基本工作流程。请注意，此流显示标签正在发布，然后手动应用的用户;或者，将触发处置回顾标签可以是自动应用于的内容。
  
![显示如何处置工作流图表](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
处置回顾是一个选项，当您在 Office 365 中创建标签。请注意，此选项不可用，但仅在使用保留设置标签中保留策略中。
  
有关标签的详细信息，请参阅[Overview of 标签](labels.md)。
  
![Label 的保留设置](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a>释放内容

审阅者通知通过电子邮件时该内容已准备好查看，可以继续转到安全的**处置**页&amp;合规性中心和选择一个或多个项目。然后可以审阅者： 
  
- 应用不同的标签。
    
- 扩展的保留期。
    
- 永久删除项目。
    
审阅者可以使用以下链接查看文档中的原始位置，如果审阅者具有对该位置的权限。在处置评审，过程内容永远不会移从其原始位置和永远不会删除之前审阅者选择这样做。
  
请注意，给审阅者每周执行自动发送电子邮件通知。因此，当内容到达其保留期结束时，可能需要最多七天的审阅者接收电子邮件通知的内容正在等待处置。
  
另请注意，审核所有处置操作。若要确保这一点，您必须启用审核功能至少一天的第一个处置操作-之前的详细信息，请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。 
  
![文档的处置选项](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a>处置的权限

若要获取对**处置**页面的访问，请审阅者必须**处置管理**角色和**仅查看审核日志**角色的成员。我们建议创建名处置审阅者的新角色组和将这两种角色添加到角色组，然后添加到角色组的成员。 
  
有关详细信息，请参阅[向 Office 365 安全性授予用户访问&amp;合规性中心](grant-access-to-the-security-and-compliance-center.md)
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>多长时间，直到释放的内容将被永久删除

仅在审阅者选择要永久删除内容后，则删除等待处置查看的内容。当审阅者选择此选项时，变为是否可以使用本节中所述的标准的清理过程中的 SharePoint 网站或 OneDrive 帐户的内容：[保留策略就地处理内容的方式](retention-policies.md#how-a-retention-policy-works-with-content-in-place)。
  
这意味着：
  
- 将文档库中的内容移动到第一阶段回收站**中 7 天**的处置，然后之后的永久删除**93 天**。回收站不通过搜索索引，因此其内容，不到电子数据展示保留可用。 
    
- 内容在演示文稿保留库将永久删除**7 天内**的处置。 
    
## <a name="view-pending-and-completed-dispositions"></a>查看挂起的和已完成的处置情况

在安全的**处置**页上&amp;合规性中心，您可以查看挂起的和已完成的处置情况： 
  
- **待处理**的处置情况已到达其保留期结束，并且需要处置审阅。复查每个项目，决定是否要对其应用不同的标签、 扩展其保留期，或永久删除。 
    
- **已完成**处置情况已批准可用于在处置评审过程删除并现在正在被永久删除。具有不同的标签，应用或保留期扩展一部分回顾不会显示此处的项目。 
    
### <a name="filter-the-disposition-views"></a>筛选处置视图

您可以按标签或时间范围筛选这些视图。有关挂起的处置情况，时间范围基于的到期日期。为历史处置情况，时间范围基于删除日期。
  
![处置上的筛选器选项](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a>处置项目导出

此外，您可以将任一视图中的项目导出为.csv 文件可以在 Excel 中打开的。
  
![在 Excel 中的导出的处置数据](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  


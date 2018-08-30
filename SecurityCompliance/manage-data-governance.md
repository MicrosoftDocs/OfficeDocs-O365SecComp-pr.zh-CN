---
title: 管理 Office 365 中的数据管理
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 5/9/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 48064107-fed2-4db0-9e5c-aa5ddd5ccb09
description: 数据治理是确保您在需要时周围的数据并获取有关所有删除它时您不。Office 365 中的数据治理，您可以从导入和开始，到创建策略的保留并永久删除内容末尾处的数据存储管理完全内容生命周期。
ms.openlocfilehash: ca3443c3b90a067bf171ddf89be604d262a7b9a4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525922"
---
# <a name="manage-data-governance-in-office-365"></a>管理 Office 365 中的数据管理

数据治理是确保您在需要时周围的数据并获取有关所有删除它时您不。Office 365 中的数据治理，您可以从导入和开始，到创建策略的保留并永久删除内容末尾处的数据存储管理完全内容生命周期。
  
## <a name="import"></a>导入

某些数据可能存储在云中，如在本地服务器或第三方应用程序中之外的位置。导入服务，可以轻松以显示您发送消息，SharePoint 和 OneDrive 用于业务数据到 Office 365 中，通过将其上载直接通过网络或传送给我们的加密的驱动器。您可以在导入服务中使用智能导入功能实际上获取导入到的目标邮箱的 PST 文件中的项进行筛选。 
  
- [PST 文件导入 Office 365 概述](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)
    
- [使用网络上载将 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md)
    
- [使用驱动器寄送，将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- [使用 PST 集合工具查找、 复制和删除组织中的 PST 文件](find-copy-and-delete-pst-files-in-your-organization.md)
    
- [PST 文件导入到 Office 365 时筛选数据](filter-data-when-importing-pst-files.md)
    
- [使用 PowerShell cmdlet 将本地内容上传到 SharePoint Online](https://support.office.com/article/555049c6-15ef-45a6-9a1f-a1ef673b867c)
    
## <a name="govern-i-store-data"></a>调控 i： 存储数据

导入数据后，您可能需要增加存储。不受限制的存档功能 （称为自动扩展存档） 的 Office 365 中提供存档邮箱中存储无限的的量。
  
- [Office 365 安全性的存档邮箱启用&amp;合规性中心](enable-archive-mailboxes.md)

- [Office 365 中的无限制存档的概述](unlimited-archiving.md)
    
- [启用无限制存档的 Office 365](enable-unlimited-archiving.md)
    

    
## <a name="govern-ii-create-policies-and-labels-to-retain-content"></a>控制 II： 创建策略和保留内容的标签

保留策略可帮助您遵守主动行业法规和内部策略通过确保您保留只要但不再需要比的内容。单个保留策略可以代替您的整个组织。此外，您可以使用标签控制，您的组织内分类数据，然后强制实施基于该分类的保留规则以实现文件计划。
  
- [保留策略概述](retention-policies.md)
    
- [标签概述](labels.md)
    
- [批量创建和使用 PowerShell 发布标签](https://support.office.com/article/8986701b-ffa1-46ec-8fd0-8f7e81d5b25f.aspx)
    
- [处置评审概述](disposition-reviews.md)
    
- [事件驱动的保留概述](event-driven-retention.md)
    
## <a name="govern-iii-retain-the-email-of-former-employees"></a>控制 III： 保留以前的员工的电子邮件

当某人离开组织时，您可以通过创建非活动邮箱中保留其电子邮件。邮箱变为非活动时诉讼保留，Office 365 保留策略，或保留项的其他类型应用于该，然后删除相应的 Office 365 用户帐户。非活动邮箱中的项目的保留或保留策略的邮箱上发出，已处于非活动状态的持续时间内保留。
  
- [Office 365 中的非活动邮箱的概述](inactive-mailboxes-in-office-365.md)
    
- [创建和管理 Office 365 中的非活动邮箱](create-and-manage-inactive-mailboxes.md)

- [更改在 Office 365 中的非活动邮箱的保留持续时间](change-the-hold-duration-for-an-inactive-mailbox.md)
  
- [恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)
 
- [还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)

- [删除 Office 365 中的非活动邮箱](delete-an-inactive-mailbox.md)

## <a name="monitor"></a>监视

监督允许您定义捕获电子邮件和您的组织中的第三方通信，以便他们可以检查内部或外部的审阅者的策略。审阅者可以分类这些通信、 确保它们符合贵组织的策略和必要提升可疑材料。
  
您可以使用数据管理报告和标签活动资源管理器要监视的标签正应用于内容与您预期的一样。
  
- [配置组织的监督策略](configure-supervision-policies.md)
    
- [监督报表](supervision-reports.md)
    
- [查看文档的标签活动](view-label-activity-for-documents.md)
    
- [查看数据治理报表](view-the-data-governance-reports.md)
    
## <a name="more-information"></a>详细信息

- [观看 Microsoft 数据治理团队的视频](https://go.microsoft.com/fwlink/?linkid=867039)
    
- [观看 Office 365 中的数据调控概述](https://go.microsoft.com/fwlink/?linkid=852644)
    
- [Office 365 安全性&amp;合规性中心 cmdlet](https://go.microsoft.com/fwlink/?linkid=852310)
    


---
title: Office 365 中的电子数据展示
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 143b3ab8-8cb0-4036-a5fc-6536d837bfce
description: Office 365 提供了许多不同的电子数据展示工具, 可用于搜索和保存在不同位置 (如 Exchange 邮箱、SharePoint 和 OneDrive for business 网站、Office 365 组和 Skype for business 会话) 中找到的内容。
ms.openlocfilehash: 51ef4e744f2347fe3cdaff757131baf0c5fe83bf
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256800"
---
# <a name="ediscovery-in-office-365"></a>Office 365 中的电子数据展示

电子发现（亦称为"电子数据展示"）是用于识别和传递可用作法律案件证据的电子信息的过程。 您可以使用 Office 365 中的电子数据展示来搜索 Exchange Online 邮箱、Office 365 组、Microsoft 团队、SharePoint Online 和 OneDrive for business 网站以及 Skype for business 会话中的内容。 您可以使用 Security & 合规性中心中的内容搜索工具在相同的电子数据展示搜索中搜索邮箱和网站。 此外, 您还可以使用安全 & 合规性中心中的电子数据展示案例来标识、保留和导出邮箱和网站中的内容。 如果您的组织拥有 office 365 E5 订阅, 您可以使用 office 365 高级电子数据展示进一步分析内容。
  
Office 365 提供以下电子数据展示工具:
  
- [Security & 合规性中心中的内容搜索](ediscovery.md#contentsearch)
    
- [安全 & 合规中心中的电子数据展示案例](ediscovery.md#ediscoverycases)
    
- [Office 365 高级电子数据展示](ediscovery.md#advancedediscovery)
    
## <a name="content-search-in-the-security--compliance-center"></a>Security & 合规性中心中的内容搜索
<a name="contentsearch"> </a>

下表包含一些主题的链接, 这些主题将帮助您使用安全 & 合规性中心中的内容搜索工具。
  
|**主题**|**说明**|
|:-----|:-----|
|[在安全 & 合规中心中运行内容搜索](run-a-content-search-in-the-security-and-compliance-center.md) <br/> |了解如何使用内容搜索工具在单个搜索的 Office 365 组织中搜索邮箱、公用文件夹、Office 365 组、Microsoft 团队、SharePoint Online 网站、一个驱动器用于商业位置和 Skype for business 对话。  <br/> |
|[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md) <br/> |了解可用于在 Office 365 组织中搜索邮箱和网站中的内容的电子邮件和文件属性和搜索条件。  <br/> |
|[查看内容搜索结果的关键字统计信息](view-keyword-statistics-for-content-search.md) <br/> |了解如何使用搜索统计信息显示和比较一个或多个内容搜索的统计信息, 以及如何配置新的和现有的搜索以在搜索查询中返回每个关键字的统计信息。  <br/> |
|[在安全 & 合规中心中批量编辑内容搜索](bulk-edit-content-searches.md) <br/> |了解如何批量编辑一个或多个内容搜索的搜索查询和内容位置。  <br/> |
|[从 Security & 合规中心导出搜索结果](export-search-results.md) <br/> |了解如何导出内容搜索的结果。  <br/> |
|[提高导出 Office 365 中的电子数据展示搜索结果时的下载速度](increase-download-speeds-when-exporting-ediscovery-results.md) <br/> |了解如何在您的计算机上配置 Windows 注册表, 以提高通过导出内容搜索结果的下载速度。  <br/> |
|[导出内容搜索报告](export-a-content-search-report.md) <br/> |了解如何下载导出报告, 而无需导出实际搜索结果。  <br/> |
|[Security & 合规中心中的内容搜索限制](limits-for-content-search.md) <br/> |了解内容搜索工具的限制, 例如一次可以运行的最大搜索数。  <br/> |
|[内容搜索中未编制索引的项目](partially-indexed-items-in-content-search.md) <br/> |了解 Exchange 和 SharePoint 中的未编制索引的项目, 您可以在运行搜索时在估计的搜索结果统计信息中包含这些项目。 您还可以在导出搜索结果时包含未编制索引的项目。  <br/> |
|[Office 365 中的预计和实际电子数据展示搜索结果之间的差异](differences-between-estimated-and-actual-ediscovery-search-results.md) <br/> |了解估计的搜索结果数与导出的实际项目数之间可能存在差异的原因。  <br/> |
|[电子数据展示搜索结果中的重复数据删除](de-duplication-in-ediscovery-search-results.md) <br/> |了解在导出作为内容搜索结果的 Exchange 电子邮件时可启用的可选重复数据消除功能。  <br/> |
|[在 Office 365 组织中搜索并删除电子邮件](search-for-and-delete-messages-in-your-organization.md) <br/> |了解如何使用内容搜索来搜索和删除组织中*所有*邮箱的电子邮件。 这可帮助你查找和删除可能有害或高风险的电子邮件。  <br/> |
|[使用内容搜索在邮箱和 OneDrive for Business 站点中搜索用户列表](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) <br/> |了解如何使用脚本在邮箱和一个驱动器的业务网站中搜索一组用户。 使用[步骤 2:](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step2)在本主题中生成用户列表, 以快速生成在步骤3中创建和运行搜索时可用于源内容位置的电子邮件地址列表。  <br/> |
|[创建、报告和删除多个内容搜索](create-report-on-and-delete-multiple-content-searches.md) <br/> |了解如何使用脚本创建多个内容搜索, 运行报告以获取每个搜索的估计结果, 然后删除搜索。 这可以帮助您快速有效地识别和挑选搜索数据。  <br/> |
|[在安全 & 合规中心中克隆内容搜索](clone-a-content-search.md) <br/> |了解如何使用本文中的 Windows PowerShell 脚本快速克隆现有的内容搜索。 这可以帮助您比较不同关键字搜索查询在相同的内容位置运行的结果或节省时间, 这是因为创建新的搜索时无需重新输入大量的内容位置。  <br/> |
|[配置内容搜索的权限筛选](permissions-filtering-for-content-search.md) <br/> |了解如何使用权限筛选使电子数据展示管理器仅搜索您的 Office 365 组织中的一部分邮箱和网站。  <br/> |
|[准备 CSV 文件以实现目标内容搜索](csv-file-for-an-id-list-content-search.md) <br/> |了解如何使用结果 .csv 文件或未编制索引的项目 .csv 文件 (其中包含有关内容搜索结果的信息) 来创建特定邮箱项目的目标搜索。  <br/> |
|[将 Office 365 中的内容搜索用于目标集合](use-content-search-for-targeted-collections.md) <br/> |了解如何使用本文中的 Windows PowerShell 脚本, 以使用内容搜索来执行目标集合。 目标集合表示要搜索特定的文件夹, 因为您确信项目的响应方式 (或特权项目) 位于该文件夹中。 使用本文中的脚本获取要搜索的特定邮箱或网站文件夹的文件夹 ID 或路径。  <br/> |
|[使用内容搜索来搜索导入到 Office 365 的第三方数据](use-content-search-to-search-third-party-data-that-was-imported.md) <br/> |了解如何使用`kind`和`itemclass`邮件属性来搜索导入到 Office 365 的第三方数据。  <br/> |
   
[Return to top](ediscovery.md#top)
  
## <a name="ediscovery-cases-in-the-security--compliance-center"></a>安全 & 合规中心中的电子数据展示案例
<a name="ediscoverycases"> </a>

下表包含一些主题的链接, 这些主题将帮助您在安全 & 合规性中心中使用电子数据展示事例。 用例添加可访问该案例的成员, 在与该案例相关的内容位置放置保留, 将多个内容搜索与该案例相关联, 并从该案例中导出搜索结果。
  
|**主题**|**说明**|
|:-----|:-----|
|[在安全 & 合规中心中管理电子数据展示事例](manage-ediscovery-cases.md) <br/> |了解如何在安全 & 合规中心中创建和管理电子数据展示事例。  <br/> |
|[在 Office?? 中分配电子数据展示权限？365安全 & 合规中心](assign-ediscovery-permissions.md) <br/> |了解如何在安全 & 合规中心中分配电子数据展示权限。 您可以分配权限以让用户创建电子数据展示事例、创建与电子数据展示事例关联的保留、运行内容搜索、预览搜索结果和导出搜索结果。  <br/> |
|[在 Office 365 中的电子数据展示事例中创建保留报告](create-a-report-on-holds-in-ediscovery-cases.md) <br/> |了解如何使用本文中的 Windows PowerShell 脚本生成一个报告, 其中包含有关与 Security & 合规中心中的电子数据展示事例相关联的所有保留的信息。  <br/> |
|[使用脚本将用户添加到安全 & 合规性中心的电子数据展示事例中的保留项](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) <br/> |了解如何使用本文中的 Windows PowerShell 脚本快速将邮箱和 OneDrive for business 网站添加到与 Security & 合规中心中的电子数据展示事例相关联的新保留中的用户列表。  <br/> |
|[在 Office 365 审核日志中搜索电子数据展示活动](search-for-ediscovery-activities-in-the-audit-log.md) <br/> |了解如何在 Office 365 审核日志中搜索与创建和管理电子数据展示事例和内容搜索相关的活动。  <br/> |
   
[Return to top](ediscovery.md#top)
  
## <a name="office-365-advanced-ediscovery"></a>Office 365 高级电子数据展示
<a name="advancedediscovery"> </a>

下表包含一些主题的链接, 这些主题将帮助您了解和使用 Office 365 中的高级电子数据展示工具。
  
|**主题**|**说明**|
|:-----|:-----|
|[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md) <br/> |了解高级电子数据展示工具如何帮助您分析 Office 365 中的数据、优化文档审阅和制定高效的电子数据展示的决策。  <br/> |
|[高级电子数据展示的快速设置](quick-setup-for-advanced-ediscovery.md) <br/> |了解如何开始使用高级电子数据展示。  <br/> |
|[为 Office 365 高级电子数据展示准备搜索结果](prepare-search-results-for-advanced-ediscovery.md) <br/> |了解如何在高级电子数据展示中准备内容搜索中的结果以进行分析。  <br/> |
|[在 Office 365 高级电子数据展示中设置用户和事例](set-up-users-and-cases-in-advanced-ediscovery.md) <br/> |了解如何配置用户角色、创建事例以及将用户分配给高级电子数据展示中的案例。  <br/> |
|[运行进程模块并加载数据](run-the-process-module-and-load-data-in-advanced-ediscovery.md) <br/> |了解使用高级电子数据展示为分析准备案例文件的指南。  <br/> |
|[在 Office 365 高级电子数据展示中使用快速分析](use-express-analysis-in-advanced-ediscovery.md) <br/> |了解如何运行高级电子数据展示的快速分析模式以快速分析事例并导出结果。  <br/> |
|[使用高级电子数据展示分析事例数据](analyze-case-data-with-advanced-ediscovery.md) <br/> |获取分析过程的概述, 它允许您设置参数、运行选项并在高级电子数据展示中查看结果。  <br/> |
|[管理高级电子数据展示相关性设置](manage-relevance-setup-in-advanced-ediscovery.md) <br/> |阅读有关设置高级电子数据展示中的相关性培训的建议, 以通过其相关性对文件进行分数和生成分析结果。  <br/> |
|[使用高级电子数据展示相关性模块](use-relevance-in-advanced-ediscovery.md) <br/> |了解高级电子数据展示中的相关性模块, 包括用于培训和文件审阅的工作流和指南以及步骤。  <br/> |
|[使用高级电子数据展示导出事例数据](export-case-data-in-advanced-ediscovery.md) <br/> |了解导出电子数据展示事例数据的准则和外部评审的结果。  <br/> |
|[提高导出 Office 365 中的电子数据展示搜索结果时的下载速度](increase-download-speeds-when-exporting-ediscovery-results.md) <br/> |了解如何配置 Windows 注册表以提高从高级电子数据展示导出事例数据时的下载速度。  <br/> |
   
[Return to top](ediscovery.md#top)
  


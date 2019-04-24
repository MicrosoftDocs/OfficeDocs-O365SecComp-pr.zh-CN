---
title: 在 Microsoft 365 中管理数据外泄事件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文介绍了如何使用安全 & 合规中心中的新数据调查 (预览版) 工具管理数据外泄事件。
ms.openlocfilehash: 93a98a4e01df011b789ba2453734f093ad8c19d6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258820"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a>在 Microsoft 365 中管理数据外泄事件

数据外泄是在不受信任的环境中发布包含机密、敏感或恶意信息的文档时。 检测到 data 外泄事件时, 重要的是要快速包含环境、评估外泄的大小和位置、检查其周围的用户活动, 然后从服务中删除溢出的数据。 使用 "数据调查 (预览)" 工具, 您可以在 Office 365 中搜索敏感的恶意数据或误放的数据, 调查以了解所发生的情况, 然后采取相应的操作。  

## <a name="scope-of-this-article"></a>本文的范围

本文提供了有关如何从 Office 365 邮箱中永久删除项目的说明列表, 以便用户或管理员无法再访问或恢复这些项目。 

> [!NOTE]
> 删除位于 SharePoint 或 OneDrive for business 网站中的项目时, 它们将在从其原始位置删除它们的时间内保留93天。

## <a name="scenario"></a>方案

您会收到一条数据外泄事件, 其中员工在不知情的情况下通过电子邮件与多个人共享高度机密的文档。 您希望快速评估在您的组织内部和外部收到此文档的用户。 在调查事件之后, 您计划与其他调查人员共享您的发现以进行查看, 然后从 Office 365 中永久删除溢出的数据。 调查完成后, 您想要删除所有证据。 

## <a name="workflow"></a>工作流

以下是使用数据调查 (预览版) 管理数据外泄事件的工作流:

1.  创建数据调查。

2.  搜索敏感、恶意或放错位置的数据, 并将其作为证据收集。

3.  查看并调查证据。

4.  永久删除溢出的数据。

5.  关闭或删除调查。


## <a name="before-you-begin"></a>准备工作

- 您将使用安全 & 合规性中心中的 "数据调查 (预览)" 工具创建调查, 搜索溢出的数据, 并对其进行审阅和分析。 然后, 使用安全 & 合规性中心 PowerShell 从 Office 365 中永久删除溢出的数据。 

- 若要创建调查, 您必须是 Security & 合规性中心中合规性管理员角色组的成员。

- 若要删除邮件, 您必须是安全 & 合规性中心中分配了搜索和清除角色的角色组的成员。 默认情况下, 将此角色分配给 "组织管理" 角色组。 有关向角色组添加用户的信息, 请参阅[Security & 合规性中心中的权限](../permissions-in-the-security-and-compliance-center.md)。 

- 若要控制调查人员可以搜索哪些用户邮箱和 OneDrive 帐户, 您的组织可以设置合规性边界。 有关详细信息, 请为[电子数据展示调查设置合规性边界](../set-up-compliance-boundaries.md)。 

## <a name="step-1-create-a-data-investigation"></a>步骤 1: 创建数据调查

若要在数据调查 (预览) 工具中创建调查, 请执行以下操作:

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com)。
    
2. 使用工作或学校帐户登录到 Office 365。
    
3. 在 "合规性中心" 中, 单击 "**数据调查**"。
 
4. 在 "**数据调查 (预览)** " 页上, 单击 "**创建新调查**"。
    
5. 在 "**新建数据调查**" 飞出页面上, 将调查命名为 "(必需)", 然后键入可选调查编号和说明。 请注意, 该名称在您的组织中必须是唯一的。

6. 在 "是否要在**创建此调查后配置其他设置？**" 下, 执行下列操作之一:

    - 单击 **"是"** 创建调查, 并在新事例中显示 "**设置**" 页。 这样, 您就可以将成员添加到调查中。
    
    - 单击 "**否**" 仅创建调查并将其显示在 "**数据调查 (预览)** " 页上的事例列表中。 如果选择此选项, 则将作为调查的唯一成员添加, 并且将使用默认搜索和分析设置。 您可以在创建调查之后随时添加成员或更改设置。

7. 单击 "**保存**" 以创建调查。

    新调查显示在 "**数据调查 (预览)** " 页面上的列表中。 

8. 若要打开调查, 请单击调查的名称。 

    将显示调查的 "**主页**" 选项卡。 

> [!TIP]
> 考虑建立调查的命名约定, 并在名称和说明中提供尽可能多的信息, 以便在将来需要时可以找到并参考。
 
## <a name="step-2-search-for-the-spilled-data"></a>步骤 2: 搜索溢出的数据 
 
如果您知道要在哪些用户中搜索溢出的数据, 则可以将其添加为感兴趣的人, 以将他们的数据源映射到调查并快速搜索其邮箱和 OneDrive 帐户。 若要添加调查的相关人员, 请单击 "**感兴趣的人员**", 然后单击 "**添加感兴趣的人员**"。 有关详细信息, 请参阅[管理感兴趣的人员](manage-people-of-interest.md)。

在 "**搜索**" 选项卡上, 您可以创建搜索以查找溢出的数据。 您将使用用于查找溢出数据的搜索查询, 以在[步骤 4](#step-4-delete-the-spilled-data)中删除这些相同的邮件。 有关创建搜索的详细信息, 请参阅[在调查中搜索数据](search-for-data.md)。

运行搜索后, 可以预览搜索结果的示例并查看搜索统计信息, 以评估搜索查询的有效性。 确定要从 Office 365 中删除的项目后, 可以单击 "**证据**" 选项卡, 然后创建一个证据集并添加包含这些项目的搜索结果。 

若要执行此操作, 请单击要调查的搜索。 在弹出页面上, 单击 "**将结果添加到证据**" 并按照说明进行操作。 然后, 在证据中, 可以查看各个文档、调查谁有权访问文档以及导出文档。 若要仅删除文档而不是查看文档, 请转到[步骤 4](#step-4-delete-the-spilled-data)。 

> [!IMPORTANT]
> 您在搜索查询中使用的关键字可能包含要搜索的实际溢出数据。 例如, 如果搜索包含社会保险号码的文档, 并将其用作搜索查询中的关键字, 则必须随后删除该查询以避免进一步外泄。 您可以删除搜索或删除[步骤 5](#step-5-close-or-delete-the-investigation)中的整个调查。 

## <a name="step-3-review-and-investigate"></a>步骤 3: 审阅和调查 

在调查中, 转到 "**证据**" 选项卡, 然后单击您在上一步中创建的证据集。 完成处理作业并将搜索结果添加到证据之后, 可以查看以本机格式、文本格式或接近本机格式的单个文档。 您可以创建其他查询来缩小文档列表的范围, 并标记文档以指示调查中的结果。 有关详细信息, 请参阅[查看证据中的数据](review-data-in-evidence.md)

若要对文档进行分组并获取更多的审阅帮助, 请单击 "**管理证据**"。 在**分析**磁贴中, 单击 "**分析**"。 这将运行高级分析, 例如重复检测、电子邮件线程和主题分析。 有关详细信息，请参阅：

- [运行分析功能，加快调查](run-analytics-to-investigate-faster.md)
- [近似重复检测](near-duplicates.md)
- [电子邮件会话](email-threading.md)
- [主题](themes.md)

若要确定数据外泄中涉及哪些用户, 可以在证据集中创建一个新查询, 然后使用发件人/作者和收件人条件。 这将创建在已添加到证据的收集数据中找到的所有发件人、收件人和作者的列表。 请务必检查列表以确定是否存在外部用户。 有关使用条件来缩小搜索结果范围的详细信息, 请参阅[搜索条件](../keyword-queries-and-search-conditions.md#search-conditions)。

## <a name="step-4-delete-the-spilled-data"></a>步骤 4: 删除溢出的数据

### <a name="deleting-mailbox-items"></a>删除邮箱项目

在您查看并验证搜索结果只包含必须删除的电子邮件后, 您可以通过在安全 & 合规性中运行**new-compliancesearchaction-PurgeType HardDelete**命令来永久删除它们。Center PowerShell。 有关说明, 请参阅[搜索和删除电子邮件](../search-for-and-delete-messages-in-your-organization.md)。 

如果为组织中的邮箱启用了单个项目恢复, 则永久删除的项目将保留在用户的 "可恢复的项目" 文件夹中 (并由管理员访问), 直到已删除项目的保留期结束 (默认值为14天)。 此外, 如果任何包含溢出数据的邮箱处于法定保留状态或分配到保留策略, 则清除的邮件将保留在 "可恢复的项目" 文件夹中, 直到项目的保留期过期。 若要立即删除邮件, 您需要执行添加任务。 有关说明, 请参阅[在保留时, 删除基于云的邮箱的 "可恢复的项目" 文件夹中的项目](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)。  

> [!IMPORTANT]
> 在删除保留策略或保留策略之前, 请与您的记录管理或法律部门进行确认。 您的组织可能有定义邮箱处于保留状态或 data 外泄事件是否优先的策略。 

### <a name="deleting-site-items"></a>删除网站项

若要从 SharePoint 网站或 OneDrive 帐户中永久删除文档, 您必须删除该文档, 然后必须从网站回收站中删除它, 然后将其从网站集回收站中删除。 有关详细信息, 请参阅[删除 SharePoint 和 OneDrive 中的文档](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business)。

或者, 您可以删除可能包含溢出数据的整个网站集。 有关说明, 请参阅[删除网站集](https://docs.microsoft.com/sharepoint/delete-site-collection)。

## <a name="step-5-close-or-delete-the-investigation"></a>步骤 5: 关闭或删除调查

在 live service 中删除源内容位置 (邮箱或网站) 中的文档后, 您仍将拥有在调查过程中添加到证据的这些文档的副本。 若要避免进一步的数据外泄, 应考虑删除调查本身。

若要删除调查, 请执行以下操作:

1. 在 "**设置**" 选项卡上, 单击 "**调查信息**"。

2. 单击 "**删除调查**"。 

如果不需要删除调查, 或者要保存在调查过程中收集的信息, 则可以单击 "**关闭事例**"。 稍后, 您可以重新打开已关闭的调查。
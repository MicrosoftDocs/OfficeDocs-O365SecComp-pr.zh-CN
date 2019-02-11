---
title: 管理 Microsoft 365 中的数据泄漏事件
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
description: 本文介绍如何使用 Office 365 安全性 & 合规性中心中新数据调查 （预览） 工具管理数据损耗情况事件。
ms.openlocfilehash: d7adc17d01a0ae2ad6b7bfb7052862a5a6419882
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706173"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a>管理 Microsoft 365 中的数据泄漏事件 

机密文档发布到不受信任的环境时，数据泄漏。检测到数据泄漏事件时，务必快速评估的大小和位置的损耗情况、 检查周围的用户活动，然后在系统中永久清除溅入的数据。

## <a name="scope-of-this-article"></a>本文的范围

本文提供有关如何从永久移除项 Office 365 邮箱，以使其无法再访问或由用户或管理员可恢复的说明的列表。 

> [!NOTE]
> 如果删除项目位于中 SharePoint 或 OneDrive for Business 站点，他们将会保留 93 天从其原始位置从删除时间。

## <a name="scenario"></a>方案

数据泄漏其中员工不知情的情况下共享的事件高度机密文档与多人通过电子邮件会通知您。您希望快速评估谁接收此组织内外的文档。您已调查事件后，您打算与其他调查员查看，，然后从 Office 365 永久移除溅入的数据共享您的发现。完成调查后，您想要删除所有证据。 

## <a name="workflow"></a>工作流

下面是使用数据调查 （预览） 来管理数据泄漏事件的工作流：

1.  创建数据调查。

2.  搜索溅入数据。

3.  查看并调查事件。

4.  永久删除溅入的数据。

5.  关闭或删除调查。


## <a name="before-you-begin"></a>准备工作

- 将使用在 Office 365 安全性 & 合规性中心数据调查 （预览） 工具创建调查、 搜索溅入的数据，并查看和对其进行分析。然后您将使用安全 & 合规性中心 PowerShell 从 Office 365 中永久删除溅入的数据。 

- 若要创建调查，您必须是安全 & 合规性中心中的合规性管理员角色组的成员。

- 若要删除的邮件，您必须是安全 & 合规性中心中的 Organization Management 角色组的成员，或者为其分配搜索和清除角色。有关将用户添加到角色组的信息，请参阅[授予用户对安全 & 合规中心的访问](../grant-access-to-the-security-and-compliance-center.md)。 

- 若要控制的用户邮箱和 OneDrive 帐户调查员可以搜索，您的组织可以设置合规性边界。有关详细信息，请参阅[设置电子数据展示调查的合规性边界](../set-up-compliance-boundaries.md)。 

## <a name="step-1-create-a-data-investigation"></a>步骤 1： 创建数据调查

创建数据调查：

1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 使用工作或学校帐户登录到 Office 365。
    
3. 在安全 & 合规性中心中，单击**数据调查**。
 
4. 在**数据调查 （预览）** 页上，单击**创建新的调查**。
    
5. 在**新数据调查**弹出页上，为调查指定一个名称 （必需）、，然后键入可选调查号和说明。请注意，必须在组织中的唯一名称。

6. 在**您想要创建此调查后配置其他设置？**，执行下列操作之一：

    - 单击**是**以创建调查，并在新的情况下显示**设置**页。这样，您将成员添加到调查。
    
    - 单击**否**刚创建调查，并显示在**数据调查 （预览）** 页上的情况下的列表中。如果您选择此选项，您将添加将使用调查和默认搜索和分析设置的唯一成员。您可以添加成员，或创建调查后随时更改设置。

7. 单击**保存**以创建调查。

    在**数据调查 （预览）** 页上的列表中显示新的调查。 

8. 要打开调查，请单击调查的名称。 

    将显示调查的**主页**选项卡。 

> [!TIP]
> 请考虑建立调查的命名约定，并提供尽可能多的信息，您可以在名称和说明中，以便您可以找到并如有必要，以便将来参考。
 
## <a name="step-2-search-for-the-spilled-data"></a>步骤 2： 搜索溅入数据 
 
如果您知道要搜索的溅入数据的用户，您可以为感兴趣的用户将其数据源映射到调查和快速搜索其邮箱和 OneDrive 帐户添加它们。若要添加到调查值得关注的人员，单击**值得关注的人员**，，然后单击**添加人员感兴趣的**。 

在**搜索**选项卡，您可以创建搜索来查找溅入的数据。您将使用您用来查找要删除这些相同的[步骤 4](##step-4:-permanently-delete-the-spilled-data)中的邮件的溅入的数据的同一个搜索查询。有关创建搜索的详细信息，请参阅[Create 搜索以收集数据](create-search-to-collect-data.md)。

运行搜索后，您可以预览搜索结果以及查看搜索统计信息来评估您的搜索查询的有效性的示例。标识后您要从 Office 365 中删除的项目，您可以单击**事件**选项卡，然后创建一个事件，并添加包含这些项的搜索结果。 

若要执行此操作，单击您想要调查的搜索。在弹出页上，单击**添加到事件的结果**并按照说明进行操作。然后中事件，您可以查看各个文档、 调查曾访问文档，并导出文档。若要只删除而不是查看这些文档，请转到[步骤 4](##step-4:-permanently-delete-the-spilled-data)。 

> [!IMPORTANT]
> 搜索查询中使用的关键字可能包含您要搜索的实际溅入的数据。例如，如果您搜索包含社会保险号码和您的文档将其用作搜索查询中的关键字，则必须删除查询以后避免进一步损耗情况。您可以删除搜索或删除整个调查中[的步骤 5](##step-5:-close-or-delete-investigation)。 

## <a name="step-3-review-and-investigate"></a>步骤 3： 查看和调查 

在调查中，转到**事件**选项卡，然后单击您在上一步中创建的事件。完成处理作业和搜索结果添加到事件之后，您可以查看其本机格式、 文本格式或附近本机格式中的单个文档。您可以创建其他进一步缩小查询的文档和标记文档，以指明从您的调查研究结果列表。

要组合文档和获取有关您进行审阅的更多帮助，请单击**管理事件**。在**分析**图块，单击**分析**。这将运行高级分析功能，如重复检测、 电子邮件超线程和主题分析。有关详细信息，请参阅：

- [近似重复检测](near-duplicates.md)
- [电子邮件会话](email-threading.md)
- [主题](themes.md)

若要确定哪些用户参与数据损耗情况，可以在事件中创建一个新的查询，并将发件人/作者和收件人条件。这将创建所有发件人、 收件人和收集的数据添加到事件中找到的作者的列表。请务必检查列表以确定列表是否有任何外部用户。有关详细信息，请参阅[搜索条件](../keyword-queries-and-search-conditions.md#search-conditions)。

## <a name="step-4-permanently-delete-the-spilled-data"></a>步骤 4： 永久删除溅入的数据

### <a name="deleting-mailbox-items"></a>删除邮箱项目

查看并验证搜索结果包含必须要删除的电子邮件之后，可以永久删除它们通过运行**新建 ComplianceSearchAction-清除-PurgeType HardDelete**命令中安全 & 合规性中心 PowerShell。有关说明，请参阅[搜索和删除电子邮件](../search-for-and-delete-messages-in-your-organization.md)。 

请注意，如果在组织中的邮箱启用单个项目恢复永久删除项目将被保留用户可恢复的项目文件夹中 （可由管理员访问） （默认值为 14 天） 的已删除的邮件保留期结束之前。此外，如果任何包含溅入的数据的邮箱的合法保留或分配给保留策略，清除的邮件将保留在可恢复的项目文件夹直到保留被删除或邮箱排除从保留策略。硬删除消息立即，您需要执行添加任务。有关说明，请参阅[删除在可恢复项目文件夹中的基于云的邮箱的保留的项目](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)。  

> [!IMPORTANT]
> 删除保留或保留策略之前，请与记录管理或法律部门。您的组织可能有定义上的邮箱是否保留策略或数据泄漏事件优先。 

### <a name="deleting-site-items"></a>删除网站项目

业务帐户从 SharePoint 网站或 OneDrive 中永久删除文档，您必须将其删除，那么您需要从网站中删除，然后从网站集回收站中删除它。有关说明，请参阅[删除 SharePoint 和 OneDrive 中的文档](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business)。

或者，也可以删除整个网站集可能包含溅入的数据。有关说明，请参阅[删除网站集](https://docs.microsoft.com/sharepoint/delete-site-collection)。

## <a name="step-5-close-or-delete-the-investigation"></a>步骤 5： 关闭或删除调查

删除源内容位置 （邮箱或网站） 中的文档后，您仍将具有这些作为调查的一部分添加到事件的文档的副本。若要避免进一步数据损耗情况，您应考虑删除调查。

删除调查：

1. 在**设置**选项卡中，单击**调查信息**。

2. 单击**删除用例**。 

如果您无需删除调查，或者如果您想要保存过程调查中收集的信息，您可以单击**关闭事例**。以后，您可以重新打开已关闭的调查。
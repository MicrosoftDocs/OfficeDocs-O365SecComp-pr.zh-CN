---
title: Microsoft 365 中的高级电子数据展示 (预览) 概述
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
description: 本文介绍了 Microsoft 365 中高级电子数据展示 (预览) 的新版本。
ms.openlocfilehash: 2296f4ee1867cacc90eada9e5f12888a8ea0d242
ms.sourcegitcommit: 13c601ea11ce6a3c71036fdafda059061c6998d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2019
ms.locfileid: "30313148"
---
# <a name="overview-of-advanced-ediscovery-preview-in-microsoft-365"></a><span data-ttu-id="fd218-103">Microsoft 365 中的高级电子数据展示 (预览) 概述</span><span class="sxs-lookup"><span data-stu-id="fd218-103">Overview of Advanced eDiscovery (Preview) in Microsoft 365</span></span>

<span data-ttu-id="fd218-p101">Microsoft 刚发布了更新的高级电子数据展示工具的预览版本, 该工具构建在 Office 365 中的现有电子数据展示功能之上。此预览版本 (称为 "*高级电子数据展示 (预览)")* 提供了一种端到端工作流, 用于保留、收集、查看、分析和导出对组织的内部和外部调查做出响应的内容。</span><span class="sxs-lookup"><span data-stu-id="fd218-p101">Microsoft has just released a preview version of the updated Advanced eDiscovery tool that builds on the existing eDiscovery capabilities in Office 365. This preview version, called *Advanced eDiscovery (Preview)*, provides an end-to-end workflow to preserve, collect, review, analyze, and export content that's responsive to your organization's internal and external investigations.</span></span> 

## <a name="alignment-with-edrm"></a><span data-ttu-id="fd218-106">与 EDRM 的对齐方式</span><span class="sxs-lookup"><span data-stu-id="fd218-106">Alignment with EDRM</span></span>

<span data-ttu-id="fd218-107">高级电子数据展示 (预览) 的内置工作流与电子发现参考模型 (EDRM) 中列出的电子数据展示过程相一致。</span><span class="sxs-lookup"><span data-stu-id="fd218-107">The built-in workflow of Advanced eDiscovery (Preview) aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span> 

![电子发现参考模型 (EDRM)](../media/EDRMv1.png)

<span data-ttu-id="fd218-p102">(图像源 edrm.net。在 "创造性 Commons 归属 3.0 Unported" 许可证下提供了源映像。</span><span class="sxs-lookup"><span data-stu-id="fd218-p102">(Image source courtesy of edrm.net. The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="fd218-111">从较高的层次来看, 高级电子数据展示 (预览版) 支持 EDRM 工作流的方式如下:</span><span class="sxs-lookup"><span data-stu-id="fd218-111">At a high level, here's how Advanced eDiscovery (Preview) supports the EDRM workflow:</span></span>

- <span data-ttu-id="fd218-p103">**标识**-在调查中发现潜在的兴趣方面后, 可以将其添加为保管人 (也称为*data 保管人*, 因为它们可能会将与调查相关的信息) 到高级电子数据展示 (预览) 案例。将用户添加为保管人后, 可以轻松地保留、收集和查看保管人文档。</span><span class="sxs-lookup"><span data-stu-id="fd218-p103">**Identification** - After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to a Advanced eDiscovery (Preview) case. After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="fd218-p104">**保留**-若要保留和保护与调查相关的数据, 高级电子数据展示 (预览) 允许您在某个情况下对与保管人相关的数据源施加合法保留。您还可以将非 custodial 数据置于保留状态。此外, 高级电子数据展示 (预览) 具有内置通信工作流, 因此您可以向保管人发送法律保留通知并跟踪其确认。</span><span class="sxs-lookup"><span data-stu-id="fd218-p104">**Preservation** - To preserve and protect data that's relevant to an investigation, Advanced eDiscovery (Preview) lets you place a legal hold on the data sources associated with the custodians in a case. You can also place non-custodial data on hold. Additionally, Advanced eDiscovery (Preview) has a built-in communications workflow so you can send a legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="fd218-117">**集合**-确定 (并保留) 与调查相关的数据源后, 您可以使用内置搜索工具在高级电子数据展示 (预览) 中搜索和收集 custodial 数据源 (和非 custodial 中的实时数据)。可能与案例相关的数据源 (如果适用)。</span><span class="sxs-lookup"><span data-stu-id="fd218-117">**Collection** - After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery (Preview) search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="fd218-p105">**处理**-在收集了与事例相关的所有数据之后, 下一步是处理它以供进一步查看和分析。在高级电子数据展示 (预览版) 中, 这意味着在集合阶段中标识的就地数据复制到 Azure 存储位置 (称为 "*工作集*"), 这将为您提供事例数据的静态视图。</span><span class="sxs-lookup"><span data-stu-id="fd218-p105">**Processing** - After you've collected all data relevant to the case, the next step is process it for further review and analysis. In Advanced eDiscovery (Preview), this means the in-place data that you identified in the collection phase is copied to an Azure storage location (called a *working set*), which provides you with a static view of the case data.</span></span> 
 
- <span data-ttu-id="fd218-p106">**审核**-在将数据添加到工作集后, 可以查看特定文档并运行其他查询, 以将数据缩减为与事例最相关的内容。此外, 还可以为特定文档添加批注和标记。</span><span class="sxs-lookup"><span data-stu-id="fd218-p106">**Review** - After data has been added to a working set, you can view specific documents and run additional queries to reduce the data to what is most relevant to the case. Additionally, you can annotate and tag specific documents.</span></span>
 
- <span data-ttu-id="fd218-p107">**分析**-高级电子数据展示 (预览版) 提供集成的分析工具, 可帮助您从确定的工作集中进一步挑选数据, 从而不与调查相关。除了减少相关数据量之外, 高级电子数据展示 (预览) 还通过让您能够组织内容以使审阅过程更简单、更高效, 从而帮助您节省法律考评成本。</span><span class="sxs-lookup"><span data-stu-id="fd218-p107">**Analysis** - Advanced eDiscovery (Preview) provides integrated analytics tools that helps you further cull data from the working set that you determine isn't relevant to the investigation. In addition to reducing the volume of relevant data, Advance eDiscovery (Preview) also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="fd218-p108">**生产**和**演示**-准备就绪后, 可以从工作集中导出文档以进行法律审查。您可以按其本机格式或 EDRM 格式导出文档, 以便可以将其导入第三方审阅应用程序中。</span><span class="sxs-lookup"><span data-stu-id="fd218-p108">**Production** and **Presentation** - When you're ready, you can export documents from a working set for legal review. You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="advanced-ediscovery-preview-workflow"></a><span data-ttu-id="fd218-126">高级电子数据展示 (预览) 工作流</span><span class="sxs-lookup"><span data-stu-id="fd218-126">Advanced eDiscovery (Preview) workflow</span></span>

<span data-ttu-id="fd218-p109">以下各节介绍高级电子数据展示 (预览) 中的内置工作流中的每个步骤。以下屏幕截图显示了名为 "*产品责任 2019002*" 的事例的 "**主页**" 选项卡。注释将对页面顶部的工作流选项卡进行排序, 使其与 EDRM 进程一致。</span><span class="sxs-lookup"><span data-stu-id="fd218-p109">The following sections describe each step in the built-in workflow in Advanced eDiscovery (Preview). The following screenshot shows the **Home** tab of a case named *Product Liability 2019002*. Note the workflow tabs at the top of the page are sequenced to align with the EDRM process.</span></span> 

<span data-ttu-id="fd218-130">有关高级电子数据展示中的端到端工作流的详细信息 (预览), 请参阅此[Microsoft 机械视频](https://go.microsoft.com/fwlink/?linkid=2066133)。</span><span class="sxs-lookup"><span data-stu-id="fd218-130">For more information about the end-to-end workflow in Advanced eDiscovery (Preview), see this [Microsoft Mechanics video](https://go.microsoft.com/fwlink/?linkid=2066133).</span></span> 

![高级电子数据展示中的选项卡 (预览) 关注 EDRM 工作流](../media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a><span data-ttu-id="fd218-132">管理保管人</span><span class="sxs-lookup"><span data-stu-id="fd218-132">Managing custodians</span></span>

<span data-ttu-id="fd218-p110">使用 "**保管人**" 选项卡可以在案例中添加和管理已确定为感兴趣的人员。在添加保管人时, 可以快速执行与保管人相关的操作, 例如, 对保管人数据源 (如邮箱和 OneDrive 帐户) 进行合法保留、与保管人进行通信以及搜索保管人数据源以收集内容这与案例相关。在这种情况下, 可以轻松地从案例中添加新的保管人或发布保管人。有关详细信息, 请参阅[高级电子数据展示中的使用保管人 (预览)](managing-custodians.md)。</span><span class="sxs-lookup"><span data-stu-id="fd218-p110">Use the **Custodians** tab to add and manage the people that you've identified as persons of interest in the case. When you add custodians, you can quickly perform custodian-related actions like placing a legal hold on custodian data sources, such as their mailbox and OneDrive account, communicating with custodians, and searching custodian data sources to collect content that's relevant to the case. As the case progresses, it's easy to add new custodians or release custodians from the case. For more information, see [Work with custodians in Advanced eDiscovery (Preview)](managing-custodians.md).</span></span>

## <a name="managing-legal-hold-notifications"></a><span data-ttu-id="fd218-137">管理法律保留通知</span><span class="sxs-lookup"><span data-stu-id="fd218-137">Managing legal hold notifications</span></span>

<span data-ttu-id="fd218-p111">在这种情况下, 使用 "**通信**" 选项卡来管理与保管人进行通信的过程。合法保留通知指示保管人保留可能与事例相关的任何内容。法律团队必须能够跟踪由保管人接收、阅读和确认的通知。如果保管人无法确认保留通知, 则高级电子数据展示 (预览) 中的通信工作流可用于创建和发送初始通知、提醒、发布通知和升级。有关详细信息, 请参阅[在高级电子数据展示中使用通信 (预览)](managing-custodian-communications.md)。</span><span class="sxs-lookup"><span data-stu-id="fd218-p111">Use the **Communications** tab to manage the process of communicating with the custodians in the case. A legal hold notice instructs custodians to preserve any content that may be relevant to the case. Legal teams must be able to track that notices have been received, read, and acknowledged by custodians. The communications workflow in Advanced eDiscovery (Preview) allows you create and send initial notifications, reminders, release notices, and escalations if custodians fail to acknowledge a hold notification. For more information, see [Work with communications in Advanced eDiscovery (Preview)](managing-custodian-communications.md).</span></span>

## <a name="managing-content-preservation"></a><span data-ttu-id="fd218-143">管理内容保留</span><span class="sxs-lookup"><span data-stu-id="fd218-143">Managing content preservation</span></span>

<span data-ttu-id="fd218-p112">向事例添加保管人时, 可以选择对 custodial 数据设置保留。使用**保留**选项卡可管理在添加保管人时创建的保留, 并管理与此案例相关的其他法律保留 (例如, 您可以在非 custodial 数据源上标识并放置保留项)。您还可以编辑该案例中的任何保留, 并将其设置为基于查询的保留, 以便在保留时仅放置与查询匹配的内容。例如, 可以将日期范围添加到保留, 以便保留在特定日期范围内创建的内容。您还可以获取处于保留状态的内容的统计信息, 删除不再与案例相关的保留, 或将其删除。有关详细信息, 请参阅[在高级电子数据展示中管理保留 (预览)](managing-holds.md)。</span><span class="sxs-lookup"><span data-stu-id="fd218-p112">When you add a custodian to a case, you have the option to place a hold on custodial data. Use the **Holds** tab to manage the hold created when you add custodians, and to manage additional legal holds associated with the case (for example, you can identify and place a hold on non-custodial data sources). You can also edit any hold in the case and make it a query-based hold so that only the content that matches the query is placed on hold. For example, you could add a date range to the hold so that only content created within a specific date ranged in preserved. You can also get statistics on content that's on hold, remove the hold after it's no longer relevant to the case, or delete it. For more information, see [Manage holds in Advanced eDiscovery (Preview)](managing-holds.md).</span></span>

## <a name="indexing-custodian-data"></a><span data-ttu-id="fd218-150">索引保管人数据</span><span class="sxs-lookup"><span data-stu-id="fd218-150">Indexing custodian data</span></span>

<span data-ttu-id="fd218-p113">向事例添加保管人和相应的 custodial 数据源时, 将对保管人数据源中的任何部分索引项重新编制索引 (由称为 "*高级索引*" 的过程)。这样, 在运行搜索以收集数据时, 可以完全搜索 custodial 内容 (如图像、不受支持的文件类型和其他可能未编制索引的内容)。使用 "**处理**" 选项卡监视高级索引的状态并修复处理错误 (使用称为 "*错误修正*" 的过程)。有关详细信息, 请参阅[修复高级电子数据展示中的处理错误 (预览)](processing-data-for-case.md)。</span><span class="sxs-lookup"><span data-stu-id="fd218-p113">When you add a custodian and the corresponding custodial data sources to a case, any partially indexed item from a custodian data source is re-indexed (by a process called *Advanced indexing*). This allows custodial content such as images, unsupported file types, and other potentially un-indexed content to be fully searchable when you run searches to collect data for the case. Use the **Processing** tab to monitor the status of Advanced indexing and fix processing errors (using a process called *error remediation*.) For more information, see [Fix processing errors in Advanced eDiscovery (Preview)](processing-data-for-case.md).</span></span>

## <a name="collecting-case-data"></a><span data-ttu-id="fd218-154">收集事例数据</span><span class="sxs-lookup"><span data-stu-id="fd218-154">Collecting case data</span></span>

<span data-ttu-id="fd218-p114">使用 "**搜索**" 选项卡来创建搜索以在 Office 365 中搜索就地 custodial 和非 custodial 数据源, 了解与案例相关的内容。您可以创建和运行基于查询的搜索 (使用关键字和条件), 以确定与案例相关的一组电子邮件和文档, 以及您希望在电子数据展示工作流中的后续步骤中进行进一步审阅和分析。您可以创建一个或多个与事例关联的搜索。此外, 还可以使用搜索工具预览示例文档, 并查看可帮助您优化和改进搜索结果的搜索统计信息。当您认为搜索结果包含与该事例相关的所有数据后, 您可以将搜索结果添加到工作集, 以供进一步查看、分析并在必要时剔除。有关详细信息, 请参阅[在高级电子数据展示中收集数据的事例 (预览)](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="fd218-p114">Use the **Searches** tab to create searches to search the in-place custodial and non-custodial data sources in Office 365 for content relevant to the case. You can create and run query-based searches (using keywords and conditions) to identify a set of email messages and documents that are relevant to the case and that you want to further review and analyze in subsequent steps in the eDiscovery workflow. You can create one or more searches associated with the case. Additionally, you can use the search tool to preview sample documents and view search statistics that may help you refine and improve the search results. Once you're satisfied that the search results contain the all data relevant to the case, you add the search results to a working set for further review, analysis and if necessary, culling. For more information, see [Collect data for a case in Advanced eDiscovery (Preview)](collecting-data-for-ediscovery.md).</span></span>

## <a name="reviewing-and-analyzing-case-data"></a><span data-ttu-id="fd218-161">查看和分析事例数据</span><span class="sxs-lookup"><span data-stu-id="fd218-161">Reviewing and analyzing case data</span></span>

<span data-ttu-id="fd218-p115">使用 "**工作集**" 选项卡可查看和分析从 live 系统中收集的内容并将其添加到工作集。*工作集*是您在电子数据展示工作流的前一阶段中收集的 custodial 数据 (以及数据的脱机副本) (如果适用, 非 custodial 数据) 的静态集合。将搜索结果添加到工作集时, 将触发一个进程, 该过程会从容器中提取文件、提取元数据并提取文本。完成此过程后, 系统将生成从保管人中收集的所有数据的新索引, 并将其添加到工作集。将数据添加到工作集后, 可以运行其他查询来缩小事例数据、以文本形式或以本机文件格式查看数据, 以及在工作集中对文档添加批注、标记密文和标记文档。此外, 还可以执行高级分析, 例如确定文档复制、电子邮件线程和主题。将数据 culled 到与事例相关的内容后, 可以直接下载文档, 也可以将它们连同文件元数据、批注和任何标记一起导出。有关详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="fd218-p115">Use the **Working sets** tab to review and analyze the content that you've collected from the live system and added to a working set. A *working set* is a static collection of that data (in other words, an offline copy of data) of custodial data (and if applicable, non-custodial data ) that you collected in the previous phase of the eDiscovery workflow. When you add search results to a working set, a process is triggered that extracts files from containers, extracts metadata, and extracts text. When this process is complete, the system builds a new index of all the data that was collected from custodians and added to the working set. After the data is added to the working set, you can run additional queries to narrow the case data, view data as text or in the native file format, and annotate, redact, and tag documents in the working set. Additionally, you can perform advanced analytics such as identify document duplication, email threading, and themes. After you've culled the data to only what is relevant to the case, you can either download documents directly or export them along with file metadata, annotations, and any tags. For more information, see:</span></span>

  - [<span data-ttu-id="fd218-170">查看高级电子数据展示中的案例数据 (预览)</span><span class="sxs-lookup"><span data-stu-id="fd218-170">Review case data in Advanced eDiscovery (Preview)</span></span>](reviewing-data-in-working-set.md)
  - [<span data-ttu-id="fd218-171">在高级电子数据展示中分析工作集中的数据 (预览)</span><span class="sxs-lookup"><span data-stu-id="fd218-171">Analyze data in a working set in Advanced eDiscovery (Preview)</span></span>](analyzing-data-in-working-set.md)

## <a name="exporting-data-for-review-and-presentation"></a><span data-ttu-id="fd218-172">导出数据以供审阅和演示</span><span class="sxs-lookup"><span data-stu-id="fd218-172">Exporting data for review and presentation</span></span>

<span data-ttu-id="fd218-p116">从工作集中导出数据后, 使用 "**导出**" 选项卡可管理导出作业并从工作集下载数据。导出工作集时, 会将数据上载到 Azure 存储位置, 然后可将其下载到本地计算机。您可以获取下载 "**导出**" 选项卡上的导出数据所需的位置和存储评估密钥。有关详细信息, 请参阅[在高级电子数据展示中导出事例数据 (预览)](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="fd218-p116">After you export the data from a working set, use the **Exports** tab to manage an export job and download data from a working set. When you export a working set, the data is uploaded to an Azure storage location and then is available to be downloaded to a local computer. You can obtain the location and storage assess key necessary to download the exported data on the **Exports** tab. For more information, see [Export case data in Advanced eDiscovery (Preview)](exporting-data-ediscover20.md).</span></span>

## <a name="managing-jobs"></a><span data-ttu-id="fd218-176">管理作业</span><span class="sxs-lookup"><span data-stu-id="fd218-176">Managing jobs</span></span>

<span data-ttu-id="fd218-p117">使用 "**作业**" 选项卡监视已启动的、与案例相关的任务的进程长时间运行。作业的示例包括与重新编制索引、搜索和导出相关的作业。例如, 可以在包含大量数据源的 "**搜索**" 选项卡上创建新的搜索。此搜索过程的状态将显示在 "**作业**" 选项卡上。有关详细信息, 请参阅[在高级电子数据展示中管理作业 (预览)](managing-jobs-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="fd218-p117">Use the **Jobs** tab to monitor long-running processes for case-related tasks that you've initiated. Example of jobs include those related to re-indexing, searches, and exports. For example, you might create a new search on the **Searches** tab that includes a large number of data sources. The status of this search process is displayed on the **Jobs** tab. For more information, see [Manage jobs in Advanced eDiscovery (Preview)](managing-jobs-ediscovery20.md).</span></span>

## <a name="configuring-case-settings"></a><span data-ttu-id="fd218-181">配置事例设置</span><span class="sxs-lookup"><span data-stu-id="fd218-181">Configuring case settings</span></span>

<span data-ttu-id="fd218-p118">使用 "**设置**" 选项卡配置大小写设置。这包括向事例添加成员、关闭或删除事例以及配置搜索和分析行为。有关详细信息, 请参阅[在高级电子数据展示中配置事例设置 (预览)](configuring-case-settings-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="fd218-p118">Use the **Settings** tab to configure case-wide settings. This includes adding members to a case, closing or deleting a case, and configuring search and analytics behavior. For more information, see [Configure case settings in Advanced eDiscovery (Preview)](configuring-case-settings-ediscovery20.md).</span></span>

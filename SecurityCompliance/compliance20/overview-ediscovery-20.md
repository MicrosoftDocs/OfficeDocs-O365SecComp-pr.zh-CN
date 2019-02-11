---
title: 高级电子数据展示 （预览） Microsoft 365 中的概述
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
description: 本文介绍了高级电子数据展示 （预览） Microsoft 365 中的新版本。
ms.openlocfilehash: cb82541037983ca21cefbefb7f72fffa3b054373
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706153"
---
# <a name="overview-of-advanced-ediscovery-preview-in-microsoft-365"></a><span data-ttu-id="c0cc1-103">高级电子数据展示 （预览） Microsoft 365 中的概述</span><span class="sxs-lookup"><span data-stu-id="c0cc1-103">Overview of Advanced eDiscovery (Preview) in Microsoft 365</span></span>

<span data-ttu-id="c0cc1-p101">Microsoft 只是已发布预览版本是基于 Office 365 中现有的电子数据展示功能构建的更新高级电子数据展示工具。调用*高级电子数据展示 （预览）*，此预览版本提供的端到端工作流保留、 收集、 查看、 分析和导出内容的响应贵组织的内部和外部调查。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p101">Microsoft has just released a preview version of the updated Advanced eDiscovery tool that builds on the existing eDiscovery capabilities in Office 365. This preview version, called *Advanced eDiscovery (Preview)*, provides an end-to-end workflow to preserve, collect, review, analyze, and export content that's responsive to your organization's internal and external investigations.</span></span> 

## <a name="alignment-with-edrm"></a><span data-ttu-id="c0cc1-106">与 EDRM 的对齐方式</span><span class="sxs-lookup"><span data-stu-id="c0cc1-106">Alignment with EDRM</span></span>

<span data-ttu-id="c0cc1-107">高级电子数据展示 （预览） 的内置工作流与列出由电子发现参考模型 (EDRM) 的电子数据展示过程对齐。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-107">The built-in workflow of Advanced eDiscovery (Preview) aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span> 

![电子发现参考模型 (EDRM)](../media/EDRMv1.png)

<span data-ttu-id="c0cc1-p102">（由 edrm.net 图像源。源图像进行创作 Commons 归属 3.0 Unported 许可证下可用。）</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p102">(Image source courtesy of edrm.net. The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="c0cc1-111">在高级别，下面是如何高级电子数据展示 （预览） 支持 EDRM 工作流：</span><span class="sxs-lookup"><span data-stu-id="c0cc1-111">At a high level, here's how Advanced eDiscovery (Preview) supports the EDRM workflow:</span></span>

- <span data-ttu-id="c0cc1-p103">**标识**-后识别潜在的调查感兴趣的人员，您可以将其添加为管理员 （也称为，*数据管理员*，因为他们可能拥有与调查相关的信息） 到高级电子数据展示 （预览） 大写。作为管理员添加用户后，很容易地保留、 收集和查看 custodian 文档。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p103">**Identification** - After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to a Advanced eDiscovery (Preview) case. After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="c0cc1-p104">**保留**的保留和保护与调查相关的数据高级种情况下管理员与关联的数据源上发出的电子数据展示 （预览） 允许合法保留。您还可以将非监控数据置于保持状态。此外，高级电子数据展示 （预览） 具有内置 communications 工作流，因此您可以向管理员发送合法保留通知和跟踪其确认。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p104">**Preservation** - To preserve and protect data that's relevant to an investigation, Advanced eDiscovery (Preview) lets you place a legal hold on the data sources that are associated with the custodians in a case. You can also place non-custodial data on hold. Additionally, Advanced eDiscovery (Preview) has a built-in communications workflow so you can send a legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="c0cc1-117">**集合**的标识 （并保留） 与调查相关的数据源后，您可以使用高级电子数据展示 （预览） 搜索和收集实时数据中的内置搜索工具从监控数据源 （和非监控数据源，如果适用） 的可能与案例相关。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-117">**Collection** - After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery (Preview) search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="c0cc1-p105">**处理**-已收集与案例相关的所有数据后下, 一步是对其进行处理进一步评审和分析。在高级电子数据展示 （预览），这意味着在收集阶段中识别的就地数据复制到 Azure 存储位置 （称为*工作集*），它为您提供的静态视图的案例数据。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p105">**Processing** - After you've collected all data relevant to the case, the next step is process it for further review and analysis. In Advanced eDiscovery (Preview), this means the in-place data that you identified in the collection phase is copied to Azure storage location (called a *working set*), which provides you with a static view of the case data.</span></span> 
 
- <span data-ttu-id="c0cc1-120">**查看**— 后数据已添加到工作集，您可以查看特定文档并运行其他查询到</span><span class="sxs-lookup"><span data-stu-id="c0cc1-120">**Review** - After data has been added to a working set, you can view specific documents and run additional queries to</span></span>  
 
- <span data-ttu-id="c0cc1-p106">**分析**-高级电子数据展示 （预览） 提供了集成的分析工具，可帮助您挑选数据从您确定工作集不与调查相关。除了减少相关的数据量，高级电子数据展示 （预览） 还有助于您通过让您组织内容以使审阅过程更容易、 更高效保存法律审阅成本。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p106">**Analysis** - Advanced eDiscovery (Preview) provides integrated analytics tools that helps you cull data from the working set that you determine isn't relevant to the investigation. In addition to reducing the volume of relevant data, Advance eDiscovery (Preview) also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="c0cc1-p107">**生产**和**演示文稿**的准备就绪后，您可以从法律审阅工作集导出文档。您可以导出以本机格式或格式 EDRM 指定文档，以便他们可以导入到第三方查看应用程序。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p107">**Production** and **Presentation** - When you're ready, you can export documents from a working set for legal review. You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="advanced-ediscovery-preview-workflow"></a><span data-ttu-id="c0cc1-125">高级电子数据展示 （预览） 工作流</span><span class="sxs-lookup"><span data-stu-id="c0cc1-125">Advanced eDiscovery (Preview) workflow</span></span>

<span data-ttu-id="c0cc1-p108">以下各节介绍了高级电子数据展示 (Preview) 中的内置工作流中的每个步骤。下面的屏幕快照显示了名为*产品责任 2019002*种情况下的**主页**选项卡。请注意工作流选项卡在页面顶部的排序与 EDRM 过程对齐。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p108">The following sections describe each step in the built-in workflow in Advanced eDiscovery (Preview). The following screenshot shows the **Home** tab of a case named *Product Liability 2019002*. Note the workflow tabs at the top of the page are sequenced to align with the EDRM process.</span></span> 

<span data-ttu-id="c0cc1-129">有关高级电子数据展示 (Preview) 中的端到端工作流的详细信息，请参阅此[视频的 Microsoft 机制](https://go.microsoft.com/fwlink/?linkid=2066133)。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-129">For more information about the end-to-end workflow in Advanced eDiscovery (Preview), see this [Microsoft Mechanics video](https://go.microsoft.com/fwlink/?linkid=2066133).</span></span> 

![高级电子数据展示 (Preview) 中的选项卡遵循 EDRM 工作流](../media/aedisco-homepage-1.png)

## <a name="managing-custodians"></a><span data-ttu-id="c0cc1-131">管理保管人</span><span class="sxs-lookup"><span data-stu-id="c0cc1-131">Managing custodians</span></span>

<span data-ttu-id="c0cc1-p109">使用**管理员**选项卡可以添加和管理已识别为情况值得关注的人员的人员。添加管理员后，可以快速执行 custodian 相关操作如 custodian 数据源上发出法律操作，如其邮箱和 OneDrive 帐户与管理员，通信和搜索 custodian 数据源收集内容这是与案例相关。作为案例的进度，则很容易添加新的管理员或发行版从用例的管理员。有关详细信息，请参阅[使用高级电子数据展示 (Preview) 中的管理员](managing-custodians.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p109">Use the **Custodians** tab to add and manage the people that you've identified as persons of interest in the case. When you add custodians, you can quickly perform custodian-related actions such as placing a legal how on custodian data sources, such as their mailbox and OneDrive account, communicating with custodians, and searching custodian data sources to collect content that's relevant to the case. As as the case progress, it's easy to add new custodians or release custodians from the case. For more information, see [Work with custodians in Advanced eDiscovery (Preview)](managing-custodians.md).</span></span>

## <a name="managing-legal-hold-notifications"></a><span data-ttu-id="c0cc1-136">管理法律保留项通知</span><span class="sxs-lookup"><span data-stu-id="c0cc1-136">Managing legal hold notifications</span></span>

<span data-ttu-id="c0cc1-p110">**Communications**选项卡用于管理与情况管理员的过程。合法保留通知指示要保留任何可能与案例相关的内容的管理员。法律团队必须能够跟踪的通知具有已收到、 读取，并确认的管理员。高级电子数据展示 (Preview) 中的 communications 工作流允许您创建和发送初始通知、 提醒、 版本通知和升级，如果管理员未确认保留通知。有关详细信息，请参阅[使用高级电子数据展示 (Preview) 中的通信](managing-custodian-communications.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p110">Use the **Communications** tab to manage the process of communicating with the custodians in the case. A legal hold notice instructs custodians to preserve any content that may be relevant to the case. Legal teams must be able to track that notices have been received, read, and acknowledged by custodians. The communications workflow in Advanced eDiscovery (Preview) allows you create and send initial notifications, reminders, release notices, and escalations if custodians fail to acknowledge a hold notification. For more information, see [Work with communications in Advanced eDiscovery (Preview)](managing-custodian-communications.md).</span></span>

## <a name="managing-content-preservation"></a><span data-ttu-id="c0cc1-142">管理内容的保留</span><span class="sxs-lookup"><span data-stu-id="c0cc1-142">Managing content preservation</span></span>

<span data-ttu-id="c0cc1-p111">当您添加到案例的管理员时，您可以选择保留置于监控数据。使用**保存**选项卡来管理创建时添加管理员和管理其他法律保留项包含与大小写; 关联例如，可以标识和保留置于非监控数据源。此外可以编辑情况任何保留，然后将其基于查询的保留以便仅与查询匹配的内容将置于保持状态;例如，您无法添加日期范围到保留项，以便在特定日期范围中创建的唯一内容保留。您可以获取有关保留的内容的统计信息，删除之后无法再与这种情况，相关时将其保留或删除它。有关详细信息，请参阅[管理保留高级电子数据展示 (Preview) 中](managing-holds.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p111">When you add a custodian to a case, you have the option to place a hold on custodial data. Use the **Holds** tab to manage the hold created when you add custodians and manage additional legal holds associated with the case; for example, you can identify and place a hold on non-custodial data sources. You can also edit any hold in the case and make it a query-based hold so that only the content that matches the query is placed on hold; for example, you could add a date range to the hold so that only content that was created within a specific date ranged in preserved. You can also get statistics on content that's on hold, remove the hold after when it's no longer relevant to the case, or delete it. For more information, see [Manage holds in Advanced eDiscovery (Preview)](managing-holds.md).</span></span>

## <a name="indexing-custodian-data"></a><span data-ttu-id="c0cc1-148">索引 custodian 数据</span><span class="sxs-lookup"><span data-stu-id="c0cc1-148">Indexing custodian data</span></span>

<span data-ttu-id="c0cc1-p112">当您添加到案例的管理员和相应的监控数据源时，（由调用*高级索引*进程） 重新编制索引 custodian 数据源的任何部分索引的项。这使监控的内容，如图像、 受支持的文件类型和其他可能不编入索引的内容运行搜索以收集与案例相关的数据时可完全搜索。使用**处理**选项卡来监视高级索引和修复处理错误 （使用过程杨柳*错误修正*。） 的状态有关详细信息，请参阅[修复高级电子数据展示 (Preview) 中的处理错误](processing-data-for-case.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p112">When you add a custodian and the corresponding custodial data sources to a case, any partially indexed item from a custodian data source is re-indexed (by a process called *Advanced indexing*). This allow custodial content such as images, unsupported file types, and other potentially un-indexed content to be fully searchable when you run searches to collect data that's relevant to the case. Use the **Processing** tab to monitor the status of Advanced indexing and fix processing errors (using a process calle *error remediation*.) For more information, see [Fix processing errors in Advanced eDiscovery (Preview)](processing-data-for-case.md).</span></span>

## <a name="collecting-case-data"></a><span data-ttu-id="c0cc1-152">收集事例数据</span><span class="sxs-lookup"><span data-stu-id="c0cc1-152">Collecting case data</span></span>

<span data-ttu-id="c0cc1-p113">使用**搜索**选项卡的与案例相关的内容在 Office 365 中创建搜索以搜索就地监控和非监控数据源。您可以创建和运行基于查询的搜索 （使用关键字和条件） 来标识设置电子邮件和文档相关的大小写和您想要进一步查看和分析电子数据展示工作流中的后续步骤中。您可以创建与案例相关联的一个或多个搜索。此外，您可以使用搜索工具预览的示例文档和查看搜索统计信息可能有助于优化改进搜索结果。您一次搜索结果中包含的所有数据与案例相关、 搜索结果添加到进一步校对，分析工作集正在达到满意且有必要，挑选。有关详细信息，请参阅[收集高级电子数据展示 (Preview) 中用例的数据](collecting-data-for-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p113">Use the **Searches** tab to create searches to search the in-place custodial and non-custodial data sources in Office 365 for content that is relevant to the case. You can create and run query-based searches (using keywords and conditions) to identify a set email messages and documents that are relevant to the case and the  you want to further review and analyze in subsequent steps in the eDiscovery workflow. You can create one or more searches associated with the case. Additionally, you can use the search tool to preview sample documents and view search statistics that may help refine and improve the search results. Once you're satisfied that the search results contain the all the data relevant to the case, you add the search results to a working set for further review, analysis and if necessary, culling. For more information, see [Collect data for a case in Advanced eDiscovery (Preview)](collecting-data-for-ediscovery.md).</span></span>

## <a name="reviewing-and-analyzing-case-data"></a><span data-ttu-id="c0cc1-159">查看和分析案例数据</span><span class="sxs-lookup"><span data-stu-id="c0cc1-159">Reviewing and analyzing case data</span></span>

<span data-ttu-id="c0cc1-p114">使用**处理设置**选项卡或查看和分析您已从 live 系统收集并添加到工作集的内容。*工作集*是静态集合 （换句话说，揭示数据的脱机副本） 的监控数据 (如果适用的话，非监控数据) 的电子数据展示工作流的早期阶段收集。当您将搜索结果添加到工作集时，将触发进程从容器中提取文件，提取元数据，并提取文本。完成此过程时，系统将生成新的索引从管理员收集并将其添加到工作集的所有数据。一旦数据添加到工作集，您可以运行其他查询来缩小范围案例数据作为文本或本机文件格式查看数据和批注、 标记密文，并在工作中的标记文档设置。此外，您可以执行高级分析功能，如标识文档重复、 电子邮件超线程，和主题。一旦您已选出仅所与案例相关的数据，您可以直接下载下载文档，或将其导出以及文件元数据、 批注和任何标记。有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p114">Use the **Working sets** tab or review and analyze the content that you've collected from the live system and added to a working set. A *working set* is a static collection (in other words, an offline copy of dat) of custodial data (and if applicable, non-custodial data ) that you collected in the previous phase of the eDiscovery workflow. When you add search results to a working set, a process is triggered that extracts files from containers, extracts metadata, and extracts text. When this process is complete, the system builds a new index of all the data collected from custodians and added to the working set. Once the data is added to the working set, you can run additional queries to narrow the case data, view data as text or in the native file format, and annotate, redact, and tag documents in the working set. Additionally, you can perform advanced analytics such as identify document duplication, email threading, and themes. Once you've culled the data to only what is relevant to the case, you can either download download documents directly or export them along with file metadata, annotations, and any tags. For more information, see:</span></span>

  - [<span data-ttu-id="c0cc1-168">查看高级电子数据展示 (Preview) 中的案例数据</span><span class="sxs-lookup"><span data-stu-id="c0cc1-168">Review case data in Advanced eDiscovery (Preview)</span></span>](reviewing-data-in-working-set.md)
  - [<span data-ttu-id="c0cc1-169">分析高级电子数据展示 (Preview) 中的工作集数据</span><span class="sxs-lookup"><span data-stu-id="c0cc1-169">Analyze data in a working set in Advanced eDiscovery (Preview)</span></span>](analyzing-data-in-working-set.md)

## <a name="exporting-data-for-review-and-presentation"></a><span data-ttu-id="c0cc1-170">导出数据的查看和演示文稿</span><span class="sxs-lookup"><span data-stu-id="c0cc1-170">Exporting data for review and presentation</span></span>

<span data-ttu-id="c0cc1-p115">将数据导出从工作集后，使用**导出**选项卡管理导出作业和从工作集下载数据。导出工作集时，将数据上载到 Azure 的存储位置，然后可用于下载到本地计算机。您可以获取位置，并存储评估下载**导出**选项卡上的导出的数据所需的密钥。有关详细信息，请参阅[导出案例高级电子数据展示 (Preview) 中的数据](exporting-data-ediscover20.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p115">After you export the data from a working set, use the **Exports** tab to manage an export job and download data from a working set. When you export a working set, the data is uploaded to an Azure storage location and then is available to be downloaded to a local computer. You can obtain the location and storage assess key necessary to download the exported data on the **Exports** tab. For more information, see [Export case data in Advanced eDiscovery (Preview)](exporting-data-ediscover20.md).</span></span>

## <a name="managing-jobs"></a><span data-ttu-id="c0cc1-174">管理作业</span><span class="sxs-lookup"><span data-stu-id="c0cc1-174">Managing jobs</span></span>

<span data-ttu-id="c0cc1-p116">使用**作业**选项卡来监视长时间运行过程已启动的与案例相关的任务、 为重新编制索引的搜索、 搜索和导出。例如，您可能包括大量数据源的**搜索**选项卡上创建一个新的搜索。在**作业**选项卡上显示此搜索过程的状态。有关详细信息，请参阅[高级电子数据展示 (Preview) 中的管理作业](managing-jobs-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p116">Use the **Jobs** tab to monitor long-running processes for case-related tasks that you've initiated, searches as re-indexing, searches, and exports. For example, you might create a new search on the **Searches** tab that includes a large number of data sources. The status of this search process is displayed on the **Jobs** tab. For more information, see [Manage jobs in Advanced eDiscovery (Preview)](managing-jobs-ediscovery20.md).</span></span>

## <a name="configuring-case-settings"></a><span data-ttu-id="c0cc1-178">配置事例设置</span><span class="sxs-lookup"><span data-stu-id="c0cc1-178">Configuring case settings</span></span>

<span data-ttu-id="c0cc1-p117">使用**设置**选项卡的配置案例范围的设置。这包括将成员添加到的情况下，关闭或删除种情况下，并配置搜索和分析的行为。有关详细信息，请参阅[配置高级电子数据展示 (Preview) 中的区分大小设置](configuring-case-settings-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cc1-p117">Use the **Settings** tab for configure case-wide settings. This includes adding members to a case, closing or deleting a case, and configuring search and analytics behavior. For more information, see [Configure case settings in Advanced eDiscovery (Preview)](configuring-case-settings-ediscovery20.md).</span></span>


---
title: 提高导出 Office 365 中的电子数据展示搜索结果时的下载速度
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: 了解如何配置 Windows 注册表, 以便在从 Office 365 安全&amp;合规性中心和 office 365 高级电子数据展示中下载搜索结果和搜索数据时增加数据吞吐量。
ms.openlocfilehash: a23525ada1ef5f36bc7df4fc738c712e22243bc0
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295425"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a><span data-ttu-id="4c547-103">提高导出 Office 365 中的电子数据展示搜索结果时的下载速度</span><span class="sxs-lookup"><span data-stu-id="4c547-103">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>

<span data-ttu-id="4c547-p101">当您使用 office 365 电子数据展示导出工具在 office 365 安全&amp;合规中心中下载内容搜索的结果或从 office 365 高级电子数据展示下载数据时, 该工具将启动一定数量的并发导出将数据下载到本地计算机的操作。默认情况下, 并发操作数设置为要用于下载数据的计算机中的核心数的8倍。例如, 如果您有一台双核计算机 (即一个芯片上有两个中央处理单元), 则并发导出操作的默认数量为16个。若要增加数据传输吞吐量并加快下载过程, 可以通过在用于下载搜索结果的计算机上配置 Windows 注册表设置来增加并发操作的数量。若要加快下载过程, 建议您首先设置24个并发操作。</span><span class="sxs-lookup"><span data-stu-id="4c547-p101">When you use the Office 365 eDiscovery Export tool to download the results of a Content Search in the Office 365 Security &amp; Compliance Center or download data from Office 365 Advanced eDiscovery, the tool starts a certain number of concurrent export operations to download the data to your local computer. By default, the number of concurrent operations is set to 8 times the number of cores in the computer you're using to download the data. For example, if you have a dual core computer (meaning two central processing units on one chip), the default number of concurrent export operations is 16. To increase the data transfer throughput and speed-up the download process, you can increase the number of concurrent operations by configuring a Windows Registry setting on the computer that you use to download the search results. To speed-up the download process, we recommend that you start with a setting of 24 concurrent operations.</span></span>
  
<span data-ttu-id="4c547-p102">如果通过低带宽网络下载搜索结果, 则增加此设置可能会产生负面影响。或者, 可以将设置增加到高带宽网络 (最大并发操作数为 512) 中的24个并发操作。配置此注册表设置后, 您可能需要将其更改为为您的环境找到最佳的并发操作数。</span><span class="sxs-lookup"><span data-stu-id="4c547-p102">If you download search results over a low-bandwidth network, increasing this setting might have a negative impact. Alternatively, you might be able to increase the setting to more than 24 concurrent operations in a high-bandwidth network (the maximum number of concurrent operations is 512). After you configure this registry setting, you might have to change it to find the optimal number of concurrent operations for your environment.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a><span data-ttu-id="4c547-112">创建注册表设置以更改导出数据时的并发操作的数量</span><span class="sxs-lookup"><span data-stu-id="4c547-112">Create a registry setting to change the number of concurrent operations when exporting data</span></span>

<span data-ttu-id="4c547-113">在您将用于从安全&amp;合规中心或高级电子数据展示中的数据下载搜索结果的计算机上执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="4c547-113">Perform the following procedure on the computer that you'll use to download search results from the Security &amp; Compliance Center or data from Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="4c547-114">如果 Office 365 电子数据展示导出工具处于打开状态, 则将其关闭。</span><span class="sxs-lookup"><span data-stu-id="4c547-114">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="4c547-115">使用文件名后缀 .reg 将以下文本保存到窗口注册表文件;例如, ConcurrentOperations。</span><span class="sxs-lookup"><span data-stu-id="4c547-115">Save the following text to a Window registry file by using a filename suffix of .reg; for example, ConcurrentOperations.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    <span data-ttu-id="4c547-116">如前所述, 我们建议您从24个并发操作开始, 然后根据需要更改此设置。</span><span class="sxs-lookup"><span data-stu-id="4c547-116">As previous explained, we recommend that you start with 24 concurrent operations, and then change this setting as appropriate.</span></span>
    
3. <span data-ttu-id="4c547-117">在 Windows 资源管理器中, 单击或双击您在上一步中创建的 .reg 文件。</span><span class="sxs-lookup"><span data-stu-id="4c547-117">In Windows Explorer, click or double-click the .reg file that you created in the previous step.</span></span>
    
4. <span data-ttu-id="4c547-118">在 "用户访问控制" 窗口中, 单击 **"是"** 以让注册表编辑器进行更改。</span><span class="sxs-lookup"><span data-stu-id="4c547-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="4c547-119">当系统提示您继续时, 请单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="4c547-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="4c547-120">注册表编辑器将显示一条消息, 指出已成功将设置添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="4c547-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
6. <span data-ttu-id="4c547-121">您可以重复步骤 2-5 以更改`DownloadConcurrency`注册表设置的值。</span><span class="sxs-lookup"><span data-stu-id="4c547-121">You can repeat steps 2 - 5 to change the value for the  `DownloadConcurrency` registry setting.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="4c547-p103">在创建或更改`DownloadConcurrency`注册表设置后, 请确保为要下载的搜索结果或数据重新创建一个新的导出作业或重新启动现有的导出作业。有关更多详细信息, 请参阅[详细信息](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="4c547-p103">After you create or change the  `DownloadConcurrency` registry setting, be sure to create a new export job or restart an existing export job for the search results or data that you want to download. See the [More information](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo) section for more details.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="4c547-124">更多信息</span><span class="sxs-lookup"><span data-stu-id="4c547-124">More information</span></span>

- <span data-ttu-id="4c547-p104">首次运行您在此过程中创建的 .reg 文件时, 会创建一个新的注册表项。然后, `DownloadConcurrency`每次更改并重新运行 .reg 编辑文件时, 都会编辑注册表设置。</span><span class="sxs-lookup"><span data-stu-id="4c547-p104">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the  `DownloadConcurrency` registry setting is edited each time you change and re-run the .reg edit file.</span></span> 
    
- <span data-ttu-id="4c547-p105">Office 365 电子数据展示导出工具使用[Azure AzCopy 实用工具](https://go.microsoft.com/fwlink/?linkid=849949)从安全&amp;合规性中心或从高级电子数据展示下载搜索数据。配置`DownloadConcurrency`注册表设置类似于在运行 AzCopy 实用工具时使用 **/NC**参数。因此, 的`"DownloadConcurrency=24"`注册表设置与使用 AzCopy 实用程序的参数值`/NC:24`具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="4c547-p105">The Office 365 eDiscovery Export tool uses the [Azure AzCopy utility](https://go.microsoft.com/fwlink/?linkid=849949) to download search data from the Security &amp; Compliance Center or from Advanced eDiscovery. Configuring the  `DownloadConcurrency` registry setting is similar to using the **/NC** parameter when running the AzCopy utility. So the registry setting of  `"DownloadConcurrency=24"` would have the same effect as using the parameter value of  `/NC:24` with the AzCopy utility.</span></span> 
    
- <span data-ttu-id="4c547-p106">如果您停止当前正在进行的导出下载, 然后重新启动它 (通过再次尝试下载搜索结果), Office 365 电子数据展示导出工具将尝试恢复相同的下载。因此, 如果你开始下载, 请先停止它, 然后更改`DownloadConcurrency`注册表设置, 如果重新启动它 (单击 "**下载导出结果**"), 下载可能会失败。这是因为导出工具将尝试使用无效的设置来恢复以前的下载, 因为您更改了注册表设置。</span><span class="sxs-lookup"><span data-stu-id="4c547-p106">If you stop an export download that's currently in progress and then restart it (by trying to download the search results again), the Office 365 eDiscovery Export tool will attempt to resume the same download. So, if you start a download, stop it, and then change the  `DownloadConcurrency` registry setting, the download will probably fail if you restart it (by clicking **Download exported results**). This is because the export tool will attempt to resume the previous download using settings that aren't valid because you changed the registry setting.</span></span>
    
    <span data-ttu-id="4c547-p107">因此, 在更改`DownloadConcurrency`注册表设置后, 请务必在安全&amp;合规中心中重新启动导出作业 (通过单击 "**重新启动导出**")。然后, 您可以下载导出的结果。有关导出搜索结果和数据的详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="4c547-p107">Therefore, after you change the  `DownloadConcurrency` registry setting, be sure to restart the export job (by clicking **Restart export**) in the Security &amp; Compliance Center. Then you can download the exported results. For more information about exporting search results and data, see:</span></span>
    
  - [<span data-ttu-id="4c547-136">从 Office 365 安全&amp;合规中心导出内容搜索结果</span><span class="sxs-lookup"><span data-stu-id="4c547-136">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
  - [<span data-ttu-id="4c547-137">导出 Office 365 高级电子数据展示中的结果</span><span class="sxs-lookup"><span data-stu-id="4c547-137">Export results in Office 365 Advanced eDiscovery</span></span>](export-results-in-advanced-ediscovery.md)
    

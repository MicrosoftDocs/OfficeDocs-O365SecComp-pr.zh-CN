---
title: 导出电子数据展示搜索结果时更改 PST 文件的大小
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 您可以在导出电子数据展示搜索结果时更改下载到您的计算机上的 PST 文件的默认大小。
ms.openlocfilehash: 98b543b6e34cb9cb075a765671def91742aee6c1
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243607"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="d9b2d-103">导出电子数据展示搜索结果时更改 PST 文件的大小</span><span class="sxs-lookup"><span data-stu-id="d9b2d-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="d9b2d-104">使用 Office 365 电子数据展示导出工具从不同的 Microsoft 电子数据展示工具导出电子数据展示搜索的电子邮件结果时, 可以导出的 PST 文件的默认大小为 10 GB。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-104">When you use the Office 365 eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB.</span></span> <span data-ttu-id="d9b2d-105">如果要更改此默认大小, 可以在用于导出搜索结果的计算机上编辑 Windows 注册表。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-105">If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="d9b2d-106">执行此操作的一个原因是, PST 文件可以放置在可移动媒体 (如 DVD、光盘或 USB 驱动器) 上。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-106">One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="d9b2d-107">Office 365 电子数据展示导出工具用于在安全与合规中心中使用内容搜索工具、Exchange online 中的就地电子数据展示和 SharePoint online 中的电子数据展示中心来导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-107">The Office 365 eDiscovery Export tool is used to export the search results when using the Content Search tool in the security and compliance center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span>
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="d9b2d-108">创建注册表设置以在导出电子数据展示搜索结果时更改 PST 文件的大小</span><span class="sxs-lookup"><span data-stu-id="d9b2d-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="d9b2d-109">在用于导出电子数据展示搜索结果的计算机上执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="d9b2d-110">如果 Office 365 电子数据展示导出工具处于打开状态, 则将其关闭。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-110">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="d9b2d-111">使用文件名后缀 .reg 将以下文本保存到窗口注册表文件;例如, PstExportSize。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="d9b2d-112">在上面的示例中, `PstSizeLimitInBytes`值设置为1073741824个字节或约 1 GB。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-112">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB.</span></span> <span data-ttu-id="d9b2d-113">下面是`PstSizeLimitInBytes`设置的一些其他示例值。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-113">Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="d9b2d-114">**大小 (以 GB 为单位) (近似)**</span><span class="sxs-lookup"><span data-stu-id="d9b2d-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="d9b2d-115">**以字节为单位的大小**</span><span class="sxs-lookup"><span data-stu-id="d9b2d-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d9b2d-116">7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="d9b2d-116">.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="d9b2d-117">751619277</span><span class="sxs-lookup"><span data-stu-id="d9b2d-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="d9b2d-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="d9b2d-118">2 GB</span></span>  <br/> |<span data-ttu-id="d9b2d-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="d9b2d-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="d9b2d-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="d9b2d-120">4 GB</span></span>  <br/> |<span data-ttu-id="d9b2d-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="d9b2d-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="d9b2d-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="d9b2d-122">8 GB</span></span>  <br/> |<span data-ttu-id="d9b2d-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="d9b2d-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="d9b2d-124">在导出`PstSizeLimitInBytes`搜索结果时, 将值更改为所需的最大 PST 文件大小, 然后保存该文件。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="d9b2d-125">在 Windows 资源管理器中, 单击或双击您在前面步骤中创建的 .reg 文件。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="d9b2d-126">在 "用户访问控制" 窗口中, 单击 **"是"** 以让注册表编辑器进行更改。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="d9b2d-127">当系统提示您继续时, 请单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="d9b2d-128">注册表编辑器将显示一条消息, 指出已成功将设置添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="d9b2d-129">您可以重复步骤 3-6 以更改`PstSizeLimitInBytes`注册表设置的值。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="d9b2d-130">在导出电子数据展示搜索结果时, 有关更改 PST 文件默认大小的常见问题</span><span class="sxs-lookup"><span data-stu-id="d9b2d-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="d9b2d-131">**为什么默认大小为 10 GB？**</span><span class="sxs-lookup"><span data-stu-id="d9b2d-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="d9b2d-132">10 GB 的默认大小是基于客户反馈;10 GB 是一种很好的平衡单个 PST 中的内容量, 并具有最小的文件损坏可能性。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="d9b2d-133">**是否应增加或减小 PST 文件的默认大小？**</span><span class="sxs-lookup"><span data-stu-id="d9b2d-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="d9b2d-134">客户倾向于减小大小限制, 以便搜索结果能够在可在其组织中物理传送其他位置的可移动媒体上进行调整。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-134">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship other locations in their organization.</span></span> <span data-ttu-id="d9b2d-135">我们建议您不要增加默认大小, 因为 PST 文件大于 10 GB 可能存在损坏问题。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-135">We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="d9b2d-136">**我必须在哪台计算机上执行此操作？**</span><span class="sxs-lookup"><span data-stu-id="d9b2d-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="d9b2d-137">您需要更改在其上运行 Office 365 电子数据展示导出工具的任何本地计算机上的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-137">You need to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="d9b2d-138">**更改此设置后, 必须重新启动计算机吗？**</span><span class="sxs-lookup"><span data-stu-id="d9b2d-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="d9b2d-139">否, 无需重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-139">No, you don't have to reboot the computer.</span></span> <span data-ttu-id="d9b2d-140">但是, 如果 Office 365 电子数据展示导出工具正在运行, 则必须将其关闭, 并在更改此设置后重新启动它。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-140">But, if the Office 365 eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="d9b2d-141">**是否已编辑现有注册表项或是否创建新的密钥？**</span><span class="sxs-lookup"><span data-stu-id="d9b2d-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="d9b2d-142">首次运行您在此过程中创建的 .reg 文件时, 会创建一个新的注册表项。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-142">A new registry key is created the first time you run the .reg file that you created in this procedure.</span></span> <span data-ttu-id="d9b2d-143">然后, 在每次更改并重新运行 .reg 编辑文件时, 都会编辑该设置。</span><span class="sxs-lookup"><span data-stu-id="d9b2d-143">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>

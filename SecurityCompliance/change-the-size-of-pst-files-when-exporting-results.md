---
title: 导出电子数据展示搜索结果时更改 PST 文件的大小
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 您可以更改的下载到您的计算机来导出电子数据展示搜索结果时的 PST 文件的默认大小。
ms.openlocfilehash: d38189c437154dbe27a084230d4d3fd4de418ece
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524870"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a><span data-ttu-id="4e8d1-103">导出电子数据展示搜索结果时更改 PST 文件的大小</span><span class="sxs-lookup"><span data-stu-id="4e8d1-103">Change the size of PST files when exporting eDiscovery search results</span></span>

<span data-ttu-id="4e8d1-p101">如果您使用 Office 365 电子数据展示导出工具从不同的 Microsoft 电子数据展示工具导出电子数据展示搜索的电子邮件结果，可以导出的 PST 文件的默认大小是 10 GB。如果您想要更改此默认大小，您可以编辑用于导出搜索结果的计算机上的 Windows 注册表。若要执行此操作的一个原因是以便 PST 文件可容纳的可移动介质、 此类 DVD、 光盘或 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-p101">When you use the Office 365 eDiscovery Export tool to export the email results of an eDiscovery search from the different Microsoft eDiscovery tools, the default size of a PST file that can be exported is 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. One reason to do this is so a PST file can fit on removable media, such a DVD, a compact disc, or a USB drive.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="4e8d1-107">Office 365 电子数据展示导出工具用于在 Office 365 安全性使用内容搜索时导出搜索结果&amp;合规性中心、 Exchange Online 中的就地电子数据展示和 SharePoint Online 中的电子数据展示中心。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-107">The Office 365 eDiscovery Export tool is used to export the search results when using Content Search in the Office 365 Security &amp; Compliance Center, In-Place eDiscovery in Exchange Online, and the eDiscovery Center in SharePoint Online.</span></span> 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="4e8d1-108">创建一个注册表设置来导出电子数据展示搜索结果时更改的 PST 文件大小</span><span class="sxs-lookup"><span data-stu-id="4e8d1-108">Create a registry setting to change the size of PST files when you export eDiscovery search results</span></span>

<span data-ttu-id="4e8d1-109">您将使用导出的电子数据展示搜索结果的计算机上执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-109">Perform the following procedure on the computer that you'll use to export the results of an eDiscovery search.</span></span>
  
1. <span data-ttu-id="4e8d1-110">如果已打开，请关闭 Office 365 电子数据展示导出工具。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-110">Close the Office 365 eDiscovery Export tool if it's open.</span></span> 
    
2. <span data-ttu-id="4e8d1-111">使用 filename 后缀.reg; 将以下文本保存到窗口注册表文件例如，PstExportSize.reg。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-111">Save the following text to a Window registry file by using a filename suffix of .reg; for example, PstExportSize.reg.</span></span> 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    <span data-ttu-id="4e8d1-p102">在上例中，`PstSizeLimitInBytes`值设置为 1073741824 字节或约为 1 GB。下面是一些其他示例值`PstSizeLimitInBytes`设置。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-p102">In the example above, the  `PstSizeLimitInBytes` value is set to 1,073,741,824 bytes or approximately 1 GB. Here are some other sample values for the  `PstSizeLimitInBytes` setting.</span></span> 
    
    |<span data-ttu-id="4e8d1-114">**Gb （约） 大小**</span><span class="sxs-lookup"><span data-stu-id="4e8d1-114">**Size in GB (approx.)**</span></span>|<span data-ttu-id="4e8d1-115">**以字节为单位的大小**</span><span class="sxs-lookup"><span data-stu-id="4e8d1-115">**Size in bytes**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="4e8d1-116">.7 GB (700 MB)</span><span class="sxs-lookup"><span data-stu-id="4e8d1-116">.7 GB (700 MB)</span></span>  <br/> |<span data-ttu-id="4e8d1-117">751619277</span><span class="sxs-lookup"><span data-stu-id="4e8d1-117">751619277</span></span>  <br/> |
    |<span data-ttu-id="4e8d1-118">2 GB</span><span class="sxs-lookup"><span data-stu-id="4e8d1-118">2 GB</span></span>  <br/> |<span data-ttu-id="4e8d1-119">2147483648</span><span class="sxs-lookup"><span data-stu-id="4e8d1-119">2147483648</span></span>  <br/> |
    |<span data-ttu-id="4e8d1-120">4 GB</span><span class="sxs-lookup"><span data-stu-id="4e8d1-120">4 GB</span></span>  <br/> |<span data-ttu-id="4e8d1-121">4294967296</span><span class="sxs-lookup"><span data-stu-id="4e8d1-121">4294967296</span></span>  <br/> |
    |<span data-ttu-id="4e8d1-122">8 GB</span><span class="sxs-lookup"><span data-stu-id="4e8d1-122">8 GB</span></span>  <br/> |<span data-ttu-id="4e8d1-123">8589934592</span><span class="sxs-lookup"><span data-stu-id="4e8d1-123">8589934592</span></span>  <br/> |
   
3. <span data-ttu-id="4e8d1-124">更改`PstSizeLimitInBytes`的 PST 文件时导出搜索结果中，然后保存该文件所需的最大大小的值。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-124">Change the `PstSizeLimitInBytes` value to the desired maximum size of a PST file when you export search results, and then save the file.</span></span> 
    
4. <span data-ttu-id="4e8d1-125">在 Windows 资源管理器中，单击或双击在上一步骤中创建该.reg 文件。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-125">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
5. <span data-ttu-id="4e8d1-126">在用户访问控制窗口中，单击**是**可允许注册表编辑器中进行的更改。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-126">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
6. <span data-ttu-id="4e8d1-127">当提示您继续，请单击**是**。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-127">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="4e8d1-128">在注册表编辑器将显示一条消息告知设置已成功添加到注册表。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-128">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
    
7. <span data-ttu-id="4e8d1-129">您可以重复步骤 3-6 以更改的值`PstSizeLimitInBytes`注册表设置。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-129">You can repeat steps 3 - 6 to change the value for the  `PstSizeLimitInBytes` registry setting.</span></span> 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a><span data-ttu-id="4e8d1-130">有关导出电子数据展示搜索结果时更改 PST 文件的默认大小的常见问题</span><span class="sxs-lookup"><span data-stu-id="4e8d1-130">Frequently asked questions about changing the default size of PST files when you export eDiscovery search results</span></span>

 <span data-ttu-id="4e8d1-131">**为什么是默认大小为 10 GB？**</span><span class="sxs-lookup"><span data-stu-id="4e8d1-131">**Why is the default size 10 GB?**</span></span>
  
<span data-ttu-id="4e8d1-132">10 GB 的默认大小基于客户反馈;10 GB 是内容的很好的平衡之间中单个 PST 文件损坏的最小有机会及最佳量。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-132">The default size of 10 GB was based on customer feedback; 10 GB is a good balance between the optimal amount of content in a single PST and with a minimum chance of file corruption.</span></span>
  
 <span data-ttu-id="4e8d1-133">**应增加或减少 PST 文件的默认大小？**</span><span class="sxs-lookup"><span data-stu-id="4e8d1-133">**Should I increase or decrease the default size of PST files?**</span></span>
  
<span data-ttu-id="4e8d1-p103">客户通常以减小大小限制，以便他们可以从物理上隔离附带其组织中的其他位置的可移动介质适合的搜索结果。我们不建议您增加默认大小，因为 PST 文件大于 10 GB 可能有损坏问题。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-p103">Customers tend to decrease the size limit so that the search results will fit on removable media that they can physically ship other locations in their organization. We don't recommend that you increase the default size because PST files larger than 10 GB might have corruption issues.</span></span>
  
 <span data-ttu-id="4e8d1-136">**有哪些计算机上执行此？**</span><span class="sxs-lookup"><span data-stu-id="4e8d1-136">**What computer do I have to do this on?**</span></span>
  
<span data-ttu-id="4e8d1-137">您需要更改运行 Office 365 电子数据展示导出工具的任何本地计算机上的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-137">You need to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span>
  
 <span data-ttu-id="4e8d1-138">**更改此设置后，是否需要重新启动计算机？**</span><span class="sxs-lookup"><span data-stu-id="4e8d1-138">**After I change this setting, do I have to reboot the computer?**</span></span>
  
<span data-ttu-id="4e8d1-p104">否，您无需重新启动计算机。但是，如果正在运行 Office 365 电子数据展示导出工具，您将需要关闭它，并在重新启动它后更改此设置。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-p104">No, you don't have to reboot the computer. But, if the Office 365 eDiscovery Export tool is running, you'll have to close it and the restart it after you change this setting.</span></span>
  
 <span data-ttu-id="4e8d1-141">**执行获取编辑现有的注册表项或执行创建新的密钥？**</span><span class="sxs-lookup"><span data-stu-id="4e8d1-141">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="4e8d1-p105">首次运行此过程中创建该.reg 文件创建一个新的注册表项。然后设置编辑每次更改并重新运行该.reg 编辑文件。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-p105">A new registry key is created the first time you run the .reg file that you created in this procedure. Then the setting is edited each time you change and re-run the .reg edit file.</span></span>

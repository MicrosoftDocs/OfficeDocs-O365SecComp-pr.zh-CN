---
title: 导出内容搜索结果时禁用报告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: 在您的本地计算机上编辑 Windows 注册表, 以便在从 Office 365 的 Security & 合规性中心导出内容搜索结果时禁用报告。 禁用这些报告可加快下载时间并节省磁盘空间。
ms.openlocfilehash: f6abcf8afe70bc6ce04f0f9343e28879f7fed885
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154824"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="05d58-104">导出内容搜索结果时禁用报告</span><span class="sxs-lookup"><span data-stu-id="05d58-104">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="05d58-105">当您使用 Office 365 电子数据展示导出工具导出 Security & 合规中心中的内容搜索结果时, 该工具会自动创建和导出包含有关导出内容的其他信息的两个报告。</span><span class="sxs-lookup"><span data-stu-id="05d58-105">When you use the Office 365 eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="05d58-106">这些报告是结果 .csv 文件和 Manifest .xml 文件 (有关这些报告的详细说明, 请参阅本主题中[有关禁用导出报告](#frequently-asked-questions-about-disabling-export-reports)部分的常见问题)。</span><span class="sxs-lookup"><span data-stu-id="05d58-106">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="05d58-107">由于这些文件可能非常大, 因此可以通过防止导出这些文件, 加快下载时间并节省磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="05d58-107">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="05d58-108">您可以通过更改用于导出搜索结果的计算机上的 Windows 注册表来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="05d58-108">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="05d58-109">如果您想要在以后包含这些报告, 可以编辑注册表设置。</span><span class="sxs-lookup"><span data-stu-id="05d58-109">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="05d58-110">创建注册表设置以禁用导出报告</span><span class="sxs-lookup"><span data-stu-id="05d58-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="05d58-111">在将用于将结果导出到内容搜索的计算机上执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="05d58-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="05d58-112">如果 Office 365 电子数据展示导出工具处于打开状态, 则将其关闭。</span><span class="sxs-lookup"><span data-stu-id="05d58-112">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="05d58-113">执行下列一项或两项操作, 具体取决于要禁用的导出报告。</span><span class="sxs-lookup"><span data-stu-id="05d58-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="05d58-114">**结果 .csv**</span><span class="sxs-lookup"><span data-stu-id="05d58-114">**Results.csv**</span></span>
    
      <span data-ttu-id="05d58-115">使用文件名后缀 .reg 将以下文本保存到 Windows 注册表文件中;例如, DisableResultsCsv。</span><span class="sxs-lookup"><span data-stu-id="05d58-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="05d58-116">**清单 .xml**</span><span class="sxs-lookup"><span data-stu-id="05d58-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="05d58-117">使用文件名后缀 .reg 将以下文本保存到 Windows 注册表文件中;例如, DisableManifestXml。</span><span class="sxs-lookup"><span data-stu-id="05d58-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="05d58-118">在 Windows 资源管理器中, 单击或双击您在前面步骤中创建的 .reg 文件。</span><span class="sxs-lookup"><span data-stu-id="05d58-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="05d58-119">在 "用户访问控制" 窗口中, 单击 **"是"** 以让注册表编辑器进行更改。</span><span class="sxs-lookup"><span data-stu-id="05d58-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="05d58-120">当系统提示您继续时, 请单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="05d58-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="05d58-121">注册表编辑器将显示一条消息, 指出已成功将设置添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="05d58-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="05d58-122">编辑注册表设置以重新启用导出报告</span><span class="sxs-lookup"><span data-stu-id="05d58-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="05d58-123">如果通过在上一过程中创建 .reg 文件禁用了结果. .csv 和 .Manifest 报告, 则可以编辑这些文件以重新启用报告, 以便将其导出到搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="05d58-123">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="05d58-124">再次在将用于将结果导出到内容搜索的计算机上执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="05d58-124">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="05d58-125">如果 Office 365 电子数据展示导出工具处于打开状态, 则将其关闭。</span><span class="sxs-lookup"><span data-stu-id="05d58-125">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="05d58-126">编辑您在上一过程中创建的 .reg 编辑文件中的一个或两个。</span><span class="sxs-lookup"><span data-stu-id="05d58-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="05d58-127">**结果 .csv**</span><span class="sxs-lookup"><span data-stu-id="05d58-127">**Results.csv**</span></span>
    
        <span data-ttu-id="05d58-128">在记事本中打开 DisableResultsCsv 文件, 将值`False`更改为`True`, 然后保存文件。</span><span class="sxs-lookup"><span data-stu-id="05d58-128">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="05d58-129">例如, 在编辑文件后, 其外观如下所示:</span><span class="sxs-lookup"><span data-stu-id="05d58-129">For example, after you edit the file, it looks like this:</span></span>
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="05d58-130">**清单 .xml**</span><span class="sxs-lookup"><span data-stu-id="05d58-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="05d58-131">在记事本中打开 DisableManifestXml 文件, 将值`False`更改为`True`, 然后保存文件。</span><span class="sxs-lookup"><span data-stu-id="05d58-131">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="05d58-132">例如, 在编辑文件后, 其外观如下所示:</span><span class="sxs-lookup"><span data-stu-id="05d58-132">For example, after you edit the file, it looks like this:</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="05d58-133">在 Windows 资源管理器中, 单击或双击在上一步中编辑过的 .reg 文件。</span><span class="sxs-lookup"><span data-stu-id="05d58-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="05d58-134">在 "用户访问控制" 窗口中, 单击 **"是"** 以让注册表编辑器进行更改。</span><span class="sxs-lookup"><span data-stu-id="05d58-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="05d58-135">当系统提示您继续时, 请单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="05d58-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="05d58-136">注册表编辑器将显示一条消息, 指出已成功将设置添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="05d58-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="05d58-137">有关禁用导出报告的常见问题</span><span class="sxs-lookup"><span data-stu-id="05d58-137">Frequently asked questions about disabling export reports</span></span>
<span data-ttu-id="05d58-138"><a name="faqs"> </a></span><span class="sxs-lookup"><span data-stu-id="05d58-138"></span></span>

 <span data-ttu-id="05d58-139">**什么是结果 .csv 和清单 .xml 报告？**</span><span class="sxs-lookup"><span data-stu-id="05d58-139">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="05d58-140">结果 .csv 和清单 .xml 文件包含有关导出的内容的其他信息。</span><span class="sxs-lookup"><span data-stu-id="05d58-140">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="05d58-141">**结果 .csv**包含作为搜索结果下载的每个项目的相关信息的 Excel 文档。</span><span class="sxs-lookup"><span data-stu-id="05d58-141">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="05d58-142">对于电子邮件, 结果日志包含有关每封邮件的信息, 其中包括:</span><span class="sxs-lookup"><span data-stu-id="05d58-142">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="05d58-143">邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。</span><span class="sxs-lookup"><span data-stu-id="05d58-143">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="05d58-144">发送或接收邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="05d58-144">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="05d58-145">邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="05d58-145">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="05d58-146">邮件的发件人和收件人。</span><span class="sxs-lookup"><span data-stu-id="05d58-146">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="05d58-147">如果在导出搜索结果时启用重复数据删除功能, 则该邮件是否为重复的邮件。</span><span class="sxs-lookup"><span data-stu-id="05d58-147">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="05d58-148">重复邮件在**父 ItemId**列中有一个将该邮件标识为重复的值。</span><span class="sxs-lookup"><span data-stu-id="05d58-148">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="05d58-149">**父 ItemId**列中的值与导出的邮件的 "**项目 DocumentId** " 列中的值相同。</span><span class="sxs-lookup"><span data-stu-id="05d58-149">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="05d58-150">对于 SharePoint 和 OneDrive for business 网站中的文档, 结果日志包含有关每个文档的信息, 包括:</span><span class="sxs-lookup"><span data-stu-id="05d58-150">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="05d58-151">文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="05d58-151">The URL for the document.</span></span>
    
  - <span data-ttu-id="05d58-152">文档所在的网站集的 URL 。</span><span class="sxs-lookup"><span data-stu-id="05d58-152">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="05d58-153">上次修改文档的日期。</span><span class="sxs-lookup"><span data-stu-id="05d58-153">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="05d58-154">文档的名称（位于结果日志中的主题列）。</span><span class="sxs-lookup"><span data-stu-id="05d58-154">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="05d58-155">**.Manifest**一个清单文件 (xml 格式), 包含搜索结果中包含的每个项目的相关信息。</span><span class="sxs-lookup"><span data-stu-id="05d58-155">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="05d58-156">此报告中的信息与 "结果 .csv" 报告相同, 但其格式为 "电子发现参考模型 (EDRM)" 指定的格式。</span><span class="sxs-lookup"><span data-stu-id="05d58-156">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="05d58-157">有关 EDRM 的详细信息, 请转[https://www.edrm.net](https://www.edrm.net)到。</span><span class="sxs-lookup"><span data-stu-id="05d58-157">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="05d58-158">**何时应禁止导出这些报告？**</span><span class="sxs-lookup"><span data-stu-id="05d58-158">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="05d58-159">这取决于您的特定需求。</span><span class="sxs-lookup"><span data-stu-id="05d58-159">It depends on your specific needs.</span></span> <span data-ttu-id="05d58-160">许多组织不需要有关搜索结果的其他信息, 也不需要这些报告。</span><span class="sxs-lookup"><span data-stu-id="05d58-160">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="05d58-161">**我必须在哪台计算机上执行此操作？**</span><span class="sxs-lookup"><span data-stu-id="05d58-161">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="05d58-162">您必须更改在其上运行 Office 365 电子数据展示导出工具的任何本地计算机上的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="05d58-162">You have to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="05d58-163">**更改此设置后, 必须重新启动计算机吗？**</span><span class="sxs-lookup"><span data-stu-id="05d58-163">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="05d58-164">否, 无需重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="05d58-164">No, you don't have to restart the computer.</span></span> <span data-ttu-id="05d58-165">但是, 如果 Office 365 电子数据展示导出工具正在运行, 则必须将其关闭, 然后在更改注册表设置后重新启动它。</span><span class="sxs-lookup"><span data-stu-id="05d58-165">But if the Office 365 eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="05d58-166">**是否已编辑现有注册表项或是否创建新的密钥？**</span><span class="sxs-lookup"><span data-stu-id="05d58-166">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="05d58-167">首次运行本主题中的过程中创建的 .reg 文件时, 会创建一个新的注册表项。</span><span class="sxs-lookup"><span data-stu-id="05d58-167">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="05d58-168">然后, 在每次更改并重新运行 .reg 编辑文件时, 都会编辑该设置。</span><span class="sxs-lookup"><span data-stu-id="05d58-168">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>

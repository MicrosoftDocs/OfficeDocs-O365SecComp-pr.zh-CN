---
title: 导出 Office 365 安全性内容的搜索结果时禁用报告&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: 编辑本地计算机上的 Windows 注册表禁用报告，从 Office 365 安全性导出内容的搜索结果时&amp;Comliance 中心。禁用这些报告可加快下载时间和节省磁盘空间。
ms.openlocfilehash: 3c09e0563ddd4469f21950dc3a698ce08b0014df
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525930"
---
# <a name="disable-reports-when-you-export-content-search-results-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="9a29f-104">导出 Office 365 安全性内容的搜索结果时禁用报告&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="9a29f-104">Disable reports when you export Content Search results in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="9a29f-p102">当您使用 Office 365 电子数据展示导出工具的安全中内容搜索结果导出&amp;合规性中心，该工具自动创建，并将导出包含有关导出的内容的其他信息的两个报表。这些报告是 Results.csv 文件和 Manifest.xml 文件 （请参阅有关这些报告的详细说明本主题中的[有关禁用导出报告的常见问题](#frequently-asked-questions-about-disabling-export-reports)一节）。由于这些文件可能会非常大，您可以加快下载时间和通过防止这些文件导出节省磁盘空间。您可以通过更改 Windows 注册表用于导出搜索结果的计算机上执行此操作。如果您想要包括在以后的报告，您可以编辑注册表设置。</span><span class="sxs-lookup"><span data-stu-id="9a29f-p102">When you use the Office 365 eDiscovery Export tool to export the results of a Content Search in the Security &amp; Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content. These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports). Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported. You can do this by changing the Windows Registry on the computer that you use to export the search results. If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="9a29f-110">创建注册表设置来禁用导出报告</span><span class="sxs-lookup"><span data-stu-id="9a29f-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="9a29f-111">您将使用导出内容的搜索结果的计算机上执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="9a29f-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="9a29f-112">如果已打开，请关闭 Office 365 电子数据展示导出工具。</span><span class="sxs-lookup"><span data-stu-id="9a29f-112">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="9a29f-113">执行一个或两个以下步骤，具体取决于哪个导出报告您想要禁用。</span><span class="sxs-lookup"><span data-stu-id="9a29f-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="9a29f-114">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="9a29f-114">**Results.csv**</span></span>
    
      <span data-ttu-id="9a29f-115">将以下文本保存到 Windows 注册表文件中，使用.reg; filename 后缀例如，DisableResultsCsv.reg。</span><span class="sxs-lookup"><span data-stu-id="9a29f-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="9a29f-116">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="9a29f-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="9a29f-117">将以下文本保存到 Windows 注册表文件中，使用.reg; filename 后缀例如，DisableManifestXml.reg。</span><span class="sxs-lookup"><span data-stu-id="9a29f-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="9a29f-118">在 Windows 资源管理器中，单击或双击在上一步骤中创建该.reg 文件。</span><span class="sxs-lookup"><span data-stu-id="9a29f-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="9a29f-119">在用户访问控制窗口中，单击**是**可允许注册表编辑器中进行的更改。</span><span class="sxs-lookup"><span data-stu-id="9a29f-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="9a29f-120">当提示您继续，请单击**是**。</span><span class="sxs-lookup"><span data-stu-id="9a29f-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="9a29f-121">在注册表编辑器将显示一条消息告知设置已成功添加到注册表。</span><span class="sxs-lookup"><span data-stu-id="9a29f-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="9a29f-122">编辑注册表设置，以重新启用导出报告</span><span class="sxs-lookup"><span data-stu-id="9a29f-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="9a29f-p103">如果您在前面过程中创建的.reg 文件禁用 Results.csv 和 Manifest.xml 报告，您可以编辑这些文件，若要重新启用报告，以便它与搜索结果导出。同样，您将使用导出内容的搜索结果的计算机上执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="9a29f-p103">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results. Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="9a29f-125">如果已打开，请关闭 Office 365 电子数据展示导出工具。</span><span class="sxs-lookup"><span data-stu-id="9a29f-125">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="9a29f-126">编辑一个或两个您在前一过程中创建的.reg 编辑文件。</span><span class="sxs-lookup"><span data-stu-id="9a29f-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="9a29f-127">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="9a29f-127">**Results.csv**</span></span>
    
        <span data-ttu-id="9a29f-p104">打开 DisableResultsCsv.reg 文件在记事本中，更改值`False`到`True`，然后保存该文件。例如，编辑该文件后，则它类似于此：</span><span class="sxs-lookup"><span data-stu-id="9a29f-p104">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file. For example, after you edit the file, it looks like this:</span></span>
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="9a29f-130">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="9a29f-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="9a29f-p105">打开 DisableManifestXml.reg 文件在记事本中，更改值`False`到`True`，然后保存该文件。例如，编辑该文件后，则它类似于此：</span><span class="sxs-lookup"><span data-stu-id="9a29f-p105">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file. For example, after you edit the file, it looks like this:</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="9a29f-133">在 Windows 资源管理器中，单击或双击在上一步中编辑.reg 文件。</span><span class="sxs-lookup"><span data-stu-id="9a29f-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="9a29f-134">在用户访问控制窗口中，单击**是**可允许注册表编辑器中进行的更改。</span><span class="sxs-lookup"><span data-stu-id="9a29f-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="9a29f-135">当提示您继续，请单击**是**。</span><span class="sxs-lookup"><span data-stu-id="9a29f-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="9a29f-136">在注册表编辑器将显示一条消息告知设置已成功添加到注册表。</span><span class="sxs-lookup"><span data-stu-id="9a29f-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="9a29f-137">有关禁用导出报告的常见问题</span><span class="sxs-lookup"><span data-stu-id="9a29f-137">Frequently asked questions about disabling export reports</span></span>
<span data-ttu-id="9a29f-138"><a name="faqs"> </a></span><span class="sxs-lookup"><span data-stu-id="9a29f-138"></span></span>

 <span data-ttu-id="9a29f-139">**Results.csv 和 Manifest.xml 报告有哪些？**</span><span class="sxs-lookup"><span data-stu-id="9a29f-139">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="9a29f-140">Results.csv 和 Manifest.xml 文件包含有关已导出的内容的其他信息。</span><span class="sxs-lookup"><span data-stu-id="9a29f-140">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="9a29f-p106">包含有关作为搜索结果是下载每个项目的信息的**Results.csv** Excel 文档。为电子邮件，结果日志包含有关每封邮件的信息包括：</span><span class="sxs-lookup"><span data-stu-id="9a29f-p106">**Results.csv** An Excel document that contains information about each item that is download as a search result. For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="9a29f-143">邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。</span><span class="sxs-lookup"><span data-stu-id="9a29f-143">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="9a29f-144">发送或接收邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="9a29f-144">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="9a29f-145">邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="9a29f-145">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="9a29f-146">邮件的发件人和收件人。</span><span class="sxs-lookup"><span data-stu-id="9a29f-146">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="9a29f-p107">邮件是否重复的邮件如果导出搜索结果时启用重复数据删除。重复的邮件将具有标识为重复的消息的**父 ItemId**列中的值。**父 ItemId**列中的值是已导出的邮件**项 DocumentId**列中的值相同。</span><span class="sxs-lookup"><span data-stu-id="9a29f-p107">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results. Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate. The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="9a29f-150">对于来自 SharePoint 和 OneDrive for Business 站点的文档，结果日志包含有关每个文档的信息包括：</span><span class="sxs-lookup"><span data-stu-id="9a29f-150">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="9a29f-151">文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="9a29f-151">The URL for the document.</span></span>
    
  - <span data-ttu-id="9a29f-152">文档所在的网站集的 URL 。</span><span class="sxs-lookup"><span data-stu-id="9a29f-152">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="9a29f-153">上次修改文档的日期。</span><span class="sxs-lookup"><span data-stu-id="9a29f-153">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="9a29f-154">文档的名称（位于结果日志中的主题列）。</span><span class="sxs-lookup"><span data-stu-id="9a29f-154">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="9a29f-p108">**Manifest.xml**清单文件 （以 XML 格式） 包含在搜索结果中包含每个项目的信息。此报告中的信息相同 Results.csv 报告，但其格式指定通过电子发现参考模型 (EDRM)。有关 EDRM 的详细信息，请转到[https://www.edrm.net](https://www.edrm.net)。</span><span class="sxs-lookup"><span data-stu-id="9a29f-p108">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results. The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM). For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="9a29f-158">**时应禁用导出这些报告？**</span><span class="sxs-lookup"><span data-stu-id="9a29f-158">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="9a29f-p109">这取决于您的特定需求。许多组织不需要有关搜索结果的其他信息，并且不需要这些报告。</span><span class="sxs-lookup"><span data-stu-id="9a29f-p109">It depends on your specific needs. Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="9a29f-161">**有哪些计算机上执行此？**</span><span class="sxs-lookup"><span data-stu-id="9a29f-161">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="9a29f-162">您必须更改运行 Office 365 电子数据展示导出工具的任何本地计算机上的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="9a29f-162">You have to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="9a29f-163">**更改此设置后，是否需要重新启动计算机？**</span><span class="sxs-lookup"><span data-stu-id="9a29f-163">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="9a29f-p110">否，您无需重新启动计算机。但是，如果正在运行 Office 365 电子数据展示导出工具，您需要关闭它，然后重新启动它后更改的注册表设置。</span><span class="sxs-lookup"><span data-stu-id="9a29f-p110">No, you don't have to restart the computer. But if the Office 365 eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="9a29f-166">**执行获取编辑现有的注册表项或执行创建新的密钥？**</span><span class="sxs-lookup"><span data-stu-id="9a29f-166">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="9a29f-p111">首次运行您在本主题中的过程中创建该.reg 文件创建一个新的注册表项。然后设置编辑每次更改并重新运行该.reg 编辑文件。</span><span class="sxs-lookup"><span data-stu-id="9a29f-p111">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic. Then the setting is edited each time you change and re-run the .reg edit file.</span></span>

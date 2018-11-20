---
title: 从 Office 365 安全性和合规性中心导出内容的搜索结果
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: '将搜索结果导出从 Office 365 安全性内容搜索&amp;合规性中心到本地计算机。Emaill 电子邮件结果导出为 PST 文件。内容来自 SharePoint 和 OneDrive for Business 网站导出为本机 Office 文档。 '
ms.openlocfilehash: 35fb0aa8a037fc77020269d1b42d738dd801ea0a
ms.sourcegitcommit: da4aa7335b577148ecd61e09bbb11039b817b287
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539114"
---
# <a name="export-content-search-results-from-the-office-365-security--compliance-center"></a><span data-ttu-id="15e1c-105">从 Office 365 安全性和合规性中心导出内容的搜索结果</span><span class="sxs-lookup"><span data-stu-id="15e1c-105">Export Content Search results from the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="15e1c-p102">内容搜索成功运行后，您可以将搜索结果导出到本地计算机。导出电子邮件结果时，他们正在下载到您的计算机作为 PST 文件。导出时内容来自 SharePoint 和 OneDrive for Business 站点，导出本机 Office 文档的副本。有更多文档和导出的搜索结果中包含的报告。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p102">After a Content Search is successfully run, you can export the search results to a local computer. When you export email results, they're downloaded to your computer as PST files. When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents are exported. There are additional documents and reports that are included with the exported search results.</span></span>
  
<span data-ttu-id="15e1c-p103">此外，导出 （作为单个邮件） 时，将解密的内容的搜索结果中包含的任何 RMS 加密电子邮件。默认情况下，此解密功能启用的电子数据展示管理员角色组的成员。这是因为 RMS 解密管理角色分配给此角色组。导出搜索结果时，请参阅有关 RMS 解密的详细信息[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p103">Additionally, any RMS-encrypted email messages that are included in the results of a Content Search will be decrypted when you export them (as individual messages). This decryption capability is enabled by default for members of the eDiscovery Manager role group. This is because the RMS Decrypt management role is assigned to this role group. See the [More information](#more-information) section for details about RMS decryption when you export search results.</span></span> 
  
<span data-ttu-id="15e1c-114">导出内容的搜索结果包括准备结果，然后将其下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="15e1c-114">Exporting the results of a Content Search involves preparing the results, and then downloading them to a local computer.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="15e1c-115">开始之前</span><span class="sxs-lookup"><span data-stu-id="15e1c-115">Before you begin</span></span>

- <span data-ttu-id="15e1c-p104">若要导出搜索结果，您必须在 Office 365 安全性的导出管理角色分配&amp;合规性中心。此角色分配给内置电子数据展示管理员角色组。它不是默认情况下分配给组织管理角色组。有关详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p104">To export search results, you have to be assigned the Export management role in the Office 365 Security &amp; Compliance Center. This role is assigned to the built-in eDiscovery Manager role group. It isn't assigned by default to the Organization Management role group. For more information, see [Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="15e1c-120">用于导出搜索结果的计算机必须满足以下系统要求：</span><span class="sxs-lookup"><span data-stu-id="15e1c-120">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="15e1c-121">32 位或 64 位版本的 Windows 7 和更高版本</span><span class="sxs-lookup"><span data-stu-id="15e1c-121">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="15e1c-122">Microsoft.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="15e1c-122">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="15e1c-123">支持的浏览器：</span><span class="sxs-lookup"><span data-stu-id="15e1c-123">A supported browser:</span></span>
    
     - <span data-ttu-id="15e1c-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="15e1c-124">Microsoft Edge</span></span>
    
        <span data-ttu-id="15e1c-125">或者</span><span class="sxs-lookup"><span data-stu-id="15e1c-125">OR</span></span>
    
     - <span data-ttu-id="15e1c-126">Microsoft Internet Explorer 10 和更高版本</span><span class="sxs-lookup"><span data-stu-id="15e1c-126">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="15e1c-p105">**注意：** Microsoft 不制造第三方扩展或 ClickOnce 应用程序加载项。导出搜索结果不受支持的浏览器使用第三方扩展或加载项中不受支持。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p105">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 
    
- <span data-ttu-id="15e1c-p106">当您下载搜索结果 （在步骤 2 中所述） 时，您可以通过使用导出搜索结果的计算机上配置的 Windows 注册表设置增加下载速度。有关详细信息，请参阅[增加下载速度导出电子数据展示搜索结果从 Office 365 时](increase-download-speeds-when-exporting-ediscovery-results.md)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p106">When you download search results (described in Step 2), you can increase the download speed by configuring a Windows Registry setting on the computer you use to export the search results. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
    
- <span data-ttu-id="15e1c-p107">导出搜索结果时，数据暂时存储在 Microsoft 云中的唯一 Microsoft Azure 存储位置之前其下载到本地计算机。确保您的组织可以连接到 Azure，即中的终结点**\*。 blob.core.windows.net** （通配符表示导出的唯一标识符）。搜索结果数据从 Azure 的存储位置创建后两周删除。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p107">When you export search results, the data is temporarily stored in a unique Microsoft Azure storage location in the Microsoft cloud before it's downloaded to your local computer. Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export). The search results data is deleted from the Azure storage location two weeks after it's created.</span></span> 
    
- <span data-ttu-id="15e1c-p108">如果您的组织使用代理服务器来与 Internet 通信，您需要您使用导出搜索结果 （以便导出工具可以由代理服务器身份验证） 的计算机上定义的代理服务器设置。若要执行此操作，匹配您的 Windows 版本的位置打开*machine.config*文件。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p108">If your organization uses a proxy server to communicate with the Internet, you need to define the proxy server settings on the computer that you use to export the search results (so the export tool can be authenticated by your proxy server). To do this, open the  *machine.config*  file in the location that matches your version of Windows.</span></span> 
    
  - <span data-ttu-id="15e1c-136">**32 位** - `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`</span><span class="sxs-lookup"><span data-stu-id="15e1c-136">**32-bit** - `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`</span></span>
    
  - <span data-ttu-id="15e1c-137">**64 位** - `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`</span><span class="sxs-lookup"><span data-stu-id="15e1c-137">**64-bit** - `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`</span></span>
    
    <span data-ttu-id="15e1c-p109">将以下行添加到*machine.config*文件其他地方之间`<configuration>`和`</configuration>`标记。请务必替换`ProxyServer`和`Port`使用正确的值为您的组织;例如， `proxy01.contoso.com:80` 。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p109">Add the following lines to the  *machine.config*  file somewhere between the  `<configuration>` and  `</configuration>` tags. Be sure to replace  `ProxyServer` and  `Port` with the correct values for your organization; for example,  `proxy01.contoso.com:80` .</span></span> 
    
    ```
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="http://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

- <span data-ttu-id="15e1c-140">请参阅有关导出搜索结果的限制的说明部分。</span><span class="sxs-lookup"><span data-stu-id="15e1c-140">See the  section for a description of the limits for exporting search results.</span></span> 
    
- <span data-ttu-id="15e1c-p110">可以导出的 PST 文件的最大大小为 10 GB。如果您想要更改此默认大小，您可以编辑用于导出搜索结果的计算机上的 Windows 注册表。请参阅[Change 导出电子数据展示搜索结果时的 PST 文件的大小](change-the-size-of-pst-files-when-exporting-results.md)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p110">The maximum size of a PST file that can be exported is 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. See [Change the size of PST files when exporting eDiscovery search results](change-the-size-of-pst-files-when-exporting-results.md).</span></span>
    
## <a name="step-1-prepare-search-results-for-export"></a><span data-ttu-id="15e1c-144">第 1 步：准备要导出的搜索结果</span><span class="sxs-lookup"><span data-stu-id="15e1c-144">Step 1: Prepare search results for export</span></span>

<span data-ttu-id="15e1c-p111">第一步是准备导出搜索结果。当您准备结果时，其上载到云中 Microsoft Azure 的存储位置。请注意，从邮箱和网站内容上载每小时 2 gb 的最大速率。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p111">The first step is to prepare the search results for exporting. When you prepare results, they are uploaded to an Azure storage location in the Microsoft cloud. Note that content from mailboxes and sites is uploaded at a maximum rate of 2 GB per hour.</span></span>
  
1. <span data-ttu-id="15e1c-148">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-148">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="15e1c-149">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="15e1c-149">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="15e1c-150">在安全与合规中心的左侧窗格中，单击“搜索和调查”\*\*\*\*\>\*\*\*\*“内容搜索”。</span><span class="sxs-lookup"><span data-stu-id="15e1c-150">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="15e1c-151">在**内容搜索**页上，选择搜索。</span><span class="sxs-lookup"><span data-stu-id="15e1c-151">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="15e1c-152">在细节窗格中，在**导出到的计算机上的结果**，下单击**开始导出**。</span><span class="sxs-lookup"><span data-stu-id="15e1c-152">In the details pane, under **Export results to a computer**, click **Start export**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="15e1c-p112">如果搜索结果不超过 7 天，系统会提示您更新搜索结果。如果发生这种情况，取消导出单击**更新搜索结果**在所选的搜索的详细信息窗格中，然后在结果更新后重新启动导出。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p112">If the results for a search are older than 7 days, you are prompted to update the search results. If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="15e1c-155">在**导出搜索结果**页上，在**包括中搜索这些项目**，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="15e1c-155">On the **Export the search results** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="15e1c-156">仅导出索引项</span><span class="sxs-lookup"><span data-stu-id="15e1c-156">Export only indexed items</span></span>
    
    - <span data-ttu-id="15e1c-157">导出编制索引和部分，索引项目</span><span class="sxs-lookup"><span data-stu-id="15e1c-157">Export indexed and partially indexed items</span></span>
    
    - <span data-ttu-id="15e1c-158">仅部分索引的项目导出</span><span class="sxs-lookup"><span data-stu-id="15e1c-158">Export only partially indexed items</span></span>
    
    <span data-ttu-id="15e1c-p113">有关导出有关如何部分索引项目的说明，请参阅[详细信息](#more-information)部分。有关部分索引项目的详细信息，请参阅[部分索引内容的搜索功能中的项目](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p113">See the [More information](#more-information) section for a description about how partially indexed items are exported. For more information about partially indexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="15e1c-161">在**导出 Exchange 的内容**，下选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="15e1c-161">Under **Export Exchange content as**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="15e1c-p114">**每个邮箱的一个 PST 文件**-包含搜索结果的每个用户邮箱的导出一个 PST 文件。相同的 PST 文件中包含用户的存档邮箱中的任何结果。请注意此选项重现的源邮箱中的邮箱文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p114">**One PST file for each mailbox** - Exports one PST file for each user mailbox that contains search results. Any results from the user's archive mailbox are included in the same PST file. Note that this option reproduces the mailbox folder structure from the source mailbox.</span></span> 
    
    - <span data-ttu-id="15e1c-p115">**包含所有邮件的一个 PST 文件**-导出 PST 包含单个文件 （名为*Exchange.pst* ） 包括在搜索所有源邮箱的搜索结果。请注意此选项重现关于每封邮件的邮箱文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p115">**One PST file containing all messages** - Exports a single PST file (named  *Exchange.pst*  ) that contains the search results from all source mailboxes included in the search. Note that this option reproduces the mailbox folder structure for each message.</span></span> 
    
    - <span data-ttu-id="15e1c-p116">**一个 PST 文件包含单个文件夹中的所有邮件**-导出到其中所有邮件单个 PST 文件的搜索结果位于单一的顶级文件夹中。此选项允许审阅者而无需导航每个项目的原始邮箱文件夹结构中查看项目按时间顺序 （按发送日期排序的项目）。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p116">**One PST file containing all messages in a single folder** - Exports search results to a single PST file where all messages are located in a single, top-level folder. This option lets reviewers review items in chronological order (items are sorted by sent date) without having to navigate the original mailbox folder structure for each item.</span></span> 
    
    - <span data-ttu-id="15e1c-p117">**单个邮件**-导出搜索结果作为单个电子邮件，使用.msg 格式。如果选择此选项，电子邮件搜索结果导出到的文件夹的文件系统中。如果结果导出到 PST 文件使用相同的单个邮件的文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p117">**Individual messages** - Exports search results as individual email messages, using the .msg format. If you select this option, email search results are exported to a folder in the file system. The folder path for individual messages is the same as the one used if you exported the results to PST files.</span></span> 
    
      > [!IMPORTANT]
      > <span data-ttu-id="15e1c-p118">解密 RMS 加密的邮件，他们正在导出时，必须将电子邮件搜索结果导出为单个邮件中。导出搜索结果为 PST 文件时，将一直保持加密加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p118">To decrypt RMS-encrypted messages when they're exported, you must export email search results as individual messages. Encrypted messages will remain encrypted if you export the search results as a PST file.</span></span> 
  
8. <span data-ttu-id="15e1c-p119">单击**启用重复数据删除**复选框来排除重复的邮件。此选项仅会显示搜索的内容源包括 Exchange 邮箱或公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p119">Click the **Enable de-duplication** checkbox to exclude duplicate messages. This option appears only if the content sources of the search includes Exchange mailboxes or public folders.</span></span> 
    
    <span data-ttu-id="15e1c-p120">如果选择此选项，即使在已搜索的邮箱中找到多个副本的相同的邮件将导出的一条消息，只有一个副本。导出结果报告 (Results.csv) 将包含重复的消息的每个副本的行，以便可以识别的邮箱 （或公用文件夹） 包含重复的邮件的副本。有关重复数据删除和如何重复项标识的详细信息，请参阅[电子数据展示搜索结果中的重复数据删除](de-duplication-in-ediscovery-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p120">If you select this option, only one copy of a message will be exported even if multiple copies of the same message are found in the mailboxes that were searched. The export results report (Results.csv) will contain a row for every copy of a duplicate message so that you can identify the mailboxes (or public folders) that contain a copy of the duplicate message. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>
    
9. <span data-ttu-id="15e1c-p121">单击要导出的 SharePoint 文档的所有版本**的 SharePoint 文档包含版本**复选框。此选项仅会显示搜索的内容源业务网站包括 SharePoint 或 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p121">Click the **Include versions for SharePoint documents** checkbox to export all versions of SharePoint documents. This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span> 
    
10. <span data-ttu-id="15e1c-p122">单击**导出文件压缩 (zip) 文件夹中的**复选框可将搜索结果导出到压缩文件夹。仅当您选择将 Exchange 项目导出为单个邮件，并且在搜索结果中包括 SharePoint 或 OneDrive 文档时，此选项才可用。主要使用此选项，若要解决 Windows 文件路径名称中的 260 字符限制，导出项目时。请参阅"中的文件名导出项的"[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p122">Click the **Export files in a compressed (zipped) folder** checkbox to export search results to compressed folders. This option is available only when you choose to export Exchange items as individual messages and when the search results include SharePoint or OneDrive documents. This option is primarily used to work around the 260 character limit in Windows file path names when items are exported. See the "Filenames of exported items" in the [More information](#more-information) section.</span></span> 
    
11. <span data-ttu-id="15e1c-185">单击**开始导出**。</span><span class="sxs-lookup"><span data-stu-id="15e1c-185">Click **Start export**.</span></span>
    
    <span data-ttu-id="15e1c-p123">搜索结果准备好用于下载，这意味着它们正在上载到 Microsoft 云中的 Azure 存储位置。搜索结果下载准备就绪后，**下载导出结果**链接详细信息窗格中显示在**导出到的计算机上的结果**下。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p123">The search results are prepared for downloading, which means they're being uploaded to the Azure storage location in the Microsoft cloud. When the search results are ready for download, the **Download exported results** link is displayed under **Export results to a computer** in the details pane.</span></span> 
  
## <a name="step-2-download-the-search-results"></a><span data-ttu-id="15e1c-188">第 2 步：下载搜索结果</span><span class="sxs-lookup"><span data-stu-id="15e1c-188">Step 2: Download the search results</span></span>

<span data-ttu-id="15e1c-189">下一步是将搜索结果从 Azure 的存储位置下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="15e1c-189">The next step is to download the search results from the Azure storage location to your local computer.</span></span>
  
<span data-ttu-id="15e1c-p124">如前所述，您可以配置用于导出搜索结果的计算机上的 Windows 注册表设置来增加下载速度。有关详细信息，请参阅[增加下载速度导出电子数据展示搜索结果从 Office 365 时](increase-download-speeds-when-exporting-ediscovery-results.md)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p124">As previously explained, you can increase the download speed by configuring a Windows Registry setting on the computer you use to export the search results. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="15e1c-192">在开始，在**导出到的计算机上的结果**下的导出搜索的详细信息窗格中，单击**下载导出结果**。</span><span class="sxs-lookup"><span data-stu-id="15e1c-192">In the details pane for the search that you started the export for, under **Export results to a computer**, click **Download exported results**.</span></span>
    
    <span data-ttu-id="15e1c-193">**下载导出结果**窗口中显示，其中包含有关将下载到计算机的搜索结果的以下信息。</span><span class="sxs-lookup"><span data-stu-id="15e1c-193">The **Download exported results** window is displayed and contains the following information about the search results that will be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="15e1c-194">将下载的项的数目。</span><span class="sxs-lookup"><span data-stu-id="15e1c-194">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="15e1c-195">将下载的项的预计总大小。</span><span class="sxs-lookup"><span data-stu-id="15e1c-195">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="15e1c-p125">是否导出索引或未编制索引。未编制索引项是可以识别格式的项目，出于其他原因被加密或未编入索引。有关详细信息，请参阅[Unindexed items in Content Search](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p125">Whether indexed or unindexed will be exported. Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons. For more information, see [Unindexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
    - <span data-ttu-id="15e1c-199">SharePoint 文档版本是否将被下载。</span><span class="sxs-lookup"><span data-stu-id="15e1c-199">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="15e1c-p126">导出准备过程的状态。即使数据准备未完成，你也可以开始下载搜索结果。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p126">The status of the export preparation process. You can start downloading search results even if the preparation of the data isn't complete.</span></span>
    
2. <span data-ttu-id="15e1c-p127">在**导出密钥**下单击**复制到剪贴板**。您将在步骤 5 中使用此项，若要下载搜索结果。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p127">Under **Export key**, click **Copy to clipboard**. You will use this key in step 5 to download the search results.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="15e1c-204">因为任何人都可以安装和启用电子数据展示导出工具，然后使用该密钥来下载搜索结果，所以一定要采取预防措施来保护此密钥，就像保护你的密码或其他与安全相关的信息。 </span><span class="sxs-lookup"><span data-stu-id="15e1c-204">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search results, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="15e1c-205">单击**下载结果**。</span><span class="sxs-lookup"><span data-stu-id="15e1c-205">Click **Download results**.</span></span>
    
4. <span data-ttu-id="15e1c-206">如果提示您安装**MicrosoftOffice 365 电子数据展示导出工具**，请单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="15e1c-206">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="15e1c-207">在**电子数据展示导出工具**中，粘贴您在步骤 2 中相应的框中复制的导出密钥。</span><span class="sxs-lookup"><span data-stu-id="15e1c-207">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="15e1c-208">单击“**浏览**”指定要下载搜索结果文件的位置。</span><span class="sxs-lookup"><span data-stu-id="15e1c-208">Click **Browse** to specify the location where you want to download the search result files.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="15e1c-209">由于高磁盘活动 （读取和写入） 量，应该下载到本地磁盘驱动器; 搜索结果不下载到映射的网络驱动器或其他网络位置。</span><span class="sxs-lookup"><span data-stu-id="15e1c-209">Due to the high amount of disk activity (reads and writes), you should download search results to a local disk drive; don't download them to a mapped network drive or other network location.</span></span> 
  
1. <span data-ttu-id="15e1c-210">单击“**开始**”将搜索结果下载到计算机。</span><span class="sxs-lookup"><span data-stu-id="15e1c-210">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="15e1c-p128">**电子数据展示导出工具**显示有关导出过程，包括估计的数量 （和大小） 的剩余的项的下载状态信息。在导出过程完成后，您可以访问他们已下载的位置中的文件。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p128">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    

  
## <a name="more-information"></a><span data-ttu-id="15e1c-213">更多信息</span><span class="sxs-lookup"><span data-stu-id="15e1c-213">More information</span></span>

<span data-ttu-id="15e1c-214">下面是有关导出搜索结果的详细信息。</span><span class="sxs-lookup"><span data-stu-id="15e1c-214">Here's more information about exporting search results.</span></span>
  
[<span data-ttu-id="15e1c-215">导出限制</span><span class="sxs-lookup"><span data-stu-id="15e1c-215">Export limits</span></span>](#export-limits)
  
[<span data-ttu-id="15e1c-216">导出报告</span><span class="sxs-lookup"><span data-stu-id="15e1c-216">Export reports</span></span>](#export-reports)
  
[<span data-ttu-id="15e1c-217">导出部分索引的项目</span><span class="sxs-lookup"><span data-stu-id="15e1c-217">Exporting partially indexed items</span></span>](#exporting-partially-indexed-items)

[<span data-ttu-id="15e1c-218">导出单个邮件或 PST 文件</span><span class="sxs-lookup"><span data-stu-id="15e1c-218">Exporting individual messages or PST files</span></span>](#exporting-individual-messages-or-pst-files)
  
[<span data-ttu-id="15e1c-219">解密 RMS 加密的邮件</span><span class="sxs-lookup"><span data-stu-id="15e1c-219">Decrypting RMS-encrypted messages</span></span>](#decrypting-rms-encrypted-messages)

[<span data-ttu-id="15e1c-220">导出项的文件名</span><span class="sxs-lookup"><span data-stu-id="15e1c-220">Filenames of exported items</span></span>](#filenames-of-exported-items)  
  
[<span data-ttu-id="15e1c-221">其他</span><span class="sxs-lookup"><span data-stu-id="15e1c-221">Miscellaneous</span></span>](#miscellaneous)
  
 ### <a name="export-limits"></a><span data-ttu-id="15e1c-222">导出限制</span><span class="sxs-lookup"><span data-stu-id="15e1c-222">Export limits</span></span>
  
- <span data-ttu-id="15e1c-223">从安全导出搜索结果&amp;合规性中心具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="15e1c-223">Exporting search results from the Security &amp; Compliance Center has the following limits:</span></span>
    
  - <span data-ttu-id="15e1c-p129">您可以从单个内容搜索导出最多 2 TB 的数据。如果搜索结果大于 2 TB，请考虑使用日期范围或其他类型的筛选器以减少在搜索结果的总大小。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p129">You can export a maximum of 2 TB of data from a single Content Search. If the search results are larger than 2 TB, consider using date ranges or other types of filters to decrease the total size of the search results.</span></span>
    
  - <span data-ttu-id="15e1c-226">您的组织可以在一天内导出最多 2 TB 的数据。</span><span class="sxs-lookup"><span data-stu-id="15e1c-226">Your organization can export a maximum of 2 TB of data during a single day.</span></span>
    
  - <span data-ttu-id="15e1c-227">在你的组织中最多可以同时运行 10 个导出。</span><span class="sxs-lookup"><span data-stu-id="15e1c-227">You can have a maximum of 10 exports running at the same time within your organization.</span></span>
    
  - <span data-ttu-id="15e1c-228">单个用户可以同时运行的三个导出的最大值。</span><span class="sxs-lookup"><span data-stu-id="15e1c-228">A single user can run a maximum of three exports at the same time.</span></span>
    
  - <span data-ttu-id="15e1c-229">导出内容的搜索报告不计入任何导出限制。</span><span class="sxs-lookup"><span data-stu-id="15e1c-229">Exporting Content Search reports doesn't count against any of the export limits.</span></span> 
    
- <span data-ttu-id="15e1c-230">如上文所述，从邮箱和网站的搜索结果上载到 Azure 的存储位置 (如中所述[步骤 1： 准备的搜索结果导出](#step-1-prepare-search-results-for-export)) 每小时 2 gb 的最大速率。</span><span class="sxs-lookup"><span data-stu-id="15e1c-230">As previously stated, search results from mailboxes and sites are uploaded to the Azure storage location (as described in [Step 1: Prepare search results for export](#step-1-prepare-search-results-for-export)) at a maximum rate of 2 GB per hour.</span></span>
    
- <span data-ttu-id="15e1c-p130">默认情况下，可以导出的 PST 文件的最大大小为 10 GB。也就是说，如果用户的邮箱的搜索结果大于 10 GB，将在两个 （或多个） 单独的 PST 文件导出邮箱的搜索结果。此外，如果您选择要导出的单个 PST 文件中的所有搜索结果，PST 文件将被 spilt 到其他 PST 文件的搜索结果的总大小大于 10 GB。如果您想要更改此默认大小，您可以编辑用于导出搜索结果的计算机上的 Windows 注册表。请参阅[Change 导出电子数据展示搜索结果时的 PST 文件的大小](change-the-size-of-pst-files-when-exporting-results.md)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p130">The maximum size of a PST file that can be exported is 10 GB by default. That means if the search results from a user's mailbox are larger than 10 GB, the search results for the mailbox will be exported in two (or more) separate PST files. Additionally, if you choose to export all search results in a single PST file, the PST file will be spilt into additional PST files if the total size of the search results is larger than 10 GB. If you want to change this default size, you can edit the Windows Registry on the computer that you use to export the search results. See [Change the size of PST files when exporting eDiscovery search results](change-the-size-of-pst-files-when-exporting-results.md).</span></span>
    
    <span data-ttu-id="15e1c-p131">此外，特定邮箱的搜索结果不会划分多个 PST 文件中的单个邮箱的内容为 10 GB 以上。如果您选择要导出搜索结果中一个 PST 文件的包含单个文件夹中的所有邮件和搜索结果是大于 10 GB，项目仍组织按时间顺序，因此他们将 spilt 到其他基于发送 d 的 PST 文件用餐。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p131">Additionally, the search results from a specific mailbox won't be divided among multiple PST files unless the content from a single mailbox is more than 10 GB. If you chose to export the search results in one PST file for that contains all messages in a single folder and the search results are larger than 10 GB, the items are still organized in chronological order, so they will be spilt into additional PST files based on the sent date.</span></span>
     
 ### <a name="export-reports"></a><span data-ttu-id="15e1c-238">导出报告</span><span class="sxs-lookup"><span data-stu-id="15e1c-238">Export reports</span></span>
  
- <span data-ttu-id="15e1c-239">导出搜索结果时，以下报告都包含除了搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="15e1c-239">When you export search results, the following reports are included in addition to the search results.</span></span>
    
  - <span data-ttu-id="15e1c-p132">**导出摘要**Excel 文档包含在导出操作的摘要。这包括信息，如搜索的内容源的数量、 搜索结果中，并已导出的项的估计和下载数目的估计和下载大小。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p132">**Export Summary** An Excel document that contains a summary of the export. This includes information such as the number of content sources that were searched, the estimated and downloaded sizes of the search results, and the estimated and downloaded number of items that were exported.</span></span> 
    
  - <span data-ttu-id="15e1c-242">**清单**包含有关包含在搜索结果中每个项目的信息 （以 XML 格式） 的清单文件。</span><span class="sxs-lookup"><span data-stu-id="15e1c-242">**Manifest** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
  - <span data-ttu-id="15e1c-p133">**结果**Excel 文档包含有关作为搜索结果是下载每个项目的信息。为电子邮件，结果日志包含有关每封邮件的信息包括：</span><span class="sxs-lookup"><span data-stu-id="15e1c-p133">**Results** An Excel document that contains information about each item that is download as a search result. For email, the result log contains information about each message, including:</span></span> 
    
      - <span data-ttu-id="15e1c-245">邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。</span><span class="sxs-lookup"><span data-stu-id="15e1c-245">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
        
      - <span data-ttu-id="15e1c-246">发送或接收邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="15e1c-246">The date the message was sent or received.</span></span>
        
      - <span data-ttu-id="15e1c-247">邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="15e1c-247">The Subject line from the message.</span></span>
        
      - <span data-ttu-id="15e1c-248">邮件的发件人和收件人。</span><span class="sxs-lookup"><span data-stu-id="15e1c-248">The sender and recipients of the message.</span></span>
        
      - <span data-ttu-id="15e1c-p134">邮件是否重复的邮件如果导出搜索结果时启用消除选项。重复的邮件将具有标识为重复的消息的**项重复**列中的值。**对项目复制到**列中的值包含已导出的邮件项标识。有关详细信息，请参阅[电子数据展示搜索结果中的重复数据删除](de-duplication-in-ediscovery-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p134">Whether the message is a duplicate message if you enabled the de-duplication option when exporting the search results. Duplicate messages will have a value in the **Duplicate to Item** column that identifies the message as a duplicate. The value in the **Duplicate to Item** column contains the item identity of the message that was exported. For more information, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>
        
      <span data-ttu-id="15e1c-253">对于来自 SharePoint 和 OneDrive for Business 站点的文档，结果日志包含有关每个文档的信息包括：</span><span class="sxs-lookup"><span data-stu-id="15e1c-253">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
        
      - <span data-ttu-id="15e1c-254">文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="15e1c-254">The URL for the document.</span></span>
        
      - <span data-ttu-id="15e1c-255">文档所在的网站集的 URL 。</span><span class="sxs-lookup"><span data-stu-id="15e1c-255">The URL for the site collection where the document is located.</span></span>
        
      - <span data-ttu-id="15e1c-256">上次修改文档的日期。</span><span class="sxs-lookup"><span data-stu-id="15e1c-256">The date that the document was last modified.</span></span>
        
      - <span data-ttu-id="15e1c-257">文档的名称（位于结果日志中的主题列）。</span><span class="sxs-lookup"><span data-stu-id="15e1c-257">The name of the document (which is located in the Subject column in the result log).</span></span>
    
  - <span data-ttu-id="15e1c-p135">**未编制索引的项目**Excel 文档包含有关将搜索结果中包含任何部分索引项目的信息。如果不包括部分索引的项目生成搜索结果报告时，此报告将仍下载，但将为空。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p135">**Unindexed Items** An Excel document that contains information about any partially indexed items that would be included in the search results. If you don't include partially indexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span> 
    
  - <span data-ttu-id="15e1c-p136">**错误和警告**包含错误和警告遇到导出的文件。请参阅错误详细信息列中的特定于每个单独的错误或警告的信息。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p136">**Errors and Warnings** Contains errors and warnings for files encountered during export. See the Error Details column for information specific to each individual error or warning.</span></span> 
    
  - <span data-ttu-id="15e1c-p137">**已跳过项目**导出时搜索结果来自 SharePoint 和 OneDrive for Business 站点，导出通常包括跳过的项目报告 (SkippedItems.csv)。在此报告中所引用的项目通常不会下载，如文件夹或文档的项目设置。不导出此类型的项是通过设计。对于而跳过其他项，错误 Type 和而跳过的项目报告中的错误详细信息字段显示项目的原因而跳过和未下载和其他搜索结果。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p137">**Skipped Items** When you export search results from SharePoint and OneDrive for Business sites, the export will usually include a skipped items report (SkippedItems.csv). The items cited in this report are typically items that won't be downloaded, such as a folder or a document set. Not exporting this types of items is by design. For other items that were skipped, the 'Error Type' and 'Error Details' field in the skipped items report show the reason the item was skipped and wasn't download with the other search results.</span></span> 
    
  - <span data-ttu-id="15e1c-266">**跟踪日志**包含有关导出过程的详细日志记录信息并可以帮助在导出过程中发现的问题。</span><span class="sxs-lookup"><span data-stu-id="15e1c-266">**Trace Log** Contains detailed logging information about the export process and can help uncover issues during export.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="15e1c-p138">您可以只导出这些文档，而无需实际的搜索结果导出。请参阅[导出内容的搜索报告](export-a-content-search-report.md)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p138">You can just export these documents without having to export the actual search results. See [Export a Content Search report](export-a-content-search-report.md).</span></span> 
  
 ### <a name="exporting-partially-indexed-items"></a><span data-ttu-id="15e1c-269">导出部分索引的项目</span><span class="sxs-lookup"><span data-stu-id="15e1c-269">Exporting partially indexed items</span></span>
  
- <span data-ttu-id="15e1c-p139">如果要从搜索结果中返回邮箱的所有项的内容搜索导出邮箱项目 (由于没有关键字位置包含搜索查询中)，部分索引的项目不会复制到 PST 文件中包含的未编制索引的项目。这是因为所有项目，包括任何部分索引的项目，将自动都包含在正则搜索结果中。这意味着将包括部分索引的项目的 PST 文件中 （或作为单个邮件） 包含的其他、 索引项。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p139">If you're exporting mailbox items from a content search that returns all mailbox items in the search results (because no keywords where included in the search query), partially indexed items won't be copied to the PST file that contains the unindexed items. This is because all items, including any partially indexed items, are automatically included in the regular search results. This means that partially indexed items will be included in a PST file (or as individual messages) that contains the other, indexed items.</span></span>
    
    <span data-ttu-id="15e1c-p140">此外，如果您将导出的索引和部分索引项目或从返回的所有项的内容搜索导出仅的已编制索引的项目，将下载相同数量的项目。即使估计的搜索结果的内容搜索发生这种情况 (安全中的搜索统计信息中显示&amp;合规性中心) 仍将包括安单独的部分索引项目数量。例如，假设包含所有项目 （没有搜索查询中的关键字） 的搜索的估计值显示 1,000 项找到并找到还到 200 部分索引的项。在这种情况下，1,000 项包括部分索引的项目，因为搜索返回的所有项目。换句话说，有 1000 返回搜索，而不 1200 项目 （如您预想） 的总项目。如果将此搜索结果导出并选择至导出编制索引和部分编制索引项 （或只是索引的项），然后将下载 1,000 项。同样，这是因为部分索引的项目附带的正则 （索引） 的结果时您使用空搜索查询返回的所有项目。在此示例中，如果您选择要导出仅部分索引的项目，然后仅 200 未编制索引的项目会下载。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p140">Additionally, if you export both the indexed and partially indexed items or if you export only the indexed items from a content search that returns all items, the same number of items will be downloaded. This happens even though the estimated search results for the content search (displayed in the search statistics in the Security &amp; Compliance Center) will still include a separate estimate for the number of partially indexed items. For example, let's say that the estimate for a search that includes all items (no keywords in the search query) shows that 1,000 items were found and that 200 partially indexed items were also found. In this case, the 1,000 items include the partially indexed items because the search returns all items. In other words, there are 1,000 total items returned by the search, and not 1,200 items (as you might expect). If you export the results of this search and choose to export indexed and partially indexed items (or just indexed items), then 1,000 items will be downloaded. Again, that's because partially indexed items are included with the regular (indexed) results when you use a blank search query to return all items. In this same example, if you choose to export only partially indexed items, then only the 200 unindexed items would be downloaded.</span></span>
    
    <span data-ttu-id="15e1c-281">另请注意，在上面的示例 （当索引和部分索引的项目导出或导出唯一索引的项），导出的搜索结果中包含**导出的摘要**报告将列表 1,000 项估计的项和 1,000 个下载如上文所述的相同原因的项目。</span><span class="sxs-lookup"><span data-stu-id="15e1c-281">Also note that in the previous example (when you export indexed and partially indexed items or you export only indexed items) , the **Export Summary** report included with the exported search results would list 1,000 items estimated items and 1,000 downloaded items for the same reasons as previously described.</span></span> 
    
- <span data-ttu-id="15e1c-p141">如果您正在导出结果的搜索特定内容的位置或您的组织中的所有内容位置的搜索，将导出仅部分中的项包含与搜索条件匹配的项的内容位置。换句话说，如果某个邮箱或站点中不发现的任何搜索结果，然后任何部分索引的邮箱中的项目或不会导出网站。原因是，导出部分索引的项目从大量组织中的位置可能增加导出错误的可能性和增加导出和下载的搜索结果所需的时间。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p141">If the search that you're exporting results from was a search of specific content locations or all content locations in your organization, only the partially items from content locations that contain items that match the search criteria will be exported. In other words, if no search results are found in a mailbox or site, then any partially indexed items in that mailbox or site won't be exported. The reason for this is that exporting partially indexed items from lots of locations in the organization might increase the likelihood of export errors and increase the time it takes to export and download the search results.</span></span>
    
    <span data-ttu-id="15e1c-285">若要从搜索的所有内容位置导出部分索引的项目，配置搜索以返回 （通过搜索查询中移除所有关键字） 的所有项目和导出搜索结果时，然后导出仅部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="15e1c-285">To export partially indexed items from all content locations for a search, configure the search to return all items (by removing any keywords from the search query) and then export only partially indexed items when you export the search results.</span></span>
    
    ![使用 thrid 导出选项仅未编制索引的项目导出](media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- <span data-ttu-id="15e1c-p142">导出时搜索结果从 SharePoint 或 OneDrive for Business 站点，能够未编制索引的项目导出还取决于您选择导出选项和搜索网站是否包含与搜索条件匹配的索引的项。例如，如果搜索特定 SharePoint 或 OneDrive for Business 站点，并不找到任何搜索结果，然后从这些网站没有未编制索引的项将导出如果您选择已编制索引和未编制索引的项目导出第二个导出选项。如果从网站索引的项不匹配的搜索条件，然后从该网站的所有未编制索引的项将被导出导出已编制索引和未编制索引的项目时。下图介绍基于网站包含与搜索条件匹配的索引的项的导出选项。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p142">When exporting search results from SharePoint or OneDrive for Business sites, the ability to export unindexed items also depends on the export option that you select and whether a site that was searched contains an indexed item that matches the search criteria. For example, if you search specific SharePoint or OneDrive for Business sites and no search results are found, then no unindexed items from those sites will be exported if you choose the second export option to export both indexed and unindexed items. If an indexed item from a site does match the search criteria, then all unindexed items from that site will be exported when exporting both indexed and unindexed items. The following illustration describes the export options based on whether or not a site contains an indexed item that matches the search criteria.</span></span>
    
    ![选择基于网站包含索引的项相匹配的搜索条件导出选项](media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    
    <span data-ttu-id="15e1c-p143">A-导出仅与搜索条件匹配的索引的项。不导出任何部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p143">A - Only indexed items that matches the search criteria are exported. No partially indexed items are exported.</span></span>
    
    <span data-ttu-id="15e1c-p144">B-如果没有索引的项目从网站相匹配的搜索条件，不导出该相同网站中的部分索引的项目。如果在搜索结果中返回网站中的索引的项，将导出的网站中的部分索引的项。换句话说，导出仅包含与搜索条件匹配的项的网站中的部分索引的项。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p144">B - If no indexed items from a site match the search criteria, then partially indexed items from that same site aren't exported. If indexed items from a site are returned in the search results, then the partially indexed items from that site are exported. In other words, only the partially indexed items from sites that contain items that match the search criteria are exported.</span></span>
    
    <span data-ttu-id="15e1c-297">C-导出所有部分索引的项目从搜索中的所有网站，而不管网站是否包含与搜索条件匹配项。</span><span class="sxs-lookup"><span data-stu-id="15e1c-297">C - All partially indexed items from all sites in the search are exported, regardless of whether a site contains items that match the search criteria.</span></span>
    
    <span data-ttu-id="15e1c-298">如果您选择要导出的部分索引的项，部分索引的邮箱项目将导出到一个单独的 PST 文件，无论在**导出 Exchange 内容**下选择的选项。</span><span class="sxs-lookup"><span data-stu-id="15e1c-298">If you choose to export partially indexed items, partially indexed mailbox items are exported in a separate PST file regardless of the option that you choose under **Export Exchange content as**.</span></span>

- <span data-ttu-id="15e1c-p145">如果部分索引的项目返回在搜索结果 （因为与搜索条件匹配的部分索引项目的其他属性），然后使用正则搜索结果导出部分索引。因此，如果您选择要导出的索引的项和部分索引的项目 （通过选择**所有项目，包括具有无法识别的格式，进行加密，或出于其他原因无法编制索引**的导出选项），则部分索引的项目导出使用正则结果将列出 Results.csv 报告中。它们将不会在未编制索引的 items.csv 报告中列出。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p145">If partially indexed items are returned in the search results (because other properties of an partially indexed items matched the search criteria), then those partially indexed are exported with the regular search results. So, if you choose to export both indexed items and partially indexed items (by selecting the **All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons** export option), the partially indexed items exported with the regular results will be listed in the Results.csv report. They will not be listed in the Unindexed items.csv report.</span></span>
    
 ### <a name="exporting-individual-messages-or-pst-files"></a><span data-ttu-id="15e1c-302">导出单个邮件或 PST 文件</span><span class="sxs-lookup"><span data-stu-id="15e1c-302">Exporting individual messages or PST files</span></span>
  
- <span data-ttu-id="15e1c-p146">如果一条消息的文件路径名称超出 Windows 的最大字符限制，被截断的文件路径名称。但的原始文件路径名称会列在的清单和 ResultsLog。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p146">If the file path name of a message exceeds the maximum character limit for Windows, the file path name is truncated. But the original file path name will be listed in the Manifest and ResultsLog.</span></span>
    
- <span data-ttu-id="15e1c-p147">如前所述，电子邮件的搜索结果导出到一个文件夹中的文件系统。单个邮件的文件夹路径将复制的文件夹路径在用户的邮箱。例如，名为"ContosoCase101"搜索用户的收件箱中的邮件将位于的文件夹路径`~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox`。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p147">As previously explained, email search results are exported to a folder in the file system. The folder path for individual messages would replicate the folder path in the user's mailbox. For example, for a search named "ContosoCase101" messages in a user's inbox would be located in the folder path  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox`.</span></span> 
    
- <span data-ttu-id="15e1c-p148">如果您选择要导出一个包含单个文件夹中的所有邮件的 PST 文件中的电子邮件，**已删除邮件**文件夹和**搜索文件夹**文件夹中包含的 PST 文件夹的最高级别。这些文件夹将为空。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p148">If you choose to export email messages in one PST file containing all messages in a single folder, a **Deleted Items** folder and a **Search Folders** folder are included in the top level of the PST folder. These folders will be empty.</span></span> 
  
 ### <a name="decrypting-rms-encrypted-messages"></a><span data-ttu-id="15e1c-310">解密 RMS 加密的邮件</span><span class="sxs-lookup"><span data-stu-id="15e1c-310">Decrypting RMS-encrypted messages</span></span>
  
- <span data-ttu-id="15e1c-p149">如前所述，若要导出其时解密 RMS 加密的邮件您必须将搜索结果导出为单个邮件。如果将搜索结果导出到 PST 文件中，RMS 加密的邮件将保持加密。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p149">As previously explained, to decrypt RMS-encrypted messages when you export them, you have to export the search results as individual messages. If you export search results to a PST file, RMS-encrypted messages will remain encrypted.</span></span>
    
- <span data-ttu-id="15e1c-p150">内容搜索中的 RMS 解密功能不会解密邮件导出搜索结果时加密与 Office 365 邮件加密 (OME)。但是，如果您的组织中的用户发送用 OME 加密的消息，用户的 Sent 文件夹中的邮件的副本不加密可查看后和导出。但是，如果使用 OME 加密的邮件都会收到您的组织中的用户的它们不会被解密他们正在导出后。有关 OME 的详细信息，请参阅[Office 365 邮件加密](https://go.microsoft.com/fwlink/p/?linkid=844966)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p150">The RMS decryption feature in Content Search doesn't decrypt messages encrypted with Office 365 Message Encryption (OME) when you export search results. However, if a message encrypted with OME is sent by a user in your organization, the copy of the message in the user's Sent folder isn't encrypted and will be viewable after it's exported. However, if messages encrypted with OME are received by users in your organization, they won't be decrypted after they're exported. For more information about OME, see [Office 365 Message Encryption](https://go.microsoft.com/fwlink/p/?linkid=844966).</span></span>
    
- <span data-ttu-id="15e1c-p151">在**ResultsLog**报表标识要解密的邮件。此报告包含名为**解码状态**，并在此列中的**解码**值标识邮件解密。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p151">Messages that are decrypted are identified in the **ResultsLog** report. This report contains a column named **Decode Status**, and a value of **Decoded** in this column identifies the messages the were decrypted.</span></span> 
    
- <span data-ttu-id="15e1c-p152">当前，此解密功能不包括来自 SharePoint 和 OneDrive for Business 站点加密的内容。当您将其导出时，将解密仅 RMS 加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p152">Currently, this decryption capability doesn't include encrypted content from SharePoint and OneDrive for Business sites. Only RMS-encrypted email messages will be decrypted when you export them.</span></span>
    
- <span data-ttu-id="15e1c-321">如果 RMS 加密电子邮件带有附件 （如文档或另一个电子邮件） 还加密的仅顶级电子邮件将被解密。</span><span class="sxs-lookup"><span data-stu-id="15e1c-321">If an RMS-encrypted email message has an attachment (such as a document or another email message) that's also encrypted, only the top-level email message will be decrypted.</span></span>
    
- <span data-ttu-id="15e1c-p153">无法预览 RMS 加密电子邮件。若要查看加密的邮件，您必须将其导出。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p153">You can't preview an RMS-encrypted email message. To view an encrypted message, you have to export it.</span></span>
    
- <span data-ttu-id="15e1c-p154">如果您需要防止某人解密 RMS 加密的邮件，您将需要 （通过复制内置电子数据展示管理员角色组） 中创建自定义角色组，然后从自定义角色组中删除 RMS 解密管理角色。然后，添加您不想要自定义角色组的成员身份解密消息的人员。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p154">If you need to prevent someone from decrypting RMS-encrypted messages, you'll have to create a custom role group (by copying the built-in eDiscovery Manager role group) and then remove the RMS Decrypt management role from the custom role group. Then add the person who you don't want to decrypt messages as a member of the custom role group.</span></span>
  
 ### <a name="filenames-of-exported-items"></a><span data-ttu-id="15e1c-326">导出项的文件名</span><span class="sxs-lookup"><span data-stu-id="15e1c-326">Filenames of exported items</span></span>
  
- <span data-ttu-id="15e1c-p155">为电子邮件和网站导出到本地计算机的文档的完整路径名称没有 260 个字符限制 （由操作系统）。导出的项目的完整路径名称包含项目的原始位置和其中将搜索结果下载到本地计算机上的文件夹位置。例如，如果您指定若要下载到搜索结果`C:\Users\Admin\Desktop\SearchResults`，在电子数据展示导出工具，然后下载电子邮件项的完整路径名会`C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg`。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p155">There is a 260-character limit (imposed by the operating system) for the full path name for email messages and site documents exported to your local computer. The full path name for exported items includes the item's original location and the folder location on the local computer where the search results are downloaded to. For example, if you specify to download the search results to  `C:\Users\Admin\Desktop\SearchResults` in the eDiscovery Export tool, then the full pathname for a downloaded email item would be  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg`.</span></span>
    
    <span data-ttu-id="15e1c-330">如果超过 260 个字符限制，则将截断为某个项目的完整路径名称。</span><span class="sxs-lookup"><span data-stu-id="15e1c-330">If the 260-character limit is exceeded, the full path name for an item will be truncated.</span></span>
    
  - <span data-ttu-id="15e1c-331">如果超过 260 个字符的完整路径名称，将缩短文件名以获取下限制;请注意截断的文件名 （不包括的文件扩展名） 不会少于 8 个字符。</span><span class="sxs-lookup"><span data-stu-id="15e1c-331">If the full path name is longer than 260 characters, the file name will be shortened to get under the limit; note that the truncated filename (excluding the file extension) won't be less than 8 characters.</span></span>
    
  - <span data-ttu-id="15e1c-p156">如果后缩短文件名的完整路径名称仍然太长，该项目是从其当前位置移动到父文件夹。如果 pathname 仍是太长，则重复此过程： 缩短文件名，如果需要再次移动到父文件夹。重复此过程，直到的完整路径名小于 260 个字符限制值。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p156">If the full path name is still too long after shortening the file name, the item is moved from its current location to the parent folder. If the pathname is still too long, then the process is repeated: shorten the filename, and if necessary move again to the parent folder. This process is repeated until the full pathname is under the 260-character limit.</span></span>
    
  - <span data-ttu-id="15e1c-335">版本号如果截断的完整路径名称已存在，将添加到末尾的文件名;例如， `statusmessage(2).msg`。</span><span class="sxs-lookup"><span data-stu-id="15e1c-335">If a truncated full path name already exists, a version number will be added to the end of the filename; for example,  `statusmessage(2).msg`.</span></span>
    
    <span data-ttu-id="15e1c-336">若要帮助缓解此问题，请考虑下载到具有较短的路径名; 位置的搜索结果例如，将搜索结果下载到一个名为文件夹`C:\Results`会将较少的字符添加到路径名称的导出项数超过其下载到一个名为文件夹`C:\Users\Admin\Desktop\Results`。</span><span class="sxs-lookup"><span data-stu-id="15e1c-336">To help mitigate this issue, consider downloading search results to a location with a short path name; for example, downloading search results to a folder named  `C:\Results` would add fewer characters to the path names of exported items than downloading them to a folder named  `C:\Users\Admin\Desktop\Results`.</span></span>
    
- <span data-ttu-id="15e1c-p157">导出网站文档时，还有可能将修改文档的原始文件名称。专门用于将置于保持状态的业务网站已从 SharePoint 或 OneDrive 中删除的文档发生这种情况。删除位于处于保留状态的网站上的文档之后，删除的文档自动移动到演示文稿保留库的网站 （该网站被置于保持状态时创建）。当所删除的文档移到演示文稿保留库时，随机生成的并且唯一 ID 追加到文档的原始文件名。例如，如果文档的文件名为`FY2017Budget.xlsx`，该文档将更高版本中删除并移到演示文稿保留库中，将被移动到演示文稿保留库文档的文件名修改为类似于`FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`。如果演示文稿保留库中的文档匹配的内容的搜索查询，您将导出的搜索结果导出的文件将具有已修改的文件名;在此示例中，导出文档的文件名应`FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p157">When you export site documents, it's also possible that the original file name of a document will be modified. This happens specifically for documents that have been deleted from a SharePoint or OneDrive for Business site that's been placed on hold. After a document that's located on a site that's on hold is deleted, the deleted document is automatically moved to the Preservation Hold library for the site (which was created when the site was placed on hold). When the deleted document is moved to the Preservation Hold library, a randomly-generated and unique ID is appended to the original filename of the document. For example, if the filename for a document is  `FY2017Budget.xlsx` and that document is later deleted and moved to the Preservation Hold library, the filename of the document that is moved to the Preservation Hold library is modified to something like  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`. If a document in the Preservation Hold library matches the query of a Content Search and you export the results of that search, the exported file will have the modified filename; in this example, the filename of the exported document would be  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx`.</span></span>
    
    <span data-ttu-id="15e1c-p158">此外时修改文档位于置于保持状态的网站 （和网站中的文档库版本控制已启用）, 文件的副本都会自动创建演示文稿保留库中。在这种情况下，随机生成的并且唯一 ID 还追加到复制到演示文稿保留库文档的文件名。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p158">Additionally, when a document located on a site that's on hold is modified (and versioning for the document library in the site has been enabled), a copy of the file is automatically created in the Preservation Hold library. In this case, a randomly-generated and unique ID is also appended to the filename of the document that's copied to the Preservation Hold library.</span></span>
    
    <span data-ttu-id="15e1c-p159">若要防止冲突的文件名的移动或复制到演示文稿保留库的文档的文件名原因。有关网站和演示文稿保留库上发出保留的详细信息，请参阅[Overview of 就地保留在 SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p159">The reason why filenames of documents that are moved or copied to the Preservation Hold library is to prevent conflicting filenames. For more information about placing a hold on sites and the Preservation Hold library, see [Overview of in-place hold in SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95).</span></span>
    
 ### <a name="miscellaneous"></a><span data-ttu-id="15e1c-347">其他</span><span class="sxs-lookup"><span data-stu-id="15e1c-347">Miscellaneous</span></span>
  
- <span data-ttu-id="15e1c-p160">所有搜索结果，并具有同名内容的搜索文件夹中包含导出报告。已导出的电子邮件消息位于名为**Exchange**文件夹中。文档位于名为**SharePoint**文件夹中。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p160">All search results and the export reports are included in a folder that has the same name as the Content Search. The email messages that were exported are located in a folder named **Exchange**. Documents are located in a folder named **SharePoint**.</span></span> 
    
- <span data-ttu-id="15e1c-p161">当文档导出到本地计算机，将保持上 SharePoint 和 OneDrive for Business 站点的文档的文件系统元数据。意味着文档属性，如创建和上次修改日期，导出文档时不会更改。</span><span class="sxs-lookup"><span data-stu-id="15e1c-p161">The file system metadata for documents on SharePoint and OneDrive for Business sites is maintained when documents are exported to your local computer. That means document properties, such as created and last modified dates, aren't changed when documents are exported.</span></span>
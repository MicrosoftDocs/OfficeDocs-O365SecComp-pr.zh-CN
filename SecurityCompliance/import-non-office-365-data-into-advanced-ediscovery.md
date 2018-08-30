---
title: 导入非 Office 365 内容以进行高级电子数据展示分析
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 5/25/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: 如何导入到 Azure 不存储 O365 中的内容的步骤 blob，以便它可以与 AeD 分析
ms.openlocfilehash: ab6c7ac76a159603a34719aa8edb51de3a4fabbb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526068"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a><span data-ttu-id="7a2cd-103">导入非 Office 365 内容以进行高级电子数据展示分析</span><span class="sxs-lookup"><span data-stu-id="7a2cd-103">Import non-Office 365 content for Advanced eDiscovery analysis</span></span>

<span data-ttu-id="7a2cd-p101">您可能需要与 Office 365 高级电子数据展示分析的不是所有文档将都 live Office 365 中。与非 Office 365 内容导入高级电子数据展示可以上载的文档，不到案例链接、 Azure 存储 blob live （除 PST 文件） 的 Office 365 中并对其进行分析与高级电子数据展示中的功能。此过程展示如何进行分析的高级电子数据展示中引入非 Office 365 文档。</span><span class="sxs-lookup"><span data-stu-id="7a2cd-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a2cd-p102">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="7a2cd-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7a2cd-p103">您可以为 Office 365 内容购买 Office 365 高级电子数据展示数据存储加载项订阅。这是以独占方式可供使用高级电子数据展示要分析的内容。按照[购买或编辑和 Office 365 业务的加载项](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6)中的步骤和购买 Office 365 高级电子数据展示存储加载项。</span><span class="sxs-lookup"><span data-stu-id="7a2cd-p103">You can purchase an Office 365 Advanced eDiscovery data storage add-on subscription for your non-Office 365 content. This is exclusively available for content that is to be analyzed with Advanced eDiscovery. Follow the steps in [Buy or edit and add-on for Office 365 for business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) and purchase the Office 365 Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="7a2cd-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="7a2cd-112">Before you begin</span></span>

<span data-ttu-id="7a2cd-113">此过程中所述使用上载非 Office 365 功能需要您具有：</span><span class="sxs-lookup"><span data-stu-id="7a2cd-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="7a2cd-114">使用高级合规性加载项或 E5 订阅 Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="7a2cd-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="7a2cd-115">将上载其 Office 365 内容的所有管理员必须高级合规性加载项或 E5 许可证都已 E3</span><span class="sxs-lookup"><span data-stu-id="7a2cd-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="7a2cd-116">现有的电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="7a2cd-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="7a2cd-p104">用于上载到文件夹其中没有 custodian 每个文件夹和文件夹的名称位于此格式*alias@domainname*中收集的所有文件。*Alias@domainname*必须是 Office 365 用户别名和域。您可以将所有*alias@domainname*文件夹都收集到根文件夹。根文件夹只能包含*alias@domainname*文件夹、 根文件夹中必须是没有松散文件</span><span class="sxs-lookup"><span data-stu-id="7a2cd-p104">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  . The  *alias@domainname*  must be users Office 365 alias and domain. You can collect all the  *alias@domainname*  folders into a root folder. The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="7a2cd-121">电子数据展示管理器或电子数据展示管理员的帐户</span><span class="sxs-lookup"><span data-stu-id="7a2cd-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="7a2cd-122">有权访问 Office 365 内容文件夹结构的计算机上安装[Microsoft Azure 存储工具](https://aka.ms/downloadazcopy)。</span><span class="sxs-lookup"><span data-stu-id="7a2cd-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="7a2cd-123">将 Office 365 内容上载到高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="7a2cd-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="7a2cd-p105">为电子数据展示管理器或电子数据展示管理员中，打开**电子数据展示**，，然后打开的情况下，会将非 Office 365 数据上载到。如果您需要创建用例，请参阅[管理 Office 365 安全性的电子数据展示事例&amp;合规性中心](manage-ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="7a2cd-p105">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to. If you need to create a case, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="7a2cd-126">单击**切换到高级电子数据展示**</span><span class="sxs-lookup"><span data-stu-id="7a2cd-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="7a2cd-127">在**源类型**下选择**非 Office 365 数据**。</span><span class="sxs-lookup"><span data-stu-id="7a2cd-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="7a2cd-p106">单击**添加容器**。命名该容器，并添加说明。</span><span class="sxs-lookup"><span data-stu-id="7a2cd-p106">Click **Add container**. Name the container and add a description.</span></span>
    
5. <span data-ttu-id="7a2cd-130">从容器列表中选择新添加的容器和复制的 URL，容器的详细信息窗格中显示，然后关闭窗格</span><span class="sxs-lookup"><span data-stu-id="7a2cd-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="7a2cd-131">打开命令提示符以管理员身份，并将目录更改到了 AzCopy 安装的文件夹。</span><span class="sxs-lookup"><span data-stu-id="7a2cd-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="7a2cd-132">构造 AzCopy 命令行上载的文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7a2cd-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="7a2cd-p107">AzCopy /Source:"*本地计算机上的根文件夹的完整路径*"/Dest:"*容器 URL 设置，但不是包括？* "/DestSAS:"*其余部分中的容器 url？到末尾*"/ s。</span><span class="sxs-lookup"><span data-stu-id="7a2cd-p107">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*  " /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="7a2cd-135">例如，使用以下值：</span><span class="sxs-lookup"><span data-stu-id="7a2cd-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="7a2cd-136">根文件夹-C:\Collected 数据</span><span class="sxs-lookup"><span data-stu-id="7a2cd-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="7a2cd-137">容器 url- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp; sr = c&amp;si = NonOfficeData15 %7c 0&amp;签名 = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA %三维</span><span class="sxs-lookup"><span data-stu-id="7a2cd-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="7a2cd-138">将 AzCopy 命令行语法：</span><span class="sxs-lookup"><span data-stu-id="7a2cd-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="7a2cd-139">有关详细信息 Azcopy 语法请参阅[传输 Windows 上 AzCopy 数据](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="7a2cd-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="7a2cd-140">必须有一个根文件夹，每个用户和文件夹名称必须是*alias@domainname*格式。</span><span class="sxs-lookup"><span data-stu-id="7a2cd-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="7a2cd-p108">文件夹完成上载后，切换回高级电子数据展示。现已准备好高级电子数据展示中处理您上载的文件夹中的内容。选择的容器，单击过程按钮。有关高级电子数据展示的详细处理的查看，[运行进程模块并加载 Office 365 高级电子数据展示中的数据](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="7a2cd-p108">Once the folders have finished uploading, switch back to Advanced eDiscovery. The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery. Select the container and click the Process button. For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7a2cd-p109">高级电子数据展示中成功处理容器之后, 将不再能够将新内容添加到 Azure 中的 SAS 存储。如果收集其他内容，并且您希望将其添加到为高级电子数据展示分析这种情况，您必须创建一个新的**非 Office 365 数据**容器并重复此过程。</span><span class="sxs-lookup"><span data-stu-id="7a2cd-p109">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure. If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="7a2cd-147">如果容器*不处理成功由于文件夹命名问题*，并且您然后修复的问题，您将仍需要创建一个新的容器和重新连接并上载再次使用本文中的过程。</span><span class="sxs-lookup"><span data-stu-id="7a2cd-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span> 
  


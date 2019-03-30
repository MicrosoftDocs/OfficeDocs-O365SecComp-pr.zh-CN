---
title: 导入非 Office 365 内容以实现高级电子数据展示分析
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: '操作方法: 将未存储在 O365 中的内容导入到 Azure blob, 以便可以使用 AeD 对其进行分析'
ms.openlocfilehash: 7b7694754b26951aa02930fd101631ba9060bc17
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001165"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a><span data-ttu-id="9f943-103">导入非 Office 365 内容以实现高级电子数据展示分析</span><span class="sxs-lookup"><span data-stu-id="9f943-103">Import non-Office 365 content for Advanced eDiscovery analysis</span></span>

<span data-ttu-id="9f943-104">并非所有可能需要使用 office 365 进行分析的文档都将在 office 365 中实时发布。</span><span class="sxs-lookup"><span data-stu-id="9f943-104">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="9f943-105">使用高级电子数据展示中的非 Office 365 内容导入功能, 可以将不在 Office 365 中的文档 (PST 文件除外) 上传到链接的大小写的 Azure 存储 blob, 并使用高级电子数据展示分析这些文档。</span><span class="sxs-lookup"><span data-stu-id="9f943-105">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="9f943-106">此过程向您演示如何将非 Office 365 文档转换为高级电子数据展示以进行分析。</span><span class="sxs-lookup"><span data-stu-id="9f943-106">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9f943-p102">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="9f943-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9f943-109">您可以购买适用于非 Office 365 内容的 Office 365 高级电子数据展示数据存储附加订阅。</span><span class="sxs-lookup"><span data-stu-id="9f943-109">You can purchase an Office 365 Advanced eDiscovery data storage add-on subscription for your non-Office 365 content.</span></span> <span data-ttu-id="9f943-110">这仅适用于要使用高级电子数据展示进行分析的内容。</span><span class="sxs-lookup"><span data-stu-id="9f943-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="9f943-111">按照 "为[商业版购买或编辑和添加 office 365](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) " 中的步骤操作, 购买 office 365 高级电子数据展示存储加载项。</span><span class="sxs-lookup"><span data-stu-id="9f943-111">Follow the steps in [Buy or edit and add-on for Office 365 for business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) and purchase the Office 365 Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="9f943-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="9f943-112">Before you begin</span></span>

<span data-ttu-id="9f943-113">如以下过程所述, 使用 "上载非 Office 365" 功能需要具备以下条件:</span><span class="sxs-lookup"><span data-stu-id="9f943-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="9f943-114">具有高级合规性外接程序或 E5 订阅的 Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="9f943-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="9f943-115">将上载非 Office 365 内容的所有保管人必须具有具有高级合规性附加或 E5 许可证的 E3</span><span class="sxs-lookup"><span data-stu-id="9f943-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="9f943-116">现有电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="9f943-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="9f943-117">将用于上载的所有文件都收集到每个保管人都有一个文件夹的文件夹中, 文件夹的名称是格式*别名 @ domainname* 。</span><span class="sxs-lookup"><span data-stu-id="9f943-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="9f943-118">*别名 @ 域名*必须是用户 Office 365 别名和域。</span><span class="sxs-lookup"><span data-stu-id="9f943-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="9f943-119">您可以将所有*别名 @ domainname*文件夹收集到一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9f943-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="9f943-120">根文件夹只能包含*别名 @ domainname*文件夹, 根文件夹中不能有松散文件</span><span class="sxs-lookup"><span data-stu-id="9f943-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="9f943-121">既可以是电子数据展示管理器, 也可以是电子数据展示管理员的帐户</span><span class="sxs-lookup"><span data-stu-id="9f943-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="9f943-122">在有权访问非 Office 365 内容文件夹结构的计算机上安装了[Microsoft Azure 存储工具](https://aka.ms/downloadazcopy)。</span><span class="sxs-lookup"><span data-stu-id="9f943-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="9f943-123">将非 Office 365 内容上载到高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="9f943-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="9f943-124">作为电子数据展示管理器或电子数据展示管理员, 打开**电子数据展示**, 并打开将向其上载非 Office 365 数据的大小写。</span><span class="sxs-lookup"><span data-stu-id="9f943-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="9f943-125">如果您需要创建一个事例, 请参阅[在 Office 365 安全&amp;合规中心中管理电子数据展示事例](manage-ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="9f943-125">If you need to create a case, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="9f943-126">单击 "**切换到高级电子数据展示**"</span><span class="sxs-lookup"><span data-stu-id="9f943-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="9f943-127">在 "**源类型**" 下, 选择**非 Office 365 数据**。</span><span class="sxs-lookup"><span data-stu-id="9f943-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="9f943-128">单击 "**添加容器**"。</span><span class="sxs-lookup"><span data-stu-id="9f943-128">Click **Add container**.</span></span> <span data-ttu-id="9f943-129">命名容器并添加说明。</span><span class="sxs-lookup"><span data-stu-id="9f943-129">Name the container and add a description.</span></span>
    
5. <span data-ttu-id="9f943-130">从容器列表中选择新添加的容器, 并复制容器详细信息窗格中显示的 URL, 然后关闭窗格</span><span class="sxs-lookup"><span data-stu-id="9f943-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="9f943-131">以管理员身份打开命令提示符, 并将目录更改为您在其中安装了 AzCopy 的文件夹。。</span><span class="sxs-lookup"><span data-stu-id="9f943-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="9f943-132">构造 AzCopy 命令行以上载如下所示的文件:</span><span class="sxs-lookup"><span data-stu-id="9f943-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="9f943-133">AzCopy/source: "*本地计算机上的根文件夹的完整路径*"/Dest: "上*的容器 URL, 但不包括？*</span><span class="sxs-lookup"><span data-stu-id="9f943-133">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*</span></span>  <span data-ttu-id="9f943-134">"/DestSAS:"*容器 url 的剩余部分 (来自？)到结尾*"/S。</span><span class="sxs-lookup"><span data-stu-id="9f943-134">" /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="9f943-135">例如, 使用以下值:</span><span class="sxs-lookup"><span data-stu-id="9f943-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="9f943-136">根文件夹-C:\Collected 数据</span><span class="sxs-lookup"><span data-stu-id="9f943-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="9f943-137">容器 url- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp; sr = c&amp;si = NonOfficeData15% 7C0&amp;sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3d</span><span class="sxs-lookup"><span data-stu-id="9f943-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="9f943-138">AzCopy 命令行语法为:</span><span class="sxs-lookup"><span data-stu-id="9f943-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="9f943-139">有关 Azcopy 语法的详细信息, 请参阅[使用 Windows 上的 Azcopy 传输数据](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="9f943-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="9f943-140">每个用户必须有一个根文件夹, 并且文件夹名称必须采用*别名 @ domainname*格式。</span><span class="sxs-lookup"><span data-stu-id="9f943-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="9f943-141">文件夹完成上载后, 切换回高级电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="9f943-141">Once the folders have finished uploading, switch back to Advanced eDiscovery.</span></span> <span data-ttu-id="9f943-142">您上载的文件夹中的内容现已准备就绪, 可以在高级电子数据展示中进行处理。</span><span class="sxs-lookup"><span data-stu-id="9f943-142">The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="9f943-143">选择容器, 然后单击 "处理" 按钮。</span><span class="sxs-lookup"><span data-stu-id="9f943-143">Select the container and click the Process button.</span></span> <span data-ttu-id="9f943-144">有关高级电子数据展示处理的更多详细信息, 请参阅在[Office 365 高级电子数据展示中运行 Process module 和 load data](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="9f943-144">For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9f943-145">在高级电子数据展示中成功处理容器后, 您将无法再将新内容添加到 Azure 中的 SAS 存储。</span><span class="sxs-lookup"><span data-stu-id="9f943-145">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="9f943-146">如果要收集其他内容, 并且想要将其添加到高级电子数据展示分析的事例中, 则必须创建一个新的**非 Office 365 数据**容器, 并重复此过程。</span><span class="sxs-lookup"><span data-stu-id="9f943-146">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="9f943-147">如果*由于文件夹命名问题而导致容器未成功处理*, 并且您随后解决了这些问题, 您仍需使用本文中的过程创建一个新的容器, 并重新连接和上传。</span><span class="sxs-lookup"><span data-stu-id="9f943-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span> 
  


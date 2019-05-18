---
title: 将非 Office 365 数据加载到证据中
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 3258ff4d5bf079a73837038135c3a1c69eb2fe26
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150804"
---
# <a name="load-non-office-365-data-into-evidence"></a><span data-ttu-id="2b0f8-102">将非 Office 365 数据加载到证据中</span><span class="sxs-lookup"><span data-stu-id="2b0f8-102">Load non-Office 365 data into evidence</span></span>

<span data-ttu-id="2b0f8-103">并非所有可能需要使用 Office 365 进行分析的文档都将在 Office 365 中实时发布。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="2b0f8-104">通过高级电子数据展示中的非 Office 365 内容导入功能, 可以将不在 Office 365 中的文档上传到工作集, 以便使用高级电子数据展示对其进行分析。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="2b0f8-105">此过程向您演示如何将非 Office 365 文档转换为高级电子数据展示以进行分析。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="2b0f8-106">高级电子数据展示需要 Office 365 E3 和您的组织的高级合规性加载项或 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="2b0f8-107">如果你没有该计划, 并且想要尝试高级电子数据展示, 可以注册 Office 365 企业版 E5 的试用版。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2b0f8-108">开始之前</span><span class="sxs-lookup"><span data-stu-id="2b0f8-108">Before you begin</span></span>
<span data-ttu-id="2b0f8-109">如以下过程所述, 使用 "上载非 Office 365" 功能需要具备以下条件:</span><span class="sxs-lookup"><span data-stu-id="2b0f8-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="2b0f8-110">具有高级合规性外接程序或 E5 订阅的 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="2b0f8-111">将上载其非 Office 365 内容的所有保管人必须具有具有高级合规性附加或 E5 许可证的 E3。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="2b0f8-112">现有电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="2b0f8-113">将用于上载的所有文件都收集到每个保管人都有一个文件夹的文件夹中, 文件夹的名称是格式*别名 @ domainname* 。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-113">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* .</span></span> <span data-ttu-id="2b0f8-114">*别名 @ 域名*必须是用户 Office 365 别名和域。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-114">The *alias@domainname* must be users Office 365 alias and domain.</span></span> <span data-ttu-id="2b0f8-115">您可以将所有*别名 @ domainname*文件夹收集到一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-115">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="2b0f8-116">根文件夹只能包含*别名 @ domainname*文件夹, 根文件夹中必须没有松散文件。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-116">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="2b0f8-117">一种帐户, 既可以是电子数据展示管理器, 也可以是安装在可访问非 Office 365 内容文件夹结构的计算机上的电子数据展示管理员 Microsoft Azure 存储工具。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="2b0f8-118">安装 AzCopy, 您可以从以下位置执行此操作:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="2b0f8-118">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="2b0f8-119">将非 Office 365 内容上载到高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="2b0f8-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="2b0f8-120">作为电子数据展示管理器或电子数据展示管理员, 打开高级电子数据展示, 然后将非 Office 365 数据上载到的情况。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-120">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="2b0f8-121">单击 "**工作集**" 选项卡, 然后选择要将非 Office 365 数据加载到的工作集。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-121">Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="2b0f8-122">如果尚未创建工作集, 现在可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-122">If you have not already created a working set, you can do so now.</span></span>  <span data-ttu-id="2b0f8-123">最后, 单击 "**管理工作原理集**", 然后查看 "非 Office 365 数据" 部分中的 "**上载**"</span><span class="sxs-lookup"><span data-stu-id="2b0f8-123">Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="2b0f8-124">单击 "**上载文件**" 按钮以启动 "非 Office 365 数据导入向导"。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![上传文件](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="2b0f8-126">向导中的第一步是为要上载的文件准备一个安全的 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-126">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="2b0f8-127">准备好后 compelted 后, 单击 "**下一步: 上传文件**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-127">Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![非 Office 365 导入-准备](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="2b0f8-129">在 "**上载文件**" 步骤中, 指定**文件位置的路径**, 这是您计划导入的非 Office 365 数据所在的位置。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-129">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="2b0f8-130">设置正确的位置可确保正确更新 AzCopy 命令。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-130">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="2b0f8-131">如果尚未安装 AzCopy, 可以从以下位置执行此操作:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="2b0f8-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="2b0f8-132">通过单击 "**复制到剪贴板**" 链接复制预定义命令。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-132">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="2b0f8-133">启动 windows 命令提示符, 粘贴命令并按 enter。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-133">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="2b0f8-134">将在下一步中将文件上载到安全 Azure blob 存储。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-134">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![非 Office 365 导入-上传文件](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 导入 AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="2b0f8-137">最后, 返回到安全 & 合规性, 然后单击 "**下一步: 处理文件**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-137">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="2b0f8-138">这将启动已上载文件的处理、文本提取和索引。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-138">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="2b0f8-139">您可以在此处或在 "**作业**" 选项卡中跟踪处理进度。 完成后, 新文件将在工作集中可用。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-139">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.</span></span>  <span data-ttu-id="2b0f8-140">完成处理后, 可以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="2b0f8-140">Once processing is complete, you can dismiss the wizard.</span></span>

![非 Office 365 导入-处理文件](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)


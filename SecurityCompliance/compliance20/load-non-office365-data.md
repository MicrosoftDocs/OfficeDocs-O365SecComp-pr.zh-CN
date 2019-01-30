---
title: 将非 Office 365 数据加载到工作集
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
description: ''
ms.openlocfilehash: 427b4c8c9dfffe351827a6869ae26a5356d646d8
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607460"
---
# <a name="load-non-office-365-data-into-a-working-set"></a><span data-ttu-id="d0935-102">将非 Office 365 数据加载到工作集</span><span class="sxs-lookup"><span data-stu-id="d0935-102">Load non-Office 365 data into a working set</span></span>

<span data-ttu-id="d0935-p101">您可能需要与 Office 365 高级电子数据展示分析的不是所有文档将都 live Office 365 中。与非 Office 365 内容导入高级电子数据展示可以上载不 live Office 365 中插入工作集以便与高级电子数据展示分析的文档中的功能。此过程展示如何进行分析的高级电子数据展示中引入非 Office 365 文档。</span><span class="sxs-lookup"><span data-stu-id="d0935-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="d0935-p102">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以注册 Office 365 企业版 E5 试用版。</span><span class="sxs-lookup"><span data-stu-id="d0935-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d0935-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="d0935-108">Before you begin</span></span>
<span data-ttu-id="d0935-109">此过程中所述使用上载非 Office 365 功能需要您具有：</span><span class="sxs-lookup"><span data-stu-id="d0935-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
* <span data-ttu-id="d0935-110">使用高级合规性加载项或 E5 订阅 Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="d0935-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
* <span data-ttu-id="d0935-111">将上载其 Office 365 内容的所有管理员必须高级合规性加载项或 E5 许可证都已 E3</span><span class="sxs-lookup"><span data-stu-id="d0935-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
* <span data-ttu-id="d0935-112">现有的电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="d0935-112">An existing eDiscovery case</span></span>
* <span data-ttu-id="d0935-p103">用于上载到文件夹其中没有 custodian 每个文件夹和文件夹的名称位于此格式*alias@domainname*中收集的所有文件。*Alias@domainname*必须是 Office 365 用户别名和域。您可以将所有*alias@domainname*文件夹都收集到根文件夹。根文件夹只能包含*alias@domainname*文件夹、 根文件夹中必须是没有松散文件</span><span class="sxs-lookup"><span data-stu-id="d0935-p103">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* . The *alias@domainname* must be users Office 365 alias and domain. You can collect all the *alias@domainname* folders into a root folder. The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder</span></span>
* <span data-ttu-id="d0935-117">电子数据展示中管理器，也有权访问 Office 365 内容文件夹结构的计算机上安装的电子数据展示管理员 Microsoft Azure 存储工具的帐户。</span><span class="sxs-lookup"><span data-stu-id="d0935-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>
* <span data-ttu-id="d0935-118">安装 AzCopy，可以执行此操作从此处：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="d0935-118">Install AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="d0935-119">将 Office 365 内容上载到高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="d0935-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>
1. <span data-ttu-id="d0935-p104">为电子数据展示管理器或电子数据展示管理员中，打开高级电子数据展示，然后用例的非 Office 365 数据将上载到。 单击**处理设置**选项卡，然后选择您希望对非 Office 365 将数据加载的工作集。 如果尚未创建工作集，您可以现在完成操作。 最后，单击**管理工作原理设置**，则非 Office 365 数据部分中的**视图上载**</span><span class="sxs-lookup"><span data-stu-id="d0935-p104">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.  Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.  If you have not already created a working set, you can do so now.  Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="d0935-124">单击**上载文件**按钮以启动非 Office 365 数据导入向导。</span><span class="sxs-lookup"><span data-stu-id="d0935-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![上载文件](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="d0935-p105">在向导的第一步只需准备安全 Azure blob 要上载的文件。 Compelted 准备后，单击**下一步： 将文件上载**按钮。</span><span class="sxs-lookup"><span data-stu-id="d0935-p105">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.  Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![非 Office 365 导入-准备](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="d0935-p106">在**上载文件**步骤中，指定**文件位置的路径**，这是您导入计划的非 Office 365 数据所在的位置。 设置正确的位置可确保正确更新命令 AzCopy。</span><span class="sxs-lookup"><span data-stu-id="d0935-p106">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.  Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="d0935-131">如果尚未安装 AzCopy，您可以从此处执行此操作：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="d0935-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="d0935-p107">通过单击**复制到剪贴板**链接复制的预定义的命令。启动 windows 命令提示符处，粘贴命令并按 enter。 文件将上载到安全的 Azure blob 存储的下一步。</span><span class="sxs-lookup"><span data-stu-id="d0935-p107">Copy the predefined command by clicking the **Copy to clipboard** link. Start a windows command prompt, paste the command and press enter.  The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![非 Office 365 导入-上载文件](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 导入-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="d0935-p108">最后，将返回到安全 & 合规性，并单击**下一步： 处理文件**按钮。 这将启动处理，文本提取和上载文件的索引。 您可以跟踪进度的处理此处或在**作业**选项卡。 完成后，新文件中将提供工作集。 处理完成后，您可以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="d0935-p108">Finally, return back to the Security & Compliance and click the **Next: Process files** button.  This will initiate processing, text extraction and indexing of the uploaded files.  You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.  Once processing is complete, you can dismiss the wizard.</span></span>

![非 Office 365 导入-处理文件](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)


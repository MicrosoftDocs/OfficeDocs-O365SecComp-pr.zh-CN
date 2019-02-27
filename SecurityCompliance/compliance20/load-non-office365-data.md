---
title: 将非 Office 365 数据加载到工作集
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: b177fc292c748f21907621196dc28d6b8fe17959
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296785"
---
# <a name="load-non-office-365-data-into-a-working-set"></a><span data-ttu-id="c800d-102">将非 Office 365 数据加载到工作集</span><span class="sxs-lookup"><span data-stu-id="c800d-102">Load non-Office 365 data into a working set</span></span>

<span data-ttu-id="c800d-p101">并非所有可能需要使用 office 365 进行分析的文档都将在 office 365 中实时发布。通过高级电子数据展示中的非 Office 365 内容导入功能, 可以将不在 Office 365 中的文档上传到工作集, 以便使用高级电子数据展示对其进行分析。此过程向您演示如何将非 Office 365 文档转换为高级电子数据展示以进行分析。</span><span class="sxs-lookup"><span data-stu-id="c800d-p101">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365. With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a working set so it is analyzed with Advanced eDiscovery. This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="c800d-p102">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以注册 Office 365 企业版 E5 试用版。</span><span class="sxs-lookup"><span data-stu-id="c800d-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c800d-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="c800d-108">Before you begin</span></span>
<span data-ttu-id="c800d-109">如以下过程所述, 使用 "上载非 Office 365" 功能需要具备以下条件:</span><span class="sxs-lookup"><span data-stu-id="c800d-109">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="c800d-110">具有高级合规性外接程序或 E5 订阅的 Office 365 E3。</span><span class="sxs-lookup"><span data-stu-id="c800d-110">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>

- <span data-ttu-id="c800d-111">将上载其非 Office 365 内容的所有保管人必须具有具有高级合规性附加或 E5 许可证的 E3。</span><span class="sxs-lookup"><span data-stu-id="c800d-111">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>

- <span data-ttu-id="c800d-112">现有电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="c800d-112">An existing eDiscovery case.</span></span>

- <span data-ttu-id="c800d-p103">将用于上载的所有文件都收集到每个保管人都有一个文件夹的文件夹中, 文件夹的名称是格式*别名 @ domainname* 。*别名 @ 域名*必须是用户 Office 365 别名和域。您可以将所有*别名 @ domainname*文件夹收集到一个根文件夹中。根文件夹只能包含*别名 @ domainname*文件夹, 根文件夹中必须没有松散文件。</span><span class="sxs-lookup"><span data-stu-id="c800d-p103">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname* . The *alias@domainname* must be users Office 365 alias and domain. You can collect all the *alias@domainname* folders into a root folder. The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="c800d-117">一种帐户, 既可以是电子数据展示管理器, 也可以是安装在可访问非 Office 365 内容文件夹结构的计算机上的电子数据展示管理员 Microsoft Azure 存储工具。</span><span class="sxs-lookup"><span data-stu-id="c800d-117">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="c800d-118">安装 AzCopy, 您可以从以下位置执行此操作:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="c800d-118">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="c800d-119">将非 Office 365 内容上载到高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="c800d-119">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="c800d-p104">作为电子数据展示管理器或电子数据展示管理员, 打开高级电子数据展示, 然后将非 Office 365 数据上载到的情况。 单击 "**工作集**" 选项卡, 然后选择要将非 Office 365 数据加载到的工作集。 如果尚未创建工作集, 现在可以执行此操作。 最后, 单击 "**管理工作原理集**", 然后查看 "非 Office 365 数据" 部分中的 "**上载**"</span><span class="sxs-lookup"><span data-stu-id="c800d-p104">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.  Click the **Working sets** tab, then select the working set you wish to load the Non-Office 365 data to.  If you have not already created a working set, you can do so now.  Finally, click **Manage workings set** then **View uploads** in the Non-Office 365 data section</span></span>

2. <span data-ttu-id="c800d-124">单击 "**上载文件**" 按钮以启动 "非 Office 365 数据导入向导"。</span><span class="sxs-lookup"><span data-stu-id="c800d-124">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

![上传文件](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="c800d-p105">向导中的第一步是为要上载的文件准备一个安全的 Azure blob。 准备好后 compelted 后, 单击 "**下一步: 上传文件**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="c800d-p105">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.  Once preparation is compelted, click the **Next: Upload files** button.</span></span>

![非 Office 365 导入-准备](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="c800d-p106">在 "**上载文件**" 步骤中, 指定**文件位置的路径**, 这是您计划导入的非 Office 365 数据所在的位置。 设置正确的位置可确保正确更新 AzCopy 命令。</span><span class="sxs-lookup"><span data-stu-id="c800d-p106">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.  Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="c800d-131">如果尚未安装 AzCopy, 可以从以下位置执行此操作:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="c800d-131">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="c800d-p107">通过单击 "**复制到剪贴板**" 链接复制预定义命令。启动 windows 命令提示符, 粘贴命令并按 enter。 将在下一步中将文件上载到安全 Azure blob 存储。</span><span class="sxs-lookup"><span data-stu-id="c800d-p107">Copy the predefined command by clicking the **Copy to clipboard** link. Start a windows command prompt, paste the command and press enter.  The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![非 Office 365 导入-上传文件](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 导入 AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="c800d-p108">最后, 返回到安全 & 合规性, 然后单击 "**下一步: 处理文件**" 按钮。 这将启动已上载文件的处理、文本提取和索引。 您可以在此处或在 "**作业**" 选项卡中跟踪处理进度。 完成后, 新文件将在工作集中可用。 完成处理后, 可以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="c800d-p108">Finally, return back to the Security & Compliance and click the **Next: Process files** button.  This will initiate processing, text extraction and indexing of the uploaded files.  You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the working set.  Once processing is complete, you can dismiss the wizard.</span></span>

![非 Office 365 导入-处理文件](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)


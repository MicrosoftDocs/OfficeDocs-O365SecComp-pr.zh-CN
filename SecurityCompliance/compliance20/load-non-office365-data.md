---
title: 将非 Office 365 数据加载到审阅集
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
ms.openlocfilehash: 86d858994f95176ea4d415405c4043f7e7c5308e
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155004"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="27fe5-102">将非 Office 365 数据加载到审阅集</span><span class="sxs-lookup"><span data-stu-id="27fe5-102">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="27fe5-103">并非所有可能需要使用 Office 365 进行分析的文档都将在 Office 365 中实时发布。</span><span class="sxs-lookup"><span data-stu-id="27fe5-103">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="27fe5-104">通过高级电子数据展示中的非 Office 365 内容导入功能, 可以将不在 Office 365 中的文档上传到审阅集, 以便使用高级电子数据展示对其进行分析。</span><span class="sxs-lookup"><span data-stu-id="27fe5-104">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 into a review set so it is analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="27fe5-105">此过程向您演示如何将非 Office 365 文档转换为高级电子数据展示以进行分析。</span><span class="sxs-lookup"><span data-stu-id="27fe5-105">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="27fe5-106">高级电子数据展示需要 Office 365 E3 和您的组织的高级合规性加载项或 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="27fe5-106">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="27fe5-107">如果你没有该计划, 并且想要尝试高级电子数据展示, 可以注册 Office 365 企业版 E5 的试用版。</span><span class="sxs-lookup"><span data-stu-id="27fe5-107">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="27fe5-108">开始之前</span><span class="sxs-lookup"><span data-stu-id="27fe5-108">Before you begin</span></span>

<span data-ttu-id="27fe5-109">如本文中所述, 使用 "上载非 Office 365" 功能要求您具备以下各项:</span><span class="sxs-lookup"><span data-stu-id="27fe5-109">Using the upload Non-Office 365 feature as described in this article requires that you have the following:</span></span>

- <span data-ttu-id="27fe5-110">Office 365 或 Microsoft 365 E5 订阅或具有高级合规性附加订阅的 E3 订阅。</span><span class="sxs-lookup"><span data-stu-id="27fe5-110">An Office 365 or Microsoft 365 E5 subscription or an E3 subscription with the Advanced Compliance add-on subscription.</span></span>

- <span data-ttu-id="27fe5-111">将上载其非 Office 365 内容的所有保管人必须具有具有高级合规性附加许可证的 E3 许可证或拥有 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="27fe5-111">All custodians whose non-Office 365 content will be uploaded must have E3 license with an Advanced Compliance add-on license or have an E5 license.</span></span>

- <span data-ttu-id="27fe5-112">现有的高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="27fe5-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="27fe5-113">必须先将保管人添加到事例, 然后才能上载与它们相关联的非 Office 365 数据。</span><span class="sxs-lookup"><span data-stu-id="27fe5-113">Custodians must be added to the case before you upload the non-Office 365 data that's associated to them.</span></span>

- <span data-ttu-id="27fe5-114">将上载的所有文件都必须位于文件夹中, 其中每个文件夹都与特定的保管人相关联。</span><span class="sxs-lookup"><span data-stu-id="27fe5-114">All files that will be uploaded must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="27fe5-115">这些文件夹的名称必须使用以下命名格式: *alias @ domainname*。</span><span class="sxs-lookup"><span data-stu-id="27fe5-115">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="27fe5-116">*别名 @ domainname*必须是用户的 Office 365 别名和域。</span><span class="sxs-lookup"><span data-stu-id="27fe5-116">The *alias@domainname* must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="27fe5-117">您可以将所有*别名 @ domainname*文件夹收集到一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="27fe5-117">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="27fe5-118">根文件夹仅可包含*别名 @ domainname*文件夹;根文件夹中不允许出现松散文件。</span><span class="sxs-lookup"><span data-stu-id="27fe5-118">The root folder can only contain the *alias@domainname* folders; loose files aren't allowed in the root folder.</span></span>

   <span data-ttu-id="27fe5-119">例如, 要上载的非 Office 365 数据的文件夹结构将类似于以下内容:</span><span class="sxs-lookup"><span data-stu-id="27fe5-119">For example, the folder structure for the non-Office 365 data that you want to upload would be similar to the following:</span></span>

   - <span data-ttu-id="27fe5-120">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="27fe5-120">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="27fe5-121">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="27fe5-121">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="27fe5-122">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="27fe5-122">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="27fe5-123">其中, abraham.mcmahon@contoso.com、jewell.gordon@contoso.com 和 staci.gonzalez@contoso.com 是在这种情况下的保管人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="27fe5-123">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![非 Office 365 数据上传文件夹结构](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="27fe5-125">既可以是电子数据展示管理器, 也可以是电子数据展示管理员的帐户</span><span class="sxs-lookup"><span data-stu-id="27fe5-125">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>

- <span data-ttu-id="27fe5-126">在有权访问非 Office 365 内容文件夹结构的计算机上安装了 Microsoft Azure 存储工具。</span><span class="sxs-lookup"><span data-stu-id="27fe5-126">Microsoft Azure Storage Tools installed on a computer that has access to the non-Office 365 content folder structure.</span></span>

- <span data-ttu-id="27fe5-127">安装 AzCopy, 您可以从以下位置执行此操作:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="27fe5-127">Install AzCopy, which you can do from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="27fe5-128">将非 Office 365 内容上载到高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="27fe5-128">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="27fe5-129">作为电子数据展示管理器或电子数据展示管理员, 打开高级电子数据展示, 然后将非 Office 365 数据上载到的情况。</span><span class="sxs-lookup"><span data-stu-id="27fe5-129">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  <span data-ttu-id="27fe5-130">单击 "**查看集**" 选项卡, 然后选择要将非 Office 365 数据加载到的审阅集。</span><span class="sxs-lookup"><span data-stu-id="27fe5-130">Click the **review sets** tab, then select the review set you wish to load the Non-Office 365 data to.</span></span>  <span data-ttu-id="27fe5-131">如果尚未创建审阅集, 现在可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="27fe5-131">If you have not already created a review set, you can do so now.</span></span>  <span data-ttu-id="27fe5-132">最后, 单击 "**管理审阅集**", 然后在 "\* \* 非 Office 365 数据" 磁贴中单击 "**查看上载**"。</span><span class="sxs-lookup"><span data-stu-id="27fe5-132">Finally, click **Manage review set** and then click **View uploads** in the \*\*Non-Office 365 data tile.</span></span>

2. <span data-ttu-id="27fe5-133">单击 "**上载文件**" 按钮以启动 "非 Office 365 数据导入向导"。</span><span class="sxs-lookup"><span data-stu-id="27fe5-133">Click the **Upload files** button to start the Non-Office 365 data import wizard.</span></span>

   ![上传文件](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="27fe5-135">向导中的第一步是为要上载的文件准备一个安全的 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="27fe5-135">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="27fe5-136">准备完成后, 单击 "**下一步: 上传文件**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="27fe5-136">Once preparation is completed, click the **Next: Upload files** button.</span></span>

   ![非 Office 365 导入-准备](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="27fe5-138">在 "**上载文件**" 步骤中, 指定**文件位置的路径**, 这是您计划导入的非 Office 365 数据所在的位置。</span><span class="sxs-lookup"><span data-stu-id="27fe5-138">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Office 365 data you plan on importing is located.</span></span>  <span data-ttu-id="27fe5-139">设置正确的位置可确保正确更新 AzCopy 命令。</span><span class="sxs-lookup"><span data-stu-id="27fe5-139">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

   > [!NOTE]
   > <span data-ttu-id="27fe5-140">如果尚未安装 AzCopy, 可以从以下位置执行此操作:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="27fe5-140">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="27fe5-141">通过单击 "**复制到剪贴板**" 链接复制预定义命令。</span><span class="sxs-lookup"><span data-stu-id="27fe5-141">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="27fe5-142">启动 windows 命令提示符, 粘贴命令并按 enter。</span><span class="sxs-lookup"><span data-stu-id="27fe5-142">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="27fe5-143">将在下一步中将文件上载到安全 Azure blob 存储。</span><span class="sxs-lookup"><span data-stu-id="27fe5-143">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

   ![非 Office 365 导入-上传文件](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   ![非 Office 365 导入 AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="27fe5-146">如果提供的 AzCopy 命令失败, 请参阅[高级电子数据展示中的故障排除 AzCopy](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="27fe5-146">If the supplied AzCopy command fails, refer to [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md)</span></span>

6. <span data-ttu-id="27fe5-147">最后, 返回到安全 & 合规性, 然后单击 "**下一步: 处理文件**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="27fe5-147">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="27fe5-148">这将启动已上载文件的处理、文本提取和索引。</span><span class="sxs-lookup"><span data-stu-id="27fe5-148">This will initiate processing, text extraction and indexing of the uploaded files.</span></span>  <span data-ttu-id="27fe5-149">您可以在此处或在 "**作业**" 选项卡中跟踪处理进度。 完成后, 新文件将在审阅集中可用。</span><span class="sxs-lookup"><span data-stu-id="27fe5-149">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files will be available in the review set.</span></span>  <span data-ttu-id="27fe5-150">完成处理后, 可以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="27fe5-150">Once processing is complete, you can dismiss the wizard.</span></span>

   ![非 Office 365 导入-处理文件](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)


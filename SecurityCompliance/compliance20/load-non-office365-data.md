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
description: 将非 Office 365 数据导入到高级电子数据展示事例中的审阅集。
ms.openlocfilehash: d7609c774e7c8a42e24b22a87fbed271a12a97f5
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048104"
---
# <a name="load-non-office-365-data-into-a-review-set"></a><span data-ttu-id="c4d41-103">将非 Office 365 数据加载到审阅集</span><span class="sxs-lookup"><span data-stu-id="c4d41-103">Load non-Office 365 data into a review set</span></span>

<span data-ttu-id="c4d41-104">并非所有需要在高级电子数据展示中进行分析的文档都位于 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="c4d41-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Office 365.</span></span> <span data-ttu-id="c4d41-105">使用高级电子数据展示中的非 Office 365 数据导入功能, 可以将不在 Office 365 中的文档上传到审阅集。</span><span class="sxs-lookup"><span data-stu-id="c4d41-105">With the non-Office 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Office 365 to a review set.</span></span> <span data-ttu-id="c4d41-106">本文介绍如何将非 Office 365 文档转换为高级电子数据展示以进行分析。</span><span class="sxs-lookup"><span data-stu-id="c4d41-106">This article shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>

>[!Note]
><span data-ttu-id="c4d41-107">高级电子数据展示需要针对你的组织的 Microsoft 365 或 Office 365 E5 订阅或具有高级合规性附加订阅的 E3 订阅。</span><span class="sxs-lookup"><span data-stu-id="c4d41-107">Advanced eDiscovery requires an Microsoft 365 or Office 365 E5 subscription for your organization or an E3 subscription with the Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="c4d41-108">如果你没有该计划, 并且想要尝试高级电子数据展示, 可以注册 Office 365 企业版 E5 的试用版。</span><span class="sxs-lookup"><span data-stu-id="c4d41-108">If you don't have that plan and want to try Advanced eDiscovery, you can sign up for a trial of Office 365 Enterprise E5.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c4d41-109">开始之前</span><span class="sxs-lookup"><span data-stu-id="c4d41-109">Before you begin</span></span>

<span data-ttu-id="c4d41-110">若要使用本文中介绍的 "上载非 Office 365" 功能, 您需要具备以下条件:</span><span class="sxs-lookup"><span data-stu-id="c4d41-110">Using the upload non-Office 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="c4d41-111">要将非 Office 365 内容与之关联的所有保管人都必须分配有一个 E5 许可证, 或具有高级合规性附加许可证的 E3 许可证。</span><span class="sxs-lookup"><span data-stu-id="c4d41-111">All custodians that you want to associate non-Office 365 content to must be assigned an E5 license, or an E3 license with an Advanced Compliance add-on license.</span></span>

- <span data-ttu-id="c4d41-112">现有的高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="c4d41-112">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="c4d41-113">必须先将保管人添加到事例, 然后才能将非 Office 365 数据上载到其中并将其与之关联。</span><span class="sxs-lookup"><span data-stu-id="c4d41-113">Custodians must be added to the case before you can upload and associate the non-Office 365 data to them.</span></span>

- <span data-ttu-id="c4d41-114">非 Office 365 数据必须是高级电子数据展示支持的文件类型。</span><span class="sxs-lookup"><span data-stu-id="c4d41-114">Non-Office 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="c4d41-115">有关详细信息, 请参阅[高级电子数据展示中支持的文件类型](supported-filetypes-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="c4d41-115">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="c4d41-116">上载到审阅集的所有文件都必须位于文件夹中, 其中每个文件夹都与特定的保管人相关联。</span><span class="sxs-lookup"><span data-stu-id="c4d41-116">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="c4d41-117">这些文件夹的名称必须使用以下命名格式: *alias @ domainname*。</span><span class="sxs-lookup"><span data-stu-id="c4d41-117">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="c4d41-118">别名 @ domainname 必须是用户的 Office 365 别名和域。</span><span class="sxs-lookup"><span data-stu-id="c4d41-118">The alias@domainname must be the user's Office 365 alias and domain.</span></span> <span data-ttu-id="c4d41-119">您可以收集根文件夹中的所有别名 @ domainname 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4d41-119">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="c4d41-120">根文件夹仅可包含别名 @ domainname 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c4d41-120">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="c4d41-121">不支持根文件夹中的松散文件。</span><span class="sxs-lookup"><span data-stu-id="c4d41-121">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="c4d41-122">您要上载的非 Office 365 数据的文件夹结构与以下示例类似:</span><span class="sxs-lookup"><span data-stu-id="c4d41-122">The folder structure for the non-Office 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="c4d41-123">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4d41-123">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="c4d41-124">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4d41-124">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="c4d41-125">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c4d41-125">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="c4d41-126">其中, abraham.mcmahon@contoso.com、jewell.gordon@contoso.com 和 staci.gonzalez@contoso.com 是在这种情况下的保管人的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="c4d41-126">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![非 Office 365 数据上传文件夹结构](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="c4d41-128">分配给电子数据展示管理器角色组 (并作为电子数据展示管理员添加) 的帐户。</span><span class="sxs-lookup"><span data-stu-id="c4d41-128">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="c4d41-129">在具有对非 Office 365 内容文件夹结构的访问权限的计算机上安装了 AzCopy (v 8.1) 工具。</span><span class="sxs-lookup"><span data-stu-id="c4d41-129">The AzCopy v8.1 tool installed on a computer that has access to the non-Office 365 content folder structure.</span></span> <span data-ttu-id="c4d41-130">若要安装 AzCopy, 请参阅[在 Windows 上使用 AzCopy 中的传输数据](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="c4d41-130">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="c4d41-131">请务必将 AzCopy 安装在默认位置, 即 **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**。</span><span class="sxs-lookup"><span data-stu-id="c4d41-131">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="c4d41-132">必须使用 AzCopy 中的 "8.1"。</span><span class="sxs-lookup"><span data-stu-id="c4d41-132">You must use AzCopy v8.1.</span></span> <span data-ttu-id="c4d41-133">其他版本的 AzCopy 在高级电子数据展示中加载非 Office 365 数据时可能不起作用。</span><span class="sxs-lookup"><span data-stu-id="c4d41-133">Other versions of AzCopy may not work when loading non-Office 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="c4d41-134">将非 Office 365 内容上载到高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="c4d41-134">Upload non-Office 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="c4d41-135">作为电子数据展示管理器或电子数据展示管理员, 打开高级电子数据展示, 然后将非 Office 365 数据上载到的情况。</span><span class="sxs-lookup"><span data-stu-id="c4d41-135">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, then the case that the non-Office 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="c4d41-136">单击 "**查看集**", 然后选择要将非 Office 365 数据上传到的审阅集。</span><span class="sxs-lookup"><span data-stu-id="c4d41-136">Click **Review sets**, and then select the review set to upload the non-Office 365 data to.</span></span>  <span data-ttu-id="c4d41-137">如果你没有评审集, 可以创建一个。</span><span class="sxs-lookup"><span data-stu-id="c4d41-137">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="c4d41-138">在审阅集中, 单击 "**管理审阅集**", 然后单击 "在**非 Office 365 数据**磁贴上**查看上载**"。</span><span class="sxs-lookup"><span data-stu-id="c4d41-138">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Office 365 data** tile.</span></span>

4. <span data-ttu-id="c4d41-139">单击 "**上载文件**" 以启动 "非 Office 365 数据导入向导"。</span><span class="sxs-lookup"><span data-stu-id="c4d41-139">Click **Upload files** to start the Non-Office 365 data import wizard.</span></span>

   ![上传文件](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="c4d41-141">向导中的第一步是准备 Microsoft 提供的安全的 Azure 存储位置, 以将文件上传到。</span><span class="sxs-lookup"><span data-stu-id="c4d41-141">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="c4d41-142">准备完成后, "**下一步: 上传文件**" 按钮将变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="c4d41-142">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![非 Office 365 导入: 准备](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="c4d41-144">单击 "**下一步: 上传文件**"。</span><span class="sxs-lookup"><span data-stu-id="c4d41-144">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="c4d41-145">在 "**上载文件**" 页上, 执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="c4d41-145">On the **Upload files** page, do the following:</span></span>

   ![非 Office 365 导入: 上传文件](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="c4d41-147">a.</span><span class="sxs-lookup"><span data-stu-id="c4d41-147">a.</span></span> <span data-ttu-id="c4d41-148">在 "**文件的位置路径**" 框中, 验证或键入您要上载的非 Office 365 数据所在的根文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="c4d41-148">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Office 365 data you want to upload.</span></span> <span data-ttu-id="c4d41-149">例如, 对于 "**开始之前" 部分**中显示的示例文件的位置, 应键入 **%USERPROFILE\Downloads\nonO365**。</span><span class="sxs-lookup"><span data-stu-id="c4d41-149">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="c4d41-150">提供正确的位置可确保正确更新路径中 "AzCopy" 命令中显示的框。</span><span class="sxs-lookup"><span data-stu-id="c4d41-150">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="c4d41-151">b.</span><span class="sxs-lookup"><span data-stu-id="c4d41-151">b.</span></span> <span data-ttu-id="c4d41-152">单击 "**复制到剪贴板**" 以复制框中显示的命令。</span><span class="sxs-lookup"><span data-stu-id="c4d41-152">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="c4d41-153">启动 Windows 命令提示符, 粘贴您在上一步中复制的命令, 然后按**enter**以启动 AzCopy 命令。</span><span class="sxs-lookup"><span data-stu-id="c4d41-153">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="c4d41-154">启动该命令后, 非 Office 365 文件将被上载到在步骤4中准备的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="c4d41-154">After you start the command, the non-Office 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![非 Office 365 导入: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="c4d41-156">如前所述, 必须使用 AzCopy 中的 "**上载文件**" 页上提供的命令, 才能成功使用。</span><span class="sxs-lookup"><span data-stu-id="c4d41-156">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="c4d41-157">如果提供的 AzCopy 命令失败, 请参阅[高级电子数据展示中的疑难解答 AzCopy](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="c4d41-157">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="c4d41-158">返回到安全 & 合规性中心, 然后单击 "**下一步: 处理**向导中的文件"。</span><span class="sxs-lookup"><span data-stu-id="c4d41-158">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="c4d41-159">这将启动对上载到 Azure 存储位置的非 Office 365 文件的处理、文本提取和索引。</span><span class="sxs-lookup"><span data-stu-id="c4d41-159">This initiates processing, text extraction, and indexing of the non-Office 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="c4d41-160">通过查看名为 "向**审阅集添加非 office 365 数据**" 的作业来跟踪处理 "**进程文件**" 页或 "**作业**" 选项卡上的非 office 365 文件的进度。</span><span class="sxs-lookup"><span data-stu-id="c4d41-160">Track the progress of processing the non-Office 365 files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Office 365 data to a review set**.</span></span>  <span data-ttu-id="c4d41-161">作业完成后, 新文件将在审阅集中可用。</span><span class="sxs-lookup"><span data-stu-id="c4d41-161">After the job is finished, the new files will be available in the review set.</span></span>

   ![非 Office 365 导入: 处理文件](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="c4d41-163">处理完成后, 可以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="c4d41-163">After the processing is finished, you can close the wizard.</span></span>
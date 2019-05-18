---
title: 修正处理数据时出现的错误
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
ms.openlocfilehash: 5a6c545b15ee07fc0200104b8408e7adb7301c79
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151784"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="f9038-102">修正处理数据时出现的错误</span><span class="sxs-lookup"><span data-stu-id="f9038-102">Error remediation when processing data</span></span>

<span data-ttu-id="f9038-103">错误修正允许电子数据展示管理员修正数据问题, 以防高级电子数据展示能够正确处理内容。</span><span class="sxs-lookup"><span data-stu-id="f9038-103">Error remediation allows eDiscovery administrators the ability to rectify data issues which prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="f9038-104">例如, 由于文件被锁定或加密, 因此无法处理受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="f9038-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="f9038-105">使用错误修正, 电子数据展示管理员可以下载具有此类错误的文件, 删除密码保护并上载修正的文件。</span><span class="sxs-lookup"><span data-stu-id="f9038-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="f9038-106">使用以下工作流修正高级电子数据展示事例中有错误的文件。</span><span class="sxs-lookup"><span data-stu-id="f9038-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="f9038-107">创建错误修正会话以纠正带有处理错误的文件</span><span class="sxs-lookup"><span data-stu-id="f9038-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="f9038-108">如果在以下过程中随时关闭错误修正向导, 则可以通过在 "**视图**" 下拉菜单中选择 "**错误" remediations**返回到 "**处理**" 选项卡中的 "错误修正" 会话。</span><span class="sxs-lookup"><span data-stu-id="f9038-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="f9038-109">在高级电子数据展示事例的 "**处理**" 选项卡上, 选择 "**视图**" 下拉菜单中的 "**错误**"。</span><span class="sxs-lookup"><span data-stu-id="f9038-109">On the **Processing** tab in an Advanced eDiscovery case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="f9038-110">通过单击 "错误类型" 或 "文件类型" 旁边的单选按钮, 选择要修正的错误。</span><span class="sxs-lookup"><span data-stu-id="f9038-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="f9038-111">在下面的示例中, 我们正在修正受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="f9038-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="f9038-112">单击 " **+ 新错误修正**"。</span><span class="sxs-lookup"><span data-stu-id="f9038-112">Click **+ New error remediation**.</span></span>

    ![错误修正](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="f9038-114">将开始错误修正会话, 从准备阶段 (将导致的文件移动到要下载的安全 Azure 位置) 开始。</span><span class="sxs-lookup"><span data-stu-id="f9038-114">The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.</span></span>

    ![准备错误修正](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="f9038-116">准备完成后, 单击 "**下一步: 下载文件**" 以继续下载。</span><span class="sxs-lookup"><span data-stu-id="f9038-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![下载文件](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="f9038-118">若要下载文件, 请指定**下载的目标路径**;这是您的本地计算机上应下载文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f9038-118">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="f9038-119">默认路径 "%USERPROFILE%\Downloads\errors" 指向已登录用户的 "下载" 文件夹;可以根据需要对此进行更改。</span><span class="sxs-lookup"><span data-stu-id="f9038-119">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="f9038-120">建议使用本地文件路径, 而不是远程网络路径, 以实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="f9038-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f9038-121">如果尚未安装 AzCopy, 则可以从此处进行安装:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="f9038-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="f9038-122">通过单击 "**复制到剪贴板**" 复制预定义命令。</span><span class="sxs-lookup"><span data-stu-id="f9038-122">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="f9038-123">启动 windows 命令提示符, 粘贴命令, 然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="f9038-123">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="f9038-124">将下载这些文件。</span><span class="sxs-lookup"><span data-stu-id="f9038-124">The files will be downloaded.</span></span>

    ![准备错误修正](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="f9038-126">如果提供的 AzCopy 命令失败, 请参阅[排查高级电子数据展示中的 AzCopy](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="f9038-126">If the supplied AzCopy command fails, see to [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md)</span></span>

7. <span data-ttu-id="f9038-127">下载文件后, 可以使用适当的工具对它们进行修正。</span><span class="sxs-lookup"><span data-stu-id="f9038-127">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="f9038-128">对于受密码保护的文件, 可以使用许多密码破解工具。</span><span class="sxs-lookup"><span data-stu-id="f9038-128">For password protected files, there are a number of password cracking tools you can use.</span></span> <span data-ttu-id="f9038-129">如果您知道这些文件的密码, 则可以打开它们并删除密码保护。</span><span class="sxs-lookup"><span data-stu-id="f9038-129">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="f9038-130">务必在 tact 中保留已修正文件的目录结构和文件名, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="f9038-130">IT is important that you retain the directory structure and file names of the remediated files in tact.</span></span>  <span data-ttu-id="f9038-131">在下载的文件和文件夹中使用的所有命名约定使 remdiated 文件可以重新关联到原始文件。</span><span class="sxs-lookup"><span data-stu-id="f9038-131">All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="f9038-132">现在, 返回到高级电子数据展示并单击 "**下一步: 上传文件**"。</span><span class="sxs-lookup"><span data-stu-id="f9038-132">Now, return to Advanced eDiscovery and click **Next: Upload files**.</span></span>  <span data-ttu-id="f9038-133">此操作将移至下一步, 你现在可以在其中上传文件。</span><span class="sxs-lookup"><span data-stu-id="f9038-133">This will move to the next step where you can now upload the files.</span></span>

    ![上传文件](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="f9038-135">在 "**文件的位置路径**" 文本框中指定修正的文件的位置, 然后单击 "**复制到 clibpboard**"。</span><span class="sxs-lookup"><span data-stu-id="f9038-135">Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.</span></span>

10. <span data-ttu-id="f9038-136">将命令粘贴到 Windows 命令提示符中, 然后按**enter**上传文件。</span><span class="sxs-lookup"><span data-stu-id="f9038-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="f9038-138">最后, 返回到高级电子数据展示并单击 "**下一步: 处理文件**"。</span><span class="sxs-lookup"><span data-stu-id="f9038-138">Finally, return to Advanced eDiscovery and click **Next: Process files**.</span></span>

12. <span data-ttu-id="f9038-139">处理完成时。</span><span class="sxs-lookup"><span data-stu-id="f9038-139">When processing is complete.</span></span>  <span data-ttu-id="f9038-140">您可以返回到评审集并查看修正的文件。</span><span class="sxs-lookup"><span data-stu-id="f9038-140">You can return to the review set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="f9038-141">修正文件时会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="f9038-141">What happens when files are remediated</span></span>

<span data-ttu-id="f9038-142">当上载修正的文件时, 原始元数据将保留, 但以下字段除外:</span><span class="sxs-lookup"><span data-stu-id="f9038-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="f9038-143">DocumentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="f9038-143">DocumentExtractedUrl</span></span>
- <span data-ttu-id="f9038-144">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="f9038-144">ExtractedTextSize</span></span>
- <span data-ttu-id="f9038-145">HasText</span><span class="sxs-lookup"><span data-stu-id="f9038-145">HasText</span></span>
- <span data-ttu-id="f9038-146">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="f9038-146">IsErrorRemediate</span></span>
- <span data-ttu-id="f9038-147">IsParentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="f9038-147">IsParentExtractedUrl</span></span>
- <span data-ttu-id="f9038-148">ItemExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="f9038-148">ItemExtractedUrl</span></span>
- <span data-ttu-id="f9038-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="f9038-149">LoadId</span></span>
- <span data-ttu-id="f9038-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="f9038-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="f9038-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="f9038-151">ProcessingStatus</span></span>
- <span data-ttu-id="f9038-152">文本</span><span class="sxs-lookup"><span data-stu-id="f9038-152">Text</span></span>
- <span data-ttu-id="f9038-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="f9038-153">WordCount</span></span>
- <span data-ttu-id="f9038-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="f9038-154">WorkingsetId</span></span>

<span data-ttu-id="f9038-155">有关高级电子数据展示中所有文档元数据字段的定义, 请参阅[document metadata fields](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="f9038-155">For a definition of all document metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
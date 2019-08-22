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
ms.openlocfilehash: c9c2660929037430535c9b612218563c51b1f056
ms.sourcegitcommit: 3f3f3ecb28ef65d023f3573f9a4e09a0586d8f53
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "36490789"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="9917c-102">修正处理数据时出现的错误</span><span class="sxs-lookup"><span data-stu-id="9917c-102">Error remediation when processing data</span></span>

<span data-ttu-id="9917c-103">错误修正使电子数据展示管理员能够修正阻止高级电子数据展示的数据问题, 从而无法正确处理内容。</span><span class="sxs-lookup"><span data-stu-id="9917c-103">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="9917c-104">例如, 由于文件被锁定或加密, 因此无法处理受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="9917c-104">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="9917c-105">使用错误修正, 电子数据展示管理员可以下载具有此类错误的文件, 删除密码保护, 然后上传修正的文件。</span><span class="sxs-lookup"><span data-stu-id="9917c-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="9917c-106">使用以下工作流修正高级电子数据展示事例中有错误的文件。</span><span class="sxs-lookup"><span data-stu-id="9917c-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="9917c-107">创建错误修正会话以修正带有处理错误的文件</span><span class="sxs-lookup"><span data-stu-id="9917c-107">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="9917c-108">如果在以下过程中随时关闭错误修正向导, 则可以通过在 "**视图**" 下拉菜单中选择 "**错误" remediations**返回到 "**处理**" 选项卡中的 "错误修正" 会话。</span><span class="sxs-lookup"><span data-stu-id="9917c-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="9917c-109">在高级电子数据展示事例的 "**处理**" 选项卡上, 选择 "**视图**" 下拉菜单中的 "**错误**"。</span><span class="sxs-lookup"><span data-stu-id="9917c-109">On the **Processing** tab in an Advanced eDiscovery case, select **Errors** in the **View** drop-down menu.</span></span>

2. <span data-ttu-id="9917c-110">通过单击 "错误类型" 或 "文件类型" 旁边的单选按钮, 选择要修正的错误。</span><span class="sxs-lookup"><span data-stu-id="9917c-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="9917c-111">在下面的示例中, 我们正在修正受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="9917c-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="9917c-112">单击 "**新建错误修正**"。</span><span class="sxs-lookup"><span data-stu-id="9917c-112">Click **New error remediation**.</span></span>

    ![错误修正](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="9917c-114">错误修正会话从准备阶段开始, 其中包含错误的文件复制到 Microsoft 提供的 Azure 存储位置, 以便将其下载到本地计算机以进行修正。</span><span class="sxs-lookup"><span data-stu-id="9917c-114">The error remediation session starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![准备错误修正](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="9917c-116">准备完成后, 单击 "**下一步: 下载文件**" 以继续下载。</span><span class="sxs-lookup"><span data-stu-id="9917c-116">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![下载文件](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="9917c-118">若要下载文件, 请指定**下载的目标路径**。</span><span class="sxs-lookup"><span data-stu-id="9917c-118">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="9917c-119">这是您的本地计算机上下载文件的路径。</span><span class="sxs-lookup"><span data-stu-id="9917c-119">This is a path on your local computer where the file is downloaded.</span></span>  <span data-ttu-id="9917c-120">默认路径 "%USERPROFILE%\Downloads\errors" 指向已登录用户的 "下载" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9917c-120">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="9917c-121">如有必要, 可以更改此路径。</span><span class="sxs-lookup"><span data-stu-id="9917c-121">You can change this path if necessary.</span></span> <span data-ttu-id="9917c-122">如果您确实要更改它, 建议使用本地文件路径以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="9917c-122">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="9917c-123">请勿使用远程网络路径。</span><span class="sxs-lookup"><span data-stu-id="9917c-123">Don't use a remote network path.</span></span>

6. <span data-ttu-id="9917c-124">通过单击 "**复制到剪贴板**" 复制预定义命令。</span><span class="sxs-lookup"><span data-stu-id="9917c-124">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="9917c-125">启动 windows 命令提示符, 粘贴命令, 然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="9917c-125">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="9917c-126">下载文件。</span><span class="sxs-lookup"><span data-stu-id="9917c-126">The files are downloaded.</span></span>

    ![准备进行错误修正](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="9917c-128">必须使用 AzCopy app-v 8.1 才能成功使用 "**下载文件**" 页上提供的命令。</span><span class="sxs-lookup"><span data-stu-id="9917c-128">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="9917c-129">在下面的步骤10中, 还必须使用 AzCopy 中的文件上传文件。</span><span class="sxs-lookup"><span data-stu-id="9917c-129">You also must use AzCopy v8.1 to upload the files in step 10 below.</span></span> <span data-ttu-id="9917c-130">若要安装此版本的 AzCopy, 请参阅[在 Windows 上使用 AzCopy ue-v 8.1 传输数据](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="9917c-130">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="9917c-131">如果提供的 AzCopy 命令失败, 请参阅[高级电子数据展示中的疑难解答 AzCopy](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="9917c-131">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="9917c-132">下载文件后, 可以使用适当的工具对它们进行修正。</span><span class="sxs-lookup"><span data-stu-id="9917c-132">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="9917c-133">对于受密码保护的文件, 可以使用几种密码破解工具。</span><span class="sxs-lookup"><span data-stu-id="9917c-133">For password-protected files, there several password cracking tools you can use.</span></span> <span data-ttu-id="9917c-134">如果您知道这些文件的密码, 则可以打开它们并删除密码保护。</span><span class="sxs-lookup"><span data-stu-id="9917c-134">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="9917c-135">必须保留已修正文件的目录结构和文件名, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="9917c-135">It's important that you retain the directory structure and file names of the remediated files.</span></span> <span data-ttu-id="9917c-136">通过下载的文件和文件夹的路径名称, 可以将修正的文件与原始文件进行关联。</span><span class="sxs-lookup"><span data-stu-id="9917c-136">The path names of the downloaded files and folders make it possible to associate the remediated files with the original files.</span></span>  <span data-ttu-id="9917c-137">如果更改了目录结构或文件的名称, 您将收到以下错误: `Cannot apply Error Remediation to the current Workingset`。</span><span class="sxs-lookup"><span data-stu-id="9917c-137">If the directory structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span>

8. <span data-ttu-id="9917c-138">现在, 返回到高级电子数据展示并单击 "**下一步: 上传文件**"。</span><span class="sxs-lookup"><span data-stu-id="9917c-138">Now, return to Advanced eDiscovery and click **Next: Upload files**.</span></span>  <span data-ttu-id="9917c-139">此操作将移至下一步, 你现在可以在其中上传文件。</span><span class="sxs-lookup"><span data-stu-id="9917c-139">This will move to the next step where you can now upload the files.</span></span>

    ![上传文件](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="9917c-141">在 "**文件的位置路径**" 文本框中指定修正的文件的位置, 然后单击 "**复制到剪贴板**"。</span><span class="sxs-lookup"><span data-stu-id="9917c-141">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="9917c-142">将命令粘贴到 Windows 命令提示符中, 然后按**enter**上传文件。</span><span class="sxs-lookup"><span data-stu-id="9917c-142">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="9917c-144">返回到高级电子数据展示并单击 "**下一步: 处理文件**"。</span><span class="sxs-lookup"><span data-stu-id="9917c-144">Return to Advanced eDiscovery and click **Next: Process files**.</span></span>

12. <span data-ttu-id="9917c-145">处理完成时。</span><span class="sxs-lookup"><span data-stu-id="9917c-145">When processing is complete.</span></span> <span data-ttu-id="9917c-146">您可以返回到评审集并查看修正的文件。</span><span class="sxs-lookup"><span data-stu-id="9917c-146">You can return to the review set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="9917c-147">修正文件时会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="9917c-147">What happens when files are remediated</span></span>

<span data-ttu-id="9917c-148">当上载修正的文件时, 原始元数据将保留, 但以下字段除外:</span><span class="sxs-lookup"><span data-stu-id="9917c-148">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="9917c-149">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="9917c-149">ExtractedTextSize</span></span>
- <span data-ttu-id="9917c-150">HasText</span><span class="sxs-lookup"><span data-stu-id="9917c-150">HasText</span></span>
- <span data-ttu-id="9917c-151">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="9917c-151">IsErrorRemediate</span></span>
- <span data-ttu-id="9917c-152">LoadId</span><span class="sxs-lookup"><span data-stu-id="9917c-152">LoadId</span></span>
- <span data-ttu-id="9917c-153">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="9917c-153">ProcessingErrorMessage</span></span>
- <span data-ttu-id="9917c-154">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="9917c-154">ProcessingStatus</span></span>
- <span data-ttu-id="9917c-155">文本</span><span class="sxs-lookup"><span data-stu-id="9917c-155">Text</span></span>
- <span data-ttu-id="9917c-156">WordCount</span><span class="sxs-lookup"><span data-stu-id="9917c-156">WordCount</span></span>
- <span data-ttu-id="9917c-157">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="9917c-157">WorkingsetId</span></span>

<span data-ttu-id="9917c-158">有关高级电子数据展示中所有元数据字段的定义, 请参阅[Document metadata fields](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="9917c-158">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>

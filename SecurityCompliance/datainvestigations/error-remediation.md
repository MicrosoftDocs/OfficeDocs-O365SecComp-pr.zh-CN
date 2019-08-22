---
title: 处理调查数据时的错误修正
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
ms.openlocfilehash: 45e4fb0651cc137a67cc5322bf5e874ea31df838
ms.sourcegitcommit: 3f3f3ecb28ef65d023f3573f9a4e09a0586d8f53
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "36490799"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="48f3a-102">处理调查数据时的错误修正</span><span class="sxs-lookup"><span data-stu-id="48f3a-102">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="48f3a-103">错误修正使调查人员能够修正阻止数据调查 (预览版) 以正确处理内容的数据问题。</span><span class="sxs-lookup"><span data-stu-id="48f3a-103">Error remediation allows investigators the ability to rectify data issues that prevent Data Investigations (Preview) from properly processing the content.</span></span> <span data-ttu-id="48f3a-104">例如, 由于文件被锁定或加密, 因此无法处理受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="48f3a-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="48f3a-105">使用错误修正, 调查人员可以下载具有此类错误的文件, 删除密码保护, 并上传修正的文件。</span><span class="sxs-lookup"><span data-stu-id="48f3a-105">Using error remediation, investigators can download files with such errors, remove the password protection, and upload the remediated files.</span></span>

<span data-ttu-id="48f3a-106">使用以下工作流修正在数据调查 (预览) 案例中出错的文件。</span><span class="sxs-lookup"><span data-stu-id="48f3a-106">Use the following workflow to remediate files with errors in Data Investigations (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="48f3a-107">创建错误修正会话以纠正带有处理错误的文件</span><span class="sxs-lookup"><span data-stu-id="48f3a-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="48f3a-108">如果在以下过程中随时关闭错误修正向导, 则可以通过在 "**视图**" 下拉菜单中选择 "**错误" remediations**返回到 "**处理**" 选项卡中的 "错误修正" 会话。</span><span class="sxs-lookup"><span data-stu-id="48f3a-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="48f3a-109">在数据调查的 "**处理**" 选项卡上, 选择 "**视图**" 下拉菜单中的 "**错误**"。</span><span class="sxs-lookup"><span data-stu-id="48f3a-109">On the **Processing** tab in a data investigation, select **Errors** in the **View** dropdown menu.</span></span>

2. <span data-ttu-id="48f3a-110">通过单击 "错误类型" 或 "文件类型" 旁边的单选按钮, 选择要修正的错误。</span><span class="sxs-lookup"><span data-stu-id="48f3a-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="48f3a-111">在下面的示例中, 我们正在修正受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="48f3a-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="48f3a-112">单击 " **+ 新错误修正**"。</span><span class="sxs-lookup"><span data-stu-id="48f3a-112">Click **+ New error remediation**.</span></span>

    ![错误修正](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="48f3a-114">错误修正会话开始, 从准备阶段开始, 其中将包含错误的文件复制到安全 Azure 位置, 以便可以下载它们。</span><span class="sxs-lookup"><span data-stu-id="48f3a-114">The error remediation session begins, starting with a preparation stage where the files with errors are copied to a secure Azure location so that they can be downloaded.</span></span>

    ![准备错误修正](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="48f3a-116">准备完成后, 单击 "**下一步: 下载文件**" 以继续下载。</span><span class="sxs-lookup"><span data-stu-id="48f3a-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![下载文件](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="48f3a-118">若要下载文件, 请指定**下载的目标路径**。</span><span class="sxs-lookup"><span data-stu-id="48f3a-118">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="48f3a-119">这是您的本地计算机上应下载文件的路径。</span><span class="sxs-lookup"><span data-stu-id="48f3a-119">This is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="48f3a-120">默认路径 "%USERPROFILE%\Downloads\errors" 指向已登录用户的 "下载" 文件夹;可以根据需要对此进行更改。</span><span class="sxs-lookup"><span data-stu-id="48f3a-120">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="48f3a-121">建议使用本地文件路径, 而不是远程网络路径, 以实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="48f3a-121">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="48f3a-122">如果尚未安装 AzCopy, 则可以从此处进行安装:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="48f3a-122">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="48f3a-123">通过单击 "**复制到剪贴板**" 复制预定义命令。</span><span class="sxs-lookup"><span data-stu-id="48f3a-123">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="48f3a-124">启动 windows 命令提示符, 粘贴命令, 然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="48f3a-124">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="48f3a-125">将下载这些文件。</span><span class="sxs-lookup"><span data-stu-id="48f3a-125">The files will be downloaded.</span></span>

    ![准备错误修正](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="48f3a-127">如果您在运行此命令时遇到问题, 请参阅[解决 AzCopy In 高级电子数据展示](../compliance20/troubleshooting-azcopy.md)问题。</span><span class="sxs-lookup"><span data-stu-id="48f3a-127">If you have issues running this command, see [Troubleshoot AzCopy in Advanced eDiscovery](../compliance20/troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="48f3a-128">下载文件后, 可以使用适当的工具对它们进行修正。</span><span class="sxs-lookup"><span data-stu-id="48f3a-128">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="48f3a-129">对于受密码保护的文件, 可以使用几种密码破解工具。</span><span class="sxs-lookup"><span data-stu-id="48f3a-129">For password protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="48f3a-130">如果您知道这些文件的密码, 则可以打开它们并删除密码保护。</span><span class="sxs-lookup"><span data-stu-id="48f3a-130">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    
   > [!NOTE]
    > <span data-ttu-id="48f3a-131">必须保留已修正文件的目录结构和文件名, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="48f3a-131">It's important that you retain the directory structure and file names of the remediated files.</span></span> <span data-ttu-id="48f3a-132">通过下载的文件和文件夹的路径名称, 可以将修正的文件与原始文件进行关联。</span><span class="sxs-lookup"><span data-stu-id="48f3a-132">The path names of the downloaded files and folders make it possible to associate the remediated files with the original files.</span></span>  <span data-ttu-id="48f3a-133">如果更改了目录结构或文件的名称, 您将收到以下错误: `Cannot apply Error Remediation to the current Evidenceset`。</span><span class="sxs-lookup"><span data-stu-id="48f3a-133">If the directory structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Evidenceset`.</span></span>

8. <span data-ttu-id="48f3a-134">现在, 返回到 "数据调查 (预览)", 然后单击 "**下一步: 上传文件**"。</span><span class="sxs-lookup"><span data-stu-id="48f3a-134">Now, return to Data Investigations (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="48f3a-135">此操作将移至下一步, 你现在可以在其中上传文件。</span><span class="sxs-lookup"><span data-stu-id="48f3a-135">This will move to the next step where you can now upload the files.</span></span>

    ![上传文件](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="48f3a-137">在 "**文件的位置路径**" 文本框中指定修正的文件的位置, 然后单击 "**复制到剪贴板**"。</span><span class="sxs-lookup"><span data-stu-id="48f3a-137">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="48f3a-138">将命令粘贴到 Windows 命令提示符中, 然后按**enter**上传文件。</span><span class="sxs-lookup"><span data-stu-id="48f3a-138">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="48f3a-140">最后, 返回到 "数据调查 (预览)", 然后单击 "**下一步: 处理文件**"。</span><span class="sxs-lookup"><span data-stu-id="48f3a-140">Finally, return to Data Investigations (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="48f3a-141">处理完成时。</span><span class="sxs-lookup"><span data-stu-id="48f3a-141">When processing is complete.</span></span>  <span data-ttu-id="48f3a-142">您可以返回到工作集并查看修正的文件。</span><span class="sxs-lookup"><span data-stu-id="48f3a-142">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="48f3a-143">修正文件时会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="48f3a-143">What happens when files are remediated</span></span>

<span data-ttu-id="48f3a-144">当上载修正的文件时, 原始元数据将保留, 但以下字段除外:</span><span class="sxs-lookup"><span data-stu-id="48f3a-144">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="48f3a-145">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="48f3a-145">ExtractedTextSize</span></span>
- <span data-ttu-id="48f3a-146">HasText</span><span class="sxs-lookup"><span data-stu-id="48f3a-146">HasText</span></span>
- <span data-ttu-id="48f3a-147">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="48f3a-147">IsErrorRemediate</span></span>
- <span data-ttu-id="48f3a-148">LoadId</span><span class="sxs-lookup"><span data-stu-id="48f3a-148">LoadId</span></span>
- <span data-ttu-id="48f3a-149">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="48f3a-149">ProcessingErrorMessage</span></span>
- <span data-ttu-id="48f3a-150">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="48f3a-150">ProcessingStatus</span></span>
- <span data-ttu-id="48f3a-151">文本</span><span class="sxs-lookup"><span data-stu-id="48f3a-151">Text</span></span>
- <span data-ttu-id="48f3a-152">WordCount</span><span class="sxs-lookup"><span data-stu-id="48f3a-152">WordCount</span></span>
- <span data-ttu-id="48f3a-153">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="48f3a-153">WorkingsetId</span></span>

<span data-ttu-id="48f3a-154">有关数据调查 (预览) 中的所有文档元数据字段的定义, 请参阅[document metadata fields](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="48f3a-154">For a definition of all document metadata fields in Data Investigations (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
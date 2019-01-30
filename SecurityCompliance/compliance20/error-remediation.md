---
title: 修正处理错误时出现的错误
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
ms.openlocfilehash: 82e6d44ded64d586611f429f9b3eebe4f47e9898
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607490"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="189a8-102">修正处理错误时出现的错误</span><span class="sxs-lookup"><span data-stu-id="189a8-102">Error remediation when processing data</span></span>

<span data-ttu-id="189a8-p101">错误修复允许电子数据展示管理员能够纠正防止高级电子数据展示 （预览） 正确处理该内容的数据问题。例如，由于文件锁定或加密，则无法处理受密码保护的文件。使用错误修复，电子数据展示管理员可以下载具有此类错误的文件、 删除密码保护并上载修正后的文件。</span><span class="sxs-lookup"><span data-stu-id="189a8-p101">Error remediation allows eDiscovery administrators the ability to rectify data issues which prevent Advanced eDiscovery (Preview) from properly processing the content. For example, files that are password protected cannot be processed since the files are locked or encrypted. Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection and upload the remediated files.</span></span>

<span data-ttu-id="189a8-106">使用以下工作流进行补救具有高级电子数据展示 （预览） 示例中的错误的文件。</span><span class="sxs-lookup"><span data-stu-id="189a8-106">Use the following workflow to remediate files with errors in Advanced eDiscovery (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="189a8-107">创建错误修复会话修正文件处理错误</span><span class="sxs-lookup"><span data-stu-id="189a8-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="189a8-108">如果错误修复向导关闭以下过程在任何时候，您可以返回到错误的修正会话从**处理**选项卡**视图**下拉列表菜单中选择**错误修复**。</span><span class="sxs-lookup"><span data-stu-id="189a8-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="189a8-109">在高级电子数据展示 （预览） 事例**处理**选项卡上，在**视图**下拉列表菜单中选择**错误**。</span><span class="sxs-lookup"><span data-stu-id="189a8-109">On the **Processing** tab in an Advanced eDiscovery (Preview) case, select **Errors** in the **View** drop down menu.</span></span>

2. <span data-ttu-id="189a8-p102">选择您想要修正通过单击旁边的错误类型或文件类型单选按钮的错误。 在以下示例中，我们正在补救密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="189a8-p102">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.  In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="189a8-112">单击 **+ 新建错误修复**。</span><span class="sxs-lookup"><span data-stu-id="189a8-112">Click **+ New error remediation**.</span></span>

    ![错误修复](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="189a8-114">错误的修正会话将开始，开头准备阶段其中的导致文件移动到一个安全的 Azure 位置下载。</span><span class="sxs-lookup"><span data-stu-id="189a8-114">The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.</span></span>

    ![准备错误修复](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="189a8-116">准备完毕后，单击**下一步： 下载文件**继续进行下载。</span><span class="sxs-lookup"><span data-stu-id="189a8-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![下载文件](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="189a8-p103">若要下载文件，指定**供下载的目标路径**;这是您应在其中下载文件的本地计算机上的路径。 默认路径，%userprofile%\downloads\errors，指向登录的用户下载文件夹。可根据需要对此进行更改。</span><span class="sxs-lookup"><span data-stu-id="189a8-p103">To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.  The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="189a8-120">我们建议您使用本地文件路径而不是远程的网络路径为获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="189a8-120">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="189a8-121">如果您尚未安装 AzCopy，您可以从此处安装它：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="189a8-121">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="189a8-p104">通过单击**复制到剪贴板**中复制的预定义的命令。启动 windows 命令提示符和粘贴命令，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="189a8-p104">Copy the predefined command by clicking **Copy to clipboard**. Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="189a8-124">将下载文件。</span><span class="sxs-lookup"><span data-stu-id="189a8-124">The files will be downloaded.</span></span>

    ![准备错误修复](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > <span data-ttu-id="189a8-126">如果运行此命令的问题，请参阅https://go.microsoft.com/fwlink/?linkid=2038117疑难解答提示。</span><span class="sxs-lookup"><span data-stu-id="189a8-126">If you have issues running this command, see https://go.microsoft.com/fwlink/?linkid=2038117 for troubleshooting tips.</span></span>

7. <span data-ttu-id="189a8-p105">下载文件之后, 您可以修正其与相应的工具。对于受密码保护的文件，有大量的密码破解可以使用的工具。如果您知道文件密码，您可以打开它们，并删除密码保护。</span><span class="sxs-lookup"><span data-stu-id="189a8-p105">After downloading the files, you can remediate them with an appropriate tool. For password protected files, there are a number of password cracking tools you can use. If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    > [!NOTE]
    > <span data-ttu-id="189a8-p106">IT 很重要，则保持原封不动修正后的文件的目录结构和文件名称。 所有命名约定用于下载文件中并文件夹使其可以将回原来的 remdiated 文件相关联。</span><span class="sxs-lookup"><span data-stu-id="189a8-p106">IT is important that you retain the directory structure and file names of the remediated files in tact.  All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.</span></span>

8. <span data-ttu-id="189a8-p107">现在，返回到高级电子数据展示 （预览），然后单击**下一步： 将文件上载**。 这将移到下一步，您现在可以上载文件。</span><span class="sxs-lookup"><span data-stu-id="189a8-p107">Now, return to Advanced eDiscovery (Preview) and click **Next: Upload files**.  This will move to the next step where you can now upload the files.</span></span>

    ![上载文件](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="189a8-135">指定在**文件位置的路径**文本框中，修正后的文件的位置，单击**复制到 clibpboard**。</span><span class="sxs-lookup"><span data-stu-id="189a8-135">Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.</span></span>

10. <span data-ttu-id="189a8-136">粘贴到 Windows 命令提示符处的命令，然后按**Enter**将文件上载。</span><span class="sxs-lookup"><span data-stu-id="189a8-136">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="189a8-138">最后，返回到高级电子数据展示 （预览），然后单击**下一步： 处理文件**。</span><span class="sxs-lookup"><span data-stu-id="189a8-138">Finally, return to Advanced eDiscovery (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="189a8-p108">完成后处理。 您可以返回到工作集，并查看修正后的文件。</span><span class="sxs-lookup"><span data-stu-id="189a8-p108">When processing is complete.  You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="189a8-141">文件修正时发生情况</span><span class="sxs-lookup"><span data-stu-id="189a8-141">What happens when files are remediated</span></span>

<span data-ttu-id="189a8-142">当修正后将文件上载时，以下字段除外保留原始的元数据：</span><span class="sxs-lookup"><span data-stu-id="189a8-142">When remediated files are uploaded, the original metadata is preserved with the exception of the following fields:</span></span> 

- <span data-ttu-id="189a8-143">DocumentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="189a8-143">DocumentExtractedUrl</span></span>
- <span data-ttu-id="189a8-144">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="189a8-144">ExtractedTextSize</span></span>
- <span data-ttu-id="189a8-145">HasText</span><span class="sxs-lookup"><span data-stu-id="189a8-145">HasText</span></span>
- <span data-ttu-id="189a8-146">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="189a8-146">IsErrorRemediate</span></span>
- <span data-ttu-id="189a8-147">IsParentExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="189a8-147">IsParentExtractedUrl</span></span>
- <span data-ttu-id="189a8-148">ItemExtractedUrl</span><span class="sxs-lookup"><span data-stu-id="189a8-148">ItemExtractedUrl</span></span>
- <span data-ttu-id="189a8-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="189a8-149">LoadId</span></span>
- <span data-ttu-id="189a8-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="189a8-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="189a8-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="189a8-151">ProcessingStatus</span></span>
- <span data-ttu-id="189a8-152">文本</span><span class="sxs-lookup"><span data-stu-id="189a8-152">Text</span></span>
- <span data-ttu-id="189a8-153">字数统计</span><span class="sxs-lookup"><span data-stu-id="189a8-153">WordCount</span></span>
- <span data-ttu-id="189a8-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="189a8-154">WorkingsetId</span></span>

<span data-ttu-id="189a8-155">有关高级电子数据展示 (Preview) 中的所有文档元数据字段的定义，请参阅[文档元数据字段](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="189a8-155">For a definition of all document metadata fields in Advanced eDiscovery (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
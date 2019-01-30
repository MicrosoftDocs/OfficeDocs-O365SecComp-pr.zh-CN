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
# <a name="error-remediation-when-processing-data"></a>修正处理错误时出现的错误

错误修复允许电子数据展示管理员能够纠正防止高级电子数据展示 （预览） 正确处理该内容的数据问题。例如，由于文件锁定或加密，则无法处理受密码保护的文件。使用错误修复，电子数据展示管理员可以下载具有此类错误的文件、 删除密码保护并上载修正后的文件。

使用以下工作流进行补救具有高级电子数据展示 （预览） 示例中的错误的文件。

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>创建错误修复会话修正文件处理错误

>[!NOTE]
>如果错误修复向导关闭以下过程在任何时候，您可以返回到错误的修正会话从**处理**选项卡**视图**下拉列表菜单中选择**错误修复**。

1. 在高级电子数据展示 （预览） 事例**处理**选项卡上，在**视图**下拉列表菜单中选择**错误**。

2. 选择您想要修正通过单击旁边的错误类型或文件类型单选按钮的错误。 在以下示例中，我们正在补救密码保护的文件。

3. 单击 **+ 新建错误修复**。

    ![错误修复](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    错误的修正会话将开始，开头准备阶段其中的导致文件移动到一个安全的 Azure 位置下载。

    ![准备错误修复](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 准备完毕后，单击**下一步： 下载文件**继续进行下载。

    ![下载文件](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. 若要下载文件，指定**供下载的目标路径**;这是您应在其中下载文件的本地计算机上的路径。 默认路径，%userprofile%\downloads\errors，指向登录的用户下载文件夹。可根据需要对此进行更改。

    >[!NOTE]
    >我们建议您使用本地文件路径而不是远程的网络路径为获得最佳性能。

    > [!NOTE]
    > 如果您尚未安装 AzCopy，您可以从此处安装它：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

6. 通过单击**复制到剪贴板**中复制的预定义的命令。启动 windows 命令提示符和粘贴命令，然后按**Enter**。  

    将下载文件。

    ![准备错误修复](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > 如果运行此命令的问题，请参阅https://go.microsoft.com/fwlink/?linkid=2038117疑难解答提示。

7. 下载文件之后, 您可以修正其与相应的工具。对于受密码保护的文件，有大量的密码破解可以使用的工具。如果您知道文件密码，您可以打开它们，并删除密码保护。
    > [!NOTE]
    > IT 很重要，则保持原封不动修正后的文件的目录结构和文件名称。 所有命名约定用于下载文件中并文件夹使其可以将回原来的 remdiated 文件相关联。

8. 现在，返回到高级电子数据展示 （预览），然后单击**下一步： 将文件上载**。 这将移到下一步，您现在可以上载文件。

    ![上载文件](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. 指定在**文件位置的路径**文本框中，修正后的文件的位置，单击**复制到 clibpboard**。

10. 粘贴到 Windows 命令提示符处的命令，然后按**Enter**将文件上载。

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. 最后，返回到高级电子数据展示 （预览），然后单击**下一步： 处理文件**。

12. 完成后处理。 您可以返回到工作集，并查看修正后的文件。

## <a name="what-happens-when-files-are-remediated"></a>文件修正时发生情况

当修正后将文件上载时，以下字段除外保留原始的元数据： 

- DocumentExtractedUrl
- ExtractedTextSize
- HasText
- IsErrorRemediate
- IsParentExtractedUrl
- ItemExtractedUrl
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- 文本
- 字数统计
- WorkingsetId

有关高级电子数据展示 (Preview) 中的所有文档元数据字段的定义，请参阅[文档元数据字段](document-metadata-fields.md)。
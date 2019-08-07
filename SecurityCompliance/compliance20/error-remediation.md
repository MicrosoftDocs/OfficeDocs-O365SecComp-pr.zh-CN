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
ms.openlocfilehash: efcee812b6082a7f7ee36e6aea0ecb7ed0243077
ms.sourcegitcommit: 6122eb026c558a5126c40845e656fbb0c40cb32a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "36168122"
---
# <a name="error-remediation-when-processing-data"></a>修正处理数据时出现的错误

错误修正使电子数据展示管理员能够修正阻止高级电子数据展示的数据问题, 从而无法正确处理内容。 例如, 由于文件被锁定或加密, 因此无法处理受密码保护的文件。 使用错误修正, 电子数据展示管理员可以下载具有此类错误的文件, 删除密码保护, 然后上传修正的文件。

使用以下工作流修正高级电子数据展示事例中有错误的文件。

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>创建错误修正会话以修正带有处理错误的文件

>[!NOTE]
>如果在以下过程中随时关闭错误修正向导, 则可以通过在 "**视图**" 下拉菜单中选择 "**错误" remediations**返回到 "**处理**" 选项卡中的 "错误修正" 会话。

1. 在高级电子数据展示事例的 "**处理**" 选项卡上, 选择 "**视图**" 下拉菜单中的 "**错误**"。

2. 通过单击 "错误类型" 或 "文件类型" 旁边的单选按钮, 选择要修正的错误。  在下面的示例中, 我们正在修正受密码保护的文件。

3. 单击 "**新建错误修正**"。

    ![错误修正](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    错误修正会话从准备阶段开始, 其中包含错误的文件复制到 Microsoft 提供的 Azure 存储位置, 以便将其下载到本地计算机以进行修正。

    ![准备错误修正](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. 准备完成后, 单击 "**下一步: 下载文件**" 以继续下载。

    ![下载文件](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. 若要下载文件, 请指定**下载的目标路径**。 这是您的本地计算机上下载文件的路径。  默认路径 "%USERPROFILE%\Downloads\errors" 指向已登录用户的 "下载" 文件夹。 如有必要, 可以更改此路径。 如果您确实要更改它, 建议使用本地文件路径以获得最佳性能。 请勿使用远程网络路径。

6. 通过单击 "**复制到剪贴板**" 复制预定义命令。 启动 windows 命令提示符, 粘贴命令, 然后按**enter**。  

    下载文件。

    ![准备进行错误修正](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > 必须使用 AzCopy app-v 8.1 才能成功使用 "**下载文件**" 页上提供的命令。 在下面的步骤10中, 还必须使用 AzCopy 中的文件上传文件。 若要安装此版本的 AzCopy, 请参阅[在 Windows 上使用 AzCopy ue-v 8.1 传输数据](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。 如果提供的 AzCopy 命令失败, 请参阅[高级电子数据展示中的疑难解答 AzCopy](troubleshooting-azcopy.md)。

7. 下载文件后, 可以使用适当的工具对它们进行修正。 对于受密码保护的文件, 可以使用几种密码破解工具。 如果您知道这些文件的密码, 则可以打开它们并删除密码保护。
    > [!NOTE]
    > 务必在 tact 中保留已修正文件的目录结构和文件名, 这一点非常重要。  在下载的文件和文件夹中使用的所有命名约定使 remdiated 文件可以重新关联到原始文件。

8. 现在, 返回到高级电子数据展示并单击 "**下一步: 上传文件**"。  此操作将移至下一步, 你现在可以在其中上传文件。

    ![上传文件](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. 在 "**文件的位置路径**" 文本框中指定修正的文件的位置, 然后单击 "**复制到剪贴板**"。

10. 将命令粘贴到 Windows 命令提示符中, 然后按**enter**上传文件。

    ![ff2ff691-629f-4065-9b37-5333f937daf6](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. 返回到高级电子数据展示并单击 "**下一步: 处理文件**"。

12. 处理完成时。 您可以返回到评审集并查看修正的文件。

## <a name="what-happens-when-files-are-remediated"></a>修正文件时会发生什么情况

当上载修正的文件时, 原始元数据将保留, 但以下字段除外: 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- 文本
- WordCount
- WorkingsetId

有关高级电子数据展示中所有元数据字段的定义, 请参阅[Document metadata fields](document-metadata-fields.md)。

---
title: 将非 Office 365 数据加载到审阅集
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
ms.openlocfilehash: 60775002d5ebec83aacbec350a044b9d6ffeb461
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834953"
---
# <a name="load-non-office-365-data-into-a-review-set"></a>将非 Office 365 数据加载到审阅集

并非所有可能需要使用 Office 365 进行分析的文档都将在 Office 365 中实时发布。 通过高级电子数据展示中的非 Office 365 内容导入功能, 可以将不在 Office 365 中的文档上传到审阅集, 以便使用高级电子数据展示对其进行分析。 此过程向您演示如何将非 Office 365 文档转换为高级电子数据展示以进行分析。

>[!Note]
>高级电子数据展示需要 Office 365 E3 和您的组织的高级合规性加载项或 E5 订阅。 如果你没有该计划, 并且想要尝试高级电子数据展示, 可以注册 Office 365 企业版 E5 的试用版。

## <a name="before-you-begin"></a>开始之前

如本文中所述, 使用 "上载非 Office 365" 功能要求您具备以下各项:

- Office 365 或 Microsoft 365 E5 订阅或具有高级合规性附加订阅的 E3 订阅。

- 将上载其非 Office 365 内容的所有保管人必须具有具有高级合规性附加许可证的 E3 许可证或拥有 E5 许可证。

- 现有的高级电子数据展示事例。

- 必须先将保管人添加到事例, 然后才能上载与它们相关联的非 Office 365 数据。

- 将上载的所有文件都必须位于文件夹中, 其中每个文件夹都与特定的保管人相关联。 这些文件夹的名称必须使用以下命名格式: *alias @ domainname*。 *别名 @ domainname*必须是用户的 Office 365 别名和域。 您可以将所有*别名 @ domainname*文件夹收集到一个根文件夹中。 根文件夹仅可包含*别名 @ domainname*文件夹;根文件夹中不允许出现松散文件。

   例如, 要上载的非 Office 365 数据的文件夹结构将类似于以下内容:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   其中, abraham.mcmahon@contoso.com、jewell.gordon@contoso.com 和 staci.gonzalez@contoso.com 是在这种情况下的保管人的 SMTP 地址。

   ![非 Office 365 数据上传文件夹结构](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- 既可以是电子数据展示管理器, 也可以是电子数据展示管理员的帐户

- 在有权访问非 Office 365 内容文件夹结构的计算机上安装了 Microsoft Azure 存储工具。

- 安装 AzCopy, 您可以从以下位置执行此操作:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>将非 Office 365 内容上载到高级电子数据展示

1. 作为电子数据展示管理器或电子数据展示管理员, 打开高级电子数据展示, 然后将非 Office 365 数据上载到的情况。  单击 "**查看集**" 选项卡, 然后选择要将非 Office 365 数据加载到的审阅集。  如果尚未创建审阅集, 现在可以执行此操作。  最后, 单击 "**管理审阅集**", 然后在 "* * 非 Office 365 数据" 磁贴中单击 "**查看上载**"。

2. 单击 "**上载文件**" 按钮以启动 "非 Office 365 数据导入向导"。

   ![上传文件](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. 向导中的第一步是为要上载的文件准备一个安全的 Azure blob。  准备完成后, 单击 "**下一步: 上传文件**" 按钮。

   ![非 Office 365 导入-准备](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. 在 "**上载文件**" 步骤中, 指定**文件位置的路径**, 这是您计划导入的非 Office 365 数据所在的位置。  设置正确的位置可确保正确更新 AzCopy 命令。

   > [!NOTE]
   > 如果尚未安装 AzCopy, 可以从以下位置执行此操作:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. 通过单击 "**复制到剪贴板**" 链接复制预定义命令。 启动 windows 命令提示符, 粘贴命令并按 enter。  将在下一步中将文件上载到安全 Azure blob 存储。

   ![非 Office 365 导入-上传文件](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   ![非 Office 365 导入 AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 如果提供的 AzCopy 命令失败, 请参阅[高级电子数据展示中的故障排除 AzCopy](troubleshooting-azcopy.md)

6. 最后, 返回到安全 & 合规性, 然后单击 "**下一步: 处理文件**" 按钮。  这将启动已上载文件的处理、文本提取和索引。  您可以在此处或在 "**作业**" 选项卡中跟踪处理进度。 完成后, 新文件将在审阅集中可用。  完成处理后, 可以关闭向导。

   ![非 Office 365 导入-处理文件](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)


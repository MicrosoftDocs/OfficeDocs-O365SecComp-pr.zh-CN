---
title: 将非 Office 365 数据加载到工作集
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
ms.openlocfilehash: 427b4c8c9dfffe351827a6869ae26a5356d646d8
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607460"
---
# <a name="load-non-office-365-data-into-a-working-set"></a>将非 Office 365 数据加载到工作集

您可能需要与 Office 365 高级电子数据展示分析的不是所有文档将都 live Office 365 中。与非 Office 365 内容导入高级电子数据展示可以上载不 live Office 365 中插入工作集以便与高级电子数据展示分析的文档中的功能。此过程展示如何进行分析的高级电子数据展示中引入非 Office 365 文档。

>[!Note]
>若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以注册 Office 365 企业版 E5 试用版。

## <a name="before-you-begin"></a>准备工作
此过程中所述使用上载非 Office 365 功能需要您具有：
* 使用高级合规性加载项或 E5 订阅 Office 365 E3
* 将上载其 Office 365 内容的所有管理员必须高级合规性加载项或 E5 许可证都已 E3
* 现有的电子数据展示事例
* 用于上载到文件夹其中没有 custodian 每个文件夹和文件夹的名称位于此格式*alias@domainname*中收集的所有文件。*Alias@domainname*必须是 Office 365 用户别名和域。您可以将所有*alias@domainname*文件夹都收集到根文件夹。根文件夹只能包含*alias@domainname*文件夹、 根文件夹中必须是没有松散文件
* 电子数据展示中管理器，也有权访问 Office 365 内容文件夹结构的计算机上安装的电子数据展示管理员 Microsoft Azure 存储工具的帐户。
* 安装 AzCopy，可以执行此操作从此处：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>将 Office 365 内容上载到高级电子数据展示
1. 为电子数据展示管理器或电子数据展示管理员中，打开高级电子数据展示，然后用例的非 Office 365 数据将上载到。 单击**处理设置**选项卡，然后选择您希望对非 Office 365 将数据加载的工作集。 如果尚未创建工作集，您可以现在完成操作。 最后，单击**管理工作原理设置**，则非 Office 365 数据部分中的**视图上载**

2. 单击**上载文件**按钮以启动非 Office 365 数据导入向导。

![上载文件](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. 在向导的第一步只需准备安全 Azure blob 要上载的文件。 Compelted 准备后，单击**下一步： 将文件上载**按钮。

![非 Office 365 导入-准备](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. 在**上载文件**步骤中，指定**文件位置的路径**，这是您导入计划的非 Office 365 数据所在的位置。 设置正确的位置可确保正确更新命令 AzCopy。

> [!NOTE]
> 如果尚未安装 AzCopy，您可以从此处执行此操作：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. 通过单击**复制到剪贴板**链接复制的预定义的命令。启动 windows 命令提示符处，粘贴命令并按 enter。 文件将上载到安全的 Azure blob 存储的下一步。

![非 Office 365 导入-上载文件](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 导入-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. 最后，将返回到安全 & 合规性，并单击**下一步： 处理文件**按钮。 这将启动处理，文本提取和上载文件的索引。 您可以跟踪进度的处理此处或在**作业**选项卡。 完成后，新文件中将提供工作集。 处理完成后，您可以关闭向导。

![非 Office 365 导入-处理文件](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)


---
title: 导入非 Office 365 内容以实现高级电子数据展示分析
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: '操作方法: 将未存储在 O365 中的内容导入到 Azure blob, 以便可以使用 AeD 对其进行分析'
ms.openlocfilehash: 7b7694754b26951aa02930fd101631ba9060bc17
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001165"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a>导入非 Office 365 内容以实现高级电子数据展示分析

并非所有可能需要使用 office 365 进行分析的文档都将在 office 365 中实时发布。 使用高级电子数据展示中的非 Office 365 内容导入功能, 可以将不在 Office 365 中的文档 (PST 文件除外) 上传到链接的大小写的 Azure 存储 blob, 并使用高级电子数据展示分析这些文档。 此过程向您演示如何将非 Office 365 文档转换为高级电子数据展示以进行分析。
  
> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
> [!NOTE]
> 您可以购买适用于非 Office 365 内容的 Office 365 高级电子数据展示数据存储附加订阅。 这仅适用于要使用高级电子数据展示进行分析的内容。 按照 "为[商业版购买或编辑和添加 office 365](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) " 中的步骤操作, 购买 office 365 高级电子数据展示存储加载项。 
  
## <a name="before-you-begin"></a>开始之前

如以下过程所述, 使用 "上载非 Office 365" 功能需要具备以下条件:
  
- 具有高级合规性外接程序或 E5 订阅的 Office 365 E3
    
- 将上载非 Office 365 内容的所有保管人必须具有具有高级合规性附加或 E5 许可证的 E3
    
- 现有电子数据展示事例
    
- 将用于上载的所有文件都收集到每个保管人都有一个文件夹的文件夹中, 文件夹的名称是格式*别名 @ domainname* 。 *别名 @ 域名*必须是用户 Office 365 别名和域。 您可以将所有*别名 @ domainname*文件夹收集到一个根文件夹中。 根文件夹只能包含*别名 @ domainname*文件夹, 根文件夹中不能有松散文件 
    
- 既可以是电子数据展示管理器, 也可以是电子数据展示管理员的帐户
    
- 在有权访问非 Office 365 内容文件夹结构的计算机上安装了[Microsoft Azure 存储工具](https://aka.ms/downloadazcopy)。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>将非 Office 365 内容上载到高级电子数据展示

1. 作为电子数据展示管理器或电子数据展示管理员, 打开**电子数据展示**, 并打开将向其上载非 Office 365 数据的大小写。 如果您需要创建一个事例, 请参阅[在 Office 365 安全&amp;合规中心中管理电子数据展示事例](manage-ediscovery-cases.md)
    
2. 单击 "**切换到高级电子数据展示**"
    
3. 在 "**源类型**" 下, 选择**非 Office 365 数据**。
    
4. 单击 "**添加容器**"。 命名容器并添加说明。
    
5. 从容器列表中选择新添加的容器, 并复制容器详细信息窗格中显示的 URL, 然后关闭窗格
    
6. 以管理员身份打开命令提示符, 并将目录更改为您在其中安装了 AzCopy 的文件夹。。
    
7. 构造 AzCopy 命令行以上载如下所示的文件:
    
    AzCopy/source: "*本地计算机上的根文件夹的完整路径*"/Dest: "上*的容器 URL, 但不包括？*  "/DestSAS:"*容器 url 的剩余部分 (来自？)到结尾*"/S。 
    
    例如, 使用以下值: 
    
  - 根文件夹-C:\Collected 数据 
    
  - 容器 url- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp; sr = c&amp;si = NonOfficeData15% 7C0&amp;sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3d
    
    AzCopy 命令行语法为:
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    有关 Azcopy 语法的详细信息, 请参阅[使用 Windows 上的 Azcopy 传输数据](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。 
    
    > [!IMPORTANT]
    > 每个用户必须有一个根文件夹, 并且文件夹名称必须采用*别名 @ domainname*格式。 
  
8. 文件夹完成上载后, 切换回高级电子数据展示。 您上载的文件夹中的内容现已准备就绪, 可以在高级电子数据展示中进行处理。 选择容器, 然后单击 "处理" 按钮。 有关高级电子数据展示处理的更多详细信息, 请参阅在[Office 365 高级电子数据展示中运行 Process module 和 load data](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
    
    > [!IMPORTANT]
    > 在高级电子数据展示中成功处理容器后, 您将无法再将新内容添加到 Azure 中的 SAS 存储。 如果要收集其他内容, 并且想要将其添加到高级电子数据展示分析的事例中, 则必须创建一个新的**非 Office 365 数据**容器, 并重复此过程。 
  
    > [!NOTE]
    > 如果*由于文件夹命名问题而导致容器未成功处理*, 并且您随后解决了这些问题, 您仍需使用本文中的过程创建一个新的容器, 并重新连接和上传。 
  


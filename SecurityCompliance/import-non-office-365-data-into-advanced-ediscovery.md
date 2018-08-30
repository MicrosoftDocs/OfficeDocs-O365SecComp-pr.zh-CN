---
title: 导入非 Office 365 内容以进行高级电子数据展示分析
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 5/25/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: 如何导入到 Azure 不存储 O365 中的内容的步骤 blob，以便它可以与 AeD 分析
ms.openlocfilehash: ab6c7ac76a159603a34719aa8edb51de3a4fabbb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526068"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a>导入非 Office 365 内容以进行高级电子数据展示分析

您可能需要与 Office 365 高级电子数据展示分析的不是所有文档将都 live Office 365 中。与非 Office 365 内容导入高级电子数据展示可以上载的文档，不到案例链接、 Azure 存储 blob live （除 PST 文件） 的 Office 365 中并对其进行分析与高级电子数据展示中的功能。此过程展示如何进行分析的高级电子数据展示中引入非 Office 365 文档。
  
> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
> [!NOTE]
> 您可以为 Office 365 内容购买 Office 365 高级电子数据展示数据存储加载项订阅。这是以独占方式可供使用高级电子数据展示要分析的内容。按照[购买或编辑和 Office 365 业务的加载项](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6)中的步骤和购买 Office 365 高级电子数据展示存储加载项。 
  
## <a name="before-you-begin"></a>准备工作

此过程中所述使用上载非 Office 365 功能需要您具有：
  
- 使用高级合规性加载项或 E5 订阅 Office 365 E3
    
- 将上载其 Office 365 内容的所有管理员必须高级合规性加载项或 E5 许可证都已 E3
    
- 现有的电子数据展示事例
    
- 用于上载到文件夹其中没有 custodian 每个文件夹和文件夹的名称位于此格式*alias@domainname*中收集的所有文件。*Alias@domainname*必须是 Office 365 用户别名和域。您可以将所有*alias@domainname*文件夹都收集到根文件夹。根文件夹只能包含*alias@domainname*文件夹、 根文件夹中必须是没有松散文件 
    
- 电子数据展示管理器或电子数据展示管理员的帐户
    
- 有权访问 Office 365 内容文件夹结构的计算机上安装[Microsoft Azure 存储工具](https://aka.ms/downloadazcopy)。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>将 Office 365 内容上载到高级电子数据展示

1. 为电子数据展示管理器或电子数据展示管理员中，打开**电子数据展示**，，然后打开的情况下，会将非 Office 365 数据上载到。如果您需要创建用例，请参阅[管理 Office 365 安全性的电子数据展示事例&amp;合规性中心](manage-ediscovery-cases.md)
    
2. 单击**切换到高级电子数据展示**
    
3. 在**源类型**下选择**非 Office 365 数据**。
    
4. 单击**添加容器**。命名该容器，并添加说明。
    
5. 从容器列表中选择新添加的容器和复制的 URL，容器的详细信息窗格中显示，然后关闭窗格
    
6. 打开命令提示符以管理员身份，并将目录更改到了 AzCopy 安装的文件夹。
    
7. 构造 AzCopy 命令行上载的文件，如下所示：
    
    AzCopy /Source:"*本地计算机上的根文件夹的完整路径*"/Dest:"*容器 URL 设置，但不是包括？* "/DestSAS:"*其余部分中的容器 url？到末尾*"/ s。 
    
    例如，使用以下值： 
    
  - 根文件夹-C:\Collected 数据 
    
  - 容器 url- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp; sr = c&amp;si = NonOfficeData15 %7c 0&amp;签名 = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA %三维
    
    将 AzCopy 命令行语法：
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    有关详细信息 Azcopy 语法请参阅[传输 Windows 上 AzCopy 数据](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。 
    
    > [!IMPORTANT]
    > 必须有一个根文件夹，每个用户和文件夹名称必须是*alias@domainname*格式。 
  
8. 文件夹完成上载后，切换回高级电子数据展示。现已准备好高级电子数据展示中处理您上载的文件夹中的内容。选择的容器，单击过程按钮。有关高级电子数据展示的详细处理的查看，[运行进程模块并加载 Office 365 高级电子数据展示中的数据](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
    
    > [!IMPORTANT]
    > 高级电子数据展示中成功处理容器之后, 将不再能够将新内容添加到 Azure 中的 SAS 存储。如果收集其他内容，并且您希望将其添加到为高级电子数据展示分析这种情况，您必须创建一个新的**非 Office 365 数据**容器并重复此过程。 
  
    > [!NOTE]
    > 如果容器*不处理成功由于文件夹命名问题*，并且您然后修复的问题，您将仍需要创建一个新的容器和重新连接并上载再次使用本文中的过程。 
  


---
title: 为 Office 365 高级电子数据展示准备搜索结果
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/10/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: 了解如何准备 Office 365 安全性内容的搜索结果的&amp;的进一步分析高级电子数据展示工具的合规性中心。
ms.openlocfilehash: 4e5668c88d62e99f7a5f40ed2e17f4687a7e9adb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526074"
---
# <a name="prepare-search-results-for-office-365-advanced-ediscovery"></a>为 Office 365 高级电子数据展示准备搜索结果

与 Office 365 安全性电子数据展示事例相关联的搜索后&amp;成功运行合规性中心，您可以准备进一步分析 Office 365 高级电子数据展示，该对话框可以分析大型，搜索结果非结构化的数据设置，并降低与法律案件相关的数据量。高级电子数据展示功能包括：
  
- **光学字符识别**-自动准备搜索结果的高级电子数据展示，光学字符识别 (OCR) 功能时从图像中提取文本和这包括与加载到的搜索结果高级电子数据展示进行分析。OCR 松散文件支持、 电子邮件附件，并嵌入图像。这样，您将高级电子数据展示 （近乎重复项、 电子邮件线程、 主题和预测编码） 的文本分析功能应用于图像文件中的文本内容。 
    
- **近乎重复检测**-允许您更有效地结构您数据进行审阅以便人审阅类似的文档的组。这有助于防止多个审阅者不必查看不同版本的同一文档。 
    
- **电子邮件线程**-可帮助您确定电子邮件主题中的唯一消息，使您可以集中在仅每条消息中的新信息。在电子邮件线程，第二个消息包含第一条消息。同样，更高版本的消息将包含所有前面的消息。电子邮件线程删除需要查看整个电子邮件线程中的每条消息。 
    
- **主题**-帮助您获得有关超出刚刚关键字搜索统计数据的价值。主题帮助调查由分组相关的文档，以便您可以查看的上下文中的文档。时使用主题，您可以查看相关的主题的一组文档、 确定任何重叠，然后确定的相关数据横截面。 
    
- **预测编码**-允许您培训上正在查找的内容，从而可以决定 （关于是否内容是相关或不） 的系统上的小型文档集。高级电子数据展示然后应用该学习 （基于您指南） 分析的所有数据集中文档时。基于该学习，高级电子数据展示提供相关性排名，以便您可以确定哪些文档查看基于哪些文档是最有可能与案例相关。 
    
- **导出的数据查看应用程序**的已完成您的分析，并降低数据集后，您可以从高级电子数据展示和 Office 365 导出数据。导出包包括 CSV 文件包含来自导出的内容并分析元数据属性。此导出包然后导入到电子数据展示查看应用程序。 
    
## <a name="before-you-begin"></a>准备工作

- 若要分析使用高级电子数据展示的用户的数据，用户 (数据的 custodian) 必须分配的 Office 365 E5 许可证。此外，可使用 Office 365 E1 或 E3 许可证的用户分配的高级电子数据展示独立许可证。管理员和合规部主管分配给情况下，并使用高级电子数据展示以分析数据不需要 E5 许可证。 
    
- 您必须是电子数据展示中管理器或 Office 365 安全性的管理员电子数据展示&amp;合规性中心以准备高级电子数据展示搜索结果。电子数据展示中管理器是电子数据展示管理员角色组的成员。电子数据展示管理员也是电子数据展示管理员角色组的成员，但已分配其他电子数据展示权限。有关分配管理员权限的电子数据展示的说明，请参阅[电子数据展示](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)的情况下，在 Office 365 安全性和合规性中心的步骤 1。
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a>步骤 1： 准备搜索结果的高级电子数据展示

您可以准备电子数据展示事例与相关联的搜索的结果。当您准备高级电子数据展示搜索结果时，并将数据上载临时存储在 Microsoft 云的唯一的 Windows Azure 存储区。此时是 OCR 功能从搜索结果中的图像中提取文本。在[步骤 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery)、 此文本和其他搜索结果数据中加载到中高级电子数据展示事例。
  
1. 安全中&amp;合规性中心，单击**搜索&amp;调查** \> **电子数据展示**案例列表中的显示您的组织中。 
    
2. 旁边的情况下，您想要准备分析高级电子数据展示中搜索结果中，单击**打开**。 
    
3. 在**主页**页为用例，单击**搜索**，然后选择搜索。
    
4. 在详细信息窗格中，在**与高级电子数据展示的分析结果**，单击**准备进行分析的结果**。
    
    > [!NOTE]
    > 如果搜索结果超过 7 天，将会提示你更新搜索结果。 
  
5. 在**准备进行分析的结果**页上，执行以下操作： 
    
    - 选择高级电子数据展示中的分析准备索引和未编制索引的项目或仅未编制索引的项目的索引的项。
    
    - 选择是否包括找到符合搜索条件的 SharePoint 上的文档的所有版本。此选项仅会显示搜索的内容源包括网站。
    
    - 指定是否希望一封通知邮件发送 （或复制） 到个人准备过程完成和已准备好高级电子数据展示中处理数据。
    
6. 单击**准备**。
    
    搜索结果准备好使用高级电子数据展示的分析。
    
7. 在细节窗格中，单击**检查准备状态**以显示有关准备过程的信息。准备过程完成后，您可以转到这种情况在高级电子数据展示处理分析的数据。 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a>步骤 2： 将搜索结果数据添加到在高级电子数据展示事例
<a name="step2"> </a>

完成准备工作后下, 一步是转到高级电子数据展示并加载与案例高级电子数据展示中搜索结果数据 （其中已上载到云中 Microsoft Azure 存储区）。如上文所述，访问您必须是电子数据展示管理员安全中的高级电子数据展示&amp;合规性中心或高级电子数据展示中的管理员。
  
> [!NOTE]
> 花费的时间的数据从安全&amp;合规性中心，以将其添加到在高级电子数据展示事例有所不同，具体取决于电子数据展示搜索的结果的大小。 
  
1. 安全中&amp;合规性中心，单击**搜索&amp;调查** \> **电子数据展示**案例列表中的显示您的组织中。 
    
2. 要加载中的数据到高级电子数据展示案例旁边，单击**打开**。 
    
3. 在**主页**页为用例，单击**高级电子数据展示**。 
    
    ![单击切换高级电子数据展示高级电子数据展示中打开这种情况](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    显示**连接到高级电子数据展示**进度栏。当您连接到高级电子数据展示时，将用例设置页上显示容器的列表。 
    
    ![用例显示在高级电子数据展示](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     这些容器表示您在步骤 1 中的高级电子数据展示中的分析准备好的搜索结果。请注意，容器的名称在的情况下，安全中有相同的名称搜索&amp;合规性中心。在容器列表中的准备。如果其他用户准备高级电子数据展示搜索结果，在相应的容器不会包含在列表中。 
    
4. 若要从容器中加载搜索结果数据，与在高级电子数据展示案例，选择容器，然后单击**过程**。
    
## <a name="next-steps"></a>后续步骤

后的结果的电子数据展示搜索被添加到种情况下下, 一步是使用高级电子数据展示工具分析数据，并确定特定法律案件做出迅速响应的内容。有关使用高级电子数据展示的信息，请参阅[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)。
  
## <a name="more-information"></a>详细信息

当准备高级电子数据展示中的分析时，将解密的搜索结果中包含任何 RMS 加密电子邮件。默认情况下，此解密功能启用的电子数据展示管理员角色组的成员。这是因为 RMS 解密管理角色分配给此角色组。注意有关解密邮件以下几点：
  
- 当前，此解密功能不包括来自 SharePoint 和 OneDrive for Business 站点加密的内容。当您将其导出时，将解密仅 RMS 加密电子邮件。
    
- 如果 RMS 加密电子邮件带有附件 （如文档或另一个电子邮件） 还加密的仅顶级电子邮件将被解密。
    
- 如果您需要防止他人解密 RMS 加密的邮件，准备进行分析高级电子数据展示中搜索结果时，您将需要 （通过复制内置电子数据展示管理员角色组） 中创建自定义角色组，然后删除 RMS解密自定义角色组中的管理角色。然后，添加您不想要自定义角色组的成员身份解密消息的人员。
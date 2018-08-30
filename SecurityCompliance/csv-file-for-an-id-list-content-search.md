---
title: 准备 CSV 文件的 ID 列表在 Office 365 中的内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/21/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: 从现有的内容搜索的 Results.csv 或未编制索引 Items.csv 文件用于创建返回特定的电子邮件 ID 列表搜索。ID 列表搜索通常用于返回部分索引的邮箱项目。
ms.openlocfilehash: 28e4a66e5c9be1817881004b1e4b3a3e6d4bfdb9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525799"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a>准备 CSV 文件的 ID 列表在 Office 365 中的内容搜索

您可以搜索特定邮箱的电子邮件和使用 Exchange Id 的列表的其他邮箱项目。若要创建 （正式称为目标的搜索） 的 ID 列表搜索，您可以提交标识要搜索的特定邮箱项目以逗号分隔的值 (CSV) 文件。对于此 CSV 文件可以使用**Results.csv**文件或将内容搜索结果导出或导出从内容搜索报告和现有的内容搜索时要包括的**未编制索引 Items.csv**文件。然后您编辑这些文件，以指示要搜索，然后创建一个新的 ID 列表搜索和提交 CSV 文件的特定项之一。 
  
下面是过程的创建 ID 列表搜索的快速概述。
  
1. 创建和运行安全中新的或指导性内容搜索&amp;合规性中心。
    
2. 将内容搜索结果导出或导出内容的搜索报告。有关详细信息，请参阅：
    
    - [从 Office 365 安全性导出内容的搜索结果&amp;合规性中心](export-search-results.md)
    
    - [导出内容搜索报告](export-a-content-search-report.md)
    
3. 编辑**Results.csv**文件或**未编制索引 Items.csv**并确定要在 ID 列表搜索中包括的特定邮箱项目。请参阅准备 ID 列表搜索 CSV 文件的[说明](#prepare-the-csv-file-for-an-id-list-search)。 
    
4. 创建新的 ID 列表搜索 （请参阅的[说明](#create-an-id-list-search)） 和提交准备 CSV 文件。创建搜索查询将仅搜索该 CSV 文件中选定的项目。
    
> [!NOTE]
> ID 列表搜索仅支持的邮箱项目。不能搜索 SharePoint 和 ID 中的 OneDrive 文档列表搜索。 
  
 **原因创建 ID 列表搜索？** 如果您无法确定基于**Results.csv**或**未编制索引 Items.csv**文件中的元数据的电子数据展示请求做出迅速响应项目时，您可以使用 ID 列表搜索来查找，预览，，然后将导出的项来确定如果它具有与您正在调查的案例响应。ID 列表搜索通常用于搜索并返回一组特定的未编制索引的项目。 
  
## <a name="prepare-the-csv-file-for-an-id-list-search"></a>准备 CSV 文件的 ID 列表搜索

导出的搜索结果或报表的内容搜索后，您可以执行以下步骤来准备 ID 列表搜索的 CSV 文件。此 CSV 文件将识别 ID 列表搜索中的所有项目。
  
请注意，您可以使用 CSV 文件从包含 SharePoint 网站和 OneDrive 帐户的搜索，但您可以选择*仅*ID 列表搜索的邮箱项目。如果您在 SharePoint 或 OneDrive 中选择一个文档，该 CSV 文件时创建 ID 列表搜索将失败验证。 
  
1. 在 Excel 中打开的**Results.csv**或**未编制索引 Items.csv**文件。 
    
2. 插入新列并将其命名为**选中**。并不重要插入列的位置。为方便起见，请考虑将其插入到第一列的左侧。
    
3. 在**选择**列中，键入**是**中的单元格对应于您想要搜索的项。对于您要搜索的每个项重复此步骤。 
    
    > [!IMPORTANT]
    > 当您在 Excel 中打开 CSV 文件时，**文档 ID**列的数据格式更改为**常规**。这将导致项目的文档 ID 显示科学记数法。例如，"481037338205"的 ID 显示为"4.81037E + 11"的文档必须执行的下一步步骤，将**文档 ID**列的数据格式更改为**号码**还原正确的格式的文档 id。如果您不执行此操作，使用 CSV 文件的 ID 列表搜索将失败。 
  
4. 右键单击整个**文档 ID**列中，选择**单元格格式**。
    
5. 在**类别**框中，单击**编号**。
    
6. 为**0**，更改的小数位数，然后单击**确定**以保存所做的更改。请注意，文档 ID 列中的值更改为号码。 
    
    下面是一个示例的已准备好进行 ID 列表内容搜索提交 CSV 文件。
    
    ![目标内容搜索 CSV 文件的示例](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)
  
7. 保存 CSV 文件或保存使用**另存为**具有不同的文件名称的文件。在这两种情况下，确保 CSV 格式保存文件。 
  
## <a name="create-an-id-list-search"></a>创建 ID 列表搜索

下一步是创建一个新的 ID 列表内容搜索并提交上一步中准备的 CSV 文件。
  
> [!IMPORTANT]
> 您应创建 ID 列表搜索不超过 2 天后从内容搜索导出的结果或报表。如果搜索结果，或报表在导出 2 天之前，您应重新导出的搜索结果或报表来生成更新的 CSV 文件。然后您可以准备一个更新后的 CSV 文件，并使用它来创建 ID 列表搜索。 
  
1. 安全中&amp;合规性中心中，转到**搜索&amp;调查** \> **内容搜索**。
    
2. 在**搜索**页上，单击箭头下一步为![添加图标](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新搜索**，然后单击**搜索按 ID 列表**。
    
    ![从新搜索下拉列表中单击搜索按 ID 列表](media/e65f9942-09b2-4127-865e-e64029a590df.png)
  
3. **按 ID 列表搜索**飞出，在名称搜索 （和 （可选） 描述），然后单击**浏览**并选择上一步骤中的准备 CSV 文件。 
    
    Office 365 尝试验证 CSV 文件。如果验证失败，将显示一条错误消息可帮助您解决验证错误。CSV 文件已成功验证创建 ID 列表搜索。
    
4. 后的 CSV 文件成功验证，单击**搜索**创建 ID 列表搜索。 
    
    下面是估计的搜索结果和生成的 ID 列表搜索查询的示例。
    
    ![在细节窗格中的目标内容搜索的搜索查询](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)
  
    请注意，估计 ID 搜索统计信息中显示的项目数应匹配在 CSV 文件中所选的项目数。
    
5. 预览或导出 ID 列表搜索返回的项。
    
> [!NOTE]
> 如果您创建的 ID 列表搜索后移动邮箱，搜索查询不会返回指定的项。这是因为邮箱移动时，会更改邮箱项目的**DocumentId**属性。在极少数实例邮箱移动时创建的 ID 列表搜索后，您应创建一个新的内容搜索 （或更新现有内容搜索的搜索结果），然后导出搜索结果或报告生成更新可用的 CSV 文件 若要创建一个新的 ID 列表搜索。 
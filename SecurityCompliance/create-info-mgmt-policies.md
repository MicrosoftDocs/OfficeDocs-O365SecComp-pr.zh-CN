---
title: 创建和应用信息管理策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
description: 信息管理策略，组织到多长时间保留内容、 审核人执行操作的内容，以及添加条形码控件或标签文档。策略可以帮助强制实施符合法律和政府法规或内部业务流程。作为管理员，您可以设置策略以控制如何跟踪文档和文档的保留多长时间。
ms.openlocfilehash: cc15b7d830e6c13e00045f7e4b672ac4a755a70e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525090"
---
# <a name="create-and-apply-information-management-policies"></a>创建和应用信息管理策略

信息管理策略，组织到多长时间保留内容、 审核人执行操作的内容，以及添加条形码控件或标签文档。策略可以帮助强制实施符合法律和政府法规或内部业务流程。作为管理员，您可以设置策略以控制如何跟踪文档和文档的保留多长时间。
  
您可以在网站层次结构，从最全面的三个不同的位置创建信息管理策略可以向最窄：
  
- 创建策略，以使用网站集中的多个内容类型。
    
- 创建网站内容类型的策略。
    
- 创建列表或库的策略。
    
有关详细信息，请参阅[Introduction to 信息管理策略](intro-to-info-mgmt-policies.md)。
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a>创建网站集内的多个内容类型的策略
<a name="__toc261001590"> </a>

以确保信息策略应用于网站集中特定类型的所有文档，请考虑在网站集级别创建策略，然后对内容类型更高版本应用策略。这些称为网站集策略。 
  
1. 在网站集主页上\>**设置**![标题栏上的 SharePoint 2016 设置按钮。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **网站设置**。
    
    中 SharePoint 组连接网站中，单击**设置**，单击**网站内容**，，然后单击**网站设置**。 
    
2. 在网站设置页上，在**网站集管理**下\>**内容类型策略模板**。 
  
![在网站设置页的内容类型策略模板链接](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. 在策略页上\>**创建**。 
    
4. 输入名称和说明策略，，然后编写简要策略声明到用户策略的用途的说明。
    
5. 创建网站内容类型以了解如何设置您想要与该策略关联的功能的策略，请参阅下一节。 
    
6. 选择"确定"。
    
## <a name="create-a-policy-for-a-site-content-type"></a>创建网站内容类型的策略
<a name="__create_a_policy"> </a>

向内容类型添加信息管理策略便于将策略功能与多个列表或库相关联。您可以选择将现有的信息管理策略添加到内容类型或创建一个唯一的策略的特定于单个内容类型。
  
 您还可以向特定于列表的内容类型添加信息管理策略。仅对该列表中的项目所使用的内容类型应用策略效果。 
  
1. 在网站集主页上\>**设置**![标题栏上的 SharePoint 2016 设置按钮。](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **网站设置**。
    
    中 SharePoint 组连接网站中，单击**设置**，单击**网站内容**，，然后单击**网站设置**。 
    
2. 在网站设置页上，在**Web 设计器库**下\>**网站内容类型**。
  
![在网站设置页的网站内容类型链接](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. 在网站内容类型设置页上，选择您想要添加到策略的内容类型。
    
4. 在网站内容类型页上的在**设置**下， \> **信息管理策略设置**。
    
5. 在编辑策略页上输入的名称和说明策略，然后写入到用户策略的用途的说明的简要说明。
    
6. 在下一步部分，选择您想要添加到您的信息管理策略的各个策略功能。 
  
![类型的内容的策略](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. 若要指定的文档和项受此策略的保留期，选择**启用保留**，然后指定保持期，以及您想要项目到期时，会发生的操作。
    
    指定保留期
    
||||||**1。**|* * 选择 * * 添加记录的保留阶段...***|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> | 选择一个保留期选项以指定文档或项设置过期。请执行以下任一操作：<br/>  若要设置的到期日期，根据日期属性，在**事件** \> **此阶段基于关闭日期属性的项**，然后选择的文档或项目的操作 （例如，创建或修改） 并在此操作 （的时间增量例如的天数、 月数或年数） 当您想要过期的项。  <br/>  若要使用自定义保留公式来确定有效期限，请选择**此服务器上安装自定义保留公式来设置**。  <br/> > [!NOTE]> 此选项才可用，如果您的管理员已设置的自定义公式。           |
||||||3.  <br/> |**启动工作流**选项是您要定义列表、 库或已具有与其关联的工作流的内容类型的策略时，才可用。然后是根据选择的工作流可供选择。<br/> |
||||||4.  <br/> |在**重复**部分中，选择**重复此阶段的操作...** 然后输入您希望再次出现的操作的频率。  <br/> > [!NOTE]> 此选项才可用可以重复您选择的操作。例如，不能设置定期**永久删除**操作。           |
||||||5.  <br/> |选择**确定**。  <br/> |
   
1. 若要启用审核的文档和受到此策略的项目，选择**启用审核**，并指定您想要审核的事件。
    
    若要启用审核
    
||||||1.* * *|在编辑策略页上 * ***下****审核** **\>** **启用审核*** *，然后选择您想要保留审核的事件旁边的复选框尾 for.* * *|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2。** <br/> |**若要提示用户插入到文档，这些条码****选择****插入条码保存或打印前的，提示用户****.** <br/> |
||||||**3。** <br/> |**选择****确定*** * 若要将审核功能应用于此策略。 ** <br/> |
|||||||审核策略功能，组织可以创建并分析审核跟踪对文档和列表项，如任务列表、 问题列表、 讨论组和日历。此策略功能提供的审核日志将记录事件，如时查看、 编辑或删除内容。  <br/> |
|||||||启用审核后信息管理策略的一部分，管理员可以查看审核数据的基于 Microsoft Excel 中并的汇总当前使用的策略使用率报告中。管理员可以使用这些报告，以确定信息组织内使用的方式。这些报告还有助于组织验证并记录其法规或研究潜在的问题。  <br/> |
|||||||审核日志可记录以下信息：事件名称、事件的日期和时间以及执行操作的用户的系统名称。  <br/> |
   
1. 启用条码后的策略的一部分，它们添加到文档属性和条形码应用于文档的页眉区域中显示。标签，如条码可以也是手动删除从文档。您可以指定是否包含条形码打印或保存项目时是否应提示用户或如果应手动插入条码 2010年中使用**插入**选项卡 Office release 程序。 
    
    若要启用条码
    
||||||1.* * *|**在编辑策略页的**条码**\> **启用条码**。**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2。** <br/> |提示用户进行这些条码插入到文档中，选择**插入条码保存或打印前的，提示用户**。  <br/> |
||||||**3。** <br/> |选择**确定**以应用于此策略的条码功能。  <br/> |
|||||||
 条码策略会生成代码 39 标准条码。每个条码图像包括下面表示条码值的条形码符号的文字。这样，即使扫描硬件不可用时要使用的条码数据。用户可以手动在搜索框中，若要找到网站上的项目键入条码编号。  <br/> |
   
1. 若要要求受此策略制约的文档具有标签、 选择**启用标签**，然后指定所需的标签的设置。
    
    若要启用标签
    
||||||**1。**|* * 到要求用户添加到文档的标签，请选择**提示用户保存或打印前插入标签**。  <br/> > [!NOTE]> 如果您希望标签为可选，不要选中此复选框。        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> |要锁定标签，以便它不能更改其插入后，请选择**标签添加标签后禁止更改标签**。  <br/>  此设置可防止更新后标签插入如 Word、 Excel 或 PowerPoint 的客户端应用程序内的项目的标签文本。如果您希望更新该文档或项目的属性时要更新的标签，请不选中此复选框。<br/> |
||||||3.  <br/> |在标签格式框中，根据需要对显示，为标签输入的文本。标签可以包含最多 10 个列引用，其中每个可以最多 255 个字符。若要创建的格式为您的标签，请执行以下操作：  <br/> 键入您想要在其中您希望其出现的顺序在标签中包括的列的名称。将列名称括在大括号 ({})、 编辑策略页上的示例中所示。  <br/> 在编辑策略页上的示例所示，请键入单词以确定在括号外的列。  <br/> |
||||||4.  <br/> |若要添加换行符， **\n**输入您希望出现换行符。  <br/> |
||||||5.  <br/> |选择的字体大小和型，它指定是否希望标签置于左、 中心，还是文档中的权限。  <br/>  选择字体和用户的计算机可用的样式。字体的大小会影响多少文本可显示标签上。  <br/> |
||||||6.  <br/> |输入高度和标签的宽度。标签高度为 20 英寸，可以从.25 英寸范围和标签宽度的范围可以从.25 英寸为 20 英寸。标签文本标签 image 内始终垂直居中。  <br/> |
||||||7.  <br/> |选择**刷新**以预览的标签内容。  <br/> |
   
1. 选择"确定"。
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a>为列表、库或文件夹创建策略（基于位置的保留策略）
<a name="__create_a_policy"> </a>

您可以定义仅适用于特定列表、 库或文件夹的保留策略。但是，如果这种方式创建保留策略，不能重新使用在其他列表、 库、 文件夹或网站，此策略，并且无法将网站集策略应用于基于位置策略。
  
如果您想要将单个保留策略应用于所有类型的单个位置中的内容，很可能需要使用基于位置的保留期。在大多数其他情况下，要验证的所有内容类型指定保留策略。
  
 每个子文件夹继承其父级的保留策略，除非您选择要断开继承并定义新的保留策略子级别。 
  
如果您想要对列表或库中定义信息管理策略保留之外，您需要定义与列表或库关联的每个单独的列表内容类型的信息管理策略。
  
 如果在任何点决定从内容类型切换到基于位置的列表或库的策略，只保留策略将用作基于位置的策略。将从关联的内容类型继承的所有其他管理策略 （审核、 条码，和条码）。 
  
 可以停用的库和文件夹基于保留功能，为网站集禁用基于位置策略。这样，网站集管理员，以确保其内容类型策略不重写的列表管理员基于位置策略。 
  
您至少需要管理列表权限若要更改列表或库的信息管理策略设置。
  
1. 导航到您要为其指定信息管理策略的列表或库。 
    
2. 在功能区中，选择**库**或**列表**选项卡\>**库设置**或**列表设置**。
    
    在 SharePoint Online 中，单击**设置**，然后单击**列表设置**或**库设置**。 
    
3. 在**权限和管理**下\>**信息管理策略设置**。
  
![在文档库设置页面上的信息管理策略链接](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. 在信息管理策略设置页上，确保保留列表或库的源，设置为库和文件夹。 
  
如果**内容类型**显示为源，单击**更改源**，然后单击**库和文件夹**。提醒您将被忽略内容类型保留策略。选择**确定**。 
    
5. 在编辑策略页上的在**库基于保留计划**，下，输入要创建的策略的简要说明。 
    
6. 选择**添加保留阶段...**
    
     请注意，在下记录，您可以选择通过选择记录选项定义不同的保留阶段中定义的记录的不同的保留策略。 
    
7. 在容器属性对话框，选择保留期选项，以指定文档或项目都设置为时过期。请执行以下任一操作：
    
  - 若要设置的到期日期，根据日期属性，在**事件** \> **此阶段基于关闭日期属性的项**，然后选择的文档或项目的操作 （例如，创建或修改） 并在此操作 （的时间增量例如的天数、 月数或年数） 当您想要过期的项。 
    
  - 若要使用自定义保留公式来确定有效期限，请选择**此服务器上安装自定义保留公式来设置**。 
    
    > [!NOTE]
    >  此选项才可用，如果您的管理员已设置的自定义公式。 
  
  - 在**操作**指定您想要在文档或项过期时执行。若要启用的文档或项目 （例如删除） 的特定操作，请从列表中选择一个操作。 
    
8. **启动工作流**选项是您要定义列表、 库或已具有与其关联的工作流的内容类型的策略时，才可用。然后是根据选择的工作流可供选择。 
    
9. 在**定期**，下选择**重复此阶段的操作...** 然后输入您希望再次出现的操作的频率。 
    
    > [!NOTE]
    >  此选项才可用可以重复您选择的操作。例如，不能设置定期**永久删除**操作。 
  
10. 选择"确定"。
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a>适用于内容类型的网站集策略
<a name="__apply_a_site"> </a>

如果信息管理策略已创建网站作为网站集策略，您可以向内容类型应用策略之一。通过执行此操作，您可以将相同的策略应用于多个内容类型在网站集中不共享相同的父内容类型的。
  
 如果您想要将策略应用于网站集中的多个内容类型，并且必须配置 Managed Metadata Service，可以使用内容类型发布出发布信息管理策略到多个网站集。请参阅[应用到跨网站集的内容类型策略](create-info-mgmt-policies.md#__apply_a_policy)的详细信息的部分。 
  
1. 导航到列表或库，其中包含您要向其应用策略的内容类型。
    
2. 在功能区中，选择**库**或**列表**选项卡\>**库设置**或**列表设置**。
    
    在 SharePoint Online 中，单击**设置**，然后单击**列表设置**或**库设置**。 
    
3. 在**权限和管理**下\>**信息管理策略设置**。
  
![在文档库设置页面上的信息管理策略链接](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. 验证策略源设置为**内容类型**，并在**内容类型策略**选择您想要应用该策略的内容类型。 
    
5. 在**指定策略**下\>**使用网站集策略**，然后选择要应用列表中的策略。 
    
    > [!NOTE]
    >  如果**使用的网站集策略**选项不可用，任何网站集策略具有已不定义的网站集。 
  
6. 选择"确定"。
    
     如果列表或库您正在使用支持多种内容类型进行管理，在**内容类型**下您可以选择要为其指定信息管理策略的内容类型。这会将您导引直接向上方的步骤 5。 
    
## <a name="apply-a-policy-across-site-collections"></a>将策略应用跨网站集
<a name="__toc260646789"> </a>

使用托管元数据服务应用程序设置内容类型发布跨网站集共享内容类型。发布的内容类型可帮助您管理内容和元数据始终在网站之间因为可以创建和集中，更新内容类型，可以将更新出发布到多个订阅的网站集或 Web 应用程序。
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a>从现有的策略，以使用跨网站集创建模板
<a name="__toc262125409"> </a>

您可以定义信息管理策略，然后从它使用所需跨多个网站集创建模板。如果您想要备份的信息策略，或还可作为的备用方法的内容类型发布使用跨网站集应用一个策略，则可以使用此方法。到另一个网站集从一个网站集中导出策略，然后导入其到保存位置或创建的是模板或策略的备份。
  
> [!IMPORTANT]
>  如果您使用导出/导入功能作为一种使一组策略模板的方式，请记住，策略.xml 文件中存在的唯一标识符。因此，您无法导入该策略网站多次而不更改此唯一标识符。 
  
### <a name="export-a-policy"></a>导出策略
<a name="__toc260646790"> </a>

1. 在网站集主页上，选择**设置**![发生的网站设置的小型设置齿轮。](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **网站设置**。
    
    中 SharePoint 组连接网站中，单击**设置**，单击**网站内容**，，然后单击**网站设置**。 
    
2. 在网站设置页上，在**网站集管理**下\>**内容类型策略模板**。 
  
![在网站设置页的内容类型策略模板链接](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. 选择您想要导出的策略\>滚动到底部\>**导出**。
    
4. 在提示符处保存或打开该文件，选择**保存**，，然后选择保存到文件位置。请务必选择可供导入的策略的网站集的位置。
    
5. 显示下载完毕对话框中，选择**关闭**。
    
### <a name="import-a-policy-to-a-different-site-collection"></a>导入到不同的网站集的策略
<a name="__toc260646791"> </a>

导入的信息管理策略，可以将其应用于多个内容类型在任何给定的网站集内网站或列表级别。此操作的好处是两种： 您无需重新定义并对每个内容类型应用策略和您可以更轻松地管理策略修改，通过更改只需一个位置中的策略。
  
1. 在您要向其应用策略的网站集的主页上，选择**设置**![发生的网站设置的小型设置齿轮。](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **网站设置**。
    
    中 SharePoint 组连接网站中，单击**设置**，单击**网站内容**，，然后单击**网站设置**。 
    
2. 在网站设置页上，在**网站集管理**下\>**内容类型策略模板**。
    
3. 在策略页上\>**导入** \> **浏览**以找到该 XML 文件的策略。 
    
4. 选择在其中保存策略的 XML 文件\>**打开**。 
    
5. 在导入网站集策略页上\>**导入**策略添加到网站集。 
    
现在，您导入的策略都可以应用于网站或列表级别的一个或多个内容类型。 
  
[信息管理策略，组织到多长时间保留内容、 审核人执行操作的内容，以及添加条形码控件或标签文档。策略可以帮助强制实施符合法律和政府法规或内部业务流程。作为管理员，您可以设置策略以控制如何跟踪文档和文档的保留多长时间。您可以在网站层次结构，从最全面的三个不同的位置创建信息管理策略可以向最窄： 创建策略，以使用网站集中的多个内容类型。创建网站内容类型的策略。创建列表或库的策略。有关详细信息，请参阅 Introduction to 信息管理策略。](create-info-mgmt-policies.md#__top)
  

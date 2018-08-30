---
title: PST 文件导入到 Office 365 时筛选数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 26af16df-34cd-4f4a-b893-bc1d2e74039e
description: '使用 Office 365 导入服务中的新的智能导入功能实际上获取导入到的目标邮箱的项进行筛选。智能导入让您主动决定哪些数据导入和要保留的内容。智能导入的数据，正在导入到 Office 365 还提供见解。 '
ms.openlocfilehash: 723a2e05a1f5d256e99bcf8497643435d0c98a23
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524815"
---
# <a name="filter-data-when-importing-pst-files-to-office-365"></a>PST 文件导入到 Office 365 时筛选数据

使用 Office 365 导入服务中的新的智能导入功能筛选实际上获取导入到的目标邮箱的 PST 文件中的项目。下面是它的工作原理：
  
- 创建和提交 PST 导入作业后，PST 文件上载到云中 Microsoft Azure 存储区。
    
- Office 365 标识的邮箱项目和 PST 文件中包含的其他消息类型的年龄，以安全方式，分析 PST 文件中的数据。
    
- 当完成分析，并已准备好导入数据时，您可以选择要导入或修整通过设置控制哪些数据获取导入的筛选器导入的数据的 PST 文件中的所有数据。例如，您可以选择：
    
  - 导入仅存在一定时间的项目。
    
  - 导入所选的消息类型。
    
  - 排除由特定人员发送或接收的消息。
    
- 配置筛选设置后，Office 365 导入符合筛选条件在导入作业中指定的目标邮箱数据。
    
下图显示了智能导入过程，并突出显示所执行的任务和执行 Office 365 的任务。
  
![Office 365 中的智能导入过程](media/f2ec309b-11f5-48f2-939c-a6ff72152d14.png)
  
## <a name="before-you-begin"></a>准备工作

- 本主题中的步骤假定您已创建 PST 导入作业导入 Office 365 服务中使用网络上载或驱动器传送。有关分步说明，请参阅以下主题：
    
  - [使用网络上载将 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md)
    
  - [使用驱动器寄送，将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- 使用网络上载创建导入作业后，Office 365 安全性页面上导入的导入作业的状态&amp;合规性中心设置为**正在进行中的分析**，这意味着 Office 365 正在分析 PST 文件中的数据的上载。单击**刷新**![刷新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)更新导入作业的状态。 
    
- 对于传送导入作业的驱动器，将进行数据分析 Office 365 后 Microsoft 数据中心人员收到您的硬盘，并将 PST 文件上载到您的组织的 Azure 存储区。
  
## <a name="filter-data-that-gets-imported-to-mailboxes"></a>筛选获取导入到邮箱的数据

您已创建后 PST 导入作业，请按照以下步骤之前将其导入 Office 365 筛选数据。
  
1. 转到[https://protection.office.com/](https://protection.office.com/)和使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. Office 365 安全性的左窗格中&amp;合规性中心，单击**数据调控** \> **导入**。
    
    在**导入**页列出了您的组织的导入作业。请注意，**状态**列中的**分析已完成**值指示已分析的 Office 365 并且可供您导入的导入作业。 
    
    ![分析完成状态指示 Office 365 具有分析 PST 文件中的数据](media/de5294f4-f0ba-4b92-a48a-a4b32b6da490.png)
  
3. 要完成的导入作业，单击**已准备好到 Office 365 导入**。 
    
    飞出页将显示有关 PST 文件的信息以及其他信息导入作业。
    
4. 单击**导入到 Office 365**。
    
    显示**筛选数据**页。它包含有关导入作业，包括有关数据的期限的 PST 文件中的数据的数据见解。 
    
    ![筛选器数据页显示的 PST 文件导入作业的数据见解](media/3b537ec0-25a4-45a4-96d5-a429e2a33128.png)
  
5. 基于您是否想要裁剪数据导入到 Office 365 中，在**您需要筛选数据？**，执行下列操作之一：
    
    答： 单击**是，我希望筛选其导入前**要裁剪您导入的数据，然后单击**下一步**。
    
    **Office 365 逐页导入数据**页将显示从 Office 365 执行分析的详细的数据见解。 
    
    ![Office 365 显示详细的数据洞察力 PST 文件与其分析](media/4881205f-0288-4c32-a440-37e2160295f2.png)
  
    此页上的图显示了将导入的数据量。图中显示有关 PST 文件中找到的每个邮件类型的信息。您可以将光标悬停在每个栏以显示有关该消息类型的特定信息。此外，还有不同期限值基于对 PST 文件的分析的下拉列表。当下拉列表中选择年龄时，图表将更新以显示将为所选的年龄导入数据量。 
    
    b.若要配置添加筛选器以减少的导入的数据量，请单击**更多的筛选选项**。
    
    ![在更多选项页，用以调整导入的数据配置筛选器](media/3f8d68c3-3fe2-4b4e-9488-b368b98fa9fe.png)
  
    您可以配置这些筛选器：
    
      - **期限**-年龄，以便更高的指定期限的唯一项都将被导入的选择。请参阅关于 Office 365 如何确定**期限**筛选器的时间跨度说明的[详细信息](filter-data-when-importing-pst-files.md#moreinfo)部分。 
    
      - **类型**-此部分显示已导入作业的 PST 文件中找到的所有消息类型。您可以取消选中要排除的消息类型旁边的框。请注意，不能排除的其他消息类型。请参阅其他类别中包括的邮箱项目列表的[详细信息](filter-data-when-importing-pst-files.md#moreinfo)部分。 
    
      - **用户**-可以排除发送或接收的特定的某个人的邮件。要排除 From 中显示的人员： 字段中，为： 字段中，或抄送： 字段的邮件，单击**排除的用户**旁边的收件人类型。键入此人的电子邮件地址 （SMTP 地址），单击**添加**![图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)将其添加到的收件人类型，排除的用户列表，然后单击**保存**以保存排除的用户的列表。 
    
        > [!NOTE]
        > Office 365 不显示数据见解所产生的设置的**人员**筛选器。但是，如果将此筛选器中排除由特定人员发送或接收的消息，这些消息将排除在实际导入过程。 
  
    c.**更多筛选选项**飞出要保存筛选器设置页中单击**应用**。 
    
    在**到 Office 365 的导入数据**页上的见解基于筛选器设置进行更新的数据，包括将导入的数据的总量基于筛选器设置。请注意，还显示筛选器设置摘要。可以更改设置，如有必要的筛选器旁边单击**编辑**。 
    
    ![基于筛选器设置进行更新数据见解](media/897e20fb-3b13-44c3-9d56-9f330750f2a3.png)
  
    d.单击**下一步**。
    
    将显示的状态页，其中显示筛选器设置。同样，您可以编辑的任何筛选器设置。
    
    e.单击**导入数据**以开始导入。请注意，将显示的总将导入的数据量。 
    
    或
    
    答： 单击**否，我想要导入所有**PST 文件中的所有数据导入到 Office 365，然后单击**下一步**。
    
    b.在**导入到 Office 365 的数据**页上，单击**导入数据**开始导入。请注意，将显示的总将导入的数据量。 
    
6. 在**导入**页上，单击**刷新**![刷新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)。导入作业的状态显示在**状态**列中。 
    
7. 单击导入作业以显示更多详细的信息，如针对每个 PST 文件和配置的筛选器设置的状态。

  
## <a name="more-information"></a>详细信息

- Office 365 是如何确定期限筛选器的增量的？当 Office 365 分析 PST 文件时，它查找在每个项目的已发送或接收的时间戳 （如果项具有两个发送和接收时间戳，处于选中状态的最早日期）。然后 Office 365 的时间戳的年值查看并比较为当前日期确定项目的时间。这些岁然后用作**期限**筛选器下拉列表中的值。例如，如果 PST 文件具有 2016年、 2015，和 2014 年的消息，则**期限**筛选器中的值将为**1 年**、 **2 年**和**3 年**可以。
    
- 下表列出的**其他**类别中的**更多选项**飞出页上的**类型**筛选器包含邮件类型 （请参阅上一过程中的步骤 5b）。目前，不能到 Office 365 中导入 Pst 时排除"其他"类别中的项目。 
    
    |**邮件类标识符**|**使用此邮件类的邮箱项目**|
    |:-----|:-----|
    |IPM。活动  <br/> |日记条目  <br/> |
    |IPM。文档  <br/> |文档和文件 （不附加到电子邮件）  <br/> |
    |IPM。文件  <br/> |（IPM 相同。文档）  <br/> |
    |IPM。Note.IMC.Notification  <br/> |通过 Internet Mail 连接，这是到 Internet 的 Exchange Server 网关发送的报告  <br/> |
    |IPM。Note.Microsoft.Fax  <br/> |传真消息  <br/> |
    |IPM。Note.Rules.Oof.Template.Microsoft  <br/> |外出自动答复邮件  <br/> |
    |IPM。Note.Rules.ReplyTemplate.Microsoft  <br/> |发送的收件箱规则的答复  <br/> |
    |IPM。OLE。类  <br/> |定期系列的例外  <br/> |
    |IPM。Recall.Report  <br/> |邮件撤回报告  <br/> |
    |IPM。远程  <br/> |远程邮件  <br/> |
    |IPM。报告  <br/> |项目状态报告  <br/> |

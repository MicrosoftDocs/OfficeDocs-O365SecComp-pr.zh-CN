---
title: 向高级电子数据展示 (预览) 案例中添加保管人
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
ms.openlocfilehash: fe208f4a9f7927d8481d5c6ec8b901baafb98626
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243542"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a>向高级电子数据展示 (预览) 案例中添加保管人

使用高级电子数据展示 (预览版), 您可以利用内置的保管人管理工具在工作流周围管理保管人, 并在事例中识别相关的 custodial 数据源。 当您添加管理员时, 系统可以自动识别其主 Exchange 邮箱和 OneDrive for business 网站上的, 并将其置于保留中。 在您进行发现时, 您可能还会发现并映射在过去或团队中, 管理员在今天的成员处访问的其他邮箱或网站。

使用以下工作流在安全 & 合规中心内的高级电子数据展示 (预览版) 案例中添加和管理保管人。 

![保管人管理选项卡](../media/CustodianMgtPage.png)


## <a name="step-1-identify-potential-custodians"></a>步骤 1: 确定潜在保管人

第一步是确定适当的保管人, 以了解你的事宜。 若要将保管人添加到案例, 您必须是电子数据展示管理器或电子数据展示管理员角色组的成员。   

![确定潜在保管人](../media/AddCustodianStep1.png)

将保管人添加到现有的高级电子数据展示 (预览版) 案例:

1. 在 "**高级电子数据展示 (预览)** " 页上, 转到您的案例。
 
2. 选择了事例后, 转到 "**保管人**" 选项卡, 然后单击 " **+ 添加保管人**"。 
 
3. 选择要添加到事例的保管人。 您可以通过键入搜索并从组织的 Azure Active Directory 中选择用户来开始。
 
4. 完成保管人列表后, 单击 "**下一步**" 以开始标识潜在的数据源。 
  
## <a name="optional-step-2-select-custodian-data-sources"></a>Optional步骤 2: 选择保管人数据源

向事例添加了保管人后, 可以利用 Office 365 来帮助您识别和保留主保管人数据源。 此工作流中的下一步是选择在步骤1中指定的保管人所拥有的数据源。 

![选择 Custodial 数据源](../media/AddCustodianStep2.png)

若要确定保管人数据源, 请执行以下操作: 

1. 对于每个保管人, 如果希望系统自动识别和添加管理员的主 Exchange 邮箱, 请选择 " **Exchange** "。 
 
2. 对于每个保管人, 如果希望系统自动识别和添加保管人的主 OneDrive URL, 请选择 " **OneDrive** "。 

    做出选择后, 系统会自动尝试识别数据源并将其添加到你的事例。
 
4. 单击 "**下一步**" 开始将其他数据源映射到你的保管人。

## <a name="optional-step-3-map-additional-data-sources"></a>Optional步骤 3: 映射其他数据源

根据您的情况, 您可能还需要添加给定的用户可以在过去使用的邮箱、保管人当前是其成员的组, 或者是保管人对过去有权访问的网站。 除了主保管人数据源之外, 还可以向保管人或利用 office 365 添加其他 Office 365 数据源, 以帮助您识别潜在的相关数据源。 

![映射其他数据源](../media/AddCustodianStep3.PNG)

若要将邮箱、网站或团队映射到特定保管人, 请执行以下操作:
1. 选择 "**添加**", 将内容位置 (如邮箱、网站和工作组) 分配给特定的保管人。 

2. 在浮出控件中, 指定以下![内容: 映射数据源](../media/AddCustodianStep4.PNG)
  -  **Exchange 邮箱**-单击 "**选择用户、组或团队**", 然后再次单击 "**选择用户、组或团队**"。 若要指定要分配给选定的保管人的邮箱, 请使用搜索框查找用户邮箱和通讯组。 您还可以为 Office 365 组或 Microsoft 团队分配相关联的邮箱。 选中 "用户、组、团队" 复选框, 单击 "**选择**", 然后单击 "**完成**"。

        > [!NOTE]
        > 当您单击 "选择用户、组或团队以指定邮箱" 时, 显示的邮箱选取器为空。 这种设计旨在增强性能。 若要将人员添加到此列表, 请在搜索框中键入一个名称 (至少3个字符)。
     
     - **SharePoint 网站**-单击 "**选择网站**", 然后再次单击 "**选择网站**", 以指定要分配给选定的管理员的其他 SharePoint 和 OneDrive for business 网站。 您还可以为 Office 365 组或 Microsoft 团队添加 SharePoint 网站的 URL。 键入要分配的每个网站的 URL。 单击 "**选择**", 然后单击 "**完成**"。
     - **Microsoft 团队**–单击 "**选择团队**", 然后再次单击 "**选择团队**", 查看保管人所属的 Microsoft 团队组列表。 选择您想要添加到您的管理员的团队。 选择后, 系统将自动识别 &。选择与该 Microsoft 团队关联的关联 SharePoint 网站和组邮箱。 单击 "**选择**", 然后单击 "**完成**"。
        
      > [!NOTE]
      > 若要添加其他 Microsoft 团队, 您需要单独添加邮箱和 SharePoint 网站, 如上所示。

完成源映射后, 可以查看您刚刚添加的保管人的邮箱、网站和团队总数。 完成与特定保管人相关的数据源后, 此映射将被维护并扩展到电子数据展示集合、处理和审阅工作流。 

## <a name="optional-step-4-place-custodians-on-hold"></a>Optional步骤 4: 将保管人置于保留状态

![就地保留](../media/AddCustodianStep5.PNG)

完成要添加到您的保管人的保管人和数据源后, 您可以选择将某些或所有保管人置于保留状态。 当您将保管人置于保留状态时, 映射到该用户的内容将一直保留, 直到您从案例中释放该保管人或删除保留。 在某些情况下, 您可能需要将保管人添加到事例中, 而无需将其置于保留状态。 

将所选的保管人和数据源置于保留状态:

1. 验证您的保管人选择, 并选中复选框以将每个保管人置于保留状态。 将管理员置于保留状态后, 将自动创建包含所有 custodial 源的保管人保留策略。 如果未选中此选项, 则会将保管人和所选数据源添加到该事例中, 但不会保留内容。

2. 转到 "**保留**" 选项卡, 然后选择 "**保管人保留" 策略**。 

3. 单击 "**编辑**" 查看所有选定的保管人数据源。

   

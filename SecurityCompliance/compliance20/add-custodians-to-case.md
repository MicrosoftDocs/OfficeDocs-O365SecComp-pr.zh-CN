---
title: 向高级电子数据展示 （预览） 用例添加管理员
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
ms.openlocfilehash: d9a7dc6b1c2eeffdcd49be64d1d09d4a2bda782b
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607463"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a>添加管理员的高级电子数据展示 （预览） 案例

使用高级电子数据展示 （预览），您可以利用内置 custodian 管理工具，来协调围绕管理管理员和标识相关、 监控数据源中种情况下工作流。添加管理员后，系统可以自动标识，并进行业务网站保留在其主 Exchange 邮箱和 OneDrive。为您执行您发现，您可能还发现并映射其他邮箱或网站的管理员访问过去或团队中管理员是今天的成员。

使用以下工作流添加和管理在高级电子数据展示 （预览） 情况下，安全 & 合规中心内的管理员。 

## <a name="step-1-identify-potential-custodians"></a>步骤 1： 确定潜在的管理员

第一步是确定您的专家的相应的管理员。若要添加到案例的管理员，您必须是成员的电子数据展示管理员或电子数据展示管理员角色组。   

将管理员添加到现有高级电子数据展示 （预览） 用例：

1. 从**高级电子数据展示 （预览）** 页上，转到您的案例。
 
2. 选择了一个案例后，转到**管理员**选项卡，然后单击 **+ 添加 Custodian**。 
 
3. 选择您想要添加到案例管理员。您可以开始通过键入以下内容搜索并从组织的 Azure Active Directory 中选择的用户。
 
4. 已完成的管理员列表后，单击**下一步**开始识别潜在的数据源。 
   
## <a name="optional-step-2-select-custodian-data-sources"></a>（可选）步骤 2： 选择 custodian 数据源

为大写添加管理员后，您可以利用 Office 365，可帮助您确定并保留主 custodian 数据源。此工作流的下一步是选择在步骤 1 中指定管理员所拥有的数据源。 

标识 custodian 数据源： 

1. 如果您希望系统自动确定并将添加 custodian 的主 Exchange 邮箱，请为每个 custodian 中,，选择**Exchange** 。 
 
2. 对于每个 custodian，如果您希望系统自动确定并将添加 custodian 主 OneDrive URL 选择**OneDrive** 。 

    所做的选择之后, 他们系统将自动尝试确定的数据源并将其添加到您的案例。
 
4. 单击**下一步**开始映射到您的管理员的其他数据源。

## <a name="optional-step-3-map-additional-data-sources"></a>（可选）步骤 3： 将其他数据源映射

根据您的情况下，您可能还需要添加给定的 custodian 可能使用了在过去的邮箱组管理员，有权访问过去 custodian 当前是成员，或网站的位置。除了主 custodian 数据源，可以将其他 Office 365 数据源添加到管理员或利用 Office 365 帮助您识别也可能相关的数据源。 

若要映射到特定 custodian 的邮箱、 站点或团队:
1. 选择要分配给特定管理员的内容的位置，如邮箱、 网站和团队的**更新**。 

2. 飞出，指定以下内容：
   
  -  **Exchange 邮箱**-单击**选择用户、 组或团队**，然后再次单击**选择用户、 组或团队**。若要指定邮箱分配给所选 custodian，使用搜索框查找用户邮箱和通讯组。您还可以为 Office 365 组或 Microsoft 团队分配关联的邮箱。选择用户、 组和团队复选框，单击**选择**，然后单击**完成**。

      > [!NOTE]
      > 当您单击选择用户、 组或团队指定邮箱时，显示邮箱选取器为空。这是设计以提高性能。要将联系人添加到此列表中，请在搜索框中键入名称 （最少的 3 个字符）。
     
   - **SharePoint 网站**-单击**选择站点**，然后单击**选择网站**再次指定您想要分配给所选 custodian 的业务网站的其他 SharePoint 和 OneDrive。您还可以为 Office 365 组或 Microsoft 团队添加 SharePoint 网站的 URL。键入要分配的每个网站的 URL。单击**选择**，然后单击**完成**。
   - **Microsoft 团队**– 单击**选择团队**，然后单击**选择团队**再次以查看 Microsoft 团队组管理员是今天的成员的列表。选择您希望将添加到您 custodian 团队。一旦选择，系统将自动标识关联的 SharePoint 网站和组邮箱关联的 Microsoft 团队到 & 选择。单击**选择**，然后单击**完成**。
        
      > [!NOTE]
      > 若要添加其他 Microsoft 团队，您将需要单独添加了邮箱和 SharePoint 网站如上所示。

映射源后，您可以查看邮箱总数、 网站和工作组刚添加的管理员。当您已为特定 custodian 定稿相关的数据源时，将维护此映射，并扩展到电子数据展示收集、 处理和审阅工作流。 

## <a name="optional-step-4-place-custodians-on-hold"></a>（可选）步骤 4： 位置上的管理员保留

 尚未最终的管理员和您希望将添加到您的情况的数据源后，（可选） 可以将放置一些或全部上您管理员保持状态。当您将置于保持状态的管理员时，直到释放 custodian 从用例，或者直到取消删除保留保留映射到该用户的内容。在某些情况下，您可能想要添加到案例的管理员，而不会将其置于保持状态。 

将所选的管理员和数据源置于保留：

1. 验证 custodian 选择，然后选择要将置于保持状态的每个 custodian checkox。一旦管理员将置于保持状态，将自动创建包含所有监控源 custodian 保留策略。如果不选中此选项，custodian & 选择数据源将添加到用例，但不是会保留内容。

2. 转到**保留**选项卡，并选择**Custodian 保留策略**。 

3. 单击**编辑**以查看所有选定的 custodian 数据源。

---
title: 管理数据调查中感兴趣的人员 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: e374509dccd235ef689609acc1c4f99db6594d4c
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150704"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a>管理数据调查中感兴趣的人员 (预览)

数据调查通常涉及感兴趣的人。 通常情况下, 他们是拥有您调查或寻求补救措施的错放、敏感或恶意数据的人。 在**数据调查 (预览版)** 中, 可以将其添加到查找用于确定搜索范围的数据源, 也可以查看其他信息 (如联系人、位置和活动日志)。 


## <a name="add-people-of-interest"></a>添加感兴趣的人员

在 "**感兴趣的人员**" 选项卡上, 您可以添加感兴趣的人员并发现他们的数据源 (如可用于确定搜索范围的 Exchange 邮箱或 OneDrive for business 网站)。 当受关注的人员限制时, 搜索会提高性能和准确性, 因为该工具会重新处理任何未编制索引的数据, 如图像或不受支持的文件类型。 您还可以查看其联系人信息、位置信息和活动日志, 您可以使用它们启动通信或进一步调查其活动。 

向调查中添加感兴趣的人员:

1. 从 "**数据调查 (预览)** " 页中, 转到您的调查。
 
2. 选择调查后, 转到 "**感兴趣的人员**" 选项卡, 然后单击 "**添加感兴趣的人**"。 
 
3. 选择要添加到调查中的人员。 您可以通过键入搜索并从组织的 Azure Active Directory 中选择用户来开始。
 
4. 完成感兴趣的人员列表后, 单击 "**下一步**" 以映射其数据源。 

5. Optional对于每个用户, 选择 " **Exchange** " 以添加人员的主 Exchange 邮箱, **OneDrive**将添加人员的主 OneDrive for business 网站。

6. Optional单击 "**下一步**" 添加您想要与您感兴趣的人员关联的任何其他数据源。

7. Optional选择 "**更新**", 将内容位置 (如邮箱、网站和团队) 分配给某个人。 

8. Optional在浮出控件中:
   
    -  **Exchange 邮箱**-单击 "**选择用户、组或团队**", 然后再次单击 "**选择用户、组或团队**"。 若要添加更多邮箱, 请使用搜索框查找用户邮箱和通讯组。 您还可以添加用于存储 Office 365 组或 Microsoft 团队信息的邮箱。 选中 "用户、组、团队" 复选框, 单击 "**选择**", 然后单击 "**完成**"。

        > [!NOTE]
        > 当您单击 "选择用户、组或团队以指定邮箱" 时, 显示的邮箱选取器为空。 这种设计旨在增强性能。 若要将人员添加到此列表, 请在搜索框中键入一个名称 (至少3个字符)。
     
     - **SharePoint 网站**-单击 "**选择网站**", 然后再次单击 "**选择网站**", 以指定要添加到人员的其他 SharePoint 和 OneDrive for business 网站 wwant。 您还可以为 Office 365 组或 Microsoft 团队添加 SharePoint 网站的 URL。 键入要分配的每个网站的 URL。 单击 "**选择**", 然后单击 "**完成**"。
     - **Microsoft 团队**–单击 "**选择团队**", 然后再次单击 "**选择团队**" 以查看此人是今天的成员的 Microsoft 团队组列表。 选择要添加到人员的团队。 选择后, 系统将自动识别 &。选择与该 Microsoft 团队关联的关联 SharePoint 网站和组邮箱。 单击 "**选择**", 然后单击 "**完成**"。
        
      > [!NOTE]
      > 若要添加其他 Microsoft 团队, 您需要单独添加邮箱和 SharePoint 网站, 如上所示。

完成将数据源映射到感兴趣的人员之后, 可以看到您刚刚添加的邮箱、网站和团队总数的摘要。 如果你将任何其他数据源映射到感兴趣的人, 并将你的搜索范围限定为关注的人员, 则在整个调查过程中将文档映射到关注的人员, 从而更轻松地组织证据或按感兴趣的人员生成报告。. 

## <a name="view-additional-people-of-interest-information"></a>查看其他感兴趣的人员信息

在 "**感兴趣的人员**" 选项卡上, 单击您 adeed 的人员。 在浮出控件中, 您将看到:

- 联系人信息

  - **显示名称**: 在通讯簿中显示的 peron 的名称。 这通常是名字、中间名首字母和姓氏的组合。
  - **Mail/smtp**: 人员的 SMTP 地址, 例如, jeff@contoso.onmicrosoft.com。  
  - **职务**: 职务。
  - **部门**: 人员在其中工作的部门的名称。
  - **经理**: 人员的经理。 管理者接收此人的任何升级通信。
  
- 位置信息

  - **City**: 人员所在的城市。
  - **状态**: 人员所在的省/市/自治区。
  - **国家/地区**: 人员所在的国家/地区;例如, "US" 或 "UK"。
  - **Office**: 人员的办公室位置。

- 处理状态

  - **索引编制状态**: 对数据源进行深入索引的状态
  - **索引上次更新时间**: 上次触发详细索引作业的时间戳。
  - **数据源**: 显示映射到人员的邮箱、网站和团队的计数

- 更新索引
    - 您可以对此人的数据源重新编制索引。 

- 查看活动 

    - 您可以查看和搜索用户的活动日志。 有关详细信息, 请参阅[查看感兴趣的人员活动](view-people-of-interest-activity.md) 

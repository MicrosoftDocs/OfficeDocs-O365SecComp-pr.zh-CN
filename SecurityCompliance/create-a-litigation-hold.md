---
title: 在 Office 365 中创建诉讼保留
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: f2d3793eac84e8f80158842c833c30986b0549c5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218652"
---
# <a name="create-a-litigation-hold-in-office-365"></a>在 Office 365 中创建诉讼保留

您可以将邮箱置于诉讼保留状态, 以保留所有邮箱内容, 包括已删除项目和已修改项目的原始版本。将用户邮箱置于诉讼保留状态时, 用户的存档邮箱 (如果已启用) 中的内容也会保留。创建保留时, 可以指定保留持续时间 (也称为*基于时间的保留*), 以便在指定时间段内保留已删除和已修改的项目, 然后从邮箱中永久删除。或者, 也可以无限期保留内容 (称为*无限保留*), 或者直到删除诉讼保留。如果您指定保留持续时间段, 则它将根据接收邮件的日期或创建邮箱项目计算得出。 
  
以下是创建诉讼保留时发生的情况。
  
- 被用户永久删除的项目将保留在用户邮箱中的 "可恢复的项目" 文件夹中的保留期。
    
- 用户在 "可恢复的项目" 文件夹中清除的项目将在保留期间保留。
    
- "可恢复的项目" 文件夹的存储配额从 30 gb 增加到 110 gb。
    
- 用户主和存档邮箱中的项目将保留
    
## <a name="before-you-begin"></a>准备工作

- 若要在诉讼保留中放置 Exchange online 邮箱, 必须为其分配 exchange online 计划2许可证。如果向某个邮箱分配了 Exchange Online 计划1许可证, 则必须为其分配一个单独的 Exchange online 存档许可证以将其置于保留状态。
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a>在 Office 365 管理中心中将邮箱置于诉讼保留状态

以下是使用 Office 365 管理中心将 maibox 置于诉讼保留状态的步骤。

1. 转到https://portal.office.com/adminportal/home并使用全局管理员帐户登录。
2. 单击左侧导航窗格中的 "**用户** > **活动用户**"。
3. 选择要将其邮箱置于诉讼保留状态的用户。
4. 在 "飞出" 页面上, 单击 "**邮件设置**", 然后单击 "**诉讼保留**" 旁边的 "**编辑**"。
5. 在 "**诉讼保留**" 页上, 单击 "切换" 以启用诉讼保留并完成显示的以下可选设置:
 
    ![O365_LitigationHold1](media/O365-LitigationHold1.png)

    一.**保留持续时间 (天)** -使用此框可以创建基于时间的保留, 并指定在将邮箱置于诉讼保留状态时邮箱项目的保留时间。持续时间从接收或创建邮箱项目的日期开始计算。如果将此框保留为空, 则项目将无限期保留或在删除保留之前进行。使用 "天" 指定持续时间。
    
    b.**注意**-使用此框通知用户其邮箱处于诉讼保留状态。如果用户使用的是 Outlook 2010 或更高版本, 注释将显示在用户邮箱中的 "帐户信息" 页面上。若要访问此页面, 用户可以在 Outlook 中单击 "**文件**"。
     
    c. 网页**** -使用此框将用户定向到网站, 以获取有关诉讼保留的详细信息。如果用户使用的是 Outlook 2010 或更高版本, 则此 URL 将显示在用户邮箱中的 "帐户信息" 页面上。若要访问此页面, 用户可以在 Outlook 中单击 "**文件**"。
 
6. 单击 "**保存**" 以创建诉讼保留。

创建保留后, 飞出页面上的邮件设置将显示所选用户的诉讼保留处于打开状态。

![O365_LitigationHold2](media/O365-LitigationHold2.png)

有关创建和管理诉讼保留和使用 Exchange Online PowerShell 批量创建诉讼保留的详细信息, 请参阅[将邮箱置于诉讼保留状态](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold)。

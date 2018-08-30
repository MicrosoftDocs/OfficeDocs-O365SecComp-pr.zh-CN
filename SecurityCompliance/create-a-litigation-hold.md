---
title: Office 365 中创建诉讼保留
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: 18b3b3a42e5671b1507522c89faaa4ae34198831
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525801"
---
# <a name="create-a-litigation-hold-in-office-365"></a>Office 365 中创建诉讼保留

您可以将邮箱置于诉讼保留状态，保留所有邮箱内容，包括已删除的项目和已修改项目的原始版本。如果您将用户邮箱置于诉讼保留时，用户的存档邮箱中的内容 （如果已启用） 是还会保留。创建保留项时，您可以指定 （也称为*基于时间的保留*） 保留持续时间，以便删除和修改的项的保留指定的时间段，然后永久删除邮箱。或可以只是无限期保留内容 （称为*无限期保留*） 或直到诉讼保留被删除。如果您指定保留持续时间段，它计算从日期收到一条消息，或创建邮箱项目。 
  
下面是创建诉讼保留时，会发生什么情况。
  
- 用户被永久删除的项目保留的持续时间内保留用户的邮箱中的可恢复的项目文件夹中。
    
- 保留项的持续时间内保留用户从可恢复邮件文件夹清除的项目。
    
- 可恢复邮件文件夹的存储配额为 110 GB 增加从 30 GB。
    
- 保留用户的主和存档邮箱中的项目
    
## <a name="before-you-begin"></a>准备工作

- 若要将 Exchange Online 邮箱置于诉讼保留状态，必须将它分配的 Exchange Online 计划 2 许可证。如果邮箱已分配的 Exchange Online 计划 1 许可证，您必须将其单独 Exchange Online Archiving 的许可证将它置于保留分配。
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a>将邮箱置于诉讼保留在 Office 365 管理中心

以下是将置于诉讼保留状态使用 Office 365 管理中心 maibox 的步骤。

1. 转到https://portal.office.com/adminportal/home和使用您的全局管理员帐户登录。
2. 单击**用户** > 左的导航窗格中的**活动用户**。
3. 选择您要置于诉讼保留其邮箱的用户。
4. 在飞出页上，单击**邮件设置**，然后单击**诉讼保留**旁边的**编辑**。
5. 在**诉讼保留**页上，单击打开置于诉讼保留状态并完成以下显示的可选设置切换:
 
    ![O365_LitigationHold1.png](media/O365-LitigationHold1.png)

    答：**保留持续时间 （天）** -使用此框可以创建基于时间的保留并指定当邮箱置于诉讼保留多长时间保留邮箱项目。接收或创建邮箱项目时，将从日期计算持续时间。如果将此框保留为空，项目保留无限期或直到保留被删除。使用天指定持续时间。
    
    b.**注意**-使用此框通知用户其邮箱位于诉讼保留。如果他们正在使用 Outlook 2010 或更高版本，注释将显示在用户的邮箱的帐户信息页上。若要访问此页，用户可以单击在 Outlook 中的**文件**。
     
    c. **Web 页**-使用此框可以将用户定向到有关诉讼保留的详细信息的网站。如果他们使用 Outlook 2010 或更高版本，此 URL 将出现在用户的邮箱的帐户信息页上。若要访问此页，用户可以单击在 Outlook 中的**文件**。
 
6. 单击**保存**以创建诉讼保留。

创建保留项后，飞出页面上的邮件设置显示诉讼保留已打开所选用户。

![O365_LitigationHold2.png](media/O365-LitigationHold2.png)

有关创建和管理诉讼保留和使用 Exchange Online PowerShell 中批量创建诉讼保留的详细信息，请参阅[位置上诉讼保留的邮箱](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold)。

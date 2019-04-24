---
title: '在 EOP 中运行管理员角色组报告 '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: 每当管理员在管理员角色组中添加或删除成员时，Microsoft Exchange Online Protection (EOP) 都会进行记录。
ms.openlocfilehash: 752def771d95fcfbb3f7cbe0bc86a33b3967716d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256180"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>在 EOP 中运行管理员角色组报告 

 每当管理员在管理员角色组中添加或删除成员时，Microsoft Exchange Online Protection (EOP) 都会进行记录。在 Exchange 管理中心中运行管理员角色组报告时，条目会作为搜索结果显示，其中包括受影响的角色组、更改角色组成员身份的用户和时间，以及做出的成员身份更新。使用此报告可以对已分配给组织中的用户的管理权限的更改进行监视。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

- 估计完成时间：2 分钟
    
- 您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"报告"部分。 
    
- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
> [!TIP]
> 遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>使用 EAC 运行管理员角色组报告

运行管理员角色组报告，以查找在特定时间段内对组织中的管理角色组所做的更改。
  
1. 在 EAC 中, 导航到 "**合规性管理** \> **审核**", 然后选择 "**运行管理员角色组报告**"。
    
2. 选择 "**开始日期**" 和 "**结束日期**"。 默认情况下，报告将搜索在过去两周内对管理员角色组所做的更改。
    
3. 若要查看特定角色组的更改, 请单击 "**选择角色组**"。 在随后的对话框中选择角色组, 然后单击 **"确定"**。 您也可以将字段留空，以查找所有更改的角色组。
    
4. 单击"搜索"。
    
如果使用指定的条件找到了所有更改，则这些更改会显示在结果窗格中。单击搜索结果中的角色组可在详细信息窗格中查看更改。
  
## <a name="how-do-you-know-this-worked"></a>如何知道操作成功？

如果您已成功运行管理员角色组报告，那么在此日期范围内更改的角色组将显示在搜索结果窗格中。如果没有显示任何结果，那么在指定日期范围内没有发生对角色组的任何更改。如果您认为应该显示结果，请更改日期范围，然后再次运行报告。
  
## <a name="monitor-changes-to-role-group-membership"></a>监视角色组成员身份的更改

向某个角色组添加成员或删除其中的成员时，在详细信息窗格中显示的搜索结果将会指示角色组成员身份已进行更新，并列出当前的成员。但搜索结果并不会明确地指出已添加或已删除的用户。
  
若要确定是否添加或删除了某个用户，则必须对报告中的两个不同条目进行比较。 例如, 让我们来看看 "**支持人员**" 角色组的以下日志条目: 
  
 **1/27/2013 4:43 PM**
  
 **管理员**
  
 **Updated members: Administrator;annb,florencef;pilarp**
  
 **2/06/2013 10:09 AM**
  
 **管理员**
  
 **Updated members: Administrator;annb;florencef;pilarp;tonip**
  
 **2/19/2013 2:12 PM**
  
 **管理员**
  
 **Updated members: Administrator;annb;florencef;tonip**
  
在本示例中，Administrator 用户帐户做出了以下更改：
  
- 在 2013 年 2 月 6 日添加了用户 tonip。
    
- 在 2013 年 2 月 19 日删除了用户 pilarp。
    


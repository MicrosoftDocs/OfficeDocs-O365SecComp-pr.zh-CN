---
title: '在 EOP 中运行管理员角色组报告 '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 中运行管理员角色组报告。 当管理员向管理员角色组添加成员或从中删除成员时, 此报告将记录, Microsoft Exchange Online Protection (EOP) 会记录每次出现的情况。
ms.openlocfilehash: 6973574ca1eeabee85dd57bd087ba5d0675da084
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676504"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>在 EOP 中运行管理员角色组报告

 当管理员向管理员角色组添加成员或从中删除成员时, Exchange Online Protection (EOP) 会记录每次发生的事件。 在 Exchange 管理中心 (EAC) 中运行管理员角色组报告时, 条目将显示为搜索结果, 并包括受影响的角色组、更改角色组成员身份的用户以及进行成员身份更新的用户。 使用此报告可以对已分配给组织中的用户的管理权限的更改进行监视。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

- 估计完成时间：2 分钟

- 若要打开 Exchange 管理中心, 请参阅 exchange [Online Protection 中的 exchange 管理中心](../exchange-admin-center-in-exchange-online-protection-eop.md)。

- 您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"报告"部分。

- 有关可能适用于本主题中的过程的键盘快捷方式的信息, 请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛中寻求帮助。
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>使用 EAC 运行管理员角色组报告

运行管理员角色组报告, 在特定时间范围内查找对组织中的管理角色组的更改。
  
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
  
> 1/27/2018 4:43 PM <br> 管理员 <br> Updated members: Administrator;annb,florencef;pilarp <br> 2/06/2018 10:09 AM <br> 管理员 <br> Updated members: Administrator;annb;florencef;pilarp;tonip <br> 2/19/2018 2:12 PM <br> Administrator <br> Updated members: Administrator;annb;florencef;tonip

在本示例中，Administrator 用户帐户做出了以下更改：
  
- 在2/06/2018 上, 他们添加了用户 tonip。

- 在2/19/2018 上, 他们删除了用户 pilarp。

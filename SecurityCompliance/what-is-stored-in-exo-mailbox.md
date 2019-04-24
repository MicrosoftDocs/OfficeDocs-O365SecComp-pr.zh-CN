---
title: 存储在 Exchange Online 邮箱中的内容
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Office 365 中基于云的应用生成的数据存储在 Microsoft 云中的用户的 Exchange Online 邮箱中。
ms.openlocfilehash: 6f7a81842df5972a03648a2f93d4bd6fbd738fec
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266894"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>存储在 Exchange Online 邮箱中的内容

Exchange Online 中的邮箱主要用于存储与电子邮件相关的项目, 如邮件、日历项目、任务和便笺。 但是, 随着基于云的 Office 365 的应用程序也会将其数据存储在用户的邮箱中。 将数据存储在邮箱中的一个优点是, 可以使用内容搜索、电子数据展示、高级电子数据展示和数据调查中的搜索工具来查找、查看和导出这些基于云的应用程序中的数据。 请注意, 其中一些应用程序中的数据存储在邮箱中非人际邮件 (非 IPM) 子树中的隐藏文件夹中。 这意味着, 当用户使用 Outlook 或其他邮件客户端访问其邮箱时, 数据将隐藏在用户的视图中。

下表列出了在基于云的邮箱中存储数据的 Office 365 应用程序。 该表还介绍了每个应用程序存储的内容类型。

|Office 365 应用  |说明  |
|:---------|:---------|
|表单     <br/> |表单 (存储为 PDF 文件) 和对表单 (存储在 CSV 文件中) 的响应将附加到电子邮件中, 并存储在创建表单的用户邮箱中的隐藏文件夹中。 从 PST 文件中的表单导出内容时, 此数据位于使用以下全局唯一标识 (GUID): **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**命名的子文件夹中的 " **ApplicationDataRoot** " 文件夹中。        <br/> |
|MyAnalytics    <br/> |   MyAnalytics 为用户提供了有关如何根据邮箱中的邮件和日历数据花费时间的见解。 此数据存储在用户的邮箱中的隐藏文件夹中。 有关 MyAnalytics 数据及其导出方式的详细信息, 请参阅[从 MyAnalytics 导出数据](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#exporting-data-from-myanalytics-and-the-office-roaming-service)。      <br/> |
|Office 365 组    <br/>|  电子邮件、日历项目、联系人 (人员)、便笺和任务存储在与 Office 365 组相关联的邮箱中。       <br/> |
|Outlook/Exchange Online<br/>|  电子邮件、日历项目、联系人 (人员)、便笺和任务存储在用户的邮箱中。       <br/> |
|人员    <br/> |  "人员" 应用中的联系人 (与 Outlook 中可访问的联系人相同) 存储在用户的邮箱中。      <br/> |
|规划器     <br/> |   在计划程序中创建的计划存储在创建新计划时设置的相应 Office 365 组的邮箱中。 组邮箱的别名是计划的名称。      <br/> |
|Skype for Business    <br/>  | Skype for business 中的对话存储在用户邮箱的 "对话历史记录" 文件夹中。 如果 Skype 会议参与者的邮箱被置于诉讼保留或分配到保留策略, 则附加到会议的文件将保留在参与者邮箱中。         <br/> |
|Sway     <br/> |  sway 存储为附加到电子邮件的 HTML 文件, 并存储在创建 sway 的用户邮箱的隐藏文件夹中。 在从 PST 文件中导出 Sway 中的内容时, 此数据位于名为以下 GUID 的子文件夹中的**ApplicationDataRoot**文件夹中) **905fcf26-4eb7-48a0-9ff0-8dcc7194b5ba**。       <br/> |
|任务    <br/> |  任务应用程序中的任务 (与 Outlook 中可访问的任务相同) 存储在用户的邮箱中。       <br/> |
|Teams    <br/>  |属于团队渠道的对话存储在与团队相关联的邮箱中。 团队中聊天列表的一部分对话 (也称为*1 x N 聊天*) 存储在参与聊天的用户的邮箱中。 此外, 团队频道中的会议和呼叫的摘要信息存储在拨入会议或呼叫的用户的邮箱中。 <br/> | 
|微软待办  <br/> | "待办事项**" 应用中的任务 (在待办事项列表中调用) 存储在用户的邮箱中。        <br/> |
||||

> [!NOTE]
> 目前, 如果将保留置于高级电子数据展示 (预览) 中的保管人邮箱上, 则保留不会保留来自表单和 Sway 的内容。 
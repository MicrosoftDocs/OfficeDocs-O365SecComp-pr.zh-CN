---
title: 业务数据删除的 office 365 Skype
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 有关业务数据删除 Skype 的说明。
ms.openlocfilehash: f3ddd0ad0797c465857919e8f7b28341492769ba
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525657"
---
# <a name="skype-for-business-data-deletion-in-office-365"></a>Office 365 中的业务数据删除的 Skype

Skype for Business 提供对等即时消息、 多方即时消息和会议中的内容上载活动的存档功能。存档功能要求具有 Exchange，并且受用户的 Exchange 邮箱就地保留属性，它对电子邮件和 Skype 业务内容进行存档。

Skype for Business 中的所有存档被视为"用户级存档"因为您启用或禁用它的一个或多个特定用户或用户组的创建、 配置和应用这些用户的用户级存档策略。没有直接从业务管理中心的 Skype 中的存档设置的控件。

Skype for Business 中不存档以下类型的内容： 
- 对等文件传输
- 对等即时消息和会议的音频/视频
- 对等即时消息和会议的应用程序共享
- 会议注释 

## <a name="meeting-content-retention"></a>会议内容保留期
使用 Skype for Business 的客户可以将内容上载到 Skype 业务会议作为附件，如 PowerPoint 演示文稿、 OneNote 文件和其他文件。已上载到会议内容保留期如下所示：
- **一次性会议**的内容将保留 15 天，从最后一个人员离开会议时开始。
- **定期会议**的内容将保留 15 天的最后一个人员离开会议的最后一个会话之后。如果某人加入同一会议会话 15 天内的，将重置保留计时器。例如，假定业务会议 Skype 计划在每周的基础上发生一年时间，并将文件上载到会议过程中的第一个实例。如果至少一个人加入会议会话每周，该文件保留在 Skype 业务联机服务器全年 plus 15 天后的最后一个人员离开会议最后一个数据系列。
- 8 小时会议结束时间后被保留**立即开会会议**的内容。

> [!NOTE]
> 如果用户是未经授权或禁用 （例如，如果**msRTCSIP userenabled**设置为*False*），则然后重新许可或重新启用，不会保留会议内容。

## <a name="meeting-expiration"></a>会议过期
用户可以在会议结束后访问某个特定的会议，但取决于以下过期时间：
- **一次性会议**的会议时安排的会议结束时间后 14 天过期。
- **与结束日期的定期会议**的会议的最后一个会议事件计划的结束时间后 14 天过期。
- **立即开会会议**-8 小时后过期的会议。

## <a name="whiteboard-collaboration"></a>白板协作
所有参与者都能看到白板上所做的注释。当保存白板，白板和所有注释将存储在业务服务器 Skype 和将根据会议内容过期策略管理员设置的服务器上保留。

## <a name="audio-test-service"></a>音频测试服务
记录您的语音短 （约 5 秒） 示例在音频测试服务调用过程。您使用语音样本检查和/或验证声音基于录制的质量的业务呼叫您 Skype 的质量。音频测试服务呼叫结束时，将删除语音样本。

## <a name="persistent-group-chat"></a>持久的群聊
持续群聊存储群聊对话的内容。如果启用，管理员可以控制的保留期，存储此信息的服务器，如果群聊历史记录存档合规性或其他目的，并管理/修改任何聊天室的属性。具有不同角色的用户具有不同持续的数据，访问，如下所示：
- 管理员可以从任何聊天室内，以防止数据库的大小会大大增长删除旧内容 （例如，在特定日期之前发布的内容）。或者，它们可以删除或替换邮件视为不当为给定的聊天室 （或视为不合适）。
- 最终用户，包括消息作者，无法删除任何聊天室内容。
- 聊天室管理员可以禁用聊天室，但不能删除聊天室。在创建后，只有管理员才能删除聊天室。
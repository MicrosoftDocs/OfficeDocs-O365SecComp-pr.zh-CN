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
# <a name="skype-for-business-data-deletion-in-office-365"></a><span data-ttu-id="87533-103">Office 365 中的业务数据删除的 Skype</span><span class="sxs-lookup"><span data-stu-id="87533-103">Skype for Business Data Deletion in Office 365</span></span>

<span data-ttu-id="87533-p101">Skype for Business 提供对等即时消息、 多方即时消息和会议中的内容上载活动的存档功能。存档功能要求具有 Exchange，并且受用户的 Exchange 邮箱就地保留属性，它对电子邮件和 Skype 业务内容进行存档。</span><span class="sxs-lookup"><span data-stu-id="87533-p101">Skype for Business provides archiving of peer-to-peer instant messages, multiparty instant messages, and content upload activities in meetings. The archiving capability requires Exchange and is controlled by the user's Exchange mailbox In-Place Hold attribute, which archives both email and Skype for Business contents.</span></span>

<span data-ttu-id="87533-p102">Skype for Business 中的所有存档被视为"用户级存档"因为您启用或禁用它的一个或多个特定用户或用户组的创建、 配置和应用这些用户的用户级存档策略。没有直接从业务管理中心的 Skype 中的存档设置的控件。</span><span class="sxs-lookup"><span data-stu-id="87533-p102">All archiving in Skype for Business is considered "user-level archiving" because you enable or disable it for one or more specific users or groups of users by creating, configuring, and applying a user-level archiving policy for those users. There is no direct control of archiving settings from within the Skype for Business admin center.</span></span>

<span data-ttu-id="87533-108">Skype for Business 中不存档以下类型的内容：</span><span class="sxs-lookup"><span data-stu-id="87533-108">The following types of content are not archived in Skype for Business:</span></span> 
- <span data-ttu-id="87533-109">对等文件传输</span><span class="sxs-lookup"><span data-stu-id="87533-109">Peer-to-peer file transfers</span></span>
- <span data-ttu-id="87533-110">对等即时消息和会议的音频/视频</span><span class="sxs-lookup"><span data-stu-id="87533-110">Audio/video for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="87533-111">对等即时消息和会议的应用程序共享</span><span class="sxs-lookup"><span data-stu-id="87533-111">Application sharing for peer-to-peer instant messages and conferences</span></span>
- <span data-ttu-id="87533-112">会议注释</span><span class="sxs-lookup"><span data-stu-id="87533-112">Conferencing annotations</span></span> 

## <a name="meeting-content-retention"></a><span data-ttu-id="87533-113">会议内容保留期</span><span class="sxs-lookup"><span data-stu-id="87533-113">Meeting Content Retention</span></span>
<span data-ttu-id="87533-p103">使用 Skype for Business 的客户可以将内容上载到 Skype 业务会议作为附件，如 PowerPoint 演示文稿、 OneNote 文件和其他文件。已上载到会议内容保留期如下所示：</span><span class="sxs-lookup"><span data-stu-id="87533-p103">Customers using Skype for Business can upload content to a Skype for Business meeting as attachments, such as PowerPoint presentations, OneNote files, and other files. The retention period for content that has been uploaded to a meeting is as follows:</span></span>
- <span data-ttu-id="87533-116">**一次性会议**的内容将保留 15 天，从最后一个人员离开会议时开始。</span><span class="sxs-lookup"><span data-stu-id="87533-116">**One-time meeting** - Content is retained for 15 days starting from when the last person leaves the meeting.</span></span>
- <span data-ttu-id="87533-p104">**定期会议**的内容将保留 15 天的最后一个人员离开会议的最后一个会话之后。如果某人加入同一会议会话 15 天内的，将重置保留计时器。例如，假定业务会议 Skype 计划在每周的基础上发生一年时间，并将文件上载到会议过程中的第一个实例。如果至少一个人加入会议会话每周，该文件保留在 Skype 业务联机服务器全年 plus 15 天后的最后一个人员离开会议最后一个数据系列。</span><span class="sxs-lookup"><span data-stu-id="87533-p104">**Recurring meeting** - Content is retained for 15 days after the last person leaves the last session of the meeting. The retention timer resets if someone joins the same meeting session within 15 days. For example, assume a Skype for Business meeting is scheduled to occur on a weekly basis for one year, and a file is uploaded to the meeting during the first instance. If at least one person joins the meeting session every week, the file is retained in Skype for Business Online servers for the entire year plus 15 days after the last person leaves the last meeting of the series.</span></span>
- <span data-ttu-id="87533-121">8 小时会议结束时间后被保留**立即开会会议**的内容。</span><span class="sxs-lookup"><span data-stu-id="87533-121">**Meet Now meeting** - Content is retained for 8 hours after the meeting end time.</span></span>

> [!NOTE]
> <span data-ttu-id="87533-122">如果用户是未经授权或禁用 （例如，如果**msRTCSIP userenabled**设置为*False*），则然后重新许可或重新启用，不会保留会议内容。</span><span class="sxs-lookup"><span data-stu-id="87533-122">If a user is unlicensed or disabled (e.g., if **msRTCSIP-userenabled** is set to *False*), and is then re-licensed or reenabled, meeting content is not retained.</span></span>

## <a name="meeting-expiration"></a><span data-ttu-id="87533-123">会议过期</span><span class="sxs-lookup"><span data-stu-id="87533-123">Meeting Expiration</span></span>
<span data-ttu-id="87533-124">用户可以在会议结束后访问某个特定的会议，但取决于以下过期时间：</span><span class="sxs-lookup"><span data-stu-id="87533-124">Users can access a specific meeting after the meeting has ended, subject to the following expiration time periods:</span></span>
- <span data-ttu-id="87533-125">**一次性会议**的会议时安排的会议结束时间后 14 天过期。</span><span class="sxs-lookup"><span data-stu-id="87533-125">**One-time meeting** - Meeting expires 14 days after the scheduled meeting end time.</span></span>
- <span data-ttu-id="87533-126">**与结束日期的定期会议**的会议的最后一个会议事件计划的结束时间后 14 天过期。</span><span class="sxs-lookup"><span data-stu-id="87533-126">**Recurring meeting with end date** - Meeting expires 14 days after the scheduled end time of the last meeting occurrence.</span></span>
- <span data-ttu-id="87533-127">**立即开会会议**-8 小时后过期的会议。</span><span class="sxs-lookup"><span data-stu-id="87533-127">**Meet Now meeting** - Meeting expires after 8 hours.</span></span>

## <a name="whiteboard-collaboration"></a><span data-ttu-id="87533-128">白板协作</span><span class="sxs-lookup"><span data-stu-id="87533-128">Whiteboard Collaboration</span></span>
<span data-ttu-id="87533-p105">所有参与者都能看到白板上所做的注释。当保存白板，白板和所有注释将存储在业务服务器 Skype 和将根据会议内容过期策略管理员设置的服务器上保留。</span><span class="sxs-lookup"><span data-stu-id="87533-p105">Annotations made on whiteboards will be seen by all participants. When saving a whiteboard, the whiteboard and all annotations will be stored on a Skype for Business server, and it will be retained on the server according to meeting content expiration policies set by the administrator.</span></span>

## <a name="audio-test-service"></a><span data-ttu-id="87533-131">音频测试服务</span><span class="sxs-lookup"><span data-stu-id="87533-131">Audio Test Service</span></span>
<span data-ttu-id="87533-p106">记录您的语音短 （约 5 秒） 示例在音频测试服务调用过程。您使用语音样本检查和/或验证声音基于录制的质量的业务呼叫您 Skype 的质量。音频测试服务呼叫结束时，将删除语音样本。</span><span class="sxs-lookup"><span data-stu-id="87533-p106">A short (approximately 5 seconds) sample of your voice is recorded during the Audio Test Service call. The voice sample is used by you to check and/or verify the sound quality of your Skype for Business call based on the quality of the recording. When the Audio Test Service call ends, the voice sample is deleted.</span></span>

## <a name="persistent-group-chat"></a><span data-ttu-id="87533-135">持久的群聊</span><span class="sxs-lookup"><span data-stu-id="87533-135">Persistent Group Chat</span></span>
<span data-ttu-id="87533-p107">持续群聊存储群聊对话的内容。如果启用，管理员可以控制的保留期，存储此信息的服务器，如果群聊历史记录存档合规性或其他目的，并管理/修改任何聊天室的属性。具有不同角色的用户具有不同持续的数据，访问，如下所示：</span><span class="sxs-lookup"><span data-stu-id="87533-p107">Persistent Group Chat stores the content of group chat conversations. If enabled, the administrator can control the retention period, the server on which this information is stored, if Group Chat history is archived for compliance or other purposes, and manage/modify any properties on a room. Users with different roles have different access to the persisted data, as follows:</span></span>
- <span data-ttu-id="87533-p108">管理员可以从任何聊天室内，以防止数据库的大小会大大增长删除旧内容 （例如，在特定日期之前发布的内容）。或者，它们可以删除或替换邮件视为不当为给定的聊天室 （或视为不合适）。</span><span class="sxs-lookup"><span data-stu-id="87533-p108">Administrators can delete older content (for example, content posted before a certain date) from any chat room to keep the size of the database from growing greatly. Or, they can remove or replace messages considered inappropriate for a given chat room (or considered unsuitable).</span></span>
- <span data-ttu-id="87533-141">最终用户，包括消息作者，无法删除任何聊天室内容。</span><span class="sxs-lookup"><span data-stu-id="87533-141">End-users, including message authors, cannot delete content from any chat room.</span></span>
- <span data-ttu-id="87533-p109">聊天室管理员可以禁用聊天室，但不能删除聊天室。在创建后，只有管理员才能删除聊天室。</span><span class="sxs-lookup"><span data-stu-id="87533-p109">Chat room managers can disable rooms but cannot delete rooms. Only administrators can delete a chat room after it is created.</span></span>
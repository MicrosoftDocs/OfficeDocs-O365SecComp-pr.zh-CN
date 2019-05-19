---
title: 在高级电子数据展示中使用通信
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
description: 利用高级电子数据展示, 可以轻松管理法律封存通知工作流, 避免在法律调查中通知保管人。
ms.openlocfilehash: cf5c8f5e932993255bda2cb959657c2c6ded3163
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154904"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="9c46e-103">在高级电子数据展示中使用通信</span><span class="sxs-lookup"><span data-stu-id="9c46e-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="9c46e-104">高级电子数据展示允许法律部门简化跟踪和分发合法保留通知的过程。</span><span class="sxs-lookup"><span data-stu-id="9c46e-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="9c46e-105">通过保管人通信工具, 法律部门可以管理和自动化整个合法保留过程, 从初始通知、提醒和升级到一个位置。</span><span class="sxs-lookup"><span data-stu-id="9c46e-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="9c46e-106">什么是合法保留通知？</span><span class="sxs-lookup"><span data-stu-id="9c46e-106">What is a legal hold notification?</span></span>

<span data-ttu-id="9c46e-107">法定保留 (也称为 "*诉讼保留*") 通知是从组织的法律部门向员工、临时员工或可与法律调查相关的数据的保管人发送的通知。</span><span class="sxs-lookup"><span data-stu-id="9c46e-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="9c46e-108">这些通知指示保管人保留以电子方式存储的信息, 以及可能与活跃或即将发生的法律事务相关的任何内容。</span><span class="sxs-lookup"><span data-stu-id="9c46e-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="9c46e-109">法律团队必须知道每位管理员已收到、阅读、理解并同意符合给定的说明。</span><span class="sxs-lookup"><span data-stu-id="9c46e-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="9c46e-110">合法保留通知过程</span><span class="sxs-lookup"><span data-stu-id="9c46e-110">The legal hold notification process</span></span>

<span data-ttu-id="9c46e-111">组织有责任在了解即将进行的诉讼或法规调查时保留相关信息。</span><span class="sxs-lookup"><span data-stu-id="9c46e-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="9c46e-112">为了符合调查的保留要求, 组织应立即通知潜在保管人的责任, 以保留相关信息。</span><span class="sxs-lookup"><span data-stu-id="9c46e-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="9c46e-113">使用高级电子数据展示, 法律团队可以创建和自定义其法律保留通知工作流。</span><span class="sxs-lookup"><span data-stu-id="9c46e-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="9c46e-114">保管人通信工具允许法律团队配置以下通知和工作流:</span><span class="sxs-lookup"><span data-stu-id="9c46e-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="9c46e-115">**颁发通知**: 在法律部门向保管人发出通知 (或发起) 的合法保留通知, 其中可能包含有关案例问题的相关信息。</span><span class="sxs-lookup"><span data-stu-id="9c46e-115">**Issuance notice**: A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="9c46e-116">此通知指示保管人保留发现可能需要的任何信息。</span><span class="sxs-lookup"><span data-stu-id="9c46e-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>
   
2.  <span data-ttu-id="9c46e-117">**重新发布通知**: 在一种情况下, 可能需要保管人来保留其他内容 (或较少的内容), 而不是以前请求的内容。</span><span class="sxs-lookup"><span data-stu-id="9c46e-117">**Re-Issuance notice**: During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="9c46e-118">在这种情况下, 您可以更新现有保留通知, 并将其重新颁发给保管人。</span><span class="sxs-lookup"><span data-stu-id="9c46e-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3.  <span data-ttu-id="9c46e-119">**发布通知**: 一旦问题得到解决, 并且保管人不再受保留要求的制约, 则可以从该案例发布保管人。</span><span class="sxs-lookup"><span data-stu-id="9c46e-119">**Release notice**: Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="9c46e-120">此外, 还可以通知管理员他们不再需要保留内容, 并提供有关如何恢复其数据相关的正常工作活动的说明。</span><span class="sxs-lookup"><span data-stu-id="9c46e-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="9c46e-121">**提醒和上报**: 在某些情况下, 仅发出通知不足以满足法律查询要求。</span><span class="sxs-lookup"><span data-stu-id="9c46e-121">**Reminders and escalations**: In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="9c46e-122">对于每个通知, 法律团队可以安排一组提醒和升级工作流, 以自动跟进保管人并使保管人保持不响应。</span><span class="sxs-lookup"><span data-stu-id="9c46e-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow-up with unresponsive custodians.</span></span>

    - <span data-ttu-id="9c46e-123">**提醒**: 在向一组保管人发出法定保留通知或重新颁发此通知后, 组织可以设置提醒, 以通知保管人的响应者。</span><span class="sxs-lookup"><span data-stu-id="9c46e-123">**Reminders**:  After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

    - <span data-ttu-id="9c46e-124">**升级**: 在某些情况下, 如果保管人在一段时间后仍无响应, 则法律团队可以设置升级工作流, 以通知不响应的保管人及其经理。</span><span class="sxs-lookup"><span data-stu-id="9c46e-124">**Escalations**: In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

## <a name="role-groups-and-permissions"></a><span data-ttu-id="9c46e-125">角色组和权限</span><span class="sxs-lookup"><span data-stu-id="9c46e-125">Role groups and permissions</span></span> 

<span data-ttu-id="9c46e-126">法律团队可以使用安全 & 合规中心中的电子数据展示相关角色组和权限控制和隔离其事例活动。</span><span class="sxs-lookup"><span data-stu-id="9c46e-126">Legal teams can control and segregate their case activity using eDiscovery-related role groups and permissions in the Security & Compliance Center.</span></span> 

<span data-ttu-id="9c46e-127">若要创建和管理合法保留通知, 用户必须是以下角色组的一部分:</span><span class="sxs-lookup"><span data-stu-id="9c46e-127">To create and manage legal hold notifications, a user must be part of the following role groups:</span></span>

- <span data-ttu-id="9c46e-128">**电子数据展示管理器**-此角色组的成员可以创建和管理电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="9c46e-128">**eDiscovery Manager** - Members of this role group can create and manage eDiscovery cases.</span></span> <span data-ttu-id="9c46e-129">他们可以添加和删除成员, 将保管人和内容位置置于保留状态, 管理法律封存通知, 创建和编辑与案例相关的内容搜索, 导出内容搜索的结果, 并准备高级搜索结果以供分析发现.</span><span class="sxs-lookup"><span data-stu-id="9c46e-129">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit Content Searches associated with a case, export the results of a Content Search, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="9c46e-130">此角色组中有两个子组。</span><span class="sxs-lookup"><span data-stu-id="9c46e-130">There are two sub-groups in this role group.</span></span> <span data-ttu-id="9c46e-131">这些子组之间的差异基于作用域。</span><span class="sxs-lookup"><span data-stu-id="9c46e-131">The difference between these subgroups is based on scope.</span></span>

  - <span data-ttu-id="9c46e-132">**电子数据展示管理器**-可以查看和管理他们创建的或为其成员的电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="9c46e-132">**eDiscovery Manager** - Can view and manage the eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="9c46e-133">如果另一个电子数据展示管理器创建了一个事例, 但未将另一个电子数据展示管理器添加为这种情况的成员, 则第二个电子数据展示管理器将无法在 Security & 合规性中心的电子数据展示页面上查看或打开事例。</span><span class="sxs-lookup"><span data-stu-id="9c46e-133">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="9c46e-134">电子数据展示管理器还可以访问高级电子数据展示中的案例, 以执行分析任务。</span><span class="sxs-lookup"><span data-stu-id="9c46e-134">eDiscovery Managers can also access their cases in Advanced eDiscovery to perform analysis tasks.</span></span>

  - <span data-ttu-id="9c46e-135">**电子数据展示管理员**-可以执行电子数据展示管理器可以执行的所有案例管理任务。</span><span class="sxs-lookup"><span data-stu-id="9c46e-135">**eDiscovery Administrator** - Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="9c46e-136">此外，电子数据展示管理员可以：</span><span class="sxs-lookup"><span data-stu-id="9c46e-136">Additionally, an eDiscovery Administrator can:</span></span>
    
    - <span data-ttu-id="9c46e-137">查看“电子数据展示”页上列出的所有事例。</span><span class="sxs-lookup"><span data-stu-id="9c46e-137">View all cases that are listed on the eDiscovery page.</span></span>
    - <span data-ttu-id="9c46e-138">在组织中管理任何事例, 然后在将自己添加为案例成员。</span><span class="sxs-lookup"><span data-stu-id="9c46e-138">Manage any case in the organization after they add themselves as a member of the case.</span></span>
    - <span data-ttu-id="9c46e-139">在高级电子数据展示中为组织中的任何情况访问事例数据。</span><span class="sxs-lookup"><span data-stu-id="9c46e-139">Access case data in Advanced eDiscovery for any case in the organization.</span></span>

<span data-ttu-id="9c46e-140">有关详细信息, 请参阅[在安全 _AMP_ 合规中心中分配电子数据展示权限](../assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="9c46e-140">For more information, see [Assign eDiscovery permissions in the Security & Compliance Center](../assign-ediscovery-permissions.md).</span></span>
---
title: 在高级电子数据展示中使用通信 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 916691e1f2470ef9e9e54d9dfe06c5277a92ba53
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296085"
---
# <a name="work-with-communications-in-advanced-ediscovery-preview"></a><span data-ttu-id="760a6-102">在高级电子数据展示中使用通信 (预览)</span><span class="sxs-lookup"><span data-stu-id="760a6-102">Work with communications in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="760a6-p101">高级电子数据展示 (预览) 允许法律部门简化跟踪和分发合法保留通知的过程。通过保管人通信功能, 法律部门可以在一个位置管理和自动执行整个法律封存流程--从通知、提醒和升级。</span><span class="sxs-lookup"><span data-stu-id="760a6-p101">Advanced eDiscovery (Preview) allows legal departments to simplify their processes around tracking and distributing legal hold notifications. The custodian communications feature enables legal departments to manage and automate their entire legal hold processes--from notifications, reminders, and escalations--all in one place.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="760a6-105">什么是合法保留通知？</span><span class="sxs-lookup"><span data-stu-id="760a6-105">What is a legal hold notification?</span></span>

<span data-ttu-id="760a6-p102">法定保留 (也称为 "*诉讼保留*") 通知是从组织的法律部门向员工、临时员工或其他数据保管人发送的通知。这些通知指示保管人保留以电子方式存储的信息 (ESI) 以及可能与活跃或即将发生的法律事务相关的任何材料。法律团队必须知道, 每个保管人都已收到、阅读和理解, 并同意遵守给定的说明。</span><span class="sxs-lookup"><span data-stu-id="760a6-p102">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or other data custodians. These notifications instruct custodians to preserve electronically stored information (ESI) as well as any material that may be relevant to an active or imminent legal matter. Legal teams must know that each custodian has received, read, and understood, and agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="760a6-109">合法保留通知过程</span><span class="sxs-lookup"><span data-stu-id="760a6-109">The legal hold notification process</span></span>

<span data-ttu-id="760a6-p103">组织有责任在了解即将进行的诉讼或法规调查时保留相关信息。为了符合保留要求, 组织应立即通知潜在保管人的责任, 以保留相关信息。</span><span class="sxs-lookup"><span data-stu-id="760a6-p103">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation. In order to comply with its preservation requirements, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span> 

<span data-ttu-id="760a6-p104">使用高级电子数据展示 (预览), 法律团队可以创建和自定义其法律保留通知工作流。保管人通信功能允许法律团队配置以下通知和工作流:</span><span class="sxs-lookup"><span data-stu-id="760a6-p104">With Advanced eDiscovery (Preview), legal teams can create and customize their legal hold notification workflow. The Custodian Communications feature allows legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="760a6-p105">**颁发通知**: 在法律部门向保管人发出通知 (或发起) 的合法保留通知, 这些通知可能具有有关案例的相关信息。此声明指示这些保管人保留发现可能需要的任何信息。</span><span class="sxs-lookup"><span data-stu-id="760a6-p105">**Issuance notice**: A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who might have relevant information about the case matter. This notice instructs those custodians to preserve any information that might be needed for discovery.</span></span> 
   
2.  <span data-ttu-id="760a6-p106">**重新发布通知**: 在一种情况下, 可能需要保管人来保留比以前指示的信息更多或更少的信息。在这种情况下, 您可以更新现有保留通知, 并将其重新颁发给保管人。</span><span class="sxs-lookup"><span data-stu-id="760a6-p106">**Re-Issuance notice**: During a case, custodians may be required to preserve additional or less information than was previously instructed. For this scenario, you can update the existing hold notice and re-issue it to your custodians.</span></span>

3.  <span data-ttu-id="760a6-p107">**发布通知**: 一旦解决问题且保管人不再受保留责任的限制, 就可以发布保管人, 以便在不需要时不再保留信息。此外, 您的管理员将收到通知, 告知他们已不再保留责任, 并提供有关如何恢复其活动的未解决说明。</span><span class="sxs-lookup"><span data-stu-id="760a6-p107">**Release notice**: Once a matter is resolved and the custodian is no longer subject to a preservation duty, the custodian can be released so that information is no longer retained if not needed. In addition, your custodian will be notified that they are no longer under preservation duty and with outstanding instructions on how to resume their activity.</span></span>

4. <span data-ttu-id="760a6-p108">**提醒和上报**: 在某些情况下, 仅发出通知不足以满足法律查询要求。对于每个通知, 法律团队可以安排一组提醒和升级工作流, 以自动跟进保管人并使保管人保持不响应。</span><span class="sxs-lookup"><span data-stu-id="760a6-p108">**Reminders and escalations**: In some instances, just issuing a notice is not enough to satisfy legal discovery requirements. With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow-up with unresponsive custodians.</span></span>

    - <span data-ttu-id="760a6-122">**提醒**: 在向一组保管人发出法定保留通知后, 或重新签发给保管人后, 组织可能会设置提醒, 以通知保管人无法响应保管人。</span><span class="sxs-lookup"><span data-stu-id="760a6-122">**Reminders**:  After a legal hold notice has been issued or re-issued to a set of custodians, an organization may set up reminders to alert unresponsive custodians.</span></span> 

    - <span data-ttu-id="760a6-123">**升级**: 在某些情况下, 如果保管人在一组提醒后仍无响应, 则法律团队可以设置升级工作流, 以通知保管人和他/她的经理。</span><span class="sxs-lookup"><span data-stu-id="760a6-123">**Escalations**: In some cases, if a custodian remains unresponsive even after a set of reminders, the legal team can set up an escalation workflow to notify the custodian and his/her manager.</span></span>

## <a name="role-groups-and-permissions"></a><span data-ttu-id="760a6-124">角色组和权限</span><span class="sxs-lookup"><span data-stu-id="760a6-124">Role groups and permissions</span></span> 

<span data-ttu-id="760a6-125">法律团队可以使用安全 & 合规中心中的电子数据展示相关角色组和权限控制和细分其事例活动。</span><span class="sxs-lookup"><span data-stu-id="760a6-125">Legal teams can control and segment their case activity using eDiscovery-related role groups and permissions in the Security & Compliance Center.</span></span> 

<span data-ttu-id="760a6-126">若要创建和管理合法保留通知, 用户必须是以下角色组的一部分:</span><span class="sxs-lookup"><span data-stu-id="760a6-126">To create and manage legal hold notifications, a user must be part of the following role groups:</span></span>

- <span data-ttu-id="760a6-p109">**电子数据展示管理器**-此角色组的成员可以创建和管理电子数据展示事例。他们可以添加和删除成员, 将保管人和内容位置置于保留状态, 管理法律封存通知, 创建和编辑与案例相关的内容搜索, 导出内容搜索的结果, 并准备高级搜索结果以供分析电子数据展示 (预览)。此角色组中有两个子组。这些子组之间的差异基于作用域。</span><span class="sxs-lookup"><span data-stu-id="760a6-p109">**eDiscovery Manager** - Members of this role group can create and manage eDiscovery cases. They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit Content Searches associated with a case, export the results of a Content Search, and prepare search results for analysis in Advanced eDiscovery (Preview). There are two sub-groups in this role group. The difference between these subgroups is based on scope.</span></span>

  - <span data-ttu-id="760a6-p110">**电子数据展示管理器**-可以查看和管理他们创建的或为其成员的电子数据展示事例。如果另一个电子数据展示管理器创建了一个事例, 但未将另一个电子数据展示管理器添加为这种情况的成员, 则第二个电子数据展示管理器将无法在 Security & 合规性中心的电子数据展示页面上查看或打开事例。电子数据展示管理器还可以在高级电子数据展示 (预览版) 中访问他们的案例, 以执行分析任务。</span><span class="sxs-lookup"><span data-stu-id="760a6-p110">**eDiscovery Manager** - Can view and manage the eDiscovery cases they create or are a member of. If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the eDiscovery page in the Security & Compliance Center. eDiscovery Managers can also access their cases in Advanced eDiscovery (Preview) to perform analysis tasks.</span></span>

  - <span data-ttu-id="760a6-p111">**电子数据展示管理员**-可以执行电子数据展示管理器可以执行的所有案例管理任务。此外, 电子数据展示管理员可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="760a6-p111">**eDiscovery Administrator** - Can perform all case management tasks that an eDiscovery Manager can do. Additionally, an eDiscovery Administrator can:</span></span>
    
    - <span data-ttu-id="760a6-136">查看“电子数据展示”页上列出的所有事例。</span><span class="sxs-lookup"><span data-stu-id="760a6-136">View all cases that are listed on the eDiscovery page.</span></span>
    - <span data-ttu-id="760a6-137">在组织中管理任何事例, 然后在将自己添加为案例成员。</span><span class="sxs-lookup"><span data-stu-id="760a6-137">Manage any case in the organization after they add themselves as a member of the case.</span></span>
    - <span data-ttu-id="760a6-138">组织中任何情况的高级电子数据展示 (预览版) 中的访问事例数据。</span><span class="sxs-lookup"><span data-stu-id="760a6-138">Access case data in Advanced eDiscovery (Preview) for any case in the organization.</span></span>

<span data-ttu-id="760a6-139">有关详细信息, 请参阅[在 Office 365 安全 & 合规中心中分配电子数据展示权限](../assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="760a6-139">For more information, see [Assign eDiscovery permissions in the Office 365 Security & Compliance Center](../assign-ediscovery-permissions.md).</span></span>
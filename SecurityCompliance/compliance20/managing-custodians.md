---
title: 在高级电子数据展示中与保管人合作
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
description: 高级电子数据展示中的保管人管理工具使您可以管理工作流, 以确定、保留和收集与法律案件相关人员相关的数据。
ms.openlocfilehash: 6e365f0b7f80a0a5caa050b2e0b08c94dbed4746
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151594"
---
# <a name="work-with-custodians-in-advanced-ediscovery"></a><span data-ttu-id="82f1e-103">在高级电子数据展示中与保管人合作</span><span class="sxs-lookup"><span data-stu-id="82f1e-103">Work with custodians in Advanced eDiscovery</span></span>

<span data-ttu-id="82f1e-104">当组织对法律调查做出响应时, 有关确定、保留和收集可能相关的内容的工作流基于组织中的人员, 这些人是相关数据的保管人。</span><span class="sxs-lookup"><span data-stu-id="82f1e-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="82f1e-105">在电子数据展示中, 这些人称为*数据保管人*(或仅供*保管人*), 并定义为 "具有文档或电子文件的管理控制的人员"。</span><span class="sxs-lookup"><span data-stu-id="82f1e-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="82f1e-106">例如, 电子邮件的管理员可以是包含相关邮件的邮箱的所有者。</span><span class="sxs-lookup"><span data-stu-id="82f1e-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>  

<span data-ttu-id="82f1e-107">在调查开始时, 电子数据展示团队必须快速确定与该案例相关的所有相关保管人和数据源。</span><span class="sxs-lookup"><span data-stu-id="82f1e-107">When an investigation begins, the eDiscovery team must quickly identify all the relevant custodians and data sources related to the case.</span></span> <span data-ttu-id="82f1e-108">随着时间的推移, 保管人的列表及其数据源可能会增加或 decreasse。</span><span class="sxs-lookup"><span data-stu-id="82f1e-108">Over time, the list of custodians and their data sources may increase or decreasse.</span></span> <span data-ttu-id="82f1e-109">因此, 组织必须在案例的整个生命周期中维护、保留和收集 custodial 内容围绕的控制过程。</span><span class="sxs-lookup"><span data-stu-id="82f1e-109">As a result, organizations must maintain a controlled process around identifying, preserving, and collecting custodial content throughout the life cycle of a case.</span></span>

<span data-ttu-id="82f1e-110">在高级电子数据展示案例中, 法律团队可以将其组织中的个人添加为保管人, 并自动识别和保留 custodial 数据源 (如 Exchange 邮箱、OneDrive 帐户和 SharePoint 和团队网站)。</span><span class="sxs-lookup"><span data-stu-id="82f1e-110">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and automatically identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="82f1e-111">通过在高级电子数据展示中使用内置保管人管理工具, 组织可以保护以电子方式存储的信息不受无意 (或有意) 删除的保护。</span><span class="sxs-lookup"><span data-stu-id="82f1e-111">By using the built-in custodian management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="82f1e-112">这使您可以消除耗时且容易出错的过程, 以手动执行合法保留过程。</span><span class="sxs-lookup"><span data-stu-id="82f1e-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span> 

<span data-ttu-id="82f1e-113">有关使用保管人的详细信息, 请参阅以下内容:</span><span class="sxs-lookup"><span data-stu-id="82f1e-113">For more information about working with custodians, see the following:</span></span> 

- [<span data-ttu-id="82f1e-114">向事例添加保管人</span><span class="sxs-lookup"><span data-stu-id="82f1e-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="82f1e-115">在某个情况下管理保管人</span><span class="sxs-lookup"><span data-stu-id="82f1e-115">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="82f1e-116">查看保管人活动</span><span class="sxs-lookup"><span data-stu-id="82f1e-116">View custodian activity</span></span>](view-custodian-activity.md)

## <a name="advanced-ediscovery-permissions"></a><span data-ttu-id="82f1e-117">高级电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="82f1e-117">Advanced eDiscovery permissions</span></span>

<span data-ttu-id="82f1e-118">在高级电子数据展示中, 可以使用内置的电子数据展示管理器角色组向法律调查人员分配必要的权限, 以便他们可以在高级电子数据展示中管理端到端工作流。</span><span class="sxs-lookup"><span data-stu-id="82f1e-118">In Advanced eDiscovery, you can use the built-in eDiscovery Manager role group to assign the necessary permissions to legal investigators so they can manage the end-to-end workflow in Advanced eDiscovery.</span></span> <span data-ttu-id="82f1e-119">或者, 您可以创建具有在高级电子数据展示中的情况下执行某些操作所需的角色子集的自定义角色组。</span><span class="sxs-lookup"><span data-stu-id="82f1e-119">Alternatively, you can create custom role groups with a subset of the roles necessary to perform certain actions in a case in Advanced eDiscovery.</span></span> <span data-ttu-id="82f1e-120">有关电子数据展示相关角色的详细信息, 请参阅[在安全 _AMP_ 合规中心中分配电子数据展示权限](../assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="82f1e-120">For more information about eDiscovery-related roles, see [Assign eDiscovery permissions in the Security & Compliance Center](../assign-ediscovery-permissions.md).</span></span>

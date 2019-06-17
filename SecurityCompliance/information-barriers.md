---
title: 信息障碍概述
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用信息障碍以确保在组织内使用 Microsoft 团队进行通信合规性。
ms.openlocfilehash: a2c202d08f1de60f92f13b2ac4c2b9d3c7f900e8
ms.sourcegitcommit: eeb51470d8996e93fac28d7f12c6117e2aeb0cf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2019
ms.locfileid: "34935934"
---
# <a name="information-barriers-preview"></a><span data-ttu-id="cfece-103">信息障碍 (预览)</span><span class="sxs-lookup"><span data-stu-id="cfece-103">Information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="cfece-104">概述</span><span class="sxs-lookup"><span data-stu-id="cfece-104">Overview</span></span>

<span data-ttu-id="cfece-105">Microsoft 云服务包括强大的通信和协作功能。</span><span class="sxs-lookup"><span data-stu-id="cfece-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="cfece-106">但假设您要限制两个组之间的通信, 以避免组织中发生利益冲突。</span><span class="sxs-lookup"><span data-stu-id="cfece-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="cfece-107">或者, 您可能希望限制组织内的某些人之间的通信, 以便保护内部信息。</span><span class="sxs-lookup"><span data-stu-id="cfece-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="cfece-108">Microsoft 365 支持跨组和组织进行通信和协作, 因此有一种方法可以在必要时限制特定用户组之间的通信吗？</span><span class="sxs-lookup"><span data-stu-id="cfece-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="cfece-109">通过信息障碍, 你可以!</span><span class="sxs-lookup"><span data-stu-id="cfece-109">With information barriers, you can!</span></span> 

<span data-ttu-id="cfece-110">信息障碍现在在预览中, 从 Microsoft 团队开始。</span><span class="sxs-lookup"><span data-stu-id="cfece-110">Information barriers are in preview now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="cfece-111">当您的组织可使用这些功能时, 合规性管理员或信息屏障管理员可以定义策略以允许或阻止 Microsoft 团队中的用户组之间的通信。</span><span class="sxs-lookup"><span data-stu-id="cfece-111">When these features are available for your organization, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="cfece-112">信息屏障策略可用于以下情况:</span><span class="sxs-lookup"><span data-stu-id="cfece-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="cfece-113">一天 trader 无法对市场营销团队中的人员进行呼叫</span><span class="sxs-lookup"><span data-stu-id="cfece-113">A day trader cannot call someone on the marketing team</span></span>
- <span data-ttu-id="cfece-114">从事机密公司信息的财务人员无法从其组织内的某些组接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="cfece-114">Finance personnel working on confidential company information cannot receive calls from certain groups within their organization</span></span>
- <span data-ttu-id="cfece-115">具有贸易秘密材料的内部团队无法与组织内特定组中的人员进行在线呼叫或聊天</span><span class="sxs-lookup"><span data-stu-id="cfece-115">An internal team with trade secret material cannot call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="cfece-116">研究团队只能与产品开发团队进行在线通话或聊天</span><span class="sxs-lookup"><span data-stu-id="cfece-116">A research team can only call or chat online with a product development team</span></span>

<span data-ttu-id="cfece-117">对于所有这些示例方案 (及更多), 可以将信息屏障策略定义为阻止或允许在 Microsoft 团队中进行通信。</span><span class="sxs-lookup"><span data-stu-id="cfece-117">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="cfece-118">此类策略可以阻止用户不应对其进行呼叫或聊天, 或使用户只能与 Microsoft 团队中的特定组进行通信。</span><span class="sxs-lookup"><span data-stu-id="cfece-118">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="cfece-119">在信息屏障策略生效时, 只要这些策略涵盖的用户尝试与 Microsoft 团队中的其他人通信, 就会执行检查以阻止 (或允许) 通信 (由信息屏障策略定义)。</span><span class="sxs-lookup"><span data-stu-id="cfece-119">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="cfece-120">若要了解有关信息障碍的用户体验方面的详细信息, 请参阅[Microsoft 团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="cfece-120">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="cfece-121">信息障碍将不适用于电子邮件通信或通过 SharePoint Online 或 OneDrive 进行文件共享。</span><span class="sxs-lookup"><span data-stu-id="cfece-121">Information barriers will not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="cfece-122">必需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="cfece-122">Required licenses and permissions</span></span>

<span data-ttu-id="cfece-123">**目前, 信息屏障功能位于私人预览版中**。</span><span class="sxs-lookup"><span data-stu-id="cfece-123">**Currently, the information barrier feature is in private preview**.</span></span> <span data-ttu-id="cfece-124">当这些功能普遍可用时, 它们将包含在订阅中, 例如:</span><span class="sxs-lookup"><span data-stu-id="cfece-124">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="cfece-125">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="cfece-125">Microsoft 365 E5</span></span>
- <span data-ttu-id="cfece-126">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="cfece-126">Office 365 E5</span></span>
- <span data-ttu-id="cfece-127">Office 365 高级合规版</span><span class="sxs-lookup"><span data-stu-id="cfece-127">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="cfece-128">Microsoft 365 E5 信息保护和合规性</span><span class="sxs-lookup"><span data-stu-id="cfece-128">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="cfece-129">有关更多详细信息, 请参阅[合规性解决方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。</span><span class="sxs-lookup"><span data-stu-id="cfece-129">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="cfece-130">若要[定义或编辑信息障碍策略](information-barriers-policies.md), 您必须分配有下列角色之一:</span><span class="sxs-lookup"><span data-stu-id="cfece-130">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="cfece-131">Microsoft 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="cfece-131">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="cfece-132">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="cfece-132">Office 365 global administrator</span></span>
- <span data-ttu-id="cfece-133">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="cfece-133">Compliance administrator</span></span>
- <span data-ttu-id="cfece-134">信息障碍管理员</span><span class="sxs-lookup"><span data-stu-id="cfece-134">Information barriers administrator</span></span>

<span data-ttu-id="cfece-135">您必须熟悉 PowerShell cmdlet, 才能定义、验证或编辑信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="cfece-135">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="cfece-136">尽管我们在操作[方法信息](information-barriers-policies.md)中提供了几个 PowerShell cmdlet 示例, 但你需要了解组织的其他详细信息, 如参数。</span><span class="sxs-lookup"><span data-stu-id="cfece-136">Although we provide several examples of PowerShell cmdlets in the [how-to information](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cfece-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cfece-137">Next steps</span></span>

- [<span data-ttu-id="cfece-138">了解有关 Microsoft 团队中的信息障碍的详细信息</span><span class="sxs-lookup"><span data-stu-id="cfece-138">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="cfece-139">请参阅可用于信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="cfece-139">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="cfece-140">定义信息障碍策略</span><span class="sxs-lookup"><span data-stu-id="cfece-140">Define policies for information barriers</span></span>](information-barriers-policies.md) 


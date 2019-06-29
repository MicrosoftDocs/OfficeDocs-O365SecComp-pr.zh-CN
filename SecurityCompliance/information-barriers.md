---
title: 信息障碍概述
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用信息障碍以确保在组织内使用 Microsoft 团队进行通信合规性。
ms.openlocfilehash: 9750eab3c91b40cc96e16a386dbf59ba767ae877
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394277"
---
# <a name="information-barriers-preview"></a><span data-ttu-id="1256d-103">信息障碍 (预览)</span><span class="sxs-lookup"><span data-stu-id="1256d-103">Information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="1256d-104">概述</span><span class="sxs-lookup"><span data-stu-id="1256d-104">Overview</span></span>

<span data-ttu-id="1256d-105">Microsoft 云服务包括强大的通信和协作功能。</span><span class="sxs-lookup"><span data-stu-id="1256d-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="1256d-106">但假设您要限制两个组之间的通信, 以避免组织中发生利益冲突。</span><span class="sxs-lookup"><span data-stu-id="1256d-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="1256d-107">或者, 您可能希望限制组织内的某些人之间的通信, 以便保护内部信息。</span><span class="sxs-lookup"><span data-stu-id="1256d-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="1256d-108">Microsoft 365 支持跨组和组织进行通信和协作, 因此有一种方法可以在必要时限制特定用户组之间的通信吗？</span><span class="sxs-lookup"><span data-stu-id="1256d-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="1256d-109">通过信息障碍, 你可以!</span><span class="sxs-lookup"><span data-stu-id="1256d-109">With information barriers, you can!</span></span> 

<span data-ttu-id="1256d-110">信息障碍现在在预览中, 从 Microsoft 团队开始。</span><span class="sxs-lookup"><span data-stu-id="1256d-110">Information barriers are in preview now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="1256d-111">当您的组织可使用这些功能时, 合规性管理员或信息屏障管理员可以定义策略以允许或阻止 Microsoft 团队中的用户组之间的通信。</span><span class="sxs-lookup"><span data-stu-id="1256d-111">When these features are available for your organization, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="1256d-112">信息屏障策略可用于以下情况:</span><span class="sxs-lookup"><span data-stu-id="1256d-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="1256d-113">一天 trader 无法对市场营销团队中的人员进行呼叫</span><span class="sxs-lookup"><span data-stu-id="1256d-113">A day trader cannot call someone on the marketing team</span></span>
- <span data-ttu-id="1256d-114">从事机密公司信息的财务人员无法从其组织内的某些组接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="1256d-114">Finance personnel working on confidential company information cannot receive calls from certain groups within their organization</span></span>
- <span data-ttu-id="1256d-115">具有贸易秘密材料的内部团队无法与组织内特定组中的人员进行在线呼叫或聊天</span><span class="sxs-lookup"><span data-stu-id="1256d-115">An internal team with trade secret material cannot call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="1256d-116">研究团队只能与产品开发团队进行在线通话或聊天</span><span class="sxs-lookup"><span data-stu-id="1256d-116">A research team can only call or chat online with a product development team</span></span>

<span data-ttu-id="1256d-117">对于所有这些示例方案 (及更多), 可以将信息屏障策略定义为阻止或允许在 Microsoft 团队中进行通信。</span><span class="sxs-lookup"><span data-stu-id="1256d-117">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="1256d-118">此类策略可以阻止用户不应对其进行呼叫或聊天, 或使用户只能与 Microsoft 团队中的特定组进行通信。</span><span class="sxs-lookup"><span data-stu-id="1256d-118">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="1256d-119">在信息屏障策略生效时, 只要这些策略涵盖的用户尝试与 Microsoft 团队中的其他人通信, 就会执行检查以阻止 (或允许) 通信 (由信息屏障策略定义)。</span><span class="sxs-lookup"><span data-stu-id="1256d-119">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="1256d-120">若要了解有关信息障碍的用户体验方面的详细信息, 请参阅[Microsoft 团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="1256d-120">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1256d-121">目前, 信息障碍不适用于电子邮件通信或通过 SharePoint Online 或 OneDrive 进行文件共享。</span><span class="sxs-lookup"><span data-stu-id="1256d-121">Currently, information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="1256d-122">此外, 信息障碍独立于[合规性边界](set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="1256d-122">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="1256d-123">在定义和应用信息屏障策略之前, 请确保您的组织没有有效的[Exchange 通讯簿策略](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies)。</span><span class="sxs-lookup"><span data-stu-id="1256d-123">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span>  

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="1256d-124">信息障碍发生的情况</span><span class="sxs-lookup"><span data-stu-id="1256d-124">What happens with information barriers</span></span>

<span data-ttu-id="1256d-125">在信息屏障策略就绪后, 不应与其他特定用户通信的人员将无法找到、选择、聊天或呼叫这些用户。</span><span class="sxs-lookup"><span data-stu-id="1256d-125">When information barrier policies are in place, people who should not communicate with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="1256d-126">通过信息障碍, 检查措施可防止未经授权的通信。</span><span class="sxs-lookup"><span data-stu-id="1256d-126">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="1256d-127">最初, 信息障碍仅适用于 Microsoft 团队聊天和频道。</span><span class="sxs-lookup"><span data-stu-id="1256d-127">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="1256d-128">在 Microsoft 团队中, 信息障碍策略决定并阻止以下类型的未经授权的通信:</span><span class="sxs-lookup"><span data-stu-id="1256d-128">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>
- <span data-ttu-id="1256d-129">搜索用户</span><span class="sxs-lookup"><span data-stu-id="1256d-129">Searching for a user</span></span>
- <span data-ttu-id="1256d-130">向团队添加成员</span><span class="sxs-lookup"><span data-stu-id="1256d-130">Adding a member to a team</span></span>
- <span data-ttu-id="1256d-131">启动与某人的聊天会话</span><span class="sxs-lookup"><span data-stu-id="1256d-131">Starting a chat session with someone</span></span>
- <span data-ttu-id="1256d-132">启动群聊天</span><span class="sxs-lookup"><span data-stu-id="1256d-132">Starting a group chat</span></span>
- <span data-ttu-id="1256d-133">邀请某人加入会议</span><span class="sxs-lookup"><span data-stu-id="1256d-133">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="1256d-134">共享屏幕</span><span class="sxs-lookup"><span data-stu-id="1256d-134">Sharing a screen</span></span>
- <span data-ttu-id="1256d-135">发出呼叫</span><span class="sxs-lookup"><span data-stu-id="1256d-135">Placing a call</span></span> 

<span data-ttu-id="1256d-136">如果涉及的人员包含在信息屏障策略中以阻止活动, 则无法继续。</span><span class="sxs-lookup"><span data-stu-id="1256d-136">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="1256d-137">此外, 在信息屏障策略中包括的每个人都可以阻止与 Microsoft 团队中的其他人通信。</span><span class="sxs-lookup"><span data-stu-id="1256d-137">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="1256d-138">当受信息障碍策略影响的人员是同一个团队或组聊天的一部分时, 他们可能会从这些聊天会话中删除, 并且可能不允许与组进行进一步通信。</span><span class="sxs-lookup"><span data-stu-id="1256d-138">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="1256d-139">若要了解有关信息障碍的用户体验方面的详细信息, 请参阅[Microsoft 团队中的信息障碍](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="1256d-139">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="1256d-140">必需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="1256d-140">Required licenses and permissions</span></span>

<span data-ttu-id="1256d-141">**目前, 信息障碍处于预览阶段**。</span><span class="sxs-lookup"><span data-stu-id="1256d-141">**Currently, information barriers are in preview**.</span></span> <span data-ttu-id="1256d-142">当这些功能普遍可用时, 它们将包含在订阅中, 例如:</span><span class="sxs-lookup"><span data-stu-id="1256d-142">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="1256d-143">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1256d-143">Microsoft 365 E5</span></span>
- <span data-ttu-id="1256d-144">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="1256d-144">Office 365 E5</span></span>
- <span data-ttu-id="1256d-145">Office 365 高级合规版</span><span class="sxs-lookup"><span data-stu-id="1256d-145">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="1256d-146">Microsoft 365 E5 信息保护和合规性</span><span class="sxs-lookup"><span data-stu-id="1256d-146">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="1256d-147">有关更多详细信息, 请参阅[合规性解决方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。</span><span class="sxs-lookup"><span data-stu-id="1256d-147">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="1256d-148">若要[定义或编辑信息障碍策略](information-barriers-policies.md), 您必须分配有下列角色之一:</span><span class="sxs-lookup"><span data-stu-id="1256d-148">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="1256d-149">Microsoft 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="1256d-149">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="1256d-150">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="1256d-150">Office 365 global administrator</span></span>
- <span data-ttu-id="1256d-151">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="1256d-151">Compliance administrator</span></span>
- <span data-ttu-id="1256d-152">IB 合规性管理 (这是一个新角色!)</span><span class="sxs-lookup"><span data-stu-id="1256d-152">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="1256d-153">(若要了解有关角色和权限的详细信息, 请参阅[Office 365 Security & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。)</span><span class="sxs-lookup"><span data-stu-id="1256d-153">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="1256d-154">您必须熟悉 PowerShell cmdlet, 才能定义、验证或编辑信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="1256d-154">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="1256d-155">尽管我们在操作[方法一文](information-barriers-policies.md)中提供了几个 PowerShell cmdlet 示例, 但你需要了解组织的其他详细信息, 如参数。</span><span class="sxs-lookup"><span data-stu-id="1256d-155">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1256d-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1256d-156">Next steps</span></span>

- [<span data-ttu-id="1256d-157">了解有关 Microsoft 团队中的信息障碍的详细信息</span><span class="sxs-lookup"><span data-stu-id="1256d-157">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [<span data-ttu-id="1256d-158">请参阅可用于信息屏障策略的属性</span><span class="sxs-lookup"><span data-stu-id="1256d-158">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)

- [<span data-ttu-id="1256d-159">定义信息障碍策略</span><span class="sxs-lookup"><span data-stu-id="1256d-159">Define policies for information barriers</span></span>](information-barriers-policies.md)

- [<span data-ttu-id="1256d-160">编辑 (或删除) 信息屏障策略 (预览)</span><span class="sxs-lookup"><span data-stu-id="1256d-160">Edit (or remove) information barrier policies (Preview)</span></span>](information-barriers-edit-segments-policies.md.md) 


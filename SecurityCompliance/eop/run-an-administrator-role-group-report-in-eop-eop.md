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
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="16304-104">在 EOP 中运行管理员角色组报告</span><span class="sxs-lookup"><span data-stu-id="16304-104">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="16304-105">当管理员向管理员角色组添加成员或从中删除成员时, Exchange Online Protection (EOP) 会记录每次发生的事件。</span><span class="sxs-lookup"><span data-stu-id="16304-105">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="16304-106">在 Exchange 管理中心 (EAC) 中运行管理员角色组报告时, 条目将显示为搜索结果, 并包括受影响的角色组、更改角色组成员身份的用户以及进行成员身份更新的用户。</span><span class="sxs-lookup"><span data-stu-id="16304-106">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="16304-107">使用此报告可以对已分配给组织中的用户的管理权限的更改进行监视。</span><span class="sxs-lookup"><span data-stu-id="16304-107">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="16304-108">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="16304-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="16304-109">估计完成时间：2 分钟</span><span class="sxs-lookup"><span data-stu-id="16304-109">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="16304-110">若要打开 Exchange 管理中心, 请参阅 exchange [Online Protection 中的 exchange 管理中心](../exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="16304-110">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="16304-p103">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"报告"部分。</span><span class="sxs-lookup"><span data-stu-id="16304-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="16304-113">有关可能适用于本主题中的过程的键盘快捷方式的信息, 请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="16304-113">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="16304-114">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="16304-114">Having problems?</span></span> <span data-ttu-id="16304-115">在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="16304-115">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="16304-116">使用 EAC 运行管理员角色组报告</span><span class="sxs-lookup"><span data-stu-id="16304-116">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="16304-117">运行管理员角色组报告, 在特定时间范围内查找对组织中的管理角色组的更改。</span><span class="sxs-lookup"><span data-stu-id="16304-117">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>
  
1. <span data-ttu-id="16304-118">在 EAC 中, 导航到 "**合规性管理** \> **审核**", 然后选择 "**运行管理员角色组报告**"。</span><span class="sxs-lookup"><span data-stu-id="16304-118">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="16304-119">选择 "**开始日期**" 和 "**结束日期**"。</span><span class="sxs-lookup"><span data-stu-id="16304-119">Choose the **Start date** and **End date**.</span></span> <span data-ttu-id="16304-120">默认情况下，报告将搜索在过去两周内对管理员角色组所做的更改。</span><span class="sxs-lookup"><span data-stu-id="16304-120">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="16304-121">若要查看特定角色组的更改, 请单击 "**选择角色组**"。</span><span class="sxs-lookup"><span data-stu-id="16304-121">To view the changes for a specific role group, click **Select role groups**.</span></span> <span data-ttu-id="16304-122">在随后的对话框中选择角色组, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="16304-122">Select the role group (or groups) in the subsequent dialog box, and click **OK**.</span></span> <span data-ttu-id="16304-123">您也可以将字段留空，以查找所有更改的角色组。</span><span class="sxs-lookup"><span data-stu-id="16304-123">You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="16304-124">单击"搜索"。</span><span class="sxs-lookup"><span data-stu-id="16304-124">Click **Search**.</span></span>

<span data-ttu-id="16304-p107">如果使用指定的条件找到了所有更改，则这些更改会显示在结果窗格中。单击搜索结果中的角色组可在详细信息窗格中查看更改。</span><span class="sxs-lookup"><span data-stu-id="16304-p107">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="16304-127">如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="16304-127">How do you know this worked?</span></span>

<span data-ttu-id="16304-p108">如果您已成功运行管理员角色组报告，那么在此日期范围内更改的角色组将显示在搜索结果窗格中。如果没有显示任何结果，那么在指定日期范围内没有发生对角色组的任何更改。如果您认为应该显示结果，请更改日期范围，然后再次运行报告。</span><span class="sxs-lookup"><span data-stu-id="16304-p108">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>
  
## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="16304-131">监视角色组成员身份的更改</span><span class="sxs-lookup"><span data-stu-id="16304-131">Monitor changes to role group membership</span></span>

<span data-ttu-id="16304-p109">向某个角色组添加成员或删除其中的成员时，在详细信息窗格中显示的搜索结果将会指示角色组成员身份已进行更新，并列出当前的成员。但搜索结果并不会明确地指出已添加或已删除的用户。</span><span class="sxs-lookup"><span data-stu-id="16304-p109">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>
  
<span data-ttu-id="16304-134">若要确定是否添加或删除了某个用户，则必须对报告中的两个不同条目进行比较。</span><span class="sxs-lookup"><span data-stu-id="16304-134">To determine if a user was added or removed, you have to compare two separate entries in the report.</span></span> <span data-ttu-id="16304-135">例如, 让我们来看看 "**支持人员**" 角色组的以下日志条目:</span><span class="sxs-lookup"><span data-stu-id="16304-135">For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>
  
> <span data-ttu-id="16304-136">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="16304-136">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="16304-137">管理员</span><span class="sxs-lookup"><span data-stu-id="16304-137">Administrator</span></span> <br> <span data-ttu-id="16304-138">Updated members: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="16304-138">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="16304-139">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="16304-139">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="16304-140">管理员</span><span class="sxs-lookup"><span data-stu-id="16304-140">Administrator</span></span> <br> <span data-ttu-id="16304-141">Updated members: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="16304-141">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="16304-142">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="16304-142">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="16304-143">Administrator</span><span class="sxs-lookup"><span data-stu-id="16304-143">Administrator</span></span> <br> <span data-ttu-id="16304-144">Updated members: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="16304-144">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="16304-145">在本示例中，Administrator 用户帐户做出了以下更改：</span><span class="sxs-lookup"><span data-stu-id="16304-145">In this example, the Administrator user account made the following changes:</span></span>
  
- <span data-ttu-id="16304-146">在2/06/2018 上, 他们添加了用户 tonip。</span><span class="sxs-lookup"><span data-stu-id="16304-146">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="16304-147">在2/19/2018 上, 他们删除了用户 pilarp。</span><span class="sxs-lookup"><span data-stu-id="16304-147">On 2/19/2018, they removed the user pilarp.</span></span>

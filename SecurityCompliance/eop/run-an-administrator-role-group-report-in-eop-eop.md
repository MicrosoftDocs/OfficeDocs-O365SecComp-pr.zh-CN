---
title: '在 EOP 中运行管理员角色组报告 '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: 每当管理员在管理员角色组中添加或删除成员时，Microsoft Exchange Online Protection (EOP) 都会进行记录。
ms.openlocfilehash: 49311faa4ee54fafa1c05a2314ed2f9d74cbe5a5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027199"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="cf75e-103">在 EOP 中运行管理员角色组报告</span><span class="sxs-lookup"><span data-stu-id="cf75e-103">Run an administrator role group report in EOP</span></span> 

 <span data-ttu-id="cf75e-p101">每当管理员在管理员角色组中添加或删除成员时，Microsoft Exchange Online Protection (EOP) 都会进行记录。在 Exchange 管理中心中运行管理员角色组报告时，条目会作为搜索结果显示，其中包括受影响的角色组、更改角色组成员身份的用户和时间，以及做出的成员身份更新。使用此报告可以对已分配给组织中的用户的管理权限的更改进行监视。</span><span class="sxs-lookup"><span data-stu-id="cf75e-p101">When an administrator adds members to or removes members from administrator role groups, Microsoft Exchange Online Protection (EOP) logs each occurrence. When you run an administrator role group report in the Exchange admin center, entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made. Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cf75e-107">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="cf75e-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cf75e-108">估计完成时间：2 分钟</span><span class="sxs-lookup"><span data-stu-id="cf75e-108">Estimated time to complete: 2 minutes</span></span>
    
- <span data-ttu-id="cf75e-p102">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"报告"部分。</span><span class="sxs-lookup"><span data-stu-id="cf75e-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="cf75e-111">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="cf75e-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="cf75e-p103">遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="cf75e-p103">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="cf75e-115">使用 EAC 运行管理员角色组报告</span><span class="sxs-lookup"><span data-stu-id="cf75e-115">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="cf75e-116">运行管理员角色组报告，以查找在特定时间段内对组织中的管理角色组所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cf75e-116">Run the administrator role group report to find the changes to management role groups in your organization within a particular timeframe.</span></span>
  
1. <span data-ttu-id="cf75e-117">在 EAC 中，导航到**合规性管理** \> **审核**，并选择**运行管理员角色组报告**。</span><span class="sxs-lookup"><span data-stu-id="cf75e-117">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>
    
2. <span data-ttu-id="cf75e-p104">选择**开始日期**和**结束日期**。默认情况下，报表搜索在过去两周内管理员角色组所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cf75e-p104">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>
    
3. <span data-ttu-id="cf75e-p105">若要查看特定的角色组的更改，请单击**选择角色组**。在随后出现的对话框中，选择角色组 （或组），然后单击**确定**。您还可以将字段留空，以查找所有已更改的角色组。</span><span class="sxs-lookup"><span data-stu-id="cf75e-p105">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>
    
4. <span data-ttu-id="cf75e-123">单击"搜索"。</span><span class="sxs-lookup"><span data-stu-id="cf75e-123">Click **Search**.</span></span>
    
<span data-ttu-id="cf75e-p106">如果使用指定的条件找到了所有更改，则这些更改会显示在结果窗格中。单击搜索结果中的角色组可在详细信息窗格中查看更改。</span><span class="sxs-lookup"><span data-stu-id="cf75e-p106">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="cf75e-126">您如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="cf75e-126">How do you know this worked?</span></span>

<span data-ttu-id="cf75e-p107">如果您已成功运行管理员角色组报告，那么在此日期范围内更改的角色组将显示在搜索结果窗格中。如果没有显示任何结果，那么在指定日期范围内没有发生对角色组的任何更改。如果您认为应该显示结果，请更改日期范围，然后再次运行报告。</span><span class="sxs-lookup"><span data-stu-id="cf75e-p107">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>
  
## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="cf75e-130">监视角色组成员身份的更改</span><span class="sxs-lookup"><span data-stu-id="cf75e-130">Monitor changes to role group membership</span></span>

<span data-ttu-id="cf75e-p108">向某个角色组添加成员或删除其中的成员时，在详细信息窗格中显示的搜索结果将会指示角色组成员身份已进行更新，并列出当前的成员。但搜索结果并不会明确地指出已添加或已删除的用户。</span><span class="sxs-lookup"><span data-stu-id="cf75e-p108">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>
  
<span data-ttu-id="cf75e-p109">若要确定已添加或删除用户，您需要比较报表中的两个单独的条目。例如，让我们看一下**HelpDesk**角色组的以下日志项：</span><span class="sxs-lookup"><span data-stu-id="cf75e-p109">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span> 
  
 <span data-ttu-id="cf75e-135">**1/27/2013 4:43 PM**</span><span class="sxs-lookup"><span data-stu-id="cf75e-135">**1/27/2013 4:43 PM**</span></span>
  
 <span data-ttu-id="cf75e-136">**管理员**</span><span class="sxs-lookup"><span data-stu-id="cf75e-136">**Administrator**</span></span>
  
 <span data-ttu-id="cf75e-137">**Updated members: Administrator;annb,florencef;pilarp**</span><span class="sxs-lookup"><span data-stu-id="cf75e-137">**Updated members: Administrator;annb,florencef;pilarp**</span></span>
  
 <span data-ttu-id="cf75e-138">**2/06/2013 10:09 AM**</span><span class="sxs-lookup"><span data-stu-id="cf75e-138">**2/06/2013 10:09 AM**</span></span>
  
 <span data-ttu-id="cf75e-139">**管理员**</span><span class="sxs-lookup"><span data-stu-id="cf75e-139">**Administrator**</span></span>
  
 <span data-ttu-id="cf75e-140">**Updated members: Administrator;annb;florencef;pilarp;tonip**</span><span class="sxs-lookup"><span data-stu-id="cf75e-140">**Updated members: Administrator;annb;florencef;pilarp;tonip**</span></span>
  
 <span data-ttu-id="cf75e-141">**2/19/2013 2:12 PM**</span><span class="sxs-lookup"><span data-stu-id="cf75e-141">**2/19/2013 2:12 PM**</span></span>
  
 <span data-ttu-id="cf75e-142">**管理员**</span><span class="sxs-lookup"><span data-stu-id="cf75e-142">**Administrator**</span></span>
  
 <span data-ttu-id="cf75e-143">**Updated members: Administrator;annb;florencef;tonip**</span><span class="sxs-lookup"><span data-stu-id="cf75e-143">**Updated members: Administrator;annb;florencef;tonip**</span></span>
  
<span data-ttu-id="cf75e-144">在本示例中，Administrator 用户帐户做出了以下更改：</span><span class="sxs-lookup"><span data-stu-id="cf75e-144">In this example, the Administrator user account made the following changes:</span></span>
  
- <span data-ttu-id="cf75e-145">在 2013 年 2 月 6 日添加了用户 tonip。</span><span class="sxs-lookup"><span data-stu-id="cf75e-145">On 2/06/2013, it added the user tonip.</span></span>
    
- <span data-ttu-id="cf75e-146">在 2013 年 2 月 19 日删除了用户 pilarp。</span><span class="sxs-lookup"><span data-stu-id="cf75e-146">On 2/19/2013, it removed the user pilarp.</span></span>
    

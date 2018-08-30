---
title: 使用 Office 365 云应用安全管理应用权限
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Office 365 云应用程序安全性的应用程序权限帮助您管理您的用户下载用于 Office 365 数据的应用程序
ms.openlocfilehash: 7bda35bbbf3a16cd1d386adcb03b1c7c4176913a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525795"
---
# <a name="manage-app-permissions-using-office-365-cloud-app-security"></a><span data-ttu-id="daf00-103">使用 Office 365 云应用安全管理应用权限</span><span class="sxs-lookup"><span data-stu-id="daf00-103">Manage app permissions using Office 365 Cloud App Security</span></span>

<span data-ttu-id="daf00-104">Office 365 高级安全管理现在是 Office 365 云应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="daf00-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="daf00-105">评估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="daf00-105">****Evaluation** \>**</span></span>|<span data-ttu-id="daf00-106">规划 * *\>**</span><span class="sxs-lookup"><span data-stu-id="daf00-106">****Planning** \>**</span></span>|<span data-ttu-id="daf00-107">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="daf00-107">****Deployment** \>**</span></span>|<span data-ttu-id="daf00-108">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="daf00-108">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="daf00-109">启动评估</span><span class="sxs-lookup"><span data-stu-id="daf00-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="daf00-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="daf00-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="daf00-111">开始部署</span><span class="sxs-lookup"><span data-stu-id="daf00-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="daf00-112">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="daf00-112">You are here!</span></span>  <br/> [<span data-ttu-id="daf00-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="daf00-113">Next steps</span></span>](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="daf00-p101">人员喜欢的应用程序和他们通常下载这些，尤其是人员思考的应用程序将通过使其更易于获取在其工作或学校信息节省时间。但是，某些应用程序可能存在一定的安全风险到您的组织，哪些信息取决于他们访问和如何处理该信息。[Office 365 云应用程序安全性](office-365-cas-overview.md)，如果您是全局或安全管理员，您可以管理应用程序权限为您的组织。您可以查看正在使用的应用程序的人员的 Office 365 数据哪些权限这些应用程序都有和更多内容。</span><span class="sxs-lookup"><span data-stu-id="daf00-p101">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage app permissions for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="daf00-118">本文介绍在哪里管理应用程序的权限、 如何批准或禁止应用程序，以及如何创建应用程序查询。</span><span class="sxs-lookup"><span data-stu-id="daf00-118">This article describes where to go to manage app permissions, how to approve or ban an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-app-permissions-page"></a><span data-ttu-id="daf00-119">如何查找管理应用程序权限页</span><span class="sxs-lookup"><span data-stu-id="daf00-119">How to find the Manage app permissions page</span></span>
<span data-ttu-id="daf00-120"><a name="findappperms"> </a></span><span class="sxs-lookup"><span data-stu-id="daf00-120"></span></span>

> [!NOTE]
> <span data-ttu-id="daf00-p102">应用程序权限管理 Office 365 云应用程序安全性门户中。您必须是要执行以下任务的全局管理员或 security 管理员程序。若要了解详细，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="daf00-p102">App permissions are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="daf00-p103">转到[https://protection.office.com](https://protection.office.com)和 Office 365 中使用您的工作或学校帐户登录。(您将转到安全&amp;合规性中心。)</span><span class="sxs-lookup"><span data-stu-id="daf00-p103">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="daf00-126">转到**通知** \> **管理高级通知**。</span><span class="sxs-lookup"><span data-stu-id="daf00-126">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="daf00-127">单击 （或点击）**转到 Office 365 云应用程序安全性**。</span><span class="sxs-lookup"><span data-stu-id="daf00-127">Click (or tap) **Go to Office 365 Cloud App Security**.</span></span>
    
    ![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
    > [!NOTE]
    > <span data-ttu-id="daf00-p104">如果 Office 365 云应用程序安全性未尚未开启，您可以在此页上执行。请参阅[为 Office 365 云应用程序安全性做好准备](get-ready-for-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="daf00-p104">If Office 365 Cloud App Security is not turned on yet, you can do that on this page. See [Get ready for Office 365 Cloud App Security](get-ready-for-office-365-cas.md).</span></span> 
  
4. <span data-ttu-id="daf00-131">选择**调查** \> **应用程序权限**。</span><span class="sxs-lookup"><span data-stu-id="daf00-131">Choose **Investigate** \> **App permissions**.</span></span>
    
    ![在 O365 CAS 门户中，选择调查。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
## <a name="what-youll-see-on-the-manage-app-permissions-page"></a><span data-ttu-id="daf00-133">您将看到管理应用程序权限页上</span><span class="sxs-lookup"><span data-stu-id="daf00-133">What you'll see on the Manage app permissions page</span></span>
<span data-ttu-id="daf00-134"><a name="whatsonpage"> </a></span><span class="sxs-lookup"><span data-stu-id="daf00-134"></span></span>

<span data-ttu-id="daf00-135">下表介绍了在管理应用程序权限页上的控件和可用选项。</span><span class="sxs-lookup"><span data-stu-id="daf00-135">The following table describes the controls and options available on the Manage app permissions page.</span></span>
  
|<span data-ttu-id="daf00-136">**项**</span><span class="sxs-lookup"><span data-stu-id="daf00-136">**Item**</span></span>|<span data-ttu-id="daf00-137">**说明**</span><span class="sxs-lookup"><span data-stu-id="daf00-137">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="daf00-138">应用程序查询栏中的基本图标</span><span class="sxs-lookup"><span data-stu-id="daf00-138">Basic icon in the app query bar</span></span>  <br/> ![表示用于查询应用程序权限的基本查询视图图标](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="daf00-140">选择此选项可切换到的高级视图。</span><span class="sxs-lookup"><span data-stu-id="daf00-140">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="daf00-141">（如果您看到**基本**，所使用的高级的视图）</span><span class="sxs-lookup"><span data-stu-id="daf00-141">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="daf00-142">应用程序查询栏中的高级的图标</span><span class="sxs-lookup"><span data-stu-id="daf00-142">Advanced icon in the app query bar</span></span>  <br/> ![指示高级查询视图查询应用程序权限的图标](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="daf00-144">选择此选项可切换到基本视图。</span><span class="sxs-lookup"><span data-stu-id="daf00-144">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="daf00-145">（如果您看到**高级**，您使用基本视图）。</span><span class="sxs-lookup"><span data-stu-id="daf00-145">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="daf00-146">打开或关闭应用程序列表中的所有详细信息图标</span><span class="sxs-lookup"><span data-stu-id="daf00-146">Open or close all details icon in the app list</span></span>  <br/> ![单击此图标可打开或关闭所有应用程序的所有详细信息](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="daf00-148">选择此图标可查看有关每个应用程序的更多或更少的详细信息。</span><span class="sxs-lookup"><span data-stu-id="daf00-148">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="daf00-149">在应用程序列表的导出图标</span><span class="sxs-lookup"><span data-stu-id="daf00-149">Export icon in the app list</span></span>  <br/> ![单击此图标可导出 csv 文件的所有应用程序](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="daf00-151">选择此图标可导出 CSV 文件包含列表的应用程序，每个应用程序与应用程序、 权限级别、 应用程序状态和社区使用级别关联的权限的用户数。</span><span class="sxs-lookup"><span data-stu-id="daf00-151">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="daf00-152">Name</span><span class="sxs-lookup"><span data-stu-id="daf00-152">Name</span></span>  <br/> |<span data-ttu-id="daf00-p105">使用此查看应用程序选择的名称的名称，以查看详细信息，例如其说明、 publisher、 应用程序网站和应用程序 id。</span><span class="sxs-lookup"><span data-stu-id="daf00-p105">Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="daf00-155">经过授权</span><span class="sxs-lookup"><span data-stu-id="daf00-155">Authorized by</span></span>  <br/> |<span data-ttu-id="daf00-p106">使用此查看多少用户有权访问其 Office 365 帐户的应用程序。选择要查看详细信息，如用户帐户的列表的编号。</span><span class="sxs-lookup"><span data-stu-id="daf00-p106">Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="daf00-158">权限级别</span><span class="sxs-lookup"><span data-stu-id="daf00-158">Permissions Level</span></span>  <br/> ![指示 permisiions 级别应用程序的图标](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="daf00-p107">用于查看的应用程序多少访问已对 Office 365 数据。权限级别指示**低**、**中等**或**高**，其中**低**可能表示应用程序仅访问用户的配置文件和名称。选择要查看详细信息，如权限授予对应用程序、 社区使用和[调控日志](suspend-or-restore-an-account-in-ocas.md)中的相关的活动的级别。</span><span class="sxs-lookup"><span data-stu-id="daf00-p107">Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  </span></span><br/> |
|<span data-ttu-id="daf00-163">应用程序状态 （ **Banned**（**已批准**，还是**未确定**）</span><span class="sxs-lookup"><span data-stu-id="daf00-163">App state ( **Banned**, **Approved**, or **Undetermined**)</span></span>  <br/> <span data-ttu-id="daf00-164">![应用程序权限图标后要允许、 阻止，或没有操作已被管理员](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)</span><span class="sxs-lookup"><span data-stu-id="daf00-164">![App permissions icons after being allowed, blocked, or no action has been taken by an admin](media/5748bd02-cd59-4bd1-a36f-d25a186e8055.png)</span></span>|<span data-ttu-id="daf00-165">用于将应用程序标记为已批准或 Banned，或将其保留为未确定。</span><span class="sxs-lookup"><span data-stu-id="daf00-165">Use this to mark an app as Approved or Banned, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="daf00-166">将应用程序标记为已批准</span><span class="sxs-lookup"><span data-stu-id="daf00-166">Mark an app as approved</span></span>
<span data-ttu-id="daf00-167"><a name="approveapp"> </a></span><span class="sxs-lookup"><span data-stu-id="daf00-167"></span></span>

<span data-ttu-id="daf00-168">在**管理应用程序权限**页上，找到您想要批准的应用程序，然后选择**作为标记应用程序获得批准**图标。</span><span class="sxs-lookup"><span data-stu-id="daf00-168">On the **Manage app permissions** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![选择应用程序标记为已批准的图标](media/dd1b7690-441a-48c9-9c3a-58466513c63d.png)
  
<span data-ttu-id="daf00-170">图标将变为绿色，并且应用程序已获得批准对所有 Office 365 用户。</span><span class="sxs-lookup"><span data-stu-id="daf00-170">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="daf00-p108">当您将应用程序标记为已批准时，最终用户没有影响。直观地标记批准的应用程序有助于分隔它们从您尚未尚未已审阅的应用程序。</span><span class="sxs-lookup"><span data-stu-id="daf00-p108">When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="daf00-173">禁止应用程序</span><span class="sxs-lookup"><span data-stu-id="daf00-173">Ban an app</span></span>
<span data-ttu-id="daf00-174"><a name="banapp"> </a></span><span class="sxs-lookup"><span data-stu-id="daf00-174"></span></span>

1. <span data-ttu-id="daf00-175">在**管理应用程序权限**页上，找到您要禁止，应用的程序，然后选择**作为标记应用程序禁止**图标。</span><span class="sxs-lookup"><span data-stu-id="daf00-175">On the **Manage app permissions** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span> 
    
    ![选择为禁止图标的标记应用程序](media/b9b1c5f6-fde7-46d5-8589-1564d05702b3.png)
  
2. <span data-ttu-id="daf00-177">选择是否让用户了解其应用程序已被禁止。</span><span class="sxs-lookup"><span data-stu-id="daf00-177">Choose whether to let users know that their app has been banned.</span></span>
    
    <span data-ttu-id="daf00-178">（推荐）以让用户了解，选择**用户授予对此禁止应用程序的访问的通知用户**，以及添加或编辑自定义通知消息。</span><span class="sxs-lookup"><span data-stu-id="daf00-178">(Recommended) To let users know, select **Notify users who granted access to this banned app**, and add or edit a custom notification message.</span></span>
    
    <span data-ttu-id="daf00-179">以不通知用户，请清除**用户授予对此禁止应用程序的访问的通知用户**。</span><span class="sxs-lookup"><span data-stu-id="daf00-179">To not let users know, clear **Notify users who granted access to this banned app**.</span></span>
    
    ![邮件模板禁止应用程序](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)
  
3. <span data-ttu-id="daf00-181">选择**禁止应用程序**。</span><span class="sxs-lookup"><span data-stu-id="daf00-181">Choose **Ban app**.</span></span>
    
## <a name="create-an-app-query"></a><span data-ttu-id="daf00-182">创建应用程序查询</span><span class="sxs-lookup"><span data-stu-id="daf00-182">Create an app query</span></span>
<span data-ttu-id="daf00-183"><a name="createapp"> </a></span><span class="sxs-lookup"><span data-stu-id="daf00-183"></span></span>

1. <span data-ttu-id="daf00-p109">在应用程序查询栏中，如果您看到**高级**，单击 （或点击） 以转到的高级视图。（请参阅 Basic，如果您使用的高级的视图; 按原样保留您的视图。）</span><span class="sxs-lookup"><span data-stu-id="daf00-p109">In the app query bar, if you see **Advanced**, click (or tap) it to go to the Advanced view. (If you see Basic, you are using the Advanced view; keep your view as it is.)</span></span>
    
2. <span data-ttu-id="daf00-p110">使用**选择筛选器**列表中选择一个选项。下表总结了您可用的筛选器选项。</span><span class="sxs-lookup"><span data-stu-id="daf00-p110">Use the **Select a filter** list to choose an option. The following table summarizes your available filter options.</span></span> 
    
|<span data-ttu-id="daf00-188">**使用此筛选器**</span><span class="sxs-lookup"><span data-stu-id="daf00-188">**Use this filter**</span></span>|<span data-ttu-id="daf00-189">**显示内容**</span><span class="sxs-lookup"><span data-stu-id="daf00-189">**To display**</span></span>|
|:-----|:-----|
|<span data-ttu-id="daf00-190">**应用**</span><span class="sxs-lookup"><span data-stu-id="daf00-190">**App**</span></span> <br/> |<span data-ttu-id="daf00-191">具有某些名称的应用程序</span><span class="sxs-lookup"><span data-stu-id="daf00-191">Apps with certain names</span></span>  <br/> |
|<span data-ttu-id="daf00-192">**应用程序状态**</span><span class="sxs-lookup"><span data-stu-id="daf00-192">**App state**</span></span> <br/> |<span data-ttu-id="daf00-193">根据状态 （已批准、 Banned 或未确定） 的应用程序</span><span class="sxs-lookup"><span data-stu-id="daf00-193">Apps based on their state (Approved, Banned, or Undetermined)</span></span>  <br/> |
|<span data-ttu-id="daf00-194">**社区的使用**</span><span class="sxs-lookup"><span data-stu-id="daf00-194">**Community use**</span></span> <br/> |<span data-ttu-id="daf00-195">基于社区的应用程序使用级别 （Rare、 Uncommon 或通用）</span><span class="sxs-lookup"><span data-stu-id="daf00-195">Apps based on community use levels (Rare, Uncommon, or Common)</span></span>  <br/> |
|<span data-ttu-id="daf00-196">**权限级别**</span><span class="sxs-lookup"><span data-stu-id="daf00-196">**Permission level**</span></span> <br/> |<span data-ttu-id="daf00-197">基于特定权限级别的应用程序</span><span class="sxs-lookup"><span data-stu-id="daf00-197">Apps based on certain permission levels</span></span>  <br/> |
|<span data-ttu-id="daf00-198">**权限**</span><span class="sxs-lookup"><span data-stu-id="daf00-198">**Permissions**</span></span> <br/> |<span data-ttu-id="daf00-199">需要哪些权限的应用程序</span><span class="sxs-lookup"><span data-stu-id="daf00-199">Apps that require certain permissions</span></span>  <br/> |
|<span data-ttu-id="daf00-200">**发布程序**</span><span class="sxs-lookup"><span data-stu-id="daf00-200">**Publisher**</span></span> <br/> |<span data-ttu-id="daf00-201">从特定的发布者的应用程序</span><span class="sxs-lookup"><span data-stu-id="daf00-201">Apps from certain publishers</span></span>  <br/> |
|<span data-ttu-id="daf00-202">**User**</span><span class="sxs-lookup"><span data-stu-id="daf00-202">**User**</span></span> <br/> |<span data-ttu-id="daf00-203">特定用户授权的应用程序</span><span class="sxs-lookup"><span data-stu-id="daf00-203">Apps that a certain user authorized</span></span>  <br/> |
   
3. <span data-ttu-id="daf00-204">选择**等于**或**不等于**，，然后指定为筛选器值。</span><span class="sxs-lookup"><span data-stu-id="daf00-204">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
4. <span data-ttu-id="daf00-205">若要添加更多筛选器，请选择加号 （</span><span class="sxs-lookup"><span data-stu-id="daf00-205">To add more filters, select the plus sign (</span></span>![添加用于查询应用程序的筛选器图标](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="daf00-207">)，然后对重复步骤 2 和 3。</span><span class="sxs-lookup"><span data-stu-id="daf00-207">), and then repeat steps 2 and 3.</span></span>
    
5. <span data-ttu-id="daf00-208">若要删除筛选器，请选择 x (</span><span class="sxs-lookup"><span data-stu-id="daf00-208">To remove a filter, select the x (</span></span>![删除查询应用程序的筛选器图标](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="daf00-210">) 旁边的筛选器名称。</span><span class="sxs-lookup"><span data-stu-id="daf00-210">) next to a filter name.</span></span>
    
<span data-ttu-id="daf00-211">自动应用筛选器并相应地更新应用程序列表。</span><span class="sxs-lookup"><span data-stu-id="daf00-211">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="daf00-212">后续步骤</span><span class="sxs-lookup"><span data-stu-id="daf00-212">Next steps</span></span>
<span data-ttu-id="daf00-213"><a name="nextsteps"> </a></span><span class="sxs-lookup"><span data-stu-id="daf00-213"></span></span>

- [<span data-ttu-id="daf00-214">查看并通知对其执行操作</span><span class="sxs-lookup"><span data-stu-id="daf00-214">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="daf00-215">查看您的[Web 流量日志和 Office 365 云应用程序安全性的数据源](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="daf00-215">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="daf00-216">查看您[的 Office 365 云应用程序安全性的使用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="daf00-216">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


---
title: 使用 Office 365 云应用安全管理 OAuth 应用
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Office 365 云应用程序安全性的 OAuth 应用程序帮助您管理您的用户下载用于 Office 365 数据的应用程序
ms.openlocfilehash: 2e3c6d9d42b22aa8bb666211431197744471e84f
ms.sourcegitcommit: 25f72d20e76463c2f0a075dfc0116f00c934bd77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/27/2018
ms.locfileid: "27447040"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a><span data-ttu-id="6d282-103">使用 Office 365 云应用安全管理 OAuth 应用</span><span class="sxs-lookup"><span data-stu-id="6d282-103">Manage OAuth apps using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="6d282-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="6d282-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="6d282-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="6d282-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="6d282-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="6d282-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="6d282-107">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="6d282-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="6d282-108">启动评估</span><span class="sxs-lookup"><span data-stu-id="6d282-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="6d282-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="6d282-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="6d282-110">开始部署</span><span class="sxs-lookup"><span data-stu-id="6d282-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="6d282-111">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="6d282-111">You are here!</span></span>  <br/> [<span data-ttu-id="6d282-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6d282-112">Next steps</span></span>](manage-app-permissions-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="6d282-p101">人员喜欢的应用程序和他们通常下载这些，尤其是人员思考的应用程序将通过使其更易于获取在其工作或学校信息节省时间。但是，某些应用程序可能存在一定的安全风险到您的组织，哪些信息取决于他们访问和如何处理该信息。[Office 365 云应用程序安全性](office-365-cas-overview.md)，如果您是全局或安全管理员，您可以管理 OAuth 应用程序为您的组织。您可以查看正在使用的应用程序的人员的 Office 365 数据哪些权限这些应用程序都有和更多内容。</span><span class="sxs-lookup"><span data-stu-id="6d282-p101">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information. However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information. With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage OAuth apps for your organization. You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="6d282-117">本文介绍在哪里管理 OAuth 应用程序、 如何批准、 禁止，或报告应用程序，以及如何创建应用程序查询。</span><span class="sxs-lookup"><span data-stu-id="6d282-117">This article describes where to go to manage OAuth apps, how to approve, ban, or report an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a><span data-ttu-id="6d282-118">如何查找管理 OAuth 应用程序页</span><span class="sxs-lookup"><span data-stu-id="6d282-118">How to find the Manage OAuth apps page</span></span>

> [!NOTE]
> <span data-ttu-id="6d282-p102">在 Office 365 云应用程序安全性门户管理 OAuth 应用程序。您必须是要执行以下任务的全局管理员或 security 管理员程序。若要了解详细，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="6d282-p102">OAuth apps are managed in the Office 365 Cloud App Security portal. You must be a global administrator or security administrator to perform the following task. To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="6d282-p103">转到[https://protection.office.com](https://protection.office.com)和 Office 365 中使用您的工作或学校帐户登录。(您将转到安全&amp;合规性中心。)</span><span class="sxs-lookup"><span data-stu-id="6d282-p103">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="6d282-124">转到**通知** \> **管理高级通知**。</span><span class="sxs-lookup"><span data-stu-id="6d282-124">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="6d282-125">单击 （或点击）**转到 Office 365 云应用程序安全性**。</span><span class="sxs-lookup"><span data-stu-id="6d282-125">Click (or tap) **Go to Office 365 Cloud App Security**.</span></span><br/><span data-ttu-id="6d282-126">![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="6d282-126">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="6d282-p104">**注意**： 如果未尚未开启 Office 365 云应用程序安全性，您可以执行的操作此页上。请参阅[为 Office 365 云应用程序安全性做好准备](get-ready-for-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="6d282-p104">**NOTE**: If Office 365 Cloud App Security is not turned on yet, you can do that on this page. See [Get ready for Office 365 Cloud App Security](get-ready-for-office-365-cas.md).</span></span> 
  
4. <span data-ttu-id="6d282-129">选择**调查** \> **OAuth 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="6d282-129">Choose **Investigate** \> **OAuth apps**.</span></span><br/><span data-ttu-id="6d282-130">![在 O365 CAS 门户中，选择调查。](media/OCAS-OAuthApps.png)</span><span class="sxs-lookup"><span data-stu-id="6d282-130">![In the O365 CAS portal, choose Investigate.](media/OCAS-OAuthApps.png)</span></span><br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a><span data-ttu-id="6d282-131">您将看到上管理 OAuth 应用程序页</span><span class="sxs-lookup"><span data-stu-id="6d282-131">What you'll see on the Manage OAuth apps page</span></span>

<span data-ttu-id="6d282-132">下表介绍了管理 OAuth 的应用程序页上的控件和可用选项。</span><span class="sxs-lookup"><span data-stu-id="6d282-132">The following table describes the controls and options available on the Manage OAuth apps page.</span></span>
  
|<span data-ttu-id="6d282-133">**项**</span><span class="sxs-lookup"><span data-stu-id="6d282-133">**Item**</span></span>|<span data-ttu-id="6d282-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="6d282-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6d282-135">应用程序查询栏中的基本图标</span><span class="sxs-lookup"><span data-stu-id="6d282-135">Basic icon in the app query bar</span></span>  <br/> ![指示查询的基本查询视图的图标](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="6d282-137">选择此选项可切换到的高级视图。</span><span class="sxs-lookup"><span data-stu-id="6d282-137">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="6d282-138">（如果您看到**基本**，所使用的高级的视图）</span><span class="sxs-lookup"><span data-stu-id="6d282-138">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="6d282-139">应用程序查询栏中的高级的图标</span><span class="sxs-lookup"><span data-stu-id="6d282-139">Advanced icon in the app query bar</span></span>  <br/> ![指示查询的高级的查询视图的图标](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="6d282-141">选择此选项可切换到基本视图。</span><span class="sxs-lookup"><span data-stu-id="6d282-141">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="6d282-142">（如果您看到**高级**，您使用基本视图）。</span><span class="sxs-lookup"><span data-stu-id="6d282-142">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="6d282-143">打开或关闭应用程序列表中的所有详细信息图标</span><span class="sxs-lookup"><span data-stu-id="6d282-143">Open or close all details icon in the app list</span></span>  <br/> ![单击此图标可打开或关闭所有应用程序的所有详细信息](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="6d282-145">选择此图标可查看有关每个应用程序的更多或更少的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6d282-145">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="6d282-146">在应用程序列表的导出图标</span><span class="sxs-lookup"><span data-stu-id="6d282-146">Export icon in the app list</span></span>  <br/> ![单击此图标可导出 csv 文件的所有应用程序](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="6d282-148">选择此图标可导出 CSV 文件包含列表的应用程序，每个应用程序与应用程序、 权限级别、 应用程序状态和社区使用级别关联的权限的用户数。</span><span class="sxs-lookup"><span data-stu-id="6d282-148">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="6d282-149">名称</span><span class="sxs-lookup"><span data-stu-id="6d282-149">Name</span></span>  <br/> |<span data-ttu-id="6d282-p105">使用此查看应用程序选择的名称的名称，以查看详细信息，例如其说明、 publisher、 应用程序网站和应用程序 id。</span><span class="sxs-lookup"><span data-stu-id="6d282-p105">Use this to see the name of an app. Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="6d282-152">经过授权</span><span class="sxs-lookup"><span data-stu-id="6d282-152">Authorized by</span></span>  <br/> |<span data-ttu-id="6d282-p106">使用此查看多少用户有权访问其 Office 365 帐户的应用程序。选择要查看详细信息，如用户帐户的列表的编号。</span><span class="sxs-lookup"><span data-stu-id="6d282-p106">Use this to see how many users have authorized an app to access their Office 365 account. Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="6d282-155">权限级别</span><span class="sxs-lookup"><span data-stu-id="6d282-155">Permissions Level</span></span>  <br/> ![指示 permisiions 级别应用程序的图标](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="6d282-p107">用于查看的应用程序多少访问已对 Office 365 数据。权限级别指示**低**、**中等**或**高**，其中**低**可能表示应用程序仅访问用户的配置文件和名称。选择要查看详细信息，如权限授予对应用程序、 社区使用和[调控日志](suspend-or-restore-an-account-in-ocas.md)中的相关的活动的级别。</span><span class="sxs-lookup"><span data-stu-id="6d282-p107">Use this to see how much access an app has to Office 365 data. Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name. Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).  </span></span><br/> |
|<span data-ttu-id="6d282-160">上次授权</span><span class="sxs-lookup"><span data-stu-id="6d282-160">Last authorized</span></span> <br/> |<span data-ttu-id="6d282-161">用于查看的日期和时间 OAuth 应用程序已最后一个权访问您组织的 Office 365 数据。</span><span class="sxs-lookup"><span data-stu-id="6d282-161">Use this to see the date and time an OAuth app was last authorized to access your organization's Office 365 data.</span></span> <br/>  |
|<span data-ttu-id="6d282-162">操作</span><span class="sxs-lookup"><span data-stu-id="6d282-162">Actions</span></span><br/>![OAuth 应用程序](media/OCAS-OAuthAppApproveBanReport.png)<br/> |<span data-ttu-id="6d282-164">使用此要查看或将应用程序标记为已批准或 Banned，向 Microsoft 报告 OAuth 应用程序或将其保留为未确定。</span><span class="sxs-lookup"><span data-stu-id="6d282-164">Use this to see or to mark an app as Approved or Banned, report an OAuth app to Microsoft, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="6d282-165">将应用程序标记为已批准</span><span class="sxs-lookup"><span data-stu-id="6d282-165">Mark an app as approved</span></span>

<span data-ttu-id="6d282-166">在**管理 OAuth 应用程序**页上，找到您想要批准的应用程序，然后选择**作为标记应用程序获得批准**图标。</span><span class="sxs-lookup"><span data-stu-id="6d282-166">On the **Manage OAuth apps** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![选择应用程序标记为已批准的图标](media/OCAS-MarkOAuthApproved.png)
  
<span data-ttu-id="6d282-168">图标将变为绿色，并且应用程序已获得批准对所有 Office 365 用户。</span><span class="sxs-lookup"><span data-stu-id="6d282-168">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d282-p108">当您将应用程序标记为已批准时，最终用户没有影响。直观地标记批准的应用程序有助于分隔它们从您尚未尚未已审阅的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6d282-p108">When you mark an app as approved, there is no effect on the end user. Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="6d282-171">禁止应用程序</span><span class="sxs-lookup"><span data-stu-id="6d282-171">Ban an app</span></span>

1. <span data-ttu-id="6d282-172">在**管理 OAuth 应用程序**页上，找到您要禁止，应用的程序，然后选择**作为标记应用程序禁止**图标。</span><span class="sxs-lookup"><span data-stu-id="6d282-172">On the **Manage OAuth apps** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span><br/><span data-ttu-id="6d282-173">![选择为禁止图标的标记应用程序](media/OCAS-MarkOAuthBanned.png)</span><span class="sxs-lookup"><span data-stu-id="6d282-173">![Choose the Mark app as banned icon](media/OCAS-MarkOAuthBanned.png)</span></span>
  
2. <span data-ttu-id="6d282-p109">在通知消息框中，保留现有的文本，按原样，或自定义的文本。选择是否让用户了解其应用程序已被禁止。</span><span class="sxs-lookup"><span data-stu-id="6d282-p109">In the notification message box, keep the existing text as it is, or customize the text. Choose whether to let users know that their app has been banned.</span></span> <br/>![邮件模板禁止应用程序](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. <span data-ttu-id="6d282-177">选择**禁止应用程序**。</span><span class="sxs-lookup"><span data-stu-id="6d282-177">Choose **Ban app**.</span></span>

## <a name="report-an-oauth-app-to-microsoft"></a><span data-ttu-id="6d282-178">向 Microsoft 报告 OAuth 应用程序</span><span class="sxs-lookup"><span data-stu-id="6d282-178">Report an OAuth app to Microsoft</span></span>

<span data-ttu-id="6d282-179">如果您想要 OAuth 的应用程序提交给 Microsoft 进行分析，您可以报告该应用程序。</span><span class="sxs-lookup"><span data-stu-id="6d282-179">If you want to submit an OAuth app to Microsoft for analysis, you can report that app.</span></span>

1. <span data-ttu-id="6d282-180">在**管理 OAuth 应用程序**页中，找到要用于分析提交应用的程序。</span><span class="sxs-lookup"><span data-stu-id="6d282-180">On the **Manage OAuth apps** page, locate the app you want to submit for analysis.</span></span>

2. <span data-ttu-id="6d282-181">选择的垂直省略号，然后选择**报告应用程序...**。</span><span class="sxs-lookup"><span data-stu-id="6d282-181">Choose the vertical ellipsis, and then choose **Report app...**.</span></span><br/><span data-ttu-id="6d282-182">![报告 OAuth 应用程序](media/OCAS-MarkOAuthReported.png)</span><span class="sxs-lookup"><span data-stu-id="6d282-182">![Report an OAuth app](media/OCAS-MarkOAuthReported.png)</span></span><br/>

3. <span data-ttu-id="6d282-p110">在**报告此应用程序**对话框中，使用下拉列表以指示您的问题。默认情况下，**此应用程序是恶意**处于选中状态。但是，您可以选择其他可用选项之一。</span><span class="sxs-lookup"><span data-stu-id="6d282-p110">In the **Report this app** dialog box, use the drop-down list to indicate your concern. By default, **This app is malicious** is selected. However, you can choose on one of the other available options. </span></span><br/><span data-ttu-id="6d282-186">![报告 OAuth 应用程序](media/OCAS-ReportOAuthApp.png)</span><span class="sxs-lookup"><span data-stu-id="6d282-186">![Report an OAuth app](media/OCAS-ReportOAuthApp.png)</span></span><br/>

4. <span data-ttu-id="6d282-187">（推荐）保留选项可与您选择，联系，确认 （或编辑） 列出的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6d282-187">(Recommended) Keep the option to contact you selected, and confirm (or edit) the email address listed.</span></span>

5. <span data-ttu-id="6d282-188">选择" **提交**"。</span><span class="sxs-lookup"><span data-stu-id="6d282-188">Choose **Submit**.</span></span> 
    
## <a name="create-an-app-query"></a><span data-ttu-id="6d282-189">创建应用程序查询</span><span class="sxs-lookup"><span data-stu-id="6d282-189">Create an app query</span></span>

<span data-ttu-id="6d282-190">我们建议使用的高级的视图，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6d282-190">We recommend using the Advanced view, which looks like this:</span></span> 

![高级的视图](media/OCAS-OAuthAppsAdvQueryView.png)

<span data-ttu-id="6d282-p111">在应用程序查询栏中，请参阅**高级**，如果您正使用的基本视图。单击 （或点击）**高级**以转到的高级视图。</span><span class="sxs-lookup"><span data-stu-id="6d282-p111">In the app query bar, if you see **Advanced**, you're using the Basic view. Click (or tap) **Advanced** to go to the Advanced view.</span></span> 

![基本视图](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. <span data-ttu-id="6d282-195">在查询栏中，使用**选择筛选器**列表选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="6d282-195">In the query bar, use the **Select a filter** list to choose an option.</span></span> 
    - <span data-ttu-id="6d282-196">**应用程序**具有某些名称的应用程序</span><span class="sxs-lookup"><span data-stu-id="6d282-196">**App** Apps with certain names</span></span>
    - <span data-ttu-id="6d282-197">**应用程序状态**根据状态 （已批准、 Banned 或未确定） 的应用程序</span><span class="sxs-lookup"><span data-stu-id="6d282-197">**App state** Apps based on their state (Approved, Banned, or Undetermined)</span></span>
    - <span data-ttu-id="6d282-198">**使用社区**基于社区的应用程序使用级别 （Rare、 Uncommon 或通用）</span><span class="sxs-lookup"><span data-stu-id="6d282-198">**Community use** Apps based on community use levels (Rare, Uncommon, or Common)</span></span>
    - <span data-ttu-id="6d282-199">**权限级别**基于特定权限级别的应用程序</span><span class="sxs-lookup"><span data-stu-id="6d282-199">**Permission level** Apps based on certain permission levels</span></span> 
    - <span data-ttu-id="6d282-200">**权限**需要哪些权限的应用程序</span><span class="sxs-lookup"><span data-stu-id="6d282-200">**Permissions** Apps that require certain permissions</span></span>
    - <span data-ttu-id="6d282-201">**Publisher** 从特定的发布者的应用程序</span><span class="sxs-lookup"><span data-stu-id="6d282-201">**Publisher**  Apps from certain publishers</span></span>
    - <span data-ttu-id="6d282-202">**用户**特定用户授权的应用程序</span><span class="sxs-lookup"><span data-stu-id="6d282-202">**User** Apps that a certain user authorized</span></span>
   
2. <span data-ttu-id="6d282-203">选择**等于**或**不等于**，，然后指定为筛选器值。</span><span class="sxs-lookup"><span data-stu-id="6d282-203">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
3. <span data-ttu-id="6d282-204">若要添加更多筛选器，请选择加号 （</span><span class="sxs-lookup"><span data-stu-id="6d282-204">To add more filters, select the plus sign (</span></span>![添加用于查询应用程序的筛选器图标](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="6d282-206">)，然后对重复步骤 2 和 3。</span><span class="sxs-lookup"><span data-stu-id="6d282-206">), and then repeat steps 2 and 3.</span></span>
    
4. <span data-ttu-id="6d282-207">若要删除筛选器，请选择 x (</span><span class="sxs-lookup"><span data-stu-id="6d282-207">To remove a filter, select the x (</span></span>![删除查询应用程序的筛选器图标](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="6d282-209">) 旁边的筛选器名称。</span><span class="sxs-lookup"><span data-stu-id="6d282-209">) next to a filter name.</span></span>
    
<span data-ttu-id="6d282-210">自动应用筛选器并相应地更新应用程序列表。</span><span class="sxs-lookup"><span data-stu-id="6d282-210">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="6d282-211">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6d282-211">Next steps</span></span>

- [<span data-ttu-id="6d282-212">查看并通知对其执行操作</span><span class="sxs-lookup"><span data-stu-id="6d282-212">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="6d282-213">查看您的[Web 流量日志和 Office 365 云应用程序安全性的数据源](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="6d282-213">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="6d282-214">查看您[的 Office 365 云应用程序安全性的使用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="6d282-214">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


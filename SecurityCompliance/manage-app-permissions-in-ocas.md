---
title: 使用 Office 365 云应用安全管理 OAuth 应用
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: office 365 中的 OAuth 应用程序安全性帮助您管理用户下载的用于 Office 365 数据的应用程序
ms.openlocfilehash: 0d9916414d55abb73fd99eaf30c3b6df0648b191
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862584"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a><span data-ttu-id="0fb82-103">使用 Office 365 云应用安全管理 OAuth 应用</span><span class="sxs-lookup"><span data-stu-id="0fb82-103">Manage OAuth apps using Office 365 Cloud App Security</span></span>

|<span data-ttu-id="0fb82-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0fb82-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="0fb82-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0fb82-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="0fb82-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="0fb82-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="0fb82-107">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="0fb82-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="0fb82-108">开始评估</span><span class="sxs-lookup"><span data-stu-id="0fb82-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="0fb82-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="0fb82-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="0fb82-110">开始部署</span><span class="sxs-lookup"><span data-stu-id="0fb82-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="0fb82-111">你在这里!</span><span class="sxs-lookup"><span data-stu-id="0fb82-111">You are here!</span></span>  <br/> [<span data-ttu-id="0fb82-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0fb82-112">Next steps</span></span>](#next-steps)<br/> |
   
<span data-ttu-id="0fb82-113">人们喜欢应用程序, 并且他们经常下载它们, 尤其是人们认为, 人们可以通过更轻松地获取工作或学校信息, 从而节省时间。</span><span class="sxs-lookup"><span data-stu-id="0fb82-113">People love apps and they download them often, especially apps that people think will save time by making it easier to get at their work or school information.</span></span> <span data-ttu-id="0fb82-114">但是, 某些应用可能会对您的组织造成安全风险, 具体取决于他们访问的信息以及它们如何处理这些信息。</span><span class="sxs-lookup"><span data-stu-id="0fb82-114">However, some apps could potentially be a security risk to your organization, depending on what information they access and how they handle that information.</span></span> <span data-ttu-id="0fb82-115">使用[Office 365 云应用安全](office-365-cas-overview.md), 如果您是全局管理员或安全管理员, 则可以管理您的组织的 OAuth 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0fb82-115">With [Office 365 Cloud App Security](office-365-cas-overview.md), if you are a global or security administrator, you can manage OAuth apps for your organization.</span></span> <span data-ttu-id="0fb82-116">您可以查看使用 Office 365 数据的应用程序, 这些应用程序具有哪些权限, 等等。</span><span class="sxs-lookup"><span data-stu-id="0fb82-116">You can see the apps people are using with Office 365 data, what permissions those apps have, and more.</span></span> 
  
<span data-ttu-id="0fb82-117">本文介绍在哪里可以转到管理 OAuth 应用程序、如何批准、禁止或报告应用程序, 以及如何创建应用程序查询。</span><span class="sxs-lookup"><span data-stu-id="0fb82-117">This article describes where to go to manage OAuth apps, how to approve, ban, or report an app, and how to create an app query.</span></span>
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a><span data-ttu-id="0fb82-118">如何查找 "管理 OAuth 应用程序" 页</span><span class="sxs-lookup"><span data-stu-id="0fb82-118">How to find the Manage OAuth apps page</span></span>

> [!NOTE]
> <span data-ttu-id="0fb82-119">在 Office 365 云应用安全门户中管理 OAuth 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0fb82-119">OAuth apps are managed in the Office 365 Cloud App Security portal.</span></span> <span data-ttu-id="0fb82-120">您必须是全局管理员或安全管理员才能执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="0fb82-120">You must be a global administrator or security administrator to perform the following task.</span></span> <span data-ttu-id="0fb82-121">若要了解详细信息, 请参阅[Office 365 &amp;安全合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="0fb82-121">To learn more see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
1. <span data-ttu-id="0fb82-122">转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="0fb82-122">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="0fb82-123">选择**调查** \> **OAuth 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="0fb82-123">Choose **Investigate** \> **OAuth apps**.</span></span><br/><span data-ttu-id="0fb82-124">![在 O365 CAS 门户中, 选择 "调查"。](media/OCAS-OAuthApps.png)</span><span class="sxs-lookup"><span data-stu-id="0fb82-124">![In the O365 CAS portal, choose Investigate.](media/OCAS-OAuthApps.png)</span></span><br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a><span data-ttu-id="0fb82-125">您将在 "管理 OAuth 应用程序" 页上看到的内容</span><span class="sxs-lookup"><span data-stu-id="0fb82-125">What you'll see on the Manage OAuth apps page</span></span>

<span data-ttu-id="0fb82-126">下表介绍了 "管理 OAuth 应用" 页上可用的控件和选项。</span><span class="sxs-lookup"><span data-stu-id="0fb82-126">The following table describes the controls and options available on the Manage OAuth apps page.</span></span>
  
|<span data-ttu-id="0fb82-127">**项**</span><span class="sxs-lookup"><span data-stu-id="0fb82-127">**Item**</span></span>|<span data-ttu-id="0fb82-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="0fb82-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0fb82-129">应用程序查询栏中的基本图标</span><span class="sxs-lookup"><span data-stu-id="0fb82-129">Basic icon in the app query bar</span></span>  <br/> ![指示查询的基本查询视图的图标](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|<span data-ttu-id="0fb82-131">选择此选项以切换到 "高级" 视图。</span><span class="sxs-lookup"><span data-stu-id="0fb82-131">Select this to switch to the Advanced view.</span></span>  <br/> <span data-ttu-id="0fb82-132">(如果看到的是 "**基本**", 则使用的是 "高级" 视图)</span><span class="sxs-lookup"><span data-stu-id="0fb82-132">(If you see **Basic**, you are using the Advanced view)</span></span>  <br/> |
|<span data-ttu-id="0fb82-133">应用程序查询栏中的高级图标</span><span class="sxs-lookup"><span data-stu-id="0fb82-133">Advanced icon in the app query bar</span></span>  <br/> ![指示查询的高级查询视图的图标](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|<span data-ttu-id="0fb82-135">选择此选项以切换到 "基本" 视图。</span><span class="sxs-lookup"><span data-stu-id="0fb82-135">Select this to switch to the Basic view.</span></span>  <br/> <span data-ttu-id="0fb82-136">(如果看到 "**高级**", 则使用的是 "基本" 视图。)</span><span class="sxs-lookup"><span data-stu-id="0fb82-136">(If you see **Advanced**, you are using the Basic view.)</span></span>  <br/> |
|<span data-ttu-id="0fb82-137">在应用程序列表中打开或关闭所有详细信息图标</span><span class="sxs-lookup"><span data-stu-id="0fb82-137">Open or close all details icon in the app list</span></span>  <br/> ![单击此图标可打开或关闭所有应用的所有详细信息](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|<span data-ttu-id="0fb82-139">选择此图标可查看有关每个应用程序的更多或更少详细信息。</span><span class="sxs-lookup"><span data-stu-id="0fb82-139">Select this icon to view more or fewer details about each app.</span></span>  <br/> |
|<span data-ttu-id="0fb82-140">在应用程序列表中导出图标</span><span class="sxs-lookup"><span data-stu-id="0fb82-140">Export icon in the app list</span></span>  <br/> ![单击此图标可导出所有应用程序的 csv 文件](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|<span data-ttu-id="0fb82-142">选择此图标可导出包含应用程序列表的 CSV 文件、每个应用程序的用户数、与应用程序关联的权限、权限级别、应用程序状态和社区使用级别。</span><span class="sxs-lookup"><span data-stu-id="0fb82-142">Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.</span></span>  <br/> |
|<span data-ttu-id="0fb82-143">名称</span><span class="sxs-lookup"><span data-stu-id="0fb82-143">Name</span></span>  <br/> |<span data-ttu-id="0fb82-144">使用此名称可查看应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="0fb82-144">Use this to see the name of an app.</span></span> <span data-ttu-id="0fb82-145">选择名称以查看详细信息, 如其说明、发布者、应用程序网站和应用 ID。</span><span class="sxs-lookup"><span data-stu-id="0fb82-145">Select the name to view more information, such as its description, publisher, app website and app ID.</span></span>  <br/> |
|<span data-ttu-id="0fb82-146">授权人</span><span class="sxs-lookup"><span data-stu-id="0fb82-146">Authorized by</span></span>  <br/> |<span data-ttu-id="0fb82-147">使用此方法可查看有多少用户已授权应用程序访问其 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="0fb82-147">Use this to see how many users have authorized an app to access their Office 365 account.</span></span> <span data-ttu-id="0fb82-148">选择号码以查看详细信息, 如用户帐户列表。</span><span class="sxs-lookup"><span data-stu-id="0fb82-148">Select the number to view more information, such as a list of user accounts.</span></span>  <br/> |
|<span data-ttu-id="0fb82-149">权限级别</span><span class="sxs-lookup"><span data-stu-id="0fb82-149">Permissions Level</span></span>  <br/> ![指示应用程序的 permisiions 级别的图标](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|<span data-ttu-id="0fb82-151">使用此方法可查看应用对 Office 365 数据的访问量。</span><span class="sxs-lookup"><span data-stu-id="0fb82-151">Use this to see how much access an app has to Office 365 data.</span></span> <span data-ttu-id="0fb82-152">权限级别指示 "**低**"、"**中**" 或 "**高**", 其中**低**可能表明应用程序仅访问用户的配置文件和名称。</span><span class="sxs-lookup"><span data-stu-id="0fb82-152">Permissions levels indicate **Low**, **Medium**, or **High**, where **Low** might indicate that the app only accesses a user's profile and name.</span></span> <span data-ttu-id="0fb82-153">选择要查看详细信息的级别, 例如授予应用程序的权限、社区使用以及[调控日志](suspend-or-restore-an-account-in-ocas.md)中的相关活动。</span><span class="sxs-lookup"><span data-stu-id="0fb82-153">Select the level to view more information, such as permissions granted to the app, community use, and related activity in the [Governance log](suspend-or-restore-an-account-in-ocas.md).</span></span>  <br/> |
|<span data-ttu-id="0fb82-154">上次授权</span><span class="sxs-lookup"><span data-stu-id="0fb82-154">Last authorized</span></span> <br/> |<span data-ttu-id="0fb82-155">使用此操作可查看 OAuth 应用上次授权访问组织的 Office 365 数据的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0fb82-155">Use this to see the date and time an OAuth app was last authorized to access your organization's Office 365 data.</span></span> <br/>  |
|<span data-ttu-id="0fb82-156">操作</span><span class="sxs-lookup"><span data-stu-id="0fb82-156">Actions</span></span><br/>![OAuth 应用程序](media/OCAS-OAuthAppApproveBanReport.png)<br/> |<span data-ttu-id="0fb82-158">使用此方法可查看或将应用程序标记为已批准或禁止, 将 OAuth 应用报告给 Microsoft, 或将其保留为未定。</span><span class="sxs-lookup"><span data-stu-id="0fb82-158">Use this to see or to mark an app as Approved or Banned, report an OAuth app to Microsoft, or leave it as undetermined.</span></span>  <br/> |
   
## <a name="mark-an-app-as-approved"></a><span data-ttu-id="0fb82-159">将应用程序标记为已批准</span><span class="sxs-lookup"><span data-stu-id="0fb82-159">Mark an app as approved</span></span>

<span data-ttu-id="0fb82-160">在 "**管理 OAuth 应用**程序" 页上, 找到要批准的应用程序, 然后选择 "将**应用标记为已批准**" 图标。</span><span class="sxs-lookup"><span data-stu-id="0fb82-160">On the **Manage OAuth apps** page, locate the app you want to approve, and choose the **Mark app as approved** icon.</span></span> 
  
![选择 "将应用标记为已批准" 图标](media/OCAS-MarkOAuthApproved.png)
  
<span data-ttu-id="0fb82-162">图标将变为绿色, 并且应用程序将针对所有 Office 365 用户进行审批。</span><span class="sxs-lookup"><span data-stu-id="0fb82-162">The icon turns green, and the app is approved for all your Office 365 users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0fb82-163">当您将某个应用程序标记为已批准时, 最终用户将不会有任何影响。</span><span class="sxs-lookup"><span data-stu-id="0fb82-163">When you mark an app as approved, there is no effect on the end user.</span></span> <span data-ttu-id="0fb82-164">以可视方式标记已批准的应用程序有助于将它们与尚未审阅的应用程序分开。</span><span class="sxs-lookup"><span data-stu-id="0fb82-164">Visually marking the apps that are approved helps to separate them from apps that haven't been reviewed yet.</span></span> 
  
## <a name="ban-an-app"></a><span data-ttu-id="0fb82-165">禁止应用</span><span class="sxs-lookup"><span data-stu-id="0fb82-165">Ban an app</span></span>

1. <span data-ttu-id="0fb82-166">在 "**管理 OAuth 应用**程序" 页上, 找到要禁止的应用程序, 然后选择 "**标记应用" 作为 "禁止**" 图标。</span><span class="sxs-lookup"><span data-stu-id="0fb82-166">On the **Manage OAuth apps** page, locate the app you want to ban, and choose the **Mark app as banned** icon.</span></span><br/><span data-ttu-id="0fb82-167">![选择 "标记应用" 作为 "禁止" 图标](media/OCAS-MarkOAuthBanned.png)</span><span class="sxs-lookup"><span data-stu-id="0fb82-167">![Choose the Mark app as banned icon](media/OCAS-MarkOAuthBanned.png)</span></span>
  
2. <span data-ttu-id="0fb82-168">在通知消息框中, 保留现有文本, 或自定义文本。</span><span class="sxs-lookup"><span data-stu-id="0fb82-168">In the notification message box, keep the existing text as it is, or customize the text.</span></span> <span data-ttu-id="0fb82-169">选择是否让用户知道他们的应用程序已被禁止。</span><span class="sxs-lookup"><span data-stu-id="0fb82-169">Choose whether to let users know that their app has been banned.</span></span> <br/>![阻止的应用程序的邮件模板](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. <span data-ttu-id="0fb82-171">选择 "**禁止应用**"。</span><span class="sxs-lookup"><span data-stu-id="0fb82-171">Choose **Ban app**.</span></span>

## <a name="report-an-oauth-app-to-microsoft"></a><span data-ttu-id="0fb82-172">向 Microsoft 报告 OAuth 应用</span><span class="sxs-lookup"><span data-stu-id="0fb82-172">Report an OAuth app to Microsoft</span></span>

<span data-ttu-id="0fb82-173">如果要将 OAuth 应用程序提交到 Microsoft 进行分析, 可以报告该应用程序。</span><span class="sxs-lookup"><span data-stu-id="0fb82-173">If you want to submit an OAuth app to Microsoft for analysis, you can report that app.</span></span>

1. <span data-ttu-id="0fb82-174">在 "**管理 OAuth 应用**程序" 页上, 找到要提交以供分析的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0fb82-174">On the **Manage OAuth apps** page, locate the app you want to submit for analysis.</span></span>

2. <span data-ttu-id="0fb82-175">选择垂直省略号, 然后选择 "**报告应用 ...**"。</span><span class="sxs-lookup"><span data-stu-id="0fb82-175">Choose the vertical ellipsis, and then choose **Report app...**.</span></span><br/><span data-ttu-id="0fb82-176">![报告 OAuth 应用](media/OCAS-MarkOAuthReported.png)</span><span class="sxs-lookup"><span data-stu-id="0fb82-176">![Report an OAuth app](media/OCAS-MarkOAuthReported.png)</span></span><br/>

3. <span data-ttu-id="0fb82-177">在 "**报告此应用程序**" 对话框中, 使用下拉列表指示你的关注。</span><span class="sxs-lookup"><span data-stu-id="0fb82-177">In the **Report this app** dialog box, use the drop-down list to indicate your concern.</span></span> <span data-ttu-id="0fb82-178">默认情况下, 将选择**此应用程序是恶意**的。</span><span class="sxs-lookup"><span data-stu-id="0fb82-178">By default, **This app is malicious** is selected.</span></span> <span data-ttu-id="0fb82-179">不过, 您可以选择其他可用选项之一。</span><span class="sxs-lookup"><span data-stu-id="0fb82-179">However, you can choose on one of the other available options.</span></span> <br/><span data-ttu-id="0fb82-180">![报告 OAuth 应用](media/OCAS-ReportOAuthApp.png)</span><span class="sxs-lookup"><span data-stu-id="0fb82-180">![Report an OAuth app](media/OCAS-ReportOAuthApp.png)</span></span><br/>

4. <span data-ttu-id="0fb82-181">适合保留选择 "联系" 选项, 并确认 (或编辑) 列出的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0fb82-181">(Recommended) Keep the option to contact you selected, and confirm (or edit) the email address listed.</span></span>

5. <span data-ttu-id="0fb82-182">Choose **Submit**.</span><span class="sxs-lookup"><span data-stu-id="0fb82-182">Choose **Submit**.</span></span> 
    
## <a name="create-an-app-query"></a><span data-ttu-id="0fb82-183">创建应用程序查询</span><span class="sxs-lookup"><span data-stu-id="0fb82-183">Create an app query</span></span>

<span data-ttu-id="0fb82-184">我们建议使用 "高级" 视图, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="0fb82-184">We recommend using the Advanced view, which looks like this:</span></span> 

![高级视图](media/OCAS-OAuthAppsAdvQueryView.png)

<span data-ttu-id="0fb82-186">在应用程序查询栏中, 如果您看到 "**高级**", 则使用的是 "基本" 视图。</span><span class="sxs-lookup"><span data-stu-id="0fb82-186">In the app query bar, if you see **Advanced**, you're using the Basic view.</span></span> <span data-ttu-id="0fb82-187">单击 (或点击) "**高级**" 以转到 "高级" 视图。</span><span class="sxs-lookup"><span data-stu-id="0fb82-187">Click (or tap) **Advanced** to go to the Advanced view.</span></span> 

![基本视图](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. <span data-ttu-id="0fb82-189">在查询栏中, 使用 "**选择筛选器**" 列表选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="0fb82-189">In the query bar, use the **Select a filter** list to choose an option.</span></span> 
    - <span data-ttu-id="0fb82-190">**应用**具有特定名称的应用程序</span><span class="sxs-lookup"><span data-stu-id="0fb82-190">**App** Apps with certain names</span></span>
    - <span data-ttu-id="0fb82-191">**应用程序状态**基于其状态 ("已批准"、"禁止" 或 "不确定") 的应用程序</span><span class="sxs-lookup"><span data-stu-id="0fb82-191">**App state** Apps based on their state (Approved, Banned, or Undetermined)</span></span>
    - <span data-ttu-id="0fb82-192">**社区使用**基于社区使用级别的应用程序 (极少、不常见或常见)</span><span class="sxs-lookup"><span data-stu-id="0fb82-192">**Community use** Apps based on community use levels (Rare, Uncommon, or Common)</span></span>
    - <span data-ttu-id="0fb82-193">**权限级别**基于某些权限级别的应用程序</span><span class="sxs-lookup"><span data-stu-id="0fb82-193">**Permission level** Apps based on certain permission levels</span></span> 
    - <span data-ttu-id="0fb82-194">**权限**需要特定权限的应用程序</span><span class="sxs-lookup"><span data-stu-id="0fb82-194">**Permissions** Apps that require certain permissions</span></span>
    - <span data-ttu-id="0fb82-195">**发布服务器** 来自特定发布者的应用程序</span><span class="sxs-lookup"><span data-stu-id="0fb82-195">**Publisher**  Apps from certain publishers</span></span>
    - <span data-ttu-id="0fb82-196">**用户**某个用户授权的应用程序</span><span class="sxs-lookup"><span data-stu-id="0fb82-196">**User** Apps that a certain user authorized</span></span>
   
2. <span data-ttu-id="0fb82-197">选择 "**等于**或**不等于**", 然后为您的筛选器指定值。</span><span class="sxs-lookup"><span data-stu-id="0fb82-197">Select **equals** or **does not equal**, and then specify a value for your filter.</span></span>
    
3. <span data-ttu-id="0fb82-198">若要添加更多筛选器, 请选择加号 (</span><span class="sxs-lookup"><span data-stu-id="0fb82-198">To add more filters, select the plus sign (</span></span>![添加用于查询应用程序的筛选器图标](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)<span data-ttu-id="0fb82-200">), 然后重复步骤2和3。</span><span class="sxs-lookup"><span data-stu-id="0fb82-200">), and then repeat steps 2 and 3.</span></span>
    
4. <span data-ttu-id="0fb82-201">若要删除筛选器, 请选择 x (</span><span class="sxs-lookup"><span data-stu-id="0fb82-201">To remove a filter, select the x (</span></span>![删除用于查询应用程序的筛选器图标](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)<span data-ttu-id="0fb82-203">) 旁边的筛选器名称。</span><span class="sxs-lookup"><span data-stu-id="0fb82-203">) next to a filter name.</span></span>
    
<span data-ttu-id="0fb82-204">将自动应用筛选器, 并相应地更新 "应用" 列表。</span><span class="sxs-lookup"><span data-stu-id="0fb82-204">The filters are applied automatically, and the apps list is updated accordingly.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="0fb82-205">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0fb82-205">Next steps</span></span>

- [<span data-ttu-id="0fb82-206">查看警报并对其执行操作</span><span class="sxs-lookup"><span data-stu-id="0fb82-206">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- <span data-ttu-id="0fb82-207">查看[适用于 Office 365 云应用程序安全性的 Web 流量日志和数据源](web-traffic-logs-and-data-sources-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="0fb82-207">Review your [Web traffic logs and data sources for Office 365 Cloud App Security](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    
- <span data-ttu-id="0fb82-208">查看[Office 365 云应用安全性的利用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="0fb82-208">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    


---
title: Microsoft 合规性管理器和 GDPR
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性管理器是 Microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使你能够跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。
ms.openlocfilehash: e41b28972dc2ada5c0591de0e73c04ea3306e039
ms.sourcegitcommit: 3962de88a143f0eb416b5cfdfd777d731f560ec8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "36649957"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="e2c89-104">Microsoft 合规性管理器和 GDPR</span><span class="sxs-lookup"><span data-stu-id="e2c89-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="e2c89-105">欧盟制定的一般数据保护条例 (GDPR) 可能会影响您的合规性策略, 并强制执行特定操作, 以管理合规性管理器中使用的用户和客户信息。</span><span class="sxs-lookup"><span data-stu-id="e2c89-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="e2c89-106">用户隐私设置</span><span class="sxs-lookup"><span data-stu-id="e2c89-106">User Privacy settings</span></span>

<span data-ttu-id="e2c89-107">某些法规要求组织必须能够删除用户历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="e2c89-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="e2c89-108">合规性管理器提供的**用户隐私设置**功能允许管理员执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e2c89-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="e2c89-109">搜索用户</span><span class="sxs-lookup"><span data-stu-id="e2c89-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="e2c89-110">导出帐户数据历史记录报告</span><span class="sxs-lookup"><span data-stu-id="e2c89-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="e2c89-111">删除用户数据历史记录</span><span class="sxs-lookup"><span data-stu-id="e2c89-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="e2c89-112">搜索用户</span><span class="sxs-lookup"><span data-stu-id="e2c89-112">Search for a user</span></span>

<span data-ttu-id="e2c89-113">若要搜索用户帐户，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e2c89-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="e2c89-114">输入用户电子邮件别名 (@ 符号左侧的信息), 然后从右侧的 "域后缀" 列表中选择域名。</span><span class="sxs-lookup"><span data-stu-id="e2c89-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="e2c89-115">对于具有多个注册域的组织, 请仔细检查域名后缀以确保其正确无误。</span><span class="sxs-lookup"><span data-stu-id="e2c89-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="e2c89-116">正确输入了用户名后, 选择 "**搜索**"。</span><span class="sxs-lookup"><span data-stu-id="e2c89-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="e2c89-117">对于未返回的用户帐户, 该页面显示 "**找不到用户**"。</span><span class="sxs-lookup"><span data-stu-id="e2c89-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="e2c89-118">检查用户的电子邮件地址信息, 并根据需要进行更正。</span><span class="sxs-lookup"><span data-stu-id="e2c89-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="e2c89-119">若要重试, 请选择 "**搜索**"。</span><span class="sxs-lookup"><span data-stu-id="e2c89-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="e2c89-120">对于返回的用户帐户, 该按钮的文本将从 "**搜索**" 更改为 "**清除**"。</span><span class="sxs-lookup"><span data-stu-id="e2c89-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="e2c89-121">这表示返回的用户帐户是其他函数的操作上下文, 并且这些函数适用于此用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e2c89-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="e2c89-122">若要清除搜索结果并搜索其他用户, 请选择 "**清除**"。</span><span class="sxs-lookup"><span data-stu-id="e2c89-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="e2c89-123">导出帐户数据历史记录报告</span><span class="sxs-lookup"><span data-stu-id="e2c89-123">Export a report of account data history</span></span>

<span data-ttu-id="e2c89-124">对于标识的每个用户帐户, 您可以生成链接到此帐户的依赖项的报告。</span><span class="sxs-lookup"><span data-stu-id="e2c89-124">For each user account identified, you can generate a report of dependencies linked to this account.</span></span> <span data-ttu-id="e2c89-125">此信息使您可以重新分配打开的操作项或确保对以前上载的证据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e2c89-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="e2c89-126">若要生成并导出报告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e2c89-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="e2c89-127">选择 "**导出**" 以生成并下载当前分配给返回的用户帐户的合规性管理器控件操作项的报告, 以及该用户上载的文档列表。</span><span class="sxs-lookup"><span data-stu-id="e2c89-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="e2c89-128">如果没有分配的操作或上载的文档, 则错误消息将显示 "没有此用户的数据"。</span><span class="sxs-lookup"><span data-stu-id="e2c89-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="e2c89-129">报告在活动浏览器窗口的后台下载—如果看不到要检查浏览器下载历史记录的下载弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="e2c89-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="e2c89-130">打开文档即可查看报告数据。</span><span class="sxs-lookup"><span data-stu-id="e2c89-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2c89-131">报告数据不是一个历史记录列表, 可保留并显示对措施项分配历史记录的状态更改。</span><span class="sxs-lookup"><span data-stu-id="e2c89-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="e2c89-132">生成的报告是运行报告时分配的控制措施项目 (写入报告中的日期和时间戳) 的快照。</span><span class="sxs-lookup"><span data-stu-id="e2c89-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="e2c89-133">例如, 如果为同一用户再次生成报表, 则任何后续的操作项重新分配都将导致不同的快照报告数据。</span><span class="sxs-lookup"><span data-stu-id="e2c89-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="e2c89-134">删除用户数据历史记录</span><span class="sxs-lookup"><span data-stu-id="e2c89-134">Delete user data history</span></span>

<span data-ttu-id="e2c89-135">将所有分配给返回的用户的控制操作项设置为 "未分配"。</span><span class="sxs-lookup"><span data-stu-id="e2c89-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="e2c89-136">将由返回的用户上载的任何文档的已**上载**的值设置为 "用户删除"。</span><span class="sxs-lookup"><span data-stu-id="e2c89-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="e2c89-137">删除用户帐户操作项和文档上载历史记录:</span><span class="sxs-lookup"><span data-stu-id="e2c89-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="e2c89-138">选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="e2c89-138">Select **Delete**.</span></span>

    <span data-ttu-id="e2c89-139">将显示确认对话框, "*这将删除所选用户的所有控制措施项分配和文档上传历史记录。此操作是永久性的。是否确实要继续？*</span><span class="sxs-lookup"><span data-stu-id="e2c89-139">A confirmation dialog is displayed, "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="e2c89-140">若要继续, 请选择 **"确定"**, 否则选择 "**取消**"。</span><span class="sxs-lookup"><span data-stu-id="e2c89-140">To continue select **OK**, otherwise select **Cancel**.</span></span>

---
title: 在 Office 365 安全&amp;合规中心中使用 DSR 机箱工具管理 GDPR 数据主体请求
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/25/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: ce9eb942-3589-42cb-88fd-1576ecb09c5c
description: GDPR 向欧盟公民 (称为 "数据主体") 授予对其个人数据的特定权限;这些权限包括获取副本、请求对其进行更改、限制处理、删除或以电子格式接收。通过数据主体对其个人数据执行操作的正式请求称为 "数据" 主题请求或 "DSR"。您可以使用 Office 365 安全&amp;合规中心中的 DSR 案例来管理您的组织的 DSR 调查。
ms.openlocfilehash: fe702ab9050e76b6b8f00fbc8d2670505a030756
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296585"
---
# <a name="manage-gdpr-data-subject-requests-with-the-dsr-case-tool-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="9e1ff-105">在 Office 365 安全&amp;合规中心中使用 DSR 机箱工具管理 GDPR 数据主体请求</span><span class="sxs-lookup"><span data-stu-id="9e1ff-105">Manage GDPR data subject requests with the DSR case tool in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="9e1ff-p102">EU 常规数据保护条例 (GDPR) 是关于保护和启用欧盟 (EU) 内部的个人隐私权利的信息。GDPR 为欧盟 (称为数据主题) 中的个人提供访问、检索、更正、擦除和限制其个人数据处理的权限。在 "GDPR" 下, "个人数据" 是指与标识或标识的自然个人相关的任何信息。某人向其组织对其个人数据执行操作的正式请求称为 "数据" 主题请求或 "DSR"。有关对 Office 365 中的数据响应 dsr 的详细信息, 请参阅[office 365 data Subject 请求指南](https://go.microsoft.com/fwlink/?linkid=871169 )。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p102">The EU General Data Protection Regulation (GDPR) is about protecting and enabling individuals' privacy rights inside the European Union (EU). The GDPR gives individuals in the European Union (known as data subjects) the right to access, retrieve, correct, erase, and restrict processing of their personal data. Under the GDPR, personal data means any information relating to an identified or identifiable natural person. A formal request by a person to their organization to take an action on their personal data is called a Data Subject Request or DSR. For detailed information about responding to DSRs for data in Office 365, see [Office 365 Data Subject Request Guide](https://go.microsoft.com/fwlink/?linkid=871169 ).</span></span>
  
<span data-ttu-id="9e1ff-111">若要管理对由组织中的人员提交的 DSR 的调查, 可以使用 Office 365 安全&amp;合规中心中的 DSR 案例工具查找存储在中的内容:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-111">To manage investigations in response to a DSR submitted by a person in your organization, you can use the DSR case tool in the Office 365 Security &amp; Compliance Center to find content stored in:</span></span>
  
- <span data-ttu-id="9e1ff-p103">组织中的任何用户邮箱。这包括 Microsoft 团队中的 Skype for business 对话和一对一聊天</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p103">Any user mailbox in your organization. This includes Skype for Business conversations and one-to-one chats in Microsoft Teams</span></span>
    
- <span data-ttu-id="9e1ff-114">与 Microsoft 团队中的 Office 365 组和所有团队邮箱关联的所有邮箱</span><span class="sxs-lookup"><span data-stu-id="9e1ff-114">All mailboxes associated with an Office 365 Group and all team mailboxes in Microsoft Teams</span></span>
    
- <span data-ttu-id="9e1ff-115">组织中的所有 SharePoint Online 网站和 OneDrive for Business 帐户</span><span class="sxs-lookup"><span data-stu-id="9e1ff-115">All SharePoint Online sites and OneDrive for Business accounts in your organization</span></span>
    
- <span data-ttu-id="9e1ff-116">组织中的所有团队网站和 Office 365 组网站</span><span class="sxs-lookup"><span data-stu-id="9e1ff-116">All Teams sites and Office 365 Group sites in your organization</span></span>
    
- <span data-ttu-id="9e1ff-117">Exchange Online 中的所有公用文件夹</span><span class="sxs-lookup"><span data-stu-id="9e1ff-117">All public folders in Exchange Online</span></span>
    
<span data-ttu-id="9e1ff-118">使用 DSR 机箱工具, 可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-118">Using the DSR case tool you can:</span></span>
  
- <span data-ttu-id="9e1ff-119">为每个 DSR 调查创建单独的事例。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-119">Create a separate case for each DSR investigation.</span></span>
    
- <span data-ttu-id="9e1ff-p104">通过将人员添加为案例成员来控制谁有权访问 DSR 事例;仅成员可以访问事例, 并且只能在安全&amp;合规中心的 " **DSR 事例**" 页上的事例列表中查看其事例。此外, 还可以为同一事例的不同成员分配不同的权限。例如, 您可以允许某些成员只查看事例和搜索结果, 并允许其他成员创建搜索和导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p104">Control who has access to the DSR case by adding people as members of the case; only members can access the case and can only see their cases in the list of cases on the **DSR cases** page in the Security &amp; Compliance Center. Additionally, you can assign different permissions to different members of the same case. For example, you can allow some members to only view the case and search results and allow other members to create searches and export search results.</span></span> 
    
- <span data-ttu-id="9e1ff-123">使用内置搜索来搜索由特定数据主体创建或上载的所有内容。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-123">Use the built-in search to search for all content created or uploaded by a specific data subject.</span></span>
    
- <span data-ttu-id="9e1ff-124">(可选) 修改内置搜索查询并重新运行搜索以缩小搜索结果的范围。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-124">Optionally revise the built-in search query and re-run the search to narrow the search results.</span></span>
    
- <span data-ttu-id="9e1ff-p105">添加与 DSR 事例相关联的其他内容搜索。这包括创建从我的分析和 Office 漫游服务中返回部分索引项和系统生成日志的搜索。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p105">Add additional content searches associated with the DSR case. This includes creating searches that return partially indexed items and system-generated logs from My Analytics and the Office Roaming Service.</span></span>
    
- <span data-ttu-id="9e1ff-127">导出数据以响应 DSR 访问或导出请求。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-127">Export data in response to a DSR access or export request.</span></span>
    
- <span data-ttu-id="9e1ff-128">在 DSR 调查过程完成时删除事例;这将删除与该事例关联的所有搜索和导出作业。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-128">Delete cases when the DSR investigation process is complete; this will remove all searches and export jobs associated with the case.</span></span>
    
<span data-ttu-id="9e1ff-129">以下是使用 dsr 机箱工具管理 dsr 调查的高级别过程:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-129">Here's the high-level process for using the DSR case tool to manage DSR investigations:</span></span>
  
[<span data-ttu-id="9e1ff-130">步骤 1：向潜在事例成员分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="9e1ff-130">Step 1: Assign eDiscovery permissions to potential case members</span></span>](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[<span data-ttu-id="9e1ff-131">步骤 2: 创建 DSR 事例并添加成员</span><span class="sxs-lookup"><span data-stu-id="9e1ff-131">Step 2: Create a DSR case and add members</span></span>](#step-2-create-a-dsr-case-and-add-members)

[<span data-ttu-id="9e1ff-132">步骤 3: 运行搜索查询</span><span class="sxs-lookup"><span data-stu-id="9e1ff-132">Step 3: Run the search query</span></span>](#step-3-run-the-search-query)

[<span data-ttu-id="9e1ff-133">步骤 4: 导出数据</span><span class="sxs-lookup"><span data-stu-id="9e1ff-133">Step 4: Export the data</span></span>](#step-4-export-the-data)

[<span data-ttu-id="9e1ff-134">Optional步骤 5: 修订内置搜索查询</span><span class="sxs-lookup"><span data-stu-id="9e1ff-134">(Optional) Step 5: Revise the built-in search query</span></span>](#optional-step-5-revise-the-built-in-search-query)

[<span data-ttu-id="9e1ff-135">有关使用 DSR 机箱工具的详细信息</span><span class="sxs-lookup"><span data-stu-id="9e1ff-135">More information about using the DSR case tool</span></span>](#more-information-about-using-the-dsr-case-tool)
  
> [!IMPORTANT]
> <span data-ttu-id="9e1ff-p106">通过使管理员能够利用在 dsr 机箱工具中找到的内置搜索和导出功能, 我们的工具可以帮助管理员执行 DSR access 或出口请求。该工具有助于促进最佳的工作方式, 以导出与数据主体提交的 DSR 请求相关的数据。但是, 请务必注意, 搜索结果可能因可能会影响某个项目是否被视为 "个人数据" 进行导出而发生变化的数据主体或管理员操作而异。例如, 如果数据主体是上次修改未创建的文件的人, 则该文件可能不会在搜索结果中返回。同样, 管理员可以在不包含部分索引项目或 SharePoint 文档的所有版本的情况下导出数据。因此, 提供的工具有助于简化数据请求的访问和导出。但是, 这些结果取决于特定的管理员和数据使用者使用方案。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p106">Our tools can help admins perform DSR access or export requests by enabling them to utilize the built-in search and export functionality found in the DSR case tool. The tool helps to facilitate a best-effort method to export data that's relevant to a DSR request submitted by a data subject. However, it's important to note that search results can vary based on the data subject or the admin actions taken that may impact whether or not an item would be deemed as "personal data" for export purposes. For example, if the data subject was the last person to modify a file they didn't create, the file might not be returned in the search results. Similarly, an admin could export data without including partially indexed items or all versions of SharePoint documents. Therefore, the tools provided can help facilitate accessing and exporting data requests; however, the results are subject to specific admin and data subject usage scenarios.</span></span> 
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a><span data-ttu-id="9e1ff-142">步骤 1：向潜在事例成员分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="9e1ff-142">Step 1: Assign eDiscovery permissions to potential case members</span></span>

<span data-ttu-id="9e1ff-p107">默认情况下, Office 365 全局管理员可以访问安全&amp;合规性中心中的 DSR 机箱工具。按照设计, 其他用户 (如数据隐私官、人力资源经理或其他参与 dsr 调查的人员) 无法访问 dsr 机箱工具, 必须为其分配适当的权限才能访问该工具。执行此操作最简单的方法是转到安全\*\*\*\* &amp;合规性中心中的 "权限" 页, 并将用户添加到 "电子数据展示管理器" 角色组。请注意, 您还必须分配这些权限, 以便将其添加为您在步骤2中创建的 DSR 事例的成员。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p107">By default, an Office 365 global administrator can access the DSR case tool in the Security &amp; Compliance Center. By design, other users such as a data privacy officer, a human resources manager, or other people involved in DSR investigations don't have access to the DSR case tool and will have to be assigned the appropriate permissions to access the tool. The easiest way to do this is to go to the **Permissions** page in the Security &amp; Compliance Center and add users to the eDiscovery Manager role group. Note that you also have to assign these permissions so you can add them as members of the DSR case that you create in Step 2.</span></span> 
  
<span data-ttu-id="9e1ff-147">有关分步说明, 请参阅[在 Office 365 安全&amp;合规中心中分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-147">For step-by-step instructions, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e1ff-p108">默认情况下, Office 365 全局管理员 (或安全&amp;合规中心中的组织管理角色组的其他成员不具有导出内容搜索结果所需的权限 (请参阅本文中的步骤 4)。若要解决此情况, 管理员可以将自己添加为电子数据展示管理器角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p108">By default, an Office 365 global administrator (or other members of the Organization Management role group in the Security &amp; Compliance Center don't have the necessary permissions to export Content Search results (see Step 4 in this article). To address this, an admin can add themselves as a member of the eDiscovery Manager role group.</span></span> 
  
## <a name="step-2-create-a-dsr-case-and-add-members"></a><span data-ttu-id="9e1ff-150">步骤 2: 创建 DSR 事例并添加成员</span><span class="sxs-lookup"><span data-stu-id="9e1ff-150">Step 2: Create a DSR case and add members</span></span>

<span data-ttu-id="9e1ff-p109">下一步是创建 DSR 事例。创建事例时, 可以选择启动内置搜索, 也可以在不启动搜索的情况下创建事例。下面的过程将指导您在不启动搜索的情况下创建事例, 并向您介绍如何向事例添加成员。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p109">The next step is to create a DSR case. When you create a case, you can choose to start the built-in search or you can create the case without starting the search. The following procedure will instruct you to create the case without starting the search and then show you how to add members to the case.</span></span>
  
1. <span data-ttu-id="9e1ff-154">请转[https://protection.office.com](https://protection.office.com)到使用你的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-154">Go to [https://protection.office.com](https://protection.office.com) and sign in to Office 365 using your work or school account.</span></span> 
    
2. <span data-ttu-id="9e1ff-155">在安全&amp;合规性中心中, 单击 "**数据隐私** \> **数据主体请求**", ![然后单击](media/ITPro-EAC-AddIcon.gif) "添加图标" "**新建 DSR 事例**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-155">In the Security &amp; Compliance Center, click **Data privacy** \> **Data subject requests**, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New DSR case**.</span></span>
    
3. <span data-ttu-id="9e1ff-p110">在 "**新建 DSR 事例**" 弹出页面上, 为事例指定名称, 键入可选说明, 然后单击 "**下一步**"。请注意, 此案例的名称在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p110">On the **New DSR case** flyout page, give the case a name, type an optional description, and then click **Next**. Note that the name of the case must be unique in your organization.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="9e1ff-p111">请考虑在新事例的名称和/或说明中添加提交您正在调查的 DSR 请求的人员的姓名。请注意, 只有此事例 (和电子数据展示管理员) 的成员才能够在 "**数据主体请求**" 页上的事例列表中查看事例。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p111">Consider adding the name of the person who submitted the DSR request that you're investigating in the name and/or description of the new case. Note that only members of this case (and eDiscovery Administrators) will be able to see the case in the list of cases on the **Data subject requests** page.</span></span> 
  
4. <span data-ttu-id="9e1ff-160">在 "**请求详细信息**" 页上的 "**数据主体 (存档此请求的人员)**" 下, 选择要查找和导出其数据的人员, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-160">On the **Request details** page, under **Data subject (the person who filed this request)**, select the person that you want to find and export data for and then click **Next**.</span></span>
    
5. <span data-ttu-id="9e1ff-p112">在 "**确认您的事例设置**" 页上, 您可以更改事例名称和说明, 并选择其他数据主体。否则, 只需单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p112">On the **Confirm your case settings** page, you can change the case name and description, and select a different data subject. Otherwise, just click **Save**.</span></span>
    
    <span data-ttu-id="9e1ff-163">将显示一页, 确认已创建新的 DSR 事例。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-163">A page is displayed that confirms the new DSR case has been created.</span></span>
    
    ![启动搜索或仅关闭新的 DSR 事例页面](media/b5e62c2c-cafe-4a8d-a38c-789ed9f9ccbd.png)
  
    <span data-ttu-id="9e1ff-165">在这种情况下, 您可以执行以下两项操作之一:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-165">At this point, you can do one of two things:</span></span>
    
    <span data-ttu-id="9e1ff-p113">依次单击 "**显示我的搜索结果**" 将启动搜索。这是默认选择。当您选择此选项以及返回的结果时, 将在步骤3中讨论内置搜索。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p113">a. Clicking **Show me search results** starts the search. This is the default selection. The built-in search that is run when you select this option and the results that are returned are discussed in Step 3.</span></span>
    
    <span data-ttu-id="9e1ff-p114">b. 单击 "**完成**" 将关闭新的 DSR 事例, 而不启动内置搜索。选择此选项时, 新的 DSR 事例将显示在 "**数据主体请求**" 页上。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p114">b. Clicking **Finish** closes the new DSR case without starting the built-in search. When you select this option, the new DSR case is displayed on the **Data subject requests** page.</span></span>
    
6. <span data-ttu-id="9e1ff-173">单击 "**完成**", 以便可以进入新的 DSR 事例并向其添加成员。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-173">Click **Finish** so that you can go in to the new DSR case and add members to it.</span></span> 
    
7. <span data-ttu-id="9e1ff-174">在 "**数据主体请求**" 页上, 单击刚刚创建的 DSR 事例的名称。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-174">On the **Data subject requests** page, click the name of the DSR case that you just created.</span></span> 
    
8. <span data-ttu-id="9e1ff-175">在 "**管理此案例**" 弹出页面上的 "**管理成员**" 下, 单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-175">On the **Manage this case** flyout page, under **Manage members**, click **Add**.</span></span> 
    
    <span data-ttu-id="9e1ff-p115">在 "**用户**" 下, 将显示已分配了相应电子数据展示权限的人员的列表。请注意, 在步骤1中为您分配的电子数据展示权限的人员将显示在此列表中。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p115">Under **Users**, a list of people that have been assigned the appropriate eDiscovery permissions is displayed. Note that the people you assigned eDiscovery permissions to in Step 1 will be displayed in this list.</span></span> 
    
9. <span data-ttu-id="9e1ff-178">选择要添加的人员作为 DSR 事例的成员, 单击 "**添加**", 然后保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-178">Select the people to add as members of the DSR case, click **Add**, and then save your changes.</span></span>
    
    <span data-ttu-id="9e1ff-179">请注意, 您还可以通过单击 "**管理角色组**" 下的 "**添加**", 将角色组添加为 DSR 事例的成员。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-179">Note that you can also add role groups as members of DSR case by clicking **Add** under **Manage role groups**.</span></span> 
    
## <a name="step-3-run-the-search-query"></a><span data-ttu-id="9e1ff-180">步骤 3: 运行搜索查询</span><span class="sxs-lookup"><span data-stu-id="9e1ff-180">Step 3: Run the search query</span></span>

<span data-ttu-id="9e1ff-p116">创建 DSR 事例并添加成员后, 下一步是运行与案例相关联的内置搜索。此默认搜索查询将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p116">After you create a DSR case and add members, the next step is to run the built-in search that's associated with the case. This default search query does the following:</span></span>
  
- <span data-ttu-id="9e1ff-p117">在组织中的所有邮箱中搜索数据主体发送或接收的所有电子邮件项目。这是通过使用*参与者*电子邮件属性来实现的, 该属性在电子邮件中的所有人员字段中搜索数据主题。此属性返回数据主题位于 "**发件人**"、"**收件人**"、 **"抄送**" 和 **"密件抄送**" 字段中的项。此外, 还会搜索 Exchange Online 中的公用文件夹, 以查找数据主体发送或接收的邮件。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p117">Searches all mailboxes in your organization for all email items that were sent or received by the data subject. This is accomplished by using the  *Participants*  email property, which searches for the data subject in all the people fields in an email message. This property returns items in which the data subject is in the **From**, **To**, **CC**, and **BCC** fields. Public folders in Exchange Online are also searched for messages sent or received by the data subject.</span></span> 
    
- <span data-ttu-id="9e1ff-p118">搜索组织中的所有网站, 以查找由数据主体创建或上载的文档和项目。这是通过使用以下网站属性来实现的:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p118">Searches all sites in your organization for documents and items that were created or uploaded by the data subject. This is accomplished by using the following site properties:</span></span>
    
  - <span data-ttu-id="9e1ff-p119">*author*属性返回 "Office 文档" 的 "作者" 字段中列出了数据主题的项。此值将持续存在, 即使文档被其他人复制和上载也是如此。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p119">The  *Author*  property returns items where the data subject is listed in the author field in Office documents. This value persists, even if the document is copied and uploaded by someone else.</span></span> 
    
  - <span data-ttu-id="9e1ff-191">*CreatedBy*属性返回由数据主体创建或上载的项。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-191">The  *CreatedBy*  property returns items that were created or uploaded by the data subject.</span></span> 
    
<span data-ttu-id="9e1ff-192">下面是创建 DSR 事例时自动创建的内置搜索的关键字查询的外观。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-192">Here's what the keyword query looks like for the built-in search that gets automatically created when you create a DSR case.</span></span>
  
```
participants:"<email address>" OR author:"<display name>" OR createdby:"<display name>"
```

<span data-ttu-id="9e1ff-193">例如, 如果数据主体的名称是中 Leonte, 则关键字查询将如下所示:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-193">For example, if the name of the data subject is Ina Leonte, the keyword query would look like this:</span></span>
  
```
participants:"ina@contoso.com" OR author:"Ina Leonte" OR createdby:"Ina Leonte"
```

 <span data-ttu-id="9e1ff-194">**运行 DSR 机箱的内置搜索的步骤:**</span><span class="sxs-lookup"><span data-stu-id="9e1ff-194">**To run the built-in search for a DSR case:**</span></span>
  
1. <span data-ttu-id="9e1ff-195">在 "安全&amp;合规性中心" 中, 单击 "**数据隐私** \> **数据主体请求**", 然后单击您在步骤2中创建的 DSR 事例旁边的 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-195">In the Security &amp; Compliance Center, click **Data privacy** \> **Data subject requests**, and then click **Open** next to the DSR case that you created in Step 2.</span></span> 
    
    <span data-ttu-id="9e1ff-p120">单击页面顶部的 "**搜索**" 选项卡, 然后单击创建新的 DSR 事例时创建的内置搜索旁边的复选框。注释搜索与 DSR 事例具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p120">Click the **Search** tab at the top of the page, and then click the checkbox next to the built-in search that was created when you created the new DSR case. Note the search has the same name as the DSR case.</span></span> 
    
2. <span data-ttu-id="9e1ff-198">在 "搜索飞出" 页中, 单击 "**打开查询**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-198">In the search flyout page, click **Open query**.</span></span>
    
    <span data-ttu-id="9e1ff-199">当您打开查询时, 搜索将会启动, 并将在几分钟后完成。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-199">When you open the query, the search is started and will complete in a few moments.</span></span> 
    
3. <span data-ttu-id="9e1ff-p121">搜索完成后, 单击 "**预览结果**" 以预览搜索结果。有关详细信息, 请参阅[预览搜索结果](content-search.md#preview-search-results)。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p121">When the search is complete, click **Preview results** to preview the search results. For more information, see [Preview search results](content-search.md#preview-search-results).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="9e1ff-p122">您还可以查看搜索查询统计信息, 以查看由搜索返回的邮箱和网站项目数, 以及包含与搜索查询匹配的项目的顶部内容位置。有关详细信息, 请参阅[查看有关搜索的信息和统计](content-search.md#view-information-and-statistics-about-a-search)信息。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p122">You can also view the search query statistics to see the number of mailbox and site items that are returned by the search, and the top content locations that contain items that match the search query. For more information see, [View information and statistics about a search](content-search.md#view-information-and-statistics-about-a-search).</span></span> 
  
<span data-ttu-id="9e1ff-p123">您可以编辑内置搜索查询, 更改搜索的内容位置, 然后重新运行搜索。有关详细信息, 请参阅[第5步](#optional-step-5-revise-the-built-in-search-query)。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p123">You can edit the built-in search query, change the content locations that are searched, and then re-run the search. See [Step 5](#optional-step-5-revise-the-built-in-search-query) for more information.</span></span> 
  
## <a name="step-4-export-the-data"></a><span data-ttu-id="9e1ff-206">步骤 4: 导出数据</span><span class="sxs-lookup"><span data-stu-id="9e1ff-206">Step 4: Export the data</span></span>

<span data-ttu-id="9e1ff-p124">在运行内置搜索后, 您可以导出搜索结果。此外, 在导出数据之前, 您可能需要修改查询以减少搜索结果的数量。有关缩小搜索结果范围的详细信息, 请参阅第5步。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p124">After you run the built-in search, you can export the search results. Alternatively, before you export the data, you may want to revise the query to reduce the number of search results. See Step 5 for more information about narrowing the search results.</span></span>
  
<span data-ttu-id="9e1ff-p125">当您导出搜索结果时, 可以在 PST 文件中或单个邮件中下载邮箱项目。当您导出 SharePoint 和 OneDrive 帐户中的内容时, 将导出本机 Office 文档和其他文档的副本。包含有关导出的每个项目的信息的结果文件也包含在搜索结果中。有关导出的更多详细信息, 请参阅[Export Content Search results from the Office &amp; 365 Security 合规中心](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p125">When you export search results, mailbox items can be downloaded in PST files or as individual messages. When you export content from SharePoint and OneDrive accounts, copies of native Office documents and other documents are exported. A results file that contains information about every item that is exported is also included with the search results. For more detailed information about exporting, see [Export Content Search results from the Office 365 Security &amp; Compliance Center](export-search-results.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e1ff-p126">默认情况下, Office 365 全局管理员 (或安全&amp;合规中心中的组织管理角色组的其他成员) 没有导出内容搜索结果所需的权限。若要解决此情况, 管理员可以将自己添加为电子数据展示管理器角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p126">By default, an Office 365 global administrator (or other members of the Organization Management role group in the Security &amp; Compliance Center) don't have the necessary permissions to export Content Search results. To address this, an admin can add themselves as a member of the eDiscovery Manager role group.</span></span> 
  
<span data-ttu-id="9e1ff-216">用于导出数据的计算机必须满足以下系统要求:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-216">The computer you use to export data has to meet the following system requirements:</span></span>
  
- <span data-ttu-id="9e1ff-217">32 位或 64 位版本的 Windows 7 和更高版本</span><span class="sxs-lookup"><span data-stu-id="9e1ff-217">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
- <span data-ttu-id="9e1ff-218">Microsoft .net Framework 4。7</span><span class="sxs-lookup"><span data-stu-id="9e1ff-218">Microsoft .NET Framework 4.7</span></span>
    
- <span data-ttu-id="9e1ff-219">支持的浏览器：</span><span class="sxs-lookup"><span data-stu-id="9e1ff-219">A supported browser:</span></span>
    
  - <span data-ttu-id="9e1ff-220">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9e1ff-220">Microsoft Edge</span></span>
    
    <span data-ttu-id="9e1ff-221">或者</span><span class="sxs-lookup"><span data-stu-id="9e1ff-221">Or</span></span>
    
  - <span data-ttu-id="9e1ff-222">Microsoft Internet Explorer 10 及更高版本</span><span class="sxs-lookup"><span data-stu-id="9e1ff-222">Microsoft Internet Explorer 10 and later versions</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9e1ff-p127">Microsoft 不会为 ClickOnce 应用程序制造第三方扩展或加载项。不支持使用不受支持的浏览器导出数据和第三方分机或加载项。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p127">Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting data using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 
  
 <span data-ttu-id="9e1ff-225">**若要在 DSR 机箱中从内置搜索导出数据, 请执行以下操作:**</span><span class="sxs-lookup"><span data-stu-id="9e1ff-225">**To export data from the built-in search in a DSR case:**</span></span>
  
1. <span data-ttu-id="9e1ff-226">在 "安全&amp;合规性中心" 中, 单击 "**数据隐私** \> **数据主体请求**", 然后单击要从中导出数据的 DSR 事例旁边的 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-226">In the Security &amp; Compliance Center, click **Data privacy** \> **Data subject requests**, and then click **Open** next to the DSR case that you want to export data from.</span></span> 
    
2. <span data-ttu-id="9e1ff-p128">单击页面顶部的 "**搜索**" 选项卡, 然后单击创建 DSR 事例时创建的内置搜索旁边的复选框。或单击其他搜索以从该搜索中导出数据。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p128">Click the **Search** tab at the top of the page, and then click the checkbox next to the built-in search that was created when you created the DSR case. Or click another search to export data from that search.</span></span> 
    
3. <span data-ttu-id="9e1ff-229">在 "搜索" 飞出页面![上, 单击 "](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **更多**" "导出搜索结果" 图标, 然后从下拉列表中选择 "**导出结果**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-229">On the search flyout page, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then select **Export results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="9e1ff-230">在 "**导出结果**" 页上, 选择适用于 DSR 导出请求的以下推荐选项。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-230">On the **Export results** page, select the following recommended options for DSR export requests.</span></span> 
    
    ![配置导出设置](media/25416b79-57da-46a1-ae07-e640602a8fa4.png)
  
    <span data-ttu-id="9e1ff-p129">在 "**输出选项**" 下, 选择第一个选项 (**所有项目 (不包括具有无法识别的格式的项目) 进行加密, 或未针对其他原因对其编制索引,** 以仅导出已编制索引的项目。您不想从内置搜索中导出部分索引项目的原因是, 将导出其他用户的部分索引项目。若要仅导出数据主体的部分已编制索引的项目, 我们建议您创建单独的搜索。有关详细信息, 请参阅 "使用 DSR case 工具的详细信息" 部分中的 "[导出部分索引的项目](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#exportunindexeditems)" 部分。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p129">a. Under **Output options**, select the first option ( **All items, excluding ones that have ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons**) to export indexed items only. The reason you don't want to export partially indexed items from the built-in search is because partially indexed items from other users will be exported. To export only the partially indexed items for the data subject, we recommend that you create a separate search. For more information, see [Exporting partially indexed items](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#exportunindexeditems) in the "More information about using the DSR case tool" section.</span></span>
    
    <span data-ttu-id="9e1ff-p130">b. 在 "将**Exchange 内容导出为**" 下, 选择第三个选项 (**包含单个文件夹中的所有邮件的一个 PST 文件**)。由于某些结果可能针对的是其他用户的邮箱中的项目, 因此此选项仅在单个文件夹中列出项目, 而不指示实际邮箱, 并且是在按下一项目中的建议对结果进行重复复制时使用的最佳选项.此选项还允许数据主体按时间顺序查看项目 (按发送日期对项目进行排序), 而无需导航到每个项目的原始邮箱文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p130">b. Under **Export Exchange content as**, select the third option, **One PST file containing all messages in a single folder**. Because some of the results may be for items that originated in another user's mailbox, this option just lists the item in a single folder without indicating the actual mailbox and is the best option to use when you de-duplicate the results as recommended in the next item. This option also lets the data subject review items in chronological order (items are sorted by sent date) without having to navigate the original mailbox folder structure for each item.</span></span>
    
    <span data-ttu-id="9e1ff-p131">c. 选择 "**启用重复数据**删除" 选项以排除重复的电子邮件。我们建议您选择此选项, 因为内置搜索将搜索组织中的所有邮箱。因此, 如果在搜索的邮箱中找到同一邮件的多个副本, 则此选项表示将只导出邮件的一个副本。此选项一起将在单个文件夹中的一个 PST 文件中导出邮件将导致 DSR 导出请求的用户体验最佳。请注意, 结果 .csv 导出报告将列出找到重复邮件的所有位置。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p131">c. Select **Enable de-duplication** option to excludes duplicate email messages. We recommend this option because the built-in search searches all mailboxes in your organization. So if multiple copies of the same message are found in the mailboxes that were searched, this option means only one copy of a message will be exported. This option, together will exporting messages in one PST file in a single folder results in the best user experience for DSR export requests. Note that the Results.csv export report will list all locations where duplicate messages were found.</span></span>
    
    <span data-ttu-id="9e1ff-p132">(可选) 您可以选择 "**包括 sharepoint 文档的版本**" 选项以导出 sharepoint 和 OneDrive 文档的所有版本。这要求已为文档库启用版本控制。此选项有助于确保导出所有相关数据。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p132">Optionally, you can select **Include versions for SharePoint documents** option to export all versions of SharePoint and OneDrive documents. This requires that versioning is turned on for document libraries. This option helps to ensure that all relevant data is exported.</span></span>
    
5. <span data-ttu-id="9e1ff-250">选择导出设置后, 单击 "**导出**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-250">After you choose the export settings, click **Export**.</span></span>
    
    <span data-ttu-id="9e1ff-p133">搜索结果已准备好下载, 这意味着它们将被上载到 Microsoft 云中的组织的 Azure 存储区域。接下来的步骤演示了如何将此数据下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p133">The search results are prepared for downloading, which means they're uploaded to the Azure storage area for your organization in the Microsoft cloud. The next steps show you how to download this data to your local computer.</span></span>
    
6. <span data-ttu-id="9e1ff-p134">单击 "**导出**" 选项卡以显示刚创建的导出作业。请注意, 导出作业与对应的搜索具有相同的名称, 并在搜索名称的末尾追加 **_Export** 。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p134">Click the **Export** tab to display the export job you just created. Note that export jobs have the same name as the corresponding search with **_Export** appended to the end of search name.</span></span> 
    
7. <span data-ttu-id="9e1ff-p135">单击刚创建的导出作业以显示 "导出" 弹出页面。此页面显示有关搜索的信息, 如要导出的项目的大小和总数, 以及已转移到 Azure 存储区域的项目的百分比。单击 "**刷新**" 以更新上载状态信息。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p135">Click the export job that you just created to display the export flyout page. This page shows information about the search, such as the size and total number of items to be exported, and the percentage of the items that have been transferred to an Azure storage area. Click **Refresh** to update the upload status information.</span></span> 
    
8. <span data-ttu-id="9e1ff-p136">在 "**导出密钥**" 下, 单击 "**复制到剪贴板**"。您将在步骤11中使用此项下载搜索结果。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p136">Under **Export key**, click **Copy to clipboard**. You will use this key in step 11 to download the search results.</span></span>
    
9. <span data-ttu-id="9e1ff-260">单击!["导出弹出页面](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) " 顶部的 "导出搜索结果图标**下载结果**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-260">Click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Download results** at the top of the export flyout page.</span></span> 
    
10. <span data-ttu-id="9e1ff-p137">在页面底部的弹出窗口中, 单击 "**打开**" 以打开**Microsoft Office 365 电子数据展示导出工具**。首次下载搜索结果时, 将会安装**电子数据展示导出工具**。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p137">In the pop-up window at the bottom of the page, click **Open** to open the **Microsoft Office 365 eDiscovery Export Tool**. The **eDiscovery Export Tool** will be installed the first time you download search results.</span></span> 
    
11. <span data-ttu-id="9e1ff-263">在 "**电子数据展示导出工具**" 中, 将您在步骤8中复制的导出密钥粘贴在相应的框中。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-263">In the **eDiscovery Export Tool**, paste the export key that you copied in step 8 in the appropriate box.</span></span>
    
12. <span data-ttu-id="9e1ff-264">单击“**浏览**”指定要下载搜索结果文件的位置。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-264">Click **Browse** to specify the location where you want to download the search result files.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9e1ff-265">由于磁盘活动量过高 (读取和写入), 因此应将搜索结果下载到本地磁盘驱动器;不要将其下载到映射的网络驱动器或其他网络位置。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-265">Due to the high amount of disk activity (reads and writes), you should download search results to a local disk drive; don't download them to a mapped network drive or other network location.</span></span> 
  
13. <span data-ttu-id="9e1ff-266">单击“**开始**”将搜索结果下载到计算机。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-266">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="9e1ff-p138">**电子数据展示导出工具**显示有关导出过程的状态信息, 包括要下载的剩余项目的数字 (和大小) 的估计值。导出过程完成后, 可以在文件的下载位置访问这些文件。有关下载内容搜索结果时包括的报告的详细信息, 请参阅 "从 Office 365 安全&amp;合规中心导出内容搜索结果" 中的 "[详细信息](export-search-results.md#more-information)" 部分。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p138">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded. For more information about the reports that included when you download Content Search results, see the [More information](export-search-results.md#more-information) section in "Export Content Search results from the Office 365 Security &amp; Compliance Center".</span></span> 
    
<span data-ttu-id="9e1ff-p139">导出数据后, 搜索结果和导出报告位于与 DSR 事例同名的文件夹中。包含邮箱项目的 PST 文件位于名为**Exchange**的子文件夹中。网站中的文档和其他项目位于名为**SharePoint**的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p139">After the data is exported, the search results and export reports are located in a folder that has the same name as the DSR case. The PST files that contain mailbox items are located in a subfolder named **Exchange**. Documents and other items from sites are located in a subfolder named **SharePoint**.</span></span> 
  
## <a name="optional-step-5-revise-the-built-in-search-query"></a><span data-ttu-id="9e1ff-273">Optional步骤 5: 修订内置搜索查询</span><span class="sxs-lookup"><span data-stu-id="9e1ff-273">(Optional) Step 5: Revise the built-in search query</span></span>

<span data-ttu-id="9e1ff-p140">在运行内置搜索后, 可以对其进行修改以缩小范围以返回较少的搜索结果。您可以通过将条件添加到查询中来执行此操作。**and**运算符在逻辑上将一个条件连接到关键字查询。这意味着在搜索结果中返回, 项目必须同时满足关键字查询和添加的任何条件。这就是条件如何帮助缩小结果范围的方法。如果向搜索查询添加两个或更多个唯一条件 (指定不同属性的条件), 则这些条件通过**AND**运算符逻辑连接。这意味着只返回满足所有条件 (除了关键字查询) 的项目。如果将多个值 (用逗号或分号分隔) 添加到单个条件中, 则这些值由**or**运算符连接。这意味着, 如果在条件中包含任何指定的属性值, 则将返回项目。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p140">After you run the built-in search, you can revise it to narrow the scope to return fewer search results. You can do this by adding conditions to the query. A condition is logically connected to the keyword query by the **AND** operator. That means to be returned in the search results, items must satisfy both the keyword query and any conditions you add. This is how conditions help to narrow the results. If you add two or more unique conditions to a search query (conditions that specify different properties), those conditions are logically connected by the **AND** operator. That means only items that satisfy all the conditions (in addition to the keyword query) are returned. If you add multiple values (separated by commas or semi-colons) to a single condition, those values are connected by the **OR** operator. That means items are returned if they contain any of the specified values for the property in the condition.</span></span> 
  
<span data-ttu-id="9e1ff-p141">下面是可以添加到 DSR 机箱的内置搜索查询的一些条件示例。在搜索查询中使用的实际属性的名称显示在括号中。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p141">Here are some examples of the conditions that you can add to the built-in search query of a DSR case. The name of the actual property used in a search query is shown parentheses.</span></span>
  
- <span data-ttu-id="9e1ff-p142">**文件类型 ( `filetype`)** -指定文档或文件的扩展名。使用此条件可搜索由特定 Office 应用程序 (如 Word、Excel 和 OneNote) 创建的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p142">**File type ( `filetype`)** - Specifies the extension of a document or file. Use this condition to search for documents and files created by specific Office applications, such as Word, Excel, and OneNote.</span></span> 
    
- <span data-ttu-id="9e1ff-p143">**Message type ( `kind`)** -指定要搜索的电子邮件项目的类型。例如, 可以使用语法`kind:email OR kind:im`仅返回 Microsoft 团队中的电子邮件和 Skype for business 对话或一对一聊天。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p143">**Message type ( `kind`)** - Specifies the type of email item to search for. For example, you can use the syntax  `kind:email OR kind:im` to return only email messages and Skype for Business conversations or one-to-one chats in Microsoft Teams.</span></span> 
    
- <span data-ttu-id="9e1ff-p144">**合规性标记`compliancetag`()** -指定分配给电子邮件或文档的标签。此条件将返回使用特定标签分类的项目。标签用于根据标签定义的分类对电子邮件和文档进行分类, 并强制执行保留规则。这是用于 DSR 调查的有用条件, 因为您的组织可能会使用标签对与数据隐私相关的内容或包含个人数据或敏感信息的内容进行分类。对于此条件的值, 请使用完整的标签名称或标签名称的第一部分和通配符。有关详细信息, 请参阅[Office 365 中的标签概述](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p144">**Compliance tag (`compliancetag`)** - Specifies a label assigned to an email message or a document. This condition will return items that are classified with a specific label. Labels are used to classify email and documents for data governance and enforce retention rules based on the classification defined by the label. This is a useful condition for DSR investigations because your organization may be using labels to classify content related to data privacy or that contains personal data or sensitive information. For the value of this condition, use the complete label name or the first part of the label name with a wildcard. For more information, see [Overview of labels in Office 365](labels.md).</span></span>
    
<span data-ttu-id="9e1ff-295">有关在 DSR 机箱工具中可用的所有条件的列表和说明, 请参阅 "内容搜索的关键字查询和搜索条件" 一文中的 "[搜索条件](keyword-queries-and-search-conditions.md#search-conditions)" 一文。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-295">For a list and description of all the conditions available in the DSR case tool, see [Search conditions](keyword-queries-and-search-conditions.md#search-conditions) in the "Keyword queries and search conditions for Content Search" article.</span></span> 
  
### <a name="changing-the-content-locations-that-are-searched"></a><span data-ttu-id="9e1ff-296">更改搜索的内容位置</span><span class="sxs-lookup"><span data-stu-id="9e1ff-296">Changing the content locations that are searched</span></span>

<span data-ttu-id="9e1ff-p145">除了修改 DSR 机箱的内置搜索之外, 您还可以更改搜索的内容位置。如前所述, 内置搜索将搜索组织中的每个邮箱和网站, 以及任何 Exchange Online 公用文件夹。例如, 您可以缩小搜索范围, 仅搜索数据主体的邮箱和 OneDrive 帐户以及选定的 SharePoint 网站。如果选择搜索特定网站, 则必须添加要搜索的每个网站。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p145">In addition to revising the built-in search for a DSR case, you can also change the content locations that are searched. As previously explained, the built-in search searches every mailbox and site in the organization, and any Exchange Online public folders. For example, you could narrow the search to only search the data subject's mailbox and OneDrive account and selected SharePoint sites. If you choose to search specific sites, you'll have to add each site that you want to search.</span></span>
  
<span data-ttu-id="9e1ff-301">若要修改要搜索的内容位置, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-301">To modify the content locations to search:</span></span>
  
1. <span data-ttu-id="9e1ff-302">打开要更改其内容位置的内置搜索。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-302">Open the built-in search that you want to change the content locations for.</span></span>
    
2. <span data-ttu-id="9e1ff-303">在搜索查询中的 "**位置**" 下, 单击 "**特定位置**" 选项旁边的 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-303">In the search query, under **Locations**, click **Modify** next to the **Specific locations** option.</span></span> 
    
    ![单击 "修改" 以更改内置搜索查询的内容位置](media/d66f7ba7-b71f-4ff5-a030-460ff02e3123.png)
  
    <span data-ttu-id="9e1ff-p146">将显示 "**修改位置**" 浮出控件页。以下是对内置搜索中的内容位置的说明, 以及有关修改搜索位置的一些信息。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p146">The **Modify locations** flyout page is displayed. Here's a description of the content locations in the built-in search and some information about modifying the locations that are searched.</span></span> 
    
    !["修改位置" 飞出页面](media/56c033f6-6735-46ba-abb2-a263a2b79836.png)
  
    <span data-ttu-id="9e1ff-p147">一. 选择了浮出页面顶部的 "在邮箱中**选择所有**内容" 部分下的切换, 这表明已搜索所有邮箱。若要缩小搜索范围, 请单击 "切换" 以取消选择, 然后单击 "**选择用户、组或团队**", 然后选择要搜索的特定邮箱。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p147">a. The toggle under **Select all** in mailbox section at the top of the flyout page is selected, which indicates that all mailboxes are searched. To narrow the scope of the search, click the toggle to unselect it, and then click **Choose users, groups, or teams** and choose specific mailboxes to search.</span></span>
    
    <span data-ttu-id="9e1ff-p148">b. 在弹出页面中间的 "**选择所有**位置" 部分下的切换处于选中状态, 这表示搜索所有网站。若要将搜索范围缩小到选定网站, 请取消选择该开关, 然后单击 "**选择网站**"。您必须添加要搜索的每个特定网站, 包括数据主体的 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p148">b. The toggle under **Select all** in the sites section in the middle of the flyout page is selected, which indicates that all sites are searched. To narrow the search to selected sites, you would unselect the toggle and then click **Choose sites**. You'll have to add each specific site that you want to search, including the data subject's OneDrive account.</span></span>
    
    <span data-ttu-id="9e1ff-p149">c. 选择 "exchange 公用文件夹" 部分中的 "切换", 这意味着将搜索所有 Exchange 公用文件夹。请注意, 您只能搜索所有 Exchange 公用文件夹, 也可以不搜索任何。您不能选择要搜索的特定文件。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p149">c. The toggle in the Exchange public folders section is selected, which means all Exchange public folders are searched. Note that you can only search all Exchange public folders or none of them. You can't choose specific ones to search.</span></span>
    
3. <span data-ttu-id="9e1ff-319">如果要修改内置搜索中的内容位置, 请单击 "**保存&amp;运行**" 以重新启动搜索。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-319">If you modify the content locations in the built-in search, click **Save &amp; run** to re-start the search.</span></span> 
  
## <a name="more-information-about-using-the-dsr-case-tool"></a><span data-ttu-id="9e1ff-320">有关使用 DSR 机箱工具的详细信息</span><span class="sxs-lookup"><span data-stu-id="9e1ff-320">More information about using the DSR case tool</span></span>

<span data-ttu-id="9e1ff-321">以下各节包含有关使用 dsr 机箱工具响应 DSR 导出请求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-321">The following sections contain more information about using the DSR case tool to respond to DSR export requests.</span></span>
  
[<span data-ttu-id="9e1ff-322">从 MyAnalytics 和 Office 漫游服务导出数据</span><span class="sxs-lookup"><span data-stu-id="9e1ff-322">Exporting data from MyAnalytics and the Office Roaming Service</span></span>](#exporting-data-from-myanalytics-and-the-office-roaming-service)

[<span data-ttu-id="9e1ff-323">导出部分索引的项目</span><span class="sxs-lookup"><span data-stu-id="9e1ff-323">Exporting partially indexed items</span></span>](#exporting-partially-indexed-items)

[<span data-ttu-id="9e1ff-324">从 Microsoft 团队和 Office 365 组中搜索和导出数据</span><span class="sxs-lookup"><span data-stu-id="9e1ff-324">Searching and exporting data from Microsoft Teams and Office 365 Groups</span></span>](#searching-and-exporting-data-from-microsoft-teams-and-office-365-groups)

[<span data-ttu-id="9e1ff-325">搜索 Exchange 公用文件夹</span><span class="sxs-lookup"><span data-stu-id="9e1ff-325">Searching Exchange public folders</span></span>](#searching-exchange-public-folders)
  
### <a name="exporting-data-from-myanalytics-and-the-office-roaming-service"></a><span data-ttu-id="9e1ff-326">从 MyAnalytics 和 Office 漫游服务导出数据</span><span class="sxs-lookup"><span data-stu-id="9e1ff-326">Exporting data from MyAnalytics and the Office Roaming Service</span></span>

<span data-ttu-id="9e1ff-p150">您可以使用 DSR case 工具搜索和导出由 MyAnalytics 和 Office 漫游服务生成的使用率数据。以下是这些服务的用途说明:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p150">You can use the DSR case tool to search for and export usage data that's generated by MyAnalytics and the Office Roaming Service. Here's a description of what these services do:</span></span>
  
- <span data-ttu-id="9e1ff-p151">**MyAnalytics** -为用户提供有关如何根据邮箱中的邮件和日历数据花费时间的见解。所有 MyAnalytics 见解均源自用户邮箱中的电子邮件和会议标头。分配了 MyAnalytics 许可证的用户可以登录到 Office 365, 并转到 MyAnalytics 仪表板, 以查看有关他们花费时间的见解。(用户可以看到这些见解的屏幕截图以响应 DSR 访问请求)。DSR 机箱中的内置搜索将导出用于生成 MyAnalytics insights 的数据。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p151">**MyAnalytics** - Provides users with insights about how they spend their time based on the mail and calendar data in their mailbox. All MyAnalytics insights are derived from email and meeting headers in the user's mailbox. Users that are assigned a MyAnalytics license can sign in to Office 365 and go to the MyAnalytics dashboard to view the insights about how they spend their time. (Users can screen shots of these insights in response to a DSR access request). The built-in search in a DSR case will export the data that's used to generate MyAnalytics insights.</span></span> 
    
- <span data-ttu-id="9e1ff-334">**Office 漫游服务**-漫游是一项服务, 它存储与 office 相关的设置, 如 office 主题、自定义词典、语言设置、开发人员模式和自动更正。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-334">**Office Roaming Service** - Roaming is a service that stores Office-related settings, such as Office theme, custom dictionary, language settings, developer mode, and auto correct.</span></span> 
    
<span data-ttu-id="9e1ff-p152">来自 MyAnalytics 和 Office 漫游服务的数据存储在 Exchange Online 邮箱的非人际邮件 (非 IPM) 子树中的隐藏文件夹中的数据主题邮箱中。这意味着, 当用户使用 Outlook 或其他邮件客户端访问其邮箱时, 数据将隐藏在用户的视图中。有关隐藏文件夹的详细信息, 请参阅[MAPI 隐藏文件夹](https://go.microsoft.com/fwlink/?linkid=872758)。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p152">The data from MyAnalytics and the Office Roaming service is stored in a data subject's mailbox in hidden folders located in a non-interpersonal message (non-IPM) subtree of Exchange Online mailboxes. This means the data is hidden from the user's view when they use Outlook or other mail clients to access their mailbox. For more information about hidden folders, see [MAPI Hidden Folders](https://go.microsoft.com/fwlink/?linkid=872758).</span></span>
  
<span data-ttu-id="9e1ff-p153">您可以创建一个单独的内容搜索 (并将其与一个 DSR 事例相关联), 以返回数据的主题邮箱中的 MyAnalytics 和 Office 漫游服务使用情况数据。此数据不包含在搜索统计中, 并且不能预览。不过, 你可以将其导出, 然后将其提供给针对 DSR 导出请求的数据主体。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p153">You can create a separate content search (and associate it with a DSR case) that returns the MyAnalytics and the Office Roaming Service usage data in the data's subjects mailbox. This data isn't included in the search statistics and it won't be available for preview. But you can export it and then give it to the data subject in response to a DSR export request.</span></span>
  
<span data-ttu-id="9e1ff-p154">从 MyAnalytics 和 Office 漫游服务导出数据时, 会将数据保存到位于**ApplicationDataRoot**文件夹中的每个应用程序的单独文件夹中, 该文件夹位于名称中包含数据主题电子邮件地址的文件夹下。此数据导出为 JSON 文件, 这些文件是与 XML 或 TXT 文件类似的可读文本文件, 这些文件附加到电子邮件。目前, 这些文件夹使用分配给 MyAnalytics 和 Office 漫游服务的全局唯一标识符 (GUID) 进行命名, 下表中列出了这些文件夹。在未来版本的 DSR 机箱工具中, GUID 将替换为实际应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p154">When you export data from MyAnalytics and the Office Roaming Service, the data is saved to a separate folder for each application that's located in the **ApplicationDataRoot** folder, which is under a folder that is name with the data subject's email address. This data is exported as JSON files, which are human-readable text files similar to XML or TXT files, that are attached to email messages. Currently, these folders are named with a globally unique identifier (GUID) that's assigned to MyAnalytics and the Office Roaming Service, which are listed in the following table. In future versions of the DSR case tool, the GUID will be replaced with the name of the actual application.</span></span> 
  
|<span data-ttu-id="9e1ff-345">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="9e1ff-345">**Application**</span></span>|<span data-ttu-id="9e1ff-346">**GUID/文件夹名称**</span><span class="sxs-lookup"><span data-stu-id="9e1ff-346">**GUID/folder name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e1ff-347">MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="9e1ff-347">MyAnalytics</span></span>  <br/> |<span data-ttu-id="9e1ff-348">3c896ded-22c5-450f-91f6-3d1ef0848f6e</span><span class="sxs-lookup"><span data-stu-id="9e1ff-348">3c896ded-22c5-450f-91f6-3d1ef0848f6e</span></span>  <br/> |
|<span data-ttu-id="9e1ff-349">Office 漫游服务</span><span class="sxs-lookup"><span data-stu-id="9e1ff-349">Office Roaming Service</span></span>  <br/> |<span data-ttu-id="9e1ff-350">1caee58f-eb14-4a6b-9339-1fe2ddf6692b</span><span class="sxs-lookup"><span data-stu-id="9e1ff-350">1caee58f-eb14-4a6b-9339-1fe2ddf6692b</span></span>  <br/> |
   
 <span data-ttu-id="9e1ff-351">**若要搜索和导出 MyAnalytics 和 Office 漫游服务数据, 请执行以下操作:**</span><span class="sxs-lookup"><span data-stu-id="9e1ff-351">**To search for and export MyAnalytics and Office Roaming Service data:**</span></span>
  
1. <span data-ttu-id="9e1ff-352">在 "安全&amp;合规性中心" 中, 单击 "**数据隐私** \> **数据主体请求**", 然后单击要为其导出使用率数据的数据主体在 DSR 事例旁边的 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-352">In the Security &amp; Compliance Center, click **Data privacy** \> **Data subject requests**, and then click **Open** next to the DSR case for the data subject that you want to export usage data for.</span></span> 
    
2. <span data-ttu-id="9e1ff-353">单击页面顶部的 "**搜索**" 选项卡, 然后单击!["添加图标](media/ITPro-EAC-AddIcon.gif) " "**导向搜索**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-353">Click the **Search** tab at the top of the page, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Guided search**.</span></span>
    
3. <span data-ttu-id="9e1ff-354">在 "**命名您的搜索**" 页上, 单击 "**取消**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-354">Click **Cancel** on the **Name your search** page.</span></span> 
    
4. <span data-ttu-id="9e1ff-355">在 "**搜索查询**" 下的 "**类型**" 条件中, 选中 " **MyAnalytics**和**Office 漫游服务**" 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-355">Under **Search query**, in the **Type** condition, select the check boxes next to **MyAnalytics** and **Office Roaming Service**.</span></span> 
    
    ![选择 "MyAnalytics" 和 "Office 漫游服务" 复选框以导出使用率数据](media/3dacbc7a-c314-492c-828c-6757fda84963.png)
  
    <span data-ttu-id="9e1ff-p155">请注意,**类型**条件 (是电子邮件类) 应为搜索查询中的唯一项。您可以删除 "**关键字**" 框或将其保留为空。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p155">Note that the **Type** condition (which are email message classes) should be the only item in the search query. You can delete the **Keywords** box or leave it blank.</span></span> 
    
5. <span data-ttu-id="9e1ff-359">在 "**位置**" 下, 确保选择了 "**特定位置**", 然后单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-359">Under **Locations**, make sure **Specific locations** is selected and then click **Modify**.</span></span>
    
6. <span data-ttu-id="9e1ff-360">在 "**修改位置**" 浮出页面 ("邮箱" 部分) 的顶部, 单击 "**选择用户、组或团队**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-360">On top part of the **Modify locations** flyout page (the mailbox section), click **Choose users, groups, or teams**.</span></span>
    
7. <span data-ttu-id="9e1ff-361">在 "**编辑位置**" 页上, 单击 "**选择用户、组或团队**", 选择数据主题的邮箱, 然后保存您的选择。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-361">On the **Edit locations** page, click **Choose users, groups, or teams**, choose the data subject's mailbox, and then save your selection.</span></span> 
    
8. <span data-ttu-id="9e1ff-362">单击 **" &amp;保存运行**", 然后命名搜索并保存它。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-362">Click **Save &amp; run**, and then name the search and save it.</span></span>
    
    <span data-ttu-id="9e1ff-363">启动搜索。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-363">The search is started.</span></span>
    
 <span data-ttu-id="9e1ff-364">**若要导出 MyAnalytics 和 Office 漫游服务数据, 请执行以下操作:**</span><span class="sxs-lookup"><span data-stu-id="9e1ff-364">**To export MyAnalytics and Office Roaming Service data:**</span></span>
  
1. <span data-ttu-id="9e1ff-p156">在上一步中创建的搜索完成后, 单击页面顶部的 "**搜索**" 选项卡, 然后单击 "搜索" 旁边的复选框。您可能需要单击 " ![刷新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) **刷新**" 以显示搜索。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p156">When the search that you created in the previous step is complete, click the **Search** tab at the top of the page, and then click the checkbox next to the search. You may have to click ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) **Refresh** to display the search.</span></span> 
    
2. <span data-ttu-id="9e1ff-367">在 "搜索" 飞出页面![上, 单击 "](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **更多**" "导出搜索结果" 图标, 然后从下拉列表中选择 "**导出结果**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-367">On the search flyout page, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then select **Export results** from the drop-down list.</span></span> 
    
3. <span data-ttu-id="9e1ff-368">在 "**导出结果**" 页上, 选择这些推荐选项以导出使用率数据。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-368">On the **Export results** page, select the these recommended options to export usage data.</span></span> 
    
    ![导出 MyAnalytics 和 Office 漫游服务使用情况数据时的导出选项](media/470a7d1e-eeae-4b42-95aa-15cb82ce2f68.png)
  
    <span data-ttu-id="9e1ff-p157">在 "**输出选项**" 下, 选择第一个选项 (**所有项目 (不包括具有无法识别的格式的项目) 进行加密, 或未针对其他原因对其编制索引,** 以仅导出已编制索引的项目。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p157">a. Under **Output options**, select the first option ( **All items, excluding ones that have ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons**) to export indexed items only.</span></span>
    
    <span data-ttu-id="9e1ff-p158">b. 在 "将**Exchange 内容导出为**" 下, 选择第二个选项 (**包含所有邮件的一个 PST 文件**)。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p158">b. Under **Export Exchange content as**, select the second option, **One PST file containing all messages**.</span></span>
    
    <span data-ttu-id="9e1ff-p159">c. 将其余的导出选项保留为未选中状态。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p159">c. Leave the remaining export options unselected.</span></span>
    
4. <span data-ttu-id="9e1ff-376">选择导出设置后, 单击 "**导出**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-376">After you choose the export settings, click **Export**.</span></span>
    
    <span data-ttu-id="9e1ff-p160">搜索结果已准备好下载, 这意味着它们将被上载到 Microsoft 云中的组织的 Azure 存储区域。接下来的步骤演示了如何将此数据下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p160">The search results are prepared for downloading, which means they're uploaded to the Azure storage area for your organization in the Microsoft cloud. The next steps show you how to download this data to your local computer.</span></span>
    
5. <span data-ttu-id="9e1ff-p161">单击 "**导出**" 选项卡以显示刚创建的导出作业。请注意, 导出作业与对应的搜索具有相同的名称, 并在搜索名称的末尾追加 **_Export** 。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p161">Click the **Export** tab to display the export job you just created. Note that export jobs have the same name as the corresponding search with **_Export** appended to the end of search name.</span></span> 
    
6. <span data-ttu-id="9e1ff-381">单击刚创建的导出作业以显示 "导出" 弹出页面。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-381">Click the export job that you just created to display the export flyout page.</span></span> 
    
7. <span data-ttu-id="9e1ff-p162">在 "**导出密钥**" 下, 单击 "**复制到剪贴板**"。您将在步骤10中使用此键下载搜索结果。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p162">Under **Export key**, click **Copy to clipboard**. You will use this key in step 10 to download the search results.</span></span>
    
8. <span data-ttu-id="9e1ff-384">单击!["导出弹出页面](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) " 顶部的 "导出搜索结果图标**下载结果**"。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-384">Click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Download results** at the top of the export flyout page.</span></span> 
    
9. <span data-ttu-id="9e1ff-p163">在页面底部的弹出窗口中, 单击 "**打开**" 以打开**Microsoft Office 365 电子数据展示导出工具**。首次下载搜索结果时, 将会安装**电子数据展示导出工具**。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p163">In the pop-up window at the bottom of the page, click **Open** to open the **Microsoft Office 365 eDiscovery Export Tool**. The **eDiscovery Export Tool** will be installed the first time you download search results.</span></span> 
    
10. <span data-ttu-id="9e1ff-387">在“**电子数据展示导出工具**”中，将在步骤 7 中复制的导出密钥粘贴在相应的框中。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-387">In the **eDiscovery Export Tool**, paste the export key that you copied in step 7 in the appropriate box.</span></span>
    
11. <span data-ttu-id="9e1ff-388">单击“**浏览**”指定要下载搜索结果文件的位置。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-388">Click **Browse** to specify the location where you want to download the search result files.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9e1ff-389">由于磁盘活动量过高 (读取和写入), 因此应将搜索结果下载到本地磁盘驱动器;不要将其下载到映射的网络驱动器或其他网络位置。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-389">Due to the high amount of disk activity (reads and writes), you should download search results to a local disk drive; don't download them to a mapped network drive or other network location.</span></span> 
  
12. <span data-ttu-id="9e1ff-390">单击“**开始**”将搜索结果下载到计算机。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-390">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="9e1ff-p164">**电子数据展示导出工具**显示有关导出过程的状态信息, 包括要下载的剩余项目的数字 (和大小) 的估计值。导出过程完成后, 可以在 Outlook 中打开 Exchange PST 文件, 然后转到**ApplicationDataRoot**文件夹以访问子文件夹, 以访问 MyAnalytics 和漫游服务。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p164">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can open the Exchange PST file in Outlook and then go to the **ApplicationDataRoot** folder to access the subfolders to MyAnalytics and Roaming service.</span></span> 
    
    <span data-ttu-id="9e1ff-p165">如前所述, 包含使用情况数据的 JSON 文件附加到邮件中。若要查看 JSON 文件, 请单击一条消息, 然后打开附加的 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p165">As previously explained, the JSON files that contains usage data are attached to messages. To view a JSON file, click a message and then open the attached JSON file.</span></span> 
  
### <a name="exporting-partially-indexed-items"></a><span data-ttu-id="9e1ff-395">导出部分索引的项目</span><span class="sxs-lookup"><span data-stu-id="9e1ff-395">Exporting partially indexed items</span></span>

<span data-ttu-id="9e1ff-p166">我们建议您不要从创建新的 DSR 事例时创建的内置搜索中导出部分索引项目 (也称为非索引项目)。这是因为搜索结果可能会包含组织中其他用户的部分索引项目, 而不是数据主体的部分索引项目。相反, 我们建议您创建一个单独的内容搜索, 该搜索与用于仅导出与数据主体相关的部分已编制索引的项目的 DSR 事例相关联。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p166">We recommend that you don't export partially indexed items (also called unindexed items) from the built-in search that's created when you create a new DSR case. That's because the search results will more than likely include partially indexed items for other users in your organization, and not just partially indexed items for the data subject). Instead, we recommend that you create a separate Content Search that's associated with the DSR case that's designed to export only the partially indexed items related to the data subject.</span></span> 
  
<span data-ttu-id="9e1ff-p167">以下是导出部分索引项目的高级别过程。导出后, 您可以查看它们以确定项目是否响应 DSR 访问或导出请求。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p167">Here's a high-level process to export partially indexed items. After they're export, you can review them to determine if an items is responsive to a DSR access or export request.</span></span>
  
1. <span data-ttu-id="9e1ff-401">打开 DSR 事例并在 "**搜索**" 页上创建新的搜索。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-401">Open the DSR case and create a new search on the **Search** page.</span></span> 
    
2. <span data-ttu-id="9e1ff-402">使用以下条件配置搜索查询和要搜索的内容位置:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-402">Use the following criteria for configuring the search query and the content locations to search:</span></span>
    
    - <span data-ttu-id="9e1ff-p168">使用空/空白的关键字查询。这将返回搜索的内容位置中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p168">Use an empty/blank keyword query. This will return all items in the content locations that are searched.</span></span>
    
    - <span data-ttu-id="9e1ff-405">仅搜索数据主体的 Exchange Online 邮箱及其 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-405">Search only the data subject's Exchange Online mailbox and their OneDrive account.</span></span>
    
3. <span data-ttu-id="9e1ff-p169">在运行搜索并完成搜索后, 您可以导出和下载搜索结果 (如[步骤 4](#step-4-export-the-data)中所述)。使用以下设置导出部分索引项目。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p169">After you run the search and it completes, you can export and download the search results (as described in [Step 4](#step-4-export-the-data)). Use the following settings to export partially indexed items.</span></span> 
    
    - <span data-ttu-id="9e1ff-408">在 "**输出选项**" 下, 选择第三个选项 (**仅限无法识别的格式、已加密或未按其他原因为其编制索引的项目**) 仅导出部分索引项目。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-408">Under **Output options**, select the third option ( **Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**) to export partially indexed items only.</span></span>
    
    - <span data-ttu-id="9e1ff-409">在 "将**Exchange 内容导出为**" 下, 可以根据自己的偏好选择任何选项。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-409">Under **Export Exchange content as**, you can select any option based on your preferences.</span></span> 
    
    - <span data-ttu-id="9e1ff-410">如果对版本进行了部分索引, 则选择 "**包括 SharePoint 文档的版本**" 选项将导出文档的版本。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-410">Selecting the **Include versions for SharePoint documents** option will export versions of documents if a version is partially indexed.</span></span> 
    
<span data-ttu-id="9e1ff-411">有关部分索引项目的详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-411">For more information about partially indexed items, see:</span></span> 
  
- [<span data-ttu-id="9e1ff-412">处理 Office 365 内容搜索中的部分索引项</span><span class="sxs-lookup"><span data-stu-id="9e1ff-412">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="9e1ff-413">导出部分索引的项目</span><span class="sxs-lookup"><span data-stu-id="9e1ff-413">Exporting partially indexed items</span></span>](export-search-results.md#exporting-partially-indexed-items)
    
### <a name="searching-and-exporting-data-from-microsoft-teams-and-office-365-groups"></a><span data-ttu-id="9e1ff-414">从 Microsoft 团队和 Office 365 组中搜索和导出数据</span><span class="sxs-lookup"><span data-stu-id="9e1ff-414">Searching and exporting data from Microsoft Teams and Office 365 Groups</span></span>

<span data-ttu-id="9e1ff-p170">Microsoft 团队 (称为团队聊天或一对一聊天) 中的聊天列表的一部分的对话存储在参与聊天的用户的 Exchange Online 邮箱中。此外, 在一对一聊天中共享的文件存储在共享该文件的人员的 OneDrive 帐户中。由于内置搜索可搜索组织中的所有邮箱和 OneDrive 帐户, 因此在聊天会话中共享的团队聊天室和文档 (创建或上载的数据主题) 将由 DSR 机箱中的内置搜索返回。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p170">Conversations that are part of the Chat list in Microsoft Teams (called Team chats or one-to-one chats) are stored in the Exchange Online mailbox of the users who participate in the chats. Also, the files a person shares in a one-to-one chat are stored in the OneDrive account of the person who shares the file. Because the built-in search searches all mailboxes and OneDrive accounts in the organization, team chats and documents shared in a chat session (that the data subject created or uploaded) will be returned by built-in search in a DSR case.</span></span>
  
<span data-ttu-id="9e1ff-p171">或者, 作为团队频道一部分的对话 (也称为频道消息) 存储在与团队相关联的邮箱中。由于搜索与 Microsoft 团队关联的所有邮箱, 因此内置搜索也会返回这些数据主题所参与的这些类型的对话。此外, 在团队频道中可能共享的数据主体图块存储在团队的 SharePoint 网站上。创建或 uploadedby 的文件将由内置搜索在 DSR 事例中返回, 因为与 Microsoft 团队关联的网站包含在搜索中。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p171">Alternatively, conversations that are part of a Teams channel (also called channel messages) are stored in the mailbox that's associated with a team. These types of conversations that the data subject participated in are also returned by the built-in search because all mailboxes associated with Microsoft Teams are searched. Additionally, tiles that a data subject might have shared in a Teams channel are stored on the team's SharePoint site. Files created or uploadedby the data subject will be returned by the built-in search in a DSR case because sites associated with Microsoft Teams are included in the search.</span></span>
  
<span data-ttu-id="9e1ff-p172">同样, 与 Office 365 组对应的邮箱和 SharePoint 网站也包含在内置搜索中。这意味着将返回由数据主体创建或上载的文件发送或接收的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p172">Similarly, mailboxes and SharePoint sites that correspond to an Office 365 Group are also included in the built-in search. This means that email messages that where sent or received by the data subject and files created or uploaded by the data subject will be returned.</span></span> 
  
<span data-ttu-id="9e1ff-424">有关使用内容搜索在 Microsoft 团队和 Office 365 组中搜索项目的详细信息, 或者若要了解如何获取成员的列表, 请参阅[Office 365 中的内容搜索](content-search.md#searching-microsoft-teams-and-office-365-groups)中的 "搜索 Microsoft 团队和 Office 365 组" 一节。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-424">For more information about using Content Search to search for items in Microsoft Teams and Office 365 Groups or to see how to get a list of a members, see the "Searching Microsoft Teams and Office 365 Groups" section in [Content Search in Office 365](content-search.md#searching-microsoft-teams-and-office-365-groups).</span></span> 
  
### <a name="searching-exchange-public-folders"></a><span data-ttu-id="9e1ff-425">搜索 Exchange 公用文件夹</span><span class="sxs-lookup"><span data-stu-id="9e1ff-425">Searching Exchange public folders</span></span>

<span data-ttu-id="9e1ff-p173">在 DSR 事例中, 内置搜索将仅返回发送到已启用邮件的公用文件夹的电子邮件或其他人发送到公用文件夹的邮件, 同时还会复制数据主题。它不会返回数据主体可能已投递到公用文件夹的消息。若要搜索数据主体投递到公用文件夹的项目, 您可以创建单独的 "创建单独的内容搜索", 以搜索数据主题投递到公用文件夹中的任何项目。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p173">The built-in search in a DSR case will only return email messages that the data subject sent to a mail-enabled public folder or messages that someone else sent to a public folder and also copied the data subject . It will not return message that the data subject might have posted to a public folder. To search for items that the data subject posted to a public folder, you can create a separate create a separate Content Search that searches for any item posted to a public folder by the data subject.</span></span>
  
<span data-ttu-id="9e1ff-429">下面是一个高级过程, 用于搜索数据主体可能已投递到公用文件夹的项目。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-429">Here's a high-level process to search for items that the data subject might have posted to a public folder.</span></span> 
  
1. <span data-ttu-id="9e1ff-430">打开 DSR 事例并在 "**搜索**" 页上创建新的搜索。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-430">Open the DSR case and create a new search on the **Search** page.</span></span> 
    
2. <span data-ttu-id="9e1ff-431">使用以下条件配置搜索查询和要搜索的内容位置:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-431">Use the following criteria for configuring the search query and the content locations to search:</span></span>
    
  - <span data-ttu-id="9e1ff-432">在 "**关键字**" 框中, 使用以下搜索查询:</span><span class="sxs-lookup"><span data-stu-id="9e1ff-432">In the **Keywords** box, use the following search query:</span></span> 
    
    ```
    itemclass:ipm.post AND "<email address of the data subject>"
    ```

  - <span data-ttu-id="9e1ff-433">搜索所有 Exchange 公用文件夹</span><span class="sxs-lookup"><span data-stu-id="9e1ff-433">Search all Exchange public folders</span></span>
    
  - <span data-ttu-id="9e1ff-p174">在运行搜索并完成搜索后, 您可以导出和下载搜索结果 (如[步骤 4](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#step4)中所述)。使用以下设置导出部分索引项目。</span><span class="sxs-lookup"><span data-stu-id="9e1ff-p174">After you run the search and it completes, you can export and download the search results (as described in [Step 4](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#step4)). Use the following settings to export partially indexed items.</span></span> 

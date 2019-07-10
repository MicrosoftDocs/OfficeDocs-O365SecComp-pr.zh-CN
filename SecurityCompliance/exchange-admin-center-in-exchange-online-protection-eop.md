---
title: 'Exchange Online Protection 中的 Exchange 管理中心 '
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Exchange 管理中心 (EAC) 是基于 Web 的 Microsoft Exchange Online Protection (EOP) 的管理控制台。
ms.openlocfilehash: 9d32e6bfc9137a04d92c3916894e2070313607a8
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599508"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="1aa5e-103">Exchange Online Protection 中的 Exchange 管理中心</span><span class="sxs-lookup"><span data-stu-id="1aa5e-103">Exchange admin center in Exchange Online Protection</span></span> 

<span data-ttu-id="1aa5e-104">Exchange 管理中心 (EAC) 是基于 Web 的 Microsoft Exchange Online Protection (EOP) 的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span> 
  
<span data-ttu-id="1aa5e-p101">正在查找此主题的 Exchange 2013 版本？请参阅 [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-p101">Looking for the Exchange 2013 version of this topic? See [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span></span>
  
<span data-ttu-id="1aa5e-p102">正在查找此主题的 Exchange Online 版本？请参阅 [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-p102">Looking for the Exchange Online version of this topic? See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>
  
## <a name="accessing-the-eac"></a><span data-ttu-id="1aa5e-109">访问 EAC</span><span class="sxs-lookup"><span data-stu-id="1aa5e-109">Accessing the EAC</span></span>

<span data-ttu-id="1aa5e-110">在大多数情况下, EOP 客户将通过 Microsoft 365 管理中心访问 EAC。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-110">In most cases, EOP customers will access the EAC through the Microsoft 365 admin center.</span></span> <span data-ttu-id="1aa5e-111">可以在“**自有**”磁贴旁的“**管理**”磁贴中的下拉菜单中找到指向 EOP 的链接。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-111">You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile.</span></span> <span data-ttu-id="1aa5e-112">单击“**管理**”磁贴，从下拉菜单中选择“**Exchange Online Protection**”以进入 EAC。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-112">Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span> 
  
<span data-ttu-id="1aa5e-p104">您也可以通过以下 URL 直接访问 EAC 登录页面：https://admin.protection.outlook.com/ecp/\<companydomain\>。例如 https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com。指定用户凭据后，您将直接进入 EAC。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-p104">You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.</span></span>
  
## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="1aa5e-116">EAC 中常用的用户界面元素</span><span class="sxs-lookup"><span data-stu-id="1aa5e-116">Common user interface elements in the EAC</span></span>

<span data-ttu-id="1aa5e-117">本部分将介绍 EAC 中的用户界面元素。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-117">This section describes the user interface elements that are found in the EAC.</span></span>
  
![EOP-AdminCenter](media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a><span data-ttu-id="1aa5e-119">功能窗格</span><span class="sxs-lookup"><span data-stu-id="1aa5e-119">Feature Pane</span></span>

<span data-ttu-id="1aa5e-p105">这是您要在 EAC 中执行的大部分任务的第一级导航。功能窗格按功能区域组织。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>
  
1. <span data-ttu-id="1aa5e-122">**收件人**你可以在此处查看内部用户和外部联系人。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-122">**Recipients** This is where you'll view internal users and external contacts.</span></span> 
    
2. <span data-ttu-id="1aa5e-123">**权限**这将管理管理员角色。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-123">**Permissions** This where you'll manage administrator roles.</span></span> 
    
3. <span data-ttu-id="1aa5e-124">**合规性管理**你可以在此处找到审核日志和报告, 如管理员角色组报告。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-124">**Compliance Management** This is where you'll find audit logs and reports, such as the administrator role group report.</span></span> 
    
4. <span data-ttu-id="1aa5e-125">**保护**你可以在此处管理组织的反恶意软件和反垃圾邮件保护, 以及管理隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-125">**Protection** This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span> 
    
5. <span data-ttu-id="1aa5e-126">**邮件流**你可以在此处管理规则、接受域和连接器, 以及你将在其中执行邮件跟踪的位置。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-126">**Mail Flow** This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span> 
    
### <a name="tabs"></a><span data-ttu-id="1aa5e-127">选项卡</span><span class="sxs-lookup"><span data-stu-id="1aa5e-127">Tabs</span></span>

<span data-ttu-id="1aa5e-p106">选项卡是导航的第二级。每个功能区都包含各种选项卡，每种选项卡代表一项功能。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-p106">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>
  
### <a name="toolbar"></a><span data-ttu-id="1aa5e-130">工具栏</span><span class="sxs-lookup"><span data-stu-id="1aa5e-130">Toolbar</span></span>

<span data-ttu-id="1aa5e-p107">单击大多数选项卡时，将看到一个工具栏。工具栏包含执行特定操作的图标。下表介绍图标及其操作。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>
  
|<span data-ttu-id="1aa5e-134">**图标**</span><span class="sxs-lookup"><span data-stu-id="1aa5e-134">**Icon**</span></span>|<span data-ttu-id="1aa5e-135">**名称**</span><span class="sxs-lookup"><span data-stu-id="1aa5e-135">**Name**</span></span>|<span data-ttu-id="1aa5e-136">**Action**</span><span class="sxs-lookup"><span data-stu-id="1aa5e-136">**Action**</span></span>|
|:-----|:-----|:-----|
|![添加图标](media/ITPro-EAC-AddIcon.gif)           <br/> |<span data-ttu-id="1aa5e-138">添加、新建</span><span class="sxs-lookup"><span data-stu-id="1aa5e-138">Add, New</span></span>  <br/> |<span data-ttu-id="1aa5e-p108">使用此图标可创建一个新对象。其中一些图标有关联的向下箭头，单击该箭头会显示可以创建的其他对象。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>  <br/> |
|![编辑图标](media/ITPro-EAC-EditIcon.gif)           <br/> |<span data-ttu-id="1aa5e-142">编辑</span><span class="sxs-lookup"><span data-stu-id="1aa5e-142">Edit</span></span>  <br/> |<span data-ttu-id="1aa5e-143">使用此图标可编辑对象。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-143">Use this icon to edit an object.</span></span>  <br/> |
|![删除图标](media/ITPro-EAC-DeleteIcon.gif)           <br/> |<span data-ttu-id="1aa5e-145">删除</span><span class="sxs-lookup"><span data-stu-id="1aa5e-145">Delete</span></span>  <br/> |<span data-ttu-id="1aa5e-p109">使用此图标可删除对象。有些删除图标有一个向下箭头，单击该箭头可显示其他选项。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>  <br/> |
|![搜索图标](media/ITPro-EAC-.gif)           <br/> |<span data-ttu-id="1aa5e-149">搜索</span><span class="sxs-lookup"><span data-stu-id="1aa5e-149">Search</span></span>  <br/> |<span data-ttu-id="1aa5e-150">使用此图标可打开一个搜索框，可在其中键入要查找的对象的搜索短语。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-150">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>  <br/> |
|![刷新图标](media/ITPro-EAC-RefreshIcon.gif)           <br/> |<span data-ttu-id="1aa5e-152">刷新</span><span class="sxs-lookup"><span data-stu-id="1aa5e-152">Refresh</span></span>  <br/> |<span data-ttu-id="1aa5e-153">使用此图标可刷新列表视图。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-153">Use this icon to refresh the list view.</span></span>  <br/> |
|![更多选项图标](media/ITPro-EAC-MoreOptionsIcon.gif)           <br/> |<span data-ttu-id="1aa5e-155">更多选项</span><span class="sxs-lookup"><span data-stu-id="1aa5e-155">More options</span></span>  <br/> |<span data-ttu-id="1aa5e-156">使用此图标可以查看可对该选项卡的对象执行的更多操作。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-156">Use this icon to view more actions you can perform for that tab's objects.</span></span> <span data-ttu-id="1aa5e-157">例如, 在 "**收件人\> " 用户**单击此图标时, 将显示用于执行**高级搜索**的选项。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-157">For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>  <br/> |
|![向上键图标](media/ITPro-EAC-UpArrowIcon.gif)![向下键图标](media/ITPro-EAC-DownArrowIcon.gif)           <br/> |<span data-ttu-id="1aa5e-160">向上箭头和向下箭头</span><span class="sxs-lookup"><span data-stu-id="1aa5e-160">Up arrow and down arrow</span></span>  <br/> |<span data-ttu-id="1aa5e-161">使用这些图标可以将对象的优先级上移或下移。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-161">Use these icons to move an object's priority up or down.</span></span>  <br/> |
|![删除图标](media/ITPro-EAC-RemoveIcon.gif)           <br/> |<span data-ttu-id="1aa5e-163">删除</span><span class="sxs-lookup"><span data-stu-id="1aa5e-163">Remove</span></span>  <br/> |<span data-ttu-id="1aa5e-164">使用此图标可从列表中删除对象。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-164">Use this icon to remove objects from a list.</span></span>  <br/> |
   
### <a name="list-view"></a><span data-ttu-id="1aa5e-165">列表视图</span><span class="sxs-lookup"><span data-stu-id="1aa5e-165">List View</span></span>

<span data-ttu-id="1aa5e-p111">选择某个选项卡时，在大多数情况下，将会看到一个列表视图。EAC 列表视图的可查看限制大约为 10,000 个对象。此外还包括了分页功能，因此可以对结果进行分页。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-p111">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>
  
### <a name="details-pane"></a><span data-ttu-id="1aa5e-169">详细信息窗格</span><span class="sxs-lookup"><span data-stu-id="1aa5e-169">Details Pane</span></span>

<span data-ttu-id="1aa5e-p112">从列表视图中选择对象时，有关该对象的信息将在详细信息窗格中显示。在某些情况下，详细信息窗格包括管理任务。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>
  
### <a name="me-tile-and-help"></a><span data-ttu-id="1aa5e-172">自有图块和帮助</span><span class="sxs-lookup"><span data-stu-id="1aa5e-172">Me tile and Help</span></span>

<span data-ttu-id="1aa5e-173">使用“自有”\*\*\*\* 图块可以注销 EAC，然后以其他用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-173">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="1aa5e-174">从 "**帮助**![帮助"](media/ITPro-EAC-HelpIcon.gif)图标下拉菜单中, 可以执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="1aa5e-174">From the **Help**![Help Icon](media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span> 
  
1. <span data-ttu-id="1aa5e-175">**帮助** 单击 ![帮助图标](media/ITPro-EAC-HelpIcon.gif) 可查看联机帮助内容。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-175">**Help** Click ![Help Icon](media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span> 
    
2. <span data-ttu-id="1aa5e-176">**禁用帮助气泡**当您创建或编辑对象时, 帮助气泡会显示字段的上下文帮助。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-176">**Disable Help bubble** The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="1aa5e-177">您可以关闭"帮助"气泡，如果已被禁用，也可以打开它。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-177">You can turn off the Help bubble or turn it on if it has been disabled.</span></span> 
    
3. <span data-ttu-id="1aa5e-178">**版权**单击此链接可阅读适用于 Exchange Online Protection 的版权通知。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-178">**Copyright** Click this link to read the copyright notice for Exchange Online Protection.</span></span> 
    
4. <span data-ttu-id="1aa5e-179">**隐私**单击以阅读 Exchange Online Protection 的隐私策略。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-179">**Privacy** Click to read the privacy policy for Exchange Online Protection.</span></span> 
    
## <a name="supported-browsers"></a><span data-ttu-id="1aa5e-180">支持的浏览器</span><span class="sxs-lookup"><span data-stu-id="1aa5e-180">Supported Browsers</span></span>

<span data-ttu-id="1aa5e-p115">若要获得最佳的 EAC 使用体验，我们建议您始终使用最新的浏览器、Office 客户端和应用程序。我们还建议您安装可用的软件更新。有关服务支持的浏览器和系统要求的详细信息，请参阅 [Office 365 系统要求](https://go.microsoft.com/fwlink/p/?LinkID=402699)。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-p115">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps. We also recommend that you install software updates when they become available. For more information about the supported browsers and system requirements for the service, see [Office 365 System Requirements](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span></span> 
  
## <a name="supported-languages-in-eop"></a><span data-ttu-id="1aa5e-184">EOP 中支持的语言</span><span class="sxs-lookup"><span data-stu-id="1aa5e-184">Supported languages in EOP</span></span>

<span data-ttu-id="1aa5e-185">Exchange Online Protection 支持并提供以下语言。</span><span class="sxs-lookup"><span data-stu-id="1aa5e-185">The following languages are supported and available for Exchange Online Protection.</span></span>
  
- <span data-ttu-id="1aa5e-186">阿姆哈拉语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-186">Amharic</span></span>
    
- <span data-ttu-id="1aa5e-187">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-187">Arabic</span></span>
    
- <span data-ttu-id="1aa5e-188">巴斯克语（巴斯克）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-188">Basque (Basque)</span></span>
    
- <span data-ttu-id="1aa5e-189">孟加拉语（印度）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-189">Bengali (India)</span></span>
    
- <span data-ttu-id="1aa5e-190">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-190">Bulgarian</span></span>
    
- <span data-ttu-id="1aa5e-191">加泰罗尼亚语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-191">Catalan</span></span>
    
- <span data-ttu-id="1aa5e-192">中文（简体）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-192">Chinese (Simplified)</span></span>
    
- <span data-ttu-id="1aa5e-193">中文（繁体）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-193">Chinese (Traditional)</span></span>
    
- <span data-ttu-id="1aa5e-194">克罗地亚语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-194">Croatian</span></span>
    
- <span data-ttu-id="1aa5e-195">捷克语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-195">Czech</span></span>
    
- <span data-ttu-id="1aa5e-196">丹麦语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-196">Danish</span></span>
    
- <span data-ttu-id="1aa5e-197">荷兰语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-197">Dutch</span></span>
    
- <span data-ttu-id="1aa5e-198">荷兰语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-198">Dutch</span></span>
    
- <span data-ttu-id="1aa5e-199">英语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-199">English</span></span>
    
- <span data-ttu-id="1aa5e-200">爱沙尼亚语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-200">Estonian</span></span>
    
- <span data-ttu-id="1aa5e-201">菲律宾语（菲律宾）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-201">Filipino (Philippines)</span></span>
    
- <span data-ttu-id="1aa5e-202">芬兰语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-202">Finnish</span></span>
    
- <span data-ttu-id="1aa5e-203">法语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-203">French</span></span>
    
- <span data-ttu-id="1aa5e-204">加利西亚语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-204">Galician</span></span>
    
- <span data-ttu-id="1aa5e-205">德语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-205">German</span></span>
    
- <span data-ttu-id="1aa5e-206">希腊语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-206">Greek</span></span>
    
- <span data-ttu-id="1aa5e-207">古吉拉特语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-207">Gujarati</span></span>
    
- <span data-ttu-id="1aa5e-208">希伯来语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-208">Hebrew</span></span>
    
- <span data-ttu-id="1aa5e-209">印地语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-209">Hindi</span></span>
    
- <span data-ttu-id="1aa5e-210">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-210">Hungarian</span></span>
    
- <span data-ttu-id="1aa5e-211">冰岛语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-211">Icelandic</span></span>
    
- <span data-ttu-id="1aa5e-212">印度尼西亚语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-212">Indonesian</span></span>
    
- <span data-ttu-id="1aa5e-213">意大利语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-213">Italian</span></span>
    
- <span data-ttu-id="1aa5e-214">日语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-214">Japanese</span></span>
    
- <span data-ttu-id="1aa5e-215">卡纳达语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-215">Kannada</span></span>
    
- <span data-ttu-id="1aa5e-216">哈萨克斯坦语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-216">Kazakh</span></span>
    
- <span data-ttu-id="1aa5e-217">斯瓦希里语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-217">Kiswahili</span></span>
    
- <span data-ttu-id="1aa5e-218">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-218">Korean</span></span>
    
- <span data-ttu-id="1aa5e-219">拉脱维亚语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-219">Latvian</span></span>
    
- <span data-ttu-id="1aa5e-220">立陶宛语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-220">Lithuanian</span></span>
    
- <span data-ttu-id="1aa5e-221">马来语（文莱达鲁萨兰国）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-221">Malay (Brunei Darussalam)</span></span>
    
- <span data-ttu-id="1aa5e-222">马来语（马来西亚）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-222">Malay (Malaysia)</span></span>
    
- <span data-ttu-id="1aa5e-223">马拉雅拉姆语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-223">Malayalam</span></span>
    
- <span data-ttu-id="1aa5e-224">马拉地语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-224">Marathi</span></span>
    
- <span data-ttu-id="1aa5e-225">挪威语（博克马尔）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-225">Norwegian (Bokmål)</span></span>
    
- <span data-ttu-id="1aa5e-226">挪威语（尼诺斯克语）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-226">Norwegian (Nynorsk)</span></span>
    
- <span data-ttu-id="1aa5e-227">奥里雅语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-227">Oriya</span></span>
    
- <span data-ttu-id="1aa5e-228">波斯语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-228">Persian</span></span>
    
- <span data-ttu-id="1aa5e-229">波兰语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-229">Polish</span></span>
    
- <span data-ttu-id="1aa5e-230">葡萄牙语（巴西）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-230">Portuguese (Brazil)</span></span>
    
- <span data-ttu-id="1aa5e-231">葡萄牙语（葡萄牙）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-231">Portuguese (Portugal)</span></span>
    
- <span data-ttu-id="1aa5e-232">罗马尼亚语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-232">Romanian</span></span>
    
- <span data-ttu-id="1aa5e-233">俄语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-233">Russian</span></span>
    
- <span data-ttu-id="1aa5e-234">塞尔维亚语（西里尔文，塞尔维亚）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-234">Serbian (Cyrillic, Serbia)</span></span>
    
- <span data-ttu-id="1aa5e-235">塞尔维亚语（拉丁文）</span><span class="sxs-lookup"><span data-stu-id="1aa5e-235">Serbian (Latin)</span></span>
    
- <span data-ttu-id="1aa5e-236">斯洛伐克语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-236">Slovak</span></span>
    
- <span data-ttu-id="1aa5e-237">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-237">Slovenian</span></span>
    
- <span data-ttu-id="1aa5e-238">西班牙语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-238">Spanish</span></span>
    
- <span data-ttu-id="1aa5e-239">瑞典语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-239">Swedish</span></span>
    
- <span data-ttu-id="1aa5e-240">泰米尔语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-240">Tamil</span></span>
    
- <span data-ttu-id="1aa5e-241">泰卢固语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-241">Telugu</span></span>
    
- <span data-ttu-id="1aa5e-242">泰语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-242">Thai</span></span>
    
- <span data-ttu-id="1aa5e-243">土耳其语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-243">Turkish</span></span>
    
- <span data-ttu-id="1aa5e-244">乌克兰语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-244">Ukrainian</span></span>
    
- <span data-ttu-id="1aa5e-245">乌尔都语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-245">Urdu</span></span>
    
- <span data-ttu-id="1aa5e-246">越南语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-246">Vietnamese</span></span>
    
- <span data-ttu-id="1aa5e-247">威尔士语</span><span class="sxs-lookup"><span data-stu-id="1aa5e-247">Welsh</span></span>
    


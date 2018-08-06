---
title: 'Exchange Online Protection 中的 Exchange 管理员中心 '
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
description: Exchange 管理中心 (EAC) 是基于 Web 的 Microsoft Exchange Online Protection (EOP) 的管理控制台。
ms.openlocfilehash: 99640e561b41e47a74e7c22f0bbdcacd0dd80bd7
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026309"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="7c06e-103">Exchange Online Protection 中的 Exchange 管理员中心</span><span class="sxs-lookup"><span data-stu-id="7c06e-103">Exchange admin center in Exchange Online Protection</span></span> 

<span data-ttu-id="7c06e-104">Exchange 管理中心 (EAC) 是基于 Web 的 Microsoft Exchange Online Protection (EOP) 的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="7c06e-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span> 
  
<span data-ttu-id="7c06e-p101">正在查找此主题的 Exchange 2013 版本？请参阅 [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p101">Looking for the Exchange 2013 version of this topic? See [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx).</span></span>
  
<span data-ttu-id="7c06e-p102">正在查找此主题的 Exchange Online 版本？请参阅 [Exchange admin center in Exchange Online](http://technet.microsoft.com/library/ace44f6b-4084-4f9c-89b3-e0317962472b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p102">Looking for the Exchange Online version of this topic? See [Exchange admin center in Exchange Online](http://technet.microsoft.com/library/ace44f6b-4084-4f9c-89b3-e0317962472b.aspx).</span></span>
  
## <a name="accessing-the-eac"></a><span data-ttu-id="7c06e-109">访问 EAC</span><span class="sxs-lookup"><span data-stu-id="7c06e-109">Accessing the EAC</span></span>

<span data-ttu-id="7c06e-p103">在大多数情况下，EOP 客户将通过 Office 365 管理中心访问 EAC。在**管理员**图块，**我**平铺旁边的下拉列表菜单中，您可以找到到 EOP 的链接。单击**管理员**图块，然后从下拉列表菜单，可以跳转到 EAC 选择**Exchange Online Protection** 。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p103">In most cases, EOP customers will access the EAC through the Office 365 admin center. You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile. Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span> 
  
<span data-ttu-id="7c06e-p104">您也可以通过以下 URL 直接访问 EAC 登录页面：https://admin.protection.outlook.com/ecp/\<companydomain\>。例如 https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com。指定用户凭据后，您将直接进入 EAC。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p104">You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.</span></span>
  
## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="7c06e-116">EAC 中常用的用户界面元素</span><span class="sxs-lookup"><span data-stu-id="7c06e-116">Common user interface elements in the EAC</span></span>
<span data-ttu-id="7c06e-117"><a name="BKMK_CommonUserInterfaceElements"> </a></span><span class="sxs-lookup"><span data-stu-id="7c06e-117"></span></span>

<span data-ttu-id="7c06e-118">本部分将介绍 EAC 中的用户界面元素。</span><span class="sxs-lookup"><span data-stu-id="7c06e-118">This section describes the user interface elements that are found in the EAC.</span></span>
  
![EOP AdminCenter](media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a><span data-ttu-id="7c06e-120">功能窗格</span><span class="sxs-lookup"><span data-stu-id="7c06e-120">Feature Pane</span></span>

<span data-ttu-id="7c06e-p105">这是您要在 EAC 中执行的大部分任务的第一级导航。功能窗格按功能区域组织。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>
  
1. <span data-ttu-id="7c06e-123">**收件人**这是您将在其中查看内部用户和外部联系人。</span><span class="sxs-lookup"><span data-stu-id="7c06e-123">**Recipients** This is where you'll view internal users and external contacts.</span></span> 
    
2. <span data-ttu-id="7c06e-124">**权限**这将在其中管理管理员角色。</span><span class="sxs-lookup"><span data-stu-id="7c06e-124">**Permissions** This where you'll manage administrator roles.</span></span> 
    
3. <span data-ttu-id="7c06e-125">**合规性管理**这是，您将在其中找到审核日志和报告，例如管理员角色组报告。</span><span class="sxs-lookup"><span data-stu-id="7c06e-125">**Compliance Management** This is where you'll find audit logs and reports, such as the administrator role group report.</span></span> 
    
4. <span data-ttu-id="7c06e-126">**保护**这是，您将为您的组织中管理反恶意软件和反垃圾邮件保护以及管理隔离中的邮件。</span><span class="sxs-lookup"><span data-stu-id="7c06e-126">**Protection** This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span> 
    
5. <span data-ttu-id="7c06e-127">**邮件流**这是在此处管理规则、 接受的域和连接器，以及您将转执行邮件跟踪。</span><span class="sxs-lookup"><span data-stu-id="7c06e-127">**Mail Flow** This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span> 
    
### <a name="tabs"></a><span data-ttu-id="7c06e-128">选项卡</span><span class="sxs-lookup"><span data-stu-id="7c06e-128">Tabs</span></span>

<span data-ttu-id="7c06e-p106">选项卡是导航的第二级。每个功能区都包含各种选项卡，每种选项卡代表一项功能。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p106">The tabs are your second level of navigation. Each of the feature areas contains various tabs, each representing a feature.</span></span>
  
### <a name="toolbar"></a><span data-ttu-id="7c06e-131">工具栏</span><span class="sxs-lookup"><span data-stu-id="7c06e-131">Toolbar</span></span>

<span data-ttu-id="7c06e-p107">单击大多数选项卡时，将看到一个工具栏。工具栏包含执行特定操作的图标。下表介绍图标及其操作。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>
  
|<span data-ttu-id="7c06e-135">**图标**</span><span class="sxs-lookup"><span data-stu-id="7c06e-135">**Icon**</span></span>|<span data-ttu-id="7c06e-136">**名称**</span><span class="sxs-lookup"><span data-stu-id="7c06e-136">**Name**</span></span>|<span data-ttu-id="7c06e-137">**Action**</span><span class="sxs-lookup"><span data-stu-id="7c06e-137">**Action**</span></span>|
|:-----|:-----|:-----|
|![添加图标](media/ITPro-EAC-AddIcon.png)           <br/> |<span data-ttu-id="7c06e-139">添加、新建</span><span class="sxs-lookup"><span data-stu-id="7c06e-139">Add, New</span></span>  <br/> |<span data-ttu-id="7c06e-p108">使用此图标可创建一个新对象。其中一些图标有关联的向下箭头，单击该箭头会显示可以创建的其他对象。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>  <br/> |
|![编辑图标](media/ITPro-EAC-EditIcon.png)           <br/> |<span data-ttu-id="7c06e-143">编辑</span><span class="sxs-lookup"><span data-stu-id="7c06e-143">Edit</span></span>  <br/> |<span data-ttu-id="7c06e-144">使用此图标可编辑对象。</span><span class="sxs-lookup"><span data-stu-id="7c06e-144">Use this icon to edit an object.</span></span>  <br/> |
|![删除图标](media/ITPro-EAC-DeleteIcon.png)           <br/> |<span data-ttu-id="7c06e-146">删除</span><span class="sxs-lookup"><span data-stu-id="7c06e-146">Delete</span></span>  <br/> |<span data-ttu-id="7c06e-p109">使用此图标可删除对象。有些删除图标有一个向下箭头，单击该箭头可显示其他选项。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>  <br/> |
|![搜索图标](media/ITPro-EAC-.png)           <br/> |<span data-ttu-id="7c06e-150">搜索</span><span class="sxs-lookup"><span data-stu-id="7c06e-150">Search</span></span>  <br/> |<span data-ttu-id="7c06e-151">使用此图标可打开一个搜索框，可在其中键入要查找的对象的搜索短语。</span><span class="sxs-lookup"><span data-stu-id="7c06e-151">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>  <br/> |
|![刷新图标](media/ITPro-EAC-RefreshIcon.png)           <br/> |<span data-ttu-id="7c06e-153">刷新</span><span class="sxs-lookup"><span data-stu-id="7c06e-153">Refresh</span></span>  <br/> |<span data-ttu-id="7c06e-154">使用此图标可刷新列表视图。</span><span class="sxs-lookup"><span data-stu-id="7c06e-154">Use this icon to refresh the list view.</span></span>  <br/> |
|![更多选项图标](media/ITPro-EAC-MoreOptionsIcon.png)           <br/> |<span data-ttu-id="7c06e-156">更多选项</span><span class="sxs-lookup"><span data-stu-id="7c06e-156">More options</span></span>  <br/> |<span data-ttu-id="7c06e-p110">使用此图标可查看可以对该选项卡对象执行的操作。例如，在**收件人\>用户**单击此图标显示在**高级搜索**选项。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p110">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.  </span></span><br/> |
|![向上键图标](media/ITPro-EAC-UpArrowIcon.png)![向下键图标](media/ITPro-EAC-DownArrowIcon.png)           <br/> |<span data-ttu-id="7c06e-161">向上箭头和向下箭头</span><span class="sxs-lookup"><span data-stu-id="7c06e-161">Up arrow and down arrow</span></span>  <br/> |<span data-ttu-id="7c06e-162">使用这些图标可以将对象的优先级上移或下移。</span><span class="sxs-lookup"><span data-stu-id="7c06e-162">Use these icons to move an object's priority up or down.</span></span>  <br/> |
|![删除图标](media/ITPro-EAC-RemoveIcon.png)           <br/> |<span data-ttu-id="7c06e-164">删除</span><span class="sxs-lookup"><span data-stu-id="7c06e-164">Remove</span></span>  <br/> |<span data-ttu-id="7c06e-165">使用此图标可从列表中删除对象。</span><span class="sxs-lookup"><span data-stu-id="7c06e-165">Use this icon to remove objects from a list.</span></span>  <br/> |
   
### <a name="list-view"></a><span data-ttu-id="7c06e-166">列表视图</span><span class="sxs-lookup"><span data-stu-id="7c06e-166">List View</span></span>

<span data-ttu-id="7c06e-p111">选择某个选项卡时，在大多数情况下，将会看到一个列表视图。EAC 列表视图的可查看限制大约为 10,000 个对象。此外还包括了分页功能，因此可以对结果进行分页。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p111">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>
  
### <a name="details-pane"></a><span data-ttu-id="7c06e-170">详细信息窗格</span><span class="sxs-lookup"><span data-stu-id="7c06e-170">Details Pane</span></span>

<span data-ttu-id="7c06e-p112">从列表视图中选择对象时，有关该对象的信息将在详细信息窗格中显示。在某些情况下，详细信息窗格包括管理任务。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>
  
### <a name="me-tile-and-help"></a><span data-ttu-id="7c06e-173">自有图块和帮助</span><span class="sxs-lookup"><span data-stu-id="7c06e-173">Me tile and Help</span></span>

<span data-ttu-id="7c06e-p113">**Me**图块，可以注销 EAC，并以其他用户身份登录。从**帮助**![帮助图标](media/ITPro-EAC-HelpIcon.png)下拉菜单中，您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7c06e-p113">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](media/ITPro-EAC-HelpIcon.png) drop-down menu, you can perform the following actions:</span></span> 
  
1. <span data-ttu-id="7c06e-176">**帮助** 单击 ![帮助图标](media/ITPro-EAC-HelpIcon.png) 可查看联机帮助内容。</span><span class="sxs-lookup"><span data-stu-id="7c06e-176">**Help** Click ![Help Icon](media/ITPro-EAC-HelpIcon.png) to view the online help content.</span></span> 
    
2. <span data-ttu-id="7c06e-p114">**禁用帮助气泡图**创建或编辑对象时，帮助气泡显示上下文帮助字段。您可以关闭气泡的帮助，或者如果已禁用，则会将其打开。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p114">**Disable Help bubble** The Help bubble displays contextual help for fields when you create or edit an object. You can turn off the Help bubble or turn it on if it has been disabled.</span></span> 
    
3. <span data-ttu-id="7c06e-179">**版权**单击此链接可以阅读 Exchange Online Protection 的版权说明。</span><span class="sxs-lookup"><span data-stu-id="7c06e-179">**Copyright** Click this link to read the copyright notice for Exchange Online Protection.</span></span> 
    
4. <span data-ttu-id="7c06e-180">**隐私**单击以阅读有关 Exchange Online Protection 的隐私策略。</span><span class="sxs-lookup"><span data-stu-id="7c06e-180">**Privacy** Click to read the privacy policy for Exchange Online Protection.</span></span> 
    
## <a name="supported-browsers"></a><span data-ttu-id="7c06e-181">支持的浏览器</span><span class="sxs-lookup"><span data-stu-id="7c06e-181">Supported Browsers</span></span>
<span data-ttu-id="7c06e-182"><a name="BKMK_SupportedBrowsers"> </a></span><span class="sxs-lookup"><span data-stu-id="7c06e-182"></span></span>

<span data-ttu-id="7c06e-p115">若要获得最佳的 EAC 使用体验，我们建议您始终使用最新的浏览器、Office 客户端和应用程序。我们还建议您安装可用的软件更新。有关服务支持的浏览器和系统要求的详细信息，请参阅 [Office 365 系统要求](https://go.microsoft.com/fwlink/p/?LinkID=402699)。</span><span class="sxs-lookup"><span data-stu-id="7c06e-p115">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps. We also recommend that you install software updates when they become available. For more information about the supported browsers and system requirements for the service, see [Office 365 System Requirements](https://go.microsoft.com/fwlink/p/?LinkID=402699).</span></span> 
  
## <a name="supported-languages-in-eop"></a><span data-ttu-id="7c06e-186">EOP 中支持的语言</span><span class="sxs-lookup"><span data-stu-id="7c06e-186">Supported languages in EOP</span></span>
<span data-ttu-id="7c06e-187"><a name="BKMK_SupportedLanguages"> </a></span><span class="sxs-lookup"><span data-stu-id="7c06e-187"></span></span>

<span data-ttu-id="7c06e-188">Exchange Online Protection 支持并提供以下语言。</span><span class="sxs-lookup"><span data-stu-id="7c06e-188">The following languages are supported and available for Exchange Online Protection.</span></span>
  
- <span data-ttu-id="7c06e-189">阿姆哈拉语</span><span class="sxs-lookup"><span data-stu-id="7c06e-189">Amharic</span></span>
    
- <span data-ttu-id="7c06e-190">阿拉伯语</span><span class="sxs-lookup"><span data-stu-id="7c06e-190">Arabic</span></span>
    
- <span data-ttu-id="7c06e-191">巴斯克语（巴斯克）</span><span class="sxs-lookup"><span data-stu-id="7c06e-191">Basque (Basque)</span></span>
    
- <span data-ttu-id="7c06e-192">孟加拉语（印度）</span><span class="sxs-lookup"><span data-stu-id="7c06e-192">Bengali (India)</span></span>
    
- <span data-ttu-id="7c06e-193">保加利亚语</span><span class="sxs-lookup"><span data-stu-id="7c06e-193">Bulgarian</span></span>
    
- <span data-ttu-id="7c06e-194">加泰罗尼亚语</span><span class="sxs-lookup"><span data-stu-id="7c06e-194">Catalan</span></span>
    
- <span data-ttu-id="7c06e-195">中文(简体)</span><span class="sxs-lookup"><span data-stu-id="7c06e-195">Chinese (Simplified)</span></span>
    
- <span data-ttu-id="7c06e-196">中文(繁体)</span><span class="sxs-lookup"><span data-stu-id="7c06e-196">Chinese (Traditional)</span></span>
    
- <span data-ttu-id="7c06e-197">克罗地亚语</span><span class="sxs-lookup"><span data-stu-id="7c06e-197">Croatian</span></span>
    
- <span data-ttu-id="7c06e-198">捷克语</span><span class="sxs-lookup"><span data-stu-id="7c06e-198">Czech</span></span>
    
- <span data-ttu-id="7c06e-199">丹麦语</span><span class="sxs-lookup"><span data-stu-id="7c06e-199">Danish</span></span>
    
- <span data-ttu-id="7c06e-200">荷兰语</span><span class="sxs-lookup"><span data-stu-id="7c06e-200">Dutch</span></span>
    
- <span data-ttu-id="7c06e-201">荷兰语</span><span class="sxs-lookup"><span data-stu-id="7c06e-201">Dutch</span></span>
    
- <span data-ttu-id="7c06e-202">英语</span><span class="sxs-lookup"><span data-stu-id="7c06e-202">English</span></span>
    
- <span data-ttu-id="7c06e-203">爱沙尼亚语</span><span class="sxs-lookup"><span data-stu-id="7c06e-203">Estonian</span></span>
    
- <span data-ttu-id="7c06e-204">菲律宾语（菲律宾）</span><span class="sxs-lookup"><span data-stu-id="7c06e-204">Filipino (Philippines)</span></span>
    
- <span data-ttu-id="7c06e-205">芬兰语</span><span class="sxs-lookup"><span data-stu-id="7c06e-205">Finnish</span></span>
    
- <span data-ttu-id="7c06e-206">法语</span><span class="sxs-lookup"><span data-stu-id="7c06e-206">French</span></span>
    
- <span data-ttu-id="7c06e-207">加利西亚语</span><span class="sxs-lookup"><span data-stu-id="7c06e-207">Galician</span></span>
    
- <span data-ttu-id="7c06e-208">德语</span><span class="sxs-lookup"><span data-stu-id="7c06e-208">German</span></span>
    
- <span data-ttu-id="7c06e-209">希腊语</span><span class="sxs-lookup"><span data-stu-id="7c06e-209">Greek</span></span>
    
- <span data-ttu-id="7c06e-210">古吉拉特语</span><span class="sxs-lookup"><span data-stu-id="7c06e-210">Gujarati</span></span>
    
- <span data-ttu-id="7c06e-211">希伯来语</span><span class="sxs-lookup"><span data-stu-id="7c06e-211">Hebrew</span></span>
    
- <span data-ttu-id="7c06e-212">印地语</span><span class="sxs-lookup"><span data-stu-id="7c06e-212">Hindi</span></span>
    
- <span data-ttu-id="7c06e-213">匈牙利语</span><span class="sxs-lookup"><span data-stu-id="7c06e-213">Hungarian</span></span>
    
- <span data-ttu-id="7c06e-214">冰岛语</span><span class="sxs-lookup"><span data-stu-id="7c06e-214">Icelandic</span></span>
    
- <span data-ttu-id="7c06e-215">印度尼西亚语</span><span class="sxs-lookup"><span data-stu-id="7c06e-215">Indonesian</span></span>
    
- <span data-ttu-id="7c06e-216">意大利语</span><span class="sxs-lookup"><span data-stu-id="7c06e-216">Italian</span></span>
    
- <span data-ttu-id="7c06e-217">日语</span><span class="sxs-lookup"><span data-stu-id="7c06e-217">Japanese</span></span>
    
- <span data-ttu-id="7c06e-218">卡纳达语</span><span class="sxs-lookup"><span data-stu-id="7c06e-218">Kannada</span></span>
    
- <span data-ttu-id="7c06e-219">哈萨克斯坦语</span><span class="sxs-lookup"><span data-stu-id="7c06e-219">Kazakh</span></span>
    
- <span data-ttu-id="7c06e-220">斯瓦希里语</span><span class="sxs-lookup"><span data-stu-id="7c06e-220">Kiswahili</span></span>
    
- <span data-ttu-id="7c06e-221">朝鲜语</span><span class="sxs-lookup"><span data-stu-id="7c06e-221">Korean</span></span>
    
- <span data-ttu-id="7c06e-222">拉脱维亚语</span><span class="sxs-lookup"><span data-stu-id="7c06e-222">Latvian</span></span>
    
- <span data-ttu-id="7c06e-223">立陶宛语</span><span class="sxs-lookup"><span data-stu-id="7c06e-223">Lithuanian</span></span>
    
- <span data-ttu-id="7c06e-224">马来语（文莱达鲁萨兰国）</span><span class="sxs-lookup"><span data-stu-id="7c06e-224">Malay (Brunei Darussalam)</span></span>
    
- <span data-ttu-id="7c06e-225">马来语（马来西亚）</span><span class="sxs-lookup"><span data-stu-id="7c06e-225">Malay (Malaysia)</span></span>
    
- <span data-ttu-id="7c06e-226">马拉雅拉姆语</span><span class="sxs-lookup"><span data-stu-id="7c06e-226">Malayalam</span></span>
    
- <span data-ttu-id="7c06e-227">马拉地语</span><span class="sxs-lookup"><span data-stu-id="7c06e-227">Marathi</span></span>
    
- <span data-ttu-id="7c06e-228">挪威语（博克马尔）</span><span class="sxs-lookup"><span data-stu-id="7c06e-228">Norwegian (Bokmål)</span></span>
    
- <span data-ttu-id="7c06e-229">挪威语（尼诺斯克语）</span><span class="sxs-lookup"><span data-stu-id="7c06e-229">Norwegian (Nynorsk)</span></span>
    
- <span data-ttu-id="7c06e-230">奥里雅语</span><span class="sxs-lookup"><span data-stu-id="7c06e-230">Oriya</span></span>
    
- <span data-ttu-id="7c06e-231">波斯语</span><span class="sxs-lookup"><span data-stu-id="7c06e-231">Persian</span></span>
    
- <span data-ttu-id="7c06e-232">波兰语</span><span class="sxs-lookup"><span data-stu-id="7c06e-232">Polish</span></span>
    
- <span data-ttu-id="7c06e-233">葡萄牙语（巴西）</span><span class="sxs-lookup"><span data-stu-id="7c06e-233">Portuguese (Brazil)</span></span>
    
- <span data-ttu-id="7c06e-234">葡萄牙语（葡萄牙）</span><span class="sxs-lookup"><span data-stu-id="7c06e-234">Portuguese (Portugal)</span></span>
    
- <span data-ttu-id="7c06e-235">罗马尼亚语</span><span class="sxs-lookup"><span data-stu-id="7c06e-235">Romanian</span></span>
    
- <span data-ttu-id="7c06e-236">俄语</span><span class="sxs-lookup"><span data-stu-id="7c06e-236">Russian</span></span>
    
- <span data-ttu-id="7c06e-237">塞尔维亚语（西里尔文，塞尔维亚）</span><span class="sxs-lookup"><span data-stu-id="7c06e-237">Serbian (Cyrillic, Serbia)</span></span>
    
- <span data-ttu-id="7c06e-238">塞尔维亚语（拉丁语）</span><span class="sxs-lookup"><span data-stu-id="7c06e-238">Serbian (Latin)</span></span>
    
- <span data-ttu-id="7c06e-239">斯洛伐克语</span><span class="sxs-lookup"><span data-stu-id="7c06e-239">Slovak</span></span>
    
- <span data-ttu-id="7c06e-240">斯洛文尼亚语</span><span class="sxs-lookup"><span data-stu-id="7c06e-240">Slovenian</span></span>
    
- <span data-ttu-id="7c06e-241">西班牙语</span><span class="sxs-lookup"><span data-stu-id="7c06e-241">Spanish</span></span>
    
- <span data-ttu-id="7c06e-242">瑞典语</span><span class="sxs-lookup"><span data-stu-id="7c06e-242">Swedish</span></span>
    
- <span data-ttu-id="7c06e-243">泰米尔语</span><span class="sxs-lookup"><span data-stu-id="7c06e-243">Tamil</span></span>
    
- <span data-ttu-id="7c06e-244">泰卢固语</span><span class="sxs-lookup"><span data-stu-id="7c06e-244">Telugu</span></span>
    
- <span data-ttu-id="7c06e-245">泰语</span><span class="sxs-lookup"><span data-stu-id="7c06e-245">Thai</span></span>
    
- <span data-ttu-id="7c06e-246">土耳其语</span><span class="sxs-lookup"><span data-stu-id="7c06e-246">Turkish</span></span>
    
- <span data-ttu-id="7c06e-247">乌克兰语</span><span class="sxs-lookup"><span data-stu-id="7c06e-247">Ukrainian</span></span>
    
- <span data-ttu-id="7c06e-248">乌尔都语</span><span class="sxs-lookup"><span data-stu-id="7c06e-248">Urdu</span></span>
    
- <span data-ttu-id="7c06e-249">越南语</span><span class="sxs-lookup"><span data-stu-id="7c06e-249">Vietnamese</span></span>
    
- <span data-ttu-id="7c06e-250">威尔士语</span><span class="sxs-lookup"><span data-stu-id="7c06e-250">Welsh</span></span>
    


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
# <a name="exchange-admin-center-in-exchange-online-protection"></a>Exchange Online Protection 中的 Exchange 管理中心 

Exchange 管理中心 (EAC) 是基于 Web 的 Microsoft Exchange Online Protection (EOP) 的管理控制台。 
  
正在查找此主题的 Exchange 2013 版本？请参阅 [Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx)。
  
正在查找此主题的 Exchange Online 版本？请参阅 [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。
  
## <a name="accessing-the-eac"></a>访问 EAC

在大多数情况下, EOP 客户将通过 Microsoft 365 管理中心访问 EAC。 可以在“**自有**”磁贴旁的“**管理**”磁贴中的下拉菜单中找到指向 EOP 的链接。 单击“**管理**”磁贴，从下拉菜单中选择“**Exchange Online Protection**”以进入 EAC。 
  
您也可以通过以下 URL 直接访问 EAC 登录页面：https://admin.protection.outlook.com/ecp/\<companydomain\>。例如 https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com。指定用户凭据后，您将直接进入 EAC。
  
## <a name="common-user-interface-elements-in-the-eac"></a>EAC 中常用的用户界面元素

本部分将介绍 EAC 中的用户界面元素。
  
![EOP-AdminCenter](media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a>功能窗格

这是您要在 EAC 中执行的大部分任务的第一级导航。功能窗格按功能区域组织。
  
1. **收件人**你可以在此处查看内部用户和外部联系人。 
    
2. **权限**这将管理管理员角色。 
    
3. **合规性管理**你可以在此处找到审核日志和报告, 如管理员角色组报告。 
    
4. **保护**你可以在此处管理组织的反恶意软件和反垃圾邮件保护, 以及管理隔离邮件。 
    
5. **邮件流**你可以在此处管理规则、接受域和连接器, 以及你将在其中执行邮件跟踪的位置。 
    
### <a name="tabs"></a>选项卡

选项卡是导航的第二级。每个功能区都包含各种选项卡，每种选项卡代表一项功能。
  
### <a name="toolbar"></a>工具栏

单击大多数选项卡时，将看到一个工具栏。工具栏包含执行特定操作的图标。下表介绍图标及其操作。
  
|**图标**|**名称**|**Action**|
|:-----|:-----|:-----|
|![添加图标](media/ITPro-EAC-AddIcon.gif)           <br/> |添加、新建  <br/> |使用此图标可创建一个新对象。其中一些图标有关联的向下箭头，单击该箭头会显示可以创建的其他对象。  <br/> |
|![编辑图标](media/ITPro-EAC-EditIcon.gif)           <br/> |编辑  <br/> |使用此图标可编辑对象。  <br/> |
|![删除图标](media/ITPro-EAC-DeleteIcon.gif)           <br/> |删除  <br/> |使用此图标可删除对象。有些删除图标有一个向下箭头，单击该箭头可显示其他选项。  <br/> |
|![搜索图标](media/ITPro-EAC-.gif)           <br/> |搜索  <br/> |使用此图标可打开一个搜索框，可在其中键入要查找的对象的搜索短语。  <br/> |
|![刷新图标](media/ITPro-EAC-RefreshIcon.gif)           <br/> |刷新  <br/> |使用此图标可刷新列表视图。  <br/> |
|![更多选项图标](media/ITPro-EAC-MoreOptionsIcon.gif)           <br/> |更多选项  <br/> |使用此图标可以查看可对该选项卡的对象执行的更多操作。 例如, 在 "**收件人\> " 用户**单击此图标时, 将显示用于执行**高级搜索**的选项。  <br/> |
|![向上键图标](media/ITPro-EAC-UpArrowIcon.gif)![向下键图标](media/ITPro-EAC-DownArrowIcon.gif)           <br/> |向上箭头和向下箭头  <br/> |使用这些图标可以将对象的优先级上移或下移。  <br/> |
|![删除图标](media/ITPro-EAC-RemoveIcon.gif)           <br/> |删除  <br/> |使用此图标可从列表中删除对象。  <br/> |
   
### <a name="list-view"></a>列表视图

选择某个选项卡时，在大多数情况下，将会看到一个列表视图。EAC 列表视图的可查看限制大约为 10,000 个对象。此外还包括了分页功能，因此可以对结果进行分页。
  
### <a name="details-pane"></a>详细信息窗格

从列表视图中选择对象时，有关该对象的信息将在详细信息窗格中显示。在某些情况下，详细信息窗格包括管理任务。
  
### <a name="me-tile-and-help"></a>自有图块和帮助

使用“自有”**** 图块可以注销 EAC，然后以其他用户身份登录。 从 "**帮助**![帮助"](media/ITPro-EAC-HelpIcon.gif)图标下拉菜单中, 可以执行下列操作: 
  
1. **帮助** 单击 ![帮助图标](media/ITPro-EAC-HelpIcon.gif) 可查看联机帮助内容。 
    
2. **禁用帮助气泡**当您创建或编辑对象时, 帮助气泡会显示字段的上下文帮助。 您可以关闭"帮助"气泡，如果已被禁用，也可以打开它。 
    
3. **版权**单击此链接可阅读适用于 Exchange Online Protection 的版权通知。 
    
4. **隐私**单击以阅读 Exchange Online Protection 的隐私策略。 
    
## <a name="supported-browsers"></a>支持的浏览器

若要获得最佳的 EAC 使用体验，我们建议您始终使用最新的浏览器、Office 客户端和应用程序。我们还建议您安装可用的软件更新。有关服务支持的浏览器和系统要求的详细信息，请参阅 [Office 365 系统要求](https://go.microsoft.com/fwlink/p/?LinkID=402699)。 
  
## <a name="supported-languages-in-eop"></a>EOP 中支持的语言

Exchange Online Protection 支持并提供以下语言。
  
- 阿姆哈拉语
    
- 阿拉伯语
    
- 巴斯克语（巴斯克）
    
- 孟加拉语（印度）
    
- 保加利亚语
    
- 加泰罗尼亚语
    
- 中文（简体）
    
- 中文（繁体）
    
- 克罗地亚语
    
- 捷克语
    
- 丹麦语
    
- 荷兰语
    
- 荷兰语
    
- 英语
    
- 爱沙尼亚语
    
- 菲律宾语（菲律宾）
    
- 芬兰语
    
- 法语
    
- 加利西亚语
    
- 德语
    
- 希腊语
    
- 古吉拉特语
    
- 希伯来语
    
- 印地语
    
- 匈牙利语
    
- 冰岛语
    
- 印度尼西亚语
    
- 意大利语
    
- 日语
    
- 卡纳达语
    
- 哈萨克斯坦语
    
- 斯瓦希里语
    
- 朝鲜语
    
- 拉脱维亚语
    
- 立陶宛语
    
- 马来语（文莱达鲁萨兰国）
    
- 马来语（马来西亚）
    
- 马拉雅拉姆语
    
- 马拉地语
    
- 挪威语（博克马尔）
    
- 挪威语（尼诺斯克语）
    
- 奥里雅语
    
- 波斯语
    
- 波兰语
    
- 葡萄牙语（巴西）
    
- 葡萄牙语（葡萄牙）
    
- 罗马尼亚语
    
- 俄语
    
- 塞尔维亚语（西里尔文，塞尔维亚）
    
- 塞尔维亚语（拉丁文）
    
- 斯洛伐克语
    
- 斯洛文尼亚语
    
- 西班牙语
    
- 瑞典语
    
- 泰米尔语
    
- 泰卢固语
    
- 泰语
    
- 土耳其语
    
- 乌克兰语
    
- 乌尔都语
    
- 越南语
    
- 威尔士语
    


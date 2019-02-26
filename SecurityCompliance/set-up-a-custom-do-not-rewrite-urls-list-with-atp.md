---
title: 使用 Office 365 ATP 安全链接设置自定义不重写 url 列表
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
description: 设置 ATP 安全链接策略时, 可以包括 "不重写" 的 url 列表, 以使组织中的某些人能够访问包含在列表中的网站。
ms.openlocfilehash: 006dab44054f9cb707bb13d158588ab6606fab5c
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2019
ms.locfileid: "30241974"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>使用 Office 365 ATP 安全链接设置自定义不重写 url 列表

> [!IMPORTANT]
> 本文适用于商业客户。如果您是在 Outlook 中查找有关安全链接的信息的家庭用户, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

使用[Office 365 高级威胁防护](office-365-atp.md)(ATP), 您的组织可以有一个[自定义的阻止 url](set-up-a-custom-blocked-urls-list-wtih-atp.md), 这样, 当用户单击电子邮件中的 web 地址 (url) 或某些 Office 文档时, 将阻止这些 url 转到这些 url。您的组织还可以为组织中的特定组提供自定义的 "不重写" 列表。"不重写" 列表使某些用户能够访问由[Office 365 中的 ATP 安全链接](atp-safe-links.md)阻止的 url。 
  
本文介绍如何指定从 ATP 安全链接扫描中排除的 url 的列表, 以及需要牢记的几个重要事项。

## <a name="set-up-a-do-not-rewrite-list"></a>设置 "不重写" 列表

ATP 安全链接保护使用多个列表, 包括组织的阻止 url 列表和 "不重写" 列表中的例外。如果您具有必要的权限, 则可以设置自定义的 "不重写" 列表。在添加或编辑适用于组织中特定收件人的安全链接策略时, 可以执行此操作。 

若要编辑 (或定义) ATP 策略, 您必须分配下表中所述的角色之一:

|角色  |分配的位置/方式  |
|---------|---------|
|Office 365 全局管理员 |默认情况下, 注册购买 Office 365 的人是全局管理员。(请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)         |
|Security Administrator |Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 组织管理 |Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> 若要了解有关角色和权限的详细信息, 请参阅[Office 365 &amp;安全合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>查看或编辑自定义 "不重写" url 列表
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用你的工作或学校帐户登录。 
    
2. 在左侧导航中的 "**威胁管理** \> **策略** \> **安全链接**" 下。
    
3. 在 "**适用于特定收件人的策略**" 部分, 选择 "**新建**" ("新建" 按钮类似**+** 于加号 ()) 以创建新策略。(也可以编辑现有策略。)<br/>![选择 "新建" 为特定的电子邮件收件人添加安全链接策略](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. 为策略指定名称和说明。
    
5. 在 "**不重写以下 url"** 部分, 选择 "**输入一个有效的 url** " 框, 然后键入 URL, 然后选择加号 (+)。 
    
6. 在 "**应用**于" 部分中, 选择 **"收件人是其成员**", 然后选择要包括在策略中的组。选择 "**添加**", 然后选择 **"确定"**。
    
7. 添加完 url 后, 在屏幕的右下角, 选择 "**保存**"。
    
> [!NOTE]
> 请务必查看您的组织的已阻止 url 的自定义列表。请参阅[使用 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)。 
  
## <a name="important-points-to-keep-in-mind"></a>需要牢记的要点

- 您在 "不重写" 列表中指定的任何 url 将从 ATP 安全链接扫描中排除, 用于您指定的收件人。
 
- 当您为 ATP 安全链接策略指定 "不重写" 列表时, 可以包含最大为三个通配符星号 (\*)。对于诸如\* `contoso.com` `http://`或`https://`之类的条目, 将假定为通配符 ()。这表示条目, `contoso.com`例如类似于 "不重`*contoso.com*`写" 列表的条目。

- 如果您在 "不重写" 列表中已经有 url 列表, 请务必查看该列表并根据需要添加通配符。例如, 如果您的现有列表中有类似`http://contoso.com/a`的条目, 并且您希望在策略`http://contoso.com/a/b`中包含类似的子路径, 请将通配符添加到您的`http://contoso.com/a*`条目, 使其看起来像这样。
    
- 请勿在 "不重写" 列表中指定的 url 中包含正斜杠 (/)。例如, 而不是在`contoso.com/` "不重写" 列表中输入, 而`contoso.com`是输入。
    
下表列出了可以输入的内容的示例以及这些项有何影响。
    
|**示例条目**|**功能**|
|:-----|:-----|
|`*contoso.com*`  <br/> |允许特定收件人访问域、子域和路径, 例如`http://www.contoso.com`、 `https://www.contoso.com` `https://maps.contoso.com`、或`http://www.contoso.com/a`  <br/> |
|`http://contoso.com/a`  <br/> |允许特定收件人访问类似`http://contoso.com/a`的网站, 但不允许像这样的子路径`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |允许特定收件人访问像这样的子`http://contoso.com/a`网站之类的子网站`http://contoso.com/a/b`  <br/> |
   
 
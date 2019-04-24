---
title: 使用 Office 365 ATP 安全链接设置自定义已阻止 url 列表
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
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
description: 了解如何使用 Office 365 高级威胁防护为您的组织设置阻止的 url 的列表。 阻止的 url 将根据 ATP 安全链接策略应用于电子邮件和 Office 文档。
ms.openlocfilehash: c5444e644a35688ea626004fbc6865df4ae645f9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264508"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>使用 Office 365 ATP 安全链接设置自定义已阻止 url 列表

> [!IMPORTANT]
> 本文适用于商业客户。 如果您是在 Outlook 中查找有关安全链接的信息的家庭用户, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

使用[Office 365 高级威胁防护](office-365-atp.md)(ATP), 您的组织可以拥有已阻止的网站地址 (url) 的自定义列表。 在阻止 url 的情况下, 单击指向被阻止 URL 的链接的用户将被带到类似于以下图像的[警告页面](atp-safe-links-warning-pages.md): 
  
![阻止此网站](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
"阻止的 url" 列表由组织的 office 365 安全团队定义, 该列表适用于组织中由 office 365 ATP 安全链接策略涵盖的所有人。 
  
阅读本文, 了解如何为[Office 365 中的 ATP 安全链接](atp-safe-links.md)设置组织的自定义 "阻止 url" 列表。
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>查看或编辑阻止的 url 的自定义列表

[Office 365 中的 ATP 安全链接](atp-safe-links.md)使用多个列表, 包括组织的自定义阻止 url 列表。 如果您具有所需的权限, 则可以设置您的组织的自定义列表。 为此, 请编辑组织的默认安全链接策略。

若要编辑 (或定义) ATP 策略, 您必须分配下表中所述的角色之一: 

|Role  |分配的位置/方式  |
|---------|---------|
|Office 365 全局管理员 |默认情况下, 注册购买 Office 365 的人是全局管理员。 (请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)         |
|Security Administrator |Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 组织管理 |Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> 若要了解有关角色和权限的详细信息, 请参阅[Office 365 &amp;安全合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>查看或编辑自定义阻止的 url 列表
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用你的工作或学校帐户登录。 
    
2. 在左侧导航中的 "**威胁管理**" 下, 选择 "**策略** \> **安全链接**"。
    
3. 在 "**适用于整个组织的策略**" 部分, 选择 "**默认**", 然后选择 "**编辑**" ("编辑" 按钮类似于铅笔)。<br/>![单击 "编辑" 编辑安全链接保护的默认策略](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>这使您可以查看已阻止 url 的列表。 首先, 你可能没有在此处列出的任何 url。<br/>!["默认安全链接策略" 中的 "阻止的 url" 列表](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. 选择 "**输入一个有效的 url** " 框, 键入 URL, 然后选择加号 (**+**)。 

5. 添加完 url 后, 在屏幕的右下角, 选择 "**保存**"。
    
## <a name="a-few-things-to-keep-in-mind"></a>请注意以下几点

将 url 添加到列表中时, 请记住以下几点: 

- 不要在 URL 的末尾包含正**/** 斜杠 ()。 例如, 而不是`http://www.contoso.com/`输入。 `http://www.contoso.com`
    
- 您可以指定一个仅域的 URL (如`contoso.com`或`tailspintoys.com`)。 这将阻止单击包含域的任何 URL。

- 您可以在不阻止整个域`toys.contoso.com*`的情况下 (如`contoso.com`) 指定子域 (如)。 这将阻止单击包含子域的任何 URL, 但它不会阻止单击包含完整域的 url。  
    
- 每个 URL 最长可包含三个\*通配符星号 ()。 下表列出了您可以输入的内容的一些示例, 以及这些项有何影响。
    
|**示例条目**|**功能**|
|:-----|:-----|
|`contoso.com` 或 `*contoso.com*`  <br/> |阻止域、子域和路径, 例如`https://www.contoso.com`、和`http://sub.contoso.com``http://contoso.com/abc`  <br/> |
|`http://contoso.com/a`  <br/> |阻止网站`http://contoso.com/a` , 而不是其他子路径 (如`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |阻止网站`http://contoso.com/a`和其他子路径 (如`http://contoso.com/a/b`  <br/> |
|`http://toys.contoso.com*`  <br/> |阻止子域 (本例中为 "玩具"), 但允许单击其他域 url (如`http://contoso.com`或`http://home.contoso.com`)。  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>如何为组织中的某些用户定义例外

如果您希望某些组能够查看其他人可能阻止的 url, 则可以指定适用于特定收件人的 ATP 安全链接策略。 请参阅[设置自定义 "不重写" 使用 ATP 安全链接的 url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。
  


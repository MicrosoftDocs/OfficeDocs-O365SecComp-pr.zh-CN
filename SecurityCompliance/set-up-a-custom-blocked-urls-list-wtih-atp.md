---
title: 设置自定义阻止 Url 列表使用 Office 365 ATP 安全链接
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 12/11/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: 了解如何设置为使用 Office 365 高级威胁保护组织的阻止 Url 的列表。阻止的 Url 将适用于电子邮件和根据您 ATP 安全链接策略的 Office 文档。
ms.openlocfilehash: 2b2fa78a4dbd6fc8bd0e46d7f23402aff732e096
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014954"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>设置自定义阻止 Url 列表使用 Office 365 ATP 安全链接

使用[Office 365 高级威胁保护](office-365-atp.md)(ATP)，您的组织可以自定义列表的被阻止的网站地址 (Url)。当阻止 URL 时，单击指向阻止 URL 的人员将转到[警告页](atp-safe-links-warning-pages.md)类似于下图中： 
  
![阻止此网站](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
阻止的 Url 列表定义由您组织的 Office 365 安全组，并且该列表适用于 Office 365 ATP 安全链接策略覆盖组织中的每个人。 
  
阅读此文，了解如何为[ATP Office 365 中的安全链接](atp-safe-links.md)设置组织的自定义阻止 Url 列表。
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>查看或编辑被阻止 Url 的自定义列表

[ATP Office 365 中的安全链接](atp-safe-links.md)使用多个列表，其中包括您组织的自定义阻止的 Url 列表。如果您有必要的权限，您可以设置组织的自定义列表。通过编辑您的组织的默认安全链接策略执行此操作。
  
1. 转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。 
    
2. 在左侧导航窗格中，**威胁管理**下面，选择**策略** \> **安全的链接**。
    
3. 在**应用于整个组织的策略**部分中，选择**默认**，，然后选择**编辑**（编辑按钮图像类似铅笔）。<br/>![单击编辑来编辑您的安全链接保护的默认策略](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>这样，您可以查看您阻止 Url 的列表。首先，您可能没有任何此处列出的 Url。<br/>![阻止默认的安全链接策略中的 Url 列表](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. 选择**输入一个有效的 URL**框中，键入 URL，然后选择加号 (**+**)。 

5. 当您完成在屏幕的右下角中添加 Url 时，选择**保存**。
    
## <a name="a-few-things-to-keep-in-mind"></a>要记住的几件事

时向列表添加 Url，请记住以下几点： 

- 不包含正斜杠 ( **/**) URL 的末尾。例如，而输入不是`http://www.contoso.com/`，输入`http://www.contoso.com`。
    
- 您可以指定仅域 URL (如`contoso.com`或`tailspintoys.com`)。这将阻止单击任何包含域的 url。

- 您可以指定子域 (如`toys.contoso.com*`) 不阻止完整的域 (如`contoso.com`)。这将阻止单击任何 URL 包含子域，但不会阻止单击到包含完整的域的 URL。  
    
- 您可以包括三个通配符星号 (\*) 每个 URL。下表列出了您可以输入和什么影响这些条目的一些示例。
    
|**示例条目**|**它的用途**|
|:-----|:-----|
|`contoso.com`或`*contoso.com*`  <br/> |阻止的域、 子域和路径，如`https://www.contoso.com`， `http://sub.contoso.com`，和`http://contoso.com/abc`  <br/> |
|`http://contoso.com/a`  <br/> |阻止对网站`http://contoso.com/a`，但不是其他子路径 like`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |阻止对网站`http://contoso.com/a`以及其他子路径 like`http://contoso.com/a/b`  <br/> |
|`http://toys.contoso.com*`  <br/> |一个子域 （在本例中的"玩具"） 的块但允许单击到其他域 Url (如`http://contoso.com`或`http://home.contoso.com`)。  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>如何在组织中定义的特定用户的例外

如果您希望某些组能够查看其他人可能被阻止的 Url，您可以指定适用于特定收件人 ATP 安全链接策略。请参阅[设置自定义"执行不重写"Url 列表使用 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。
  


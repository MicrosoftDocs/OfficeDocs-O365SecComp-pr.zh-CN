---
title: 设置自定义重写不执行操作的 Url 列表使用 Office 365 ATP 安全链接
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: 当您设置了您 ATP 的安全链接策略时，可以包括 do not 写以使您的组织中的某些用户访问列表中包括的网站的 Url 的列表。
ms.openlocfilehash: 3ce783a3f783889bdc59ad8d412c80a79e7dd914
ms.sourcegitcommit: 7032830867eb3fc71760e04b8342aff174c5d757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "25353258"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>设置自定义重写不执行操作的 Url 列表使用 Office 365 ATP 安全链接

[Office 365 高级威胁保护](office-365-atp.md)(ATP)，您的组织可以[自定义被阻止的 Url](set-up-a-custom-blocked-urls-list-wtih-atp.md)，以便当人员单击 web 地址 (Url) 中的电子邮件或某些 Office 文档，他们无法转到这些 Url。您的组织也可以在组织中有特定的组的自定义"执行不重写"列表。"执行不重写"列表使一些人访问否则阻止通过[ATP Office 365 中的安全链接](atp-safe-links.md)的 Url。 
  
本文介绍如何指定将排除在扫描 ATP 安全链接和一些重要事项，需要注意以下事项的 Url 的列表。

## <a name="set-up-a-do-not-rewrite-list"></a>设置"执行不重写"列表

ATP 安全链接保护使用多个列表，其中包括贵组织的阻止的 Url 列表和"执行不重写"的例外列表。如果您有必要的权限，您可以设置自定义"执行不重写"列表。添加或编辑将应用于特定收件人在组织中的安全链接策略时执行此操作。 
  
1. 转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。 
    
2. 在左侧导航窗格中，在**威胁管理**下\>**策略** \> **安全的链接**。
    
3. 在**的可以应用到特定收件人的策略**部分中，选择**新建**(新建按钮图像类似一个加号 ( **+**)) 创建新策略。（或者，您可以编辑现有的策略。）
    
    ![选择新建以添加特定的电子邮件收件人的安全链接策略](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. 指定的名称和说明您的策略。
    
5. 在**不重写以下 Url**部分中，选择**输入一个有效的 URL**框中，然后键入一个 URL，，然后选择加号 （+）。 
    
6. 在**应用于**部分中，选择**收件人是的成员**，，然后选择您想要包括在您的策略的组。选择**添加**，然后选择**确定**。
    
7. 当您完成在屏幕的右下角中添加 Url 时，选择**保存**。
    
> [!NOTE]
> 请务必查看贵组织的自定义阻止 Url 的列表。请参阅[设置自定义阻止 Url 列表使用 ATP 安全链接](set-up-a-custom-blocked-urls-list-wtih-atp.md)。 
  
## <a name="important-points-to-keep-in-mind"></a>需要牢记的重要因素

- 从 ATP 安全链接您指定的收件人扫描中排除"执行不重写"列表中指定的任何 Url。
 
- 当您指定的 ATP 安全链接策略的"执行不重写"列表时，可以包括三个通配符星号 (\*)。通配符 (\*) 如假定条目`contoso.com`，其中不显式包括前缀或子域，如`http://`或`https://`。这意味着条目，如`contoso.com`类似于`*contoso.com*`"执行不重写"列表。

- 如果您已有"执行不重写"列表中的 Url 的列表，请务必查看该列表并根据需要添加通配符。例如，如果您现有列表条目，如`http://contoso.com/a`并且想要包括类似的子路径`http://contoso.com/a/b`在您的策略，将通配符添加到您的项，使其类似`http://contoso.com/a*`。
    
- 在"执行不重写"列表中指定的 Url 中不包括斜线 （/）。例如，而不是输入`contoso.com/`在"执行不重写"列表中，输入`contoso.com`。
    
您可以输入和什么影响这些条目的以下表列表示例具有。
    
|**示例条目**|**它的用途**|
|:-----|:-----|
|`*contoso.com*`  <br/> |允许特定收件人访问域、 子域和路径，如`http://www.contoso.com`， `https://www.contoso.com`， `https://maps.contoso.com`，或`http://www.contoso.com/a`  <br/> |
|`http://contoso.com/a`  <br/> |允许特定收件人访问的站点，如`http://contoso.com/a`，但不是子路径 like`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |允许特定收件人访问的站点，如`http://contoso.com/a`以及 like 子路径`http://contoso.com/a/b`  <br/> |
   
  

## <a name="related-topics"></a>相关主题

[Office 365 高级威胁防护](office-365-atp.md)
  
[Office 365 中的 ATP 安全链接](atp-safe-links.md)
  
[设置 Office 365 中的安全链接 ATP 策略](set-up-atp-safe-links-policies.md)
  
[设置自定义阻止 Url 列表使用 ATP 安全链接](set-up-a-custom-blocked-urls-list-wtih-atp.md)

[Office 365 高级威胁保护的视图报告](view-reports-for-atp.md)

[Office 365 安全性权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)
  


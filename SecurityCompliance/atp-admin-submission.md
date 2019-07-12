---
title: Office 365 ATP 中的管理员提交
ms.author: brwilcox
author: briwilcox
manager: dansimp
ms.date: 07/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 了解如何将潜在有害的邮件、Url 和文件提交给 Microsoft。
ms.openlocfilehash: 6f7ea63cae4d7cafb0d1386b29d99101d290ef30
ms.sourcegitcommit: 9e2df36b05a2c93ce2629a7a5eda8f44159d114d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "35632222"
---
# <a name="admin-submissions-in-office-365-atp"></a>Office 365 ATP 中的管理员提交

管理员现在可以使用文件或网络邮件 ID、Url 和文件在 Office 365 中进行扫描, 来发送电子邮件。 "更新的提交" 部分仍包括用户报告的消息。 

当您提交电子邮件时, 您将获得可能允许传入的电子邮件进入租户的任何策略的信息, 以及对邮件中的任何 Url 和附件的检查。 可能允许邮件的策略包括单个用户的安全发件人列表以及租户级策略 (如 ETR 规则)。 


## <a name="how-to-submit-content"></a>如何提交内容

若要将内容提交给 Microsoft, 请单击 "提交" 页面左上角的 "**新建提交**" 按钮。 将显示页面右侧的浮出控件, 其中包含用于提交电子邮件、URL 或文件的选项。 

### <a name="email"></a>电子邮件
![电子邮件提交示例](media/submission-flyout-email.PNG)
1. 若要提交电子邮件, 请选择 "**电子邮件**", 并指定电子邮件**网络邮件 ID**或上载电子邮件文件。 

2. 指定您想要运行策略检查的收件人。 策略检查将确定电子邮件是否因用户或租户级别策略而绕过扫描。 

3. 指定是否应阻止电子邮件。 如果应阻止该电子邮件, 请指定是否应将其阻止为垃圾邮件、网络钓鱼或恶意软件。 如果您不确定可能的类型, 请使用您的最佳 judgement。  

* 如果由于提交策略而绕过筛选器, 你将看到有关该策略的信息。

* 如果筛选器由于一个或多个策略而被绕过, 扫描将在几分钟内完成。 您将通过单击状态链接来查看有关提交的其他信息。 这包括策略检查结果和重新扫描判定结果。 注意这不会再次通过 Office 365 ATP 完全筛选堆栈运行电子邮件, 但会根据邮件、URL 或文件的某些属性运行部分重新扫描。 

4. 单击 "**提交**" 按钮。

### <a name="url"></a>URL
![电子邮件提交示例](media/submission-url-flyout.png)
1. 若要提交 URL, 请从浮出控件中选择**url** 。 键入完整 URL, 包括协议 (**https://**)。 

* 如果您选择了 "**应该已经过筛选**", 请指定 URL 是否为网络钓鱼或恶意软件。

2. 单击 "**提交**" 按钮。 


### <a name="file"></a>文件
![电子邮件提交示例](media/submission-file-flyout.PNG)
1. 若要提交文件, 请从浮出控件中选择**文件**, 并上载要扫描的文件。 

2. 单击 "**提交**" 按钮。


## <a name="related-topics"></a>相关主题

[Office 365 高级威胁防护计划2](office-365-ti.md)
  
[防御 Office 365 中的威胁](protect-against-threats.md)
  
[查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)
  


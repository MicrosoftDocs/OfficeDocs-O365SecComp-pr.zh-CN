---
title: Office 365 中的管理员提交, O365 报送, Office 365 垃圾邮件问题, O365 false 负数, 提交在 office 365 中的网络钓鱼, 提交电子邮件以便进行扫描, 在 Office 365 中提交可疑电子邮件, 扫描邮件, 让 Microsoft 扫描网络钓鱼, 使用 microsoft 扫描进行垃圾邮件, 提交电子邮件、提交电子邮件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 了解如何将可疑电子邮件、可疑的网络钓鱼邮件、垃圾邮件和其他可能有害的邮件、Url 和文件从 Office 365 租户提交到 Microsoft 进行扫描。
ms.openlocfilehash: 5a909e8b587e2a1265c1b2afbd5e063d46a04e2c
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230946"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a>如何将可疑的垃圾邮件、网络钓鱼、Url 和文件提交到 Microsoft for Office 365 扫描

管理员可以通过使用文件或网络邮件 ID、Url 和文件来通过 Microsoft Office 365 中的扫描来发送电子邮件。 "更新的提交" 部分仍包括用户报告的消息, 并可供使用 EOP 的所有客户使用。

当您提交电子邮件时, 您将获得可能允许传入的电子邮件进入租户的任何策略的信息, 以及对邮件中的任何 Url 和附件的检查。 可能允许邮件的策略包括单个用户的安全发件人列表以及租户级策略 (如 ETR 规则)。 

## <a name="how-to-submit-content-to-microsoft-for-office-365-scanning"></a>如何将内容提交到 Microsoft for Office 365 扫描

若要将内容提交给 Microsoft, 请单击 "提交" 页面左上角的 "**新建提交**" 按钮。 将显示页面右侧的浮出控件, 其中包含用于提交电子邮件、URL 或文件的选项。 

### <a name="submit-an-email-to-microsoft"></a>向 Microsoft 提交电子邮件
![电子邮件提交示例](media/submission-flyout-email.PNG)
1. 若要提交电子邮件, 请选择 "**电子邮件**", 并指定电子邮件**网络邮件 ID**或上载电子邮件文件。 

2. 指定您想要运行策略检查的收件人。 策略检查将确定电子邮件是否因用户或租户级别策略而绕过扫描。 

3. 指定是否应阻止电子邮件。 如果应阻止该电子邮件, 请指定是否应将其阻止为垃圾邮件、网络钓鱼或恶意软件。 如果您不确定可能的类型, 请使用您的最佳 judgement。  

* 如果由于提交策略而绕过筛选器, 你将看到有关该策略的信息。

* 如果筛选器由于一个或多个策略而被绕过, 扫描将在几分钟内完成。 您将通过单击状态链接来查看有关提交的其他信息。 这包括策略检查结果和重新扫描判定结果。 注意这不会再次通过 Office 365 ATP 完全筛选堆栈运行电子邮件, 但会根据邮件、URL 或文件的某些属性运行部分重新扫描。 

4. 单击 "**提交**" 按钮。

### <a name="submit-a-url-to-microsoft"></a>向 Microsoft 提交 URL
![电子邮件提交示例](media/submission-url-flyout.png)
1. 若要提交 URL, 请从浮出控件中选择**url** 。 键入完整 URL, 包括协议 (**https://**)。 

* 如果您选择了 "**应该已经过筛选**", 请指定 URL 是否为网络钓鱼或恶意软件。

2. 单击 "**提交**" 按钮。 


### <a name="submit-a-file-to-microsoft"></a>将文件提交给 Microsoft
![电子邮件提交示例](media/submission-file-flyout.PNG)
1. 若要提交文件, 请从浮出控件中选择**文件**, 并上载要扫描的文件。 

2. 单击 "**提交**" 按钮。


## <a name="related-topics"></a>相关主题

[Office 365 高级威胁防护计划2](office-365-ti.md)
  
[防御 Office 365 中的威胁](protect-against-threats.md)
  
[查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)
  


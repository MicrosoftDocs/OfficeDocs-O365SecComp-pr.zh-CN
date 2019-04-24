---
title: 使用邮件流规则来查看用户向 Microsoft 报告的内容
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: 您可以创建 Exchange 邮件流规则, 以防止用户将电子邮件发送给 Microsoft 进行分析并在自己的安全过程中使用它们。
ms.openlocfilehash: 3552899c2fb471624234625331492edcd8421da6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264274"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>使用邮件流规则来查看用户向 Microsoft 报告的内容

您可以使用多种方法将假负和误报邮件发送给 Microsoft 进行分析。 作为管理员, 您可以使用邮件流规则查看用户以垃圾邮件、非垃圾邮件和网络钓鱼诈骗的形式向 Microsoft 报告的内容。 有关详细信息, 请参阅[将垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。 相反, 您可以创建 Exchange 邮件流规则 (也称为传输规则), 以阻止用户将电子邮件发送给 Microsoft 进行分析, 并在自己的安全过程中使用它们。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

估计完成时间：5 分钟
  
您必须先获得权限，然后才能执行此过程或多个过程。 若要查看所需的权限, 请参阅邮件[策略和合规性权限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的 "邮件流规则" 条目和 "[客户端和移动设备权限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)" 主题中的 "Outlook on the web 邮箱策略" 条目。 
  
若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>使用 EAC 创建邮件流规则, 以查看用户的 "手动垃圾邮件"、"网络钓鱼" 和 "非垃圾邮件" 报告

1. 在 EAC 中, 导航到 "**邮件流** \> "**规则**。
    
2. 单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后选择 "**创建新规则**"。
    
3. 为该规则命名，然后单击“更多选项”****。
    
4. 在“应用此规则的条件”**** 下，选择“收件人”****，然后选择“地址包含这些词语中的任意词语”****。
    
5. 在“指定词语或短语”**** 框中，执行以下操作： 
    - 键入`abuse@messaging.microsoft.com` , 然后单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后`junk@office365.microsoft.com`键入并单击!["添加](media/ITPro-EAC-AddIcon.gif)图标"。 这些电子邮件地址用于向 Microsoft 提交假负邮件。
    - 键入`phish@office365.microsoft.com` , 然后单击!["添加](media/ITPro-EAC-AddIcon.gif)图标"。 此电子邮件地址用于将错过的网络钓鱼邮件提交给 Microsoft。
    - 键入`false_positive@messaging.microsoft.com` , 然后单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后`not_junk@office365.microsoft.com`键入并单击!["添加](media/ITPro-EAC-AddIcon.gif)图标"。 这些电子邮件地址用于向 Microsoft 提交误报邮件。
    - 单击“确定”****。
    
6. 在 "**执行以下操作**" 下, 选择 **"将邮件密件抄送给 ...** ", 然后选择您想要在其中接收邮件的邮箱。 
    
7. 如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。 我们建议首先在一段时间内测试规则，然后再强制应用。 请参阅[邮件流规则的过程](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)。 
    
8. 单击“保存”**** 按钮以保存规则。 它会出现在您的规则列表中。 
    
创建并强制执行规则后, 从您的组织发送到指定电子邮件地址的任何邮件都将被复制到指定的邮箱。
  


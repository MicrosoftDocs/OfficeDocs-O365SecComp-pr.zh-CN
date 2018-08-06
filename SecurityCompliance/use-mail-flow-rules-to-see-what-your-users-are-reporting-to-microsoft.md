---
title: 使用邮件流规则以查看您的用户都向 Microsoft 报告
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/23/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: 您可以创建 Exchange 传输规则以防止用户将电子邮件发送给 Microsoft 进行分析和在您自己的安全过程中使用它们
ms.openlocfilehash: f2376668e2a1a16eba9913178a100fc31763b227
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026769"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>使用邮件流规则以查看您的用户都向 Microsoft 报告

有多种方法可以将 false 的误报和假负邮件向 Microsoft 发送进行分析。作为管理员，您可以使用邮件流规则以查看哪些用户向 Microsoft 报告垃圾邮件、 非垃圾邮件和网络钓鱼诈骗。有关详细信息，请参阅[提交垃圾邮件和非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。相反，您可以创建 Exchange 传输规则以防止用户将电子邮件发送给 Microsoft 进行分析和在您自己的安全过程中使用它们。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，需要知道什么？
<a name="sectionSection0"> </a>

估计完成时间：5 分钟
  
您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Messaging 策略和遵从性 permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的"传输规则"条目和[客户端和移动设备权限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)主题中的"Outlook Web App 邮箱策略"条目。 
  
若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>使用 EAC 创建查看用户手动垃圾、 网络钓鱼和非垃圾邮件报告的邮件流规则
<a name="sectionSection1"> </a>

1. 在 EAC 中，导航到**邮件流** \> **规则**。
    
2. 单击![添加图标](media/ITPro-EAC-AddIcon.png)，然后选择**创建新规则**。
    
3. 为该规则指定一个名称，然后单击**更多选项**。
    
4. 在**以下情况应用此规则**，选择**收件人**，然后选择**地址中包含以下任何词语**。
    
5. 在**指定词语或短语**框中，执行以下操作： 
    - 键入**abuse@messaging.microsoft.com** ，然后单击![添加图标](media/ITPro-EAC-AddIcon.png)，然后键入**junk@office365.microsoft.com** ，然后单击![添加图标](media/ITPro-EAC-AddIcon.png)。这些电子邮件地址用于提交假负邮件给 Microsoft。
    - 键入**phish@office365.microsoft.com** ，然后单击![添加图标](media/ITPro-EAC-AddIcon.png)。此电子邮件地址用于提交错过网络钓鱼邮件提交给 Microsoft。
    - 键入**false_positive@messaging.microsoft.com** ，然后单击![添加图标](media/ITPro-EAC-AddIcon.png)，然后键入**not_junk@office365.microsoft.com** ，然后单击![添加图标](media/ITPro-EAC-AddIcon.png)。这些电子邮件地址用于提交误报邮件给 Microsoft。
    - 单击**确定**。
    
6. 在下，**执行以下操作**，选择**密件抄送邮件到...** ，然后，然后选择其中您想要的邮箱接收邮件。 
    
7. 如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。我们建议首先在一段时间内测试规则，然后再强制应用。[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)包含有关这些选择的详细信息。 
    
8. 单击**保存**按钮保存规则。显示在列表中的规则。 
    
创建和强制执行规则后，从您的组织发送到指定的电子邮件地址的任何邮件将复制到指定的邮箱。
  


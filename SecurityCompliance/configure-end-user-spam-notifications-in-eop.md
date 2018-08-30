---
title: 在 EOP 中配置最终用户垃圾邮件通知
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
description: 您可以针对默认的公司范围内内容筛选器策略或应用于域的自定义内容筛选器策略配置最终用户垃圾邮件通知。
ms.openlocfilehash: 990fa31cc22b33d235d6e8f106511996a52212a2
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002921"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a>在 EOP 中配置最终用户垃圾邮件通知
  
> [!IMPORTANT]
> 本主题适用于正在保护内部部署邮箱的 Exchange Online Protection (EOP) 独立客户。正在保护云托管的邮箱的 Exchange Online 客户应改为阅读以下主题：[配置最终用户垃圾邮件通知在 Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md)。 
  
您可以针对默认的公司范围内内容筛选器策略或应用于域的自定义内容筛选器策略配置最终用户垃圾邮件通知。启用最终用户垃圾邮件通知邮件可以使您的最终用户自己管理自己的垃圾邮件隔离邮件。最终用户垃圾邮件通知无法与应用于用户、组的策略或有例外情况的策略一起使用。
  
最终用户垃圾邮件通知包含最终用户在您所配置的时间段（您可以指定一个介于 1 到 15 天之间的值）内收到的所有垃圾邮件隔离邮件的列表。您还可以配置通知邮件的编写语言。
  
在收到通知邮件后，最终用户可以通过单击将垃圾电子邮件移动至收件箱，或将垃圾电子邮件报告为"非垃圾邮件"，在这种情况下，该邮件会被发送至 Microsoft 垃圾邮件分析团队。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，需要知道什么？
<a name="sectionSection0"> </a>

估计完成时间：5 分钟
  
您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](eop/feature-permissions-in-eop.md)主题中的"反垃圾邮件"条目。 
  
若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>使用 EAC 配置最终用户垃圾邮件通知

1. 在 Exchange 管理员中心 (EAC) 中，导航到**保护** \> **内容筛选器**。
    
2. 选择您想要启用最终用户垃圾邮件通知（默认禁用）的内容筛选器策略。
    
3. 在右窗格中，其中显示有关您的策略的摘要信息，请单击**配置最终用户垃圾邮件通知**链接。 
    
4. 在随后出现的对话框中，您可以配置以下选项：
    
1. **启用最终用户垃圾邮件通知**选中此复选框以启用此策略的最终用户垃圾邮件通知。（相反，如果启用此策略，则您可以清除此复选框以禁用此策略的最终用户垃圾邮件通知。） 
    
2. **发送最终用户垃圾邮件通知每 （天）** 指定频率发送最终用户垃圾邮件通知。默认值为 3 天。您可以指定介于 1 到 15 天之间。如果您指定为 7 天，例如，通知将包含的所有邮件发送到垃圾邮件隔离改为在过去 7 天内供该用户的列表。 
    
3. **通知语言**使用下拉列表，选择编写此策略的最终用户垃圾邮件通知的语言。 
    
5. 单击**保存**。在右窗格中显示的内容筛选器策略设置，包括您的最终用户垃圾邮件通知设置摘要。
    
> [!NOTE]
>  最终用户垃圾邮件通知只对已启用的内容筛选器策略可用。 >  每天只发送一次最终用户垃圾邮件通知。无法保证和配置任何特定客户的通知发送时间。 
  
 **提示：** 如果您想要通过完全实现它们之前将其发送到一组有限的用户来测试最终用户垃圾邮件通知，创建自定义内容筛选器策略，用户驻留在其中的域的最终用户垃圾邮件通知。然后，在 EAC 中，在**邮件流\>规则**，创建传输规则阻止邮件从 quarantine@messaging.microsoft.com （发送通知的电子邮件地址） 与您想要接收通知的用户的例外。下图是从域 Contoso.com 创建两个用户 （SaraD 和 AlexD） 的异常的示例： 
  
![测试最终用户垃圾邮件通知的传输规则](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>详细信息

[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)
  

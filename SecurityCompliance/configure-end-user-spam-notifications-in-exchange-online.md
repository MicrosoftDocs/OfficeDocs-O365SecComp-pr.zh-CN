---
title: Exchange Online 中配置最终用户垃圾邮件通知
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
description: 您可以针对默认的公司范围内内容筛选器策略或应用于域的自定义内容筛选器策略配置最终用户垃圾邮件通知。
ms.openlocfilehash: e29cc850b7f91ed4ec963a8e52e40a0044fa7f6c
ms.sourcegitcommit: 234a22c61859133ed5e7988a9551a569781518a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23875804"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Exchange Online 中配置最终用户垃圾邮件通知

> [!IMPORTANT]
> 本主题适用于 Exchange Online 客户正在保护云托管的邮箱。正在保护内部部署邮箱的 Exchange Online Protection (EOP) 独立客户应改为阅读以下主题：[在 EOP 中的配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-eop.md)。 
  
您可以针对默认的公司范围内内容筛选器策略或应用于域的自定义内容筛选器策略配置最终用户垃圾邮件通知。启用最终用户垃圾邮件通知邮件可以使您的最终用户自己管理自己的垃圾邮件隔离邮件。最终用户垃圾邮件通知无法与应用于用户、组的策略或有例外情况的策略一起使用。
  
最终用户垃圾邮件通知包含最终用户在您所配置的时间段（您可以指定一个介于 1 到 15 天之间的值）内收到的所有垃圾邮件隔离邮件的列表。您还可以配置通知邮件的编写语言。
  
在收到一封通知邮件，最终用户可以选择以下选项：

**预览**邮件如果您想要预览的内容或之前采取操作的标头。

**下载**如果您想要在您的设备之前采取操作时，（如果有） 查看消息和附件的邮件。

**版本**如果邮件不是垃圾邮件，并且您希望 Office 365 邮件发送给您的邮箱。

**发行版和允许的发件人**如果邮件不是垃圾邮件，并且您希望 Office 365 将发件人添加到您的安全发件人和将来的电子邮件的收件人列表。请记住，您的管理员可能必须覆盖安全发件人列表的其他组织范围允许/阻止配置。

**发布和报告**、 如果邮件不是垃圾邮件和您想要将邮件发送到您的邮箱并将其报告给 Microsoft 进行分析。

**阻止**如果您希望 Office 365 将发件人添加到阻止的发件人列表。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

估计完成时间：2 分钟
  
您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的"反垃圾邮件"条目。 
  
若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
  
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
  

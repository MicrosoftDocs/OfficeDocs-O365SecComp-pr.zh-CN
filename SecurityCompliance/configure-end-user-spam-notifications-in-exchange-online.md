---
title: 在 Exchange Online 中配置最终用户垃圾邮件通知
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: 您可以为适用于域的默认公司范围的垃圾邮件筛选器策略或自定义垃圾邮件筛选器策略配置最终用户垃圾邮件通知。
ms.openlocfilehash: e3e5ce044879318dab55f5d08ec2ee0e3379dfb2
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341363"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>在 Exchange Online 中配置最终用户垃圾邮件通知

> [!IMPORTANT]
> 本主题适用于正在保护云托管邮箱的 Exchange Online 客户。Exchange Online Protection (EOP) 保护本地邮箱的独立客户应阅读以下主题:[在 EOP 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-eop.md)。 
  
您可以为适用于域的默认公司范围的垃圾邮件筛选器策略或自定义垃圾邮件筛选器策略配置最终用户垃圾邮件通知。启用最终用户垃圾邮件通知可让最终用户自行管理自己的垃圾邮件隔离邮件。最终用户垃圾邮件通知不能与应用于用户或组的策略一起使用, 也不能用于有例外的策略。
  
最终用户垃圾邮件通知包含最终用户在您所配置的时间段（您可以指定一个介于 1 到 15 天之间的值）内收到的所有垃圾邮件隔离邮件的列表。您还可以配置通知邮件的编写语言。
  
收到通知邮件后, 最终用户可以从以下选项中进行选择:

如果要在执行操作之前预览内容或标题, 请**预览**邮件。

如果要在执行操作之前查看设备上的邮件和附件 (如果有), 请**下载**邮件。

如果邮件不是垃圾邮件, 并且您希望 Office 365 将邮件发送到您的邮箱, 则**释放**。

**发布 &** 如果邮件不是垃圾邮件, 并且您希望 Office 365 将发件人添加到安全发件人和收件人列表中, 以供将来的电子邮件。请注意, 您的管理员可能有其他组织范围的允许/阻止配置替代安全发件人列表。

**发布 & 报告**, 如果邮件不是垃圾邮件, 并且您想要将邮件发送到您的邮箱并将其报告给 Microsoft 进行分析。

如果您希望 Office 365 将发件人添加到阻止发件人列表, 则**阻止**。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

估计完成时间：2 分钟
  
您需要先分配权限, 然后才能执行此过程或过程。若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的 "反垃圾邮件" 条目。 
  
若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>使用 EAC 配置最终用户垃圾邮件通知

1. 在 Exchange 管理中心 (EAC) 中, 导航到 "**保护** \> **垃圾邮件筛选器**"。
    
2. 选择要为其启用最终用户垃圾邮件通知的垃圾邮件筛选器策略 (默认情况下禁用)。
    
3. 在右侧窗格中显示策略的摘要信息的位置, 单击 "**配置最终用户垃圾邮件通知**" 链接。 
    
4. 在随后出现的对话框中，您可以配置以下选项：
    
1. **启用最终用户垃圾邮件通知**选中此复选框, 以便为此策略启用最终用户垃圾邮件通知。(相反, 如果启用此策略, 则可以清除此复选框, 以便为此策略禁用最终用户垃圾邮件通知。) 
    
2. **每隔 (天) 发送最终用户垃圾邮件通知**指定发送最终用户垃圾邮件通知的频率。默认值为3天。可以指定1到15天。例如, 如果指定7天, 则通知将在过去7天内发送到垃圾邮件隔离的所有邮件的列表中包含为该用户预定的所有邮件。 
    
3. **通知语言**使用下拉列表, 选择为此策略编写最终用户垃圾邮件通知所使用的语言。 
    
5. 单击 "**保存**"。在右侧窗格中将显示垃圾邮件筛选器策略设置的摘要, 包括您的最终用户垃圾邮件通知设置。
    
> [!NOTE]
>  最终用户垃圾邮件通知将仅适用于启用的垃圾邮件筛选器策略。> 最终用户垃圾邮件通知每天仅发送一次。无法保证任何特定客户的通知传递时间, 并且不可配置。 
  
 **提示:** 如果要在完全实现最终用户垃圾邮件通知之前将其发送给一组有限的用户, 请创建自定义垃圾邮件筛选器策略, 为用户驻留的域启用最终用户垃圾邮件通知。然后, 在 EAC 中的 "**邮件流\>规则**" 下, 创建邮件流规则 (也称为 "传输规则"), 以阻止来自 quarantine@messaging.microsoft.com 的邮件 (发送通知的电子邮件地址), 并对所需的用户例外。以接收通知。下面的图像是一个为来自 domain Contoso.com 的两个用户 (SaraD 和 AlexD) 创建异常的示例: 
  
![测试最终用户垃圾邮件通知的传输规则](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>详细信息

[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)
  

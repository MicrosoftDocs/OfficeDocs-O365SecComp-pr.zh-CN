---
title: 在 EOP 中配置最终用户垃圾邮件通知
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: 您可以针对默认的公司范围内内容筛选器策略或应用于域的自定义内容筛选器策略配置最终用户垃圾邮件通知。
ms.openlocfilehash: 07bca81f06a347bbce5e997e570553f85deb5c1d
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151454"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a>在 EOP 中配置最终用户垃圾邮件通知
  
> [!IMPORTANT]
> 该主题适用于要保护本地邮箱的 Exchange Online Protection (EOP) 独立客户。 正在保护云托管邮箱的 Exchange Online 客户应阅读以下主题:[在 Exchange Online 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-exchange-online.md)。 
  
您可以针对默认的公司范围内内容筛选器策略或应用于域的自定义内容筛选器策略配置最终用户垃圾邮件通知。启用最终用户垃圾邮件通知邮件可以使您的最终用户自己管理自己的垃圾邮件隔离邮件。最终用户垃圾邮件通知无法与应用于用户、组的策略或有例外情况的策略一起使用。
  
最终用户垃圾邮件通知包含最终用户在您所配置的时间段（您可以指定一个介于 1 到 15 天之间的值）内收到的所有垃圾邮件隔离邮件的列表。您还可以配置通知邮件的编写语言。
  
收到通知邮件后, 最终用户可以从以下选项中进行选择:

如果要在执行操作之前预览内容或标题, 请**预览**邮件。

如果要在执行操作之前查看设备上的邮件和附件 (如果有), 请**下载**邮件。

如果邮件不是垃圾邮件, 并且您希望 Office 365 将邮件发送到您的邮箱, 则**释放**。

**发布 &** 如果邮件不是垃圾邮件, 并且您希望 Office 365 将发件人添加到安全发件人和收件人列表中, 以供将来的电子邮件。 请注意, 您的管理员可能有其他组织范围的允许/阻止配置替代安全发件人列表。

**发布 _AMP_ 报告**, 如果邮件不是垃圾邮件, 并且您想要将邮件发送到您的邮箱并将其报告给 Microsoft 进行分析。

如果您希望 Office 365 将发件人添加到阻止发件人列表, 则**阻止**。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？
<a name="sectionSection0"> </a>

估计完成时间：5 分钟
  
您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](eop/feature-permissions-in-eop.md)主题中的"反垃圾邮件"条目。 
  
若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>使用 EAC 配置最终用户垃圾邮件通知

1. 在 Exchange 管理中心 (EAC) 中, 导航到 "**保护** \> **内容筛选器**"。
    
2. 选择您想要启用最终用户垃圾邮件通知（默认禁用）的内容筛选器策略。
    
3. 在显示您的策略摘要信息的右窗格中，单击“配置最终用户垃圾邮件通知”**** 链接。 
    
4. 在随后出现的对话框中，您可以配置以下选项：
    
1. **启用最终用户垃圾邮件通知**选中此复选框, 以便为此策略启用最终用户垃圾邮件通知。 ） 
    
2. **每隔 (天) 发送最终用户垃圾邮件通知**指定发送最终用户垃圾邮件通知的频率。 默认值为 3 天。 您可以指定一个介于 1 到 15 天之间的值。 例如，如果您指定 7 天，则该通知将包括在过去 7 天内预期发送给该用户但实际发送到垃圾邮件隔离邮箱的所有邮件列表。 
    
3. **通知语言**使用下拉列表, 选择为此策略编写最终用户垃圾邮件通知所使用的语言。 
    
5. 单击“保存”****。 右窗格中将显示内容筛选器策略设置的摘要，包括您的最终用户垃圾邮件通知设置。
    
> [!NOTE]
>  最终用户垃圾邮件通知只对已启用的内容筛选器策略可用。 >  每天只发送一次最终用户垃圾邮件通知。无法保证和配置任何特定客户的通知发送时间。 
  
 **提示:** 如果要在完全实现最终用户垃圾邮件通知之前将其发送给一组有限的用户, 请创建自定义内容筛选器策略, 为用户驻留的域启用最终用户垃圾邮件通知。 然后, 在 EAC 中的 "**邮件流\>规则**" 下, 创建邮件流规则 (也称为 "传输规则"), 以阻止来自 quarantine@messaging.microsoft.com 的邮件 (发送通知的电子邮件地址), 并对所需的用户例外。以接收通知。 下图是为 Contoso.com 域中的两个用户（SaraD 和 AlexD）创建一个异常的示例： 
  
![测试最终用户垃圾邮件通知的传输规则](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>详细信息

[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)
  

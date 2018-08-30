---
title: 零时差自动清除 - 防范垃圾邮件和恶意软件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/9/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: 零时差自动清除 (ZAP) 是一个检测到的已发送到用户的收件箱，垃圾邮件或恶意软件的邮件的电子邮件保护功能，然后呈现恶意内容权衡。ZAP 原理这取决于检测到的恶意内容类型。
ms.openlocfilehash: dc8901dc7c1db5b323ccbeee610647b8a302fcb3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525008"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>零时差自动清除 - 防范垃圾邮件和恶意软件

零时差自动清除 (ZAP) 是一个检测到的已发送到用户的收件箱，垃圾邮件或恶意软件的邮件的电子邮件保护功能，然后呈现恶意内容权衡。ZAP 原理这取决于检测到的恶意内容类型。
  
默认值是包含任何 Office 365 订阅包含 Exchange Online 邮箱的 Exchange Online Protection 提供 ZAP。
  
## <a name="how-does-zap-work"></a>ZAP 如何工作？

Office 365 更新中的反垃圾邮件引擎和恶意软件签名实时每天。但是，用户可能仍获取恶意邮件传递到各种原因，包括何时内容已 weaponized 一次后第一次传递到用户的收件箱。将清除的地址这通过不断监视更新到 Office 365 垃圾邮件和恶意软件签名，并可以因此查找和收件箱中已删除之前已发送的邮件。已被标识为垃圾邮件的邮件，ZAP 将未读的邮件移动到用户的垃圾邮件文件夹。为新检测到恶意软件、 ZAP 从电子邮件，而不管是否已读取邮件，或不删除附件。相反的以前正确分类为恶意邮件的邮件，则返回 true。
  
ZAP 操作是无缝邮箱用户，他或她不通知邮件已被移动。
  
允许列表、[邮件流规则](https://go.microsoft.com/fwlink/p/?LinkId=722755)和最终用户规则或其他筛选器优先于 ZAP。
  
 **本文内容：**
  
> [设置垃圾邮件筛选器策略](zero-hour-auto-purge.md#BK_SetSpam)
    
> [请参阅 ZAP 是否移动消息](zero-hour-auto-purge.md#BK_DidZAPMove)
    
> [禁用 ZAP](zero-hour-auto-purge.md#BK_Posh)
    
> [常见问题解答](zero-hour-auto-purge.md#BK_FAQ)
    
## <a name="working-with-zap"></a>使用 ZAP

ZAP 已打开默认情况下，但您需要确保满足两个条件：
  
- 垃圾邮件筛选器策略设置为[移动到垃圾邮件文件夹的邮件](zero-hour-auto-purge.md#BK_SetSpam)。
    
    您还可以创建仅适用于一组用户如果您不希望通过 ZAP 屏蔽所有邮箱的新垃圾邮件筛选器策略。
    
- 用户的[选项\>垃圾邮件](https://support.office.com/article/068FA430-F8D7-4518-A8DA-8BC74958F05F)。
    
如果要[查看 ZAP 如果移动消息](zero-hour-auto-purge.md#BK_DidZAPMove)，您可以使用 Exchange Online 邮件跟踪工具。
  
管理员还可以[禁用 ZAP](zero-hour-auto-purge.md#BK_Posh)使用 PowerShell。 
  
 **将垃圾邮件筛选器策略设置**
  
1. 登录到[从何处登录到 Office 365 的业务](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)和选择**保护** \> **垃圾邮件筛选器**。 
    
    ![在 EAC 中，选择保护，然后垃圾邮件筛选器](media/0463c879-63fa-4a6c-9b03-e980d5ef3954.PNG)
  
2. 选择您想要调整的筛选器策略，或选择**添加**![添加图标](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)创建一个新。 
    
    在以前的屏幕截图，策略名为"Default"，但如果创建额外的垃圾邮件筛选器策略您可以为其提供一个不同的名称。此外可以将策略应用于仅一组有限的用户。
    
3. 在策略窗口中，选择**垃圾邮件和批量操作**，并确保**垃圾邮件**被设置为**将邮件移至垃圾邮件文件夹**。 
    
    如果您选择**保存**，将策略应用于 Office 365 租户。 
    
    ![设置垃圾邮件和批量 Mpve 邮件到垃圾邮件文件夹的操作](media/4332cfb3-89e1-48ba-8da8-9286f2fa1089.PNG)
  
4. 如果您创建新策略，并且想要将策略应用于一组的用户，滚动到**应用于**部分和菜单控件中策略筛选窗口中，选择**收件人**、**域**或**组成员身份**您要应用该策略。您还可以设置其他条件和例外。 
    
    ![在应用于部分中，选择收件人](media/19ca10db-c0f4-432c-b3de-ad4101a23de6.PNG)
  
    选择**保存**以将策略应用于所选用户。 
    
 **若要查看 ZAP 是否移动消息**
  
- 可以使用[查找和修复为业务管理 Office 365 的电子邮件传递问题](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6)来确定邮件是否已通过 ZAP 移动： 
    
    查看您的跟踪详细信息，以确定一条消息，已通过 ZAP 移动中的文本"零时差自动清除 (ZAP)"。
    
 **若要禁用 ZAP**
  
- 如果您想要禁用的 Office 365 租户，将清除或一组用户，使用[Set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)，EOP cmdlet 的**ZapEnabled**参数。
    
    在以下示例中，名为"Test"的内容筛选器策略禁用 ZAP。
    
||
|:-----|
|
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

|
   
## <a name="faq"></a>常见问题解答
<a name="BK_FAQ"> </a>

 **如果合法邮件移动到垃圾邮件文件夹，则会发生什么情况？**
  
您应遵循的误报报告的常规过程。应为邮件将从收件箱移动到垃圾邮件文件夹的唯一原因，因为该服务已确定的消息是垃圾邮件或恶意。
  
 **如果使用 Office 365 隔离而不是垃圾邮件文件夹？**
  
ZAP 不将邮件移动到隔离收件箱这一次。
  
 **如果我有自定义邮件流规则 （阻止 / 允许规则）？**
  
由管理员 （邮件流规则） 或阻止和允许规则创建的规则的优先级。此类邮件将排除在功能条件。
  
## <a name="related-topics"></a>相关主题
<a name="BK_FAQ"> </a>

[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)
  
[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](block-email-spam-to-prevent-false-negatives.md)
  


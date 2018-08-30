---
title: Exchange Online 中的安全发件人和阻止发件人列表
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
description: 作为 Exchange Online 或 Exchange Online Protection (EOP) 管理员，你可以帮助确保通过服务传递的电子邮件不会被标记为垃圾邮件。实现上述任务的一种方法是为组织中的人员创建白名单和黑名单。
ms.openlocfilehash: cbf886bdcc40044a31b285b6806aecbc95f0f97c
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003101"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Exchange Online 中的安全发件人和阻止发件人列表

作为 Exchange Online 或 Exchange Online Protection (EOP) 管理员，你可以帮助确保通过服务传递的电子邮件不会被标记为垃圾邮件。实现上述任务的一种方法是为组织中的人员创建白名单和黑名单。 
  
 *有关作为管理员使用这些名单的更新提示和过程，请参阅* [使用安全列表或其他技术防止误报电子邮件被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkID=534224)。 
  
如果你不是管理员，并且你只想使用一个白名单管理你在 Outlook 中的垃圾邮件，请查看此[垃圾邮件筛选器](https://go.microsoft.com/fwlink/?LinkId=817222)概述中的步骤。 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Exchange Online 中的安全发件人限制和阻止发件人限制是什么？

Exchange Online 中的安全发件人限制和阻止发件人限制与 Active Directory 和 Outlook 限制不同。区别在于：
  
- 安全发件人限制： 1024
    
- 阻止发件人限制： 500
    
注意：
  
您可能遇到的错误的所述 KB 2590466 （"会收到错误"垃圾电子邮件验证错误"Outlook Web App 中的 Exchange Server 2010"）。若要解决此问题，请清除"信任来自我的联系人的电子邮件"复选框。此外，减少的是在默认联系人文件夹将其放在允许的最大限制 1024 个在 Exchange Online 设置为"MaxSafeSenders"属性的电子邮件地址。有关此属性并使用 Set-mailbox cmdlet 的详细信息，seethe 以下主题：
  
[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox?view=exchange-ps)
  
## <a name="see-also"></a>See also

[Sender filtering in Exchange 2016](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)


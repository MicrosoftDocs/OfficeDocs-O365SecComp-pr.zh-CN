---
title: Exchange Online 中的安全发件人和阻止发件人列表
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: 作为 Exchange Online 或 Exchange Online Protection (EOP) 管理员，你可以帮助确保通过服务传递的电子邮件不会被标记为垃圾邮件。实现上述任务的一种方法是为组织中的人员创建白名单和黑名单。
ms.openlocfilehash: 11ae38733418bb0842732978512698ca6a6274fd
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692221"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Exchange Online 中的安全发件人和阻止发件人列表

作为 Exchange Online 或 Exchange Online Protection (EOP) 管理员，你可以帮助确保通过服务传递的电子邮件不会被标记为垃圾邮件。实现上述任务的一种方法是为组织中的人员创建白名单和黑名单。 
  
 *有关作为管理员使用这些名单的更新提示和过程，请参阅* [使用安全列表或其他技术防止误报电子邮件被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkID=534224)。 
  
如果你不是管理员，并且你只想使用一个白名单管理你在 Outlook 中的垃圾邮件，请查看此[垃圾邮件筛选器](https://go.microsoft.com/fwlink/?LinkId=817222)概述中的步骤。 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Exchange Online 中的安全发件人限制和阻止发件人限制是什么？

Exchange Online 中的安全发件人限制和阻止发件人限制与 Active Directory 和 Outlook 限制不同。区别在于：
  
- 安全发件人限制: 1024
    
- 阻止的发件人限制: 500
    
注意：
  
您可能会遇到[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)中所述的错误。 若要解决此问题, 请清除 "信任来自我的联系人的电子邮件" 复选框。 或者, 减少默认 "联系人" 文件夹中的电子邮件地址量, 使其在 Exchange Online 中为 "MaxSafeSenders" 属性设置的最大允许限制为1024。 有关此属性和 Set 邮箱 cmdlet 的详细信息, 请 seethe 以下主题:
  
[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
## <a name="see-also"></a>另请参阅

[Sender filtering in Exchange 2016](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)


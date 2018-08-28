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
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
description: 作为 Exchange Online 或 Exchange Online Protection (EOP) 管理员，你可以帮助确保通过服务传递的电子邮件不会被标记为垃圾邮件。实现上述任务的一种方法是为组织中的人员创建白名单和黑名单。
ms.openlocfilehash: fcb43f990750782788dc6f459dd5c7d296146a38
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22028079"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="3dee5-104">Exchange Online 中的安全发件人和阻止发件人列表</span><span class="sxs-lookup"><span data-stu-id="3dee5-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="3dee5-p102">作为 Exchange Online 或 Exchange Online Protection (EOP) 管理员，你可以帮助确保通过服务传递的电子邮件不会被标记为垃圾邮件。实现上述任务的一种方法是为组织中的人员创建白名单和黑名单。</span><span class="sxs-lookup"><span data-stu-id="3dee5-p102">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam. One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span> 
  
 <span data-ttu-id="3dee5-107">*有关作为管理员使用这些名单的更新提示和过程，请参阅* [使用安全列表或其他技术防止误报电子邮件被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkID=534224)。</span><span class="sxs-lookup"><span data-stu-id="3dee5-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [Prevent false positive email marked as spam with a safelist or other techniques](https://go.microsoft.com/fwlink/p/?LinkID=534224).</span></span> 
  
<span data-ttu-id="3dee5-108">如果你不是管理员，并且你只想使用一个白名单管理你在 Outlook 中的垃圾邮件，请查看此[垃圾邮件筛选器](https://go.microsoft.com/fwlink/?LinkId=817222)概述中的步骤。</span><span class="sxs-lookup"><span data-stu-id="3dee5-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in this overview of [the Junk Email Filter](https://go.microsoft.com/fwlink/?LinkId=817222).</span></span> 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="3dee5-109">Exchange Online 中的安全发件人限制和阻止发件人限制是什么？</span><span class="sxs-lookup"><span data-stu-id="3dee5-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="3dee5-p103">Exchange Online 中的安全发件人限制和阻止发件人限制与 Active Directory 和 Outlook 限制不同。区别在于：</span><span class="sxs-lookup"><span data-stu-id="3dee5-p103">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits. They are:</span></span>
  
- <span data-ttu-id="3dee5-112">安全发件人限制： 1024</span><span class="sxs-lookup"><span data-stu-id="3dee5-112">Safe sender limit: 1,024</span></span>
    
- <span data-ttu-id="3dee5-113">阻止发件人限制： 500</span><span class="sxs-lookup"><span data-stu-id="3dee5-113">Blocked sender limit: 500</span></span>
    
<span data-ttu-id="3dee5-114">注意：</span><span class="sxs-lookup"><span data-stu-id="3dee5-114">Note:</span></span>
  
<span data-ttu-id="3dee5-p104">您可能遇到的错误的所述 KB 2590466 （"会收到错误"垃圾电子邮件验证错误"Outlook Web App 中的 Exchange Server 2010"）。若要解决此问题，请清除"信任来自我的联系人的电子邮件"复选框。此外，减少的是在默认联系人文件夹将其放在允许的最大限制 1024 个在 Exchange Online 设置为"MaxSafeSenders"属性的电子邮件地址。有关此属性并使用 Set-mailbox cmdlet 的详细信息，seethe 以下主题：</span><span class="sxs-lookup"><span data-stu-id="3dee5-p104">You may experience the error that is described in KB 2590466 ("You receive the error "Junk e-mail validation error" in Outlook Web App for Exchange Server 2010"). To resolve this issue, clear the "Trust emails from my contacts" check box. Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1,024 in Exchange Online that is set for "MaxSafeSenders" attribute. For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>
  
[<span data-ttu-id="3dee5-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="3dee5-119">Set-Mailbox</span></span>](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/Set-Mailbox?view=exchange-ps)
  
## <a name="see-also"></a><span data-ttu-id="3dee5-120">See also</span><span class="sxs-lookup"><span data-stu-id="3dee5-120">See also</span></span>

[<span data-ttu-id="3dee5-121">Sender filtering in Exchange 2016</span><span class="sxs-lookup"><span data-stu-id="3dee5-121">Sender filtering in Exchange 2016</span></span>](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

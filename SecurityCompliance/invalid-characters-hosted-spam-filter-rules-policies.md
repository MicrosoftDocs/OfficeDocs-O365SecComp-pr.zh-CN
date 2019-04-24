---
title: 避免垃圾邮件筛选器规则和垃圾邮件筛选器策略中的无效字符
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 9/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 为在反垃圾邮件配置中具有无效字符的管理员提供帮助, 并在尝试使用安全&amp;合规性中心时遇到问题。
ms.openlocfilehash: 797389da26823b6528c2aee0baaa118fbfcf7942
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253950"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="099b9-103">避免垃圾邮件筛选器规则和垃圾邮件筛选器策略中的无效字符</span><span class="sxs-lookup"><span data-stu-id="099b9-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="099b9-104">以前, Office 365 管理员使用 Exchange 管理中心 (EAC) 设置和配置了垃圾邮件筛选器规则和垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="099b9-104">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange admin center (EAC).</span></span> <span data-ttu-id="099b9-105">现在, 您可以使用安全&amp;合规性中心管理您的反垃圾邮件配置。</span><span class="sxs-lookup"><span data-stu-id="099b9-105">Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration.</span></span> <span data-ttu-id="099b9-106">以下字符在 EAC 中受支持, 但不支持在安全&amp;合规性中心中使用。</span><span class="sxs-lookup"><span data-stu-id="099b9-106">The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="099b9-107">**无效字符:**</span><span class="sxs-lookup"><span data-stu-id="099b9-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="099b9-108">如果垃圾邮件筛选器规则或垃圾邮件筛选器策略包含任何无效字符, 则可能会遇到以下任何或所有问题:</span><span class="sxs-lookup"><span data-stu-id="099b9-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="099b9-109">您可能无法在安全&amp;合规中心中找到策略或规则。</span><span class="sxs-lookup"><span data-stu-id="099b9-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="099b9-110">尝试使用 Windows PowerShell 获取规则或策略时, 可能会收到错误。</span><span class="sxs-lookup"><span data-stu-id="099b9-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="099b9-111">您可能会发现策略或设置未按预期方式运行或执行。</span><span class="sxs-lookup"><span data-stu-id="099b9-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="099b9-112">删除垃圾邮件筛选器策略和规则中的无效字符</span><span class="sxs-lookup"><span data-stu-id="099b9-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="099b9-113">在确定了包含无效字符的策略和规则后, 可以使用 Windows PowerShell cmdlet 更改这些名称。</span><span class="sxs-lookup"><span data-stu-id="099b9-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="099b9-114">[使用远程 PowerShell 连接到 Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="099b9-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="099b9-115">若要更改垃圾邮件筛选器策略的名称, 请运行 set-hostedcontentfilterpolicy cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="099b9-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="099b9-116">若要更改垃圾邮件筛选器规则的名称, 请运行 disable-hostedcontentfilterrule cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="099b9-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="099b9-117">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="099b9-117">For more information</span></span>

[<span data-ttu-id="099b9-118">安全&amp;合规性中心中的威胁管理</span><span class="sxs-lookup"><span data-stu-id="099b9-118">Threat management in the Security &amp; Compliance Center</span></span>](threat-management.md)
  
[<span data-ttu-id="099b9-119">set-hostedcontentfilterpolicy</span><span class="sxs-lookup"><span data-stu-id="099b9-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[<span data-ttu-id="099b9-120">disable-hostedcontentfilterrule</span><span class="sxs-lookup"><span data-stu-id="099b9-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)

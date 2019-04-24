---
title: 关闭 web 上的 Outlook 中的垃圾邮件报告
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: 作为 Office 365 管理员, 您可以关闭用户将电子邮件报告为垃圾邮件的功能。
ms.openlocfilehash: f3e8a8cf837e7923d3c7241852ab2acd375492b8
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264164"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="80fb1-103">关闭 web 上的 Outlook 中的垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="80fb1-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="80fb1-104">您可以使用 web 上的 outlook (以前称为 "outlook web App") 垃圾邮件报告选项, 将垃圾邮件、网络钓鱼邮件和非垃圾邮件发送给 Microsoft 进行分析, 如在[outlook 网页版中报告垃圾电子邮件和网络钓鱼诈骗](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="80fb1-104">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span> <span data-ttu-id="80fb1-105">如果不想使用这些选项, 管理员可以通过[set-owamailboxpolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet 将其关闭。</span><span class="sxs-lookup"><span data-stu-id="80fb1-105">If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="80fb1-106">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="80fb1-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="80fb1-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="80fb1-107"></span></span>

- <span data-ttu-id="80fb1-108">估计完成时间：5 分钟</span><span class="sxs-lookup"><span data-stu-id="80fb1-108">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="80fb1-109">您必须先获得权限，然后才能执行此过程或多个过程。</span><span class="sxs-lookup"><span data-stu-id="80fb1-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="80fb1-110">若要查看所需的权限, 请参阅[web 权限](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp)主题中的 "outlook on the web 邮箱策略" 条目。</span><span class="sxs-lookup"><span data-stu-id="80fb1-110">To see what permissions you need, see the "Outlook on the web mailbox policies" entry in the [Outlook on the web permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) topic.</span></span> 

- <span data-ttu-id="80fb1-111">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="80fb1-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="80fb1-112">关闭对 Microsoft 的垃圾邮件、网络钓鱼和非垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="80fb1-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="80fb1-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="80fb1-113"></span></span>

<span data-ttu-id="80fb1-114">首先, 运行以下命令以获取您的可用 Outlook 在 web 邮箱策略上的名称:</span><span class="sxs-lookup"><span data-stu-id="80fb1-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>
  
```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="80fb1-115">接下来, 使用以下语法在 web 上的 Outlook 中对 Microsoft 启用或禁用垃圾邮件和非垃圾邮件报告:</span><span class="sxs-lookup"><span data-stu-id="80fb1-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="80fb1-116">本示例将关闭默认 Outlook web app 邮箱策略中的报告功能:</span><span class="sxs-lookup"><span data-stu-id="80fb1-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="80fb1-117">有关语法和参数的详细信息, 请参阅[set-owamailboxpolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx)和[set-owamailboxpolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)。</span><span class="sxs-lookup"><span data-stu-id="80fb1-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) and [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="80fb1-118">您如何知道这有效？</span><span class="sxs-lookup"><span data-stu-id="80fb1-118">How do you know this worked?</span></span>
<span data-ttu-id="80fb1-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="80fb1-119"></span></span>

<span data-ttu-id="80fb1-120">运行**set-owamailboxpolicy**以检查参数值, 然后在 web 上为受影响的用户 (已对其应用 outlook 网页邮箱策略) 打开 Outlook, 并验证报告垃圾邮件、网络钓鱼邮件和非垃圾邮件的选项是否不可用。</span><span class="sxs-lookup"><span data-stu-id="80fb1-120">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available.</span></span> <span data-ttu-id="80fb1-121">您仍可以将邮件标记为垃圾邮件、网络钓鱼邮件, 而不能将其报告为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="80fb1-121">You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span> 

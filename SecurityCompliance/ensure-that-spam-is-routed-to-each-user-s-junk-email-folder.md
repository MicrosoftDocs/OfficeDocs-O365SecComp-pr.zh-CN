---
title: 确保垃圾邮件已路由到每个用户的“垃圾邮件”文件夹
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何将垃圾邮件路由到 Exchange Online Protection 中的用户垃圾邮件文件夹。
ms.openlocfilehash: 390ba26167521ccea7b69e7fac21924c0b9ec7de
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153206"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="59d5c-103">确保垃圾邮件已路由到每个用户的“垃圾邮件”文件夹</span><span class="sxs-lookup"><span data-stu-id="59d5c-103">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59d5c-104">本主题仅适用于在混合部署中承载本地邮箱的 Exchange Online Protection (EOP) 客户。</span><span class="sxs-lookup"><span data-stu-id="59d5c-104">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment.</span></span> <span data-ttu-id="59d5c-105">其邮箱在 Office 365 中完全托管的 Exchange Online 客户无需运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="59d5c-105">Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span> 
  
<span data-ttu-id="59d5c-106">EOP 客户的默认反垃圾邮件操作是将垃圾邮件移到收件人的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="59d5c-106">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder.</span></span> <span data-ttu-id="59d5c-107">为了使此操作能够与本地邮箱配合使用, 必须在本地边缘或中心服务器上配置 Exchange 邮件流规则 (也称为传输规则), 以检测由 EOP 添加的垃圾邮件头。</span><span class="sxs-lookup"><span data-stu-id="59d5c-107">In order for this action to work with on-premises mailboxes, you must configure Exchange mail flow rules (also known as transport rules) on your on-premises Edge or Hub servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="59d5c-108">这些邮件流规则将 Set-organizationconfig cmdlet 的 SclJunkThreshold 属性使用的垃圾邮件可信度 (SCL) 设置为将垃圾邮件移到每个邮箱的 "垃圾邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="59d5c-108">These mail flow rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span> 
  
### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="59d5c-109">添加邮件流规则, 以确保使用 Windows PowerShell 将垃圾邮件移动到 "垃圾邮件" 文件夹</span><span class="sxs-lookup"><span data-stu-id="59d5c-109">To add mail flow rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="59d5c-110">访问内部部署 Exchange 服务器的 Exchange 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="59d5c-110">Access the Exchange Management Shell for your on-premises Exchange server.</span></span> <span data-ttu-id="59d5c-111">若要了解如何在本地 Exchange 组织中打开 Exchange 命令行管理程序，请参阅 **Open the Shell**。</span><span class="sxs-lookup"><span data-stu-id="59d5c-111">To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>
    
2. <span data-ttu-id="59d5c-112">运行以下命令以将内容经过筛选的垃圾邮件路由到垃圾邮件文件夹：</span><span class="sxs-lookup"><span data-stu-id="59d5c-112">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    <span data-ttu-id="59d5c-113">其中_NameForRule_是新规则的名称, 例如, JunkContentFilteredMail。</span><span class="sxs-lookup"><span data-stu-id="59d5c-113">Where  _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span> 
    
3. <span data-ttu-id="59d5c-114">运行以下命令以将在到达内容筛选器之前标记为垃圾邮件的邮件路由到垃圾邮件文件夹：</span><span class="sxs-lookup"><span data-stu-id="59d5c-114">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    <span data-ttu-id="59d5c-115">其中_NameForRule_是新规则的名称, 例如, JunkMailBeforeReachingContentFilter。</span><span class="sxs-lookup"><span data-stu-id="59d5c-115">Where  _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span> 
    
4. <span data-ttu-id="59d5c-116">运行以下命令，以确保来自垃圾邮件筛选器策略中阻止列表的发件人的邮件（如**发件人阻止**列表）都会被路由到垃圾邮件文件夹：</span><span class="sxs-lookup"><span data-stu-id="59d5c-116">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span> 
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    <span data-ttu-id="59d5c-117">其中_NameForRule_是新规则的名称, 例如, JunkMailInSenderBlockList。</span><span class="sxs-lookup"><span data-stu-id="59d5c-117">Where  _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span> 
    
<span data-ttu-id="59d5c-118">如果您不想使用 "**将邮件移动到垃圾邮件文件夹**" 操作, 则可以在 Exchange 管理中心中的内容筛选器策略中选择另一个操作。</span><span class="sxs-lookup"><span data-stu-id="59d5c-118">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="59d5c-119">有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="59d5c-119">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="59d5c-120">有关邮件头中这些字段的详细信息, 请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="59d5c-120">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
  

> [!TIP]
> <span data-ttu-id="59d5c-121">如果不想使用 "**将邮件移动到垃圾邮件文件夹**" 操作, 则可以在 Exchange 管理中心中的内容筛选器策略中选择另一个操作。</span><span class="sxs-lookup"><span data-stu-id="59d5c-121">If you don't want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="59d5c-122">有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="59d5c-122">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="59d5c-123">有关邮件头中这些字段的详细信息, 请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="59d5c-123">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
> 
## <a name="see-also"></a><span data-ttu-id="59d5c-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59d5c-124">See also</span></span>

[<span data-ttu-id="59d5c-125">New-transportrule cmdlet</span><span class="sxs-lookup"><span data-stu-id="59d5c-125">New-TransportRule cmdlet</span></span>](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)


---
title: 确保垃圾邮件已路由到每个用户的“垃圾邮件”文件夹
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/16/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
description: EOP 客户的默认反垃圾邮件操作是将垃圾邮件移动到收件人的垃圾邮件文件夹。为了使此操作，以与内部部署邮箱一起使用，您必须来检测垃圾邮件邮件头由 EOP 添加您的内部边缘或集线器服务器上配置 Exchange 传输规则。这些传输规则设置 Set-organizationconfig cmdlet 的 SclJunkThreshold 属性用来将垃圾邮件移动到垃圾邮件文件夹中每个邮箱的垃圾邮件可信度 (SCL)。
ms.openlocfilehash: 1b0a9e5ee39820baade714612ca0b0bdb7a81bb9
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002851"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="f2587-105">确保垃圾邮件已路由到每个用户的“垃圾邮件”文件夹</span><span class="sxs-lookup"><span data-stu-id="f2587-105">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2587-p102">本主题仅适用于承载邮箱的本地混合部署中的 Exchange Online Protection (EOP) 客户。邮箱已在 Office 365 中完全承载的 Exchange Online 客户不需要运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="f2587-p102">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment. Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span> 
  
<span data-ttu-id="f2587-p103">EOP 客户的默认反垃圾邮件操作是将垃圾邮件移动到收件人的垃圾邮件文件夹。为了使此操作，以与内部部署邮箱一起使用，您必须来检测垃圾邮件邮件头由 EOP 添加您的内部边缘或集线器服务器上配置 Exchange 传输规则。这些传输规则设置 Set-organizationconfig cmdlet 的 SclJunkThreshold 属性用来将垃圾邮件移动到垃圾邮件文件夹中每个邮箱的垃圾邮件可信度 (SCL)。</span><span class="sxs-lookup"><span data-stu-id="f2587-p103">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder. In order for this action to work with on-premises mailboxes, you must configure Exchange Transport rules on your on-premises Edge or Hub servers to detect spam headers added by EOP. These Transport rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span> 
  
### <a name="to-add-transport-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="f2587-111">将传输规则以确保垃圾邮件移动到垃圾邮件文件夹使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2587-111">To add transport rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="f2587-p104">访问 Exchange 命令行管理程序在本地 Exchange 服务器。若要了解如何在本地 Exchange 组织中打开 Exchange Management Shell，请参阅**打开命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="f2587-p104">Access the Exchange Management Shell for your on-premises Exchange server. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>
    
2. <span data-ttu-id="f2587-114">运行以下命令以将内容经过筛选的垃圾邮件路由到垃圾邮件文件夹：</span><span class="sxs-lookup"><span data-stu-id="f2587-114">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    <span data-ttu-id="f2587-115">其中_NameForRule_是新规则，例如 JunkContentFilteredMail 的名称。</span><span class="sxs-lookup"><span data-stu-id="f2587-115">Where  _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span> 
    
3. <span data-ttu-id="f2587-116">运行以下命令以将在到达内容筛选器之前标记为垃圾邮件的邮件路由到垃圾邮件文件夹：</span><span class="sxs-lookup"><span data-stu-id="f2587-116">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    <span data-ttu-id="f2587-117">其中_NameForRule_是新规则，例如 JunkMailBeforeReachingContentFilter 的名称。</span><span class="sxs-lookup"><span data-stu-id="f2587-117">Where  _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span> 
    
4. <span data-ttu-id="f2587-118">运行以下命令，以确保来自垃圾邮件筛选器策略中阻止列表的发件人的邮件（如**发件人阻止**列表）都会被路由到垃圾邮件文件夹：</span><span class="sxs-lookup"><span data-stu-id="f2587-118">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span> 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    <span data-ttu-id="f2587-119">其中_NameForRule_是新规则，例如 JunkMailInSenderBlockList 的名称。</span><span class="sxs-lookup"><span data-stu-id="f2587-119">Where  _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span> 
    
<span data-ttu-id="f2587-p105">如果不希望使用**移动到垃圾邮件文件夹的邮件**操作，您可以选择您在 Exchange 管理中心中的内容筛选器策略中的另一项操作。有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。有关这些邮件头中的字段的详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="f2587-p105">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f2587-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2587-123">See also</span></span>

[<span data-ttu-id="f2587-124">New-transportrule cmdlet</span><span class="sxs-lookup"><span data-stu-id="f2587-124">New-TransportRule cmdlet</span></span>](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)


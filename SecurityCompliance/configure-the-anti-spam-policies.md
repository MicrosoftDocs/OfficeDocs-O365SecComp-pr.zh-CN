---
title: 配置反垃圾邮件策略
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: 反垃圾邮件筛选通过默认反垃圾邮件策略（连接筛选器、垃圾邮件筛选器和出站垃圾邮件）在全公司自动启用。作为管理员，您可以查看和编辑，但不能删除默认反垃圾邮件策略，以最适合贵组织的需求。更精确地讲，您也可以创建自定义策略，并将其应用到特定的用户、组或者组织中的域。默认情况下，自定义策略优先于默认策略，但您可以更改策略的优先顺序。
ms.openlocfilehash: ebd65050fb5a0d3862653e0279ef530fbcabc042
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215422"
---
# <a name="configure-the-anti-spam-policies"></a><span data-ttu-id="1ac1b-106">配置反垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="1ac1b-106">Configure the anti-spam policies</span></span>

<span data-ttu-id="1ac1b-p102">反垃圾邮件筛选通过默认反垃圾邮件策略（连接筛选器、垃圾邮件筛选器和出站垃圾邮件）在全公司自动启用。作为管理员，您可以查看和编辑，但不能删除默认反垃圾邮件策略，以最适合贵组织的需求。更精确地讲，您也可以创建自定义策略，并将其应用到特定的用户、组或者组织中的域。默认情况下，自定义策略优先于默认策略，但您可以更改策略的优先顺序。</span><span class="sxs-lookup"><span data-stu-id="1ac1b-p102">Spam filtering is automatically enabled company-wide through the default anti-spam policies (connection filter, spam filter, and outbound spam). As an administrator, you can view and edit, but not delete, the default anti-spam policies so that they are tailored to best meet the needs of your organization. For greater granularity, you can also create custom policies and apply them to specified users, groups, or domains in your organization. By default, custom policies take precedence over the default policy, but you can change the priority of your policies.</span></span> 
  
<span data-ttu-id="1ac1b-111">有关配置反垃圾邮件策略的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="1ac1b-111">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="1ac1b-112">配置连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="1ac1b-112">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="1ac1b-113">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="1ac1b-113">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> <span data-ttu-id="1ac1b-p103">对于 EOP 独立客户: 默认情况下, EOP 内容筛选器将检测到垃圾邮件的邮件发送到每个收件人的 "垃圾邮件" 文件夹。但是, 为了确保 "**将邮件移动到垃圾邮件文件夹**" 操作可用于内部部署邮箱, 必须在您的本地服务器上配置两个 Exchange 传输规则, 以检测由 EOP 添加的垃圾邮件头。有关详细信息, 请参阅[确保垃圾邮件已路由到每个用户的 "垃圾邮件" 文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="1ac1b-p103">For EOP standalone customers: By default, the EOP content filters send spam-detected messages to each recipients' Junk Email folder. However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange Transport rules on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
[<span data-ttu-id="1ac1b-117">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="1ac1b-117">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  


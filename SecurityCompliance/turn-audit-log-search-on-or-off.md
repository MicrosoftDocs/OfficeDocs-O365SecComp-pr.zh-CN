---
title: 启用或禁用 Office 365 审核日志搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: 您可以打开 Office 365 安全性的审核日志搜索功能&amp;合规性中心。如果更改您应注意，您可以随时如果关闭。审核日志搜索关闭时，管理员无法在组织中搜索用户和管理活动的 Office 365 审核日志。
ms.openlocfilehash: 4fa6ac095222addce578294813cbd22dfc50a2ab
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525419"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="d61c0-105">启用或禁用 Office 365 审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="d61c0-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="d61c0-p102">您 （或其他管理员） 必须启用审核日志记录之前可以开始搜索的 Office 365 审核日志。当审核日志搜索 Office 365 安全性&amp;合规性中心处于打开状态，从您的组织的用户和管理活动中的审核日志记录并保留 90 天。但是，您的组织可能不希望记录并保留审核日志数据。或者，您可能要使用的第三方安全信息和事件管理 (SIEM) 应用程序来访问审核数据。在这些情况下，全局管理员可以关闭 Office 365 中的审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="d61c0-p102">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log. When audit log search in the Office 365 Security &amp; Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days. However, your organization might not want to record and retain audit log data. Or you might be using a third-party security information and event management (SIEM) application to access your auditing data. In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="d61c0-111">准备工作</span><span class="sxs-lookup"><span data-stu-id="d61c0-111">Before you begin</span></span>

- <span data-ttu-id="d61c0-p103">您必须分配审核日志角色在 Exchange Online 以启用或禁用 Office 365 组织中的审核日志搜索。默认情况下，此角色分配给 Exchange 管理中心中的**权限**页上合规性管理和组织管理角色组。Office 365 中的全局管理员是 Organization Management 角色组的成员在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="d61c0-p103">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization. By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="d61c0-p104">用户必须为其分配权限在 Exchange Online 以启用或禁用的审核日志搜索。如果您将用户分配安全中**权限**页上的审核日志角色&amp;合规性中心，它们将无法打开或关闭的审核日志搜索。这是因为基础 cmdlet 是 Exchange Online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d61c0-p104">Users have to be assigned permissions in Exchange Online to turn audit log search on or off. If you assign users the Audit Logs role on the **Permissions** page in the Security &amp; Compliance Center, they won't be able to turn audit log search on or off. This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="d61c0-p105">如果要关闭 Office 365 中的审核日志搜索，您仍可以使用 Office 365 管理活动 API 访问审核数据的组织。按照本文中的步骤关闭审核日志搜索是指搜索使用安全的审核日志时，将返回任何结果&amp;合规性中心或 Exchange Online 中运行**搜索 UnifiedAuditLog** cmdlet 时PowerShell。但是，如果您已被授权访问 Office 365 管理活动 API 通过组织的审核数据的任何应用程序，这些应用程序将继续工作。</span><span class="sxs-lookup"><span data-stu-id="d61c0-p105">If you turn off audit log search in Office 365, you can still use the Office 365 Management Activity API to access auditing data for your organization. Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security &amp; Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell. However, if you've authorized any application to access your organization's auditing data via the Office 365 Management Activity API , those applications will continue to work.</span></span> 
    
- <span data-ttu-id="d61c0-121">搜索 Office 365 的分步指导审核日志，请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="d61c0-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="d61c0-122">启用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="d61c0-122">Turn on audit log search</span></span>

<span data-ttu-id="d61c0-p106">您可以使用安全&amp;合规性中心或 PowerShell 打开 Office 365 中的审核日志搜索。可能需要几个小时后就启用审核日志搜索之前搜索审核日志时，可以返回结果。您必须分配审核日志角色在 Exchange Online 以启用审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="d61c0-p106">You can use the Security &amp; Compliance Center or PowerShell to turn on audit log search in Office 365. It might take several hours after you turn on audit log search before you can return results when you search the audit log. You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security-amp-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="d61c0-126">使用安全&amp;打开审核日志搜索的合规性中心</span><span class="sxs-lookup"><span data-stu-id="d61c0-126">Use the Security &amp; Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="d61c0-127">安全中&amp;合规性中心中，转到**搜索&amp;调查** \> **审核日志搜索**。</span><span class="sxs-lookup"><span data-stu-id="d61c0-127">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Audit log search**.</span></span>
    
2. <span data-ttu-id="d61c0-128">单击**开始录制用户和管理活动**。</span><span class="sxs-lookup"><span data-stu-id="d61c0-128">Click **Start recording user and admin activities**.</span></span>
    
    ![单击“开始记录用户和管理员活动”启用审核](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="d61c0-130">告知用户和管理组织中的活动将对 Office 365 审核日志记录和报告中可查看来显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="d61c0-130">A dialog box is displayed saying that user and admin activity in your organization will be recorded to the Office 365 audit log and available to view in a report.</span></span> 
    
3. <span data-ttu-id="d61c0-131">单击" **开启** "。</span><span class="sxs-lookup"><span data-stu-id="d61c0-131">Click **Turn on**.</span></span>
    
    <span data-ttu-id="d61c0-132">将显示一条消息，指出正在准备审核日志和，您可以在几个小时准备完毕后运行搜索。</span><span class="sxs-lookup"><span data-stu-id="d61c0-132">A message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="d61c0-133">使用 PowerShell 启用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="d61c0-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="d61c0-134">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d61c0-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="d61c0-135">运行以下 PowerShell 命令打开 Office 365 中的审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="d61c0-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="d61c0-136">被显示一条消息，告知，可能需要最多 60 分钟更改才能生效。</span><span class="sxs-lookup"><span data-stu-id="d61c0-136">A message is displayed saying that it might take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="d61c0-137">关闭审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="d61c0-137">Turn off audit log search</span></span>

<span data-ttu-id="d61c0-p107">您需要使用远程 PowerShell 连接到 Exchange Online 组织关闭审核日志搜索。类似于打开审核日志搜索，您需要分配审核日志角色在 Exchange Online 关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="d61c0-p107">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search. Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="d61c0-140">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d61c0-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="d61c0-141">运行以下 PowerShell 命令，将会关闭 Office 365 中的审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="d61c0-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="d61c0-p108">后一段时间，确认审核日志搜索关闭 （禁用）。有两种方法来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="d61c0-p108">After a while, verify that audit log search is turned off (disabled). There are two ways to do this:</span></span>
    
    - <span data-ttu-id="d61c0-144">在 PowerShell 中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d61c0-144">In PowerShell, run the following command:</span></span>

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        <span data-ttu-id="d61c0-145">值`False`的_UnifiedAuditLogIngestionEnabled_属性指示处于关闭状态的审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="d61c0-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="d61c0-146">安全中&amp;合规性中心中，转到**搜索&amp;调查** \> **审核日志搜索**，然后单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="d61c0-146">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Audit log search**, and then click **Search**.</span></span>
    
      <span data-ttu-id="d61c0-147">反映审核日志搜索未开启来显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="d61c0-147">A message is displayed saying that audit log search isn't turned on.</span></span> 
    
      ![如果审核处于关闭状态，一条消息，则 dispayed](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)

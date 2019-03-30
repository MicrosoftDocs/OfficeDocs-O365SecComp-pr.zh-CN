---
title: 启用或禁用 Office 365 审核日志搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: 您可以在安全 & 合规中心启用审核日志搜索功能。 如果你更改了想法, 你可以随时关闭。 当 "审核日志搜索" 关闭时, 管理员无法在组织中搜索用户和管理员活动的 Office 365 审核日志。
ms.openlocfilehash: a77114ac9b5de18d4718a543983f7a1f94ebc41f
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000925"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="4ba9b-105">启用或禁用 Office 365 审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="4ba9b-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="4ba9b-106">您 (或另一个管理员) 必须先启用审核日志记录, 然后才能开始搜索 Office 365 审核日志。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="4ba9b-107">当 Security & 合规中心中的审核日志搜索打开时, 您的组织中的用户和管理员活动将记录在审核日志中, 并在90天内保留。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days.</span></span> <span data-ttu-id="4ba9b-108">但是, 您的组织可能不想记录和保留审核日志数据。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-108">However, your organization might not want to record and retain audit log data.</span></span> <span data-ttu-id="4ba9b-109">或者, 您可能使用第三方安全信息和事件管理 (SIEM) 应用程序访问您的审核数据。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-109">Or you might be using a third-party security information and event management (SIEM) application to access your auditing data.</span></span> <span data-ttu-id="4ba9b-110">在这些情况下, 全局管理员可以在 Office 365 中关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-110">In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="4ba9b-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="4ba9b-111">Before you begin</span></span>

- <span data-ttu-id="4ba9b-112">您必须在 Exchange Online 中向您分配 "审核日志" 角色, 才能在 Office 365 组织中打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="4ba9b-113">默认情况下, 此角色在 Exchange 管理中心中的 "**权限**" 页上分配给合规性管理和组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="4ba9b-114">Office 365 中的全局管理员是 Exchange Online 中的 "组织管理" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-114">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="4ba9b-115">必须在 Exchange Online 中向用户分配权限, 才能打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="4ba9b-116">如果在 Security & 合规性中心中向用户分配 "**权限**" 页面上的 "审核日志" 角色, 他们将无法打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="4ba9b-117">这是因为基础 cmdlet 是 Exchange Online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="4ba9b-118">如果关闭了 office 365 中的审核日志搜索, 您仍可以使用 Office 365 管理活动 API 访问您的组织的审核数据。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-118">If you turn off audit log search in Office 365, you can still use the Office 365 Management Activity API to access auditing data for your organization.</span></span> <span data-ttu-id="4ba9b-119">按照本文中的步骤关闭审核日志搜索意味着, 在使用 Security & 合规性中心搜索审核日志时, 或者在 Exchange Online 中运行**UnifiedAuditLog** cmdlet 时, 不会返回任何结果。PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ba9b-119">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="4ba9b-120">但是, 如果你已通过 Office 365 管理活动 API 授权任何应用程序访问组织的审核数据, 则这些应用程序将继续工作。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-120">However, if you've authorized any application to access your organization's auditing data via the Office 365 Management Activity API , those applications will continue to work.</span></span> 
    
- <span data-ttu-id="4ba9b-121">有关搜索 Office 365 审核日志的分步说明, 请参阅[在 Security & 合规性中心搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="4ba9b-122">启用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="4ba9b-122">Turn on audit log search</span></span>

<span data-ttu-id="4ba9b-123">您可以使用安全 & 合规性中心或 PowerShell 在 Office 365 中启用审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="4ba9b-124">在您打开审核日志搜索后, 可能需要几个小时才能在搜索审核日志时返回结果。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-124">It might take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="4ba9b-125">您必须在 Exchange Online 中向您分配 "审核日志" 角色, 才能启用审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="4ba9b-126">使用安全 & 合规性中心启用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="4ba9b-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="4ba9b-127">在 "安全 & 合规性中心" 中, 转到 "**搜索** \> **审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
2. <span data-ttu-id="4ba9b-128">单击 "**开始记录用户和管理员活动**"。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-128">Click **Start recording user and admin activities**.</span></span>
    
    ![单击 "开始记录用户和管理员活动" 以启用审核](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="4ba9b-130">将显示一个对话框, 指出组织中的用户和管理员活动将记录到 Office 365 审核日志中, 并可在报告中查看。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-130">A dialog box is displayed saying that user and admin activity in your organization will be recorded to the Office 365 audit log and available to view in a report.</span></span> 
    
3. <span data-ttu-id="4ba9b-131">单击" **开启** "。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-131">Click **Turn on**.</span></span>
    
    <span data-ttu-id="4ba9b-132">将显示一条消息, 指出正在准备审核日志, 并且您可以在准备完成后的几小时内运行搜索。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-132">A message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="4ba9b-133">使用 PowerShell 打开审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="4ba9b-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="4ba9b-134">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ba9b-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="4ba9b-135">运行以下 PowerShell 命令以在 Office 365 中启用审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="4ba9b-136">将显示一条消息, 指出可能需要长达60分钟的时间才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-136">A message is displayed saying that it might take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="4ba9b-137">关闭审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="4ba9b-137">Turn off audit log search</span></span>

<span data-ttu-id="4ba9b-138">您必须使用连接到 Exchange Online 组织的远程 PowerShell, 才能关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-138">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="4ba9b-139">与启用审核日志搜索类似, 您必须在 Exchange Online 中将 "审核日志" 角色分配给 "关闭审核日志搜索"。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-139">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="4ba9b-140">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="4ba9b-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="4ba9b-141">运行以下 PowerShell 命令以关闭 Office 365 中的审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="4ba9b-142">一段时间后, 验证审核日志搜索是否已关闭 (已禁用)。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-142">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="4ba9b-143">可通过 2 种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="4ba9b-143">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="4ba9b-144">在 PowerShell 中, 运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="4ba9b-144">In PowerShell, run the following command:</span></span>

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        <span data-ttu-id="4ba9b-145">UnifiedAuditLogIngestionEnabled 属性的`False`值指示__ 已关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="4ba9b-146">在 "安全 & 合规性中心" 中, 转到 "**搜索** \> **审核日志搜索**", 然后单击 "**搜索**"。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-146">In the Security & Compliance Center, go to **Search** \> **Audit log search**, and then click **Search**.</span></span>
    
      <span data-ttu-id="4ba9b-147">将显示一条消息, 指出未启用审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="4ba9b-147">A message is displayed saying that audit log search isn't turned on.</span></span> 
    
      ![如果禁用了审核功能, 则会显示一条消息](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)

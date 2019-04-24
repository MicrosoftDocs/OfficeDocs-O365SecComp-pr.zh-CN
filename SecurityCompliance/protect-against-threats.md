---
title: 防御 Office 365 中的威胁
ms.author: tracyp
author: msfttracyp
manager: laurawi
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 现在, 请使用本文作为指南来配置您的威胁防护功能。
ms.openlocfilehash: 065071999130f209d63bcafc09ad72daceceac04
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261630"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="7cc01-103">防御 Office 365 中的威胁</span><span class="sxs-lookup"><span data-stu-id="7cc01-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="7cc01-104">Office 365 包括各种威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="7cc01-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="7cc01-105">以下是可用作检查表的快速入门指南, 以确保为您的组织设置了威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="7cc01-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="7cc01-106">如果你是 Office 365 中的威胁防护功能新手, 或者你不确定从哪里开始, 请使用以下指南作为起点。</span><span class="sxs-lookup"><span data-stu-id="7cc01-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7cc01-107">**为每种策略提供了初始推荐设置; 但是, 有许多可用选项, 您可以调整设置以满足特定组织的需求**。</span><span class="sxs-lookup"><span data-stu-id="7cc01-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="7cc01-108">为你的策略或更改允许大约30分钟, 以在你的数据中心中工作。</span><span class="sxs-lookup"><span data-stu-id="7cc01-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="7cc01-109">Requirements</span><span class="sxs-lookup"><span data-stu-id="7cc01-109">Requirements</span></span>

### <a name="licenses"></a><span data-ttu-id="7cc01-110">许可证</span><span class="sxs-lookup"><span data-stu-id="7cc01-110">Licenses</span></span>

<span data-ttu-id="7cc01-111">威胁防护功能包含在所有 Office 365 订阅中;但是, 某些订阅包含更多高级功能, 例如 Office 365 高级威胁防护中的功能。</span><span class="sxs-lookup"><span data-stu-id="7cc01-111">Threat protection features are included in all Office 365 subscriptions; however, some subscriptions include more advanced features, such as those in Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="7cc01-112">在本文中, 我们包括每个保护区域的订阅要求。</span><span class="sxs-lookup"><span data-stu-id="7cc01-112">In this article we include subscription requirements for each protection area.</span></span>

<span data-ttu-id="7cc01-113">若要了解有关威胁防护功能和 subsriptions 的详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="7cc01-113">To learn more about threat protection features and subsriptions, see the following resources:</span></span>
- [<span data-ttu-id="7cc01-114">Office 365 高级威胁防护服务说明</span><span class="sxs-lookup"><span data-stu-id="7cc01-114">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
- [<span data-ttu-id="7cc01-115">Exchange Online Protection 服务说明</span><span class="sxs-lookup"><span data-stu-id="7cc01-115">Exchange Online Protection Service Description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)
- [<span data-ttu-id="7cc01-116">Office 365 安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="7cc01-116">Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

### <a name="roles-and-permissions"></a><span data-ttu-id="7cc01-117">角色和权限</span><span class="sxs-lookup"><span data-stu-id="7cc01-117">Roles and permissions</span></span>

<span data-ttu-id="7cc01-118">必须为您分配适当的角色, 以便在[安全 & 合规性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)中配置策略。</span><span class="sxs-lookup"><span data-stu-id="7cc01-118">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="7cc01-119">下表包括一些示例:</span><span class="sxs-lookup"><span data-stu-id="7cc01-119">The following table includes some examples:</span></span> 

|<span data-ttu-id="7cc01-120">角色或角色组</span><span class="sxs-lookup"><span data-stu-id="7cc01-120">Role or role group</span></span>  |<span data-ttu-id="7cc01-121">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="7cc01-121">Where to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="7cc01-122">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="7cc01-122">Office 365 Global Administrator</span></span> |[<span data-ttu-id="7cc01-123">关于 Office 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="7cc01-123">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="7cc01-124">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="7cc01-124">Security Administrator</span></span> |[<span data-ttu-id="7cc01-125">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="7cc01-125">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="7cc01-126">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="7cc01-126">Exchange Online Organization Management</span></span> |[<span data-ttu-id="7cc01-127">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="7cc01-127">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="7cc01-128">和</span><span class="sxs-lookup"><span data-stu-id="7cc01-128">and</span></span><br> [<span data-ttu-id="7cc01-129">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="7cc01-129">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="7cc01-130">若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7cc01-130">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware"></a><span data-ttu-id="7cc01-131">第1部分-反恶意软件</span><span class="sxs-lookup"><span data-stu-id="7cc01-131">Part 1 - Anti-malware</span></span>

<span data-ttu-id="7cc01-132">[反恶意软件保护](anti-malware-protection.md)在包含[Exchange Online protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="7cc01-132">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP).</span></span> 

1. <span data-ttu-id="7cc01-133">在 "[安全 & 合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **反恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-133">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="7cc01-134">双击**默认**策略, 然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-134">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="7cc01-135">指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="7cc01-135">Specify the following settings:</span></span>
    
    - <span data-ttu-id="7cc01-136">在 "**恶意软件检测响应**" 部分, 保留默认设置 "**否**"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-136">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>
   
    - <span data-ttu-id="7cc01-137">在 "**常见附件类型筛选器**" 部分, 选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="7cc01-137">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="7cc01-138">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7cc01-138">Click **Save**.</span></span>

<span data-ttu-id="7cc01-139">若要了解有关反恶意软件策略选项的详细信息, 请参阅[配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7cc01-139">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---zero-day-protection"></a><span data-ttu-id="7cc01-140">第2部分-零天保护</span><span class="sxs-lookup"><span data-stu-id="7cc01-140">Part 2 - Zero-day protection</span></span>

<span data-ttu-id="7cc01-141">0天保护在包含[Office 365 高级威胁防护](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)(ATP) 的订阅中可用, 并通过[atp 安全附件](atp-safe-attachments.md)和[atp 安全链接](atp-safe-links.md)策略进行设置。</span><span class="sxs-lookup"><span data-stu-id="7cc01-141">Zero-day protection is available in subscriptions that include [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="7cc01-142">ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="7cc01-142">ATP Safe Attachments policies</span></span>

<span data-ttu-id="7cc01-143">若要设置[atp 安全附件](atp-safe-attachments.md), 必须至少定义一个 ATP 安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="7cc01-143">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span> 

1. <span data-ttu-id="7cc01-144">在 "[安全 & 合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **ATP 安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-144">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="7cc01-145">选择 "**打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP**" 选项。</span><span class="sxs-lookup"><span data-stu-id="7cc01-145">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="7cc01-146">在 "**保护电子邮件附件**" 部分, 单击加号 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="7cc01-146">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="7cc01-147">指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="7cc01-147">Specify the following settings:</span></span>

    - <span data-ttu-id="7cc01-148">在 "**名称**" 框中`Block malware`, 键入。</span><span class="sxs-lookup"><span data-stu-id="7cc01-148">In the **Name** box, type `Block malware`.</span></span>

    - <span data-ttu-id="7cc01-149">在 "响应" 部分, 选择 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-149">In the response section, choose **Block**.</span></span>

    - <span data-ttu-id="7cc01-150">在 "**重定向附件**" 部分中, 选择 "**启用重定向**" 选项, 然后指定将查看检测到的文件的组织的安全管理员或操作员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7cc01-150">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

    - <span data-ttu-id="7cc01-151">在 "**应用**于" 部分中, 选择 **"收件人域"**。</span><span class="sxs-lookup"><span data-stu-id="7cc01-151">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="7cc01-152">然后, 选择您的域, 选择 "**添加**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="7cc01-152">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="7cc01-153">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7cc01-153">Click **Save**.</span></span>

6. <span data-ttu-id="7cc01-154">(**建议的附加步骤**)作为全局管理员或 SharePoint Online 管理员, 运行**[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet, 并将 Office 365 环境的**DisallowInfectedFileDownload**参数设置为*true* 。</span><span class="sxs-lookup"><span data-stu-id="7cc01-154">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="7cc01-155">(这将阻止用户打开、移动、复制或共享被检测为恶意的文件。)</span><span class="sxs-lookup"><span data-stu-id="7cc01-155">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="7cc01-156">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="7cc01-156">To learn more, see:</span></span> 
- [<span data-ttu-id="7cc01-157">设置 Office 365 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="7cc01-157">Set up Office 365 ATP Safe Attachments policies</span></span>](set-up-atp-safe-attachments-policies.md)
- [<span data-ttu-id="7cc01-158">打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="7cc01-158">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)

### <a name="atp-safe-links-policies"></a><span data-ttu-id="7cc01-159">ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="7cc01-159">ATP Safe Links policies</span></span>

<span data-ttu-id="7cc01-160">若要设置[ATP 安全链接](atp-safe-links.md), 请查看并编辑默认策略, 并为特定用户添加策略。</span><span class="sxs-lookup"><span data-stu-id="7cc01-160">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="7cc01-161">在 "[安全 & 合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-161">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="7cc01-162">双击**默认**策略。</span><span class="sxs-lookup"><span data-stu-id="7cc01-162">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="7cc01-163">在 "**使用安全链接**" 部分, 选择 " **office 365 专业增强版"、"office for iOS" 和 "Android**" 选项, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-163">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="7cc01-164">在 "**适用于特定收件人的策略**" 部分, 单击加号 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="7cc01-164">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="7cc01-165">指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="7cc01-165">Specify the following settings:</span></span>

    - <span data-ttu-id="7cc01-166">在 "**名称**" 框中, 键入一个名称, `Safe Links`例如。</span><span class="sxs-lookup"><span data-stu-id="7cc01-166">In the **Name** box, type a name, such as `Safe Links`.</span></span>

    - <span data-ttu-id="7cc01-167">在 "**选择操作**" 部分, 选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="7cc01-167">In the **Select the action** section, choose **On**.</span></span>

    - <span data-ttu-id="7cc01-168">选择以下选项:</span><span class="sxs-lookup"><span data-stu-id="7cc01-168">Select these options:</span></span>

        - <span data-ttu-id="7cc01-169">**使用安全附件扫描可下载的内容**</span><span class="sxs-lookup"><span data-stu-id="7cc01-169">**Use safe attachments to scan downloadable content**</span></span> 

        - <span data-ttu-id="7cc01-170">**将安全链接应用于在组织内发送的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="7cc01-170">**Apply safe links to email messages sent within the organization**</span></span>

        - <span data-ttu-id="7cc01-171">**不要让用户通过指向原始 URL 的安全链接进行单击**</span><span class="sxs-lookup"><span data-stu-id="7cc01-171">**Do not let users click through safe links to original URL**</span></span>

    - <span data-ttu-id="7cc01-172">在 "**应用**于" 部分中, 选择 **"收件人域"**。</span><span class="sxs-lookup"><span data-stu-id="7cc01-172">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="7cc01-173">然后, 选择您的域, 选择 "**添加**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="7cc01-173">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="7cc01-174">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7cc01-174">Click **Save**.</span></span>

<span data-ttu-id="7cc01-175">若要了解详细信息, 请参阅[设置 Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7cc01-175">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing"></a><span data-ttu-id="7cc01-176">第3部分-反网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="7cc01-176">Part 3 - Anti-phishing</span></span> 

<span data-ttu-id="7cc01-177">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的订阅中提供了[反网络钓鱼保护](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="7cc01-177">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="7cc01-178">在[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中提供高级反钓鱼保护。</span><span class="sxs-lookup"><span data-stu-id="7cc01-178">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="7cc01-179">以下过程介绍如何配置 ATP 反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="7cc01-179">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="7cc01-180">配置反网络钓鱼策略 (不包括 ATP) 的步骤类似。</span><span class="sxs-lookup"><span data-stu-id="7cc01-180">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="7cc01-181">在 "[安全 & 合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-181">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="7cc01-182">单击 "**默认策略**"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-182">Click **Default policy**.</span></span>

3. <span data-ttu-id="7cc01-183">在 "**模拟**" 部分, 单击 "**编辑**", 然后指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="7cc01-183">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

    -  <span data-ttu-id="7cc01-184">在 "**添加要保护的用户**" 选项卡上打开 "保护"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-184">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="7cc01-185">然后添加用户, 如贵组织的董事会成员、CEO、CFO 和其他高级领导者。</span><span class="sxs-lookup"><span data-stu-id="7cc01-185">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="7cc01-186">(可以键入单个电子邮件地址, 或单击以显示列表。)</span><span class="sxs-lookup"><span data-stu-id="7cc01-186">(You can type an individual email address, or click to display a list.)</span></span>

    - <span data-ttu-id="7cc01-187">在 "**要保护的添加域**" 选项卡上, 打开 "**自动包括我拥有的域"**。</span><span class="sxs-lookup"><span data-stu-id="7cc01-187">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="7cc01-188">如果你有自定义域, 请将其添加。</span><span class="sxs-lookup"><span data-stu-id="7cc01-188">If you have custom domains, add those as well.</span></span>

    - <span data-ttu-id="7cc01-189">在 "**操作**" 选项卡上, 选择 "**将邮件移至收件人的垃圾邮件文件夹"** 以模拟用户和模拟域, 然后打开安全提示。</span><span class="sxs-lookup"><span data-stu-id="7cc01-189">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>

    - <span data-ttu-id="7cc01-190">在 "**邮箱智能**" 选项卡上, 确保邮箱智能已打开。</span><span class="sxs-lookup"><span data-stu-id="7cc01-190">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>

    - <span data-ttu-id="7cc01-191">查看设置选项卡上的 "**查看设置**" 选项卡后, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-191">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="7cc01-192">在 "**欺骗**" 部分, 单击 "**编辑**", 然后指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="7cc01-192">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

    - <span data-ttu-id="7cc01-193">在 "**哄骗筛选器设置**" 选项卡上, 确保已打开 "反欺骗保护"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-193">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

    - <span data-ttu-id="7cc01-194">在 "**操作**" 选项卡上, 选择 "将邮件移动到收件人的垃圾邮件文件夹"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-194">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>

    - <span data-ttu-id="7cc01-195">查看设置选项卡上的 "**查看设置**" 选项卡后, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-195">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="7cc01-196">(如果未进行任何更改, 请单击 "**取消**"。)</span><span class="sxs-lookup"><span data-stu-id="7cc01-196">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="7cc01-197">关闭 "默认策略设置" 页。</span><span class="sxs-lookup"><span data-stu-id="7cc01-197">Close the default policy settings page.</span></span>

<span data-ttu-id="7cc01-198">若要了解有关反网络钓鱼策略选项的详细信息, 请参阅[设置反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7cc01-198">To learn more about your anti-phishing policy options, see [Set up anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam"></a><span data-ttu-id="7cc01-199">第4部分-反垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="7cc01-199">Part 4 - Anti-spam</span></span>

<span data-ttu-id="7cc01-200">[反垃圾邮件保护](anti-spam-protection.md)在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="7cc01-200">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="7cc01-201">在 "[安全 & 合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **反垃圾邮件**"。</span><span class="sxs-lookup"><span data-stu-id="7cc01-201">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="7cc01-202">在 "**自定义**" 选项卡上, 打开**自定义设置**。</span><span class="sxs-lookup"><span data-stu-id="7cc01-202">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="7cc01-203">展开 "**默认垃圾邮件筛选器策略**", 单击 "**编辑策略**", 然后指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="7cc01-203">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

    - <span data-ttu-id="7cc01-204">在 "**垃圾邮件和批量操作**" 部分, 将阈值设置为值5或6。</span><span class="sxs-lookup"><span data-stu-id="7cc01-204">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

    - <span data-ttu-id="7cc01-205">在 "**允许列表**" 部分中, 查看 (必要时编辑) 您允许的发件人和域。</span><span class="sxs-lookup"><span data-stu-id="7cc01-205">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="7cc01-206">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="7cc01-206">Click **Save**.</span></span>

<span data-ttu-id="7cc01-207">若要了解有关反垃圾邮件策略选项的详细信息, 请参阅[配置反垃圾邮件策略](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7cc01-207">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---service-wide-settings"></a><span data-ttu-id="7cc01-208">第5部分-服务范围设置</span><span class="sxs-lookup"><span data-stu-id="7cc01-208">Part 5 - Service-wide settings</span></span>

### <a name="zero-hour-auto-purge"></a><span data-ttu-id="7cc01-209">零小时自动清除</span><span class="sxs-lookup"><span data-stu-id="7cc01-209">Zero-hour auto purge</span></span>

<span data-ttu-id="7cc01-210">[零小时自动清除](zero-hour-auto-purge.md)(ZAP) 在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="7cc01-210">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="7cc01-211">此保护在默认情况下处于启用状态。但是, 若要使保护生效, 必须满足以下条件:</span><span class="sxs-lookup"><span data-stu-id="7cc01-211">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="7cc01-212">垃圾邮件操作设置为将**邮件移动到**[反垃圾邮件策略](anti-spam-protection.md)中的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="7cc01-212">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="7cc01-213">用户保留其默认的[垃圾邮件设置](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), 但尚未关闭垃圾邮件保护。</span><span class="sxs-lookup"><span data-stu-id="7cc01-213">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="7cc01-214">若要了解详细信息, 请参阅[针对垃圾邮件和恶意软件的零小时自动清除保护](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="7cc01-214">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging"></a><span data-ttu-id="7cc01-215">审核日志记录</span><span class="sxs-lookup"><span data-stu-id="7cc01-215">Audit logging</span></span>

<span data-ttu-id="7cc01-216">审核日志记录在包括[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="7cc01-216">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="7cc01-217">为了查看威胁防护报告中的数据 (如[安全仪表板](security-dashboard.md)、[电子邮件安全报告](view-email-security-reports.md)和[浏览器](use-explorer-in-security-and-compliance.md)), 必须为您的组织打开审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="7cc01-217">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="7cc01-218">若要了解详细信息, 请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="7cc01-218">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="7cc01-219">安装后任务</span><span class="sxs-lookup"><span data-stu-id="7cc01-219">Post-setup tasks</span></span>

### <a name="watch-for-new-features-and-service-updates"></a><span data-ttu-id="7cc01-220">监视新功能和服务更新</span><span class="sxs-lookup"><span data-stu-id="7cc01-220">Watch for new features and service updates</span></span>

- [<span data-ttu-id="7cc01-221">设置标准或目标发布选项</span><span class="sxs-lookup"><span data-stu-id="7cc01-221">Set up the Standard or Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)

- [<span data-ttu-id="7cc01-222">转到你的消息中心以查看功能通知</span><span class="sxs-lookup"><span data-stu-id="7cc01-222">Go to your Message center to view feature announcements</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) 

- [<span data-ttu-id="7cc01-223">访问 Microsoft 365 路线图以查看新功能的状态</span><span class="sxs-lookup"><span data-stu-id="7cc01-223">Visit the Microsoft 365 Roadmap to see status of new features</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [<span data-ttu-id="7cc01-224">查看 Office 365 服务说明</span><span class="sxs-lookup"><span data-stu-id="7cc01-224">Review the Office 365 Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)

### <a name="see-how-threat-protection-features-are-working-for-your-organization"></a><span data-ttu-id="7cc01-225">查看组织的威胁防护功能的工作原理</span><span class="sxs-lookup"><span data-stu-id="7cc01-225">See how threat protection features are working for your organization</span></span>

- [<span data-ttu-id="7cc01-226">访问安全仪表板</span><span class="sxs-lookup"><span data-stu-id="7cc01-226">Visit your security dashboard</span></span>](security-dashboard.md)

- <span data-ttu-id="7cc01-227">[查看 Office 365 的报告 ATP](view-reports-for-atp.md), 包括[资源管理器](use-explorer-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="7cc01-227">[View the reports for Office 365 ATP](view-reports-for-atp.md), including [Explorer](use-explorer-in-security-and-compliance.md)</span></span>

- [<span data-ttu-id="7cc01-228">查看您的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="7cc01-228">View your email security reports</span></span>](view-email-security-reports.md)

### <a name="periodically-review-and-revise-your-threat-protection-policies"></a><span data-ttu-id="7cc01-229">定期查看和修改威胁防护策略</span><span class="sxs-lookup"><span data-stu-id="7cc01-229">Periodically review and revise your threat protection policies</span></span>

- [<span data-ttu-id="7cc01-230">查看安全分数</span><span class="sxs-lookup"><span data-stu-id="7cc01-230">Review your Secure Score</span></span>](microsoft-secure-score.md)

- [<span data-ttu-id="7cc01-231">在安全&amp;合规中心中使用智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="7cc01-231">Use your smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md) 

- [<span data-ttu-id="7cc01-232">使用 Office 365 威胁调查和响应功能保持用户安全</span><span class="sxs-lookup"><span data-stu-id="7cc01-232">Keep users safe with Office 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md) 
 
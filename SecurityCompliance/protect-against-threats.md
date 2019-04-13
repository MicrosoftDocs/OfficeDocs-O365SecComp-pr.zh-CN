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
description: 将本文用作立即配置威胁防护功能的指南。
ms.openlocfilehash: c651c13d5aacf1a7f95a93cacf5030e8ade4b8fd
ms.sourcegitcommit: 895f67531f2b4afe46c7487ca5b44555ca791bae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2019
ms.locfileid: "31836826"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="007b3-103">防御 Office 365 中的威胁</span><span class="sxs-lookup"><span data-stu-id="007b3-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="007b3-104">Office 365 包括各种威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="007b3-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="007b3-105">以下是可用作检查表的快速入门指南, 以确保为您的组织设置了威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="007b3-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="007b3-106">如果你是 Office 365 中的威胁防护功能新手, 或者你不确定从哪里开始, 请使用以下指南作为起点。</span><span class="sxs-lookup"><span data-stu-id="007b3-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="007b3-107">**为每种策略提供了初始推荐设置; 但是, 有许多可用选项, 您可以调整设置以满足特定组织的需求**。</span><span class="sxs-lookup"><span data-stu-id="007b3-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="007b3-108">为你的策略或更改允许大约30分钟, 以在你的数据中心中工作。</span><span class="sxs-lookup"><span data-stu-id="007b3-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="007b3-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="007b3-109">Prerequisites</span></span>

<span data-ttu-id="007b3-110">必须为您分配适当的角色, 以便在[安全 & 合规性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)中配置策略。</span><span class="sxs-lookup"><span data-stu-id="007b3-110">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="007b3-111">下表包括一些示例:</span><span class="sxs-lookup"><span data-stu-id="007b3-111">The following table includes some examples:</span></span> 

|<span data-ttu-id="007b3-112">角色或角色组</span><span class="sxs-lookup"><span data-stu-id="007b3-112">Role or role group</span></span>  |<span data-ttu-id="007b3-113">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="007b3-113">Where to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="007b3-114">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="007b3-114">Office 365 Global Administrator</span></span> |[<span data-ttu-id="007b3-115">关于 Office 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="007b3-115">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="007b3-116">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="007b3-116">Security Administrator</span></span> |[<span data-ttu-id="007b3-117">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="007b3-117">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="007b3-118">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="007b3-118">Exchange Online Organization Management</span></span> |[<span data-ttu-id="007b3-119">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="007b3-119">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="007b3-120">和</span><span class="sxs-lookup"><span data-stu-id="007b3-120">and</span></span><br> [<span data-ttu-id="007b3-121">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="007b3-121">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="007b3-122">若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="007b3-122">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware"></a><span data-ttu-id="007b3-123">第1部分-反恶意软件</span><span class="sxs-lookup"><span data-stu-id="007b3-123">Part 1 - Anti-malware</span></span>

<span data-ttu-id="007b3-124">反恶意软件保护在包含[Exchange Online protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP) 的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="007b3-124">Anti-malware protection is available in subscriptions that include [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP).</span></span> 

1. <span data-ttu-id="007b3-125">在 "[安全 & 合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **反恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="007b3-125">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>
2. <span data-ttu-id="007b3-126">双击**默认**策略, 然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="007b3-126">Double-click the **Default** policy, and then choose **settings**.</span></span>
3. <span data-ttu-id="007b3-127">指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="007b3-127">Specify the following settings:</span></span>
    - <span data-ttu-id="007b3-128">在 "**恶意软件检测响应**" 部分, 保留默认设置 "**否**"。</span><span class="sxs-lookup"><span data-stu-id="007b3-128">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>
    - <span data-ttu-id="007b3-129">在 "**常见附件类型筛选器**" 部分, 选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="007b3-129">In the **Common Attachment Types Filter** section, choose **On**.</span></span>
4. <span data-ttu-id="007b3-130">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="007b3-130">Click **Save**.</span></span>

<span data-ttu-id="007b3-131">若要了解有关反恶意软件策略选项的详细信息, 请参阅[配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="007b3-131">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---zero-day-protection"></a><span data-ttu-id="007b3-132">第2部分-零天保护</span><span class="sxs-lookup"><span data-stu-id="007b3-132">Part 2 - Zero-day protection</span></span>

<span data-ttu-id="007b3-133">0天保护在包含[Office 365 高级威胁防护](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)(ATP) 的订阅中可用, 并通过[atp 安全链接](atp-safe-links.md)和[atp 安全附件](atp-safe-attachments.md)策略进行设置。</span><span class="sxs-lookup"><span data-stu-id="007b3-133">Zero-day protection is available in subscriptions that include [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Links](atp-safe-links.md) and [ATP Safe Attachments](atp-safe-attachments.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="007b3-134">ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="007b3-134">ATP Safe Attachments policies</span></span>

1. <span data-ttu-id="007b3-135">在 "[安全 & 合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **ATP 安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="007b3-135">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>
2. <span data-ttu-id="007b3-136">选择 "**打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP**" 选项。</span><span class="sxs-lookup"><span data-stu-id="007b3-136">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>
3. <span data-ttu-id="007b3-137">在 "**保护电子邮件附件**" 部分, 单击加号 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="007b3-137">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>
4. <span data-ttu-id="007b3-138">指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="007b3-138">Specify the following settings:</span></span>
    - <span data-ttu-id="007b3-139">在 "**名称**" 框中`Block malware`, 键入。</span><span class="sxs-lookup"><span data-stu-id="007b3-139">In the **Name** box, type `Block malware`.</span></span>
    - <span data-ttu-id="007b3-140">在 "响应" 部分, 选择 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="007b3-140">In the response section, choose **Block**.</span></span>
    - <span data-ttu-id="007b3-141">在 "**重定向附件**" 部分中, 选择 "**启用重定向**" 选项, 然后指定将查看检测到的文件的组织的安全管理员或操作员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="007b3-141">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>
    - <span data-ttu-id="007b3-142">在 "**应用**于" 部分中, 选择 **"收件人域"**。</span><span class="sxs-lookup"><span data-stu-id="007b3-142">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="007b3-143">然后, 选择您的域, 选择 "**添加**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="007b3-143">Then, select your domain, choose **Add**, and then click **OK**.</span></span>
5. <span data-ttu-id="007b3-144">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="007b3-144">Click **Save**.</span></span>
6. <span data-ttu-id="007b3-145">(建议的附加步骤)作为全局管理员或 SharePoint Online 管理员, 运行**[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet, 并将 Office 365 环境的**DisallowInfectedFileDownload**参数设置为*true* 。</span><span class="sxs-lookup"><span data-stu-id="007b3-145">(Recommended additional step) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="007b3-146">(这将阻止用户打开、移动、复制或共享被检测为恶意的文件。)</span><span class="sxs-lookup"><span data-stu-id="007b3-146">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="007b3-147">若要了解详细信息, 请参阅[设置 office 365 atp 安全附件策略](set-up-atp-safe-attachments-policies.md)和[打开 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="007b3-147">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="007b3-148">ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="007b3-148">ATP Safe Links policies</span></span>

<span data-ttu-id="007b3-149">若要设置 ATP 安全链接, 请查看您的默认策略并添加策略。</span><span class="sxs-lookup"><span data-stu-id="007b3-149">To set up ATP Safe Links, review your default policy and add a policy.</span></span>

1. <span data-ttu-id="007b3-150">在 "[安全 & 合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="007b3-150">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>
2. <span data-ttu-id="007b3-151">双击**默认**策略。</span><span class="sxs-lookup"><span data-stu-id="007b3-151">Double-click the **Default** policy.</span></span>
3. <span data-ttu-id="007b3-152">在 "**使用安全链接**" 部分, 选择 " **office 365 专业增强版"、"office for iOS" 和 "Android**" 选项, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="007b3-152">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>
4. <span data-ttu-id="007b3-153">在 "**适用于特定收件人的策略**" 部分, 单击加号 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="007b3-153">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>
5. <span data-ttu-id="007b3-154">指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="007b3-154">Specify the following settings:</span></span>
    - <span data-ttu-id="007b3-155">在 "**名称**" 框中, 键入一个名称, `Safe Links`例如。</span><span class="sxs-lookup"><span data-stu-id="007b3-155">In the **Name** box, type a name, such as `Safe Links`.</span></span>
    - <span data-ttu-id="007b3-156">在 "**选择操作**" 部分, 选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="007b3-156">In the **Select the action** section, choose **On**.</span></span>
    - <span data-ttu-id="007b3-157">选择以下选项:</span><span class="sxs-lookup"><span data-stu-id="007b3-157">Select these options:</span></span>
        - <span data-ttu-id="007b3-158">**使用安全附件扫描可下载的内容**</span><span class="sxs-lookup"><span data-stu-id="007b3-158">**Use safe attachments to scan downloadable content**</span></span> 
        - <span data-ttu-id="007b3-159">**将安全链接应用于在组织内发送的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="007b3-159">**Apply safe links to email messages sent within the organization**</span></span>
        - <span data-ttu-id="007b3-160">**不要让用户通过指向原始 URL 的安全链接进行单击**</span><span class="sxs-lookup"><span data-stu-id="007b3-160">**Do not let users click through safe links to original URL**</span></span>
    - <span data-ttu-id="007b3-161">在 "**应用**于" 部分中, 选择 **"收件人域"**。</span><span class="sxs-lookup"><span data-stu-id="007b3-161">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="007b3-162">然后, 选择您的域, 选择 "**添加**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="007b3-162">Then, select your domain, choose **Add**, and then click **OK**.</span></span>
6. <span data-ttu-id="007b3-163">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="007b3-163">Click **Save**.</span></span>

<span data-ttu-id="007b3-164">若要了解详细信息, 请参阅[设置 Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="007b3-164">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing"></a><span data-ttu-id="007b3-165">第3部分-反网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="007b3-165">Part 3 - Anti-phishing</span></span> 

<span data-ttu-id="007b3-166">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的订阅中提供了反网络钓鱼保护。</span><span class="sxs-lookup"><span data-stu-id="007b3-166">Anti-phishing protection is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="007b3-167">在[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中提供高级反钓鱼保护。</span><span class="sxs-lookup"><span data-stu-id="007b3-167">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="007b3-168">以下过程介绍如何配置 ATP 反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="007b3-168">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="007b3-169">配置反网络钓鱼策略 (不包括 ATP) 的步骤类似。</span><span class="sxs-lookup"><span data-stu-id="007b3-169">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="007b3-170">在 "[安全 & 合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="007b3-170">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>
2. <span data-ttu-id="007b3-171">单击 "**默认策略**"。</span><span class="sxs-lookup"><span data-stu-id="007b3-171">Click **Default policy**.</span></span>
3. <span data-ttu-id="007b3-172">在 "**模拟**" 部分, 单击 "**编辑**", 然后指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="007b3-172">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>
    -  <span data-ttu-id="007b3-173">在 "**添加要保护的用户**" 选项卡上打开 "保护"。</span><span class="sxs-lookup"><span data-stu-id="007b3-173">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="007b3-174">然后添加用户, 如贵组织的董事会成员、CEO、CFO 和其他高级领导者。</span><span class="sxs-lookup"><span data-stu-id="007b3-174">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="007b3-175">(可以键入单个电子邮件地址, 或单击以显示列表。)</span><span class="sxs-lookup"><span data-stu-id="007b3-175">(You can type an individual email address, or click to display a list.)</span></span>
    - <span data-ttu-id="007b3-176">在 "**要保护的添加域**" 选项卡上, 打开 "**自动包括我拥有的域"**。</span><span class="sxs-lookup"><span data-stu-id="007b3-176">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="007b3-177">如果你有自定义域, 请将其添加。</span><span class="sxs-lookup"><span data-stu-id="007b3-177">If you have custom domains, add those as well.</span></span>
    - <span data-ttu-id="007b3-178">在 "**操作**" 选项卡上, 选择 "**将邮件移至收件人的垃圾邮件文件夹"** 以模拟用户和模拟域, 然后打开安全提示。</span><span class="sxs-lookup"><span data-stu-id="007b3-178">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>
    - <span data-ttu-id="007b3-179">在 "**邮箱智能**" 选项卡上, 确保邮箱智能已打开。</span><span class="sxs-lookup"><span data-stu-id="007b3-179">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>
    - <span data-ttu-id="007b3-180">查看设置选项卡上的 "**查看设置**" 选项卡后, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="007b3-180">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>
4. <span data-ttu-id="007b3-181">在 "**欺骗**" 部分, 单击 "**编辑**", 然后指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="007b3-181">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>
    - <span data-ttu-id="007b3-182">在 "**哄骗筛选器设置**" 选项卡上, 确保已打开 "反欺骗保护"。</span><span class="sxs-lookup"><span data-stu-id="007b3-182">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>
    - <span data-ttu-id="007b3-183">在 "**操作**" 选项卡上, 选择 "将邮件移动到收件人的垃圾邮件文件夹"。</span><span class="sxs-lookup"><span data-stu-id="007b3-183">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>
    - <span data-ttu-id="007b3-184">查看设置选项卡上的 "**查看设置**" 选项卡后, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="007b3-184">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="007b3-185">(如果未进行任何更改, 请单击 "**取消**"。)</span><span class="sxs-lookup"><span data-stu-id="007b3-185">(If you didn't make any changes, click **Cancel**.)</span></span>
5. <span data-ttu-id="007b3-186">关闭 "默认策略设置" 页。</span><span class="sxs-lookup"><span data-stu-id="007b3-186">Close the default policy settings page.</span></span>

<span data-ttu-id="007b3-187">若要了解有关反网络钓鱼策略选项的详细信息, 请参阅[设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="007b3-187">To learn more about your anti-phishing policy options, see [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam"></a><span data-ttu-id="007b3-188">第4部分-反垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="007b3-188">Part 4 - Anti-spam</span></span>

<span data-ttu-id="007b3-189">反垃圾邮件保护在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="007b3-189">Anti-spam protection is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="007b3-190">在 "[安全 & 合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **反垃圾邮件**"。</span><span class="sxs-lookup"><span data-stu-id="007b3-190">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>
2. <span data-ttu-id="007b3-191">在 "**自定义**" 选项卡上, 打开**自定义设置**。</span><span class="sxs-lookup"><span data-stu-id="007b3-191">On the **Custom** tab, turn **Custom settings** on.</span></span>
3. <span data-ttu-id="007b3-192">展开 "**默认垃圾邮件筛选器策略**", 单击 "**编辑策略**", 然后指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="007b3-192">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>
    - <span data-ttu-id="007b3-193">在 "**垃圾邮件和批量操作**" 部分, 将阈值设置为值5或6。</span><span class="sxs-lookup"><span data-stu-id="007b3-193">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>
    - <span data-ttu-id="007b3-194">在 "**允许列表**" 部分中, 查看 (必要时编辑) 您允许的发件人和域。</span><span class="sxs-lookup"><span data-stu-id="007b3-194">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>
4. <span data-ttu-id="007b3-195">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="007b3-195">Click **Save**.</span></span>

<span data-ttu-id="007b3-196">若要了解有关反垃圾邮件策略选项的详细信息, 请参阅[配置反垃圾邮件策略](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="007b3-196">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---service-wide-settings"></a><span data-ttu-id="007b3-197">第5部分-服务范围设置</span><span class="sxs-lookup"><span data-stu-id="007b3-197">Part 5 - Service-wide settings</span></span>

### <a name="zero-hour-auto-purge"></a><span data-ttu-id="007b3-198">零小时自动清除</span><span class="sxs-lookup"><span data-stu-id="007b3-198">Zero-hour auto purge</span></span>

<span data-ttu-id="007b3-199">0小时自动清除 (ZAP) 在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="007b3-199">Zero-hour auto purge (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="007b3-200">此保护在默认情况下处于启用状态。但是, 若要使保护生效, 必须满足以下条件:</span><span class="sxs-lookup"><span data-stu-id="007b3-200">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>
- <span data-ttu-id="007b3-201">垃圾邮件操作设置为将**邮件移动到**反垃圾邮件策略中的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="007b3-201">Spam actions are set to **Move message to Junk Email folder** in anti-spam policies.</span></span>
- <span data-ttu-id="007b3-202">用户保留其默认的垃圾邮件设置, 但尚未关闭垃圾邮件保护。</span><span class="sxs-lookup"><span data-stu-id="007b3-202">Users have kept their default junk email settings, and have not turned off junk email protection.</span></span>

<span data-ttu-id="007b3-203">若要了解详细信息, 请参阅[针对垃圾邮件和恶意软件的零小时自动清除保护](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="007b3-203">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging"></a><span data-ttu-id="007b3-204">审核日志记录</span><span class="sxs-lookup"><span data-stu-id="007b3-204">Audit logging</span></span>

<span data-ttu-id="007b3-205">审核日志记录在包括[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)的订阅中可用。</span><span class="sxs-lookup"><span data-stu-id="007b3-205">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="007b3-206">为了查看威胁防护报告中的数据 (如[安全仪表板](security-dashboard.md)、[电子邮件安全报告](view-email-security-reports.md)和[浏览器](use-explorer-in-security-and-compliance.md)), 必须为您的组织打开审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="007b3-206">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="007b3-207">若要了解详细信息, 请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="007b3-207">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="007b3-208">安装后任务</span><span class="sxs-lookup"><span data-stu-id="007b3-208">Post-setup tasks</span></span>

### <a name="watch-for-new-features-and-service-updates"></a><span data-ttu-id="007b3-209">监视新功能和服务更新</span><span class="sxs-lookup"><span data-stu-id="007b3-209">Watch for new features and service updates</span></span>

- [<span data-ttu-id="007b3-210">访问 Microsoft 365 路线图</span><span class="sxs-lookup"><span data-stu-id="007b3-210">Visit the Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [<span data-ttu-id="007b3-211">请参阅 Office 365 高级威胁防护服务说明</span><span class="sxs-lookup"><span data-stu-id="007b3-211">See the Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)

### <a name="see-how-atp-is-working-for-your-organization"></a><span data-ttu-id="007b3-212">了解 ATP 如何为你的组织工作</span><span class="sxs-lookup"><span data-stu-id="007b3-212">See how ATP is working for your organization</span></span>

- [<span data-ttu-id="007b3-213">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="007b3-213">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

- [<span data-ttu-id="007b3-214">在安全&amp;合规中心中使用资源管理器</span><span class="sxs-lookup"><span data-stu-id="007b3-214">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)

### <a name="periodically-review-and-revise-your-atp-policies"></a><span data-ttu-id="007b3-215">定期查看和修订 ATP 策略</span><span class="sxs-lookup"><span data-stu-id="007b3-215">Periodically review and revise your ATP policies</span></span>

- [<span data-ttu-id="007b3-216">使用 office 365 的威胁调查和响应确保 office 365 用户安全</span><span class="sxs-lookup"><span data-stu-id="007b3-216">Keep your Office 365 users safe with Office 365 threat investigation and response</span></span>](keep-users-safe-with-office-365-ti.md) 

- [<span data-ttu-id="007b3-217">在 Office 365 安全&amp;合规中心中使用智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="007b3-217">Use the smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md) 
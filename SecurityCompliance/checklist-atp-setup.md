---
title: '快速入门: 设置 Office 365 高级威胁防护'
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 您可以使用下面的快速入门指南来确保为您的组织设置和配置 Office 365 高级威胁防护 (ATP)。
ms.openlocfilehash: 5aecbdb63f30a620812de44907b29dcae838ba36
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693292"
---
# <a name="quick-start-guide-set-up-office-365-advanced-threat-protection"></a><span data-ttu-id="bed05-103">快速入门指南: 设置 Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="bed05-103">Quick Start Guide: Set up Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="bed05-104">下面是可用作检查表以确保为您的组织设置了 Office 365 高级威胁防护 (ATP) 的快速入门指南。</span><span class="sxs-lookup"><span data-stu-id="bed05-104">Here's a quick-start guide you can use as a checklist to make sure Office 365 Advanced Threat Protection (ATP) is set up for your organization.</span></span> <span data-ttu-id="bed05-105">如果你是 Office 365 中的威胁防护新手, 或者你不确定从何处入手, 请使用以下指南作为起点。</span><span class="sxs-lookup"><span data-stu-id="bed05-105">If you're new to threat protection in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="bed05-106">**为每种策略提供了初始推荐设置; 但是, 有许多可用选项, 您可以调整设置以满足特定组织的需求**。</span><span class="sxs-lookup"><span data-stu-id="bed05-106">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="bed05-107">为你的策略或更改允许大约30分钟, 以在你的数据中心中工作。</span><span class="sxs-lookup"><span data-stu-id="bed05-107">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bed05-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="bed05-108">Prerequisites</span></span>

- <span data-ttu-id="bed05-109">您的组织必须具有包含[Office 365 高级威胁防护](office-365-atp.md)(ATP) 的订阅。</span><span class="sxs-lookup"><span data-stu-id="bed05-109">Your organization must have a subscription that includes [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP).</span></span>

- <span data-ttu-id="bed05-110">必须为您分配适当的角色才能访问 ATP 功能。</span><span class="sxs-lookup"><span data-stu-id="bed05-110">You must be assigned an appropriate role to access ATP features.</span></span> <span data-ttu-id="bed05-111">下表包括一些示例:</span><span class="sxs-lookup"><span data-stu-id="bed05-111">The following table includes some examples:</span></span> 

    |<span data-ttu-id="bed05-112">角色或角色组</span><span class="sxs-lookup"><span data-stu-id="bed05-112">Role or role group</span></span>  |<span data-ttu-id="bed05-113">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="bed05-113">Where to learn more</span></span>  |
    |---------|---------|
    |<span data-ttu-id="bed05-114">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="bed05-114">Office 365 Global Administrator</span></span> |[<span data-ttu-id="bed05-115">关于 Office 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="bed05-115">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
    |<span data-ttu-id="bed05-116">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="bed05-116">Security Administrator</span></span> |[<span data-ttu-id="bed05-117">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="bed05-117">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
    |<span data-ttu-id="bed05-118">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="bed05-118">Exchange Online Organization Management</span></span> |[<span data-ttu-id="bed05-119">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="bed05-119">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="bed05-120">and</span><span class="sxs-lookup"><span data-stu-id="bed05-120">and</span></span><br> [<span data-ttu-id="bed05-121">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="bed05-121">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

    <span data-ttu-id="bed05-122">(请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。)</span><span class="sxs-lookup"><span data-stu-id="bed05-122">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

## <a name="part-1---anti-malware"></a><span data-ttu-id="bed05-123">第1部分-反恶意软件</span><span class="sxs-lookup"><span data-stu-id="bed05-123">Part 1 - Anti-malware</span></span>

1. <span data-ttu-id="bed05-124">在 " [Office 365 安全 & 合规中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **反恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="bed05-124">In the [Office 365 Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>
2. <span data-ttu-id="bed05-125">双击**默认**策略, 然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="bed05-125">Double-click the **Default** policy, and then choose **settings**.</span></span>
3. <span data-ttu-id="bed05-126">指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="bed05-126">Specify the following settings:</span></span>
    - <span data-ttu-id="bed05-127">在 "**恶意软件检测响应**" 部分, 保留默认设置 "**否**"。</span><span class="sxs-lookup"><span data-stu-id="bed05-127">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>
    - <span data-ttu-id="bed05-128">在 "**常见附件类型筛选器**" 部分, 选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="bed05-128">In the **Common Attachment Types Filter** section, choose **On**.</span></span>
4. <span data-ttu-id="bed05-129">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bed05-129">Click **Save**.</span></span>

<span data-ttu-id="bed05-130">若要了解有关反恶意软件策略选项的详细信息, 请参阅[配置反恶意软件策略](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bed05-130">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---zero-day-protection"></a><span data-ttu-id="bed05-131">第2部分-零天保护</span><span class="sxs-lookup"><span data-stu-id="bed05-131">Part 2 - Zero-day protection</span></span>

<span data-ttu-id="bed05-132">通过策略 (如 ATP 安全链接和安全附件策略) 设置零日保护。</span><span class="sxs-lookup"><span data-stu-id="bed05-132">Zero-day protection is set up through policies, such as ATP Safe Links and Safe Attachments policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="bed05-133">ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="bed05-133">ATP Safe Attachments policies</span></span>

1. <span data-ttu-id="bed05-134">在 " [Office 365 安全 & 合规中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **ATP 安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="bed05-134">In the [Office 365 Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>
2. <span data-ttu-id="bed05-135">选择 "**打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP**" 选项。</span><span class="sxs-lookup"><span data-stu-id="bed05-135">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>
3. <span data-ttu-id="bed05-136">在 "**保护电子邮件附件**" 部分, 单击加号 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="bed05-136">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>
4. <span data-ttu-id="bed05-137">指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="bed05-137">Specify the following settings:</span></span>
    - <span data-ttu-id="bed05-138">在 "**名称**" 框中`Block malware`, 键入。</span><span class="sxs-lookup"><span data-stu-id="bed05-138">In the **Name** box, type `Block malware`.</span></span>
    - <span data-ttu-id="bed05-139">在 "响应" 部分, 选择 "**阻止**"。</span><span class="sxs-lookup"><span data-stu-id="bed05-139">In the response section, choose **Block**.</span></span>
    - <span data-ttu-id="bed05-140">在 "**重定向附件**" 部分中, 选择 "**启用重定向**" 选项, 然后指定将查看检测到的文件的组织的安全管理员或操作员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="bed05-140">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>
    - <span data-ttu-id="bed05-141">在 "**应用**于" 部分中, 选择 **"收件人域"**。</span><span class="sxs-lookup"><span data-stu-id="bed05-141">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="bed05-142">然后, 选择您的域, 选择 "**添加**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="bed05-142">Then, select your domain, choose **Add**, and then click **OK**.</span></span>
5. <span data-ttu-id="bed05-143">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bed05-143">Click **Save**.</span></span>
6. <span data-ttu-id="bed05-144">(建议的附加步骤)作为全局管理员或 SharePoint Online 管理员, 运行**[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet, 并将 Office 365 环境的**DisallowInfectedFileDownload**参数设置为*true* 。</span><span class="sxs-lookup"><span data-stu-id="bed05-144">(Recommended additional step) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="bed05-145">(这将阻止用户打开、移动、复制或共享被检测为恶意的文件。)</span><span class="sxs-lookup"><span data-stu-id="bed05-145">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="bed05-146">若要了解详细信息, 请参阅[设置 office 365 atp 安全附件策略](set-up-atp-safe-attachments-policies.md)和[打开 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="bed05-146">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="bed05-147">ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="bed05-147">ATP Safe Links policies</span></span>

<span data-ttu-id="bed05-148">若要设置 ATP 安全链接, 请查看您的默认策略并添加策略。</span><span class="sxs-lookup"><span data-stu-id="bed05-148">To set up ATP Safe Links, review your default policy and add a policy.</span></span>

1. <span data-ttu-id="bed05-149">在 " [Office 365 安全 & 合规中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **ATP 安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="bed05-149">In the [Office 365 Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>
2. <span data-ttu-id="bed05-150">双击**默认**策略。</span><span class="sxs-lookup"><span data-stu-id="bed05-150">Double-click the **Default** policy.</span></span>
3. <span data-ttu-id="bed05-151">在 "**使用安全链接**" 部分, 选择 " **office 365 专业增强版"、"office for iOS" 和 "Android**" 选项, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="bed05-151">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>
4. <span data-ttu-id="bed05-152">在 "**适用于特定收件人的策略**" 部分, 单击加号 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="bed05-152">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>
5. <span data-ttu-id="bed05-153">指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="bed05-153">Specify the following settings:</span></span>
    - <span data-ttu-id="bed05-154">在 "**名称**" 框中, 键入一个名称, `Safe Links`例如。</span><span class="sxs-lookup"><span data-stu-id="bed05-154">In the **Name** box, type a name, such as `Safe Links`.</span></span>
    - <span data-ttu-id="bed05-155">在 "**选择操作**" 部分, 选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="bed05-155">In the **Select the action** section, choose **On**.</span></span>
    - <span data-ttu-id="bed05-156">选择以下选项:</span><span class="sxs-lookup"><span data-stu-id="bed05-156">Select these options:</span></span>
        - <span data-ttu-id="bed05-157">**使用安全附件扫描可下载的内容**</span><span class="sxs-lookup"><span data-stu-id="bed05-157">**Use safe attachments to scan downloadable content**</span></span> 
        - <span data-ttu-id="bed05-158">**将安全链接应用于在组织内发送的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="bed05-158">**Apply safe links to email messages sent within the organization**</span></span>
        - <span data-ttu-id="bed05-159">**不要让用户通过指向原始 URL 的安全链接进行单击**</span><span class="sxs-lookup"><span data-stu-id="bed05-159">**Do not let users click through safe links to original URL**</span></span>
    - <span data-ttu-id="bed05-160">在 "**应用**于" 部分中, 选择 **"收件人域"**。</span><span class="sxs-lookup"><span data-stu-id="bed05-160">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="bed05-161">然后, 选择您的域, 选择 "**添加**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="bed05-161">Then, select your domain, choose **Add**, and then click **OK**.</span></span>
6. <span data-ttu-id="bed05-162">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bed05-162">Click **Save**.</span></span>

<span data-ttu-id="bed05-163">若要了解详细信息, 请参阅[设置 Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bed05-163">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing"></a><span data-ttu-id="bed05-164">第3部分-反网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="bed05-164">Part 3 - Anti-phishing</span></span> 

1. <span data-ttu-id="bed05-165">在 " [Office 365 安全 & 合规中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **ATP 反网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="bed05-165">In the [Office 365 Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>
2. <span data-ttu-id="bed05-166">单击 "**默认策略**"。</span><span class="sxs-lookup"><span data-stu-id="bed05-166">Click **Default policy**.</span></span>
3. <span data-ttu-id="bed05-167">在 "**模拟**" 部分, 单击 "**编辑**", 然后指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="bed05-167">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>
    -  <span data-ttu-id="bed05-168">在 "**添加要保护的用户**" 选项卡上打开 "保护"。</span><span class="sxs-lookup"><span data-stu-id="bed05-168">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="bed05-169">然后添加用户, 如贵组织的董事会成员、CEO、CFO 和其他高级领导者。</span><span class="sxs-lookup"><span data-stu-id="bed05-169">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="bed05-170">(可以键入单个电子邮件地址, 或单击以显示列表。)</span><span class="sxs-lookup"><span data-stu-id="bed05-170">(You can type an individual email address, or click to display a list.)</span></span>
    - <span data-ttu-id="bed05-171">在 "**要保护的添加域**" 选项卡上, 打开 "**自动包括我拥有的域"**。</span><span class="sxs-lookup"><span data-stu-id="bed05-171">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="bed05-172">如果你有自定义域, 请将其添加。</span><span class="sxs-lookup"><span data-stu-id="bed05-172">If you have custom domains, add those as well.</span></span>
    - <span data-ttu-id="bed05-173">在 "**操作**" 选项卡上, 选择 "**将邮件移至收件人的垃圾邮件文件夹"** 以模拟用户和模拟域, 然后打开安全提示。</span><span class="sxs-lookup"><span data-stu-id="bed05-173">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>
    - <span data-ttu-id="bed05-174">在 "**邮箱智能**" 选项卡上, 确保邮箱智能已打开。</span><span class="sxs-lookup"><span data-stu-id="bed05-174">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>
    - <span data-ttu-id="bed05-175">查看设置选项卡上的 "**查看设置**" 选项卡后, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="bed05-175">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>
4. <span data-ttu-id="bed05-176">在 "**欺骗**" 部分, 单击 "**编辑**", 然后指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="bed05-176">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>
    - <span data-ttu-id="bed05-177">在 "**哄骗筛选器设置**" 选项卡上, 确保已打开 "反欺骗保护"。</span><span class="sxs-lookup"><span data-stu-id="bed05-177">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>
    - <span data-ttu-id="bed05-178">在 "**操作**" 选项卡上, 选择 "将邮件移动到收件人的垃圾邮件文件夹"。</span><span class="sxs-lookup"><span data-stu-id="bed05-178">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>
    - <span data-ttu-id="bed05-179">查看设置选项卡上的 "**查看设置**" 选项卡后, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="bed05-179">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="bed05-180">(如果未进行任何更改, 请单击 "**取消**"。)</span><span class="sxs-lookup"><span data-stu-id="bed05-180">(If you didn't make any changes, click **Cancel**.)</span></span>
5. <span data-ttu-id="bed05-181">关闭 "默认策略设置" 页。</span><span class="sxs-lookup"><span data-stu-id="bed05-181">Close the default policy settings page.</span></span>

<span data-ttu-id="bed05-182">若要了解有关反网络钓鱼策略选项的详细信息, 请参阅[设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bed05-182">To learn more about your anti-phishing policy options, see [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam"></a><span data-ttu-id="bed05-183">第4部分-反垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="bed05-183">Part 4 - Anti-spam</span></span>

1. <span data-ttu-id="bed05-184">在 " [Office 365 安全 & 合规中心](https://protection.office.com)" 中, 选择 "**威胁管理** > **策略** > **反垃圾邮件**"。</span><span class="sxs-lookup"><span data-stu-id="bed05-184">In the [Office 365 Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>
2. <span data-ttu-id="bed05-185">在 "**自定义**" 选项卡上, 打开**自定义设置**。</span><span class="sxs-lookup"><span data-stu-id="bed05-185">On the **Custom** tab, turn **Custom settings** on.</span></span>
3. <span data-ttu-id="bed05-186">展开 "**默认垃圾邮件筛选器策略**", 单击 "**编辑策略**", 然后指定以下设置:</span><span class="sxs-lookup"><span data-stu-id="bed05-186">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>
    - <span data-ttu-id="bed05-187">在 "**垃圾邮件和批量操作**" 部分, 将阈值设置为值5或6。</span><span class="sxs-lookup"><span data-stu-id="bed05-187">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>
    - <span data-ttu-id="bed05-188">在 "**允许列表**" 部分中, 查看 (必要时编辑) 您允许的发件人和域。</span><span class="sxs-lookup"><span data-stu-id="bed05-188">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>
4. <span data-ttu-id="bed05-189">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bed05-189">Click **Save**.</span></span>

<span data-ttu-id="bed05-190">若要了解有关反垃圾邮件策略选项的详细信息, 请参阅[配置反垃圾邮件策略](configure-the-anti-spam-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bed05-190">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---service-wide-settings"></a><span data-ttu-id="bed05-191">第5部分-服务范围设置</span><span class="sxs-lookup"><span data-stu-id="bed05-191">Part 5 - Service-wide settings</span></span>

### <a name="zero-hour-auto-purge"></a><span data-ttu-id="bed05-192">零小时自动清除</span><span class="sxs-lookup"><span data-stu-id="bed05-192">Zero-hour auto purge</span></span>

<span data-ttu-id="bed05-193">0小时自动清除 (ZAP) 在默认情况下处于打开状态。但是, 必须满足以下条件:</span><span class="sxs-lookup"><span data-stu-id="bed05-193">Zero-hour auto purge (ZAP) is turned on by default; however, the following conditions must be met:</span></span>
- <span data-ttu-id="bed05-194">垃圾邮件操作设置为将**邮件移动到**反垃圾邮件策略中的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bed05-194">Spam actions are set to **Move message to Junk Email folder** in anti-spam policies.</span></span>
- <span data-ttu-id="bed05-195">用户保留其默认的垃圾邮件设置, 但尚未关闭垃圾邮件保护。</span><span class="sxs-lookup"><span data-stu-id="bed05-195">Users have kept their default junk email settings, and have not turned off junk email protection.</span></span>

<span data-ttu-id="bed05-196">若要了解详细信息, 请参阅[针对垃圾邮件和恶意软件的零小时自动清除保护](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="bed05-196">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging"></a><span data-ttu-id="bed05-197">审核日志记录</span><span class="sxs-lookup"><span data-stu-id="bed05-197">Audit logging</span></span>

<span data-ttu-id="bed05-198">为了查看威胁防护报告中的数据 (如[安全仪表板](security-dashboard.md)和[浏览器](use-explorer-in-security-and-compliance.md)), 必须为您的组织打开审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="bed05-198">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md) and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span>

<span data-ttu-id="bed05-199">请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="bed05-199">See [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="bed05-200">安装后任务</span><span class="sxs-lookup"><span data-stu-id="bed05-200">Post-setup tasks</span></span>

### <a name="watch-for-new-features-and-service-updates"></a><span data-ttu-id="bed05-201">监视新功能和服务更新</span><span class="sxs-lookup"><span data-stu-id="bed05-201">Watch for new features and service updates</span></span>

- [<span data-ttu-id="bed05-202">访问 Microsoft 365 路线图</span><span class="sxs-lookup"><span data-stu-id="bed05-202">Visit the Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [<span data-ttu-id="bed05-203">请参阅 Office 365 高级威胁防护服务说明</span><span class="sxs-lookup"><span data-stu-id="bed05-203">See the Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)

### <a name="see-how-atp-is-working-for-your-organization"></a><span data-ttu-id="bed05-204">了解 ATP 如何为你的组织工作</span><span class="sxs-lookup"><span data-stu-id="bed05-204">See how ATP is working for your organization</span></span>

- [<span data-ttu-id="bed05-205">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="bed05-205">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

- [<span data-ttu-id="bed05-206">在安全&amp;合规中心中使用资源管理器</span><span class="sxs-lookup"><span data-stu-id="bed05-206">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)

### <a name="periodically-review-and-revise-your-atp-policies"></a><span data-ttu-id="bed05-207">定期查看和修订 ATP 策略</span><span class="sxs-lookup"><span data-stu-id="bed05-207">Periodically review and revise your ATP policies</span></span>

- [<span data-ttu-id="bed05-208">使用 office 365 的威胁调查和响应确保 office 365 用户安全</span><span class="sxs-lookup"><span data-stu-id="bed05-208">Keep your Office 365 users safe with Office 365 threat investigation and response</span></span>](keep-users-safe-with-office-365-ti.md) 

- [<span data-ttu-id="bed05-209">在 Office 365 安全&amp;合规中心中使用智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="bed05-209">Use the smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md) 
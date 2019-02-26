---
title: 设置 Office 365 ATP 安全链接策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 设置安全链接策略以保护您的组织免受 Word、Excel、PowerPoint 和 Visio 文件以及电子邮件中的恶意链接。
ms.openlocfilehash: 0cf6c22be42f11fe52a1f43d0ebef48bd639675d
ms.sourcegitcommit: 5b5bbced1577701bdb6befc8ed252e9d9e776529
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2019
ms.locfileid: "30245598"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a><span data-ttu-id="82e2d-103">设置 Office 365 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="82e2d-103">Set up Office 365 ATP Safe Links policies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82e2d-p101">本文适用于 Office 365 企业客户。如果您使用的是 Outlook.com、office 365 家庭版或 office 365 个人版, 并且您正在查找有关 Outlook 中的安全链接的信息, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-p101">This article is intended for Office 365 Enterprise customers. If you are using Outlook.com, Office 365 Home, or Office 365 Personal, and you're looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="82e2d-p102">[ATP 安全链接](atp-safe-links.md)是[Office 365 高级威胁防护](office-365-atp.md)(ATP) 的一项功能, 可帮助保护您的组织免受网络钓鱼和其他攻击中使用的恶意链接。如果您拥有[Office 365 安全&amp;合规中心](permissions-in-the-security-and-compliance-center.md)的必要权限, 则可以设置 ATP 安全链接策略, 以帮助确保当用户单击 "web 地址" (url) 时, 您的组织受到保护。您的 ATP 安全链接策略可以配置为扫描 Office 文档中的电子邮件和 url 中的 url。</span><span class="sxs-lookup"><span data-stu-id="82e2d-p102">[ATP Safe Links](atp-safe-links.md), a feature of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), can help protect your organization from malicious links used in phishing and other attacks. If you have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can set up ATP Safe Links policies to help ensure that when people click web addresses (URLs), your organization is protected. Your ATP Safe Links policies can be configured to scan URLs in email and URLs in Office documents.</span></span>
  
<span data-ttu-id="82e2d-p103">[将新功能连续添加到 ATP](office-365-atp.md#new-features-in-office-365-atp)。添加新功能时, 您可能需要对现有的 ATP 安全链接策略进行调整。</span><span class="sxs-lookup"><span data-stu-id="82e2d-p103">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp). As new features are added, you may need to make adjustments to your existing ATP Safe Links policies.</span></span>

## <a name="what-to-do"></a><span data-ttu-id="82e2d-111">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="82e2d-111">What to do</span></span> 
  
1. <span data-ttu-id="82e2d-112">[查看先决条件](#review-the-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-112">[Review the prerequisites](#review-the-prerequisites).</span></span>
    
2. <span data-ttu-id="82e2d-p104">[查看和编辑适用于每个人的默认 ATP 安全链接策略](#define-an-atp-safe-links-policy-that-applies-to-everyone)。例如, 您可以[为 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-p104">[Review and edit the default ATP Safe Links policy that applies to everyone](#define-an-atp-safe-links-policy-that-applies-to-everyone). For example, you can [set up your custom blocked URLs list for ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span>
    
3. <span data-ttu-id="82e2d-115">[为特定的电子邮件收件人添加或编辑策略](#add-a-policy-for-specific-email-recipients), 包括[设置 ATP 安全链接的自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-115">[Add or edit policies for specific email recipients](#add-a-policy-for-specific-email-recipients), including [setting up your custom "Do not rewrite" URLs list for ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
    
4. <span data-ttu-id="82e2d-116">[了解 ATP 安全链接策略选项](#learn-about-atp-safe-links-policy-options)(在本文中), 包括最近更改的设置。</span><span class="sxs-lookup"><span data-stu-id="82e2d-116">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article), including settings for recent changes.</span></span>
    
## <a name="step-1-review-the-prerequisites"></a><span data-ttu-id="82e2d-117">步骤 1: 查看先决条件</span><span class="sxs-lookup"><span data-stu-id="82e2d-117">Step 1: Review the prerequisites</span></span>

- <span data-ttu-id="82e2d-118">确保您的组织具有[Office 365 高级威胁防护](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-118">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>
    
- <span data-ttu-id="82e2d-p105">请确保您具有必要的权限。若要定义 (或编辑) ATP 策略, 必须为您分配适当的角色。下表介绍了一些示例:</span><span class="sxs-lookup"><span data-stu-id="82e2d-p105">Make sure that you have the necessary permissions. To define (or edit) ATP policies, you must be assigned an appropriate role. Some examples are described in the following table:</span></span> <br>

    |<span data-ttu-id="82e2d-122">角色</span><span class="sxs-lookup"><span data-stu-id="82e2d-122">Role</span></span>  |<span data-ttu-id="82e2d-123">分配的位置/方式</span><span class="sxs-lookup"><span data-stu-id="82e2d-123">Where/how assigned</span></span>  |
    |---------|---------|
    |<span data-ttu-id="82e2d-124">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="82e2d-124">Office 365 Global Administrator</span></span> |<span data-ttu-id="82e2d-p106">默认情况下, 注册购买 Office 365 的人是全局管理员。(请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)</span><span class="sxs-lookup"><span data-stu-id="82e2d-p106">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
    |<span data-ttu-id="82e2d-127">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="82e2d-127">Security Administrator</span></span> |<span data-ttu-id="82e2d-128">Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="82e2d-128">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
    |<span data-ttu-id="82e2d-129">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="82e2d-129">Exchange Online Organization Management</span></span> |<span data-ttu-id="82e2d-130">Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="82e2d-130">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="82e2d-131">或</span><span class="sxs-lookup"><span data-stu-id="82e2d-131">or</span></span> <br>  <span data-ttu-id="82e2d-132">PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="82e2d-132">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

    <span data-ttu-id="82e2d-133">若要了解有关角色和权限的详细信息, 请参阅[Office 365 &amp;安全合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-133">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="82e2d-134">请确保将 Office 客户端配置为使用[新式验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)(这适用于 office 文档中的 ATP 安全链接保护)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-134">Make sure that Office clients are configured to use [Modern Authentication](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (this is for ATP Safe Links protection in Office documents).</span></span>
    
- <span data-ttu-id="82e2d-135">[了解 ATP 安全链接策略选项](#learn-about-atp-safe-links-policy-options)(在本文中)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-135">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article).</span></span> 

- <span data-ttu-id="82e2d-136">最长允许30分钟, 新的或更新的策略将传播到所有的 Office 365 数据中心。</span><span class="sxs-lookup"><span data-stu-id="82e2d-136">Allow up to 30 minutes for your new or updated policy to spread to all Office 365 datacenters.</span></span>
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a><span data-ttu-id="82e2d-137">步骤 2: 定义 (或查看) 适用于每个人的 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="82e2d-137">Step 2: Define (or review) the ATP Safe Links policy that applies to everyone</span></span>

<span data-ttu-id="82e2d-p107">当您拥有[Office 365 高级威胁防护功能](office-365-atp.md)时, 将拥有适用于组织中每个人的默认 ATP 安全链接策略。请务必查看, 如果需要, 请编辑您的默认策略。</span><span class="sxs-lookup"><span data-stu-id="82e2d-p107">When you have [Office 365 Advanced Threat Protection](office-365-atp.md), you will have a default ATP Safe Links policy that applies to everyone in your organization. Make sure to review, and if needed, edit your default policy.</span></span>
  
1. <span data-ttu-id="82e2d-140">转到[https://protection.office.com](https://protection.office.com)并使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="82e2d-140">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="82e2d-141">在左侧导航中的 "**威胁管理**" 下, 选择 "\*\*策略\> \*\* **安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="82e2d-141">In the left navigation, under **Threat management**, choose **Policy \>** **Safe Links**.</span></span>
    
3. <span data-ttu-id="82e2d-142">在 "**适用于整个组织的策略**" 部分, 选择 "**默认**", 然后选择 "**编辑**" ("编辑" 按钮类似于铅笔)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-142">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="82e2d-143">![单击 "编辑" 编辑安全链接保护的默认策略](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="82e2d-143">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span>
  
4. <span data-ttu-id="82e2d-p108">在 "**阻止以下 url** " 部分中, 指定要阻止组织中的用户访问的一个或多个 url。(请参阅[使用 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)。)</span><span class="sxs-lookup"><span data-stu-id="82e2d-p108">In the **Block the following URLs** section, specify one or more URLs that you want to prevent people in your organization from visiting. (See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).)</span></span>
    
5. <span data-ttu-id="82e2d-p109">在 "**应用于除电子邮件以外的内容的设置**" 部分, 选择 (或清除) 要使用的选项。(我们建议您选择所有选项。)</span><span class="sxs-lookup"><span data-stu-id="82e2d-p109">In the **Settings that apply to content except email** section, select (or clear) the options you want to use. (We recommend that you select all the options.)</span></span> 
    
6. <span data-ttu-id="82e2d-148">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="82e2d-148">Choose **Save**.</span></span>
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a><span data-ttu-id="82e2d-149">步骤 3: 添加 (或编辑) 适用于特定电子邮件收件人的 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="82e2d-149">Step 3: Add (or edit) ATP Safe Links policies that apply to specific email recipients</span></span>

<span data-ttu-id="82e2d-p110">在查看 (或编辑) 适用于每个人的默认 ATP 安全链接策略之后, 下一步是定义适用于特定收件人的其他策略。例如, 您可以通过定义其他策略来指定您的默认策略的例外。</span><span class="sxs-lookup"><span data-stu-id="82e2d-p110">After you have reviewed (or edited) the default ATP Safe Links policy that applies to everyone, your next step is to define additional policies that would apply to specific recipients. For example, you can specify exceptions to your default policy by defining an additional policy.</span></span> 
  
1. <span data-ttu-id="82e2d-152">转到[https://protection.office.com](https://protection.office.com)并使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="82e2d-152">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="82e2d-153">在左侧导航中的 "**威胁管理**" 下, 选择 "**策略**"。</span><span class="sxs-lookup"><span data-stu-id="82e2d-153">In the left navigation, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="82e2d-154">选择 "**安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="82e2d-154">Choose **Safe Links**.</span></span>
    
4. <span data-ttu-id="82e2d-155">在 "**适用于特定收件人的策略**" 部分, 选择 "**新建**" ("新建" 按钮类似**+** 于 "加号" ())。</span><span class="sxs-lookup"><span data-stu-id="82e2d-155">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)).</span></span><br/><span data-ttu-id="82e2d-156">![选择 "新建" 为特定的电子邮件收件人添加安全链接策略](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="82e2d-156">![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
5. <span data-ttu-id="82e2d-157">指定策略的名称、说明和设置。</span><span class="sxs-lookup"><span data-stu-id="82e2d-157">Specify the name, description, and settings for your policy.</span></span><br/><span data-ttu-id="82e2d-158">**示例:** 若要设置一个名为 "无直接单击" 的策略, 且不允许组织中特定组中的用户在没有 ATP 安全链接保护的情况下单击特定网站, 可以指定以下推荐设置:</span><span class="sxs-lookup"><span data-stu-id="82e2d-158">**Example:** To set up a policy called "no direct click through" that does not allow people in a certain group in your organization to click through to a specific website without ATP Safe Links protection, you might specify the following recommended settings:</span></span> 
    
  - <span data-ttu-id="82e2d-159">在 "**名称**" 框中, 键入 "无直接单击"。</span><span class="sxs-lookup"><span data-stu-id="82e2d-159">In the **Name** box, type no direct click through.</span></span>
    
  - <span data-ttu-id="82e2d-160">在 "**说明**" 框中, 键入一个说明 (如), 以防止某些组中的用户在没有 ATP 安全链接验证的情况下单击到网站。</span><span class="sxs-lookup"><span data-stu-id="82e2d-160">In the **Description** box, type a description like, Prevents people in certain groups from clicking through to a website without ATP Safe Links verification.</span></span>
    
  - <span data-ttu-id="82e2d-161">在 "**选择操作**" 部分, 选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="82e2d-161">In the **Select the action** section, choose **On**.</span></span>
    
  - <span data-ttu-id="82e2d-162">选择 "**使用安全附件扫描可下载的内容**"。</span><span class="sxs-lookup"><span data-stu-id="82e2d-162">Select **Use Safe Attachments to scan downloadable content**.</span></span>
    
  - <span data-ttu-id="82e2d-163">如果此选项可用, 请选择 "**将安全链接应用于在组织内发送的邮件"**。</span><span class="sxs-lookup"><span data-stu-id="82e2d-163">If this option is available, select **Apply Safe Links to messages sent within the organization**.</span></span>
    
  - <span data-ttu-id="82e2d-164">选择 **"不允许用户单击到原始 URL"**。</span><span class="sxs-lookup"><span data-stu-id="82e2d-164">Select **Do not allow user to click through to original URL**.</span></span>
    
  - <span data-ttu-id="82e2d-p111">(这是可选的)在 "**不重写以下 url"** 部分, 指定一个或多个被视为对您的组织而言是安全的 url。(请参阅[设置自定义 "不重写" url 列表使用 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))</span><span class="sxs-lookup"><span data-stu-id="82e2d-p111">(This is optional) In the **Do not rewrite the following URLs** section, specify one or more URLs that are considered to be safe for your organization. (See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))</span></span>
    
  - <span data-ttu-id="82e2d-p112">在 "**应用**于" 部分中, 选择 **"收件人是其成员**", 然后选择要包括在策略中的组。选择 "**添加**", 然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="82e2d-p112">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
6. <span data-ttu-id="82e2d-169">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="82e2d-169">Choose **Save**.</span></span>
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a><span data-ttu-id="82e2d-170">步骤 4: 了解 ATP 安全链接策略选项</span><span class="sxs-lookup"><span data-stu-id="82e2d-170">Step 4: Learn about ATP Safe Links policy options</span></span>

<span data-ttu-id="82e2d-p113">在设置或编辑 ATP 安全链接策略时, 将看到几个可用选项。如果您想知道这些选项是什么, 下表介绍了每一个选项及其效果。请注意, 有两种主要的 ATP 安全链接策略可供定义或编辑:</span><span class="sxs-lookup"><span data-stu-id="82e2d-p113">As you set up or edit your ATP Safe Links policies, will see several options available. In case you are wondering what these options are, the following table describes each one and its effect. Remember that there are two main kinds of ATP Safe Links policies to define or edit:</span></span>
- <span data-ttu-id="82e2d-174">适用于每个人的[默认策略](#default-policy-options)</span><span class="sxs-lookup"><span data-stu-id="82e2d-174">a [default policy](#default-policy-options) that applies to everyone</span></span> 
- <span data-ttu-id="82e2d-175">[为特定收件人定义](#policies-that-apply-to-specific-email-recipients)的其他策略</span><span class="sxs-lookup"><span data-stu-id="82e2d-175">additional [policies that are defined for specific recipients](#policies-that-apply-to-specific-email-recipients)</span></span> 

### <a name="default-policy-options"></a><span data-ttu-id="82e2d-176">默认策略选项</span><span class="sxs-lookup"><span data-stu-id="82e2d-176">Default policy options</span></span>

<span data-ttu-id="82e2d-177">默认策略选项适用于组织中的所有人。</span><span class="sxs-lookup"><span data-stu-id="82e2d-177">Default policy options apply to everyone in your organization.</span></span>

|<span data-ttu-id="82e2d-178">此选项</span><span class="sxs-lookup"><span data-stu-id="82e2d-178">This option</span></span>  |<span data-ttu-id="82e2d-179">执行的操作</span><span class="sxs-lookup"><span data-stu-id="82e2d-179">Does this</span></span>  |
|---------|---------|
| <span data-ttu-id="82e2d-180">**阻止以下 url**</span><span class="sxs-lookup"><span data-stu-id="82e2d-180">**Block the following URLs**</span></span> <br/>    | <span data-ttu-id="82e2d-p114">允许您的组织具有自动阻止的自定义 url 的自定义列表。当用户单击此列表中的某个 URL 时, 将会看到一个[警告页面](atp-safe-links-warning-pages.md), 说明为什么阻止了该 url。</span><span class="sxs-lookup"><span data-stu-id="82e2d-p114">Enables your organization to have a custom list of URLs that are automatically blocked. When users click a URL in this list, they'll be taken to a [warning page](atp-safe-links-warning-pages.md) that explains why the URL is blocked.  </span></span><br/> <span data-ttu-id="82e2d-183">若要了解详细信息, 请参阅 [使用 ATP 安全链接设置自定义阻止的 url 列表</span><span class="sxs-lookup"><span data-stu-id="82e2d-183">To learn more, see [Set up a custom blocked URLs list using ATP Safe Links</span></span>      |
| <span data-ttu-id="82e2d-184">**office 365 专业增强版、适用于 iOS 和 Android 的 office**</span><span class="sxs-lookup"><span data-stu-id="82e2d-184">**Office 365 ProPlus, Office for iOS and Android**</span></span> <br/>    | <span data-ttu-id="82e2d-185">选择此选项后, ATP 安全链接保护将应用于在 Office 365 专业增强版 (Word、Excel 和 PowerPoint on windows 或 Mac OS)、iOS 或 Android 设备上的 office 文档、windows 上的 Visio 2016 和 Office Online (word) 中打开的文档中的 url。Online、PowerPoint online、Excel Online 和 OneNote Online) (如果用户已登录 Office 365)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-185">When this option is selected, ATP Safe Links protection is applied to URLs in documents that are open in Office 365 ProPlus (Word, Excel, and PowerPoint on Windows or Mac OS), Office documents on iOS, or Android devices, Visio 2016 on Windows, and Office Online (Word Online, PowerPoint Online, Excel Online, and OneNote Online), provided the user has signed into Office 365.</span></span> <br/><br/><span data-ttu-id="82e2d-p115">如果你**在 Windows 上仅看到 office 2016**, 则功能更新尚未到达你的 office 365 环境 (即将推出)。在此之前, ATP 安全链接保护适用于在 Windows 上运行的 Word 2016、Excel 2016、PowerPoint 2016 或 Visio 2016。</span><span class="sxs-lookup"><span data-stu-id="82e2d-p115">If you see only **Office 2016 on Windows**, then the feature updates have not reached your Office 365 environment yet (and they are coming soon). Until then, ATP Safe Links protection applies to Word 2016, Excel 2016, PowerPoint 2016 or Visio 2016 running on Windows.</span></span>            |
| <span data-ttu-id="82e2d-188">**在用户单击 ATP 安全链接时不进行跟踪**</span><span class="sxs-lookup"><span data-stu-id="82e2d-188">**Don't track when users click ATP Safe Links**</span></span> <br/>  | <span data-ttu-id="82e2d-189">选择此选项后, 将不存储在 Word、Excel、PowerPoint 和 Visio 文档中的 url 的数据。</span><span class="sxs-lookup"><span data-stu-id="82e2d-189">When this option is selected, click data for URLs in Word, Excel, PowerPoint, and Visio documents is not stored.</span></span>  <br/> |
|<span data-ttu-id="82e2d-190">**不要让用户点击到原始 URL 的 ATP 安全链接**</span><span class="sxs-lookup"><span data-stu-id="82e2d-190">**Don't let users click through ATP Safe Links to original URL**</span></span> <br/> |<span data-ttu-id="82e2d-191">选择此选项后, 用户将无法继续处理被确定为恶意的 URL 之后的[警告页](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-191">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a><span data-ttu-id="82e2d-192">适用于特定电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="82e2d-192">Policies that apply to specific email recipients</span></span>

|<span data-ttu-id="82e2d-193">此选项</span><span class="sxs-lookup"><span data-stu-id="82e2d-193">This option</span></span>  |<span data-ttu-id="82e2d-194">执行的操作</span><span class="sxs-lookup"><span data-stu-id="82e2d-194">Does this</span></span>  |
|---------|---------|
|<span data-ttu-id="82e2d-195">**关**</span><span class="sxs-lookup"><span data-stu-id="82e2d-195">**Off**</span></span> <br/> |<span data-ttu-id="82e2d-196">不扫描电子邮件中的 url。</span><span class="sxs-lookup"><span data-stu-id="82e2d-196">Does not scan URLs in email messages.</span></span>  <br/> <span data-ttu-id="82e2d-197">使您能够定义例外规则, 如不扫描电子邮件中的 url 的特定收件人组的 url 的规则。</span><span class="sxs-lookup"><span data-stu-id="82e2d-197">Enables you to define an exception rule, such as a rule that does not scan URLs in email messages for a specific group of recipients.</span></span>  <br/> |
|<span data-ttu-id="82e2d-198">**中**</span><span class="sxs-lookup"><span data-stu-id="82e2d-198">**On**</span></span> <br/> |<span data-ttu-id="82e2d-199">通过在用户单击电子邮件中的 url 时, 通过 ATP 安全链接保护来重写 url 以路由用户。</span><span class="sxs-lookup"><span data-stu-id="82e2d-199">Rewrites URLs to route users through ATP Safe Links protection when the users click URLs in email messages.</span></span>  <br/> <span data-ttu-id="82e2d-200">对被阻止或恶意 url 的列表单击时检查 URL。</span><span class="sxs-lookup"><span data-stu-id="82e2d-200">Checks a URL when clicked against a list of blocked or malicious URLs.</span></span>  <br/> |
|<span data-ttu-id="82e2d-201">**使用安全附件扫描可下载的内容**</span><span class="sxs-lookup"><span data-stu-id="82e2d-201">**Use Safe Attachments to scan downloadable content**</span></span> <br/> |<span data-ttu-id="82e2d-202">如果选择此选项, 则会扫描指向可下载内容的 url。</span><span class="sxs-lookup"><span data-stu-id="82e2d-202">When this option is selected, URLs that point to downloadable content are scanned.</span></span>  <br/> |
|<span data-ttu-id="82e2d-203">**将安全链接应用于在组织内发送的邮件**</span><span class="sxs-lookup"><span data-stu-id="82e2d-203">**Apply Safe Links to messages sent within the organization**</span></span> <br/> | <span data-ttu-id="82e2d-204">当此选项可用并选中时, 如果电子邮件帐户托管在 Office 365 中, 则会将 ATP 安全链接保护应用于在组织中的人员之间发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="82e2d-204">When this option is available and selected, ATP Safe Links protection is applied to email messages sent between people in your organization, provided the email accounts are hosted in Office 365.</span></span>  <br/> |
|<span data-ttu-id="82e2d-205">**不跟踪用户点击**</span><span class="sxs-lookup"><span data-stu-id="82e2d-205">**Do not track user clicks**</span></span> <br/> |<span data-ttu-id="82e2d-p116">选择此选项后, 请单击 "来自外部发件人的电子邮件中的 url 数据未存储"。URL 单击 "跟踪" 以查找在组织内发送的电子邮件中的链接当前不受支持。</span><span class="sxs-lookup"><span data-stu-id="82e2d-p116">When this option is selected, click data for URLs in email from external senders is not stored. URL click tracking for links within email messages sent within the organization is currently not supported.</span></span>  <br/> |
|<span data-ttu-id="82e2d-208">**不允许用户单击到原始 URL**</span><span class="sxs-lookup"><span data-stu-id="82e2d-208">**Do not allow users to click through to original URL**</span></span> <br/> |<span data-ttu-id="82e2d-209">选择此选项后, 用户将无法继续处理被确定为恶意的 URL 之后的[警告页](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-209">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |
|<span data-ttu-id="82e2d-210">**不重写以下 url**</span><span class="sxs-lookup"><span data-stu-id="82e2d-210">**Do not rewrite the following URLs**</span></span> <br/> |<span data-ttu-id="82e2d-p117">将 url 保留为。保留自定义不需要在组织中对特定电子邮件收件人组进行扫描的安全 url 列表。 有关更多详细信息 (包括对通配符星号 (\*) 支持的最新更改), 请参阅[设置自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-p117">Leaves URLs as they are. Keeps a custom list of safe URLs that don't need scanning for a specific group of email recipients in your organization.  See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for more details, including recent changes to support for wildcard asterisks (\*).  </span></span><br/> |
   
## <a name="next-steps"></a><span data-ttu-id="82e2d-214">后续步骤</span><span class="sxs-lookup"><span data-stu-id="82e2d-214">Next steps</span></span>

<span data-ttu-id="82e2d-p118">在 ATP 安全链接策略准备就绪后, 您可以通过查看报告了解 atp 在 orgnization 中的工作原理。若要了解详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="82e2d-p118">Once your ATP Safe Links policies are in place, you can see how ATP is working for your orgnization by viewing reports. See the following resources to learn more:</span></span>

- [<span data-ttu-id="82e2d-217">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="82e2d-217">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

- [<span data-ttu-id="82e2d-218">在安全&amp;合规中心中使用资源管理器</span><span class="sxs-lookup"><span data-stu-id="82e2d-218">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)

<span data-ttu-id="82e2d-p119">继续在新功能的前面提供 ATP。访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)并了解要[添加到 ATP 的新功能](office-365-atp.md#new-features-in-office-365-atp)。</span><span class="sxs-lookup"><span data-stu-id="82e2d-p119">Stay on top of new features coming to ATP. visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) and learn about [new features that are being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span>
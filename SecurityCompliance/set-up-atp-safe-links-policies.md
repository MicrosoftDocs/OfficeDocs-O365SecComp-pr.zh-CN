---
title: 设置 Office 365 ATP 安全链接策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 11/02/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
description: 设置以从 Word、 Excel、 PowerPoint 和 Visio 文件中以及电子邮件中的恶意链接保护您的组织的安全链接策略。
ms.openlocfilehash: 823dc6073dfa6302f19154a86bafa7f19d5affdc
ms.sourcegitcommit: 49abeb8e57a5ee622d72a3782175a989b1a2e3c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25935549"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a><span data-ttu-id="4821f-103">设置 Office 365 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="4821f-103">Set up Office 365 ATP Safe Links policies</span></span>

<span data-ttu-id="4821f-p101">[ATP 安全链接](atp-safe-links.md)， [Office 365 高级威胁保护](office-365-atp.md)(ATP) 的一项功能可帮助您的组织防止恶意欺诈和其他攻击中使用的链接。如果您有必要[Office 365 安全性分配权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)，您可以设置 ATP 安全链接策略以帮助确保当人员单击 web 地址 (Url) 时，保护您的组织。可以将 ATP 安全链接策略配置为扫描电子邮件中的 Url 和 Office 文档中的 Url。</span><span class="sxs-lookup"><span data-stu-id="4821f-p101">[ATP Safe Links](atp-safe-links.md) , a feature of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), can help protect your organization from malicious links used in phishing and other attacks. If you have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can set up ATP Safe Links policies to help ensure that when people click web addresses (URLs), your organization is protected. Your ATP Safe Links policies can be configured to scan URLs in email and URLs in Office documents.</span></span>
  
<span data-ttu-id="4821f-p102">[ATP 安全链接到不断添加了新功能](atp-safe-links.md#new-features-are-continually-being-added-to-atp-safe-links)。添加新功能时，您可能需要对您现有的 ATP 安全链接策略进行调整。</span><span class="sxs-lookup"><span data-stu-id="4821f-p102">[New features are continually being added to ATP Safe Links](atp-safe-links.md#new-features-are-continually-being-added-to-atp-safe-links). As new features are added, you may need to make adjustments to your existing ATP Safe Links policies.</span></span>

## <a name="what-to-do"></a><span data-ttu-id="4821f-109">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="4821f-109">What to do</span></span> 
  
1. <span data-ttu-id="4821f-110">[查看先决条件](#review-the-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="4821f-110">[Review the prerequisites](#review-the-prerequisites).</span></span>
    
2. <span data-ttu-id="4821f-p103">[查看和编辑默认 ATP 安全链接策略可应用于所有人](#define-an-atp-safe-links-policy-that-applies-to-everyone)。例如，您可以[设置 ATP 安全链接阻止您自定义 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="4821f-p103">[Review and edit the default ATP Safe Links policy that applies to everyone](#define-an-atp-safe-links-policy-that-applies-to-everyone). For example, you can [set up your custom blocked URLs list for ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span>
    
3. <span data-ttu-id="4821f-113">[为特定的电子邮件收件人添加或编辑策略](#add-a-policy-for-specific-email-recipients)，包括[您自定义"执行不重写"Url 列表 ATP 安全链接的设置](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="4821f-113">[Add or edit policies for specific email recipients](#add-a-policy-for-specific-email-recipients), including [setting up your custom "Do not rewrite" URLs list for ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
    
4. <span data-ttu-id="4821f-114">[了解 ATP 安全链接策略选项](#learn-about-atp-safe-links-policy-options)（本文中），包括的最新更改的设置</span><span class="sxs-lookup"><span data-stu-id="4821f-114">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article), including settings for recent changes</span></span>
    
## <a name="step-1-review-the-prerequisites"></a><span data-ttu-id="4821f-115">步骤 1： 查看必备组件</span><span class="sxs-lookup"><span data-stu-id="4821f-115">Step 1: Review the prerequisites</span></span>

- <span data-ttu-id="4821f-116">请确保您的组织具有[Office 365 高级威胁保护](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="4821f-116">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>
    
- <span data-ttu-id="4821f-p104">请确保您具有定义或编辑 ATP 策略所需的权限。请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="4821f-p104">Make sure that you have the necessary permissions to define or edit ATP policies. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="4821f-119">确保 Office 客户端被配置为使用[现代身份验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)（这适用于在 Office 文档中的安全链接 ATP 保护）。</span><span class="sxs-lookup"><span data-stu-id="4821f-119">Make sure that Office clients are configured to use [Modern Authentication](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (this is for ATP Safe Links protection in Office documents).</span></span>
    
- <span data-ttu-id="4821f-120">[了解 ATP 安全链接策略选项](#learn-about-atp-safe-links-policy-options)（本文中）。</span><span class="sxs-lookup"><span data-stu-id="4821f-120">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article).</span></span> 

- <span data-ttu-id="4821f-121">允许最多 30 分钟的新的或更新策略传播到所有 Office 365 数据中心。</span><span class="sxs-lookup"><span data-stu-id="4821f-121">Allow up to 30 minutes for your new or updated policy to spread to all Office 365 datacenters.</span></span>
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a><span data-ttu-id="4821f-122">步骤 2： 定义 （或查看） ATP 安全链接策略应用于所有人</span><span class="sxs-lookup"><span data-stu-id="4821f-122">Step 2: Define (or review) the ATP Safe Links policy that applies to everyone</span></span>

<span data-ttu-id="4821f-p105">Office 365 企业版中有高级威胁保护，您可以在适用于您的组织中的每个人的默认 ATP 安全链接策略。请务必查看，，如果需要编辑默认策略。</span><span class="sxs-lookup"><span data-stu-id="4821f-p105">When you have Advanced Threat Protection in Office 365 Enterprise, you will have a default ATP Safe Links policy that applies to everyone in your organization. Make sure to review, and if needed, edit your default policy.</span></span>
  
1. <span data-ttu-id="4821f-125">转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4821f-125">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="4821f-126">在左侧导航窗格中，**威胁管理**下面，选择**策略\>\*\*\*\*安全的链接**。</span><span class="sxs-lookup"><span data-stu-id="4821f-126">In the left navigation, under **Threat management**, choose **Policy \>** **Safe Links**.</span></span>
    
3. <span data-ttu-id="4821f-127">在**应用于整个组织的策略**部分中，选择**默认**，，然后选择**编辑**（编辑按钮图像类似铅笔）。</span><span class="sxs-lookup"><span data-stu-id="4821f-127">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span> 
    
    ![单击编辑来编辑您的安全链接保护的默认策略](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. <span data-ttu-id="4821f-p106">在**阻止以下 Url**部分中，指定您想要阻止访问从组织中的人员的一个或多个 Url。（请参阅[设置自定义阻止 Url 列表使用 ATP 安全链接](set-up-a-custom-blocked-urls-list-wtih-atp.md)）。</span><span class="sxs-lookup"><span data-stu-id="4821f-p106">In the **Block the following URLs** section, specify one or more URLs that you want to prevent people in your organization from visiting. (See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).)</span></span>
    
5. <span data-ttu-id="4821f-p107">在**设置，将应用于除电子邮件的内容**部分中，选中 （或清除） 您想要使用的选项。（我们建议您选择的所有选项。）</span><span class="sxs-lookup"><span data-stu-id="4821f-p107">In the **Settings that apply to content except email** section, select (or clear) the options you want to use. (We recommend that you select all the options.)</span></span> 
    
6. <span data-ttu-id="4821f-133">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="4821f-133">Choose **Save**.</span></span>
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a><span data-ttu-id="4821f-134">步骤 3： 添加 （或编辑） ATP 安全链接策略将应用于特定的电子邮件收件人</span><span class="sxs-lookup"><span data-stu-id="4821f-134">Step 3: Add (or edit) ATP Safe Links policies that apply to specific email recipients</span></span>

<span data-ttu-id="4821f-p108">您已审阅 （或编辑） 适用于每个人的默认 ATP 安全链接策略后下, 一步是定义将应用于特定收件人的其他策略。例如，您可以通过定义其他策略为默认策略指定例外。</span><span class="sxs-lookup"><span data-stu-id="4821f-p108">After you have reviewed (or edited) the default ATP Safe Links policy that applies to everyone, your next step is to define additional policies that would apply to specific recipients. For example, you can specify exceptions to your default policy by defining an additional policy.</span></span> 
  
1. <span data-ttu-id="4821f-137">转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="4821f-137">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="4821f-138">在左侧导航窗格中，**威胁管理**下面，选择**策略**。</span><span class="sxs-lookup"><span data-stu-id="4821f-138">In the left navigation, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="4821f-139">选择**安全的链接**。</span><span class="sxs-lookup"><span data-stu-id="4821f-139">Choose **Safe Links**.</span></span>
    
4. <span data-ttu-id="4821f-140">在**的可以应用到特定收件人的策略**部分中，选择**新建**(新建按钮图像类似一个加号 ( **+**))。</span><span class="sxs-lookup"><span data-stu-id="4821f-140">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)).</span></span><br/><span data-ttu-id="4821f-141">![选择新建以添加特定的电子邮件收件人的安全链接策略](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="4821f-141">![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
5. <span data-ttu-id="4821f-142">指定策略的名称、说明和设置。</span><span class="sxs-lookup"><span data-stu-id="4821f-142">Specify the name, description, and settings for your policy.</span></span><br/><span data-ttu-id="4821f-143">**示例：** 若要设置名为"通过没有直接单击"不允许人员没有 ATP 安全链接保护的特定网站点阅贵组织中的特定组中的策略，您可以指定以下建议的设置：</span><span class="sxs-lookup"><span data-stu-id="4821f-143">**Example:** To set up a policy called "no direct click through" that does not allow people in a certain group in your organization to click through to a specific website without ATP Safe Links protection, you might specify the following recommended settings:</span></span> 
    
  - <span data-ttu-id="4821f-144">在**名称**框中，键入没有直接点击率。</span><span class="sxs-lookup"><span data-stu-id="4821f-144">In the **Name** box, type no direct click through.</span></span>
    
  - <span data-ttu-id="4821f-145">在**说明**框中，键入类似，防止通过单击而无需 ATP 安全链接验证的网站中的特定组中的人员的说明。</span><span class="sxs-lookup"><span data-stu-id="4821f-145">In the **Description** box, type a description like, Prevents people in certain groups from clicking through to a website without ATP Safe Links verification.</span></span>
    
  - <span data-ttu-id="4821f-146">在**选择操作**部分中，选择**上**。</span><span class="sxs-lookup"><span data-stu-id="4821f-146">In the **Select the action** section, choose **On**.</span></span>
    
  - <span data-ttu-id="4821f-147">选择**使用安全附件扫描可下载的内容**。</span><span class="sxs-lookup"><span data-stu-id="4821f-147">Select **Use Safe Attachments to scan downloadable content**.</span></span>
    
  - <span data-ttu-id="4821f-148">如果此选项才可用，选择**应用发送组织内的邮件的安全链接**。</span><span class="sxs-lookup"><span data-stu-id="4821f-148">If this option is available, select **Apply Safe Links to messages sent within the organization**.</span></span>
    
  - <span data-ttu-id="4821f-149">选择**不允许用户通过单击到原始 URL**。</span><span class="sxs-lookup"><span data-stu-id="4821f-149">Select **Do not allow user to click through to original URL**.</span></span>
    
  - <span data-ttu-id="4821f-p109">（这是可选的）在**不重写以下 Url**部分中，指定一个或多个被视为安全的组织的 Url。（请参阅[设置自定义"执行不重写"Url 列表使用 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)）</span><span class="sxs-lookup"><span data-stu-id="4821f-p109">(This is optional) In the **Do not rewrite the following URLs** section, specify one or more URLs that are considered to be safe for your organization. (See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))</span></span>
    
  - <span data-ttu-id="4821f-p110">在**应用于**部分中，选择**收件人是的成员**，，然后选择您想要包括在您的策略的组。选择**添加**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="4821f-p110">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
6. <span data-ttu-id="4821f-154">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="4821f-154">Choose **Save**.</span></span>
    
## <a name="step-5-learn-about-atp-safe-links-policy-options"></a><span data-ttu-id="4821f-155">第 5 步： 了解 ATP 安全链接策略选项</span><span class="sxs-lookup"><span data-stu-id="4821f-155">Step 5: Learn about ATP Safe Links policy options</span></span>

<span data-ttu-id="4821f-p111">设置或编辑 ATP 安全链接策略时，将看到可用的几个选项。如果您想知道这些选项什么下, 表介绍每个和受到影响。</span><span class="sxs-lookup"><span data-stu-id="4821f-p111">As you set up or edit your ATP Safe Links policies, will see several options available. In case you are wondering what these options are, the following table describes each one and its effect.</span></span> 

<span data-ttu-id="4821f-p112">有两种主要的策略定义或编辑： 适用于每个人的默认策略和其他策略定义的特定收件人。下表中的**为此策略**列中对那些的区别在于。</span><span class="sxs-lookup"><span data-stu-id="4821f-p112">There are two main kinds of policies to define or edit: a default policy that applies to everyone, and additional policies that are defined for specific recipients. Those are differentiated in the **For this policy** column in the following table.</span></span>
  
|<span data-ttu-id="4821f-160">**此策略**</span><span class="sxs-lookup"><span data-stu-id="4821f-160">**For this policy**</span></span>|<span data-ttu-id="4821f-161">**此选项**</span><span class="sxs-lookup"><span data-stu-id="4821f-161">**This option**</span></span>|<span data-ttu-id="4821f-162">**执行的操作**</span><span class="sxs-lookup"><span data-stu-id="4821f-162">**Does this**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4821f-163">默认 （定义后，默认策略适用于组织中的每个人）</span><span class="sxs-lookup"><span data-stu-id="4821f-163">Default (once defined, the default policy applies to everyone in the organization)</span></span>  <br/> |<span data-ttu-id="4821f-164">**阻止以下 Url**</span><span class="sxs-lookup"><span data-stu-id="4821f-164">**Block the following URLs**</span></span> <br/> |<span data-ttu-id="4821f-p113">允许贵组织拥有的自动阻止 Url 的自定义列表。当用户单击此列表中的 URL 时，它们将转到说明为什么阻止 URL[页警告](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="4821f-p113">Enables your organization to have a custom list of URLs that are automatically blocked. When users click a URL in this list, they'll be taken to a [warning page](atp-safe-links-warning-pages.md) that explains why the URL is blocked.  </span></span><br/> <span data-ttu-id="4821f-167">请参阅的详细信息，如新添加支持多达三个通配符星号的[设置使用 ATP 安全链接的自定义阻止 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)(\*)。</span><span class="sxs-lookup"><span data-stu-id="4821f-167">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md) for more details, such as newly added support for up to three wildcard asterisks (\*).</span></span>  <br/> |
|<span data-ttu-id="4821f-168">默认</span><span class="sxs-lookup"><span data-stu-id="4821f-168">Default</span></span>  <br/> |<span data-ttu-id="4821f-169">**Office 365 ProPlus，适用于 iOS 的 Office 和 Android**</span><span class="sxs-lookup"><span data-stu-id="4821f-169">**Office 365 ProPlus, Office for iOS and Android**</span></span> <br/> |<span data-ttu-id="4821f-170">选中此选项后，ATP 安全链接保护文档中的应用到 Url 中打开 Office 365 ProPlus （Word、 Excel 和 PowerPoint 在 Windows 或 Mac 操作系统上的） iOS 或 Android 设备，在 Windows 和 Office Online (Word Visio 2016 上的 Office 文档Online、 PowerPoint Online、 Excel Online 和 OneNote Online），提供用户已登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4821f-170">When this option is selected, ATP Safe Links protection is applied to URLs in documents that are open in Office 365 ProPlus (Word, Excel, and PowerPoint on Windows or Mac OS), Office documents on iOS, or Android devices, Visio 2016 on Windows, and Office Online (Word Online, PowerPoint Online, Excel Online, and OneNote Online), provided the user has signed into Office 365.</span></span> <br/><br/><span data-ttu-id="4821f-p114">如果您看到仅**在 Windows 上的 Office 2016**，然后功能更新尚未达到 Office 365 环境尚未 （和即将推出）。之前，ATP 安全链接保护适用于 Word 2016、 Excel 2016、 PowerPoint 2016 或 Visio 2016 Windows 上运行。</span><span class="sxs-lookup"><span data-stu-id="4821f-p114">If you see only **Office 2016 on Windows**, then the feature updates have not reached your Office 365 environment yet (and they are coming soon). Until then, ATP Safe Links protection applies to Word 2016, Excel 2016, PowerPoint 2016 or Visio 2016 running on Windows.</span></span>           |
|<span data-ttu-id="4821f-173">默认</span><span class="sxs-lookup"><span data-stu-id="4821f-173">Default</span></span>  <br/> |<span data-ttu-id="4821f-174">**当用户单击 ATP 安全链接不跟踪**</span><span class="sxs-lookup"><span data-stu-id="4821f-174">**Don't track when users click ATP Safe Links**</span></span> <br/> |<span data-ttu-id="4821f-175">选中此选项后，单击数据的 Word、 Excel、 PowerPoint 和 Visio 文档中的 Url，而未存储。</span><span class="sxs-lookup"><span data-stu-id="4821f-175">When this option is selected, click data for URLs in Word, Excel, PowerPoint, and Visio documents is not stored.</span></span>  <br/> |
|<span data-ttu-id="4821f-176">默认</span><span class="sxs-lookup"><span data-stu-id="4821f-176">Default</span></span>  <br/> |<span data-ttu-id="4821f-177">**不要让用户单击通过 ATP 原始 URL 的安全链接**</span><span class="sxs-lookup"><span data-stu-id="4821f-177">**Don't let users click through ATP Safe Links to original URL**</span></span> <br/> |<span data-ttu-id="4821f-178">选中此选项后，用户将无法继续过[警告页](atp-safe-links-warning-pages.md)被确定为恶意 url。</span><span class="sxs-lookup"><span data-stu-id="4821f-178">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |
|<span data-ttu-id="4821f-179">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="4821f-179">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="4821f-180">**关**</span><span class="sxs-lookup"><span data-stu-id="4821f-180">**Off**</span></span> <br/> |<span data-ttu-id="4821f-181">不扫描电子邮件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="4821f-181">Does not scan URLs in email messages.</span></span>  <br/> <span data-ttu-id="4821f-182">可以定义例外规则，例如不扫描 Url 电子邮件中一组特定的收件人的规则。</span><span class="sxs-lookup"><span data-stu-id="4821f-182">Enables you to define an exception rule, such as a rule that does not scan URLs in email messages for a specific group of recipients.</span></span>  <br/> |
|<span data-ttu-id="4821f-183">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="4821f-183">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="4821f-184">**在**</span><span class="sxs-lookup"><span data-stu-id="4821f-184">**On**</span></span> <br/> |<span data-ttu-id="4821f-185">当用户单击 Url 电子邮件中，可向路由用户通过 ATP 安全链接保护 Url。</span><span class="sxs-lookup"><span data-stu-id="4821f-185">Rewrites URLs to route users through ATP Safe Links protection when the users click URLs in email messages.</span></span>  <br/> <span data-ttu-id="4821f-186">检查时针对阻止列表或恶意 Url 的列表的 URL。</span><span class="sxs-lookup"><span data-stu-id="4821f-186">Checks a URL when clicked against a list of blocked or malicious URLs.</span></span>  <br/> |
|<span data-ttu-id="4821f-187">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="4821f-187">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="4821f-188">**使用安全附件扫描可下载内容**</span><span class="sxs-lookup"><span data-stu-id="4821f-188">**Use Safe Attachments to scan downloadable content**</span></span> <br/> |<span data-ttu-id="4821f-189">选中此选项后，会扫描指向可下载内容的 Url。</span><span class="sxs-lookup"><span data-stu-id="4821f-189">When this option is selected, URLs that point to downloadable content are scanned.</span></span>  <br/> |
|<span data-ttu-id="4821f-190">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="4821f-190">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="4821f-191">**适用于组织中发送的邮件的安全链接**</span><span class="sxs-lookup"><span data-stu-id="4821f-191">**Apply Safe Links to messages sent within the organization**</span></span> <br/> | <span data-ttu-id="4821f-192">可用并选中此选项时，为您提供的电子邮件帐户的组织中的人员之间发送的邮件位于 Office 365 中的电子邮件应用 ATP 安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="4821f-192">When this option is available and selected, ATP Safe Links protection is applied to email messages sent between people in your organization, provided the email accounts are hosted in Office 365.</span></span>  <br/> |
|<span data-ttu-id="4821f-193">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="4821f-193">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="4821f-194">**不跟踪用户单击**</span><span class="sxs-lookup"><span data-stu-id="4821f-194">**Do not track user clicks**</span></span> <br/> |<span data-ttu-id="4821f-p115">选中此选项后，单击数据为来自外部发件人的电子邮件中的 Url，而未存储。当前不支持 URL 单击跟踪的组织中发送的电子邮件中的链接。</span><span class="sxs-lookup"><span data-stu-id="4821f-p115">When this option is selected, click data for URLs in email from external senders is not stored. URL click tracking for links within email messages sent within the organization is currently not supported.</span></span>  <br/> |
|<span data-ttu-id="4821f-197">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="4821f-197">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="4821f-198">**不允许用户通过单击到原始 URL**</span><span class="sxs-lookup"><span data-stu-id="4821f-198">**Do not allow users to click through to original URL**</span></span> <br/> |<span data-ttu-id="4821f-199">选中此选项后，用户将无法继续过[警告页](atp-safe-links-warning-pages.md)被确定为恶意 url。</span><span class="sxs-lookup"><span data-stu-id="4821f-199">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |
|<span data-ttu-id="4821f-200">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="4821f-200">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="4821f-201">**不重写以下 Url**</span><span class="sxs-lookup"><span data-stu-id="4821f-201">**Do not rewrite the following URLs**</span></span> <br/> |<span data-ttu-id="4821f-p116">与离开 Url。保留自定义列表的安全无需扫描一组特定的电子邮件收件人在组织中的 Url。 请参阅的详细信息，包括支持的通配符星号的最新更改的[设置自定义"执行不重写"Url 列表使用 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)(\*)。</span><span class="sxs-lookup"><span data-stu-id="4821f-p116">Leaves URLs as they are. Keeps a custom list of safe URLs that don't need scanning for a specific group of email recipients in your organization.  See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for more details, including recent changes to support for wildcard asterisks (\*).  </span></span><br/> |
   
## <a name="related-topics"></a><span data-ttu-id="4821f-205">相关主题</span><span class="sxs-lookup"><span data-stu-id="4821f-205">Related topics</span></span>

[<span data-ttu-id="4821f-206">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="4821f-206">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="4821f-207">Office 365 中的 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="4821f-207">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="4821f-208">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="4821f-208">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="4821f-209">设置自定义阻止 Url 列表使用 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="4821f-209">Set up a custom blocked URLs list using ATP Safe Links</span></span>](set-up-a-custom-blocked-urls-list-wtih-atp.md)
  
[<span data-ttu-id="4821f-210">设置自定义"执行不重写"Url 列表使用 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="4821f-210">Set up a custom "Do not rewrite" URLs list using ATP Safe Links</span></span>](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
  
[<span data-ttu-id="4821f-211">查看高级威胁保护报告</span><span class="sxs-lookup"><span data-stu-id="4821f-211">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="4821f-212">Office 365 安全性权限&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="4821f-212">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  


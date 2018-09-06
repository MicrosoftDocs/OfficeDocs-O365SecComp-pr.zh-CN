---
title: 设置 Office 365 ATP 安全链接策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
description: 设置以从 Word、 Excel、 PowerPoint 和 Visio 文件中以及电子邮件中的恶意链接保护您的组织的安全链接策略。
ms.openlocfilehash: a0c88a81503555417c16501ec9283cf2316c6d09
ms.sourcegitcommit: a8884b9675559018e1fddec1c0cc2de0bc3bdde5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "23839972"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a><span data-ttu-id="1631a-103">设置 Office 365 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="1631a-103">Set up Office 365 ATP Safe Links policies</span></span>

<span data-ttu-id="1631a-p101">[ATP 安全链接](atp-safe-links.md)， [Office 365 高级威胁保护](office-365-atp.md)(ATP) 的一项功能可帮助您的组织防止恶意欺诈和其他攻击中使用的链接。如果您有必要[Office 365 安全性分配权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)，您可以设置 ATP 安全链接策略以帮助确保当人员单击 web 地址 (Url) 时，保护您的组织。可以将 ATP 安全链接策略配置为扫描电子邮件中的 Url 和 Office 文档中的 Url。</span><span class="sxs-lookup"><span data-stu-id="1631a-p101">[ATP Safe Links](atp-safe-links.md) , a feature of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), can help protect your organization from malicious links used in phishing and other attacks. If you have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can set up ATP Safe Links policies to help ensure that when people click web addresses (URLs), your organization is protected. Your ATP Safe Links policies can be configured to scan URLs in email and URLs in Office documents.</span></span>
  
<span data-ttu-id="1631a-107">不断到 ATP 安全链接添加了新功能：</span><span class="sxs-lookup"><span data-stu-id="1631a-107">New features are continually being added to ATP Safe Links:</span></span>
  
- <span data-ttu-id="1631a-108">在最晚年 10 月 2017，扩展 ATP 安全链接保护应用于为 Office 365 ProPlus 的文档，如 Word、 Excel、 PowerPoint Windows、 iOS 和 Android 设备和 Windows 上的 Visio 文件中的 Url 或电子邮件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="1631a-108">In late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint on Windows, iOS, and Android devices, and Visio files on Windows.</span></span>
    
- <span data-ttu-id="1631a-109">从开始年 3 月 2018年，被扩展 ATP 安全链接保护应用于组织中的用户之间发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1631a-109">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people in an organization.</span></span>
    
- <span data-ttu-id="1631a-110">从开始后期年 3 月 2018年，ATP 安全链接保护扩展要应用于在 Office Online （Word Online、 Excel Online、 PowerPoint Online 和 OneNote 联机） 和 Office 365 ProPlus Mac 操作系统上的 Url。</span><span class="sxs-lookup"><span data-stu-id="1631a-110">Beginning in late March 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac OS.</span></span>
    
- <span data-ttu-id="1631a-111">从开始年 5 月 2018年，[警告页面](atp-safe-links-warning-pages.md)更新与新的配色方案、 更多详细信息，和以继续前进到而不考虑给定的建议的网站的功能。</span><span class="sxs-lookup"><span data-stu-id="1631a-111">Beginning in May 2018, [warning pages](atp-safe-links-warning-pages.md) are updated with a new color scheme, more details, and the ability to continue to a site despite the given recommendations.</span></span> 

<span data-ttu-id="1631a-112">添加新功能时，您可能需要对您现有的 ATP 安全链接策略进行调整。</span><span class="sxs-lookup"><span data-stu-id="1631a-112">As new features are added, you may need to make adjustments to your existing ATP Safe Links policies.</span></span>

## <a name="what-to-do"></a><span data-ttu-id="1631a-113">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="1631a-113">What to do</span></span> 
  
1. <span data-ttu-id="1631a-114">[查看先决条件](#review-the-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="1631a-114">[Review the prerequisites](#review-the-prerequisites).</span></span>
    
2. <span data-ttu-id="1631a-p102">[查看和编辑默认 ATP 安全链接策略可应用于所有人](#define-an-atp-safe-links-policy-that-applies-to-everyone)。例如，您可以[设置 ATP 安全链接阻止您自定义 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="1631a-p102">[Review and edit the default ATP Safe Links policy that applies to everyone](#define-an-atp-safe-links-policy-that-applies-to-everyone). For example, you can [set up your custom blocked URLs list for ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span>
    
3. <span data-ttu-id="1631a-117">[添加特定的电子邮件收件人的策略](#add-a-policy-for-specific-email-recipients)，包括[您自定义"执行不重写"Url 列表 ATP 安全链接的设置](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="1631a-117">[Add a policy for specific email recipients](#add-a-policy-for-specific-email-recipients), including [setting up your custom "Do not rewrite" URLs list for ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
    
4. <span data-ttu-id="1631a-118">[了解 ATP 安全链接策略选项](#learn-about-atp-safe-links-policy-options)（本文中），包括的最新更改的设置</span><span class="sxs-lookup"><span data-stu-id="1631a-118">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article), including settings for recent changes</span></span>
    
## <a name="review-the-prerequisites"></a><span data-ttu-id="1631a-119">查看先决条件</span><span class="sxs-lookup"><span data-stu-id="1631a-119">Review the prerequisites</span></span>

- <span data-ttu-id="1631a-120">请确保您的组织具有[Office 365 高级威胁保护](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="1631a-120">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>
    
- <span data-ttu-id="1631a-121">请确保您具有必要[Office 365 安全性分配权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1631a-121">Make sure that you have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="1631a-122">[了解 ATP 安全链接策略选项](#learn-about-atp-safe-links-policy-options)（本文中）。</span><span class="sxs-lookup"><span data-stu-id="1631a-122">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article).</span></span> 
    
- <span data-ttu-id="1631a-123">允许最多 30 分钟的新的或更新策略传播到所有 Office 365 数据中心。</span><span class="sxs-lookup"><span data-stu-id="1631a-123">Allow up to 30 minutes for your new or updated policy to spread to all Office 365 datacenters.</span></span>
    
## <a name="define-an-atp-safe-links-policy-that-applies-to-everyone"></a><span data-ttu-id="1631a-124">定义适用于每个人的 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="1631a-124">Define an ATP Safe Links policy that applies to everyone</span></span>

<span data-ttu-id="1631a-p103">Office 365 企业版中有高级威胁保护，您可以在适用于您的组织中的每个人的默认 ATP 安全链接策略。您可以编辑您的策略任一安全中&amp;合规性中心或 Exchange 管理员中心。**我们建议使用安全&amp;合规性中心以查看或编辑任何 ATP 策略**。</span><span class="sxs-lookup"><span data-stu-id="1631a-p103">When you have Advanced Threat Protection in Office 365 Enterprise, you will have a default ATP Safe Links policy that applies to everyone in your organization. You can edit your policy in either the Security &amp; Compliance Center or the Exchange admin center. **We recommend using the Security &amp; Compliance Center to review or edit any of your ATP policies**.</span></span>
  
1. <span data-ttu-id="1631a-128">转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="1631a-128">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="1631a-129">在左侧导航窗格中，**威胁管理**下面，选择**策略\>\*\*\*\*安全的链接**。</span><span class="sxs-lookup"><span data-stu-id="1631a-129">In the left navigation, under **Threat management**, choose **Policy \>** **Safe Links**.</span></span>
    
3. <span data-ttu-id="1631a-130">在**应用于整个组织的策略**部分中，选择**默认**，，然后选择**编辑**（编辑按钮图像类似铅笔）。</span><span class="sxs-lookup"><span data-stu-id="1631a-130">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span> 
    
    ![单击编辑来编辑您的安全链接保护的默认策略](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. <span data-ttu-id="1631a-p104">在**阻止以下 Url**部分中，指定您想要阻止访问从组织中的人员的一个或多个 Url。（请参阅[设置自定义阻止 Url 列表使用 ATP 安全链接](set-up-a-custom-blocked-urls-list-wtih-atp.md)）。</span><span class="sxs-lookup"><span data-stu-id="1631a-p104">In the **Block the following URLs** section, specify one or more URLs that you want to prevent people in your organization from visiting. (See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).)</span></span>
    
5. <span data-ttu-id="1631a-p105">在**设置，将应用于除电子邮件的内容**部分中，选中 （或清除） 您想要使用的选项。（我们建议您选择的所有选项。）</span><span class="sxs-lookup"><span data-stu-id="1631a-p105">In the **Settings that apply to content except email** section, select (or clear) the options you want to use. (We recommend that you select all the options.)</span></span> 
    
6. <span data-ttu-id="1631a-136">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="1631a-136">Choose **Save**.</span></span>
    
## <a name="add-a-policy-for-specific-email-recipients"></a><span data-ttu-id="1631a-137">为特定的电子邮件收件人添加策略</span><span class="sxs-lookup"><span data-stu-id="1631a-137">Add a policy for specific email recipients</span></span>

<span data-ttu-id="1631a-p106">检查所有用户的策略后，请考虑为电子邮件收件人的特定组定义其他策略。这样，您可以指定为默认策略例外。您可以添加策略使用任一安全&amp;合规性中心 （推荐） 或 Exchange 管理员中心。**我们建议使用安全&amp;合规性中心以查看或编辑任何 ATP 策略**。</span><span class="sxs-lookup"><span data-stu-id="1631a-p106">After you have reviewed the policy for all users, consider defining additional policies for specific groups of email recipients. This enables you to specify exceptions to your default policy. You can add policies using either the Security &amp; Compliance Center (recommended) or the Exchange admin center. **We recommend using the Security &amp; Compliance Center to review or edit any of your ATP policies**.</span></span>
  
1. <span data-ttu-id="1631a-142">转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="1631a-142">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="1631a-143">在左侧导航窗格中，**威胁管理**下面，选择**策略**。</span><span class="sxs-lookup"><span data-stu-id="1631a-143">In the left navigation, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="1631a-144">选择**安全的链接**。</span><span class="sxs-lookup"><span data-stu-id="1631a-144">Choose **Safe Links**.</span></span>
    
4. <span data-ttu-id="1631a-145">在**的可以应用到特定收件人的策略**部分中，选择**新建**(新建按钮图像类似一个加号 ( **+**))。</span><span class="sxs-lookup"><span data-stu-id="1631a-145">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)).</span></span>
    
    ![选择新建以添加特定的电子邮件收件人的安全链接策略](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. <span data-ttu-id="1631a-147">指定策略的名称、说明和设置。</span><span class="sxs-lookup"><span data-stu-id="1631a-147">Specify the name, description, and settings for your policy.</span></span>
    
    <span data-ttu-id="1631a-148">**示例：** 若要设置名为"通过没有直接单击"不允许人员没有 ATP 安全链接保护的特定网站点阅贵组织中的特定组中的策略，您可以指定以下建议的设置：</span><span class="sxs-lookup"><span data-stu-id="1631a-148">**Example:** To set up a policy called "no direct click through" that does not allow people in a certain group in your organization to click through to a specific website without ATP Safe Links protection, you might specify the following recommended settings:</span></span> 
    
  - <span data-ttu-id="1631a-149">在**名称**框中，键入没有直接点击率。</span><span class="sxs-lookup"><span data-stu-id="1631a-149">In the **Name** box, type no direct click through.</span></span>
    
  - <span data-ttu-id="1631a-150">在**说明**框中，键入类似，防止通过单击而无需 ATP 安全链接验证的网站中的特定组中的人员的说明。</span><span class="sxs-lookup"><span data-stu-id="1631a-150">In the **Description** box, type a description like, Prevents people in certain groups from clicking through to a website without ATP Safe Links verification.</span></span>
    
  - <span data-ttu-id="1631a-151">在**选择操作**部分中，选择**上**。</span><span class="sxs-lookup"><span data-stu-id="1631a-151">In the **Select the action** section, choose **On**.</span></span>
    
  - <span data-ttu-id="1631a-152">选择**使用安全附件扫描可下载的内容**。</span><span class="sxs-lookup"><span data-stu-id="1631a-152">Select **Use Safe Attachments to scan downloadable content**.</span></span>
    
  - <span data-ttu-id="1631a-153">如果此选项才可用，选择**应用发送组织内的邮件的安全链接**。</span><span class="sxs-lookup"><span data-stu-id="1631a-153">If this option is available, select **Apply Safe Links to messages sent within the organization**.</span></span>
    
  - <span data-ttu-id="1631a-154">选择**不允许用户通过单击到原始 URL**。</span><span class="sxs-lookup"><span data-stu-id="1631a-154">Select **Do not allow user to click through to original URL**.</span></span>
    
  - <span data-ttu-id="1631a-p107">（这是可选的）在**不重写以下 Url**部分中，指定一个或多个被视为安全的组织的 Url。（请参阅[设置自定义"执行不重写"Url 列表使用 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)）</span><span class="sxs-lookup"><span data-stu-id="1631a-p107">(This is optional) In the **Do not rewrite the following URLs** section, specify one or more URLs that are considered to be safe for your organization. (See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))</span></span>
    
  - <span data-ttu-id="1631a-p108">在**应用于**部分中，选择**收件人是的成员**，，然后选择您想要包括在您的策略的组。选择**添加**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="1631a-p108">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
6. <span data-ttu-id="1631a-159">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="1631a-159">Choose **Save**.</span></span>
    
## <a name="learn-about-atp-safe-links-policy-options"></a><span data-ttu-id="1631a-160">了解 ATP 安全链接策略选项</span><span class="sxs-lookup"><span data-stu-id="1631a-160">Learn about ATP Safe Links policy options</span></span>

<span data-ttu-id="1631a-p109">设置或编辑 ATP 安全链接策略时，将看到可用的几个选项。如果您想知道这些选项什么下, 表介绍每个和受到影响。请注意，有两种主要的策略定义或编辑： 适用于每个人的默认策略和其他策略定义的特定收件人。</span><span class="sxs-lookup"><span data-stu-id="1631a-p109">As you set up or edit an ATP Safe Links policy, will see several options available. In case you are wondering what these options are, the following table describes each one and its effect. Note that there are two main kinds of policies to define or edit: a default policy that applies to everyone, and additional policies that are defined for specific recipients.</span></span>
  
|<span data-ttu-id="1631a-164">**此策略**</span><span class="sxs-lookup"><span data-stu-id="1631a-164">**For this policy**</span></span>|<span data-ttu-id="1631a-165">**此选项**</span><span class="sxs-lookup"><span data-stu-id="1631a-165">**This option**</span></span>|<span data-ttu-id="1631a-166">**执行的操作**</span><span class="sxs-lookup"><span data-stu-id="1631a-166">**Does this**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1631a-167">默认 （定义后，默认策略适用于组织中的每个人）</span><span class="sxs-lookup"><span data-stu-id="1631a-167">Default (once defined, the default policy applies to everyone in the organization)</span></span>  <br/> |<span data-ttu-id="1631a-168">**阻止以下 Url**</span><span class="sxs-lookup"><span data-stu-id="1631a-168">**Block the following URLs**</span></span> <br/> |<span data-ttu-id="1631a-p110">允许贵组织拥有的自动阻止 Url 的自定义列表。当用户单击此列表中的 URL 时，它们将转到说明为什么阻止 URL[页警告](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="1631a-p110">Enables your organization to have a custom list of URLs that are automatically blocked. When users click a URL in this list, they'll be taken to a [warning page](atp-safe-links-warning-pages.md) that explains why the URL is blocked.  </span></span><br/> <span data-ttu-id="1631a-171">请参阅的详细信息，如新添加支持多达三个通配符星号的[设置使用 ATP 安全链接的自定义阻止 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)(\*)。</span><span class="sxs-lookup"><span data-stu-id="1631a-171">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md) for more details, such as newly added support for up to three wildcard asterisks (\*).</span></span>  <br/> |
|<span data-ttu-id="1631a-172">默认</span><span class="sxs-lookup"><span data-stu-id="1631a-172">Default</span></span>  <br/> |<span data-ttu-id="1631a-173">**Office 365 ProPlus，适用于 iOS 的 Office 和 Android**</span><span class="sxs-lookup"><span data-stu-id="1631a-173">**Office 365 ProPlus, Office for iOS and Android**</span></span> <br/> |<span data-ttu-id="1631a-174">选中此选项后，ATP 安全链接保护文档中的应用到 Url 中打开 Office 365 ProPlus （Word、 Excel 和 PowerPoint 在 Windows 或 Mac 操作系统上的） iOS 或 Android 设备，在 Windows 和 Office Online (Word Visio 2016 上的 Office 文档Online、 PowerPoint Online、 Excel Online 和 OneNote Online），提供用户已登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1631a-174">When this option is selected, ATP Safe Links protection is applied to URLs in documents that are open in Office 365 ProPlus (Word, Excel, and PowerPoint on Windows or Mac OS), Office documents on iOS, or Android devices, Visio 2016 on Windows, and Office Online (Word Online, PowerPoint Online, Excel Online, and OneNote Online), provided the user has signed into Office 365.</span></span> </br></br><span data-ttu-id="1631a-p111">如果您看到仅**在 Windows 上的 Office 2016**，然后功能更新尚未达到 Office 365 环境尚未 （和即将推出）。之前，ATP 安全链接保护适用于 Word 2016、 Excel 2016、 PowerPoint 2016 或 Visio 2016 Windows 上运行。</span><span class="sxs-lookup"><span data-stu-id="1631a-p111">If you see only **Office 2016 on Windows**, then the feature updates have not reached your Office 365 environment yet (and they are coming soon). Until then, ATP Safe Links protection applies to Word 2016, Excel 2016, PowerPoint 2016 or Visio 2016 running on Windows.</span></span>           |
|<span data-ttu-id="1631a-177">默认</span><span class="sxs-lookup"><span data-stu-id="1631a-177">Default</span></span>  <br/> |<span data-ttu-id="1631a-178">**当用户单击 ATP 安全链接不跟踪**</span><span class="sxs-lookup"><span data-stu-id="1631a-178">**Don't track when users click ATP Safe Links**</span></span> <br/> |<span data-ttu-id="1631a-179">选中此选项后，单击数据的 Word、 Excel、 PowerPoint 和 Visio 文档中的 Url，而未存储。</span><span class="sxs-lookup"><span data-stu-id="1631a-179">When this option is selected, click data for URLs in Word, Excel, PowerPoint, and Visio documents is not stored.</span></span>  <br/> |
|<span data-ttu-id="1631a-180">默认</span><span class="sxs-lookup"><span data-stu-id="1631a-180">Default</span></span>  <br/> |<span data-ttu-id="1631a-181">**不要让用户单击通过 ATP 原始 URL 的安全链接**</span><span class="sxs-lookup"><span data-stu-id="1631a-181">**Don't let users click through ATP Safe Links to original URL**</span></span> <br/> |<span data-ttu-id="1631a-182">选中此选项后，用户将无法继续过[警告页](atp-safe-links-warning-pages.md)被确定为恶意 url。</span><span class="sxs-lookup"><span data-stu-id="1631a-182">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |
|<span data-ttu-id="1631a-183">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="1631a-183">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="1631a-184">**关**</span><span class="sxs-lookup"><span data-stu-id="1631a-184">**Off**</span></span> <br/> |<span data-ttu-id="1631a-185">不扫描电子邮件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="1631a-185">Does not scan URLs in email messages.</span></span>  <br/> <span data-ttu-id="1631a-186">可以定义例外规则，例如不扫描 Url 电子邮件中一组特定的收件人的规则。</span><span class="sxs-lookup"><span data-stu-id="1631a-186">Enables you to define an exception rule, such as a rule that does not scan URLs in email messages for a specific group of recipients.</span></span>  <br/> |
|<span data-ttu-id="1631a-187">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="1631a-187">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="1631a-188">**在**</span><span class="sxs-lookup"><span data-stu-id="1631a-188">**On**</span></span> <br/> |<span data-ttu-id="1631a-189">当用户单击 Url 电子邮件中，可向路由用户通过 ATP 安全链接保护 Url。</span><span class="sxs-lookup"><span data-stu-id="1631a-189">Rewrites URLs to route users through ATP Safe Links protection when the users click URLs in email messages.</span></span>  <br/> <span data-ttu-id="1631a-190">检查时针对阻止列表或恶意 Url 的列表的 URL。</span><span class="sxs-lookup"><span data-stu-id="1631a-190">Checks a URL when clicked against a list of blocked or malicious URLs.</span></span>  <br/> |
|<span data-ttu-id="1631a-191">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="1631a-191">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="1631a-192">**使用安全附件扫描可下载内容**</span><span class="sxs-lookup"><span data-stu-id="1631a-192">**Use Safe Attachments to scan downloadable content**</span></span> <br/> |<span data-ttu-id="1631a-193">选中此选项后，会扫描指向可下载内容的 Url。</span><span class="sxs-lookup"><span data-stu-id="1631a-193">When this option is selected, URLs that point to downloadable content are scanned.</span></span>  <br/> |
|<span data-ttu-id="1631a-194">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="1631a-194">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="1631a-195">**适用于组织中发送的邮件的安全链接**</span><span class="sxs-lookup"><span data-stu-id="1631a-195">**Apply Safe Links to messages sent within the organization**</span></span> <br/> | <span data-ttu-id="1631a-196">可用并选中此选项时，为您提供的电子邮件帐户的组织中的人员之间发送的邮件位于 Office 365 中的电子邮件应用 ATP 安全链接保护。</span><span class="sxs-lookup"><span data-stu-id="1631a-196">When this option is available and selected, ATP Safe Links protection is applied to email messages sent between people in your organization, provided the email accounts are hosted in Office 365.</span></span>  <br/> |
|<span data-ttu-id="1631a-197">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="1631a-197">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="1631a-198">**不跟踪用户单击**</span><span class="sxs-lookup"><span data-stu-id="1631a-198">**Do not track user clicks**</span></span> <br/> |<span data-ttu-id="1631a-p112">选中此选项后，单击数据为来自外部发件人的电子邮件中的 Url，而未存储。当前不支持 URL 单击跟踪的组织中发送的电子邮件中的链接。</span><span class="sxs-lookup"><span data-stu-id="1631a-p112">When this option is selected, click data for URLs in email from external senders is not stored. URL click tracking for links within email messages sent within the organization is currently not supported.</span></span>  <br/> |
|<span data-ttu-id="1631a-201">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="1631a-201">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="1631a-202">**不允许用户通过单击到原始 URL**</span><span class="sxs-lookup"><span data-stu-id="1631a-202">**Do not allow users to click through to original URL**</span></span> <br/> |<span data-ttu-id="1631a-203">选中此选项后，用户将无法继续过[警告页](atp-safe-links-warning-pages.md)被确定为恶意 url。</span><span class="sxs-lookup"><span data-stu-id="1631a-203">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |
|<span data-ttu-id="1631a-204">创建特定的电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="1631a-204">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="1631a-205">**不重写以下 Url**</span><span class="sxs-lookup"><span data-stu-id="1631a-205">**Do not rewrite the following URLs**</span></span> <br/> |<span data-ttu-id="1631a-p113">与离开 Url。保留自定义列表的安全无需扫描一组特定的电子邮件收件人在组织中的 Url。 请参阅的详细信息，包括支持的通配符星号的最新更改的[设置自定义"执行不重写"Url 列表使用 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)(\*)。</span><span class="sxs-lookup"><span data-stu-id="1631a-p113">Leaves URLs as they are. Keeps a custom list of safe URLs that don't need scanning for a specific group of email recipients in your organization.  See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for more details, including recent changes to support for wildcard asterisks (\*).  </span></span><br/> |
   
## <a name="related-topics"></a><span data-ttu-id="1631a-209">相关主题</span><span class="sxs-lookup"><span data-stu-id="1631a-209">Related topics</span></span>

[<span data-ttu-id="1631a-210">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="1631a-210">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="1631a-211">Office 365 中的 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="1631a-211">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="1631a-212">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="1631a-212">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="1631a-213">设置自定义阻止 Url 列表使用 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="1631a-213">Set up a custom blocked URLs list using ATP Safe Links</span></span>](set-up-a-custom-blocked-urls-list-wtih-atp.md)
  
[<span data-ttu-id="1631a-214">设置自定义"执行不重写"Url 列表使用 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="1631a-214">Set up a custom "Do not rewrite" URLs list using ATP Safe Links</span></span>](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
  
[<span data-ttu-id="1631a-215">查看高级威胁保护报告</span><span class="sxs-lookup"><span data-stu-id="1631a-215">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="1631a-216">Office 365 安全性权限&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="1631a-216">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  


---
title: 设置 Office 365 ATP 安全附件策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/8/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
description: 定义附件安全策略，以从电子邮件中的恶意文件保护您的组织。
ms.openlocfilehash: 03fb0b62d37dc628241a1108b4b256290c23509b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525312"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a><span data-ttu-id="592cd-103">设置 Office 365 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="592cd-103">Set up Office 365 ATP Safe Attachments policies</span></span>

<span data-ttu-id="592cd-p101">人员定期发送，接收和共享附件，如文档、 演示文稿、 电子表格和详细信息。它并不总是易于判断附件是安全或恶意只通过查看电子邮件。和所需的最后一项是通过，获取恶意附件现在为您的组织破坏。幸运的是，可以帮助[Office 365 高级威胁保护](office-365-atp.md)(ATP)。您可以设置[ATP 安全附件](atp-safe-attachments.md)策略，以帮助确保您的组织受不安全的电子邮件附件攻击。</span><span class="sxs-lookup"><span data-stu-id="592cd-p101">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more. It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message. And the last thing you want is a malicious attachment to get through, wreaking havoc for your organization. Fortunately, [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) can help. You can set up [ATP Safe Attachments](atp-safe-attachments.md) policies to help ensure that your organization is protected against attacks by unsafe email attachments.</span></span> 
  
## <a name="what-to-do"></a><span data-ttu-id="592cd-109">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="592cd-109">What to do</span></span> 
  
1. [<span data-ttu-id="592cd-110">查看先决条件</span><span class="sxs-lookup"><span data-stu-id="592cd-110">Review the prerequisites</span></span>](#review-the-prerequisites)
    
2. [<span data-ttu-id="592cd-111">设置 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="592cd-111">Set up an ATP Safe Attachments policy</span></span>](#set-up-an-atp-safe-attachments-policy)
    
3. [<span data-ttu-id="592cd-112">了解 ATP 安全附件策略选项</span><span class="sxs-lookup"><span data-stu-id="592cd-112">Learn about ATP Safe Attachments policy options</span></span>](#learn-about-atp-safe-attachments-policy-options)
    
## <a name="review-the-prerequisites"></a><span data-ttu-id="592cd-113">查看先决条件</span><span class="sxs-lookup"><span data-stu-id="592cd-113">Review the prerequisites</span></span>

- <span data-ttu-id="592cd-114">请确保您的组织具有[Office 365 高级威胁保护](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="592cd-114">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>
    
- <span data-ttu-id="592cd-115">请确保您具有必要[Office 365 安全性分配权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="592cd-115">Make sure that you have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="592cd-p102">[了解 ATP 安全附件策略选项](#learn-about-atp-safe-attachments-policy-options)（本文中）。扫描的附件时，一些选项，如监视或替换选项中，会导致次要电子邮件的延迟。若要避免出现邮件延迟，请考虑使用[动态交付和预览](dynamic-delivery-and-previewing.md)。</span><span class="sxs-lookup"><span data-stu-id="592cd-p102">[Learn about ATP Safe Attachments policy options](#learn-about-atp-safe-attachments-policy-options) (in this article). Some options, such as the Monitor or Replace options, can result in a minor delay of email while attachments are scanned. To avoid message delays, consider using [dynamic delivery and previewing](dynamic-delivery-and-previewing.md).</span></span>
    
- <span data-ttu-id="592cd-119">允许最多 30 分钟的新的或更新策略传播到所有 Office 365 数据中心。</span><span class="sxs-lookup"><span data-stu-id="592cd-119">Allow up to 30 minutes for your new or updated policy to spread to all Office 365 datacenters.</span></span>
    
## <a name="set-up-an-atp-safe-attachments-policy"></a><span data-ttu-id="592cd-120">设置 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="592cd-120">Set up an ATP Safe Attachments policy</span></span>

<span data-ttu-id="592cd-p103">您可以设置 ATP 安全附件策略使用 Office 365 安全性&amp;合规性中心或 Exchange 管理员中心 (EAC)。**我们建议使用 Office 365 安全性&amp;合规性中心**。</span><span class="sxs-lookup"><span data-stu-id="592cd-p103">You can set up an ATP Safe Attachments policy using either the Office 365 Security &amp; Compliance Center or the Exchange admin center (EAC). **We recommend using the Office 365 Security &amp; Compliance Center**.</span></span> 
  
1. <span data-ttu-id="592cd-123">以全局管理员或 security 管理员程序中，转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="592cd-123">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="592cd-124">Office 365 安全性&amp;合规性中心在左侧的导航窗格中，**威胁管理**下面，选择**策略** \> **安全的附件**。</span><span class="sxs-lookup"><span data-stu-id="592cd-124">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>
    
3. <span data-ttu-id="592cd-p104">如果您看到**打开 SharePoint、 OneDrive 和 Microsoft 团队 ATP**，我们建议您选择此选项。Office 365 环境，这将使[Office 365 高级威胁 Protection for SharePoint、 OneDrive 和 Microsoft 团队](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="592cd-p104">If you see **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**, we recommend that you select this option. This will enable [Office 365 Advanced Threat Protection for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) for your Office 365 environment.</span></span> 
    
4. <span data-ttu-id="592cd-127">选择**新建**(新建按钮图像类似一个加号 ( **+**)) 开始创建您的策略。</span><span class="sxs-lookup"><span data-stu-id="592cd-127">Choose **New** (the New button resembles a plus sign ( **+**)) to start creating your policy.</span></span>
    
5. <span data-ttu-id="592cd-128">指定名称、 说明和策略设置。</span><span class="sxs-lookup"><span data-stu-id="592cd-128">Specify the name, description, and settings for the policy.</span></span>
    
    <span data-ttu-id="592cd-129">**示例：** 若要设置的策略名为"无延迟"立即传递每个人的邮件，然后重新附加附件，他们正在扫描后，您可能会指定以下设置：</span><span class="sxs-lookup"><span data-stu-id="592cd-129">**Example:** To set up a policy called "no delays" that delivers everyone's messages immediately and then reattaches attachments after they're scanned, you might specify the following settings:</span></span> 
    
  - <span data-ttu-id="592cd-130">在**名称**框中，键入任何延迟。</span><span class="sxs-lookup"><span data-stu-id="592cd-130">In the **Name** box, type no delays.</span></span>
    
  - <span data-ttu-id="592cd-131">在**说明**框中，键入类似，立即提供了邮件和重新附加附件扫描后的说明。</span><span class="sxs-lookup"><span data-stu-id="592cd-131">In the **Description** box, type a description like, Delivers messages immediately and reattaches attachments after scanning.</span></span>
    
  - <span data-ttu-id="592cd-p105">在响应部分中，选择**动态传递**选项。（[了解更多有关动态交付和 ATP 安全附件预览](dynamic-delivery-and-previewing.md)。）</span><span class="sxs-lookup"><span data-stu-id="592cd-p105">In the response section, choose the **Dynamic Delivery** option. ([Learn more about dynamic delivery and previewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).)</span></span>
    
  - <span data-ttu-id="592cd-134">在**重定向附件**部分中，选择启用重定向并键入您的 Office 365 全局管理员、 安全管理员或安全分析师，负责调查恶意附件的电子邮件地址的选项。</span><span class="sxs-lookup"><span data-stu-id="592cd-134">In the **Redirect attachment** section, select the option to enable redirect and type the email address of your Office 365 global administrator, security administrator, or security analyst who will investigate malicious attachments.</span></span> 
    
  - <span data-ttu-id="592cd-p106">在**应用于**部分中，选择**收件人的域是**，，然后选择您的域。选择**添加**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="592cd-p106">In the **Applied To** section, choose **The recipient domain is**, and then select your domain. Choose **Add**, and then choose **OK**.</span></span>
    
6. <span data-ttu-id="592cd-137">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="592cd-137">Choose **Save**.</span></span>
    
<span data-ttu-id="592cd-p107">请考虑您的组织的多个 ATP 安全附件策略设置。将它们在**ATP 安全附件**上列出的顺序应用这些策略。已定义或编辑策略后，允许至少 30 分钟的策略生效整个 Microsoft 数据中心。</span><span class="sxs-lookup"><span data-stu-id="592cd-p107">Consider setting up multiple ATP Safe Attachments policies for your organization. These policies will be applied in the order they're listed on the **ATP Safe Attachments** page. After a policy has been defined or edited, allow at least 30 minutes for the polices to take effect throughout Microsoft datacenters.</span></span> 
  
## <a name="learn-about-atp-safe-attachments-policy-options"></a><span data-ttu-id="592cd-141">了解 ATP 安全附件策略选项</span><span class="sxs-lookup"><span data-stu-id="592cd-141">Learn about ATP Safe Attachments policy options</span></span>

<span data-ttu-id="592cd-p108">设置 ATP 安全附件策略时，将从多个选项，包括监视、 阻止、 Replace、 动态传递等选择。如果您想知道有关这些选项所执行的操作下, 表总结了每个和受到影响。</span><span class="sxs-lookup"><span data-stu-id="592cd-p108">As you set up your ATP Safe Attachments policies, you choose from among many options, including Monitor, Block, Replace, Dynamic Delivery, and so on. In case you're wondering about what these options do, the following table summarizes each and its effect.</span></span>
  
|<span data-ttu-id="592cd-144">**选项**</span><span class="sxs-lookup"><span data-stu-id="592cd-144">**Option**</span></span>|<span data-ttu-id="592cd-145">**效果**</span><span class="sxs-lookup"><span data-stu-id="592cd-145">**Effect**</span></span>|<span data-ttu-id="592cd-146">**时要使用：**</span><span class="sxs-lookup"><span data-stu-id="592cd-146">**Use when you want to:**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="592cd-147">**关**</span><span class="sxs-lookup"><span data-stu-id="592cd-147">**Off**</span></span> <br/> |<span data-ttu-id="592cd-148">不扫描附件的恶意软件</span><span class="sxs-lookup"><span data-stu-id="592cd-148">Does not scan attachments for malware</span></span>  <br/> <span data-ttu-id="592cd-149">不延迟邮件传递</span><span class="sxs-lookup"><span data-stu-id="592cd-149">Does not delay message delivery</span></span>  <br/> |<span data-ttu-id="592cd-150">关闭扫描的内部发件人、 扫描程序、 传真或才会发送已知的良好的附件的智能主机</span><span class="sxs-lookup"><span data-stu-id="592cd-150">Turn scanning off for internal senders, scanners, faxes, or smart hosts that will only send known, good attachments</span></span>  <br/> <span data-ttu-id="592cd-151">阻止路由内部邮件中不必要的延迟</span><span class="sxs-lookup"><span data-stu-id="592cd-151">Prevent unnecessary delays in routing internal mail</span></span>  <br/> <span data-ttu-id="592cd-p109">> [!IMPORTANT]> 不建议大多数用户使用此选项。使您可以关闭 ATP 安全附件扫描内部发件人一小组。</span><span class="sxs-lookup"><span data-stu-id="592cd-p109">> [!IMPORTANT]> This option is not recommended for most users. It enables you to turn ATP Safe Attachments scanning off for a small group of internal senders.</span></span>           |
|<span data-ttu-id="592cd-154">**监视器**</span><span class="sxs-lookup"><span data-stu-id="592cd-154">**Monitor**</span></span> <br/> |<span data-ttu-id="592cd-155">提供了带附件的邮件，然后跟踪与检测到恶意软件会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="592cd-155">Delivers messages with attachments and then tracks what happens with detected malware</span></span>  <br/> |<span data-ttu-id="592cd-156">请参阅您的组织中检测到恶意软件的位置</span><span class="sxs-lookup"><span data-stu-id="592cd-156">See where detected malware goes in your organization</span></span>  <br/> |
|<span data-ttu-id="592cd-157">**阻止**</span><span class="sxs-lookup"><span data-stu-id="592cd-157">**Block**</span></span> <br/> |<span data-ttu-id="592cd-158">阻止从继续检测到恶意软件附件的邮件</span><span class="sxs-lookup"><span data-stu-id="592cd-158">Prevents messages with detected malware attachments from proceeding</span></span>  <br/> <span data-ttu-id="592cd-159">将检测到恶意软件的邮件发送到[Office 365 中的隔离](manage-quarantined-messages-and-files.md)其中安全管理员或分析师可以查看和版本 （或删除） 这些消息</span><span class="sxs-lookup"><span data-stu-id="592cd-159">Sends messages with detected malware to [quarantine in Office 365](manage-quarantined-messages-and-files.md) where a security administrator or analyst can review and release (or delete) those messages</span></span>  <br/> <span data-ttu-id="592cd-160">自动阻止将来的邮件和附件</span><span class="sxs-lookup"><span data-stu-id="592cd-160">Blocks future messages and attachments automatically</span></span>  <br/> |<span data-ttu-id="592cd-161">保护您的组织中使用相同的恶意软件附件的重复攻击</span><span class="sxs-lookup"><span data-stu-id="592cd-161">Safeguard your organization from repeated attacks using the same malware attachments</span></span>  <br/> |
|<span data-ttu-id="592cd-162">**替换**</span><span class="sxs-lookup"><span data-stu-id="592cd-162">**Replace**</span></span> <br/> |<span data-ttu-id="592cd-163">删除检测到恶意软件的附件</span><span class="sxs-lookup"><span data-stu-id="592cd-163">Removes detected malware attachments</span></span>  <br/> <span data-ttu-id="592cd-164">通知收件人的已删除附件</span><span class="sxs-lookup"><span data-stu-id="592cd-164">Notifies recipients that attachments have been removed</span></span>  <br/> <span data-ttu-id="592cd-165">将检测到恶意软件的邮件发送到[Office 365 中的隔离](manage-quarantined-messages-and-files.md)其中安全管理员或分析师可以查看和版本 （或删除） 这些消息</span><span class="sxs-lookup"><span data-stu-id="592cd-165">Sends messages with detected malware to [quarantine in Office 365](manage-quarantined-messages-and-files.md) where a security administrator or analyst can review and release (or delete) those messages</span></span>  <br/> |<span data-ttu-id="592cd-166">提升到收件人的已删除由于检测到恶意软件的附件的可见性</span><span class="sxs-lookup"><span data-stu-id="592cd-166">Raise visibility to recipients that attachments were removed because of detected malware</span></span>  <br/> |
|<span data-ttu-id="592cd-167">**动态传递**</span><span class="sxs-lookup"><span data-stu-id="592cd-167">**Dynamic Delivery**</span></span> <br/> |<span data-ttu-id="592cd-168">立即发送的邮件</span><span class="sxs-lookup"><span data-stu-id="592cd-168">Delivers messages immediately</span></span>  <br/> <span data-ttu-id="592cd-169">替换附件是占位符文件之前扫描已完成，并且如果检测到没有恶意软件，然后重新附加附件</span><span class="sxs-lookup"><span data-stu-id="592cd-169">Replaces attachments with a placeholder file until scanning is complete, and then reattaches the attachments if no malware is detected</span></span>  <br/> <span data-ttu-id="592cd-170">包含附件预览功能对于大多数 Pdf 和 Office 在扫描过程中的文件</span><span class="sxs-lookup"><span data-stu-id="592cd-170">Includes attachment previewing capabilities for most PDFs and Office files during scanning</span></span>  <br/> <span data-ttu-id="592cd-171">将与检测到恶意软件的邮件发送到其中的安全管理员或分析师可以查看和版本 （或删除） 这些邮件隔离邮箱</span><span class="sxs-lookup"><span data-stu-id="592cd-171">Sends messages with detected malware to Quarantine where a security administrator or analyst can review and release (or delete) those messages</span></span>  <br/> [<span data-ttu-id="592cd-172">了解动态交付和 ATP 安全附件预览</span><span class="sxs-lookup"><span data-stu-id="592cd-172">Learn about dynamic delivery and previewing with ATP Safe Attachments</span></span>](dynamic-delivery-and-previewing.md) <br/> |<span data-ttu-id="592cd-173">避免同时从恶意文件保护收件人的邮件延迟</span><span class="sxs-lookup"><span data-stu-id="592cd-173">Avoid message delays while protecting recipients from malicious files</span></span>  <br/> <span data-ttu-id="592cd-174">启用收件人时扫描正在进行预览在安全模式下的附件</span><span class="sxs-lookup"><span data-stu-id="592cd-174">Enable recipients to preview attachments in safe mode while scanning is taking place</span></span>  <br/> |
|<span data-ttu-id="592cd-175">**启用重定向**</span><span class="sxs-lookup"><span data-stu-id="592cd-175">**Enable redirect**</span></span> <br/> |<span data-ttu-id="592cd-176">适用时选择了监视、 阻止或替换选项</span><span class="sxs-lookup"><span data-stu-id="592cd-176">Applies when the Monitor, Block, or Replace option is chosen</span></span>  <br/> <span data-ttu-id="592cd-177">发送到指定的电子邮件地址的附件安全管理员或分析师可以调查</span><span class="sxs-lookup"><span data-stu-id="592cd-177">Sends attachments to a specified email address where security administrators or analysts can investigate</span></span>  <br/> |<span data-ttu-id="592cd-178">启用安全管理员和分析师研究可疑附件</span><span class="sxs-lookup"><span data-stu-id="592cd-178">Enable security administrators and analysts to research suspicious attachments</span></span>  <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="592cd-179">相关主题</span><span class="sxs-lookup"><span data-stu-id="592cd-179">Related topics</span></span>

[<span data-ttu-id="592cd-180">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="592cd-180">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="592cd-181">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="592cd-181">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="592cd-182">Office 365 中的 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="592cd-182">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="592cd-183">设置 Office 365 中的安全链接 ATP 策略</span><span class="sxs-lookup"><span data-stu-id="592cd-183">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="592cd-184">查看高级威胁保护报告</span><span class="sxs-lookup"><span data-stu-id="592cd-184">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="592cd-185">Office 365 安全性权限&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="592cd-185">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  


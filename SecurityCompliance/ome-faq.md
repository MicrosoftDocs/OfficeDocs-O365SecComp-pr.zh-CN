---
title: Office 365 邮件加密 FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/11/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: 有关于 Office 365 中的新邮件保护功能的工作方式的问题？检查此处答案。
ms.openlocfilehash: 8774d5e11bbd5b240cb1984e6d8b67b98bfa856e
ms.sourcegitcommit: d6b1632a44e40522a4a16e7cb05ba5189214baeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29890033"
---
# <a name="office-365-message-encryption-faq"></a><span data-ttu-id="71a69-104">Office 365 邮件加密 FAQ</span><span class="sxs-lookup"><span data-stu-id="71a69-104">Office 365 Message Encryption FAQ</span></span>

<span data-ttu-id="71a69-p102">有关于 Office 365 中的新邮件保护功能的工作方式的问题？检查此处答案。此外，看看[有关在 Azure 信息保护的数据保护的常见问题](https://docs.microsoft.com/information-protection/get-started/faqs-rms)的 Azure 权限管理的数据保护服务有关的问题的解答在 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="71a69-p102">Have a question about how the new message protection capabilities in Office 365 work? Check for an answer here. Also, take a look at [Frequently asked questions about data protection in Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/faqs-rms) for answers to questions about the data protection service, Azure Rights Management, in Azure Information Protection.</span></span>

||
|:-----|
|<span data-ttu-id="71a69-p103">本文是系列的有关 Office 365 邮件加密的文章的较大一部分。本文旨在为管理员和 ITPros。如果您只查找有关的信息发送或接收加密的邮件， [Office 365 邮件加密 (OME)](ome.md)中的文章的列表，请参阅并找到最适合您的需求的文章。</span><span class="sxs-lookup"><span data-stu-id="71a69-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||
  
## <a name="what-is-office-365-message-encryption-ome"></a><span data-ttu-id="71a69-111">什么是 Office 365 邮件加密 (OME)？</span><span class="sxs-lookup"><span data-stu-id="71a69-111">What is Office 365 Message Encryption (OME)?</span></span>

<span data-ttu-id="71a69-p104">OME 结合了电子邮件加密和权限管理功能。Azure 信息保护由供电权限管理功能。</span><span class="sxs-lookup"><span data-stu-id="71a69-p104">OME combines email encryption and rights management capabilities. Rights management capabilities are powered by Azure Information Protection.</span></span>
  
## <a name="who-can-use-ome"></a><span data-ttu-id="71a69-114">谁可以使用 OME？</span><span class="sxs-lookup"><span data-stu-id="71a69-114">Who can use OME?</span></span>

<span data-ttu-id="71a69-115">在下列情况下，您可以使用的 OME 的新功能：</span><span class="sxs-lookup"><span data-stu-id="71a69-115">You can use the new capabilities for OME under the following conditions:</span></span>
  
- <span data-ttu-id="71a69-116">如果您从不为 Office 365 中 Exchange Online 设置 OME 或 IRM。</span><span class="sxs-lookup"><span data-stu-id="71a69-116">If you have never set up OME or IRM for Exchange Online in Office 365.</span></span>
    
- <span data-ttu-id="71a69-117">如果您已设置 OME 和 IRM，您可以使用这些步骤，如果您使用的从 Azure 信息保护 Azure 权限管理服务。</span><span class="sxs-lookup"><span data-stu-id="71a69-117">If you have set up OME and IRM, you can use these steps if you are using the Azure Rights Management service from Azure Information Protection.</span></span>
    
- <span data-ttu-id="71a69-p105">如果您使用 Exchange Online 与 Active Directory 权限管理服务 (AD RMS)，不能立即启用这些新功能。相反，您需要[迁移到 Azure 信息保护 AD RMS](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)首先。完成迁移后，您可以成功设置 OME。</span><span class="sxs-lookup"><span data-stu-id="71a69-p105">If you are using Exchange Online with Active Directory Rights Management service (AD RMS), you can't enable these new capabilities right away. Instead, you need to [migrate AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) first. When you've finished the migration, you can successfully set up OME.</span></span> 
    
    <span data-ttu-id="71a69-121">如果您选择要继续使用本地 AD RMS 与 Exchange Online 而不是迁移到 Azure 信息保护，您将无法使用这些新功能。</span><span class="sxs-lookup"><span data-stu-id="71a69-121">If you choose to continue to use on-premises AD RMS with Exchange Online instead of migrating to Azure Information Protection, you will not be able to use these new capabilities.</span></span>
    
## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a><span data-ttu-id="71a69-122">使用新的 OME 功能需要哪些订阅？</span><span class="sxs-lookup"><span data-stu-id="71a69-122">What subscriptions do I need to use the new OME capabilities?</span></span>

<span data-ttu-id="71a69-123">若要使用的新 OME 功能，您需要以下计划之一：</span><span class="sxs-lookup"><span data-stu-id="71a69-123">To use the new OME capabilities, you need one of the following plans:</span></span>
  
- <span data-ttu-id="71a69-p106">Office 365 邮件加密的 Office 365 企业版 E3 和 E5、 Microsoft 企业版 E3 和 E5、 Microsoft 365 企业版、 Office 365 A1，A3，和 A5 和 Office 365 政府版 G3 和 G5 一部分提供。客户不需要额外许可证接收由 Azure 信息保护的新保护功能。</span><span class="sxs-lookup"><span data-stu-id="71a69-p106">Office 365 Message Encryption is offered as part of Office 365 Enterprise E3 and E5, Microsoft Enterprise E3 and E5, Microsoft 365 Business, Office 365 A1, A3, and A5, and Office 365 Government G3 and G5. Customers do not need additional licenses to receive the new protection capabilities powered by Azure Information Protection.</span></span> 
    
- <span data-ttu-id="71a69-126">您还可以添加到以下 Azure 信息保护计划 1 计划收到新的 Office 365 邮件加密功能： Exchange Online 计划 1、 Exchange Online 计划 2、 Office 365 F1、 Office 365 业务 Essentials、 Office 365 企业高级版，或Office 365 企业版 E1。</span><span class="sxs-lookup"><span data-stu-id="71a69-126">You can also add Azure Information Protection Plan 1 to the following plans to receive the new Office 365 Message Encryption capabilities: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Office 365 Business Essentials, Office 365 Business Premium, or Office 365 Enterprise E1.</span></span>
    
- <span data-ttu-id="71a69-127">受益于 Office 365 邮件加密的每个用户需要被许可功能覆盖。</span><span class="sxs-lookup"><span data-stu-id="71a69-127">Each user benefiting from Office 365 Message Encryption needs to be licensed to be covered by the feature.</span></span>
    
- <span data-ttu-id="71a69-128">完整列表请参阅为 Office 365 邮件加密的[Exchange Online 服务说明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)。</span><span class="sxs-lookup"><span data-stu-id="71a69-128">For the full list see the [Exchange Online service descriptions](https://technet.microsoft.com/library/exchange-online-service-description.aspx) for Office 365 Message Encryption.</span></span> 
    
## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a><span data-ttu-id="71a69-129">可以使用 Exchange Online 使用将您自己的密钥 (BYOK) 放在 Azure 信息保护？</span><span class="sxs-lookup"><span data-stu-id="71a69-129">Can I use Exchange Online with bring your own key (BYOK) in Azure Information Protection?</span></span>

<span data-ttu-id="71a69-p107">是的！Microsoft 建议您完成设置 BYOK 设置 OME 之前的步骤。</span><span class="sxs-lookup"><span data-stu-id="71a69-p107">Yes! Microsoft recommends that you complete the steps to set up BYOK before you set up OME.</span></span>
  
<span data-ttu-id="71a69-132">有关 BYOK 的详细信息，请参阅[规划和实现您的 Azure 信息保护租户密钥](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="71a69-132">For more information about BYOK, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).</span></span>
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a><span data-ttu-id="71a69-133">OME 和 Azure 的信息保护 BYOK 更改 Microsoft 的方法为第三方数据请求，例如传讯？</span><span class="sxs-lookup"><span data-stu-id="71a69-133">Do OME and BYOK with Azure Information Protection change Microsoft's approach to third-party data requests such as subpoenas?</span></span>

<span data-ttu-id="71a69-p108">不。未设计 OME 和选项来提供自己的加密密钥，从 Azure 信息保护调用 BYOK，法律强制实施传讯响应。OME，与 Azure 信息保护 BYOK 设计的合规性中心客户。Microsoft 非常严重采用第三方客户数据请求。为云服务提供程序，我们始终提倡隐私的客户数据。在事件我们获得传唤，我们始终尝试将第三方重定向客户以获取信息。(请阅读 Brad Smith 的博客：[从政府窥探 Protecting 客户数据](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。我们将定期发布我们收到的请求的详细的信息。有关第三方数据请求的详细信息，，请参阅[响应政府和法律强制实施请求访问客户数据](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data)，Microsoft 信任中心上。另请参阅"泄露的客户数据"的[联机服务条款 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)文件中。</span><span class="sxs-lookup"><span data-stu-id="71a69-p108">No. OME and the option to provide and control your own encryption keys, called BYOK, from Azure Information Protection were not designed to respond to law enforcement subpoenas. OME, with BYOK for Azure Information Protection, was designed for compliance-focused customers. Microsoft takes third-party requests for customer data very seriously. As a cloud service provider, we always advocate for the privacy of customer data. In the event we get a subpoena, we always attempt to redirect the third party to the customer to obtain the information. (Please read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). We periodically publish detailed information of the request we receive. For more information regarding third-party data requests, see [Responding to government and law enforcement requests to access customer data](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data) on the Microsoft Trust Center. Also, see "Disclosure of Customer Data" in the [Online Services Terms (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx).</span></span>
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a><span data-ttu-id="71a69-144">此功能如何与旧的 Office 365 邮件加密 (OME) 和信息权限管理 (IRM) 功能？</span><span class="sxs-lookup"><span data-stu-id="71a69-144">How is this feature related to legacy Office 365 Message Encryption (OME) and Information Rights Management (IRM) features?</span></span>

<span data-ttu-id="71a69-p109">Office 365 邮件加密的新功能的现有 IRM 和旧式 OME 解决方案的发展。下表提供了更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="71a69-p109">The new capabilities for Office 365 Message Encryption are an evolution of the existing IRM and legacy OME solutions. The following table provides more details.</span></span>
  
<span data-ttu-id="71a69-147">**旧 OME、 IRM 和 OME 的新功能的比较**</span><span class="sxs-lookup"><span data-stu-id="71a69-147">**Comparison of legacy OME, IRM, and new OME capabilities**</span></span>

|<span data-ttu-id="71a69-148">**功能**</span><span class="sxs-lookup"><span data-stu-id="71a69-148">**Capability**</span></span>|<span data-ttu-id="71a69-149">**早期版本的 OME**</span><span class="sxs-lookup"><span data-stu-id="71a69-149">**Previous versions of OME**</span></span>|<span data-ttu-id="71a69-150">**IRM**</span><span class="sxs-lookup"><span data-stu-id="71a69-150">**IRM**</span></span>|<span data-ttu-id="71a69-151">**OME 的新功能**</span><span class="sxs-lookup"><span data-stu-id="71a69-151">**New OME capabilities**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="71a69-152">**发送加密电子邮件**</span><span class="sxs-lookup"><span data-stu-id="71a69-152">**Sending an encrypted email**</span></span>|<span data-ttu-id="71a69-153">只能通过 Exchange 邮件流规则</span><span class="sxs-lookup"><span data-stu-id="71a69-153">Only through Exchange mail flow rules</span></span>|<span data-ttu-id="71a69-154">最终用户从 Outlook 中的 PC、 for Mac、 Outlook 或 Outlook web; 上启动或通过 Exchange 邮件流规则</span><span class="sxs-lookup"><span data-stu-id="71a69-154">End-user initiated from Outlook for PC, Outlook for Mac, or Outlook on the web; or through Exchange mail flow rules</span></span>|<span data-ttu-id="71a69-155">最终用户从 Outlook 中的 PC、 for Mac、 Outlook 或 Outlook web; 上启动或通过邮件流规则</span><span class="sxs-lookup"><span data-stu-id="71a69-155">End-user initiated from Outlook for PC, Outlook for Mac, or Outlook on the web; or through mail flow rules</span></span>|
|<span data-ttu-id="71a69-156">**版权管理**</span><span class="sxs-lookup"><span data-stu-id="71a69-156">**Rights management**</span></span>|-|<span data-ttu-id="71a69-157">不转接选项和自定义模板</span><span class="sxs-lookup"><span data-stu-id="71a69-157">Do Not Forward option and custom templates</span></span>|<span data-ttu-id="71a69-158">执行不转接选项、 仅用于加密的选项、 默认和自定义模板</span><span class="sxs-lookup"><span data-stu-id="71a69-158">Do Not Forward option, encrypt-only option, default and custom templates</span></span>|
|<span data-ttu-id="71a69-159">**受支持的收件人类型**</span><span class="sxs-lookup"><span data-stu-id="71a69-159">**Supported recipient type**</span></span>|<span data-ttu-id="71a69-160">仅外部收件人</span><span class="sxs-lookup"><span data-stu-id="71a69-160">External recipients only</span></span>|<span data-ttu-id="71a69-161">仅内部收件人</span><span class="sxs-lookup"><span data-stu-id="71a69-161">Internal recipients only</span></span>|<span data-ttu-id="71a69-162">内部和外部收件人</span><span class="sxs-lookup"><span data-stu-id="71a69-162">Internal and external recipients</span></span>|
|<span data-ttu-id="71a69-163">**收件人的体验**</span><span class="sxs-lookup"><span data-stu-id="71a69-163">**Experience for recipient**</span></span>|<span data-ttu-id="71a69-164">外部收件人收到 HTML 邮件它们下载和浏览器中打开或下载移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="71a69-164">External recipients received an HTML message that they downloaded and opened in a browser or downloaded mobile app.</span></span>|<span data-ttu-id="71a69-165">内部收件人仅收到的 PC 的 Outlook、 Outlook for Mac 和在 web 上的 Outlook 中的加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="71a69-165">Internal recipients only received encrypted email in Outlook for PC, Outlook for Mac, and Outlook on the web.</span></span>|<span data-ttu-id="71a69-p110">内部和外部收件人的 PC 的 Outlook、 Outlook for Mac、 web 上的 Outlook、 for Android，Outlook 和 Outlook 中接收电子邮件，适用于 iOS，或通过 web 门户，无论他们是相同的 Office 365 组织中或任何 Office 365 中组织。OME 门户需要没有单独下载。</span><span class="sxs-lookup"><span data-stu-id="71a69-p110">Internal and external recipients receive email in Outlook for PC, Outlook for Mac, Outlook on the web, Outlook for Android, and Outlook for iOS, or through a web portal, regardless of whether or not they are in the same Office 365 organization or in any Office 365 organization. The OME portal requires no separate download.</span></span>|
|<span data-ttu-id="71a69-168">**使您自己的密钥支持**</span><span class="sxs-lookup"><span data-stu-id="71a69-168">**Bring Your Own Key support**</span></span>|<span data-ttu-id="71a69-169">不可用</span><span class="sxs-lookup"><span data-stu-id="71a69-169">Not available</span></span>|<span data-ttu-id="71a69-170">不可用</span><span class="sxs-lookup"><span data-stu-id="71a69-170">Not available</span></span>| <span data-ttu-id="71a69-171">BYOK 支持</span><span class="sxs-lookup"><span data-stu-id="71a69-171">BYOK supported</span></span>|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a><span data-ttu-id="71a69-172">如何为我的组织中启用新的 OME 功能？</span><span class="sxs-lookup"><span data-stu-id="71a69-172">How do I enable the new OME capabilities for my organization?</span></span>

<span data-ttu-id="71a69-173">请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="71a69-173">See [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a><span data-ttu-id="71a69-174">将被弃用 OME 的早期版本？</span><span class="sxs-lookup"><span data-stu-id="71a69-174">Will the previous version of OME be deprecated?</span></span>

<span data-ttu-id="71a69-p111">您仍可以使用以前版本的 OME，此时将不弃用。但是，我们强烈建议组织使用新的和改进 OME 解决方案。不已经部署了 OME 的客户不能设置 OME 的早期版本的新部署。</span><span class="sxs-lookup"><span data-stu-id="71a69-p111">You can still use the previous version of OME, it will not be deprecated at this time. However, we highly encourage organizations to use the new and improved OME solution. Customers that have not already deployed OME cannot set up a new deployment of the previous version of OME.</span></span>
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a><span data-ttu-id="71a69-178">我的组织使用 Active Directory 权限管理，可以使用此功能？</span><span class="sxs-lookup"><span data-stu-id="71a69-178">My organization uses Active Directory Rights Management, can I use this functionality?</span></span>

<span data-ttu-id="71a69-p112">不。如果您使用 Exchange Online 与 Active Directory 权限管理服务 (AD RMS)，不能立即启用这些新功能。相反，您需要[迁移到 Azure 信息保护 AD RMS](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)首先。</span><span class="sxs-lookup"><span data-stu-id="71a69-p112">No. If you are using Exchange Online with Active Directory Rights Management service (AD RMS), you can't enable these new capabilities right away. Instead, you need to [migrate AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) first.</span></span> 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a><span data-ttu-id="71a69-p113">我的组织具有的 Exchange 混合部署。可以使用此功能？</span><span class="sxs-lookup"><span data-stu-id="71a69-p113">My organization has an Exchange Hybrid deployment. Can I use this feature?</span></span>

<span data-ttu-id="71a69-p114">内部部署用户可以发送加密的邮件使用 Exchange Online 邮件流规则。若要执行此操作，您需要通过 Exchange Online 电子邮件路由。有关详细信息，请参阅[部分 2： 配置邮件流从电子邮件服务器到 Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="71a69-p114">On-premises users can send encrypted mail using Exchange Online mail flow rules. In order to do this, you need to route email through Exchange Online. For more information, see [Part 2: Configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).</span></span>
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a><span data-ttu-id="71a69-p115">需要哪些电子邮件客户端使用以创建 OME 加密的邮件？支持哪些应用程序发送受保护的邮件？</span><span class="sxs-lookup"><span data-stu-id="71a69-p115">What email client do I need to use in order to create an OME encrypted message? What applications are supported for sending protected messages?</span></span>

<span data-ttu-id="71a69-189">从 Outlook 2016 和 Outlook 2013 的 PC 和 Mac，以及 web 上的 Outlook，您可以创建受保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="71a69-189">You can create protected messages from Outlook 2016, and Outlook 2013 for PC and Mac, and from Outlook on the web.</span></span>
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a><span data-ttu-id="71a69-190">读取和受保护的电子邮件进行回复操作支持哪些电子邮件客户端？</span><span class="sxs-lookup"><span data-stu-id="71a69-190">What email clients are supported to read and reply to protected emails?</span></span>

<span data-ttu-id="71a69-p116">您可以阅读并响应从 Outlook PC 和 Mac （2013年和 2016年）、 在 web 上，Outlook 和 Outlook mobile （Android 和 iOS），如果您是 Office 365 用户。如果您的组织允许，您还可以使用 iOS 的本机邮件客户端。如果您是 Office 365 用户，您可以阅读并回复加密邮件 web 上通过 web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="71a69-p116">You can read and respond from Outlook for PC and Mac (2013 and 2016), Outlook on the web, and Outlook mobile (Android and iOS) if you are an Office 365 user. You can also use the iOS native mail client if your organization allows it. If you are a non-Office 365 user, you can read and reply to encrypted messages on the web through your web browser.</span></span>
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a><span data-ttu-id="71a69-p117">在受保护的电子邮件中的附件为支持哪些文件类型？附件将继承与受保护的电子邮件相关的保护策略？</span><span class="sxs-lookup"><span data-stu-id="71a69-p117">What file types are supported as attachments in protected emails? Do attachments inherit the protection policies associated with protected emails?</span></span>

<span data-ttu-id="71a69-196">可以附加到受保护的邮件，任何文件类型，但仅在文件格式提到[此处](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)应用保护策略。</span><span class="sxs-lookup"><span data-stu-id="71a69-196">You can attach any file type to a protected mail, however protection policies are applied only on the file formats mentioned [here](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types).</span></span> 
  
<span data-ttu-id="71a69-p118">如果受支持的文件格式，例如 Word、 Excel 或 PowerPoint 文件，该文件始终受保护，即使已收件人下载附件。例如，如果附件受不要转发，且原始收件人下载和转发给新收件人的附件，新收件人将无法打开受保护的文件。</span><span class="sxs-lookup"><span data-stu-id="71a69-p118">If a file format is supported, such as a Word, Excel, or PowerPoint file, the file is always protected, even after the attachment has been downloaded by the recipient. For example, if an attachment is protected by Do Not Forward, and the original recipient downloads and forwards the attachment to a new recipient, the new recipient will not be able to open the protected file.</span></span>
  
## <a name="are-pdf-file-attachments-supported"></a><span data-ttu-id="71a69-199">PDF 文件附件支持？</span><span class="sxs-lookup"><span data-stu-id="71a69-199">Are PDF file attachments supported?</span></span>

<span data-ttu-id="71a69-p119">如果将 PDF 文件附加到受保护的邮件，将受保护邮件本身，但没有其他保护将应用到 PDF 文件之后收件人已收到。这意味着，收件人可以另存为、 转接、 复制和打印为 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="71a69-p119">If you attach a PDF file to a protected message, the message itself will be protected, but no additional protection will be applied to the PDF file after the recipient has received it. This means that the recipient can Save As, Forward, Copy, and Print the PDF file.</span></span>
  
## <a name="are-onedrive-for-business-attachments-supported"></a><span data-ttu-id="71a69-202">支持的业务附件 OneDrive？</span><span class="sxs-lookup"><span data-stu-id="71a69-202">Are OneDrive for Business attachments supported?</span></span>

<span data-ttu-id="71a69-p120">还没有。不支持的 OneDrive for Business 附件和最终用户无法对包含云 OneDrive for Business 附件的邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="71a69-p120">Not yet. OneDrive for Business attachments are not supported and end-users can't encrypt a mail that contains a cloud OneDrive for Business attachment.</span></span>
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a><span data-ttu-id="71a69-205">可以自动加密邮件的设置策略？</span><span class="sxs-lookup"><span data-stu-id="71a69-205">Can I automatically encrypt messages by setting up policies?</span></span>

<span data-ttu-id="71a69-p121">是的。邮件流规则在 Exchange Online 使用自动加密根据某些条件一条消息。例如，您可以创建基于收件人的策略 ID，收件人的域，或在正文或邮件的主题中的内容。请参阅[定义邮件流规则来加密 Office 365 中的电子邮件。](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="71a69-p121">Yes. Use mail flow rules in Exchange Online to automatically encrypt a message based on certain conditions. For example, you can create policies that are based on recipient ID, recipient domain, or on the content in the body or subject of the message. See [Define mail flow rules to encrypt email messages in Office 365.](define-mail-flow-rules-to-encrypt-email.md)</span></span>
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a><span data-ttu-id="71a69-210">可以我自动加密邮件的设置策略中的数据丢失防护 (DLP) 通过安全&amp;合规性中心？</span><span class="sxs-lookup"><span data-stu-id="71a69-210">Can I automatically encrypt messages by setting up policies in Data Loss Prevention (DLP) through the Security &amp; Compliance Center?</span></span>

<span data-ttu-id="71a69-p122">是的！您可以设置邮件流规则在 Exchange Online 或中安全使用 DLP&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="71a69-p122">Yes! You can set up mail flow rules in Exchange Online or by using DLP in the Security &amp; Compliance Center.</span></span>
  
## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a><span data-ttu-id="71a69-213">可以打开加密的邮件发送到共享邮箱？</span><span class="sxs-lookup"><span data-stu-id="71a69-213">Can I open encrypted messages sent to a Shared Mailbox?</span></span>

<span data-ttu-id="71a69-214">共享邮箱不支持当前加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="71a69-214">Currently encrypted messages are not supported for a Shared Mailbox.</span></span>

## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a><span data-ttu-id="71a69-215">可以自加密的邮件定义与公司品牌</span><span class="sxs-lookup"><span data-stu-id="71a69-215">Can I customize encrypted messages with my company branding?</span></span>

<span data-ttu-id="71a69-p123">是的！自定义电子邮件和 OME 门户网站的信息，请参阅将您的组织品牌添加到加密邮件。请参阅[将您的组织品牌添加到加密邮件。](add-your-organization-brand-to-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="71a69-p123">Yes! For information on customizing email messages and the OME portal, see Add your organization's brand to your encrypted messages. See [Add your organization's brand to your encrypted messages.](add-your-organization-brand-to-encrypted-messages.md)</span></span>
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a><span data-ttu-id="71a69-219">是否有任何报告的功能或见解的加密电子邮件？</span><span class="sxs-lookup"><span data-stu-id="71a69-219">Are there any reporting capabilities or insights for encrypted emails?</span></span>

<span data-ttu-id="71a69-220">不能在此时间但即将提供。</span><span class="sxs-lookup"><span data-stu-id="71a69-220">Not at this time but coming soon.</span></span>
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a><span data-ttu-id="71a69-221">可以使用如电子数据展示的合规性功能使用邮件加密吗？</span><span class="sxs-lookup"><span data-stu-id="71a69-221">Can I use message encryption with compliance features such as eDiscovery?</span></span>

<span data-ttu-id="71a69-p124">是的。所有加密的电子邮件是通过 Office 365 合规性功能可供搜索。</span><span class="sxs-lookup"><span data-stu-id="71a69-p124">Yes. All encrypted email messages are discoverable by Office 365 compliance features.</span></span>
  


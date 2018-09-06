---
title: Office 365 邮件加密 FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: 有关于 Office 365 中的新邮件保护功能的工作方式的问题？检查此处答案。
ms.openlocfilehash: 8fc3fa2378dfc8dba6ed17c042269f726235bc58
ms.sourcegitcommit: a8884b9675559018e1fddec1c0cc2de0bc3bdde5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "23839952"
---
# <a name="office-365-message-encryption-faq"></a><span data-ttu-id="90439-104">Office 365 邮件加密 FAQ</span><span class="sxs-lookup"><span data-stu-id="90439-104">Office 365 Message Encryption FAQ</span></span>

<span data-ttu-id="90439-p102">有关于 Office 365 中的新邮件保护功能的工作方式的问题？检查此处答案。此外，看看[有关在 Azure 信息保护的数据保护的常见问题](https://docs.microsoft.com/information-protection/get-started/faqs-rms)的 Azure 权限管理的数据保护服务有关的问题的解答在 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="90439-p102">Have a question about how the new message protection capabilities in Office 365 work? Check for an answer here. Also, take a look at [Frequently asked questions about data protection in Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/faqs-rms) for answers to questions about the data protection service, Azure Rights Management, in Azure Information Protection.</span></span> 
  
## <a name="what-is-office-365-message-encryption-ome"></a><span data-ttu-id="90439-108">什么是 Office 365 邮件加密 (OME)？</span><span class="sxs-lookup"><span data-stu-id="90439-108">What is Office 365 Message Encryption (OME)?</span></span>

<span data-ttu-id="90439-p103">OME 结合了电子邮件加密和权限管理功能。Azure 信息保护由供电权限管理功能。</span><span class="sxs-lookup"><span data-stu-id="90439-p103">OME combines email encryption and rights management capabilities. Rights management capabilities are powered by Azure Information Protection.</span></span>
  
## <a name="who-can-use-ome"></a><span data-ttu-id="90439-111">谁可以使用 OME？</span><span class="sxs-lookup"><span data-stu-id="90439-111">Who can use OME?</span></span>

<span data-ttu-id="90439-112">在下列情况下，您可以使用的 OME 的新功能：</span><span class="sxs-lookup"><span data-stu-id="90439-112">You can use the new capabilities for OME under the following conditions:</span></span>
  
- <span data-ttu-id="90439-113">如果您从不为 Office 365 中 Exchange Online 设置 OME 或 IRM。</span><span class="sxs-lookup"><span data-stu-id="90439-113">If you have never set up OME or IRM for Exchange Online in Office 365.</span></span>
    
- <span data-ttu-id="90439-114">如果您已设置 OME 和 IRM，您可以使用这些步骤，如果您使用的从 Azure 信息保护 Azure 权限管理服务。</span><span class="sxs-lookup"><span data-stu-id="90439-114">If you have set up OME and IRM, you can use these steps if you are using the Azure Rights Management service from Azure Information Protection.</span></span>
    
- <span data-ttu-id="90439-p104">如果您使用 Exchange Online 与 Active Directory 权限管理服务 (AD RMS)，不能立即启用这些新功能。相反，您需要[迁移到 Azure 信息保护 AD RMS](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)首先。完成迁移后，您可以成功设置 OME。</span><span class="sxs-lookup"><span data-stu-id="90439-p104">If you are using Exchange Online with Active Directory Rights Management service (AD RMS), you can't enable these new capabilities right away. Instead, you need to [migrate AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) first. When you've finished the migration, you can successfully set up OME.</span></span> 
    
    <span data-ttu-id="90439-118">如果您选择要继续使用本地 AD RMS 与 Exchange Online 而不是迁移到 Azure 信息保护，您将无法使用这些新功能。</span><span class="sxs-lookup"><span data-stu-id="90439-118">If you choose to continue to use on-premises AD RMS with Exchange Online instead of migrating to Azure Information Protection, you will not be able to use these new capabilities.</span></span>
    
## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a><span data-ttu-id="90439-119">使用新的 OME 功能需要哪些订阅？</span><span class="sxs-lookup"><span data-stu-id="90439-119">What subscriptions do I need to use the new OME capabilities?</span></span>

<span data-ttu-id="90439-120">若要使用的新 OME 功能，您需要以下计划之一：</span><span class="sxs-lookup"><span data-stu-id="90439-120">To use the new OME capabilities, you need one of the following plans:</span></span>
  
- <span data-ttu-id="90439-p105">Office 365 邮件加密的 Office 365 E3 和 E5、 Microsoft E3 和 E5、 Office 365 A1，A3，和 A5 和 Office 365 G3 和 G5 一部分提供。客户不需要额外许可证接收由 Azure 信息保护的新保护功能。</span><span class="sxs-lookup"><span data-stu-id="90439-p105">Office 365 Message Encryption is offered as part of Office 365 E3 and E5, Microsoft E3 and E5, Office 365 A1, A3, and A5, and Office 365 G3 and G5. Customers do not need additional licenses to receive the new protection capabilities powered by Azure Information Protection.</span></span> 
    
- <span data-ttu-id="90439-123">您还可以添加到以下 Azure 信息保护计划 1 计划收到新的 Office 365 邮件加密功能： Exchange Online 计划 1、 Exchange Online 计划 2、 Office 365 F1、 Office 365 业务 Essentials、 Office 365 企业高级版，或Office 365 企业版 E1。</span><span class="sxs-lookup"><span data-stu-id="90439-123">You can also add Azure Information Protection Plan 1 to the following plans to receive the new Office 365 Message Encryption capabilities: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Office 365 Business Essentials, Office 365 Business Premium, or Office 365 Enterprise E1.</span></span>
    
- <span data-ttu-id="90439-124">受益于 Office 365 邮件加密的每个用户需要被许可功能覆盖。</span><span class="sxs-lookup"><span data-stu-id="90439-124">Each user benefiting from Office 365 Message Encryption needs to be licensed to be covered by the feature.</span></span>
    
- <span data-ttu-id="90439-125">完整列表请参阅为 Office 365 邮件加密的[Exchange Online 服务说明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)。</span><span class="sxs-lookup"><span data-stu-id="90439-125">For the full list see the [Exchange Online service descriptions](https://technet.microsoft.com/library/exchange-online-service-description.aspx) for Office 365 Message Encryption.</span></span> 
    
## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a><span data-ttu-id="90439-126">可以使用 Exchange Online 使用将您自己的密钥 (BYOK) 放在 Azure 信息保护？</span><span class="sxs-lookup"><span data-stu-id="90439-126">Can I use Exchange Online with bring your own key (BYOK) in Azure Information Protection?</span></span>

<span data-ttu-id="90439-p106">是的！Microsoft 建议您完成设置 BYOK 设置 OME 之前的步骤。</span><span class="sxs-lookup"><span data-stu-id="90439-p106">Yes! Microsoft recommends that you complete the steps to set up BYOK before you set up OME.</span></span>
  
<span data-ttu-id="90439-129">有关 BYOK 的详细信息，请参阅[规划和实现您的 Azure 信息保护租户密钥](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="90439-129">For more information about BYOK, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).</span></span>
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a><span data-ttu-id="90439-130">OME 和 Azure 的信息保护 BYOK 更改 Microsoft 的方法为第三方数据请求，例如传讯？</span><span class="sxs-lookup"><span data-stu-id="90439-130">Do OME and BYOK with Azure Information Protection change Microsoft's approach to third-party data requests such as subpoenas?</span></span>

<span data-ttu-id="90439-p107">不。未设计 OME 和选项来提供自己的加密密钥，从 Azure 信息保护调用 BYOK，法律强制实施传讯响应。OME，与 Azure 信息保护 BYOK 设计的合规性中心客户。Microsoft 非常严重采用第三方客户数据请求。为云服务提供程序，我们始终提倡隐私的客户数据。在事件我们获得传唤，我们始终尝试将第三方重定向客户以获取信息。(请阅读 Brad Smith 的博客：[从政府窥探 Protecting 客户数据](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。我们将定期发布我们收到的请求的详细的信息。有关第三方数据请求的详细信息，，请参阅[响应政府和法律强制实施请求访问客户数据](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data)，Microsoft 信任中心上。另请参阅"泄露的客户数据"的[联机服务条款 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)文件中。</span><span class="sxs-lookup"><span data-stu-id="90439-p107">No. OME and the option to provide and control your own encryption keys, called BYOK, from Azure Information Protection were not designed to respond to law enforcement subpoenas. OME, with BYOK for Azure Information Protection, was designed for compliance-focused customers. Microsoft takes third-party requests for customer data very seriously. As a cloud service provider, we always advocate for the privacy of customer data. In the event we get a subpoena, we always attempt to redirect the third party to the customer to obtain the information. (Please read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). We periodically publish detailed information of the request we receive. For more information regarding third-party data requests, see [Responding to government and law enforcement requests to access customer data](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data) on the Microsoft Trust Center. Also, see "Disclosure of Customer Data" in the [Online Services Terms (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx).</span></span>
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a><span data-ttu-id="90439-141">此功能如何与旧的 Office 365 邮件加密 (OME) 和信息权限管理 (IRM) 功能？</span><span class="sxs-lookup"><span data-stu-id="90439-141">How is this feature related to legacy Office 365 Message Encryption (OME) and Information Rights Management (IRM) features?</span></span>

<span data-ttu-id="90439-p108">Office 365 邮件加密的新功能的现有 IRM 和旧式 OME 解决方案的发展。下表提供了更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="90439-p108">The new capabilities for Office 365 Message Encryption are an evolution of the existing IRM and legacy OME solutions. The following table provides more details.</span></span>
  
<span data-ttu-id="90439-144">**旧 OME、 IRM 和 OME 的新功能的比较**</span><span class="sxs-lookup"><span data-stu-id="90439-144">**Comparison of legacy OME, IRM, and new OME capabilities**</span></span>

|<span data-ttu-id="90439-145">**功能**</span><span class="sxs-lookup"><span data-stu-id="90439-145">**Capability**</span></span>|<span data-ttu-id="90439-146">**早期版本的 OME**</span><span class="sxs-lookup"><span data-stu-id="90439-146">**Previous versions of OME**</span></span>|<span data-ttu-id="90439-147">**IRM**</span><span class="sxs-lookup"><span data-stu-id="90439-147">**IRM**</span></span>|<span data-ttu-id="90439-148">**OME 的新功能**</span><span class="sxs-lookup"><span data-stu-id="90439-148">**New OME capabilities**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="90439-149">**发送加密电子邮件**</span><span class="sxs-lookup"><span data-stu-id="90439-149">**Sending an encrypted email**</span></span>|<span data-ttu-id="90439-150">只能通过 Exchange 邮件流规则</span><span class="sxs-lookup"><span data-stu-id="90439-150">Only through Exchange mail flow rules</span></span>|<span data-ttu-id="90439-151">最终用户从 Outlook 中的 PC、 for Mac、 Outlook 或 Outlook web; 上启动或通过 Exchange 邮件流规则</span><span class="sxs-lookup"><span data-stu-id="90439-151">End-user initiated from Outlook for PC, Outlook for Mac, or Outlook on the web; or through Exchange mail flow rules</span></span>|<span data-ttu-id="90439-152">最终用户从 Outlook 中的 PC、 for Mac、 Outlook 或 Outlook web; 上启动或通过邮件流规则</span><span class="sxs-lookup"><span data-stu-id="90439-152">End-user initiated from Outlook for PC, Outlook for Mac, or Outlook on the web; or through mail flow rules</span></span>|
|<span data-ttu-id="90439-153">**版权管理**</span><span class="sxs-lookup"><span data-stu-id="90439-153">**Rights management**</span></span>|-|<span data-ttu-id="90439-154">不转接选项和自定义模板</span><span class="sxs-lookup"><span data-stu-id="90439-154">Do Not Forward option and custom templates</span></span>|<span data-ttu-id="90439-155">执行不转接选项、 仅用于加密的选项、 默认和自定义模板</span><span class="sxs-lookup"><span data-stu-id="90439-155">Do Not Forward option, encrypt-only option, default and custom templates</span></span>|
|<span data-ttu-id="90439-156">**受支持的收件人类型**</span><span class="sxs-lookup"><span data-stu-id="90439-156">**Supported recipient type**</span></span>|<span data-ttu-id="90439-157">仅外部收件人</span><span class="sxs-lookup"><span data-stu-id="90439-157">External recipients only</span></span>|<span data-ttu-id="90439-158">仅内部收件人</span><span class="sxs-lookup"><span data-stu-id="90439-158">Internal recipients only</span></span>|<span data-ttu-id="90439-159">内部和外部收件人</span><span class="sxs-lookup"><span data-stu-id="90439-159">Internal and external recipients</span></span>|
|<span data-ttu-id="90439-160">**收件人的体验**</span><span class="sxs-lookup"><span data-stu-id="90439-160">**Experience for recipient**</span></span>|<span data-ttu-id="90439-161">外部收件人收到 HTML 邮件它们下载和浏览器中打开或下载移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="90439-161">External recipients received an HTML message that they downloaded and opened in a browser or downloaded mobile app.</span></span>|<span data-ttu-id="90439-162">内部收件人仅收到的 PC 的 Outlook、 Outlook for Mac 和在 web 上的 Outlook 中的加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="90439-162">Internal recipients only received encrypted email in Outlook for PC, Outlook for Mac, and Outlook on the web.</span></span>|<span data-ttu-id="90439-p109">内部和外部收件人的 PC 的 Outlook、 Outlook for Mac、 web 上的 Outlook、 for Android，Outlook 和 Outlook 中接收电子邮件，适用于 iOS，或通过 web 门户，无论他们是相同的 Office 365 组织中或任何 Office 365 中组织。OME 门户需要没有单独下载。</span><span class="sxs-lookup"><span data-stu-id="90439-p109">Internal and external recipients receive email in Outlook for PC, Outlook for Mac, Outlook on the web, Outlook for Android, and Outlook for iOS, or through a web portal, regardless of whether or not they are in the same Office 365 organization or in any Office 365 organization. The OME portal requires no separate download.</span></span>|
|<span data-ttu-id="90439-165">**使您自己的密钥支持**</span><span class="sxs-lookup"><span data-stu-id="90439-165">**Bring Your Own Key support**</span></span>|<span data-ttu-id="90439-166">不可用</span><span class="sxs-lookup"><span data-stu-id="90439-166">Not available</span></span>|<span data-ttu-id="90439-167">不可用</span><span class="sxs-lookup"><span data-stu-id="90439-167">Not available</span></span>| <span data-ttu-id="90439-168">BYOK 支持</span><span class="sxs-lookup"><span data-stu-id="90439-168">BYOK supported</span></span>|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a><span data-ttu-id="90439-169">如何为我的组织中启用新的 OME 功能？</span><span class="sxs-lookup"><span data-stu-id="90439-169">How do I enable the new OME capabilities for my organization?</span></span>

<span data-ttu-id="90439-170">请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="90439-170">See [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a><span data-ttu-id="90439-171">将被弃用 OME 的早期版本？</span><span class="sxs-lookup"><span data-stu-id="90439-171">Will the previous version of OME be deprecated?</span></span>

<span data-ttu-id="90439-p110">您仍可以使用以前版本的 OME，此时将不弃用。但是，我们强烈建议组织使用新的和改进 OME 解决方案。不已经部署了 OME 的客户不能设置 OME 的早期版本的新部署。</span><span class="sxs-lookup"><span data-stu-id="90439-p110">You can still use the previous version of OME, it will not be deprecated at this time. However, we highly encourage organizations to use the new and improved OME solution. Customers that have not already deployed OME cannot set up a new deployment of the previous version of OME.</span></span>
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a><span data-ttu-id="90439-175">我的组织使用 Active Directory 权限管理，可以使用此功能？</span><span class="sxs-lookup"><span data-stu-id="90439-175">My organization uses Active Directory Rights Management, can I use this functionality?</span></span>

<span data-ttu-id="90439-p111">不。如果您使用 Exchange Online 与 Active Directory 权限管理服务 (AD RMS)，不能立即启用这些新功能。相反，您需要[迁移到 Azure 信息保护 AD RMS](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)首先。</span><span class="sxs-lookup"><span data-stu-id="90439-p111">No. If you are using Exchange Online with Active Directory Rights Management service (AD RMS), you can't enable these new capabilities right away. Instead, you need to [migrate AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) first.</span></span> 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a><span data-ttu-id="90439-p112">我的组织具有的 Exchange 混合部署。可以使用此功能？</span><span class="sxs-lookup"><span data-stu-id="90439-p112">My organization has an Exchange Hybrid deployment. Can I use this feature?</span></span>

<span data-ttu-id="90439-p113">内部部署用户可以发送加密的邮件使用 Exchange Online 邮件流规则。若要执行此操作，您需要通过 Exchange Online 电子邮件路由。</span><span class="sxs-lookup"><span data-stu-id="90439-p113">On-premises users can send encrypted mail using Exchange Online mail flow rules. In order to do this, you need to route email through Exchange Online.</span></span>
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a><span data-ttu-id="90439-p114">需要哪些电子邮件客户端使用以创建 OME 加密的邮件？支持哪些应用程序发送受保护的邮件？</span><span class="sxs-lookup"><span data-stu-id="90439-p114">What email client do I need to use in order to create an OME encrypted message? What applications are supported for sending protected messages?</span></span>

<span data-ttu-id="90439-185">从 Outlook 2016 和 Outlook 2013 的 PC 和 Mac，以及 web 上的 Outlook，您可以创建受保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="90439-185">You can create protected messages from Outlook 2016, and Outlook 2013 for PC and Mac, and from Outlook on the web.</span></span>
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a><span data-ttu-id="90439-186">读取和受保护的电子邮件进行回复操作支持哪些电子邮件客户端？</span><span class="sxs-lookup"><span data-stu-id="90439-186">What email clients are supported to read and reply to protected emails?</span></span>

<span data-ttu-id="90439-p115">您可以阅读并响应从 Outlook PC 和 Mac （2013年和 2016年）、 在 web 上，Outlook 和 Outlook mobile （Android 和 iOS），如果您是 Office 365 用户。如果您的组织允许，您还可以使用 iOS 的本机邮件客户端。如果您是 Office 365 用户，您可以阅读并回复加密邮件 web 上通过 web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="90439-p115">You can read and respond from Outlook for PC and Mac (2013 and 2016), Outlook on the web, and Outlook mobile (Android and iOS) if you are an Office 365 user. You can also use the iOS native mail client if your organization allows it. If you are a non-Office 365 user, you can read and reply to encrypted messages on the web through your web browser.</span></span>
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a><span data-ttu-id="90439-p116">在受保护的电子邮件中的附件为支持哪些文件类型？附件将继承与受保护的电子邮件相关的保护策略？</span><span class="sxs-lookup"><span data-stu-id="90439-p116">What file types are supported as attachments in protected emails? Do attachments inherit the protection policies associated with protected emails?</span></span>

<span data-ttu-id="90439-192">可以附加到受保护的邮件，任何文件类型，但仅在文件格式提到[此处](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)应用保护策略。</span><span class="sxs-lookup"><span data-stu-id="90439-192">You can attach any file type to a protected mail, however protection policies are applied only on the file formats mentioned [here](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types).</span></span> 
  
<span data-ttu-id="90439-p117">如果受支持的文件格式，例如 Word、 Excel 或 PowerPoint 文件，该文件始终受保护，即使已收件人下载附件。例如，如果附件受不要转发，且原始收件人下载和转发给新收件人的附件，新收件人将无法打开受保护的文件。</span><span class="sxs-lookup"><span data-stu-id="90439-p117">If a file format is supported, such as a Word, Excel, or PowerPoint file, the file is always protected, even after the attachment has been downloaded by the recipient. For example, if an attachment is protected by Do Not Forward, and the original recipient downloads and forwards the attachment to a new recipient, the new recipient will not be able to open the protected file.</span></span>
  
## <a name="are-pdf-file-attachments-supported"></a><span data-ttu-id="90439-195">PDF 文件附件支持？</span><span class="sxs-lookup"><span data-stu-id="90439-195">Are PDF file attachments supported?</span></span>

<span data-ttu-id="90439-p118">如果将 PDF 文件附加到受保护的邮件，将受保护邮件本身，但没有其他保护将应用到 PDF 文件之后收件人已收到。这意味着，收件人可以另存为、 转接、 复制和打印为 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="90439-p118">If you attach a PDF file to a protected message, the message itself will be protected, but no additional protection will be applied to the PDF file after the recipient has received it. This means that the recipient can Save As, Forward, Copy, and Print the PDF file.</span></span>
  
## <a name="are-onedrive-for-business-attachments-supported"></a><span data-ttu-id="90439-198">支持的业务附件 OneDrive？</span><span class="sxs-lookup"><span data-stu-id="90439-198">Are OneDrive for Business attachments supported?</span></span>

<span data-ttu-id="90439-p119">还没有。不支持的 OneDrive for Business 附件和最终用户无法对包含云 OneDrive for Business 附件的邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="90439-p119">Not yet. OneDrive for Business attachments are not supported and end-users can't encrypt a mail that contains a cloud OneDrive for Business attachment.</span></span>
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a><span data-ttu-id="90439-201">可以自动加密邮件的设置策略？</span><span class="sxs-lookup"><span data-stu-id="90439-201">Can I automatically encrypt messages by setting up policies?</span></span>

<span data-ttu-id="90439-p120">是的。邮件流规则在 Exchange Online 使用自动加密根据某些条件一条消息。例如，您可以创建基于收件人的策略 ID，收件人的域，或在正文或邮件的主题中的内容。请参阅[定义邮件流规则来加密 Office 365 中的电子邮件。](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="90439-p120">Yes. Use mail flow rules in Exchange Online to automatically encrypt a message based on certain conditions. For example, you can create policies that are based on recipient ID, recipient domain, or on the content in the body or subject of the message. See [Define mail flow rules to encrypt email messages in Office 365.](define-mail-flow-rules-to-encrypt-email.md)</span></span>
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a><span data-ttu-id="90439-206">可以我自动加密邮件的设置策略中的数据丢失防护 (DLP) 通过安全&amp;合规性中心？</span><span class="sxs-lookup"><span data-stu-id="90439-206">Can I automatically encrypt messages by setting up policies in Data Loss Prevention (DLP) through the Security &amp; Compliance Center?</span></span>

<span data-ttu-id="90439-p121">当前您可以仅设置邮件流规则在 Exchange Online。通过安全 DLP 中当前不支持加密&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="90439-p121">Currently you can only set up mail flow rules in Exchange Online. Encryption is currently not supported in DLP through the Security &amp; Compliance Center.</span></span>
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a><span data-ttu-id="90439-209">可以自加密的邮件定义与公司品牌</span><span class="sxs-lookup"><span data-stu-id="90439-209">Can I customize encrypted messages with my company branding?</span></span>

<span data-ttu-id="90439-p122">是的！自定义电子邮件和 OME 门户网站的信息，请参阅将您的组织品牌添加到加密邮件。请参阅[将您的组织品牌添加到加密邮件。](add-your-organization-brand-to-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="90439-p122">Yes! For information on customizing email messages and the OME portal, see Add your organization's brand to your encrypted messages. See [Add your organization's brand to your encrypted messages.](add-your-organization-brand-to-encrypted-messages.md)</span></span>
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a><span data-ttu-id="90439-213">是否有任何报告的功能或见解的加密电子邮件？</span><span class="sxs-lookup"><span data-stu-id="90439-213">Are there any reporting capabilities or insights for encrypted emails?</span></span>

<span data-ttu-id="90439-214">不能在此时间但即将提供。</span><span class="sxs-lookup"><span data-stu-id="90439-214">Not at this time but coming soon.</span></span>
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a><span data-ttu-id="90439-215">可以使用如电子数据展示的合规性功能使用邮件加密吗？</span><span class="sxs-lookup"><span data-stu-id="90439-215">Can I use message encryption with compliance features such as eDiscovery?</span></span>

<span data-ttu-id="90439-p123">是的。所有加密的电子邮件是通过 Office 365 合规性功能可供搜索。</span><span class="sxs-lookup"><span data-stu-id="90439-p123">Yes. All encrypted email messages are discoverable by Office 365 compliance features.</span></span>
  


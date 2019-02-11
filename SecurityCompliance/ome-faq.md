---
title: Office 365 邮件加密 FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/9/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: 有关于 Office 365 中的新邮件保护功能的工作方式的问题？检查此处答案。
ms.openlocfilehash: e35495106b44ccb566f4da743264def8c7d4f96f
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696266"
---
# <a name="office-365-message-encryption-faq"></a>Office 365 邮件加密 FAQ

有关于 Office 365 中的新邮件保护功能的工作方式的问题？检查此处答案。此外，看看[有关在 Azure 信息保护的数据保护的常见问题](https://docs.microsoft.com/information-protection/get-started/faqs-rms)的 Azure 权限管理的数据保护服务有关的问题的解答在 Azure 信息保护。

||
|:-----|
|本文是系列的有关 Office 365 邮件加密的文章的较大一部分。本文旨在为管理员和 ITPros。如果您只查找有关的信息发送或接收加密的邮件， [Office 365 邮件加密 (OME)](ome.md)中的文章的列表，请参阅并找到最适合您的需求的文章。 |
||
  
## <a name="what-is-office-365-message-encryption-ome"></a>什么是 Office 365 邮件加密 (OME)？

OME 结合了电子邮件加密和权限管理功能。Azure 信息保护由供电权限管理功能。
  
## <a name="who-can-use-ome"></a>谁可以使用 OME？

在下列情况下，您可以使用的 OME 的新功能：
  
- 如果您从不为 Office 365 中 Exchange Online 设置 OME 或 IRM。
    
- 如果您已设置 OME 和 IRM，您可以使用这些步骤，如果您使用的从 Azure 信息保护 Azure 权限管理服务。
    
- 如果您使用 Exchange Online 与 Active Directory 权限管理服务 (AD RMS)，不能立即启用这些新功能。相反，您需要[迁移到 Azure 信息保护 AD RMS](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)首先。完成迁移后，您可以成功设置 OME。 
    
    如果您选择要继续使用本地 AD RMS 与 Exchange Online 而不是迁移到 Azure 信息保护，您将无法使用这些新功能。
    
## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>使用新的 OME 功能需要哪些订阅？

若要使用的新 OME 功能，您需要以下计划之一：
  
- Office 365 邮件加密的 Office 365 E3 和 E5、 Microsoft E3 和 E5、 Office 365 A1，A3，和 A5 和 Office 365 G3 和 G5 一部分提供。客户不需要额外许可证接收由 Azure 信息保护的新保护功能。 
    
- 您还可以添加到以下 Azure 信息保护计划 1 计划收到新的 Office 365 邮件加密功能： Exchange Online 计划 1、 Exchange Online 计划 2、 Office 365 F1、 Office 365 业务 Essentials、 Office 365 企业高级版，或Office 365 企业版 E1。
    
- 受益于 Office 365 邮件加密的每个用户需要被许可功能覆盖。
    
- 完整列表请参阅为 Office 365 邮件加密的[Exchange Online 服务说明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)。 
    
## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>可以使用 Exchange Online 使用将您自己的密钥 (BYOK) 放在 Azure 信息保护？

是的！Microsoft 建议您完成设置 BYOK 设置 OME 之前的步骤。
  
有关 BYOK 的详细信息，请参阅[规划和实现您的 Azure 信息保护租户密钥](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>OME 和 Azure 的信息保护 BYOK 更改 Microsoft 的方法为第三方数据请求，例如传讯？

不。未设计 OME 和选项来提供自己的加密密钥，从 Azure 信息保护调用 BYOK，法律强制实施传讯响应。OME，与 Azure 信息保护 BYOK 设计的合规性中心客户。Microsoft 非常严重采用第三方客户数据请求。为云服务提供程序，我们始终提倡隐私的客户数据。在事件我们获得传唤，我们始终尝试将第三方重定向客户以获取信息。(请阅读 Brad Smith 的博客：[从政府窥探 Protecting 客户数据](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。我们将定期发布我们收到的请求的详细的信息。有关第三方数据请求的详细信息，，请参阅[响应政府和法律强制实施请求访问客户数据](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data)，Microsoft 信任中心上。另请参阅"泄露的客户数据"的[联机服务条款 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)文件中。
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>此功能如何与旧的 Office 365 邮件加密 (OME) 和信息权限管理 (IRM) 功能？

Office 365 邮件加密的新功能的现有 IRM 和旧式 OME 解决方案的发展。下表提供了更多详细信息。
  
**旧 OME、 IRM 和 OME 的新功能的比较**

|**功能**|**早期版本的 OME**|**IRM**|**OME 的新功能**|
|:-----|:-----|:-----|:-----|
|**发送加密电子邮件**|只能通过 Exchange 邮件流规则|最终用户从 Outlook 中的 PC、 for Mac、 Outlook 或 Outlook web; 上启动或通过 Exchange 邮件流规则|最终用户从 Outlook 中的 PC、 for Mac、 Outlook 或 Outlook web; 上启动或通过邮件流规则|
|**版权管理**|-|不转接选项和自定义模板|执行不转接选项、 仅用于加密的选项、 默认和自定义模板|
|**受支持的收件人类型**|仅外部收件人|仅内部收件人|内部和外部收件人|
|**收件人的体验**|外部收件人收到 HTML 邮件它们下载和浏览器中打开或下载移动应用程序。|内部收件人仅收到的 PC 的 Outlook、 Outlook for Mac 和在 web 上的 Outlook 中的加密电子邮件。|内部和外部收件人的 PC 的 Outlook、 Outlook for Mac、 web 上的 Outlook、 for Android，Outlook 和 Outlook 中接收电子邮件，适用于 iOS，或通过 web 门户，无论他们是相同的 Office 365 组织中或任何 Office 365 中组织。OME 门户需要没有单独下载。|
|**使您自己的密钥支持**|不可用|不可用| BYOK 支持|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>如何为我的组织中启用新的 OME 功能？

请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>将被弃用 OME 的早期版本？

您仍可以使用以前版本的 OME，此时将不弃用。但是，我们强烈建议组织使用新的和改进 OME 解决方案。不已经部署了 OME 的客户不能设置 OME 的早期版本的新部署。
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>我的组织使用 Active Directory 权限管理，可以使用此功能？

不。如果您使用 Exchange Online 与 Active Directory 权限管理服务 (AD RMS)，不能立即启用这些新功能。相反，您需要[迁移到 Azure 信息保护 AD RMS](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)首先。 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>我的组织具有的 Exchange 混合部署。可以使用此功能？

内部部署用户可以发送加密的邮件使用 Exchange Online 邮件流规则。若要执行此操作，您需要通过 Exchange Online 电子邮件路由。有关详细信息，请参阅[部分 2： 配置邮件流从电子邮件服务器到 Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>需要哪些电子邮件客户端使用以创建 OME 加密的邮件？支持哪些应用程序发送受保护的邮件？

从 Outlook 2016 和 Outlook 2013 的 PC 和 Mac，以及 web 上的 Outlook，您可以创建受保护的邮件。
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>读取和受保护的电子邮件进行回复操作支持哪些电子邮件客户端？

您可以阅读并响应从 Outlook PC 和 Mac （2013年和 2016年）、 在 web 上，Outlook 和 Outlook mobile （Android 和 iOS），如果您是 Office 365 用户。如果您的组织允许，您还可以使用 iOS 的本机邮件客户端。如果您是 Office 365 用户，您可以阅读并回复加密邮件 web 上通过 web 浏览器。
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>在受保护的电子邮件中的附件为支持哪些文件类型？附件将继承与受保护的电子邮件相关的保护策略？

可以附加到受保护的邮件，任何文件类型，但仅在文件格式提到[此处](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)应用保护策略。 
  
如果受支持的文件格式，例如 Word、 Excel 或 PowerPoint 文件，该文件始终受保护，即使已收件人下载附件。例如，如果附件受不要转发，且原始收件人下载和转发给新收件人的附件，新收件人将无法打开受保护的文件。
  
## <a name="are-pdf-file-attachments-supported"></a>PDF 文件附件支持？

如果将 PDF 文件附加到受保护的邮件，将受保护邮件本身，但没有其他保护将应用到 PDF 文件之后收件人已收到。这意味着，收件人可以另存为、 转接、 复制和打印为 PDF 文件。
  
## <a name="are-onedrive-for-business-attachments-supported"></a>支持的业务附件 OneDrive？

还没有。不支持的 OneDrive for Business 附件和最终用户无法对包含云 OneDrive for Business 附件的邮件进行加密。
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>可以自动加密邮件的设置策略？

是的。邮件流规则在 Exchange Online 使用自动加密根据某些条件一条消息。例如，您可以创建基于收件人的策略 ID，收件人的域，或在正文或邮件的主题中的内容。请参阅[定义邮件流规则来加密 Office 365 中的电子邮件。](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>可以我自动加密邮件的设置策略中的数据丢失防护 (DLP) 通过安全&amp;合规性中心？

是的！您可以设置邮件流规则在 Exchange Online 或中安全使用 DLP&amp;合规性中心。
  
## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>可以打开加密的邮件发送到共享邮箱？

共享邮箱不支持当前加密的邮件。

## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>可以自加密的邮件定义与公司品牌

是的！自定义电子邮件和 OME 门户网站的信息，请参阅将您的组织品牌添加到加密邮件。请参阅[将您的组织品牌添加到加密邮件。](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>是否有任何报告的功能或见解的加密电子邮件？

不能在此时间但即将提供。
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>可以使用如电子数据展示的合规性功能使用邮件加密吗？

是的。所有加密的电子邮件是通过 Office 365 合规性功能可供搜索。
  


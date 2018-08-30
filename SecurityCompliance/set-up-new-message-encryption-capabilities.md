---
title: 设置全新的 Office 365 邮件加密功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: 可以使用内置到 Azure 信息保护，您的组织的顶部功能的新 Office 365 邮件加密保护与您的组织内外的人员的电子邮件通信。新的 OME 功能使用其他 Office 365 组织、 Outlook.com、 Gmail 和其他电子邮件服务。
ms.openlocfilehash: e59368f5854c86c04f4f0bdf376537d3f6b02d33
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525983"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="6b9c6-104">设置全新的 Office 365 邮件加密功能</span><span class="sxs-lookup"><span data-stu-id="6b9c6-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="6b9c6-p102">使用新的 Office 365 邮件加密 (OME) 功能，利用 Azure Information Protection 中的保护功能，您的组织可以轻松地共享受保护的电子邮件与任何设备上的任何人。用户可以发送和接收与其他 Office 365 组织以及非 Office 365 客户使用 Outlook.com、 Gmail 和其他电子邮件服务的受保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p102">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device. Users can send and receive protected messages with other Office 365 organizations as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>
  
## <a name="get-started-with-ome-by-activating-azure-rights-management-part-of-azure-information-protection"></a><span data-ttu-id="6b9c6-107">开始使用 OME 通过激活 Azure 权限管理 Azure 信息保护的一部分</span><span class="sxs-lookup"><span data-stu-id="6b9c6-107">Get started with OME by activating Azure Rights Management, part of Azure Information Protection</span></span>

<span data-ttu-id="6b9c6-p103">现在，则很容易入门的新 OME 功能。从年 2 月 2018 Office 365 自动启用合格组织内我们数据中心的新 OME 功能。如果为一个新的 Office 365 租户并且您的组织具有相应的订阅，则合格您的组织。* * 如果 * * * * 已启用 Azure 权限管理 (Azure RMS)，一部分 Azure 信息保护，则我们为您自动启用 Office 365 邮件加密。* * 您无需进行任何其他启用 OME 操作。若要激活 Azure 权限管理，请参阅[激活 Azure 权限管理](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)。订阅的信息，请参阅"哪些订阅我需要使用新的 OME capabilities?"在[Office 365 邮件加密 FAQ](ome-faq.md)。有关购买订阅 Azure 信息保护信息，请参阅[Azure 信息保护](https://azure.microsoft.com/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p103">It's now easy to get started with the new OME capabilities. As of February 2018, Office 365 automatically enables the new OME capabilities for eligible organizations within our datacenters. Your organization is eligible if it is a new Office 365 tenant and your organization has the appropriate subscriptions. ** If ** ** you have enabled Azure Rights Management (Azure RMS), part of Azure Information Protection, then we automatically enable Office 365 Message Encryption for you. ** You don't have to do anything else to enable OME. To activate Azure Rights Management, see [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). For information on subscriptions, see "What subscriptions do I need to use the new OME capabilities?" in the [Office 365 Message Encryption FAQ](ome-faq.md). For information about purchasing a subscription to Azure Information Protection, see [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>
  
<span data-ttu-id="6b9c6-p104">如果您使用 Exchange Online 与 Active Directory 权限管理服务 (AD RMS)，不能立即启用这些新功能。相反，您需要从迁移 AD RMS 到 Azure 信息保护第一次。完成迁移后，您可以成功完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p104">If you are using Exchange Online with Active Directory Rights Management service (AD RMS), you can't enable these new capabilities right away. Instead, you need to migrate from AD RMS to Azure Information Protection first. When you've finished the migration, you can successfully complete these steps.</span></span>
  
<span data-ttu-id="6b9c6-120">如果您选择要继续使用本地 AD RMS 与 Exchange Online 而不是迁移到 Azure 信息保护，您将无法使用这些新功能。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-120">If you choose to continue to use on-premises AD RMS with Exchange Online instead of migrating to Azure Information Protection, you will not be able to use these new capabilities.</span></span>
  
## <a name="how-the-new-capabilities-for-ome-work"></a><span data-ttu-id="6b9c6-121">新功能以 OME 的工作方式</span><span class="sxs-lookup"><span data-stu-id="6b9c6-121">How the new capabilities for OME work</span></span>

<span data-ttu-id="6b9c6-p105">新的 Office 365 邮件加密功能使用的保护功能，也称为从 Azure 信息保护的 Azure 权限管理 (Azure RMS)。这包括加密、 标识和授权的策略，以帮助保护您的电子邮件。您可以使用权限管理模板、[不要转发选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)中，和[仅加密选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)加密邮件。用户可以然后加密电子邮件和 Office 365 附件各种使用这些选项。有关受支持的附件类型的完整列表，请参阅["文件类型涵盖时附加到邮件的 IRM 策略"中的电子邮件的 IRM 简介](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)。作为管理员，您还可以定义要应用此保护的邮件流规则。例如，您可以定义其中的往特定收件人或包含特定词语的主题行中的所有未受保护的邮件防止未经授权的访问和收件人不能复制或打印邮件的内容的规则。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p105">The new Office 365 Message Encryption capabilities use the protection capabilities, also called Azure Rights Management (Azure RMS), from Azure Information Protection. This includes encryption, identity, and authorization policies to help secure your email. You can encrypt messages by using rights management templates, the [Do Not Forward option](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails), and the [encrypt-only option](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails). Users can then encrypt email messages and a variety of Office 365 attachments by using these options. For a full list of supported attachment types, see ["File types covered by IRM policies when they are attached to messages" in Introduction to IRM for email messages](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM). As an administrator, you can also define mail flow rules to apply this protection. For example, you can define a rule where all unprotected messages that are addressed to a specific recipient or that contain specific words in the subject line are protected from unauthorized access, and the recipients can't copy or print the contents of the message.</span></span>
  
<span data-ttu-id="6b9c6-p106">与以前的版本 OME 不同这些新功能提供统一的发件人的体验，是否要在组织内部或外部 Office 365 的收件人发送邮件。此外，接收发送到 Office 365 帐户 Outlook 2016 或 web 上的 Outlook 中受保护的电子邮件收件人无需采取任何其他操作来查看该邮件。无缝工作。收件人使用其他电子邮件客户端和电子邮件服务提供商还具有改进的体验。有关信息，请参阅[了解 Office 365 中的受保护的邮件](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)和[如何打开受保护的邮件](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p106">Unlike the previous version of OME, these new capabilities provide a unified sender experience whether you're sending mail inside your organization or to recipients outside of Office 365. In addition, recipients who receive a protected email message sent to an Office 365 account in Outlook 2016 or Outlook on the web, don't have to take any additional action to view the message. It works seamlessly. Recipients using other email clients and email service providers also have an improved experience. For information, see [Learn about protected messages in Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) and [How do I open a protected message](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).</span></span>
  
## <a name="steps-to-manually-set-up-the-new-capabilities-for-ome"></a><span data-ttu-id="6b9c6-134">手动设置的新功能，为 OME 步骤</span><span class="sxs-lookup"><span data-stu-id="6b9c6-134">Steps to manually set up the new capabilities for OME</span></span>

<span data-ttu-id="6b9c6-135">如果您的组织不自动具有 OME 启用，或者打开 OME 关闭，请按照以下步骤手动设置的新功能，为 OME。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-135">If your organization does not automatically have OME enabled, or if you turned OME off, follow these steps to manually set up the new capabilities for OME.</span></span>
  
### <a name="to-manually-set-up-the-new-capabilities-for-ome"></a><span data-ttu-id="6b9c6-136">手动设置的新功能，为 OME</span><span class="sxs-lookup"><span data-stu-id="6b9c6-136">To manually set up the new capabilities for OME</span></span>

1. <span data-ttu-id="6b9c6-p107">确保您的组织具有右订阅。有关订阅的信息，请参阅"哪些订阅我需要使用新的 OME capabilities?"中的[Office 365 邮件加密 FAQ。](ome-faq.md)有关购买订阅 Azure 信息保护信息，请参阅[Azure 信息保护](https://azure.microsoft.com/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p107">Ensure you have the right subscription for your organization. For information on subscriptions, see "What subscriptions do I need to use the new OME capabilities?" in the [Office 365 Message Encryption FAQ.](ome-faq.md) For information about purchasing a subscription to Azure Information Protection, see [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>
    
2. <span data-ttu-id="6b9c6-p108">决定是否要在 Microsoft 管理根密钥的 Azure 信息保护 （默认），或生成并管理此密钥自己 （称为使您自己的项或 BYOK）。如果您想要生成并自己管理此项，需要完成一些步骤之前为 OME 设置的新功能。有关详细信息，请参阅[规划和实现您的 Azure 信息保护租户密钥](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。Microsoft 建议您之前设置 OME 完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p108">Decide whether you want Microsoft to manage the root key for Azure Information Protection (the default), or generate and manage this key yourself (known as bring your own key, or BYOK). If you want to generate and manage this key yourself, you need to complete some steps before you set up the new capabilities for OME. For more information, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key). Microsoft recommends that you complete these steps before you set up OME.</span></span>
    
3. <span data-ttu-id="6b9c6-p109">激活 Azure 权限管理 OME 中启用的新功能。有关说明，请参阅[激活 Azure 权限管理](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)。当执行此操作时，Office 365 自动启用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p109">Enable the new capabilities for OME by activating Azure Rights Management. For instructions, see [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). When you do this, Office 365 automatically enables the new OME capabilities for you.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="6b9c6-p110">在 Web 上的 outlook 缓存其 UI，因此很好办法等待一天之前您尝试使用此客户端的电子邮件的 OME 应用的新功能。用户界面更新以反映新配置之前，新功能以 OME 将不可用。用户界面更新后，用户可以使用适用于 OME 的新功能保护电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p110">Outlook on the Web caches its UI, so it's a good idea to wait a day before you try applying the new capabilities for OME to email messages using this client. Before the UI updates to reflect the new configuration, the new capabilities for OME won't be available. After the UI updates, users can protect email messages by using the new capabilities for OME.</span></span> 
  
4. <span data-ttu-id="6b9c6-151">（可选）设置新的邮件流规则或更新现有定义如何以及何时要对从组织发出的邮件进行加密的 Office 365 的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-151">(Optional) Set up new mail flow rules or update existing mail flow rules that define how and when you want Office 365 to encrypt messages sent from your organization.</span></span>
    
## <a name="verify-that-the-new-capabilities-for-ome-are-configured-properly-by-using-windows-powershell"></a><span data-ttu-id="6b9c6-152">验证 OME 的新功能正确配置，可以使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b9c6-152">Verify that the new capabilities for OME are configured properly by using Windows PowerShell</span></span>

<span data-ttu-id="6b9c6-153">按照以下步骤，若要验证正确配置您的租户 OME 通过 Exchange Online PowerShell 中使用的新功能。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-153">Follow these steps to verify that your tenant is properly configured to use the new capabilities for OME through Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="6b9c6-p111">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，请启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="6b9c6-156">运行 Test-irmconfiguration cmdlet 使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="6b9c6-156">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>
    
  ```
  Test-IRMConfiguration [-Sender <email address >]
  ```

    <span data-ttu-id="6b9c6-157">例如：</span><span class="sxs-lookup"><span data-stu-id="6b9c6-157">For example:</span></span>
    
  ```
  Test-IRMConfiguration -Sender securityadmin@contoso.com
  ```

    <span data-ttu-id="6b9c6-p112">其中电子邮件地址是用户的 Office 365 组织中的电子邮件地址。可选的提供的发件人电子邮件地址强制执行其他检查系统的同时。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p112">Where email address is the email address of a user in your Office 365 organization. While optional, providing a sender email address forces the system to perform additional checks.</span></span>
    
    <span data-ttu-id="6b9c6-160">您的结果应类似于这些：</span><span class="sxs-lookup"><span data-stu-id="6b9c6-160">Your results should look like these:</span></span>
    
  ```
  Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not 
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.
            
            OVERALL RESULT: PASS
  ```

    <span data-ttu-id="6b9c6-161">其中*Contoso*被替换 Office 365 组织的名称。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-161">Where  *Contoso*  is replaced with the name of your Office 365 organization.</span></span> 
    
    <span data-ttu-id="6b9c6-162">可能不同于上面结果中显示的结果中返回的默认模板的名称。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-162">The names of the default templates returned in the results may be different from those displayed in the results above.</span></span>
    
    <span data-ttu-id="6b9c6-p113">模板和信息的默认模板简介，请参阅[配置和管理 Azure 信息保护模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关不要转发选项，仅用于加密的选项，以及如何创建其他模板或找出哪些权限中包含的现有模板，请参阅[Configuring Azure 权限管理的使用权限](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights)。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p113">For an introduction to templates and information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the Do Not Forward option, encrypt-only option, and how to create additional templates, or find out what rights are included in an existing template, see [Configuring usage rights for Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights).</span></span>
    
3. <span data-ttu-id="6b9c6-165">运行 Remove-pssession cmdlet，以断开 Rights Management 服务。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-165">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>
    
  ```
  Remove-PSSession $session
  ```

## <a name="next-steps-define-new-mail-flow-rules-that-use-the-new-ome-capabilities"></a><span data-ttu-id="6b9c6-166">后续步骤： 定义使用新的 OME 功能的新邮件流规则</span><span class="sxs-lookup"><span data-stu-id="6b9c6-166">Next steps: Define new mail flow rules that use the new OME capabilities</span></span>
<span data-ttu-id="6b9c6-167"><a name="Rules_1"> </a></span><span class="sxs-lookup"><span data-stu-id="6b9c6-167"></span></span>

<span data-ttu-id="6b9c6-p114">此步骤是可选的新 OME 部署，但是，此步骤是必需的现有 OME 部署的已邮件流规则设置为加密传出邮件。如果您想要利用新的 OME 功能，则必须更新现有的邮件流规则。否则，您的用户将继续接收加密电子邮件，而不是新的、 无缝 OME 体验使用以前的 HTML 附件格式。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p114">This step is optional for new OME deployments, however, this step is required for existing OME deployments that already have mail flow rules set up to encrypt outgoing mail. If you want to take advantage of the new OME capabilities, you must update your existing mail flow rules. Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience.</span></span>
  
<span data-ttu-id="6b9c6-p115">邮件流规则确定在什么条件电子邮件消息应进行加密，以及删除加密的条件。设置规则操作时，他们正在发送时，匹配的规则条件的任何邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-p115">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption. When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="6b9c6-173">有关邮件流规则的详细信息，请参阅[定义邮件流规则来加密 Office 365 中的电子邮件](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="6b9c6-173">For more information about mail flow rules, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6b9c6-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="6b9c6-174">Related Topics</span></span>
<span data-ttu-id="6b9c6-175"><a name="Rules_1"> </a></span><span class="sxs-lookup"><span data-stu-id="6b9c6-175"></span></span>

[<span data-ttu-id="6b9c6-176">发送、 查看和回复 Outlook 中的加密邮件</span><span class="sxs-lookup"><span data-stu-id="6b9c6-176">Send, view, and reply to encrypted messages in Outlook</span></span>](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
  
[<span data-ttu-id="6b9c6-177">启用 Aadrm</span><span class="sxs-lookup"><span data-stu-id="6b9c6-177">Enable-Aadrm</span></span>](https://docs.microsoft.com/powershell/module/aadrm/enable-aadrm?view=azureipps)
  
[<span data-ttu-id="6b9c6-178">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6b9c6-178">Connect to Exchange Online PowerShell</span></span>](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="6b9c6-179">定义邮件流规则来加密 Office 365 中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="6b9c6-179">Define mail flow rules to encrypt email messages in Office 365</span></span>](define-mail-flow-rules-to-encrypt-email.md)
  


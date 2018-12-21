---
title: 为以前版本的 Office 365 邮件加密设置 Azure 权限管理
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 以前版本的 Office 365 邮件加密取决于在 Microsoft Azure 权限管理 （以前称为 Windows Azure Active Directory 权限管理）。
ms.openlocfilehash: 994364fd74881e40f97daa3c2d12e31282b421fd
ms.sourcegitcommit: 1c00bba6ddcdd7ead6cc0153c8a2c20de05262ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2018
ms.locfileid: "27382922"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="1ec8f-103">为以前版本的 Office 365 邮件加密设置 Azure 权限管理</span><span class="sxs-lookup"><span data-stu-id="1ec8f-103">Set up Azure Rights Management for the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="1ec8f-104">本主题介绍需要才能激活并将设置 Azure 权限管理 (RMS)，与以前版本的 Office 365 邮件加密 (OME) 一起使用的 Azure 信息保护的一部分执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="1ec8f-105">本文仅适用于 OME 的早期版本</span><span class="sxs-lookup"><span data-stu-id="1ec8f-105">This article only applies to the previous version of OME</span></span>
<span data-ttu-id="1ec8f-p101">如果您没有尚未将您的 Office 365 组织移到 OME 的新功能，但您已经部署了 OME，本文中的信息适用于您的组织。Microsoft 建议您进行规划，以将移动到新的 OME 功能只要很合理为您的组织。有关说明，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。如果您想要找出有关的新功能，首先工作的方式的详细信息，请参阅[Office 365 邮件加密](ome.md)。本文的其余部分是指之前的版本的新功能，OME OME 行为。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-p101">If you haven't yet moved your Office 365 organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md). If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md). The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="1ec8f-111">使用以前版本的 Office 365 邮件加密的先决条件</span><span class="sxs-lookup"><span data-stu-id="1ec8f-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="1ec8f-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="1ec8f-112"></span></span>

<span data-ttu-id="1ec8f-p102">Office 365 邮件加密 (OME)，包括 IRM，取决于 Azure 权限管理 (Azure RMS)。Azure RMS 是使用 Azure 信息保护保护技术。若要使用 OME，您的 Office 365 组织必须包括 Exchange Online 或 Exchange Online Protection 的订阅，反过来，包括 Azure 权限管理订阅。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-p102">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS). Azure RMS is the protection technology used by Azure Information Protection. To use OME, your Office 365 organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="1ec8f-116">如果您不确定您的订阅所包含的内容，请参阅[邮件策略、 恢复以及合规性](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)的 Exchange Online 服务说明。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span></span>

- <span data-ttu-id="1ec8f-117">如果您没有 Azure RMS 订阅 Exchange Online 或 Exchange Online Protection，您必须购买订阅和先激活。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-117">If you don't have an Azure RMS subscription for Exchange Online or Exchange Online Protection, you must purchase a subscription and activate it first.</span></span>

    <span data-ttu-id="1ec8f-p103">有关购买订阅 Azure 权限管理的信息，请参阅[Azure 权限管理](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT)。下一节提供了有关激活 Azure 权限管理的信息。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-p103">For information about purchasing a subscription to Azure Rights Management, see [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). The next section gives you information about activating Azure Rights Management.</span></span>

- <span data-ttu-id="1ec8f-120">如果您有 Azure 权限管理，但它未设置 Exchange Online 或 Exchange Online Protection，这篇文章介绍如何激活 Azure 权限管理，然后介绍设置 OME 以使用 Azure 权限管理的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-120">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="1ec8f-p104">如果您已设置 OME 能够使用 Azure 权限管理 Exchange Online 或 Exchange Online Protection，具体取决于您将其设置，您可能已准备好开始立即使用 OME 和其新的功能。本文介绍如何确定是否您已设置 OME 正确，如果您需要更改您的设置，怎么办以及如果您选择不更改您的安装程序会发生什么情况。例如，若要使用的新功能，您必须使用 Azure RMS OME。不能使用内部部署 Active Directory RMS 的新功能。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-p104">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away. This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup. For example, in order to use the new capabilities, you must use Azure RMS with OME. You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="1ec8f-125">早期版本的 Office 365 中的 OME 激活 Azure 权限管理</span><span class="sxs-lookup"><span data-stu-id="1ec8f-125">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="1ec8f-p105">您需要激活 Azure 权限管理，以便您的组织中的用户可以应用于他们发送的消息的信息保护和打开邮件和 Azure Rights Management 服务受保护的文件。有关说明，请参阅[激活 Azure 权限管理](https://go.microsoft.com/fwlink/p/?LinkId=525775)。完成激活之后，此处返回，并继续执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-p105">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service. For instructions, see [Activating Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="1ec8f-129">将以前版本的 OME 设置为使用 Azure RMS 通过导入可信发布域 (TPDs)</span><span class="sxs-lookup"><span data-stu-id="1ec8f-129">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="1ec8f-p106">TPD 是一个 XML 文件包含有关您组织的权限管理设置的信息。例如，TPD 包含有关用于签名和加密证书和许可证的服务器许可方证书 (SLC) 的信息，Url 用于许可和发布，等等。使用 Windows PowerShell 您导入您的 Office 365 组织的 TPD。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-p106">A TPD is an XML file that contains information about your organization's rights management settings. For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on. You import the TPD into your Office 365 organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1ec8f-p107">以前，您可以选择将 TPDs 从 Active Directory 权限管理服务 (AD RMS) 导入您的 Office 365 组织。但是，这样会阻止您使用的新 OME 功能并不建议使用。如果这种方式配置 Office 365 组织的当前状态，Microsoft 建议您制定的计划以从您的本地 Active Directory RMS 迁移到基于云的 Azure 信息保护。有关详细信息，请参阅[Migrating from AD RMS 到 Azure 信息保护](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。您将无法使用新的 OME 功能，直到您已完成迁移到 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-p107">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your Office 365 organization. However, doing so will prevent you from using the new OME capabilities and is not recommended. If your Office 365 organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection. For more information, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="1ec8f-138">**从 Azure RMS 导入 TPDs**</span><span class="sxs-lookup"><span data-stu-id="1ec8f-138">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="1ec8f-139">[连接到 Exchange Online 使用远程 PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-139">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="1ec8f-140">选择对应于您的 Office 365 组织的地理位置的关键共享 URL:</span><span class="sxs-lookup"><span data-stu-id="1ec8f-140">Choose the key-sharing URL that corresponds to your Office 365 organization's geographic location:</span></span>

|<span data-ttu-id="1ec8f-141">**位置**</span><span class="sxs-lookup"><span data-stu-id="1ec8f-141">**Location**</span></span>|<span data-ttu-id="1ec8f-142">**关键共享位置的 URL**</span><span class="sxs-lookup"><span data-stu-id="1ec8f-142">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1ec8f-143">北美</span><span class="sxs-lookup"><span data-stu-id="1ec8f-143">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="1ec8f-144">欧盟</span><span class="sxs-lookup"><span data-stu-id="1ec8f-144">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="1ec8f-145">亚洲</span><span class="sxs-lookup"><span data-stu-id="1ec8f-145">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="1ec8f-146">南美洲</span><span class="sxs-lookup"><span data-stu-id="1ec8f-146">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="1ec8f-147">政府用 Office 365（政府社区云）</span><span class="sxs-lookup"><span data-stu-id="1ec8f-147">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="1ec8f-148">此 RMS 密钥共享位置以供客户已购买 Office 365 政府版 sku。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-148">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. <span data-ttu-id="1ec8f-149">通过运行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet，如下所示配置密钥共享位置：</span><span class="sxs-lookup"><span data-stu-id="1ec8f-149">Configure the key-sharing location by running the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet as follows:</span></span> 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    <span data-ttu-id="1ec8f-150">例如，若要配置的关键共享位置，如果在北美位于您的组织：</span><span class="sxs-lookup"><span data-stu-id="1ec8f-150">For example, to configure the key sharing location if your organization is located in North America:</span></span>
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. <span data-ttu-id="1ec8f-151">与-RMSOnline 开关从 Azure 权限管理导入 TPD 运行[Import-rmstrustedpublishingdomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1ec8f-151">Run the [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    <span data-ttu-id="1ec8f-p108">您想要用于 TPD 其中*TPDName*是名称。例如，"Contoso 北美 TPD"。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-p108">Where  *TPDName*  is the name you want to use for the TPD. For example, "Contoso North American TPD".</span></span> 
    
5. <span data-ttu-id="1ec8f-154">若要验证已成功配置了 Office 365 组织以使用 Azure 权限管理服务，请运行[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet 与-RMSOnline 开关，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1ec8f-154">To verify that you successfully configured your Office 365 organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet with the -RMSOnline switch as follows:</span></span> 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    <span data-ttu-id="1ec8f-155">除此之外，此 cmdlet 检查与 Azure 权限管理服务的连接，下载 TPD，并检查其有效性。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-155">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>
    
6. <span data-ttu-id="1ec8f-156">运行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet，如下所示禁用 Outlook 在 web 和 Outlook 中不可用的 Azure 权限管理模板：</span><span class="sxs-lookup"><span data-stu-id="1ec8f-156">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. <span data-ttu-id="1ec8f-157">运行[Set-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet，如下所示的基于云的电子邮件组织启用 Azure 权限管理并将其配置为使用 Office 365 邮件加密 Azure 权限管理：</span><span class="sxs-lookup"><span data-stu-id="1ec8f-157">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span> 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. <span data-ttu-id="1ec8f-p109">若要验证您已成功导入 TPD 并启用 Azure 权限管理，请使用 Test-irmconfiguration cmdlet 来测试 Azure 权限管理功能。有关详细信息，请参阅[Test-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)中的"示例 1"。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-p109">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality. For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span></span>
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="1ec8f-160">我有以前版本的 OME 设置与 Active Directory 权限管理不 Azure 信息保护，我该怎么办？</span><span class="sxs-lookup"><span data-stu-id="1ec8f-160">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="1ec8f-161"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="1ec8f-161"></span></span>

<span data-ttu-id="1ec8f-p110">您可以继续使用您现有的 Office 365 邮件加密邮件流规则与 Active Directory 权限管理，但您无法配置或使用新的 OME 功能。相反，您需要将迁移到 Azure 信息保护。有关迁移和这意味着您的组织的信息，请参阅[Migrating from AD RMS 到 Azure 信息保护](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-p110">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities. Instead, you need to migrate to Azure Information Protection. For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="1ec8f-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1ec8f-165">Next steps</span></span>
<span data-ttu-id="1ec8f-166"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="1ec8f-166"></span></span>

<span data-ttu-id="1ec8f-167">当您完成 Azure 权限管理设置，如果您想要启用新的 OME 功能，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部。](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span><span class="sxs-lookup"><span data-stu-id="1ec8f-167">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span></span>
  
<span data-ttu-id="1ec8f-168">已设置您的组织使用的新 OME 功能后，您已准备好[定义邮件流规则来保护与 OME 的新功能的电子邮件消息](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="1ec8f-168">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1ec8f-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="1ec8f-169">Related topics</span></span>
<span data-ttu-id="1ec8f-170"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="1ec8f-170"></span></span>

[<span data-ttu-id="1ec8f-171">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="1ec8f-171">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="1ec8f-172">有关 Office 365 加密的技术参考详情</span><span class="sxs-lookup"><span data-stu-id="1ec8f-172">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="1ec8f-173">什么是 Azure 权限管理？</span><span class="sxs-lookup"><span data-stu-id="1ec8f-173">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  


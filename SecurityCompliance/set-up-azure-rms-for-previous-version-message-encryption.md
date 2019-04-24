---
title: 为以前版本的 Office 365 邮件加密设置 Azure 权限管理
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 早期版本的 Office 365 邮件加密取决于 Microsoft azure 权限管理 (以前称为 "Windows azure Active Directory 权限管理")。
ms.openlocfilehash: 89b86035f57699457c86fefb49888b8428f4e01c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266884"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="d5ab0-103">为以前版本的 Office 365 邮件加密设置 Azure 权限管理</span><span class="sxs-lookup"><span data-stu-id="d5ab0-103">Set up Azure Rights Management for the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="d5ab0-104">本主题介绍了为激活前一版本的 Office 365 邮件加密 (OME) 而激活和设置 azure 权限管理 (RMS) (azure 信息保护的一部分) 时需要遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="d5ab0-105">本文仅适用于早期版本的 OME</span><span class="sxs-lookup"><span data-stu-id="d5ab0-105">This article only applies to the previous version of OME</span></span>
<span data-ttu-id="d5ab0-106">如果您尚未将 Office 365 组织移动到新的 OME 功能, 但您已经部署了 OME, 则本文中的信息适用于您的组织。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-106">If you haven't yet moved your Office 365 organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="d5ab0-107">Microsoft 建议您制定一个计划, 尽快移动到新的 OME 功能, 因为它对您的组织合理。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="d5ab0-108">有关说明, 请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="d5ab0-109">如果您想要详细了解新功能的工作方式, 请参阅[Office 365 邮件加密](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="d5ab0-110">本文的其余部分是在发布新的 OME 功能之前的 OME 行为。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="d5ab0-111">使用早期版本的 Office 365 邮件加密的先决条件</span><span class="sxs-lookup"><span data-stu-id="d5ab0-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="d5ab0-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="d5ab0-112"></span></span>

<span data-ttu-id="d5ab0-113">Office 365 邮件加密 (OME) (包括 IRM) 取决于 Azure 权限管理 (azure RMS)。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="d5ab0-114">azure RMS 是 azure 信息保护使用的保护技术。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="d5ab0-115">若要使用 OME, Office 365 组织必须包括 exchange online 或 exchange online 保护订阅, 这些订阅又包括 Azure 权限管理订阅。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-115">To use OME, your Office 365 organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="d5ab0-116">如果你不确定订阅包含的内容, 请参阅 Exchange Online 服务说明[中的邮件策略、恢复和合规性](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span></span>

- <span data-ttu-id="d5ab0-117">如果没有适用于 exchange online 或 exchange online Protection 的 Azure RMS 订阅, 则必须先购买订阅并将其激活。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-117">If you don't have an Azure RMS subscription for Exchange Online or Exchange Online Protection, you must purchase a subscription and activate it first.</span></span>

    <span data-ttu-id="d5ab0-118">有关购买 azure 权限管理订阅的信息, 请参阅[azure 权限管理](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT)。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-118">For information about purchasing a subscription to Azure Rights Management, see [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT).</span></span> <span data-ttu-id="d5ab0-119">下一部分介绍了如何激活 Azure 权限管理。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-119">The next section gives you information about activating Azure Rights Management.</span></span>

- <span data-ttu-id="d5ab0-120">如果你拥有 Azure 权限管理, 但未针对 exchange online 或 exchange online Protection 进行设置, 则本文介绍如何激活 azure 权限管理, 然后介绍了设置 OME 以使用 Azure 权限管理的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-120">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="d5ab0-121">如果你已将 OME 设置为使用适用于 Azure 权限管理的 exchange online 或 exchange online Protection, 则可能已准备好立即开始使用 OME 及其新功能。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-121">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="d5ab0-122">本文介绍如何确定您是否已正确设置 OME, 如果需要更改设置, 应执行的操作, 如果您选择不更改设置, 会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-122">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="d5ab0-123">例如, 若要使用新功能, 必须将 Azure RMS 与 OME 结合使用。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-123">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="d5ab0-124">您不能将新功能用于本地 Active Directory RMS。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-124">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="d5ab0-125">为 Office 365 中的早期版本的 OME 激活 Azure 权限管理</span><span class="sxs-lookup"><span data-stu-id="d5ab0-125">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="d5ab0-126">您需要激活 azure 权限管理, 以便组织中的用户可以对其发送的邮件应用信息保护, 并打开由 Azure 权限管理服务保护的邮件和文件。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-126">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="d5ab0-127">有关说明, 请参阅[激活 Azure 权限管理](https://go.microsoft.com/fwlink/p/?LinkId=525775)。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-127">For instructions, see [Activating Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775).</span></span> <span data-ttu-id="d5ab0-128">完成激活后, 请返回此处并继续执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-128">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="d5ab0-129">通过导入受信任的发布域 (tpd), 将早期版本的 OME 设置为使用 Azure RMS</span><span class="sxs-lookup"><span data-stu-id="d5ab0-129">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="d5ab0-130">TPD 是一个 XML 文件, 其中包含有关您的组织的权限管理设置的信息。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-130">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="d5ab0-131">例如, TPD 包含有关用于对证书和许可证进行签名和加密的服务器许可方证书 (SLC) 的信息、用于许可和发布的 url 等。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-131">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="d5ab0-132">您可以使用 Windows PowerShell 将 TPD 导入到 Office 365 组织中。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-132">You import the TPD into your Office 365 organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d5ab0-133">以前, 可以选择将 tpd 从 Active Directory 权限管理服务 (AD RMS) 导入 Office 365 组织中。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-133">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your Office 365 organization.</span></span> <span data-ttu-id="d5ab0-134">但是, 这样做会阻止您使用新的 OME 功能, 不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-134">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="d5ab0-135">如果您的 Office 365 组织当前以这种方式配置, Microsoft 建议您创建从本地 Active Directory RMS 迁移到基于云的 Azure 信息保护的计划。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-135">If your Office 365 organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="d5ab0-136">有关详细信息, 请参阅[从 AD RMS 迁移到 Azure 信息保护](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-136">For more information, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="d5ab0-137">在完成到 Azure 信息保护的迁移之前, 你将无法使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-137">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="d5ab0-138">**从 Azure RMS 导入 tpd**</span><span class="sxs-lookup"><span data-stu-id="d5ab0-138">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="d5ab0-139">[使用远程 PowerShell 连接到 Exchange Online](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-139">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="d5ab0-140">选择与您的 Office 365 组织的地理位置对应的密钥共享 URL:</span><span class="sxs-lookup"><span data-stu-id="d5ab0-140">Choose the key-sharing URL that corresponds to your Office 365 organization's geographic location:</span></span>

|<span data-ttu-id="d5ab0-141">**Location**</span><span class="sxs-lookup"><span data-stu-id="d5ab0-141">**Location**</span></span>|<span data-ttu-id="d5ab0-142">**键共享位置 URL**</span><span class="sxs-lookup"><span data-stu-id="d5ab0-142">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d5ab0-143">北美</span><span class="sxs-lookup"><span data-stu-id="d5ab0-143">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="d5ab0-144">欧盟</span><span class="sxs-lookup"><span data-stu-id="d5ab0-144">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="d5ab0-145">亚洲</span><span class="sxs-lookup"><span data-stu-id="d5ab0-145">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="d5ab0-146">南美洲</span><span class="sxs-lookup"><span data-stu-id="d5ab0-146">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="d5ab0-147">政府用 Office 365（政府社区云）</span><span class="sxs-lookup"><span data-stu-id="d5ab0-147">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="d5ab0-148">此 RMS 密钥共享位置是为购买了 Office 365 for 政府 sku 的客户预留的。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-148">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. <span data-ttu-id="d5ab0-149">通过运行[get-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet 配置键共享位置, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="d5ab0-149">Configure the key-sharing location by running the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet as follows:</span></span> 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    <span data-ttu-id="d5ab0-150">例如, 如果您的组织位于北美, 若要配置关键共享位置, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="d5ab0-150">For example, to configure the key sharing location if your organization is located in North America:</span></span>
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. <span data-ttu-id="d5ab0-151">使用-RMSOnline 开关运行[import-rmstrustedpublishingdomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet, 以从 Azure 权限管理导入 TPD:</span><span class="sxs-lookup"><span data-stu-id="d5ab0-151">Run the [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    <span data-ttu-id="d5ab0-152">其中, *TPDName*是要用于 TPD 的名称。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-152">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="d5ab0-153">例如, "Contoso 北方美洲 TPD"。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-153">For example, "Contoso North American TPD".</span></span> 
    
5. <span data-ttu-id="d5ab0-154">若要验证您是否已成功将 Office 365 组织配置为使用 Azure 权限管理服务, 请运行[get-irmconfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet 和-RMSOnline 开关, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="d5ab0-154">To verify that you successfully configured your Office 365 organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet with the -RMSOnline switch as follows:</span></span> 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    <span data-ttu-id="d5ab0-155">此外, 此 cmdlet 还检查与 Azure 权限管理服务的连接, 下载 TPD, 并检查其有效性。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-155">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>
    
6. <span data-ttu-id="d5ab0-156">运行[get-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet, 如下所示, 以禁用 web 和 outlook 上的 outlook 中提供的 Azure 权限管理模板:</span><span class="sxs-lookup"><span data-stu-id="d5ab0-156">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. <span data-ttu-id="d5ab0-157">运行[get-irmconfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet, 如下所示, 为您的基于云的电子邮件组织启用 azure 权限管理, 并将其配置为使用 azure 权限管理 for Office 365 邮件加密:</span><span class="sxs-lookup"><span data-stu-id="d5ab0-157">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span> 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. <span data-ttu-id="d5ab0-158">若要验证您是否已成功导入 TPD 并启用 azure 权限管理, 请使用 get-irmconfiguration cmdlet 测试 Azure 权限管理功能。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-158">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="d5ab0-159">有关详细信息，请参阅 [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx) 中的"示例 1"。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-159">For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span></span>
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="d5ab0-160">我已将早期版本的 OME 设置为使用 Active Directory 权限管理, 而不是 Azure 信息保护, 我该怎么办？</span><span class="sxs-lookup"><span data-stu-id="d5ab0-160">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="d5ab0-161"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="d5ab0-161"></span></span>

<span data-ttu-id="d5ab0-162">您可以继续使用现有的 Office 365 邮件加密邮件流规则与 Active Directory 权限管理, 但不能配置或使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-162">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="d5ab0-163">而是需要迁移到 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-163">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="d5ab0-164">有关迁移和组织的这种方法的信息, 请参阅[从 AD RMS 迁移到 Azure 信息保护](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-164">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="d5ab0-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d5ab0-165">Next steps</span></span>
<span data-ttu-id="d5ab0-166"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="d5ab0-166"></span></span>

<span data-ttu-id="d5ab0-167">完成 Azure 权限管理安装程序后, 如果要启用新的 OME 功能, 请参阅[设置基于 Azure 信息保护基础构建的新 Office 365 邮件加密功能。](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span><span class="sxs-lookup"><span data-stu-id="d5ab0-167">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span></span>
  
<span data-ttu-id="d5ab0-168">将组织设置为使用新的 OME 功能之后, 您就可以[定义邮件流规则, 以使用新的 OME 功能保护电子](define-mail-flow-rules-to-encrypt-email.md)邮件。</span><span class="sxs-lookup"><span data-stu-id="d5ab0-168">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d5ab0-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="d5ab0-169">Related topics</span></span>
<span data-ttu-id="d5ab0-170"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="d5ab0-170"></span></span>

[<span data-ttu-id="d5ab0-171">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="d5ab0-171">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="d5ab0-172">有关 Office 365 加密的技术参考详情</span><span class="sxs-lookup"><span data-stu-id="d5ab0-172">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="d5ab0-173">什么是 Azure 权限管理？</span><span class="sxs-lookup"><span data-stu-id="d5ab0-173">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  


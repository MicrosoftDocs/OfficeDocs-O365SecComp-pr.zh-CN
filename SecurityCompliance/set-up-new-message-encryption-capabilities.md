---
title: 设置全新的 Office 365 邮件加密功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 新的 Office 365 邮件加密功能基于 Azure 信息保护构建, 贵组织可以将受保护的电子邮件通信与组织内部和外部的人员结合使用。 新的 OME 功能适用于其他 Office 365 组织、Outlook.com、Gmail 和其他电子邮件服务。
ms.openlocfilehash: 415e598a28033271b115aff639fb1ddd7a6345af
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156504"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="79db4-104">设置全新的 Office 365 邮件加密功能</span><span class="sxs-lookup"><span data-stu-id="79db4-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="79db4-105">新的 Office 365 邮件加密 (OME) 功能允许组织与任何设备上的任何人共享受保护的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="79db4-105">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="79db4-106">用户可以使用 Outlook.com、Gmail 和其他电子邮件服务与其他 Office 365 组织和非 Office 365 客户交换受保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="79db4-106">Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

||
|:-----|
|<span data-ttu-id="79db4-107">本文是有关 Office 365 邮件加密的更多系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="79db4-107">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="79db4-108">本文适用于管理员和 IT 专业人员。</span><span class="sxs-lookup"><span data-stu-id="79db4-108">This article is intended for administrators and IT Pros.</span></span> <span data-ttu-id="79db4-109">如果只是查找有关发送或接收加密邮件的信息, 请参阅[Office 365 邮件加密 (OME)](ome.md)中的文章列表, 并找到最符合您的需求的文章。</span><span class="sxs-lookup"><span data-stu-id="79db4-109">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

<span data-ttu-id="79db4-110">请按照下面的步骤操作, 以确保新的 OME 功能在 Office 365 组织中可用。</span><span class="sxs-lookup"><span data-stu-id="79db4-110">Follow the steps below to ensure that the New OME capabilities are available in your Office 365 organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="79db4-111">验证 Azure 权限管理是否处于活动状态</span><span class="sxs-lookup"><span data-stu-id="79db4-111">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="79db4-112">新的 OME 功能利用[Azure 权限管理服务 (AZURE RMS)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)中的保护功能, 由[azure 信息保护](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)用来通过加密和访问控制来保护电子邮件和文档的技术。</span><span class="sxs-lookup"><span data-stu-id="79db4-112">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="79db4-113">使用新的 OME 功能的唯一先决条件是必须在组织的租户中激活[Azure 权限管理](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)。</span><span class="sxs-lookup"><span data-stu-id="79db4-113">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="79db4-114">如果是这样, Office 365 将自动激活新的 OME 功能, 无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="79db4-114">If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="79db4-115">对于最符合条件的计划, 也会自动激活 Azure RMS, 因此您可能不需要在这方面执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="79db4-115">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="79db4-116">有关详细信息, 请参阅[激活 Azure 权限管理](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="79db4-116">See [Activating Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="79db4-117">如果将 Active Directory 权限管理服务 (AD RMS) 与 Exchange Online 结合使用, 则需要先[迁移到 Azure 信息保护](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms), 然后才能使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="79db4-117">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="79db4-118">OME 与 AD RMS 不兼容。</span><span class="sxs-lookup"><span data-stu-id="79db4-118">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="79db4-119">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="79db4-119">For more information, see:</span></span>

- <span data-ttu-id="79db4-120">[使用新的 OME 功能需要什么订阅？](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)检查订阅计划是否包含 Azure 信息保护 (包括 Azure RMS 功能)。</span><span class="sxs-lookup"><span data-stu-id="79db4-120">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="79db4-121">有关购买符合条件的订阅的信息, 请参阅[Azure 信息保护](https://azure.microsoft.com/en-us/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="79db4-121">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="79db4-122">手动激活 Azure 权限管理</span><span class="sxs-lookup"><span data-stu-id="79db4-122">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="79db4-123">如果禁用了 Azure RMS, 或者如果由于任何原因未自动激活, 则可以在中手动激活:</span><span class="sxs-lookup"><span data-stu-id="79db4-123">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="79db4-124">**Office 365 管理中心**: 有关说明, 请参阅[如何从 Office 365 管理中心激活 Azure 权限管理](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="79db4-124">**Office 365 admin center**: See [How to activate Azure Rights Management from the Office 365 admin center](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="79db4-125">**Azure 门户**: 了解[如何从 Azure 门户激活 azure 权限管理](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure), 以获取相关说明。</span><span class="sxs-lookup"><span data-stu-id="79db4-125">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="79db4-126">配置 Azure 信息保护租户密钥的管理</span><span class="sxs-lookup"><span data-stu-id="79db4-126">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="79db4-127">这是一个可选步骤。</span><span class="sxs-lookup"><span data-stu-id="79db4-127">This is an optional step.</span></span> <span data-ttu-id="79db4-128">允许 Microsoft 管理 Azure 信息保护的根是默认设置, 为大多数 Office 365 租户提供建议的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="79db4-128">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants.</span></span> <span data-ttu-id="79db4-129">如果是这种情况, 则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="79db4-129">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="79db4-130">有许多原因 (例如合规性要求), 可能需要您生成和管理自己的根密钥 (也称为 "引入自己的密钥 (BYOK)")。</span><span class="sxs-lookup"><span data-stu-id="79db4-130">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="79db4-131">如果是这种情况, 建议您在设置新的 OME 功能之前完成所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="79db4-131">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="79db4-132">有关详细[信息, 请参阅规划和实现 Azure 信息保护租户密钥](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="79db4-132">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="79db4-133">在 Exchange Online PowerShell 中验证新的 OME 配置</span><span class="sxs-lookup"><span data-stu-id="79db4-133">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="79db4-134">您可以验证您的 Office 365 租户是否已正确配置为使用[Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)中的新 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="79db4-134">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="79db4-135">使用 Office 365 租户中具有全局管理员权限的帐户[连接到 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="79db4-135">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="79db4-136">运行 Get-irmconfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="79db4-136">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="79db4-137">您应该会看到 AzureRMSLicensingEnabled 参数的值为 $True, 这表示 OME 是在租户中配置的。</span><span class="sxs-lookup"><span data-stu-id="79db4-137">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="79db4-138">如果不是, 请使用 Get-irmconfiguration 将 AzureRMSLicensingEnabled 的值设置为 $True 以启用 OME。</span><span class="sxs-lookup"><span data-stu-id="79db4-138">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="79db4-139">使用以下语法运行 Get-irmconfiguration cmdlet:</span><span class="sxs-lookup"><span data-stu-id="79db4-139">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="79db4-140">**示例**：</span><span class="sxs-lookup"><span data-stu-id="79db4-140">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="79db4-141">提供发件人电子邮件是可选的, 但强制系统执行其他检查。</span><span class="sxs-lookup"><span data-stu-id="79db4-141">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="79db4-142">使用 Office 365 租户中任何用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="79db4-142">Use the email address of any user in your Office 365 tenant.</span></span>

     <span data-ttu-id="79db4-143">您的结果应类似于:</span><span class="sxs-lookup"><span data-stu-id="79db4-143">Your results should be similar to:</span></span>

     ```text
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

   - <span data-ttu-id="79db4-144">你的 Office 365 组织名称将替换*Contoso*。</span><span class="sxs-lookup"><span data-stu-id="79db4-144">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="79db4-145">默认的模板名称可能与上面显示的不同。</span><span class="sxs-lookup"><span data-stu-id="79db4-145">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="79db4-146">有关详细[信息, 请参阅配置和管理用于 Azure 信息保护的模板](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="79db4-146">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="79db4-147">运行移除-PSSession cmdlet 以断开与 Rights Management service 的连接。</span><span class="sxs-lookup"><span data-stu-id="79db4-147">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="79db4-148">后续步骤: 定义邮件流规则以使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="79db4-148">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="79db4-149">如果以前配置的邮件流规则用于在 Office 365 组织中对电子邮件进行加密, 则需要更新现有规则以使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="79db4-149">If there are previously configured mail flow rules to encrypt email in your Office 365 organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="79db4-150">对于新的部署, 您需要创建新的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="79db4-150">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="79db4-151">如果不更新现有的邮件流规则, 则用户将继续接收使用以前的 HTML 附件格式的加密邮件, 而不是新的无缝 OME 体验。</span><span class="sxs-lookup"><span data-stu-id="79db4-151">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="79db4-152">邮件流规则确定应对哪些条件加密电子邮件, 以及删除该加密的条件。</span><span class="sxs-lookup"><span data-stu-id="79db4-152">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="79db4-153">为规则设置操作时, 与规则条件匹配的任何邮件在发送时都将进行加密。</span><span class="sxs-lookup"><span data-stu-id="79db4-153">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="79db4-154">有关为 OME 创建邮件流规则的步骤, 请参阅在[Office 365 中定义用于加密电子邮件的邮件流规则](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="79db4-154">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="79db4-155">若要更新现有规则以使用新的 OME 功能, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="79db4-155">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="79db4-156">在 Office 365 管理中心, 转到**管理中心中心 _GT_ Exchange**。</span><span class="sxs-lookup"><span data-stu-id="79db4-156">In the Office 365 admin center, go to **Admin centers > Exchange**.</span></span>
2. <span data-ttu-id="79db4-157">在 Exchange 管理中心中, 转到 "**邮件流" _GT_ Rules**。</span><span class="sxs-lookup"><span data-stu-id="79db4-157">In the Exchange admin center, go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="79db4-158">对于每个规则, 请**执行以下**操作:</span><span class="sxs-lookup"><span data-stu-id="79db4-158">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="79db4-159">选择 **"修改邮件安全性"**。</span><span class="sxs-lookup"><span data-stu-id="79db4-159">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="79db4-160">选择 "**应用 Office 365 邮件加密和权限保护**"。</span><span class="sxs-lookup"><span data-stu-id="79db4-160">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="79db4-161">从列表中选择一个 RMS 模板。</span><span class="sxs-lookup"><span data-stu-id="79db4-161">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="79db4-162">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="79db4-162">Select **Save**.</span></span>
    - <span data-ttu-id="79db4-163">选择“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="79db4-163">Select **OK**.</span></span>

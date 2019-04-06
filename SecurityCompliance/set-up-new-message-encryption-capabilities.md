---
title: 设置全新的 Office 365 邮件加密功能
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: 新的 Office 365 邮件加密功能基于 Azure 信息保护构建, 贵组织可以将受保护的电子邮件通信与组织内部和外部的人员结合使用。 新的 OME 功能适用于其他 Office 365 组织、Outlook.com、Gmail 和其他电子邮件服务。
ms.openlocfilehash: fd237e537aa1ff961d2d975b3b30f4a51744ba7c
ms.sourcegitcommit: e24f70699021c4f4ba56508ad0afb6f65010c357
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2019
ms.locfileid: "31479648"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="f81f8-104">设置全新的 Office 365 邮件加密功能</span><span class="sxs-lookup"><span data-stu-id="f81f8-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="f81f8-105">新的 Office 365 邮件加密 (OME) 功能允许组织与任何设备上的任何人共享受保护的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f81f8-105">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="f81f8-106">用户可以使用 Outlook.com、Gmail 和其他电子邮件服务与其他 Office 365 组织和非 Office 365 客户交换受保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="f81f8-106">Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>


>[!NOTE]
><span data-ttu-id="f81f8-107">本文适用于管理员和 IT 专业人员。</span><span class="sxs-lookup"><span data-stu-id="f81f8-107">This article is intended for administrators and IT professionals.</span></span> <span data-ttu-id="f81f8-108">如果您是最终用户, 请参阅适用解决方案的[Office 365 邮件加密 (OME)](ome.md)中的文章列表。</span><span class="sxs-lookup"><span data-stu-id="f81f8-108">If you're an end-user, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) for appropriate solutions.</span></span>

<span data-ttu-id="f81f8-109">请按照下面的步骤操作, 以确保新的 OME 功能在 Office 365 租户中可用。</span><span class="sxs-lookup"><span data-stu-id="f81f8-109">Follow the steps below to ensure that the New OME capabilities are available in your Office 365 tenant.</span></span>

## <a name="verify-azure-rights-management-arm-is-active"></a><span data-ttu-id="f81f8-110">验证 Azure 权限管理 (ARM) 是否处于活动状态</span><span class="sxs-lookup"><span data-stu-id="f81f8-110">Verify Azure Rights Management (ARM) is active</span></span>

>[!NOTE]
><span data-ttu-id="f81f8-111">新的 OME 功能利用[azure 信息保护](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)中的保护功能, 即[azure 权限管理 (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)使用的技术。</span><span class="sxs-lookup"><span data-stu-id="f81f8-111">The new OME capabilities leverage the protection features in [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), the technology used by [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms).</span></span>

<span data-ttu-id="f81f8-112">使用新的 OME 功能的唯一先决条件是必须在 Office 365 租户中激活[Azure 权限管理 (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) 。</span><span class="sxs-lookup"><span data-stu-id="f81f8-112">The only prerequisite for using the new OME capabilities is that [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) must be activated in your Office 365 tenant.</span></span> <span data-ttu-id="f81f8-113">如果是这样, Office 365 将自动激活新的 OME 功能, 无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="f81f8-113">If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="f81f8-114">还会自动为最符合条件的计划激活 ARM, 因此您可能不需要在这方面执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="f81f8-114">ARM is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="f81f8-115">有关详细信息, 请参阅[激活 Azure 权限管理](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="f81f8-115">See [Activating Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) for more.</span></span>

>[!IMPORTANT]
><span data-ttu-id="f81f8-116">如果将 Active Directory 权限管理服务 (AD RMS) 与 Exchange Online 结合使用, 则需要先[迁移到 Azure 信息保护](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms), 然后才能使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="f81f8-116">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="f81f8-117">AD RMS 与 ARM 不兼容。</span><span class="sxs-lookup"><span data-stu-id="f81f8-117">AD RMS is not compatible with ARM.</span></span>  

<span data-ttu-id="f81f8-118">有关详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="f81f8-118">For more, see:</span></span>

- <span data-ttu-id="f81f8-119">[使用新的 OME 功能需要什么订阅？](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)检查订阅计划是否包含 Azure 信息保护 (包括 ARM)。</span><span class="sxs-lookup"><span data-stu-id="f81f8-119">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes ARM).</span></span>
- <span data-ttu-id="f81f8-120">有关购买符合条件的订阅的信息, 请参阅[Azure 信息保护](https://azure.microsoft.com/en-us/services/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="f81f8-120">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-arm"></a><span data-ttu-id="f81f8-121">手动激活 ARM</span><span class="sxs-lookup"><span data-stu-id="f81f8-121">Manually activating ARM</span></span>

<span data-ttu-id="f81f8-122">如果禁用了 ARM, 或者如果由于某种原因未自动激活, 则可以在中手动激活:</span><span class="sxs-lookup"><span data-stu-id="f81f8-122">If you disabled ARM, or if it was not automatically activated for any reason, you can activated it manually in the:</span></span>

- <span data-ttu-id="f81f8-123">**Office 365 管理中心**: 有关说明, 请参阅[如何从 Office 365 管理中心激活 Azure 权限管理](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="f81f8-123">**Office 365 admin center**: See [How to activate Azure Rights Management from the Office 365 admin center](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="f81f8-124">**Azure 门户**: 了解[如何从 azure 门户激活 azure 权限管理](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure), 以获取相关说明。</span><span class="sxs-lookup"><span data-stu-id="f81f8-124">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="f81f8-125">配置 Azure 信息保护租户密钥的管理</span><span class="sxs-lookup"><span data-stu-id="f81f8-125">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="f81f8-126">这是一个可选步骤。</span><span class="sxs-lookup"><span data-stu-id="f81f8-126">This is an optional step.</span></span> <span data-ttu-id="f81f8-127">允许 Microsoft 管理 Azure 信息保护的根是默认设置, 为大多数 Office 365 租户提供建议的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="f81f8-127">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants.</span></span> <span data-ttu-id="f81f8-128">如果是这种情况, 则无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="f81f8-128">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="f81f8-129">有许多原因 (例如合规性要求), 可能需要您生成和管理自己的根密钥 (也称为 "引入自己的密钥 (BYOK)")。</span><span class="sxs-lookup"><span data-stu-id="f81f8-129">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="f81f8-130">如果是这种情况, 建议您在设置新的 OME 功能之前完成所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="f81f8-130">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="f81f8-131">有关详细[信息, 请参阅规划和实现 Azure 信息保护租户密钥](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="f81f8-131">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="f81f8-132">在 Exchange Online PowerShell 中验证新的 OME 配置</span><span class="sxs-lookup"><span data-stu-id="f81f8-132">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="f81f8-133">您可以验证您的 Office 365 租户是否已正确配置为使用[Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)中的新 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="f81f8-133">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="f81f8-134">使用 Office 365 租户中具有全局管理员权限的帐户[连接到 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="f81f8-134">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="f81f8-135">使用以下语法运行 get-irmconfiguration cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f81f8-135">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="f81f8-136">**示例**：</span><span class="sxs-lookup"><span data-stu-id="f81f8-136">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="f81f8-137">提供发件人电子邮件是可选的, 但强制系统执行其他检查。</span><span class="sxs-lookup"><span data-stu-id="f81f8-137">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="f81f8-138">使用 Office 365 租户中任何用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f81f8-138">Use the email address of any user in your Office 365 tenant.</span></span> 

     <span data-ttu-id="f81f8-139">您的结果应类似于:</span><span class="sxs-lookup"><span data-stu-id="f81f8-139">Your results should be similar to:</span></span>

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

   - <span data-ttu-id="f81f8-140">你的 Office 365 组织名称将替换*Contoso*。</span><span class="sxs-lookup"><span data-stu-id="f81f8-140">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="f81f8-141">默认的模板名称可能与上面显示的不同。</span><span class="sxs-lookup"><span data-stu-id="f81f8-141">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="f81f8-142">有关详细[信息, 请参阅配置和管理用于 Azure 信息保护的模板](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="f81f8-142">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) for more.</span></span>

3. <span data-ttu-id="f81f8-143">运行移除-PSSession cmdlet 以断开与 Rights Management service 的连接。</span><span class="sxs-lookup"><span data-stu-id="f81f8-143">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="update-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="f81f8-144">将邮件流规则更新为使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="f81f8-144">Update mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="f81f8-145">如果以前配置的邮件流规则用于在 Office 365 租户中[对电子邮件进行加密](define-mail-flow-rules-to-encrypt-email.md), 则需要更新这些现有的规则, 以使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="f81f8-145">If there are previously configured [mail flow rules to encrypt email](define-mail-flow-rules-to-encrypt-email.md) in your Office 365 tenant, you need to update these existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="f81f8-146">对于新的部署, 此阶段不需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="f81f8-146">For new deployments, this step is unnecessary at this stage.</span></span>   

>[!Note]
><span data-ttu-id="f81f8-147">邮件流规则定义对电子邮件进行加密的条件, 以及应删除加密的条件。</span><span class="sxs-lookup"><span data-stu-id="f81f8-147">Mail flow rules define the conditions under which email messages are encrypted, and when encryption should be removed.</span></span> <span data-ttu-id="f81f8-148">有关详细信息, 请参阅[定义邮件流规则, 以对 Office 365 中的电子邮件进行加密](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="f81f8-148">See [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md) for more.</span></span>

<span data-ttu-id="f81f8-149">若要更新现有规则以使用新的 OME 功能, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="f81f8-149">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="f81f8-150">在 Office 365 管理中心, 转到**管理中心中心 > Exchange**。</span><span class="sxs-lookup"><span data-stu-id="f81f8-150">In the Office 365 admin center, go to **Admin centers > Exchange**.</span></span>

2. <span data-ttu-id="f81f8-151">在 Exchange 管理中心中, 转到 "**邮件流" > Rules**。</span><span class="sxs-lookup"><span data-stu-id="f81f8-151">In the Exchange admin center, go to **Mail flow > Rules**.</span></span> 
3. <span data-ttu-id="f81f8-152">对于每个规则, 请**执行以下**操作:</span><span class="sxs-lookup"><span data-stu-id="f81f8-152">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="f81f8-153">选择 **"修改邮件安全性"**。</span><span class="sxs-lookup"><span data-stu-id="f81f8-153">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="f81f8-154">选择 "**应用 Office 365 邮件加密和权限保护**"。</span><span class="sxs-lookup"><span data-stu-id="f81f8-154">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="f81f8-155">从列表中选择一个 RMS 模板。</span><span class="sxs-lookup"><span data-stu-id="f81f8-155">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="f81f8-156">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f81f8-156">Select **Save**.</span></span>
    - <span data-ttu-id="f81f8-157">选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="f81f8-157">Select **OK**.</span></span>
  
>[!IMPORTANT]
><span data-ttu-id="f81f8-158">如果不更新现有的邮件流规则, 则用户将继续接收使用以前的 HTML 附件格式的加密邮件, 而不是新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="f81f8-158">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new OME capabilities.</span></span>

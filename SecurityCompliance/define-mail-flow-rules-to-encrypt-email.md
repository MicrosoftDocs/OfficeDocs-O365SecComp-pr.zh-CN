---
title: 定义邮件流规则来加密 Office 365 中的电子邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: 管理员可以了解到创建邮件流规则 （也称作传输规则） 进行加密和解密邮件使用 Office 365 邮件加密 (OME)。
ms.openlocfilehash: 35867d45bb8ad5cb8de2fa1aa0c870ee9a66fe5d
ms.sourcegitcommit: 8c5a88433cff23c59b436260808cf3d91b06fdef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "27194673"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="5d3ce-103">定义邮件流规则来加密 Office 365 中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="5d3ce-103">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="5d3ce-p101">作为 Office 365 全局管理员，您可以创建邮件流规则 （也称作传输规则） 来帮助保护发送和接收的电子邮件。您可以设置来加密任何传出电子邮件和加密的邮件来自您组织内从或从组织发出的加密邮件答复中删除加密的规则。您可以使用 Exchange 管理中心 (EAC) 或 Exchange Online PowerShell 中创建这些规则。除了整体加密规则，您可以启用或禁用最终用户的单个邮件加密选项。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p101">As an Office 365 global administrator, you can create mail flow rules (also known as transport rules) to help protect email messages you send and receive. You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization. You can use the Exchange admin center (EAC) or Exchange Online PowerShell to create these rules. In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>

<span data-ttu-id="5d3ce-p102">如果您最近迁移从 AD RMS 到 Azure 信息保护，您将需要查看您现有的邮件流规则，以确保它们继续在新环境中工作。此外，如果您想要通过 Azure 信息保护给您充分利用可用的新 Office 365 邮件加密 (OME) 功能，您需要更新现有的邮件流规则。否则，您的用户将继续接收加密电子邮件，而不是新的、 无缝 OME 体验使用以前的 HTML 附件格式。如果您尚未尚未设置 OME，信息，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p102">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment. Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules. Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience. If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md) for information.</span></span>

<span data-ttu-id="5d3ce-p103">有关组件构成邮件流规则和如何邮件流规则工作的信息，请参阅[Exchange Online 中的邮件流规则 （传输规则）](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。有关邮件流规则与 Azure 信息保护的工作方式的其他信息，请参阅[Azure 信息保护标签配置 Exchange Online 邮件流规则](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p103">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d3ce-p104">对于 Exchange 的混合环境，内部部署用户可以发送电子邮件路由通过 Exchange Online 时，才使用 OME 的加密的邮件。若要配置 OME 混合 Exchange 环境中，您需要[配置混合使用混合配置向导](https://docs.microsoft.com/Exchange/exchange-hybrid)的第一个，然后[配置邮件流从电子邮件服务器到 Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。一次已配置邮件流过 Office 365，然后您也可以通过使用本指南为 OME 配置邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p104">For hybrid Exchange environments, on-premises users can send encrypted mail using OME only if email is routed through Exchange Online. To configure OME in a hybrid Exchange environment, you need to first [configure hybrid using the Hybrid Configuration wizard](https://docs.microsoft.com/Exchange/exchange-hybrid) and then [configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). Once you've configured mail to flow through Office 365, then you can configure mail flow rules for OME by using this guidance.</span></span>

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="5d3ce-117">创建邮件流规则进行加密的新功能，OME 与电子邮件</span><span class="sxs-lookup"><span data-stu-id="5d3ce-117">Create mail flow rules to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="5d3ce-118">您可以定义使用 EAC 触发新 OME 功能的邮件加密的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-118">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="5d3ce-119">使用 EAC 创建加密电子邮件与新的 OME 功能的规则</span><span class="sxs-lookup"><span data-stu-id="5d3ce-119">Use the EAC to create a rule for encrypting email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="5d3ce-120">在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-120">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="5d3ce-121">选择**管理员**图块。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-121">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="5d3ce-122">在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-122">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="5d3ce-p105">在 EAC 中，转到**邮件流** \> **规则**和选择**新建**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p105">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="5d3ce-125">在**名称**框中，键入规则名称，如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-125">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="5d3ce-p106">在**以下情况应用此规则**中选择一个条件，并输入一个值，如有必要。例如，若要加密邮件转到 DrToniRamos@hotmail.com:</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p106">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="5d3ce-128">在**以下情况应用此规则**，请选择**收件人**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-128">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="5d3ce-129">从联系人列表中选择一个现有名称，或在**检查名称**框中键入新的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-129">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>
    
      - <span data-ttu-id="5d3ce-130">要选择一个现有名称，从列表中选择，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-130">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="5d3ce-131">若要输入新名称，在**检查名称**框中键入电子邮件地址，然后选择**检查名称** \> **确定**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-131">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="5d3ce-132">若要添加更多条件，选择**更多选项**然后选择**添加条件**并从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-132">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span>

   <span data-ttu-id="5d3ce-133">例如，仅当收件人位于组织外部，则应用规则，选择**添加条件**，然后选择**收件人是内部/外部** \> **组织外部** \> **确定**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-133">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="5d3ce-p107">若要使用的新的 OME 功能，**执行以下操作**，从加密选择**修改邮件安全性**，然后选择**应用 Office 365 邮件加密和权限保护**。从列表中选择的 RMS 模板，选择**保存**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p107">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>

   <span data-ttu-id="5d3ce-p108">模板的列表包含所有的默认模板和选项，以及您已创建的任何自定义模板使用 Office 365。如果列表为空，确保您已设置 Office 365 邮件加密的新功能与[设置新的 Office 365 邮件加密功能基于顶部 Azure 信息保护](set-up-new-message-encryption-capabilities.md)中所述。有关默认模板的信息，请参阅[配置和管理 Azure 信息保护模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关**不要转发**选项的信息，请参阅[不要转发的电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。有关**仅加密**选项的信息，请参阅[仅加密的电子邮件的选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p108">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="5d3ce-141">如果您希望指定另一项操作，可以选择**添加操作**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-141">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a><span data-ttu-id="5d3ce-142">使用 EAC 来更新现有的邮件流规则，以使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="5d3ce-142">Use the EAC to update an existing mail flow rule to use the new OME capabilities</span></span>

1. <span data-ttu-id="5d3ce-143">在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-143">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="5d3ce-144">选择**管理员**图块。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-144">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="5d3ce-145">在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-145">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="5d3ce-146">在 EAC 中，转到**邮件流** \> **规则**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-146">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

5. <span data-ttu-id="5d3ce-147">在邮件流规则列表中，选择您想要修改以使用新的 OME 功能，然后选择**编辑**的规则![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-147">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

6. <span data-ttu-id="5d3ce-p109">若要使用的新的 OME 功能，**执行以下操作**，从加密选择**修改邮件安全性**，然后选择**应用 Office 365 邮件加密和权限保护**。从列表中选择的 RMS 模板选择**保存**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p109">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>

   <span data-ttu-id="5d3ce-p110">模板的列表包含所有的默认模板和选项，以及您已创建的任何自定义模板使用 Office 365。如果列表为空，确保您已设置 Office 365 邮件加密的新功能与[设置新的 Office 365 邮件加密功能基于顶部 Azure 信息保护](set-up-new-message-encryption-capabilities.md)中所述。有关默认模板的信息，请参阅[配置和管理 Azure 信息保护模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关**不要转发**选项的信息，请参阅[不要转发的电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。有关**仅加密**选项的信息，请参阅[仅加密的电子邮件的选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p110">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="5d3ce-155">如果您希望指定另一项操作，可以选择**添加操作**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-155">You can choose **add action** if you want to specify another action.</span></span>

7. <span data-ttu-id="5d3ce-156">从**执行以下操作**列表中，删除分配给**修改邮件安全性**的任何操作\>**应用 OME 的早期版本**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-156">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>

8. <span data-ttu-id="5d3ce-157">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-157">Choose **Save**.</span></span>

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="5d3ce-158">创建邮件流规则为 Office 365 邮件加密没有的新功能</span><span class="sxs-lookup"><span data-stu-id="5d3ce-158">Create mail flow rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="5d3ce-p111">如果尚未没有移 Office 365 组织的新 OME 功能，可以使用这些任务定义为您的组织的邮件进行加密的邮件流规则。Microsoft 建议您进行规划，以将移动到新的 OME 功能只要很合理为您的组织。有关说明，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p111">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="5d3ce-162">使用 EAC 创建加密电子邮件不带新 OME 功能的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="5d3ce-162">Use the EAC to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="5d3ce-163">在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-163">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="5d3ce-164">选择**管理员**图块。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-164">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="5d3ce-165">在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-165">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="5d3ce-p112">在 EAC 中，转到**邮件流** \> **规则**和选择**新建**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange admin center 在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p112">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**. For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="5d3ce-168">在**名称**框中，键入规则名称，如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-168">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="5d3ce-p113">在**以下情况应用此规则**中选择一个条件，并输入一个值，如有必要。例如，若要加密邮件转到 DrToniRamos@hotmail.com:</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p113">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span> 

   1. <span data-ttu-id="5d3ce-171">在**以下情况应用此规则**，请选择**收件人**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-171">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="5d3ce-172">从联系人列表中选择一个现有名称，或在**检查名称**框中键入新的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-172">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="5d3ce-173">要选择一个现有名称，从列表中选择，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-173">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="5d3ce-174">若要输入新名称，在**检查名称**框中键入电子邮件地址，然后选择**检查名称** \> **确定**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-174">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="5d3ce-175">若要添加更多条件，选择**更多选项**，然后选择**添加条件**，从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-175">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span>

   <span data-ttu-id="5d3ce-176">例如，仅当收件人位于组织外部，则应用规则，选择**添加条件**，然后选择**收件人是内部/外部** \> **组织外部** \> **确定**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-176">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

  8. <span data-ttu-id="5d3ce-177">要加密在不使用新的 OME 功能中，**执行以下操作**，请选中**修改邮件安全性** \> **应用 OME 的早期版本**，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-177">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>

    <span data-ttu-id="5d3ce-p114">如果您收到一条错误，未启用 IRM 许可，然后尚未设置您的组织尚未 OME。如果您想要设置 OME 现在，您必须设置它以使用新的 OME 功能。有关信息，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。Microsoft 不再支持设置新部署的 OME 没有的新功能。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p114">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet. If you'd like to set up OME now, you must set it up to use the new OME capabilities. For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>

    <span data-ttu-id="5d3ce-182">如果您希望指定另一项操作，可以选择**添加操作**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-182">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="5d3ce-183">Exchange Online PowerShell 中用于创建加密电子邮件不带新 OME 功能的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="5d3ce-183">Use Exchange Online PowerShell to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="5d3ce-p115">连接到 Exchange Online PowerShell 中。有关详细信息，请参阅[Connect to Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p115">Connect to Exchange Online PowerShell. For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="5d3ce-186">使用**New-transportrule** cmdlet 创建规则，并将_ApplyOME_参数设置为`$true`。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-186">Create a rule by using the **New-TransportRule** cmdlet and set the _ApplyOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="5d3ce-187">此示例要求对所有电子邮件发送到 DrToniRamos@hotmail.com 必须进行都加密。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-187">This example requires that all email messages sent to DrToniRamos@hotmail.com must be encrypted.</span></span>

   ```
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   <span data-ttu-id="5d3ce-188">**注意**：</span><span class="sxs-lookup"><span data-stu-id="5d3ce-188">**Notes**:</span></span>

   - <span data-ttu-id="5d3ce-189">新规则的唯一名称是"灾难恢复 Toni Ramos 加密规则"。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-189">The unique name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>

   - <span data-ttu-id="5d3ce-p116">_SentTo_参数指定邮件的收件人 （由名称、 电子邮件地址、 可分辨的名称等标识。）。本示例中，收件人的电子邮件地址"DrToniRamos@hotmail.com"由标识。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p116">The _SentTo_ parameter specifies the message recipients (identified by name, email address, distinguished name, etc.). In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span>

   - <span data-ttu-id="5d3ce-p117">_SentToScope_参数指定的收件人的位置。本示例中，收件人的邮箱是 hotmail 中而不是 Office 365 组织的一部分，以便值`NotInOrganization`使用。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p117">The _SentToScope_ parameter specifies the location of the message recipients. In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the value `NotInOrganization` is used.</span></span>

   <span data-ttu-id="5d3ce-194">有关详细的语法和参数信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-194">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="5d3ce-195">从新 OME 功能不加密的电子邮件答复中删除加密</span><span class="sxs-lookup"><span data-stu-id="5d3ce-195">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="5d3ce-p118">当您的电子邮件用户发送加密的邮件时，可以使用加密的答复响应这些邮件的收件人。您可以创建邮件流规则自动删除从答复加密，所以您的组织中的电子邮件用户不需要登录到加密门户以查看它们。您可以使用 EAC 或 Windows PowerShell cmdlet 定义这些规则。如果您没有尚未使用的新 OME 功能，您可以仅解密之一从组织或组织内从发送邮件的答复邮件中发送的邮件。无法解密来自组织外部的加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p118">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies. You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them. You can use the EAC or Windows PowerShell cmdlets to define these rules. If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization. You cannot decrypt encrypted messages originating from outside of your organization.</span></span>

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="5d3ce-201">使用 EAC 创建从新 OME 功能不加密的电子邮件答复中删除加密的规则</span><span class="sxs-lookup"><span data-stu-id="5d3ce-201">Use the EAC to create a rule for removing encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="5d3ce-202">在 web 浏览器中，使用工作或学校帐户已被授予管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-202">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="5d3ce-203">选择**管理员**图块。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-203">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="5d3ce-204">在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-204">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="5d3ce-p119">在 EAC 中，转到**邮件流** \> **规则**和选择**新建**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange admin center 在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p119">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**. For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="5d3ce-207">在**名称**框中，键入该规则，如 Remove encryption from 传入邮件的名称。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-207">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>

6. <span data-ttu-id="5d3ce-208">在**以下情况应用此规则**选择应从邮件，如**收件人是位于**中删除加密的条件\>**组织内部**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-208">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>

7. <span data-ttu-id="5d3ce-209">在**执行以下操作**，选择**修改邮件安全性** \> **OME 的早期版本中删除**。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-209">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>

8. <span data-ttu-id="5d3ce-210">选择" **保存** "。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-210">Select **Save**.</span></span>

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="5d3ce-211">Exchange Online PowerShell 中用于创建从新 OME 功能不加密的电子邮件答复中删除加密的规则</span><span class="sxs-lookup"><span data-stu-id="5d3ce-211">Use Exchange Online PowerShell to create a rule to remove encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="5d3ce-p120">连接到 Exchange Online PowerShell 中。有关详细信息，请参阅[Connect to Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p120">Connect to Exchange Online PowerShell. For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="5d3ce-214">使用**New-transportrule** cmdlet 创建规则，并将_RemoveOME_参数设置为`$true`。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-214">Create a rule by using the **New-TransportRule** cmdlet and set the _RemoveOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="5d3ce-215">此示例从所有发送到 Office 365 组织中的收件人的邮件中删除加密。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-215">This example removes the encryption from all mail sent to recipients in the Office 365 organization.</span></span>

   ```
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   <span data-ttu-id="5d3ce-216">**注意**：</span><span class="sxs-lookup"><span data-stu-id="5d3ce-216">**Notes**:</span></span>

   - <span data-ttu-id="5d3ce-217">新规则的唯一名称为"Remove encryption from incoming mail"。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-217">The unique name of the new rule is "Remove encryption from incoming mail".</span></span>

   - <span data-ttu-id="5d3ce-p121">_SentToScope_参数指定的收件人的位置。在此示例中，值`InOrganization`使用了值，表示：</span><span class="sxs-lookup"><span data-stu-id="5d3ce-p121">The _SentToScope_ parameter specifies the location of the message recipients. In this example, the value `InOrganization` value is used, which indicates:</span></span> 

     - <span data-ttu-id="5d3ce-220">收件人的邮箱、 邮件用户、 组或组织中已启用邮件的公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-220">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization.</span></span>

       <span data-ttu-id="5d3ce-221">或</span><span class="sxs-lookup"><span data-stu-id="5d3ce-221">or</span></span>

     - <span data-ttu-id="5d3ce-222">收件人的电子邮件地址位于配置为权威域或中您的组织，_和_邮件已发送或接收通过经过身份验证连接的内部中继域的接受域。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-222">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain in your organization, _and_ the message was sent or received over an authenticated connection.</span></span>

<span data-ttu-id="5d3ce-223">有关详细的语法和参数信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)。</span><span class="sxs-lookup"><span data-stu-id="5d3ce-223">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5d3ce-224">相关主题</span><span class="sxs-lookup"><span data-stu-id="5d3ce-224">Related Topics</span></span>

[<span data-ttu-id="5d3ce-225">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="5d3ce-225">Encryption in Office 365</span></span>](encryption.md)

[<span data-ttu-id="5d3ce-226">设置新的 Office 365 邮件加密功能构建到 Azure 信息保护顶部</span><span class="sxs-lookup"><span data-stu-id="5d3ce-226">Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection</span></span>](set-up-new-message-encryption-capabilities.md)

[<span data-ttu-id="5d3ce-227">将品牌添加到加密邮件</span><span class="sxs-lookup"><span data-stu-id="5d3ce-227">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)

[<span data-ttu-id="5d3ce-228">Exchange Online 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="5d3ce-228">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[<span data-ttu-id="5d3ce-229">Exchange Online Protection 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="5d3ce-229">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)

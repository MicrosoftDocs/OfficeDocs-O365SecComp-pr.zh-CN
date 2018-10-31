---
title: 定义邮件流规则来加密 Office 365 中的电子邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: 作为 Office 365 全局管理员，您可以创建邮件流规则启用 Office 365 邮件加密 (OME)。可以对任何传出电子邮件进行加密，并从内部邮件或从组织发出的加密邮件答复中删除加密。
ms.openlocfilehash: e9c6874ce304d1af9da093c02cbc954c54dae8cc
ms.sourcegitcommit: c05076501dfe118e575998ecfc08ad69d13c8abc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25853087"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="826cd-104">定义邮件流规则来加密 Office 365 中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="826cd-104">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="826cd-p102">作为 Office 365 全局管理员，您可以创建邮件流规则，也称为传输规则，来帮助保护发送和接收的电子邮件。您可以设置来加密任何传出电子邮件和加密的邮件来自您组织内从或从组织发出的加密邮件答复中删除加密的规则。您可以使用 Exchange 管理中心 (EAC) 或 Exchange Online 的 Windows PowerShell cmdlet 创建这些规则。 除了整体加密规则，您可以启用或禁用最终用户的单个邮件加密选项。</span><span class="sxs-lookup"><span data-stu-id="826cd-p102">As an Office 365 global administrator, you can create mail flow rules, also known as transport rules, to help protect email messages you send and receive. You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization. You can use the Exchange admin center (EAC) or Windows PowerShell cmdlets for Exchange Online to create these rules.  In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>
  
<span data-ttu-id="826cd-p103">如果您最近迁移从 AD RMS 到 Azure 信息保护，您将需要查看您现有的邮件流规则，以确保它们继续在新环境中工作。此外，如果您想要通过 Azure 信息保护给您充分利用可用的新 Office 365 邮件加密 (OME) 功能，您需要更新现有的邮件流规则。否则，您的用户将继续接收加密电子邮件，而不是新的、 无缝 OME 体验使用以前的 HTML 附件格式。如果您尚未尚未设置 OME，信息，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="826cd-p103">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment. Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules. Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience. If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md) for information.</span></span> 
  
<span data-ttu-id="826cd-p104">有关组件构成邮件流规则和如何邮件流规则工作的信息，请参阅[Exchange Online 中的邮件流规则 （传输规则）](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)。有关邮件流规则与 Azure 信息保护的工作方式的其他信息，请参阅[Azure 信息保护标签配置 Exchange Online 邮件流规则](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。</span><span class="sxs-lookup"><span data-stu-id="826cd-p104">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx). For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>
  
## <a name="hybrid-exchange-environments-do-this-first"></a><span data-ttu-id="826cd-115">Exchange 的混合环境： 第一步</span><span class="sxs-lookup"><span data-stu-id="826cd-115">Hybrid Exchange environments: Do this first</span></span>
<span data-ttu-id="826cd-p105">内部部署用户可以发送加密的邮件使用 OME，如果您将通过 Exchange Online 电子邮件路由。若要执行此操作，您需要配置邮件流到流从电子邮件服务器到 Office 365。配置邮件流过 Office 365 后，您可以使用本文为 OME 进行邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="826cd-p105">On-premises users can send encrypted mail using OME if you route email through Exchange Online. In order to do this, you need to configure mail flow to flow from your email server to Office 365. Once you've configured mail to flow through Office 365, you can make mail flow rules for OME by using this article.</span></span>

<span data-ttu-id="826cd-p106">有关说明，请参阅[设置连接器路由 Office 365 和电子邮件服务器之间的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)。具体而言，完成中的步骤"第 2 部分： 配置邮件流从电子邮件服务器到 Office 365"。</span><span class="sxs-lookup"><span data-stu-id="826cd-p106">For instructions, see [Set up connectors to route mail between Office 365 and your own email servers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail). In particular, complete the steps in "Part 2: Configure mail to flow from your email server to Office 365".</span></span>

## <a name="create-a-mail-flow-rule-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="826cd-121">创建新 OME 功能的电子邮件加密的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="826cd-121">Create a mail flow rule to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="826cd-122">您可以定义使用 EAC 触发新 OME 功能的邮件加密的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="826cd-122">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>
  
### <a name="to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="826cd-123">若要创建新的 OME 功能的电子邮件加密使用 EAC 的规则</span><span class="sxs-lookup"><span data-stu-id="826cd-123">To create a rule for encrypting email messages with the new OME capabilities by using the EAC</span></span>

1. <span data-ttu-id="826cd-124">在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="826cd-124">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="826cd-125">选择**管理员**图块。</span><span class="sxs-lookup"><span data-stu-id="826cd-125">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="826cd-126">在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="826cd-126">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="826cd-p107">在 EAC 中，转到**邮件流** \> **规则** \> ![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)（**新**） \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="826cd-p107">In the EAC, go to **mail flow** \> **rules** \> ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) ( **New**) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx).</span></span>
    
5. <span data-ttu-id="826cd-129">在**名称**框中，键入规则名称，如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="826cd-129">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>
    
6. <span data-ttu-id="826cd-p108">在**以下情况应用此规则**中选择一个条件，并输入一个值，如有必要。例如，若要加密邮件转到 DrToniRamos@hotmail.com:</span><span class="sxs-lookup"><span data-stu-id="826cd-p108">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span> 
    
    1. <span data-ttu-id="826cd-132">在**以下情况应用此规则**，请选择**收件人**。</span><span class="sxs-lookup"><span data-stu-id="826cd-132">In **Apply this rule if**, select **the recipient is**.</span></span>
    
    2. <span data-ttu-id="826cd-133">从联系人列表中选择一个现有名称，或在**检查名称**框中键入新的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="826cd-133">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span> 
    
        <span data-ttu-id="826cd-134">要选择一个现有名称，从列表中选择，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="826cd-134">To select an existing name, select it from the list and then click **OK**.</span></span>
    
        <span data-ttu-id="826cd-135">若要输入新名称，在**检查名称**框中键入电子邮件地址，然后选择**检查名称** \> **确定**。</span><span class="sxs-lookup"><span data-stu-id="826cd-135">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>
    
7. <span data-ttu-id="826cd-136">若要添加更多条件，选择**更多选项**然后选择**添加条件**并从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="826cd-136">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span> 
    
    <span data-ttu-id="826cd-137">例如，仅当收件人位于组织外部，则应用规则，选择**添加条件**，然后选择**收件人是内部/外部** \> **组织外部** \> **确定**。</span><span class="sxs-lookup"><span data-stu-id="826cd-137">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>
    
8. <span data-ttu-id="826cd-p109">若要使用的新的 OME 功能，**执行以下操作**，从加密选择**修改邮件安全性**，然后选择**应用 Office 365 邮件加密和权限保护**。从列表中选择的 RMS 模板，选择**保存**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="826cd-p109">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
    
    <span data-ttu-id="826cd-p110">模板的列表包含所有的默认模板和选项，以及您已创建的任何自定义模板使用 Office 365。如果列表为空，确保您已设置 Office 365 邮件加密的新功能与[设置新的 Office 365 邮件加密功能基于顶部 Azure 信息保护](set-up-new-message-encryption-capabilities.md)中所述。有关默认模板的信息，请参阅[配置和管理 Azure 信息保护模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关**不要转发**选项的信息，请参阅[不要转发的电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。有关**仅加密**选项的信息，请参阅[仅加密的电子邮件的选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="826cd-p110">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>
    
    <span data-ttu-id="826cd-145">如果您希望指定另一项操作，可以选择**添加操作**。</span><span class="sxs-lookup"><span data-stu-id="826cd-145">You can choose **add action** if you want to specify another action.</span></span> 
    
### <a name="to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="826cd-146">更新现有邮件流规则使用 EAC 使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="826cd-146">To update an existing mail flow rule to use the new OME capabilities by using the EAC</span></span>

1. <span data-ttu-id="826cd-147">在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="826cd-147">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="826cd-148">选择**管理员**图块。</span><span class="sxs-lookup"><span data-stu-id="826cd-148">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="826cd-149">在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="826cd-149">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="826cd-150">在 EAC 中，转到**邮件流** \> **规则**。</span><span class="sxs-lookup"><span data-stu-id="826cd-150">In the EAC, go to **mail flow** \> **rules**.</span></span>
    
5. <span data-ttu-id="826cd-151">在邮件流规则列表中，选择您想要修改以使用新的 OME 功能，然后选择的规则![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)（**编辑**）。</span><span class="sxs-lookup"><span data-stu-id="826cd-151">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ( **Edit**).</span></span>
    
6. <span data-ttu-id="826cd-p111">若要使用的新的 OME 功能，**执行以下操作**，从加密选择**修改邮件安全性**，然后选择**应用 Office 365 邮件加密和权限保护**。从列表中选择的 RMS 模板选择**保存**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="826cd-p111">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>
    
    <span data-ttu-id="826cd-p112">模板的列表包含所有的默认模板和选项，以及您已创建的任何自定义模板使用 Office 365。如果列表为空，确保您已设置 Office 365 邮件加密的新功能与[设置新的 Office 365 邮件加密功能基于顶部 Azure 信息保护](set-up-new-message-encryption-capabilities.md)中所述。有关默认模板的信息，请参阅[配置和管理 Azure 信息保护模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关**不要转发**选项的信息，请参阅[不要转发的电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。有关**仅加密**选项的信息，请参阅[仅加密的电子邮件的选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="826cd-p112">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>
    
    <span data-ttu-id="826cd-159">如果您希望指定另一项操作，可以选择**添加操作**。</span><span class="sxs-lookup"><span data-stu-id="826cd-159">You can choose **add action** if you want to specify another action.</span></span> 
    
7. <span data-ttu-id="826cd-160">从**执行以下操作**列表中，删除分配给**修改邮件安全性**的任何操作\>**应用 OME 的早期版本**。</span><span class="sxs-lookup"><span data-stu-id="826cd-160">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>
    
8. <span data-ttu-id="826cd-161">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="826cd-161">Choose **Save**.</span></span>
    
## <a name="creating-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="826cd-162">为 Office 365 邮件加密创建规则，不带新功能</span><span class="sxs-lookup"><span data-stu-id="826cd-162">Creating rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="826cd-p113">如果尚未没有移 Office 365 组织的新 OME 功能，可以使用这些任务定义为您的组织的邮件进行加密的邮件流规则。Microsoft 建议您进行规划，以将移动到新的 OME 功能只要很合理为您的组织。有关说明，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="826cd-p113">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>
  
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="826cd-166">创建加密电子邮件的新功能，OME 不使用 EAC 的规则</span><span class="sxs-lookup"><span data-stu-id="826cd-166">To create a rule for encrypting email messages without the new OME capabilities by using the EAC</span></span>

1. <span data-ttu-id="826cd-167">在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="826cd-167">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="826cd-168">选择**管理员**图块。</span><span class="sxs-lookup"><span data-stu-id="826cd-168">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="826cd-169">在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="826cd-169">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="826cd-p114">在 EAC 中，转到**邮件流** \> **规则** \> **+** （**新**） \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="826cd-p114">In the EAC, go to **mail flow** \> **rules** \> **+** ( **New**) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx).</span></span>
    
5. <span data-ttu-id="826cd-172">在**名称**框中，键入规则名称，如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="826cd-172">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>
    
6. <span data-ttu-id="826cd-p115">在**以下情况应用此规则**中选择一个条件，并输入一个值，如有必要。例如，若要加密邮件转到 DrToniRamos@hotmail.com:</span><span class="sxs-lookup"><span data-stu-id="826cd-p115">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span> 
    
1. <span data-ttu-id="826cd-175">在**以下情况应用此规则**，请选择**收件人**。</span><span class="sxs-lookup"><span data-stu-id="826cd-175">In **Apply this rule if**, select **the recipient is**.</span></span>
    
2. <span data-ttu-id="826cd-176">从联系人列表中选择一个现有名称，或在**检查名称**框中键入新的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="826cd-176">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span> 
    
    <span data-ttu-id="826cd-177">要选择一个现有名称，从列表中选择，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="826cd-177">To select an existing name, select it from the list and then click **OK**.</span></span>
    
    <span data-ttu-id="826cd-178">若要输入新名称，在**检查名称**框中键入电子邮件地址，然后选择**检查名称** \> **确定**。</span><span class="sxs-lookup"><span data-stu-id="826cd-178">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>
    
7. <span data-ttu-id="826cd-179">若要添加更多条件，选择**更多选项**，然后选择**添加条件**，从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="826cd-179">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span> 
    
    <span data-ttu-id="826cd-180">例如，仅当收件人位于组织外部，则应用规则，选择**添加条件**，然后选择**收件人是内部/外部** \> **组织外部** \> **确定**。</span><span class="sxs-lookup"><span data-stu-id="826cd-180">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>
    
8. <span data-ttu-id="826cd-181">要加密在不使用新的 OME 功能中，**执行以下操作**，请选中**修改邮件安全性** \> **应用 OME 的早期版本**，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="826cd-181">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>
    
    <span data-ttu-id="826cd-p116">如果您收到一条错误，未启用 IRM 许可，然后尚未设置您的组织尚未 OME。如果您想要设置 OME 现在，您必须设置它以使用新的 OME 功能。有关信息，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。Microsoft 不再支持设置新部署的 OME 没有的新功能。</span><span class="sxs-lookup"><span data-stu-id="826cd-p116">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet. If you'd like to set up OME now, you must set it up to use the new OME capabilities. For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>
    
    <span data-ttu-id="826cd-186">如果您希望指定另一项操作，可以选择**添加操作**。</span><span class="sxs-lookup"><span data-stu-id="826cd-186">You can choose **add action** if you want to specify another action.</span></span> 
    
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a><span data-ttu-id="826cd-187">若要创建使用 Windows PowerShell 进行 Exchange Online 加密不带新 OME 功能的电子邮件的规则</span><span class="sxs-lookup"><span data-stu-id="826cd-187">To create a rule for encrypting email messages without the new OME capabilities by using Windows PowerShell for Exchange Online</span></span>

1. <span data-ttu-id="826cd-p117">在本地计算机上使用 Windows PowerShell 创建与 Exchange Online 的远程 PowerShell 会话。有关详细信息，请参阅[Connect to Exchange Online PowerShell 中](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="826cd-p117">Use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online. For more information, see [Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).</span></span>
    
2. <span data-ttu-id="826cd-190">使用**New-transportrule** cmdlet 定义规则，并将**ApplyOME**属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="826cd-190">Define a rule by using the **New-TransportRule** cmdlet and set the **ApplyOME** attribute to **true**.</span></span>
    
    <span data-ttu-id="826cd-191">例如，若要求必须加密往 DrToniRamos@hotmail.com 的所有电子邮件，请键入：</span><span class="sxs-lookup"><span data-stu-id="826cd-191">For example, to require that all email messages that are addressed to DrToniRamos@hotmail.com must be encrypted, type:</span></span>
    
     ```
     New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
     ```

    <span data-ttu-id="826cd-192">在此示例中：</span><span class="sxs-lookup"><span data-stu-id="826cd-192">In this example:</span></span>
    
  - <span data-ttu-id="826cd-193">新规则的名称为"灾难恢复 Toni Ramos 加密规则"。</span><span class="sxs-lookup"><span data-stu-id="826cd-193">The name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>
    
  - <span data-ttu-id="826cd-p118">**-SentTo**参数指定的收件人电子邮件中查找的条件。您可以使用任何值，该值唯一地标识收件人，如电子邮件地址、 名称、 可分辨的名称 (DN)、 等。本示例中，收件人的电子邮件地址"DrToniRamos@hotmail.com"由标识。</span><span class="sxs-lookup"><span data-stu-id="826cd-p118">The **-SentTo** parameter, specifies a condition that looks for recipients in email messages. You can use any value that uniquely identifies the recipient, such as an email address, name, distinguished name (DN), etc. In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span> 
    
  - <span data-ttu-id="826cd-p119">**-SentToScope**参数指定收件人的位置查找的条件。本示例中，收件人的邮箱位于 hotmail 并不是 Office 365 组织的一部分，以便使用"NotInOrganization"值。</span><span class="sxs-lookup"><span data-stu-id="826cd-p119">The **-SentToScope** parameter specifies a condition that looks for the location of recipients. In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the "NotInOrganization" value is used.</span></span> 
    
    <span data-ttu-id="826cd-198">您可以设置使用此 cmdlet 的邮件流规则条件的详细信息，请参阅[New-transportrule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="826cd-198">For more information about the conditions you can set on mail flow rules using this cmdlet, see [New-TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx).</span></span>
    
### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="826cd-199">从新 OME 功能不加密的电子邮件答复中删除加密</span><span class="sxs-lookup"><span data-stu-id="826cd-199">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="826cd-p120">当您的电子邮件用户发送加密的邮件时，可以使用加密的答复响应这些邮件的收件人。您可以创建邮件流规则自动删除从答复加密，所以您的组织中的电子邮件用户不需要登录到加密门户以查看它们。您可以使用 EAC 或 Windows PowerShell cmdlet 定义这些规则。如果您没有尚未使用的新 OME 功能，您可以仅解密之一从组织或组织内从发送邮件的答复邮件中发送的邮件。无法解密来自组织外部的加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="826cd-p120">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies. You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them. You can use the EAC or Windows PowerShell cmdlets to define these rules. If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization. You cannot decrypt encrypted messages originating from outside of your organization.</span></span>
  
#### <a name="to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="826cd-205">若要创建从新 OME 功能不使用 EAC 加密的电子邮件答复中删除加密的规则</span><span class="sxs-lookup"><span data-stu-id="826cd-205">To create a rule for removing encryption from email replies encrypted without the new OME capabilities by using the EAC</span></span>
<span data-ttu-id="826cd-206"><a name="DecryptruleEACNoNewOME"> </a></span><span class="sxs-lookup"><span data-stu-id="826cd-206"></span></span>

1. <span data-ttu-id="826cd-207">在 web 浏览器中，使用工作或学校帐户已被授予管理员权限，[登录到 Office 365](https://support.office.com/article/Sign-in-to-Office-or-Office-365-b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="826cd-207">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/Sign-in-to-Office-or-Office-365-b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="826cd-208">选择**管理员**图块。</span><span class="sxs-lookup"><span data-stu-id="826cd-208">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="826cd-209">在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="826cd-209">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="826cd-p121">在 EAC 中，转到**邮件流** \> **规则** \> **+** （**新**） \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/en-us/library/jj200743%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="826cd-p121">In the EAC, go to **mail flow** \> **rules** \> **+** ( **New**) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/en-us/library/jj200743%28v=exchg.150%29.aspx).</span></span>
    
5. <span data-ttu-id="826cd-212">在**名称**框中，键入该规则，如 Remove encryption from 传入邮件的名称。</span><span class="sxs-lookup"><span data-stu-id="826cd-212">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>
    
6. <span data-ttu-id="826cd-213">在**以下情况应用此规则**选择应从邮件，如**收件人是位于**中删除加密的条件\>**组织内部**。</span><span class="sxs-lookup"><span data-stu-id="826cd-213">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>
    
7. <span data-ttu-id="826cd-214">在**执行以下操作**，选择**修改邮件安全性** \> **OME 的早期版本中删除**。</span><span class="sxs-lookup"><span data-stu-id="826cd-214">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>
    
8. <span data-ttu-id="826cd-215">选择" **保存** "。</span><span class="sxs-lookup"><span data-stu-id="826cd-215">Select **Save**.</span></span>
    
#### <a name="to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a><span data-ttu-id="826cd-216">若要创建从 Exchange online 中使用 Windows PowerShell 的新功能，OME 不加密的电子邮件答复中删除加密的规则</span><span class="sxs-lookup"><span data-stu-id="826cd-216">To create a rule to remove encryption from email replies encrypted without the new OME capabilities by using Windows PowerShell for Exchange Online</span></span>
<span data-ttu-id="826cd-217"><a name="DecryptrulePShellNoNewOME"> </a></span><span class="sxs-lookup"><span data-stu-id="826cd-217"></span></span>

1. <span data-ttu-id="826cd-p122">在本地计算机上使用 Windows PowerShell 创建与 Exchange Online 的远程 PowerShell 会话。有关详细信息，请参阅[Connect to Exchange Online PowerShell 中](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="826cd-p122">Use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online. For more information, see [Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).</span></span>
    
2. <span data-ttu-id="826cd-220">使用**New-transportrule** cmdlet 定义规则，并将**RemoveOME**属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="826cd-220">Define a rule by using the **New-TransportRule** cmdlet and set the **RemoveOME** attribute to **true**.</span></span>
    
    <span data-ttu-id="826cd-221">例如，若要从所有发送到 Office 365 组织中的收件人的邮件中删除加密，请键入：</span><span class="sxs-lookup"><span data-stu-id="826cd-221">For example, to remove the encryption from all mail sent to recipients in your Office 365 organization, type:</span></span>
    
     ```
     New-TransportRule - Name "Remove encryption from incoming mail"     -SentToScope "InOrganization" -RemoveOME $true
     ```

    <span data-ttu-id="826cd-222">在此示例中：</span><span class="sxs-lookup"><span data-stu-id="826cd-222">In this example:</span></span>
    
  - <span data-ttu-id="826cd-223">新规则的名称为"Remove encryption from incoming mail"。</span><span class="sxs-lookup"><span data-stu-id="826cd-223">The name of the new rule is "Remove encryption from incoming mail".</span></span>
    
  - <span data-ttu-id="826cd-p123">**-SentToScope**参数指定收件人的位置查找的条件。本示例中，使用"InOrganization"值指示：</span><span class="sxs-lookup"><span data-stu-id="826cd-p123">The **-SentToScope** parameter specifies a condition that looks for the location of recipients. In this example, the "InOrganization" value is used which indicates that:</span></span> 
    
  - <span data-ttu-id="826cd-226">收件人是邮箱、 邮件用户、 组或组织中已启用邮件的公用文件夹或</span><span class="sxs-lookup"><span data-stu-id="826cd-226">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization, or</span></span>
    
  - <span data-ttu-id="826cd-227">收件人的电子邮件地址位于配置为权威域或内部中继域的接受的域中， 并且 通过经验证的连接发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="826cd-227">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain, and the message was sent or received over an authenticated connection.</span></span>
    
    <span data-ttu-id="826cd-228">您可以设置使用此 cmdlet 的邮件流规则条件的详细信息，请参阅[New-transportrule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="826cd-228">For more information about the conditions you can set on mail flow rules using this cmdlet, see [New-TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="826cd-229">相关主题</span><span class="sxs-lookup"><span data-stu-id="826cd-229">Related Topics</span></span>

[<span data-ttu-id="826cd-230">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="826cd-230">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="826cd-231">设置新的 Office 365 邮件加密功能构建到 Azure 信息保护顶部</span><span class="sxs-lookup"><span data-stu-id="826cd-231">Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection</span></span>](set-up-new-message-encryption-capabilities.md)
  
[<span data-ttu-id="826cd-232">将品牌添加到加密邮件</span><span class="sxs-lookup"><span data-stu-id="826cd-232">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)
  
[<span data-ttu-id="826cd-233">Exchange Online 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="826cd-233">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)
  
[<span data-ttu-id="826cd-234">Exchange Online Protection 中的邮件流规则（传输规则）</span><span class="sxs-lookup"><span data-stu-id="826cd-234">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
  


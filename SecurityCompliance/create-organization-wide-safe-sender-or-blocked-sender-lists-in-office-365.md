---
title: Create organization-wide safe sender or blocked sender lists in Office 365
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/8/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 如果您想要确保您收到邮件来自特定发件人，因为您信任它们和其邮件，则可以调整您允许在 Exchange 管理中心中的垃圾邮件筛选器策略中的列表。
ms.openlocfilehash: 1086a4a710432eb412ae9f08f204beda52aa5390
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027539"
---
# <a name="create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365"></a><span data-ttu-id="511f2-103">Create organization-wide safe sender or blocked sender lists in Office 365</span><span class="sxs-lookup"><span data-stu-id="511f2-103">Create organization-wide safe sender or blocked sender lists in Office 365</span></span>
  
<span data-ttu-id="511f2-p101">如果您想要确保您收到邮件来自特定发件人，因为您信任它们和其邮件，则可以调整您允许在**保护**Exchange 管理员中心 (EAC) 中的垃圾邮件筛选器策略中的列表\>**垃圾邮件筛选器**。了解详细信息此在[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。创建 Exchange 传输规则 works 像域或基于用户的垃圾邮件筛选器中允许列表是另一个选项。您可以阻止邮件太发送来自特定域或用户以类似方式。</span><span class="sxs-lookup"><span data-stu-id="511f2-p101">If you want to be sure that you receive mail from a particular sender, because you trust them and their messages, you can adjust your allow list in a spam filter policy in the Exchange admin center (EAC) at **Protection** \> **Spam filter**. Learn more about this at [Configure your spam filter policies](configure-your-spam-filter-policies.md). Another option would be create an Exchange transport rule that works like the domain or user-based allow list in the spam filter. You can block messages sent from a particular domain or user in a similar manner too.</span></span>
  
<span data-ttu-id="511f2-p102">传输规则会很有用在此情况下，如果您需要筛选的复杂的条件，如检查邮件头或附件的名称或您要添加复杂操作，如向邮件添加免责声明或应用时间段其中 rule 处于活动状态。但是，确保来自特定发件人或域的电子邮件绕过垃圾邮件筛选器的首选的方法是将它们添加到您的垃圾邮件筛选器策略。开始与此在 EAC 中，转到**保护** \> **垃圾邮件筛选器**。有关详细信息[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="511f2-p102">A transport rule would be useful in this situation if you need to filter for complex criteria such as checking message headers or the names of attachments or if you want to add complex actions such as adding a disclaimer to the message or applying a time period where the rule is active. However, the preferred method to make sure emails from a specific sender or domain bypass your spam filter is to add them to your spam filter policy. Get started with this in the EAC by going to **Protection** \> **Spam filter**. Learn more at [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="511f2-p103">基于域的列表中的传输规则不是一个 IP 地址基于列表，尽可能安全，因为可以造假域。此外，如果在阻止列表发送 IP 地址，它仍被阻止即使筛选为域或用户绕过了。这是因为传输规则在域或用户不会覆盖全局 IP 阻止列表。我们建议在大多数情况下使用的 IP 地址基于列表。若要创建的 IP 地址基于列表，可以在连接筛选器中使用的 IP 允许列表或 IP 阻止列表。从这些 IP 地址发送的任何邮件不会检查内容筛选器。有关如何通过将 IP 地址添加到 IP 允许列表或 IP 阻止列表配置连接筛选器策略的说明，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="511f2-p103">A domain-based list in a transport rule isn't as secure as an IP address-based list, because domains can be spoofed. Also, if the sending IP address is on a Block list, it will still be blocked even if filtering for the domain or user is being bypassed. This is because a transport rule on a domain or user does not override the global IP Block list. We recommend using an IP address-based list in most cases. To create an IP address-based list, you can use the IP Allow list or IP Block list in the connection filter. Any messages sent from these IP addresses aren't checked by the content filter. For instructions on how to configure the connection filter policy by adding IP addresses to the IP Allow list or IP Block list, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).</span></span> 
  
<span data-ttu-id="511f2-119">有关与传输规则相关的其他管理任务，请参阅[Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)。</span><span class="sxs-lookup"><span data-stu-id="511f2-119">For additional management tasks related to transport rules, see [Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).</span></span>
  
## <a name="use-the-eac-to-customize-a-block-or-allow-list-to-prevent-or-receive-email-from-a-domain-or-user"></a><span data-ttu-id="511f2-120">使用 EAC 以自定义阻止或允许列表来阻止或从域或用户接收电子邮件</span><span class="sxs-lookup"><span data-stu-id="511f2-120">Use the EAC to customize a block or allow list to prevent or receive email from a domain or user</span></span>
<span data-ttu-id="511f2-121"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="511f2-121"></span></span>

1. <span data-ttu-id="511f2-122">在 EAC 中，转到**保护** \> **垃圾邮件筛选器**。</span><span class="sxs-lookup"><span data-stu-id="511f2-122">In the EAC, go to **Protection** \> **Spam filter**.</span></span> 
    
2. <span data-ttu-id="511f2-123">在**常规**页上，执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="511f2-123">On the **general** page, do one of the following:</span></span> 
    
  - <span data-ttu-id="511f2-124">双击默认策略或现有的策略以便开始编辑它。</span><span class="sxs-lookup"><span data-stu-id="511f2-124">Double-click the default policy or an existing policy in order to start editing it.</span></span>
    
  - <span data-ttu-id="511f2-125">单击**新建**以创建新的自定义垃圾邮件筛选器策略可应用于用户、 组和您的组织中的域。</span><span class="sxs-lookup"><span data-stu-id="511f2-125">Click **New** in order to create a new custom spam-filter policy that can be applied to users, groups, and domains in your organization.</span></span> 
    
3. <span data-ttu-id="511f2-p104">在**允许列表**页上，您可以指定项，如发件人或域时，总是会发送到收件箱。垃圾邮件筛选器不处理电子邮件从这些条目。执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="511f2-p104">On the **Allow Lists** page, you can specify entries, such as senders or domains, that will always be delivered to the inbox. Email from these entries is not processed by the spam filter. Do the following:</span></span> 
    
  - <span data-ttu-id="511f2-p105">添加受信任的发件人与发件人允许列表。单击**添加**，然后在选择对话框中，添加您希望允许的发件人地址。您可以单独使用分号或新行的多个条目。单击确定以返回到**允许列表**页。</span><span class="sxs-lookup"><span data-stu-id="511f2-p105">Add trusted senders to the Sender allow list. Click **Add**, and then in the selection dialog box, add the sender addresses you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
  - <span data-ttu-id="511f2-p106">添加受信任的域到域的允许列表。单击**添加**，然后在选择对话框中，添加您希望允许的域。您可以单独使用分号或新行的多个条目。单击确定以返回到**允许列表**页。</span><span class="sxs-lookup"><span data-stu-id="511f2-p106">Add trusted domains to the Domain allow list. Click **Add**, and then in the selection dialog box, add the domains you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="511f2-137">如果您允许顶级域，很可能会将您不需要的电子邮件发送到收件箱。</span><span class="sxs-lookup"><span data-stu-id="511f2-137">If you allow top-level domains, it's likely that email you don't want will be delivered to an inbox.</span></span> 
  
4. <span data-ttu-id="511f2-p107">在**阻止列表**页上，您可以指定项，如发件人或域时，将始终标记为垃圾邮件。该服务将这些条目匹配的电子邮件上应用配置高可信度垃圾邮件操作。</span><span class="sxs-lookup"><span data-stu-id="511f2-p107">On the **Block Lists** page, you can specify entries, such as senders or domains, that will always be marked as spam. The service will apply the configured high confidence spam action on email that matches these entries.</span></span> 
    
  - <span data-ttu-id="511f2-p108">将不需要的发件人添加到阻止发件人列表中。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.png)，然后在选择对话框中，添加您想要阻止的发件人地址。您可以单独使用分号或新行的多个条目。单击**确定**以返回到**阻止列表**页上。</span><span class="sxs-lookup"><span data-stu-id="511f2-p108">Add unwanted senders to the Sender block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the sender addresses you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
  - <span data-ttu-id="511f2-p109">将不需要的域添加到阻止域列表中。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.png)，然后在选择对话框中，添加您想要阻止的域。您可以单独使用分号或新行的多个条目。单击**确定**以返回到**阻止列表**页上。</span><span class="sxs-lookup"><span data-stu-id="511f2-p109">Add unwanted domains to the Domain block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the domains you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="511f2-148">如果您阻止顶级域，很可能会将您需要的电子邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="511f2-148">If you block top-level domains, it's likely that email you want will be marked as spam.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin-creating-a-transport-rule"></a><span data-ttu-id="511f2-149">您需要知道您开始创建传输规则？</span><span class="sxs-lookup"><span data-stu-id="511f2-149">What do you need to know before you begin creating a transport rule?</span></span>
<span data-ttu-id="511f2-150"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="511f2-150"></span></span>

- <span data-ttu-id="511f2-151">估计完成时间：15 分钟</span><span class="sxs-lookup"><span data-stu-id="511f2-151">Estimated time to complete: 15 minutes</span></span>
    
- <span data-ttu-id="511f2-p110">您无需创建传输规则以绕过垃圾邮件筛选或将电子邮件标记为垃圾邮件的发件人或域。使用 Exchange Online Protection 块，并允许列表中而不是此传输规则的垃圾邮件策略，如果您只想要阻止或允许特定发件人或域并不附加任何额外的条件。了解详细信息此在[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="511f2-p110">You don't need to create a transport rule to bypass spam filtering or mark email as spam for a sender or domain. Use the Exchange Online Protection block and allow lists in a spam policy instead of this transport rule if you simply want to block or allow a specific sender or domain and not attach any extra conditions. Learn more about this at [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
- <span data-ttu-id="511f2-p111">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的"传输规则"条目。</span><span class="sxs-lookup"><span data-stu-id="511f2-p111">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="511f2-157">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="511f2-157">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="511f2-p112">遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="511f2-p112">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-the-eac-to-create-a-transport-rule-to-bypass-spam-filtering-for-a-domain-or-user"></a><span data-ttu-id="511f2-161">使用 EAC 创建传输规则以绕过域或用户的垃圾邮件筛选</span><span class="sxs-lookup"><span data-stu-id="511f2-161">Use the EAC to create a transport rule to bypass spam filtering for a domain or user</span></span>
<span data-ttu-id="511f2-162"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="511f2-162"></span></span>

1. <span data-ttu-id="511f2-p113">在 EAC 中，导航到**邮件流** \> **规则**。选择**添加**![添加图标](media/ITPro-EAC-AddIcon.png)，然后选择**绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="511f2-p113">In the EAC, navigate to **Mail flow** \> **Rules**. Choose **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) and then choose **Bypass spam filtering**.</span></span>
    
2. <span data-ttu-id="511f2-p114">为该规则指定一个名称。在**以下情况应用此规则**，选择**发件人**，然后选择以下条件之一:</span><span class="sxs-lookup"><span data-stu-id="511f2-p114">Give the rule a name. Under **Apply this rule if**, choose **The sender** and then select one of the following conditions:</span></span> 
    
  - <span data-ttu-id="511f2-p115">如果您想要指定域，则选择**域**。在**指定域**对话框中，输入您想要指定为安全，例如，contoso.com 的发件人的域。**添加**![添加图标](media/ITPro-EAC-AddIcon.png)以将其移到的短语列表。如果您想要添加其他域，并在完成时单击**确定**，请重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="511f2-p115">If you want to specify a domain, choose **domain is**. In the **Specify domain** dialog box, enter the domain of the sender you want to designate as safe, such as contoso.com. **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) to move it to the list of phrases. Repeat this step if you want to add additional domains, and click **OK** when you are finished.</span></span> 
    
  - <span data-ttu-id="511f2-p116">如果您想要指定用户，选择**此人**。在**选择成员**对话框中，从列表中添加用户或键入用户并单击**检查名称**。如果您想要添加其他用户，并在完成时单击**确定**，请重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="511f2-p116">If you want to specify a user, choose **is this person**. In the **Select members** dialog box, add the user from the list or type the user and click **Check names**. Repeat this step if you want to add additional users, and click **OK** when you are finished.</span></span> 
    
3. <span data-ttu-id="511f2-174">选择**停止处理其他规则**复选框以确保没有其他规则可以还原绕过操作</span><span class="sxs-lookup"><span data-stu-id="511f2-174">Select the **Stop processing more rules** check box to ensure that no other rule can reverse the bypass action</span></span> 
    
4. <span data-ttu-id="511f2-175">对于**邮件中的匹配发件人地址**选项中，选择**标头或信封**。</span><span class="sxs-lookup"><span data-stu-id="511f2-175">For the **Match sender address in message** option, select **Header or envelope**.</span></span>
    
5. <span data-ttu-id="511f2-p117">如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。建议在组织中实施规则之前，对规则测试一段时间。有关这些选择的详细信息，请参阅[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="511f2-p117">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period of time before enforcing it in your organization. For more information about these selections, see [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx).</span></span>
    
6. <span data-ttu-id="511f2-179">选择**保存**保存规则。</span><span class="sxs-lookup"><span data-stu-id="511f2-179">Choose **Save** to save the rule.</span></span> 
    
<span data-ttu-id="511f2-180">创建和强制执行规则后，将对您指定的域或用户绕过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="511f2-180">After you create and enforce the rule, spam filtering is bypassed for the domain or user you specified.</span></span>
  
## <a name="use-the-eac-to-create-a-transport-rule-that-blocks-messages-sent-from-a-domain-or-user"></a><span data-ttu-id="511f2-181">使用 EAC 创建传输规则阻止从某个域或用户发送的邮件</span><span class="sxs-lookup"><span data-stu-id="511f2-181">Use the EAC to create a transport rule that blocks messages sent from a domain or user</span></span>
<span data-ttu-id="511f2-182"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="511f2-182"></span></span>

1. <span data-ttu-id="511f2-p118">在 EAC 中，导航到**邮件流** \> **规则**。选择**添加**![添加图标](media/ITPro-EAC-AddIcon.png)，然后选择**创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="511f2-p118">In the EAC, navigate to **Mail flow** \> **Rules**. Choose **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) and then choose **Create a new rule**.</span></span>
    
2. <span data-ttu-id="511f2-185">为该规则指定一个名称，然后单击**更多选项**。</span><span class="sxs-lookup"><span data-stu-id="511f2-185">Give the rule a name and then click **More options**.</span></span> 
    
3. <span data-ttu-id="511f2-186">在**以下情况应用此规则**，选择**发件人**，然后选择以下条件之一:</span><span class="sxs-lookup"><span data-stu-id="511f2-186">Under **Apply this rule if**, choose **The sender** and then select one of the following conditions:</span></span> 
    
  - <span data-ttu-id="511f2-p119">如果您想要指定域，则选择**域**。在指定域对话框中，输入想要阻止邮件，例如 contoso.com 的发件人域。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.png)以将其移到的短语列表。如果您想要添加其他域，并在完成时单击**确定**，请重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="511f2-p119">If you want to specify a domain, choose **domain is**. In the Specify domain dialog box, enter the sender domain from which you want to block messages, such as contoso.com. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) to move it to the list of phrases. Repeat this step if you want to add additional domains, and click **OK** when you are finished.</span></span> 
    
  - <span data-ttu-id="511f2-p120">如果您想要指定用户，选择**此人**。在**选择成员**对话框中，从列表中添加用户或键入用户并单击**检查名称**。如果您想要添加其他用户，并在完成时单击**确定**，请重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="511f2-p120">If you want to specify a user, choose **is this person**. In the **Select members** dialog box, add the user from the list or type the user and click **Check names**. Repeat this step if you want to add additional users, and click **OK** when you are finished.</span></span> 
    
4. <span data-ttu-id="511f2-194">下**执行以下操作**，选择**阻止邮件**，然后单击一个如**删除不通知任何人的邮件**的其他选项。</span><span class="sxs-lookup"><span data-stu-id="511f2-194">Under **Do the following**, choose **Block the message** and then click one of the other options such as **Delete the message without notifying anyone**.</span></span>
    
5. <span data-ttu-id="511f2-195">单击**更多选项**，然后对于**邮件中的匹配发件人地址**选项中，选择**标头或信封**。</span><span class="sxs-lookup"><span data-stu-id="511f2-195">Click **More options**, and then for the **Match sender address in message** option, select **Header or envelope**.</span></span>
    
6. <span data-ttu-id="511f2-p121">如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。建议在组织中实施规则之前，对规则测试一段时间。有关这些选择的详细信息，请参阅[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="511f2-p121">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period of time before enforcing it in your organization. For more information about these selections, see [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx).</span></span>
    
7. <span data-ttu-id="511f2-199">选择**保存**保存规则。</span><span class="sxs-lookup"><span data-stu-id="511f2-199">Choose **Save** to save the rule.</span></span> 
    
<span data-ttu-id="511f2-200">创建和强制执行规则后，从您指定的域或用户发送的任何邮件都将被阻止。</span><span class="sxs-lookup"><span data-stu-id="511f2-200">After you create and enforce the rule, any messages sent from the domain or user you specify will be blocked.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="511f2-201">另请参阅</span><span class="sxs-lookup"><span data-stu-id="511f2-201">See also</span></span>
<span data-ttu-id="511f2-202"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="511f2-202"></span></span>

[<span data-ttu-id="511f2-203">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="511f2-203">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="511f2-204">使用传输规则来配置筛选批量电子邮件</span><span class="sxs-lookup"><span data-stu-id="511f2-204">Use transport rules to configure bulk email filtering</span></span>](use-transport-rules-to-configure-bulk-email-filtering.md)


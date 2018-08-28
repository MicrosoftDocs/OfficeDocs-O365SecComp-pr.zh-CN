---
title: 配置垃圾邮件筛选器策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
description: 选择要对标识为垃圾邮件的邮件采取的操作，并选择是否要筛选以特定语言撰写或从特定国家或地区发送的邮件，包括基本的垃圾邮件筛选器设置。
ms.openlocfilehash: b0a5fa1a5640bd0baab68c29d8098059a6025f7d
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026529"
---
# <a name="configure-your-spam-filter-policies"></a><span data-ttu-id="0a1e1-103">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="0a1e1-103">Configure your spam filter policies</span></span>
  
<span data-ttu-id="0a1e1-p101">选择要对标识为垃圾邮件的邮件采取的操作，并选择是否要筛选以特定语言撰写或从特定国家或地区发送的邮件，包括基本的垃圾邮件筛选器设置。垃圾邮件筛选器策略设置是仅应用于入站邮件。您可以编辑默认垃圾邮件筛选器策略来配置您的公司范围内垃圾邮件筛选器设置和创建自定义垃圾邮件筛选器策略，然后将它们应用于特定用户、 组或组织中的域。自定义策略始终优先于默认策略。您可以更改您的自定义策略运行通过更改每个自定义策略的优先级顺序。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p101">Basic spam filter settings include selecting the action to take on messages that are identified as spam, and choosing whether to filter messages that are written in specific languages or sent from specific countries or regions. Spam filter policy settings are applied to inbound messages only. You can edit the default spam filter policy to configure your company-wide spam filter settings and create custom spam filter policies, and then apply them to specific users, groups, or domains in your organization. Custom policies always take precedence over the default policy. You can change the order in which your custom policies run by changing the priority of each custom policy.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0a1e1-p102">Exchange Online Protection (EOP) 独立客户： 默认情况下，EOP 垃圾邮件筛选器将垃圾邮件检测到的邮件发送到每个收件人的垃圾邮件文件夹。但是，以确保本地邮箱**移动到垃圾邮件文件夹的邮件**操作，必须配置 Exchange 传输规则来检测垃圾邮件邮件头由 EOP 添加您的本地服务器上。有关详细信息，请参阅[确保垃圾邮件被路由到每个用户的垃圾邮件文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p102">For Exchange Online Protection (EOP) stand-alone customers: By default, the EOP spam filters send spam-detected messages to each recipient's Junk Email folder. However, in order to ensure that the **Move message to Junk Email folder** action works for on-premises mailboxes, you must configure Exchange Transport rules on your on-premises servers to detect spam headers that are added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
## <a name="what-you-must-know-before-you-begin"></a><span data-ttu-id="0a1e1-112">您必须知道开始之前</span><span class="sxs-lookup"><span data-stu-id="0a1e1-112">What you must know before you begin</span></span>
<span data-ttu-id="0a1e1-113"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="0a1e1-113"></span></span>

<span data-ttu-id="0a1e1-114">估计完成时间：30 分钟</span><span class="sxs-lookup"><span data-stu-id="0a1e1-114">Estimated time to complete: 30 minutes</span></span>
  
<span data-ttu-id="0a1e1-p103">您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的反垃圾邮件条目。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="0a1e1-117">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-exchange-admin-center-eac-to-configure-spam-filter-policies"></a><span data-ttu-id="0a1e1-118">使用 Exchange 管理中心 (EAC) 配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="0a1e1-118">Use the Exchange Admin Center (EAC) to configure spam filter policies</span></span>
<span data-ttu-id="0a1e1-119"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="0a1e1-119"></span></span>

1. <span data-ttu-id="0a1e1-120">在 Exchange 管理员中心 (EAC) 中，导航到**保护** \> **垃圾邮件筛选器**。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-120">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="0a1e1-121">执行下列操作之一在**常规**页上：</span><span class="sxs-lookup"><span data-stu-id="0a1e1-121">Do one of the following on the **general** page:</span></span> 
    
  - <span data-ttu-id="0a1e1-122">双击默认策略，以编辑公司范围的策略。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-122">Double-click the default policy in order to edit this company-wide policy.</span></span>
    
  - <span data-ttu-id="0a1e1-p104">单击![添加图标](media/ITPro-EAC-AddIcon.png)以创建新的自定义垃圾邮件筛选器策略可应用于用户、 组和您的组织中的域的**新**图标。您还可以通过双击其编辑现有的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p104">Click the ![Add Icon](media/ITPro-EAC-AddIcon.png) **New** icon in order to create a new custom spam-filter policy that can be applied to users, groups, and domains in your organization. You can also edit existing custom policies by double-clicking them.</span></span> 
    
3. <span data-ttu-id="0a1e1-p105">自定义的策略，指定此策略的名称。您还可以指定的更详细的说明。无法重命名默认策略。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p105">For custom policies only, specify a name for this policy. Optionally, you can also specify a more detailed description. You cannot rename the default policy.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0a1e1-p106">创建策略时，单个屏幕上将显示所有配置设置。相比之下，编辑策略时，您必须在多个屏幕导航。设置是在任一情况下，相同，但此过程的其余部分将介绍如何访问这些设置，当您编辑策略。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p106">When you create a policy, all configuration settings appear on a single screen. By contrast, when you edit a policy, you must navigate through multiple screens. The settings are the same in either case, but the rest of this procedure describes how to access these settings when you edit a policy.</span></span> 
  
4. <span data-ttu-id="0a1e1-p107">在**垃圾邮件和批量电子邮件操作**页上的在**垃圾邮件**和**高可信度垃圾邮件**，下，选择要为传入的垃圾邮件和批量电子邮件执行的操作。默认情况下，选择**将邮件移动到垃圾邮件文件夹**。其他可能的值为：</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p107">On the **spam and bulk email actions** page, under **Spam** and **High confidence spam**, select the action to take for incoming spam and bulk email. By default, **Move messages to Junk Email folder** is selected. The other possible values are:</span></span> 
    
  - <span data-ttu-id="0a1e1-134">**删除消息**删除整个邮件，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-134">**Delete message** Deletes the entire message, including all attachments.</span></span> 
    
  - <span data-ttu-id="0a1e1-p108">**隔离邮件**发送到预期接收人而不是隔离的邮件。如果选择此选项，请在**保留期限 （天） 的垃圾邮件**输入框中，指定将在此期间隔离垃圾邮件的天数。（它将自动删除后经过的时间。默认值为 15 天，这是最大值。最小值是 1 天）。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p108">**Quarantine message** Sends the message to quarantine instead of to the intended recipients. If you select this option, in the **Retain spam for (days)** input box, specify the number of days during which the spam message will be quarantined. (It will automatically be deleted after the time elapses. The default value is 15 days which is the maximum value. The minimum value is 1 day.)</span></span> 
    
    > [!TIP]
    >  <span data-ttu-id="0a1e1-p109">有关管理员如何管理 EAC 的隔离驻留的电子邮件的信息，请参阅[隔离](quarantine.md)和[查找并释放隔离的邮件，以管理员身份](find-and-release-quarantined-messages-as-an-administrator.md)。> 的有关如何配置垃圾邮件通知消息发送给用户的信息，请参阅[配置最终用户垃圾邮件在 EOP 中的通知](configure-end-user-spam-notifications-in-eop.md)或[配置最终用户垃圾邮件通知在 Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p109">For information about how administrators can manage email messages that reside in the quarantine in the EAC, see [Quarantine](quarantine.md) and [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md). >  For information about how to configure spam notification messages to be sent to users, see [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md) or [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
  - <span data-ttu-id="0a1e1-p110">**移动到垃圾邮件文件夹的邮件**将邮件发送到指定的收件人的垃圾邮件文件夹。这是这两个可信度阈值级别的默认操作。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p110">**Move message to Junk Email folder** Sends the message to the Junk Email folder of the specified recipients. This is the default action for both confidence threshold levels.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="0a1e1-p111">仅针对 Exchange Online Protection (EOP) 客户：要使用内部部署邮箱执行此项操作，必须在内部部署服务器上配置两个 Exchange 传输规则，检测 EOP 添加的垃圾邮件头。有关详细信息，请参阅[确保垃圾邮件已路由到每个用户的"垃圾邮件"文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p111">For Exchange Online Protection (EOP) customers: In order for this action to work with on-premises mailboxes, you must configure two Exchange Transport rules on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
  - <span data-ttu-id="0a1e1-p112">**添加 X 标头**将邮件发送到指定的收件人，但将 X 标头文本添加到邮件头，以便识别为垃圾邮件消息。使用此文本作为标识符，您可以 （可选） 创建收件箱规则或使用下游设备对邮件进行操作。默认 X 标头文本是**出现此消息是垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p112">**Add X-header** Sends the message to the specified recipients, but adds X-header text to the message header in order to identify the message as spam. Using this text as an identifier, you can optionally create inbox rules or use a downstream device to act on the message. The default X-header text is **This message appears to be spam**.</span></span>
    
    <span data-ttu-id="0a1e1-p113">使用**添加此 X 标头文本**输入框中，可以自定义 X 标头文本。如果您在自定义 X 标头文本，应注意以下条件：</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p113">You can customize the X-header text by using the **Add this X-header text** input box. If you customize the X-header text, be aware of the following conditions:</span></span> 
    
  - <span data-ttu-id="0a1e1-p114">如果只有标头指定格式的\<*标头*\>，其中内没有空格\<*标头*\>，冒号将追加到的自定义文本后, 跟默认文本。例如，如果您指定"这是-我的自定义的标头"，则 X 标头文本将显示为"这是-我的自定义的标头： 出现此消息是垃圾邮件。"      </span><span class="sxs-lookup"><span data-stu-id="0a1e1-p114">If you specify only the header in the format \< *header*  \>, where there are no spaces within the \<  *header*  \>, a colon will be appended to the custom text, followed by the default text. For example, if you specify "This-is-my-custom-header," the X-header text will appear as "This-is-my-custom-header: This message appears to be spam."</span></span> 
    
  - <span data-ttu-id="0a1e1-153">如果包括空格内的自定义标头文本，或者如果您自己添加冒号 (如"X 这是我的自定义标头"或"X-This-is-my-custom-header:")，则 X 标头文本恢复为默认值为"X 此-是-垃圾邮件： 出现此消息是垃圾邮件。"</span><span class="sxs-lookup"><span data-stu-id="0a1e1-153">If you include spaces within the custom header text, or if you add the colon yourself (such as "X This is my custom header" or "X-This-is-my-custom-header:"), the X-header text reverts to the default as "X-This-Is-Spam: This message appears to be spam."</span></span>
    
  - <span data-ttu-id="0a1e1-p115">不能指定的标题文本格式的\<*标头*\>:\<*值*\>。如果这样做，同时值之前和之后冒号将被忽略，和默认 X 标头文本显示改为:"X 此-是-垃圾邮件： 出现此消息是垃圾邮件。"      </span><span class="sxs-lookup"><span data-stu-id="0a1e1-p115">You can't specify the header text in the format \< *header*  \>:\<  *value*  \>. If you do this, both values before and after the colon will be ignored, and the default X-header text appears instead: "X-This-Is-Spam: This message appears to be spam."</span></span> 
    
  - <span data-ttu-id="0a1e1-p116">**Prepend 主题行文本**将邮件发送给预期收件人但预置的主题行**前缀与此文本的主题行**输入框中指定的文本。使用此文本作为标识符，您可以选择创建规则以筛选或将消息路由必要。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p116">**Prepend subject line with text** Sends the message to the intended recipients but prepends the subject line with the text that you specify in the **Prefix subject line with this text** input box. Using this text as an identifier, you can optionally create rules to filter or route the messages as necessary.</span></span> 
    
  - <span data-ttu-id="0a1e1-p117">**电子邮件地址的邮件重定向**将邮件发送到指定的电子邮件地址，而不是给预期收件人。**重定向到此电子邮件地址**输入框中指定的"重定向"地址。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p117">**Redirect message to email address** Sends the message to a designated email address instead of to the intended recipients. Specify the "redirect" address in the **Redirect to this email address** input box.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0a1e1-160">有关垃圾邮件可信度级别的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-160">For more information about spam confidence levels, see [Spam confidence levels](spam-confidence-levels.md).</span></span> 
  
5. <span data-ttu-id="0a1e1-p118">在**批量电子邮件**，下，您可以选择将批量电子邮件视为垃圾邮件阈值。此阈值基于消息的批量投诉级别。可以从 1 到 9，其中 1 表示为垃圾邮件，电子邮件最大容量，9 允许大多数批量电子邮件传送选择的阈值设置。服务然后执行配置的操作，例如将邮件发送到收件人的垃圾邮件文件夹。请参阅[批量投诉级别值](bulk-complaint-level-values.md)和[垃圾邮件和批量邮件之间的区别是什么？](what-s-the-difference-between-junk-email-and-bulk-email.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p118">Under **Bulk email**, you can select a threshold to treat bulk email as spam. This threshold is based on the bulk complaint level of the message. You can choose a threshold setting from 1 to 9, where 1 indicates most bulk email as spam, and 9 allows the most bulk email to be delivered. The service then performs the configured action, such as sending the message to the recipient's Junk Email folder. See [Bulk Complaint Level values](bulk-complaint-level-values.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) for more details.</span></span> 
    
6. <span data-ttu-id="0a1e1-p119">在**阻止列表**页上，您可以指定项，如发件人或域时，将始终标记为垃圾邮件。该服务将这些条目匹配的电子邮件上应用配置高可信度垃圾邮件操作。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p119">On the **Block Lists** page, you can specify entries, such as senders or domains, that will always be marked as spam. The service will apply the configured high confidence spam action on email that matches these entries.</span></span> 
    
  - <span data-ttu-id="0a1e1-p120">将不需要的发件人添加到阻止发件人列表中。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.png)，然后在选择对话框中，添加您想要阻止的发件人地址。您可以单独使用分号或新行的多个条目。单击**确定**以返回到**阻止列表**页上。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p120">Add unwanted senders to the Sender block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the sender addresses you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
  - <span data-ttu-id="0a1e1-p121">将不需要的域添加到阻止域列表中。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.png)，然后在选择对话框中，添加您想要阻止的域。您可以单独使用分号或新行的多个条目。单击**确定**以返回到**阻止列表**页上。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p121">Add unwanted domains to the Domain block list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the domains you want to block. You can separate multiple entries using a semi-colon or a new line. Click **Ok** to return to the **Block Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="0a1e1-176">如果您阻止顶级域，很可能会将您需要的电子邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-176">If you block top-level domains, it's likely that email you want will be marked as spam.</span></span> 
  
7. <span data-ttu-id="0a1e1-p122">在**允许列表**页上，您可以指定项，如发件人或域时，总是会发送到收件箱。垃圾邮件筛选器不处理电子邮件从这些条目。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p122">On the **Allow Lists** page, you can specify entries, such as senders or domains, that will always be delivered to the inbox. Email from these entries is not processed by the spam filter.</span></span> 
    
  - <span data-ttu-id="0a1e1-p123">添加受信任的发件人与发件人允许列表。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.png)，然后在选择对话框中，添加您希望允许的发件人地址。您可以单独使用分号或新行的多个条目。单击确定以返回到**允许列表**页。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p123">Add trusted senders to the Sender allow list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the sender addresses you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
  - <span data-ttu-id="0a1e1-p124">添加受信任的域到域的允许列表。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.png)，然后在选择对话框中，添加您希望允许的域。您可以单独使用分号或新行的多个条目。单击确定以返回到**允许列表**页。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p124">Add trusted domains to the Domain allow list. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then in the selection dialog box, add the domains you wish to allow. You can separate multiple entries using a semi-colon or a new line. Click ok to return to the **Allow Lists** page.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="0a1e1-187">如果您允许顶级域，很可能会将您不需要的电子邮件发送到收件箱。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-187">If you allow top-level domains, it's likely that email you don't want will be delivered to an inbox.</span></span> 
  
8. <span data-ttu-id="0a1e1-p125">**国际垃圾邮件**页上，您可以筛选以特定语言撰写或从特定国家或地区发送的电子邮件。您可以配置最多 86 不同的语言和 250 不同的区域。该服务将应用高可信度垃圾邮件配置的操作。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p125">On the **International Spam** page you can filter email messages that are written in specific languages or sent from specific countries or regions. You can configure up to 86 different languages and 250 different regions. The service will apply the configured action for high-confidence spam.</span></span> 
    
1. <span data-ttu-id="0a1e1-p126">选择**筛选器中的以下语言编写的电子邮件**复选框以启用此功能。单击![添加图标](media/ITPro-EAC-AddIcon.png)，然后，在选择对话框中进行的选择 （支持多重选择）。例如，如果**隔离邮件**是您配置的操作的高可信度垃圾邮件筛选消息写入中阿拉伯语 (AR)，选择，则会隔离阿拉伯语中写入任何邮件。单击**确定**以返回到**国际垃圾邮件**窗格。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p126">Select the **Filter email messages written in the following languages** check box to enable this functionality. Click ![Add Icon](media/ITPro-EAC-AddIcon.png), and then, in the selection dialog box, make your choices (multi-selection is supported). For example, if you select to filter messages written in Arabic (AR), and **Quarantine message** is your configured action for high confidence spam messages, any messages written in Arabic will be quarantined. Click **ok** to return to the **International Spam** pane.</span></span> 
    
2. <span data-ttu-id="0a1e1-p127">选择**从以下的国家或地区筛选器电子邮件发送**复选框以启用此功能。单击![添加图标](media/ITPro-EAC-AddIcon.png)，然后，在选择对话框中进行的选择 （支持多重选择）。例如，如果您选择，以筛选从澳大利亚 (AU)，发送的所有邮件和**隔离邮件**是从澳大利亚发送中您配置的操作的高可信度垃圾邮件，则任何邮件将被隔离。单击**确定**以返回到**国际垃圾邮件**窗格。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p127">Select the **Filter email messages sent from the following countries or regions** check box to enable this functionality. Click ![Add Icon](media/ITPro-EAC-AddIcon.png), and then, in the selection dialog box, make your choices (multi-selection is supported). For example, if you select to filter all messages that are sent from Australia (AU), and **Quarantine message** is your configured action for high-confidence spam messages, then any messages that is sent from Australia will be quarantined. Click **ok** to return to the **International Spam** pane.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0a1e1-p128">默认情况下，如果未选择任何国际垃圾邮件选项，那么该服务将对采用所有语言及来自所有区域的邮件执行正常垃圾邮件筛选。如果确定邮件为垃圾邮件或高可信度垃圾邮件，则会对其进行分析并应用配置的操作。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p128">By default, if no international spam options are selected, the service performs normal spam filtering on messages sent in all languages and from all regions. Messages are analyzed and the configured actions are applied if the message is determined to be spam or high confidence spam.</span></span> 
  
9. <span data-ttu-id="0a1e1-201">在**高级选项**页中，可以为每个高级垃圾邮件筛选选项中选择**上**，**关闭**或**测试**。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-201">On the **Advanced Options** page, you can select **On**, **Off**, or **Test** for each advanced spam filtering option.</span></span> 
    
1. <span data-ttu-id="0a1e1-p129">**在**根据与该选项相关联的规则主动筛选消息。可以将邮件标记为垃圾邮件或将其垃圾邮件得分基础上增大了，具体取决于哪些选项您打开。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p129">**On** Messages are actively filtered according to the rule that is associated with that option. Messages are either marked as spam or will have their spam scores increased, depending on which options you turn on.</span></span> 
    
2. <span data-ttu-id="0a1e1-p130">**关闭**符合垃圾邮件筛选器条件的邮件不采取任何操作。默认情况下关闭所有选项。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p130">**Off** No action is taken on messages that meet the spam filter criteria. All options are turned off by default.</span></span> 
    
3. <span data-ttu-id="0a1e1-p131">**测试**符合垃圾邮件筛选器条件的邮件不采取任何操作。但是，可以通过其传送到预期接收人之前添加 X 标头标记邮件。此 X 标头让您了解哪个 ASF 选项匹配。如果您指定的任何高级选项的**测试**，您可以配置以下测试模式设置要应用对已启用测试选项进行匹配时：</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p131">**Test** No action is taken on messages that meet the spam filter criteria. However, messages can be tagged by adding an X-header before they are delivered to the intended recipient. This X-header lets you know which ASF option was matched. If you specified **Test** for any of the advanced options, you can configure the following test mode settings to be applied when a match is made to a test-enabled option:</span></span> 
    
  - <span data-ttu-id="0a1e1-p132">**无**对邮件采取任何测试模式操作。这是默认按钮。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p132">**None** Take no test mode action on the message. This is the default.</span></span> 
    
  - <span data-ttu-id="0a1e1-212">**添加默认测试 X 标头文本**选择此选项将邮件发送到指定的收件人，但还将特殊 X 标头添加到邮件标识为具有匹配特定高级垃圾邮件筛选选项。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-212">**Add the default test X-header text** Selecting this option sends the message to the specified recipients, but also adds a special X-header to the message to identify it as having matched a specific advanced spam filtering option.</span></span> 
    
  - <span data-ttu-id="0a1e1-213">**发送到此地址密件抄送邮件**选择此选项将邮件的密件抄送副本发送到的输入框中指定的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-213">**Send a Bcc message to this address** Selecting this option sends a blind carbon copy of the message to the email address that you specify in the input box.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0a1e1-214">有关高级垃圾邮件筛选选项，包括有关每个选项和 X 标头文本与每个，关联的说明的详细信息，请参阅[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-214">For more information about the advanced spam filtering options, including descriptions about each option and the X-header text that is associated with each one, see [Advanced spam filtering  options](advanced-spam-filtering-asf-options.md).</span></span> 
  
10. <span data-ttu-id="0a1e1-p133">自定义策略仅，单击**应用于**菜单项，然后创建基于条件的规则以指定用户、 组和要应用此策略的域。如果它们都是唯一，您可以创建多个条件。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p133">For custom policies only, click the **Apply to** menu item, and then create a condition-based rule to specify the users, groups, and domains to which to apply this policy. You can create multiple conditions, if they are unique.</span></span> 
    
  - <span data-ttu-id="0a1e1-p134">若要选择用户，选择**收件人**。在随后出现的对话框中，从您的公司从用户选取器列表中，选择一个或多个发件人，然后单击**添加**。若要添加的发件人不在列表中，键入其电子邮件地址，然后单击**检查名称**。在此框中，您还可以使用通配符的多个电子邮件地址 (例如： \* @  _domainname_)。当您完成进行选择，单击**确定**以返回到主屏幕。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p134">To select users, select **The recipient is**. In the subsequent dialog box, select one or more senders from your company from the user picker list, and then click **add**. To add senders who aren't on the list, type their email addresses, and then click **Check names**. In this box, you can also use wildcards for multiple email addresses (for example: \*@ _domainname_). When you are done making your selections, click **ok** to return to the main screen.</span></span> 
    
  - <span data-ttu-id="0a1e1-p135">若要选择组，选择**收件人的成员**。然后，在随后出现的对话框中，选择或指定的组。单击**确定**以返回到主屏幕。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p135">To select groups, select **The recipient is a member of**. Then, in the subsequent dialog box, select or specify the groups. Click **ok** to return to the main screen.</span></span> 
    
  - <span data-ttu-id="0a1e1-p136">若要选择域，选择**收件人的域是**。然后，在随后出现的对话框中，添加域。单击**确定**以返回到主屏幕。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p136">To select domains, select **The recipient domain is**. Then, in the subsequent dialog box, add the domains. Click **ok** to return to the main screen.</span></span> 
    
    <span data-ttu-id="0a1e1-p137">您可以创建在规则中的例外。例如，您可以筛选来自特定域除外的所有域的邮件。单击**添加例外**，然后创建例外条件类似于您创建其他条件的方式。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p137">You can create exceptions within the rule. For example, you can filter messages from all domains except for a certain domain. Click **add exception**, and then create your exception conditions similar to the way that you created the other conditions.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="0a1e1-231">将垃圾邮件策略应用于组是仅支持**启用邮件的安全组**。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-231">Applying a spam policy to a group is supported only for **Mail Enabled Security Groups**.</span></span> 
  
11. <span data-ttu-id="0a1e1-p138">单击**保存**。在右窗格中显示的策略设置摘要。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p138">Click **save**. A summary of your policy settings appears in the right pane.</span></span>
    
> [!TIP]
>  <span data-ttu-id="0a1e1-p139">您可以选择或清除**启用**列中启用或禁用您的自定义策略中的复选框。默认情况下，启用所有策略。无法禁用默认策略。> 到删除自定义策略，请选择该策略中，单击![删除图标](media/ITPro-EAC-DeleteIcon.png)**删除**图标，然后确认您想要删除的策略。无法删除默认策略。> 自定义策略始终优先于默认策略。自定义策略与您在其中创建这些 （从最旧到最新），相反的顺序运行，但您可以通过单击更改您的自定义策略的优先级 （运行顺序）![向上箭头图标](media/ITPro-EAC-UpArrowIcon.png)向上箭头和![向下箭头图标](media/ITPro-EAC-DownArrowIcon.png)向下箭头。**优先级**为**0**的策略将运行第一个、 后跟**1**，然后**2**，依此类推。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p139">You can select or clear the check boxes in the **ENABLED** column to enable or disable your custom policies. By default, all policies are enabled. The default policy cannot be disabled. >  To delete a custom policy, select the policy, click the ![Delete icon](media/ITPro-EAC-DeleteIcon.png) **Delete** icon, and then confirm that you want to delete the policy. The default policy cannot be deleted. >  Custom policies always take precedence over the default policy. Custom policies run in the reverse order in which you created them (from oldest to newest), but you can change the priority (running order) of your custom policies by clicking the ![Up Arrow Icon](media/ITPro-EAC-UpArrowIcon.png) up arrow and ![Down Arrow Icon](media/ITPro-EAC-DownArrowIcon.png) down arrow. The policy that has a **PRIORITY** of **0** will run first, followed by **1**, then **2**, and so on.</span></span> 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a><span data-ttu-id="0a1e1-242">使用远程 PowerShell 配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="0a1e1-242">Use remote PowerShell to configure spam filter policies</span></span>
<span data-ttu-id="0a1e1-243"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="0a1e1-243"></span></span>

<span data-ttu-id="0a1e1-p140">您还可以配置并应用在 PowerShell 中的垃圾邮件筛选器策略。若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?linkid=396554)。若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection，请参阅[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p140">You can also configure and apply spam filter policies in PowerShell. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554). To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span>
  
- <span data-ttu-id="0a1e1-247">[Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) 查看垃圾邮件筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-247">[Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) View your spam filter settings.</span></span> 
    
- <span data-ttu-id="0a1e1-248">[Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) 编辑垃圾邮件筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-248">[Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) Edit your spam filter settings.</span></span> 
    
- <span data-ttu-id="0a1e1-249">[New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) 创建新的自定义垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-249">[New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) Create a new custom spam filter policy.</span></span> 
    
- <span data-ttu-id="0a1e1-250">[Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) 删除自定义垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-250">[Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) Delete a custom spam filter policy.</span></span> 
    
<span data-ttu-id="0a1e1-p141">若要向用户、组和/或域应用自定义垃圾邮件筛选器策略，请使用 [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) cmdlet（创建可应用于自定义策略的新筛选器规则）或 [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) cmdlet（编辑可应用于自定义策略的现有筛选器规则）。使用 [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) cmdlet 或 [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) cmdlet 可启用或禁用应用于策略的规则。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p141">To apply a custom spam filter policy to users, groups, and/or domains, use the [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) cmdlet (to create a new filter rule that can be applied to custom policies) or the [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) cmdlet (to edit an existing filter rule that can be applied to custom policies). Use the [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) cmdlet or the [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) cmdlet to enable or disable the rule applied to the policy.</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="0a1e1-253">您如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="0a1e1-253">How do you know this worked?</span></span>
<span data-ttu-id="0a1e1-254"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="0a1e1-254"></span></span>

<span data-ttu-id="0a1e1-p142">为了确保垃圾邮件被正确地检测并处理过，您可以通过服务发送一封 GTUBE 邮件。与 EICAR 杀毒测试文件相似，GTUBE 提供了一个测试，通过此测试可以验证服务是否正在检测传入的垃圾邮件。GTUBE 邮件应该始终被垃圾邮件筛选器检测为垃圾邮件，对邮件执行的操作应该与配置设置相匹配。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p142">To ensure that spam is being properly detected and acted upon, you can send a GTUBE message through the service. Similar to the EICAR antivirus test file, GTUBE provides a test by which you can verify that the service is detecting incoming spam. A GTUBE message should always be detected as spam by the spam filter, and the actions that are performed upon the message should match your configured settings.</span></span>
  
<span data-ttu-id="0a1e1-258">邮件中包括以下单行 GTUBE 文本，没有任何空格或换行符：</span><span class="sxs-lookup"><span data-stu-id="0a1e1-258">Include the following GTUBE text in a mail message on a single line, without any spaces or line breaks:</span></span>
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a><span data-ttu-id="0a1e1-259">优化垃圾邮件筛选器策略，防止误报和漏报</span><span class="sxs-lookup"><span data-stu-id="0a1e1-259">Fine tuning your spam filter policy to prevent false positives and false negatives</span></span>
<span data-ttu-id="0a1e1-260"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="0a1e1-260"></span></span>

<span data-ttu-id="0a1e1-p143">如果想采取积极方法进行垃圾邮件筛选，可以启用高级垃圾邮件筛选选项。有关适用于整个组织的常规垃圾邮件设置，请参阅[使用安全列表或其他技术防止误报电子邮件被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)。如果你拥有管理员级别控制，并且你想要阻止误报或漏报问题，这些会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p143">You can enable advanced spam filtering options if you want to pursue an aggressive approach to spam filtering. For general spam settings that apply to the whole organization, take a look at [Prevent false positive email marked as spam with a safelist or other techniques](https://go.microsoft.com/fwlink/p/?LinkId=534224) or [Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225). These are helpful if you have administrator-level control and you want to prevent false positives or false negatives.</span></span>
  
## <a name="new-to-office-365"></a><span data-ttu-id="0a1e1-264">刚开始接触 Office 365？</span><span class="sxs-lookup"><span data-stu-id="0a1e1-264">New to Office 365?</span></span>
<span data-ttu-id="0a1e1-265"><a name="sectionSection5"> </a></span><span class="sxs-lookup"><span data-stu-id="0a1e1-265"></span></span>

||
|:-----|
|<span data-ttu-id="0a1e1-p144">![LinkedIn Learning 短图标](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **刚开始接触 Office 365？**         发现 LinkedIn Learning 向 **Office 365 admins and IT pros**提供的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="0a1e1-p144">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span> |
   
## <a name="for-more-information"></a><span data-ttu-id="0a1e1-268">详细信息</span><span class="sxs-lookup"><span data-stu-id="0a1e1-268">For more information</span></span>
<span data-ttu-id="0a1e1-269"><a name="sectionSection6"> </a></span><span class="sxs-lookup"><span data-stu-id="0a1e1-269"></span></span>

[<span data-ttu-id="0a1e1-270">配置连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="0a1e1-270">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="0a1e1-271">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="0a1e1-271">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="0a1e1-272">隔离</span><span class="sxs-lookup"><span data-stu-id="0a1e1-272">Quarantine</span></span>](quarantine.md)
  
[<span data-ttu-id="0a1e1-273">使用安全列表或其他技术阻止误报电子邮件被标记为垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="0a1e1-273">Prevent false positive email marked as spam with a safelist or other techniques</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[<span data-ttu-id="0a1e1-274">使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题</span><span class="sxs-lookup"><span data-stu-id="0a1e1-274">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

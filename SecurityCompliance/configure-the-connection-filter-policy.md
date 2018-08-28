---
title: 配置连接筛选器策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
description: 若要确保不阻止从您信任的人员发送的电子邮件，可以使用的连接筛选器策略创建一个允许列表，也称为安全发件人列表，您信任的 IP 地址。您还可以创建阻止发件人列表。
ms.openlocfilehash: d106e55779c6246b77018fef3ab9d58fa759d99e
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027599"
---
# <a name="configure-the-connection-filter-policy"></a><span data-ttu-id="20dcf-104">配置连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="20dcf-104">Configure the connection filter policy</span></span>
 
<span data-ttu-id="20dcf-p102">我们大多数人都有值得信赖的朋友和商业伙伴。若是在垃圾邮件文件夹中发现有来自他们的电子邮件，甚至是完全被垃圾邮件筛选器阻止，这将会是一件很令人沮丧的事情。如果想要确保对您信任的人所发的电子邮件不进行阻止，您可以使用连接筛选策略创建一个由您信任的 IP 地址构成的"允许"名单，也称为白名单。您通常也可以从已知垃圾邮件发送者（您永远不想接收由他们发来的电子邮件）创建一个阻止的发件人名单，也就是由一些 IP 地址组成的列表。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p102">Most of us have friends and business partners we trust. It can be frustrating to find email from them in your junk email folder, or even blocked entirely by a spam filter. If you want to make sure that email sent from people you trust isn't blocked, you can use the connection filter policy to create an Allow list, also known as a safe sender list, of IP addresses that you trust. You can also create a blocked senders list, which is a list of IP addresses, typically from known spammers, that you don't ever want to receive email messages from.</span></span>
  
 <span data-ttu-id="20dcf-p103">有关适用于整个组织的详细垃圾邮件设置，请参阅[如何帮助确保邮件不会被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)。如果你拥有管理员级别控制，并且你想要防止误报或漏报问题，这些内容会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p103">For more spam settings that apply to the whole organization, take a look at [How to help ensure that a message isn't marked as spam](https://go.microsoft.com/fwlink/p/?LinkId=534224) or [Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225). These are helpful if you have administrator-level control and you want to prevent false positives or false negatives.</span></span>
  
<span data-ttu-id="20dcf-111">下面的视频显示了连接筛选器策略的配置步骤：</span><span class="sxs-lookup"><span data-stu-id="20dcf-111">The following video shows the configuration steps for the connection filter policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20dcf-112">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="20dcf-112">What do you need to know before you begin?</span></span>
<span data-ttu-id="20dcf-113"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="20dcf-113"></span></span>

- <span data-ttu-id="20dcf-114">估计完成时间：15 分钟</span><span class="sxs-lookup"><span data-stu-id="20dcf-114">Estimated time to complete: 15 minutes</span></span>
    
- <span data-ttu-id="20dcf-p104">您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的"反垃圾邮件"条目。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
    
- <span data-ttu-id="20dcf-p105">要获取想要允许或阻止其邮件的发件人的 IP 地址，你可以检查邮件的 Internet 标题。查找 CIP 标题，如[反垃圾邮件邮件头](anti-spam-message-headers.md)中所述。有关如何查看各种电子邮件客户端中的电子邮件头的信息，请参阅[邮件头分析器](https://go.microsoft.com/fwlink/p/?LinkId=306583)主题。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p105">To obtain the IP address of the sender whose messages you want to allow or block, you can check the Internet header of the message. Look for the CIP header as described in [Anti-spam message headers](anti-spam-message-headers.md). For information about how to view a message header in various email clients, see the [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583) topic.</span></span> 
    
- <span data-ttu-id="20dcf-120">从 IP 阻止列表中的 IP 地址发送的电子邮件被拒绝，未标记为垃圾邮件，且未进行其他筛选。</span><span class="sxs-lookup"><span data-stu-id="20dcf-120">Email messages sent from an IP address on the IP Block list are rejected, not marked as spam, and no additional filtering occurs.</span></span>
    
- <span data-ttu-id="20dcf-p106">也可以通过远程 PowerShell 执行下面的连接筛选器过程。使用[Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) cmdlet 可以查看您的设置，以及[Set-hostedconnectionfilterpolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx)编辑您的连接筛选器策略设置。若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection，请参阅[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p106">The following connection filter procedure can also be performed via remote PowerShell. Use the [Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) cmdlet to review your settings, and the [Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) to edit your connection filter policy settings. To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290). To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="20dcf-125">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-125">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a><span data-ttu-id="20dcf-126">使用 EAC 编辑默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="20dcf-126">Use the EAC to edit the default connection filter policy</span></span>
<span data-ttu-id="20dcf-127"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="20dcf-127"></span></span>

<span data-ttu-id="20dcf-p107">在 Exchange 管理中心 (EAC) 编辑连接筛选器策略，创建 IP 允许列表或 IP 阻止列表。连接筛选器策略设置只适用于入站邮件。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p107">You create an IP Allow list or IP Block list by editing the connection filter policy in the Exchange admin center (EAC). The connection filter policy settings are applied to inbound messages only.</span></span>
  
1. <span data-ttu-id="20dcf-130">在 Exchange 管理员中心 (EAC) 中，导航到**保护** \> **连接筛选器**，然后双击默认策略。</span><span class="sxs-lookup"><span data-stu-id="20dcf-130">In the Exchange admin center (EAC), navigate to **Protection** \> **Connection filter**, and then double-click the default policy.</span></span>
    
2. <span data-ttu-id="20dcf-131">单击**连接筛选**菜单项，然后创建所需的列表： IP 允许列表、 IP 阻止列表，或同时。</span><span class="sxs-lookup"><span data-stu-id="20dcf-131">Click the **Connection filtering** menu item and then create the lists you want: an IP Allow list, an IP Block list, or both.</span></span> 
    
    <span data-ttu-id="20dcf-p108">若要创建这些列表，请单击![添加图标](media/ITPro-EAC-AddIcon.png)。在随后出现的对话框中指定的 IP 地址或地址范围，，然后单击**ok**。重复此过程以添加其他地址。（您可以还编辑或删除 IP 地址后已添加。）</span><span class="sxs-lookup"><span data-stu-id="20dcf-p108">To create these lists, click ![Add Icon](media/ITPro-EAC-AddIcon.png). In the subsequent dialog box, specify the IP address or address range, and then click **ok**. Repeat this process to add additional addresses. (You can also edit or remove IP addresses after they have been added.)</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="20dcf-p109">如果向这两个列表添加一个 IP 地址，则允许从其发送的电子邮件。 >  IPV4 IP 地址必须以 nnn.nnn.nnn.nnn 的格式进行指定，其中 nnn 代表 0 至 255 的任意数字。您也可以采用 nnn.nnn.nnn.nnn/rr 格式指定无类别域际路由选择 (CIDR) 的范围，其中 rr 代表 24 至 32 的任意数字。要指定超出 24 至 32 的范围，请参阅 [配置 IP 允许列表时的其他注意事项](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists)。 >  您最多可以指定 1273 个条目，条目可以是单个 IP 地址或 IP 地址的 CIDR 范围（从 /24 到 /32）。 >  如果您发送 TLS 加密邮件，则不支持 IPv6 地址和地址范围。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p109">If you add an IP address to both lists, email sent from it is allowed. >  IPV4 IP addresses must be specified in the format nnn.nnn.nnn.nnn where nnn is a number from 0 to 255. You can also specify Classless Inter-Domain Routing (CIDR) ranges in the format nnn.nnn.nnn.nnn/rr where rr is a number from 24 to 32. To specify ranges outside of the 24 to 32 range, see [Additional considerations when configuring IP Allow lists](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists). >  You can specify a maximum of 1273 entries, where an entry is either a single IP address or a CIDR range of IP addresses from /24 to /32. >  If you're sending TLS-encrypted messages, IPv6 addresses and address ranges are not supported.</span></span> 
  
3. <span data-ttu-id="20dcf-p110">（可选） 选中**启用安全列表**复选框，以防止缺少来自特定已知发件人的电子邮件。如何？Microsoft 订阅到的受信任的发件人的第三方源。使用此安全列表意味着这些受信任的发件人不会错误地标记为垃圾邮件。我们建议选择此选项，因为它应减少的收到的误报 （为垃圾邮件分类的良好邮件）。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p110">Optionally, select the **Enable safe list** check box to prevent missing email from certain well-known senders. How? Microsoft subscribes to third-party sources of trusted senders. Using this safe list means that these trusted senders aren't mistakenly marked as spam. We recommend selecting this option because it should reduce the number of false positives (good mail that's classified as spam) you receive.</span></span> 
    
4. <span data-ttu-id="20dcf-p111">单击**保存**。在右窗格中显示的默认策略设置摘要。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p111">Click **save**. A summary of your default policy settings appears in the right pane.</span></span>
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a><span data-ttu-id="20dcf-149">配置 IP 允许列表时的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="20dcf-149">Additional considerations when configuring IP Allow lists</span></span>
<span data-ttu-id="20dcf-150"><a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a></span><span class="sxs-lookup"><span data-stu-id="20dcf-150"></span></span>

<span data-ttu-id="20dcf-151">以下是在配置 IP 允许列表时需要考虑或应该注意的其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="20dcf-151">The following are additional considerations you may want to consider or that you should be aware of when configuring an IP Allow list.</span></span>
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a><span data-ttu-id="20dcf-152">指定超出建议范围的 CIDR 范围</span><span class="sxs-lookup"><span data-stu-id="20dcf-152">Specifying a CIDR range that falls outside of the recommended range</span></span>

<span data-ttu-id="20dcf-p112">若要指定 CIDR IP 地址范围为从/1 到 /23，必须创建传输规则操作的设置的垃圾邮件可信度 (SCL) 的 IP 地址范围**绕过垃圾邮件筛选**（这意味着从收到此 IP 地址范围内的所有消息都都到设置为"非垃圾邮件？和任何其他筛选服务执行）。但是，如果任何这些 IP 地址出现在任何 Microsoft 的专有阻止列表或我们第三方阻止的任何列表，仍能阻止这些邮件。因此强烈建议您使用到/24/32 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p112">To specify a CIDR IP address range from /1 to /23, you must create a Transport rule that operates on the IP address range that sets the spam confidence level (SCL) to **Bypass spam filtering** (meaning that all messages received from within this IP address range are set to "not spam�? and no additional filtering is performed by the service). However, if any of these IP addresses appear on any of Microsoft's proprietary block lists or on any of our third-party block lists, these messages will still be blocked. It is therefore strongly recommended that you use the /32 to /24 IP address range.</span></span> 
  
<span data-ttu-id="20dcf-157">若要创建此传输规则，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="20dcf-157">To create this Transport rule, perform the following steps.</span></span>
  
1. <span data-ttu-id="20dcf-158">在 EAC 中，导航到**邮件流** \> **规则**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-158">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="20dcf-159">单击![添加图标](media/ITPro-EAC-AddIcon.png)，然后选择**创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-159">Click ![Add Icon](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="20dcf-160">为该规则指定一个名称，然后单击**更多选项**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-160">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="20dcf-161">在**以下情况应用此规则**，选择**发件人**，然后选择**IP 地址处于这些范围或完全匹配**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-161">Under **Apply this rule if**, select **The sender** and then choose **IP address is in any of these ranges or exactly matches**.</span></span>
    
5. <span data-ttu-id="20dcf-162">在**指定 IP 地址**，请指定 IP 地址范围，单击**添加**![添加图标](media/ITPro-EAC-AddIcon.png)，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-162">In the **specify IP addresses**, specify the IP address range, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then click **ok**.</span></span>
    
6. <span data-ttu-id="20dcf-p113">在**执行以下操作**下选择**修改邮件属性**，然后**将垃圾邮件可信度 (SCL) 设置**中设置操作。在**指定 SCL**框中，选择**绕过垃圾邮件筛选**，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p113">Under **Do the following** box, set the action by choosing **Modify the message properties** and then **set the spam confidence level (SCL)**. In the **specify SCL** box, select **Bypass spam filtering**, and click **ok**.</span></span>
    
7. <span data-ttu-id="20dcf-p114">如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。我们建议首先在一段时间内测试规则，然后再强制应用。[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)包含有关这些选择的详细信息。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p114">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) contains more information about these selections.</span></span> 
    
8. <span data-ttu-id="20dcf-p115">单击**保存**按钮保存规则。显示在列表中的规则。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p115">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="20dcf-170">创建并强制应用规则之后，您指定的 IP 地址范围会绕过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="20dcf-170">After you create and enforce the rule, spam filtering is bypassed for the IP address range you specified.</span></span>
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a><span data-ttu-id="20dcf-171">为特定域设置 IP 允许列表例外作用域</span><span class="sxs-lookup"><span data-stu-id="20dcf-171">Scoping an IP Allow list exception for a specific domain</span></span>

<span data-ttu-id="20dcf-p116">通常情况下，我们建议您将您认为对于所有域而言安全的 IP 地址（或 IP 地址范围）添加到 IP 允许列表。但是，如果您不希望 IP 允许列表条目应用于所有域，则可以创建一条应用范围不包括特定域的传输规则。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p116">In general, we recommend that you add the IP addresses (or IP address ranges) for all your domains that you consider safe to the IP Allow list. However, if you don't want your IP Allow List entry to apply to all your domains, you can create a Transport rule that excepts specific domains.</span></span> 
  
<span data-ttu-id="20dcf-p117">例如，让我们假设您有三个域：ContosoA.com、ContosoB.com 和 ContosoC.com，您希望添加 IP 地址（为了简便起见，我们使用 1.2.3.4），并且只针对域 ContosoB.com 跳过筛选。您可以为 1.2.3.4 创建 IP 允许列表，它会将所有域的垃圾邮件可信度 (SCL) 设置为 -1（意味着它被分类为非垃圾邮件）。然后，您可以创建一条传输规则，将除 ContosoB.com 之外的所有域的 SCL 设置为 0。这将使与该 IP 地址相关、除 ContosoB.com（在规则中被列为例外的域）之外的所有域的邮件被重新扫描。ContosoB.com 的 SCL 仍为 -1，这意味着它将跳过筛选，而 ContosoA.com 和 ContosoC.com 的 SCL 为 0，这意味着内容筛选器将重新扫描它们。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p117">For example, let's say you have three domains: ContosoA.com, ContosoB.com, and ContosoC.com, and you want to add the IP address (for simplicity's sake, let's use 1.2.3.4) and skip filtering only for domain ContosoB.com. You would create an IP Allow list for 1.2.3.4, which sets the spam confidence level (SCL) to -1 (meaning it is classified as non-spam) for all domains. You can then create a Transport rule that sets the SCL for all domains except ContosoB.com to 0. This results in the message being rescanned for all domains associated with the IP address except for ContosoB.com which is the domain listed as the exception in the rule. ContosoB.com still has an SCL of -1 which means skip filtering, whereas ContosoA.com and ContosoC.com have SCLs of 0, meaning they will be rescanned by the content filter.</span></span>
  
<span data-ttu-id="20dcf-179">为此，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="20dcf-179">To do this, perform the following steps:</span></span>
  
1. <span data-ttu-id="20dcf-180">在 EAC 中，导航到**邮件流** \> **规则**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-180">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="20dcf-181">单击![添加图标](media/ITPro-EAC-AddIcon.png)，然后选择**创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-181">Click ![Add Icon](media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="20dcf-182">为该规则指定一个名称，然后单击**更多选项**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-182">Give the rule a name and then click **More options**.</span></span>
    
4. <span data-ttu-id="20dcf-183">在**以下情况应用此规则**，选择**发件人**，然后选择**IP 地址处于这些范围或完全匹配**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-183">Under **Apply this rule if**, select **The sender** and then choose **IP address is in any of these ranges or exactly matches**.</span></span>
    
5. <span data-ttu-id="20dcf-184">在**指定 IP 地址**框中，指定的 IP 地址或 IP 地址范围您输入的 IP 允许列表中，单击**添加**![添加图标](media/ITPro-EAC-AddIcon.png)，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-184">In the **specify IP addresses** box, specify the IP address or IP address range you entered in the IP Allow list, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png), and then click **ok**.</span></span>
    
6. <span data-ttu-id="20dcf-p118">下**执行以下操作**，通过选择**修改邮件属性**，然后**将垃圾邮件可信度 (SCL) 设置**来设置操作。在**指定 SCL**框中，选择**0**，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p118">Under **Do the following**, set the action by choosing **Modify the message properties** and then **set the spam confidence level (SCL)**. In the **specify SCL** box, select **0**, and click **ok**.</span></span>
    
7. <span data-ttu-id="20dcf-187">单击**添加例外**，并在**除非**下选择**发件人**选择**域**。</span><span class="sxs-lookup"><span data-stu-id="20dcf-187">Click **add exception**, and under **Except if**, select **The sender** and choose **domain is**.</span></span> 
    
8. <span data-ttu-id="20dcf-p119">在**指定域**框中，输入您要绕过垃圾邮件筛选，如**contosob.com**的域。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.png)以将其移到的短语列表。如果您想要将其他域添加为异常，并在完成时单击**确定**，请重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p119">In the **specify domain** box, enter the domain for which you want to bypass spam filtering, such as **contosob.com**. Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.png) to move it to the list of phrases. Repeat this step if you want to add additional domains as exceptions, and click **ok** when you are finished.</span></span> 
    
9. <span data-ttu-id="20dcf-p120">如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。我们建议首先在一段时间内测试规则，然后再强制应用。[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)包含有关这些选择的详细信息。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p120">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections. We recommend testing the rule for a period before you enforce it. [Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) contains more information about these selections.</span></span> 
    
10. <span data-ttu-id="20dcf-p121">单击**保存**按钮保存规则。显示在列表中的规则。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p121">Click the **save** button to save the rule. It appears in your list of rules.</span></span> 
    
<span data-ttu-id="20dcf-196">在创建和强制应用规则后，仅为您输入的例外的域绕过指定 IP 地址或 IP 地址范围的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="20dcf-196">After you create and enforce the rule, spam filtering for the IP address or IP address range you specified is bypassed only for the domain exception you entered.</span></span>
  
## <a name="new-to-office-365"></a><span data-ttu-id="20dcf-197">刚开始接触 Office 365？</span><span class="sxs-lookup"><span data-stu-id="20dcf-197">New to Office 365?</span></span>
<span data-ttu-id="20dcf-198"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="20dcf-198"></span></span>

||
|:-----|
|<span data-ttu-id="20dcf-p122">![LinkedIn Learning 短图标](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **刚开始接触 Office 365？**         发现 LinkedIn Learning 向 **Office 365 admins and IT pros**提供的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="20dcf-p122">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span> |
   
## <a name="for-more-information"></a><span data-ttu-id="20dcf-201">详细信息</span><span class="sxs-lookup"><span data-stu-id="20dcf-201">For more information</span></span>
<span data-ttu-id="20dcf-202"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="20dcf-202"></span></span>

[<span data-ttu-id="20dcf-203">Exchange Online 中的安全发件人和阻止发件人列表</span><span class="sxs-lookup"><span data-stu-id="20dcf-203">Safe sender and blocked sender lists in Exchange Online</span></span>](safe-sender-and-blocked-sender-lists-faq.md)
  
[<span data-ttu-id="20dcf-204">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="20dcf-204">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="20dcf-205">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="20dcf-205">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="20dcf-206">如何帮助确保邮件不会标记为垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="20dcf-206">How to help ensure that a message isn't marked as spam</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[<span data-ttu-id="20dcf-207">使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题</span><span class="sxs-lookup"><span data-stu-id="20dcf-207">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

---
title: 配置连接筛选器策略、允许列表、阻止列表
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: 若要确保从不受信任的人发送的电子邮件被阻止, 可以使用连接筛选器策略创建您信任的 IP 地址的允许列表 (也称为 "安全发件人列表")。 您还可以创建阻止的发件人列表。
ms.openlocfilehash: 71dd34ea822324936713380e557d2341e1e389c0
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "36699257"
---
# <a name="configure-the-connection-filter-policy"></a><span data-ttu-id="97aea-104">配置连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="97aea-104">Configure the connection filter policy</span></span>

<span data-ttu-id="97aea-p102">我们大多数人都有值得信赖的朋友和商业伙伴。若是在垃圾邮件文件夹中发现有来自他们的电子邮件，甚至是完全被垃圾邮件筛选器阻止，这将会是一件很令人沮丧的事情。如果想要确保对您信任的人所发的电子邮件不进行阻止，您可以使用连接筛选策略创建一个由您信任的 IP 地址构成的"允许"名单，也称为白名单。您通常也可以从已知垃圾邮件发送者（您永远不想接收由他们发来的电子邮件）创建一个阻止的发件人名单，也就是由一些 IP 地址组成的列表。</span><span class="sxs-lookup"><span data-stu-id="97aea-p102">Most of us have friends and business partners we trust. It can be frustrating to find email from them in your junk email folder, or even blocked entirely by a spam filter. If you want to make sure that email sent from people you trust isn't blocked, you can use the connection filter policy to create an Allow list, also known as a safe sender list, of IP addresses that you trust. You can also create a blocked senders list, which is a list of IP addresses, typically from known spammers, that you don't ever want to receive email messages from.</span></span>
  
- <span data-ttu-id="97aea-109">考虑*[允许列表](create-safe-sender-lists-in-office-365.md)* 时, 请记住, 连接筛选器策略与筛选器*允许的受信任帐户*密切相关。</span><span class="sxs-lookup"><span data-stu-id="97aea-109">When thinking about *[Allow lists](create-safe-sender-lists-in-office-365.md)*, keep in mind connection filter policies concern themselves with the *trusted accounts allowed* by the filter.</span></span> <span data-ttu-id="97aea-110">这样做是为了更准确地筛选出不受信任或不受信任的发件人, 同时保留您所需的信息。</span><span class="sxs-lookup"><span data-stu-id="97aea-110">This is done in the interest of more accurately filtering out less trusted or untrusted mailers while keeping what you need.</span></span> <span data-ttu-id="97aea-111">连接筛选器策略允许列表从更大的帐户和 Ip 池向少数几个受信任的 Ip 进行筛选, 并确保您的受信任的访问者更易于访问。</span><span class="sxs-lookup"><span data-stu-id="97aea-111">A connection filter policy Allow list is about filtering to the few trusted IPs from a much larger pool of accounts and IPs, and assuring your trusted mailers easier access.</span></span>

- <span data-ttu-id="97aea-112">可以将创建阻止列表的连接筛选器策略视为筛选器中的 "仅捕获较少" 或 "不可信" 帐户。</span><span class="sxs-lookup"><span data-stu-id="97aea-112">A connection filter policy creating a Block list can be thought of as catching less, or untrustworthy accounts in the filter instead.</span></span>

 <span data-ttu-id="97aea-p104">有关适用于整个组织的详细垃圾邮件设置，请参阅[如何帮助确保邮件不会被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)。如果你拥有管理员级别控制，并且你想要防止误报或漏报问题，这些内容会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="97aea-p104">For more spam settings that apply to the whole organization, take a look at [How to help ensure that a message isn't marked as spam](https://go.microsoft.com/fwlink/p/?LinkId=534224) or [Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225). These are helpful if you have administrator-level control and you want to prevent false positives or false negatives.</span></span>

> [!TIP]
> <span data-ttu-id="97aea-115">您可能想要暂停并阅读有关如何创建[允许 (或安全发件人) 列表](create-safe-sender-lists-in-office-365.md)和[阻止列表](create-block-sender-lists-in-office-365.md)的说明。</span><span class="sxs-lookup"><span data-stu-id="97aea-115">You may want to pause and read up on how to create [Allow (or safe sender) lists](create-safe-sender-lists-in-office-365.md) and [Block lists](create-block-sender-lists-in-office-365.md).</span></span>
  
<span data-ttu-id="97aea-116">下面的视频显示了连接筛选器策略的配置步骤：</span><span class="sxs-lookup"><span data-stu-id="97aea-116">The following video shows the configuration steps for the connection filter policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="97aea-117">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="97aea-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="97aea-118">估计完成时间：15 分钟</span><span class="sxs-lookup"><span data-stu-id="97aea-118">Estimated time to complete: 15 minutes</span></span>

- <span data-ttu-id="97aea-119">您必须先获得权限，然后才能执行此过程或多个过程。</span><span class="sxs-lookup"><span data-stu-id="97aea-119">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="97aea-120">若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的 "反垃圾邮件" 条目。</span><span class="sxs-lookup"><span data-stu-id="97aea-120">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

- <span data-ttu-id="97aea-121">要获取想要允许或阻止其邮件的发件人的 IP 地址，你可以检查邮件的 Internet 标题。</span><span class="sxs-lookup"><span data-stu-id="97aea-121">To obtain the IP address of the sender whose messages you want to allow or block, you can check the Internet header of the message.</span></span> <span data-ttu-id="97aea-122">查找 CIP 标题，如[反垃圾邮件邮件头](anti-spam-message-headers.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="97aea-122">Look for the CIP header as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="97aea-123">有关如何在各种电子邮件客户端中查看邮件头的信息, 请参阅[邮件头分析器](https://go.microsoft.com/fwlink/p/?LinkId=306583)。</span><span class="sxs-lookup"><span data-stu-id="97aea-123">For information about how to view a message header in various email clients, see [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583).</span></span>

- <span data-ttu-id="97aea-124">从 IP 阻止列表中的 IP 地址发送的电子邮件被拒绝，未标记为垃圾邮件，且未进行其他筛选。</span><span class="sxs-lookup"><span data-stu-id="97aea-124">Email messages sent from an IP address on the IP Block list are rejected, not marked as spam, and no additional filtering occurs.</span></span>

- <span data-ttu-id="97aea-125">以下连接筛选器步骤也可以通过远程 PowerShell 执行。</span><span class="sxs-lookup"><span data-stu-id="97aea-125">The following connection filter procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="97aea-126">使用 [Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) cmdlet 查看设置，以及使用 [Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) 编辑连接筛选策略设置。</span><span class="sxs-lookup"><span data-stu-id="97aea-126">Use the [Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) cmdlet to review your settings, and the [Set-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) to edit your connection filter policy settings.</span></span> <span data-ttu-id="97aea-127">若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection, 请参阅[连接到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。</span><span class="sxs-lookup"><span data-stu-id="97aea-127">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span> <span data-ttu-id="97aea-128">若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="97aea-128">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a><span data-ttu-id="97aea-129">使用 EAC 编辑默认连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="97aea-129">Use the EAC to edit the default connection filter policy</span></span>

<span data-ttu-id="97aea-p108">在 Exchange 管理中心 (EAC) 编辑连接筛选器策略，创建 IP 允许列表或 IP 阻止列表。连接筛选器策略设置只适用于入站邮件。</span><span class="sxs-lookup"><span data-stu-id="97aea-p108">You create an IP Allow list or IP Block list by editing the connection filter policy in the Exchange admin center (EAC). The connection filter policy settings are applied to inbound messages only.</span></span>
  
1. <span data-ttu-id="97aea-132">在 Exchange 管理中心 (EAC) 中, 导航到 "**保护** \> **连接筛选器**", 然后双击默认策略。</span><span class="sxs-lookup"><span data-stu-id="97aea-132">In the Exchange admin center (EAC), navigate to **Protection** \> **Connection filter**, and then double-click the default policy.</span></span>

2. <span data-ttu-id="97aea-133">单击“连接筛选”\*\*\*\* 菜单项目，然后创建所需列表：IP 允许列表和/或 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="97aea-133">Click the **Connection filtering** menu item and then create the lists you want: an IP Allow list, an IP Block list, or both.</span></span>

   <span data-ttu-id="97aea-134">若要创建这些列表, ![请单击](media/ITPro-EAC-AddIcon.gif)"添加图标"。</span><span class="sxs-lookup"><span data-stu-id="97aea-134">To create these lists, click ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="97aea-135">重复此过程以添加其他地址。</span><span class="sxs-lookup"><span data-stu-id="97aea-135">In the subsequent dialog box, specify the IP address or address range, and then click **ok**.</span></span> <span data-ttu-id="97aea-136">（您还可以在添加完 IP 地址后编辑或删除它们。</span><span class="sxs-lookup"><span data-stu-id="97aea-136">Repeat this process to add additional addresses.</span></span> <span data-ttu-id="97aea-137">）</span><span class="sxs-lookup"><span data-stu-id="97aea-137">(You can also edit or remove IP addresses after they have been added.)</span></span>

   <span data-ttu-id="97aea-138">以 nnn 的格式指定 IPV4 IP 地址。 nnn 为0到255之间的数字。</span><span class="sxs-lookup"><span data-stu-id="97aea-138">Specify IPV4 IP addresses in the format nnn.nnn.nnn.nnn where nnn is a number from 0 to 255.</span></span> <span data-ttu-id="97aea-139">您也可以采用 nnn.nnn.nnn.nnn/rr 格式指定无类别域际路由选择 (CIDR) 的范围，其中 rr 代表 24 至 32 的任意数字。</span><span class="sxs-lookup"><span data-stu-id="97aea-139">You can also specify Classless Inter-Domain Routing (CIDR) ranges in the format nnn.nnn.nnn.nnn/rr where rr is a number from 24 to 32.</span></span> <span data-ttu-id="97aea-140">若要指定从24至32范围之外的范围, 请参阅下一节:[配置 IP 允许列表时的其他注意事项](#additional-considerations-when-configuring-ip-allow-lists)。</span><span class="sxs-lookup"><span data-stu-id="97aea-140">To specify ranges outside of the 24 to 32 range, see the next section, [Additional considerations when configuring IP Allow lists](#additional-considerations-when-configuring-ip-allow-lists).</span></span>

   > [!NOTE]
   > <span data-ttu-id="97aea-141">如果将 IP 地址添加到两个列表中, 则允许从该 IP 地址发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="97aea-141">If you add an IP address to both lists, email sent from that IP address is allowed.</span></span> <br/><br/> <span data-ttu-id="97aea-p112">您最多可以指定 1273 个条目，条目可以是单个 IP 地址或 IP 地址的 CIDR 范围（从 /24 到 /32）。</span><span class="sxs-lookup"><span data-stu-id="97aea-p112">You can specify a maximum of 1273 entries, where an entry is either a single IP address or a CIDR range of IP addresses from /24 to /32. </span></span><br/><br/> <span data-ttu-id="97aea-143">如果要发送 TLS 加密邮件, 则不支持 IPv6 地址和地址范围。</span><span class="sxs-lookup"><span data-stu-id="97aea-143">If you're sending TLS-encrypted messages, IPv6 addresses and address ranges are not supported.</span></span>
  
3. <span data-ttu-id="97aea-144">（可选）选中“启用安全列表”\*\*\*\* 复选框，防止漏掉某些已知发件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="97aea-144">Optionally, select the **Enable safe list** check box to prevent missing email from certain well-known senders.</span></span> <span data-ttu-id="97aea-145">如何操作？</span><span class="sxs-lookup"><span data-stu-id="97aea-145">How?</span></span> <span data-ttu-id="97aea-146">Microsoft 订阅到第三方受信任发件人来源。</span><span class="sxs-lookup"><span data-stu-id="97aea-146">Microsoft subscribes to third-party sources of trusted senders.</span></span> <span data-ttu-id="97aea-147">使用此安全列表意味着这些信任的发件人不会被错误地标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="97aea-147">Using this safe list means that these trusted senders aren't mistakenly marked as spam.</span></span> <span data-ttu-id="97aea-148">我们建议选择此选项, 因为它应减少您收到的误报数 (作为垃圾邮件分类的邮件)。</span><span class="sxs-lookup"><span data-stu-id="97aea-148">We recommend selecting this option because it should reduce the number of false positives (good mail that's classified as spam) that you receive.</span></span> 

4. <span data-ttu-id="97aea-p114">单击“保存”\*\*\*\*。右侧窗格中将会显示默认策略设置的摘要。</span><span class="sxs-lookup"><span data-stu-id="97aea-p114">Click **save**. A summary of your default policy settings appears in the right pane.</span></span>

## <a name="additional-considerations-when-configuring-ip-allow-lists"></a><span data-ttu-id="97aea-151">配置 IP 允许列表时的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="97aea-151">Additional considerations when configuring IP Allow lists</span></span>

<span data-ttu-id="97aea-152">以下是在配置 IP 允许列表时需要考虑或应该注意的其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="97aea-152">The following are additional considerations you may want to consider or that you should be aware of when configuring an IP Allow list.</span></span>
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a><span data-ttu-id="97aea-153">指定超出建议范围的 CIDR 范围</span><span class="sxs-lookup"><span data-stu-id="97aea-153">Specifying a CIDR range that falls outside of the recommended range</span></span>

<span data-ttu-id="97aea-154">若要指定从/1 到/23 的 CIDR IP 地址范围, 必须创建一个邮件流规则, 该规则在设置垃圾邮件可信度 (SCL) 的 IP 地址范围上运行, 以**绕过垃圾邮件筛选**(意味着从该 IP 地址范围内接收的所有邮件都是设置为 "非垃圾邮件"), 并且服务不执行其他筛选。</span><span class="sxs-lookup"><span data-stu-id="97aea-154">To specify a CIDR IP address range from /1 to /23, you must create a mail flow rule that operates on the IP address range that sets the spam confidence level (SCL) to **Bypass spam filtering** (meaning that all messages received from within this IP address range are set to "not spam") and no additional filtering is performed by the service).</span></span> <span data-ttu-id="97aea-155">但是, 如果这些 IP 地址中的任何一个出现在任何 Microsoft 的专用阻止列表或任何第三方阻止列表中, 则这些邮件仍将被阻止。</span><span class="sxs-lookup"><span data-stu-id="97aea-155">However, if any of these IP addresses appear on any of Microsoft's proprietary block lists or on any of our third-party block lists, these messages will still be blocked.</span></span> <span data-ttu-id="97aea-156">因此, 强烈建议使用/24 to/32 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="97aea-156">It is therefore strongly recommended that you use the /24 to /32 IP address range.</span></span>
  
<span data-ttu-id="97aea-157">若要创建此邮件流规则, 请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="97aea-157">To create this mail flow rule, perform the following steps.</span></span>
  
1. <span data-ttu-id="97aea-158">在 EAC 中, 导航到 "**邮件流** \> "**规则**。</span><span class="sxs-lookup"><span data-stu-id="97aea-158">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="97aea-159">单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="97aea-159">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="97aea-160">为该规则命名，然后单击“更多选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="97aea-160">Give the rule a name and then click **More options**.</span></span>

4. <span data-ttu-id="97aea-161">在“应用此规则的条件”\*\*\*\* 下，选择“发件人”\*\*\*\*，然后选择“IP 地址处于这些范围之内或准确匹配”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="97aea-161">Under **Apply this rule if**, select **The sender** and then choose **IP address is in any of these ranges or exactly matches**.</span></span>

5. <span data-ttu-id="97aea-162">在 "**指定 ip 地址**" 中, 指定 ip 地址范围, \*\*\*\* ![单击 "添加](media/ITPro-EAC-AddIcon.gif)" "添加图标", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="97aea-162">In the **specify IP addresses**, specify the IP address range, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **ok**.</span></span>

6. <span data-ttu-id="97aea-p116">在“执行以下操作”\*\*\*\* 框下，通过选择“修改邮件属性”\*\*\*\* 和“设置垃圾邮件可信度 (SCL)”\*\*\*\* 来设置操作。在“指定 SCL”\*\*\*\* 框中，选择“绕过垃圾邮件筛选”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="97aea-p116">Under **Do the following** box, set the action by choosing **Modify the message properties** and then **set the spam confidence level (SCL)**. In the **specify SCL** box, select **Bypass spam filtering**, and click **ok**.</span></span>

7. <span data-ttu-id="97aea-165">如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。</span><span class="sxs-lookup"><span data-stu-id="97aea-165">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="97aea-166">我们建议首先在一段时间内测试规则，然后再强制应用。</span><span class="sxs-lookup"><span data-stu-id="97aea-166">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="97aea-167">[Exchange Server 中的邮件流规则的过程](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)包含有关这些选择的详细信息。</span><span class="sxs-lookup"><span data-stu-id="97aea-167">[Procedures for mail flow rules in Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) contains more information about these selections.</span></span>

8. <span data-ttu-id="97aea-168">单击 "**保存**" 以保存该规则。</span><span class="sxs-lookup"><span data-stu-id="97aea-168">Click **save** to save the rule.</span></span> <span data-ttu-id="97aea-169">规则将显示在规则列表中。</span><span class="sxs-lookup"><span data-stu-id="97aea-169">The rule appears in your list of rules.</span></span>

<span data-ttu-id="97aea-170">创建并强制执行规则后, 服务将绕过您指定的 IP 地址范围的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="97aea-170">After you create and enforce the rule, the service bypasses spam filtering for the IP address range you specified.</span></span>

### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a><span data-ttu-id="97aea-171">为特定域设置 IP 允许列表例外作用域</span><span class="sxs-lookup"><span data-stu-id="97aea-171">Scoping an IP Allow list exception for a specific domain</span></span>

<span data-ttu-id="97aea-172">通常情况下，我们建议您将您认为对于所有域而言安全的 IP 地址（或 IP 地址范围）添加到 IP 允许列表。</span><span class="sxs-lookup"><span data-stu-id="97aea-172">In general, we recommend that you add the IP addresses (or IP address ranges) for all your domains that you consider safe to the IP Allow list.</span></span> <span data-ttu-id="97aea-173">但是, 如果您不希望您的 IP 允许列表条目应用于您的所有域, 则可以创建 excepts 特定域的邮件流规则 (也称为传输规则)。</span><span class="sxs-lookup"><span data-stu-id="97aea-173">However, if you don't want your IP Allow List entry to apply to all your domains, you can create a mail flow rule (also known as a transport rule) that excepts specific domains.</span></span>
  
<span data-ttu-id="97aea-174">例如，让我们假设您有三个域：ContosoA.com、ContosoB.com 和 ContosoC.com，您希望添加 IP 地址（为了简便起见，我们使用 1.2.3.4），并且只针对域 ContosoB.com 跳过筛选。</span><span class="sxs-lookup"><span data-stu-id="97aea-174">For example, let's say you have three domains: ContosoA.com, ContosoB.com, and ContosoC.com, and you want to add the IP address (for simplicity's sake, let's use 1.2.3.4) and skip filtering only for domain ContosoB.com.</span></span> <span data-ttu-id="97aea-175">您可以为 1.2.3.4 创建 IP 允许列表，它会将所有域的垃圾邮件可信度 (SCL) 设置为 -1（意味着它被分类为非垃圾邮件）。</span><span class="sxs-lookup"><span data-stu-id="97aea-175">You would create an IP Allow list for 1.2.3.4, which sets the spam confidence level (SCL) to -1 (meaning it is classified as non-spam) for all domains.</span></span> <span data-ttu-id="97aea-176">然后, 您可以创建邮件流规则, 将除 ContosoB.com 之外的所有域的 SCL 设置为0。</span><span class="sxs-lookup"><span data-stu-id="97aea-176">You can then create a mail flow rule that sets the SCL for all domains except ContosoB.com to 0.</span></span> <span data-ttu-id="97aea-177">这将使与该 IP 地址相关、除 ContosoB.com（在规则中被列为例外的域）之外的所有域的邮件被重新扫描。</span><span class="sxs-lookup"><span data-stu-id="97aea-177">This results in the message being rescanned for all domains associated with the IP address except for ContosoB.com which is the domain listed as the exception in the rule.</span></span> <span data-ttu-id="97aea-178">ContosoB.com 的 SCL 仍为 -1，这意味着它将跳过筛选，而 ContosoA.com 和 ContosoC.com 的 SCL 为 0，这意味着内容筛选器将重新扫描它们。</span><span class="sxs-lookup"><span data-stu-id="97aea-178">ContosoB.com still has an SCL of -1 which means skip filtering, whereas ContosoA.com and ContosoC.com have SCLs of 0, meaning they will be rescanned by the content filter.</span></span>
  
<span data-ttu-id="97aea-179">为此，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="97aea-179">To do this, perform the following steps:</span></span>
  
1. <span data-ttu-id="97aea-180">在 EAC 中, 导航到 "**邮件流** \> "**规则**。</span><span class="sxs-lookup"><span data-stu-id="97aea-180">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="97aea-181">单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="97aea-181">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="97aea-182">为该规则命名，然后单击“更多选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="97aea-182">Give the rule a name and then click **More options**.</span></span>

4. <span data-ttu-id="97aea-183">在“应用此规则的条件”\*\*\*\* 下，选择“发件人”\*\*\*\*，然后选择“IP 地址处于这些范围之内或准确匹配”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="97aea-183">Under **Apply this rule if**, select **The sender** and then choose **IP address is in any of these ranges or exactly matches**.</span></span>

5. <span data-ttu-id="97aea-184">在 "**指定 ip 地址**" 框中, 指定在 ip 允许列表中输入的 ip 地址或 ip 地址范围, \*\*\*\* ![单击 "添加](media/ITPro-EAC-AddIcon.gif)" "添加" 图标, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="97aea-184">In the **specify IP addresses** box, specify the IP address or IP address range you entered in the IP Allow list, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif), and then click **OK**.</span></span>

6. <span data-ttu-id="97aea-185">在 "**执行以下**操作" 下, 通过选择 **"修改邮件属性**", 然后**设置垃圾邮件可信度 (SCL)** 来设置操作。</span><span class="sxs-lookup"><span data-stu-id="97aea-185">Under **Do the following**, set the action by choosing **Modify the message properties** and then **Set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="97aea-186">在 "**指定 SCL** " 框中, 选择 " **0**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="97aea-186">In the **Specify SCL** box, select **0**, and click **OK**.</span></span>

7. <span data-ttu-id="97aea-187">单击 "**添加例外**", 并在 "**除非**" 下选择 **"发件人"** , 然后选择 "**域为**"。</span><span class="sxs-lookup"><span data-stu-id="97aea-187">Click **Add exception**, and under **Except if**, select **The sender** and choose **domain is**.</span></span>

8. <span data-ttu-id="97aea-188">在 "**指定域**" 框中, 输入要绕过垃圾邮件筛选的域, 例如**contosob.com**。</span><span class="sxs-lookup"><span data-stu-id="97aea-188">In the **Specify domain** box, enter the domain for which you want to bypass spam filtering, such as **contosob.com**.</span></span> <span data-ttu-id="97aea-189">单击 "**添加** !["](media/ITPro-EAC-AddIcon.gif)图标将其移动到短语列表。</span><span class="sxs-lookup"><span data-stu-id="97aea-189">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) to move it to the list of phrases.</span></span> <span data-ttu-id="97aea-190">如果要添加其他域作为例外，请重复此步骤，然后在完成时单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="97aea-190">Repeat this step if you want to add additional domains as exceptions, and click **ok** when you are finished.</span></span> 

9. <span data-ttu-id="97aea-191">如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。</span><span class="sxs-lookup"><span data-stu-id="97aea-191">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="97aea-192">我们建议首先在一段时间内测试规则，然后再强制应用。</span><span class="sxs-lookup"><span data-stu-id="97aea-192">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="97aea-193">[Exchange Server 中的邮件流规则的过程](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)包含有关这些选择的详细信息。</span><span class="sxs-lookup"><span data-stu-id="97aea-193">[Procedures for mail flow rules in Exchange Server](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) contains more information about these selections.</span></span>

10. <span data-ttu-id="97aea-194">单击 "**保存**" 以保存该规则。</span><span class="sxs-lookup"><span data-stu-id="97aea-194">Click **Save** to save the rule.</span></span> <span data-ttu-id="97aea-195">规则将显示在规则列表中。</span><span class="sxs-lookup"><span data-stu-id="97aea-195">The rule appears in your list of rules.</span></span>

<span data-ttu-id="97aea-196">在创建和强制应用规则后，仅为您输入的例外的域绕过指定 IP 地址或 IP 地址范围的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="97aea-196">After you create and enforce the rule, spam filtering for the IP address or IP address range you specified is bypassed only for the domain exception you entered.</span></span>

### <a name="scenarios-where-allowed-ip-addresses-are-still-filtered"></a><span data-ttu-id="97aea-197">仍在其中筛选允许的 IP 地址的方案</span><span class="sxs-lookup"><span data-stu-id="97aea-197">Scenarios where allowed IP addresses are still filtered</span></span>

<span data-ttu-id="97aea-198">在下列情况下, 来自已在连接筛选器策略中配置的来自允许的 IP 地址的邮件仍将受到垃圾邮件筛选:</span><span class="sxs-lookup"><span data-stu-id="97aea-198">Messages from allowed IP addresses that you've configured in connection filter policies are still subject to spam filtering in the following scenarios:</span></span>

- <span data-ttu-id="97aea-199">您的连接筛选器策略中的源 IP 地址也是在*任何*租户 (让我们称之为租户 a) 中的本地基于 IP 的入站连接器中配置的\*\*\*\* , 并在第一次遇到的租户 a 和 Exchange Online Protection 服务器上进行配置Office 365 中的消息都发生在 Microsoft 数据中心中的同一 Active Directory 林中。</span><span class="sxs-lookup"><span data-stu-id="97aea-199">The source IP address in your connection filter policy is also configured in an on-premises, IP-based inbound connector in *any* tenant (let's call this Tenant A), **and** Tenant A and the Exchange Online Protection server that first encounters the message in Office 365 both happen to be in the same Active Directory forest in the Microsoft datacenters.</span></span> <span data-ttu-id="97aea-200">在这种情况下, **IPV: CAL**将添加到邮件的[反垃圾邮件邮件头](anti-spam-message-headers.md)(指示邮件绕过垃圾邮件筛选), 但邮件仍受垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="97aea-200">In this scenario, **IPV:CAL** is added to the message's [anti-spam message headers](anti-spam-message-headers.md) (indicating the message bypassed spam filtering), but the message is still subject to spam filtering.</span></span>

- <span data-ttu-id="97aea-201">你的租户 (在其中配置了连接筛选器策略) 和在 Office 365 中首次遇到此邮件的 Exchange Online Protection 服务器在 Microsoft 数据中心的不同 Active Directory 林中都是如此。</span><span class="sxs-lookup"><span data-stu-id="97aea-201">Your tenant (where you've configured the connection filter policy) and the Exchange Online Protection server that first encounters the message in Office 365 both happen to be in different Active Directory forests in the Microsoft datacenters.</span></span> <span data-ttu-id="97aea-202">在这种情况下, **IPV: CAL**不会添加到邮件头中, 因此邮件仍受垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="97aea-202">In this scenario, **IPV:CAL** is not added to the message headers, so the message is still subject to spam filtering.</span></span>

<span data-ttu-id="97aea-203">如果遇到上述任一情况, 可以在 EAC 中创建邮件流规则和 (至少) 以下设置, 以确保来自 IP 地址或地址绕过垃圾邮件筛选的邮件:</span><span class="sxs-lookup"><span data-stu-id="97aea-203">If you encounter either of these scenarios, you can create a mail flow rule in the EAC with (at a minimum) the following settings to ensure messages from the IP address or addresses bypass spam filtering:</span></span>

- <span data-ttu-id="97aea-204">\>规则条件: 如果**发件人** \> **IP 地址为任意一种范围或完全匹配** \> (IP 地址或地址), 则**应用此规则**。</span><span class="sxs-lookup"><span data-stu-id="97aea-204">Rule condition: **Apply this rule if** \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (your IP address or addresses).</span></span>

- <span data-ttu-id="97aea-205">规则操作:**修改邮件属性** \> **设置垃圾邮件信任级别 (SCL)** \> **绕过垃圾邮件筛选**。</span><span class="sxs-lookup"><span data-stu-id="97aea-205">Rule action: **Modify the message properties** \> **Set the spam confidence level (SCL)** \> **Bypass spam filtering**.</span></span>

<span data-ttu-id="97aea-206">这基本上是与以前的作用域相同的规则创建过程[特定域部分的 IP 允许列表例外](#scoping-an-ip-allow-list-exception-for-a-specific-domain)。</span><span class="sxs-lookup"><span data-stu-id="97aea-206">This is basically the same rule creation procedure from the previous [Scoping an IP Allow list exception for a specific domain](#scoping-an-ip-allow-list-exception-for-a-specific-domain) section.</span></span>

## <a name="new-to-office-365"></a><span data-ttu-id="97aea-207">刚开始接触 Office 365？</span><span class="sxs-lookup"><span data-stu-id="97aea-207">New to Office 365?</span></span>

||
|:-----|
|<span data-ttu-id="97aea-208">![LinkedIn Learning 短图标](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **刚开始接触 Office 365？**</span><span class="sxs-lookup"><span data-stu-id="97aea-208">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**</span></span> <span data-ttu-id="97aea-209">发现 LinkedIn Learning 向 **Office 365 admins and IT pros**提供的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="97aea-209">Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|

## <a name="for-more-information"></a><span data-ttu-id="97aea-210">详细信息</span><span class="sxs-lookup"><span data-stu-id="97aea-210">For more information</span></span>

[<span data-ttu-id="97aea-211">Exchange Online 中的安全发件人和阻止发件人列表</span><span class="sxs-lookup"><span data-stu-id="97aea-211">Safe sender and blocked sender lists in Exchange Online</span></span>](safe-sender-and-blocked-sender-lists-faq.md)
  
[<span data-ttu-id="97aea-212">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="97aea-212">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="97aea-213">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="97aea-213">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="97aea-214">如何帮助确保邮件不会标记为垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="97aea-214">How to help ensure that a message isn't marked as spam</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[<span data-ttu-id="97aea-215">使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题</span><span class="sxs-lookup"><span data-stu-id="97aea-215">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534225)

---
title: 反垃圾邮件邮件头
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/9/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
description: Exchange Online Protection 扫描到入站电子邮件时，它会在每封邮件中插入" **X-Forefront-Antispam-Report**"标头。
ms.openlocfilehash: 7baa15f4d687c809d45461a135f64f0d18f49a7f
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026499"
---
# <a name="anti-spam-message-headers"></a><span data-ttu-id="cca79-103">反垃圾邮件邮件头</span><span class="sxs-lookup"><span data-stu-id="cca79-103">Anti-spam message headers</span></span>

<span data-ttu-id="cca79-p101">Exchange Online Protection 扫描到入站电子邮件时，它会在每封邮件中插入" **X-Forefront-Antispam-Report**"标头。该邮件头中的这些字段有助于为管理员提供与邮件及其处理方式有关的信息。" **X-Microsoft-Antispam**"标头中的字段提供批量邮件和网络钓鱼的更多信息。除这两种标头外，Exchange Online Protection 还会在" **Authentication-results**"标头中为每封邮件插入其处理的电子邮件身份验证结果。</span><span class="sxs-lookup"><span data-stu-id="cca79-p101">When Exchange Online Protection scans an inbound email message it inserts the **X-Forefront-Antispam-Report** header into each message. The fields in this header can help provide administrators with information about the message and about how it was processed. The fields in the **X-Microsoft-Antispam** header provide additional information about bulk mail and phishing. In addition to these two headers, Exchange Online Protection also inserts email authentication results for each message it processes in the **Authentication-results** header.</span></span> 
  
> [!TIP]
> <span data-ttu-id="cca79-p102">有关如何查看各种电子邮件客户端中的电子邮件头的信息，请参阅[邮件头分析器](https://go.microsoft.com/fwlink/p/?LinkId=306583)。你可以将邮件头的内容复制并粘贴到[邮件头分析器](https://testconnectivity.microsoft.com/?tabid=mha)工具中。当你在 Exchange 管理中心隔离邮箱中选择一封邮件时，" **查看邮件头**"链接也使你可以轻松地将邮件头文本复制并粘贴到工具中。进入邮件头分析器工具后，单击" **分析标头**"以检索关于标头的信息。</span><span class="sxs-lookup"><span data-stu-id="cca79-p102">For information about how to view an email message header in various email clients, see [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583). You can copy and paste the contents of the message header into the [Message Header Analyzer](https://testconnectivity.microsoft.com/?tabid=mha) tool. When you select a message in the quarantine in the Exchange admin center, the **View message header** link also easily lets you copy and paste the message header text into the tool. Once in the Message Header Analyzer tool, click **Analyze headers** in order to retrieve information about the header.</span></span> 
  
## <a name="x-forefront-antispam-report-message-header-fields"></a><span data-ttu-id="cca79-112">X-Forefront-Antispam-Report 邮件标头字段</span><span class="sxs-lookup"><span data-stu-id="cca79-112">X-Forefront-Antispam-Report message header fields</span></span>
<span data-ttu-id="cca79-113"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="cca79-113"></span></span>

<span data-ttu-id="cca79-p103">获取邮件头信息后，搜索" **X-Forefront-Antispam-Report**"，然后查找这些字段。此标头中的其他字段专供 Microsoft 反垃圾邮件团队用于进行诊断。</span><span class="sxs-lookup"><span data-stu-id="cca79-p103">After accessing the message header information, search for **X-Forefront-Antispam-Report** and then look for these fields. Other fields in this header are used exclusively by the Microsoft anti-spam team for diagnostic purposes.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cca79-116">**标头字段**</span><span class="sxs-lookup"><span data-stu-id="cca79-116">**Header field**</span></span> <br/> |<span data-ttu-id="cca79-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="cca79-117">**Description**</span></span> <br/> |
|<span data-ttu-id="cca79-118">CIP：[IP 地址]</span><span class="sxs-lookup"><span data-stu-id="cca79-118">CIP: [IP address]</span></span>  <br/> |<span data-ttu-id="cca79-p104">连接 IP 地址。在连接筛选器中创建 IP 允许列表或 IP 阻止列表时，您可能需要指定此 IP 地址。有关详细信息，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p104">The connecting IP address. You may want to specify this IP address when creating an IP Allow list or an IP Block list in the connection filter. For more information, see [Configure the connection filter policy](configure-the-connection-filter-policy.md).  </span></span><br/> |
|<span data-ttu-id="cca79-122">CTRY</span><span class="sxs-lookup"><span data-stu-id="cca79-122">CTRY</span></span>  <br/> |<span data-ttu-id="cca79-p105">邮件与服务连接时所处的国家/地区。该值由连接 IP 地址决定，它可能与原始发送 IP 地址不同。</span><span class="sxs-lookup"><span data-stu-id="cca79-p105">The country from which the message connected to the service. This is determined by the connecting IP address, which may not be the same as the originating sending IP address.</span></span>  <br/> |
|<span data-ttu-id="cca79-125">LANG</span><span class="sxs-lookup"><span data-stu-id="cca79-125">LANG</span></span>  <br/> |<span data-ttu-id="cca79-126">邮件的编写语言，由国家/地区代码指定（例如，俄语的代码为 ru_RU）。</span><span class="sxs-lookup"><span data-stu-id="cca79-126">The language in which the message was written, as specified by the country code (for example, ru_RU for Russian).</span></span>  <br/> |
|<span data-ttu-id="cca79-127">SCL</span><span class="sxs-lookup"><span data-stu-id="cca79-127">SCL</span></span>  <br/> |<span data-ttu-id="cca79-p106">邮件的垃圾邮件可信度 (SCL) 值。有关这些值的详细解释信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p106">The Spam Confidence Level (SCL) value of the message. For more information about interpreting these values, see [Spam confidence levels](spam-confidence-levels.md).  </span></span><br/> |
|<span data-ttu-id="cca79-130">PCL</span><span class="sxs-lookup"><span data-stu-id="cca79-130">PCL</span></span>  <br/> |<span data-ttu-id="cca79-p107">邮件的网络钓鱼可能性等级 (PCL) 值。请参阅 [PCL](anti-spam-message-headers.md#PCL) 以查看有关 PCL 值的更多信息。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p107">The Phishing Confidence Level (PCL) value of the message. See [PCL](anti-spam-message-headers.md#PCL) for more information about PCL values.  </span></span><br/> |
|<span data-ttu-id="cca79-133">SRV:BULK</span><span class="sxs-lookup"><span data-stu-id="cca79-133">SRV:BULK</span></span>  <br/> |<span data-ttu-id="cca79-p108">邮件被标识为批量电子邮件。如果" **阻止所有批量电子邮件高级垃圾邮件筛选选项**"已启用，则相应的邮件会被标记为垃圾邮件。如果未启用，则该邮件只会在剩余筛选规则确定邮件是垃圾邮件时才被标记为垃圾邮件。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p108">The message was identified as a bulk email message. If the **Block all bulk email messages advanced spam filtering option** is enabled, it will be marked as spam. If it is not enabled, it will only be marked as spam if the rest of the filtering rules determine that the message is spam.  </span></span><br/> |
|<span data-ttu-id="cca79-137">SFV:SFE</span><span class="sxs-lookup"><span data-stu-id="cca79-137">SFV:SFE</span></span>  <br/> |<span data-ttu-id="cca79-138">由于邮件发送自个人的安全发件人列表上的地址，因此邮件会跳过筛选并得以通过。</span><span class="sxs-lookup"><span data-stu-id="cca79-138">Filtering was skipped and the message was let through because it was sent from an address on an individual's safe sender list.</span></span>  <br/> |
|<span data-ttu-id="cca79-139">SFV:BLK</span><span class="sxs-lookup"><span data-stu-id="cca79-139">SFV:BLK</span></span>  <br/> |<span data-ttu-id="cca79-140">由于邮件发送自个人的阻止的发件人名单上的地址，因此邮件会跳过筛选并得以阻止。</span><span class="sxs-lookup"><span data-stu-id="cca79-140">Filtering was skipped and the message was blocked because it was sent from an address on an individual's blocked sender list.</span></span>  <br/> <span data-ttu-id="cca79-141">**提示：** 若要详细了解最终用户如何创建安全发件人列表和阻止的发件人名单，请参阅 [阻止或允许（垃圾邮件设置）](https://go.microsoft.com/fwlink/p/?LinkId=294862)(OWA) 和[垃圾邮件筛选器概述](https://go.microsoft.com/fwlink/p/?LinkId=270065) (Outlook)。</span><span class="sxs-lookup"><span data-stu-id="cca79-141">**Tip:** For more information about how end users can create safe and blocked sender lists, see [Block or allow (junk email settings)](https://go.microsoft.com/fwlink/p/?LinkId=294862) (OWA) and [Overview of the Junk Email Filter](https://go.microsoft.com/fwlink/p/?LinkId=270065) (Outlook).</span></span>  <br/> |
|<span data-ttu-id="cca79-142">IPV:CAL</span><span class="sxs-lookup"><span data-stu-id="cca79-142">IPV:CAL</span></span>  <br/> |<span data-ttu-id="cca79-143">邮件已获得垃圾邮件筛选器的允许，因为 IP 地址已在连接筛选器的 IP 允许列表中指定。</span><span class="sxs-lookup"><span data-stu-id="cca79-143">The message was allowed through the spam filters because the IP address was specified in an IP Allow list in the connection filter.</span></span>  <br/> |
|<span data-ttu-id="cca79-144">IPV:NLI</span><span class="sxs-lookup"><span data-stu-id="cca79-144">IPV:NLI</span></span>  <br/> |<span data-ttu-id="cca79-145">IP 地址没有在任何 IP 信誉列表中列出。</span><span class="sxs-lookup"><span data-stu-id="cca79-145">The IP address was not listed on any IP reputation list.</span></span>  <br/> |
|<span data-ttu-id="cca79-146">SFV:SPM</span><span class="sxs-lookup"><span data-stu-id="cca79-146">SFV:SPM</span></span>  <br/> |<span data-ttu-id="cca79-147">邮件由内容筛选器标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="cca79-147">The message was marked as spam by the content filter.</span></span>  <br/> |
|<span data-ttu-id="cca79-148">SFV:SKS</span><span class="sxs-lookup"><span data-stu-id="cca79-148">SFV:SKS</span></span>  <br/> |<span data-ttu-id="cca79-p109">在内容筛选器处理之前，邮件被标记为垃圾邮件。这包括符合以下传输规则条件的邮件：自动将邮件标记为垃圾邮件并规避其他所有筛选。</span><span class="sxs-lookup"><span data-stu-id="cca79-p109">The message was marked as spam prior to being processed by the content filter. This includes messages where the message matched a Transport rule to automatically mark it as spam and bypass all additional filtering.</span></span>  <br/> |
|<span data-ttu-id="cca79-151">SFV:SKA</span><span class="sxs-lookup"><span data-stu-id="cca79-151">SFV:SKA</span></span>  <br/> |<span data-ttu-id="cca79-152">邮件已跳过筛选并已传递到收件箱，因为它匹配垃圾邮件筛选器策略中，如**发件人允许**列表中的允许列表。</span><span class="sxs-lookup"><span data-stu-id="cca79-152">The message skipped filtering and was delivered to the inbox because it matched an allow list in the spam filter policy, such as the **Sender allow** list.</span></span>  <br/> |
|<span data-ttu-id="cca79-153">SFV:SKB</span><span class="sxs-lookup"><span data-stu-id="cca79-153">SFV:SKB</span></span>  <br/> |<span data-ttu-id="cca79-154">邮件被标记为垃圾邮件，因为它符合垃圾邮件筛选器策略中的阻止列表，例如" **发件人阻止**"列表。</span><span class="sxs-lookup"><span data-stu-id="cca79-154">The message was marked as spam because it matched a block list in the spam filter policy, such as the **Sender block** list.</span></span>  <br/> |
|<span data-ttu-id="cca79-155">SFV:SKN</span><span class="sxs-lookup"><span data-stu-id="cca79-155">SFV:SKN</span></span>  <br/> |<span data-ttu-id="cca79-p110">在内容筛选器处理之前，邮件被标记为非垃圾邮件。这包括符合以下传输规则条件的邮件：自动将邮件标记为非垃圾邮件并绕过其他所有筛选。</span><span class="sxs-lookup"><span data-stu-id="cca79-p110">The message was marked as non-spam prior to being processed by the content filter. This includes messages where the message matched a transport rule to automatically mark it as non-spam and bypass all additional filtering.</span></span>  <br/> |
|<span data-ttu-id="cca79-158">SFV:SKI</span><span class="sxs-lookup"><span data-stu-id="cca79-158">SFV:SKI</span></span>  <br/> |<span data-ttu-id="cca79-159">与 SFV:SKN 类似，由于其他原因而导致邮件跳过筛选，例如该邮件是租户内的组织间电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cca79-159">Similar to SFV:SKN, the message skipped filtering for another reason such as being intra-organizational email within a tenant.</span></span>  <br/> |
|<span data-ttu-id="cca79-160">SFV:SKQ</span><span class="sxs-lookup"><span data-stu-id="cca79-160">SFV:SKQ</span></span>  <br/> |<span data-ttu-id="cca79-161">邮件从隔离区释放，并发送给目标收件人。</span><span class="sxs-lookup"><span data-stu-id="cca79-161">The message was released from the quarantine and was sent to the intended recipients.</span></span>  <br/> |
|<span data-ttu-id="cca79-162">SFV:NSPM</span><span class="sxs-lookup"><span data-stu-id="cca79-162">SFV:NSPM</span></span>  <br/> |<span data-ttu-id="cca79-163">邮件被标记为非垃圾邮件并发送给预期收件人。</span><span class="sxs-lookup"><span data-stu-id="cca79-163">The message was marked as non-spam and was sent to the intended recipients.</span></span>  <br/> |
|<span data-ttu-id="cca79-164">H:[helostring]</span><span class="sxs-lookup"><span data-stu-id="cca79-164">H: [helostring]</span></span>  <br/> |<span data-ttu-id="cca79-165">连接邮件服务器的 HELO 或 EHLO 字符串。</span><span class="sxs-lookup"><span data-stu-id="cca79-165">The HELO or EHLO string of the connecting mail server.</span></span>  <br/> |
|<span data-ttu-id="cca79-166">PTR:[ReverseDNS]</span><span class="sxs-lookup"><span data-stu-id="cca79-166">PTR: [ReverseDNS]</span></span>  <br/> |<span data-ttu-id="cca79-167">发送 IP 地址的 PTR 记录或指针记录，亦称为反向 DNS 地址。</span><span class="sxs-lookup"><span data-stu-id="cca79-167">The PTR record, or pointer record, of the sending IP address, also known as the reverse DNS address.</span></span>  <br/> |
|<span data-ttu-id="cca79-168">SFTY</span><span class="sxs-lookup"><span data-stu-id="cca79-168">SFTY</span></span>  <br/> | <span data-ttu-id="cca79-169">邮件标识为网络钓鱼并也将具有下列值之一标记：</span><span class="sxs-lookup"><span data-stu-id="cca79-169">The message was identified as phishing and will also be marked with one of the following values:</span></span>  <br/>  <span data-ttu-id="cca79-p111">9.1-默认值。邮件包含网络钓鱼 URL、 可能包含其他仿冒内容，或可能已被标记为网络钓鱼另一个邮件筛选器，如 Exchange 服务器的内部部署版本中继到 Office 365 邮件之前。</span><span class="sxs-lookup"><span data-stu-id="cca79-p111">9.1 - Default value. The message contains a phishing URL, may contain other phishing content, or may have been marked as phishing by another mail filter such as an on-premises version of Exchange Server before relaying the message to Office 365.</span></span>  <br/>  <span data-ttu-id="cca79-172">9.11-消息失败反欺骗检查其中在从的发送域： 页眉相同，或与，或属于同一组织为接收域。</span><span class="sxs-lookup"><span data-stu-id="cca79-172">9.11 - Message failed anti-spoofing checks where the sending domain in the From: header is the same as, or aligns with, or is part of the same organization as the receiving domain.</span></span>  <br/>  <span data-ttu-id="cca79-p112">9.21-消息失败反欺骗检查和发送域在从： 标头不进行身份验证。与 CompAuth 结合使用 （请参阅身份验证结果）。</span><span class="sxs-lookup"><span data-stu-id="cca79-p112">9.21 - Message failed anti-spoofing checks and the sending domain in the From: header does not authenticate. Used in combination with CompAuth (see Authentication-Results).</span></span>  <br/>  <span data-ttu-id="cca79-175">9.22-相同 9.21，只不过用户具有已被重写安全发件人。</span><span class="sxs-lookup"><span data-stu-id="cca79-175">9.22 - Same as 9.21, except that the user has a safe sender that was overridden.</span></span>  <br/>  <span data-ttu-id="cca79-176">9.23-相同 9.22，只不过组织具有允许的发件人或域已被重写的。</span><span class="sxs-lookup"><span data-stu-id="cca79-176">9.23 - Same as 9.22, except that the organization has an allowed sender or domain that was overridden.</span></span>  <br/>  <span data-ttu-id="cca79-177">9.24-9.23，相同的用户具有规则的 Exchange 邮件流已被重写。</span><span class="sxs-lookup"><span data-stu-id="cca79-177">9.24 - Same as 9.23, except that the user has an Exchange mail flow rule that was overridden.</span></span>  <br/> |
|<span data-ttu-id="cca79-178">X-CustomSpam：[ASFOption]</span><span class="sxs-lookup"><span data-stu-id="cca79-178">X-CustomSpam: [ASFOption]</span></span>  <br/> |<span data-ttu-id="cca79-p113">邮件匹配高级垃圾邮件筛选选项。例如， **X-customspam： 到远程站点的链接图像**表示**到远程站点的图像链接**ASF 选项是否相匹配。若要找出哪些 X 标头文本被添加为每个特定 ASF 选项，请参阅[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="cca79-p113">The message matched an advanced spam filtering  option. For example, **X-CustomSpam: Image links to remote sites** denotes that the **Image links to remote sites** ASF option was matched. To find out which X-header text is added for each specific ASF option, see [Advanced spam filtering  options](advanced-spam-filtering-asf-options.md).  </span></span><br/> |
   
## <a name="x-microsoft-antispam-message-header-fields"></a><span data-ttu-id="cca79-182">X-Microsoft-Antispam 邮件标头字段</span><span class="sxs-lookup"><span data-stu-id="cca79-182">X-Microsoft-Antispam message header fields</span></span>
<span data-ttu-id="cca79-183"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="cca79-183"></span></span>

<span data-ttu-id="cca79-p114">下表描述了" **X-Microsoft-Antispam**"邮件头中的有用字段。此标头中的其他字段专供 Microsoft 反垃圾邮件团队用于进行诊断。</span><span class="sxs-lookup"><span data-stu-id="cca79-p114">The following table describes useful fields in the **X-Microsoft-Antispam** message header. Other fields in this header are used exclusively by the Microsoft anti-spam team for diagnostic purposes.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cca79-186">**标头字段**</span><span class="sxs-lookup"><span data-stu-id="cca79-186">**Header field**</span></span> <br/> |<span data-ttu-id="cca79-187">**说明**</span><span class="sxs-lookup"><span data-stu-id="cca79-187">**Description**</span></span> <br/> |
|<span data-ttu-id="cca79-188">BCL</span><span class="sxs-lookup"><span data-stu-id="cca79-188">BCL</span></span>  <br/> |<span data-ttu-id="cca79-p115">邮件的批量投诉级别 (BCL)。有关详细信息，请参阅[批量投诉级别值](bulk-complaint-level-values.md)。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p115">The Bulk Complaint Level (BCL) of the message. For more information, see [Bulk Complaint Level values](bulk-complaint-level-values.md).  </span></span><br/> |
|<span data-ttu-id="cca79-191">PCL</span><span class="sxs-lookup"><span data-stu-id="cca79-191">PCL</span></span>  <br/> | <span data-ttu-id="cca79-192">邮件的网络钓鱼可能性等级 (PCL) 显示这是否为网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="cca79-192">The Phishing Confidence Level (PCL) of the message, which indicates whether it's a phishing message.</span></span>  <br/>  <span data-ttu-id="cca79-193">此状态会以下列其中一个数值返回：</span><span class="sxs-lookup"><span data-stu-id="cca79-193">This status can be returned as one of the following numerical values:</span></span>  <br/> <span data-ttu-id="cca79-194">**0-3** 邮件的内容不太可能是网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="cca79-194">**0-3** The message's content isn't likely to be phishing.</span></span>  <br/> <span data-ttu-id="cca79-195">**4-8** 邮件的内容可能是网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="cca79-195">**4-8** The message's content is likely to be phishing.</span></span>  <br/> <span data-ttu-id="cca79-196">**-9990** （仅限 Exchange Online Protection）邮件的内容可能是网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="cca79-196">**-9990** (Exchange Online Protection only) The message's content is likely to be phishing.</span></span>  <br/>  <span data-ttu-id="cca79-p116">这些值用于确定你的电子邮件客户端对这些邮件采取什么操作。例如，Microsoft Office Outlook 使用 PCL 标记阻止可疑邮件的内容。有关网络钓鱼和 Outlook 如何处理网络钓鱼邮件的详细信息，请参阅 [打开或关闭电子邮件中的链接](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8)。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p116">The values are used to determine what action your email client takes on messages. For example, Microsoft Office Outlook uses the PCL stamp to block the content of suspicious messages. For more information about phishing, and how Outlook processes phishing messages, see [Turn on or off links in email messages](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8).  </span></span><br/> |
   
## <a name="authentication-results-message-header"></a><span data-ttu-id="cca79-200">"Authentication-results"邮件头</span><span class="sxs-lookup"><span data-stu-id="cca79-200">Authentication-results message header</span></span>
<span data-ttu-id="cca79-201"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="cca79-201"></span></span>

<span data-ttu-id="cca79-202">邮件服务器收到电子邮件后，Office 365 将基于 SPF、DKIM 或 DMARC 将检查结果记录或标记在" **Authentication-results**"邮件头中。</span><span class="sxs-lookup"><span data-stu-id="cca79-202">The results of checks against SPF, DKIM, and DMARC are recorded, or stamped, by Office 365 in the **Authentication-results** message header when our mail servers receive an email message.</span></span> 
  
### <a name="check-stamp-syntax-and-examples"></a><span data-ttu-id="cca79-203">检查标记语法和示例</span><span class="sxs-lookup"><span data-stu-id="cca79-203">check stamp syntax and examples</span></span>
<span data-ttu-id="cca79-204"><a name="referenceSPFstamp"> </a></span><span class="sxs-lookup"><span data-stu-id="cca79-204"></span></span>

<span data-ttu-id="cca79-p117">以下语法示例演示了 Office 365 应用于每封电子邮件（在由我们的邮件服务器接收时执行电子邮件身份验证检查）的邮件头的部分文本"标记"。此标记已添加到" **Authentication-Results**"标头。</span><span class="sxs-lookup"><span data-stu-id="cca79-p117">The following syntax examples show a portion of the text "stamp" that Office 365 applies to the message header for each email that undergoes an email authentication check when it is received by our mail servers. The stamp is added to the **Authentication-Results** header.</span></span> 
  
 <span data-ttu-id="cca79-207">**语法：SPF 检查标记**</span><span class="sxs-lookup"><span data-stu-id="cca79-207">**Syntax: SPF check stamp**</span></span>
  
<span data-ttu-id="cca79-208">以下语法适用于 SPF。</span><span class="sxs-lookup"><span data-stu-id="cca79-208">For SPF, the following syntax applies.</span></span>
  
```
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

 <span data-ttu-id="cca79-209">**示例：SPF 检查标记**</span><span class="sxs-lookup"><span data-stu-id="cca79-209">**Examples: SPF check stamp**</span></span>
  
```
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com

```

 <span data-ttu-id="cca79-210">**语法：DKIM 检查标记**</span><span class="sxs-lookup"><span data-stu-id="cca79-210">**Syntax: DKIM check stamp**</span></span>
  
<span data-ttu-id="cca79-211">以下语法适用于 DKIMF。</span><span class="sxs-lookup"><span data-stu-id="cca79-211">For DKIM, the following syntax applies.</span></span>
  
```
dkim=<pass|fail (reason)|none> header.d=<domain>
```

 <span data-ttu-id="cca79-212">**示例：DKIM 检查标记**</span><span class="sxs-lookup"><span data-stu-id="cca79-212">**Examples: DKIM check stamp**</span></span>
  
```
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

 <span data-ttu-id="cca79-213">**语法：DMARC 检查标记**</span><span class="sxs-lookup"><span data-stu-id="cca79-213">**Syntax: DMARC check stamp**</span></span>
  
<span data-ttu-id="cca79-214">以下语法适用于 DMARC。</span><span class="sxs-lookup"><span data-stu-id="cca79-214">For DMARC, the following syntax applies.</span></span>
  
```
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

 <span data-ttu-id="cca79-215">**示例：DMARC 检查标记**</span><span class="sxs-lookup"><span data-stu-id="cca79-215">**Examples: DMARC check stamp**</span></span>
  
```
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a><span data-ttu-id="cca79-216">Office 365 电子邮件身份验证使用的"Authentication-results"邮件头字段</span><span class="sxs-lookup"><span data-stu-id="cca79-216">Authentication-results message header fields used by Office 365 email authentication</span></span>
<span data-ttu-id="cca79-217"><a name="referenceSPFstamp"> </a></span><span class="sxs-lookup"><span data-stu-id="cca79-217"></span></span>

<span data-ttu-id="cca79-218">本表描述了每封电子邮件身份验证检查的字段和可能的值。</span><span class="sxs-lookup"><span data-stu-id="cca79-218">This table describes the fields and possible values for each email authentication check.</span></span>
  
|<span data-ttu-id="cca79-219">**标头字段**</span><span class="sxs-lookup"><span data-stu-id="cca79-219">**Header field**</span></span>|<span data-ttu-id="cca79-220">**说明**</span><span class="sxs-lookup"><span data-stu-id="cca79-220">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cca79-221">spf</span><span class="sxs-lookup"><span data-stu-id="cca79-221">spf</span></span>  <br/> | <span data-ttu-id="cca79-p118">说明邮件的 SPF 检查结果。可能的值包括：  </span><span class="sxs-lookup"><span data-stu-id="cca79-p118">Describes the results of the SPF check for the message. Possible values include:  </span></span><br/> <span data-ttu-id="cca79-p119">" **pass (IP address)**"指示邮件通过 SPF 检查，且其中包括发件人的 IP 地址。已授权客户端代表发件人的域发送或中继电子邮件。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p119">**pass (IP address)** indicates the SPF check for the message passed and includes the sender's IP address. The client is authorized to send or relay email on behalf of the sender's domain.  </span></span><br/> <span data-ttu-id="cca79-p120">" **fail (IP address)**"指示邮件未通过 SPF 检查，且其中包括发件人的 IP 地址。有时也称其为硬失败。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p120">**fail (IP address)** indicates the SPF check for the message failed and includes the sender's IP address. This is sometimes called hard fail.  </span></span><br/> <span data-ttu-id="cca79-228">" **softfail (reason)**"指示 SPF 记录已将主机指定为不允许发送但正处于转换状态。</span><span class="sxs-lookup"><span data-stu-id="cca79-228">**softfail (reason)** indicates that the SPF record has designated the host as not being allowed to send but is in transition.</span></span>  <br/> <span data-ttu-id="cca79-229">" **neutral**"指示 SPF 记录已明确表明 其不断言 IP 地址是否获得授权。</span><span class="sxs-lookup"><span data-stu-id="cca79-229">**neutral** indicates that the SPF record has explicitly stated that it is not asserting whether the IP address is authorized.</span></span>  <br/> <span data-ttu-id="cca79-230">" **none**"指示域没有 SPF 记录或 SPF 记录未生成结果。</span><span class="sxs-lookup"><span data-stu-id="cca79-230">**none** indicates that the domain does not have an SPF record or the SPF record does not evaluate to a result.</span></span>  <br/> <span data-ttu-id="cca79-p121">" **temperror**"指示遇到的错误实际上可能是临时的，例如 DNS 错误。无需任何管理员操作，稍后再次尝试可能 就会成功。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p121">**temperror** indicates that an error has occurred that may be temporary in nature, for example, a DNS error. Trying again later might succeed without any administrator action.  </span></span><br/> <span data-ttu-id="cca79-p122">" **permerror**"指示已出现永久错误。例如，域的 SPF 记录格式非常不规范时会出现此值。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p122">**permerror** indicates that a permanent error has occurred. This happens when, for example, the domain has a badly formatted SPF record.  </span></span><br/> |
|<span data-ttu-id="cca79-235">smtp.mailfrom</span><span class="sxs-lookup"><span data-stu-id="cca79-235">smtp.mailfrom</span></span>  <br/> |<span data-ttu-id="cca79-p123">包含发送邮件的源域。此电子邮件的任何错误都将发送到负责此域的 postmaster 或实体。在邮件信封上有时也称其为"5321.MailFrom 地址"或"反向路径地址"。</span><span class="sxs-lookup"><span data-stu-id="cca79-p123">Contains the source domain from which the message was sent. Any errors about this email message will be sent to the postmaster or the entity responsible for the domain. This is sometimes called the 5321.MailFrom address or the reverse-path address on the message envelope.</span></span>  <br/> |
|<span data-ttu-id="cca79-239">dkim</span><span class="sxs-lookup"><span data-stu-id="cca79-239">dkim</span></span>  <br/> | <span data-ttu-id="cca79-p124">说明邮件的 DKIM 检查结果。可能的值包括：  </span><span class="sxs-lookup"><span data-stu-id="cca79-p124">Describes the results of the DKIM check for the message. Possible values include:  </span></span><br/> <span data-ttu-id="cca79-242">" **pass**"指示邮件通过 DMARC 检查。</span><span class="sxs-lookup"><span data-stu-id="cca79-242">**pass** indicates the DKIM check for the message passed.</span></span>  <br/> <span data-ttu-id="cca79-p125">" **fail (reason)**"指示邮件未通过 DMARC 检查及其原因。例如，如果邮件未签名或签名未经验证。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p125">**fail (reason)** indicates the DKIM check for the message failed and why. For example, if the message was not signed or the signature was not verified.  </span></span><br/> <span data-ttu-id="cca79-p126">" **none**"指示邮件未签名。这可能表示或不表示域存在 DKIM 记录或 DKIM 记录未生成结果，仅表示该邮件未签名。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p126">**none** indicates that the message was not signed. This may or may not indicate that the domain has a DKIM record or the DKIM record does not evaluate to a result, only that this message was not signed.  </span></span><br/> |
|<span data-ttu-id="cca79-247">header.d</span><span class="sxs-lookup"><span data-stu-id="cca79-247">header.d</span></span>  <br/> |<span data-ttu-id="cca79-p127">DKIM 签名中标识的域（如有）。这指的是 针对公钥查询的域。</span><span class="sxs-lookup"><span data-stu-id="cca79-p127">Domain identified in the DKIM signature if any. This is the domain that's queried for the public key.</span></span>  <br/> |
|<span data-ttu-id="cca79-250">dmarc</span><span class="sxs-lookup"><span data-stu-id="cca79-250">dmarc</span></span>  <br/> | <span data-ttu-id="cca79-p128">说明邮件的 DMARC 检查结果。可能的值包括：  </span><span class="sxs-lookup"><span data-stu-id="cca79-p128">Describes the results of the DMARC check for the message. Possible values include:  </span></span><br/> <span data-ttu-id="cca79-253">**pass** 指示邮件通过 DMARC 检查。</span><span class="sxs-lookup"><span data-stu-id="cca79-253">**pass** indicates the DMARC check for the message passed.</span></span>  <br/> <span data-ttu-id="cca79-254">**fail** 指示邮件未通过 DMARC 检查。</span><span class="sxs-lookup"><span data-stu-id="cca79-254">**fail** indicates the DMARC check for the message failed.</span></span>  <br/> <span data-ttu-id="cca79-p129">**bestguesspass** 指示不存在域的任何 DMARC TXT 记录，但如果已存在一个，邮件的 DMARC 检查就已通过。这是因为 5321.MailFrom 地址中的域与 5322.From 地址中的域相匹配。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p129">**bestguesspass** indicates that no DMARC TXT record for the domain exists, but if one had existed, the DMARC check for the message would have passed. This is because the domain in the 5321.MailFrom address matches the domain in the 5322.From address.  </span></span><br/> <span data-ttu-id="cca79-257">**none** 指示 DNS 中不存在发送域的任何 DKIM TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="cca79-257">**none** indicates that no DKIM TXT record exists for the sending domain in DNS.</span></span>  <br/> |
|<span data-ttu-id="cca79-258">action</span><span class="sxs-lookup"><span data-stu-id="cca79-258">action</span></span>  <br/> | <span data-ttu-id="cca79-p130">指示垃圾邮件筛选器基于 DMARC 检查结果执行的操作。例如：  </span><span class="sxs-lookup"><span data-stu-id="cca79-p130">Indicates the action taken by the spam filter based on the results of the DMARC check. For example:  </span></span><br/> <span data-ttu-id="cca79-p131">**permerror** DMARC 评估过程中出现的永久性错误，例如，在 DNS 中遇到格式不正确的 DMARC TXT 记录。尝试重新发送此邮件不太可能产生不同的结果。你反而可能需要联系域的所有者，以解决该问题。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p131">**permerror** A permanent error occurred during DMARC evaluation, such as encountering an incorrectly formed DMARC TXT record in DNS. Attempting to resend this message isn't likely to end with a different result. Instead, you may need to contact the domain's owner in order to resolve the issue.  </span></span><br/> <span data-ttu-id="cca79-p132">**temperror**DMARC 评估期间出现的临时错误。你可以请求发件人稍后重新发送邮件，以正确处理电子邮件。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p132">**temperror** A temporary error occurred during DMARC evaluation. You may be able to request that the sender resend the message later in order to process the email properly.  </span></span><br/> <span data-ttu-id="cca79-p133">**oreject**或 **o.reject**代表覆盖拒绝。在这种情况下，Office 365 在从 DMARC TXT 记录的策略为 p=reject 的域中接收未通过 DMARC 检查的邮件时使用此操作。Office 365 将该邮件标记为垃圾邮件，而不是删除或拒绝该邮件。有关这样配置 Office 365 的原因的详细信息，请参阅 [Office 365 如何处理未通过 DMARC 的入站电子邮件](use-dmarc-to-validate-email.md#inbounddmarcfail)。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p133">**oreject** or **o.reject** Stands for override reject. In this case Office 365 uses this action when it receives a message that fails the DMARC check from a domain whose DMARC TXT record has a policy of p=reject. Instead of deleting or rejecting the message, Office 365 marks the message as spam. For more information on why Office 365 is configured this way, see [How Office 365 handles inbound email that fails DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).  </span></span><br/> <span data-ttu-id="cca79-p134">**pct.quarantine** 指示未通过 DMARC 的邮件将按少于 100% 的比例以任意方式传递。这表示邮件未通过 DMARC 且已将策略设置为隔离，但 pct 字段未设置为 100% 且系统根据每个特定域的策略随机决定不执行 DMARC 操作。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p134">**pct.quarantine** Indicates that a percentage less than 100% of messages that do not pass DMARC will be delivered anyway. This means that the message failed DMARC and the policy was set to quarantine, but the pct field was not set to 100% and the system randomly determined not to apply the DMARC action, as per the specified domain's policy.  </span></span><br/> <span data-ttu-id="cca79-p135">**pct.reject** 指示未通过 DMARC 的邮件将按少于 100% 的比例以任意方式传递。这表示邮件未通过 DMARC 且已将策略设置为拒绝，但 pct 字段未设置为 100% 且系统根据每个特定域的策略随机决定不执行 DMARC 操作。  </span><span class="sxs-lookup"><span data-stu-id="cca79-p135">**pct.reject** Indicates that a percentage less than 100% of messages that do not pass DMARC will be delivered anyway. This means that the message failed DMARC and the policy was set to reject, but the pct field was not set to 100% and the system randomly determined not to apply the DMARC action, as per the specified domain's policy.  </span></span><br/> |
|<span data-ttu-id="cca79-274">header.from</span><span class="sxs-lookup"><span data-stu-id="cca79-274">header.from</span></span>  <br/> |<span data-ttu-id="cca79-p136">电子邮件标头中发件人地址的域。有时也称其为"5322.From 地址"。</span><span class="sxs-lookup"><span data-stu-id="cca79-p136">The domain of the From address in the email message header. This is sometimes called the 5322.From address.</span></span>  <br/> |
|<span data-ttu-id="cca79-277">compauth</span><span class="sxs-lookup"><span data-stu-id="cca79-277">compauth</span></span>  <br/> |<span data-ttu-id="cca79-p137">复合身份验证结果。由 Office 365 用于组合多个类型的身份验证，如 SPF、 DKIM、 DMARC 或任何其他部件的邮件以确定对邮件进行身份验证。使用 From： 域作为评估的基础。</span><span class="sxs-lookup"><span data-stu-id="cca79-p137">Composite authentication result. Used by Office 365 to combine multiple types of authentication such as SPF, DKIM, DMARC, or any other part of the message to determine whether or not the message is authenticated. Uses the From: domain as the basis of evaluation.</span></span>  <br/> |
|<span data-ttu-id="cca79-281">原因</span><span class="sxs-lookup"><span data-stu-id="cca79-281">reason</span></span>  <br/> | <span data-ttu-id="cca79-p138">原因复合身份验证通过或失败。原因的值由三个数字组成：</span><span class="sxs-lookup"><span data-stu-id="cca79-p138">The reason the composite authentication passed or failed. The value for the reason is made up of three digits:</span></span>  <br/>  <span data-ttu-id="cca79-p139">000-的消息显式失败的身份验证。例如，消息接收的隔离或拒绝操作 DMARC 失败。</span><span class="sxs-lookup"><span data-stu-id="cca79-p139">000 - The message explicitly failed authentication. For example, the message received a DMARC fail with an action of quarantine or reject.</span></span>  <br/>  <span data-ttu-id="cca79-p140">001-隐式消息失败的身份验证，并发送域未发布身份验证策略。例如，p DMARC 策略 = none。</span><span class="sxs-lookup"><span data-stu-id="cca79-p140">001 - The message implicitly failed authentication, and the sending domain did not publish authentication policies. For example, a DMARC policy of p=none.</span></span>  <br/>  <span data-ttu-id="cca79-p141">1xx-邮件传递身份验证。两个数字是内部使用的 Office 365 的代码。</span><span class="sxs-lookup"><span data-stu-id="cca79-p141">1xx - The message passed authentication. The second two digits are internal codes used by Office 365.</span></span>  <br/>  <span data-ttu-id="cca79-p142">2xx-消息软传递身份验证。两个数字是内部使用的 Office 365 的代码。</span><span class="sxs-lookup"><span data-stu-id="cca79-p142">2xx - The message soft-passed authentication. The second two digits are internal codes used by Office 365.</span></span>  <br/>  <span data-ttu-id="cca79-292">3xx-邮件未签复合身份验证。</span><span class="sxs-lookup"><span data-stu-id="cca79-292">3xx - The message was not checked for composite authentication.</span></span>  <br/>  <span data-ttu-id="cca79-p143">4xx-的消息被忽略复合身份验证。两个数字是内部使用的 Office 365 的代码。</span><span class="sxs-lookup"><span data-stu-id="cca79-p143">4xx - The message bypassed composite authentication. The second two digits are internal codes used by Office 365.</span></span>  <br/> |
  
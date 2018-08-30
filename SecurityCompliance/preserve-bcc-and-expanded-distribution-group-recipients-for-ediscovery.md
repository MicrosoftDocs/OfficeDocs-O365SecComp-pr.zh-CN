---
title: 为电子数据展示保存密件抄送和展开的通讯组收件人
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: 就地保留、 诉讼保留，和 Office 365 的保留策略允许您保留邮箱内容，以满足法规遵从性和电子数据展示要求。
ms.openlocfilehash: fe13884497db9e2549011815704c571c66a92476
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002831"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a><span data-ttu-id="543ab-103">为电子数据展示保存密件抄送和展开的通讯组收件人</span><span class="sxs-lookup"><span data-stu-id="543ab-103">Preserve Bcc and expanded distribution group recipients for eDiscovery</span></span>
  
<span data-ttu-id="543ab-p101">就地保留、 诉讼保留，和[Office 365 保留策略](http://go.microsoft.com/fwlink/?LinkID=827811)(在 Office 365 安全性中创建&amp;合规性中心) 允许您保留邮箱内容，以满足管理法规遵从性和电子数据展示要求。有关收件人信息直接解决收件人和抄送字段的默认情况下，所有邮件都包含一条消息，但您的组织可能需要能够搜索并重现的详细信息的邮件的所有收件人。这包括：</span><span class="sxs-lookup"><span data-stu-id="543ab-p101">In-Place Hold, Litigation Hold, and [Office 365 retention policies](http://go.microsoft.com/fwlink/?LinkID=827811) (created in the Office 365 Security &amp; Compliance Center) allow you to preserve mailbox content to meet regulatory compliance and eDiscovery requirements. Information about recipients directly addressed in the To and Cc fields of a message is included in all messages by default, but your organization may require the ability to search for and reproduce details about all recipients of a message. This includes:</span></span> 
  
- <span data-ttu-id="543ab-107">**使用邮件密件抄送字段输入地址的收件人：** 密件抄送收件人存储在发件人邮箱的邮件中，但不包含于发送给收件人的邮件标头中。</span><span class="sxs-lookup"><span data-stu-id="543ab-107">**Recipients addressed using the Bcc field of a message** Bcc recipients are stored in the message in the sender's mailbox, but not included in headers of the message delivered to recipients.</span></span> 
    
- <span data-ttu-id="543ab-108">**展开的通讯组收件人：** 接收此邮件的收件人，因为他们是以"收件人"、"抄送"或"密件抄送"字段在邮件中输入地址的通讯组成员。</span><span class="sxs-lookup"><span data-stu-id="543ab-108">**Expanded distribution group recipients** Recipients who receive the message because they're members of a distribution group to which the message was addressed, either in the To, Cc or Bcc fields.</span></span> 
    
<span data-ttu-id="543ab-p102">Exchange Online 和 Exchange Server 2013 （累积更新 7 和更高版本） 保留密件抄送和扩展的通讯组收件人信息。您可以通过使用 Exchange 管理中心 (EAC) 中的就地电子数据展示搜索或内容的搜索安全中搜索此信息&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="543ab-p102">Exchange Online and Exchange Server 2013 (Cumulative Update 7 and later versions) retain information about Bcc and expanded distribution group recipients. You can search for this information by using an In-Place eDiscovery search in the Exchange admin center (EAC) or a Content Search in the Security &amp; Compliance Center.</span></span> 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a><span data-ttu-id="543ab-111">如何保留密件抄送收件人和展开的通讯组收件人</span><span class="sxs-lookup"><span data-stu-id="543ab-111">How Bcc recipients and expanded distribution group recipients are preserved</span></span>
<span data-ttu-id="543ab-112"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="543ab-112"></span></span>

<span data-ttu-id="543ab-p103">如上文所述，密收件人信息存储为邮件发件人的邮箱中。此信息是索引并且适用于电子数据展示搜索和保留。</span><span class="sxs-lookup"><span data-stu-id="543ab-p103">As stated earlier, information about Bcc'ed recipients is stored with the message in the sender's mailbox. This information is indexed and available to eDiscovery searches and holds.</span></span> 
  
<span data-ttu-id="543ab-p104">有关扩展的通讯组收件人信息存储为邮件后您将邮箱置于就地保留或诉讼保留。Office 365 中的 Office 365 保留策略应用于邮箱时也存储此信息。在发送邮件时确定通讯组成员身份。为邮件存储的扩展的收件人列表不受对组成员资格的更改后发送邮件。</span><span class="sxs-lookup"><span data-stu-id="543ab-p104">Information about expanded distribution group recipients is stored with the message after you place a mailbox on In-Place Hold or Litigation Hold. In Office 365, this information is also stored when an Office 365 retention policy is applied to a mailbox. Distribution group membership is determined at the time the message is sent. The expanded recipients list stored with the message is not impacted by changes to membership of the group after the message is sent.</span></span> 
  
|<span data-ttu-id="543ab-119">**有关信息…**</span><span class="sxs-lookup"><span data-stu-id="543ab-119">**Information about…**</span></span>|<span data-ttu-id="543ab-120">**存储在...**</span><span class="sxs-lookup"><span data-stu-id="543ab-120">**Is stored in…**</span></span>|<span data-ttu-id="543ab-121">**默认情况下存储？**</span><span class="sxs-lookup"><span data-stu-id="543ab-121">**Is stored by default?**</span></span>|<span data-ttu-id="543ab-122">**可访问…**</span><span class="sxs-lookup"><span data-stu-id="543ab-122">**Is accessible to…**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="543ab-123">"收件人"和"抄送"收件人</span><span class="sxs-lookup"><span data-stu-id="543ab-123">To and Cc recipients</span></span>  <br/> |<span data-ttu-id="543ab-124">发件人和收件人邮箱中的邮件属性。</span><span class="sxs-lookup"><span data-stu-id="543ab-124">Message properties in the sender and recipients' mailboxes.</span></span>  <br/> |<span data-ttu-id="543ab-125">是</span><span class="sxs-lookup"><span data-stu-id="543ab-125">Yes</span></span>  <br/> |<span data-ttu-id="543ab-126">发件人、收件人和合规部主管</span><span class="sxs-lookup"><span data-stu-id="543ab-126">Sender, recipients, and compliance officers</span></span>  <br/> |
|<span data-ttu-id="543ab-127">密件抄送收件人</span><span class="sxs-lookup"><span data-stu-id="543ab-127">Bcc recipients</span></span>  <br/> |<span data-ttu-id="543ab-128">发件人邮箱中的邮件属性。</span><span class="sxs-lookup"><span data-stu-id="543ab-128">Message property in the sender's mailbox.</span></span>  <br/> |<span data-ttu-id="543ab-129">是</span><span class="sxs-lookup"><span data-stu-id="543ab-129">Yes</span></span>  <br/> |<span data-ttu-id="543ab-130">发件人和合规部主管</span><span class="sxs-lookup"><span data-stu-id="543ab-130">Sender and compliance officers</span></span>  <br/> |
|<span data-ttu-id="543ab-131">展开的通讯组收件人</span><span class="sxs-lookup"><span data-stu-id="543ab-131">Expanded distribution group recipients</span></span>  <br/> |<span data-ttu-id="543ab-132">发件人邮箱中的邮件属性。</span><span class="sxs-lookup"><span data-stu-id="543ab-132">Message properties in the sender's mailbox.</span></span>  <br/> |<span data-ttu-id="543ab-p105">不。扩展的通讯组收件人信息存储后邮箱置于就地保留或诉讼保留，或者分配给 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="543ab-p105">No. Expanded distribution group recipient information is stored after a mailbox is placed on In-Place Hold or Litigation Hold, or assigned to an Office 365 retention policy.</span></span>  <br/> |<span data-ttu-id="543ab-135">合规部主管</span><span class="sxs-lookup"><span data-stu-id="543ab-135">Compliance officers</span></span>  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a><span data-ttu-id="543ab-136">搜索发送给密件抄送以及展开的通讯组收件人的邮件</span><span class="sxs-lookup"><span data-stu-id="543ab-136">Searching for messages sent to Bcc and expanded distribution group recipients</span></span>
<span data-ttu-id="543ab-137"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="543ab-137"></span></span>

<span data-ttu-id="543ab-p106">在搜索发送给收件人的邮件时，目前，电子数据展示搜索结果包括发送给收件人为通讯组成员的邮件。下表显示的方案中，邮件发送至电子数据展示搜索中返回的密件抄送以及展开的通讯组收件人。</span><span class="sxs-lookup"><span data-stu-id="543ab-p106">When searching for messages sent to a recipient, eDiscovery search results now include messages sent to a distribution group that the recipient is a member of. The following table shows the scenarios where messages sent to Bcc and expanded distribution group recipients are returned in eDiscovery searches.</span></span>
  
<span data-ttu-id="543ab-p107">方案 1：John 是美国销售通讯组的成员。当 Bob 通过通讯组直接或间接发送一封邮件给 John 时，此表将显示电子数据展示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="543ab-p107">Scenario 1: John is a member of the US-Sales distribution group. This table shows eDiscovery search results when Bob sends a message to John directly or indirectly via a distribution group.</span></span>
  
|<span data-ttu-id="543ab-142">**当您在 Bob 的邮箱中搜索发送的邮件时…**</span><span class="sxs-lookup"><span data-stu-id="543ab-142">**When you search Bob's mailbox for messages sent…**</span></span>|<span data-ttu-id="543ab-143">**并与邮件一起发送…**</span><span class="sxs-lookup"><span data-stu-id="543ab-143">**And the message is sent with…**</span></span>|<span data-ttu-id="543ab-144">**结果包含邮件？**</span><span class="sxs-lookup"><span data-stu-id="543ab-144">**Results include message?**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="543ab-145">收件人：John</span><span class="sxs-lookup"><span data-stu-id="543ab-145">To:John</span></span>  <br/> |<span data-ttu-id="543ab-146">处于"收件人"中的 John</span><span class="sxs-lookup"><span data-stu-id="543ab-146">John on TO</span></span>  <br/> |<span data-ttu-id="543ab-147">是</span><span class="sxs-lookup"><span data-stu-id="543ab-147">Yes</span></span>  <br/> |
|<span data-ttu-id="543ab-148">收件人：John</span><span class="sxs-lookup"><span data-stu-id="543ab-148">To:John</span></span>  <br/> |<span data-ttu-id="543ab-149">处于"收件人"中的美国销售</span><span class="sxs-lookup"><span data-stu-id="543ab-149">US-Sales on TO</span></span>  <br/> |<span data-ttu-id="543ab-150">是</span><span class="sxs-lookup"><span data-stu-id="543ab-150">Yes</span></span>  <br/> |
|<span data-ttu-id="543ab-151">收件人：美国销售</span><span class="sxs-lookup"><span data-stu-id="543ab-151">To:US-Sales</span></span>  <br/> |<span data-ttu-id="543ab-152">处于"收件人"中的美国销售</span><span class="sxs-lookup"><span data-stu-id="543ab-152">US-Sales on TO</span></span>  <br/> |<span data-ttu-id="543ab-153">是</span><span class="sxs-lookup"><span data-stu-id="543ab-153">Yes</span></span>  <br/> |
|<span data-ttu-id="543ab-154">抄送：John</span><span class="sxs-lookup"><span data-stu-id="543ab-154">Cc:John</span></span>  <br/> |<span data-ttu-id="543ab-155">处于"抄送"中的 John</span><span class="sxs-lookup"><span data-stu-id="543ab-155">John on CC</span></span>  <br/> |<span data-ttu-id="543ab-156">是</span><span class="sxs-lookup"><span data-stu-id="543ab-156">Yes</span></span>  <br/> |
|<span data-ttu-id="543ab-157">抄送：John</span><span class="sxs-lookup"><span data-stu-id="543ab-157">Cc:John</span></span>  <br/> |<span data-ttu-id="543ab-158">处于"抄送"中的美国销售</span><span class="sxs-lookup"><span data-stu-id="543ab-158">US-Sales on CC</span></span>  <br/> |<span data-ttu-id="543ab-159">是</span><span class="sxs-lookup"><span data-stu-id="543ab-159">Yes</span></span>  <br/> |
|<span data-ttu-id="543ab-160">抄送：美国销售</span><span class="sxs-lookup"><span data-stu-id="543ab-160">Cc:US-Sales</span></span>  <br/> |<span data-ttu-id="543ab-161">处于"抄送"中的美国销售</span><span class="sxs-lookup"><span data-stu-id="543ab-161">US-Sales on CC</span></span>  <br/> |<span data-ttu-id="543ab-162">是</span><span class="sxs-lookup"><span data-stu-id="543ab-162">Yes</span></span>  <br/> |
   
<span data-ttu-id="543ab-p108">方案 2：Bob 发送一封电子邮件给 John（收件人/抄送）和 Jack（通过通讯组直接或间接密件抄送）。下表显示了电子数据展示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="543ab-p108">Scenario 2: Bob sends an email to John (To/Cc) and Jack (Bcc directly, or indirectly via a distribution group). The table below shows eDiscovery search results.</span></span>
  
|<span data-ttu-id="543ab-165">**当搜索…**</span><span class="sxs-lookup"><span data-stu-id="543ab-165">**When you search…**</span></span>|<span data-ttu-id="543ab-166">**对于发送的邮件…**</span><span class="sxs-lookup"><span data-stu-id="543ab-166">**For messages sent…**</span></span>|<span data-ttu-id="543ab-167">**结果包含邮件？**</span><span class="sxs-lookup"><span data-stu-id="543ab-167">**Results include message?**</span></span>|<span data-ttu-id="543ab-168">**注释**</span><span class="sxs-lookup"><span data-stu-id="543ab-168">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="543ab-169">Bob 的邮箱</span><span class="sxs-lookup"><span data-stu-id="543ab-169">Bob's mailbox</span></span>  <br/> |<span data-ttu-id="543ab-170">收件人/抄送：John</span><span class="sxs-lookup"><span data-stu-id="543ab-170">To/Cc:John</span></span>  <br/> |<span data-ttu-id="543ab-171">是</span><span class="sxs-lookup"><span data-stu-id="543ab-171">Yes</span></span>  <br/> |<span data-ttu-id="543ab-172">显示一个表明 Jack 被密件抄送的指示。</span><span class="sxs-lookup"><span data-stu-id="543ab-172">Presents an indication that Jack was Bcc'ed.</span></span>  <br/> |
|<span data-ttu-id="543ab-173">Bob 的邮箱</span><span class="sxs-lookup"><span data-stu-id="543ab-173">Bob's mailbox</span></span>  <br/> |<span data-ttu-id="543ab-174">密件抄送：Jack</span><span class="sxs-lookup"><span data-stu-id="543ab-174">Bcc:Jack</span></span>  <br/> |<span data-ttu-id="543ab-175">是</span><span class="sxs-lookup"><span data-stu-id="543ab-175">Yes</span></span>  <br/> |<span data-ttu-id="543ab-176">显示一个表明 Jack 被密件抄送的指示。</span><span class="sxs-lookup"><span data-stu-id="543ab-176">Presents an indication that Jack was Bcc'ed.</span></span>  <br/> |
|<span data-ttu-id="543ab-177">Bob 的邮箱</span><span class="sxs-lookup"><span data-stu-id="543ab-177">Bob's mailbox</span></span>  <br/> |<span data-ttu-id="543ab-178">密件抄送：Jack（通过通讯组）</span><span class="sxs-lookup"><span data-stu-id="543ab-178">Bcc:Jack (via distribution group)</span></span>  <br/> |<span data-ttu-id="543ab-179">是</span><span class="sxs-lookup"><span data-stu-id="543ab-179">Yes</span></span>  <br/> |<span data-ttu-id="543ab-180">发送邮件时会展开密件抄送通讯组成员列表，电子数据展示搜索结果预览、导出和日志中会显示此列表。</span><span class="sxs-lookup"><span data-stu-id="543ab-180">List of members of the Bcc'ed distribution group, expanded when the message was sent, is visible in eDiscovery search preview, export and logs.</span></span>  <br/> |
|<span data-ttu-id="543ab-181">John 的邮箱</span><span class="sxs-lookup"><span data-stu-id="543ab-181">John's mailbox</span></span>  <br/> |<span data-ttu-id="543ab-182">收件人/抄送：John</span><span class="sxs-lookup"><span data-stu-id="543ab-182">To/Cc:John</span></span>  <br/> |<span data-ttu-id="543ab-183">是</span><span class="sxs-lookup"><span data-stu-id="543ab-183">Yes</span></span>  <br/> |<span data-ttu-id="543ab-184">不会显示密件抄送收件人。</span><span class="sxs-lookup"><span data-stu-id="543ab-184">No indication of Bcc recipients.</span></span>  <br/> |
|<span data-ttu-id="543ab-185">John 的邮箱</span><span class="sxs-lookup"><span data-stu-id="543ab-185">John's mailbox</span></span>  <br/> |<span data-ttu-id="543ab-186">密件抄送：Jack（直接或通过通讯组）</span><span class="sxs-lookup"><span data-stu-id="543ab-186">Bcc:Jack (directly or via distribution group)</span></span>  <br/> |<span data-ttu-id="543ab-187">否</span><span class="sxs-lookup"><span data-stu-id="543ab-187">No</span></span>  <br/> |<span data-ttu-id="543ab-p109">密件抄送信息不存储在发送给收件人的邮件中。您必须搜索发件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="543ab-p109">Bcc information is not stored in the message delivered to recipients. You must search the sender's mailbox.</span></span>  <br/> |
|<span data-ttu-id="543ab-190">Jack 的邮箱</span><span class="sxs-lookup"><span data-stu-id="543ab-190">Jack's mailbox</span></span>  <br/> |<span data-ttu-id="543ab-191">收件人/抄送：John（直接或通过通讯组）</span><span class="sxs-lookup"><span data-stu-id="543ab-191">To/Cc:John (directly or via distribution group)</span></span>  <br/> |<span data-ttu-id="543ab-192">是</span><span class="sxs-lookup"><span data-stu-id="543ab-192">Yes</span></span>  <br/> |<span data-ttu-id="543ab-193">收件人/抄送信息包含在发送给所有收件人的邮件中。</span><span class="sxs-lookup"><span data-stu-id="543ab-193">To/Cc information is included in message delivered to all recipients.</span></span>  <br/> |
|<span data-ttu-id="543ab-194">Jack 的邮箱</span><span class="sxs-lookup"><span data-stu-id="543ab-194">Jack's mailbox</span></span>  <br/> |<span data-ttu-id="543ab-195">密件抄送：Jack（直接或通过通讯组）</span><span class="sxs-lookup"><span data-stu-id="543ab-195">Bcc:Jack (directly or via distribution group)</span></span>  <br/> |<span data-ttu-id="543ab-196">否</span><span class="sxs-lookup"><span data-stu-id="543ab-196">No</span></span>  <br/> |<span data-ttu-id="543ab-p110">密件抄送信息不存储在发送给收件人的邮件中。您必须搜索发件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="543ab-p110">Bcc information is not stored in the message delivered to recipients. You must search the sender's mailbox.</span></span>  <br/> |
   
## <a name="frequently-asked-questions"></a><span data-ttu-id="543ab-199">常见问题</span><span class="sxs-lookup"><span data-stu-id="543ab-199">Frequently asked questions</span></span>
<span data-ttu-id="543ab-200"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="543ab-200"></span></span>

 <span data-ttu-id="543ab-201">**问：何时何地存储密件抄送收件人信息？**</span><span class="sxs-lookup"><span data-stu-id="543ab-201">**Q. When and where is Bcc recipient information stored?**</span></span>
  
<span data-ttu-id="543ab-p111">答： 密件抄送收件人信息是默认情况下，在原始消息发件人的邮箱中保留的。如果密件抄送收件人是通讯组，通讯组成员身份为仅扩展如果发件人的邮箱置于保留状态，或分配给 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="543ab-p111">A. Bcc recipient information is preserved by default in the original message in sender's mailbox. If the Bcc recipient is a distribution group, distribution group membership is only expanded if the sender's mailbox is on hold or assigned to an Office 365 retention policy.</span></span>
  
 <span data-ttu-id="543ab-205">**问：何时何地存储展开的通讯组收件人列表？**</span><span class="sxs-lookup"><span data-stu-id="543ab-205">**Q. When and where is the list of expanded distribution group recipients stored?**</span></span>
  
<span data-ttu-id="543ab-p112">A.发送邮件时展开组成员身份。扩展的通讯组成员的列表存储在原始邮件发件人的邮箱中。发件人的邮箱必须位于就地保留，诉讼保留，或分配给 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="543ab-p112">A. Group membership is expanded at the time the message is sent. The list of expanded distribution group members is stored in the original message in the sender's mailbox. The sender's mailbox must be on In-Place Hold, Litigation Hold, or assigned to an Office 365 retention policy.</span></span>
  
 <span data-ttu-id="543ab-210">**问：收件人/抄送收件人可以看到被密件抄送的收件人吗？**</span><span class="sxs-lookup"><span data-stu-id="543ab-210">**Q. Can the To/Cc recipients see which recipients were Bcc'ed?**</span></span>
  
<span data-ttu-id="543ab-p113">答：此信息并不包含在邮件标头中，对收件人/抄送收件人不可见。发件人可以看到其邮箱中所存储原始邮件中的密件抄送字段。搜索发件人邮箱时，合规部主管可以看到此信息。</span><span class="sxs-lookup"><span data-stu-id="543ab-p113">A. No. This information is not included in message headers, and isn't visible to To/Cc recipients. The sender can see the Bcc field stored in the original message stored in their mailbox. Compliance officers can see this information when searching the sender's mailbox.</span></span>
  
 <span data-ttu-id="543ab-216">**问：如何确保展开的通讯组收件人一直保留下去？**</span><span class="sxs-lookup"><span data-stu-id="543ab-216">**Q. How can I ensure expanded distribution group recipients are always preserved?**</span></span>
  
<span data-ttu-id="543ab-p114">答： 来确保始终保留一条消息，[位置上的所有邮箱都保留](http://technet.microsoft.com/library/4c141604-3210-44cc-b98e-f3e0f15613b8.aspx)扩展的通讯组成员，或创建组织范围内的 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="543ab-p114">A. To ensure expanded distribution group members are always preserved with a message, [Place all mailboxes on hold](http://technet.microsoft.com/library/4c141604-3210-44cc-b98e-f3e0f15613b8.aspx) or create an organization-wide Office 365 retention policy.</span></span> 
  
 <span data-ttu-id="543ab-219">**问：支持哪些类型的组？**</span><span class="sxs-lookup"><span data-stu-id="543ab-219">**Q. Which types of groups are supported?**</span></span>
  
<span data-ttu-id="543ab-p115">答：支持通讯组、已启用邮件的安全组和动态通讯组。</span><span class="sxs-lookup"><span data-stu-id="543ab-p115">A. Distribution groups, mail-enabled security groups, and dynamic distribution groups are supported.</span></span> 
  
 <span data-ttu-id="543ab-222">**问：邮件中展开和存储的通讯组收件人数量存在限制吗？**</span><span class="sxs-lookup"><span data-stu-id="543ab-222">**Q. Is there a limit on the number of distribution group recipients that are expanded and stored in the message?**</span></span>
  
<span data-ttu-id="543ab-p116">答：最多保留 10000 个通讯组成员。</span><span class="sxs-lookup"><span data-stu-id="543ab-p116">A. Up to 10,000 members of a distribution group is preserved.</span></span>
  
 <span data-ttu-id="543ab-225">**问：支持嵌套通讯组吗？**</span><span class="sxs-lookup"><span data-stu-id="543ab-225">**Q. Are nested distribution groups supported?**</span></span>
  
<span data-ttu-id="543ab-p117">答：支持，可展开 25 层级嵌套通讯组。</span><span class="sxs-lookup"><span data-stu-id="543ab-p117">A. Yes, 25 levels of nested distribution groups are expanded.</span></span>
  
 <span data-ttu-id="543ab-228">**问：密件抄送和展开的通讯组收件人信息在哪里可见？**</span><span class="sxs-lookup"><span data-stu-id="543ab-228">**Q. Where is the Bcc and expanded distribution group recipient information visible?**</span></span>
  
<span data-ttu-id="543ab-p118">答：当执行电子数据展示搜索时，密件抄送和展开的通讯组收件人信息对合规部主管可见。复制到发现邮箱或导出到 PST 文件以及搜索结果电子数据展示日志的搜索结果中包含密件抄送和展开的通讯组收件人。密件抄送收件人信息在搜索预览中也可用。</span><span class="sxs-lookup"><span data-stu-id="543ab-p118">A. Bcc and expanded distribution group recipients information is visible to Compliance officers when performing an eDiscovery search. Bcc and expanded distribution group recipients are included in search results copied to a Discovery mailbox or exported to a PST file and in the eDiscovery log included in search results. Bcc recipient information is also available in search preview.</span></span>
  
 <span data-ttu-id="543ab-233">**问：如果通讯组中的一个成员在组织的全局地址列表 (GAL) 中被隐藏会怎样？**</span><span class="sxs-lookup"><span data-stu-id="543ab-233">**Q. What happens if a member of a distribution group is hidden from the organization's global address list (GAL)?**</span></span>
  
<span data-ttu-id="543ab-p119">答：没有任何影响。如果收件人在 GAL 中被隐藏，它们仍包括在展开的通讯组的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="543ab-p119">A. There's no impact. If recipients are hidden from the GAL, they're still included in the list of recipients for the expanded distribution group.</span></span>
  


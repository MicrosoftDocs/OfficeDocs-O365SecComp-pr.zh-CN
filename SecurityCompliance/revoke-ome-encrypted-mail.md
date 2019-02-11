---
title: 撤销使用 Office 365 邮件加密进行加密的电子邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
description: 作为 Office 365 管理员，您可以撤消某些使用 Office 365 邮件加密已加密的电子邮件。
ms.openlocfilehash: 018f12105e19382372a8a4b3a91248bb60b228be
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696236"
---
# <a name="office-365-message-encryption-email-revocation"></a><span data-ttu-id="b0d20-103">Office 365 邮件加密电子邮件吊销</span><span class="sxs-lookup"><span data-stu-id="b0d20-103">Office 365 Message Encryption email revocation</span></span>

<span data-ttu-id="b0d20-p101">本文是系列的有关[Office 365 邮件加密](ome.md)的文章的较大一部分。现在，加密电子邮件吊销处于预览。预期更新和更改功能和内容，如我们继续改进我们的产品。</span><span class="sxs-lookup"><span data-stu-id="b0d20-p101">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md). Right now, encrypted email revocation is in preview. Expect updates and changes to the feature and the content as we continue to improve our offering.</span></span>

<span data-ttu-id="b0d20-p102">您可能会发现需要撤消已发送电子邮件。如果您是 Office 365 管理员使用 Office 365 邮件加密，加密电子邮件，您可以执行此操作在某些情况下的电子邮件。本文介绍在什么情况下是可能以及如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b0d20-p102">You may find it necessary to revoke an email that has already been sent. If the email was encrypted using Office 365 Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions. This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="b0d20-110">可以取消的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="b0d20-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="b0d20-p103">如果收件人收到链接基于，品牌加密的电子邮件，您可以撤消加密电子邮件。如果收件人在支持的 Outlook 客户端中收到的本机内嵌体验，这些电子邮件不能被吊销。</span><span class="sxs-lookup"><span data-stu-id="b0d20-p103">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email. If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="b0d20-p104">收件人收到基于链接的体验，还是内嵌体验取决于收件人身份类型： Office 365 和 Microsoft 帐户收件人 （如 outlook.com 用户） 获取内嵌体验中支持的 Outlook 客户端。所有其他收件人类型，如 Gmail 收件人，获取基于链接的体验。</span><span class="sxs-lookup"><span data-stu-id="b0d20-p104">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients. All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

<span data-ttu-id="b0d20-p105">即将推出，组织会强制无论收件人的标识的基于链接的体验的功能。这种方式，所有收件人都将都获得一个链接到他们都将能够读取和回复加密电子邮件的 Office 365 邮件加密门户的品牌化电子邮件。将可撤销此类加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b0d20-p105">Coming soon, organizations will have the ability to force a link-based experience regardless of the recipient identity. This way, all recipients will get a branded email with a link to the Office 365 Message Encryption portal where they will be able to read and reply to encrypted emails. All such encrypted emails will be revocable.</span></span>
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="b0d20-118">收件人已吊销加密电子邮件体验</span><span class="sxs-lookup"><span data-stu-id="b0d20-118">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="b0d20-119">尝试通过 Office 365 邮件加密门户访问加密的电子邮件时电子邮件已被吊销，一旦收件人将收到错误:"已被吊销邮件发件人"。</span><span class="sxs-lookup"><span data-stu-id="b0d20-119">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![显示已吊销的加密电子邮件的屏幕截图。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="b0d20-121">如何撤消加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="b0d20-121">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="b0d20-p106">步骤 1。获取电子邮件消息 ID</span><span class="sxs-lookup"><span data-stu-id="b0d20-p106">Step 1. Obtain the Message ID of the email</span></span>

<span data-ttu-id="b0d20-p107">您可以取消加密的邮件之前，您需要收集邮件 ID 的邮件。MessageId 通常的格式：</span><span class="sxs-lookup"><span data-stu-id="b0d20-p107">Before you can revoke an encrypted mail you need to gather the Message ID of the mail. The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="b0d20-p108">有多种方法来查找您要取消的电子邮件的邮件 ID。本节介绍几种情况下，但您可以使用任何方法提供 id。</span><span class="sxs-lookup"><span data-stu-id="b0d20-p108">There are multiple ways to find the Message ID of the email that you want to revoke. This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="b0d20-128">若要确定您要取消中安全使用邮件跟踪电子邮件的邮件 ID&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="b0d20-128">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="b0d20-129">通过发件人或使用[新的 Message Trace in Office 365 安全性 & 合规中心](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)的收件人的电子邮件中搜索。</span><span class="sxs-lookup"><span data-stu-id="b0d20-129">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>
2. <span data-ttu-id="b0d20-p109">您已找到电子邮件选择以显示**邮件跟踪详细信息**窗格。展开**更多信息**查找邮件 id。</span><span class="sxs-lookup"><span data-stu-id="b0d20-p109">Once you've located the email select it to bring up the **Message trace details** pane. Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="b0d20-132">若要确定您要取消中安全使用 Office 邮件加密报告的电子邮件的邮件 ID&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="b0d20-132">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="b0d20-133">安全中&amp;合规性中心中，导航到**邮件加密报告**。</span><span class="sxs-lookup"><span data-stu-id="b0d20-133">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>
2. <span data-ttu-id="b0d20-134">选择**查看详细信息**表，并确定您要取消的邮件。</span><span class="sxs-lookup"><span data-stu-id="b0d20-134">Choose the **View details** table and identify the message that you want to revoke.</span></span>
3. <span data-ttu-id="b0d20-135">双击该消息查看详细信息，包括邮件 id。</span><span class="sxs-lookup"><span data-stu-id="b0d20-135">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="b0d20-p110">步骤 2。验证邮件可撤销</span><span class="sxs-lookup"><span data-stu-id="b0d20-p110">Step 2. Verify that the mail is revocable</span></span>

<span data-ttu-id="b0d20-138">若要验证可以撤消特定的电子邮件，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b0d20-138">To verify whether or not you can revoke a particular email message, complete these steps.</span></span>

1. <span data-ttu-id="b0d20-p111">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，请启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b0d20-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b0d20-141">运行设置 OMEMessageStatus cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b0d20-141">Run the Set-OMEMessageStatus cmdlet as follows:</span></span>
     ```powershell
     Get-OMEMessageStatus -MessageId "<messagieid>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="b0d20-p112">这将返回邮件和邮件是否可撤销的主题。例如，</span><span class="sxs-lookup"><span data-stu-id="b0d20-p112">This returns the subject of the message and whether the message is revocable. For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="b0d20-p113">步骤 3。取消邮件</span><span class="sxs-lookup"><span data-stu-id="b0d20-p113">Step 3. Revoke the mail</span></span>  

<span data-ttu-id="b0d20-146">一旦您知道要撤消，则该电子邮件消息 ID，且您已验证邮件可撤销，您可以使用集 OMEMessageRevocation cmdlet 取消电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b0d20-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="b0d20-147">[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b0d20-147">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b0d20-148">运行设置 OMEMessageRevocation cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b0d20-148">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="b0d20-149">若要检查是否已被吊销电子邮件，请运行 Get OMEMessageStatus cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b0d20-149">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```  
    <span data-ttu-id="b0d20-150">如果吊销成功，cmdlet 将返回以下结果：</span><span class="sxs-lookup"><span data-stu-id="b0d20-150">If revocation was successful, the cmdlet returns the following result:</span></span>  

    `Revoked: True`

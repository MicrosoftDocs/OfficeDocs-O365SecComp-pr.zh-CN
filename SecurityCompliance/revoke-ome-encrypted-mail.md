---
title: 撤销使用 Office 365 邮件加密进行加密的电子邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 作为 office 365 管理员, 您可以吊销使用 Office 365 邮件加密进行加密的某些电子邮件。
ms.openlocfilehash: 75b5e46e25f447ddac0de5a7911d0df8385da6b9
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214892"
---
# <a name="office-365-message-encryption-email-revocation"></a><span data-ttu-id="d24a9-103">Office 365 邮件加密电子邮件吊销</span><span class="sxs-lookup"><span data-stu-id="d24a9-103">Office 365 Message Encryption email revocation</span></span>

<span data-ttu-id="d24a9-p101">本文是有关[Office 365 邮件加密](ome.md)的更多系列文章的一部分。现在, 已加密的电子邮件吊销处于预览阶段。在我们继续改进我们的产品时, 需要对功能和内容进行更新和更改。</span><span class="sxs-lookup"><span data-stu-id="d24a9-p101">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md). Right now, encrypted email revocation is in preview. Expect updates and changes to the feature and the content as we continue to improve our offering.</span></span>

<span data-ttu-id="d24a9-p102">你可能会发现有必要吊销已发送的电子邮件。如果电子邮件是使用 office 365 邮件加密进行加密的, 并且您是 office 365 管理员, 则可以在特定条件下对电子邮件执行此操作。本文介绍在何种情况下可能会发生这种情况以及如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d24a9-p102">You may find it necessary to revoke an email that has already been sent. If the email was encrypted using Office 365 Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions. This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="d24a9-110">您可以撤销的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="d24a9-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="d24a9-p103">如果收件人收到基于链接的、品牌加密的电子邮件, 则可以撤销加密的电子邮件。如果收件人在受支持的 Outlook 客户端中收到本机内嵌体验, 则无法撤消这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d24a9-p103">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email. If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="d24a9-p104">收件人是否收到基于链接的体验或内嵌体验取决于收件人标识类型: Office 365 和 Microsoft 帐户收件人 (例如, outlook.com 用户) 在支持的 outlook 客户端中获取内嵌体验。所有其他收件人类型 (如 Gmail 收件人) 都获得了基于链接的体验。</span><span class="sxs-lookup"><span data-stu-id="d24a9-p104">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients. All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

<span data-ttu-id="d24a9-p105">接下来, 组织将能够强制实施基于链接的体验, 而无需考虑收件人身份。这样一来, 所有收件人都将收到一个带有指向 Office 365 邮件加密门户的链接的署名电子邮件, 用户可以在其中阅读和回复加密电子邮件。所有此类加密电子邮件都将是可吊销的。</span><span class="sxs-lookup"><span data-stu-id="d24a9-p105">Coming soon, organizations will have the ability to force a link-based experience regardless of the recipient identity. This way, all recipients will get a branded email with a link to the Office 365 Message Encryption portal where they will be able to read and reply to encrypted emails. All such encrypted emails will be revocable.</span></span>
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="d24a9-118">已撤销加密电子邮件的收件人体验</span><span class="sxs-lookup"><span data-stu-id="d24a9-118">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="d24a9-119">一旦电子邮件被吊销, 收件人在通过 Office 365 邮件加密门户尝试访问加密电子邮件时, 将会收到错误消息: "邮件已被发件人吊销"。</span><span class="sxs-lookup"><span data-stu-id="d24a9-119">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![显示已吊销加密电子邮件的屏幕截图。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="d24a9-121">如何撤销加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="d24a9-121">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="d24a9-p106">步骤1。获取电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="d24a9-p106">Step 1. Obtain the Message ID of the email</span></span>

<span data-ttu-id="d24a9-p107">必须先收集邮件的邮件 ID, 然后才能撤销加密邮件。MessageId 的格式通常为:</span><span class="sxs-lookup"><span data-stu-id="d24a9-p107">Before you can revoke an encrypted mail you need to gather the Message ID of the mail. The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="d24a9-p108">有多种方法可查找要吊销的电子邮件的邮件 ID。本节介绍了几个选项, 但您可以使用任何提供该 ID 的方法。</span><span class="sxs-lookup"><span data-stu-id="d24a9-p108">There are multiple ways to find the Message ID of the email that you want to revoke. This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="d24a9-128">使用安全&amp;合规性中心中的邮件跟踪来标识要吊销的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="d24a9-128">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d24a9-129">[在 Office 365 Security & 合规中心中使用新邮件跟踪](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/), 按发件人或收件人搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d24a9-129">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>
2. <span data-ttu-id="d24a9-p109">找到电子邮件后, 选择它以显示**邮件跟踪详细信息**窗格。展开**详细信息**以查找邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="d24a9-p109">Once you've located the email select it to bring up the **Message trace details** pane. Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="d24a9-132">在安全&amp;合规中心中使用 Office 邮件加密报告确定要吊销的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="d24a9-132">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d24a9-133">在 "安全&amp;合规性中心" 中, 导航到 "**邮件加密" 报告**。</span><span class="sxs-lookup"><span data-stu-id="d24a9-133">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>
2. <span data-ttu-id="d24a9-134">选择 "**查看详细信息**" 表, 并确定要撤消的邮件。</span><span class="sxs-lookup"><span data-stu-id="d24a9-134">Choose the **View details** table and identify the message that you want to revoke.</span></span>
3. <span data-ttu-id="d24a9-135">双击邮件以查看包含邮件 ID 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d24a9-135">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="d24a9-p110">步骤2。验证邮件是否可吊销</span><span class="sxs-lookup"><span data-stu-id="d24a9-p110">Step 2. Verify that the mail is revocable</span></span>

<span data-ttu-id="d24a9-138">若要验证是否可以撤消特定的电子邮件, 请完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d24a9-138">To verify whether or not you can revoke a particular email message, complete these steps.</span></span>

1. <span data-ttu-id="d24a9-p111">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="d24a9-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="d24a9-141">运行 OMEMessageStatus cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="d24a9-141">Run the Set-OMEMessageStatus cmdlet as follows:</span></span>
     ```powershell
     Get-OMEMessageStatus -MessageId "<messagieid>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="d24a9-p112">这将返回邮件的主题以及邮件是否是不可吊销的。例如,</span><span class="sxs-lookup"><span data-stu-id="d24a9-p112">This returns the subject of the message and whether the message is revocable. For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="d24a9-p113">步骤3。撤销邮件</span><span class="sxs-lookup"><span data-stu-id="d24a9-p113">Step 3. Revoke the mail</span></span>  

<span data-ttu-id="d24a9-146">一旦您知道要吊销的电子邮件的邮件 ID, 并且已验证该邮件是可吊销的, 则可以使用 OMEMessageRevocation cmdlet 吊销该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d24a9-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="d24a9-147">[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="d24a9-147">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="d24a9-148">运行 OMEMessageRevocation cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="d24a9-148">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="d24a9-149">若要检查电子邮件是否已被吊销, 请运行 OMEMessageStatus cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="d24a9-149">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```  
    <span data-ttu-id="d24a9-150">如果吊销成功, 则 cmdlet 将返回以下结果:</span><span class="sxs-lookup"><span data-stu-id="d24a9-150">If revocation was successful, the cmdlet returns the following result:</span></span>  

    `Revoked: True`

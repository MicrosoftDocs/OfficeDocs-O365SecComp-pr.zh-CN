---
title: 撤销使用 Office 365 高级邮件加密进行加密的电子邮件
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 作为 Office 365 管理员, 您可以吊销使用 Office 365 高级邮件加密进行加密的某些电子邮件。
ms.openlocfilehash: e55129f68c7add589bd973b36f069d7cdbf631cf
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857612"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="48ddb-103">撤销使用 Office 365 高级邮件加密进行加密的电子邮件</span><span class="sxs-lookup"><span data-stu-id="48ddb-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="48ddb-104">电子邮件吊销作为 Office 365 高级邮件加密的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="48ddb-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="48ddb-105">Office 365 高级邮件加密在特定订阅中的 Office 365 邮件加密的顶层可用。</span><span class="sxs-lookup"><span data-stu-id="48ddb-105">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="48ddb-106">[Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)e5、Office 365 企业版 E5 和 Office 365 教育版 A5 中包含高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="48ddb-106">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="48ddb-107">如果您的组织有一个不包含 Office 365 高级邮件加密的 Office 365 订阅, 则可以将高级邮件加密作为加载项进行购买, 使其具有高级合规性 SKU 的 E5 合规性。</span><span class="sxs-lookup"><span data-stu-id="48ddb-107">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="48ddb-108">本文是有关[Office 365 邮件加密](ome.md)的更多系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="48ddb-108">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="48ddb-109">如果使用 Office 365 高级邮件加密对邮件进行了加密, 并且您是 Office 365 管理员, 则可以在特定条件下吊销邮件。</span><span class="sxs-lookup"><span data-stu-id="48ddb-109">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do revoke the message under certain conditions.</span></span> <span data-ttu-id="48ddb-110">本文介绍了可以进行吊销的情况以及执行操作的方法。</span><span class="sxs-lookup"><span data-stu-id="48ddb-110">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="48ddb-111">您可以撤销的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="48ddb-111">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="48ddb-112">如果收件人收到基于链接的、品牌加密的电子邮件, 则可以撤销加密的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="48ddb-112">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="48ddb-113">如果收件人在受支持的 Outlook 客户端中收到本机内嵌体验, 则无法撤消这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="48ddb-113">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="48ddb-114">收件人是否收到基于链接的体验或内嵌体验取决于收件人标识类型: Office 365 和 Microsoft 帐户收件人 (例如, outlook.com 用户) 在支持的 Outlook 客户端中获取内嵌体验。</span><span class="sxs-lookup"><span data-stu-id="48ddb-114">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="48ddb-115">所有其他收件人类型 (如 Gmail 收件人) 都获得了基于链接的体验。</span><span class="sxs-lookup"><span data-stu-id="48ddb-115">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="48ddb-116">已撤销加密电子邮件的收件人体验</span><span class="sxs-lookup"><span data-stu-id="48ddb-116">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="48ddb-117">一旦电子邮件被吊销, 收件人通过 Office 365 邮件加密门户访问加密的电子邮件时, 会收到错误消息: "邮件已被发件人吊销"。</span><span class="sxs-lookup"><span data-stu-id="48ddb-117">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![显示已吊销加密电子邮件的屏幕截图。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="48ddb-119">如何撤销加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="48ddb-119">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="48ddb-120">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="48ddb-120">Step 1.</span></span> <span data-ttu-id="48ddb-121">获取电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="48ddb-121">Obtain the Message ID of the email</span></span>

<span data-ttu-id="48ddb-122">在撤销加密邮件之前, 您可以收集邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="48ddb-122">Before you can revoke an encrypted mail you gather the Message ID of the mail.</span></span> <span data-ttu-id="48ddb-123">MessageId 的格式通常为:</span><span class="sxs-lookup"><span data-stu-id="48ddb-123">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="48ddb-124">有多种方法可查找要吊销的电子邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="48ddb-124">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="48ddb-125">本节介绍了几个选项, 但您可以使用任何提供该 ID 的方法。</span><span class="sxs-lookup"><span data-stu-id="48ddb-125">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="48ddb-126">使用安全&amp;合规性中心中的邮件跟踪来标识要吊销的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="48ddb-126">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="48ddb-127">[在 Office 365 安全 & 合规中心中使用新邮件跟踪](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/), 按发件人或收件人搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="48ddb-127">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="48ddb-128">找到电子邮件后, 选择它以显示**邮件跟踪详细信息**窗格。</span><span class="sxs-lookup"><span data-stu-id="48ddb-128">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="48ddb-129">展开**详细信息**以查找邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="48ddb-129">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="48ddb-130">在安全&amp;合规中心中使用 Office 邮件加密报告确定要吊销的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="48ddb-130">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="48ddb-131">在 "安全&amp;合规性中心" 中, 导航到 "**邮件加密" 报告**。</span><span class="sxs-lookup"><span data-stu-id="48ddb-131">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="48ddb-132">有关此报告的信息, 请参阅[查看&amp;安全合规性中心中的电子邮件安全报告](view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="48ddb-132">For information on this report, see [View email security reports in the Security &amp; Compliance Center](view-email-security-reports.md).</span></span>

2. <span data-ttu-id="48ddb-133">选择 "**查看详细信息**" 表, 并确定要撤消的邮件。</span><span class="sxs-lookup"><span data-stu-id="48ddb-133">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="48ddb-134">双击邮件以查看包含邮件 ID 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="48ddb-134">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="48ddb-135">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="48ddb-135">Step 2.</span></span> <span data-ttu-id="48ddb-136">验证邮件是否可吊销</span><span class="sxs-lookup"><span data-stu-id="48ddb-136">Verify that the mail is revocable</span></span>

<span data-ttu-id="48ddb-137">若要验证是否可以撤消邮件, 请检查安全&amp;合规性中心的**详细信息**表中的加密报告中是否显示 "吊销状态" 字段。</span><span class="sxs-lookup"><span data-stu-id="48ddb-137">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="48ddb-138">若要验证是否可以使用 Windows Powershell 撤消特定的电子邮件, 请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="48ddb-138">To verify whether you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="48ddb-139">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="48ddb-139">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="48ddb-140">有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="48ddb-140">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="48ddb-141">运行 OMEMessageStatus cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="48ddb-141">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="48ddb-142">这将返回邮件的主题以及邮件是否是不可吊销的。</span><span class="sxs-lookup"><span data-stu-id="48ddb-142">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="48ddb-143">For example,</span><span class="sxs-lookup"><span data-stu-id="48ddb-143">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="48ddb-144">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="48ddb-144">Step 3.</span></span> <span data-ttu-id="48ddb-145">撤销邮件</span><span class="sxs-lookup"><span data-stu-id="48ddb-145">Revoke the mail</span></span>

<span data-ttu-id="48ddb-146">一旦您知道要吊销的电子邮件的邮件 ID, 并且已验证该邮件是可吊销的, 则可以使用安全&amp;合规性中心或 Windows Powershell 吊销该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="48ddb-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows Powershell.</span></span>

<span data-ttu-id="48ddb-147">使用安全&amp;合规中心撤销邮件</span><span class="sxs-lookup"><span data-stu-id="48ddb-147">To revoke the message using the Security &amp; Compliance Center</span></span>

<span data-ttu-id="48ddb-148">若要在安全&amp;合规中心中撤销电子邮件, 请在加密报告中的邮件的**详细信息**表中, 选择 "**撤消邮件**"。</span><span class="sxs-lookup"><span data-stu-id="48ddb-148">To revoke the email in the Security &amp; Compliance Center, in the Encryption report, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="48ddb-149">您可以使用 Windows Powershell 吊销电子邮件, 方法是使用 OMEMessageRevocation cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48ddb-149">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="48ddb-150">[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="48ddb-150">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="48ddb-151">运行 OMEMessageRevocation cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="48ddb-151">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="48ddb-152">若要检查电子邮件是否已被吊销, 请运行 OMEMessageStatus cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="48ddb-152">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="48ddb-153">如果吊销成功, 则 cmdlet 将返回以下结果:</span><span class="sxs-lookup"><span data-stu-id="48ddb-153">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="48ddb-154">有关 Office 365 高级邮件加密的详细信息</span><span class="sxs-lookup"><span data-stu-id="48ddb-154">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="48ddb-155">Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="48ddb-155">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="48ddb-156">Office 365 高级邮件加密-电子邮件过期</span><span class="sxs-lookup"><span data-stu-id="48ddb-156">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="48ddb-157">邮件策略和合规性服务说明</span><span class="sxs-lookup"><span data-stu-id="48ddb-157">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

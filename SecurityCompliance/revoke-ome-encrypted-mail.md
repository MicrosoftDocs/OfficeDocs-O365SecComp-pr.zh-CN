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
ms.openlocfilehash: 098ce50791152c8bbb4e4692d6fb85e4c2c7cb58
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156784"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="9ec85-103">撤销使用 Office 365 高级邮件加密进行加密的电子邮件</span><span class="sxs-lookup"><span data-stu-id="9ec85-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="9ec85-104">电子邮件吊销作为 Office 365 高级邮件加密的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="9ec85-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="9ec85-105">Office 365 高级邮件加密在特定订阅中的 Office 365 邮件加密的顶层可用。</span><span class="sxs-lookup"><span data-stu-id="9ec85-105">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="9ec85-106">[Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)e5、Office 365 企业版 E5 和 Office 365 教育版 A5 中包含高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="9ec85-106">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="9ec85-107">如果您的组织有一个不包含 Office 365 高级邮件加密的 Office 365 订阅, 则可以将高级邮件加密作为加载项进行购买, 使其具有高级合规性 SKU 的 E5 合规性。</span><span class="sxs-lookup"><span data-stu-id="9ec85-107">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="9ec85-108">本文是有关[Office 365 邮件加密](ome.md)的更多系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="9ec85-108">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="9ec85-109">你可能会发现有必要吊销已发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9ec85-109">You may find it necessary to revoke an email that has already been sent.</span></span> <span data-ttu-id="9ec85-110">如果已使用 Office 365 高级邮件加密对电子邮件进行了加密, 并且您是 Office 365 管理员, 则可以在特定条件下对电子邮件执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9ec85-110">If the email was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do this for email under certain conditions.</span></span> <span data-ttu-id="9ec85-111">本文介绍在何种情况下可能会发生这种情况以及如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9ec85-111">This article describes under what circumstances this is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="9ec85-112">您可以撤销的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="9ec85-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="9ec85-113">如果收件人收到基于链接的、品牌加密的电子邮件, 则可以撤销加密的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9ec85-113">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="9ec85-114">如果收件人在受支持的 Outlook 客户端中收到本机内嵌体验, 则无法撤消这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9ec85-114">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="9ec85-115">收件人是否收到基于链接的体验或内嵌体验取决于收件人标识类型: Office 365 和 Microsoft 帐户收件人 (例如, outlook.com 用户) 在支持的 Outlook 客户端中获取内嵌体验。</span><span class="sxs-lookup"><span data-stu-id="9ec85-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="9ec85-116">所有其他收件人类型 (如 Gmail 收件人) 都获得了基于链接的体验。</span><span class="sxs-lookup"><span data-stu-id="9ec85-116">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="9ec85-117">已撤销加密电子邮件的收件人体验</span><span class="sxs-lookup"><span data-stu-id="9ec85-117">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="9ec85-118">一旦电子邮件被吊销, 收件人在通过 Office 365 邮件加密门户尝试访问加密电子邮件时, 将会收到错误消息: "邮件已被发件人吊销"。</span><span class="sxs-lookup"><span data-stu-id="9ec85-118">Once an email has been revoked, the recipient will get an error when trying to access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![显示已吊销加密电子邮件的屏幕截图。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="9ec85-120">如何撤销加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="9ec85-120">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="9ec85-121">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="9ec85-121">Step 1.</span></span> <span data-ttu-id="9ec85-122">获取电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="9ec85-122">Obtain the Message ID of the email</span></span>

<span data-ttu-id="9ec85-123">必须先收集邮件的邮件 ID, 然后才能撤销加密邮件。</span><span class="sxs-lookup"><span data-stu-id="9ec85-123">Before you can revoke an encrypted mail you need to gather the Message ID of the mail.</span></span> <span data-ttu-id="9ec85-124">MessageId 的格式通常为:</span><span class="sxs-lookup"><span data-stu-id="9ec85-124">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="9ec85-125">有多种方法可查找要吊销的电子邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="9ec85-125">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="9ec85-126">本节介绍了几个选项, 但您可以使用任何提供该 ID 的方法。</span><span class="sxs-lookup"><span data-stu-id="9ec85-126">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="9ec85-127">使用安全&amp;合规性中心中的邮件跟踪来标识要吊销的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="9ec85-127">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="9ec85-128">[在 Office 365 Security _AMP_ 合规中心中使用新邮件跟踪](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/), 按发件人或收件人搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9ec85-128">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="9ec85-129">找到电子邮件后, 选择它以显示**邮件跟踪详细信息**窗格。</span><span class="sxs-lookup"><span data-stu-id="9ec85-129">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="9ec85-130">展开**详细信息**以查找邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="9ec85-130">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="9ec85-131">在安全&amp;合规中心中使用 Office 邮件加密报告确定要吊销的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="9ec85-131">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="9ec85-132">在 "安全&amp;合规性中心" 中, 导航到 "**邮件加密" 报告**。</span><span class="sxs-lookup"><span data-stu-id="9ec85-132">In the Security &amp; Compliance Center, navigate to the **Message Encryption Report**.</span></span>

2. <span data-ttu-id="9ec85-133">选择 "**查看详细信息**" 表, 并确定要撤消的邮件。</span><span class="sxs-lookup"><span data-stu-id="9ec85-133">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="9ec85-134">双击邮件以查看包含邮件 ID 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9ec85-134">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="9ec85-135">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="9ec85-135">Step 2.</span></span> <span data-ttu-id="9ec85-136">验证邮件是否可吊销</span><span class="sxs-lookup"><span data-stu-id="9ec85-136">Verify that the mail is revocable</span></span>

<span data-ttu-id="9ec85-137">若要验证是否可以撤消特定的电子邮件, 请检查安全&amp;合规性中心的**详细信息**表中是否显示 "吊销状态" 字段。</span><span class="sxs-lookup"><span data-stu-id="9ec85-137">To verify whether you can revoke a particular email message, check whether the Revocation Status field is visible in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="9ec85-138">若要验证是否可以使用 Windows Powershell 撤消特定的电子邮件, 请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9ec85-138">To verify whether or not you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="9ec85-139">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9ec85-139">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9ec85-140">有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="9ec85-140">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9ec85-141">运行 OMEMessageStatus cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="9ec85-141">Run the Set-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="9ec85-142">这将返回邮件的主题以及邮件是否是不可吊销的。</span><span class="sxs-lookup"><span data-stu-id="9ec85-142">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="9ec85-143">For example,</span><span class="sxs-lookup"><span data-stu-id="9ec85-143">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="9ec85-144">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="9ec85-144">Step 3.</span></span> <span data-ttu-id="9ec85-145">撤销邮件</span><span class="sxs-lookup"><span data-stu-id="9ec85-145">Revoke the mail</span></span>  

<span data-ttu-id="9ec85-146">一旦您知道要吊销的电子邮件的邮件 ID, 并且已验证该邮件是可吊销的, 您就可以撤销该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9ec85-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email.</span></span>

<span data-ttu-id="9ec85-147">若要在安全&amp;合规中心中撤销电子邮件, 请在 "**详细信息**" 表中, 选择 "**吊销**"。</span><span class="sxs-lookup"><span data-stu-id="9ec85-147">To revoke the email in the Security &amp; Compliance Center, in the **Details** table, choose **Revoke**.</span></span>

<span data-ttu-id="9ec85-148">您可以使用 Windows Powershell 吊销电子邮件, 方法是使用 OMEMessageRevocation cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9ec85-148">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="9ec85-149">[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="9ec85-149">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9ec85-150">运行 OMEMessageRevocation cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="9ec85-150">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="9ec85-151">若要检查电子邮件是否已被吊销, 请运行 OMEMessageStatus cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="9ec85-151">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="9ec85-152">如果吊销成功, 则 cmdlet 将返回以下结果:</span><span class="sxs-lookup"><span data-stu-id="9ec85-152">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="9ec85-153">有关 Office 365 高级邮件加密的详细信息</span><span class="sxs-lookup"><span data-stu-id="9ec85-153">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="9ec85-154">Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="9ec85-154">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="9ec85-155">Office 365 高级邮件加密-电子邮件过期</span><span class="sxs-lookup"><span data-stu-id="9ec85-155">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="9ec85-156">邮件策略和合规性服务说明</span><span class="sxs-lookup"><span data-stu-id="9ec85-156">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
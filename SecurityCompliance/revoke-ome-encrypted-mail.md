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
# <a name="office-365-message-encryption-email-revocation"></a>Office 365 邮件加密电子邮件吊销

本文是有关[Office 365 邮件加密](ome.md)的更多系列文章的一部分。现在, 已加密的电子邮件吊销处于预览阶段。在我们继续改进我们的产品时, 需要对功能和内容进行更新和更改。

你可能会发现有必要吊销已发送的电子邮件。如果电子邮件是使用 office 365 邮件加密进行加密的, 并且您是 office 365 管理员, 则可以在特定条件下对电子邮件执行此操作。本文介绍在何种情况下可能会发生这种情况以及如何执行此操作。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>您可以撤销的加密电子邮件

如果收件人收到基于链接的、品牌加密的电子邮件, 则可以撤销加密的电子邮件。如果收件人在受支持的 Outlook 客户端中收到本机内嵌体验, 则无法撤消这些电子邮件。

收件人是否收到基于链接的体验或内嵌体验取决于收件人标识类型: Office 365 和 Microsoft 帐户收件人 (例如, outlook.com 用户) 在支持的 outlook 客户端中获取内嵌体验。所有其他收件人类型 (如 Gmail 收件人) 都获得了基于链接的体验。

接下来, 组织将能够强制实施基于链接的体验, 而无需考虑收件人身份。这样一来, 所有收件人都将收到一个带有指向 Office 365 邮件加密门户的链接的署名电子邮件, 用户可以在其中阅读和回复加密电子邮件。所有此类加密电子邮件都将是可吊销的。
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a>已撤销加密电子邮件的收件人体验

一旦电子邮件被吊销, 收件人在通过 Office 365 邮件加密门户尝试访问加密电子邮件时, 将会收到错误消息: "邮件已被发件人吊销"。

![显示已吊销加密电子邮件的屏幕截图。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>如何撤销加密电子邮件

### <a name="step-1-obtain-the-message-id-of-the-email"></a>步骤1。获取电子邮件的邮件 ID

必须先收集邮件的邮件 ID, 然后才能撤销加密邮件。MessageId 的格式通常为:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

有多种方法可查找要吊销的电子邮件的邮件 ID。本节介绍了几个选项, 但您可以使用任何提供该 ID 的方法。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>使用安全&amp;合规性中心中的邮件跟踪来标识要吊销的电子邮件的邮件 ID

1. [在 Office 365 Security & 合规中心中使用新邮件跟踪](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/), 按发件人或收件人搜索电子邮件。
2. 找到电子邮件后, 选择它以显示**邮件跟踪详细信息**窗格。展开**详细信息**以查找邮件 ID。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>在安全&amp;合规中心中使用 Office 邮件加密报告确定要吊销的电子邮件的邮件 ID

1. 在 "安全&amp;合规性中心" 中, 导航到 "**邮件加密" 报告**。
2. 选择 "**查看详细信息**" 表, 并确定要撤消的邮件。
3. 双击邮件以查看包含邮件 ID 的详细信息。

### <a name="step-2-verify-that-the-mail-is-revocable"></a>步骤2。验证邮件是否可吊销

若要验证是否可以撤消特定的电子邮件, 请完成这些步骤。

1. 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 运行 OMEMessageStatus cmdlet, 如下所示:
     ```powershell
     Get-OMEMessageStatus -MessageId "<messagieid>" | ft -a  Subject, IsRevocable
     ```

   这将返回邮件的主题以及邮件是否是不可吊销的。例如,

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a>步骤3。撤销邮件  

一旦您知道要吊销的电子邮件的邮件 ID, 并且已验证该邮件是可吊销的, 则可以使用 OMEMessageRevocation cmdlet 吊销该电子邮件。

1. [连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 运行 OMEMessageRevocation cmdlet, 如下所示:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 若要检查电子邮件是否已被吊销, 请运行 OMEMessageStatus cmdlet, 如下所示:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```  
    如果吊销成功, 则 cmdlet 将返回以下结果:  

    `Revoked: True`

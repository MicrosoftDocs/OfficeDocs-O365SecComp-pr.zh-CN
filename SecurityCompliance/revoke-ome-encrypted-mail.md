---
title: 撤销使用 Office 365 邮件加密进行加密的电子邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/29/2019
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
description: 作为 Office 365 管理员，您可以撤消某些使用 Office 365 邮件加密已加密的电子邮件。
ms.openlocfilehash: a3f5c08d2c8660e56c378fc5fa7a850ff2c12eb5
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614386"
---
# <a name="office-365-message-encryption-email-revocation"></a>Office 365 邮件加密电子邮件吊销

本文是系列的有关[Office 365 邮件加密](ome.md)的文章的较大一部分。现在，加密电子邮件吊销处于预览。预期更新和更改功能和内容，如我们继续改进我们的产品。

您可能会发现需要撤消已发送电子邮件。如果您是 Office 365 管理员使用 Office 365 邮件加密，加密电子邮件，您可以执行此操作在某些情况下的电子邮件。本文介绍在什么情况下是可能以及如何执行此操作。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>可以取消的加密电子邮件

如果收件人收到链接基于，品牌加密的电子邮件，您可以撤消加密电子邮件。如果收件人在支持的 Outlook 客户端中收到的本机内嵌体验，这些电子邮件不能被吊销。

收件人收到基于链接的体验，还是内嵌体验取决于收件人身份类型： Office 365 和 Microsoft 帐户收件人 （如 outlook.com 用户） 获取内嵌体验中支持的 Outlook 客户端。所有其他收件人类型，如 Gmail 收件人，获取基于链接的体验。

即将推出，组织会强制无论收件人的标识的基于链接的体验的功能。这种方式，所有收件人都将都获得一个链接到他们都将能够读取和回复加密电子邮件的 Office 365 邮件加密门户的品牌化电子邮件。将可撤销此类加密电子邮件。
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a>收件人已吊销加密电子邮件体验

尝试通过 Office 365 邮件加密门户访问加密的电子邮件时电子邮件已被吊销，一旦收件人将收到错误:"已被吊销邮件发件人"。

![显示已吊销的加密电子邮件的屏幕截图。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>如何撤消加密电子邮件

### <a name="step-1-obtain-the-message-id-of-the-email"></a>步骤 1。获取电子邮件消息 ID

您可以取消加密的邮件之前，您需要收集邮件 ID 的邮件。MessageId 通常的格式：

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

有多种方法来查找您要取消的电子邮件的邮件 ID。本节介绍几种情况下，但您可以使用任何方法提供 id。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>若要确定您要取消中安全使用邮件跟踪电子邮件的邮件 ID&amp;合规性中心

1. 通过发件人或使用[新的 Message Trace in Office 365 安全性 & 合规中心](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)的收件人的电子邮件中搜索。
2. 您已找到电子邮件选择以显示**邮件跟踪详细信息**窗格。展开**更多信息**查找邮件 id。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>若要确定您要取消中安全使用 Office 邮件加密报告的电子邮件的邮件 ID&amp;合规性中心

1. 安全中&amp;合规性中心中，导航到**邮件加密报告**。
2. 选择**查看详细信息**表，并确定您要取消的邮件。
3. 双击该消息查看详细信息，包括邮件 id。

### <a name="step-2-revoke-the-mail"></a>步骤 2。取消邮件  

一旦您知道要取消的电子邮件的邮件 ID，您可以使用集 OMEMessageRevocation cmdlet 撤消电子邮件。

1. [连接到 Exchange Online 使用远程 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

2. 运行设置 OMEMessageRevocation cmdlet，如下所示：

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```  

3. 若要检查是否已被吊销电子邮件，请运行 Get OMEMessageStatus cmdlet，如下所示：

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | fl Revoked
    ```  
    如果吊销成功，cmdlet 将返回以下结果：  

    `Revoked: True`

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
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a>撤销使用 Office 365 高级邮件加密进行加密的电子邮件

电子邮件吊销作为 Office 365 高级邮件加密的一部分提供。 Office 365 高级邮件加密在特定订阅中的 Office 365 邮件加密的顶层可用。 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)e5、Office 365 企业版 E5 和 Office 365 教育版 A5 中包含高级邮件加密。 如果您的组织有一个不包含 Office 365 高级邮件加密的 Office 365 订阅, 则可以将高级邮件加密作为加载项进行购买, 使其具有高级合规性 SKU 的 E5 合规性。

本文是有关[Office 365 邮件加密](ome.md)的更多系列文章的一部分。

你可能会发现有必要吊销已发送的电子邮件。 如果已使用 Office 365 高级邮件加密对电子邮件进行了加密, 并且您是 Office 365 管理员, 则可以在特定条件下对电子邮件执行此操作。 本文介绍在何种情况下可能会发生这种情况以及如何执行此操作。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>您可以撤销的加密电子邮件

如果收件人收到基于链接的、品牌加密的电子邮件, 则可以撤销加密的电子邮件。 如果收件人在受支持的 Outlook 客户端中收到本机内嵌体验, 则无法撤消这些电子邮件。

收件人是否收到基于链接的体验或内嵌体验取决于收件人标识类型: Office 365 和 Microsoft 帐户收件人 (例如, outlook.com 用户) 在支持的 Outlook 客户端中获取内嵌体验。 所有其他收件人类型 (如 Gmail 收件人) 都获得了基于链接的体验。

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>已撤销加密电子邮件的收件人体验

一旦电子邮件被吊销, 收件人在通过 Office 365 邮件加密门户尝试访问加密电子邮件时, 将会收到错误消息: "邮件已被发件人吊销"。

![显示已吊销加密电子邮件的屏幕截图。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>如何撤销加密电子邮件

### <a name="step-1-obtain-the-message-id-of-the-email"></a>步骤 1. 获取电子邮件的邮件 ID

必须先收集邮件的邮件 ID, 然后才能撤销加密邮件。 MessageId 的格式通常为:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

有多种方法可查找要吊销的电子邮件的邮件 ID。 本节介绍了几个选项, 但您可以使用任何提供该 ID 的方法。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>使用安全&amp;合规性中心中的邮件跟踪来标识要吊销的电子邮件的邮件 ID

1. [在 Office 365 Security _AMP_ 合规中心中使用新邮件跟踪](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/), 按发件人或收件人搜索电子邮件。

2. 找到电子邮件后, 选择它以显示**邮件跟踪详细信息**窗格。 展开**详细信息**以查找邮件 ID。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>在安全&amp;合规中心中使用 Office 邮件加密报告确定要吊销的电子邮件的邮件 ID

1. 在 "安全&amp;合规性中心" 中, 导航到 "**邮件加密" 报告**。

2. 选择 "**查看详细信息**" 表, 并确定要撤消的邮件。

3. 双击邮件以查看包含邮件 ID 的详细信息。

### <a name="step-2-verify-that-the-mail-is-revocable"></a>步骤 2. 验证邮件是否可吊销

若要验证是否可以撤消特定的电子邮件, 请检查安全&amp;合规性中心的**详细信息**表中是否显示 "吊销状态" 字段。

若要验证是否可以使用 Windows Powershell 撤消特定的电子邮件, 请完成以下步骤。

1. 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 运行 OMEMessageStatus cmdlet, 如下所示:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   这将返回邮件的主题以及邮件是否是不可吊销的。 For example,

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a>步骤 3. 撤销邮件  

一旦您知道要吊销的电子邮件的邮件 ID, 并且已验证该邮件是可吊销的, 您就可以撤销该电子邮件。

若要在安全&amp;合规中心中撤销电子邮件, 请在 "**详细信息**" 表中, 选择 "**吊销**"。

您可以使用 Windows Powershell 吊销电子邮件, 方法是使用 OMEMessageRevocation cmdlet。

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

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>有关 Office 365 高级邮件加密的详细信息

- [Office 365 高级邮件加密](ome-advanced-message-encryption.md)

- [Office 365 高级邮件加密-电子邮件过期](ome-advanced-expiration.md)

- [邮件策略和合规性服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
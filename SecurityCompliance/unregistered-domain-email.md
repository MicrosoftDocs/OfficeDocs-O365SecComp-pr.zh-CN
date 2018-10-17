---
title: 未注册的域的电子邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: 如果您发送大量未注册的域的电子邮件，则运行获取阻止您的电子邮件的风险。阅读此文，了解详细信息。
ms.openlocfilehash: 30d7887be0429195380f2c4ae1a328904dffd69c
ms.sourcegitcommit: 6d72cdb882b93edf6dfddb5ff2e6d8a16e2fa0bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25596725"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a>未注册域电子邮件： 您需要知道

Office 365 允许租户中继某些消息通过 Exchange Online Protection (EOP)。如果用户拥有 Office 365 邮箱和外部的某人发送电子邮件但，以便它返回到用户的外部邮箱配置邮件转发，应为此一个受支持的示例。这是最常见教育环境学生要利用其个人电子邮件界面，但仍可获得与学校相关的电子邮件中。时的用户在混合方案，并已发送电子邮件 EOP 出的本地服务器，另一个示例。

## <a name="problems-with-unregistered-domains"></a>未注册域问题

内部服务器获取威胁和最终中继大量的 EOP 出垃圾邮件时出现问题。几乎在所有情况下，右连接器设置但正在从未注册，也称为取消设置，域发送电子邮件。Office 365 允许一定的邮件来自未注册的域，但应在每个域发送外出您计划在管理中心中配置接受域。

一旦威胁，租户将阻止发送出站邮件未注册的域。用户将收到未送达报告 (NDR) 的状态：

- 550 5.7.750 服务不可用。阻止来自未注册的域发送的客户端

## <a name="unblocking-tenant-in-order-to-send-again"></a>取消阻止租户以再次发送

有几种方法需要获取阻止来自未注册的域发送时如何操作：

1. 请确保您注册您的域的所有 Office 365 管理中心中。可以找到更多信息[此处](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。

2. 特殊的连接线的外观。通常，恶意参与者将在 Office 365 租户发送垃圾邮件中创建新的入站的连接器。可以找到检查您连接器的详细信息[此处](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)。 

3. 锁定的本地服务器，并确保它们不泄漏。

> [!TIP]
> 有许多因素涉及到在这里，尤其是这些是第三方服务器。无论，您将需要能确认合法保留您的服务器的所有邮件。

4. 完成后，您将需要呼叫 Microsoft 支持联系，以获取您取消再次从未注册的域发送的租户。 提供的错误代码是非常有用，但您将需要证明安全的环境，不会在再次发送垃圾邮件。打开支持案例的详细信息可以找到[此处](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)。
  
## <a name="for-more-information"></a>详细信息

[Office 365 email anti-spam protection](anti-spam-protection.md)

[Office 365 中的电子邮件未送达报告](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[配置邮箱的电子邮件转发](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[如何设置多功能设备或应用程序以使用 Office 365 发送电子邮件](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[管理接受域在 Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。

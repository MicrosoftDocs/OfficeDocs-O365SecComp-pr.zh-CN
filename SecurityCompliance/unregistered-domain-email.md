---
title: 未注册的域电子邮件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 如果您发送大量未注册的域电子邮件, 则可能会导致电子邮件被阻止。 阅读本文以了解详细信息。
ms.openlocfilehash: 21c403c8072902565f63048782b06c531cdbceb0
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263984"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a>未注册的域电子邮件: 需要了解的内容

Office 365 允许租户通过 Exchange Online Protection (EOP) 中继某些邮件。 一种受支持的示例是, 当用户拥有 Office 365 邮箱, 而其他人向其发送电子邮件, 但电子邮件转发已配置为返回到用户的外部邮箱。 这在教育环境中最常见, 在这种情况下, 学生希望利用个人电子邮件界面, 但仍会收到与学校相关的电子邮件。 另一个示例是当客户处于混合方案中, 并且具有从 EOP 发送电子邮件的本地服务器时。

## <a name="problems-with-unregistered-domains"></a>未注册域的问题

问题是, 在本地服务器受到威胁时, 最终会将大量垃圾邮件转发给 EOP。 在几乎所有情况下, 都设置了正确的连接器, 但电子邮件是从未注册 (也称为 "未设置的域") 发送的。 Office 365 确实允许未注册的域中包含合理的邮件, 但应该为您计划发送的每个域在管理中心中配置一个接受域。

一旦受到威胁, 租户将被阻止为未注册的域发送出站邮件。 用户将收到一个未送达报告 (NDR), 其中指出:

- 550 5.7.750 服务不可用。 阻止从未注册的域发送的客户端

## <a name="unblocking-tenant-in-order-to-send-again"></a>取消阻止租户以便再次发送

如果阻止从未注册的域发送, 需要执行以下几项操作:

1. 请确保在 Microsoft 365 管理中心内注册所有域。 可在[此处](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)找到详细信息。

2. 查找异常连接器。 恶意参与者通常会在 Office 365 租户中创建新的入站连接器以发送垃圾邮件。 可在[此处](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps)找到有关检查连接器的详细信息。 

3. 锁定你的本地服务器, 并确保其不会受到威胁。

> [!TIP]
> 此处涉及许多因素, 尤其是当它们是第三方服务器时。 无论如何, 您都需要能够确认离开服务器的所有邮件都是合法的。

4. 完成后, 你将需要致电 Microsoft 支持部门, 让你的租户不再被阻止, 以从未注册的域中再次发送。  提供错误代码很有帮助, 但您需要证明您的环境是安全的, 并且不会再次发送垃圾邮件。 可在[此处](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online)找到有关打开支持案例的详细信息。
  
## <a name="for-more-information"></a>有关详细信息

[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)

[Office 365 中的电子邮件未送达报告](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[配置邮箱的电子邮件转发](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[如何设置多功能设备或应用程序以使用 Office 365 发送电子邮件](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[在 Exchange Online 中管理接受的域](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。

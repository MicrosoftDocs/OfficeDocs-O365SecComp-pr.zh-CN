---
title: 设置 EOP 服务
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/23/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: 本主题介绍了如何设置 Microsoft Exchange Online Protection (EOP)。 如果您已从 Office 365 域向导登录到这里，则假如您不想使用 Exchange Online Protection，请返回到 Office 365 域向导。 若要详细了解如何配置连接器，请参阅Configure mail flow using connectors in Office 365。
ms.openlocfilehash: 5c17e88784c5987d48930c26e9c4319256a95c43
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676532"
---
# <a name="set-up-your-eop-service"></a>设置 EOP 服务

本主题介绍了如何设置 Microsoft Exchange Online Protection (EOP)。如果您已从 Office 365 域向导登录到这里，则假如您不想使用 Exchange Online Protection，请返回到 Office 365 域向导。若要详细了解如何配置连接器，请参阅[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。
  
> [!NOTE]
> 此主题假设你拥有内部部署邮箱，并且想使用 EOP 对其进行保护，这称为独立方案。 如果要使用 Exchange Online 在云中托管所有邮箱, 则不必完成本主题中的所有步骤。 转到[Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312)以注册并购买云邮箱。 如果你想在内部部署和云中分别托管一部分邮箱，这称为混合方案。 这需要更高级的邮件流设置。 [Exchange Server 混合部署](https://docs.microsoft.com/exchange/exchange-hybrid)介绍了混合邮件流, 并提供了指向说明如何进行设置的资源的链接。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

- 估计完成该任务的时间：1 小时

- 要配置连接器，你的帐户必须是 Office 365 全局管理员或 Exchange 公司管理员（组织管理角色组）。 有关信息, 请参阅[EOP 中的功能权限](feature-permissions-in-eop.md)。

- 如果你还未注册 EOP，请访问 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=282660) 并选择购买或者试用服务。

- 有关可能适用于本主题中的过程的键盘快捷方式的信息, 请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛中寻求帮助。

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>步骤 1: 使用 Microsoft 365 管理中心添加并验证你的域

1. 在[Microsoft 365 管理中心](https://go.microsoft.com/fwlink/p/?LinkId=521888), 转到 "**安装程序**", 将您的域添加到服务中。

2. 按照该步骤将适用的 DNS 记录添加到您的 DNS 托管提供程序以验证域所有权。

> [!TIP]
> 在 office 365 的任何 DNS 托管提供程序中[添加域到 office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) , 并在将您的域添加到服务和配置 DNS 时,[在任何 dns 托管提供程序中创建 dns 记录](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。
  
## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>步骤 2：添加收件人，并选择性启用 DBEB

在配置您的邮件，使其流动到 EOP 服务和从 EOP 服务流出之前，我们建议将您的收件人添加到服务。执行此操作有几种方法，如[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中所述。此外，如果您希望启用基于目录的边缘阻止 (DBEB)，以便在添加收件人之后强制实施服务内的收件人验证，您需要将域类型设置为"权威"。有关 DBEB 的详细信息，请参阅[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>步骤 3：使用 EAC 设置邮件流

在能使邮件在 EOP 和你的内部部署邮件服务器间流动的 [Set up connectors to route mail between Office 365 and your own email servers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail) (EAC) 中创建连接器。有关详细说明，请参阅Exchange 管理中心。
  
### <a name="how-do-you-know-this-task-worked"></a>如何判断此任务生效？

检查服务与您的环境之间的邮件流。 有关详细信息, 请参阅[Test mail flow by 验证 Office 365 连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>步骤 4：允许入站端口 25 SMTP 访问

配置连接器后，请等待 72 小时，允许准备 DNS 记录更新。在此之后，限制防火墙或邮件服务器上的入站端口-25 SMTP 通信，以仅接受来自 EOP 数据中心的邮件，特别是来自 [Exchange Online Protection IP 地址](exchange-online-protection-ip-addresses.md)中列出的 IP 地址的邮件。此操作将通过限制可以接收的入站邮件范围，保护内部部署环境。此外，如果邮件服务器上的设置控制了允许为邮件中继连接的 IP 地址，也要更新这些设置。
  
> [!TIP]
> 将 SMTP 服务器上的设置配置 60 秒的连接时间。 在大多数情况下, 此设置是可接受的, 例如, 在使用大型附件发送邮件时, 会发生一定的延迟。
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>步骤 5：使用命令行管理程序确保垃圾邮件被路由到每个用户的垃圾邮件文件夹

若要确保垃圾邮件被正确路由到每个用户的 "垃圾邮件" 文件夹, 您必须执行几个配置步骤。 提供的步骤可[确保将垃圾邮件路由到每个用户的 "垃圾邮件" 文件夹](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。
  
如果您不想将邮件移至每个用户的垃圾电子邮件文件夹，可以选择其他操作，方法是在 Exchange 管理中心编辑内容筛选策略。 有关详细信息，请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)。
  
## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>步骤 6: 使用 Microsoft 365 管理中心将 MX 记录指向 EOP

按照 Office 365 域配置步骤更新你的域的 MX 记录，以便于你的入站电子邮件能够通过 EOP。请务必将你的 MX 记录直接指向 EOP 而不是让第三方筛选服务将电子邮件中继到 EOP。有关详细信息，请再次参阅[为 Office 365 创建 DNS 记录](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。
  
### <a name="how-do-you-know-this-task-worked"></a>如何判断此任务生效？

此时，您已验证经过适当配置的出站内部部署连接器的服务传递，而且已验证 MX 记录是否指向 EOP。现在，您可以选择运行以下其他测试来验证该服务是否会将电子邮件成功传递到内部部署环境：
  
- 检查服务与您的环境之间的邮件流。 有关详细信息, 请参阅[Test mail flow by 验证 Office 365 连接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。

- 将来自基于 Web 的任何电子邮件帐户的电子邮件发送到组织中的邮件收件人，组织的域与您添加到服务上的域相匹配。使用 Microsoft Outlook 或另一个电子邮件客户端确认邮件是否已传递到内部部署邮箱。

- 如果您想进行出站电子邮件测试，可以发送组织中一个用户的电子邮件到基于 Web 的电子邮件帐户并确认是否收到邮件。

> [!TIP]
> 完成安装后，您无需进行其他操作，EOP 即可删除垃圾邮件和恶意软件。 EOP 会自动删除垃圾邮件和恶意软件。 但是，您可以根据您的业务需求调整 EAC 中的设置。 有关详细信息, 请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](../anti-spam-and-anti-malware-protection.md)。 <br/><br/> 现在, 您的服务正在运行, 我们建议您阅读[有关配置 EOP 的最佳实践](best-practices-for-configuring-eop.md), 其中介绍了设置 EOP 后建议的设置和注意事项。

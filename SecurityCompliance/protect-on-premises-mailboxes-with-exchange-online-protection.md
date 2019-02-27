---
title: 使用 Exchange Online Protection 保护本地邮箱
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/1/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
description: 即使您计划在本地承载部分或全部邮箱, 仍可以使用 Exchange Online Protection (EOP) 保护邮箱。若要配置连接器, 你的帐户必须是 Office 365 全局管理员或 Exchange 公司管理员 (组织管理角色组)。有关 Office 365 权限与 Exchange 权限的关系的信息, 请参阅在由世纪互联运营的 office 365 中分配管理员角色。如果所有 Exchange 邮箱都是本地的, 请按照以下步骤设置您的 EOP 服务。
ms.openlocfilehash: 40fb5471a084cf245d9aef7f7b2b88effb5c4a83
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276032"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>使用 Exchange Online Protection 保护本地邮箱

> [!NOTE]
> 本文仅适用于由中国世纪互联运营的 Office 365。 
  
即使您计划在本地承载部分或全部邮箱, 仍可以使用 Exchange Online Protection (EOP) 保护邮箱。若要配置连接器, 你的帐户必须是 Office 365 全局管理员或 Exchange 公司管理员 (组织管理角色组)。有关 Office 365 权限与 Exchange 权限的关系的信息, 请参阅[在由世纪互联运营的 office 365 中分配管理员角色](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac)。如果所有 Exchange 邮箱都是本地的, 请按照以下步骤设置您的 EOP 服务。 
  
## <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a>步骤 1：使用 Office 365 管理中心添加并验证你的域

1. 在 Office 365 管理中心中，导航至" 设置"，将你的域添加到服务中。
    
2.  按照门户中的步骤将适用的 dns 记录添加到您的 DNS 托管提供商, 以验证域所有权。 
    
> [!TIP]
> [将您的域和用户添加到由世纪互联运营的 office 365](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78)中, 并为[office 365 创建 dns 记录。当您](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)将您的域添加到服务并配置 dns 时, 可以参考这些资源, 从而为 office 创建 DNS 记录。 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>步骤 2: 添加收件人并配置域类型

在配置您的邮件，使其流动到 EOP 服务和从 EOP 服务流出之前，我们建议将您的收件人添加到服务。执行此操作有几种方法，如[在 EOP 中管理邮件用户](https://go.microsoft.com/fwlink/?LinkId=506782)中所述。此外，如果您希望启用基于目录的边缘阻止 (DBEB)，以便在添加收件人之后强制实施服务内的收件人验证，您需要将域类型设置为"权威"。有关 DBEB 的详细信息，请参阅[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781)。
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>步骤 3：使用 EAC 设置邮件流

在 Exchange 管理中心 (EAC) 中创建可在 EOP 和本地邮件服务器之间实现邮件流的连接器。有关详细说明, 请参阅[创建必需的连接器以设置通过 EOP 的基本电子邮件流](https://go.microsoft.com/fwlink/?LinkId=506780)。
  
 如何判断此任务生效？ 
  
 使用远程连接分析器运行检查服务和环境之间的邮件流的测试。有关详细信息, 请参阅[test mail flow with the remote connectivity analyzer](https://go.microsoft.com/fwlink/?LinkId=506784)中的 "使用远程连接分析器测试电子邮件传递" 一节。
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>步骤 4：允许入站端口 25 SMTP 访问

配置连接器后, 请等待72小时以允许传播 DNS 记录更新。执行此操作后, 将防火墙或邮件服务器上的入站端口-25 SMTP 流量限制为仅接受来自 EOP 数据中心的邮件, 尤其是在[由世纪互联运营的 Office 365 的 url 和 ip 地址范围](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection)中列出的 ip 地址。这将通过限制您可以接收的入站邮件的范围来保护您的本地环境。此外, 如果您的邮件服务器上的设置控制了允许连接邮件中继的 IP 地址, 也需要更新这些设置。
  
> [!TIP]
> 将 SMTP 服务器上的设置配置 60 秒的连接时间。此设置在大多数情况下都可接受，例如，在发送带有很大附件的邮件时允许有些延迟。 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>步骤 5：使用命令行管理程序确保垃圾邮件被路由到每个用户的垃圾邮件文件夹

若要确保垃圾邮件被正确路由到每个用户的 "垃圾邮件" 文件夹, 您必须执行几个配置步骤。提供的步骤可[确保将垃圾邮件路由到每个用户的 "垃圾邮件" 文件夹](https://go.microsoft.com/fwlink/?LinkId=506804)。如果不想将邮件移动到每个用户的 "垃圾邮件" 文件夹, 则可以通过在 Exchange 管理中心中编辑内容筛选器策略来选择另一个操作。有关详细信息, 请参阅[配置内容筛选器策略](https://go.microsoft.com/fwlink/?LinkId=506805)。 
  
## <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a>步骤 6：使用 Office 365 管理中心将 MX 记录指向 EOP

按照 Office 365 域配置步骤更新您的域的 MX 记录, 以便入站电子邮件通过 EOP 流。有关详细信息, 请参阅[管理 dns 记录时, 可以再次引用为 Office 365 创建 dns 记录](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)。
  
如何判断此任务生效？
  
 使用远程连接分析器运行验证 MX 记录的测试。有关详细信息, 请参阅[test mail flow with the remote connectivity analyzer](https://go.microsoft.com/fwlink/?LinkId=506784)中的 "使用远程连接分析器测试 MX 记录和出站连接器" 一节。 
  
此时，您已验证经过适当配置的出站内部部署连接器的服务传递，而且已验证 MX 记录是否指向 EOP。现在，您可以选择运行以下其他测试来验证该服务是否会将电子邮件成功传递到内部部署环境：
  
- 在远程连接分析器中, 单击 " **Office 365** " 选项卡, 然后运行位于 " **Internet 电子邮件测试**" 下的 "**入站 SMTP 电子邮件**" 测试。
    
- 将来自基于 Web 的任何电子邮件帐户的电子邮件发送到组织中的邮件收件人，组织的域与您添加到服务上的域相匹配。使用 Microsoft Outlook 或另一个电子邮件客户端确认邮件是否已传递到内部部署邮箱。
    
- 如果您想进行出站电子邮件测试，可以发送组织中一个用户的电子邮件到基于 Web 的电子邮件帐户并确认是否收到邮件。
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>不太常见: 包含本地邮箱和云中的混合安装

如果 exchange Online 中有本地 exchange 邮箱以及 exchange Online 中的云中的一个或多个邮箱, 则可以使用*混合*设置。在混合安装中, 诸如忙/闲日历共享和邮件路由等功能在本地和云环境中协同工作。您可能在将邮箱转换为 Exchange Online 时设置了混合设置。混合环境的设置与 EOP 独立保护的方式不同。 
  
您可以选择一种混合方案, 以充分利用基于云的电子邮件为大多数员工。您可以执行此操作, 同时在本地承载一些邮箱; 请参阅。例如, 适用于法律部门。 
  
混合设置可能非常复杂, 但具有许多好处。若要了解有关使用 exchange 设置混合方案的详细信息, 请参阅[使用由世纪互联运营的 Office 365 配置 Exchange 混合部署功能](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d)。
  


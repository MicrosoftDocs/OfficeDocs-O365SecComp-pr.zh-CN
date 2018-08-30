---
title: 保护内部部署邮箱与 Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/1/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
description: 即使您打算承载邮箱本地的部分或全部，您仍可以保护邮箱与 Exchange Online Protection (EOP)。若要配置连接器，您的帐户必须是 Office 365 全局管理员或 Exchange 公司管理员 （组织管理角色组）。有关 Office 365 权限与 Exchange 权限的相关信息，请参阅由 21Vianet 的 Office 365 中的分配管理员角色。如果您的 Exchange 邮箱的所有内部部署，请按照下列步骤设置 EOP 服务。
ms.openlocfilehash: 4751bb2183e61d292805d1799519644b77b08c2a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526055"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>保护内部部署邮箱与 Exchange Online Protection

> [!NOTE]
> 本文仅适用于 Office 365 21Vianet 在中国由。 
  
即使您打算承载邮箱本地的部分或全部，您仍可以保护邮箱与 Exchange Online Protection (EOP)。若要配置连接器，您的帐户必须是 Office 365 全局管理员或 Exchange 公司管理员 （组织管理角色组）。有关 Office 365 权限与 Exchange 权限的相关信息，请参阅[由 21Vianet 的 Office 365 中的分配管理员角色](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac)。如果您的 Exchange 邮箱的所有内部部署，请按照下列步骤设置 EOP 服务。 
  
## <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a>步骤 1：使用 Office 365 管理中心添加并验证你的域

1. 在 Office 365 管理中心中，导航至" 设置"，将你的域添加到服务中。
    
2.  按照将适用的 DNS 记录添加到您的 DNS 托管提供商，以验证域所有权门户中的步骤。 
    
> [!TIP]
> [添加您的域和用户移动到 Office 365 由 21Vianet](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78)和[为 Office 365 管理 DNS 记录时创建 DNS 记录](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)是引用您的域添加到服务和配置 DNS 的有用资源。 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>步骤 2： 添加收件人并配置域类型

在配置您的邮件，使其流动到 EOP 服务和从 EOP 服务流出之前，我们建议将您的收件人添加到服务。执行此操作有几种方法，如[在 EOP 中管理邮件用户](https://go.microsoft.com/fwlink/?LinkId=506782)中所述。此外，如果您希望启用基于目录的边缘阻止 (DBEB)，以便在添加收件人之后强制实施服务内的收件人验证，您需要将域类型设置为"权威"。有关 DBEB 的详细信息，请参阅[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781)。
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>步骤 3：使用 EAC 设置邮件流

在启用 EOP 与内部部署邮件服务器之间的邮件流 Exchange 管理员中心 (EAC) 创建连接器。有关详细说明，请参阅[创建所需的连接线设置通过 EOP 的基本电子邮件流](https://go.microsoft.com/fwlink/?LinkId=506780)。
  
 您如何知道此任务有效？ 
  
 使用远程连接分析器运行检查服务和您的环境之间的邮件流测试。有关详细信息，请参阅[测试 with Remote Connectivity Analyzer 的邮件流](https://go.microsoft.com/fwlink/?LinkId=506784)中的"使用远程连接分析器测试电子邮件传递"一节。
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>步骤 4：允许入站端口 25 SMTP 访问

配置连接器后，等待 72 小时允许的 DNS 记录更新传播。接着，限制防火墙或邮件服务器以仅接受来自邮件到 EOP 数据中心，特别是从[Url 和 IP 地址范围由 21Vianet 的 Office 365](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection)中列出的 IP 地址上的入站的端口 25 SMTP 通信。这将通过限制范围可以接收的入站邮件保护您的内部部署环境。此外，如果必须在您的邮件服务器的控制允许的邮件中继连接的 IP 地址的设置，更新以及这些设置。
  
> [!TIP]
> 将 SMTP 服务器上的设置配置 60 秒的连接时间。此设置在大多数情况下都可接受，例如，在发送带有很大附件的邮件时允许有些延迟。 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>步骤 5：使用命令行管理程序确保垃圾邮件被路由到每个用户的垃圾邮件文件夹

若要确保垃圾邮件 （垃圾） 电子邮件正确路由到每个用户的垃圾邮件文件夹，您必须执行以下几个配置步骤。[确保垃圾邮件被路由到每个用户的垃圾邮件文件夹](https://go.microsoft.com/fwlink/?LinkId=506804)中提供的步骤。如果您不想要将邮件移动到每个用户的垃圾邮件文件夹，您可以通过编辑您在 Exchange 管理中心中的内容筛选器策略选择另一项操作。有关详细信息，请参阅[Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805)。 
  
## <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a>步骤 6：使用 Office 365 管理中心将 MX 记录指向 EOP

遵循更新为您的域，MX 记录的 Office 365 域配置步骤，以便通过 EOP 的入站电子邮件流。有关详细信息，可以再次引用[为 Office 365 管理 DNS 记录时创建 DNS 记录](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)。
  
您如何知道此任务有效？
  
 使用远程连接分析器来运行测试，验证 MX 记录。有关详细信息，请参阅[测试 with Remote Connectivity Analyzer 的邮件流](https://go.microsoft.com/fwlink/?LinkId=506784)中的"使用远程连接分析器测试 MX 记录和出站连接器"一节。 
  
此时，您已验证经过适当配置的出站内部部署连接器的服务传递，而且已验证 MX 记录是否指向 EOP。现在，您可以选择运行以下其他测试来验证该服务是否会将电子邮件成功传递到内部部署环境：
  
- 在远程连接分析器中，单击**Office 365**选项卡，，然后运行**入站 SMTP 电子邮件**测试位于下**Internet 电子邮件测试**。
    
- 将来自基于 Web 的任何电子邮件帐户的电子邮件发送到组织中的邮件收件人，组织的域与您添加到服务上的域相匹配。使用 Microsoft Outlook 或另一个电子邮件客户端确认邮件是否已传递到内部部署邮箱。
    
- 如果您想进行出站电子邮件测试，可以发送组织中一个用户的电子邮件到基于 Web 的电子邮件帐户并确认是否收到邮件。
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>通常不： 混合安装与本地邮箱，并在云中

如果您拥有 Exchange 本地邮箱和一个或多个邮箱必须在 Exchange Online 中云中，*混合*安装程序。在混合设置中，如功能共享忙/闲日历和邮件路由内部部署中协同工作和云环境。转换到 Exchange Online 邮箱时，您可能必须就地混合安装程序。混合环境设置不同 EOP 独立保护。 
  
您可能选择混合方案以利用大部分员工的基于云的电子邮件。您可以执行此操作时还承载一些本地邮箱;例如，对于您的法律部门。 
  
混合安装程序可能会很复杂，但它具有许多好处。若要了解有关设置与 Exchange 的混合方案，请参阅[与 Office 365 由 21Vianet 配置 Exchange 混合部署功能](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d)。
  


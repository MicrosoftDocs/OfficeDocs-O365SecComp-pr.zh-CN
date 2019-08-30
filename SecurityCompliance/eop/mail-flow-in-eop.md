---
title: EOP 中的邮件流
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: 作为 Exchange Online Protection (EOP) 客户，发送到您的组织的所有邮件都将先通过 EOP，然后工作人员才能看到这些邮件。不论您是在云中托管所有 Exchange Online 邮箱，还是在本地托管邮箱（称为独立方案），为了继续利用现有基础结构，您可以选择如何路由邮件，这些邮件将首先通过 EOP 处理，然后才能路由到工作人员收件箱。
ms.openlocfilehash: 2081aff8da44244a1476b51eed49e5f23a5a9b9a
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676755"
---
# <a name="mail-flow-in-eop"></a>EOP 中的邮件流

作为 Exchange Online Protection (EOP) 客户，发送到您的组织的所有邮件都将先通过 EOP，然后工作人员才能看到这些邮件。不论您是在云中托管所有 Exchange Online 邮箱，还是在本地托管邮箱（称为独立方案），为了继续利用现有基础结构，您可以选择如何路由邮件，这些邮件将首先通过 EOP 处理，然后才能路由到工作人员收件箱。
  
您可能需要配置自定义邮件路由，使邮件传递满足您的业务要求。例如，您可以通过策略筛选装置传递所有出站邮件。
  
## <a name="working-with-messages-and-message-access-options"></a>使用邮件和邮件访问选项

EOP 在您的邮件路由方式上提供了很大的灵活性。以下主题说明了邮件流过程中的步骤。
  
[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)介绍基于目录的边缘阻止功能, 该功能使您可以在服务网络外围拒绝对无效收件人的邮件。 
  
[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)介绍了如何管理与 EOP 服务相关的域。
  
如果将子域添加到组织，则 EOP 服务也可以帮助您管理这些子域。 有关子域的详细信息, 请参阅在[Exchange Online 中为子域启用邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。
  
[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)介绍了连接器以及如何使用连接器自定义邮件路由。方案包括确保与合作伙伴组织进行安全通信，并设置智能主机。
  
若要确保将垃圾邮件正确路由到每个用户的垃圾邮件文件夹, 您必须执行几个配置步骤。 在[确保垃圾邮件被路由到每个用户的 "垃圾邮件" 文件夹](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)时, 会对这些信息进行详细说明。 如果不想将邮件移动到每个用户的垃圾邮件文件夹, 则可以通过在 Exchange 管理中心中编辑内容筛选器策略来选择另一个操作。 有关详细信息，请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)。
  
## <a name="verify-mail-flow"></a>验证邮件流

要验证包括连接器配置在内的 EOP 安装是否正常工作，请参阅[设置 EOP 服务](set-up-your-eop-service.md)中的"您如何知道此任务有效？"部分。
  
[通过验证 Office 365 连接器测试邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)提供了有关测试您的邮件流设置正确的说明。

---
title: EOP 中的邮件流
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/13/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: 作为 Exchange Online Protection (EOP) 客户，发送到您的组织的所有邮件都将先通过 EOP，然后工作人员才能看到这些邮件。不论您是在云中托管所有 Exchange Online 邮箱，还是在本地托管邮箱（称为独立方案），为了继续利用现有基础结构，您可以选择如何路由邮件，这些邮件将首先通过 EOP 处理，然后才能路由到工作人员收件箱。
ms.openlocfilehash: b19db691304efeccfffa245d61f367f7b653739a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150174"
---
# <a name="mail-flow-in-eop"></a>EOP 中的邮件流

作为 Exchange Online Protection (EOP) 客户，发送到您的组织的所有邮件都将先通过 EOP，然后工作人员才能看到这些邮件。不论您是在云中托管所有 Exchange Online 邮箱，还是在本地托管邮箱（称为独立方案），为了继续利用现有基础结构，您可以选择如何路由邮件，这些邮件将首先通过 EOP 处理，然后才能路由到工作人员收件箱。
  
您可能需要配置自定义邮件路由，使邮件传递满足您的业务要求。例如，您可以通过策略筛选装置传递所有出站邮件。 
  
## <a name="working-with-messages-and-message-access-options"></a>使用邮件和邮件访问选项

EOP 在您的邮件路由方式上提供了很大的灵活性。以下主题说明了邮件流过程中的步骤。
  
[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx) 介绍"基于目录的边缘阻止"功能，您可以通过此功能拒绝在服务网络外围向无效收件人发送邮件。 
  
[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)介绍了如何管理与 EOP 服务相关的域。 
  
如果将子域添加到组织，则 EOP 服务也可以帮助您管理这些子域。有关子域的详细信息，请参阅[Enable Mail Flow for Subdomains in Exchange Online](http://technet.microsoft.com/library/4033a30a-f506-481c-8ef0-fd9a0508ae38.aspx)。
  
[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx)介绍了连接器以及如何使用连接器自定义邮件路由。方案包括确保与合作伙伴组织进行安全通信，并设置智能主机。 
  
若要确保将垃圾邮件正确路由到每个用户的垃圾邮件文件夹, 您必须执行几个配置步骤。 在[确保垃圾邮件被路由到每个用户的 "垃圾邮件" 文件夹](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)时, 会对这些信息进行详细说明。 如果不想将邮件移动到每个用户的垃圾邮件文件夹, 则可以通过在 Exchange 管理中心中编辑内容筛选器策略来选择另一个操作。 有关详细信息，请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)。
  
## <a name="verify-mail-flow"></a>验证邮件流

要验证包括连接器配置在内的 EOP 安装是否正常工作，请参阅[设置 EOP 服务](set-up-your-eop-service.md)中的"您如何知道此任务有效？"部分。 
  
[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)提供了有关测试您的邮件流设置正确的说明。 
  


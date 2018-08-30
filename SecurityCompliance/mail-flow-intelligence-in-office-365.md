---
title: Office 365 中的邮件流智能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/27/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: '通常，使用连接器路由邮件从 Office 365 组织到本地邮件环境。您可能还使用连接器路由邮件从 Office 365 合作伙伴组织。时 Office 365 无法传送连接器通过这些消息，它们是在 Office 365 中排队。 '
ms.openlocfilehash: 4effbb783d6ba8f3b33d0aed446e031193d2f2a3
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002714"
---
# <a name="mail-flow-intelligence-in-office-365"></a>Office 365 中的邮件流智能
  
通常，使用连接器路由邮件从 Office 365 组织到本地邮件环境。您可能还使用连接器路由邮件从 Office 365 合作伙伴组织。时 Office 365 无法传送连接器通过这些消息，它们是在 Office 365 中排队。Office 365 将继续 48 小时重试关于每封邮件的传递。48 小时内，将过期排队的消息，并将向未送达报告 （也称为 NDR 或弹跳消息） 的原始发件人返回邮件。
  
Office 365 将生成一个错误，不能使用连接器传递一条消息。本主题中描述的最常见的错误和他们的解决方案。统称未送达发送的邮件通过连接器的队列和通知错误称为邮件流智能。
  
 **目录**
  
- [错误代码： 450 4.4.312 DNS 查询失败](mail-flow-intelligence-in-office-365.md#ErrorCode44312)
    
- [错误代码： 450 4.4.315 连接超时](mail-flow-intelligence-in-office-365.md#ErrorCode44315)
    
- [错误代码： 450 4.4.316 连接拒绝](mail-flow-intelligence-in-office-365.md#ErrorCode44316)
    
- [错误代码： 450 4.4.317 无法连接到远程服务器](mail-flow-intelligence-in-office-365.md#ErrorCode44317)
    
- [错误代码： 450 4.4.318 连接已关闭突然](mail-flow-intelligence-in-office-365.md#ErrorCode44318)
    
- [错误代码： 450 4.7.320 证书验证失败](mail-flow-intelligence-in-office-365.md#ErrorCode47320)
    
## <a name="error-code-450-44312-dns-query-failed"></a>错误代码： 450 4.4.312 DNS 查询失败

此错误通常意味着 Office 365 尝试连接到智能主机指定在连接器，但是 DNS 查询，以查找智能主机的 IP 地址失败。此错误可能的原因是：
  
- 没有与您的域的 DNS 托管服务 （维护您的域的权威页面的名称服务器方） 问题。
    
- 您的域最近已过期的因此无法检索 MX 记录。
    
- 最近更改您的域的 MX 记录，和 Office 365 DNS 服务器仍具有以前缓存为您的域的 DNS 信息。
    
您需要通过使用您的 DNS 托管服务修复 DNS 问题。
  
如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。
  
## <a name="error-code-450-44315-connection-timed-out"></a>错误代码： 450 4.4.315 连接超时

通常，这意味着 Office 365 无法连接到目标消息服务器。错误详细信息将说明该问题。例如：
  
- 您的内部部署邮件服务器已关闭。
    
- 没有错误连接符的智能主机设置，以便 Office 365 尝试连接到错误的 IP 地址。
    
找出哪些方案适用于您，并进行必要的纠正。例如，如果邮件流工作正常，并且您没有更改连接器设置，则需要检查您的内部部署邮件环境如果服务器已关闭，或者是否存在已对网络基础结构的任何更改 （例如，您已更改 Internet 服务提供商，因此您现在有不同的 IP 地址）。
  
如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。
  
## <a name="error-code-450-44316-connection-refused"></a>错误代码： 450 4.4.316 连接拒绝

通常，此错误表示 Office 365 时其尝试连接到目标消息服务器遇到连接错误。此错误的可能原因是您的防火墙阻止连接从 Office 365 IP 地址。或者，如果您已完全迁移您的内部部署邮件系统到 Office 365 并关闭内部部署此错误可能是设计使然邮件环境。
  
- 如果内部部署环境中拥有邮箱，则需要修改防火墙设置以允许从 TCP 端口 25 上的 Office 365 IP 地址连接到内部部署邮件服务器。Office 365 IP 地址的列表，请参阅[Office 365 Url 和 IP 地址范围](https://go.microsoft.com/fwlink/p/?linkid=228887)。
    
- 如果没有更多邮件应传递到内部部署环境中，请**立即修复**的通知中单击以便 Office 365 可以立即拒绝具有无效收件人的邮件。这将降低无效收件人，可能会影响普通邮件传递超出贵组织的配额的风险。或者，您可以使用以下说明手动修复问题： 
    
  - 禁用或删除连接器从 Office 365 到内部部署环境： Office 365 管理中心\>**管理中心** \> **Exchange** \> **邮件流** \> **连接器**\>选择连接器与**Office 365**中的**从**值和**为**值**贵组织的电子邮件服务器**。通过单击**删除**删除连接器![删除图标](media/ITPro-EAC-DeleteIcon.gif)，或通过单击**编辑**禁用连接器![编辑图标](media/ITPro-EAC-EditIcon.gif)和取消选中，则**将其打开**。
    
  - 更改您的内部部署与相关联的 Office 365 中的接受的域从**内部中继**到**权威**的邮件环境。有关说明，请参阅[Exchange Online 中管理接受域](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx)。
    
    **注意**： 通常情况下，这些更改将一小时 30 分钟之间才会生效。一个小时后，确认您不再收到错误。
    
如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。
  
## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>错误代码： 450 4.4.317 无法连接到远程服务器

通常情况下，此错误表示 Office 365 连接到目标消息服务器上，但服务器响应即时错误，或者不满足连接要求。错误详细信息将说明该问题。例如：
  
- 目标消息服务器响应一个"服务不可用"错误，指示服务器不能维护与 Office 365 的通信。
    
- 连接器配置为要求 TLS，但目标消息服务器不支持 TLS。
    
验证的 TLS 设置和您的内部部署上的证书消息服务器和连接器上的 TLS 设置。
  
如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。
  
## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>错误代码： 450 4.4.318 连接已关闭突然

此错误通常意味着 Office 365 通信时遇到困难与本地邮件环境，以便连接已断开。此错误可能的原因是：
  
- 防火墙使用 SMTP 包检查规则，并且这些规则不能正常工作。
    
- 您的内部部署邮件服务器不正确 （如服务挂起、 崩溃或系统资源不足） 工作，导致超时的服务器并关闭该连接到 Office 365。
    
- 没有您的内部部署环境与 Office 365 之间的网络问题。如果问题仍然存在，请与您的网络团队解决问题。
    
找出哪些方案适用于您，并进行必要的纠正。
  
如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。
  
## <a name="error-code-450-47320-certificate-validation-failed"></a>错误代码： 450 4.7.320 证书验证失败

通常，此错误表示 Office 365 尝试验证目标消息服务器的证书时遇到错误。错误详细信息将解释错误。例如：
  
- 证书过期
    
- 证书主题不匹配
    
- 证书不再有效
    
请修复证书或连接器，以便在 Office 365can 排队的邮件传递。
  
如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。
  
## <a name="other-error-codes"></a>其他错误代码

Office 365 时遇到困难到您的内部部署或消息服务器的合作伙伴提供消息。使用错误的**目标服务器**信息检查您的环境中的问题或修改连接器，如果没有配置错误。 
  
如果错误是合作伙伴组织 （例如，第三方云服务提供商） 中，您需要联系您的合作伙伴可以解决此问题。
  


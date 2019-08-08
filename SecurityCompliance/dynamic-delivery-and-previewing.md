---
title: 使用 Office 365 ATP 安全附件进行动态传递和预览
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: 设置 ATP 安全附件策略时, 请选择 "动态传递" 以避免邮件延迟, 并使用户能够预览正在扫描的附件。
ms.openlocfilehash: 203f5082701f1f3eeea36b385918328cb85deb81
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230646"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>使用 Office 365 ATP 安全附件进行动态传递和预览

## <a name="overview"></a>概述

动态传递是可选择用于[ATP 安全附件](atp-safe-attachments.md)的选项。 阅读本文, 了解有关[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)中的动态传递和附件预览功能的信息。

为您的组织[设置 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)时, 有几个选项可用于处理电子邮件附件。 其中包括 "**阻止**"、"**替换**" 和 "**动态传递**"。 根据配置 ATP 安全附件策略的方式, 在扫描附件时, 电子邮件收件人可能会遇到电子邮件传递的轻微延迟。 若要避免邮件延迟, 请选择 "**动态传递**"。
  
## <a name="how-dynamic-delivery-works"></a>动态传递的工作原理
  
动态传递通过将电子邮件的正文发送给具有每个电子邮件附件占位符的收件人来消除电子邮件延迟。 该占位符将一直保留, 直到通过[ATP 安全附件](atp-safe-attachments.md)扫描并确定附件的副本是安全的。 

- 每个附件被清除后, 即可打开或下载。 

- 如果某个附件被确定为恶意附件, 则会将其发送到隔离区, 其中组织的安全团队 (如 Office 365 全局管理员或安全管理员) 的用户可以[在 Office 365 中管理隔离的邮件](manage-quarantined-messages-and-files.md)。

大多数 Pdf 和 Office 文档可在 ATP 扫描进行过程中在安全模式下进行预览。 如果附件与动态传递预览器不兼容, 则在完成 ATP 安全附件扫描之前, 电子邮件收件人会看到一个附件占位符。

> [!TIP]
> 如果您使用的是移动设备, 并且 Pdf 在最初不在动态传递预览器中呈现, 请尝试使用移动浏览器登录 Office 365。

通过动态传递, 用户可以立即阅读并回复他们的电子邮件, 同时分析他们的附件。 

ATP 安全附件扫描发生在 Office 365 数据所在的同一个区域中。 有关数据中心地理位置的详细信息, 请参阅[您的数据位于何处？](https://products.office.com/where-is-your-data-located?geo=All) 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>当有人转发包含附件的电子邮件时, 会发生什么情况？

假定组织正在对其[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)使用动态传递, 并且有人收到包含附件的电子邮件。 现在, 假设某人将电子邮件转发给其他人。 会发生什么情况？ 这取决于其他收件人是否包含在 ATP 安全附件策略中。
  
- 如果使用动态传递选项的 ATP 安全附件策略覆盖某个收件人, 则收件人将看到该占位符, 并能够预览兼容文件。
    
- 如果 ATP 安全附件策略未涵盖某个收件人, 则电子邮件和附件将继续进行, 而不需要任何 ATP 安全附件扫描或附件占位符。
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>动态传递所需的工作原理是什么？

- 您的组织必须具有[Office 365 高级威胁防护](office-365-atp.md)
    
- 必须使用动态传递选项为 ATP 安全附件定义策略 (请参阅[在 Office 365 中设置 Atp 安全附件策略](set-up-atp-safe-attachments-policies.md))
    
- 您的组织的电子邮件必须托管在 Office 365 中。 尽管[office 365 高级威胁防护可用于任何 SMTP 邮件传输代理](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp)(如 Exchange Server), 但 ATP 安全附件的动态传递选项要求组织的电子邮件托管在 Office 365 中。 如果您的电子邮件不是托管在 Office 365 中, 请选择不同的[ATP 安全附件策略选项](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), 如**Block**。
    
## <a name="additional-considerations"></a>其他注意事项

在某些情况下, 不支持动态传递。 其中包括以下项：
  
- 公用文件夹中的电子邮件
    
- 使用自定义规则从用户邮箱中路由的电子邮件, 然后再返回到该用户的邮箱
    
- 移动 (自动或手动) 从托管邮箱移到其他位置 (包括存档文件夹) 的电子邮件
    
- 删除的电子邮件
    
- 处于错误状态的用户的邮箱搜索文件夹
    
- Exchange Online 管理员已在其中启用 Exclaimer 的环境。 若要解决此问题, 请参阅[使用 ATP 动态传递和 Exclaimer 时, 带有附件的邮件不会送达](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)

- 使用[安全/多用途 Internet 邮件扩展 (S/MIME)](s-mime-for-message-signing-and-encryption.md)加密的邮件

- 在不支持动态传递的情况下, ATP 安全附件不会扫描电子邮件。 但是, 将检查包含 Url 的附件的电子邮件, 具体取决于您的[ATP 安全链接策略](set-up-atp-safe-links-policies.md)的配置方式。 在这些情况下, 将检查电子邮件和 Office 文件中的 Url。

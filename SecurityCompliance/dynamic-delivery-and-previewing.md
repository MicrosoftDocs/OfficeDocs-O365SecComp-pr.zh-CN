---
title: 动态传递和与 Office 365 ATP 安全附件预览
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: 将您 ATP 附件安全策略设置，当您选择动态传递，以避免消息延迟和使人们可以预览正在被扫描的附件。
ms.openlocfilehash: ae027986cf5114bd024c679a59975d1e4be52d32
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995143"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>动态传递和与 Office 365 ATP 安全附件预览

**摘要**： 动态传递是可以为[ATP 安全附件](atp-safe-attachments.md)选择一个选项。阅读此文，了解有关动态交付和[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)中的附件预览功能。

当[ATP 安全附件策略设置](set-up-atp-safe-attachments-policies.md)为贵组织有多种选择如何处理电子邮件附件。其中包括**阻止**、**替换**和**动态传递**。根据 ATP 安全附件策略的配置方式，电子邮件收件人在扫描及其附件时可能遇到次要中电子邮件传递延迟。若要避免出现邮件延迟，请选择**动态传递**。
  
## <a name="how-dynamic-delivery-works"></a>动态传递的工作原理
  
动态传递通过将通过一封电子邮件的正文发送给收件人提供每个电子邮件附件的占位符，消除了电子邮件延迟。扫描附件的副本并将其由为安全起见[ATP 安全附件](atp-safe-attachments.md)一直占位符。 

- 每个附件处于清除状态，它是可用于打开或下载。 

- 如果附件确定恶意，它是发送到隔离，某人贵组织的安全工作组 （例如 Office 365 全局管理员或安全管理员） 可以[管理 Office 365 中的隔离的邮件](manage-quarantined-messages-and-files.md)。

大多数 Pdf 和 Office ATP 扫描正在进行时，可以在安全模式下预览文档。如果某个附件不可与动态传递预览器兼容，电子邮件收件人请参阅附件占位符，直到 ATP 安全附件扫描已完成。

> [!TIP]
> 如果您使用的移动设备，Pdf 不呈现中最初动态传递预览器，请尝试登录到 Office 365 使用移动浏览器。

使用动态传递，用户可以读取和响应对其电子邮件立即时正在分析其附件。 

ATP 安全附件扫描考虑放置在 Office 365 数据所在的同一区域中。有关数据中心地理区域的详细信息，请参阅[其中是位于数据？](https://products.office.com/where-is-your-data-located?geo=All) 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>当某人的转发电子邮件时，会发生什么情况包含附件？

假设其[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)中，为组织使用动态传递有人收到包含附件的电子邮件。现在假设此人将电子邮件转发给其他人。会发生什么情况？这取决于是否 ATP 安全附件策略中包含其他收件人。
  
- 如果收件人使用动态交付选项 ATP 安全附件策略涵盖，收件人会占位符，看到可以预览兼容的文件中。
    
- 如果收件人不受 ATP 安全附件策略，然后电子邮件和附件将经过，不含 ATP 安全扫描的附件或附件占位符。
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>有什么要求动态传递工作？

- 您的组织必须具有[Office 365 高级威胁保护](office-365-atp.md)
    
- 必须为 ATP 安全附件使用动态交付选项 （请参阅[Set up Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)） 定义策略
    
- 必须在 Office 365 中承载您的组织的电子邮件
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a>是否有为其动态传递不可用的方案？

有某些方案中不支持动态送达。其中包括：
  
- 在公用文件夹中的电子邮件
    
- 外出时的路由，然后再返回到使用自定义规则的用户的邮箱的电子邮件
    
- 将托管的邮箱超出传到其他位置，包括移动 （自动或手动） 的电子邮件存档文件夹
    
- 将被删除的电子邮件
    
- 处于错误状态的用户的邮箱搜索文件夹
    
- Exchange Online 管理员已在其中启用 Exclaimer 的环境。若要解决此问题，请参阅[使用 ATP 动态传递和 Exclaimer 时都未将发送带附件的邮件](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)

- 使用[安全/多用途 Internet 邮件扩展 (S/MIME)](s-mime-for-message-signing-and-encryption.md)加密的邮件）


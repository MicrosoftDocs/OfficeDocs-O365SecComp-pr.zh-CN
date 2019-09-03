---
title: 发送垃圾电子邮件后，从受限用户门户删除用户
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 如果用户从 Office 365 连续发送被归类为垃圾邮件的电子邮件，这些用户将被限制发送任何其他电子邮件。
ms.openlocfilehash: 56f1a34fe4b47a722ff1dace73dd001f0c4812a2
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854716"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>发送垃圾电子邮件后，从受限用户门户删除用户

如果用户从 Office 365 连续发送被归类为垃圾邮件的电子邮件，这些用户将被限制发送电子邮件，但仍然能够接收电子邮件。 该用户将在服务中列为错误的出站发件人，并且将收到未送达报告 (NDR)，其中指出：

> “你的邮件无法送达，因为系统认为你不是有效的发件人。 这种情形最常见的原因是怀疑你的电子邮件地址正在发送垃圾邮件，且不再允许它发送电子邮件。  请联系电子邮件管理员获取帮助。 远程服务器返回“550 5.1.8 拒绝访问，错误出站发件人”。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？
<a name="sectionSection0"> </a>

估计完成时间：5 分钟
  
您必须先获得权限，然后才能执行此过程或多个过程。 若要查看所需的权限，请参阅 [Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的“反垃圾邮件”条目。

以下步骤也可以通过远程 PowerShell 执行。 使用 Get-BlockedSenderAddress cmdlet 获取受限用户的列表，并使用 Remove-BlockedSenderAddress  移除限制。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>移除对阻止的 Office 365 电子邮件帐户的限制

可在安全与合规中心 (SCC) 中完成此任务。 有关 SCC 的详细信息, 请[转到安全与合规中心](go-to-the-securitycompliance-center.md)。 若要执行这些功能，你需要在 **“组织管理”** 或 **“安全管理员”** 角色组中。 有关 SCC 角色组的更多详细信息，请[转到安全与合规中心中的“权限”](permissions-in-the-security-and-compliance-center.md)。

1. 使用具有 office 365 全局管理员权限的工作或学校帐户登录到 office 365 安全与合规中心，然后在左侧的列表中展开 **“威胁管理”**，选择 **“审阅”**，然后选择 **“受限用户”**。
    
    > [!TIP]
    > 若要直接转到安全&amp;合规中心中的 **“受限用户”** 页面（以前称为“操作中心”），请使用此 URL：> [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. 此页面将包含已被阻止发送电子邮件的用户的列表。  查找想要为其移除限制的用户，然后选择 **“取消阻止”**。

3. 一个飞出窗口将转到有关其发送受限的帐户的详细信息。 应按照建议进行操作，确保在帐户实际遭到破坏的情况下采取适当的措施。 完成后，单击 **“下一步”**。

4. 下一个屏幕包含可帮助防止以后遭到破坏的建议。 启用多重身份验证 (MFA) 和更改密码是一种很好的防御措施。 完成后，单击 **“解锁用户”**。

5. 单击 **“是”** 确认更改。

    > [!NOTE]
    > 移除限制可能需要 30 分钟或更长时间。 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>确保在这种情况下提醒管理员

Office 365 安全与合规性警报策略页下有一条“被限制发送电子邮件的用户”警报策略。 此策略以前是出站垃圾邮件策略，但现在是 Office 365 警报平台的原生策略。 有关警报的详细信息，请转到[安全与合规中心中的警报策略](alert-policies.md)。

> [!IMPORTANT]
> 为了警报正常工作，必须启用审核日志搜索。 有关详细信息，请参阅[启用或禁用 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。

此警报的策略是默认策略，随每个 Office 365 租户提供，无需进行设置。 它被视为一种严重性警报，每当用户被限制发送电子邮件时，都会在触发警报时向配置的 TenantAdmins 组发送电子邮件。 管理员可通过转到 SCC 门户 >“警报”>“警报策略”>“被限制发送电子邮件的用户”，更新在发生警报时收到通知的组。

你将能够编辑警报以便执行以下操作：
- 打开/关闭电子邮件通知
- 向所需的收件人发送电子邮件
- 限制每天收到的通知

## <a name="checking-for-and-removing-restrictions-using-powershell"></a>使用 PowerShell 检查和移除限制
适用于受限用户的 PowerShell 命令包括：
- `Get-BlockedSenderAddress`：运行以检索被限制发送电子邮件的用户的列表
- `Remove-BlockedSenderAddress`：运行以解除用户限制

## <a name="for-more-information"></a>有关详细信息

[响应遭到入侵的电子邮件帐户](responding-to-a-compromised-email-account.md)

[了解“被限制发送电子邮件的用户”警报](https://docs.microsoft.com/zh-CN/office365/securitycompliance/alert-policies)

[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)

[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)

[安全与合规中心内的警报策略](https://docs.microsoft.com/zh-CN/office365/securitycompliance/alert-policies)

---
title: 发送垃圾电子邮件后，从受限用户门户删除用户
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/12/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 如果用户不断发送来自受分类为垃圾邮件的 Office 365 的电子邮件, 则会受到限制, 无法发送更多的邮件。
ms.openlocfilehash: 3e05b250d5a3cdca79c7cf494b84be02ce3ecdc9
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857622"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>发送垃圾电子邮件后，从受限用户门户删除用户

如果用户持续发送的电子邮件是来自 Office 365 的垃圾邮件, 则他们将受到限制, 无法发送电子邮件, 但仍然能够收到。 用户将在服务中列为错误的出站发件人, 并将收到一份状态为的未送达报告 (NDR):

> 无法传递你的消息, 因为你未被识别为有效的发件人。 导致此问题的最常见原因是, 你的电子邮件地址怀疑发送垃圾邮件, 并且不再允许它发送电子邮件。  请联系你的电子邮件管理员以获取帮助。 远程服务器返回 "550 5.1.8 访问被拒绝, 错误的出站发件人"。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？
<a name="sectionSection0"> </a>

估计完成时间：5 分钟
  
您必须先获得权限，然后才能执行此过程或多个过程。 若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的 "反垃圾邮件" 条目。

还可以通过远程 PowerShell 执行以下过程。 使用 BlockedSenderAddress cmdlet 获取受限制的用户列表, 并删除-BlockedSenderAddress 以删除限制。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>删除对被阻止的 Office 365 电子邮件帐户的限制

您在安全 & 合规中心 (SCC) 中完成此任务。 有关 SCC 的更多详细信息,[请转到 Security & 合规性中心](go-to-the-securitycompliance-center.md)。 必须在 "**组织管理**" 或 "**安全管理员**" 角色组中, 才能执行这些功能。 若要详细了解 SCC 角色组,[请转到 Security & 合规性中心中的 "权限"](permissions-in-the-security-and-compliance-center.md) 。

1. 使用具有 Office 365 全局管理员权限的工作或学校帐户登录到 Office 365 安全性和合规性中心, 并在左侧的列表中展开 "**威胁管理**", 选择 "**查看**", 然后选择 "**受限"用户**。
    
    > [!TIP]
    > 若要直接转到安全&amp;合规性中心中的 "**受限用户**" 页 (以前称为 "操作中心"), 请使用以下 URL: >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. 此页面将包含已阻止发送电子邮件的用户的列表。  查找要从中删除限制的用户, 然后选择 "**取消阻止**"。

3. 飞出将进入有关其发送受限的帐户的详细信息。 应仔细考虑这些建议, 以确保在帐户实际受到危害时采取正确的措施。 完成后, 单击 "**下一步**"。

4. 下一个屏幕提供了有助于防止将来受到危害的建议。 启用多重身份验证 (MFA) 和更改密码是一项良好的防御措施。 完成后, 单击 "**取消阻止用户**"。

5. 单击 **"是"** 确认更改。

    > [!NOTE]
    > 删除限制可能需要30分钟或更长时间。 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>确保在发生此情况时提醒管理员

"Office 365 Security & 合规性警报策略" 页下的 "将受限制的用户发送电子邮件" 警报作为策略提供。 这是以前的出站垃圾邮件策略, 但现在是 Office 365 警报平台的本地。 有关通知的详细信息, 请转到[Security & 合规性中心中的 "通知策略](alert-policies.md)"。

> [!IMPORTANT]
> 若要使警报正常运行, 必须打开审核日志搜索。 有关详细信息, 请参阅如何[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。

此警报的策略是默认策略, 并附带每个 Office 365 租户, 无需进行设置。 它被视为高严重性警报, 当用户被限制发送邮件时, 将通过电子邮件通知已配置的 TenantAdmins 组。 管理员可以通过转到 SCC 门户 > 警报 > 通知策略 > 受限制发送电子邮件的用户) 在此通知发生警报时更新组通知。

你可以将此通知编辑为:
- 打开/关闭电子邮件通知
- 通过电子邮件发送所需收件人
- 限制每天获取的通知

## <a name="for-more-information"></a>详细信息

[响应已泄露的电子邮件帐户](responding-to-a-compromised-email-account.md)

[了解限制发送电子邮件通知的用户](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)

[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)

[安全 & 合规中心中的警报策略](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

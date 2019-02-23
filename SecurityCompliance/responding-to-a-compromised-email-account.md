---
title: 响应 Office 365 中遭到入侵的电子邮件帐户
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: 了解如何识别和响应 Office 365 中的受损电子邮件帐户
ms.openlocfilehash: 8d2e7f501b6e3ee73a14d4d7b3edb4c49f99d051
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213212"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>响应 Office 365 中遭到入侵的电子邮件帐户

**摘要**了解如何在 Office 365 中识别和响应已泄露的电子邮件帐户。

## <a name="what-is-a-compromised-email-account-in-office-365"></a>什么是 Office 365 中的受损电子邮件帐户？
可以通过使用凭据 (例如用户名和密码或 PIN) 来控制对 Office 365 邮箱、数据和其他服务的访问。当目标用户之外的其他人盗取这些凭据时, 被盗用的凭据被视为已泄露。使用它们, 攻击者可以以原始用户的形式登录, 并执行非法操作。通过使用失窃凭据, 攻击者可以访问用户的 Office 365 邮箱、SharePoint 文件夹或用户的 OneDrive 中的文件。一个常见的操作是, 攻击者将电子邮件作为原始用户发送给组织内部和外部的收件人。当攻击者通过电子邮件将数据发送给外部收件人时, 这称为 data exfiltration。

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>受损坏的 Office 365 电子邮件帐户的症状
用户可能会注意到并报告其 Office 365 邮箱中的异常活动。下面列出了一些常见症状:
- 可疑活动, 如丢失或删除的电子邮件。
- 如果发件人的 "**已发送邮件**" 文件夹中的相应电子邮件不存在, 则其他用户可能会收到受损帐户发来的电子邮件。
- 未由预期用户或管理员创建的收件箱规则的存在。这些规则可能会自动将电子邮件转发到未知地址, 或将其移动到 "**笔记**"、"**垃圾邮件**" 或 " **RSS 订阅**" 文件夹中。
- 在全局地址列表中可能会更改用户的显示名称。
- 阻止用户的邮箱发送电子邮件。
- Microsoft Outlook 或 web 上的 Outlook (以前称为 Outlook web App) 中的 "已发送邮件" 或 "已删除邮件" 文件夹包含常见的黑客攻击帐户, 如 "我在伦敦的电子邮件中, 发送金钱"。
- 异常配置文件更改 (如名称、电话号码或邮政编码) 已更新。
- 需要进行多个密码更改 (例如, 需要多次更改)。
- 最近添加了邮件转发。
- 最近添加了一个不寻常的签名, 例如假冒银行签名或处方药品签名。

如果用户报告以上任何症状, 应执行进一步调查。Office 365 Security & 合规性中心和 Azure 门户提供了一些工具, 可帮助您调查怀疑可能受到威胁的用户帐户的活动。
- Office 365 中的 "统一审核日志" 安全 & 合规中心-通过筛选日期范围内的所有活动, 在最近发生可疑活动之前的日期范围内, 查看该可疑帐户的所有活动。不要在搜索过程中对活动进行筛选。
- 使用 azure ad 登录日志和在 azure ad 门户中可用的其他风险报告。检查以下各列中的值:
    - 查看 IP 地址
    - 登录位置
    - 登录时间
    - 登录成功或失败

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>如何保护电子邮件功能并将其还原到可疑的受危害的 Office 365 帐户和邮箱

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

即使已重新获得帐户访问权限, 攻击者也可能已添加了后门项, 使攻击者能够恢复帐户的控制。

您必须执行以下所有步骤以更快地重新获取对帐户的访问权限, 以确保 hijacker 不会恢复控制您的帐户。这些步骤可帮助您删除 hijacker 可能已添加到您的帐户中的任何后门项。在执行这些步骤后, 我们建议您运行病毒扫描以确保您的计算机不会受到威胁。

### <a name="step-1-reset-the-users-password"></a>步骤1重置用户的密码
> [!WARNING]
> 不要通过电子邮件向目标用户发送新密码, 因为此时攻击者仍可以访问邮箱。

1. 按照管理员中的其他人的 "重置 office 365 业务密码" 过程[操作: 重置 office 365 业务密码](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)

**注意：**
- 请确保密码是强密码, 并且包含大写和小写字母、至少一个数字以及至少一个特殊字符。 
- 请勿重用你的最后五个密码中的任何一个。尽管密码历史要求允许您重用较新的密码, 但您应选择攻击者无法猜测的内容。
- 如果您的本地标识与 Office 365 联合在一起, 您必须更改本地密码, 然后必须向管理员通知攻击的安全。

> [!TIP]
> 强烈建议您启用多重身份验证 (MFA) 以防止受到危害, 尤其是具有管理权限的帐户。 你可以在[此处](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)了解详细信息。

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>步骤2删除可疑电子邮件转发地址
1. 打开 " **Office 365 管理中心 > 活动用户**"。
2. 查找 "有问题的用户帐户" 和 "展开**邮件设置**"。
3. 对于**电子邮件转发**, 请单击 "**编辑**"。
4. 删除任何可疑的转发地址。

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>步骤3禁用任何可疑的收件箱规则
1. 使用 Outlook 网页登录到用户的邮箱。
2. 单击齿轮图标并单击 "**邮件**"。
3. 单击 **"收件箱" 和 "扫描规则**", 并查看规则。
4. 禁用或删除可疑规则。

### <a name="step-4-unblock-the-user-from-sending-mail"></a>步骤4取消阻止用户发送邮件
如果在 illicitly 中使用可疑的受攻击邮箱发送垃圾邮件, 则可能已阻止该邮箱发送邮件。
1. 若要取消阻止邮箱发送邮件, 请按照[发送垃圾电子邮件后从阻止列表中删除用户、域或 IP 地址](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email )中的过程操作。

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>步骤5可选: 阻止用户帐户登录
> [!IMPORTANT]
> 您可以阻止可疑的受攻击帐户登录, 直到您认为可以安全地重新启用访问。

1. 转到 Office 365 管理中心。
2. 在 Office 365 管理中心 中，选择" **用户** "。
3. 选择要阻止的员工, 然后在用户窗格中选择 "**登录状态**" 旁边的 "**编辑**"
4. 在" **登录状态** "窗格中，选择" **阻止登录** "，然后" **保存** "。 
5. 在 Office 365 管理中心的左下角导航窗格中, 展开 "**管理中心**", 然后选择 " **Exchange**"。
6. 在 Exchange 管理中心中, 导航到 "**收件人" "> 邮箱**"。
7. 选择用户, 然后在 "用户属性" 页上的 "**移动设备**" 下, 单击 "**禁用 Exchange ActivcSync** " 并**禁用 "适用于设备的 OWA** ", 并对二者同时回答 **"是"**
8. 在 "**电子邮件连接**" 下,**禁用**并回答 **"是"**。 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>步骤6可选: 从所有管理角色组中删除可疑的受攻击帐户
> [!NOTE]
> 在帐户受到保护之后, 可以恢复管理角色组成员身份。

1. 使用全局管理员帐户登录到 Office 365 管理中心并打开**活动用户**。
2. 查找可疑的受攻击帐户并手动查看是否有分配给该帐户的任何管理角色。
3. 打开 "**安全 & 合规中心**"。
4. 单击 "**权限**"。
5. 手动查看角色组, 以查看可疑的受攻击帐户是否为它们的成员。 如果是, 则单击 "角色组", 然后单击 "**编辑角色组**"。 b. 单击 "**选择成员**", 然后单击 "**编辑**" 从角色组中删除用户。
6. 打开**Exchange 管理中心**
7. 单击 "**权限**"。
8. 手动查看角色组, 以查看可疑的受攻击帐户是否为它们的成员。如果是, 则单击 "角色组", 然后单击 "**编辑**"。 b. 使用 "**成员**" 部分从角色组中删除用户。

### <a name="step-7-optional-additional-precautionary-steps"></a>步骤7可选: 其他预防措施步骤
1. 请确保验证已发送的邮件。您可能需要向 "联系人" 列表通知用户您的帐户已泄露。攻击者可能已向其提问了金钱, 例如, 您在不同的国家/地区和所需的资金, 或者攻击者可能会向其发送病毒以劫持其计算机。
2. 使用此 Exchange 帐户作为其备用电子邮件帐户的任何其他服务可能已泄露。首先, 为 Office 365 订阅执行这些步骤, 然后为其他帐户执行这些步骤。
3. 请确保您的联系信息 (如电话号码和地址) 正确无误。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>安全的 Office 365, 如 cybersecurity pro
您的 Office 365 订阅附带了一组功能强大的安全功能, 可用于保护您的数据和用户。 使用[Office 365 安全路线图: 前30天、90天和更高版本的首要优先级](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352), 以实现 Microsoft 建议的保护 Office 365 租户的最佳做法。
- 在前30天内要完成的任务。 这些值会立即生效, 并对用户造成影响较小。
- 要在90天内完成的任务。它们需要花一点时间来规划和实施, 但大大提高了您的安全状况。
- 超过90天。这些增强功能将在您的前90天工作中构建。

## <a name="see-also"></a>另请参阅:
- [Office 365 的安全最佳做法](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [在 Office 365 中检测并修正 Outlook 规则和自定义窗体注入攻击](detect-and-remediate-outlook-rules-forms-attack.md)
- [Internet 犯罪投诉中心](http://www.ic3.gov/preventiontips.aspx)
- [证券和交换委员会-"网络钓鱼" 欺诈](http://www.sec.gov/investor/pubs/phishing.htm)

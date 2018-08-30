---
title: 响应 Office 365 中遭到入侵的电子邮件帐户
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: 了解如何识别并响应在 Office 365 中受到攻击的电子邮件帐户
ms.openlocfilehash: ef97ecd3198234cf2c3d609f81a4a4a8af2c237e
ms.sourcegitcommit: 08f36794552e2213d0baf35180e47744d3e87fe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "23531875"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>响应 Office 365 中遭到入侵的电子邮件帐户

**摘要**了解如何识别并响应在 Office 365 中受到攻击的电子邮件帐户。

## <a name="what-is-a-compromised-email-account-in-office-365"></a>什么是 Office 365 中的威胁电子邮件帐户？
访问 Office 365 邮箱、 数据和其他服务，使用凭据，例如用户名和密码或 PIN 控制。当某人之外的预期用户窃取这些凭据时，被盗的凭据被视为受到威胁。与他们攻击者可以为原始用户登录并执行非法的操作。使用窃取的凭据，攻击者可以访问用户的 Office 365 邮箱、 SharePoint 文件夹或用户的 OneDrive 中的文件。常见的一个操作是攻击者向收件人组织内外均为原始用户发送电子邮件。如果攻击者向外部收件人电子邮件数据，这就称为数据 exfiltration。

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>受到攻击的 Office 365 电子邮件帐户的症状
用户可能会注意到和报告在其 Office 365 邮箱中的异常活动。下面是一些常见症状：
- 可疑活动，如缺失或被删除的电子邮件。
- 其他用户可能会收到电子邮件从受到攻击的帐户没有相应的发件人的**已发送邮件**文件夹中现有的电子邮件。
- 预期的用户或管理员不需要创建的收件箱规则的状态。这些规则可能会自动转发到未知地址的电子邮件或将它们移动到的**注释**，**垃圾邮件**或**RSS 订阅**的文件夹。
- 可能的全局地址列表中更改的用户显示名称。
- 用户的邮箱阻止发送电子邮件。
- 在 Microsoft Outlook 或 Microsoft Outlook Web App 中的已发送或已删除邮件文件夹包含常见黑客攻击-帐户邮件，如"我正在停止伦敦，发送资金。"
- 特殊的配置文件更改，如名称、 电话号码或邮政编码已进行了更新。
- 特殊凭据更改，如多个密码更改是必需的。
- 最近添加了邮件转发。
- 特殊的签名最近已添加，如假银行业签名或惯例药品签名。

如果用户报告的任何上述症状，应执行进一步调查。Office 365 安全性和合规性中心和 Azure 门户提供工具可以帮助您调查您怀疑可能受到威胁的用户帐户的活动。
- Office 365 统一审核日志中的安全性和合规性中心-查看筛选结果的日期范围跨越从可疑活动发生为当前日期前一刻可疑的帐户的所有活动。不要筛选的活动搜索过程中。
- 使用 Azure AD 登录日志和其他风险报表的 Azure AD 门户中可用。检查这些列中的值：
    - 查看 IP 地址
    - 登录位置
    - 登录时间
    - 登录成功或失败



## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>如何保护和还原到可疑的电子邮件函数威胁 Office 365 帐户和邮箱

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

即使已重新访问获得到您的帐户后，攻击者可能已添加使攻击者恢复该帐户的控制后门条目。

您必须执行以下所有步骤才能重新访问您的帐户，以确保不会继续 hijacker 更好更快地控制您的帐户。这些步骤可帮助您删除 hijacker 可能已添加到您的帐户的任何后门条目。执行这些步骤后，我们建议您运行病毒扫描，以确保您的计算机不破坏。

### <a name="step-1-reset-the-users-password"></a>步骤 1 重置用户的密码
> [!WARNING]
> 不要给目标用户通过电子邮件发送新密码，如攻击者仍可以访问到邮箱此时。

1. 遵循重置 Office 365 业务密码的某人中的其他过程[Admins： 重置 Office 365 业务密码](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)

**注意：**
- 确保密码强，且它包含大写和小写字母、 至少一个数字和至少一个特殊字符。 
- 不重用的任何您最近五密码。即使密码历史记录要求使您可以重用较新密码，您应选择内容的攻击者不能猜测。
- 如果您的本地标识与 Office 365 联盟，则必须更改密码内部部署，然后必须通知危害的管理员。

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>步骤 2 删除可疑的电子邮件转发地址
1. 打开**Office 365 管理中心 > 活动用户**。
2. 查找问题的用户帐户，展开**邮件设置**。
3. 以**电子邮件转发**，单击**编辑**。
4. 删除任何可疑转发地址。

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>步骤 3 禁用任何可疑收件箱规则
1. 登录到用户的邮箱使用 Outlook Web App (OWA)。
2. 单击齿轮图标，单击**邮件**。
3. 单击**收件箱和偏离规则**并查看的规则。
4. 禁用或删除可疑的规则。

### <a name="step-4-unblock-the-user-from-sending-mail"></a>步骤 4 取消阻止用户发送邮件
如果可疑受到攻击的邮箱非法用于发送垃圾电子邮件，则可能邮箱已被阻止发送邮件。
1. 若要取消阻止发送邮件的邮箱，请按照中[删除用户、 域或 IP 地址从阻止列表后发送垃圾电子邮件](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email )的过程。

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>步骤 5 可选： 阻止从签名中的用户帐户
> [!IMPORTANT]
> 您可以阻止从签名接程序直到您认为安全地重新启用访问的可疑受到攻击的帐户。

1. 转到 Office 365 管理中心。
2. 在 Office 365 管理中心中，选择**用户**。
3. 选择您想要阻止，员工，然后再在用户窗格中选择**登录 status**旁边的**编辑**
4. 在**登录状态**窗格中，选择**登录被阻止**，然后**保存**。 
5. 在 Office 365 管理中心中，在左导航窗格中，展开**管理中心**，然后选择**Exchange**。
6. 在 Exchange 管理中心中，导航到**收件人 > 邮箱**。
7. 选择该用户，并在用户属性页中，在**移动设备**下单击**禁用 Exchange ActivcSync**和**禁用 OWA for Devices**到这两个回答**是**。
8. 在**电子邮件连接**、**禁用**和应答**是**。 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>步骤 6 可选： 从所有管理角色组中删除可疑受到攻击的帐户
> [!NOTE]
> 在固定帐户之后，可以还原管理角色组成员身份。

1. 登录到 Office 365 管理中心使用的全局管理员帐户并打开**活动用户**。
2. 查找可疑威胁帐户和手动检查以查看是否有任何管理角色分配给该帐户。
3. 打开**安全性和合规性中心**。
4. 单击**权限**。
5. 手动检查以查看是否可疑威胁帐户是其中的任何成员的角色组。 如果： 答： 单击角色组，单击**编辑角色组**。 b.单击**选择成员**和**编辑**以从角色组中删除用户。
6. 打开**Exchange 管理中心**
7. 单击**权限**。
8. 手动检查以查看是否可疑威胁帐户是其中的任何成员的角色组。如果： 答： 单击角色组，单击**编辑**。 b.使用**成员**部分，若要从角色组中删除用户。

### <a name="step-7-optional-additional-precautionary-steps"></a>步骤 7 可选： 其他预防
1. 请确保您确认您已发送的邮件。您可能需要告知您的帐户已泄露的联系人列表上的人员。攻击者可能已要求它们的资金，欺骗，例如，您已在不同的国家/地区闲置和所需资金，或攻击者可能会向其发送病毒也劫持其计算机。
2. 任何其他服务的其替代的电子邮件帐户已泄露用作此 Exchange 帐户。首先，为您的 Office 365 订阅，执行以下步骤，然后为其他帐户执行这些步骤。
3. 请确保您的联系人信息，如电话号码和地址正确。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>像网络专业人员的安全保护 Office 365
Office 365 订阅附带了强大的可用于保护您的数据和用户的安全功能集。 使用[Office 365 安全路线图： Top 优先级的前 30 天，90 天及其他认证实战](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)实现 Microsoft 建议的用于保护 Office 365 租户的最佳做法。
- 第一个 30 天内完成的任务。 这些没有直接影响，因此低影响到您的用户。
- 若要在 90 天内完成的任务。这些需要更多时间规划和实现但大大提高安全状况。
- 90 天前。在您的第一个 90 天工作中构建这些增强功能。

## <a name="see-also"></a>另请参阅：
- [Office 365 的安全最佳做法](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [检测并修正 Office 365 中的 Outlook 规则和自定义窗体注入攻击](detect-and-remediate-outlook-rules-forms-attack.md)
- [Internet 犯罪投诉中心](http://www.ic3.gov/preventiontips.aspx)
- [证券和交易委员会"网络钓鱼"欺诈](http://www.sec.gov/investor/pubs/phishing.htm)
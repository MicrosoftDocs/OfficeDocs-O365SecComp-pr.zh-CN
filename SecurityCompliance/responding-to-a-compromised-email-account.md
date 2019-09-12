---
title: 响应 Office 365 中遭到入侵的电子邮件帐户
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何识别并响应 Office 365 中遭到入侵的电子邮件帐户
ms.openlocfilehash: 4eaabfc65a6d3118dd995a14a1ce0c8e941a77fc
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156854"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>响应 Office 365 中遭到入侵的电子邮件帐户

**摘要** 了解如何识别并响应 Office 365 中遭到入侵的电子邮件帐户。

## <a name="what-is-a-compromised-email-account-in-office-365"></a>什么是 Office 365 中遭到入侵的电子邮件帐户？
通过使用凭据（例如用户名和密码或 PIN）来控制对 Office 365 邮箱、数据和其他服务的访问。 如果除预期用户以外的其他人窃取了这些凭据，则被盗的凭据将视为遭到入侵。 借助这些凭据，攻击者能够以原始用户的身份登录并执行非法操作。
通过使用窃取的凭据，攻击者可以访问用户的 Office 365 邮箱、SharePoint 文件夹或用户 OneDrive 中的文件。 其中一种常见操作是攻击者以原始用户的身份将电子邮件发送给组织内外的收件人。 当攻击者通过电子邮件将数据发送给外部收件人时，这称为数据泄露。

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>遭到入侵的 Office 365 电子邮件帐户的症状
用户可能会注意到并报告其 Office 365 邮箱中的异常活动。 下面是一些常见症状：
- 可疑活动，例如丢失或删除的电子邮件。
- 其他用户可能会收到来自遭到入侵的帐户的电子邮件，而发件人的“**已发送邮件**”文件夹中没有相应的电子邮件。
- 存在并非由预期用户或管理员创建的收件箱规则。 这些规则可以自动将电子邮件转发到未知地址，或将其移动到“**便笺**”、“**垃圾邮件**”或“**RSS 订阅**”文件夹。
- 在全局地址列表中，用户的显示名称可能已发生更改。
- 用户的邮箱被阻止发送电子邮件。
- Microsoft Outlook 或 Outlook 网页版（以前称为 Outlook Web App）中的“已发送邮件”或“已删除邮件”文件夹包含常见的黑客帐户邮件，例如“我被困在伦敦，请给我汇款”。
- 异常的个人资料更改，例如更新了姓名、电话号码或邮政编码。
- 异常的凭据更改，例如多次要求进行密码更改。
- 最近添加了邮件转发功能。
- 最近添加了异常的签名，例如假银行签名或处方药签名。

如果用户报告了上述任何症状，你应该进一步展开调查。 Microsoft 365 安全与合规中心和 Azure 门户提供了各种工具，可帮助你对疑似遭到入侵的用户帐户的活动展开调查。
- 安全与合规中心中的 Office 365 统一审核日志 - 通过筛选从可疑活动发生前一天到当前日期之间的日期范围的结果，检查可疑帐户的所有活动。 不要在搜索过程中筛选活动。
- 使用 Azure AD 登录日志和 Azure AD 门户中提供的其他风险报告。 检查以下列中的值：
    - 查看 IP 地址
    - 登录位置
    - 登录时间
    - 登录成功或失败

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>如何保护和恢复疑似遭到入侵的 Office 365 帐户和邮箱的电子邮件功能

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

即使你重新获得对帐户的访问权限，攻击者也可能添加了后门条目，这让攻击者能够恢复对该帐户的控制权。

你必须执行以下所有步骤才能重新获得对帐户的访问权限，以便更快地确保劫持者无法继续控制你的帐户。 这些步骤可帮助你删除劫持者可能已添加到你帐户的任何后门条目。 执行这些步骤后，我们建议你运行病毒扫描以确保你的计算机不会遭到入侵。

### <a name="step-1-reset-the-users-password"></a>步骤 1 重置用户密码
> [!WARNING]
> 不要通过电子邮件将新密码发送给预期用户，因为此时攻击者仍可以访问邮箱。

1. 按照“[管理员：重置 Office 365 商业版密码](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)”中的“为其他人重置 Office 365 商业版密码”步骤执行操作。

**注意：**
- 确保密码为强密码，并且包含大写和小写字母、至少一个数字和至少一个特殊字符。 
- 不要重复使用过去五个密码中的任何一个。 即使密码历史记录要求允许你重复使用最近使用过的密码，你也应该选择攻击者无法猜到的密码。
- 如果你的本地标识已与 Office 365 联合，则必须在本地更改密码，然后通知管理员帐户遭到入侵。

> [!TIP]
> 强烈建议你启用多重身份验证 (MFA) 以防止入侵，尤其是对于具有管理权限的帐户。  你可以在[此处](https://support.office.com/zh-CN/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)了解更多信息。

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>步骤 2 删除可疑的电子邮件转发地址
1. 打开“**Microsoft 365 管理中心 > 活动用户**”。
2. 找到存在问题的用户帐户并展开“**邮件设置**”。
3. 对于“**电子邮件转发**”，单击“**编辑**”。
4. 删除所有可疑的转发地址。

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>步骤 3 禁用任何可疑的收件箱规则
1. 使用 Outlook 网页版登录用户的邮箱。
2. 单击齿轮图标，然后单击“**邮件**”。
3. 单击“**收件箱和整理规则**”并查看规则。
4. 禁用或删除可疑的规则。

### <a name="step-4-unblock-the-user-from-sending-mail"></a>步骤 4 取消阻止用户发送邮件
如果疑似遭到入侵的邮箱被非法用于发送垃圾电子邮件，则可能是该邮箱已被阻止发送邮件。
1. 若要取消阻止邮箱发送邮件，请按照[在发送垃圾电子邮件后从阻止列表中删除用户、域或 IP 地址](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email )中的步骤执行操作。

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>步骤 5（可选）阻止用户帐户登录
> [!IMPORTANT]
> 你可以阻止疑似遭到入侵的帐户登录，直到你认为重新启用访问权限是安全的。

1. 转到 Microsoft 365 管理中心。
2. 在 Microsoft 365 管理中心，选择“**用户**”。
3. 选择要阻止的员工，然后在用户窗格中选择“**登录状态**”旁边的“**编辑**”
4. 在“**登录状态**”窗格上，选择“**阻止登录**”，然后选择“**保存**”。 
5. 在管理中心左下方的导航窗格中，展开“**管理中心**”，然后选择“**Exchange**”。
6. 在 Exchange 管理中心，导航到“**收件人 > 邮箱**”。
7. 选择用户，然后在用户属性页面的“**移动设备**”下，单击“**禁用 Exchange ActivcSync**”和“**禁用适用于设备的 OWA**”，并对两者选择“**是**”。
8. 在“**电子邮件连接**”下，单击“**禁用**”并选择“**是**”。 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>步骤 6（可选）从所有管理角色组中删除疑似遭到入侵的帐户
> [!NOTE]
> 在帐户受到保护后，可以恢复管理角色组成员身份。

1. 使用全局管理员帐户登录 Microsoft 365 管理中心，然后打开“**活动用户**”。
2. 找到疑似遭到入侵的帐户并手动检查是否为该帐户分配了任何管理角色。
3. 打开“**安全与合规中心**”。
4. 单击“**权限**”。
5. 手动检查角色组以查看疑似遭到入侵的帐户是否是其中任何一个组的成员。  如果是，a. 单击角色组，然后单击“**编辑角色组**”。
    b. 单击“**选择成员**”和“**编辑**”以从角色组中删除用户。
6. 打开“**Exchange 管理中心**”
7. 单击“**权限**”。
8. 手动检查角色组以查看疑似遭到入侵的帐户是否是其中任何一个组的成员。 如果是，a. 单击角色组，然后单击“**编辑**”。
    b. 使用“**成员**”部分从角色组中删除用户。

### <a name="step-7-optional-additional-precautionary-steps"></a>步骤 7（可选）其他预防措施
1. 确保验证已发送的邮件。 你可能需要通知联系人列表中的人员你的帐户遭到入侵。 例如，攻击者可能会向他们要钱，谎称他们被困在另一个国家/地区并且需要钱，也可能会向他们发送病毒以便劫持其计算机。
2. 将此 Exchange 帐户用作其备用电子邮件帐户的任何其他服务可能已遭到入侵。 首先，为 Office 365 订阅执行这些步骤，然后为其他帐户执行这些步骤。
3. 确保你的联系信息（如电话号码和地址）正确无误。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>像网络安全专家那样保护 Office 365
你的 Office 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。  使用“[Office 365 安全路线图：前 30 天、90 天内以及之后的首要行动](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)”，通过实施 Microsoft 建议的最佳做法来保护你的 Office 365 租户。
- 需要在前 30 天完成的任务。  这些任务会对你的用户产生直接影响并且影响很小。
- 需要在 90 天内完成的任务。 这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。
- 90 天后。 这些增强功能基于前 90 天的工作构建。

## <a name="see-also"></a>另请参阅：
- [Office 365 的安全最佳做法](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [在 Office 365 中检测并修正 Outlook 规则和自定义窗体注入攻击](detect-and-remediate-outlook-rules-forms-attack.md)
- [Internet 犯罪投诉中心](http://www.ic3.gov/preventiontips.aspx)
- [证券交易委员会 -“网络钓鱼”诈骗](http://www.sec.gov/investor/pubs/phishing.htm)
- [使用报告消息加载项](https://support.office.com/zh-CN/article/Use-the-Report-Message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)直接向 Microsoft 和你的管理员报告垃圾邮件

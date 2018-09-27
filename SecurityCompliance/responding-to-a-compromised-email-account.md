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
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: 了解如何识别并响应在 Office 365 中受到攻击的电子邮件帐户
ms.openlocfilehash: b10bf58aaebc46938e3962494ff30dfb1e226130
ms.sourcegitcommit: 411713004251ee62d29b550eabea04c08a87e41f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "25341417"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a><span data-ttu-id="93b2a-103">响应 Office 365 中遭到入侵的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="93b2a-103">Responding to a Compromised Email Account in Office 365</span></span>

<span data-ttu-id="93b2a-104">**摘要**了解如何识别并响应在 Office 365 中受到攻击的电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="93b2a-104">**Summary** Learn how to recognize and respond to a compromised email account in Office 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-office-365"></a><span data-ttu-id="93b2a-105">什么是 Office 365 中的威胁电子邮件帐户？</span><span class="sxs-lookup"><span data-stu-id="93b2a-105">What is a Compromised Email Account in Office 365?</span></span>
<span data-ttu-id="93b2a-p101">访问 Office 365 邮箱、 数据和其他服务，使用凭据，例如用户名和密码或 PIN 控制。当某人之外的预期用户窃取这些凭据时，被盗的凭据被视为受到威胁。与他们攻击者可以为原始用户登录并执行非法的操作。使用窃取的凭据，攻击者可以访问用户的 Office 365 邮箱、 SharePoint 文件夹或用户的 OneDrive 中的文件。常见的一个操作是攻击者向收件人组织内外均为原始用户发送电子邮件。如果攻击者向外部收件人电子邮件数据，这就称为数据 exfiltration。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p101">Access to Office 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN. When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised. With them the attacker can sign in as the original user and perform illicit actions. Using the stolen credentials, the attacker can access the user’s Office 365 mailbox, SharePoint folders, or files in the user's OneDrive. One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization. When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-office-365-email-account"></a><span data-ttu-id="93b2a-112">受到攻击的 Office 365 电子邮件帐户的症状</span><span class="sxs-lookup"><span data-stu-id="93b2a-112">Symptoms of a Compromised Office 365 Email Account</span></span>
<span data-ttu-id="93b2a-p102">用户可能注意和报告在其 Office 365 邮箱中的异常活动。下面是一些常见症状：</span><span class="sxs-lookup"><span data-stu-id="93b2a-p102">Users might notice and report unusual activity in their Office 365 mailboxes. Here are some common symptoms:</span></span>
- <span data-ttu-id="93b2a-115">可疑活动，如缺失或被删除的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="93b2a-115">Suspicious activity, such as missing or deleted emails.</span></span>
- <span data-ttu-id="93b2a-116">其他用户可能会收到电子邮件从受到攻击的帐户没有相应的发件人的**已发送邮件**文件夹中现有的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="93b2a-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>
- <span data-ttu-id="93b2a-p103">预期的用户或管理员不需要创建的收件箱规则的状态。这些规则可能会自动转发到未知地址的电子邮件或将它们移动到的**注释**，**垃圾邮件**或**RSS 订阅**的文件夹。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p103">The presence of inbox rules that weren't created by the intended user or the administrator. These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>
- <span data-ttu-id="93b2a-119">全局地址列表中，可能更改用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="93b2a-119">The user's display name might be changed in the Global Address List.</span></span>
- <span data-ttu-id="93b2a-120">用户的邮箱阻止发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="93b2a-120">The user's mailbox is blocked from sending email.</span></span>
- <span data-ttu-id="93b2a-121">在 Microsoft Outlook 或 Microsoft Outlook Web App 中的已发送或已删除邮件文件夹包含常见的黑客攻击帐户消息，如"我正在停止伦敦，发送资金。"</span><span class="sxs-lookup"><span data-stu-id="93b2a-121">The Sent or Deleted Items folders in Microsoft Outlook or in Microsoft Outlook Web App contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>
- <span data-ttu-id="93b2a-122">特殊的配置文件更改，如名称、 电话号码或邮政编码已进行了更新。</span><span class="sxs-lookup"><span data-stu-id="93b2a-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>
- <span data-ttu-id="93b2a-123">特殊凭据更改，如多个密码更改是必需的。</span><span class="sxs-lookup"><span data-stu-id="93b2a-123">Unusual credential changes, such as multiple password changes are required.</span></span>
- <span data-ttu-id="93b2a-124">最近添加了邮件转发。</span><span class="sxs-lookup"><span data-stu-id="93b2a-124">Mail forwarding was recently added.</span></span>
- <span data-ttu-id="93b2a-125">特殊的签名最近已添加，如假银行业签名或惯例药品签名。</span><span class="sxs-lookup"><span data-stu-id="93b2a-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="93b2a-p104">如果用户报告的任何上述症状，应执行进一步调查。Office 365 安全性和合规性中心和 Azure 门户提供工具可以帮助您调查您怀疑可能受到威胁的用户帐户的活动。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p104">If a user reports any of the above symptoms, you should perform further investigation. The Office 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>
- <span data-ttu-id="93b2a-p105">Office 365 统一审核日志中的安全性和合规性中心-查看筛选结果的日期范围跨越从可疑活动发生为当前日期前一刻可疑的帐户的所有活动。不要筛选的活动搜索过程中。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p105">Office 365 Unified Audit Logs in the Security & Compliance Center - Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date. Do not filter on the activities during the search.</span></span>
- <span data-ttu-id="93b2a-p106">使用 Azure AD 登录日志和其他风险报表的 Azure AD 门户中可用。检查这些列中的值：</span><span class="sxs-lookup"><span data-stu-id="93b2a-p106">Use the Azure AD Sign-in logs and other risk reports that are available in the Azure AD portal. Examine the values in these columns:</span></span>
    - <span data-ttu-id="93b2a-132">查看 IP 地址</span><span class="sxs-lookup"><span data-stu-id="93b2a-132">Review IP address</span></span>
    - <span data-ttu-id="93b2a-133">登录位置</span><span class="sxs-lookup"><span data-stu-id="93b2a-133">sign-in locations</span></span>
    - <span data-ttu-id="93b2a-134">登录时间</span><span class="sxs-lookup"><span data-stu-id="93b2a-134">sign-in times</span></span>
    - <span data-ttu-id="93b2a-135">登录成功或失败</span><span class="sxs-lookup"><span data-stu-id="93b2a-135">sign-in success or failure</span></span>



## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a><span data-ttu-id="93b2a-136">如何保护和还原到可疑的电子邮件函数威胁 Office 365 帐户和邮箱</span><span class="sxs-lookup"><span data-stu-id="93b2a-136">How to secure and restore email function to a suspected compromised Office 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="93b2a-137">即使已重新访问获得到您的帐户后，攻击者可能已添加使攻击者恢复该帐户的控制后门条目。</span><span class="sxs-lookup"><span data-stu-id="93b2a-137">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="93b2a-p107">您必须执行以下所有步骤才能重新访问您的帐户，以确保不会继续 hijacker 更好更快地控制您的帐户。这些步骤可帮助您删除 hijacker 可能已添加到您的帐户的任何后门条目。执行这些步骤后，我们建议您运行病毒扫描，以确保您的计算机不破坏。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p107">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account. These steps help you remove any back-door entries that the hijacker may have added to your account. After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="93b2a-141">步骤 1 重置用户的密码</span><span class="sxs-lookup"><span data-stu-id="93b2a-141">Step 1 Reset the user's password</span></span>
> [!WARNING]
> <span data-ttu-id="93b2a-142">不要给目标用户通过电子邮件发送新密码，如攻击者仍可以访问到邮箱此时。</span><span class="sxs-lookup"><span data-stu-id="93b2a-142">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="93b2a-143">遵循重置 Office 365 业务密码的某人中的其他过程[Admins： 重置 Office 365 业务密码](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)</span><span class="sxs-lookup"><span data-stu-id="93b2a-143">Follow the Reset an Office 365 business password for someone else procedures in [Admins: Reset Office 365 business passwords](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)</span></span>

<span data-ttu-id="93b2a-144">**注意：**</span><span class="sxs-lookup"><span data-stu-id="93b2a-144">**Notes:**</span></span>
- <span data-ttu-id="93b2a-145">确保密码强，且它包含大写和小写字母、 至少一个数字和至少一个特殊字符。</span><span class="sxs-lookup"><span data-stu-id="93b2a-145">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span> 
- <span data-ttu-id="93b2a-p108">不重用的任何您最近五密码。即使密码历史记录要求使您可以重用较新密码，您应选择内容的攻击者不能猜测。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p108">Don't reuse any of your last five passwords. Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
- <span data-ttu-id="93b2a-148">如果您的本地标识与 Office 365 联盟，则必须更改密码内部部署，然后必须通知危害的管理员。</span><span class="sxs-lookup"><span data-stu-id="93b2a-148">If your on-premises identity is federated with Office 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="93b2a-p109">强烈建议您启用多重身份验证 (MFA)，以阻止威胁，尤其是对于具有管理权限的帐户。 您可以了解更多信息[此处](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p109">It is highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.  You can learn more [here](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="93b2a-151">步骤 2 删除可疑的电子邮件转发地址</span><span class="sxs-lookup"><span data-stu-id="93b2a-151">Step 2 Remove suspicious email forwarding addresses</span></span>
1. <span data-ttu-id="93b2a-152">打开**Office 365 管理中心 > 活动用户**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-152">Open the **Office 365 Admin Center > Active Users**.</span></span>
2. <span data-ttu-id="93b2a-153">查找问题的用户帐户，展开**邮件设置**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-153">Find the user account in question and expand **Mail Settings**.</span></span>
3. <span data-ttu-id="93b2a-154">以**电子邮件转发**，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-154">For **Email forwarding**, click **Edit**.</span></span>
4. <span data-ttu-id="93b2a-155">删除任何可疑转发地址。</span><span class="sxs-lookup"><span data-stu-id="93b2a-155">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="93b2a-156">步骤 3 禁用任何可疑收件箱规则</span><span class="sxs-lookup"><span data-stu-id="93b2a-156">Step 3 Disable any suspicious inbox rules</span></span>
1. <span data-ttu-id="93b2a-157">登录到用户的邮箱使用 Outlook Web App (OWA)。</span><span class="sxs-lookup"><span data-stu-id="93b2a-157">Sign in to the user's mailbox using Outlook Web App (OWA).</span></span>
2. <span data-ttu-id="93b2a-158">单击齿轮图标，单击**邮件**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-158">Click on the gear icon and click **Mail**.</span></span>
3. <span data-ttu-id="93b2a-159">单击**收件箱和偏离规则**并查看的规则。</span><span class="sxs-lookup"><span data-stu-id="93b2a-159">Click **Inbox and sweep rules** and review the rules.</span></span>
4. <span data-ttu-id="93b2a-160">禁用或删除可疑的规则。</span><span class="sxs-lookup"><span data-stu-id="93b2a-160">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="93b2a-161">步骤 4 取消阻止用户发送邮件</span><span class="sxs-lookup"><span data-stu-id="93b2a-161">Step 4 Unblock the user from sending mail</span></span>
<span data-ttu-id="93b2a-162">如果可疑受到攻击的邮箱非法用于发送垃圾电子邮件，则可能邮箱已被阻止发送邮件。</span><span class="sxs-lookup"><span data-stu-id="93b2a-162">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>
1. <span data-ttu-id="93b2a-163">若要取消阻止发送邮件的邮箱，请按照中[删除用户、 域或 IP 地址从阻止列表后发送垃圾电子邮件](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email )的过程。</span><span class="sxs-lookup"><span data-stu-id="93b2a-163">To unblock a mailbox from sending mail, follow the procedures in [Removing a user, domain, or IP Address from a block list after sending spam email](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email ).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="93b2a-164">步骤 5 可选： 阻止从签名中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="93b2a-164">Step 5 Optional: Block the user account from signing-in</span></span>
> [!IMPORTANT]
> <span data-ttu-id="93b2a-165">您可以阻止从签名接程序直到您认为安全地重新启用访问的可疑受到攻击的帐户。</span><span class="sxs-lookup"><span data-stu-id="93b2a-165">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="93b2a-166">转到 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="93b2a-166">Go to the Office 365 admin center.</span></span>
2. <span data-ttu-id="93b2a-167">在 Office 365 管理中心中，选择**用户**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-167">In the Office 365 admin center, select **Users**.</span></span>
3. <span data-ttu-id="93b2a-168">选择您想要阻止，员工，然后再在用户窗格中选择**登录 status**旁边的**编辑**</span><span class="sxs-lookup"><span data-stu-id="93b2a-168">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane</span></span>
4. <span data-ttu-id="93b2a-169">在**登录状态**窗格中，选择**登录被阻止**，然后**保存**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-169">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span> 
5. <span data-ttu-id="93b2a-170">在 Office 365 管理中心中，在左导航窗格中，展开**管理中心**，然后选择**Exchange**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-170">In the Office 365 admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>
6. <span data-ttu-id="93b2a-171">在 Exchange 管理中心中，导航到**收件人 > 邮箱**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-171">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>
7. <span data-ttu-id="93b2a-172">选择该用户，并在用户属性页中，在**移动设备**下单击**禁用 Exchange ActivcSync**和**禁用 OWA for Devices**到这两个回答**是**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-172">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>
8. <span data-ttu-id="93b2a-173">在**电子邮件连接**、**禁用**和应答**是**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-173">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span> 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="93b2a-174">步骤 6 可选： 从所有管理角色组中删除可疑受到攻击的帐户</span><span class="sxs-lookup"><span data-stu-id="93b2a-174">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>
> [!NOTE]
> <span data-ttu-id="93b2a-175">在固定帐户之后，可以还原管理角色组成员身份。</span><span class="sxs-lookup"><span data-stu-id="93b2a-175">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="93b2a-176">登录到 Office 365 管理中心使用的全局管理员帐户并打开**活动用户**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-176">Sign in to the Office 365 Admin Center with a global administrator account and open **Active Users**.</span></span>
2. <span data-ttu-id="93b2a-177">查找可疑威胁帐户和手动检查以查看是否有任何管理角色分配给该帐户。</span><span class="sxs-lookup"><span data-stu-id="93b2a-177">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>
3. <span data-ttu-id="93b2a-178">打开**安全性和合规性中心**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-178">Open the **Security & Compliance Center**.</span></span>
4. <span data-ttu-id="93b2a-179">单击**权限**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-179">Click **Permissions**.</span></span>
5. <span data-ttu-id="93b2a-p110">手动检查以查看是否可疑威胁帐户是其中的任何成员的角色组。 如果： 答： 单击角色组，单击**编辑角色组**。 b.单击**选择成员**和**编辑**以从角色组中删除用户。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p110">Manually review the role groups to see if the suspected compromised account is a member of any of them.  If it is:  a. Click the role group and click **Edit Role Group**.  b. Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>
6. <span data-ttu-id="93b2a-185">打开**Exchange 管理中心**</span><span class="sxs-lookup"><span data-stu-id="93b2a-185">Open the **Exchange Admin Center**</span></span>
7. <span data-ttu-id="93b2a-186">单击**权限**。</span><span class="sxs-lookup"><span data-stu-id="93b2a-186">Click **Permissions**.</span></span>
8. <span data-ttu-id="93b2a-p111">手动检查以查看是否可疑威胁帐户是其中的任何成员的角色组。如果： 答： 单击角色组，单击**编辑**。 b.使用**成员**部分，若要从角色组中删除用户。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p111">Manually review the role groups to see if the suspected compromised account is a member of any of them. If it is:  a. Click the role group and click **Edit**.  b. Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="93b2a-192">步骤 7 可选： 其他预防</span><span class="sxs-lookup"><span data-stu-id="93b2a-192">Step 7 Optional: Additional precautionary steps</span></span>
1. <span data-ttu-id="93b2a-p112">请确保您确认您已发送的邮件。您可能需要告知您的帐户已泄露的联系人列表上的人员。攻击者可能已要求它们的资金，欺骗，例如，您已在不同的国家/地区闲置和所需资金，或攻击者可能会向其发送病毒也劫持其计算机。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p112">Make sure that you verify your sent items. You may have to inform people on your contacts list that your account was compromised. The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>
2. <span data-ttu-id="93b2a-p113">任何其他服务的其替代的电子邮件帐户已泄露用作此 Exchange 帐户。首先，为您的 Office 365 订阅，执行以下步骤，然后为其他帐户执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p113">Any other service that used this Exchange account as its alternative email account may have been compromised. First, perform these steps for your Office 365 subscription, and then perform these steps for your other accounts.</span></span>
3. <span data-ttu-id="93b2a-198">请确保您的联系人信息，如电话号码和地址正确。</span><span class="sxs-lookup"><span data-stu-id="93b2a-198">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="93b2a-199">像网络专业人员的安全保护 Office 365</span><span class="sxs-lookup"><span data-stu-id="93b2a-199">Secure Office 365 like a cybersecurity pro</span></span>
<span data-ttu-id="93b2a-p114">Office 365 订阅附带了强大的可用于保护您的数据和用户的安全功能集。 使用[Office 365 安全路线图： Top 优先级的前 30 天，90 天及其他认证实战](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)实现 Microsoft 建议的用于保护 Office 365 租户的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p114">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.  Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>
- <span data-ttu-id="93b2a-p115">第一个 30 天内完成的任务。 这些没有直接影响，因此低影响到您的用户。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p115">Tasks to accomplish in the first 30 days.  These have immediate affect and are low-impact to your users.</span></span>
- <span data-ttu-id="93b2a-p116">若要在 90 天内完成的任务。这些需要更多时间规划和实现但大大提高安全状况。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p116">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>
- <span data-ttu-id="93b2a-p117">90 天前。在您的第一个 90 天工作中构建这些增强功能。</span><span class="sxs-lookup"><span data-stu-id="93b2a-p117">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="93b2a-208">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="93b2a-208">See also:</span></span>
- [<span data-ttu-id="93b2a-209">Office 365 的安全最佳做法</span><span class="sxs-lookup"><span data-stu-id="93b2a-209">Security best practices for Office 365</span></span>](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [<span data-ttu-id="93b2a-210">检测并修正 Office 365 中的 Outlook 规则和自定义窗体注入攻击</span><span class="sxs-lookup"><span data-stu-id="93b2a-210">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)
- [<span data-ttu-id="93b2a-211">Internet 犯罪投诉中心</span><span class="sxs-lookup"><span data-stu-id="93b2a-211">Internet Crime Complaint Center</span></span>](http://www.ic3.gov/preventiontips.aspx)
- [<span data-ttu-id="93b2a-212">证券和交易委员会"网络钓鱼"欺诈</span><span class="sxs-lookup"><span data-stu-id="93b2a-212">Securities and Exchange Commission - "Phishing" Fraud</span></span>](http://www.sec.gov/investor/pubs/phishing.htm)

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
# <a name="responding-to-a-compromised-email-account-in-office-365"></a><span data-ttu-id="9bde0-103">响应 Office 365 中遭到入侵的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="9bde0-103">Responding to a Compromised Email Account in Office 365</span></span>

<span data-ttu-id="9bde0-104">**摘要**了解如何在 Office 365 中识别和响应已泄露的电子邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="9bde0-104">**Summary** Learn how to recognize and respond to a compromised email account in Office 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-office-365"></a><span data-ttu-id="9bde0-105">什么是 Office 365 中的受损电子邮件帐户？</span><span class="sxs-lookup"><span data-stu-id="9bde0-105">What is a Compromised Email Account in Office 365?</span></span>
<span data-ttu-id="9bde0-p101">可以通过使用凭据 (例如用户名和密码或 PIN) 来控制对 Office 365 邮箱、数据和其他服务的访问。当目标用户之外的其他人盗取这些凭据时, 被盗用的凭据被视为已泄露。使用它们, 攻击者可以以原始用户的形式登录, 并执行非法操作。通过使用失窃凭据, 攻击者可以访问用户的 Office 365 邮箱、SharePoint 文件夹或用户的 OneDrive 中的文件。一个常见的操作是, 攻击者将电子邮件作为原始用户发送给组织内部和外部的收件人。当攻击者通过电子邮件将数据发送给外部收件人时, 这称为 data exfiltration。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p101">Access to Office 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN. When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised. With them the attacker can sign in as the original user and perform illicit actions. Using the stolen credentials, the attacker can access the user’s Office 365 mailbox, SharePoint folders, or files in the user's OneDrive. One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization. When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-office-365-email-account"></a><span data-ttu-id="9bde0-112">受损坏的 Office 365 电子邮件帐户的症状</span><span class="sxs-lookup"><span data-stu-id="9bde0-112">Symptoms of a Compromised Office 365 Email Account</span></span>
<span data-ttu-id="9bde0-p102">用户可能会注意到并报告其 Office 365 邮箱中的异常活动。下面列出了一些常见症状:</span><span class="sxs-lookup"><span data-stu-id="9bde0-p102">Users might notice and report unusual activity in their Office 365 mailboxes. Here are some common symptoms:</span></span>
- <span data-ttu-id="9bde0-115">可疑活动, 如丢失或删除的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9bde0-115">Suspicious activity, such as missing or deleted emails.</span></span>
- <span data-ttu-id="9bde0-116">如果发件人的 "**已发送邮件**" 文件夹中的相应电子邮件不存在, 则其他用户可能会收到受损帐户发来的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9bde0-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>
- <span data-ttu-id="9bde0-p103">未由预期用户或管理员创建的收件箱规则的存在。这些规则可能会自动将电子邮件转发到未知地址, 或将其移动到 "**笔记**"、"**垃圾邮件**" 或 " **RSS 订阅**" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p103">The presence of inbox rules that weren't created by the intended user or the administrator. These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>
- <span data-ttu-id="9bde0-119">在全局地址列表中可能会更改用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9bde0-119">The user's display name might be changed in the Global Address List.</span></span>
- <span data-ttu-id="9bde0-120">阻止用户的邮箱发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9bde0-120">The user's mailbox is blocked from sending email.</span></span>
- <span data-ttu-id="9bde0-121">Microsoft Outlook 或 web 上的 Outlook (以前称为 Outlook web App) 中的 "已发送邮件" 或 "已删除邮件" 文件夹包含常见的黑客攻击帐户, 如 "我在伦敦的电子邮件中, 发送金钱"。</span><span class="sxs-lookup"><span data-stu-id="9bde0-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>
- <span data-ttu-id="9bde0-122">异常配置文件更改 (如名称、电话号码或邮政编码) 已更新。</span><span class="sxs-lookup"><span data-stu-id="9bde0-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>
- <span data-ttu-id="9bde0-123">需要进行多个密码更改 (例如, 需要多次更改)。</span><span class="sxs-lookup"><span data-stu-id="9bde0-123">Unusual credential changes, such as multiple password changes are required.</span></span>
- <span data-ttu-id="9bde0-124">最近添加了邮件转发。</span><span class="sxs-lookup"><span data-stu-id="9bde0-124">Mail forwarding was recently added.</span></span>
- <span data-ttu-id="9bde0-125">最近添加了一个不寻常的签名, 例如假冒银行签名或处方药品签名。</span><span class="sxs-lookup"><span data-stu-id="9bde0-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="9bde0-p104">如果用户报告以上任何症状, 应执行进一步调查。Office 365 Security & 合规性中心和 Azure 门户提供了一些工具, 可帮助您调查怀疑可能受到威胁的用户帐户的活动。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p104">If a user reports any of the above symptoms, you should perform further investigation. The Office 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>
- <span data-ttu-id="9bde0-p105">Office 365 中的 "统一审核日志" 安全 & 合规中心-通过筛选日期范围内的所有活动, 在最近发生可疑活动之前的日期范围内, 查看该可疑帐户的所有活动。不要在搜索过程中对活动进行筛选。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p105">Office 365 Unified Audit Logs in the Security & Compliance Center - Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date. Do not filter on the activities during the search.</span></span>
- <span data-ttu-id="9bde0-p106">使用 azure ad 登录日志和在 azure ad 门户中可用的其他风险报告。检查以下各列中的值:</span><span class="sxs-lookup"><span data-stu-id="9bde0-p106">Use the Azure AD Sign-in logs and other risk reports that are available in the Azure AD portal. Examine the values in these columns:</span></span>
    - <span data-ttu-id="9bde0-132">查看 IP 地址</span><span class="sxs-lookup"><span data-stu-id="9bde0-132">Review IP address</span></span>
    - <span data-ttu-id="9bde0-133">登录位置</span><span class="sxs-lookup"><span data-stu-id="9bde0-133">sign-in locations</span></span>
    - <span data-ttu-id="9bde0-134">登录时间</span><span class="sxs-lookup"><span data-stu-id="9bde0-134">sign-in times</span></span>
    - <span data-ttu-id="9bde0-135">登录成功或失败</span><span class="sxs-lookup"><span data-stu-id="9bde0-135">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a><span data-ttu-id="9bde0-136">如何保护电子邮件功能并将其还原到可疑的受危害的 Office 365 帐户和邮箱</span><span class="sxs-lookup"><span data-stu-id="9bde0-136">How to secure and restore email function to a suspected compromised Office 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="9bde0-137">即使已重新获得帐户访问权限, 攻击者也可能已添加了后门项, 使攻击者能够恢复帐户的控制。</span><span class="sxs-lookup"><span data-stu-id="9bde0-137">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="9bde0-p107">您必须执行以下所有步骤以更快地重新获取对帐户的访问权限, 以确保 hijacker 不会恢复控制您的帐户。这些步骤可帮助您删除 hijacker 可能已添加到您的帐户中的任何后门项。在执行这些步骤后, 我们建议您运行病毒扫描以确保您的计算机不会受到威胁。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p107">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account. These steps help you remove any back-door entries that the hijacker may have added to your account. After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="9bde0-141">步骤1重置用户的密码</span><span class="sxs-lookup"><span data-stu-id="9bde0-141">Step 1 Reset the user's password</span></span>
> [!WARNING]
> <span data-ttu-id="9bde0-142">不要通过电子邮件向目标用户发送新密码, 因为此时攻击者仍可以访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="9bde0-142">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="9bde0-143">按照管理员中的其他人的 "重置 office 365 业务密码" 过程[操作: 重置 office 365 业务密码](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)</span><span class="sxs-lookup"><span data-stu-id="9bde0-143">Follow the Reset an Office 365 business password for someone else procedures in [Admins: Reset Office 365 business passwords](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)</span></span>

<span data-ttu-id="9bde0-144">**注意：**</span><span class="sxs-lookup"><span data-stu-id="9bde0-144">**Notes:**</span></span>
- <span data-ttu-id="9bde0-145">请确保密码是强密码, 并且包含大写和小写字母、至少一个数字以及至少一个特殊字符。</span><span class="sxs-lookup"><span data-stu-id="9bde0-145">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span> 
- <span data-ttu-id="9bde0-p108">请勿重用你的最后五个密码中的任何一个。尽管密码历史要求允许您重用较新的密码, 但您应选择攻击者无法猜测的内容。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p108">Don't reuse any of your last five passwords. Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
- <span data-ttu-id="9bde0-148">如果您的本地标识与 Office 365 联合在一起, 您必须更改本地密码, 然后必须向管理员通知攻击的安全。</span><span class="sxs-lookup"><span data-stu-id="9bde0-148">If your on-premises identity is federated with Office 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="9bde0-p109">强烈建议您启用多重身份验证 (MFA) 以防止受到危害, 尤其是具有管理权限的帐户。 你可以在[此处](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p109">It is highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.  You can learn more [here](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="9bde0-151">步骤2删除可疑电子邮件转发地址</span><span class="sxs-lookup"><span data-stu-id="9bde0-151">Step 2 Remove suspicious email forwarding addresses</span></span>
1. <span data-ttu-id="9bde0-152">打开 " **Office 365 管理中心 > 活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="9bde0-152">Open the **Office 365 Admin Center > Active Users**.</span></span>
2. <span data-ttu-id="9bde0-153">查找 "有问题的用户帐户" 和 "展开**邮件设置**"。</span><span class="sxs-lookup"><span data-stu-id="9bde0-153">Find the user account in question and expand **Mail Settings**.</span></span>
3. <span data-ttu-id="9bde0-154">对于**电子邮件转发**, 请单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="9bde0-154">For **Email forwarding**, click **Edit**.</span></span>
4. <span data-ttu-id="9bde0-155">删除任何可疑的转发地址。</span><span class="sxs-lookup"><span data-stu-id="9bde0-155">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="9bde0-156">步骤3禁用任何可疑的收件箱规则</span><span class="sxs-lookup"><span data-stu-id="9bde0-156">Step 3 Disable any suspicious inbox rules</span></span>
1. <span data-ttu-id="9bde0-157">使用 Outlook 网页登录到用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="9bde0-157">Sign in to the user's mailbox using Outlook on the web.</span></span>
2. <span data-ttu-id="9bde0-158">单击齿轮图标并单击 "**邮件**"。</span><span class="sxs-lookup"><span data-stu-id="9bde0-158">Click on the gear icon and click **Mail**.</span></span>
3. <span data-ttu-id="9bde0-159">单击 **"收件箱" 和 "扫描规则**", 并查看规则。</span><span class="sxs-lookup"><span data-stu-id="9bde0-159">Click **Inbox and sweep rules** and review the rules.</span></span>
4. <span data-ttu-id="9bde0-160">禁用或删除可疑规则。</span><span class="sxs-lookup"><span data-stu-id="9bde0-160">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="9bde0-161">步骤4取消阻止用户发送邮件</span><span class="sxs-lookup"><span data-stu-id="9bde0-161">Step 4 Unblock the user from sending mail</span></span>
<span data-ttu-id="9bde0-162">如果在 illicitly 中使用可疑的受攻击邮箱发送垃圾邮件, 则可能已阻止该邮箱发送邮件。</span><span class="sxs-lookup"><span data-stu-id="9bde0-162">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>
1. <span data-ttu-id="9bde0-163">若要取消阻止邮箱发送邮件, 请按照[发送垃圾电子邮件后从阻止列表中删除用户、域或 IP 地址](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email )中的过程操作。</span><span class="sxs-lookup"><span data-stu-id="9bde0-163">To unblock a mailbox from sending mail, follow the procedures in [Removing a user, domain, or IP Address from a block list after sending spam email](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email ).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="9bde0-164">步骤5可选: 阻止用户帐户登录</span><span class="sxs-lookup"><span data-stu-id="9bde0-164">Step 5 Optional: Block the user account from signing-in</span></span>
> [!IMPORTANT]
> <span data-ttu-id="9bde0-165">您可以阻止可疑的受攻击帐户登录, 直到您认为可以安全地重新启用访问。</span><span class="sxs-lookup"><span data-stu-id="9bde0-165">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="9bde0-166">转到 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="9bde0-166">Go to the Office 365 admin center.</span></span>
2. <span data-ttu-id="9bde0-167">在 Office 365 管理中心 中，选择" **用户** "。</span><span class="sxs-lookup"><span data-stu-id="9bde0-167">In the Office 365 admin center, select **Users**.</span></span>
3. <span data-ttu-id="9bde0-168">选择要阻止的员工, 然后在用户窗格中选择 "**登录状态**" 旁边的 "**编辑**"</span><span class="sxs-lookup"><span data-stu-id="9bde0-168">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane</span></span>
4. <span data-ttu-id="9bde0-169">在" **登录状态** "窗格中，选择" **阻止登录** "，然后" **保存** "。</span><span class="sxs-lookup"><span data-stu-id="9bde0-169">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span> 
5. <span data-ttu-id="9bde0-170">在 Office 365 管理中心的左下角导航窗格中, 展开 "**管理中心**", 然后选择 " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="9bde0-170">In the Office 365 admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>
6. <span data-ttu-id="9bde0-171">在 Exchange 管理中心中, 导航到 "**收件人" "> 邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="9bde0-171">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>
7. <span data-ttu-id="9bde0-172">选择用户, 然后在 "用户属性" 页上的 "**移动设备**" 下, 单击 "**禁用 Exchange ActivcSync** " 并**禁用 "适用于设备的 OWA** ", 并对二者同时回答 **"是"**</span><span class="sxs-lookup"><span data-stu-id="9bde0-172">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>
8. <span data-ttu-id="9bde0-173">在 "**电子邮件连接**" 下,**禁用**并回答 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="9bde0-173">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span> 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="9bde0-174">步骤6可选: 从所有管理角色组中删除可疑的受攻击帐户</span><span class="sxs-lookup"><span data-stu-id="9bde0-174">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>
> [!NOTE]
> <span data-ttu-id="9bde0-175">在帐户受到保护之后, 可以恢复管理角色组成员身份。</span><span class="sxs-lookup"><span data-stu-id="9bde0-175">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="9bde0-176">使用全局管理员帐户登录到 Office 365 管理中心并打开**活动用户**。</span><span class="sxs-lookup"><span data-stu-id="9bde0-176">Sign in to the Office 365 Admin Center with a global administrator account and open **Active Users**.</span></span>
2. <span data-ttu-id="9bde0-177">查找可疑的受攻击帐户并手动查看是否有分配给该帐户的任何管理角色。</span><span class="sxs-lookup"><span data-stu-id="9bde0-177">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>
3. <span data-ttu-id="9bde0-178">打开 "**安全 & 合规中心**"。</span><span class="sxs-lookup"><span data-stu-id="9bde0-178">Open the **Security & Compliance Center**.</span></span>
4. <span data-ttu-id="9bde0-179">单击 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="9bde0-179">Click **Permissions**.</span></span>
5. <span data-ttu-id="9bde0-p110">手动查看角色组, 以查看可疑的受攻击帐户是否为它们的成员。 如果是, 则单击 "角色组", 然后单击 "**编辑角色组**"。 b. 单击 "**选择成员**", 然后单击 "**编辑**" 从角色组中删除用户。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p110">Manually review the role groups to see if the suspected compromised account is a member of any of them.  If it is:  a. Click the role group and click **Edit Role Group**.  b. Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>
6. <span data-ttu-id="9bde0-185">打开**Exchange 管理中心**</span><span class="sxs-lookup"><span data-stu-id="9bde0-185">Open the **Exchange Admin Center**</span></span>
7. <span data-ttu-id="9bde0-186">单击 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="9bde0-186">Click **Permissions**.</span></span>
8. <span data-ttu-id="9bde0-p111">手动查看角色组, 以查看可疑的受攻击帐户是否为它们的成员。如果是, 则单击 "角色组", 然后单击 "**编辑**"。 b. 使用 "**成员**" 部分从角色组中删除用户。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p111">Manually review the role groups to see if the suspected compromised account is a member of any of them. If it is:  a. Click the role group and click **Edit**.  b. Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="9bde0-192">步骤7可选: 其他预防措施步骤</span><span class="sxs-lookup"><span data-stu-id="9bde0-192">Step 7 Optional: Additional precautionary steps</span></span>
1. <span data-ttu-id="9bde0-p112">请确保验证已发送的邮件。您可能需要向 "联系人" 列表通知用户您的帐户已泄露。攻击者可能已向其提问了金钱, 例如, 您在不同的国家/地区和所需的资金, 或者攻击者可能会向其发送病毒以劫持其计算机。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p112">Make sure that you verify your sent items. You may have to inform people on your contacts list that your account was compromised. The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>
2. <span data-ttu-id="9bde0-p113">使用此 Exchange 帐户作为其备用电子邮件帐户的任何其他服务可能已泄露。首先, 为 Office 365 订阅执行这些步骤, 然后为其他帐户执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p113">Any other service that used this Exchange account as its alternative email account may have been compromised. First, perform these steps for your Office 365 subscription, and then perform these steps for your other accounts.</span></span>
3. <span data-ttu-id="9bde0-198">请确保您的联系信息 (如电话号码和地址) 正确无误。</span><span class="sxs-lookup"><span data-stu-id="9bde0-198">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="9bde0-199">安全的 Office 365, 如 cybersecurity pro</span><span class="sxs-lookup"><span data-stu-id="9bde0-199">Secure Office 365 like a cybersecurity pro</span></span>
<span data-ttu-id="9bde0-p114">您的 Office 365 订阅附带了一组功能强大的安全功能, 可用于保护您的数据和用户。 使用[Office 365 安全路线图: 前30天、90天和更高版本的首要优先级](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352), 以实现 Microsoft 建议的保护 Office 365 租户的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p114">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.  Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>
- <span data-ttu-id="9bde0-p115">在前30天内要完成的任务。 这些值会立即生效, 并对用户造成影响较小。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p115">Tasks to accomplish in the first 30 days.  These have immediate affect and are low-impact to your users.</span></span>
- <span data-ttu-id="9bde0-p116">要在90天内完成的任务。它们需要花一点时间来规划和实施, 但大大提高了您的安全状况。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p116">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>
- <span data-ttu-id="9bde0-p117">超过90天。这些增强功能将在您的前90天工作中构建。</span><span class="sxs-lookup"><span data-stu-id="9bde0-p117">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bde0-208">另请参阅:</span><span class="sxs-lookup"><span data-stu-id="9bde0-208">See also:</span></span>
- [<span data-ttu-id="9bde0-209">Office 365 的安全最佳做法</span><span class="sxs-lookup"><span data-stu-id="9bde0-209">Security best practices for Office 365</span></span>](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [<span data-ttu-id="9bde0-210">在 Office 365 中检测并修正 Outlook 规则和自定义窗体注入攻击</span><span class="sxs-lookup"><span data-stu-id="9bde0-210">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)
- [<span data-ttu-id="9bde0-211">Internet 犯罪投诉中心</span><span class="sxs-lookup"><span data-stu-id="9bde0-211">Internet Crime Complaint Center</span></span>](http://www.ic3.gov/preventiontips.aspx)
- [<span data-ttu-id="9bde0-212">证券和交换委员会-"网络钓鱼" 欺诈</span><span class="sxs-lookup"><span data-stu-id="9bde0-212">Securities and Exchange Commission - "Phishing" Fraud</span></span>](http://www.sec.gov/investor/pubs/phishing.htm)

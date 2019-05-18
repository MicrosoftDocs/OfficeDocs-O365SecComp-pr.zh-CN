---
title: 检测和修正 Office 365 中的 Outlook 规则和自定义窗体注入攻击
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何识别和修正 Office 365 中的 Outlook 规则和自定义窗体注入攻击
ms.openlocfilehash: ef2f08c953b91ccefcadd5947d2d0a9f39683ae2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150254"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks-in-office-365"></a>在 Office 365 中检测并修正 Outlook 规则和自定义窗体注入攻击

**摘要**了解如何识别和修正 Office 365 中的 Outlook 规则和自定义窗体注入攻击。

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Outlook 规则和自定义窗体注入攻击是什么？
在攻击者破坏了租赁中的帐户并在中进行了获取之后, 将尝试并建立一种在发现和删除这些帐户后将其保留或返回的方法。 这称为建立持久性机制。 可以通过以下两种方式来执行此操作: 利用 Outlook 规则或将自定义窗体插入 Outlook。
在这两种情况下, 规则或表单都将从云服务同步到桌面客户端, 因此完整的格式和重新安装客户端软件不会消除注入机制。 这是因为当 Outlook 客户端软件重新连接到云中的邮箱时, 它将从云中重新下载规则和表单。 规则和表单准备就绪后, 攻击者将使用它们执行远程或自定义代码, 通常是在本地计算机上安装恶意软件。 恶意软件然后重新盗取凭据或执行其他违法活动。 好消息是, 如果你将客户端修补到最新版本, 则不会因当前 Outlook 客户端默认阻止这两种机制而受到威胁。 

攻击通常遵循以下模式:

规则利用
1. 攻击者盗取某个用户的用户名和密码。
2. 然后, 攻击者登录到该用户的 Exchange 邮箱。 邮箱可以位于 Exchange online 中, 也可以位于本地 Exchange 中。
3. 然后, 攻击者在邮箱收到符合规则条件的电子邮件时触发的邮箱中创建转发规则。 规则的条件和触发器电子邮件的内容为彼此进行了自适应。
4. 攻击者将触发器电子邮件发送到正常使用其邮箱的用户。
5. 收到电子邮件时, 将触发该规则。 通常情况下, 该规则的操作是在远程 (WebDAV) 服务器上启动应用程序。
6. 应用程序通常会在用户的计算机上本地安装恶意软件, 如[Powershell Empire](https://www.powershellempire.com/)。
7. 恶意软件允许攻击者重新盗取用户的用户名和密码或本地计算机中的其他凭据, 并执行其他恶意活动。

表单利用
1. 攻击者盗取某个用户的用户名和密码。
2. 然后, 攻击者登录到该用户的 Exchange 邮箱。 邮箱可以位于 Exchange online 中, 也可以位于本地 Exchange 中。
3. 然后, 攻击者创建一个自定义邮件表单模板, 并将其插入到用户的邮箱中。  当邮箱收到需要邮箱加载自定义表单的电子邮件时, 将触发自定义表单。 自定义窗体和电子邮件的格式是彼此进行量身定制的。
4. 攻击者将触发器电子邮件发送给用户, 该用户将正常使用其邮箱。
5. 收到电子邮件时, 将加载表单。 表单启动远程 (WebDAV) 服务器上的应用程序。
6. 应用程序通常会在用户的计算机上本地安装恶意软件, 如[Powershell Empire](https://www.powershellempire.com/)。
7. 恶意软件允许攻击者重新盗取用户的用户名和密码或本地计算机中的其他凭据, 并执行其他恶意活动。


## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>哪些规则和自定义窗体注入攻击可能看起来像 Office 365？

这些永久性机制不太可能被用户注意到, 有时在某些情况下可能对它们不可见。  本文将介绍如何查找以下列出的任何七个符号 (泄露指示器) 中的任何一个。 如果您发现其中任何一个, 则需要采取补救措施。

- 规则泄露的指示器
    - 规则操作是启动应用程序。
    - Rule 引用 EXE、ZIP 或 URL。
    - 在本地计算机上, 查找来自 Outlook PID 的新进程启动。
- 自定义窗体的指示器受到危害 
    - 自定义表单显示另存为自己的邮件类。
    - 邮件类包含可执行代码。
    - 通常存储在 "个人表单库" 或 "收件箱" 文件夹中。
    - 表单名为 IPM。便笺.[custom name]。

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>查找此攻击的迹象和确认此攻击的步骤
您可以使用这两种方法中的任何一种来确认攻击。
- 使用 Outlook 客户端手动检查每个邮箱的规则和窗体。  这种方法是彻底的, 但如果您有多个用户要进行检查, 则一次只能检查邮箱用户。  此外, 它还会导致破坏正在运行检查的计算机。
- 使用[Get-AllTenantRulesAndForms](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 脚本自动为租户中的所有用户转储所有邮件转发规则和自定义窗体。 这是最快、最安全的方法, 最小开销。


### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>使用 Outlook 客户端确认规则攻击
1. 以用户的形式打开用户 Outlook 客户端。  用户可能需要您的帮助来检查其邮箱上的规则。
2. 有关如何在2007、2010或2013版本的 Outlook 中打开 rules 接口的过程, 请参阅[使用规则文章管理电子邮件](https://support.office.com/article/manage-email-messages-by-using-rules-c24f5dea-9465-4df4-ad17-a50704d66c59#ID0EAABAAA=2010)。
3. 查找用户未创建的规则或具有可疑名称的任何意外规则或规则。
4. 在规则说明中查找启动和应用程序或引用的规则操作的规则说明。EXE。ZIP 文件或启动 URL。
5. 查找所有使用 Outlook 进程 ID 开始的新进程。  请参阅[查找进程 ID](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)。

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>使用 Outlook 客户端确认表单攻击的步骤
1. 以用户的形式打开用户 Outlook 客户端。
2. 按照中的步骤, 为用户版本的 Outlook[显示 "开发工具" 选项卡](https://support.office.com/article/show-the-developer-tab-e1192344-5e56-4d45-931b-e5fd9bea2d45)。
3. 在 Outlook 中打开 "现在可见的开发工具" 选项卡, 然后单击 "**设计窗体**"。
4. 从 "**查找范围**" 列表中选择 "**收件箱**"。 查找任何自定义窗体。  自定义窗体非常罕见, 如果你有任何自定义表单, 则需要更深入的了解。
5. 调查任何自定义窗体, 尤其是那些标记为隐藏的窗体。
6. 打开任何自定义窗体, 然后在**窗体**组中单击 "**查看代码**" 以查看加载窗体时的运行内容。

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>使用 PowerShell 确认规则和表单攻击的步骤
验证规则或自定义表单攻击的最简单方法是运行[Get-AllTenantRulesAndForms](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 脚本。  此脚本将连接到租户中的每个邮箱, 并将所有规则和窗体转储为两个 .csv 文件。

#### <a name="pre-requisites"></a>先决条件
由于脚本将连接到租赁中的每个邮箱, 您需要具有全局管理员权限才能运行该脚本, 以读取规则和表单。

1. 登录到您将使用本地管理员权限运行脚本的计算机。
2. 将 Get-AllTenantRulesAndForms 脚本从 GitHub 下载或复制到将从中运行它的文件夹中。  该脚本将创建两个日期戳文件到此文件夹、MailboxFormsExport-yyyy-mm-dd 和 MailboxRulesExport-yyyy-mm-dd。
3. 以管理员身份打开 PowerShell 实例, 并打开保存脚本的文件夹。
4. 按如下所示`.\Get-AllTenantRulesAndForms.ps1`运行此 PowerShell 命令行 .\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>解释输出

MailboxRulesExport-*mm-dd*–检查包含应用程序或可执行文件的操作条件的规则 (每行一个)。
- ActionType (列 A) –如果您看到值 "ID_ACTION_CUSTOM", 则该规则可能是恶意的。
- IsPotentiallyMalicious (column D) –如果此值为 "TRUE", 则该规则可能是恶意的。
- ActionCommand (column G) –如果这列出了应用程序或任何带 .exe、.zip 扩展名的文件或引用了 URL 的条目, 则该规则可能是恶意的。

MailboxFormsExport-*dd*.csv –通常情况下, 使用自定义窗体非常罕见。  如果在此工作簿中找到任何类型, 则打开该用户的邮箱并检查表单本身。  如果您的组织没有有意将其放在那里, 则可能是恶意的。



## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>如何停止和修正 Outlook 规则和表单攻击
如果您发现上述任一攻击的任何证据, 补救措施就很简单, 只需从邮箱中删除该规则或表单即可。 您可以使用 Outlook 客户端或使用远程 PowerShell 删除规则。

### <a name="using-outlook"></a>使用 Outlook
1. 标识用户在 Outlook 中使用的所有设备。  所有这些人都需要清除潜在的恶意软件。  在清理所有设备之前, 不要允许用户登录并使用电子邮件。
2. 按照 "删除每个设备的[规则](https://support.office.com/article/Delete-a-rule-2F0E7139-F696-4422-8498-44846DB9067F)" 中的步骤操作。
3. 如果您不确定是否存在其他恶意软件, 可以在设备上格式化并重新安装所有软件。  对于移动设备, 您可以按照制造商的步骤操作, 将设备重置为出厂映像。
4. 安装最新版本的 Outlook。  请注意, 默认情况下, 当前版本的 Outlook 阻止这两种攻击类型。
5. 删除邮箱的所有脱机副本后, 重置用户的密码 (使用高质量的密码), 并按照 Setup 多重身份365验证 (如果尚未启用 MFA) 中的步骤操作。 这可确保用户的凭据不会通过其他方式 (如网络钓鱼或密码重用) 公开。

### <a name="using-powershell"></a>使用 PowerShell
有两个可用于删除或禁用危险规则的远程 PowerShell cmdlet。 只需按照步骤操作即可。
 
Exchange 服务器上的邮箱的步骤

1. 使用远程 PowerShell 连接到 Exchange 服务器。 按照[使用远程 PowerShell 连接到 Exchange 服务器](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell?view=exchange-ps)中的步骤操作。
2. 如果要从邮箱中完全删除单个规则、多个规则或所有规则, 请使用 "[删除收件箱" 规则 cmdlet ](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps)-使用此项可从邮箱中完全删除一个、多个或所有规则。
3. 如果要保留规则及其内容以进行进一步调查, 请使用[new-inboxrule cmdlet](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx)。 

Exchange Online 中邮箱的步骤
1. 按照 "[使用 PowerShell 连接到 Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)" 中的步骤操作。
2.  如果要完全删除单个规则、多个规则或来自一个邮箱的所有规则, 请使用 "[删除收件箱" 规则 cmdlet](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps)。
3.  如果要保留规则及其内容以进行进一步调查, 请使用[new-inboxrule cmdlet](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx)。 

## <a name="how-to-minimize-future-attacks"></a>如何最大限度地减少未来攻击

### <a name="first-protect-your-accounts"></a>首先: 保护你的帐户

只有攻击者在窃取或破坏用户的帐户后, 才会使用这些规则和表单攻击。 因此, 阻止对组织使用这些漏洞的第一步是主动保护您的用户帐户。  帐户受到破坏的一些最常见的方法是通过网络钓鱼或[密码 spraying](http://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)攻击。



保护用户帐户 (尤其是管理员帐户) 的最佳方法是为[Office 365 用户设置多重身份验证](https://support.office.com/article/set-up-multi-factor-authentication-for-office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6)。  此外, 还应执行以下操作:
<ol>
    <li>监视如何<a href="https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports">访问和使用</a>您的用户帐户。 您可能不会阻止最初的破坏, 但您将通过更快地进行检测来缩短危害的持续时间和影响。 您可以使用以下内容: <a href="https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security">Office 365 云应用安全策略</a>来监视您的帐户并通知异常活动。 
        <ol type="a">
            <li><b>多次失败的登录尝试</b>当用户在一个会话中执行多个失败的登录活动时, 此策略将配置为您的环境并触发警报, 这可能表示尝试受到破坏。</li>
            <li><b>无法旅行</b>-此策略配置您的环境, 并在从同一用户在两个位置之间的不同位置 (短于两个位置之间的预期旅行时间) 内检测到活动时触发警报。 这可能表示其他用户正在使用相同的凭据。 如果检测到此异常行为, 则可以在七天内学习新用户的活动模式的初始学习期。</li>
            <li><b>异常模拟活动 (按用户)</b>-当用户在一个会话中执行多个模拟活动时, 此策略将对你的环境和触发警报进行分析, 这可能表示尝试了泄露。</li>
        </ol>
    </li>
    <li>利用类似于<a href="https://securescore.office.com/">Office 365 安全分数</a>的工具来管理帐户安全配置和行为。 
    </li>
</ol> 

### <a name="second-keep-your-outlook-clients-current"></a>其次: 将 Outlook 客户端保持为最新
完全更新和修补的 Outlook 2013 版本, 2016 默认禁用 "启动应用程序" 规则/表单操作。  这将确保即使攻击者破坏了帐户, 规则和表单操作也将受到阻止。  您可以按照[安装 Office 更新](https://support.office.com/article/Install-Office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)中的步骤安装最新的更新和安全修补程序。

下面是 Outlook 2013 和2016客户端的修补程序版本:
- Outlook 2013: 15.0.4937.1000 或更高版本
- Outlook 2016: 16.0.4534.1001 或更高版本

有关各个安全修补程序的详细信息, 请参阅:

- [Outlook 2013 安全修补程序](https://support.microsoft.com/en-us/help/3191938) 
- [Outlook 2016 安全修补程序](https://support.microsoft.com/en-us/help/3191883)

### <a name="third-monitor-your-outlook-clients"></a>第三个: 监视您的 Outlook 客户端
请注意, 即使安装了修补程序和更新, 攻击者也有可能更改本地计算机配置以重新启用 "启动应用程序" 行为。 您可以使用[高级组策略管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/)在客户端上监视和强制实施本地计算机策略。  
通过使用[如何使用 Windows 的64位版本查看系统注册表](https://support.microsoft.com/en-us/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows)中的信息, 可以查看是否已通过注册表中的替代重新启用了 "启动应用程序"。  检查以下子项: 

- Outlook 2016: HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\
- Outlook 2013: HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\

查找注册表项 EnableUnsafeClientMailRules。 如果已存在并且设置为 1, 则表示 Outlook 安全修补程序已被覆盖, 并且计算机易受表单/规则攻击。 如果值为 0, 则禁用 "启动应用程序" 操作。  如果安装了已更新和修补的 Outlook 版本, 但此注册表项不存在, 则系统不易受到这些攻击。

使用本地 Exchange 安装的客户应考虑阻止未提供修补程序的旧版本的 Outlook。 有关此过程的详细信息, 请参阅[配置 Outlook 客户端阻止](https://technet.microsoft.com/en-us/library/dd335207(v=exchg.150).aspx)一文。

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>像网络安全专家那样保护 Office 365
你的 Office 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。  使用“[Office 365 安全路线图：前 30 天、90 天内以及之后的首要行动](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352)”，通过实施 Microsoft 建议的最佳做法来保护你的 Office 365 租户。
- 需要在前 30 天完成的任务。  这些任务会对你的用户产生直接影响并且影响很小。
- 需要在 90 天内完成的任务。 这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。
- 90 天后。 这些增强功能基于前 90 天的工作构建。

## <a name="see-also"></a>另请参阅：
- [恶意 Outlook 规则](https://silentbreaksecurity.com/malicious-outlook-rules/)SilentBreak 安全公告关于规则矢量提供有关 Outlook 规则的详细审阅。 
- [MAPI OVER HTTP 和 Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) On the Sensepost 博客 For Mailrule Pwnage 讨论了一个称为标尺的工具, 可让您通过 Outlook 规则利用邮箱。
- 有关表单威胁向量的 Sensepost 博客上的[Outlook 窗体和 shell](https://sensepost.com/blog/2017/outlook-forms-and-shells/) 。 
- [标尺基本代码](https://github.com/sensepost/ruler)
- [标尺指示器的危害](https://github.com/sensepost/notruler/blob/master/iocs.md)
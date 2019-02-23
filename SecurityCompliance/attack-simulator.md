---
title: Office 365 中的攻击模拟器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: 作为 Office 365 全局管理员, 你可以使用攻击模拟器在你的组织中运行实际的攻击方案。这可帮助你在真正的攻击击中你的业务之前识别和查找易受攻击的用户。
ms.openlocfilehash: ba5658dfa9075b5779f8ca09ccad3547dbddcbb5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216272"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="acc81-104">Office 365 中的攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="acc81-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="acc81-p102">**摘要**如果您是 office 365 全局管理员, 并且您的组织拥有[office 365 的威胁智能](office-365-ti.md), 则可以使用攻击模拟器在组织中运行实际的攻击方案。这可以帮助您识别和查找易受攻击的用户, 在真正的攻击影响你的底线之前。阅读本文以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="acc81-p102">**Summary** If you are an Office 365 global administrator and your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line. Read this article to learn more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="acc81-p103">从2019年2月起开始, 在接下来的几个月中, office 365 威胁情报将成为 office 365 高级威胁防护计划 2, 其中包含其他威胁防护功能。若要了解详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="acc81-p103">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="acc81-110">攻击</span><span class="sxs-lookup"><span data-stu-id="acc81-110">The Attacks</span></span>

<span data-ttu-id="acc81-111">目前提供三种攻击模拟:</span><span class="sxs-lookup"><span data-stu-id="acc81-111">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="acc81-112">显示名称 spear 网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="acc81-112">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="acc81-113">密码喷涂攻击</span><span class="sxs-lookup"><span data-stu-id="acc81-113">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="acc81-114">强力密码攻击</span><span class="sxs-lookup"><span data-stu-id="acc81-114">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="acc81-p104">若要成功启动攻击, 请对要使用的帐户使用多重身份验证, 以运行模拟攻击。此外, 您必须是 Office 365 全局管理员。</span><span class="sxs-lookup"><span data-stu-id="acc81-p104">For an attack to be successfully launched, you use multi-factor authentication on the account you are using to run simulated attacks. In addition, you must be an Office 365 global administrator.</span></span>
  
> [!NOTE]
> <span data-ttu-id="acc81-117">即将推出对条件访问的支持。</span><span class="sxs-lookup"><span data-stu-id="acc81-117">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="acc81-118">若要访问攻击模拟器, 请在&amp; "安全合规性中心" 中, 选择 "**威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="acc81-118">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="acc81-119">开始之前 .。。</span><span class="sxs-lookup"><span data-stu-id="acc81-119">Before you begin...</span></span>

<span data-ttu-id="acc81-120">请确保您和您的组织满足以下攻击模拟器的要求:</span><span class="sxs-lookup"><span data-stu-id="acc81-120">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="acc81-p105">您的组织的电子邮件托管在 Exchange Online 中。(攻击模拟器对本地电子邮件服务器不可用。)</span><span class="sxs-lookup"><span data-stu-id="acc81-p105">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="acc81-123">你是 Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="acc81-123">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="acc81-124">您的组织正在[对 Office 365 用户使用多重身份验证](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="acc81-124">Your organization is using [Multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span></span>
 
- <span data-ttu-id="acc81-125">您的组织[具有 Office 365 威胁智能](office-365-ti.md), 在&amp;安全合规性中心中显示攻击模拟器 (转到**威胁管理** \> **攻击模拟器**)</span><span class="sxs-lookup"><span data-stu-id="acc81-125">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span><br/><span data-ttu-id="acc81-126">![威胁管理-攻击模拟器](media/ThreatMgmt-AttackSimulator.png)</span><span class="sxs-lookup"><span data-stu-id="acc81-126">![Threat management - Attack Simulator](media/ThreatMgmt-AttackSimulator.png)</span></span>

    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="acc81-127">显示名称 spear 网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="acc81-127">Display name spear-phishing attack</span></span>

<span data-ttu-id="acc81-p106">网络钓鱼是一种通用术语, 用于作为社会工程手段攻击的广泛攻击组 classed。此攻击主要针对 spear 网络钓鱼, 这是一种更有针对性的攻击, 面向一组特定的个人或组织。通常, 自定义攻击会执行某些侦测, 并使用将在收件人中生成信任的显示名称, 例如看起来像来自组织中的执行者的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="acc81-p106">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="acc81-p107">此攻击的重点在于通过更改显示名称和源地址, 使您能够操纵发件人显示的来源。如果 spear 攻击成功, 网络罪犯将获得对用户凭据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="acc81-p107">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="acc81-133">模拟 spear 网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="acc81-133">To simulate a spear-phishing attack</span></span>

![撰写电子邮件正文](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="acc81-135">您可以直接在**电子邮件正文**字段中手工创建丰富的 HTML 编辑器, 或使用 HTML 源。</span><span class="sxs-lookup"><span data-stu-id="acc81-135">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>
  
1. <span data-ttu-id="acc81-136">在 "[安全&amp;合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="acc81-136">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="acc81-137">为攻击指定有意义的市场活动名称或选择一个模板。</span><span class="sxs-lookup"><span data-stu-id="acc81-137">Specify a meaningful campaign name for the attack or select a template.</span></span> <br/>![网络钓鱼起始页](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="acc81-p108">指定目标收件人。它可以是组织中的个人或组。每个目标收件人都必须具有 Exchange Online 邮箱, 攻击才会成功。</span><span class="sxs-lookup"><span data-stu-id="acc81-p108">Specify the target recipients. This can be individuals or groups in your organization. Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> <br/>![收件人选择](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="acc81-143">配置网络钓鱼电子邮件详细信息。</span><span class="sxs-lookup"><span data-stu-id="acc81-143">Configure the Phishing email details.</span></span> <br/>![配置电子邮件详细信息](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/><span data-ttu-id="acc81-p109">HTML 格式可以是复杂的, 也可以是基本的活动需求。由于电子邮件格式为 HTML, 因此您可以插入图像和文本, 以增强 believability。您可以控制收到的邮件在接收电子邮件客户端中的显示形式。</span><span class="sxs-lookup"><span data-stu-id="acc81-p109">The HTML formatting can be as complex or basic as your campaign needs. As the email format is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="acc81-p110">指定 "**发件人" (名称)** 域的文本。这是在接收电子邮件客户端的**显示名称**中显示的字段。</span><span class="sxs-lookup"><span data-stu-id="acc81-p110">Specify text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="acc81-p111">指定文本或 "**发件人**" 字段。这是在接收电子邮件客户端中显示为发件人的电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="acc81-p111">Specify text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client. </span></span><br/><span data-ttu-id="acc81-p112">您可以在组织中输入现有的电子邮件命名空间 (这样做将使电子邮件地址在接收客户端中实际解析, 从而便于实现非常高的信任模型), 也可以输入外部电子邮件地址。您指定的电子邮件地址不一定确实存在, 但需要遵循有效 SMTP 地址的格式, 例如, 用户 @ domainname. 扩展名。</span><span class="sxs-lookup"><span data-stu-id="acc81-p112">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
7. <span data-ttu-id="acc81-p113">使用下拉选择器, 选择一个网络钓鱼登录服务器 URL, 该 URL 反映你将在攻击中遇到的内容的类型。提供了多个主题 url 供您选择, 例如文档交付、技术、工资等。实际上, 这是要求目标用户单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="acc81-p113">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="acc81-p114">指定自定义登陆页面 URL。使用此将会将用户重定向到成功攻击结束时指定的 URL。例如, 如果您具有内部意识培训, 可以在此处指定。</span><span class="sxs-lookup"><span data-stu-id="acc81-p114">Specify a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="acc81-p115">指定 "**主题**" 字段的文本。这是在接收电子邮件客户端中显示为**主题名称**的字段。</span><span class="sxs-lookup"><span data-stu-id="acc81-p115">Specify text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="acc81-161">撰写目标将接收的**电子邮件正文**。</span><span class="sxs-lookup"><span data-stu-id="acc81-161">Compose the **Email body** that the target will receive.</span></span> <br/><span data-ttu-id="acc81-162">`${username}`将目标名称插入到电子邮件正文中。</span><span class="sxs-lookup"><span data-stu-id="acc81-162">`${username}` inserts the targets name into the Email body.</span></span> <br/><span data-ttu-id="acc81-163">`${loginserverurl}`插入要让目标用户单击的 URL</span><span class="sxs-lookup"><span data-stu-id="acc81-163">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="acc81-p116">选择 **"下一步",** 然后单击 "**完成**" 以启动攻击。将 spear 网络钓鱼电子邮件传递到目标收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="acc81-p116">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="acc81-166">密码喷涂攻击</span><span class="sxs-lookup"><span data-stu-id="acc81-166">Password-spray attack</span></span>

<span data-ttu-id="acc81-p117">对组织的密码喷涂攻击通常在损坏的主角成功从租户获取有效用户列表之后使用。错误参与者知道用户使用的常见密码。这是一种广泛使用的攻击, 因为它是运行的廉价攻击, 并且比强力方法更难检测。</span><span class="sxs-lookup"><span data-stu-id="acc81-p117">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant. The bad actor knows about common passwords that people use. This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="acc81-170">此攻击的重点是让您可以为用户的大型目标群体指定一个公用密码。</span><span class="sxs-lookup"><span data-stu-id="acc81-170">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="acc81-171">模拟密码喷涂攻击</span><span class="sxs-lookup"><span data-stu-id="acc81-171">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="acc81-172">在 "[安全&amp;合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="acc81-172">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="acc81-173">为攻击指定有意义的市场活动名称。</span><span class="sxs-lookup"><span data-stu-id="acc81-173">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="acc81-p118">指定目标收件人。它可以是组织中的个人或组。目标收件人必须具有 Exchange Online 邮箱, 攻击才会成功。</span><span class="sxs-lookup"><span data-stu-id="acc81-p118">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="acc81-p119">指定用于攻击的密码。例如, 您可以尝试的`Fall2017`一个常见的相关密码。另一个可能`Spring2018`是或`Password1`。</span><span class="sxs-lookup"><span data-stu-id="acc81-p119">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="acc81-180">选择 "**完成**" 以启动攻击。</span><span class="sxs-lookup"><span data-stu-id="acc81-180">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="acc81-181">强力密码攻击</span><span class="sxs-lookup"><span data-stu-id="acc81-181">Brute-force password attack</span></span>

<span data-ttu-id="acc81-p120">对组织的强力密码攻击通常在已损坏的主角成功从租户获取关键用户列表之后使用。此攻击主要针对单个用户的帐户尝试使用一组密码。</span><span class="sxs-lookup"><span data-stu-id="acc81-p120">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant. This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="acc81-184">模拟强力密码攻击</span><span class="sxs-lookup"><span data-stu-id="acc81-184">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="acc81-185">在 "[安全&amp;合规性中心](https://protection.office.com)" 中, 选择 "**威胁管理** \> **攻击模拟器**"。</span><span class="sxs-lookup"><span data-stu-id="acc81-185">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="acc81-186">为攻击指定有意义的市场活动名称。</span><span class="sxs-lookup"><span data-stu-id="acc81-186">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="acc81-p121">指定目标收件人。目标收件人必须具有 Exchange Online 邮箱, 攻击才会成功。</span><span class="sxs-lookup"><span data-stu-id="acc81-p121">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="acc81-p122">指定用于攻击的一组密码。为此, 您可以对密码列表使用文本 (.txt) 文件。文件大小中的文本文件不能超过 10 MB。每行使用一个密码, 并确保在列表中的最后一个密码后面包含一个硬回车。</span><span class="sxs-lookup"><span data-stu-id="acc81-p122">Specify a set of passwords to use for the attack. To do this, you can use a text (.txt) file for your list of passwords. The text file cannot exceed 10 MB in file size. Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="acc81-193">选择 "**完成**" 以启动攻击。</span><span class="sxs-lookup"><span data-stu-id="acc81-193">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="acc81-194">攻击模拟器中的新功能</span><span class="sxs-lookup"><span data-stu-id="acc81-194">New features in Attack Simulator</span></span>

<span data-ttu-id="acc81-p123">向攻击模拟器添加了新功能。这些内容包括:</span><span class="sxs-lookup"><span data-stu-id="acc81-p123">New features are being added to Attack Simulator. These include:</span></span>
- <span data-ttu-id="acc81-p124">**高级报告功能**。您将能够查看诸如速度最快 (或最慢) 的数据打开攻击模拟电子邮件、最快 (或最慢) 的时间单击邮件中的链接等。</span><span class="sxs-lookup"><span data-stu-id="acc81-p124">**Advanced reporting capabilities**. You'll be able to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more.</span></span>
- <span data-ttu-id="acc81-p125">**电子邮件模板编辑器**。您可以创建可用于将来的攻击模拟的自定义、可重用电子邮件模板。</span><span class="sxs-lookup"><span data-stu-id="acc81-p125">**Email template editor**. You can create a custom, reusable email template that you can use for future attack simulations.</span></span>

<span data-ttu-id="acc81-201">请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)以查看正在开发的内容、正在滚动的内容以及已启动的内容。</span><span class="sxs-lookup"><span data-stu-id="acc81-201">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>




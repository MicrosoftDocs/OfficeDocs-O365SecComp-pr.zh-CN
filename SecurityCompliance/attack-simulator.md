---
title: Office 365 中的攻击模拟器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/02/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: 作为 Office 365 全局管理员，您可以使用攻击模拟器若要运行您的组织中的实际攻击方案。这可以帮助您确定并查找易受攻击用户前真实攻击点击您的业务。
ms.openlocfilehash: 1a1d22b0b36ce8b6a2086296be8f8b5d47d79280
ms.sourcegitcommit: d512c1df01377e305e8d5c0170c822cf78f09565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "27471995"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="143fe-104">Office 365 中的攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="143fe-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="143fe-p102">**摘要**如果您是 Office 365 全局管理员和贵组织拥有[Office 365 威胁智能](office-365-ti.md)，您可以使用攻击模拟器运行您的组织中的实际攻击方案。这可以帮助您确定并查找易受攻击用户前真实攻击影响您底线。阅读此文，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="143fe-p102">**Summary** If you are an Office 365 global administrator and your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line. Read this article to learn more.</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="143fe-108">攻击</span><span class="sxs-lookup"><span data-stu-id="143fe-108">The Attacks</span></span>

<span data-ttu-id="143fe-109">三种类型的攻击模拟当前有：</span><span class="sxs-lookup"><span data-stu-id="143fe-109">Three kinds of attack simulations are currently available:</span></span>
  
- [<span data-ttu-id="143fe-110">显示名称矛网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="143fe-110">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="143fe-111">密码喷涂攻击</span><span class="sxs-lookup"><span data-stu-id="143fe-111">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="143fe-112">强制密码攻击</span><span class="sxs-lookup"><span data-stu-id="143fe-112">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="143fe-p103">攻击者要成功启动，您使用多因素身份验证帐户用于运行模拟的攻击。此外，您必须是 Office 365 全局管理员。</span><span class="sxs-lookup"><span data-stu-id="143fe-p103">For an attack to be successfully launched, you use multi-factor authentication on the account you are using to run simulated attacks. In addition, you must be an Office 365 global administrator.</span></span>
  
> [!NOTE]
> <span data-ttu-id="143fe-115">条件访问支持即将提供。</span><span class="sxs-lookup"><span data-stu-id="143fe-115">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="143fe-116">若要访问攻击模拟器，安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="143fe-116">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="143fe-117">开始之前...</span><span class="sxs-lookup"><span data-stu-id="143fe-117">Before you begin...</span></span>

<span data-ttu-id="143fe-118">请确保您和您的组织满足攻击模拟器的以下要求：</span><span class="sxs-lookup"><span data-stu-id="143fe-118">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
      
- <span data-ttu-id="143fe-p104">Exchange Online 中位于组织的电子邮件。（攻击模拟器不可用的内部部署电子邮件服务器。）</span><span class="sxs-lookup"><span data-stu-id="143fe-p104">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="143fe-121">您是 Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="143fe-121">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="143fe-122">您的组织使用[的 Office 365 用户的多因素身份验证](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="143fe-122">Your organization is using [Multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication?view=o365-worldwide)</span></span>
 
- <span data-ttu-id="143fe-123">贵组织拥有[Office 365 威胁智能](office-365-ti.md)与安全中可见的攻击模拟器&amp;合规性中心 (转到**威胁管理** \> **攻击模拟器**)</span><span class="sxs-lookup"><span data-stu-id="143fe-123">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span><br/><span data-ttu-id="143fe-124">![威胁管理-攻击模拟器](media/ThreatMgmt-AttackSimulator.png)</span><span class="sxs-lookup"><span data-stu-id="143fe-124">![Threat management - Attack Simulator](media/ThreatMgmt-AttackSimulator.png)</span></span>

    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="143fe-125">显示名称矛网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="143fe-125">Display name spear-phishing attack</span></span>

<span data-ttu-id="143fe-p105">网络钓鱼的攻击 classed 社会工程样式攻击作为一组广泛的通用术语。此类攻击重点矛网络钓鱼，旨在个人或组织的特定组更有针对性的攻击。通常情况下，自定义与使用将生成信任收件人，例如看起来像来自组织内主管电子邮件中的显示名称并执行一些侦测攻击。</span><span class="sxs-lookup"><span data-stu-id="143fe-p105">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="143fe-p106">此类攻击着重于让您通过更改显示名称和源地址源自消息显示的操作。矛网络钓鱼攻击成功后，犯罪访问用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="143fe-p106">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="143fe-131">若要模拟矛网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="143fe-131">To simulate a spear-phishing attack</span></span>

![撰写电子邮件正文](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="143fe-133">可以创建定制直接在**电子邮件正文**字段本身中丰富的 HTML 编辑器，也可以使用 HTML 源代码。</span><span class="sxs-lookup"><span data-stu-id="143fe-133">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>
  
1. <span data-ttu-id="143fe-134">在[安全&amp;合规性中心](https://security.microsoft.com)，选择**威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="143fe-134">In the [Security &amp; Compliance Center](https://security.microsoft.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="143fe-135">指定攻击的有意义的市场活动名称，或选择一个模板。</span><span class="sxs-lookup"><span data-stu-id="143fe-135">Specify a meaningful campaign name for the attack or select a template.</span></span> <br/>![网络钓鱼开始页](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="143fe-p107">指定目标收件人。这可以是您的组织内个人或组。每个目标的收件人必须具有 Exchange Online 邮箱为了攻击成功。</span><span class="sxs-lookup"><span data-stu-id="143fe-p107">Specify the target recipients. This can be individuals or groups in your organization. Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span> <br/>![收件人选择](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="143fe-141">配置网络钓鱼电子邮件详细信息。</span><span class="sxs-lookup"><span data-stu-id="143fe-141">Configure the Phishing email details.</span></span> <br/>![配置电子邮件的详细信息](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)<br/><span data-ttu-id="143fe-p108">HTML 格式可以为复杂或基本随着您市场需求。电子邮件格式为 HTML，如可以插入图像和文本以增强 believability。您可以控制上收到的消息中接收电子邮件客户端的类似。</span><span class="sxs-lookup"><span data-stu-id="143fe-p108">The HTML formatting can be as complex or basic as your campaign needs. As the email format is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
5. <span data-ttu-id="143fe-p109">指定文本的**从 （名称）** 域。这是接收的电子邮件客户端中的**显示名称**中显示的字段。</span><span class="sxs-lookup"><span data-stu-id="143fe-p109">Specify text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
6. <span data-ttu-id="143fe-p110">指定文本或**从**域。这是显示为接收电子邮件客户端的发件人的电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="143fe-p110">Specify text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client. </span></span><br/><span data-ttu-id="143fe-p111">您可以输入贵组织中的现有电子邮件命名空间 （执行此操作将导致实际解决接收客户端，从而推动非常高信任模型中的电子邮件地址），也可以输入外部电子邮件地址。您指定不必实际存在的电子邮件地址，但它确实需要为以下的一个有效的 SMTP 地址，例如 user@domainname.extension 格式。</span><span class="sxs-lookup"><span data-stu-id="143fe-p111">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
7. <span data-ttu-id="143fe-p112">使用下拉选择器，选择一个反映您将拥有您攻击中的内容类型的网络钓鱼登录服务器 URL。您可供选择，如文档传递，技术，工资等提供多种应用了主题的 Url。这是有效目标的用户时要求您单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="143fe-p112">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
8. <span data-ttu-id="143fe-p113">指定自定义登录页 URL。使用此将用户重定向到末尾的成功的攻击指定的 URL。如果您具有内部认知培训，例如，您可以指定的下面。</span><span class="sxs-lookup"><span data-stu-id="143fe-p113">Specify a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
9. <span data-ttu-id="143fe-p114">指定**主题**字段的文本。这是显示为接收电子邮件客户端中的**使用者名称**的字段。</span><span class="sxs-lookup"><span data-stu-id="143fe-p114">Specify text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
10. <span data-ttu-id="143fe-159">撰写**电子邮件正文**将接收目标。</span><span class="sxs-lookup"><span data-stu-id="143fe-159">Compose the **Email body** that the target will receive.</span></span> <br/><span data-ttu-id="143fe-160">`${username}`将目标名称插入到电子邮件正文。</span><span class="sxs-lookup"><span data-stu-id="143fe-160">`${username}` inserts the targets name into the Email body.</span></span> <br/><span data-ttu-id="143fe-161">`${loginserverurl}`插入我们希望目标用户单击的 URL</span><span class="sxs-lookup"><span data-stu-id="143fe-161">`${loginserverurl}` inserts the URL we want target users to click</span></span> 
    
11. <span data-ttu-id="143fe-p115">选择**下一步，** 然后**完成**以启动攻击。矛网络钓鱼电子邮件传递到目标收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="143fe-p115">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="143fe-164">密码喷涂攻击</span><span class="sxs-lookup"><span data-stu-id="143fe-164">Password-spray attack</span></span>

<span data-ttu-id="143fe-p116">不良的 actor 成功获得有效用户从租户的列表后将通常用于针对组织的密码喷涂攻击。不良的 actor 了解常见人员使用的密码。这是广泛使用的攻击中，因为它是运行，且更难比暴力方法检测到便宜攻击。</span><span class="sxs-lookup"><span data-stu-id="143fe-p116">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant. The bad actor knows about common passwords that people use. This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="143fe-168">此类攻击着重于让您指定的用户的大型目标基针对公用密码。</span><span class="sxs-lookup"><span data-stu-id="143fe-168">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="143fe-169">若要模拟密码喷涂攻击</span><span class="sxs-lookup"><span data-stu-id="143fe-169">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="143fe-170">在[安全&amp;合规性中心](https://security.microsoft.com)，选择**威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="143fe-170">In the [Security &amp; Compliance Center](https://security.microsoft.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="143fe-171">指定攻击的有意义的市场活动名称。</span><span class="sxs-lookup"><span data-stu-id="143fe-171">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="143fe-p117">指定目标收件人。这可以是您的组织内个人或组。目标的收件人必须具有 Exchange Online 邮箱为了攻击成功。</span><span class="sxs-lookup"><span data-stu-id="143fe-p117">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="143fe-p118">指定要使用的攻击的密码。例如，您可以尝试的一个常见、 相关密码是`Fall2017`。可能有另一个`Spring2018`，或`Password1`。</span><span class="sxs-lookup"><span data-stu-id="143fe-p118">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="143fe-178">选择**完成**以启动攻击。</span><span class="sxs-lookup"><span data-stu-id="143fe-178">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="143fe-179">强制密码攻击</span><span class="sxs-lookup"><span data-stu-id="143fe-179">Brute-force password attack</span></span>

<span data-ttu-id="143fe-p119">不良的 actor 成功获得从租户的关键用户列表后，通常使用针对组织的密码强力攻击。此类攻击着重于尝试一组对单个用户的帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="143fe-p119">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant. This attack focuses on trying a set of passwords on a single user's account.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="143fe-182">模拟密码强力攻击</span><span class="sxs-lookup"><span data-stu-id="143fe-182">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="143fe-183">在[安全&amp;合规性中心](https://security.microsoft.com)，选择**威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="143fe-183">In the [Security &amp; Compliance Center](https://security.microsoft.com), choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="143fe-184">指定攻击的有意义的市场活动名称。</span><span class="sxs-lookup"><span data-stu-id="143fe-184">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="143fe-p120">指定目标收件人。目标的收件人必须具有 Exchange Online 邮箱为了攻击成功。</span><span class="sxs-lookup"><span data-stu-id="143fe-p120">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="143fe-p121">指定一组用于攻击的密码。若要执行此操作，您可用于文本 (.txt) 文件的密码列表。文本文件不能超过 10 MB 文件大小。使用一个密码每行，并确保可在列表中的最后一个密码后包含硬回车。</span><span class="sxs-lookup"><span data-stu-id="143fe-p121">Specify a set of passwords to use for the attack. To do this, you can use a text (.txt) file for your list of passwords. The text file cannot exceed 10 MB in file size. Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>
    
5. <span data-ttu-id="143fe-191">选择**完成**以启动攻击。</span><span class="sxs-lookup"><span data-stu-id="143fe-191">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="143fe-192">在攻击模拟器中的新增功能</span><span class="sxs-lookup"><span data-stu-id="143fe-192">New features in Attack Simulator</span></span>

<span data-ttu-id="143fe-p122">新功能添加到攻击模拟器。这些工具包括：</span><span class="sxs-lookup"><span data-stu-id="143fe-p122">New features are being added to Attack Simulator. These include:</span></span>
- <span data-ttu-id="143fe-p123">**报告功能的高级**。您将能够看到数据，例如最快 （或最慢） 时间最快 （或最慢） 时间打开攻击模拟电子邮件，单击中的消息和详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="143fe-p123">**Advanced reporting capabilities**. You'll be able to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more.</span></span>
- <span data-ttu-id="143fe-p124">**电子邮件模板编辑器**。您可以创建可用于将来攻击模拟的自定义的、 可重用的电子邮件模板。</span><span class="sxs-lookup"><span data-stu-id="143fe-p124">**Email template editor**. You can create a custom, reusable email template that you can use for future attack simulations.</span></span>

<span data-ttu-id="143fe-199">请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)以查看新增开发中什么推出，和哪些已启动。</span><span class="sxs-lookup"><span data-stu-id="143fe-199">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>




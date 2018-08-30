---
title: Office 365 中的攻击模拟器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/19/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
description: 了解关于三种不同类型的网络攻击，您可以使用攻击模拟器运行。
ms.openlocfilehash: 364144c0b2f8109c67fb262ce879414088380ebe
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525139"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="4a15f-103">Office 365 中的攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="4a15f-103">Attack Simulator in Office 365</span></span>

<span data-ttu-id="4a15f-p101">与攻击模拟器 （包含在[Office 365 威胁智能](office-365-ti.md)），如果您的组织的安全工作组成员可以实际攻击方案中运行您的组织。这可以帮助您确定并查找易受攻击用户前真实攻击影响您底线。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p101">With Attack Simulator (included in [Office 365 Threat Intelligence](office-365-ti.md)), if you are a member of your organization's security team, you can run realistic attack scenarios in your organization. This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span>
  
## <a name="the-attacks"></a><span data-ttu-id="4a15f-106">攻击</span><span class="sxs-lookup"><span data-stu-id="4a15f-106">The Attacks</span></span>

<span data-ttu-id="4a15f-107">在预览版我们提供您可以运行的攻击模拟的三种：</span><span class="sxs-lookup"><span data-stu-id="4a15f-107">At preview release we offer three kinds of attack simulations that you can run:</span></span>
  
- [<span data-ttu-id="4a15f-108">显示名称矛网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="4a15f-108">Display name spear-phishing attack</span></span>](attack-simulator.md#spearphish)
    
- [<span data-ttu-id="4a15f-109">密码喷涂攻击</span><span class="sxs-lookup"><span data-stu-id="4a15f-109">Password-spray attack</span></span>](attack-simulator.md#passwordspray)
    
- [<span data-ttu-id="4a15f-110">强制密码攻击</span><span class="sxs-lookup"><span data-stu-id="4a15f-110">Brute-force password attack</span></span>](attack-simulator.md#bruteforce)
    
<span data-ttu-id="4a15f-111">攻击者要成功启动，正在运行攻击和登录的帐户必须使用多因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="4a15f-111">For an attack to be successfully launched, the account that is running the attack and logged on must use multi-factor authentication.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a15f-112">条件访问支持即将提供。</span><span class="sxs-lookup"><span data-stu-id="4a15f-112">Support for Conditional Access is coming soon.</span></span> 
  
<span data-ttu-id="4a15f-113">若要访问攻击模拟器，安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="4a15f-113">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="4a15f-114">开始之前...</span><span class="sxs-lookup"><span data-stu-id="4a15f-114">Before you begin...</span></span>

<span data-ttu-id="4a15f-115">请确保您和您的组织满足攻击模拟器的以下要求：</span><span class="sxs-lookup"><span data-stu-id="4a15f-115">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>
  
- <span data-ttu-id="4a15f-116">贵组织拥有[Office 365 威胁智能](office-365-ti.md)与安全中可见的攻击模拟器&amp;合规性中心 (转到**威胁管理** \> **攻击模拟器**)</span><span class="sxs-lookup"><span data-stu-id="4a15f-116">Your organization has [Office 365 Threat Intelligence](office-365-ti.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>
    
- <span data-ttu-id="4a15f-p102">Exchange Online 中位于组织的电子邮件。（攻击模拟器不可用的内部部署电子邮件服务器。）</span><span class="sxs-lookup"><span data-stu-id="4a15f-p102">Your organization's email is hosted in Exchange Online. (Attack Simulator is not available for on-premises email servers.)</span></span>
    
- <span data-ttu-id="4a15f-119">您是 Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="4a15f-119">You are an Office 365 global administrator</span></span>
    
- <span data-ttu-id="4a15f-120">您的组织使用[的 Office 365 用户的多因素身份验证](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)</span><span class="sxs-lookup"><span data-stu-id="4a15f-120">Your organization is using [Multi-factor authentication for Office 365 users](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)</span></span>
    
## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="4a15f-121">显示名称矛网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="4a15f-121">Display name spear-phishing attack</span></span>

<span data-ttu-id="4a15f-p103">网络钓鱼的攻击 classed 社会工程样式攻击作为一组广泛的通用术语。此类攻击重点矛网络钓鱼，旨在个人或组织的特定组更有针对性的攻击。通常情况下，自定义与使用将生成信任收件人，例如看起来像来自组织内主管电子邮件中的显示名称并执行一些侦测攻击。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p103">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack. This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization. Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>
  
<span data-ttu-id="4a15f-p104">此类攻击着重于让您通过更改显示名称和源地址源自消息显示的操作。矛网络钓鱼攻击成功后，犯罪访问用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p104">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address. When spear-phishing attacks are successful, cybercriminals gain access to users' credentials.</span></span>
  
### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="4a15f-127">若要模拟矛网络钓鱼攻击</span><span class="sxs-lookup"><span data-stu-id="4a15f-127">To simulate a spear-phishing attack</span></span>

![撰写电子邮件正文](media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)
  
<span data-ttu-id="4a15f-p105">可以创建定制直接在**电子邮件正文**字段本身中丰富的 HTML 编辑器，也可以使用 HTML 源代码。有两个重要字段以包含在 HTML 中：</span><span class="sxs-lookup"><span data-stu-id="4a15f-p105">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source. There are two important fields for inclusion in the HTML:</span></span> 
  
1. <span data-ttu-id="4a15f-131">安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="4a15f-131">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="4a15f-132">指定攻击的有意义的市场活动名称，或选择一个模板。</span><span class="sxs-lookup"><span data-stu-id="4a15f-132">Specify a meaningful campaign name for the attack or select a template.</span></span>
    
    ![网络钓鱼开始页](media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)
  
3. <span data-ttu-id="4a15f-p106">指定目标收件人。这可以是您的组织内个人或组。目标的收件人必须具有 Exchange Online 邮箱为了攻击成功。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p106">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
    ![收件人选择](media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)
  
4. <span data-ttu-id="4a15f-138">配置网络钓鱼电子邮件详细信息。</span><span class="sxs-lookup"><span data-stu-id="4a15f-138">Configure the Phishing email details.</span></span>
    
    ![配置电子邮件的详细信息](media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)
  
    <span data-ttu-id="4a15f-p107">HTML 格式可以为复杂或基本随着您市场需求。按原样 HTML，您可以插入图像和文本以增强 believability。您可以控制上收到的消息中接收电子邮件客户端的类似。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p107">The HTML formatting can be as complex or basic as your campaign needs. As it is HTML, you can insert images and text to enhance believability. You have control on what the received message will look like in the receiving email client.</span></span>
    
1. <span data-ttu-id="4a15f-p108">文本输入**从 （名称）** 域。这是接收的电子邮件客户端中的**显示名称**中显示的字段。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p108">Enter text for the **From (Name)** field. This is the field that shows in the **Display Name** in the receiving email client.</span></span> 
    
2. <span data-ttu-id="4a15f-p109">输入文本或**从**域。这是显示为接收电子邮件客户端的发件人的电子邮件地址的字段。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p109">Enter text or the **From** field. This is the field that shows as the email address of the sender in the receiving email client.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="4a15f-p110">您可以输入贵组织中的现有电子邮件命名空间 （执行此操作将导致实际解决接收客户端，从而推动非常高信任模型中的电子邮件地址），也可以输入外部电子邮件地址。您指定不必实际存在的电子邮件地址，但它确实需要为以下的一个有效的 SMTP 地址，例如 user@domainname.extension 格式。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p110">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address. The email address that you specify does not have to actually exist, but it does need to following the format of a valid SMTP address, such as user@domainname.extension.</span></span> 
  
3. <span data-ttu-id="4a15f-p111">使用下拉选择器，选择一个反映您将拥有您攻击中的内容类型的网络钓鱼登录服务器 URL。您可供选择，如文档传递，技术，工资等提供多种应用了主题的 Url。这是有效目标的用户时要求您单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p111">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack. Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>
    
4. <span data-ttu-id="4a15f-p112">输入自定义登录页 URL。使用此将用户重定向到末尾的成功的攻击指定的 URL。如果您具有内部认知培训，例如，您可以指定的下面。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p112">Enter a custom landing page URL. Using this will redirect users to a URL you specify at the end of a successful attack. If you have internal awareness training, for example, you can specify that here.</span></span>
    
5. <span data-ttu-id="4a15f-p113">为**主题**字段中输入文本。这是显示为接收电子邮件客户端中的**使用者名称**的字段。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p113">Enter text for the **Subject** field. This is the field that shows as the **Subject Name** in the receiving email client.</span></span> 
    
5. <span data-ttu-id="4a15f-156">撰写**电子邮件正文**将接收目标。</span><span class="sxs-lookup"><span data-stu-id="4a15f-156">Compose the **Email body** that the target will receive.</span></span> 
  
 <span data-ttu-id="4a15f-157">**${用户名}** 将目标名称插入到电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="4a15f-157">**${username}** inserts the targets name into the Email body</span></span> 
  
 <span data-ttu-id="4a15f-158">**${loginserverurl}** 插入我们希望目标用户单击的 URL</span><span class="sxs-lookup"><span data-stu-id="4a15f-158">**${loginserverurl}** inserts the URL we want target users to click</span></span> 
    
6. <span data-ttu-id="4a15f-p114">选择**下一步，** 然后**完成**以启动攻击。矛网络钓鱼电子邮件传递到目标收件人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p114">Choose **Next,** then **Finish** to launch the attack. The spear phishing email message is delivered to your target recipients' mailboxes.</span></span> 
    
## <a name="password-spray-attack"></a><span data-ttu-id="4a15f-161">密码喷涂攻击</span><span class="sxs-lookup"><span data-stu-id="4a15f-161">Password-spray attack</span></span>

<span data-ttu-id="4a15f-p115">不良 actor 成功具有枚举的有效用户从租户，利用不知情的常见所用的密码列表后，通常用于针对组织的密码喷涂攻击。它是利用广泛，它是一种便宜的攻击，若要运行，且更难检测比暴力方法。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p115">A password spray attack against an organization is typically used after a bad actor has successfully enumerated a list of valid users from the tenant, utilizing their knowledge of common passwords used. It is utilized widely as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>
  
<span data-ttu-id="4a15f-164">此类攻击着重于让您指定的用户的大型目标基针对公用密码。</span><span class="sxs-lookup"><span data-stu-id="4a15f-164">This attack focuses on letting you specify a common password against a large target base of users.</span></span>
  
### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="4a15f-165">若要模拟密码喷涂攻击</span><span class="sxs-lookup"><span data-stu-id="4a15f-165">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="4a15f-166">安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="4a15f-166">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="4a15f-167">指定攻击的有意义的市场活动名称。</span><span class="sxs-lookup"><span data-stu-id="4a15f-167">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="4a15f-p116">指定目标收件人。这可以是您的组织内个人或组。目标的收件人必须具有 Exchange Online 邮箱为了攻击成功。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p116">Specify the target recipients. This can be individuals or groups in your organization. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="4a15f-p117">指定要使用的攻击的密码。例如，您可以尝试的一个常见、 相关密码是`Fall2017`。可能有另一个`Spring2018`，或`Password1`。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p117">Specify a password to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="4a15f-174">选择**完成**以启动攻击。</span><span class="sxs-lookup"><span data-stu-id="4a15f-174">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="brute-force-password-attack"></a><span data-ttu-id="4a15f-175">强制密码攻击</span><span class="sxs-lookup"><span data-stu-id="4a15f-175">Brute-force password attack</span></span>

<span data-ttu-id="4a15f-p118">针对组织的密码强力攻击通常用于后不良 actor 已成功枚举从租户的关键用户的列表。此类攻击着重于让您指定一组针对单个用户的密码。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p118">A brute-force password attack against an organization is typically used after a bad actor has successfully enumerated a list of key users from the tenant. This attack focuses on letting you specify a set of passwords against a single user.</span></span>
  
### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="4a15f-178">模拟密码强力攻击</span><span class="sxs-lookup"><span data-stu-id="4a15f-178">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="4a15f-179">安全中&amp;合规性中心中，选择**威胁管理** \> **攻击模拟器**。</span><span class="sxs-lookup"><span data-stu-id="4a15f-179">In the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>
    
2. <span data-ttu-id="4a15f-180">指定攻击的有意义的市场活动名称。</span><span class="sxs-lookup"><span data-stu-id="4a15f-180">Specify a meaningful campaign name for the attack.</span></span>
    
3. <span data-ttu-id="4a15f-p119">指定目标收件人。目标的收件人必须具有 Exchange Online 邮箱为了攻击成功。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p119">Specify the target recipient. A targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>
    
4. <span data-ttu-id="4a15f-p120">指定一组用于攻击的密码。例如，您可以尝试的一个常见、 相关密码是`Fall2017`。可能有另一个`Spring2018`，或`Password1`。</span><span class="sxs-lookup"><span data-stu-id="4a15f-p120">Specify a set of passwords to use for the attack. For example, one common, relevant password you could try is `Fall2017`. Another might be `Spring2018`, or `Password1`.</span></span>
    
5. <span data-ttu-id="4a15f-186">选择**完成**以启动攻击。</span><span class="sxs-lookup"><span data-stu-id="4a15f-186">Choose **Finish** to launch the attack.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="4a15f-187">相关主题</span><span class="sxs-lookup"><span data-stu-id="4a15f-187">Related topics</span></span>

[<span data-ttu-id="4a15f-188">Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="4a15f-188">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  


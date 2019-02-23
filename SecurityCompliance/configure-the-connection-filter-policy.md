---
title: 配置连接筛选器策略
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: 若要确保从不受信任的人发送的电子邮件被阻止, 可以使用连接筛选器策略创建您信任的 IP 地址的允许列表 (也称为 "安全发件人列表")。您还可以创建阻止的发件人列表。
ms.openlocfilehash: d7c99f8fb6b9b05efb800804927ccb26f7dd9f40
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216902"
---
# <a name="configure-the-connection-filter-policy"></a>配置连接筛选器策略
 
我们大多数人都有值得信赖的朋友和商业伙伴。若是在垃圾邮件文件夹中发现有来自他们的电子邮件，甚至是完全被垃圾邮件筛选器阻止，这将会是一件很令人沮丧的事情。如果想要确保对您信任的人所发的电子邮件不进行阻止，您可以使用连接筛选策略创建一个由您信任的 IP 地址构成的"允许"名单，也称为白名单。您通常也可以从已知垃圾邮件发送者（您永远不想接收由他们发来的电子邮件）创建一个阻止的发件人名单，也就是由一些 IP 地址组成的列表。
  
 有关适用于整个组织的详细垃圾邮件设置，请参阅[如何帮助确保邮件不会被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)。如果你拥有管理员级别控制，并且你想要防止误报或漏报问题，这些内容会很有帮助。
  
下面的视频显示了连接筛选器策略的配置步骤：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？
<a name="sectionSection0"> </a>

- 预计完成时间：15 分钟
    
- 您需要先分配权限, 然后才能执行此过程或过程。若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的 "反垃圾邮件" 条目。 
    
- 若要获取要允许或阻止其邮件的发件人的 IP 地址, 可以检查邮件的 Internet 邮件头。如[反垃圾邮件邮件头](anti-spam-message-headers.md)中所述, 查找 CIP 标头。有关如何在各种电子邮件客户端中查看邮件头的信息, 请参阅[邮件头分析器](https://go.microsoft.com/fwlink/p/?LinkId=306583)。 
    
- 从 IP 阻止列表中的 IP 地址发送的电子邮件被拒绝，未标记为垃圾邮件，且未进行其他筛选。
    
- 还可以通过远程 PowerShell 执行以下连接筛选过程。使用[set-hostedconnectionfilterpolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) cmdlet 可查看您的设置, 以及用于编辑连接筛选器策略设置的[set-hostedconnectionfilterpolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx) 。若要了解如何使用 Windows PowerShell 连接到 exchange online protection, 请参阅[连接到 exchange online protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。若要了解如何使用 Windows PowerShell 连接到 exchange online, 请参阅[连接到 exchange online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>使用 EAC 编辑默认连接筛选器策略
<a name="sectionSection1"> </a>

在 Exchange 管理中心 (EAC) 编辑连接筛选器策略，创建 IP 允许列表或 IP 阻止列表。连接筛选器策略设置只适用于入站邮件。
  
1. 在 Exchange 管理中心 (EAC) 中, 导航到 "**保护** \> **连接筛选器**", 然后双击默认策略。
    
2. 单击 "**连接筛选**" 菜单项, 然后创建所需的列表: ip 允许列表和/或 ip 阻止列表。 
    
    若要创建这些列表, ![请单击](media/ITPro-EAC-AddIcon.gif)"添加图标"。在随后出现的对话框中, 指定 IP 地址或地址范围, 然后单击 **"确定"**。重复此过程以添加其他地址。(添加或删除已添加的 IP 地址后, 也可以对其进行编辑或删除。)
    
    > [!NOTE]
    >  如果将 IP 地址添加到两个列表中, 则允许从该 ip 地址发送的电子邮件。 

    以 nnn 的格式指定 IPV4 IP 地址。 nnn 为0到255之间的数字。您还可以指定无类别的域间路由 (CIDR) 范围, 格式为 nnn/rr, 其中 rr 是介于24到32之间的数字。若要指定从24至32范围之外的范围, 请参阅[配置 IP 允许列表时的其他注意事项](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists)。 

    最多可以指定1273个条目, 其中条目是单个 ip 地址或 ip 地址的 CIDR 范围 (从/24 到/32)。> 如果要发送 TLS 加密邮件, 则不支持 IPv6 地址和地址范围。 
  
3. (可选) 选中 "**启用安全列表**" 复选框以防止某些已知发件人丢失的电子邮件。计算?Microsoft 订阅了受信任发件人的第三方来源。使用此安全列表意味着这些受信任的发件人不会被错误地标记为垃圾邮件。我们建议选择此选项, 因为它应减少您收到的误报数 (作为垃圾邮件分类的邮件)。 
    
4. 单击 "**保存**"。右窗格中将显示默认策略设置的摘要。
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>配置 IP 允许列表时的其他注意事项
<a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a>

以下是在配置 IP 允许列表时需要考虑或应该注意的其他注意事项。
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>指定超出建议范围的 CIDR 范围

若要指定从/1 到/23 的 CIDR IP 地址范围, 必须创建一个邮件流规则, 该规则在设置垃圾邮件可信度 (SCL) 的 IP 地址范围上运行, 以**绕过垃圾邮件筛选**(意味着从该 IP 地址范围内接收的所有邮件都是设置为 "非垃圾邮件"), 并且服务不执行其他筛选。但是, 如果这些 IP 地址中的任何一个出现在任何 Microsoft 的专用阻止列表或任何第三方阻止列表中, 则这些邮件仍将被阻止。因此, 强烈建议使用/24 to/32 IP 地址范围。 
  
若要创建此邮件流规则, 请执行以下步骤。
  
1. 在 EAC 中, 导航到 "**邮件流** \> "**规则**。
    
2. 单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后选择 "**创建新规则**"。
    
3. 为该规则命名, 然后单击 "**更多选项**"。
    
4. 在 "在以下**情况应用此规则**" 下, 选择 **"发件人"** , 然后选择 " **IP 地址" 在这些范围中的任何范围或完全匹配**。
    
5. 在 "**指定 ip 地址**" 中, 指定 ip 地址范围, **** ![单击 "添加](media/ITPro-EAC-AddIcon.gif)" "添加图标", 然后单击 **"确定"**。
    
6. 在 "**执行以下**操作" 框中, 通过选择 **"修改邮件属性**", 然后**设置垃圾邮件可信度 (SCL)** 来设置操作。在 "**指定 SCL** " 框中, 选择 "**绕过垃圾邮件筛选**", 然后单击 **"确定"**。
    
7. 如果你愿意, 可以选择审核规则、测试规则、在特定时间段内激活规则, 以及进行其他选择。建议在强制执行规则之前对其进行测试。[Exchange Server 中的邮件流规则的过程](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)包含有关这些选择的详细信息。 
    
8. 单击 "**保存**" 以保存该规则。规则将显示在规则列表中。 
    
创建并强制执行规则后, 服务将绕过您指定的 IP 地址范围的垃圾邮件筛选。
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>为特定域设置 IP 允许列表例外作用域

通常情况下，我们建议您将您认为对于所有域而言安全的 IP 地址（或 IP 地址范围）添加到 IP 允许列表。但是，如果您不希望 IP 允许列表条目应用于所有域，则可以创建一条应用范围不包括特定域的传输规则。 
  
例如，让我们假设您有三个域：ContosoA.com、ContosoB.com 和 ContosoC.com，您希望添加 IP 地址（为了简便起见，我们使用 1.2.3.4），并且只针对域 ContosoB.com 跳过筛选。您可以为 1.2.3.4 创建 IP 允许列表，它会将所有域的垃圾邮件可信度 (SCL) 设置为 -1（意味着它被分类为非垃圾邮件）。然后，您可以创建一条传输规则，将除 ContosoB.com 之外的所有域的 SCL 设置为 0。这将使与该 IP 地址相关、除 ContosoB.com（在规则中被列为例外的域）之外的所有域的邮件被重新扫描。ContosoB.com 的 SCL 仍为 -1，这意味着它将跳过筛选，而 ContosoA.com 和 ContosoC.com 的 SCL 为 0，这意味着内容筛选器将重新扫描它们。
  
为此，请执行下列步骤：
  
1. 在 EAC 中, 导航到 "**邮件流** \> "**规则**。
    
2. 单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后选择 "**创建新规则**"。
    
3. 为该规则命名, 然后单击 "**更多选项**"。
    
4. 在 "在以下**情况应用此规则**" 下, 选择 **"发件人"** , 然后选择 " **IP 地址" 在这些范围中的任何范围或完全匹配**。
    
5. 在 "**指定 ip 地址**" 框中, 指定在 ip 允许列表中输入的 ip 地址或 ip 地址范围, **** ![单击 "添加](media/ITPro-EAC-AddIcon.gif)" "添加" 图标, 然后单击 **"确定"**。
    
6. 在 "**执行以下**操作" 下, 通过选择 **"修改邮件属性**", 然后**设置垃圾邮件可信度 (SCL)** 来设置操作。在 "**指定 SCL** " 框中, 选择 " **0**", 然后单击 **"确定"**。
    
7. 单击 "**添加例外**", 并在 "**除非**" 下选择 **"发件人"** , 然后选择 "**域为**"。 
    
8. 在 "**指定域**" 框中, 输入要绕过垃圾邮件筛选的域, 例如**contosob.com**。单击 "**添加** !["](media/ITPro-EAC-AddIcon.gif)图标将其移动到短语列表。如果要将其他域添加为例外, 请重复此步骤, 然后在完成时单击 **"确定"** 。 
    
9. 如果你愿意, 可以选择审核规则、测试规则、在特定时间段内激活规则, 以及进行其他选择。建议在强制执行规则之前对其进行测试。[Exchange Server 中的邮件流规则的过程](https://docs.microsoft.com/en-us/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)包含有关这些选择的详细信息。 
    
10. 单击 "**保存**" 以保存该规则。规则将显示在规则列表中。 
    
在创建和强制应用规则后，仅为您输入的例外的域绕过指定 IP 地址或 IP 地址范围的垃圾邮件筛选。
  
## <a name="new-to-office-365"></a>刚开始接触 Office 365？
<a name="sectionSection3"> </a>

||
|:-----|
|![LinkedIn Learning 短图标](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **刚开始接触 Office 365？**         发现 LinkedIn Learning 向 **Office 365 admins and IT pros**提供的免费视频课程。 |
   
## <a name="for-more-information"></a>详细信息
<a name="sectionSection4"> </a>

[Exchange Online 中的安全发件人和阻止发件人列表](safe-sender-and-blocked-sender-lists-faq.md)
  
[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)
  
[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)
  
[如何帮助确保邮件不会标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  


---
title: 配置连接筛选器策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
description: 若要确保不阻止从您信任的人员发送的电子邮件，可以使用的连接筛选器策略创建一个允许列表，也称为安全发件人列表，您信任的 IP 地址。您还可以创建阻止发件人列表。
ms.openlocfilehash: cb9b73ff61b477f1c7ea0bb8da4039bebce83d1b
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003261"
---
# <a name="configure-the-connection-filter-policy"></a>配置连接筛选器策略
 
我们大多数人都有值得信赖的朋友和商业伙伴。若是在垃圾邮件文件夹中发现有来自他们的电子邮件，甚至是完全被垃圾邮件筛选器阻止，这将会是一件很令人沮丧的事情。如果想要确保对您信任的人所发的电子邮件不进行阻止，您可以使用连接筛选策略创建一个由您信任的 IP 地址构成的"允许"名单，也称为白名单。您通常也可以从已知垃圾邮件发送者（您永远不想接收由他们发来的电子邮件）创建一个阻止的发件人名单，也就是由一些 IP 地址组成的列表。
  
 有关适用于整个组织的详细垃圾邮件设置，请参阅[如何帮助确保邮件不会被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)。如果你拥有管理员级别控制，并且你想要防止误报或漏报问题，这些内容会很有帮助。
  
下面的视频显示了连接筛选器策略的配置步骤：
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？
<a name="sectionSection0"> </a>

- 估计完成时间：15 分钟
    
- 您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的"反垃圾邮件"条目。 
    
- 要获取想要允许或阻止其邮件的发件人的 IP 地址，你可以检查邮件的 Internet 标题。查找 CIP 标题，如[反垃圾邮件邮件头](anti-spam-message-headers.md)中所述。有关如何查看各种电子邮件客户端中的电子邮件头的信息，请参阅[邮件头分析器](https://go.microsoft.com/fwlink/p/?LinkId=306583)主题。 
    
- 从 IP 阻止列表中的 IP 地址发送的电子邮件被拒绝，未标记为垃圾邮件，且未进行其他筛选。
    
- 也可以通过远程 PowerShell 执行下面的连接筛选器过程。使用[Get-HostedConnectionFilterPolicy](http://technet.microsoft.com/library/bd751db2-3f26-495b-8e5a-4fcab53b17fd.aspx) cmdlet 可以查看您的设置，以及[Set-hostedconnectionfilterpolicy](http://technet.microsoft.com/library/ccb5731b-3fca-4d69-a91f-5049ea963fac.aspx)编辑您的连接筛选器策略设置。若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection，请参阅[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>使用 EAC 编辑默认连接筛选器策略
<a name="sectionSection1"> </a>

在 Exchange 管理中心 (EAC) 编辑连接筛选器策略，创建 IP 允许列表或 IP 阻止列表。连接筛选器策略设置只适用于入站邮件。
  
1. 在 Exchange 管理员中心 (EAC) 中，导航到**保护** \> **连接筛选器**，然后双击默认策略。
    
2. 单击**连接筛选**菜单项，然后创建所需的列表： IP 允许列表、 IP 阻止列表，或同时。 
    
    若要创建这些列表，请单击![添加图标](media/ITPro-EAC-AddIcon.gif)。在随后出现的对话框中指定的 IP 地址或地址范围，，然后单击**ok**。重复此过程以添加其他地址。（您可以还编辑或删除 IP 地址后已添加。）
    
    > [!NOTE]
    >  如果向这两个列表添加一个 IP 地址，则允许从其发送的电子邮件。 >  IPV4 IP 地址必须以 nnn.nnn.nnn.nnn 的格式进行指定，其中 nnn 代表 0 至 255 的任意数字。您也可以采用 nnn.nnn.nnn.nnn/rr 格式指定无类别域际路由选择 (CIDR) 的范围，其中 rr 代表 24 至 32 的任意数字。要指定超出 24 至 32 的范围，请参阅 [配置 IP 允许列表时的其他注意事项](configure-the-connection-filter-policy.md#bkmk_addtionalconsiderationswhenconfiguringipallowlists)。 >  您最多可以指定 1273 个条目，条目可以是单个 IP 地址或 IP 地址的 CIDR 范围（从 /24 到 /32）。 >  如果您发送 TLS 加密邮件，则不支持 IPv6 地址和地址范围。 
  
3. （可选） 选中**启用安全列表**复选框，以防止缺少来自特定已知发件人的电子邮件。如何？Microsoft 订阅到的受信任的发件人的第三方源。使用此安全列表意味着这些受信任的发件人不会错误地标记为垃圾邮件。我们建议选择此选项，因为它应减少的收到的误报 （为垃圾邮件分类的良好邮件）。 
    
4. 单击**保存**。在右窗格中显示的默认策略设置摘要。
    
## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>配置 IP 允许列表时的其他注意事项
<a name="bkmk_addtionalconsiderationswhenconfiguringipallowlists"> </a>

以下是在配置 IP 允许列表时需要考虑或应该注意的其他注意事项。
  
### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>指定超出建议范围的 CIDR 范围

若要指定 CIDR IP 地址范围为从/1 到 /23，必须创建传输规则操作的设置的垃圾邮件可信度 (SCL) 的 IP 地址范围**绕过垃圾邮件筛选**（这意味着从收到此 IP 地址范围内的所有消息都都到设置为"非垃圾邮件？和任何其他筛选服务执行）。但是，如果任何这些 IP 地址出现在任何 Microsoft 的专有阻止列表或我们第三方阻止的任何列表，仍能阻止这些邮件。因此强烈建议您使用到/24/32 IP 地址范围。 
  
若要创建此传输规则，请执行以下步骤。
  
1. 在 EAC 中，导航到**邮件流** \> **规则**。
    
2. 单击![添加图标](media/ITPro-EAC-AddIcon.gif)，然后选择**创建新规则**。
    
3. 为该规则指定一个名称，然后单击**更多选项**。
    
4. 在**以下情况应用此规则**，选择**发件人**，然后选择**IP 地址处于这些范围或完全匹配**。
    
5. 在**指定 IP 地址**，请指定 IP 地址范围，单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后单击**确定**。
    
6. 在**执行以下操作**下选择**修改邮件属性**，然后**将垃圾邮件可信度 (SCL) 设置**中设置操作。在**指定 SCL**框中，选择**绕过垃圾邮件筛选**，并单击**确定**。
    
7. 如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。我们建议首先在一段时间内测试规则，然后再强制应用。[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)包含有关这些选择的详细信息。 
    
8. 单击**保存**按钮保存规则。显示在列表中的规则。 
    
创建并强制应用规则之后，您指定的 IP 地址范围会绕过垃圾邮件筛选。
  
### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>为特定域设置 IP 允许列表例外作用域

通常情况下，我们建议您将您认为对于所有域而言安全的 IP 地址（或 IP 地址范围）添加到 IP 允许列表。但是，如果您不希望 IP 允许列表条目应用于所有域，则可以创建一条应用范围不包括特定域的传输规则。 
  
例如，让我们假设您有三个域：ContosoA.com、ContosoB.com 和 ContosoC.com，您希望添加 IP 地址（为了简便起见，我们使用 1.2.3.4），并且只针对域 ContosoB.com 跳过筛选。您可以为 1.2.3.4 创建 IP 允许列表，它会将所有域的垃圾邮件可信度 (SCL) 设置为 -1（意味着它被分类为非垃圾邮件）。然后，您可以创建一条传输规则，将除 ContosoB.com 之外的所有域的 SCL 设置为 0。这将使与该 IP 地址相关、除 ContosoB.com（在规则中被列为例外的域）之外的所有域的邮件被重新扫描。ContosoB.com 的 SCL 仍为 -1，这意味着它将跳过筛选，而 ContosoA.com 和 ContosoC.com 的 SCL 为 0，这意味着内容筛选器将重新扫描它们。
  
为此，请执行下列步骤：
  
1. 在 EAC 中，导航到**邮件流** \> **规则**。
    
2. 单击![添加图标](media/ITPro-EAC-AddIcon.gif)，然后选择**创建新规则**。
    
3. 为该规则指定一个名称，然后单击**更多选项**。
    
4. 在**以下情况应用此规则**，选择**发件人**，然后选择**IP 地址处于这些范围或完全匹配**。
    
5. 在**指定 IP 地址**框中，指定的 IP 地址或 IP 地址范围您输入的 IP 允许列表中，单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后单击**确定**。
    
6. 下**执行以下操作**，通过选择**修改邮件属性**，然后**将垃圾邮件可信度 (SCL) 设置**来设置操作。在**指定 SCL**框中，选择**0**，并单击**确定**。
    
7. 单击**添加例外**，并在**除非**下选择**发件人**选择**域**。 
    
8. 在**指定域**框中，输入您要绕过垃圾邮件筛选，如**contosob.com**的域。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)以将其移到的短语列表。如果您想要将其他域添加为异常，并在完成时单击**确定**，请重复此步骤。 
    
9. 如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。我们建议首先在一段时间内测试规则，然后再强制应用。[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)包含有关这些选择的详细信息。 
    
10. 单击**保存**按钮保存规则。显示在列表中的规则。 
    
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
  


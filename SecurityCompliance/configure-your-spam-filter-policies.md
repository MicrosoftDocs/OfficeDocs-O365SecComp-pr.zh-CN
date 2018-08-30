---
title: 配置垃圾邮件筛选器策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
description: 选择要对标识为垃圾邮件的邮件采取的操作，并选择是否要筛选以特定语言撰写或从特定国家或地区发送的邮件，包括基本的垃圾邮件筛选器设置。
ms.openlocfilehash: 3e24a69dacc18272baa710c18492759f67583f4f
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002961"
---
# <a name="configure-your-spam-filter-policies"></a>配置垃圾邮件筛选器策略
  
选择要对标识为垃圾邮件的邮件采取的操作，并选择是否要筛选以特定语言撰写或从特定国家或地区发送的邮件，包括基本的垃圾邮件筛选器设置。垃圾邮件筛选器策略设置是仅应用于入站邮件。您可以编辑默认垃圾邮件筛选器策略来配置您的公司范围内垃圾邮件筛选器设置和创建自定义垃圾邮件筛选器策略，然后将它们应用于特定用户、 组或组织中的域。自定义策略始终优先于默认策略。您可以更改您的自定义策略运行通过更改每个自定义策略的优先级顺序。
  
> [!IMPORTANT]
> Exchange Online Protection (EOP) 独立客户： 默认情况下，EOP 垃圾邮件筛选器将垃圾邮件检测到的邮件发送到每个收件人的垃圾邮件文件夹。但是，以确保本地邮箱**移动到垃圾邮件文件夹的邮件**操作，必须配置 Exchange 传输规则来检测垃圾邮件邮件头由 EOP 添加您的本地服务器上。有关详细信息，请参阅[确保垃圾邮件被路由到每个用户的垃圾邮件文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 
  
## <a name="what-you-must-know-before-you-begin"></a>您必须知道开始之前

估计完成时间：30 分钟
  
您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的反垃圾邮件条目。 
  
若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
  
## <a name="use-the-exchange-admin-center-eac-to-configure-spam-filter-policies"></a>使用 Exchange 管理中心 (EAC) 配置垃圾邮件筛选器策略

1. 在 Exchange 管理员中心 (EAC) 中，导航到**保护** \> **垃圾邮件筛选器**。
    
2. 执行下列操作之一在**常规**页上： 
    
  - 双击默认策略，以编辑公司范围的策略。
    
  - 单击![添加图标](media/ITPro-EAC-AddIcon.gif)以创建新的自定义垃圾邮件筛选器策略可应用于用户、 组和您的组织中的域的**新**图标。您还可以通过双击其编辑现有的自定义策略。 
    
3. 自定义的策略，指定此策略的名称。您还可以指定的更详细的说明。无法重命名默认策略。
    
    > [!NOTE]
    > 创建策略时，单个屏幕上将显示所有配置设置。相比之下，编辑策略时，您必须在多个屏幕导航。设置是在任一情况下，相同，但此过程的其余部分将介绍如何访问这些设置，当您编辑策略。 
  
4. 在**垃圾邮件和批量电子邮件操作**页上的在**垃圾邮件**和**高可信度垃圾邮件**，下，选择要为传入的垃圾邮件和批量电子邮件执行的操作。默认情况下，选择**将邮件移动到垃圾邮件文件夹**。其他可能的值为： 
    
  - **删除消息**删除整个邮件，包括所有附件。 
    
  - **隔离邮件**发送到预期接收人而不是隔离的邮件。如果选择此选项，请在**保留期限 （天） 的垃圾邮件**输入框中，指定将在此期间隔离垃圾邮件的天数。（它将自动删除后经过的时间。默认值为 15 天，这是最大值。最小值是 1 天）。 
    
    > [!TIP]
    >  有关管理员如何管理 EAC 的隔离驻留的电子邮件的信息，请参阅[隔离](quarantine.md)和[查找并释放隔离的邮件，以管理员身份](find-and-release-quarantined-messages-as-an-administrator.md)。> 的有关如何配置垃圾邮件通知消息发送给用户的信息，请参阅[配置最终用户垃圾邮件在 EOP 中的通知](configure-end-user-spam-notifications-in-eop.md)或[配置最终用户垃圾邮件通知在 Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md)。 
  
  - **移动到垃圾邮件文件夹的邮件**将邮件发送到指定的收件人的垃圾邮件文件夹。这是这两个可信度阈值级别的默认操作。 
    
    > [!IMPORTANT]
    > 仅针对 Exchange Online Protection (EOP) 客户：要使用内部部署邮箱执行此项操作，必须在内部部署服务器上配置两个 Exchange 传输规则，检测 EOP 添加的垃圾邮件头。有关详细信息，请参阅[确保垃圾邮件已路由到每个用户的"垃圾邮件"文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 
  
  - **添加 X 标头**将邮件发送到指定的收件人，但将 X 标头文本添加到邮件头，以便识别为垃圾邮件消息。使用此文本作为标识符，您可以 （可选） 创建收件箱规则或使用下游设备对邮件进行操作。默认 X 标头文本是**出现此消息是垃圾邮件**。
    
    使用**添加此 X 标头文本**输入框中，可以自定义 X 标头文本。如果您在自定义 X 标头文本，应注意以下条件： 
    
  - 如果只有标头指定格式的\<*标头*\>，其中内没有空格\<*标头*\>，冒号将追加到的自定义文本后, 跟默认文本。例如，如果您指定"这是-我的自定义的标头"，则 X 标头文本将显示为"这是-我的自定义的标头： 出现此消息是垃圾邮件。"       
    
  - 如果包括空格内的自定义标头文本，或者如果您自己添加冒号 (如"X 这是我的自定义标头"或"X-This-is-my-custom-header:")，则 X 标头文本恢复为默认值为"X 此-是-垃圾邮件： 出现此消息是垃圾邮件。"
    
  - 不能指定的标题文本格式的\<*标头*\>:\<*值*\>。如果这样做，同时值之前和之后冒号将被忽略，和默认 X 标头文本显示改为:"X 此-是-垃圾邮件： 出现此消息是垃圾邮件。"       
    
  - **Prepend 主题行文本**将邮件发送给预期收件人但预置的主题行**前缀与此文本的主题行**输入框中指定的文本。使用此文本作为标识符，您可以选择创建规则以筛选或将消息路由必要。 
    
  - **电子邮件地址的邮件重定向**将邮件发送到指定的电子邮件地址，而不是给预期收件人。**重定向到此电子邮件地址**输入框中指定的"重定向"地址。 
    
    > [!NOTE]
    > 有关垃圾邮件可信度级别的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。 
  
5. 在**批量电子邮件**，下，您可以选择将批量电子邮件视为垃圾邮件阈值。此阈值基于消息的批量投诉级别。可以从 1 到 9，其中 1 表示为垃圾邮件，电子邮件最大容量，9 允许大多数批量电子邮件传送选择的阈值设置。服务然后执行配置的操作，例如将邮件发送到收件人的垃圾邮件文件夹。请参阅[批量投诉级别值](bulk-complaint-level-values.md)和[垃圾邮件和批量邮件之间的区别是什么？](what-s-the-difference-between-junk-email-and-bulk-email.md)的详细信息。 
    
6. 在**阻止列表**页上，您可以指定项，如发件人或域时，将始终标记为垃圾邮件。该服务将这些条目匹配的电子邮件上应用配置高可信度垃圾邮件操作。 
    
  - 将不需要的发件人添加到阻止发件人列表中。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后在选择对话框中，添加您想要阻止的发件人地址。您可以单独使用分号或新行的多个条目。单击**确定**以返回到**阻止列表**页上。 
    
  - 将不需要的域添加到阻止域列表中。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后在选择对话框中，添加您想要阻止的域。您可以单独使用分号或新行的多个条目。单击**确定**以返回到**阻止列表**页上。 
    
    > [!CAUTION]
    > 如果您阻止顶级域，很可能会将您需要的电子邮件标记为垃圾邮件。 
  
7. 在**允许列表**页上，您可以指定项，如发件人或域时，总是会发送到收件箱。垃圾邮件筛选器不处理电子邮件从这些条目。 
    
  - 添加受信任的发件人与发件人允许列表。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后在选择对话框中，添加您希望允许的发件人地址。您可以单独使用分号或新行的多个条目。单击确定以返回到**允许列表**页。 
    
  - 添加受信任的域到域的允许列表。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后在选择对话框中，添加您希望允许的域。您可以单独使用分号或新行的多个条目。单击确定以返回到**允许列表**页。 
    
    > [!CAUTION]
    > 如果您允许顶级域，很可能会将您不需要的电子邮件发送到收件箱。 
  
8. **国际垃圾邮件**页上，您可以筛选以特定语言撰写或从特定国家或地区发送的电子邮件。您可以配置最多 86 不同的语言和 250 不同的区域。该服务将应用高可信度垃圾邮件配置的操作。 
    
1. 选择**筛选器中的以下语言编写的电子邮件**复选框以启用此功能。单击![添加图标](media/ITPro-EAC-AddIcon.gif)，然后，在选择对话框中进行的选择 （支持多重选择）。例如，如果**隔离邮件**是您配置的操作的高可信度垃圾邮件筛选消息写入中阿拉伯语 (AR)，选择，则会隔离阿拉伯语中写入任何邮件。单击**确定**以返回到**国际垃圾邮件**窗格。 
    
2. 选择**从以下的国家或地区筛选器电子邮件发送**复选框以启用此功能。单击![添加图标](media/ITPro-EAC-AddIcon.gif)，然后，在选择对话框中进行的选择 （支持多重选择）。例如，如果您选择，以筛选从澳大利亚 (AU)，发送的所有邮件和**隔离邮件**是从澳大利亚发送中您配置的操作的高可信度垃圾邮件，则任何邮件将被隔离。单击**确定**以返回到**国际垃圾邮件**窗格。 
    
    > [!NOTE]
    > 默认情况下，如果未选择任何国际垃圾邮件选项，那么该服务将对采用所有语言及来自所有区域的邮件执行正常垃圾邮件筛选。如果确定邮件为垃圾邮件或高可信度垃圾邮件，则会对其进行分析并应用配置的操作。 
  
9. 在**高级选项**页中，可以为每个高级垃圾邮件筛选选项中选择**上**，**关闭**或**测试**。 
    
1. **在**根据与该选项相关联的规则主动筛选消息。可以将邮件标记为垃圾邮件或将其垃圾邮件得分基础上增大了，具体取决于哪些选项您打开。 
    
2. **关闭**符合垃圾邮件筛选器条件的邮件不采取任何操作。默认情况下关闭所有选项。 
    
3. **测试**符合垃圾邮件筛选器条件的邮件不采取任何操作。但是，可以通过其传送到预期接收人之前添加 X 标头标记邮件。此 X 标头让您了解哪个 ASF 选项匹配。如果您指定的任何高级选项的**测试**，您可以配置以下测试模式设置要应用对已启用测试选项进行匹配时： 
    
  - **无**对邮件采取任何测试模式操作。这是默认按钮。 
    
  - **添加默认测试 X 标头文本**选择此选项将邮件发送到指定的收件人，但还将特殊 X 标头添加到邮件标识为具有匹配特定高级垃圾邮件筛选选项。 
    
  - **发送到此地址密件抄送邮件**选择此选项将邮件的密件抄送副本发送到的输入框中指定的电子邮件地址。 
    
    > [!TIP]
    > 有关高级垃圾邮件筛选选项，包括有关每个选项和 X 标头文本与每个，关联的说明的详细信息，请参阅[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)。 
  
10. 自定义策略仅，单击**应用于**菜单项，然后创建基于条件的规则以指定用户、 组和要应用此策略的域。如果它们都是唯一，您可以创建多个条件。 
    
  - 若要选择用户，选择**收件人**。在随后出现的对话框中，从您的公司从用户选取器列表中，选择一个或多个发件人，然后单击**添加**。若要添加的发件人不在列表中，键入其电子邮件地址，然后单击**检查名称**。在此框中，您还可以使用通配符的多个电子邮件地址 (例如： \* @  _domainname_)。当您完成进行选择，单击**确定**以返回到主屏幕。 
    
  - 若要选择组，选择**收件人的成员**。然后，在随后出现的对话框中，选择或指定的组。单击**确定**以返回到主屏幕。 
    
  - 若要选择域，选择**收件人的域是**。然后，在随后出现的对话框中，添加域。单击**确定**以返回到主屏幕。 
    
    您可以创建在规则中的例外。例如，您可以筛选来自特定域除外的所有域的邮件。单击**添加例外**，然后创建例外条件类似于您创建其他条件的方式。
    
    > [!TIP]
    > 将垃圾邮件策略应用于组是仅支持**启用邮件的安全组**。 
  
11. 单击**保存**。在右窗格中显示的策略设置摘要。
    
> [!TIP]
>  您可以选择或清除**启用**列中启用或禁用您的自定义策略中的复选框。默认情况下，启用所有策略。无法禁用默认策略。> 到删除自定义策略，请选择该策略中，单击![删除图标](media/ITPro-EAC-DeleteIcon.gif)**删除**图标，然后确认您想要删除的策略。无法删除默认策略。> 自定义策略始终优先于默认策略。自定义策略与您在其中创建这些 （从最旧到最新），相反的顺序运行，但您可以通过单击更改您的自定义策略的优先级 （运行顺序）![向上箭头图标](media/ITPro-EAC-UpArrowIcon.gif)向上箭头和![向下箭头图标](media/ITPro-EAC-DownArrowIcon.gif)向下箭头。**优先级**为**0**的策略将运行第一个、 后跟**1**，然后**2**，依此类推。 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>使用远程 PowerShell 配置垃圾邮件筛选器策略

您还可以配置并应用在 PowerShell 中的垃圾邮件筛选器策略。若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?linkid=396554)。若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection，请参阅[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。
  
- [Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) 查看垃圾邮件筛选器设置。 
    
- [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) 编辑垃圾邮件筛选器设置。 
    
- [New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) 创建新的自定义垃圾邮件筛选器策略。 
    
- [Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) 删除自定义垃圾邮件筛选器策略。 
    
若要向用户、组和/或域应用自定义垃圾邮件筛选器策略，请使用 [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) cmdlet（创建可应用于自定义策略的新筛选器规则）或 [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) cmdlet（编辑可应用于自定义策略的现有筛选器规则）。使用 [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) cmdlet 或 [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) cmdlet 可启用或禁用应用于策略的规则。 
  
## <a name="how-do-you-know-this-worked"></a>您如何知道操作成功？

为了确保垃圾邮件被正确地检测并处理过，您可以通过服务发送一封 GTUBE 邮件。与 EICAR 杀毒测试文件相似，GTUBE 提供了一个测试，通过此测试可以验证服务是否正在检测传入的垃圾邮件。GTUBE 邮件应该始终被垃圾邮件筛选器检测为垃圾邮件，对邮件执行的操作应该与配置设置相匹配。
  
邮件中包括以下单行 GTUBE 文本，没有任何空格或换行符：
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a>优化垃圾邮件筛选器策略，防止误报和漏报

如果想采取积极方法进行垃圾邮件筛选，可以启用高级垃圾邮件筛选选项。有关适用于整个组织的常规垃圾邮件设置，请参阅[使用安全列表或其他技术防止误报电子邮件被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)。如果你拥有管理员级别控制，并且你想要阻止误报或漏报问题，这些会很有帮助。
   
## <a name="for-more-information"></a>详细信息
<a name="sectionSection6"> </a>

[配置连接筛选器策略](configure-the-connection-filter-policy.md)
  
[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)
  
[隔离](quarantine.md)
  
[使用安全列表或其他技术阻止误报电子邮件被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  


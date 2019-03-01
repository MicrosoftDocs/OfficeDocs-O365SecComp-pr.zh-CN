---
title: 配置垃圾邮件筛选器策略
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 基本垃圾邮件筛选器设置包括选择要对被标识为垃圾邮件的邮件执行的操作, 并选择是筛选以特定语言编写的邮件还是从特定的国家或地区发送的邮件。
ms.openlocfilehash: 1f5ff5db88d11971df070d316ad4aaff6eb88712
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341803"
---
# <a name="configure-your-spam-filter-policies"></a>配置垃圾邮件筛选器策略
  
基本垃圾邮件筛选器设置包括选择要对被标识为垃圾邮件的邮件执行的操作。垃圾邮件筛选器策略设置仅适用于入站邮件。您可以编辑默认垃圾邮件筛选器策略, 以配置公司范围的垃圾邮件筛选器设置并创建自定义垃圾邮件筛选器策略, 然后将其应用到组织中的特定用户、组或域。自定义策略的优先级始终高于默认策略。您可以通过更改每个自定义策略的优先级来更改自定义策略的运行顺序;但是, 如果有多个策略满足条件集, 将仅应用最高优先级策略。 
  
> [!IMPORTANT]
> 对于 Exchange Online Protection (EOP) 独立客户: 默认情况下, EOP 垃圾邮件筛选器将检测到的垃圾邮件发送到每个收件人的 "垃圾邮件" 文件夹。但是, 为了确保 "**将邮件移动到垃圾邮件文件夹**" 操作适用于本地邮箱, 您必须在您的本地服务器上配置 Exchange 邮件流规则 (也称为传输规则), 以检测通过添加的垃圾邮件头。EOP.有关详细信息, 请参阅[确保垃圾邮件已路由到每个用户的 "垃圾邮件" 文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 
  
## <a name="what-you-must-know-before-you-begin"></a>开始之前您必须了解的内容

估计完成时间：30 分钟
  
您需要先分配权限, 然后才能执行此过程或过程。若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的反垃圾邮件条目。 
  
若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
  
## <a name="use-the-security--compliance-center-scc-to-configure-spam-filter-policies"></a>使用安全 & 合规性中心 (SCC) 配置垃圾邮件筛选器策略

1. 在安全 & 合规性中心 (SCC) 中, 导航到 "**威胁管理** \> **策略** \> **反垃圾邮件**"。
    
2. 在 "**反垃圾邮件设置**" 页上执行下列操作之一: 
    
      - 查看 "标准设置" 下的 "默认公司范围" 策略。
    
      - 单击 "**自定义**" 选项卡, 将 "**自定义设置**选择器" 更改为![ **"打开**", 然后单击 "添加图标](media/ITPro-EAC-AddIcon.gif) " "**创建策略**" 按钮, 以便创建可应用于用户、组和的新自定义垃圾邮件筛选器策略组织中的域。您还可以通过双击现有的自定义策略对其进行编辑。 
    
3. 对于 "仅限自定义策略", 请指定策略的名称。(可选) 还可以指定更详细的说明。您不能重命名默认策略。<br/><br/>注意: 创建策略时, 所有配置设置都将显示在单个屏幕上。相比之下, 在编辑策略时, 您必须在多个屏幕中导航。在这两种情况下, 设置都是相同的, 但此过程的其余部分介绍在编辑策略时如何访问这些设置。 
  
4. 在 "**垃圾邮件和批量电子邮件操作**" 页上的 "**垃圾**邮件和**高可信度垃圾**邮件" 下, 选择要对传入垃圾邮件和批量电子邮件执行的操作。默认情况下, "**将邮件移动到垃圾邮件" 文件夹**处于选中状态。其他可能的值包括: 
    
      - **删除邮件:** 删除整个邮件, 包括所有附件。 
        
      - **隔离邮件:** 将邮件发送到隔离, 而不是发送给预期的收件人。如果选择此选项, 请在 "**保留垃圾邮件时间 (天)** " 输入框中, 指定隔离垃圾邮件的天数。(它将在经过一段时间后自动删除。默认值为15天, 即最大值。最小值为1天。<br/><br/>提示: 有关管理员如何管理 EAC 中隔离的电子邮件的信息, 请参阅[隔离](quarantine.md)并[以管理员身份查找并释放隔离邮件](find-and-release-quarantined-messages-as-an-administrator.md)。> 有关如何配置要发送给用户的垃圾邮件通知邮件的信息, 请参阅[在 EOP 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-eop.md)或[在 Exchange Online 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-exchange-online.md)。 
  
      - **将邮件移动到垃圾邮件文件夹:** 将邮件发送到指定收件人的 "垃圾邮件" 文件夹。这是这两个置信度阈值级别的默认操作。<br/><br/>**重要说明**: 对于 Exchange Online Protection (EOP) 客户: 为了使此操作能够使用本地邮箱, 必须在您的本地服务器上配置两个 Exchange 邮件流规则, 以检测 EOP 添加的垃圾邮件头。有关详细信息, 请参阅[确保垃圾邮件已路由到每个用户的 "垃圾邮件" 文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。
  
      - **添加 X 标头:** 将邮件发送给指定的收件人, 但将 X 标头文本添加到邮件头, 以便将邮件标识为垃圾邮件。使用此文本作为标识符, 您可以选择创建收件箱规则或使用下游设备对邮件进行操作。默认的 X 标头文本是**此消息看起来是垃圾**邮件。<br/>您可以使用 "**添加此 x 标头文本**输入" 框自定义 X 标头文本。如果自定义 X 标头文本, 请注意以下条件: 
    
      - 如果您仅在格式\< *头*\>中指定了标头, 而\<*页眉*\>中没有空格, 则会将冒号追加到自定义文本, 后跟默认文本。例如, 如果指定 "my my custom-header", 则 X 标头文本将显示为 "我自定义标头: 此消息看起来是垃圾邮件"。       
        
      - 如果在自定义页眉文本中包含空格, 或者您在自己添加冒号 (例如 "x 这是我的自定义标头" 或 "x-my custom-头:"), 则 X 标头文本将恢复为默认值 "x-垃圾邮件: 此邮件看起来是垃圾邮件"。
    
      - 不能在 " \< *页眉*\>:\<"*值*\>中指定标头文本。如果这样做, 冒号前后的值都将被忽略, 而默认的 X 标头文本将显示为: "x-this-垃圾邮件: 此邮件看起来是垃圾邮件"。       
      
      - 请注意, 由于邮箱垃圾邮件配置, 具有此 X 标头的邮件可能仍被移动到邮箱垃圾邮件文件夹中。您可以通过使用 set-mailboxjunkemailconfiguration 禁用此功能来更改此设置。
        
      - 将**主题行前置文字:** 将邮件发送给预期收件人, 但在 "主题" 行前面加上在 "**前缀主题行**" 中指定的文本, 并在此文本输入框中指定。使用此文本作为标识符, 您可以根据需要创建规则以筛选或路由邮件。 
        
      - **将邮件重定向到电子邮件地址:** 将邮件发送到指定的电子邮件地址, 而不是发送给预期的收件人。在 "**重定向到此电子邮件地址**" 输入框中, 指定 "重定向" 地址。<br/><br/>注意: 有关垃圾邮件可信度级别的详细信息, 请参阅[垃圾邮件可信度](spam-confidence-levels.md)。 
  
5. 在 "**批量电子邮件**" 下, 您可以选择将批量电子邮件视为垃圾邮件的阈值。此阈值基于邮件的批量投诉级别。可以选择1到9之间的阈值设置, 其中1表示最大批量电子邮件为垃圾邮件, 9 允许传递最大批量电子邮件。然后, 该服务执行配置的操作, 例如, 将邮件发送到收件人的 "垃圾邮件" 文件夹。请参阅[批量投诉级别值](bulk-complaint-level-values.md)以及[垃圾邮件和批量电子邮件之间有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)有关详细信息, 请参阅。 
    
6. 在 "**阻止列表**" 页上, 您可以指定将始终被标记为垃圾邮件的条目, 如发件人或域。该服务将对与这些条目匹配的电子邮件应用配置的高可信度垃圾邮件操作。 
    
      - 将不需要的发件人添加到发件人阻止列表。单击 "**添加**!["](media/ITPro-EAC-AddIcon.gif)"添加" 图标, 然后在选择对话框中添加要阻止的发件人地址。您可以使用分号或新行分隔多个条目。单击 **"确定"** 以返回到 "**阻止列表**" 页面。 
        
      - 将不需要的域添加到域阻止列表中。单击 "**添加**!["](media/ITPro-EAC-AddIcon.gif)"添加" 图标, 然后在选择对话框中添加要阻止的域。您可以使用分号或新行分隔多个条目。单击 **"确定"** 以返回到 "**阻止列表**" 页面。<br/><br/>**警告: 如果阻止顶级域, 您需要的电子邮件可能会被标记为垃圾邮件。** 
  
7. 在 "**允许列表**" 页上, 您可以指定将始终传递到收件箱的条目, 如发件人或域。垃圾邮件筛选器不会处理来自这些条目的电子邮件。 
    
      - 将受信任的发件人添加到发件人允许列表。单击 "**添加**!["](media/ITPro-EAC-AddIcon.gif)"添加" 图标, 然后在选择对话框中添加您希望允许的发件人地址。您可以使用分号或新行分隔多个条目。单击 "确定" 以返回到 "**允许列表**" 页。 
        
      - 将受信任域添加到域允许列表中。单击 "**添加**!["](media/ITPro-EAC-AddIcon.gif)"添加" 图标, 然后在选择对话框中添加您希望允许的域。您可以使用分号或新行分隔多个条目。单击 "确定" 以返回到 "**允许列表**" 页。<br/><br/>**警告: 如果允许顶级域, 则不需要的电子邮件将被传递到收件箱。** 
  
8. 在 "**国际垃圾邮件**" 页面上, 您可以筛选以特定语言编写或从特定国家或地区发送的电子邮件。您可以配置最高86个不同的语言和250个不同的区域。该服务将对高可信度垃圾邮件应用已配置的操作。 
    
9. 选中 "**筛选使用以下语言编写的电子**邮件" 复选框以启用此功能。单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后在选择对话框中进行选择 (支持多重选择)。例如, 如果您选择筛选以阿拉伯语 (AR) 编写的邮件, 并且**隔离邮件**是为高可信度垃圾邮件配置的操作, 则将隔离以阿拉伯语编写的所有邮件。单击 **"确定"** 以返回到**国际垃圾邮件**窗格。 
    
10. 选中 "**筛选从以下国家或地区发送的电子**邮件" 复选框以启用此功能。单击!["添加](media/ITPro-EAC-AddIcon.gif)图标", 然后在选择对话框中进行选择 (支持多重选择)。例如, 如果您选择筛选从澳大利亚 (AU) 发送的所有邮件, 并且**隔离邮件**是为高可信度垃圾邮件配置的操作, 则将隔离从澳大利亚发送的所有邮件。单击 **"确定"** 以返回到**国际垃圾邮件**窗格。<br/><br/>默认情况下，如果未选择任何国际垃圾邮件选项，那么该服务将对采用所有语言及来自所有区域的邮件执行正常垃圾邮件筛选。如果确定邮件为垃圾邮件或高可信度垃圾邮件，则会对其进行分析并应用配置的操作。 
  
11. 在 "**高级选项**" 页上, 可以为每个高级垃圾邮件筛选选项选择 **"开**"、"**关**" 或 "**测试**"。 
    
12. **上**邮件将根据与该选项相关联的规则进行主动筛选。邮件可能被标记为垃圾邮件, 或者将根据您打开的选项增加垃圾邮件得分。 
    
13. **Off**不会对符合垃圾邮件筛选条件的邮件执行任何操作。默认情况下, 所有选项都处于关闭状态。 
    
14. **测试**不会对符合垃圾邮件筛选条件的邮件执行任何操作。但是, 可以通过在将 X 标头传递给预期的收件人之前添加 X 标头来标记邮件。此 X 标头可让你知道匹配哪个 ASF 选项。如果为任何高级选项指定了**Test** , 则可以配置以下测试模式设置, 以便在对启用了测试的选项进行匹配时应用: 
    
      - **无**对邮件不执行任何测试模式操作。此为默认值。 
        
      - **添加默认测试 X 标头文本**如果选择此选项, 则会将邮件发送给指定的收件人, 但也会在邮件中添加特殊的 X 标头, 以将其标识为符合特定高级垃圾邮件筛选选项。 
        
      - 向**此地址发送密件抄送邮件**选择此选项可将邮件的密件抄送副本发送到您在输入框中指定的电子邮件地址。 <br/><br/>有关高级垃圾邮件筛选选项的详细信息, 包括每个选项的说明以及与每个选项相关联的 X 标头文本, 请参阅[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)。 
  
15. 仅对于自定义策略, 单击 "**应用于**" 菜单项, 然后创建基于条件的规则, 以指定要向其应用此策略的用户、组和域。您可以创建多个条件 (如果它们是唯一的)。 
    
      - 若要选择用户, 请选择 **"收件人是"**。在随后出现的对话框中, 从 "用户选取器" 列表中选择公司中的一个或多个发件人, 然后单击 "**添加**"。若要添加不在列表中的发件人, 请键入他们的电子邮件地址, 然后单击 "**检查姓名**"。在此框中, 您还可以对多个电子邮件地址使用通配符 ( \* @ 例如: _domainname_)。完成选择后, 单击 **"确定"** 以返回到主屏幕。 
        
      - 若要选择组, 请选择 **"收件人是" 的成员**。然后, 在随后出现的对话框中, 选择或指定组。单击 **"确定"** 返回到主屏幕。 
        
      - 若要选择域, 请选择 **"收件人域"**。然后, 在随后的对话框中, 添加域。单击 **"确定"** 返回到主屏幕。<br/><br/>您可以在规则中创建例外。例如, 可以从除特定域之外的所有域中筛选邮件。单击 "**添加例外**", 然后创建例外条件, 类似于创建其他条件的方法。<br/><br/>仅支持**启用邮件的安全组**将垃圾邮件策略应用到组。 
  
16. 单击 "**保存**"。右窗格中将显示策略设置的摘要。

无法禁用或删除默认策略, 并且自定义策略的优先级始终高于默认策略。对于自定义策略, 您可以选中或清除 "**启用**" 列中的复选框以启用或禁用它们。默认情况下, 启用所有策略。若要删除自定义策略, 请选择该策略, ![单击 "](media/ITPro-EAC-DeleteIcon.gif)删除图标" "**删除**" 图标, 然后确认要删除该策略。

> [!TIP]
>  您![可以通过单击向上箭头图标](media/ITPro-EAC-UpArrowIcon.gif)向上箭头和![向下箭头图标](media/ITPro-EAC-DownArrowIcon.gif)向下箭头更改自定义策略的优先级 (运行顺序)。**优先级**为**0**的策略将先运行, 再运行**1**, 然后是**2**, 依此类推。 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>使用远程 PowerShell 配置垃圾邮件筛选器策略

您还可以在 PowerShell 中配置和应用垃圾邮件筛选器策略。若要了解如何使用 Windows PowerShell 连接到 exchange online, 请参阅[连接到 exchange online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。若要了解如何使用 Windows PowerShell 连接到 exchange online protection, 请参阅[连接到 exchange online protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。
  
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
  


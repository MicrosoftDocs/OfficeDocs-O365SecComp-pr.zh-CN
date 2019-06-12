---
title: 配置垃圾邮件筛选器策略
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/05/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 基本垃圾邮件筛选器设置包括选择要对被标识为垃圾邮件的邮件执行的操作。
ms.openlocfilehash: be99c017a5038fbfb431edbcf2d65c877d92388c
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857652"
---
# <a name="configure-your-spam-filter-policies"></a>配置垃圾邮件筛选器策略
垃圾邮件筛选器设置包括选择要对被标识为垃圾邮件的邮件执行的操作。 垃圾邮件筛选器策略设置仅适用于入站邮件, 有两种类型:

  - 默认: 默认的垃圾邮件筛选器策略用于配置公司范围的垃圾邮件筛选器设置。 此策略不能重命名, 且始终处于打开。

  - 自定义: 自定义垃圾邮件筛选器策略可以精细并应用于组织中的特定用户、组或域。 自定义策略的优先级始终高于默认策略。 您可以通过更改每个自定义策略的优先级来更改自定义策略的运行顺序;但是, 如果多个策略满足条件集, 则只有最高优先级 (即最接近0的数字) 策略适用。

## <a name="what-you-must-know-before-you-begin"></a>开始之前您必须了解的内容

估计完成时间：30 分钟
  
您必须先获得权限，然后才能执行此过程或多个过程。 若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的反垃圾邮件条目。

垃圾邮件筛选器策略设置全部在安全 & 合规中心 (SCC) 中。 有关详细信息, 请参阅[Office 365 Security & 合规性中心](go-to-the-securitycompliance-center.md)。 "反垃圾邮件设置" 页位于 "SCC \> **威胁管理** \> **策略** \> **反垃圾邮件**" 部分中。

## <a name="access-and-create-spam-filter-policies"></a>访问和创建垃圾邮件筛选器策略

在 "反垃圾邮件设置" 页面中, 可以在 "标准" 选项卡中查看默认设置。若要更改这些设置, 请切换到 "**自定义**" 选项卡。你将能够在默认垃圾邮件筛选器策略中查看和配置某些默认设置。

若要启用更多自定义设置或添加自定义策略, 请将**自定义设置**选择器更改为**打开**, 以启用自定义垃圾邮件筛选器策略。 您可以通过在此处展开现有的自定义策略来查看它们。

## <a name="configure-custom-spam-filter-policy-settings"></a>配置自定义垃圾邮件筛选器策略设置

1. 如果要编辑策略, 请选择并单击 "**编辑策略**"。否则, 单击 "**创建策略**"

2. 您可以为自定义策略指定一个唯一名称, 但不能重命名默认的名称。 (可选) 还可以为任何策略指定更详细的说明。

3. 在 "**垃圾邮件和批量操作**" 部分下:

  - 为**垃圾**邮件、**高可信度垃圾邮件**、**网络钓鱼电子**邮件和**批量电子邮件**类型选择操作。 可用值有： 

    - **将邮件移动到垃圾邮件文件夹:** 将邮件发送到指定收件人的 "垃圾邮件" 文件夹。 这是垃圾邮件、高可信度垃圾邮件和批量的默认操作。<br/><br/>

    > [!NOTE]
    > 为了使此操作能够与本地邮箱配合使用, 必须在您的本地服务器上配置两个 Exchange 邮件流规则 (也称为传输规则), 以检测由 EOP 添加的垃圾邮件头。 有关详细信息, 请参阅如何[确保垃圾邮件被路由到每个用户的 "垃圾邮件" 文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 此步骤对 Exchange Online Protection (EOP) 独立客户非常关键。

    - **添加 X 标头:** 将邮件发送给指定的收件人, 但将 X 标头文本添加到邮件头, 以便将邮件标识为垃圾邮件。 使用此文本作为标识符, 您可以选择创建收件箱规则或使用下游设备对邮件进行操作。 默认的 X 标头文本是**此消息看起来是垃圾**邮件。<br/>您可以使用 "**添加此 x 标头文本**输入" 框自定义 X 标头文本。 如果自定义 X 标头文本, 请注意以下条件: 
    
      - 如果您仅在格式\< *头*\>中指定了标头, 而\<*页眉*\>中没有空格, 则会将冒号追加到自定义文本, 后跟默认文本。       例如, 如果指定 "my my custom-header", 则 X 标头文本将显示为 "我自定义标头: 此消息看起来是垃圾邮件"。 
        
      - 如果在自定义页眉文本中包含空格, 或者您在自己添加冒号 (例如 "X 这是我的自定义标头" 或 "X-my custom-头:"), 则 X 标头文本将恢复为默认值 "X-垃圾邮件: 此邮件看起来是垃圾邮件"。
    
      - 您不能指定格式为 \< *header*  \>:\<  *value*  \> 的标头文本。 如果这样做, 冒号前后的值都将被忽略, 而默认的 X 标头文本将显示为: "X-This-垃圾邮件: 此邮件看起来是垃圾邮件"。 
      
      - 请注意, 由于邮箱垃圾邮件配置, 具有此 X 标头的邮件可能仍被移动到邮箱垃圾邮件文件夹中。 您可以通过使用 Set-mailboxjunkemailconfiguration 禁用此功能来更改此设置。

    - 将**主题行前置文字:** 将邮件发送给预期收件人, 但在 "主题" 行前面加上在 "**前缀主题行**" 中指定的文本, 并在此文本输入框中指定。 使用此文本作为标识符, 您可以根据需要创建规则以筛选或路由邮件。 

    - **将邮件重定向到电子邮件地址:** 将邮件发送到指定的电子邮件地址, 而不是发送给预期的收件人。 在 "**重定向到此电子邮件地址**" 输入框中, 指定 "重定向" 地址。

    - **删除邮件:** 删除整个邮件, 包括所有附件。 
        
    - **隔离邮件:** 将邮件发送到隔离, 而不是发送给预期的收件人。 这是网络钓鱼的默认操作。 （它将在该时间结束后自动删除。 默认值为 15 天，也是最大值。 默认值为30天, 即最大值。 ）<br/><br/>提示: 有关管理员如何管理 EAC 中隔离的电子邮件的信息, 请参阅[隔离](quarantine.md)并[以管理员身份查找并释放隔离邮件](find-and-release-quarantined-messages-as-an-administrator.md)。 > 有关如何配置要发送给用户的垃圾邮件通知邮件的信息, 请参阅[在 EOP 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-eop.md)或[在 Exchange Online 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-exchange-online.md)。 

  - 配置**选择 "阈值"** , 以根据邮件的批量投诉级别 (BCL) 确定要将批量电子邮件视为垃圾邮件的方式。 可以选择1到9之间的阈值设置, 其中1表示最大批量电子邮件为垃圾邮件, 9 允许传递最大批量电子邮件。 然后，服务执行配置的操作，如将邮件发送到收件人的"垃圾邮件"文件夹。 请参阅[批量投诉级别值](bulk-complaint-level-values.md)以及[垃圾邮件和批量电子邮件之间有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)有关详细信息, 请参阅。 

4. 在 "**垃圾邮件属性**" 页上, 您可以通过配置以下命令来设置策略的测试模式选项: 
    
      - **无**对邮件不执行任何测试模式操作。 此为默认选项。 
        
      - **添加默认测试 X 标头文本**如果选择此选项, 则会将邮件发送给指定的收件人, 但也会在邮件中添加特殊的 X 标头, 以将其标识为符合特定高级垃圾邮件筛选选项。 
        
      - 向**此地址发送密件抄送邮件**选择此选项可将邮件的密件抄送副本发送到您在输入框中指定的电子邮件地址。 <br/><br/>有关高级垃圾邮件筛选选项的详细信息, 包括每个选项的说明以及与每个选项相关联的 X 标头文本, 请参阅[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)。

5. 仅对于自定义策略, 单击 "**应用于**" 菜单项, 然后创建基于条件的规则, 以指定要向其应用此策略的用户、组和域。 您可以创建多个条件 (如果它们是唯一的)。 
    
      - 若要选择用户，请选择“收件人是”****。 在随后出现的对话框中, 从 "用户选取器" 列表中选择公司中的一个或多个发件人, 然后单击 "**添加**"。 若要添加不在列表中的发件人, 请键入他们的电子邮件地址, 然后单击 "**检查姓名**"。 在该框中，您也可以使用通配符来表示多个电子邮件地址（例如：\*@ _domainname_）。 完成选择后, 单击 **"确定"** 以返回到主屏幕。 
        
      - 若要选择组, 请选择 **"收件人是" 的成员**。 然后, 在随后出现的对话框中, 选择或指定组。 单击“确定”**** 返回到主屏幕。 
        
      - 若要选择域, 请选择 **"收件人域"**。 然后, 在随后的对话框中, 添加域。 单击“确定”**** 返回到主屏幕。 <br/><br/>您可以在规则中创建例外。 例如, 可以从除特定域之外的所有域中筛选邮件。 单击 "**添加例外**", 然后创建例外条件, 类似于创建其他条件的方法。<br/><br/>仅支持**启用邮件的安全组**将垃圾邮件策略应用到组。 
  
6. 单击“保存”****。 右窗格中将会显示策略设置的摘要。

无法禁用或删除默认策略, 并且自定义策略的优先级始终高于默认策略。 对于自定义策略, 您可以选中或清除 "**启用**" 列中的复选框以启用或禁用它们。 默认情况下, 启用所有策略。 若要删除自定义策略, 请选择该策略, ![单击 "](media/ITPro-EAC-DeleteIcon.gif)删除图标" "**删除**" 图标, 然后确认要删除该策略。

> [!TIP]
> 您![可以通过单击向上箭头图标](media/ITPro-EAC-UpArrowIcon.gif)向上箭头和![向下箭头图标](media/ITPro-EAC-DownArrowIcon.gif)向下箭头更改自定义策略的优先级 (运行顺序)。 **优先级**为**0**的策略将先运行, 再运行**1**, 然后是**2**, 依此类推。 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>使用远程 PowerShell 配置垃圾邮件筛选器策略

您也可以在 PowerShell 中配置和应用垃圾邮件筛选器策略。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection, 请参阅[连接到 Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。
  
- [Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) 查看垃圾邮件筛选器设置。 
    
- [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) 编辑垃圾邮件筛选器设置。 
    
- [New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) 创建新的自定义垃圾邮件筛选器策略。 
    
- [Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) 删除自定义垃圾邮件筛选器策略。 
    
若要向用户、组和/或域应用自定义垃圾邮件筛选器策略，请使用 [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) cmdlet（创建可应用于自定义策略的新筛选器规则）或 [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) cmdlet（编辑可应用于自定义策略的现有筛选器规则）。使用 [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) cmdlet 或 [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) cmdlet 可启用或禁用应用于策略的规则。 
  
## <a name="how-do-you-know-this-worked"></a>您如何知道这有效？

为了确保垃圾邮件被正确地检测并处理过，您可以通过服务发送一封 GTUBE 邮件。与 EICAR 杀毒测试文件相似，GTUBE 提供了一个测试，通过此测试可以验证服务是否正在检测传入的垃圾邮件。GTUBE 邮件应该始终被垃圾邮件筛选器检测为垃圾邮件，对邮件执行的操作应该与配置设置相匹配。
  
邮件中包括以下单行 GTUBE 文本，没有任何空格或换行符：
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a>优化垃圾邮件筛选器策略，防止误报和漏报

如果要采用更严格的垃圾邮件筛选方法, 可以启用高级垃圾邮件筛选技术。 有关适用于整个组织的常规垃圾邮件设置，请参阅[使用安全列表或其他技术防止误报电子邮件被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](reduce-spam-email.md)。 如果你拥有管理员级别控制，并且你想要阻止误报或漏报问题，这些会很有帮助。

## <a name="allowblock-lists"></a>允许/阻止列表

有时, 我们的筛选器会错过邮件, 或者我们的系统需要一些时间才能追赶。 在这种情况下, 反垃圾邮件策略具有可用于覆盖当前判定的 Allow 和 Block 列表。 此选项应只使用很少的原因, 因为列表可能会变得难以管理和暂时临时, 因为我们的筛选堆栈应执行所需的操作。

"允许" 和 "阻止" 列表均配置为任何客户反垃圾邮件策略的一部分:

1. 在 "**允许列表**" 部分, 您可以指定将始终传递到收件箱的条目, 如发件人或域。 这些条目发送的电子邮件不会被垃圾邮件筛选器处理。 
    
      - 将可信发件人添加到发件人允许列表。 单击 "**编辑**![添加](media/ITPro-EAC-AddIcon.gif)图标", 然后在选择对话框中添加您希望允许的发件人地址。 您可以使用分号或通过换行分隔多个条目。 单击 "**保存**" 以返回到 "**允许列表**" 页。 
        
      - 将可信域添加到域允许列表。 单击 "**编辑**![添加](media/ITPro-EAC-AddIcon.gif)图标", 然后在选择对话框中添加您希望允许的域。 您可以使用分号或通过换行分隔多个条目。 单击 "**保存**" 以返回到 "**允许列表**" 页。 

> [!CAUTION]
> 永远不应将接受的域 (拥有的域) 或通用域 (如 Microsoft.com、office.com 等) 列出到允许列表中。 这可以轻松地让 spoofers 向组织发送不受限制的邮件。

2. 在 "**阻止列表**" 页上, 您可以指定将始终被标记为垃圾邮件的条目, 如发件人或域。 服务将对匹配这些条目的电子邮件应用配置的高可信度垃圾邮件操作。 
    
      - 将不需要的发件人添加到发件人阻止列表。 单击 "**编辑**![添加](media/ITPro-EAC-AddIcon.gif)图标", 然后在选择对话框中添加要阻止的发件人地址。 您可以使用分号或通过换行分隔多个条目。 单击 "**保存**" 以返回到 "**阻止列表**" 页面。 
        
      - 将不需要的域添加到域阻止列表。 单击 "**编辑**![添加](media/ITPro-EAC-AddIcon.gif)图标", 然后在选择对话框中添加要阻止的域。 您可以使用分号或通过换行分隔多个条目。 单击 "**保存**" 以返回到 "**阻止列表**" 页面。

> [!TIP]
>  在某些情况下, 您的组织可能与服务所提供的结论不一致。 在这种情况下, 您可能希望保留 "允许" 或 "阻止" 列表永久保留。 但是, 如果您要将某个域放在允许列表中的时间过长, 您应该告知发件人, 以确保其域已通过身份验证, 如果不是, 则将其设置为 DMARC 拒绝。

## <a name="for-more-information"></a>详细信息
<a name="sectionSection6"> </a>

[为 DMARC 设置域](use-dmarc-to-validate-email.md)
  
[隔离](quarantine.md)
  
[使用安全列表或其他技术阻止误报电子邮件被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)

[垃圾邮件可信度](spam-confidence-levels.md)
  


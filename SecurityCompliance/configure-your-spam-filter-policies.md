---
title: 配置垃圾邮件筛选器策略
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/05/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 基本垃圾邮件筛选器设置包括选择要对标识为垃圾邮件的邮件采取的措施。
ms.openlocfilehash: e06714e4a27601c7606c580551217155688a6169
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854656"
---
# <a name="configure-your-spam-filter-policies"></a>配置垃圾邮件筛选器策略
垃圾邮件筛选器设置包括选择要对标识为垃圾邮件的邮件采取的措施。 垃圾邮件筛选器策略设置仅适用于入站邮件，并且有两种类型：

  - 默认：将使用默认垃圾邮件筛选器策略来配置公司范围的垃圾邮件筛选器设置。 无法重命名此策略，并且其始终启用。

  - 自定义：自定义垃圾邮件筛选器策略可能很精细， 并应用到组织中的特定用户、组或域。 自定义策略的优先级始终高于默认策略。 可通过更改每个自定义策略的优先级来更改自定义策略的运行顺序。但是，如果多个策略符合设置的条件，则仅应用最高优先级（即最接近 0 的数字）的策略。

## <a name="what-you-must-know-before-you-begin"></a>开始之前必须了解的内容

估计完成时间：30 分钟
  
您必须先获得权限，然后才能执行此过程或多个过程。 若要查看所需的权限，请参阅 [Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的"反垃圾邮件"条目。

垃圾邮件筛选器策略设置均位于安全与合规中心 (SCC) 中。 更多信息可在[转到 Office 365 安全与合规中心](go-to-the-securitycompliance-center.md)中找到。 “反垃圾邮件设置”页面位于“SCC”\>**“威胁管理”** **\>**“策略”**\>**“反垃圾邮件”** 部分。 

## <a name="access-and-create-spam-filter-policies"></a>访问和创建垃圾邮件筛选器策略

在“反垃圾邮件设置”页面中，可在“标准”选项卡中查看默认设置。若要更改这些设置, 请切换到 **“自定义”** 选项卡。你将能够在“默认”垃圾邮件筛选器策略中查看和配置某些默认设置。

若要启用更多自定义设置或添加自定义策略，请将 **“自定义设置”** 选择器更改为 **“启用”** 以启用自定义垃圾邮件筛选器策略。 可通过在此处展开现有自定义策略查看它们。

## <a name="configure-custom-spam-filter-policy-settings"></a>配置自定义垃圾邮件筛选器策略设置

1. 如果正在编辑策略，请选择并单击 **“编辑策略”**；否则单击 **“创建策略”**

2. 可为自定义策略指定唯一的名称，但不能重命名默认项。 你还可以选择性地为任何策略指定详细说明。

3. 在 **“垃圾邮件和批量操作”** 部分下：

  - 为 **“垃圾邮件”**、**“高可信度垃圾邮件”**、**“仿冒电子邮件”** 和 **“批量电子邮件”** 类型指定操作。 可用值有： 

    - **将邮件移动到垃圾邮件文件夹：** 将邮件发送到指定收件人的垃圾邮件文件夹。 这是适用于垃圾邮件、高度可信度垃圾邮件和批量邮件的默认操作。<br/><br/>

    > [!NOTE]
    > 要使用内部部署邮箱执行此项操作，必须在内部部署服务器上配置两个 Exchange 流程规则（也称为传输规则），检测 EOP 添加的垃圾邮件头。 有关详细信息，请参阅如何[确保垃圾邮件已路由到每个用户的“垃圾邮件”文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 此步骤对于 Exchange Online Protection (EOP) 独立客户至关重要。

    - **添加 X 标头：** 发送邮件给指定收件人，但是为邮件添加 X 标头文本将其标识为垃圾邮件。 使用此文本作为标识符，你可以选择性地创建收件箱规则，或者使用下游设备来操作该邮件。 默认的 X 标头文本是 **“此邮件可能是垃圾邮件”**。<br/>您可以使用 **“添加该 X 标头文本”** 输入框自定义 X 标头文本。 如果您自定义 X 标头文本，请注意以下情况： 
    
      - 如果您仅指定格式为 \<*header*\> 的标头（\<*header*\> 中没有空格），那么自定义文本会附加一个冒号，后跟默认文本。 例如，如果您指定“This-is-my-custom-header”，则 X 标头文本会显示为“This-is-my-custom-header: 此邮件可能是垃圾邮件。” 
        
      - 如果你在自定义标头文本中包含空格，或者自己添加了冒号（例如“X This is my custom header”或“X-This-is-my-custom-header:”），X 标头文本将恢复为默认设置“X-This-Is-Spam: 此邮件可能是垃圾邮件。”
    
      - 你不能指定格式为“\<*header*  \>:\<  *value* \>”的标头文本。 如果这样做，系统将会忽略冒号前后的两个值，并且改为显示默认 X 标头文本：“X-This-Is-Spam: 此邮件可能是垃圾邮件。” 
      
      - 请注意，由于邮箱垃圾邮件配置的原因，包含此 X 标头的邮件可能仍会被移到邮箱垃圾邮件文件夹中。 可通过使用“MailboxJunkEmailConfiguration”禁用此功能来更改这一点。

    - **预挂起带文本的主题行：** 发送邮件给目标收件人，但是预挂起在 **“带该文本的前缀主题行”** 输入框中指定的带文本主题行。 通过将此文本作为标识符，可以选择创建按需筛选或路由邮件的规则。 

    - **重定向至电子邮件地址：**  发送邮件到指定电子邮件地址而不是目标收件人。 在 **“重定向至此电子邮件地址”** 输入框中指定“重定向”地址。

    - **删除邮件：** 删除整个邮件，包括所有附件。 
        
    - **隔离邮件：** 发送邮件至隔离邮件而不是目标收件人。 这是适用于仿冒邮件的默认操作。 （它将在该时间结束后自动删除。 （它将在该时间结束后自动删除。 默认值为 30 天（最大值）。 最小值为 1 天。）<br/><br/>提示：有关管理员如何管理 EAC 的隔离电子邮件的信息，请参阅[隔离](quarantine.md)和[以管理员身份查找并释放隔离邮件](find-and-release-quarantined-messages-as-an-administrator.md)。 > 有关如何配置要发送到用户的垃圾邮件通知消息的信息，请参阅[在 EOP 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-eop.md)或[在 Exchange Online 中配置最终用户垃圾邮件通知](configure-end-user-spam-notifications-in-exchange-online.md)。 

  - 配置 **“选择阈值”**，以根据邮件的批量投诉级别 (BCL) 确定希望如何将批量电子邮件视为垃圾邮件。 您可以从 1 - 9 中选择一个阈值设置，其中 1 将大部分批量电子邮件指明为垃圾邮件，9 允许传递大部分批量电子邮件。 服务随后将执行配置的操作，例如将邮件发送到收件人的“垃圾邮件”文件夹。 有关更多详细信息，请参阅[批量投诉级别值](bulk-complaint-level-values.md)和[垃圾邮件和批量电子邮件有何不同？](what-s-the-difference-between-junk-email-and-bulk-email.md)。 

4. 在 **“垃圾邮件属性”** 页面上，可通过配置以下各项来设置策略的测试模式选项： 
    
      - **无：** 不对邮件进行任何测试模式操作。 这是默认选项。 
        
      - **添加默认测试 X 标头文本：** 选择此选项会将邮件发送到指定的收件人，但会向邮件添加特殊的 X 标头，用于标识邮件与特定的高级垃圾邮件筛选选项匹配。  
        
      - **将 Bcc 邮件发送至此地址**：选择此选项会将邮件的密件抄送副本发送到你在输入框中指定的电子邮件地址。  <br/><br/>有关高级垃圾邮件筛选选项的详细信息，包括每个选项的说明以及与每个选项相关的 X 标头文本，请参阅[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)。

5. （仅适用于自定义策略）单击 **“应用到”** 菜单项，然后创建基于条件的规则，以指定要应用此策略的用户、组和域。 可以创建多个唯一性条件。 
    
      - 若要选择用户，请选择 **“收件人是”**。 在随后的对话框中，从用户选取器列表中选择一个或多个您公司中的发件人，然后单击 **“添加”**。 若要添加列表中没有的发件人，请键入他们的电子邮件地址，并单击 **“检查姓名”**。 在此框中，还可以使用通配符来表示多个电子邮件地址（例如：\*@ _domainname_）。 完成选择后，单击 **“确定”** 返回主屏幕。 
        
      - 若要选择组，请选择 **“收件人为以下组的成员”**。 然后，在随后出现的对话框中选择或指定组。 单击 **“确定”** 返回到主屏幕。 
        
      - 若要选择域，请选择 **“收件人域为”**。 然后，在随后出现的对话框中添加域。 单击 **“确定”** 返回到主屏幕。 <br/><br/>可以在规则中创建例外。 例如，可以筛选来自除某个域之外的所有域的邮件。 单击 **“添加例外”**，然后创建例外条件，此过程与创建其他条件的方法类似。<br/><br/>只有**启用了邮件的安全组**才支持将垃圾邮件策略应用到组。 
  
6. 单击 **“保存”**。 右侧窗格中将会显示策略设置的摘要。

无法禁用或删除默认策略，并且自定义策略始终优先于默认策略。 对于自定义策略，可以选中或清除 **“启用”** 列中的复选框，以启用或禁用自定义策略。 默认情况下，所有策略处于启用状态。 若要删除自定义策略，请选择该策略，单击 ![删除图标](media/ITPro-EAC-DeleteIcon.gif) **“删除”** 图标，然后确认要删除该策略。

> [!TIP]
> 您可以通过单击 ![向上键图标](media/ITPro-EAC-UpArrowIcon.gif) 向上箭头和 ![向下键图标](media/ITPro-EAC-DownArrowIcon.gif) 向下箭头来更改自定义策略的优先级（运行顺序）。 **“优先级”** 为 **“0”** 的策略将首先开始运行，接下来是 **“1”**，然后是 **“2”**，依此类推。 
  
## <a name="use-remote-powershell-to-configure-spam-filter-policies"></a>使用远程 PowerShell 配置垃圾邮件筛选器策略

您也可以在 PowerShell 中配置和应用垃圾邮件筛选器策略。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection，请参阅[使用 Remote PowerShell 连接到 Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290)。
  
- [Get-HostedContentFilterPolicy](http://technet.microsoft.com/library/d510471a-dda5-4df7-b3f8-2ee7a1948436.aspx) 查看垃圾邮件筛选器设置。 
    
- [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) 编辑垃圾邮件筛选器设置。 
    
- [New-HostedContentFilterPolicy](http://technet.microsoft.com/library/4d15128d-9e16-42a1-8ac5-36f07d4bbbf0.aspx) 创建新的自定义垃圾邮件筛选器策略。 
    
- [Remove-HostedContentFilterPolicy](http://technet.microsoft.com/library/9fe1fe03-8f83-41e3-9bf5-084a392784d6.aspx) 删除自定义垃圾邮件筛选器策略。 
    
若要向用户、组和/或域应用自定义垃圾邮件筛选器策略，请使用 [New-HostedContentFilterRule](http://technet.microsoft.com/library/2df13ba9-1eb0-4da3-bd72-a79d5fa15e26.aspx) cmdlet（创建可应用于自定义策略的新筛选器规则）或 [Set-HostedContentFilterRule](http://technet.microsoft.com/library/ba259260-ffd3-43f3-8ef4-9d8659679d02.aspx) cmdlet（编辑可应用于自定义策略的现有筛选器规则）。使用 [Enable-HostedContentFilterRule](http://technet.microsoft.com/library/354ece28-dcde-4b5f-88ed-475115e7ea78.aspx) cmdlet 或 [Disable-HostedContentFilterRule](http://technet.microsoft.com/library/c1f8dafc-ef5d-47e3-b0fb-71a88e145fc5.aspx) cmdlet 可启用或禁用应用于策略的规则。 
  
## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

为了确保垃圾邮件被正确地检测并处理过，您可以通过服务发送一封 GTUBE 邮件。与 EICAR 杀毒测试文件相似，GTUBE 提供了一个测试，通过此测试可以验证服务是否正在检测传入的垃圾邮件。GTUBE 邮件应该始终被垃圾邮件筛选器检测为垃圾邮件，对邮件执行的操作应该与配置设置相匹配。
  
邮件中包括以下单行 GTUBE 文本，没有任何空格或换行符：
  
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a>优化垃圾邮件筛选器策略，防止误报和漏报

如果想采取更积极的方法进行垃圾邮件筛选，你可以启用高级垃圾邮件筛选技术。 有关适用于整个组织的常规垃圾邮件设置，请参阅[使用安全列表或其他技术防止误报电子邮件被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](reduce-spam-email.md)。 如果您拥有管理员级别控制，并且您想要防止误报或漏报问题，这些内容会很有帮助。

## <a name="allowblock-lists"></a>允许/阻止列表

有时候，筛选器会缺少邮件，或者我们的系统需要花费时间捕获邮件。 在这种情况下，反垃圾邮件策略提供了一个“允许”列表和一个“阻止”列表，可用于推翻现行裁决。 应谨慎使用此选项，因为列表可能变得不可管理，而且由于我们的筛选堆栈应该做它应该做的事情，因此只能暂时使用此选项。

任何客户反垃圾邮件策略中均会配置“允许”和“阻止”列表：

1. 在 **“允许列表”** 部分，你可以指定将始终发送到收件箱的条目，例如发件人或域。 这些条目发送的电子邮件不会被垃圾邮件筛选器处理。 
    
      - 将可信发件人添加到发件人允许列表。 单击 **“编辑”**![添加图标](media/ITPro-EAC-AddIcon.gif) ，然后在选择对话框中添加希望允许的发件人地址。 你可以使用分号或通过换行分隔多个条目。 单击 **“保存”** 返回到 **“允许列表”** 页面。 
        
      - 将可信域添加到域允许列表。 单击 **“编辑”**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后在选择对话框中添加希望允许的域。 你可以使用分号或通过换行分隔多个条目。 单击 **“保存”** 返回到 **“允许列表”** 页面。 

> [!CAUTION]
> 永远不要将接受的域（你拥有的域）或常见域（如 Microsoft.com、office.com 等）列在“允许列表”中。 如果这样做，欺骗者将能轻松地将不受限制的邮件发送到你的组织。

2. 在 **“阻止列表”** 页上，你可以指定将始终标记为垃圾邮件的条目，例如发件人或域。 服务将对匹配这些条目的电子邮件应用配置的高可信度垃圾邮件操作。 
    
      - 将不需要的发件人添加到发件人阻止列表。 单击 **“编辑”**![添加图标](media/ITPro-EAC-AddIcon.gif) ，然后在选择对话框中添加希望阻止的发件人地址。 你可以使用分号或通过换行分隔多个条目。 单击 **“保存”** 返回到 **“阻止列表”** 页面。 
        
      - 将不需要的域添加到“域阻止列表”。 单击 **“编辑”**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后在选择对话框中添加希望阻止的域。 你可以使用分号或通过换行分隔多个条目。 单击 **“保存”** 返回到 **“阻止列表”** 页面。

> [!TIP]
>  在某些情况下，组织可能会不同意服务提供的结论。 在这种情况下, 你可能希望永久保留“允许”或“阻止”列表。 但是，如果你想要将一个域放在“允许”列表中一段时间，则应告知发件人确保其域已通过验证，并将其设置为“DMARC 拒绝”（如果不是）。

## <a name="for-more-information"></a>有关详细信息
<a name="sectionSection6"> </a>

[针对 DMARC 设置域](use-dmarc-to-validate-email.md)
  
[隔离](quarantine.md)
  
[使用安全列表或其他技术避免出现标记为“垃圾邮件”的误报电子邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件以免出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)

[垃圾邮件可信度](spam-confidence-levels.md)
  


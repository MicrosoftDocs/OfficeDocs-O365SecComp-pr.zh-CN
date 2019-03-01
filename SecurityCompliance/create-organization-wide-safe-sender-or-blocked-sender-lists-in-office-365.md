---
title: 在 Office 365 中创建整个组织的安全发件人或阻止发件人名单
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/8/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: 如果您想要确保收到来自特定发件人的邮件, 因为您信任这些邮件及其邮件, 您可以在 Exchange 管理中心的垃圾邮件筛选器策略中调整您的允许列表。
ms.openlocfilehash: 0759d054f270cae03b98d9da7e2e2dcfe442d68f
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341593"
---
# <a name="create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365"></a>在 Office 365 中创建整个组织的安全发件人或阻止发件人名单
  
如果您想要确保收到来自特定发件人的邮件, 因为您信任这些邮件及其邮件, 则可以在 "**保护** \> **垃圾邮件筛选器**" 的 Exchange 管理中心 (EAC) 中的垃圾邮件筛选器策略中调整您的允许列表。有关详细信息, 请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。另一种方法是创建一个 Exchange 邮件流规则 (也称为传输规则), 它的工作方式类似于垃圾邮件筛选器中的域或基于用户的允许列表。您可以按类似方式阻止从特定域或用户发送的邮件。
  
如果需要筛选复杂条件 (如检查邮件头或附件的名称, 或者如果您想要添加复杂操作, 例如将免责声明添加到邮件中或应用 rul 的时间段), 则可以使用邮件流规则在这种情况下很有用。e 为活动状态。但是, 要确保来自特定发件人或域的电子邮件绕过垃圾邮件筛选器的首选方法是将其添加到垃圾邮件筛选器策略中。在 EAC 中, 转到**保护** \> **垃圾邮件筛选器**以开始使用此功能。有关详细信息, 请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。
  
> [!TIP]
> 邮件流规则中基于域的列表不像基于 IP 地址的列表那样安全, 因为域可能是欺骗的。此外, 如果发送 IP 地址在阻止列表中, 它仍将被阻止, 即使已绕过对域或用户的筛选也是如此。这是因为域或用户的邮件流规则不会覆盖全局 IP 阻止列表。我们建议在大多数情况下使用基于 IP 地址的列表。若要创建基于 ip 地址的列表, 可以使用连接筛选器中的 ip 允许列表或 ip 阻止列表。内容筛选器不会检查从这些 IP 地址发送的任何邮件。有关如何通过将 ip 地址添加到 ip 允许列表或 ip 阻止列表来配置连接筛选器策略的说明, 请参阅[configure the connection filter policy](configure-the-connection-filter-policy.md)。 
  
有关与邮件流规则相关的其他管理任务, 请参阅[Exchange Online 中的邮件流规则 (传输规则)](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)。
  
## <a name="use-the-eac-to-customize-a-block-or-allow-list-to-prevent-or-receive-email-from-a-domain-or-user"></a>使用 EAC 自定义阻止或接收来自域或用户的电子邮件的阻止或允许列表

1. 在 EAC 中, 转到 "**保护** \> **垃圾邮件筛选器**"。 
    
2. 在 "**常规**" 页面上, 执行下列操作之一: 
    
  - 双击默认策略或现有策略, 以便开始对其进行编辑。
    
  - 单击 "**新建**" 以创建一个新的自定义垃圾邮件筛选器策略, 该策略可应用于组织中的用户、组和域。 
    
3. 在 "**允许列表**" 页上, 您可以指定将始终传递到收件箱的条目, 如发件人或域。垃圾邮件筛选器不会处理来自这些条目的电子邮件。执行以下操作: 
    
  - 将受信任的发件人添加到发件人允许列表。单击 "**添加**", 然后在选择对话框中添加您希望允许的发件人地址。您可以使用分号或新行分隔多个条目。单击 "确定" 以返回到 "**允许列表**" 页。 
    
  - 将受信任域添加到域允许列表中。单击 "**添加**", 然后在选择对话框中添加您希望允许的域。您可以使用分号或新行分隔多个条目。单击 "确定" 以返回到 "**允许列表**" 页。 
    
    > [!CAUTION]
    > 如果您允许顶级域，很可能会将您不需要的电子邮件发送到收件箱。 
  
4. 在 "**阻止列表**" 页上, 您可以指定将始终被标记为垃圾邮件的条目, 如发件人或域。该服务将对与这些条目匹配的电子邮件应用配置的高可信度垃圾邮件操作。 
    
  - 将不需要的发件人添加到发件人阻止列表。单击 "**添加**!["](media/ITPro-EAC-AddIcon.gif)"添加" 图标, 然后在选择对话框中添加要阻止的发件人地址。您可以使用分号或新行分隔多个条目。单击 **"确定"** 以返回到 "**阻止列表**" 页面。 
    
  - 将不需要的域添加到域阻止列表中。单击 "**添加**!["](media/ITPro-EAC-AddIcon.gif)"添加" 图标, 然后在选择对话框中添加要阻止的域。您可以使用分号或新行分隔多个条目。单击 **"确定"** 以返回到 "**阻止列表**" 页面。 
    
    > [!CAUTION]
    > 如果您阻止顶级域，很可能会将您需要的电子邮件标记为垃圾邮件。 
  
## <a name="what-do-you-need-to-know-before-you-begin-creating-a-mail-flow-rule"></a>开始创建邮件流规则之前, 您需要知道什么？
    
- 您无需创建邮件流规则来绕过垃圾邮件筛选, 或将电子邮件标记为发件人或域的垃圾邮件。如果只想阻止或允许特定的发件人或域而不附加任何额外的条件, 请使用 Exchange Online Protection block 并允许在垃圾邮件策略中的列表 (而不是此邮件流规则)。有关详细信息, 请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。
    
- 您需要先分配权限, 然后才能执行此过程或过程。若要查看所需的权限, 请参阅邮件[策略和合规性权限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的 "邮件流规则" 条目。 
    
- 若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
> [!TIP]
> 遇到问题？在 Exchange 论坛中寻求帮助。请访问[exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、 [exchange online](https://go.microsoft.com/fwlink/p/?linkId=267542)或[exchange online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)中的论坛。 
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-bypass-spam-filtering-for-a-domain-or-user"></a>使用 EAC 创建邮件流规则以绕过域或用户的垃圾邮件筛选

1. 在 EAC 中, 导航到 "**邮件流** \> "**规则**。选择 "**添加** !["](media/ITPro-EAC-AddIcon.gif) "添加" 图标, 然后选择 "**绕过垃圾邮件筛选**"。
    
2. 为规则指定名称。在 "在以下情况**应用此规则**" 下, 选择**发件人**, 然后选择以下条件之一: 
    
  - 如果要指定域, 请选择 "**域是**"。在 "**指定域**" 对话框中, 输入要指定为安全的发件人的域, 如 contoso.com。**将**![添加图标](media/ITPro-EAC-AddIcon.gif)以将其移动到短语列表中。如果要添加其他域, 请重复此步骤, 完成后单击 **"确定"** 。 
    
  - 如果要指定用户, 请选择 "**是此人**"。在 "**选择成员**" 对话框中, 从列表中添加用户或键入用户并单击 "**检查名称**"。如果要添加其他用户, 请重复此步骤, 完成后单击 **"确定"** 。 
    
3. 选中 "**停止处理其他规则**" 复选框, 以确保没有其他规则可以撤消绕过操作 
    
4. 对于 "**邮件中的匹配发件人地址**" 选项, 选择 "**页眉" 或 "信封**"。
    
5. 如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。
    
6. 选择 "**保存**" 以保存该规则。 
    
创建和强制执行规则后，将对您指定的域或用户绕过垃圾邮件筛选。
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-that-blocks-messages-sent-from-a-domain-or-user"></a>使用 EAC 创建邮件流规则, 阻止从某个域或用户发送的邮件

1. 在 EAC 中, 导航到 "**邮件流** \> "**规则**。选择 "**添加** !["](media/ITPro-EAC-AddIcon.gif) "添加" 图标, 然后选择 "**创建新规则**"。
    
2. 为该规则命名, 然后单击 "**更多选项**"。 
    
3. 在 "在以下情况**应用此规则**" 下, 选择**发件人**, 然后选择以下条件之一: 
    
  - 如果要指定域, 请选择 "**域是**"。在 "指定域" 对话框中, 输入要阻止其邮件的发件人域, 例如 contoso.com。单击 "**添加** !["](media/ITPro-EAC-AddIcon.gif)图标将其移动到短语列表。如果要添加其他域, 请重复此步骤, 完成后单击 **"确定"** 。 
    
  - 如果要指定用户, 请选择 "**是此人**"。在 "**选择成员**" 对话框中, 从列表中添加用户或键入用户并单击 "**检查名称**"。如果要添加其他用户, 请重复此步骤, 完成后单击 **"确定"** 。 
    
4. 在 "**执行以下操作**" 下, 选择 "**阻止邮件"** , 然后单击其他选项之一, 如 "**删除邮件, 但不通知任何人**"。
    
5. 单击 "**更多选项**", 然后在 "**邮件中的匹配发件人地址**" 选项中, 选择 "**页眉或信封**"。
    
6. 如果你愿意, 可以选择审核规则、测试规则、在特定时间段内激活规则, 以及进行其他选择。建议在您的组织中实施规则前的一段时间内对其进行测试。
    
7. 选择 "**保存**" 以保存该规则。 
    
创建和强制执行规则后，从您指定的域或用户发送的任何邮件都将被阻止。
  
## <a name="see-also"></a>另请参阅

[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)
  
[使用邮件流规则配置批量电子邮件筛选](use-transport-rules-to-configure-bulk-email-filtering.md)


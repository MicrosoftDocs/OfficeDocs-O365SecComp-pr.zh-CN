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
description: 如果您想要确保您收到邮件来自特定发件人，因为您信任它们和其邮件，则可以调整您允许在 Exchange 管理中心中的垃圾邮件筛选器策略中的列表。
ms.openlocfilehash: a90679fc900ca5695904898af3627fc1900a8545
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003161"
---
# <a name="create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365"></a>在 Office 365 中创建整个组织的安全发件人或阻止发件人名单
  
如果您想要确保您收到邮件来自特定发件人，因为您信任它们和其邮件，则可以调整您允许在**保护**Exchange 管理员中心 (EAC) 中的垃圾邮件筛选器策略中的列表\>**垃圾邮件筛选器**。了解详细信息此在[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。创建 Exchange 传输规则 works 像域或基于用户的垃圾邮件筛选器中允许列表是另一个选项。您可以阻止邮件太发送来自特定域或用户以类似方式。
  
传输规则会很有用在此情况下，如果您需要筛选的复杂的条件，如检查邮件头或附件的名称或您要添加复杂操作，如向邮件添加免责声明或应用时间段其中 rule 处于活动状态。但是，确保来自特定发件人或域的电子邮件绕过垃圾邮件筛选器的首选的方法是将它们添加到您的垃圾邮件筛选器策略。开始与此在 EAC 中，转到**保护** \> **垃圾邮件筛选器**。有关详细信息[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。
  
> [!TIP]
> 基于域的列表中的传输规则不是一个 IP 地址基于列表，尽可能安全，因为可以造假域。此外，如果在阻止列表发送 IP 地址，它仍被阻止即使筛选为域或用户绕过了。这是因为传输规则在域或用户不会覆盖全局 IP 阻止列表。我们建议在大多数情况下使用的 IP 地址基于列表。若要创建的 IP 地址基于列表，可以在连接筛选器中使用的 IP 允许列表或 IP 阻止列表。从这些 IP 地址发送的任何邮件不会检查内容筛选器。有关如何通过将 IP 地址添加到 IP 允许列表或 IP 阻止列表配置连接筛选器策略的说明，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。 
  
有关与传输规则相关的其他管理任务，请参阅[Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)。
  
## <a name="use-the-eac-to-customize-a-block-or-allow-list-to-prevent-or-receive-email-from-a-domain-or-user"></a>使用 EAC 以自定义阻止或允许列表来阻止或从域或用户接收电子邮件

1. 在 EAC 中，转到**保护** \> **垃圾邮件筛选器**。 
    
2. 在**常规**页上，执行以下任一操作： 
    
  - 双击默认策略或现有的策略以便开始编辑它。
    
  - 单击**新建**以创建新的自定义垃圾邮件筛选器策略可应用于用户、 组和您的组织中的域。 
    
3. 在**允许列表**页上，您可以指定项，如发件人或域时，总是会发送到收件箱。垃圾邮件筛选器不处理电子邮件从这些条目。执行以下操作： 
    
  - 添加受信任的发件人与发件人允许列表。单击**添加**，然后在选择对话框中，添加您希望允许的发件人地址。您可以单独使用分号或新行的多个条目。单击确定以返回到**允许列表**页。 
    
  - 添加受信任的域到域的允许列表。单击**添加**，然后在选择对话框中，添加您希望允许的域。您可以单独使用分号或新行的多个条目。单击确定以返回到**允许列表**页。 
    
    > [!CAUTION]
    > 如果您允许顶级域，很可能会将您不需要的电子邮件发送到收件箱。 
  
4. 在**阻止列表**页上，您可以指定项，如发件人或域时，将始终标记为垃圾邮件。该服务将这些条目匹配的电子邮件上应用配置高可信度垃圾邮件操作。 
    
  - 将不需要的发件人添加到阻止发件人列表中。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后在选择对话框中，添加您想要阻止的发件人地址。您可以单独使用分号或新行的多个条目。单击**确定**以返回到**阻止列表**页上。 
    
  - 将不需要的域添加到阻止域列表中。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后在选择对话框中，添加您想要阻止的域。您可以单独使用分号或新行的多个条目。单击**确定**以返回到**阻止列表**页上。 
    
    > [!CAUTION]
    > 如果您阻止顶级域，很可能会将您需要的电子邮件标记为垃圾邮件。 
  
## <a name="what-do-you-need-to-know-before-you-begin-creating-a-transport-rule"></a>您需要知道您开始创建传输规则？
    
- 您无需创建传输规则以绕过垃圾邮件筛选或将电子邮件标记为垃圾邮件的发件人或域。使用 Exchange Online Protection 块，并允许列表中而不是此传输规则的垃圾邮件策略，如果您只想要阻止或允许特定发件人或域并不附加任何额外的条件。了解详细信息此在[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。
    
- 您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的"传输规则"条目。 
    
- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
> [!TIP]
> 有问题？寻求帮助 Exchange 论坛。访问在[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、 [Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛。 
  
## <a name="use-the-eac-to-create-a-transport-rule-to-bypass-spam-filtering-for-a-domain-or-user"></a>使用 EAC 创建传输规则以绕过域或用户的垃圾邮件筛选

1. 在 EAC 中，导航到**邮件流** \> **规则**。选择**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后选择**绕过垃圾邮件筛选**。
    
2. 为该规则指定一个名称。在**以下情况应用此规则**，选择**发件人**，然后选择以下条件之一: 
    
  - 如果您想要指定域，则选择**域**。在**指定域**对话框中，输入您想要指定为安全，例如，contoso.com 的发件人的域。**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)以将其移到的短语列表。如果您想要添加其他域，并在完成时单击**确定**，请重复此步骤。 
    
  - 如果您想要指定用户，选择**此人**。在**选择成员**对话框中，从列表中添加用户或键入用户并单击**检查名称**。如果您想要添加其他用户，并在完成时单击**确定**，请重复此步骤。 
    
3. 选择**停止处理其他规则**复选框以确保没有其他规则可以还原绕过操作 
    
4. 对于**邮件中的匹配发件人地址**选项中，选择**标头或信封**。
    
5. 如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。建议在组织中实施规则之前，对规则测试一段时间。有关这些选择的详细信息，请参阅[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)。
    
6. 选择**保存**保存规则。 
    
创建和强制执行规则后，将对您指定的域或用户绕过垃圾邮件筛选。
  
## <a name="use-the-eac-to-create-a-transport-rule-that-blocks-messages-sent-from-a-domain-or-user"></a>使用 EAC 创建传输规则阻止从某个域或用户发送的邮件

1. 在 EAC 中，导航到**邮件流** \> **规则**。选择**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后选择**创建新规则**。
    
2. 为该规则指定一个名称，然后单击**更多选项**。 
    
3. 在**以下情况应用此规则**，选择**发件人**，然后选择以下条件之一: 
    
  - 如果您想要指定域，则选择**域**。在指定域对话框中，输入想要阻止邮件，例如 contoso.com 的发件人域。单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)以将其移到的短语列表。如果您想要添加其他域，并在完成时单击**确定**，请重复此步骤。 
    
  - 如果您想要指定用户，选择**此人**。在**选择成员**对话框中，从列表中添加用户或键入用户并单击**检查名称**。如果您想要添加其他用户，并在完成时单击**确定**，请重复此步骤。 
    
4. 下**执行以下操作**，选择**阻止邮件**，然后单击一个如**删除不通知任何人的邮件**的其他选项。
    
5. 单击**更多选项**，然后对于**邮件中的匹配发件人地址**选项中，选择**标头或信封**。
    
6. 如果需要，您可以进行选择，在特定时间内审核规则、测试规则及激活规则，或者选择进行其他操作。建议在组织中实施规则之前，对规则测试一段时间。有关这些选择的详细信息，请参阅[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)。
    
7. 选择**保存**保存规则。 
    
创建和强制执行规则后，从您指定的域或用户发送的任何邮件都将被阻止。
  
## <a name="see-also"></a>另请参阅

[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)
  
[使用传输规则来配置批量电子邮件筛选](use-transport-rules-to-configure-bulk-email-filtering.md)


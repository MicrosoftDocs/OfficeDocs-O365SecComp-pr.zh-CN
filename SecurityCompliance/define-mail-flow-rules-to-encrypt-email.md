---
title: 定义邮件流规则来加密 Office 365 中的电子邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: 作为 Office 365 全局管理员，您可以创建邮件流规则启用 Office 365 邮件加密 (OME)。可以对任何传出电子邮件进行加密，并从内部邮件或从组织发出的加密邮件答复中删除加密。
ms.openlocfilehash: e9c6874ce304d1af9da093c02cbc954c54dae8cc
ms.sourcegitcommit: c05076501dfe118e575998ecfc08ad69d13c8abc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25853087"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a>定义邮件流规则来加密 Office 365 中的电子邮件

作为 Office 365 全局管理员，您可以创建邮件流规则，也称为传输规则，来帮助保护发送和接收的电子邮件。您可以设置来加密任何传出电子邮件和加密的邮件来自您组织内从或从组织发出的加密邮件答复中删除加密的规则。您可以使用 Exchange 管理中心 (EAC) 或 Exchange Online 的 Windows PowerShell cmdlet 创建这些规则。 除了整体加密规则，您可以启用或禁用最终用户的单个邮件加密选项。
  
如果您最近迁移从 AD RMS 到 Azure 信息保护，您将需要查看您现有的邮件流规则，以确保它们继续在新环境中工作。此外，如果您想要通过 Azure 信息保护给您充分利用可用的新 Office 365 邮件加密 (OME) 功能，您需要更新现有的邮件流规则。否则，您的用户将继续接收加密电子邮件，而不是新的、 无缝 OME 体验使用以前的 HTML 附件格式。如果您尚未尚未设置 OME，信息，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。 
  
有关组件构成邮件流规则和如何邮件流规则工作的信息，请参阅[Exchange Online 中的邮件流规则 （传输规则）](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)。有关邮件流规则与 Azure 信息保护的工作方式的其他信息，请参阅[Azure 信息保护标签配置 Exchange Online 邮件流规则](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。
  
## <a name="hybrid-exchange-environments-do-this-first"></a>Exchange 的混合环境： 第一步
内部部署用户可以发送加密的邮件使用 OME，如果您将通过 Exchange Online 电子邮件路由。若要执行此操作，您需要配置邮件流到流从电子邮件服务器到 Office 365。配置邮件流过 Office 365 后，您可以使用本文为 OME 进行邮件流规则。

有关说明，请参阅[设置连接器路由 Office 365 和电子邮件服务器之间的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)。具体而言，完成中的步骤"第 2 部分： 配置邮件流从电子邮件服务器到 Office 365"。

## <a name="create-a-mail-flow-rule-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>创建新 OME 功能的电子邮件加密的邮件流规则

您可以定义使用 EAC 触发新 OME 功能的邮件加密的邮件流规则。
  
### <a name="to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities-by-using-the-eac"></a>若要创建新的 OME 功能的电子邮件加密使用 EAC 的规则

1. 在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。
    
2. 选择**管理员**图块。 
    
3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。
    
4. 在 EAC 中，转到**邮件流** \> **规则** \> ![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)（**新**） \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)。
    
5. 在**名称**框中，键入规则名称，如 Encrypt mail for DrToniRamos@hotmail.com。
    
6. 在**以下情况应用此规则**中选择一个条件，并输入一个值，如有必要。例如，若要加密邮件转到 DrToniRamos@hotmail.com: 
    
    1. 在**以下情况应用此规则**，请选择**收件人**。
    
    2. 从联系人列表中选择一个现有名称，或在**检查名称**框中键入新的电子邮件地址。 
    
        要选择一个现有名称，从列表中选择，然后单击**确定**。
    
        若要输入新名称，在**检查名称**框中键入电子邮件地址，然后选择**检查名称** \> **确定**。
    
7. 若要添加更多条件，选择**更多选项**然后选择**添加条件**并从列表中选择。 
    
    例如，仅当收件人位于组织外部，则应用规则，选择**添加条件**，然后选择**收件人是内部/外部** \> **组织外部** \> **确定**。
    
8. 若要使用的新的 OME 功能，**执行以下操作**，从加密选择**修改邮件安全性**，然后选择**应用 Office 365 邮件加密和权限保护**。从列表中选择的 RMS 模板，选择**保存**，然后选择**确定**。
    
    模板的列表包含所有的默认模板和选项，以及您已创建的任何自定义模板使用 Office 365。如果列表为空，确保您已设置 Office 365 邮件加密的新功能与[设置新的 Office 365 邮件加密功能基于顶部 Azure 信息保护](set-up-new-message-encryption-capabilities.md)中所述。有关默认模板的信息，请参阅[配置和管理 Azure 信息保护模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关**不要转发**选项的信息，请参阅[不要转发的电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。有关**仅加密**选项的信息，请参阅[仅加密的电子邮件的选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。
    
    如果您希望指定另一项操作，可以选择**添加操作**。 
    
### <a name="to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities-by-using-the-eac"></a>更新现有邮件流规则使用 EAC 使用新的 OME 功能

1. 在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。
    
2. 选择**管理员**图块。 
    
3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。
    
4. 在 EAC 中，转到**邮件流** \> **规则**。
    
5. 在邮件流规则列表中，选择您想要修改以使用新的 OME 功能，然后选择的规则![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)（**编辑**）。
    
6. 若要使用的新的 OME 功能，**执行以下操作**，从加密选择**修改邮件安全性**，然后选择**应用 Office 365 邮件加密和权限保护**。从列表中选择的 RMS 模板选择**保存**，然后选择**确定**。
    
    模板的列表包含所有的默认模板和选项，以及您已创建的任何自定义模板使用 Office 365。如果列表为空，确保您已设置 Office 365 邮件加密的新功能与[设置新的 Office 365 邮件加密功能基于顶部 Azure 信息保护](set-up-new-message-encryption-capabilities.md)中所述。有关默认模板的信息，请参阅[配置和管理 Azure 信息保护模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关**不要转发**选项的信息，请参阅[不要转发的电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。有关**仅加密**选项的信息，请参阅[仅加密的电子邮件的选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。
    
    如果您希望指定另一项操作，可以选择**添加操作**。 
    
7. 从**执行以下操作**列表中，删除分配给**修改邮件安全性**的任何操作\>**应用 OME 的早期版本**。
    
8. 选择" **保存**"。
    
## <a name="creating-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>为 Office 365 邮件加密创建规则，不带新功能

如果尚未没有移 Office 365 组织的新 OME 功能，可以使用这些任务定义为您的组织的邮件进行加密的邮件流规则。Microsoft 建议您进行规划，以将移动到新的 OME 功能只要很合理为您的组织。有关说明，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。
  
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-the-eac"></a>创建加密电子邮件的新功能，OME 不使用 EAC 的规则

1. 在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。
    
2. 选择**管理员**图块。 
    
3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。
    
4. 在 EAC 中，转到**邮件流** \> **规则** \> **+** （**新**） \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)。
    
5. 在**名称**框中，键入规则名称，如 Encrypt mail for DrToniRamos@hotmail.com。
    
6. 在**以下情况应用此规则**中选择一个条件，并输入一个值，如有必要。例如，若要加密邮件转到 DrToniRamos@hotmail.com: 
    
1. 在**以下情况应用此规则**，请选择**收件人**。
    
2. 从联系人列表中选择一个现有名称，或在**检查名称**框中键入新的电子邮件地址。 
    
    要选择一个现有名称，从列表中选择，然后单击**确定**。
    
    若要输入新名称，在**检查名称**框中键入电子邮件地址，然后选择**检查名称** \> **确定**。
    
7. 若要添加更多条件，选择**更多选项**，然后选择**添加条件**，从列表中选择。 
    
    例如，仅当收件人位于组织外部，则应用规则，选择**添加条件**，然后选择**收件人是内部/外部** \> **组织外部** \> **确定**。
    
8. 要加密在不使用新的 OME 功能中，**执行以下操作**，请选中**修改邮件安全性** \> **应用 OME 的早期版本**，然后选择**保存**。
    
    如果您收到一条错误，未启用 IRM 许可，然后尚未设置您的组织尚未 OME。如果您想要设置 OME 现在，您必须设置它以使用新的 OME 功能。有关信息，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。Microsoft 不再支持设置新部署的 OME 没有的新功能。
    
    如果您希望指定另一项操作，可以选择**添加操作**。 
    
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a>若要创建使用 Windows PowerShell 进行 Exchange Online 加密不带新 OME 功能的电子邮件的规则

1. 在本地计算机上使用 Windows PowerShell 创建与 Exchange Online 的远程 PowerShell 会话。有关详细信息，请参阅[Connect to Exchange Online PowerShell 中](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。
    
2. 使用**New-transportrule** cmdlet 定义规则，并将**ApplyOME**属性设置为**true**。
    
    例如，若要求必须加密往 DrToniRamos@hotmail.com 的所有电子邮件，请键入：
    
     ```
     New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
     ```

    在此示例中：
    
  - 新规则的名称为"灾难恢复 Toni Ramos 加密规则"。
    
  - **-SentTo**参数指定的收件人电子邮件中查找的条件。您可以使用任何值，该值唯一地标识收件人，如电子邮件地址、 名称、 可分辨的名称 (DN)、 等。本示例中，收件人的电子邮件地址"DrToniRamos@hotmail.com"由标识。 
    
  - **-SentToScope**参数指定收件人的位置查找的条件。本示例中，收件人的邮箱位于 hotmail 并不是 Office 365 组织的一部分，以便使用"NotInOrganization"值。 
    
    您可以设置使用此 cmdlet 的邮件流规则条件的详细信息，请参阅[New-transportrule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)。
    
### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>从新 OME 功能不加密的电子邮件答复中删除加密

当您的电子邮件用户发送加密的邮件时，可以使用加密的答复响应这些邮件的收件人。您可以创建邮件流规则自动删除从答复加密，所以您的组织中的电子邮件用户不需要登录到加密门户以查看它们。您可以使用 EAC 或 Windows PowerShell cmdlet 定义这些规则。如果您没有尚未使用的新 OME 功能，您可以仅解密之一从组织或组织内从发送邮件的答复邮件中发送的邮件。无法解密来自组织外部的加密的邮件。
  
#### <a name="to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-the-eac"></a>若要创建从新 OME 功能不使用 EAC 加密的电子邮件答复中删除加密的规则
<a name="DecryptruleEACNoNewOME"> </a>

1. 在 web 浏览器中，使用工作或学校帐户已被授予管理员权限，[登录到 Office 365](https://support.office.com/article/Sign-in-to-Office-or-Office-365-b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。
    
2. 选择**管理员**图块。 
    
3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。
    
4. 在 EAC 中，转到**邮件流** \> **规则** \> **+** （**新**） \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange Admin Center in Exchange Online](https://technet.microsoft.com/en-us/library/jj200743%28v=exchg.150%29.aspx)。
    
5. 在**名称**框中，键入该规则，如 Remove encryption from 传入邮件的名称。
    
6. 在**以下情况应用此规则**选择应从邮件，如**收件人是位于**中删除加密的条件\>**组织内部**。
    
7. 在**执行以下操作**，选择**修改邮件安全性** \> **OME 的早期版本中删除**。
    
8. 选择" **保存** "。
    
#### <a name="to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a>若要创建从 Exchange online 中使用 Windows PowerShell 的新功能，OME 不加密的电子邮件答复中删除加密的规则
<a name="DecryptrulePShellNoNewOME"> </a>

1. 在本地计算机上使用 Windows PowerShell 创建与 Exchange Online 的远程 PowerShell 会话。有关详细信息，请参阅[Connect to Exchange Online PowerShell 中](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。
    
2. 使用**New-transportrule** cmdlet 定义规则，并将**RemoveOME**属性设置为**true**。
    
    例如，若要从所有发送到 Office 365 组织中的收件人的邮件中删除加密，请键入：
    
     ```
     New-TransportRule - Name "Remove encryption from incoming mail"     -SentToScope "InOrganization" -RemoveOME $true
     ```

    在此示例中：
    
  - 新规则的名称为"Remove encryption from incoming mail"。
    
  - **-SentToScope**参数指定收件人的位置查找的条件。本示例中，使用"InOrganization"值指示： 
    
  - 收件人是邮箱、 邮件用户、 组或组织中已启用邮件的公用文件夹或
    
  - 收件人的电子邮件地址位于配置为权威域或内部中继域的接受的域中， 并且 通过经验证的连接发送或接收邮件。
    
    您可以设置使用此 cmdlet 的邮件流规则条件的详细信息，请参阅[New-transportrule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)。
    
## <a name="related-topics"></a>相关主题

[Office 365 中的加密](encryption.md)
  
[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护顶部](set-up-new-message-encryption-capabilities.md)
  
[将品牌添加到加密邮件](add-your-organization-brand-to-encrypted-messages.md)
  
[Exchange Online 中的邮件流规则（传输规则）](https://go.microsoft.com/fwlink/p/?LinkId=506707)
  
[Exchange Online Protection 中的邮件流规则（传输规则）](https://go.microsoft.com/fwlink/p/?LinkId=506708)
  


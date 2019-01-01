---
title: 定义用于加密 Office 365 中的电子邮件的邮件流规则
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: 管理员可以了解到创建邮件流规则 （也称作传输规则） 进行加密和解密邮件使用 Office 365 邮件加密 (OME)。
ms.openlocfilehash: 6633958478c947d765251145ecd6d45e34dea2ab
ms.sourcegitcommit: 31098b35607d0fd949fd357f783d1e9ed2444deb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2018
ms.locfileid: "27466921"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a>定义用于加密 Office 365 中的电子邮件的邮件流规则

作为 Office 365 全局管理员，您可以创建邮件流规则 （也称作传输规则） 来帮助保护发送和接收的电子邮件。您可以设置来加密任何传出电子邮件和加密的邮件来自您组织内从或从组织发出的加密邮件答复中删除加密的规则。您可以使用 Exchange 管理中心 (EAC) 或 Exchange Online PowerShell 中创建这些规则。除了整体加密规则，您可以启用或禁用最终用户的单个邮件加密选项。

如果您最近迁移从 AD RMS 到 Azure 信息保护，您将需要查看您现有的邮件流规则，以确保它们继续在新环境中工作。此外，如果您想要通过 Azure 信息保护给您充分利用可用的新 Office 365 邮件加密 (OME) 功能，您需要更新现有的邮件流规则。否则，您的用户将继续接收加密电子邮件，而不是新的、 无缝 OME 体验使用以前的 HTML 附件格式。如果您尚未尚未设置 OME，信息，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。

有关组件构成邮件流规则和如何邮件流规则工作的信息，请参阅[Exchange Online 中的邮件流规则 （传输规则）](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。有关邮件流规则与 Azure 信息保护的工作方式的其他信息，请参阅[Azure 信息保护标签配置 Exchange Online 邮件流规则](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。

> [!IMPORTANT]
> 对于 Exchange 的混合环境，内部部署用户可以发送电子邮件路由通过 Exchange Online 时，才使用 OME 的加密的邮件。若要配置 OME 混合 Exchange 环境中，您需要[配置混合使用混合配置向导](https://docs.microsoft.com/Exchange/exchange-hybrid)的第一个，然后[配置邮件流从电子邮件服务器到 Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。一次已配置邮件流过 Office 365，然后您也可以通过使用本指南为 OME 配置邮件流规则。

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>创建邮件流规则进行加密的新功能，OME 与电子邮件

您可以定义使用 EAC 触发新 OME 功能的邮件加密的邮件流规则。

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>使用 EAC 创建加密电子邮件与新的 OME 功能的规则

1. 在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择**管理员**图块。

3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。

4. 在 EAC 中，转到**邮件流** \> **规则**和选择**新建**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在**名称**框中，键入规则名称，如 Encrypt mail for DrToniRamos@hotmail.com。

6. 在**以下情况应用此规则**中选择一个条件，并输入一个值，如有必要。例如，若要加密邮件转到 DrToniRamos@hotmail.com:

   1. 在**以下情况应用此规则**，请选择**收件人**。

   2. 从联系人列表中选择一个现有名称，或在**检查名称**框中键入新的电子邮件地址。
    
      - 要选择一个现有名称，从列表中选择，然后单击**确定**。

      - 若要输入新名称，在**检查名称**框中键入电子邮件地址，然后选择**检查名称** \> **确定**。

7. 若要添加更多条件，选择**更多选项**然后选择**添加条件**并从列表中选择。

   例如，仅当收件人位于组织外部，则应用规则，选择**添加条件**，然后选择**收件人是内部/外部** \> **组织外部** \> **确定**。

8. 若要使用的新的 OME 功能，**执行以下操作**，从加密选择**修改邮件安全性**，然后选择**应用 Office 365 邮件加密和权限保护**。从列表中选择的 RMS 模板，选择**保存**，然后选择**确定**。

   模板的列表包含所有的默认模板和选项，以及您已创建的任何自定义模板使用 Office 365。如果列表为空，确保您已设置 Office 365 邮件加密的新功能与[设置新的 Office 365 邮件加密功能基于顶部 Azure 信息保护](set-up-new-message-encryption-capabilities.md)中所述。有关默认模板的信息，请参阅[配置和管理 Azure 信息保护模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关**不要转发**选项的信息，请参阅[不要转发的电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。有关**仅加密**选项的信息，请参阅[仅加密的电子邮件的选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   如果您希望指定另一项操作，可以选择**添加操作**。

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>使用 EAC 来更新现有的邮件流规则，以使用新的 OME 功能

1. 在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择**管理员**图块。

3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。

4. 在 EAC 中，转到**邮件流** \> **规则**。

5. 在邮件流规则列表中，选择您想要修改以使用新的 OME 功能，然后选择**编辑**的规则![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。

6. 若要使用的新的 OME 功能，**执行以下操作**，从加密选择**修改邮件安全性**，然后选择**应用 Office 365 邮件加密和权限保护**。从列表中选择的 RMS 模板选择**保存**，然后选择**确定**。

   模板的列表包含所有的默认模板和选项，以及您已创建的任何自定义模板使用 Office 365。如果列表为空，确保您已设置 Office 365 邮件加密的新功能与[设置新的 Office 365 邮件加密功能基于顶部 Azure 信息保护](set-up-new-message-encryption-capabilities.md)中所述。有关默认模板的信息，请参阅[配置和管理 Azure 信息保护模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关**不要转发**选项的信息，请参阅[不要转发的电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。有关**仅加密**选项的信息，请参阅[仅加密的电子邮件的选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   如果您希望指定另一项操作，可以选择**添加操作**。

7. 从**执行以下操作**列表中，删除分配给**修改邮件安全性**的任何操作\>**应用 OME 的早期版本**。

8. 选择" **保存**"。

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>创建邮件流规则为 Office 365 邮件加密没有的新功能

如果尚未没有移 Office 365 组织的新 OME 功能，可以使用这些任务定义为您的组织的邮件进行加密的邮件流规则。Microsoft 建议您进行规划，以将移动到新的 OME 功能只要很合理为您的组织。有关说明，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>使用 EAC 创建加密电子邮件不带新 OME 功能的邮件流规则

1. 在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择**管理员**图块。

3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。

4. 在 EAC 中，转到**邮件流** \> **规则**和选择**新建**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange admin center 在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在**名称**框中，键入规则名称，如 Encrypt mail for DrToniRamos@hotmail.com。

6. 在**以下情况应用此规则**中选择一个条件，并输入一个值，如有必要。例如，若要加密邮件转到 DrToniRamos@hotmail.com: 

   1. 在**以下情况应用此规则**，请选择**收件人**。

   2. 从联系人列表中选择一个现有名称，或在**检查名称**框中键入新的电子邮件地址。

      - 要选择一个现有名称，从列表中选择，然后单击**确定**。

      - 若要输入新名称，在**检查名称**框中键入电子邮件地址，然后选择**检查名称** \> **确定**。

7. 若要添加更多条件，选择**更多选项**，然后选择**添加条件**，从列表中选择。

   例如，仅当收件人位于组织外部，则应用规则，选择**添加条件**，然后选择**收件人是内部/外部** \> **组织外部** \> **确定**。

  8. 要加密在不使用新的 OME 功能中，**执行以下操作**，请选中**修改邮件安全性** \> **应用 OME 的早期版本**，然后选择**保存**。

    如果您收到一条错误，未启用 IRM 许可，然后尚未设置您的组织尚未 OME。如果您想要设置 OME 现在，您必须设置它以使用新的 OME 功能。有关信息，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。Microsoft 不再支持设置新部署的 OME 没有的新功能。

    如果您希望指定另一项操作，可以选择**添加操作**。

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Exchange Online PowerShell 中用于创建加密电子邮件不带新 OME 功能的邮件流规则

1. 连接到 Exchange Online PowerShell 中。有关详细信息，请参阅[Connect to Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

2. 使用**New-transportrule** cmdlet 创建规则，并将_ApplyOME_参数设置为`$true`。

   此示例要求对所有电子邮件发送到 DrToniRamos@hotmail.com 必须进行都加密。

   ```
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   **注意**：

   - 新规则的唯一名称是"灾难恢复 Toni Ramos 加密规则"。

   - _SentTo_参数指定邮件的收件人 （由名称、 电子邮件地址、 可分辨的名称等标识。）。本示例中，收件人的电子邮件地址"DrToniRamos@hotmail.com"由标识。

   - _SentToScope_参数指定的收件人的位置。本示例中，收件人的邮箱是 hotmail 中而不是 Office 365 组织的一部分，以便值`NotInOrganization`使用。

   有关详细的语法和参数信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)。

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>从新 OME 功能不加密的电子邮件答复中删除加密

当您的电子邮件用户发送加密的邮件时，可以使用加密的答复响应这些邮件的收件人。您可以创建邮件流规则自动删除从答复加密，所以您的组织中的电子邮件用户不需要登录到加密门户以查看它们。您可以使用 EAC 或 Windows PowerShell cmdlet 定义这些规则。如果您没有尚未使用的新 OME 功能，您可以仅解密之一从组织或组织内从发送邮件的答复邮件中发送的邮件。无法解密来自组织外部的加密的邮件。

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>使用 EAC 创建从新 OME 功能不加密的电子邮件答复中删除加密的规则

1. 在 web 浏览器中，使用工作或学校帐户已被授予管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择**管理员**图块。

3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。

4. 在 EAC 中，转到**邮件流** \> **规则**和选择**新建**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange admin center 在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在**名称**框中，键入该规则，如 Remove encryption from 传入邮件的名称。

6. 在**以下情况应用此规则**选择应从邮件，如**收件人是位于**中删除加密的条件\>**组织内部**。

7. 在**执行以下操作**，选择**修改邮件安全性** \> **OME 的早期版本中删除**。

8. 选择" **保存** "。

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Exchange Online PowerShell 中用于创建从新 OME 功能不加密的电子邮件答复中删除加密的规则

1. 连接到 Exchange Online PowerShell 中。有关详细信息，请参阅[Connect to Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

2. 使用**New-transportrule** cmdlet 创建规则，并将_RemoveOME_参数设置为`$true`。

   此示例从所有发送到 Office 365 组织中的收件人的邮件中删除加密。

   ```
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   **注意**：

   - 新规则的唯一名称为"Remove encryption from incoming mail"。

   - _SentToScope_参数指定的收件人的位置。在此示例中，值`InOrganization`使用了值，表示： 

     - 收件人的邮箱、 邮件用户、 组或组织中已启用邮件的公用文件夹。

       或

     - 收件人的电子邮件地址位于配置为权威域或中您的组织，_和_邮件已发送或接收通过经过身份验证连接的内部中继域的接受域。

有关详细的语法和参数信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)。

## <a name="related-topics"></a>相关主题

[Office 365 中的加密](encryption.md)

[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护顶部](set-up-new-message-encryption-capabilities.md)

[将品牌添加到加密邮件](add-your-organization-brand-to-encrypted-messages.md)

[Exchange Online 中的邮件流规则（传输规则）](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Exchange Online Protection 中的邮件流规则（传输规则）](https://go.microsoft.com/fwlink/p/?LinkId=506708)

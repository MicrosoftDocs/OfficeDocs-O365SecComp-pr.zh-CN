---
title: 定义用于加密 Office 365 中的电子邮件的邮件流规则
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: 管理员可以学习使用 Office 365 邮件加密来创建邮件流规则 (传输规则), 以对邮件进行加密和解密。
ms.openlocfilehash: 1f5b0ff9be5994f036d2367d0b15744c24f2bbe0
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357553"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a>定义用于加密 Office 365 中的电子邮件的邮件流规则

作为 Office 365 全局管理员, 您可以创建邮件流规则 (也称为传输规则), 以帮助保护您发送和接收的电子邮件。您可以设置规则来加密任何传出的电子邮件, 并删除来自组织内部或从组织发送的加密邮件的答复的加密邮件的加密。您可以使用 exchange 管理中心 (EAC) 或 exchange Online PowerShell 创建这些规则。除了整体加密规则之外, 您还可以选择为最终用户启用或禁用单个邮件加密选项。

||
|:-----|
|本文是有关 Office 365 邮件加密的更多系列文章的一部分。本文适用于管理员和 ITPros。如果只是查找有关发送或接收加密邮件的信息, 请参阅[Office 365 邮件加密 (OME)](ome.md)中的文章列表, 并找到最符合您的需求的文章。 |
||

如果你最近从 AD RMS 迁移到 Azure 信息保护, 你将需要查看现有的邮件流规则, 以确保它们可以在你的新环境中继续工作。此外, 如果您想利用新的 Office 365 邮件加密 (OME) 功能通过 Azure 信息保护来使用, 则需要更新现有的邮件流规则。否则, 您的用户将继续接收使用以前的 HTML 附件格式的加密邮件, 而不是新的无缝 OME 体验。如果尚未设置 OME, 请参阅为信息[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

有关组成邮件流规则的组件和邮件流规则的工作方式的信息, 请参阅[Exchange Online 中的邮件流规则 (传输规则)](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。有关邮件流规则如何使用 azure 信息保护的其他信息, 请参阅[为 azure 信息保护标签配置 Exchange Online 邮件流规则](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。

> [!IMPORTANT]
> 对于混合 Exchange 环境, 只有在通过 Exchange Online 路由电子邮件的情况下, 本地用户才能使用 OME 发送加密邮件。若要在混合 Exchange 环境中配置 OME, 需要先[使用 "混合配置" 向导配置混合](https://docs.microsoft.com/Exchange/exchange-hybrid), 然后[将邮件配置为从您的电子邮件服务器传递到 Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。将邮件配置为通过 Office 365 传输之后, 可以使用本指南配置 OME 的邮件流规则。

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>创建邮件流规则, 以使用新的 OME 功能对电子邮件进行加密

您可以使用 EAC 定义邮件流规则, 以使用新的 OME 功能触发邮件加密。

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>使用 EAC 创建使用新的 OME 功能对电子邮件进行加密的规则

1. 在 web 浏览器中, 使用已被授予全局管理员权限的工作或学校帐户,[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择 "**管理**" 磁贴。

3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。

4. 在 EAC 中, 转到 "**邮件流** \> **规则**", 然后选择 "**新建** ![" 图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。有关使用 EAC 的详细信息, 请参阅 exchange [Online 中的 exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 "**名称**" 中, 键入规则的名称, 例如 "为 DrToniRamos@hotmail.com 加密邮件"。

6. 在 "在**以下情况应用此规则**" 中选择一个条件, 并根据需要输入一个值。例如, 若要加密发往 DrToniRamos@hotmail.com 的邮件, 请执行以下操作:

   1. 在 "在**以下情况应用此规则**" 中, 选择 **"收件人是"**。

   2. 从联系人列表中选择一个现有名称, 或在 "**检查名称**" 框中键入新的电子邮件地址。

      - 若要选择现有名称, 请从列表中选择该名称, 然后单击 **"确定"**。

      - 若要输入新名称, 请在 "**检查名称**" 框中键入电子邮件地址, 然后选择 "**检查名称** \> **" "确定"**。

7. 若要添加更多条件, 请选择 "**更多选项**", 然后选择 "**添加条件**", 然后从列表中选择。

   例如, 若要仅在收件人在组织外部时应用规则, 请选择 "**添加条件**", 然后选择 "在**组织** \>外部 **/内部的收件人是外部/内部** \> **"**。

8. 若要使用新的 OME 功能启用加密, 请从**执行以下操作**, 选择 "**修改邮件安全性"** , 然后选择 "**应用 Office 365 邮件加密和权限保护**"。从列表中选择一个 RMS 模板, 选择 "**保存**", 然后选择 **"确定"**。
  
  模板列表包含所有默认模板和选项, 以及您创建的用于 Office 365 的任何自定义模板。如果列表为空, 请确保已使用新功能设置了 Office 365 邮件加密, 如[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)中所述。有关默认模板的信息, 请参阅[配置和管理 Azure 信息保护的模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关 "**不要转发**" 选项的信息, 请参阅[电子邮件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)的 "不要转发" 选项。有关**仅加密**选项的信息, 请参阅[仅加密电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

  如果要指定另一个操作, 可以选择 "**添加操作**"。

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>使用 EAC 更新现有的邮件流规则, 以使用新的 OME 功能

1. 在 web 浏览器中, 使用已被授予全局管理员权限的工作或学校帐户,[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择 "**管理**" 磁贴。

3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。

4. 在 EAC 中, 转到 "**邮件流** \> **规则**"。

5. 在邮件流规则的列表中, 选择要修改的规则以使用新的 OME 功能, 然后选择 "**编辑** ![" "编辑](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)" 图标。

6. 若要使用新的 OME 功能启用加密, 请从**执行以下操作**, 选择 "**修改邮件安全性"** , 然后选择 "**应用 Office 365 邮件加密和权限保护**"。从列表中选择一个 RMS 模板, 选择 "**保存**", 然后选择 **"确定"**。

   模板列表包含所有默认模板和选项, 以及您创建的用于 Office 365 的任何自定义模板。如果列表为空, 请确保已使用新功能设置了 Office 365 邮件加密, 如[设置新的 office 365 邮件加密功能 (基于 Azure 信息保护的基础之上](set-up-new-message-encryption-capabilities.md)) 中所述。有关默认模板的信息, 请参阅[配置和管理 Azure 信息保护的模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关 "**不要转发**" 选项的信息, 请参阅[电子邮件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)的 "不要转发" 选项。有关**仅加密**选项的信息, 请参阅[仅加密电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   如果要指定另一个操作, 可以选择 "**添加操作**"。

7. 从 "**执行以下**操作" 列表中, 删除为**修改邮件安全性** \>而分配的所有操作**应用早期版本的 OME**。

8. 选择" **保存**"。

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>创建不带新功能的 Office 365 邮件加密的邮件流规则

如果您尚未将 Office 365 组织移动到新的 OME 功能, 请使用这些任务定义邮件流规则, 以对组织的邮件进行加密。Microsoft 建议您制定一个计划, 尽快移动到新的 OME 功能, 因为它对您的组织合理。有关说明, 请参阅[设置基于 Azure 信息保护基础构建的新 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>使用 EAC 创建邮件流规则, 以在不使用新的 OME 功能的情况下加密电子邮件

1. 在 web 浏览器中, 使用已被授予全局管理员权限的工作或学校帐户,[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择 "**管理**" 磁贴。

3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。

4. 在 EAC 中, 转到 "**邮件流** \> **规则**", 然后选择 "**新建** ![" 图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。有关使用 EAC 的详细信息, 请参阅 exchange [Online 中的 exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 "**名称**" 中, 键入规则的名称, 例如 "为 DrToniRamos@hotmail.com 加密邮件"。

6. 在 "在**以下情况应用此规则**" 中选择一个条件, 并根据需要输入一个值。例如, 若要加密发往 DrToniRamos@hotmail.com 的邮件, 请执行以下操作:

   1. 在 "在**以下情况应用此规则**" 中, 选择 **"收件人是"**。

   2. 从联系人列表中选择一个现有名称, 或在 "**检查名称**" 框中键入新的电子邮件地址。

      - 若要选择现有名称, 请从列表中选择该名称, 然后单击 **"确定"**。

      - 若要输入新名称, 请在 "**检查名称**" 框中键入电子邮件地址, 然后选择 "**检查名称** \> **" "确定"**。

7. 若要添加更多条件, 请选择 "**更多选项**", 然后选择 "**添加条件**", 然后从列表中选择。

   例如, 若要仅在收件人在组织外部时应用规则, 请选择 "**添加条件**", 然后选择 "在**组织** \>外部 **/内部的收件人是外部/内部** \> **"**。

8. 若要在不使用新的 OME 功能的情况下启用加密, 请在**执行以下操作**中, 选择 **"修改邮件安全性** \> **应用以前版本的 OME**", 然后选择 "**保存**"。

  如果您收到未启用 IRM 许可的错误, 则您还没有为您的组织设置 OME。如果想要立即设置 OME, 则必须将其设置为使用新的 OME 功能。有关详细信息, 请参阅建立[基于 Azure 信息保护基础之上的新 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。Microsoft 不再支持在没有新功能的情况下设置新的 OME 部署。

  如果要指定另一个操作, 可以选择 "**添加操作**"。

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>使用 Exchange Online PowerShell 创建邮件流规则, 以在不提供新 OME 功能的情况下加密电子邮件

1. 连接到 Exchange Online PowerShell。有关详细信息, 请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

2. 使用**new-transportrule** cmdlet 创建一个规则, 并将_ApplyOME_参数设置为`$true`。

   此示例要求发送到 DrToniRamos@hotmail.com 的所有电子邮件都必须加密。

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   **注意**：

   - 新规则的唯一名称是 "加密 Dr Toni Ramos" 的规则。

   - _SentTo_参数指定邮件收件人 (由姓名、电子邮件地址、可分辨名称等)。在此示例中, 收件人由电子邮件地址 "DrToniRamos@hotmail.com" 标识。

   - _SentToScope_参数指定邮件收件人的位置。在此示例中, 收件人的邮箱在 hotmail 中, 而不是 Office 365 组织的一部分, 因此使用此`NotInOrganization`值。

   有关详细的语法和参数信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)。

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>从加密的电子邮件答复中删除加密, 而不具有新的 OME 功能

当您的电子邮件用户发送加密邮件时, 这些邮件的收件人可以使用加密答复进行响应。您可以创建邮件流规则以自动删除答复的加密, 以便组织中的电子邮件用户无需登录到加密门户即可查看加密门户。您可以使用 EAC 或 Windows PowerShell cmdlet 来定义这些规则。如果尚未使用新的 OME 功能, 则只能对从组织内部发送的邮件或从组织内部发送的邮件答复邮件进行解密。无法对源自组织外部的加密邮件进行解密。

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>使用 EAC 创建一个规则, 用于从加密的电子邮件答复中删除加密, 而不使用新的 OME 功能

1. 在 web 浏览器中, 使用已被授予管理员权限的工作或学校帐户,[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择 "**管理**" 磁贴。

3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。

4. 在 EAC 中, 转到 "**邮件流** \> **规则**", 然后选择 "**新建** ![" 图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。有关使用 EAC 的详细信息, 请参阅 exchange [Online 中的 exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 "**名称**" 中, 键入规则的名称, 例如 "从传入邮件中删除加密"。

6. 在 "**应用此规则**" 中, 如果选择应从邮件中删除加密的条件, 例如**收件人位于** \> **组织内部**。

7. 在 **"执行以下操作**" 中, 选择 "**修改邮件安全性** \> **" 删除 OME 的早期版本**。

8. 选择" **保存** "。

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>使用 Exchange Online PowerShell 创建一个规则, 以从加密的电子邮件答复中删除加密, 而不使用新的 OME 功能

1. 连接到 Exchange Online PowerShell。有关详细信息, 请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

2. 使用**new-transportrule** cmdlet 创建一个规则, 并将_RemoveOME_参数设置为`$true`。

   本示例将从所有发送到 Office 365 组织中的收件人的邮件中删除加密。

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   **注意**：

   - 新规则的唯一名称是 "从传入邮件中删除加密"。

   - _SentToScope_参数指定邮件收件人的位置。在此示例中, 使用`InOrganization`了值值, 该值指示:

     - 收件人是组织中的邮箱、邮件用户、组或已启用邮件的公用文件夹。

       或

     - 收件人的电子邮件地址位于您的组织中配置为权威域或内部中继域的接受域中,_并且_邮件是通过经过身份验证的连接发送或接收的。

有关详细的语法和参数信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)。

## <a name="related-topics"></a>相关主题

[Office 365 中的加密](encryption.md)

[设置全新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)

[将品牌添加到加密邮件](add-your-organization-brand-to-encrypted-messages.md)

[Exchange Online 中的邮件流规则（传输规则）](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Exchange Online Protection 中的邮件流规则（传输规则）](https://go.microsoft.com/fwlink/p/?LinkId=506708)

---
title: 使用敏感度标签中的加密限制对内容的访问
ms.author: stephow
author: stephow-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 创建敏感度标签时，可以限制对将要应用标签的内容的访问。敏感度标签可以使用加密来保护内容。
ms.openlocfilehash: a30f5d6168ea8118ef6b30ff26a429857affaa4a
ms.sourcegitcommit: fd3db13cd4fc71cd2cb164fd702007acba3e7399
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "36717647"
---
# <a name="restrict-access-to-content-by-using-encryption-in-sensitivity-labels"></a>使用敏感度标签中的加密限制对内容的访问

创建敏感度标签时，可以限制对将要应用标签的内容的访问。例如，通过敏感度标签的加密设置，可以保护内容，以便：

- 只有组织中的用户才能打开机密文档或电子邮件。
- 只有市场部的用户才能编辑和打印促销声明文档或电子邮件，而组织中的所有其他用户只能阅读它。
- 用户无法转发电子邮件或从中复制包含有关内部组织的新闻的信息。
- 发送到业务合作伙伴的当前价目表在指定日期后无法打开。

当文档或电子邮件被加密时，对内容的访问将受到限制，以便它：

- 只能由标签的加密设置授权的用户解密。
- 无论其所在位置（组织内部或外部）如何，仍保持加密状态，即使该文件被重命名也是如此。
- 静态加密（例如，在 OneDrive 帐户中）和传输加密（例如，发送的电子邮件）。

最后，作为管理员，在创建敏感度标签时，你可选择执行下述任一操作：

- **立即分配权限**，以便准确确定哪些用户获得了带有该标签的内容的哪些权限。
- 在用户将此标签应用到内容时**允许用户分配权限**。 这样，即可让组织内部人员在协作处理和完成任务时具有可能需要的一定程度的灵活性。

在 Microsoft 365 合规中心、Microsoft 365 安全中心或 Office 365 安全与合规中心创建敏感度标签时，可使用加密设置。 在左侧导航栏中，选择“**分类**” > “**敏感度标签**” > “**创建标签**”。

## <a name="how-encryption-works"></a>加密工作原理

加密使用 Azure Rights Management (Azure RMS)。Azure RMS 使用加密、标识和授权策略。若要了解详细信息，请参阅 [Azure Rights Management 是什么？](https://docs.microsoft.com/zh-CN/azure/information-protection/what-is-azure-rms)

## <a name="how-to-turn-on-encryption-for-a-sensitivity-label"></a>如何打开敏感度标签的加密

首先，只需将“**加密**”切换到“**开**”，然后选择是否要：

- **立即分配权限**，以便可准确确定哪些用户获得了带有该标签的内容的哪些权限。 有关详细信息，请参阅下一部分：[立即分配权限](#assign-permissions-now)。
- 在用户将此标签应用到内容时**允许用户分配权限**。 这样，即可让组织内部人员在协作处理和完成任务时具有可能需要的一定程度的灵活性。 有关详细信息，请参阅下述部分：[允许用户分配权限](#let-users-assign-permissions)。

例如，如果你有一个名为“**高度机密**”的敏感度标签，它将应用于你的大部分敏感内容，则你可能需要决定谁对该内容获得哪种类型的权限。

或者，如果你有一个名为“**商业合同**”的敏感度标签，而你所在组织的工作流要员工临时与不同人员协作处理此内容，则你可能需要允许用户在分配此标签时决定由谁获得权限。 这种灵活性都能帮助你的用户保持高效，同时减少管理员要更新或新建敏感度标签来应对特定场景的请求。

![用于添加用户或管理员定义的权限的选项](media/sensitivity-label-user-or-admin-defined-permissions.png)

## <a name="assign-permissions-now"></a>立即分配权限

使用下述选项来控制哪些人员可访问应用了此标签的电子邮件或文档。 可执行下列操作：

1. **向电子邮件和文档同时应用加密，或只向电子邮件应用加密。** 如果选择只向电子邮件应用加密，则具有此标签的邮件将在 Outlook 中被加密，但具有此标签的文档将不会在其他应用中加密（例如，Word 或 PowerPoint）。 
2. **允许对标记的内容的访问权限过期**（在某个特定日期或在应用标签后的特定天数后）。在此时间后，用户将无法打开标记的项。如果指定某个日期，则它将于该日期午夜（在你的当前时区）生效。请注意，某些电子邮件客户端由于其缓存机制，可能不强制过期，也不显示超过其过期日期的电子邮件。
3. **允许脱机访问**（从不、始终或在应用标签后的特定天后）。如果将脱机访问限制为从不或一定天数，则当达到该阈值时，必须对用户重新进行身份验证并记录其访问。有关详细信息，请参阅下一部分有关 Rights Management 使用许可证的内容。

![有关管理员定义的权限的设置](media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a>针对脱机访问的 Rights Management 使用许可证

当用户在脱机状态下打开已受敏感度标签保护的文档或电子邮件时，将向用户授予针对该内容的 Azure Rights Management 使用许可证。此使用许可证是一个证书，其中包含用户对文档或电子邮件的使用权限，以及用于加密内容的加密密钥。使用许可证还包括到期日期（如果对此进行了设置）以及使用许可证的有效期。

如果尚未设置任何到期日期，则针对租户的默认使用许可证有效期为 30 天。在使用许可证有效期内，无需就内容对用户重新进行身份验证或授权。这使用户无需具有 Internet 连接即可继续打开受保护的文档或电子邮件。当用户许可有效期到期后，在用户下次访问受保护的文档或电子邮件时，必须对用户重新进行身份验证和授权。

除重新进行身份验证以外，还将重新评估策略和用户组成员身份。这意味着，如果自他们最后一次访问内容时在策略或组成员身份中存在更改，则对于同一文档或电子邮件，他们可能会收到不同的访问结果。

若要了解如何更改默认的 30 天设置，请参阅 [Rights Management 使用许可证](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-management-use-license)。

### <a name="assign-permissions-to-specific-users-or-groups"></a>向特定用户或组分配权限

可以向特定人员授予权限，只允许这些人员与标记的内容进行交互。

实现此功能只需简单的两个步骤：

1. 首先，添加将向其分配对标记的内容具有访问权限的用户或组。
2. 然后，选择这些用户对标记的内容所具有的权限。

![向用户分配权限的选项](media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a>添加用户或组

分配权限时，可以选择：

- 组织中的任何人（所有租户成员）。此设置不包括来宾帐户。
- 任何特定用户或启用了电子邮件的安全组、通讯组、Office 365 组或动态通讯组。 
- 组织外部的任何电子邮件地址或域，例如 gmail.com、hotmail.com 或 outlook.com。

选择所有租户成员或浏览目录时，用户或组必须具有电子邮件地址。

最佳做法是使用组，而不是使用用户。此策略可使你的配置更为简单。

#### <a name="choose-permissions"></a>选择权限

选择允许为这些用户或组使用哪些权限时，可以选择：

- 具有预设权限组的[预定义权限级别](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels)，例如共同创作或审阅者。
- 自定义权限组，可选择想要允许使用的任何权限。

有关每个特定权限的详细信息，请参阅[使用权限和说明](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)。  

![选择预设权限或自定义权限的选项。](media/Sensitivity-Choose-permissions-settings.png)

请注意，同一标签可向不同用户授予不同的权限。例如，一个标签可将某些用户分配为审阅者，并可将其他用户分配为共同创作，如下所示。

为此，添加用户或组、向其分配权限并保存这些设置。然后重复这些步骤，添加用户并向其分配权限、每次保存设置。可以根据需要经常执行此操作，以便为不同用户定义不同权限。

![具有不同权限的不同用户](media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a>Rights Management 颁发者（应用敏感度标签的用户）始终具有完全控制

敏感度标签的加密使用 Azure RMS。当用户通过使用 Azure RMS 应用敏感度标签以保护文档或电子邮件时，该用户变为该内容的Rights Management 颁发者。

Rights Management 颁发者将始终被授予对文档或电子邮件的完全控制权限，此外：

- 如果保护设置包含过期日期，则 Rights Management 颁发者在该日期后仍可以打开和编辑文档或电子邮件。
- Rights Management 颁发者可以始终在脱机状态下访问文档或电子邮件。
- 在文档被撤销后，Rights Management 颁发者仍然可以打开该文档。

有关详细信息，请参阅 [Rights Management 颁发者和 Rights Management 所有者](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)。

## <a name="let-users-assign-permissions"></a>允许用户分配权限

可使用下述选项来允许用户在向内容手动应用敏感度标签时分配权限：

- 在 Outlook 中，用户可强制实施与“**请勿转发**”选项等效的限制。 此选项在 Windows 版 Outlook 上本地支持，且不要求你安装 Azure 信息保护统一标签客户端。
- 在 Word、PowerPoint 和 Excel 中，系统会提示用户为特定用户、组或组织选择一个权限级别。 此选项在这些 Office 应用中本地不受支持，因此你的用户必须安装 Azure 信息保护统一标签客户端。

这些选项可决定哪些应用中将显示敏感度标签：

- 如果敏感度标签仅启用了 Outlook 选项，则该标签仅对 Outlook 中的用户可见。
- 如果敏感度标签仅启用了 Word、PowerPoint 和 Excel 选项，则该标签仅对这些应用中的用户可见。
- 如果敏感度标签启用了上述两个选项，则标签对所有可用应用（Outlook、Word、PowerPoint 和 Excel）中的用户可见。

允许用户分配权限的敏感度标签仅可由用户手动应用于内容；它不能自动应用，也不能用作建议的标签。

> [!NOTE]
> 需具备 Azure 信息保护订阅，才可允许用户分配权限。 要在 Word、PowerPoint 和 Excel 中使用此功能，必须下载和安装 [Azure 信息保护统一标签客户端](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)。 我们正在开发在这些 Office 应用中对此功能的本机支持，让其无需 Azure 信息保护客户端。 此外，客户端仅在 Windows 上运行，因此 Mac、iOS、Android 和 Office 网页版上尚不支持此功能。

![有关用户定义的权限的加密设置](media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a>Outlook 限制

在 Outlook 中，当用户向邮件应用允许其分配权限的敏感度标签时，需遵守的限制与“请勿转发”选项相同。 用户将在邮件顶部看到标签名称和说明，这表示正在保护该内容。 与 Word、PowerPoint 和 Excel 不同（详见[下一部分](#word-powerpoint-and-excel-permissions)），系统不会提示用户选择特定权限。

![应用于 Outlook 中的邮件的敏感度标签](media/sensitivity-label-outlook-protection-applied.png)

向电子邮件应用“请勿转发”选项时，电子邮件将被加密，且收件人必须通过身份验证。 其次，收件人不得转发、打印和复制该邮件。 例如，在 Outlook 客户端中，“转发”按钮不可用，“另存为”和“打印”菜单选项也不可用，并且你不可在“收件人”、“抄送”和“密件抄送”框中添加或更改收件人。

自动附加到电子邮件且不受保护的 Office 文档会自动继承相同的限制。 应用于这些文档的使用权限为“编辑内容”、“编辑”，“保存”，“视图”、“打开”、“阅读”，以及“允许宏”。 如果用户对附件实施其他使用权限，或者附件并非支持该继承权限的 Office 文档，则用户需要在将文件附加到电子邮件之前保护该文件。

### <a name="word-powerpoint-and-excel-permissions"></a>Word、PowerPoint 和 Excel 权限

在 Word、PowerPoint 和 Excel 中，当用户向文档应用允许其分配权限的敏感度标签时，系统会提示他们如下所示来保护内容。

用户可执行下列操作：

- 选择权限级别，例如查看者（可分配“仅查看”权限）或合著者（可分配“查看”、“编辑”、“复制”和“打印”权限）。
- 选择用户、组或组织。 这可包括你所在组织内部或外部的人员。
- 设置到期日期，所选用户在该日期后不可访问内容。 有关详细信息，请参阅上一部分：[针对脱机访问的 Rights Management 使用许可证](#rights-management-use-license-for-offline-access)。

![供用户通过自定义权限进行保护的选项](media/sensitivity-aip-custom-permissions-dialog.png)

## <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a>应用标签后，现有加密会发生什么情况

在向内容应用敏感度标签之前，用户可能已通过应用一些其他保护设置进行了内容加密。 例如，用户可能已应用：

- “**请勿转发**”选项。
- 通过 Azure 信息保护统一标记客户端实现的自定义保护。
- 会加密内容但不与标签关联的 Azure 权限管理服务 (RMS) 模板。

下表说明了在向该内容应用敏感度标签后现有加密发生的情况。
<br/>
<br/>

| |**用户在加密关闭的情况下应用敏感度标签**|**用户在加密开启的情况下应用敏感度标签**|**用户应用具有“去除保护”的标签**<sup>1</sup>|
|:-----|:-----|:-----|:-----|
|**请勿转发**|电子邮件 - 已去除保护<br/>文档 - 已保留保护|已应用标签保护|已删除“**请勿转发**”|
|**自定义保护**<sup>1</sup>|已保留保护|已应用标签保护|已去除自定义保护|
|**Azure RMS 模板**|已保留保护|已应用标签保护|已去除自定义保护|

<sup>1</sup>此功能仅在 Azure 信息保护标记客户端中受支持。

## <a name="storing-encrypted-content-in-onedrive-and-sharepoint"></a>存储 OneDrive 和 SharePoint 中加密的内容

请注意，将加密应用于 OneDrive 和 SharePoint 中存储的文件时，该服务无法处理这些文件的内容。这意味着共同创作、电子数据展示、搜索、Delve 和其他协作功能将无法正常使用。此外，数据丢失防护 (DLP) 策略只适用于元数据（包括 Office 365 标签），但并不适用于这些加密的文件的内容（例如，文件内的信用卡号）。

这仅适用于在 OneDrive 和 SharePoint 中存储的内容。在 Exchange Online 中，邮件流规则（也称为传输规则）使用[超级用户帐户](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-super-users)，以便他们能够扫描加密的内容和强制实施 DLP 策略。

## <a name="important-prerequisites"></a>重要先决条件

在使用加密前，可能需要执行这些任务。

### <a name="activating-azure-rights-management"></a>激活 Azure Rights Management

若要使用敏感度标签中的加密，需要在租户中激活 Azure Rights Management 服务。在较新的租户中，该服务在默认情况下为启用状态，但可能需要手动激活该服务。有关详细信息，请参阅[激活 Azure Rights Management](https://docs.microsoft.com/zh-CN/azure/information-protection/activate-service)。

### <a name="configure-exchange-for-azure-information-protection"></a>配置用于 Azure 信息保护的 Exchange

在用户能够在 Outlook 中应用标签以保护其电子邮件前，无需对 Exchange 进行配置以用于 Azure 信息保护。但是，如果没有针对 Azure 信息保护对 Exchange 进行配置，你将无法在 Exchange 中获取使用 Azure Rights Management 的完整功能。
 
例如，用户无法查看移动电话或 Outlook 网页版上受保护的电子邮件，无法索引受保护的电子邮件以用于搜索，并且无法针对 Rights Management 保护配置 Exchange Online DLP。 

为确保 Exchange 可以支持这些其他应用场景，请参阅以下内容：

- 对于 Exchange Online，请参阅 [Exchange Online：IRM 配置](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-office365#exchange-online-irm-configuration)的说明。
- 对于本地 Exchange，必须部署 [RMS 连接器并配置你的 Exchange 服务器](https://docs.microsoft.com/zh-CN/azure/information-protection/deploy-rms-connector)。 

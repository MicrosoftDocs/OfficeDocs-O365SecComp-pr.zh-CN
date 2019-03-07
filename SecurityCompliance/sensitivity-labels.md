---
title: 敏感度标签概述
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 10/22/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用 Office 365 中的敏感度标签，可以对敏感内容进行分类和保护，同时确保组织内人员的工作效率和协作能力不受阻碍。敏感度标签可用于强制执行保护设置，如对已标记内容设置加密或水印。
ms.openlocfilehash: 05f53c508126962d36be3e131413d5a4314875a9
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "30455024"
---
# <a name="overview-of-sensitivity-labels"></a>敏感度标签概述

组织内人员需要与组织内外的其他人员协作，才能完成工作。也就是说，内容不再一直停留在防火墙后面，而是跨设备、应用和服务到处漫游。你希望内容的漫游方式不仅安全、受保护，还符合组织的业务和合规性策略。

使用 Office 365 中的敏感度标签，可以对敏感内容进行分类和保护，同时确保组织内人员的工作效率和协作能力不受阻碍。

![Excel 功能区和状态栏上的敏感度标签](media/Sensitivity_label_in_Excel.png)

借助敏感度标签，你可以：
  
- **强制执行保护设置，如对已标记内容设置加密或水印。** 例如，用户可以向文档或电子邮件应用“机密”标签，然后此标签便能加密相应内容，并应用“机密”水印。    

- **跨不同平台和设备保护 Office 应用中的内容。** 敏感度标签适用于 Windows、Mac、iOS 和 Android 上的 Office 应用。我们即将推出对 Office Web 应用的支持。
    
- **利用 Microsoft Intune 终结点保护，防止在 Windows 设备上驻留的敏感内容从组织中泄露。** 当 Windows 设备上驻留的内容已应用有敏感度标签后，终结点保护可以阻止此类内容被复制到第三方应用（如 Twitter 或 Gmail），也可以阻止此类内容被复制到可移动存储（如 U 盘）。

- **将敏感度标签扩展到第三方应用和服务。** 借助 Microsoft 信息保护 SDK，Windows、Mac 和 Linux 上的第三方应用可以读取敏感度标签，并应用保护设置。我们即将推出对 iOS 和 Android 上应用的支持。

- **对内容进行分类，而不使用任何保护设置。** 也可以只对内容进行分类（如不干胶标签），只要有人使用和共享内容，此分类就会随内容一起暂留和漫游。使用此分类，可生成使用情况报告，并查看敏感内容的活动数据。根据此类信息，稍后随时可以选择应用保护设置。
    
无论是上述哪种用途，Office 365 中的敏感度标签都可有助于对正确的内容执行适当的操作。借助敏感度标签，可对整个组织中的数据进行分类，并根据此分类强制执行保护设置。
  
敏感度标签是在 Office 365 安全与合规中心内创建。目前，安全与合规中心是跨 Azure 信息保护和 Office 365 配置敏感度标签和策略的唯一位置。这些敏感度标签可供 Azure 信息保护、Office 应用和 Office 365 服务使用。

Azure 信息保护客户可以在安全与合规中心内使用 Azure 信息保护标签。如果信息保护客户选择执行其他配置或高级配置，这些信息保护标签便会与 Azure 门户同步。Azure 信息保护标签和 Office 365 敏感度标签彼此完全相互兼容。**** 也就是说，例如，如果内容已有 Azure 信息保护标签，无需重新对此内容进行分类或标记。

![安全与合规中心内“标签”页上的“敏感度”选项卡](media/Sensitivity_label_tab_on_Labels_page.png)

## <a name="what-a-sensitivity-label-is"></a>什么是敏感度标签

向文档或电子邮件分配的敏感度标签就像是具有以下特征的标记：

- **可自定义**：可以为组织中不同级别的敏感内容创建类别，如“个人”、“公开”、“常规”、“机密”和“高度机密”。

- **以明文形式显示**：由于敏感度标签以明文形式显示，因此第三方应用和服务可利用标签向已标记内容应用保护性操作。

- **永久性**：向内容应用的敏感度标签在相应电子邮件或文档的元数据中暂留。也就是说，标签（包括保护设置）随内容一起漫游，并成为应用和强制执行策略的基础。

在 Office 应用中，敏感度标签只显示为电子邮件或文档上的标记。

每个内容项都可以应用有一个敏感度标签。但请注意，一个内容项可以同时应用有一个敏感度标签和一个[保留标签](labels.md)。

![应用于电子邮件的敏感度标签](media/Sensitivity_label_on_email.png)

## <a name="what-sensitivity-labels-can-do"></a>敏感度标签有何用途

当电子邮件或文档应用有敏感度标签后，系统便会对内容强制执行相应标签的保护设置。敏感度标签可用于：

- **加密**：仅加密电子邮件，或同时加密电子邮件和文档。可选择哪些用户或组在多长时间内有权执行哪些操作。例如，可选择允许组织外特定域中的用户，仅在内容应用有标签后的 7 天内有权查看相应内容。有关详细信息，请参阅[使用敏感度标签中的加密限制对内容的访问](encryption-sensitivity-labels.md)。

- **标记内容**：具体方法是将自定义水印、页眉或页脚添加到已应用有标签的电子邮件或文档中。请注意，水印只能应用于文档，不能应用于电子邮件。水印的长度上限为 255 个字符。此外，页眉和页脚的长度上限为 1024 个字符（但在 Excel 中除外，其中的长度上限为 255 个字符，具体取决于文档是否包含其他页眉或页脚和其他因素）。

    ![应用于文档的水印和页眉](media/Sensitivity_label_watermark_header.png)

- 
  **数据丢失防护**：方法为启用 Intune 终结点保护。如果敏感内容已下载，可防止数据从 Windows 设备中丢失。例如，无法将已标记内容复制到 Dropbox、Gmail 或 U 盘。必须先在 Azure 门户中创建应用保护策略，敏感度标签才能使用 Windows 信息保护 (WIP)。有关详细信息，请参阅 [Windows 信息保护如何保护具有敏感度标签的文件](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)。

- **将标签应用到包含敏感信息的内容。** 你可以选择要标记的敏感信息类型，标签可以自动应用，也可以提示用户应用你推荐的标签。如果你推荐标签，则提示会显示你选择的任何文本。有关详细信息，请参阅[自动将敏感标签应用于内容](apply_sensitivity_label_automatically.md)。

    ![提示分配所需的标签](media/Sensitivity_label_Prompt_for_required_label.png)


在安全与合规中心内创建标签时，可使用以上所有选项。

![创建敏感度标签时可使用的选项](media/Sensitivity_label_create_options.png)

### <a name="label-priority-order-matters"></a>标签优先级（顺序非常重要）

如果在安全与合规中心内创建敏感度标签，标签显示在“标签”**** 页上“敏感度”**** 选项卡中的列表内。此列表中的标签顺序非常重要，因为它反映了标签优先级。建议让限制最多的敏感度标签（如“高度机密”）显示在列表最下面****，并让限制最少的敏感度标签（如“公开”）显示在列表最上面****。

一个文档或电子邮件只能应用有一个敏感度标签。若有要求用户必须提供将标签更改为较低分类的理由，理由可以是此列表的排序，因为它决定了较低分类是什么。

![子标签创建选项](media/Sensitivity_label_sublabel_options.png)

### <a name="sublabels-grouping-labels"></a>子标签（对标签进行分组）

使用子标签，你可以将一个或多个标签分组到用户在 Office 应用程序中看到的父标签下方。 例如，在“机密”下，你的组织可能会为该分类的特定类型使用多个不同的标签。 在此示例中，父标签“机密”仅仅是没有保护设置的文本标签，并且因为它具有子标签，所以它不能应用于内容。 相反，用户必须选择“机密”才能查看子标签，然后他们可以选择要应用于内容的子标签。

子标签只是向逻辑组中的用户显示标签的一种方式。 子标签不会从其父标签继承任何设置。 子标签可以应用于内容；父标签不能。

（另外，不应选择父标签作为默认标签（请参阅下一节），或将父标签配置为自动应用或推荐使用，因为父标签不会应用于使用 Azure 信息保护统一标签客户端的 Office 应用程序中的内容。）

![功能区上的已分组子标签](media/Sensitivity_label_grouped_labels.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a>编辑或删除敏感度标签

如果在安全与合规中心内删除敏感度标签，请注意标签并未从内容中删除，且对内容继续执行所有保护设置。

如果在安全与合规中心内编辑敏感度标签，应用于内容的标签版本就是对相应内容强制执行的标签。

## <a name="what-label-policies-can-do"></a>标签策略有何用途

创建敏感度标签后，需要发布它们，以便组织内人员能够将标签应用于内容。与发布到所有 Exchange 邮箱等位置的保留标签不同，敏感度标签是发布到用户或组。然后，敏感度标签便会显示在这些用户或组的 Office 应用中。

借助标签策略，你可以：

- **选择向哪些用户和组显示标签。** 可以将标签发布到任意启用电子邮件的安全组、通讯组、Office 365 组或动态通讯组。

- **将默认标签**应用于标签策略中包含的用户和组创建的所有新文档和电子邮件。 此默认标签可以设置要应用于所有内容的基本级别的保护设置。 （请注意，）

- **要求提供更改标签的理由。** 如果内容应用有“机密”标签，但用户要删除此标签或将它替换为较低分类（如“公开”标签），你可以要求用户必须在执行此操作时提供理由。这些理由可供管理员查看。目前，我们正在努力推出可供管理员查看用户理由的报告。

    ![提示用户输入理由的页面](media/Sensitivity_label_justification_required.png)

- **要求用户将标签应用于他们的电子邮件和文档。** 如果你希望标记用户的所有内容，则可以要求必须将标签应用于所有已保存的文档和已发送的电子邮件。标签可以由用户手动分配、按条件自动分配或者进行默认分配（上述默认标签选项）。以下是当要求用户分配标签时 Outlook 中显示的提示。

    > [!NOTE]
    > 要使用强制标签，需要具备 Azure 信息保护订阅。要使用此功能，必须下载并安装 [Azure 信息保护客户端](https://www.microsoft.com/en-us/download/details.aspx?id=53018)或后续的 [Azure 信息保护统一标签客户端](https://docs.microsoft.com/zh-CN/azure/information-protection/rms-client/install-unifiedlabelingclient-app)。我们正在设法实现 Office 应用对此功能的本机支持，因此届时将不需要 Azure 信息保护客户端。此外，客户端仅在 Windows 上运行，因此 Mac、iOS 和 Android 上尚不支持此功能。

    ![在 Outlook 中要求用户应用所需标签的提示](media/sensitivity_labels_mandatory_prompt_aipv2_outlook.PNG)

- **提供指向自定义帮助页的帮助链接。** 如果用户不确定敏感度标签的含义或应如何使用标签，你可以提供在 Office 应用中“敏感度”标签菜单底部显示的“了解更多”URL。

    ![功能区上“敏感度”按钮中的“了解更多”链接](media/Sensitivity_label_learn_more.png)

在你创建标签策略并将敏感度标签分配给用户和组后，这些人员会在不超过一小时的时间内在 Office 应用中看到这些标签。

## <a name="how-to-get-started"></a>如何开始使用

敏感度标签可快速上手：

1. **定义标签。** 首先要建立分类，用于定义各种敏感内容级别。应使用用户能理解的常见名称或术语。例如，可以从“个人”、“公开”、“常规”、“机密”和“高度机密”等标签入手。可利用子标签按类别对相似标签进行分组。此外，创建标签时，还需要提供工具提示，即用户将鼠标悬停在功能区中的某个标签选项时在 Office 应用中看到的提示。

1. **定义每个标签有何用途。** 然后，配置要与每个标签关联的保护设置。例如，较低敏感度内容（应用有“常规”标签）可以只应用有页眉或页脚，而较高敏感度内容（应用有“机密”标签）则可以应用有水印、加密和 WIP，这样有助于确保只有特权用户才能访问它。
 
1. **定义谁能获取标签。** 定义组织的标签后，通过标签策略发布它们。标签策略控制了哪些用户和组能看到这些标签。一个标签是可重用的。也就是说，定义标签一次后，可将它添加到分配给不同用户的多个标签策略。不过，必须先发布相应标签，使其显示在 Office 应用或其他服务中，然后才能将标签分配给内容。刚开始的时候，可尝试仅将敏感度标签分配给少数几个人员。

下面的基本流展示了管理员、用户和 Office 应用为了让敏感度标签起作用所要执行的操作。

![敏感度标签工作流关系图](media/Sensitivity_label_flow.png)

## <a name="where-sensitivity-labels-can-appear"></a>敏感度标签可以显示在哪里

敏感度标签显示在 Office 应用 UI 中。若要查看敏感度标签对特定应用和平台的最新适用情况，请参阅**[此功能目前在何处适用？](https://support.office.com/zh-CN/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9?ad=US&ui=en-US&rs=en-US#bkmk_whereavailable)**

### <a name="office-apps-on-windows"></a>Windows 上的 Office 应用

在 Windows 设备上的 Office 应用中，敏感度标签显示在功能区上“开始”**** 选项卡的“敏感度”**** 按钮中。已应用的标签还显示在窗口底部的状态栏中。

我们即将推出对 Windows 上 Office 应用中敏感度标签的本机支持。

如果已是 Azure 信息保护客户，可以部署 Azure 信息保护统一标记客户端。此客户端支持敏感度标签。有关下载此客户端的更多信息，请参阅 [Azure 信息保护统一标记客户端：版本发布信息](https://docs.microsoft.com/zh-CN/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)目前，我们正在努力推出对 Windows 上 Office 应用中敏感度标签的本机支持，所以届时将无需再使用 Azure 信息保护统一标记客户端。

![Windows 上 Excel 功能区中的“敏感度”按钮](media/Sensitivity_label_Sensitivity_button.png)

### <a name="office-apps-on-mac"></a>Mac 上的 Office 应用

在 Mac 设备上的 Office 应用中，敏感度标签显示在功能区上“开始”**** 选项卡的“敏感度”**** 按钮中。已应用的标签还显示在窗口底部的状态栏中。

![Mac 上 Office 功能区中的“敏感度”按钮](media/Sensitivity_label_on_Mac.png)

### <a name="office-apps-on-ios"></a>iOS 上的 Office 应用

在 iOS 设备上的 Office 应用中，敏感度标签显示在功能区上“开始”**** 选项卡的“敏感度”**** 按钮中。已应用的标签还显示在窗口底部的状态栏中。

![iOS 上 Office 功能区中的“敏感度”按钮](media/Sensitivity_label_on_iOS.png)

### <a name="office-apps-on-android"></a>Android 上的 Office 应用

在 Android 设备上的 Office 应用中，敏感度标签显示在功能区上“开始”**** 选项卡的“敏感度”**** 按钮中。已应用的标签还显示在窗口底部的状态栏中。

![Android 上 Office 功能区中的“敏感度”按钮](media/Sensitivity_label_on_Android.png)

### <a name="more-information-on-sensitivity-labels-in-office-apps"></a>详细了解 Office 应用中的敏感度标签

- [将敏感度标签应用于 Office 文档和电子邮件](https://support.office.com/zh-CN/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
- [将敏感度标签应用于 Office 文件时的已知问题](https://support.office.com/zh-CN/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)

## <a name="how-sensitivity-labels-work-with-existing-azure-information-protection-labels"></a>如何结合使用敏感度标签与现有 Azure 信息保护标签

目前，Azure 信息保护用户可使用 Azure 信息保护统一标记客户端，对 Windows 上的内容进行分类和标记。可顺畅地结合使用现有 Azure 信息保护标签与新敏感度标签。也就是说，可执行下列操作：

- 保留文档和电子邮件中的现有 Azure 信息保护标签。
- 保留现有 Azure 信息保护标签配置。

若要使用 Azure 信息保护标签，目前的建议是，除非完成迁移，否则不要在安全与合规中心内新建标签。[Azure 信息保护迁移主题](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-policy-migrate-labels)介绍了重要信息和一些具体注意事项。如果尚未准备好将生产租户迁移为使用敏感度标签，也无需担心，因为目前用户可继续使用 Azure 信息保护客户端，管理员也能继续使用 Azure 门户进行管理。

## <a name="protect-content-on-windows-devices-by-using-endpoint-protection-in-microsoft-intune"></a>使用 Microsoft Intune 终结点保护来保护 Windows 设备上的内容

创建敏感度标签时，可视需要指示 Windows 具有此标签的文件是敏感内容，需要保护存储在 Windows 设备上的此类文件，以防发生数据泄露。此选项有助于确保具有此标签的内容只能共享或复制到批准的位置上，即使内容存储在终结点上，也不例外。实际上，如果对敏感度标签启用此选项，便是在指示 Windows 这是非常关键的数据，有必要施加额外使用限制。

当你启用此选项后，Windows 便能读取、理解和处理文档中的敏感度标签，并自动对内容应用 Windows 信息保护 (WIP)，无论内容是以何种方式到达 Windows 托管设备的。这样有助于防止已标记文件发生意外数据泄露，无论是否应用加密。

例如，Windows 可知道驻留在用户计算机上的 Word 文档已应用有“机密”标签，WIP 可应用应用保护策略，以防相应设备中的数据被复制或共享到任何非工作位置（如个人 OneDrive、个人电子邮件帐户、社交媒体或 U 盘）。

如果用户试图将已标记内容上传到个人 Gmail 帐户，便会看到以下消息。

![提示无法将已标记内容复制到 Gmail 的消息](media/Sensitivity_label_WIP_Gmail.png)

此外，如果用户试图将已标记内容保存到 U 盘，还会看到以下消息。

![提示无法将已标记内容保存到 U 盘的消息](media/Sensitivity_label_WIP_USB_drive.png)

### <a name="important-prerequisites"></a>重要先决条件

必须先满足 [Windows 信息保护如何保护具有敏感度标签的文件](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)中提及的先决条件，然后敏感度标签才能使用 WIP。这篇主题提及以下先决条件：

- 确保运行的是 Windows 10 版本 1809 或更高版本。
- [设置 Windows Defender 高级威胁防护 (WDATP)](https://docs.microsoft.com/zh-CN/windows/security/threat-protection/windows-defender-atp/get-started)，以扫描内容中是否有标签，并应用相应的 WIP 保护。ATP 与 WIP 分开执行一些操作，如报告异常。
- 创建适用于终结点设备的 Windows 信息保护 (WIP) 策略。可以在下列两个位置之一执行此操作：
    - [使用适用于 Microsoft Intune 的 Azure 门户通过 MDM 创建 Windows 信息保护 (WIP) 策略](https://docs.microsoft.com/zh-CN/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)
    - [使用 System Center Configuration Manager 创建并部署 Windows 信息保护 (WIP) 策略](https://docs.microsoft.com/zh-CN/windows/security/information-protection/windows-information-protection/create-wip-policy-using-sccm)

## <a name="extend-sensitivity-labels-to-third-party-apps-and-services-by-using-the-microsoft-information-protection-sdk"></a>使用 Microsoft 信息保护 SDK 将敏感度标签扩展到第三方应用和服务

由于敏感度标签以明文形式暂留在文档的元数据中，因此第三方应用和服务可选择支持识别和保护包含此类标签的内容。我们会一直扩大对其他应用和服务的支持。

借助 [Microsoft 信息保护 SDK](https://docs.microsoft.com/zh-CN/information-protection/develop/)，第三方应用和服务可读取敏感度标签，并向文档应用敏感度标签和保护设置。此 SDK 支持 Windows、Mac 和 Linux 上的应用。我们即将推出对 iOS 和 Android 上应用的支持。

借助此 SDK，可以标记和保护内容，且方式与其他 Microsoft 信息保护应用和服务（如 Office 应用、Office 365 服务、Azure 信息保护扫描程序、Microsoft Cloud App Security 及其他多个合作伙伴解决方案）兼容。有关示例，请详细了解 [Adobe Acrobat 中的敏感度标签支持](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738)。

若要详细了解 Microsoft 信息保护 SDK，请参阅[技术社区博客公告](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144)。此外，还可以了解[与 Microsoft 信息保护集成的合作伙伴解决方案](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657)。

## <a name="permissions"></a>权限

若为创建敏感度标签的合规性团队成员，必须有权访问安全与合规中心。默认情况下，租户管理员有权访问此位置，并可向合规部主管及其他人员授予对安全与合规中心的访问权限，而不授予租户管理员的所有权限。为此，建议转到安全与合规中心内的“权限”**** 页，编辑“合规性管理员”**** 角色组，再向此角色组添加成员。

有关详细信息，请参阅“向用户授予对 Office 365 安全与合规中心的访问权限”。

只有在创建和应用标签和标签策略时，才必须拥有这些权限。强制执行策略并不需要访问内容。

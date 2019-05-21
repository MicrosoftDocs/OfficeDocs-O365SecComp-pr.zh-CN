---
title: 敏感度标签概述
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 使用敏感度标签，可以对敏感内容进行分类和保护，同时确保组织内人员的工作效率和协作能力不受阻碍。敏感度标签可用于强制执行保护设置，如对已标记内容设置加密或水印。
ms.openlocfilehash: 63470a4375c1a3cc1420b64725d6741aa8e95af4
ms.sourcegitcommit: 28d5972adef5bbe1377d89ff9962c531f5f08dbf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "34166919"
---
# <a name="overview-of-sensitivity-labels"></a><span data-ttu-id="d5c48-104">敏感度标签概述</span><span class="sxs-lookup"><span data-stu-id="d5c48-104">Overview of sensitivity labels</span></span>

<span data-ttu-id="d5c48-p102">组织内人员需要与组织内外的其他人员协作，才能完成工作。也就是说，内容不再一直停留在防火墙后面，而是跨设备、应用和服务到处漫游。你希望内容的漫游方式不仅安全、受保护，还符合组织的业务和合规性策略。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p102">To get their work done, people in your organization need to collaborate with others both inside and outside the organization. This means that content no longer stays behind a firewall – it roams everywhere, across devices, apps, and services. And when it roams, you want it to do so in a secure, protected way that meets your organization’s business and compliance policies.</span></span>

<span data-ttu-id="d5c48-108">使用敏感度标签，可以对敏感内容进行分类和保护，同时确保组织内人员的工作效率和协作能力不受阻碍。</span><span class="sxs-lookup"><span data-stu-id="d5c48-108">With sensitivity labels, you can classify and help protect your sensitive content, while making sure that your people’s productivity and ability to collaborate isn’t hindered.</span></span>

![Excel 功能区和状态栏上的敏感度标签](media/Sensitivity_label_in_Excel.png)

<span data-ttu-id="d5c48-110">借助敏感度标签，你可以：</span><span class="sxs-lookup"><span data-stu-id="d5c48-110">You can use sensitivity labels to:</span></span>
  
- <span data-ttu-id="d5c48-p103">**强制执行保护设置，如对已标记内容设置加密或水印。** 例如，用户可以向文档或电子邮件应用“机密”标签，然后此标签便能加密相应内容，并应用“机密”水印。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p103">**Enforce protection settings such as encryption or watermarks on labeled content.** For example, your users can apply a Confidential label to a document or email, and that label can encrypt the content and apply a Confidential watermark.</span></span>    

- <span data-ttu-id="d5c48-p104">**跨不同平台和设备保护 Office 应用中的内容。** 敏感度标签适用于 Windows、Mac、iOS 和 Android 上的 Office 应用。我们即将推出对 Office Web 应用的支持。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p104">**Protect content in Office apps across different platforms and devices.** Sensitivity labels work in Office apps on Windows, Mac, iOS, and Android. Support for Office web apps is coming soon.</span></span>
    
- <span data-ttu-id="d5c48-p105">**利用 Microsoft Intune 终结点保护，防止在 Windows 设备上驻留的敏感内容从组织中泄露。** 当 Windows 设备上驻留的内容已应用有敏感度标签后，终结点保护可以阻止此类内容被复制到第三方应用（如 Twitter 或 Gmail），也可以阻止此类内容被复制到可移动存储（如 U 盘）。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p105">**Prevent sensitive content from leaving your organization on devices running Windows**, by using endpoint protection in Microsoft Intune. After a sensitivity label has been applied to content that resides on a Windows device, endpoint protection can prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>

- <span data-ttu-id="d5c48-118">利用 Microsoft Cloud App Security **保护第三方应用和服务中的内容**。</span><span class="sxs-lookup"><span data-stu-id="d5c48-118">**Protect content in third-party apps and services**, by using Microsoft Cloud App Security.</span></span> <span data-ttu-id="d5c48-119">借助 Cloud App Security，可检测、分类、标记和保护第三方服务和应用（如 SalesForce、Box 或 Dropbox）中的内容，即使第三方应用或服务无法读取或不支持敏感度标签也不例外。</span><span class="sxs-lookup"><span data-stu-id="d5c48-119">With Cloud App Security, you can detect, classify, label, and protect content in third-party apps and services, such as SalesForce, Box, or DropBox, even if the third-party app or service does not read or support sensitivity labels.</span></span>

- <span data-ttu-id="d5c48-p107">**将敏感度标签扩展到第三方应用和服务。** 借助 Microsoft 信息保护 SDK，Windows、Mac 和 Linux 上的第三方应用可以读取敏感度标签，并应用保护设置。我们即将推出对 iOS 和 Android 上应用的支持。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p107">**Extend sensitivity labels to third-party apps and services.** With the Microsoft Information Protection SDK, third-party apps on Windows, Mac, and Linux can read sensitivity labels and apply protection settings. Support for apps on iOS and Android is coming soon.</span></span>

- <span data-ttu-id="d5c48-p108">**对内容进行分类，而不使用任何保护设置。** 也可以只对内容进行分类（如不干胶标签），只要有人使用和共享内容，此分类就会随内容一起暂留和漫游。使用此分类，可生成使用情况报告，并查看敏感内容的活动数据。根据此类信息，稍后随时可以选择应用保护设置。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p108">**Classify content without using any protection settings.** You can also simply assign a classification to content (like a sticker) that persists and roams with the content as it's used and shared. You can use this classification to generate usage reports and see activity data for your sensitive content. Based on this information, you can always choose at a later time to apply protection settings.</span></span>
    
<span data-ttu-id="d5c48-p109">无论是上述哪种用途，Office 365 中的敏感度标签都可有助于对正确的内容执行适当的操作。借助敏感度标签，可对整个组织中的数据进行分类，并根据此分类强制执行保护设置。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p109">In all of these cases, sensitivity labels in Office 365 can help you take the right actions on the right content. With sensitivity labels, you can classify data across your organization and enforce protection settings based on that classification.</span></span>
  
<span data-ttu-id="d5c48-p110">在 Microsoft 365 合规中心、Microsoft 365 安全中心或 Office 365 安全与合规中心创建敏感度标签。这些敏感度标签可供 Azure 信息保护、Office 应用和 Office 365 服务使用。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p110">You create sensitivity labels in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center. These sensitivity labels can be used by Azure Information Protection, Office apps, and Office 365 services.</span></span>

<span data-ttu-id="d5c48-131">对于 Azure 信息保护客户，可以在其他管理中心内使用 Azure 信息保护标签。如果你选择执行其他配置或高级配置，这些标签便会与 Azure 门户同步。</span><span class="sxs-lookup"><span data-stu-id="d5c48-131">For Azure Information Protection customers, you can use your Azure Information Protection labels in the other admin centers, and your labels will be synced with the Azure portal in case you choose to perform additional or advanced configuration.</span></span> <span data-ttu-id="d5c48-132">**Azure 信息保护标签和 Office 365 敏感度标签彼此完全相互兼容。**</span><span class="sxs-lookup"><span data-stu-id="d5c48-132">**Azure Information Protection labels and Office 365 sensitivity labels are fully compatible with each other.**</span></span> <span data-ttu-id="d5c48-133">也就是说，例如，如果内容已有 Azure 信息保护标签，无需重新对此内容进行分类或标记。</span><span class="sxs-lookup"><span data-stu-id="d5c48-133">This means, for example, if you have content labeled by Azure Information Protection, you won’t need to reclassify or relabel your content.</span></span>

## <a name="what-a-sensitivity-label-is"></a><span data-ttu-id="d5c48-134">什么是敏感度标签</span><span class="sxs-lookup"><span data-stu-id="d5c48-134">What a sensitivity label is</span></span>

<span data-ttu-id="d5c48-135">向文档或电子邮件分配的敏感度标签就像是具有以下特征的标记：</span><span class="sxs-lookup"><span data-stu-id="d5c48-135">When you assign a sensitivity label to a document or email, it’s simply like a tag that is:</span></span>

- <span data-ttu-id="d5c48-p112">**可自定义**：可以为组织中不同级别的敏感内容创建类别，如“个人”、“公开”、“常规”、“机密”和“高度机密”。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p112">**Customizable.** You can create categories for different levels of sensitive content in your organization, such as Personal, Public, General, Confidential, and Highly Confidential.</span></span>

- <span data-ttu-id="d5c48-p113">**以明文形式显示**：由于敏感度标签以明文形式显示，因此第三方应用和服务可利用标签向已标记内容应用保护性操作。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p113">**Clear text.** Because the label is in clear text, it’s available for third-party apps and services to apply protective actions to labeled content.</span></span>

- <span data-ttu-id="d5c48-p114">**永久性**：向内容应用的敏感度标签在相应电子邮件或文档的元数据中暂留。也就是说，标签（包括保护设置）随内容一起漫游，并成为应用和强制执行策略的基础。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p114">**Persistent.** After a sensitivity label is applied to content, it persists in the metadata of that email or document. This means the label roams with the content, including the protection settings, and becomes the basis for applying and enforcing policies.</span></span>

<span data-ttu-id="d5c48-143">在 Office 应用中，敏感度标签只显示为电子邮件或文档上的标记。</span><span class="sxs-lookup"><span data-stu-id="d5c48-143">In the Office apps, a sensitivity label simply appears as a tag on an email or document.</span></span>

<span data-ttu-id="d5c48-p115">每个内容项都可以应用有一个敏感度标签。但请注意，一个内容项可以同时应用有一个敏感度标签和一个[保留标签](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p115">Each item of content can have a single sensitivity label applied to it. But note that an item can have both a single sensitivity label and a single [retention label](labels.md) applied to it.</span></span>

![应用于电子邮件的敏感度标签](media/Sensitivity_label_on_email.png)

## <a name="what-sensitivity-labels-can-do"></a><span data-ttu-id="d5c48-147">敏感度标签有何用途</span><span class="sxs-lookup"><span data-stu-id="d5c48-147">What sensitivity labels can do</span></span>

<span data-ttu-id="d5c48-p116">当电子邮件或文档应用有敏感度标签后，系统便会对内容强制执行相应标签的保护设置。敏感度标签可用于：</span><span class="sxs-lookup"><span data-stu-id="d5c48-p116">After a sensitivity label is applied to an email or document, the protection settings for that label are enforced on the content. With a sensitivity label, you can:</span></span>

- <span data-ttu-id="d5c48-p117">**加密**：仅加密电子邮件，或同时加密电子邮件和文档。可选择哪些用户或组在多长时间内有权执行哪些操作。例如，可选择允许组织外特定域中的用户，仅在内容应用有标签后的 7 天内有权查看相应内容。有关详细信息，请参阅[使用敏感度标签中的加密限制对内容的访问](encryption-sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p117">**Encrypt** email only or both email and documents. You can choose which users or group have permissions to perform which actions and for how long. For example, you can choose to allow users in a specific domain outside your organization to have permissions to review the content for only 7 days after the content is labeled. For more information, see [Restrict access to content by using encryption in sensitivity labels](encryption-sensitivity-labels.md).</span></span>

- <span data-ttu-id="d5c48-p118">**标记内容**：具体方法是将自定义水印、页眉或页脚添加到已应用有标签的电子邮件或文档中。请注意，水印只能应用于文档，不能应用于电子邮件。水印的长度上限为 255 个字符。此外，页眉和页脚的长度上限为 1024 个字符（但在 Excel 中除外，其中的长度上限为 255 个字符，具体取决于文档是否包含其他页眉或页脚和其他因素）。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p118">**Mark the content** by adding custom watermarks, headers, or footers to email or documents that have the label applied. Note that watermarks are applied only to documents, not email, and they're limited to 255 characters. Also, headers and footers are limited to 1024 characters (except in Excel, where they're limited to 255 characters or fewer, depending on whether the document contains other headers or footers and other factors.)</span></span>

    ![应用于文档的水印和页眉](media/Sensitivity_label_watermark_header.png)

- <span data-ttu-id="d5c48-p119">
  \*\*数据丢失防护\*\*：方法为启用 Intune 终结点保护。如果敏感内容已下载，可防止数据从 Windows 设备中丢失。例如，无法将已标记内容复制到 Dropbox、Gmail 或 U 盘。必须先在 Azure 门户中创建应用保护策略，敏感度标签才能使用 Windows 信息保护 (WIP)。有关详细信息，请参阅 [Windows 信息保护如何保护具有敏感度标签的文件](https://docs.microsoft.com/zh-CN/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p119">**Prevent data loss** by turning on endpoint protection in Intune. If sensitive content gets downloaded, you can help prevent the loss of data from Windows devices. For example, you can’t copy labeled content into Dropbox, Gmail, or USB drive. Before your sensitivity labels can use Windows Information Protection (WIP), you first need to create an app protection policy in the Azure portal. For more information, see [How Windows Information Protection protects files with a sensitivity label](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553).</span></span>

- <span data-ttu-id="d5c48-p120">**将标签应用到包含敏感信息的内容。** 你可以选择要标记的敏感信息类型，标签可以自动应用，也可以提示用户应用你推荐的标签。如果你推荐标签，则提示会显示你选择的任何文本。有关详细信息，请参阅[自动将敏感标签应用于内容](apply_sensitivity_label_automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p120">**Apply the label automatically to content that contains sensitive information.** You can choose what types of sensitive information that you want labeled, and the label can either be applied automatically, or you can prompt users to apply the label that you recommend. If you recommend a label, the prompt displays whatever text you choose. For more information, see [Apply a sensitivity label to content automatically](apply_sensitivity_label_automatically.md).</span></span>

    ![提示分配所需的标签](media/Sensitivity_label_Prompt_for_required_label.png)


<span data-ttu-id="d5c48-168">创建敏感度标签时即会提供以下所有选项。</span><span class="sxs-lookup"><span data-stu-id="d5c48-168">All of these options are available when you create a sensitivity label.</span></span>

![创建敏感度标签时可使用的选项](media/Sensitivity_label_create_options.png)

### <a name="label-priority-order-matters"></a><span data-ttu-id="d5c48-170">标签优先级（顺序非常重要）</span><span class="sxs-lookup"><span data-stu-id="d5c48-170">Label priority (order matters)</span></span>

<span data-ttu-id="d5c48-171">创建敏感度标签时，这些标签会显示在“标签”页的“敏感度”选项卡的列表中\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d5c48-171">When you create your sensitivity labels, they appear in a list on the **Sensitivity** tab on the **Labels** page.</span></span> <span data-ttu-id="d5c48-172">此列表中的标签顺序至关重要，因为它反映了标签的优先级。</span><span class="sxs-lookup"><span data-stu-id="d5c48-172">In this list, the order of the labels is important because it reflects their priority.</span></span> <span data-ttu-id="d5c48-173">限制性最高的敏感度标签（如“高度机密”）需显示在此列表的**底部**，限制性最低的敏感度标签（如“公开”）需显示在**顶部**。</span><span class="sxs-lookup"><span data-stu-id="d5c48-173">You want your most restrictive sensitivity label, such as Highly Confidential, to appear at the **bottom** of the list, and your least restrictive sensitivity label, such as Public, to appear at the **top**.</span></span>

<span data-ttu-id="d5c48-p122">一个文档或电子邮件只能应用有一个敏感度标签。若有要求用户必须提供将标签更改为较低分类的理由，理由可以是此列表的排序，因为它决定了较低分类是什么。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p122">A document or email can have only a single sensitivity label applied to it. If you require your users to provide a justification for changing the label to a lower classification, the order of this list determines what's a lower classification.</span></span>

![子标签创建选项](media/Sensitivity_label_sublabel_options.png)

<span data-ttu-id="d5c48-177">请注意，除了标签优先级之外，标签策略的顺序也很重要 - 请参阅[下面的此部分](#sensitivity-label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="d5c48-177">Note that in addition to label priority, the order of the label policies also matters - see [this section below](#sensitivity-label-priority-order-matters).</span></span>

### <a name="sublabels-grouping-labels"></a><span data-ttu-id="d5c48-178">子标签（对标签进行分组）</span><span class="sxs-lookup"><span data-stu-id="d5c48-178">Sublabels (grouping labels)</span></span>

<span data-ttu-id="d5c48-179">使用子标签，你可以将一个或多个标签分组到用户在 Office 应用程序中看到的父标签下方。</span><span class="sxs-lookup"><span data-stu-id="d5c48-179">With sublabels, you can group one or more labels below a parent label that a user sees in an Office app.</span></span> <span data-ttu-id="d5c48-180">例如，在“机密”下，你的组织可能会为该分类的特定类型使用多个不同的标签。</span><span class="sxs-lookup"><span data-stu-id="d5c48-180">For example, under Confidential, your organization might use several different labels for specific types of that classification.</span></span> <span data-ttu-id="d5c48-181">在此示例中，父标签“机密”仅仅是没有保护设置的文本标签，并且因为它具有子标签，所以它不能应用于内容。</span><span class="sxs-lookup"><span data-stu-id="d5c48-181">In this example, the parent label Confidential is simply a text label with no protection settings, and because it has sublabels, it can’t be applied to content.</span></span> <span data-ttu-id="d5c48-182">相反，用户必须选择“机密”才能查看子标签，然后他们可以选择要应用于内容的子标签。</span><span class="sxs-lookup"><span data-stu-id="d5c48-182">Instead, users must choose Confidential to view the sublabels, and then they can choose a sublabel to apply to content.</span></span>

<span data-ttu-id="d5c48-183">子标签只是向逻辑组中的用户显示标签的一种方式。</span><span class="sxs-lookup"><span data-stu-id="d5c48-183">Sublabels are simply a way to present labels to users in logical groups.</span></span> <span data-ttu-id="d5c48-184">子标签不会从其父标签继承任何设置。</span><span class="sxs-lookup"><span data-stu-id="d5c48-184">Sublabels don’t inherit any settings from their parent label.</span></span> <span data-ttu-id="d5c48-185">子标签可以应用于内容；父标签不能。</span><span class="sxs-lookup"><span data-stu-id="d5c48-185">Sublabels can be applied to content; parent labels cannot.</span></span>

<span data-ttu-id="d5c48-186">（另外，不应选择父标签作为默认标签（请参阅下一节），或将父标签配置为自动应用或推荐使用，因为父标签不会应用于使用 Azure 信息保护统一标签客户端的 Office 应用程序中的内容。）</span><span class="sxs-lookup"><span data-stu-id="d5c48-186">(Also, you should not choose a parent label as the default label (see next section), or configure a parent label to be auto-applied or recommended, because the parent label won't be applied to content in Office apps that use the Azure Information Protection unified labeling client.)</span></span>

![功能区上的已分组子标签](media/Sensitivity_label_grouped_labels.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a><span data-ttu-id="d5c48-188">编辑或删除敏感度标签</span><span class="sxs-lookup"><span data-stu-id="d5c48-188">Editing or deleting a sensitivity label</span></span>

<span data-ttu-id="d5c48-189">如果删除敏感度标签，请注意标签并未从内容中删除，且对内容继续强制执行所有保护设置。</span><span class="sxs-lookup"><span data-stu-id="d5c48-189">If you delete a sensitivity label, note that the label is not removed from content, and any protection settings continue to be enforced on the content.</span></span>

<span data-ttu-id="d5c48-190">如果编辑敏感度标签，应用于内容的标签版本就是对相应内容强制执行的标签。</span><span class="sxs-lookup"><span data-stu-id="d5c48-190">If you edit a sensitivity label, the version of the label that was applied to content is what’s enforced on that content.</span></span>

## <a name="what-label-policies-can-do"></a><span data-ttu-id="d5c48-191">标签策略有何用途</span><span class="sxs-lookup"><span data-stu-id="d5c48-191">What label policies can do</span></span>

<span data-ttu-id="d5c48-p125">创建敏感度标签后，需要发布它们，以便组织内人员能够将标签应用于内容。与发布到所有 Exchange 邮箱等位置的保留标签不同，敏感度标签是发布到用户或组。然后，敏感度标签便会显示在这些用户或组的 Office 应用中。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p125">After you create your sensitivity labels, you need to publish them, to make them available to people in your organization, who can then apply the labels to content. Unlike retention labels, which are published to locations, such as all Exchange mailboxes, sensitivity labels are published to users or groups. Sensitivity labels then appear in Office apps for those users and groups.</span></span>

<span data-ttu-id="d5c48-195">借助标签策略，你可以：</span><span class="sxs-lookup"><span data-stu-id="d5c48-195">With a label policy, you can:</span></span>

- <span data-ttu-id="d5c48-p126">**选择向哪些用户和组显示标签。** 可以将标签发布到任意启用电子邮件的安全组、通讯组、Office 365 组或动态通讯组。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p126">**Choose which users and groups see the labels.** Labels can be published to any email-enabled security group, distribution group, Office 365 group, or dynamic distribution group.</span></span>

- <span data-ttu-id="d5c48-p127">**将默认标签应用于**标签策略包含的用户和组新建的所有文档和电子邮件。此默认标签可设置要对所有内容应用的保护设置的基本级别。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p127">**Apply a default label** to all new documents and email created by the users and groups included in the label policy. This default label can set a base level of protection settings that you want applied to all your content.</span></span>

- <span data-ttu-id="d5c48-p128">**要求提供更改标签的理由。** 如果内容应用有“机密”标签，但用户要删除此标签或将它替换为较低分类（如“公开”标签），你可以要求用户必须在执行此操作时提供理由。这些理由可供管理员查看。目前，我们正在努力推出可供管理员查看用户理由的报告。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p128">**Require a justification for changing a label.** If content is marked Confidential and a user wants to remove that label or replace it with a lower classification, such as a label named Public, you can require that the user provide a justification when performing this action. These justifications will be available for the admin to review. We’re currently working on a report where admins can view the user justifications.</span></span>

    ![提示用户输入理由的页面](media/Sensitivity_label_justification_required.png)

- <span data-ttu-id="d5c48-p129">**要求用户将标签应用于他们的电子邮件和文档。** 如果你希望标记用户的所有内容，则可以要求必须将标签应用于所有已保存的文档和已发送的电子邮件。标签可以由用户手动分配、按条件自动分配或者进行默认分配（上述默认标签选项）。以下是当要求用户分配标签时 Outlook 中显示的提示。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p129">**Require users to apply a label to their email and documents.** If you want all of a user's content to be labeled, you can require that a label must be applied to all of their saved documents and sent emails. The label can be assigned manually by the user, automatically as a result of a condition, or be assigned by default (the default label option described above). Here's the prompt shown in Outlook when a user is required to assign a label.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d5c48-p130">要使用强制标签，需要具备 Azure 信息保护订阅。要使用此功能，必须下载并安装 [Azure 信息保护客户端](https://www.microsoft.com/en-us/download/details.aspx?id=53018)或后续的 [Azure 信息保护统一标签客户端](https://docs.microsoft.com/zh-CN/azure/information-protection/rms-client/install-unifiedlabelingclient-app)。我们正在设法实现 Office 应用对此功能的本机支持，因此届时将不需要 Azure 信息保护客户端。此外，客户端仅在 Windows 上运行，因此 Mac、iOS 和 Android 上尚不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p130">Mandatory labeling requires an Azure Information Protection subscription. To use this feature, you must download and install either the [Azure Information Protection client](https://www.microsoft.com/en-us/download/details.aspx?id=53018) or the later [Azure Information Protection unified labeling client](https://docs.microsoft.com/en-us/azure/information-protection/rms-client/install-unifiedlabelingclient-app). We're working on native support for this feature in Office apps, so that it won't require the Azure Information Protection client. Also, the client runs only on Windows, so this feature is not yet supported on Mac, iOS, and Android.</span></span>

    ![在 Outlook 中要求用户应用所需标签的提示](media/sensitivity_labels_mandatory_prompt_aipv2_outlook.PNG)

- <span data-ttu-id="d5c48-p131">**提供指向自定义帮助页的帮助链接。** 如果用户不确定敏感度标签的含义或应如何使用标签，你可以提供在 Office 应用中“敏感度”标签菜单底部显示的“了解更多”URL。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p131">**Provide help link to a custom help page.** If your users aren’t sure what your sensitivity labels mean or how they should be used, you can provide a Learn More URL that appears at the bottom of the Sensitivity label menu in the Office apps.</span></span>

    ![功能区上“敏感度”按钮中的“了解更多”链接](media/Sensitivity_label_learn_more.png)

<span data-ttu-id="d5c48-217">在你创建标签策略并将敏感度标签分配给用户和组后，这些人员会在不超过一小时的时间内在 Office 应用中看到这些标签。</span><span class="sxs-lookup"><span data-stu-id="d5c48-217">After you create a label policy and assign sensitivity labels to users and groups, those people will see those labels available in the Office apps in an hour or less.</span></span>

### <a name="label-policy-priority-order-matters"></a><span data-ttu-id="d5c48-218">标签策略优先级（顺序非常重要）</span><span class="sxs-lookup"><span data-stu-id="d5c48-218">Label priority (order matters)</span></span>

<span data-ttu-id="d5c48-219">你可以通过在敏感度标签策略中发布敏感度标签来向用户提供敏感度标签，该策略显示在“**标签策略**”页的“**敏感度策略**”选项卡的列表中。</span><span class="sxs-lookup"><span data-stu-id="d5c48-219">You make your sensitivity labels available to users by publishing them in a sensitivity label policy, which appears in a list on the **Sensitivity policies** tab on the **Label policies** page.</span></span> <span data-ttu-id="d5c48-220">正如敏感度标签（参见[上面的部分](#sensitivity-label-priority-order-matters)）一样，敏感度标签策略的顺序很重要，因为它反映了它们的优先级。</span><span class="sxs-lookup"><span data-stu-id="d5c48-220">Just like sensitivity labels (see [the above section](#sensitivity-label-priority-order-matters)), the order of the sensitivity label policies is important because it reflects their priority.</span></span> <span data-ttu-id="d5c48-221">优先级最低的标签策略显示在**顶部**，优先级最高的标签策略显示在**底部**。</span><span class="sxs-lookup"><span data-stu-id="d5c48-221">The label policy with lowest priority is shown at the **top**, and label policy with the highest priority is shown at the **bottom**.</span></span>

<span data-ttu-id="d5c48-222">标签策略包括：</span><span class="sxs-lookup"><span data-stu-id="d5c48-222">A label policy consists of:</span></span>

- <span data-ttu-id="d5c48-223">一组标签。</span><span class="sxs-lookup"><span data-stu-id="d5c48-223">A set of modules.</span></span>
- <span data-ttu-id="d5c48-224">标签策略的范围，表示策略中包含的用户和组。</span><span class="sxs-lookup"><span data-stu-id="d5c48-224">The scope of the label policy, meaning the users and groups included in the policy.</span></span>
- <span data-ttu-id="d5c48-225">上述标签策略的设置（默认标签、对齐方式、强制标签和帮助链接）。</span><span class="sxs-lookup"><span data-stu-id="d5c48-225">The settings of the label policy described above (default label, justification, mandatory label, and help link).</span></span>

<span data-ttu-id="d5c48-226">可以在多个标签策略中包含某个用户，该用户将看到这些策略中的所有敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="d5c48-226">You can include a user in multiple label policies, and the user will see all of the sensitivity labels from those policies.</span></span> <span data-ttu-id="d5c48-227">但是，用户将只看到具有最高优先级的标签策略中的策略设置。</span><span class="sxs-lookup"><span data-stu-id="d5c48-227">However, a user will see only the policy settings from the label policy with the highest priority.</span></span>

<span data-ttu-id="d5c48-228">如果组织中的用户或组在标签策略中没有看到你想要的选项（例如默认标签或强制标签），请检查敏感度标签策略的顺序。</span><span class="sxs-lookup"><span data-stu-id="d5c48-228">If a user or group in your organization is not seeing an option in the label policy that you intended, such as a default or mandatory label, check the order of the sensitivity label policies.</span></span> <span data-ttu-id="d5c48-229">若要重新排序标签策略，请选择某个敏感度标签策略 > 选择右侧的省略号 >“**下移**”或“**上移**”。</span><span class="sxs-lookup"><span data-stu-id="d5c48-229">To re-order the label policies, select a sensitivity label policy > choose the ellipsis on the right > **Move down** or **Move up**.</span></span>

![敏感度标签策略页上的移动选项](media/sensitivity-label-policy-priority.png)

<span data-ttu-id="d5c48-231">请注意，虽然敏感度标签策略的优先级很重要，但保留标签策略的优先级并**不**重要。</span><span class="sxs-lookup"><span data-stu-id="d5c48-231">Note that while priority matters for sensitivity label policies, it does **not** matter for retention label policies.</span></span> <span data-ttu-id="d5c48-232">如[保留原则或优先原则？](labels.md#the-principles-of-retention-or-what-takes-precedence)中所述，内容可能受多个保留策略的约束。</span><span class="sxs-lookup"><span data-stu-id="d5c48-232">As explained in [The principles of retention, or what takes precedence?](labels.md#the-principles-of-retention-or-what-takes-precedence), content can be subject to multiple retention policies.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="d5c48-233">如何开始使用</span><span class="sxs-lookup"><span data-stu-id="d5c48-233">How to get started</span></span>

<span data-ttu-id="d5c48-234">敏感度标签可快速上手：</span><span class="sxs-lookup"><span data-stu-id="d5c48-234">Getting started with sensitivity labels is a quick process:</span></span>

1. <span data-ttu-id="d5c48-p136">**定义标签。** 首先要建立分类，用于定义各种敏感内容级别。应使用用户能理解的常见名称或术语。例如，可以从“个人”、“公开”、“常规”、“机密”和“高度机密”等标签入手。可利用子标签按类别对相似标签进行分组。此外，创建标签时，还需要提供工具提示，即用户将鼠标悬停在功能区中的某个标签选项时在 Office 应用中看到的提示。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p136">**Define the labels.** First, you want to establish your taxonomy for defining different levels of sensitive content. You should use common names or terms that make sense to your users. For example, you can start with labels such as Personal, Public, General, Confidential, and Highly Confidential. You can use sublabels to group similar labels by category. Also, when you create a label, a tool tip is required, which appears in the Office apps when a user hovers over a label option on the Ribbon.</span></span>

1. <span data-ttu-id="d5c48-p137">**定义每个标签有何用途。** 然后，配置要与每个标签关联的保护设置。例如，较低敏感度内容（应用有“常规”标签）可以只应用有页眉或页脚，而较高敏感度内容（应用有“机密”标签）则可以应用有水印、加密和 WIP，这样有助于确保只有特权用户才能访问它。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p137">**Define what each label can do.** Then, configure the protection settings you want associated with each label. For example, lower sensitivity content (a “General” label) might simply have a header or footer applied to it, while higher sensitivity content (a “Confidential” label) may have a watermark, encryption, and WIP applied to it, to help ensure that only privileged users can access it.</span></span>
 
1. <span data-ttu-id="d5c48-p138">**定义谁能获取标签。** 定义组织的标签后，通过标签策略发布它们。标签策略控制了哪些用户和组能看到这些标签。一个标签是可重用的。也就是说，定义标签一次后，可将它添加到分配给不同用户的多个标签策略。不过，必须先发布相应标签，使其显示在 Office 应用或其他服务中，然后才能将标签分配给内容。刚开始的时候，可尝试仅将敏感度标签分配给少数几个人员。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p138">**Define who gets the labels.** After you define your organization’s labels, you publish them in a label policy that controls which users and groups see those labels. A single label is reusable – you define it once, and then you can include it in several label policies assigned to different users. But in order for a label to be assigned to content, you must first publish that label so that it’s available in Office apps and other services. When just starting out, you can pilot your sensitivity labels by assigning them to just a few people.</span></span>

<span data-ttu-id="d5c48-249">下面的基本流展示了管理员、用户和 Office 应用为了让敏感度标签起作用所要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d5c48-249">Here’s the basic flow of what the admin, user, and Office app do to make sensitivity labels work.</span></span>

![敏感度标签工作流关系图](media/Sensitivity_label_flow.png)

## <a name="where-sensitivity-labels-can-appear"></a><span data-ttu-id="d5c48-251">敏感度标签可以显示在哪里</span><span class="sxs-lookup"><span data-stu-id="d5c48-251">Where sensitivity labels can appear</span></span>

<span data-ttu-id="d5c48-p139">敏感度标签显示在 Office 应用 UI 中。若要查看敏感度标签对特定应用和平台的最新适用情况，请参阅**[此功能目前在何处适用？](https://support.office.com/zh-CN/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9?ad=US&ui=en-US&rs=en-US#bkmk_whereavailable)**</span><span class="sxs-lookup"><span data-stu-id="d5c48-p139">Sensitivity labels appear in the UI of Office apps. To view the current availability for specific apps and platforms, see **[Where is the feature available today?](https://support.office.com/en-us/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9?ad=US&ui=en-US&rs=en-US#bkmk_whereavailable)**</span></span>

### <a name="office-apps-on-windows"></a><span data-ttu-id="d5c48-254">Windows 上的 Office 应用</span><span class="sxs-lookup"><span data-stu-id="d5c48-254">Office apps on Windows</span></span>

<span data-ttu-id="d5c48-p140">在 Windows 设备上的 Office 应用中，敏感度标签显示在功能区上“开始”\*\*\*\* 选项卡的“敏感度”\*\*\*\* 按钮中。已应用的标签还显示在窗口底部的状态栏中。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p140">In Office apps on devices running Windows, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

<span data-ttu-id="d5c48-257">我们即将推出对 Windows 上 Office 应用中敏感度标签的本机支持。</span><span class="sxs-lookup"><span data-stu-id="d5c48-257">Coming soon is native support for sensitivity labels in Office apps on Windows.</span></span>

<span data-ttu-id="d5c48-p141">如果已是 Azure 信息保护客户，可以部署 Azure 信息保护统一标记客户端。此客户端支持敏感度标签。有关下载此客户端的更多信息，请参阅 [Azure 信息保护统一标记客户端：版本发布信息](https://docs.microsoft.com/zh-CN/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)目前，我们正在努力推出对 Windows 上 Office 应用中敏感度标签的本机支持，所以届时将无需再使用 Azure 信息保护统一标记客户端。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p141">If you're an existing Azure Information Protection customer, you can deploy the Azure Information Protection unified labeling client, which supports sensitivity labels. For more information about downloading the client, see [Azure Information Protection unified labeling client: Version release information](https://docs.microsoft.com/en-us/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). We’re currently working on native support for sensitivity labels in Office apps on Windows, so that the Azure Information Protection unified labeling client will no longer be required.</span></span>

![Windows 上 Excel 功能区中的“敏感度”按钮](media/Sensitivity_label_Sensitivity_button.png)

### <a name="office-apps-on-mac"></a><span data-ttu-id="d5c48-262">Mac 上的 Office 应用</span><span class="sxs-lookup"><span data-stu-id="d5c48-262">Office apps on Mac</span></span>

<span data-ttu-id="d5c48-p142">在 Mac 设备上的 Office 应用中，敏感度标签显示在功能区上“开始”\*\*\*\* 选项卡的“敏感度”\*\*\*\* 按钮中。已应用的标签还显示在窗口底部的状态栏中。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p142">In Office apps on Mac devices, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

![Mac 上 Office 功能区中的“敏感度”按钮](media/Sensitivity_label_on_Mac.png)

### <a name="office-apps-on-ios"></a><span data-ttu-id="d5c48-266">iOS 上的 Office 应用</span><span class="sxs-lookup"><span data-stu-id="d5c48-266">Office apps on iOS</span></span>

<span data-ttu-id="d5c48-p143">在 iOS 设备上的 Office 应用中，敏感度标签显示在功能区上“开始”\*\*\*\* 选项卡的“敏感度”\*\*\*\* 按钮中。已应用的标签还显示在窗口底部的状态栏中。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p143">In Office apps on iOS devices, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

![iOS 上 Office 功能区中的“敏感度”按钮](media/Sensitivity_label_on_iOS.png)

### <a name="office-apps-on-android"></a><span data-ttu-id="d5c48-270">Android 上的 Office 应用</span><span class="sxs-lookup"><span data-stu-id="d5c48-270">Office apps on Android</span></span>

<span data-ttu-id="d5c48-p144">在 Android 设备上的 Office 应用中，敏感度标签显示在功能区上“开始”\*\*\*\* 选项卡的“敏感度”\*\*\*\* 按钮中。已应用的标签还显示在窗口底部的状态栏中。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p144">In Office apps on Android devices, sensitivity labels appear on the **Sensitivity** button, on the **Home** tab on the Ribbon. The label applied also appears in the Status bar at the bottom of the window.</span></span>

![Android 上 Office 功能区中的“敏感度”按钮](media/Sensitivity_label_on_Android.png)

### <a name="more-information-on-sensitivity-labels-in-office-apps"></a><span data-ttu-id="d5c48-274">详细了解 Office 应用中的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="d5c48-274">More information on sensitivity labels in Office apps</span></span>

- <span data-ttu-id="d5c48-275">
  [将敏感度标签应用于 Office 文档和电子邮件](https://support.office.com/zh-CN/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)</span><span class="sxs-lookup"><span data-stu-id="d5c48-275">[Apply sensitivity labels to your documents and email within Office](https://support.office.com/en-us/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)</span></span>
- <span data-ttu-id="d5c48-276">
  [将敏感度标签应用于 Office 文件时的已知问题](https://support.office.com/zh-CN/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)</span><span class="sxs-lookup"><span data-stu-id="d5c48-276">[Known issues when you apply sensitivity labels to your Office files](https://support.office.com/en-us/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)</span></span>

## <a name="how-sensitivity-labels-work-with-existing-azure-information-protection-labels"></a><span data-ttu-id="d5c48-277">如何结合使用敏感度标签与现有 Azure 信息保护标签</span><span class="sxs-lookup"><span data-stu-id="d5c48-277">How sensitivity labels work with existing Azure Information Protection labels</span></span>

<span data-ttu-id="d5c48-p145">目前，Azure 信息保护用户可使用 Azure 信息保护统一标记客户端，对 Windows 上的内容进行分类和标记。可顺畅地结合使用现有 Azure 信息保护标签与新敏感度标签。也就是说，可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d5c48-p145">Azure Information Protection users are currently able to classify and label content on Windows by using the Azure Information Protection unified labeling client. Existing Azure Information Protection labels work seamlessly with new sensitivity labels. This means you can:</span></span>

- <span data-ttu-id="d5c48-281">保留文档和电子邮件中的现有 Azure 信息保护标签。</span><span class="sxs-lookup"><span data-stu-id="d5c48-281">Keep your existing Azure Information Protection labels on documents and email.</span></span>
- <span data-ttu-id="d5c48-282">保留现有 Azure 信息保护标签配置。</span><span class="sxs-lookup"><span data-stu-id="d5c48-282">Keep your existing Azure Information Protection label configuration.</span></span>

<span data-ttu-id="d5c48-283">如果目前使用的是 Azure 信息保护标签，在你完成迁移前，建议避免在其他管理中心创建新标签。</span><span class="sxs-lookup"><span data-stu-id="d5c48-283">If you are using Azure Information Protection labels, for now we recommend that you avoid creating new labels in other admin centers until after you’ve completed your migration.</span></span> <span data-ttu-id="d5c48-284">
  [Azure 信息保护迁移主题](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-policy-migrate-labels)包含重要信息以及一些特定的注意事项。</span><span class="sxs-lookup"><span data-stu-id="d5c48-284">The [Azure Information Protection migration topic](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-migrate-labels) has important information and some specific caveats.</span></span> <span data-ttu-id="d5c48-285">如果尚未准备好将生产租户迁移到敏感度标签，也无需担心：目前用户可以继续使用 Azure 信息保护客户端，管理员可以继续使用 Azure 门户进行管理。</span><span class="sxs-lookup"><span data-stu-id="d5c48-285">If you are not yet ready to migrate your production tenants to sensitivity labels, there is no cause for concern: for the moment, your users can continue using the Azure Information Protection client, and admins can continue using the Azure portal for management.</span></span>

## <a name="protect-content-on-windows-devices-by-using-endpoint-protection-in-microsoft-intune"></a><span data-ttu-id="d5c48-286">使用 Microsoft Intune 终结点保护来保护 Windows 设备上的内容</span><span class="sxs-lookup"><span data-stu-id="d5c48-286">Protect content on Windows devices by using endpoint protection in Microsoft Intune</span></span>

<span data-ttu-id="d5c48-p147">创建敏感度标签时，可视需要指示 Windows 具有此标签的文件是敏感内容，需要保护存储在 Windows 设备上的此类文件，以防发生数据泄露。此选项有助于确保具有此标签的内容只能共享或复制到批准的位置上，即使内容存储在终结点上，也不例外。实际上，如果对敏感度标签启用此选项，便是在指示 Windows 这是非常关键的数据，有必要施加额外使用限制。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p147">When you create a sensitivity label, you have the option to tell Windows that files with this label are sensitive and need to be protected against data leakage when stored on Windows devices. This option can help ensure that content with this label can be shared or copied only to sanctioned locations, even when it’s stored on an endpoint. In essence, turning on this option for a sensitivity label tells Windows that this is extra critical data that warrants additional usage constraints.</span></span>

<span data-ttu-id="d5c48-p148">当你启用此选项后，Windows 便能读取、理解和处理文档中的敏感度标签，并自动对内容应用 Windows 信息保护 (WIP)，无论内容是以何种方式到达 Windows 托管设备的。这样有助于防止已标记文件发生意外数据泄露，无论是否应用加密。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p148">When you turn on this option, Windows can read, understand, and act on sensitivity labels in documents and automatically apply Windows Information Protection (WIP) on content, no matter how it reaches a managed Windows device. This helps protect labeled files from accidental leakage, with or without applying encryption.</span></span>

<span data-ttu-id="d5c48-292">例如，Windows 可知道驻留在用户计算机上的 Word 文档已应用有“机密”标签，WIP 可应用应用保护策略，以防相应设备中的数据被复制或共享到任何非工作位置（如个人 OneDrive、个人电子邮件帐户、社交媒体或 U 盘）。</span><span class="sxs-lookup"><span data-stu-id="d5c48-292">For example, Windows can understand that a Word document residing on a user’s machine has a Confidential label applied to it, and WIP can apply an app protection policy to prevent the copying or sharing of the data to any non-work location from that device (such as a personal OneDrive, personal email accounts, social media, or USB drives).</span></span>

<span data-ttu-id="d5c48-293">如果用户试图将已标记内容上传到个人 Gmail 帐户，便会看到以下消息。</span><span class="sxs-lookup"><span data-stu-id="d5c48-293">If a user attempts to upload labeled content to a personal Gmail account, they see this message.</span></span>

![提示无法将已标记内容复制到 Gmail 的消息](media/Sensitivity_label_WIP_Gmail.png)

<span data-ttu-id="d5c48-295">此外，如果用户试图将已标记内容保存到 U 盘，还会看到以下消息。</span><span class="sxs-lookup"><span data-stu-id="d5c48-295">And if a user attempts to save labeled content to a USB drive, they see this message.</span></span>

![提示无法将已标记内容保存到 U 盘的消息](media/Sensitivity_label_WIP_USB_drive.png)

### <a name="important-prerequisites"></a><span data-ttu-id="d5c48-297">重要先决条件</span><span class="sxs-lookup"><span data-stu-id="d5c48-297">Important prerequisites</span></span>

<span data-ttu-id="d5c48-p149">必须先满足 [Windows 信息保护如何保护具有敏感度标签的文件](https://docs.microsoft.com/zh-CN/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553)中提及的先决条件，然后敏感度标签才能使用 WIP。这篇主题提及以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="d5c48-p149">Before your sensitivity labels can use WIP, you first need to do the prerequisites described here: [How Windows Information Protection protects files with a sensitivity label](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553). This topic describes the following prerequisites:</span></span>

- <span data-ttu-id="d5c48-300">确保运行的是 Windows 10 版本 1809 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d5c48-300">Make sure you're running Windows 10, version 1809 or later.</span></span>
- <span data-ttu-id="d5c48-p150">
  [设置 Windows Defender 高级威胁防护 (WDATP)](https://docs.microsoft.com/zh-CN/windows/security/threat-protection/windows-defender-atp/get-started)，以扫描内容中是否有标签，并应用相应的 WIP 保护。ATP 与 WIP 分开执行一些操作，如报告异常。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p150">[Set up Windows Defender Advanced Threat Protection (WDATP)](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-atp/get-started), which scans content for a label and applies the corresponding WIP protection. ATP performs some actions independently from WIP, such as reporting anomalies.</span></span>
- <span data-ttu-id="d5c48-p151">创建适用于终结点设备的 Windows 信息保护 (WIP) 策略。可以在下列两个位置之一执行此操作：</span><span class="sxs-lookup"><span data-stu-id="d5c48-p151">Create a Windows Information Protection (WIP) policy that applies to endpoint devices. You can do this in either of these locations:</span></span>
    - <span data-ttu-id="d5c48-305">
  [使用适用于 Microsoft Intune 的 Azure 门户通过 MDM 创建 Windows 信息保护 (WIP) 策略](https://docs.microsoft.com/zh-CN/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span><span class="sxs-lookup"><span data-stu-id="d5c48-305">[Create a Windows Information Protection (WIP) policy with MDM using the Azure portal for Microsoft Intune](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span></span>
    - <span data-ttu-id="d5c48-306">
  [使用 System Center Configuration Manager 创建并部署 Windows 信息保护 (WIP) 策略](https://docs.microsoft.com/zh-CN/windows/security/information-protection/windows-information-protection/create-wip-policy-using-sccm)</span><span class="sxs-lookup"><span data-stu-id="d5c48-306">[Create and deploy a Windows Information Protection (WIP) policy using System Center Configuration Manager](https://docs.microsoft.com/en-us/windows/security/information-protection/windows-information-protection/create-wip-policy-using-sccm)</span></span>

## <a name="protect-content-in-third-party-apps-and-services-by-using-microsoft-cloud-app-security"></a><span data-ttu-id="d5c48-307">利用 Microsoft Cloud App Security 保护第三方应用和服务中的内容</span><span class="sxs-lookup"><span data-stu-id="d5c48-307">Protect content in third-party apps and services by using Microsoft Cloud App Security</span></span>

<span data-ttu-id="d5c48-308">利用 Cloud App Security (CAS) 保护第三方应用和服务中的内容。</span><span class="sxs-lookup"><span data-stu-id="d5c48-308">Protect content in third-party apps and services by using Cloud App Security (CAS).</span></span> <span data-ttu-id="d5c48-309">借助 CAS，可检测、分类、标记和保护第三方服务和应用（如 SalesForce、Box 或 Dropbox）中的内容。</span><span class="sxs-lookup"><span data-stu-id="d5c48-309">With CAS, you can detect, classify, label, and protect content in third-party services and apps, such as SalesForce, Box, or Dropbox.</span></span> <span data-ttu-id="d5c48-310">例如，Dropbox 可能无法理解敏感度标签，但 CAS 可访问并保护该位置中带标签的内容。</span><span class="sxs-lookup"><span data-stu-id="d5c48-310">For example, Dropbox might not understand a sensitivity label, but CAS can reach out and protect labeled content in that location.</span></span>

<span data-ttu-id="d5c48-311">有关详细信息，请参阅[自动应用 Azure 信息保护分类标签](https://docs.microsoft.com/zh-CN/cloud-app-security/use-case-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="d5c48-311">For more information, see [Automatically apply Azure Information Protection classification labels](https://docs.microsoft.com/en-us/cloud-app-security/use-case-information-protection).</span></span>

### <a name="important-prerequisites"></a><span data-ttu-id="d5c48-312">重要先决条件</span><span class="sxs-lookup"><span data-stu-id="d5c48-312">Important prerequisites</span></span>

<span data-ttu-id="d5c48-313">必须先满足[自动应用 Azure 信息保护分类标签](https://docs.microsoft.com/zh-CN/cloud-app-security/use-case-information-protection)中提及的先决条件，这样敏感度标签才能使用 CAS。</span><span class="sxs-lookup"><span data-stu-id="d5c48-313">Before your sensitivity labels can use CAS, you first need to do the prerequisites described here: [Automatically apply Azure Information Protection classification labels](https://docs.microsoft.com/en-us/cloud-app-security/use-case-information-protection).</span></span> <span data-ttu-id="d5c48-314">本主题介绍了以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="d5c48-314">This topic describes the following prerequisites:</span></span>

- <span data-ttu-id="d5c48-315">为租户[启用 Cloud App Security 和 Azure 信息保护](https://docs.microsoft.com/zh-CN/cloud-app-security/azip-integration)。</span><span class="sxs-lookup"><span data-stu-id="d5c48-315">[Enable Cloud App Security and Azure Information Protection](https://docs.microsoft.com/en-us/cloud-app-security/azip-integration) for your tenant.</span></span>
- <span data-ttu-id="d5c48-316">
  [将应用连接到](https://docs.microsoft.com/zh-CN/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps) Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="d5c48-316">[Connect the app](https://docs.microsoft.com/en-us/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps) to Cloud App Security.</span></span>

## <a name="extend-sensitivity-labels-to-third-party-apps-and-services-by-using-the-microsoft-information-protection-sdk"></a><span data-ttu-id="d5c48-317">使用 Microsoft 信息保护 SDK 将敏感度标签扩展到第三方应用和服务</span><span class="sxs-lookup"><span data-stu-id="d5c48-317">Extend sensitivity labels to third-party apps and services by using the Microsoft Information Protection SDK</span></span>

<span data-ttu-id="d5c48-p154">由于敏感度标签以明文形式暂留在文档的元数据中，因此第三方应用和服务可选择支持识别和保护包含此类标签的内容。我们会一直扩大对其他应用和服务的支持。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p154">Because a sensitivity label is persisted as clear text in the metadata of a document, third-party apps and services can choose to support identifying and protecting content that contains such a label. Support in other apps and services is always expanding.</span></span>

<span data-ttu-id="d5c48-p155">借助 [Microsoft 信息保护 SDK](https://docs.microsoft.com/zh-CN/information-protection/develop/)，第三方应用和服务可读取敏感度标签，并向文档应用敏感度标签和保护设置。此 SDK 支持 Windows、Mac 和 Linux 上的应用。我们即将推出对 iOS 和 Android 上应用的支持。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p155">With the [Microsoft Information Protection SDK](https://docs.microsoft.com/en-us/information-protection/develop/), third-party apps and services can read and apply sensitivity labels and protection to documents. The SDK supports apps on Windows, Mac, and Linux. Coming soon is support for apps on iOS and Android.</span></span>

<span data-ttu-id="d5c48-p156">借助此 SDK，可以标记和保护内容，且方式与其他 Microsoft 信息保护应用和服务（如 Office 应用、Office 365 服务、Azure 信息保护扫描程序、Microsoft Cloud App Security 及其他多个合作伙伴解决方案）兼容。有关示例，请详细了解 [Adobe Acrobat 中的敏感度标签支持](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738)。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p156">Using the SDK, you can label and protect content in a way that works with other Microsoft Information Protection apps and services, such as Office apps, Office 365 services, the Azure Information Protection scanner, Microsoft Cloud App Security, and several other partner solutions. For example, learn more about [support for sensitivity labels in Adobe Acrobat](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738).</span></span>

<span data-ttu-id="d5c48-p157">若要详细了解 Microsoft 信息保护 SDK，请参阅[技术社区博客公告](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144)。此外，还可以了解[与 Microsoft 信息保护集成的合作伙伴解决方案](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657)。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p157">To learn more about the Microsoft Information Protection SDK, see the [announcement on the Tech Community blog](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144). You can also learn about [partner solutions that are integrated with Microsoft Information Protection](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657).</span></span>

## <a name="permissions"></a><span data-ttu-id="d5c48-327">权限</span><span class="sxs-lookup"><span data-stu-id="d5c48-327">Permissions</span></span>

<span data-ttu-id="d5c48-p158">若为创建敏感度标签的合规性团队成员，必须有权访问安全与合规中心。默认情况下，租户管理员有权访问此位置，并可向合规部主管及其他人员授予对安全与合规中心的访问权限，而不授予租户管理员的所有权限。为此，建议转到安全与合规中心内的“权限”\*\*\*\* 页，编辑“合规性管理员”\*\*\*\* 角色组，再向此角色组添加成员。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p158">Members of your compliance team who will create sensitivity labels need permissions to the Security & Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security & Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security & Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span>

<span data-ttu-id="d5c48-330">有关详细信息，请参阅[授予用户访问 Office 365 安全与合规中心的权限](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d5c48-330">For more information, see [Give users access to the Office 365 Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="d5c48-p159">只有在创建和应用标签和标签策略时，才必须拥有这些权限。强制执行策略并不需要访问内容。</span><span class="sxs-lookup"><span data-stu-id="d5c48-p159">These permissions are required only to create and apply labels and a label policy. Policy enforcement does not require access to the content.</span></span>

---
title: 使用敏感度标签中的加密限制对内容的访问
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 10/22/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: 创建敏感度标签时，可以限制对将要应用标签的内容的访问。敏感度标签可以使用加密来保护内容。
ms.openlocfilehash: 154be1d4dd1e891913e1b64d8f1ae5dfa34706bf
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "26547314"
---
# <a name="restrict-access-to-content-by-using-encryption-in-sensitivity-labels"></a><span data-ttu-id="ce849-104">使用敏感度标签中的加密限制对内容的访问</span><span class="sxs-lookup"><span data-stu-id="ce849-104">Restrict access to content by using encryption in sensitivity labels</span></span>

<span data-ttu-id="ce849-p102">创建敏感度标签时，可以限制对将要应用标签的内容的访问。例如，通过敏感度标签的加密设置，可以保护内容，以便：</span><span class="sxs-lookup"><span data-stu-id="ce849-p102">When you create a sensitivity label, you can restrict access to content that the label will be applied to. For example, with the encryption settings for a sensitivity label, you can protect content so that:</span></span>

- <span data-ttu-id="ce849-107">只有组织中的用户才能打开机密文档或电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ce849-107">Only users within your organization can open a confidential document or email.</span></span>
- <span data-ttu-id="ce849-108">只有市场部的用户才能编辑和打印促销声明文档或电子邮件，而组织中的所有其他用户只能阅读它。</span><span class="sxs-lookup"><span data-stu-id="ce849-108">Only users in the marketing department can edit and print the promotion announcement document or email, while all other users in your organization can only read it.</span></span>
- <span data-ttu-id="ce849-109">用户无法转发电子邮件或从中复制包含有关内部组织的新闻的信息。</span><span class="sxs-lookup"><span data-stu-id="ce849-109">Users cannot forward an email or copy information from it that contains news about an internal reorganization.</span></span>
- <span data-ttu-id="ce849-110">发送到业务合作伙伴的当前价目表在指定日期后无法打开。</span><span class="sxs-lookup"><span data-stu-id="ce849-110">The current price list that is sent to business partners cannot be opened after a specified date.</span></span>

<span data-ttu-id="ce849-111">当文档或电子邮件被加密时，对内容的访问将受到限制，以便它：</span><span class="sxs-lookup"><span data-stu-id="ce849-111">When a document or email is encrypted, access to the content is restricted, so that it:</span></span>

- <span data-ttu-id="ce849-112">只能由标签的加密设置授权的用户解密。</span><span class="sxs-lookup"><span data-stu-id="ce849-112">Can be decrypted only by users authorized by the label’s encryption settings.</span></span>
- <span data-ttu-id="ce849-113">无论其所在位置（组织内部或外部）如何，仍保持加密状态，即使该文件被重命名也是如此。</span><span class="sxs-lookup"><span data-stu-id="ce849-113">Remains encrypted no matter where it resides, inside or outside your organization, even if the file’s renamed.</span></span>
- <span data-ttu-id="ce849-114">静态加密（例如，在 OneDrive 帐户中）和传输加密（例如，发送的电子邮件）。</span><span class="sxs-lookup"><span data-stu-id="ce849-114">Is encrypted both at rest (for example, in a OneDrive account) and in transit (for example, a sent email).</span></span>

<span data-ttu-id="ce849-115">可以在 Office 365 安全与合规中心 >“标签”\*\*\*\* 页面 >“敏感度”\*\*\*\* 选项卡 >“创建标签”\*\*\*\* 中找到加密设置。</span><span class="sxs-lookup"><span data-stu-id="ce849-115">The encryption settings are available in the Office 365 Security & Compliance Center > **Labels** page > **Sensitivity** tab > **Create a label**.</span></span>

## <a name="how-encryption-works"></a><span data-ttu-id="ce849-116">加密工作原理</span><span class="sxs-lookup"><span data-stu-id="ce849-116">How encryption works</span></span>

<span data-ttu-id="ce849-p103">加密使用 Azure Rights Management (Azure RMS)。Azure RMS 使用加密、标识和授权策略。若要了解详细信息，请参阅 [Azure Rights Management 是什么？](https://docs.microsoft.com/zh-CN/azure/information-protection/what-is-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="ce849-p103">Encryption uses Azure Rights Management (Azure RMS). Azure RMS uses encryption, identity, and authorization policies. To learn more, see [What is Azure Rights Management?](https://docs.microsoft.com/zh-CN/azure/information-protection/what-is-azure-rms)</span></span>

## <a name="how-to-turn-on-encryption-for-a-sensitivity-label"></a><span data-ttu-id="ce849-120">如何打开敏感度标签的加密</span><span class="sxs-lookup"><span data-stu-id="ce849-120">How to turn on encryption for a sensitivity label</span></span>

<span data-ttu-id="ce849-p104">要开始使用，只需将“**加密**”切换到“**开**”，然后使用下述选项来控制哪些人员可访问应用了此标签的电子邮件或文档。你可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ce849-p104">To begin, simply toggle **Encryption** to **On**, and then use the options below to control who can acess email or documents to which this label is applied. You can:</span></span>

1. <span data-ttu-id="ce849-p105">**向电子邮件和文档同时应用加密，或只向电子邮件应用加密。** 如果选择只向电子邮件应用加密，则具有此标签的邮件将在 Outlook 中被加密，但具有此标签的文档将不会在其他应用中加密（例如，Word 或 PowerPoint）。</span><span class="sxs-lookup"><span data-stu-id="ce849-p105">**Apply encryption to both email and documents, or just email.** If you choose just email, messages with this label will be encrypted in Outlook, but documents with this label won't be encrypted in other apps, such as Word or PowerPoint.</span></span> 
2. <span data-ttu-id="ce849-p106">**允许对标记的内容的访问权限过期**（在某个特定日期或在应用标签后的特定天数后）。在此时间后，用户将无法打开标记的项。如果指定某个日期，则它将于该日期午夜（在你的当前时区）生效。</span><span class="sxs-lookup"><span data-stu-id="ce849-p106">**Allow access to labeled content to expire**, either on a specific date or after a specific number of days after the label is applied. After this time, users won’t be able to open the labeled item. If you specify a date, it is effective midnight on that date in your current time zone.</span></span> 
3. <span data-ttu-id="ce849-p107">**允许脱机访问**（从不、始终或在应用标签后的特定天后）。如果将脱机访问限制为从不或一定天数，则当达到该阈值时，必须对用户重新进行身份验证并记录其访问。有关详细信息，请参阅下一部分有关 Rights Management 使用许可证的内容。</span><span class="sxs-lookup"><span data-stu-id="ce849-p107">**Allow offline access** never, always, or for a specific number of days after the label is applied. If you restrict offline access to never or a number of days, when that threshold is reached, users must be reauthenticated and their access is logged. For more information, see the next section on the Rights Management use license.</span></span>

![敏感度标签的加密设置](media/Sensitivity_Encryption_settings_for_sensitivity_label.png)

### <a name="rights-management-use-license-for-offline-access"></a><span data-ttu-id="ce849-132">针对脱机访问的 Rights Management 使用许可证</span><span class="sxs-lookup"><span data-stu-id="ce849-132">Rights Management use license for offline access</span></span>

<span data-ttu-id="ce849-p108">当用户在脱机状态下打开已受敏感度标签保护的文档或电子邮件时，将向用户授予针对该内容的 Azure Rights Management 使用许可证。此使用许可证是一个证书，其中包含用户对文档或电子邮件的使用权限，以及用于加密内容的加密密钥。使用许可证还包括到期日期（如果对此进行了设置）以及使用许可证的有效期。</span><span class="sxs-lookup"><span data-stu-id="ce849-p108">When a user opens a document or email offline that’s been protected by a sensitivity label, an Azure Rights Management use license for that content is granted to the user. This use license is a certificate that contains the user's usage rights for the document or email, and the encryption key that was used to encrypt the content. The use license also contains an expiration date if this has been set, and how long the use license is valid.</span></span>

<span data-ttu-id="ce849-p109">如果尚未设置任何到期日期，则针对租户的默认使用许可证有效期为 30 天。在使用许可证有效期内，无需就内容对用户重新进行身份验证或授权。这使用户无需具有 Internet 连接即可继续打开受保护的文档或电子邮件。当用户许可有效期到期后，在用户下次访问受保护的文档或电子邮件时，必须对用户重新进行身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="ce849-p109">If no expiration date has been set, the default use license validity period for a tenant is 30 days. For the duration of the use license, the user is not reauthenticated or reauthorized for the content. This lets the user continue to open the protected document or email without an Internet connection. When the use license validity period expires, the next time the user accesses the protected document or email, the user must be reauthenticated and reauthorized.</span></span>

<span data-ttu-id="ce849-p110">除重新进行身份验证以外，还将重新评估策略和用户组成员身份。这意味着，如果自他们最后一次访问内容时在策略或组成员身份中存在更改，则对于同一文档或电子邮件，他们可能会收到不同的访问结果。</span><span class="sxs-lookup"><span data-stu-id="ce849-p110">In addition to reauthentication, the policy and user group membership is reevaluated. This means that users could experience different access results for the same document or email if there are changes in the policy or group membership from when they last accessed the content.</span></span>

<span data-ttu-id="ce849-142">若要了解如何更改默认的 30 天设置，请参阅 [Rights Management 使用许可证](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-management-use-license)。</span><span class="sxs-lookup"><span data-stu-id="ce849-142">To learn how to change the default 30-day setting, see [Rights Management use license](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-management-use-license).</span></span>

## <a name="assign-permissions-to-specific-users-or-groups"></a><span data-ttu-id="ce849-143">向特定用户或组分配权限</span><span class="sxs-lookup"><span data-stu-id="ce849-143">Assign permissions to specific users or groups</span></span>

<span data-ttu-id="ce849-144">可以向特定人员授予权限，只允许这些人员与标记的内容进行交互。</span><span class="sxs-lookup"><span data-stu-id="ce849-144">You can grant permissions to specific people so that only they can interact with the labeled content.</span></span>

<span data-ttu-id="ce849-145">实现此功能只需简单的两个步骤：</span><span class="sxs-lookup"><span data-stu-id="ce849-145">Doing so is a straightforward two-step process:</span></span>

1. <span data-ttu-id="ce849-146">首先，添加将向其分配对标记的内容具有访问权限的用户或组。</span><span class="sxs-lookup"><span data-stu-id="ce849-146">First you add users or groups that will be assigned permissions to the labeled content.</span></span>
2. <span data-ttu-id="ce849-147">然后，选择这些用户对标记的内容所具有的权限。</span><span class="sxs-lookup"><span data-stu-id="ce849-147">Then you choose which permissions those users have for the labeled content.</span></span>

![向用户分配权限的选项](media/Sensitivity_Assign_permissions_settings.png)

### <a name="add-users-or-groups"></a><span data-ttu-id="ce849-149">添加用户或组</span><span class="sxs-lookup"><span data-stu-id="ce849-149">Add users or groups</span></span>

<span data-ttu-id="ce849-150">分配权限时，可以选择：</span><span class="sxs-lookup"><span data-stu-id="ce849-150">When you assign permissions, you can choose:</span></span>

- <span data-ttu-id="ce849-p111">组织中的任何人（所有租户成员）。此设置不包括来宾帐户。</span><span class="sxs-lookup"><span data-stu-id="ce849-p111">Everyone in your organization (all tenant members). This setting excludes guest accounts.</span></span>
- <span data-ttu-id="ce849-153">任何特定用户或启用了电子邮件的安全组、通讯组、Office 365 组或动态通讯组。</span><span class="sxs-lookup"><span data-stu-id="ce849-153">Any specific user or email-enabled security group, distribution group, Office 365 group, or dynamic distribution group.</span></span> 
- <span data-ttu-id="ce849-154">组织外部的任何电子邮件地址或域，例如 gmail.com、hotmail.com 或 outlook.com。</span><span class="sxs-lookup"><span data-stu-id="ce849-154">Any email address or domain outside your organization, such as gmail.com, hotmail.com, or outlook.com.</span></span>

<span data-ttu-id="ce849-155">选择所有租户成员或浏览目录时，用户或组必须具有电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ce849-155">When you choose all tenant members or browse the directory, the users or groups must have an email address.</span></span>

<span data-ttu-id="ce849-p112">最佳做法是使用组，而不是使用用户。此策略可使你的配置更为简单。</span><span class="sxs-lookup"><span data-stu-id="ce849-p112">As a best practice, use groups rather than users. This strategy keeps your configuration simpler.</span></span>

### <a name="choose-permissions"></a><span data-ttu-id="ce849-158">选择权限</span><span class="sxs-lookup"><span data-stu-id="ce849-158">Choose permissions</span></span>

<span data-ttu-id="ce849-159">选择允许为这些用户或组使用哪些权限时，可以选择：</span><span class="sxs-lookup"><span data-stu-id="ce849-159">When you choose which permissions to allow for those users or groups, you can select either:</span></span>

- <span data-ttu-id="ce849-160">具有预设权限组的[预定义权限级别](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels)，例如共同创作或审阅者。</span><span class="sxs-lookup"><span data-stu-id="ce849-160">A [predefined permissions level](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) with a preset group of rights, such as Co-Author or Reviewer.</span></span>
- <span data-ttu-id="ce849-161">自定义权限组，可选择想要允许使用的任何权限。</span><span class="sxs-lookup"><span data-stu-id="ce849-161">A Custom group of rights, where you choose whichever permissions you want.</span></span>

<span data-ttu-id="ce849-162">有关每个特定权限的详细信息，请参阅[使用权限和说明](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)。</span><span class="sxs-lookup"><span data-stu-id="ce849-162">For more information on each specific permission, see [Usage rights and descriptions](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).</span></span>  

![选择预设权限或自定义权限的选项。](media/Sensitivity_Choose_permissions_settings.png)

<span data-ttu-id="ce849-p113">请注意，同一标签可向不同用户授予不同的权限。例如，一个标签可将某些用户分配为审阅者，并可将其他用户分配为共同创作，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ce849-p113">Note that the same label can grant different permissions to different users. For example, a single label can assign some users as Reviewer and a different user as Co-author, as shown below.</span></span>

<span data-ttu-id="ce849-p114">为此，添加用户或组、向其分配权限并保存这些设置。然后重复这些步骤，添加用户并向其分配权限、每次保存设置。可以根据需要经常执行此操作，以便为不同用户定义不同权限。</span><span class="sxs-lookup"><span data-stu-id="ce849-p114">To do this, add users or groups, assign them permissions, and save those settings. Then repeat these steps, adding users and assigning them permissions, saving the settings each time. You can do this as often as necessary, to define different permissions for different users.</span></span>

![具有不同权限的不同用户](media/Sensitivity_Multiple_users_permissions.png)

### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a><span data-ttu-id="ce849-170">Rights Management 颁发者（应用敏感度标签的用户）始终具有完全控制</span><span class="sxs-lookup"><span data-stu-id="ce849-170">Rights Management issuer (user applying the sensitivity label) always has Full Control</span></span>

<span data-ttu-id="ce849-p115">敏感度标签的加密使用 Azure RMS。当用户通过使用 Azure RMS 应用敏感度标签以保护文档或电子邮件时，该用户变为该内容的Rights Management 颁发者。</span><span class="sxs-lookup"><span data-stu-id="ce849-p115">Encryption for a sensitivity label uses Azure RMS. When a user applies a sensitivity label to protect a document or email by using Azure RMS, that user becomes the Rights Management issuers for that content.</span></span>

<span data-ttu-id="ce849-173">Rights Management 颁发者将始终被授予对文档或电子邮件的完全控制权限，此外：</span><span class="sxs-lookup"><span data-stu-id="ce849-173">The Rights Management issuer is always granted Full Control permissions for the document or email, and in addition:</span></span>

- <span data-ttu-id="ce849-174">如果保护设置包含过期日期，则 Rights Management 颁发者在该日期后仍可以打开和编辑文档或电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ce849-174">If the protection settings include an expiration date, the Rights Management issuer can still open and edit the document or email after that date.</span></span>
- <span data-ttu-id="ce849-175">Rights Management 颁发者可以始终在脱机状态下访问文档或电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ce849-175">The Rights Management issuer can always access the document or email offline.</span></span>
- <span data-ttu-id="ce849-176">在文档被撤销后，Rights Management 颁发者仍然可以打开该文档。</span><span class="sxs-lookup"><span data-stu-id="ce849-176">The Rights Management issuer can still open a document after it is revoked.</span></span>

<span data-ttu-id="ce849-177">有关详细信息，请参阅 [Rights Management 颁发者和 Rights Management 所有者](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)。</span><span class="sxs-lookup"><span data-stu-id="ce849-177">For more information, see [Rights Management issuer and Rights Management owner](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).</span></span>

## <a name="storing-encrypted-content-in-onedrive-and-sharepoint"></a><span data-ttu-id="ce849-178">存储 OneDrive 和 SharePoint 中加密的内容</span><span class="sxs-lookup"><span data-stu-id="ce849-178">Storing encrypted content in OneDrive and SharePoint</span></span>

<span data-ttu-id="ce849-p116">请注意，将加密应用于 OneDrive 和 SharePoint 中存储的文件时，该服务无法处理这些文件的内容。这意味着共同创作、电子数据展示、搜索、Delve 和其他协作功能将无法正常使用。此外，数据丢失防护 (DLP) 策略只适用于元数据（包括 Office 365 标签），但并不适用于这些加密的文件的内容（例如，文件内的信用卡号）。</span><span class="sxs-lookup"><span data-stu-id="ce849-p116">Be aware that when encryption is applied to files stored in OneDrive and SharePoint, the service cannot process the contents of these files. This means that features such as co-authoring, eDiscovery, search, Delve, and other collaborative features do not work. Also, data loss prevention (DLP) policies can work only with the metadata (including Office 365 labels) but not the contents of encrypted files (such as credit card numbers within files).</span></span>

<span data-ttu-id="ce849-p117">这仅适用于在 OneDrive 和 SharePoint 中存储的内容。在 Exchange Online 中，传输规则使用[超级用户帐户](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-super-users)，以便他们能够扫描加密的内容和强制实施 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="ce849-p117">This applies only to content stored in OneDrive and SharePoint. In Exchange Online, transport rules use the [super user account](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-super-users) so that they can scan encrypted content and enforce DLP policies.</span></span>

## <a name="important-prerequisites"></a><span data-ttu-id="ce849-184">重要先决条件</span><span class="sxs-lookup"><span data-stu-id="ce849-184">Important prerequisites</span></span>

<span data-ttu-id="ce849-185">在使用加密前，可能需要执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="ce849-185">Before you can use encryption, you might need to perform these tasks.</span></span>

### <a name="activating-azure-rights-management"></a><span data-ttu-id="ce849-186">激活 Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="ce849-186">Activating Azure Rights Management</span></span>

<span data-ttu-id="ce849-p118">若要使用敏感度标签中的加密，需要在租户中激活 Azure Rights Management 服务。在较新的租户中，该服务在默认情况下为启用状态，但可能需要手动激活该服务。有关详细信息，请参阅[激活 Azure Rights Management](https://docs.microsoft.com/zh-CN/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="ce849-p118">To use encryption in sensitivity labels, the Azure Rights Management service needs to be activated in your tenant. In newer tenants, the service is on by default, but you might need to manually activate the service. For more information, see [Activating Azure Rights Management](https://docs.microsoft.com/zh-CN/azure/information-protection/activate-service).</span></span>

### <a name="configure-exchange-for-azure-information-protection"></a><span data-ttu-id="ce849-190">配置用于 Azure 信息保护的 Exchange</span><span class="sxs-lookup"><span data-stu-id="ce849-190">Configure Exchange for Azure Information Protection</span></span>

<span data-ttu-id="ce849-p119">在用户能够在 Outlook 中应用标签以保护其电子邮件前，无需对 Exchange 进行配置以用于 Azure 信息保护。但是，如果没有针对 Azure 信息保护对 Exchange 进行配置，你将无法在 Exchange 中获取使用 Azure Rights Management 的完整功能。</span><span class="sxs-lookup"><span data-stu-id="ce849-p119">Exchange does not have to be configured for Azure Information Protection before users can apply labels in Outlook to protect their emails. However, until Exchange is configured for Azure Information Protection, you do not get the full functionality of using Azure Rights Management protection with Exchange.</span></span>
 
<span data-ttu-id="ce849-193">例如，用户无法查看移动电话或 Outlook 网页版上受保护的电子邮件，无法索引受保护的电子邮件以用于搜索，并且无法针对 Rights Management 保护配置 Exchange Online DLP。</span><span class="sxs-lookup"><span data-stu-id="ce849-193">For example, users cannot view protected emails on mobile phones or with Outlook on the web, protected emails cannot be indexed for search, and you cannot configure Exchange Online DLP for Rights Management protection.</span></span> 

<span data-ttu-id="ce849-194">为确保 Exchange 可以支持这些其他应用场景，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="ce849-194">To ensure that Exchange can support these additional scenarios, see the following:</span></span>

- <span data-ttu-id="ce849-195">对于 Exchange Online，请参阅 [Exchange Online：IRM 配置](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-office365#exchange-online-irm-configuration)的说明。</span><span class="sxs-lookup"><span data-stu-id="ce849-195">For Exchange Online, see the instructions for [Exchange Online: IRM Configuration](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-office365#exchange-online-irm-configuration).</span></span>
- <span data-ttu-id="ce849-196">对于本地 Exchange，必须部署 [RMS 连接器并配置你的 Exchange 服务器](https://docs.microsoft.com/zh-CN/azure/information-protection/deploy-rms-connector)。</span><span class="sxs-lookup"><span data-stu-id="ce849-196">For Exchange on-premises, you must deploy the [RMS connector and configure your Exchange servers](https://docs.microsoft.com/zh-CN/azure/information-protection/deploy-rms-connector).</span></span> 

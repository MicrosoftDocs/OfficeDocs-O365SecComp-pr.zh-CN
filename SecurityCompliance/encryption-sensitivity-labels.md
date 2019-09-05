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
# <a name="restrict-access-to-content-by-using-encryption-in-sensitivity-labels"></a><span data-ttu-id="af058-104">使用敏感度标签中的加密限制对内容的访问</span><span class="sxs-lookup"><span data-stu-id="af058-104">Restrict access to content by using encryption in sensitivity labels</span></span>

<span data-ttu-id="af058-p102">创建敏感度标签时，可以限制对将要应用标签的内容的访问。例如，通过敏感度标签的加密设置，可以保护内容，以便：</span><span class="sxs-lookup"><span data-stu-id="af058-p102">When you create a sensitivity label, you can restrict access to content that the label will be applied to. For example, with the encryption settings for a sensitivity label, you can protect content so that:</span></span>

- <span data-ttu-id="af058-107">只有组织中的用户才能打开机密文档或电子邮件。</span><span class="sxs-lookup"><span data-stu-id="af058-107">Only users within your organization can open a confidential document or email.</span></span>
- <span data-ttu-id="af058-108">只有市场部的用户才能编辑和打印促销声明文档或电子邮件，而组织中的所有其他用户只能阅读它。</span><span class="sxs-lookup"><span data-stu-id="af058-108">Only users in the marketing department can edit and print the promotion announcement document or email, while all other users in your organization can only read it.</span></span>
- <span data-ttu-id="af058-109">用户无法转发电子邮件或从中复制包含有关内部组织的新闻的信息。</span><span class="sxs-lookup"><span data-stu-id="af058-109">Users cannot forward an email or copy information from it that contains news about an internal reorganization.</span></span>
- <span data-ttu-id="af058-110">发送到业务合作伙伴的当前价目表在指定日期后无法打开。</span><span class="sxs-lookup"><span data-stu-id="af058-110">The current price list that is sent to business partners cannot be opened after a specified date.</span></span>

<span data-ttu-id="af058-111">当文档或电子邮件被加密时，对内容的访问将受到限制，以便它：</span><span class="sxs-lookup"><span data-stu-id="af058-111">When a document or email is encrypted, access to the content is restricted, so that it:</span></span>

- <span data-ttu-id="af058-112">只能由标签的加密设置授权的用户解密。</span><span class="sxs-lookup"><span data-stu-id="af058-112">Can be decrypted only by users authorized by the label’s encryption settings.</span></span>
- <span data-ttu-id="af058-113">无论其所在位置（组织内部或外部）如何，仍保持加密状态，即使该文件被重命名也是如此。</span><span class="sxs-lookup"><span data-stu-id="af058-113">Remains encrypted no matter where it resides, inside or outside your organization, even if the file’s renamed.</span></span>
- <span data-ttu-id="af058-114">静态加密（例如，在 OneDrive 帐户中）和传输加密（例如，发送的电子邮件）。</span><span class="sxs-lookup"><span data-stu-id="af058-114">Is encrypted both at rest (for example, in a OneDrive account) and in transit (for example, a sent email).</span></span>

<span data-ttu-id="af058-115">最后，作为管理员，在创建敏感度标签时，你可选择执行下述任一操作：</span><span class="sxs-lookup"><span data-stu-id="af058-115">Finally, as an admin, when you create a sensitivity label, you can choose either to:</span></span>

- <span data-ttu-id="af058-116">**立即分配权限**，以便准确确定哪些用户获得了带有该标签的内容的哪些权限。</span><span class="sxs-lookup"><span data-stu-id="af058-116">**Assign permissions now**, so that you determine exactly which users get which permissions to content with that label.</span></span>
- <span data-ttu-id="af058-117">在用户将此标签应用到内容时**允许用户分配权限**。</span><span class="sxs-lookup"><span data-stu-id="af058-117">**Let users assign permissions** when they apply the label to content.</span></span> <span data-ttu-id="af058-118">这样，即可让组织内部人员在协作处理和完成任务时具有可能需要的一定程度的灵活性。</span><span class="sxs-lookup"><span data-stu-id="af058-118">This way, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span>

<span data-ttu-id="af058-119">在 Microsoft 365 合规中心、Microsoft 365 安全中心或 Office 365 安全与合规中心创建敏感度标签时，可使用加密设置。</span><span class="sxs-lookup"><span data-stu-id="af058-119">The encryption settings are available when you create a sensitivity label in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="af058-120">在左侧导航栏中，选择“**分类**” > “**敏感度标签**” > “**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="af058-120">In the left nav, choose **Classification** > **Sensitivity label** > **Create a label**.</span></span>

## <a name="how-encryption-works"></a><span data-ttu-id="af058-121">加密工作原理</span><span class="sxs-lookup"><span data-stu-id="af058-121">How encryption works</span></span>

<span data-ttu-id="af058-p105">加密使用 Azure Rights Management (Azure RMS)。Azure RMS 使用加密、标识和授权策略。若要了解详细信息，请参阅 [Azure Rights Management 是什么？](https://docs.microsoft.com/zh-CN/azure/information-protection/what-is-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="af058-p105">Encryption uses Azure Rights Management (Azure RMS). Azure RMS uses encryption, identity, and authorization policies. To learn more, see [What is Azure Rights Management?](https://docs.microsoft.com/zh-CN/azure/information-protection/what-is-azure-rms)</span></span>

## <a name="how-to-turn-on-encryption-for-a-sensitivity-label"></a><span data-ttu-id="af058-125">如何打开敏感度标签的加密</span><span class="sxs-lookup"><span data-stu-id="af058-125">How to turn on encryption for a sensitivity label</span></span>

<span data-ttu-id="af058-126">首先，只需将“**加密**”切换到“**开**”，然后选择是否要：</span><span class="sxs-lookup"><span data-stu-id="af058-126">To begin, simply toggle **Encryption** to **On**, and then choose whether to:</span></span>

- <span data-ttu-id="af058-127">**立即分配权限**，以便可准确确定哪些用户获得了带有该标签的内容的哪些权限。</span><span class="sxs-lookup"><span data-stu-id="af058-127">**Assign permissions now**, so that you can determine exactly which users get which permissions to content with that label.</span></span> <span data-ttu-id="af058-128">有关详细信息，请参阅下一部分：[立即分配权限](#assign-permissions-now)。</span><span class="sxs-lookup"><span data-stu-id="af058-128">For more information, see the next section.</span></span>
- <span data-ttu-id="af058-129">在用户将此标签应用到内容时**允许用户分配权限**。</span><span class="sxs-lookup"><span data-stu-id="af058-129">**Let users assign permissions** when they apply the label to content.</span></span> <span data-ttu-id="af058-130">这样，即可让组织内部人员在协作处理和完成任务时具有可能需要的一定程度的灵活性。</span><span class="sxs-lookup"><span data-stu-id="af058-130">This way, you can allow people in your organization some flexibility that they might need to collaborate and get their work done.</span></span> <span data-ttu-id="af058-131">有关详细信息，请参阅下述部分：[允许用户分配权限](#let-users-assign-permissions)。</span><span class="sxs-lookup"><span data-stu-id="af058-131">For more information, see the below section [Let users assign permissions](#let-users-assign-permissions).</span></span>

<span data-ttu-id="af058-132">例如，如果你有一个名为“**高度机密**”的敏感度标签，它将应用于你的大部分敏感内容，则你可能需要决定谁对该内容获得哪种类型的权限。</span><span class="sxs-lookup"><span data-stu-id="af058-132">For example, if you have a sensitivity label named **Highly Confidential** that will be applied to your most sensitive content, you may want to decide now who gets what type of permissions to that content.</span></span>

<span data-ttu-id="af058-133">或者，如果你有一个名为“**商业合同**”的敏感度标签，而你所在组织的工作流要员工临时与不同人员协作处理此内容，则你可能需要允许用户在分配此标签时决定由谁获得权限。</span><span class="sxs-lookup"><span data-stu-id="af058-133">Alternatively, if you have a sensitivity label named **Business Contracts**, and your organization's workflow requires that your people collaborate on this content with different people on an ad hoc basis, you may want to allow your users to decide who gets permissions when they assign the label.</span></span> <span data-ttu-id="af058-134">这种灵活性都能帮助你的用户保持高效，同时减少管理员要更新或新建敏感度标签来应对特定场景的请求。</span><span class="sxs-lookup"><span data-stu-id="af058-134">This flexibility both helps your users' productivity and reduces the requests for your admins to update or create new sensitivity labels to address specific scenarios.</span></span>

![用于添加用户或管理员定义的权限的选项](media/sensitivity-label-user-or-admin-defined-permissions.png)

## <a name="assign-permissions-now"></a><span data-ttu-id="af058-136">立即分配权限</span><span class="sxs-lookup"><span data-stu-id="af058-136">Assign permissions now</span></span>

<span data-ttu-id="af058-137">使用下述选项来控制哪些人员可访问应用了此标签的电子邮件或文档。</span><span class="sxs-lookup"><span data-stu-id="af058-137">To begin, simply toggle Encryption to On, and then use the options below to control who can access email or documents to which this label is applied. You can:</span></span> <span data-ttu-id="af058-138">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="af058-138">You can:</span></span>

1. <span data-ttu-id="af058-p110">**向电子邮件和文档同时应用加密，或只向电子邮件应用加密。** 如果选择只向电子邮件应用加密，则具有此标签的邮件将在 Outlook 中被加密，但具有此标签的文档将不会在其他应用中加密（例如，Word 或 PowerPoint）。</span><span class="sxs-lookup"><span data-stu-id="af058-p110">**Apply encryption to both email and documents, or just email.** If you choose just email, messages with this label will be encrypted in Outlook, but documents with this label won't be encrypted in other apps, such as Word or PowerPoint.</span></span> 
2. <span data-ttu-id="af058-p111">**允许对标记的内容的访问权限过期**（在某个特定日期或在应用标签后的特定天数后）。在此时间后，用户将无法打开标记的项。如果指定某个日期，则它将于该日期午夜（在你的当前时区）生效。请注意，某些电子邮件客户端由于其缓存机制，可能不强制过期，也不显示超过其过期日期的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="af058-p111">**Allow access to labeled content to expire**, either on a specific date or after a specific number of days after the label is applied. After this time, users won’t be able to open the labeled item. If you specify a date, it is effective midnight on that date in your current time zone. (Note that some email clients may not enforce expiration and show emails past their expiration date, due to their caching mechanisms.)</span></span>
3. <span data-ttu-id="af058-p112">**允许脱机访问**（从不、始终或在应用标签后的特定天后）。如果将脱机访问限制为从不或一定天数，则当达到该阈值时，必须对用户重新进行身份验证并记录其访问。有关详细信息，请参阅下一部分有关 Rights Management 使用许可证的内容。</span><span class="sxs-lookup"><span data-stu-id="af058-p112">**Allow offline access** never, always, or for a specific number of days after the label is applied. If you restrict offline access to never or a number of days, when that threshold is reached, users must be reauthenticated and their access is logged. For more information, see the next section on the Rights Management use license.</span></span>

![有关管理员定义的权限的设置](media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a><span data-ttu-id="af058-149">针对脱机访问的 Rights Management 使用许可证</span><span class="sxs-lookup"><span data-stu-id="af058-149">Rights Management use license for offline access</span></span>

<span data-ttu-id="af058-p113">当用户在脱机状态下打开已受敏感度标签保护的文档或电子邮件时，将向用户授予针对该内容的 Azure Rights Management 使用许可证。此使用许可证是一个证书，其中包含用户对文档或电子邮件的使用权限，以及用于加密内容的加密密钥。使用许可证还包括到期日期（如果对此进行了设置）以及使用许可证的有效期。</span><span class="sxs-lookup"><span data-stu-id="af058-p113">When a user opens a document or email offline that’s been protected by a sensitivity label, an Azure Rights Management use license for that content is granted to the user. This use license is a certificate that contains the user's usage rights for the document or email, and the encryption key that was used to encrypt the content. The use license also contains an expiration date if this has been set, and how long the use license is valid.</span></span>

<span data-ttu-id="af058-p114">如果尚未设置任何到期日期，则针对租户的默认使用许可证有效期为 30 天。在使用许可证有效期内，无需就内容对用户重新进行身份验证或授权。这使用户无需具有 Internet 连接即可继续打开受保护的文档或电子邮件。当用户许可有效期到期后，在用户下次访问受保护的文档或电子邮件时，必须对用户重新进行身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="af058-p114">If no expiration date has been set, the default use license validity period for a tenant is 30 days. For the duration of the use license, the user is not reauthenticated or reauthorized for the content. This lets the user continue to open the protected document or email without an Internet connection. When the use license validity period expires, the next time the user accesses the protected document or email, the user must be reauthenticated and reauthorized.</span></span>

<span data-ttu-id="af058-p115">除重新进行身份验证以外，还将重新评估策略和用户组成员身份。这意味着，如果自他们最后一次访问内容时在策略或组成员身份中存在更改，则对于同一文档或电子邮件，他们可能会收到不同的访问结果。</span><span class="sxs-lookup"><span data-stu-id="af058-p115">In addition to reauthentication, the policy and user group membership is reevaluated. This means that users could experience different access results for the same document or email if there are changes in the policy or group membership from when they last accessed the content.</span></span>

<span data-ttu-id="af058-159">若要了解如何更改默认的 30 天设置，请参阅 [Rights Management 使用许可证](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-management-use-license)。</span><span class="sxs-lookup"><span data-stu-id="af058-159">To learn how to change the default 30-day setting, see [Rights Management use license](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-management-use-license).</span></span>

### <a name="assign-permissions-to-specific-users-or-groups"></a><span data-ttu-id="af058-160">向特定用户或组分配权限</span><span class="sxs-lookup"><span data-stu-id="af058-160">Assign permissions to specific users or groups</span></span>

<span data-ttu-id="af058-161">可以向特定人员授予权限，只允许这些人员与标记的内容进行交互。</span><span class="sxs-lookup"><span data-stu-id="af058-161">You can grant permissions to specific people so that only they can interact with the labeled content.</span></span>

<span data-ttu-id="af058-162">实现此功能只需简单的两个步骤：</span><span class="sxs-lookup"><span data-stu-id="af058-162">Doing so is a straightforward two-step process:</span></span>

1. <span data-ttu-id="af058-163">首先，添加将向其分配对标记的内容具有访问权限的用户或组。</span><span class="sxs-lookup"><span data-stu-id="af058-163">First you add users or groups that will be assigned permissions to the labeled content.</span></span>
2. <span data-ttu-id="af058-164">然后，选择这些用户对标记的内容所具有的权限。</span><span class="sxs-lookup"><span data-stu-id="af058-164">Then you choose which permissions those users have for the labeled content.</span></span>

![向用户分配权限的选项](media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a><span data-ttu-id="af058-166">添加用户或组</span><span class="sxs-lookup"><span data-stu-id="af058-166">Add users or groups</span></span>

<span data-ttu-id="af058-167">分配权限时，可以选择：</span><span class="sxs-lookup"><span data-stu-id="af058-167">When you assign permissions, you can choose:</span></span>

- <span data-ttu-id="af058-p116">组织中的任何人（所有租户成员）。此设置不包括来宾帐户。</span><span class="sxs-lookup"><span data-stu-id="af058-p116">Everyone in your organization (all tenant members). This setting excludes guest accounts.</span></span>
- <span data-ttu-id="af058-170">任何特定用户或启用了电子邮件的安全组、通讯组、Office 365 组或动态通讯组。</span><span class="sxs-lookup"><span data-stu-id="af058-170">Any specific user or email-enabled security group, distribution group, Office 365 group, or dynamic distribution group.</span></span> 
- <span data-ttu-id="af058-171">组织外部的任何电子邮件地址或域，例如 gmail.com、hotmail.com 或 outlook.com。</span><span class="sxs-lookup"><span data-stu-id="af058-171">Any email address or domain outside your organization, such as gmail.com, hotmail.com, or outlook.com.</span></span>

<span data-ttu-id="af058-172">选择所有租户成员或浏览目录时，用户或组必须具有电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="af058-172">When you choose all tenant members or browse the directory, the users or groups must have an email address.</span></span>

<span data-ttu-id="af058-p117">最佳做法是使用组，而不是使用用户。此策略可使你的配置更为简单。</span><span class="sxs-lookup"><span data-stu-id="af058-p117">As a best practice, use groups rather than users. This strategy keeps your configuration simpler.</span></span>

#### <a name="choose-permissions"></a><span data-ttu-id="af058-175">选择权限</span><span class="sxs-lookup"><span data-stu-id="af058-175">Choose permissions</span></span>

<span data-ttu-id="af058-176">选择允许为这些用户或组使用哪些权限时，可以选择：</span><span class="sxs-lookup"><span data-stu-id="af058-176">When you choose which permissions to allow for those users or groups, you can select either:</span></span>

- <span data-ttu-id="af058-177">具有预设权限组的[预定义权限级别](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels)，例如共同创作或审阅者。</span><span class="sxs-lookup"><span data-stu-id="af058-177">A [predefined permissions level](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) with a preset group of rights, such as Co-Author or Reviewer.</span></span>
- <span data-ttu-id="af058-178">自定义权限组，可选择想要允许使用的任何权限。</span><span class="sxs-lookup"><span data-stu-id="af058-178">A Custom group of rights, where you choose whichever permissions you want.</span></span>

<span data-ttu-id="af058-179">有关每个特定权限的详细信息，请参阅[使用权限和说明](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions)。</span><span class="sxs-lookup"><span data-stu-id="af058-179">For more information on each specific permission, see [Usage rights and descriptions](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).</span></span>  

![选择预设权限或自定义权限的选项。](media/Sensitivity-Choose-permissions-settings.png)

<span data-ttu-id="af058-p118">请注意，同一标签可向不同用户授予不同的权限。例如，一个标签可将某些用户分配为审阅者，并可将其他用户分配为共同创作，如下所示。</span><span class="sxs-lookup"><span data-stu-id="af058-p118">Note that the same label can grant different permissions to different users. For example, a single label can assign some users as Reviewer and a different user as Co-author, as shown below.</span></span>

<span data-ttu-id="af058-p119">为此，添加用户或组、向其分配权限并保存这些设置。然后重复这些步骤，添加用户并向其分配权限、每次保存设置。可以根据需要经常执行此操作，以便为不同用户定义不同权限。</span><span class="sxs-lookup"><span data-stu-id="af058-p119">To do this, add users or groups, assign them permissions, and save those settings. Then repeat these steps, adding users and assigning them permissions, saving the settings each time. You can do this as often as necessary, to define different permissions for different users.</span></span>

![具有不同权限的不同用户](media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a><span data-ttu-id="af058-187">Rights Management 颁发者（应用敏感度标签的用户）始终具有完全控制</span><span class="sxs-lookup"><span data-stu-id="af058-187">Rights Management issuer (user applying the sensitivity label) always has Full Control</span></span>

<span data-ttu-id="af058-p120">敏感度标签的加密使用 Azure RMS。当用户通过使用 Azure RMS 应用敏感度标签以保护文档或电子邮件时，该用户变为该内容的Rights Management 颁发者。</span><span class="sxs-lookup"><span data-stu-id="af058-p120">Encryption for a sensitivity label uses Azure RMS. When a user applies a sensitivity label to protect a document or email by using Azure RMS, that user becomes the Rights Management issuers for that content.</span></span>

<span data-ttu-id="af058-190">Rights Management 颁发者将始终被授予对文档或电子邮件的完全控制权限，此外：</span><span class="sxs-lookup"><span data-stu-id="af058-190">The Rights Management issuer is always granted Full Control permissions for the document or email, and in addition:</span></span>

- <span data-ttu-id="af058-191">如果保护设置包含过期日期，则 Rights Management 颁发者在该日期后仍可以打开和编辑文档或电子邮件。</span><span class="sxs-lookup"><span data-stu-id="af058-191">If the protection settings include an expiration date, the Rights Management issuer can still open and edit the document or email after that date.</span></span>
- <span data-ttu-id="af058-192">Rights Management 颁发者可以始终在脱机状态下访问文档或电子邮件。</span><span class="sxs-lookup"><span data-stu-id="af058-192">The Rights Management issuer can always access the document or email offline.</span></span>
- <span data-ttu-id="af058-193">在文档被撤销后，Rights Management 颁发者仍然可以打开该文档。</span><span class="sxs-lookup"><span data-stu-id="af058-193">The Rights Management issuer can still open a document after it is revoked.</span></span>

<span data-ttu-id="af058-194">有关详细信息，请参阅 [Rights Management 颁发者和 Rights Management 所有者](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner)。</span><span class="sxs-lookup"><span data-stu-id="af058-194">For more information, see [Rights Management issuer and Rights Management owner](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).</span></span>

## <a name="let-users-assign-permissions"></a><span data-ttu-id="af058-195">允许用户分配权限</span><span class="sxs-lookup"><span data-stu-id="af058-195">Let users assign permissions</span></span>

<span data-ttu-id="af058-196">可使用下述选项来允许用户在向内容手动应用敏感度标签时分配权限：</span><span class="sxs-lookup"><span data-stu-id="af058-196">You can use these options to let users assign permissions when they manually apply a sensitivity label to content:</span></span>

- <span data-ttu-id="af058-197">在 Outlook 中，用户可强制实施与“**请勿转发**”选项等效的限制。</span><span class="sxs-lookup"><span data-stu-id="af058-197">In Outlook, a user can enforce restrictions equivalent to the **Do Not Forward** option.</span></span> <span data-ttu-id="af058-198">此选项在 Windows 版 Outlook 上本地支持，且不要求你安装 Azure 信息保护统一标签客户端。</span><span class="sxs-lookup"><span data-stu-id="af058-198">This option is supported natively in Outlook on Windows, and does not require you to install the Azure Information Protection unified labeling client.</span></span>
- <span data-ttu-id="af058-199">在 Word、PowerPoint 和 Excel 中，系统会提示用户为特定用户、组或组织选择一个权限级别。</span><span class="sxs-lookup"><span data-stu-id="af058-199">In Word, PowerPoint, and Excel, a user is prompted to select a permission level for specific users, groups, or organizations.</span></span> <span data-ttu-id="af058-200">此选项在这些 Office 应用中本地不受支持，因此你的用户必须安装 Azure 信息保护统一标签客户端。</span><span class="sxs-lookup"><span data-stu-id="af058-200">This option is not supported natively in these Office apps, so your users must install the Azure Information Protection unified labeling client.</span></span>

<span data-ttu-id="af058-201">这些选项可决定哪些应用中将显示敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="af058-201">These options determine in which apps the sensitivity label will appear:</span></span>

- <span data-ttu-id="af058-202">如果敏感度标签仅启用了 Outlook 选项，则该标签仅对 Outlook 中的用户可见。</span><span class="sxs-lookup"><span data-stu-id="af058-202">If the sensitivity label has only the Outlook option enabled, the label will appear to users only in Outlook.</span></span>
- <span data-ttu-id="af058-203">如果敏感度标签仅启用了 Word、PowerPoint 和 Excel 选项，则该标签仅对这些应用中的用户可见。</span><span class="sxs-lookup"><span data-stu-id="af058-203">If the sensitivity label has only the Word, PowerPoint, and Excel option enabled, the label will appear to users only in those apps.</span></span>
- <span data-ttu-id="af058-204">如果敏感度标签启用了上述两个选项，则标签对所有可用应用（Outlook、Word、PowerPoint 和 Excel）中的用户可见。</span><span class="sxs-lookup"><span data-stu-id="af058-204">If the sensitivity label has both options enabled, the label will appear to users in all of the available apps: Outlook, Word, PowerPoint, and Excel.</span></span>

<span data-ttu-id="af058-205">允许用户分配权限的敏感度标签仅可由用户手动应用于内容；它不能自动应用，也不能用作建议的标签。</span><span class="sxs-lookup"><span data-stu-id="af058-205">A sensitivity label that lets users assign permissions can be applied to content only manually by users; it can't be auto-applied or used as a recommended label.</span></span>

> [!NOTE]
> <span data-ttu-id="af058-206">需具备 Azure 信息保护订阅，才可允许用户分配权限。</span><span class="sxs-lookup"><span data-stu-id="af058-206">Letting users assign permissions requires an Azure Information Protection subscription.</span></span> <span data-ttu-id="af058-207">要在 Word、PowerPoint 和 Excel 中使用此功能，必须下载和安装 [Azure 信息保护统一标签客户端](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app)。</span><span class="sxs-lookup"><span data-stu-id="af058-207">To use this feature in Word, PowerPoint, and Excel, you must download and install the [Azure Information Protection unified labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> <span data-ttu-id="af058-208">我们正在开发在这些 Office 应用中对此功能的本机支持，让其无需 Azure 信息保护客户端。</span><span class="sxs-lookup"><span data-stu-id="af058-208">We're working on native support for this feature in these Office apps, so that they won't require the Azure Information Protection client.</span></span> <span data-ttu-id="af058-209">此外，客户端仅在 Windows 上运行，因此 Mac、iOS、Android 和 Office 网页版上尚不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="af058-209">Also, the client runs only on Windows, so this feature is not yet supported on Mac, iOS, Android, or Office for the web.</span></span>

![有关用户定义的权限的加密设置](media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a><span data-ttu-id="af058-211">Outlook 限制</span><span class="sxs-lookup"><span data-stu-id="af058-211">Outlook restrictions</span></span>

<span data-ttu-id="af058-212">在 Outlook 中，当用户向邮件应用允许其分配权限的敏感度标签时，需遵守的限制与“请勿转发”选项相同。</span><span class="sxs-lookup"><span data-stu-id="af058-212">In Outlook, when a user applies a sensitivity label that lets them assign permissions to a message, the restrictions are the same as the Do Not Forward option.</span></span> <span data-ttu-id="af058-213">用户将在邮件顶部看到标签名称和说明，这表示正在保护该内容。</span><span class="sxs-lookup"><span data-stu-id="af058-213">The user will see the label name and description at the top of the message, which indicates the content's being protected.</span></span> <span data-ttu-id="af058-214">与 Word、PowerPoint 和 Excel 不同（详见[下一部分](#word-powerpoint-and-excel-permissions)），系统不会提示用户选择特定权限。</span><span class="sxs-lookup"><span data-stu-id="af058-214">Unlike Word, PowerPoint, and Excel (see the [next section](#word-powerpoint-and-excel-permissions)), users aren't prompted to select specific permissions.</span></span>

![应用于 Outlook 中的邮件的敏感度标签](media/sensitivity-label-outlook-protection-applied.png)

<span data-ttu-id="af058-216">向电子邮件应用“请勿转发”选项时，电子邮件将被加密，且收件人必须通过身份验证。</span><span class="sxs-lookup"><span data-stu-id="af058-216">When the Do Not Forward option is applied to an email, the email is encrypted and recipients must be authenticated.</span></span> <span data-ttu-id="af058-217">其次，收件人不得转发、打印和复制该邮件。</span><span class="sxs-lookup"><span data-stu-id="af058-217">Then, the recipients cannot forward it, print it, or copy from it.</span></span> <span data-ttu-id="af058-218">例如，在 Outlook 客户端中，“转发”按钮不可用，“另存为”和“打印”菜单选项也不可用，并且你不可在“收件人”、“抄送”和“密件抄送”框中添加或更改收件人。</span><span class="sxs-lookup"><span data-stu-id="af058-218">For example, in the Outlook client, the Forward button is not available, the Save As and Print menu options are not available, and you cannot add or change recipients in the To, Cc, or Bcc boxes.</span></span>

<span data-ttu-id="af058-219">自动附加到电子邮件且不受保护的 Office 文档会自动继承相同的限制。</span><span class="sxs-lookup"><span data-stu-id="af058-219">Unprotected Office documents that are attached to the email automatically inherit the same restrictions.</span></span> <span data-ttu-id="af058-220">应用于这些文档的使用权限为“编辑内容”、“编辑”，“保存”，“视图”、“打开”、“阅读”，以及“允许宏”。</span><span class="sxs-lookup"><span data-stu-id="af058-220">The usage rights applied to these documents are Edit Content, Edit; Save; View, Open, Read; and Allow Macros.</span></span> <span data-ttu-id="af058-221">如果用户对附件实施其他使用权限，或者附件并非支持该继承权限的 Office 文档，则用户需要在将文件附加到电子邮件之前保护该文件。</span><span class="sxs-lookup"><span data-stu-id="af058-221">If the user wants different usage rights for an attachment, or the attachment is not an Office document that supports this inherited protection, the user needs to protect the file before attaching it to the email.</span></span>

### <a name="word-powerpoint-and-excel-permissions"></a><span data-ttu-id="af058-222">Word、PowerPoint 和 Excel 权限</span><span class="sxs-lookup"><span data-stu-id="af058-222">Word, PowerPoint, and Excel permissions</span></span>

<span data-ttu-id="af058-223">在 Word、PowerPoint 和 Excel 中，当用户向文档应用允许其分配权限的敏感度标签时，系统会提示他们如下所示来保护内容。</span><span class="sxs-lookup"><span data-stu-id="af058-223">In Word, PowerPoint, and Excel, when a user applies a sensitivity label that lets them assign permissions to a document, they are prompted to protect the content as shown below.</span></span>

<span data-ttu-id="af058-224">用户可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="af058-224">The user can modify records.</span></span>

- <span data-ttu-id="af058-225">选择权限级别，例如查看者（可分配“仅查看”权限）或合著者（可分配“查看”、“编辑”、“复制”和“打印”权限）。</span><span class="sxs-lookup"><span data-stu-id="af058-225">Select a permission level, such as Viewer (which assigns View Only permission) or Co-Author (which assigns View, Edit, Copy, and Print permissions).</span></span>
- <span data-ttu-id="af058-226">选择用户、组或组织。</span><span class="sxs-lookup"><span data-stu-id="af058-226">Select users, groups, or organizations.</span></span> <span data-ttu-id="af058-227">这可包括你所在组织内部或外部的人员。</span><span class="sxs-lookup"><span data-stu-id="af058-227">This can include people both inside or outside your organizations.</span></span>
- <span data-ttu-id="af058-228">设置到期日期，所选用户在该日期后不可访问内容。</span><span class="sxs-lookup"><span data-stu-id="af058-228">Set an expiration date, after which the selected users cannot access the content.</span></span> <span data-ttu-id="af058-229">有关详细信息，请参阅上一部分：[针对脱机访问的 Rights Management 使用许可证](#rights-management-use-license-for-offline-access)。</span><span class="sxs-lookup"><span data-stu-id="af058-229">For more information, see the above section [Rights Management use license for offline access](#rights-management-use-license-for-offline-access).</span></span>

![供用户通过自定义权限进行保护的选项](media/sensitivity-aip-custom-permissions-dialog.png)

## <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a><span data-ttu-id="af058-231">应用标签后，现有加密会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="af058-231">What happens to existing encryption when a label's applied</span></span>

<span data-ttu-id="af058-232">在向内容应用敏感度标签之前，用户可能已通过应用一些其他保护设置进行了内容加密。</span><span class="sxs-lookup"><span data-stu-id="af058-232">Before a sensitivity label is applied to content, it's possible that a user already encrypted the content by applying some other protection setting.</span></span> <span data-ttu-id="af058-233">例如，用户可能已应用：</span><span class="sxs-lookup"><span data-stu-id="af058-233">For example, a user might have applied:</span></span>

- <span data-ttu-id="af058-234">“**请勿转发**”选项。</span><span class="sxs-lookup"><span data-stu-id="af058-234">The **Do Not Forward** option.</span></span>
- <span data-ttu-id="af058-235">通过 Azure 信息保护统一标记客户端实现的自定义保护。</span><span class="sxs-lookup"><span data-stu-id="af058-235">Custom protection by using the Azure Information Protection unified labeling client.</span></span>
- <span data-ttu-id="af058-236">会加密内容但不与标签关联的 Azure 权限管理服务 (RMS) 模板。</span><span class="sxs-lookup"><span data-stu-id="af058-236">An Azure Rights Management Service (RMS) template that encrypts the content but is not associated with a label.</span></span>

<span data-ttu-id="af058-237">下表说明了在向该内容应用敏感度标签后现有加密发生的情况。</span><span class="sxs-lookup"><span data-stu-id="af058-237">This table describe what happens to existing encyption when a sensitivity label is applied to that content.</span></span>
<br/>
<br/>

| |<span data-ttu-id="af058-238">**用户在加密关闭的情况下应用敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="af058-238">**User applies a sensitivity label with encryption turned off**</span></span>|<span data-ttu-id="af058-239">**用户在加密开启的情况下应用敏感度标签**</span><span class="sxs-lookup"><span data-stu-id="af058-239">**User applies a sensitivity label with encryption turned on**</span></span>|<span data-ttu-id="af058-240">**用户应用具有“去除保护”的标签**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="af058-240">**User applies a label with Remove Protection**<sup>1</sup></span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af058-241">**请勿转发**</span><span class="sxs-lookup"><span data-stu-id="af058-241">**Do Not Forward**</span></span>|<span data-ttu-id="af058-242">电子邮件 - 已去除保护</span><span class="sxs-lookup"><span data-stu-id="af058-242">Email - Protection is removed</span></span><br/><span data-ttu-id="af058-243">文档 - 已保留保护</span><span class="sxs-lookup"><span data-stu-id="af058-243">Document - Protection is preserved</span></span>|<span data-ttu-id="af058-244">已应用标签保护</span><span class="sxs-lookup"><span data-stu-id="af058-244">Label protection is applied</span></span>|<span data-ttu-id="af058-245">已删除“**请勿转发**”</span><span class="sxs-lookup"><span data-stu-id="af058-245">**Do Not Forward** is removed</span></span>|
|<span data-ttu-id="af058-246">**自定义保护**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="af058-246">**Custom protection**<sup>1</sup></span></span>|<span data-ttu-id="af058-247">已保留保护</span><span class="sxs-lookup"><span data-stu-id="af058-247">Protection is preserved</span></span>|<span data-ttu-id="af058-248">已应用标签保护</span><span class="sxs-lookup"><span data-stu-id="af058-248">Label protection is applied</span></span>|<span data-ttu-id="af058-249">已去除自定义保护</span><span class="sxs-lookup"><span data-stu-id="af058-249">Custom protection is removed</span></span>|
|<span data-ttu-id="af058-250">**Azure RMS 模板**</span><span class="sxs-lookup"><span data-stu-id="af058-250">**Azure RMS template**</span></span>|<span data-ttu-id="af058-251">已保留保护</span><span class="sxs-lookup"><span data-stu-id="af058-251">Protection is preserved</span></span>|<span data-ttu-id="af058-252">已应用标签保护</span><span class="sxs-lookup"><span data-stu-id="af058-252">Label protection is applied</span></span>|<span data-ttu-id="af058-253">已去除自定义保护</span><span class="sxs-lookup"><span data-stu-id="af058-253">Custom protection is removed</span></span>|

<span data-ttu-id="af058-254"><sup>1</sup>此功能仅在 Azure 信息保护标记客户端中受支持。</span><span class="sxs-lookup"><span data-stu-id="af058-254"><sup>1</sup>This is supported only in the Azure Information Protection labeling client.</span></span>

## <a name="storing-encrypted-content-in-onedrive-and-sharepoint"></a><span data-ttu-id="af058-255">存储 OneDrive 和 SharePoint 中加密的内容</span><span class="sxs-lookup"><span data-stu-id="af058-255">Storing encrypted content in OneDrive and SharePoint</span></span>

<span data-ttu-id="af058-p130">请注意，将加密应用于 OneDrive 和 SharePoint 中存储的文件时，该服务无法处理这些文件的内容。这意味着共同创作、电子数据展示、搜索、Delve 和其他协作功能将无法正常使用。此外，数据丢失防护 (DLP) 策略只适用于元数据（包括 Office 365 标签），但并不适用于这些加密的文件的内容（例如，文件内的信用卡号）。</span><span class="sxs-lookup"><span data-stu-id="af058-p130">Be aware that when encryption is applied to files stored in OneDrive and SharePoint, the service cannot process the contents of these files. This means that features such as co-authoring, eDiscovery, search, Delve, and other collaborative features do not work. Also, data loss prevention (DLP) policies can work only with the metadata (including Office 365 labels) but not the contents of encrypted files (such as credit card numbers within files).</span></span>

<span data-ttu-id="af058-p131">这仅适用于在 OneDrive 和 SharePoint 中存储的内容。在 Exchange Online 中，邮件流规则（也称为传输规则）使用[超级用户帐户](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-super-users)，以便他们能够扫描加密的内容和强制实施 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="af058-p131">This applies only to content stored in OneDrive and SharePoint. In Exchange Online, mail flow rules (also known as transport rules) use the [super user account](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-super-users) so that they can scan encrypted content and enforce DLP policies.</span></span>

## <a name="important-prerequisites"></a><span data-ttu-id="af058-261">重要先决条件</span><span class="sxs-lookup"><span data-stu-id="af058-261">Important prerequisites</span></span>

<span data-ttu-id="af058-262">在使用加密前，可能需要执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="af058-262">Before you can use encryption, you might need to perform these tasks.</span></span>

### <a name="activating-azure-rights-management"></a><span data-ttu-id="af058-263">激活 Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="af058-263">Activating Azure Rights Management</span></span>

<span data-ttu-id="af058-p132">若要使用敏感度标签中的加密，需要在租户中激活 Azure Rights Management 服务。在较新的租户中，该服务在默认情况下为启用状态，但可能需要手动激活该服务。有关详细信息，请参阅[激活 Azure Rights Management](https://docs.microsoft.com/zh-CN/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="af058-p132">To use encryption in sensitivity labels, the Azure Rights Management service needs to be activated in your tenant. In newer tenants, the service is on by default, but you might need to manually activate the service. For more information, see [Activating Azure Rights Management](https://docs.microsoft.com/zh-CN/azure/information-protection/activate-service).</span></span>

### <a name="configure-exchange-for-azure-information-protection"></a><span data-ttu-id="af058-267">配置用于 Azure 信息保护的 Exchange</span><span class="sxs-lookup"><span data-stu-id="af058-267">Configure Exchange for Azure Information Protection</span></span>

<span data-ttu-id="af058-p133">在用户能够在 Outlook 中应用标签以保护其电子邮件前，无需对 Exchange 进行配置以用于 Azure 信息保护。但是，如果没有针对 Azure 信息保护对 Exchange 进行配置，你将无法在 Exchange 中获取使用 Azure Rights Management 的完整功能。</span><span class="sxs-lookup"><span data-stu-id="af058-p133">Exchange does not have to be configured for Azure Information Protection before users can apply labels in Outlook to protect their emails. However, until Exchange is configured for Azure Information Protection, you do not get the full functionality of using Azure Rights Management protection with Exchange.</span></span>
 
<span data-ttu-id="af058-270">例如，用户无法查看移动电话或 Outlook 网页版上受保护的电子邮件，无法索引受保护的电子邮件以用于搜索，并且无法针对 Rights Management 保护配置 Exchange Online DLP。</span><span class="sxs-lookup"><span data-stu-id="af058-270">For example, users cannot view protected emails on mobile phones or with Outlook on the web, protected emails cannot be indexed for search, and you cannot configure Exchange Online DLP for Rights Management protection.</span></span> 

<span data-ttu-id="af058-271">为确保 Exchange 可以支持这些其他应用场景，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="af058-271">To ensure that Exchange can support these additional scenarios, see the following:</span></span>

- <span data-ttu-id="af058-272">对于 Exchange Online，请参阅 [Exchange Online：IRM 配置](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-office365#exchange-online-irm-configuration)的说明。</span><span class="sxs-lookup"><span data-stu-id="af058-272">For Exchange Online, see the instructions for [Exchange Online: IRM Configuration](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-office365#exchange-online-irm-configuration).</span></span>
- <span data-ttu-id="af058-273">对于本地 Exchange，必须部署 [RMS 连接器并配置你的 Exchange 服务器](https://docs.microsoft.com/zh-CN/azure/information-protection/deploy-rms-connector)。</span><span class="sxs-lookup"><span data-stu-id="af058-273">For Exchange on-premises, you must deploy the [RMS connector and configure your Exchange servers](https://docs.microsoft.com/zh-CN/azure/information-protection/deploy-rms-connector).</span></span> 

---
title: 在 Office 365 中存档第三方数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 管理员可以将来自社交媒体平台、即时消息平台和文档协作平台的第三方数据导入 Office 365 组织中的邮箱。 这样, 你就可以在 Office 365 中存档 Facebook、Twitter 和其他第三方数据源中的数据。 然后, 您可以使用并应用适用于第三方数据的 Office 365 合规性功能 (如法律封存、电子数据展示、就地存档和保留策略)。
ms.openlocfilehash: b96c4852c3c9226219120a1be014ea3988cf91a2
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33402910"
---
# <a name="archive-third-party-data-in-office-365"></a><span data-ttu-id="89e0c-105">在 Office 365 中存档第三方数据</span><span class="sxs-lookup"><span data-stu-id="89e0c-105">Archive third-party data in Office 365</span></span>

<span data-ttu-id="89e0c-106">office 365 使管理员能够从社交媒体平台、即时消息平台和文档协作平台将第三方数据导入和存档到 Office 365 组织中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="89e0c-106">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization.</span></span> <span data-ttu-id="89e0c-107">可以导入到 Office 365 的第三方数据源示例包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="89e0c-107">Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="89e0c-108">**社交**-Twitter、Facebook、Yammer 和 LinkedIn</span><span class="sxs-lookup"><span data-stu-id="89e0c-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="89e0c-109">**即时消息**-Yahoo Messenger、GoogleTalk 和 Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="89e0c-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="89e0c-110">**文档协作**-Box 和 DropBox</span><span class="sxs-lookup"><span data-stu-id="89e0c-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="89e0c-111">**垂直行业**-客户关系管理 (如 Salesforce Chatter) 和金融服务 (如 Bloomberg 和 Thomson Reuters)</span><span class="sxs-lookup"><span data-stu-id="89e0c-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span> 
    
- <span data-ttu-id="89e0c-112">**SMS/短信**-BlackBerry</span><span class="sxs-lookup"><span data-stu-id="89e0c-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="89e0c-113">导入第三方数据后, 可以将 Office 365 合规性功能 (如诉讼保留、电子数据展示、就地存档、审核、监督和 Office 365 保留策略) 应用于此类数据。</span><span class="sxs-lookup"><span data-stu-id="89e0c-113">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Supervision, and Office 365 retention policies—to this data.</span></span> <span data-ttu-id="89e0c-114">例如，当将邮箱置于诉讼保留时，将保留第三方数据。</span><span class="sxs-lookup"><span data-stu-id="89e0c-114">For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved.</span></span> <span data-ttu-id="89e0c-115">您可以使用 Microsoft 电子数据展示工具搜索第三方数据。</span><span class="sxs-lookup"><span data-stu-id="89e0c-115">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="89e0c-116">或者，您可以将存档和保留策略应用于第三方数据，就像可以应用于 Microsoft 数据那样。</span><span class="sxs-lookup"><span data-stu-id="89e0c-116">Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="89e0c-117">简言之, 在 Office 365 中存档第三方数据可帮助您的组织遵守政府和法规策略。</span><span class="sxs-lookup"><span data-stu-id="89e0c-117">In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="89e0c-118">有两种方法可在 Office 365 中导入和存档第三方数据:</span><span class="sxs-lookup"><span data-stu-id="89e0c-118">There are two ways to import and archive third-party data in Office 365:</span></span>

- <span data-ttu-id="89e0c-119">**在安全 & 合规中心中使用第三方数据连接器**-使用在 Office 365 的 security & 合规性中心中提供的自定义数据连接器。</span><span class="sxs-lookup"><span data-stu-id="89e0c-119">**Use a third-party data connector in the Security & Compliance Center** - Use a custom data connector that's available in the Security & Compliance Center in Office 365.</span></span> <span data-ttu-id="89e0c-120">设置并配置连接器后, 它会连接到第三方数据源, 将项目的内容转换为电子邮件格式, 然后将该项目导入 Office 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="89e0c-120">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Office 365.</span></span> <span data-ttu-id="89e0c-121">有关这些连接器支持的第三方数据源和设置连接器的分步过程, 请参阅[使用示例连接器存档 Office 365 中的第三方数据 (预览)](archive-third-party-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="89e0c-121">For the third-party data sources supported by these connectors and the step-by-step process to set up a connector, see [Use sample connectors to archive third-party data in Office 365 (Preview)](archive-third-party-data-with-sample-connector.md).</span></span>

- <span data-ttu-id="89e0c-122">**使用 microsoft 合作伙伴**-你的组织与 microsoft 合作伙伴合作, 该合作伙伴将提供一个自定义连接器, 该合作伙伴将配置为从第三方数据源提取项目 (定期), 然后连接到 Microsoft 云第三方 API 并将这些项目导入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="89e0c-122">**Work with a Microsoft partner** - Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source (on a regular basis) and then connect to the Microsoft cloud by a third-party API and import those items to Office 365.</span></span> <span data-ttu-id="89e0c-123">合作伙伴连接器还将项目的内容从第三方数据源转换为电子邮件, 然后将其导入到 Office 365 中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="89e0c-123">The partner connector also converts the content of an item from the third-party data source to an email message and then imports them to a mailbox in Office 365.</span></span> <span data-ttu-id="89e0c-124">有关可以使用的合作伙伴列表和此方法的分步过程, 请参阅在[Office 365 中存档第三方数据](work-with-partner-to-archive-third-party-data.md)的合作合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="89e0c-124">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>
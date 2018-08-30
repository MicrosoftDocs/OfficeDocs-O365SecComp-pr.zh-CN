---
title: 在 Office 365 中存档第三方数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 管理员可以从导入第三方数据社交媒体平台、 即时消息平台，以及文档协作平台到 Office 365 组织中的邮箱。这样可以存档来自 Office 365 中的 Facebook、 Twitter 和数据源的数据。然后您可以对第三方数据 appply Office 365 合规性功能 （如合法保留、 内容搜索和保留策略）。
ms.openlocfilehash: 3d51d9f5cb546b33fa636fab0ca319e4d24b1ad4
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23230034"
---
# <a name="archiving-third-party-data-in-office-365"></a><span data-ttu-id="b405a-105">在 Office 365 中存档第三方数据</span><span class="sxs-lookup"><span data-stu-id="b405a-105">Archiving third-party data in Office 365</span></span>

<span data-ttu-id="b405a-p102">Office 365 允许管理员导入和存档即时消息平台和文档协作平台，对您的 Office 365 组织中邮箱的从社交媒体平台的第三方数据。可以导入到 Office 365 的第三方数据源的示例包括：</span><span class="sxs-lookup"><span data-stu-id="b405a-p102">Office 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Office 365 organization. Examples of third-party data sources that you can import to Office 365 include the following:</span></span> 
  
- <span data-ttu-id="b405a-108">**社交**-Twitter、 Facebook、 Yammer 和 LinkedIn</span><span class="sxs-lookup"><span data-stu-id="b405a-108">**Social** - Twitter, Facebook, Yammer, and LinkedIn</span></span> 
    
- <span data-ttu-id="b405a-109">**即时消息**-Yahoo Messenger 和 GoogleTalk，Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="b405a-109">**Instant messaging** - Yahoo Messenger, GoogleTalk, and Cisco Jabber</span></span> 
    
- <span data-ttu-id="b405a-110">**文档协作**-框和收存箱</span><span class="sxs-lookup"><span data-stu-id="b405a-110">**Document collaboration** - Box and DropBox</span></span> 
    
- <span data-ttu-id="b405a-111">**纵向行业**-客户关系管理 （如销售队伍争议） 和财务 （如 Thomson Reuters 和彭博美国）</span><span class="sxs-lookup"><span data-stu-id="b405a-111">**Vertical industries** - Customer Relationship Management (such as Salesforce Chatter) and Financials (such as Thomson Reuters and Bloomberg)</span></span> 
    
- <span data-ttu-id="b405a-112">**SMS/短信服务**的 BlackBerry</span><span class="sxs-lookup"><span data-stu-id="b405a-112">**SMS/text messaging** - BlackBerry</span></span> 
    
<span data-ttu-id="b405a-p103">导入第三方数据后，您可以应用 Office 365 合规性功能，如诉讼保留、 内容搜索、 就地存档、 审核和 Office 365 的保留策略 — 对此数据。例如，当邮箱置于诉讼保留，将保留第三方的数据。您可以通过使用内容搜索中搜索第三方数据。或可应用存档和保留策略与第三方数据像可用于 Microsoft 数据。简而言之，存档 Office 365 中的第三方数据可帮助组织保持符合政府和法规的策略。</span><span class="sxs-lookup"><span data-stu-id="b405a-p103">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data. For example, when a mailbox is placed on Litigation Hold, third-party data will be preserved. You can search third-party data by using Content Search. Or you can apply archiving and retention polices to third-party data just like you can for Microsoft data. In short, archiving third-party data in Office 365 can help your organization stay compliant with government and regulatory policies.</span></span>
  
<span data-ttu-id="b405a-118">下面是第三方数据导入到 Office 365 所需的过程和步骤概述。</span><span class="sxs-lookup"><span data-stu-id="b405a-118">Here's an overview of the process and the steps necessary to import third-party data to Office 365.</span></span>

[<span data-ttu-id="b405a-119">步骤 1：寻找第三方数据合作伙伴</span><span class="sxs-lookup"><span data-stu-id="b405a-119">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="b405a-120">步骤 2：在 Office 365 中创建和配置第三方数据邮箱</span><span class="sxs-lookup"><span data-stu-id="b405a-120">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="b405a-121">步骤 3：为第三方数据配置用户邮箱</span><span class="sxs-lookup"><span data-stu-id="b405a-121">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="b405a-122">步骤 4：为合作伙伴提供信息</span><span class="sxs-lookup"><span data-stu-id="b405a-122">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="b405a-123">如何第三方数据导入过程适用于 ></span><span class="sxs-lookup"><span data-stu-id="b405a-123">How the third-party data import process works></span></span>

<span data-ttu-id="b405a-124">下图及说明介绍了第三方数据导入过程的工作原理。</span><span class="sxs-lookup"><span data-stu-id="b405a-124">The following illustration and description explain how the third-party data import process works.</span></span>
  
![第三方数据导入过程的工作原理](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="b405a-126">选择要配置连接器，将从第三方数据源提取项目，然后将这些项目导入到 Office 365 其合作伙伴适用于客户。</span><span class="sxs-lookup"><span data-stu-id="b405a-126">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="b405a-p104">合作伙伴连接器连接到通过第三方 API （基于计划或作为配置） 的第三方数据源，并从数据源提取项目。合作伙伴连接器将项目的内容转换为电子邮件格式。请参阅有关的邮件格式架构的说明[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="b405a-p104">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source. The partner connector converts the content of an item to an email message format. See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="b405a-130">合作伙伴连接器连接到 Office 365 中的 Azure 服务使用通过已知的终结点的 Exchange Web 服务 (EWS)。</span><span class="sxs-lookup"><span data-stu-id="b405a-130">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="b405a-p105">项目便导入到特定用户的邮箱或“catch-all”第三方数据邮箱。无论项目是导入到特定用户邮箱还是第三方数据邮箱，都要基于以下条件：</span><span class="sxs-lookup"><span data-stu-id="b405a-p105">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="b405a-p106">答：**项目的具有对应于 Office 365 用户帐户的用户 ID** -如果合作伙伴连接器可以将第三方数据源中的项的用户 ID 映射到特定用户在 Office 365 中，项目 ID 被复制到用户的中的**清除**文件夹可恢复项目文件夹。用户无法访问清除文件夹中的项目。但是，您可以使用 Office 365 电子数据展示工具搜索清除文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="b405a-p106">a. **Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder. Users can't access items in the Purges folder. However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="b405a-p107">b.**不具有对应于 Office 365 用户帐户的用户 ID 的项**-合作伙伴连接器无法将项目的用户 ID 映射到特定用户在 Office 365 中，项目 ID 被复制到第三方数据邮箱的**收件箱**文件夹。将项目导入到收件箱中登录到要查看和管理这些项，以及是否需要在合作伙伴连接器配置进行任何调整的第三方邮箱贵组织允许您或其他人。</span><span class="sxs-lookup"><span data-stu-id="b405a-p107">b. **Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox. Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="b405a-140">步骤 1：寻找第三方数据合作伙伴</span><span class="sxs-lookup"><span data-stu-id="b405a-140">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="b405a-p108">为 Office 365 中的第三方数据存档的关键组件是查找并使用第三方数据源的数据捕获和导入到 Office 365 中的 Microsoft 合作伙伴，专门。导入的数据后，它可以存档和保留与您的组织的其他 Microsoft 数据，如电子邮件从 Exchange 和 SharePoint 和 OneDrive for Business 中的文档。合作伙伴创建从组织的第三方数据源 （如 BlackBerry、 Facebook、 Google +、 Thomson Reuters、 Twitter 和 YouTube） 提取数据，并将该数据传递给将项目导入到 Exchange 邮箱作为 Office 365 API 的连接器将电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b405a-p108">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365. After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business. A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="b405a-144">以下各节列出 Microsoft 合作伙伴 — 和它们支持第三方数据源 — 为 Office 365 中的第三方数据存档程序正在参与。</span><span class="sxs-lookup"><span data-stu-id="b405a-144">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="b405a-145">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="b405a-145">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="b405a-146">Actiance</span><span class="sxs-lookup"><span data-stu-id="b405a-146">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="b405a-147">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="b405a-147">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="b405a-148">Globanet</span><span class="sxs-lookup"><span data-stu-id="b405a-148">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="b405a-149">OpenText</span><span class="sxs-lookup"><span data-stu-id="b405a-149">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="b405a-150">Verba</span><span class="sxs-lookup"><span data-stu-id="b405a-150">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="b405a-151">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="b405a-151">17a-4 LLC</span></span>

<span data-ttu-id="b405a-152">17a-4 LLC 支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="b405a-152">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="b405a-153">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="b405a-153">BlackBerry</span></span>
    
- <span data-ttu-id="b405a-154">Bloomberg 数据流</span><span class="sxs-lookup"><span data-stu-id="b405a-154">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="b405a-155">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="b405a-155">Cisco Jabber</span></span>
    
- <span data-ttu-id="b405a-156">FactSet</span><span class="sxs-lookup"><span data-stu-id="b405a-156">FactSet</span></span>
    
- <span data-ttu-id="b405a-157">HipChat</span><span class="sxs-lookup"><span data-stu-id="b405a-157">HipChat</span></span>
    
- <span data-ttu-id="b405a-158">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="b405a-158">InvestEdge</span></span>
    
- <span data-ttu-id="b405a-159">LivePerson</span><span class="sxs-lookup"><span data-stu-id="b405a-159">LivePerson</span></span>
    
- <span data-ttu-id="b405a-160">
MessageLabs 数据流
</span><span class="sxs-lookup"><span data-stu-id="b405a-160">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="b405a-161">OpenText</span><span class="sxs-lookup"><span data-stu-id="b405a-161">OpenText</span></span>
    
- <span data-ttu-id="b405a-162">Oracle/ATG“单击以呼叫”Live 帮助
</span><span class="sxs-lookup"><span data-stu-id="b405a-162">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="b405a-163">Pivot IMTRADER
</span><span class="sxs-lookup"><span data-stu-id="b405a-163">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="b405a-164">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="b405a-164">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="b405a-165">MindAlign</span><span class="sxs-lookup"><span data-stu-id="b405a-165">MindAlign</span></span>
    
- <span data-ttu-id="b405a-166">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="b405a-166">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="b405a-167">
Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="b405a-167">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="b405a-168">
Skype for Business Online (Lync Online)
</span><span class="sxs-lookup"><span data-stu-id="b405a-168">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="b405a-169">SQL 数据库</span><span class="sxs-lookup"><span data-stu-id="b405a-169">SQL Databases</span></span>
    
- <span data-ttu-id="b405a-170">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="b405a-170">Squawker</span></span>
    
- <span data-ttu-id="b405a-171">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="b405a-171">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="b405a-172">Actiance</span><span class="sxs-lookup"><span data-stu-id="b405a-172">Actiance</span></span>

<span data-ttu-id="b405a-173">[Actiance](https://www.actiance.com)支持下列第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="b405a-173">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="b405a-174">AIM</span><span class="sxs-lookup"><span data-stu-id="b405a-174">AIM</span></span>
    
- <span data-ttu-id="b405a-175">American Idol</span><span class="sxs-lookup"><span data-stu-id="b405a-175">American Idol</span></span>
    
- <span data-ttu-id="b405a-176">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="b405a-176">Apple Juice</span></span>
    
- <span data-ttu-id="b405a-177">
使用 Pivot 客户端的 AOL
</span><span class="sxs-lookup"><span data-stu-id="b405a-177">AOL with Pivot client</span></span>
    
- <span data-ttu-id="b405a-178">Ares</span><span class="sxs-lookup"><span data-stu-id="b405a-178">Ares</span></span>
    
- <span data-ttu-id="b405a-179">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="b405a-179">Bazaar Voice</span></span>
    
- <span data-ttu-id="b405a-180">Bear Share</span><span class="sxs-lookup"><span data-stu-id="b405a-180">Bear Share</span></span>
    
- <span data-ttu-id="b405a-181">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="b405a-181">Bit Torrent</span></span>
    
- <span data-ttu-id="b405a-182">BlackBerry 呼叫日志（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="b405a-182">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="b405a-183">BlackBerry Messenger（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="b405a-183">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="b405a-184">BlackBerry PIN（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="b405a-184">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="b405a-185">BlackBerry 短信（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="b405a-185">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="b405a-186">Bloomberg 邮件
</span><span class="sxs-lookup"><span data-stu-id="b405a-186">Bloomberg Mail</span></span>
    
- <span data-ttu-id="b405a-187">CellTrust</span><span class="sxs-lookup"><span data-stu-id="b405a-187">CellTrust</span></span>
    
- <span data-ttu-id="b405a-188">Chat Import
</span><span class="sxs-lookup"><span data-stu-id="b405a-188">Chat Import</span></span>
    
- <span data-ttu-id="b405a-189">聊天实时日志记录和策略
</span><span class="sxs-lookup"><span data-stu-id="b405a-189">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="b405a-190">Chatter
</span><span class="sxs-lookup"><span data-stu-id="b405a-190">Chatter</span></span>
    
- <span data-ttu-id="b405a-191">Cisco IM&amp;状态服务器 (v9.0.1、 v9.1，v9.1.1 SU1、 v10，v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="b405a-191">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="b405a-192">Cisco Unified Presence 服务器（v8.6.3、v8.6.4、v8.6.5）
</span><span class="sxs-lookup"><span data-stu-id="b405a-192">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="b405a-193">协作导入
</span><span class="sxs-lookup"><span data-stu-id="b405a-193">Collaboration Import</span></span>
    
- <span data-ttu-id="b405a-194">协作实时日志记录
</span><span class="sxs-lookup"><span data-stu-id="b405a-194">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="b405a-195">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="b405a-195">Direct Connect</span></span>
    
- <span data-ttu-id="b405a-196">Facebook</span><span class="sxs-lookup"><span data-stu-id="b405a-196">Facebook</span></span>
    
- <span data-ttu-id="b405a-197">FactSet</span><span class="sxs-lookup"><span data-stu-id="b405a-197">FactSet</span></span>
    
- <span data-ttu-id="b405a-198">FastTrack</span><span class="sxs-lookup"><span data-stu-id="b405a-198">FastTrack</span></span>
    
- <span data-ttu-id="b405a-199">Gnutella</span><span class="sxs-lookup"><span data-stu-id="b405a-199">Gnutella</span></span>
    
- <span data-ttu-id="b405a-200">Google+
</span><span class="sxs-lookup"><span data-stu-id="b405a-200">Google+</span></span>
    
- <span data-ttu-id="b405a-201">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="b405a-201">GoToMyPC</span></span>
    
- <span data-ttu-id="b405a-202">Hopster</span><span class="sxs-lookup"><span data-stu-id="b405a-202">Hopster</span></span>
    
- <span data-ttu-id="b405a-203">HubConnex</span><span class="sxs-lookup"><span data-stu-id="b405a-203">HubConnex</span></span>
    
- <span data-ttu-id="b405a-204">IBM Connections（v3.0.1、v4.0、v4.5、v4.5 CR3、v5）
</span><span class="sxs-lookup"><span data-stu-id="b405a-204">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="b405a-205">IBM Connections Chat Cloud
</span><span class="sxs-lookup"><span data-stu-id="b405a-205">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="b405a-206">IBM Connections Social Cloud
</span><span class="sxs-lookup"><span data-stu-id="b405a-206">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="b405a-207">IBM SameTime Advanced 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="b405a-207">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="b405a-208">IBM SameTime Communicate 9.0
</span><span class="sxs-lookup"><span data-stu-id="b405a-208">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="b405a-209">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)
</span><span class="sxs-lookup"><span data-stu-id="b405a-209">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="b405a-210">IBM SameTime Complete 9.0
</span><span class="sxs-lookup"><span data-stu-id="b405a-210">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="b405a-211">IBM SameTime Conference 9.0
</span><span class="sxs-lookup"><span data-stu-id="b405a-211">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="b405a-212">IBM SameTime Meeting 8.5.2 IFR1
</span><span class="sxs-lookup"><span data-stu-id="b405a-212">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="b405a-213">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="b405a-213">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="b405a-214">即时消息导入
</span><span class="sxs-lookup"><span data-stu-id="b405a-214">IM Import</span></span>
    
- <span data-ttu-id="b405a-215">即时消息实时日志记录和策略
</span><span class="sxs-lookup"><span data-stu-id="b405a-215">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="b405a-216">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="b405a-216">Indii Messenger</span></span>
    
- <span data-ttu-id="b405a-217">即时 Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="b405a-217">Instant Bloomberg</span></span>
    
- <span data-ttu-id="b405a-218">IRC</span><span class="sxs-lookup"><span data-stu-id="b405a-218">IRC</span></span>
    
- <span data-ttu-id="b405a-219">Jive
</span><span class="sxs-lookup"><span data-stu-id="b405a-219">Jive</span></span>
    
- <span data-ttu-id="b405a-220">Jive 6 实时日志记录（v6、v7）
</span><span class="sxs-lookup"><span data-stu-id="b405a-220">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="b405a-221">Jive 导入</span><span class="sxs-lookup"><span data-stu-id="b405a-221">Jive Import</span></span>
    
- <span data-ttu-id="b405a-222">JXTA</span><span class="sxs-lookup"><span data-stu-id="b405a-222">JXTA</span></span>
    
- <span data-ttu-id="b405a-223">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="b405a-223">LinkedIn</span></span>
    
- <span data-ttu-id="b405a-224">
Microsoft Lync（2010、2013）
</span><span class="sxs-lookup"><span data-stu-id="b405a-224">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="b405a-225">MFTP</span><span class="sxs-lookup"><span data-stu-id="b405a-225">MFTP</span></span>
    
- <span data-ttu-id="b405a-226">Microsoft Lync 2013 语音
</span><span class="sxs-lookup"><span data-stu-id="b405a-226">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="b405a-227">Microsoft SharePoint（2010、2013）
</span><span class="sxs-lookup"><span data-stu-id="b405a-227">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="b405a-228">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b405a-228">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="b405a-229">Microsoft UC（统一通信）</span><span class="sxs-lookup"><span data-stu-id="b405a-229">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="b405a-230">MindAlign</span><span class="sxs-lookup"><span data-stu-id="b405a-230">MindAlign</span></span>
    
- <span data-ttu-id="b405a-231">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="b405a-231">Mobile Guard</span></span>
    
- <span data-ttu-id="b405a-232">MSN</span><span class="sxs-lookup"><span data-stu-id="b405a-232">MSN</span></span>
    
- <span data-ttu-id="b405a-233">My Space</span><span class="sxs-lookup"><span data-stu-id="b405a-233">My Space</span></span>
    
- <span data-ttu-id="b405a-234">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="b405a-234">NEONetwork</span></span>
    
- <span data-ttu-id="b405a-235">Office 365 Lync 专用
</span><span class="sxs-lookup"><span data-stu-id="b405a-235">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="b405a-236">Office 365 共享即时消息
</span><span class="sxs-lookup"><span data-stu-id="b405a-236">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="b405a-237">Pinterest</span><span class="sxs-lookup"><span data-stu-id="b405a-237">Pinterest</span></span>
    
- <span data-ttu-id="b405a-238">Pivot</span><span class="sxs-lookup"><span data-stu-id="b405a-238">Pivot</span></span>
    
- <span data-ttu-id="b405a-239">QQ</span><span class="sxs-lookup"><span data-stu-id="b405a-239">QQ</span></span>
    
- <span data-ttu-id="b405a-240">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="b405a-240">Skype for Business 2015</span></span>
    
- <span data-ttu-id="b405a-241">SoftEther</span><span class="sxs-lookup"><span data-stu-id="b405a-241">SoftEther</span></span>
    
- <span data-ttu-id="b405a-242">Symphony
</span><span class="sxs-lookup"><span data-stu-id="b405a-242">Symphony</span></span>
    
- <span data-ttu-id="b405a-243">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="b405a-243">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="b405a-244">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="b405a-244">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="b405a-245">Tor</span><span class="sxs-lookup"><span data-stu-id="b405a-245">Tor</span></span>
    
- <span data-ttu-id="b405a-246">TTT</span><span class="sxs-lookup"><span data-stu-id="b405a-246">TTT</span></span>
    
- <span data-ttu-id="b405a-247">Twitter</span><span class="sxs-lookup"><span data-stu-id="b405a-247">Twitter</span></span>
    
- <span data-ttu-id="b405a-248">WinMX</span><span class="sxs-lookup"><span data-stu-id="b405a-248">WinMX</span></span>
    
- <span data-ttu-id="b405a-249">Winny</span><span class="sxs-lookup"><span data-stu-id="b405a-249">Winny</span></span>
    
- <span data-ttu-id="b405a-250">Yahoo
</span><span class="sxs-lookup"><span data-stu-id="b405a-250">Yahoo</span></span>
    
- <span data-ttu-id="b405a-251">Yammer</span><span class="sxs-lookup"><span data-stu-id="b405a-251">Yammer</span></span>
    
- <span data-ttu-id="b405a-252">YouTube</span><span class="sxs-lookup"><span data-stu-id="b405a-252">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="b405a-253">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="b405a-253">ArchiveSocial</span></span>

<span data-ttu-id="b405a-254">[ArchiveSocial](https://www.archivesocial.com)支持下列第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="b405a-254">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="b405a-255">Facebook</span><span class="sxs-lookup"><span data-stu-id="b405a-255">Facebook</span></span>
    
- <span data-ttu-id="b405a-256">Flickr
</span><span class="sxs-lookup"><span data-stu-id="b405a-256">Flickr</span></span>
    
- <span data-ttu-id="b405a-257">Instagram
</span><span class="sxs-lookup"><span data-stu-id="b405a-257">Instagram</span></span>
    
- <span data-ttu-id="b405a-258">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="b405a-258">LinkedIn</span></span>
    
- <span data-ttu-id="b405a-259">Pinterest</span><span class="sxs-lookup"><span data-stu-id="b405a-259">Pinterest</span></span>
    
- <span data-ttu-id="b405a-260">Twitter</span><span class="sxs-lookup"><span data-stu-id="b405a-260">Twitter</span></span>
    
- <span data-ttu-id="b405a-261">YouTube</span><span class="sxs-lookup"><span data-stu-id="b405a-261">YouTube</span></span>
    
- <span data-ttu-id="b405a-262">Vimeo</span><span class="sxs-lookup"><span data-stu-id="b405a-262">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="b405a-263">Globanet</span><span class="sxs-lookup"><span data-stu-id="b405a-263">Globanet</span></span>

<span data-ttu-id="b405a-264">[Globanet](https://www.globanet.com)支持下列第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="b405a-264">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="b405a-265">使用 Pivot 客户端的 AOL</span><span class="sxs-lookup"><span data-stu-id="b405a-265">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="b405a-266">BlackBerry 呼叫日志（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="b405a-266">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="b405a-267">BlackBerry Messenger（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="b405a-267">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="b405a-268">BlackBerry PIN（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="b405a-268">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="b405a-269">BlackBerry 短信（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="b405a-269">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="b405a-270">Bloomberg 聊天
</span><span class="sxs-lookup"><span data-stu-id="b405a-270">Bloomberg Chat</span></span>
    
- <span data-ttu-id="b405a-271">Bloomberg 邮件
</span><span class="sxs-lookup"><span data-stu-id="b405a-271">Bloomberg Mail</span></span>
    
- <span data-ttu-id="b405a-272">Box
</span><span class="sxs-lookup"><span data-stu-id="b405a-272">Box</span></span>
    
- <span data-ttu-id="b405a-273">适用于 Salesforce Chatter 的 CipherCloud</span><span class="sxs-lookup"><span data-stu-id="b405a-273">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="b405a-274">Cisco IM&amp;状态服务器 (v10，v10.5.1 SU1 v11.0，v11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="b405a-274">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="b405a-275">Cisco Webex 团队</span><span class="sxs-lookup"><span data-stu-id="b405a-275">Cisco Webex Teams</span></span>

- <span data-ttu-id="b405a-276">Citrix 工作区&amp;ShareFile</span><span class="sxs-lookup"><span data-stu-id="b405a-276">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="b405a-277">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="b405a-277">CrowdCompass</span></span>

- <span data-ttu-id="b405a-278">自定义带分隔符的文本文件
</span><span class="sxs-lookup"><span data-stu-id="b405a-278">Custom delimited text files</span></span>
    
- <span data-ttu-id="b405a-279">自定义 XML 文件
</span><span class="sxs-lookup"><span data-stu-id="b405a-279">Custom XML files</span></span>
    
- <span data-ttu-id="b405a-280">Facebook （页）</span><span class="sxs-lookup"><span data-stu-id="b405a-280">Facebook (Pages)</span></span>
    
- <span data-ttu-id="b405a-281">Factset
</span><span class="sxs-lookup"><span data-stu-id="b405a-281">Factset</span></span>
    
- <span data-ttu-id="b405a-282">FXConnect</span><span class="sxs-lookup"><span data-stu-id="b405a-282">FXConnect</span></span>
    
- <span data-ttu-id="b405a-283">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="b405a-283">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="b405a-284">Jive
</span><span class="sxs-lookup"><span data-stu-id="b405a-284">Jive</span></span>
    
- <span data-ttu-id="b405a-285">Macgregor XIP
</span><span class="sxs-lookup"><span data-stu-id="b405a-285">Macgregor XIP</span></span>

- <span data-ttu-id="b405a-286">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b405a-286">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="b405a-287">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="b405a-287">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="b405a-288">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b405a-288">Microsoft Teams</span></span>
       
- <span data-ttu-id="b405a-289">Microsoft Yammer
</span><span class="sxs-lookup"><span data-stu-id="b405a-289">Microsoft Yammer</span></span>
    
- <span data-ttu-id="b405a-290">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="b405a-290">Mobile Guard</span></span>
    
- <span data-ttu-id="b405a-291">Pivot</span><span class="sxs-lookup"><span data-stu-id="b405a-291">Pivot</span></span>
    
- <span data-ttu-id="b405a-292">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="b405a-292">Salesforce Chatter</span></span>

- <span data-ttu-id="b405a-293">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b405a-293">Skype for Business Online</span></span>
    
- <span data-ttu-id="b405a-294">Skype for Business，版本 2007 R2 - 2016（本地）
</span><span class="sxs-lookup"><span data-stu-id="b405a-294">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="b405a-295">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="b405a-295">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="b405a-296">Symphony
</span><span class="sxs-lookup"><span data-stu-id="b405a-296">Symphony</span></span>
    
- <span data-ttu-id="b405a-297">Thomson Reuters Eikon
</span><span class="sxs-lookup"><span data-stu-id="b405a-297">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="b405a-298">Thomson Reuters Messenger
</span><span class="sxs-lookup"><span data-stu-id="b405a-298">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="b405a-299">Thomson Reuters Dealings 3000 / FX Trading
</span><span class="sxs-lookup"><span data-stu-id="b405a-299">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="b405a-300">Twitter</span><span class="sxs-lookup"><span data-stu-id="b405a-300">Twitter</span></span>
    
- <span data-ttu-id="b405a-301">UBS 聊天
</span><span class="sxs-lookup"><span data-stu-id="b405a-301">UBS Chat</span></span>
    
- <span data-ttu-id="b405a-302">YouTube</span><span class="sxs-lookup"><span data-stu-id="b405a-302">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="b405a-303">OpenText</span><span class="sxs-lookup"><span data-stu-id="b405a-303">OpenText</span></span>

<span data-ttu-id="b405a-304">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)支持下列第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="b405a-304">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="b405a-305">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="b405a-305">Axs Encrypted</span></span>
    
- <span data-ttu-id="b405a-306">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="b405a-306">Axs Exchange</span></span>
    
- <span data-ttu-id="b405a-307">Axs 本地存档</span><span class="sxs-lookup"><span data-stu-id="b405a-307">Axs Local Archive</span></span>
    
- <span data-ttu-id="b405a-308">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="b405a-308">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="b405a-309">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="b405a-309">Axs Signed</span></span>
    
- <span data-ttu-id="b405a-310">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="b405a-310">Bloomberg</span></span>
    
- <span data-ttu-id="b405a-311">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="b405a-311">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="b405a-312">Verba</span><span class="sxs-lookup"><span data-stu-id="b405a-312">Verba</span></span>

<span data-ttu-id="b405a-313">[Verba](https://www.verba.com)支持下列第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="b405a-313">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="b405a-314">Avaya Aura 视频
</span><span class="sxs-lookup"><span data-stu-id="b405a-314">Avaya Aura Video</span></span>
    
- <span data-ttu-id="b405a-315">Avaya Aura 语音
</span><span class="sxs-lookup"><span data-stu-id="b405a-315">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="b405a-316">Avtec 调频广播
</span><span class="sxs-lookup"><span data-stu-id="b405a-316">Avtec Radio</span></span>
    
- <span data-ttu-id="b405a-317">Bosch/Telex 调频广播
</span><span class="sxs-lookup"><span data-stu-id="b405a-317">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="b405a-318">BroadSoft 视频
</span><span class="sxs-lookup"><span data-stu-id="b405a-318">BroadSoft Video</span></span>
    
- <span data-ttu-id="b405a-319">BroadSoft 语音
</span><span class="sxs-lookup"><span data-stu-id="b405a-319">BroadSoft Voice</span></span>
    
- <span data-ttu-id="b405a-320">Centile 语音
</span><span class="sxs-lookup"><span data-stu-id="b405a-320">Centile Voice</span></span>
    
- <span data-ttu-id="b405a-321">Cisco Jabber 即时消息
</span><span class="sxs-lookup"><span data-stu-id="b405a-321">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="b405a-322">Cisco UC 视频
</span><span class="sxs-lookup"><span data-stu-id="b405a-322">Cisco UC Video</span></span>
    
- <span data-ttu-id="b405a-323">Cisco UC 语音
</span><span class="sxs-lookup"><span data-stu-id="b405a-323">Cisco UC Voice</span></span>
    
- <span data-ttu-id="b405a-324">Cisco UCCX/UCCE 视频</span><span class="sxs-lookup"><span data-stu-id="b405a-324">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="b405a-325">Cisco UCCX/UCCE 语音</span><span class="sxs-lookup"><span data-stu-id="b405a-325">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="b405a-326">ESChat 调频广播</span><span class="sxs-lookup"><span data-stu-id="b405a-326">ESChat Radio</span></span>
    
- <span data-ttu-id="b405a-327">Geoman 联络专家</span><span class="sxs-lookup"><span data-stu-id="b405a-327">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="b405a-328">IP Trade 语音
</span><span class="sxs-lookup"><span data-stu-id="b405a-328">IP Trade Voice</span></span>
    
- <span data-ttu-id="b405a-329">Luware LUCS 联络中心</span><span class="sxs-lookup"><span data-stu-id="b405a-329">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="b405a-330">Microsoft UC（统一通信）</span><span class="sxs-lookup"><span data-stu-id="b405a-330">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="b405a-331">适用于 Lync 的 Mitel MiContact 中心 (prairieFyre) 
</span><span class="sxs-lookup"><span data-stu-id="b405a-331">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="b405a-332">Oracle / Acme 数据包会话边界控制器视频  
</span><span class="sxs-lookup"><span data-stu-id="b405a-332">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="b405a-333">Oracle / Acme 数据包会话边界控制器语音
</span><span class="sxs-lookup"><span data-stu-id="b405a-333">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="b405a-334">Singtel Mobile 语音
</span><span class="sxs-lookup"><span data-stu-id="b405a-334">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="b405a-335">SIPREC 视频</span><span class="sxs-lookup"><span data-stu-id="b405a-335">SIPREC Video</span></span>
    
-  <span data-ttu-id="b405a-336">SIPREC 语音</span><span class="sxs-lookup"><span data-stu-id="b405a-336">SIPREC Voice</span></span> 
    
- <span data-ttu-id="b405a-337">Skype for Business/Lync 即时消息
</span><span class="sxs-lookup"><span data-stu-id="b405a-337">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="b405a-338">Skype for Business/Lync 视频
</span><span class="sxs-lookup"><span data-stu-id="b405a-338">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="b405a-339">Skype for Business/Lync 语音
</span><span class="sxs-lookup"><span data-stu-id="b405a-339">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="b405a-340">Speakerbus 语音
</span><span class="sxs-lookup"><span data-stu-id="b405a-340">Speakerbus Voice</span></span>
    
- <span data-ttu-id="b405a-341">标准 SIP/H.323 视频 
</span><span class="sxs-lookup"><span data-stu-id="b405a-341">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="b405a-342">标准 SIP/H.323 语音 
</span><span class="sxs-lookup"><span data-stu-id="b405a-342">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="b405a-343">Truphone 语音
</span><span class="sxs-lookup"><span data-stu-id="b405a-343">Truphone Voice</span></span>
    
- <span data-ttu-id="b405a-344">TwistedPair 调频广播
</span><span class="sxs-lookup"><span data-stu-id="b405a-344">TwistedPair Radio</span></span>
    
- <span data-ttu-id="b405a-345">Windows 桌面计算机屏幕 
</span><span class="sxs-lookup"><span data-stu-id="b405a-345">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="b405a-346">步骤 2：在 Office 365 中创建和配置第三方数据邮箱</span><span class="sxs-lookup"><span data-stu-id="b405a-346">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="b405a-p109">下面是用于创建和配置数据导入到 Office 365 的第三方数据邮箱的步骤。与以前所述，项目被导入到此邮箱的合作伙伴连接器无法将该项目的用户 ID 映射到 Office 365 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b405a-p109">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365. As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="b405a-349">**完成这些任务在 Office 365 管理中心**</span><span class="sxs-lookup"><span data-stu-id="b405a-349">**Complete these tasks in the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="b405a-p110">在 Office 365 中创建新的用户帐户，并将其分配的 Exchange Online 计划 2 许可证;请参阅[添加到 Office 365 的用户](https://go.microsoft.com/fwlink/p/?LinkId=692098)。计划 2 许可证需要将置于诉讼保留状态的邮箱或启用存档邮箱的具有不受限制的存储配额。</span><span class="sxs-lookup"><span data-stu-id="b405a-p110">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="b405a-352">第三方数据邮箱的用户帐户添加到 Office 365; 中的**Exchange 管理员**管理角色请参阅[Office 365 中的管理角色分配](https://go.microsoft.com/fwlink/p/?LinkId=532393)。</span><span class="sxs-lookup"><span data-stu-id="b405a-352">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b405a-p111">写下此用户帐户的凭据。您需要将它们提供给您的合作伙伴，如步骤 4 中所述。</span><span class="sxs-lookup"><span data-stu-id="b405a-p111">Write down the credentials for this user account. You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="b405a-355">**完成这些任务在 Exchange 管理中心**</span><span class="sxs-lookup"><span data-stu-id="b405a-355">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="b405a-p112">第三方数据中隐藏邮箱通讯簿和您的组织; 在其他地址列表请参阅[管理用户邮箱](https://go.microsoft.com/fwlink/p/?LinkId=616058)。此外，还可以运行以下 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="b405a-p112">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058). Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="b405a-358">分配给第三方数据邮箱的**FullAccess**权限，以便管理员或合规部主管可以在 Outlook 桌面客户端，则打开第三方数据邮箱请参阅[Manage permissions for 收件人](https://go.microsoft.com/fwlink/p/?LinkId=692104)。</span><span class="sxs-lookup"><span data-stu-id="b405a-358">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="b405a-359">启用了以下合规性相关 Office 365 功能的第三方数据邮箱：</span><span class="sxs-lookup"><span data-stu-id="b405a-359">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="b405a-p113">启用存档邮箱中;请参阅[Office 365 安全性启用存档邮箱&amp;合规性中心](enable-archive-mailboxes.md)和[启用 Office 365 中的无限制存档](enable-unlimited-archiving.md)。这会让您通过设置将第三方数据项目移动到存档邮箱的存档策略的主邮箱中释放存储空间。这将为您提供不受限制的存储的第三方数据。</span><span class="sxs-lookup"><span data-stu-id="b405a-p113">Enable the archive mailbox; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md). This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox. This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="b405a-p114">将置于诉讼保留状态的第三方数据邮箱。您还可以应用 Office 365 安全性的 Office 365 保留策略&amp;合规性中心。保持发出此邮箱将保留第三方数据项目 （无限期或指定的持续时间），并防止它们从邮箱被清除。请参阅以下主题之一：</span><span class="sxs-lookup"><span data-stu-id="b405a-p114">Place the third-party data mailbox on Litigation Hold. You can also apply an Office 365 retention policy in the Office 365 Security &amp; Compliance Center. Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox. See one of the following topics:</span></span>
    
      - [<span data-ttu-id="b405a-367">将邮箱置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="b405a-367">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="b405a-368">Office 365 中的保留策略概述</span><span class="sxs-lookup"><span data-stu-id="b405a-368">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="b405a-p115">启用邮箱审核日志记录所有者、 委派和管理访问的第三方数据邮箱;请参阅[启用邮箱审核 Office 365 中](enable-mailbox-auditing.md)。这将使您能够审核执行的任何用户都有权访问的第三方数据邮箱的所有活动。</span><span class="sxs-lookup"><span data-stu-id="b405a-p115">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md). This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="b405a-371">步骤 3：为第三方数据配置用户邮箱</span><span class="sxs-lookup"><span data-stu-id="b405a-371">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="b405a-p116">下一步是配置用户邮箱以支持第三方数据。使用 Exchange 管理中心或使用相应的 Windows PowerShell cmdlet，请完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="b405a-p116">The next step is to configure user mailboxes to support third-party data. Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="b405a-374">启用存档邮箱的每个用户;请参阅[Office 365 安全性启用存档邮箱&amp;合规性中心](enable-archive-mailboxes.md)和[启用 Office 365 中的无限制存档](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="b405a-374">Enable the archive mailbox for each user; see [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="b405a-375">将用户邮箱置于诉讼保留或应用 Office 365 的保留策略。请参阅以下主题之一：</span><span class="sxs-lookup"><span data-stu-id="b405a-375">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="b405a-376">将邮箱置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="b405a-376">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="b405a-377">Office 365 中的保留策略概述</span><span class="sxs-lookup"><span data-stu-id="b405a-377">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="b405a-378">如前所述，在将邮箱置于保留时，您可以设置保留第三方数据源中项目的时长，或者也可以选择无限期保留这些项目。</span><span class="sxs-lookup"><span data-stu-id="b405a-378">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="b405a-379">步骤 4：为合作伙伴提供信息</span><span class="sxs-lookup"><span data-stu-id="b405a-379">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="b405a-380">最后一步是为您的合作伙伴提供以下信息，这样他们便能够配置连接器以连接到 Office 365 组织，从而将数据导入到用户邮箱和第三方数据邮箱。</span><span class="sxs-lookup"><span data-stu-id="b405a-380">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="b405a-381">终结点用于连接到 Office 365 中的 Azure 服务：</span><span class="sxs-lookup"><span data-stu-id="b405a-381">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="b405a-p117">您在步骤 2 中创建的第三方数据邮箱 （Office 365 用户 ID 和密码） 凭据登录。这些凭据是必需，以便合作伙伴连接器可以访问和项目导入到用户邮箱和第三方数据邮箱。</span><span class="sxs-lookup"><span data-stu-id="b405a-p117">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2. These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
    

  
## <a name="more-information"></a><span data-ttu-id="b405a-384">详细信息</span><span class="sxs-lookup"><span data-stu-id="b405a-384">More information</span></span>

- <span data-ttu-id="b405a-p118">与以前所述，从第三方数据源导入到 Exchange 邮箱作为电子邮件项目。合作伙伴连接器导入使用所需的 Office 365 API 的架构的项。下表说明了第三方数据源中的项目的邮件属性后导入到 Exchange 邮箱作为电子邮件。表还指示是否强制 message 属性。必须填充必需的属性。如果项目缺少必需属性，它不会导入到 Office 365。导入过程将返回解释原因项目未导入和哪个属性是缺少一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="b405a-p118">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages. The partner connector imports the item using a schema required by the Office 365 API. The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message. The table also indicates if the message property is mandatory. Mandatory properties must be populated. If an item is missing a mandatory property, it won't be imported to Office 365. The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="b405a-392">**邮件属性**</span><span class="sxs-lookup"><span data-stu-id="b405a-392">**Message property**</span></span>|<span data-ttu-id="b405a-393">**必需？**</span><span class="sxs-lookup"><span data-stu-id="b405a-393">**Mandatory?**</span></span>|<span data-ttu-id="b405a-394">**说明**</span><span class="sxs-lookup"><span data-stu-id="b405a-394">**Description**</span></span>|<span data-ttu-id="b405a-395">**示例值**</span><span class="sxs-lookup"><span data-stu-id="b405a-395">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="b405a-396">**发件人**</span><span class="sxs-lookup"><span data-stu-id="b405a-396">**FROM**</span></span> <br/> |<span data-ttu-id="b405a-397">是</span><span class="sxs-lookup"><span data-stu-id="b405a-397">Yes</span></span>  <br/> |<span data-ttu-id="b405a-p119">最初创建或发送第三方数据源中的项目的用户。合作伙伴连接器会尝试将从源项 （例如 Twitter 句柄） 到 Office 365 用户帐户的用户 ID 映射所有参与者 （从和收件人字段中的用户）。邮件的副本将导入到每个参与者的邮箱中。如果无项中的参与者可以映射到 Office 365 用户帐户，该项目将导入到 Office 365 中的第三方存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="b405a-p119">The user who originally created or sent the item in the third-party data source. The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields). A copy of the message will be imported to the mailbox of every participant. If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.  </span></span><br/> <br/> <span data-ttu-id="b405a-p120">标识项目的发件人为参与者必须具有项目正在导入到 Office 365 组织中的活动邮箱。如果发件人没有活动邮箱，则返回以下错误：</span><span class="sxs-lookup"><span data-stu-id="b405a-p120">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to. If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="b405a-404">**收件人**</span><span class="sxs-lookup"><span data-stu-id="b405a-404">**TO**</span></span> <br/> |<span data-ttu-id="b405a-405">是</span><span class="sxs-lookup"><span data-stu-id="b405a-405">Yes</span></span>  <br/> |<span data-ttu-id="b405a-406">接收项目的用户（如果适用于数据源中的项目）。</span><span class="sxs-lookup"><span data-stu-id="b405a-406">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="b405a-407">**主题**</span><span class="sxs-lookup"><span data-stu-id="b405a-407">**SUBJECT**</span></span> <br/> |<span data-ttu-id="b405a-408">否</span><span class="sxs-lookup"><span data-stu-id="b405a-408">No</span></span>  <br/> |<span data-ttu-id="b405a-409">源项目中的主题。</span><span class="sxs-lookup"><span data-stu-id="b405a-409">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="b405a-410">**日期**</span><span class="sxs-lookup"><span data-stu-id="b405a-410">**DATE**</span></span> <br/> |<span data-ttu-id="b405a-411">是</span><span class="sxs-lookup"><span data-stu-id="b405a-411">Yes</span></span>  <br/> |<span data-ttu-id="b405a-412">最初在客户数据源中创建或发布项目的日期；例如，发布 Twitter 消息的日期。</span><span class="sxs-lookup"><span data-stu-id="b405a-412">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="b405a-413">**正文**</span><span class="sxs-lookup"><span data-stu-id="b405a-413">**BODY**</span></span> <br/> |<span data-ttu-id="b405a-414">否</span><span class="sxs-lookup"><span data-stu-id="b405a-414">No</span></span>  <br/> |<span data-ttu-id="b405a-p121">Post 消息的内容。对于某些数据源，此属性的内容可能是**SUBJECT**属性的内容相同。在导入过程中，合作伙伴连接器将尝试维护尽可能的内容源的完全保真的。如果可能文件、 图形或其他内容源项目的正文包括在此属性。否则，从源项的内容包含在**附件**属性。此属性的内容将取决于合作伙伴连接器和源平台的功能。</span><span class="sxs-lookup"><span data-stu-id="b405a-p121">The contents of the message or post. For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property. During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible. If possible files, graphics, or other content from the body of the source item is included in this property. Otherwise, content from the source item is included in the **ATTACHMENT** property. The contents of this property will depend on the partner connector and on the capability of the source platform.  </span></span><br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="b405a-421">**附件**</span><span class="sxs-lookup"><span data-stu-id="b405a-421">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="b405a-422">否</span><span class="sxs-lookup"><span data-stu-id="b405a-422">No</span></span>  <br/> |<span data-ttu-id="b405a-p122">如果数据源 （如 Twitter 或即时消息对话中 tweet) 中的项都有一个附加的文件，或包含图像，合作伙伴连接将第一次尝试在**BODY**属性中包含附件。如果这不是可能的则会添加到 * * 附件 * * 属性。附件的其他示例包括顶帖 Facebook，从内容源和答复邮件或文章的元数据中。</span><span class="sxs-lookup"><span data-stu-id="b405a-p122">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property. If that isn't possible, then it's added to the ** ATTACHMENT ** property. Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.  </span></span><br/> | `image.gif` <br/> |
    |<span data-ttu-id="b405a-426">**邮件类**</span><span class="sxs-lookup"><span data-stu-id="b405a-426">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="b405a-427">是</span><span class="sxs-lookup"><span data-stu-id="b405a-427">Yes</span></span>  <br/> | <span data-ttu-id="b405a-p123">这是一个多值属性，其中创建和填充合作伙伴连接器。此属性的格式为`IPM.NOTE.Source.Event`。(此属性必须以`IPM.NOTE`; 此格式是相似的`IPM.NOTE.X`邮件类。)此属性包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="b405a-p123">This is a multi-value property, which is created and populated by partner connector. The format of this property is  `IPM.NOTE.Source.Event`. (This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:  </span></span><br/><br/><span data-ttu-id="b405a-431">`Source`-指示第三方数据源;例如，Twitter、 Facebook 或 BlackBerry。</span><span class="sxs-lookup"><span data-stu-id="b405a-431">`Source` - Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="b405a-p124">`Event`-指示执行生成项，则在第三方数据源中的活动的类型例如，tweet Twitter 或的帖子中 Facebook 中。事件是特定于数据源。</span><span class="sxs-lookup"><span data-stu-id="b405a-p124">`Event` - Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook. Events are specific to the data source.  </span></span><br/> <br/>  <span data-ttu-id="b405a-p125">此属性的一个用途是基于其中项目产生或基于事件的类型的数据源的特定项进行筛选。例如，在电子数据展示搜索中无法创建搜索查询来查找特定的用户发布的所有 tweets。</span><span class="sxs-lookup"><span data-stu-id="b405a-p125">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event. For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.  </span></span><br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="b405a-p126">当项目被成功导入到 Office 365 中的邮箱中时，作为一部分的 HTTP 响应呼叫者回返回的唯一标识符。此标识符 — 调用`x-IngestionCorrelationID`— 可用于项目的端到端跟踪的伙伴后续疑难解答目的。建议合作伙伴捕获此信息，并相应地登录其末尾。下面是显示此标识符的 HTTP 响应示例：</span><span class="sxs-lookup"><span data-stu-id="b405a-p126">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response. This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items. It's recommended that partners capture this information and log it accordingly at their end. Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="b405a-p127">您可以在 Office 365 安全性使用内容搜索工具&amp;合规性中心搜索已导入到 Office 365 中的邮箱从第三方数据源的项目。若要搜索专门针对这些导入的项，可以在内容搜索关键字框中使用以下邮件属性值对。.</span><span class="sxs-lookup"><span data-stu-id="b405a-p127">You can use the Content Search tool in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search. .</span></span> 
    
  - <span data-ttu-id="b405a-p128">**`kind:externaldata`**-使用此属性值对搜索所有第三方数据类型。例如，若要搜索已从第三方数据源导入和导入项目的 Subject 属性中包含的单词"contoso"的项目，需要使用关键字查询`kind:externaldata AND subject:contoso`。</span><span class="sxs-lookup"><span data-stu-id="b405a-p128">**`kind:externaldata`** - Use this property-value pair to search all third-party data types. For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="b405a-p129">**`itemclass:ipm.externaldata.<third-party data type>`**-使用此属性值对仅查找指定的第三方数据类型。例如，若要仅搜索包含单词"contoso"的使用者属性中的 Facebook 数据，需要使用关键字查询`itemclass:ipm.externaldata.Facebook* AND subject:contoso`。</span><span class="sxs-lookup"><span data-stu-id="b405a-p129">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data. For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="b405a-447">有关要使用第三方数据类型的值的完整列表`itemclass`属性，请参阅[使用内容搜索第三方数据的已导入到 Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="b405a-447">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="b405a-448">有关如何使用内容搜索以及创建关键字搜索查询的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b405a-448">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="b405a-449">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="b405a-449">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="b405a-450">内容搜索的关键字查询和搜索条件</span><span class="sxs-lookup"><span data-stu-id="b405a-450">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 

---
title: 与合作伙伴合作, 以在 Office 365 中存档第三方数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 您的组织可以与 Microsoft 合作伙伴合作, 设置自定义连接器, 以便从数据源 (如 Salesforce Chatter、Yahoo Messenger 或 Yammer) 导入第三方数据。 这使您可以在 office 365 中存档第三方数据源中的数据, 以便您可以使用 office 365 合规性功能 (如合法保留、内容搜索和保留策略) 来管理组织的第三方数据的管理。
ms.openlocfilehash: dce015438c9764f66e98936df9454cba73fd8472
ms.sourcegitcommit: 63a10dc5ffa9d709fac437d3fc9e554b1bcd826f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "33307764"
---
# <a name="work-with-a-partner-to-archive-third-party-data-in-office-365"></a><span data-ttu-id="227c0-104">与合作伙伴合作, 以在 Office 365 中存档第三方数据</span><span class="sxs-lookup"><span data-stu-id="227c0-104">Work with a partner to archive third-party data in Office 365</span></span>

<span data-ttu-id="227c0-105">您可以与 Microsoft 合作伙伴合作, 将第三方数据源中的数据导入和存档到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="227c0-105">You can work with a Microsoft Partner to import and archive data from a third-party data source to Office 365.</span></span> <span data-ttu-id="227c0-106">合作伙伴可以为您提供一个自定义连接器, 该连接器被配置为从第三方数据源提取项目 (定期), 然后将这些项目导入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="227c0-106">A partner can provide you with an custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items to Office 365.</span></span> <span data-ttu-id="227c0-107">合作伙伴连接器将项目的内容从数据源转换为电子邮件格式, 然后将这些项目存储在 Office 365 中的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="227c0-107">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes in Office 365.</span></span> <span data-ttu-id="227c0-108">导入第三方数据后, 可以将 Office 365 合规性功能 (如诉讼保留、内容搜索、就地存档、审核和 Office 365 保留策略) 应用于此类数据。</span><span class="sxs-lookup"><span data-stu-id="227c0-108">After third-party data is imported, you can apply Office 365 compliance features—such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies—to this data.</span></span>
  
<span data-ttu-id="227c0-109">下面概述了使用 Microsoft 合作伙伴将第三方数据导入 Office 365 时所需的过程和步骤。</span><span class="sxs-lookup"><span data-stu-id="227c0-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data to Office 365.</span></span>

[<span data-ttu-id="227c0-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="227c0-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="227c0-111">Step 2: Create and configure a third-party data mailbox in Office 365</span><span class="sxs-lookup"><span data-stu-id="227c0-111">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="227c0-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="227c0-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="227c0-113">步骤 4：为合作伙伴提供信息</span><span class="sxs-lookup"><span data-stu-id="227c0-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="227c0-114">步骤 5: 在 Azure Active Directory 中注册第三方数据连接器</span><span class="sxs-lookup"><span data-stu-id="227c0-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="227c0-115">第三方数据导入过程的工作原理</span><span class="sxs-lookup"><span data-stu-id="227c0-115">How the third-party data import process works</span></span>

<span data-ttu-id="227c0-116">下图和说明介绍了在使用合作伙伴时第三方数据导入过程的工作原理。</span><span class="sxs-lookup"><span data-stu-id="227c0-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![第三方数据导入过程的工作原理](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="227c0-118">客户可以通过其选择的合作伙伴来配置将从第三方数据源提取项目的连接器, 然后将这些项目导入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="227c0-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="227c0-119">合作伙伴连接器通过第三方 API (根据计划或已配置的原则) 连接到第三方数据源, 并从数据源中提取项目。</span><span class="sxs-lookup"><span data-stu-id="227c0-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="227c0-120">合作伙伴连接器将项目内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="227c0-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="227c0-121">请参阅[More information](#more-information)部分，了解有关邮件格式架构的说明。</span><span class="sxs-lookup"><span data-stu-id="227c0-121">See the [More information](#more-information) section for a description of the message format schema.</span></span> 
    
3. <span data-ttu-id="227c0-122">合作伙伴连接器通过已知终结点使用 Exchange Web 服务 (EWS) 连接到 Office 365 中的 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="227c0-122">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="227c0-p104">项目便导入到特定用户的邮箱或“catch-all”第三方数据邮箱。无论项目是导入到特定用户邮箱还是第三方数据邮箱，都要基于以下条件：</span><span class="sxs-lookup"><span data-stu-id="227c0-p104">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="227c0-125">a.</span><span class="sxs-lookup"><span data-stu-id="227c0-125">a.</span></span> <span data-ttu-id="227c0-126">**具有与 office 365 用户帐户对应的用户 id 的项目**-如果合作伙伴连接器可以将第三方数据源中项目的用户 id 映射到 office 365 中的特定用户 id, 则会将该项目复制到用户的 Rec 中的 "**清除**" 文件夹中。overable "项目" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="227c0-126">**Items that have a user ID that corresponds to an Office 365 user account** - If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="227c0-127">用户无法访问“清除”文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="227c0-127">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="227c0-128">不过, 您可以使用 Office 365 电子数据展示工具搜索 "清除" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="227c0-128">However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="227c0-129">b.</span><span class="sxs-lookup"><span data-stu-id="227c0-129">b.</span></span> <span data-ttu-id="227c0-130">**没有与 office 365 用户帐户对应的用户 id 的项目**-如果合作伙伴连接器无法将项目的用户 id 映射到 office 365 中的特定用户 id, 则会将该项目复制到第三方数据邮箱的 **"收件箱**" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="227c0-130">**Items that don't have a user ID that corresponds to an Office 365 user account** - If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="227c0-131">将项目导入到收件箱允许您或组织中的其他人登录到第三方邮箱来查看和管理这些项目，并查看是否需要在合作伙伴连接器配置中进行任何调整。</span><span class="sxs-lookup"><span data-stu-id="227c0-131">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="227c0-132">步骤 1：寻找第三方数据合作伙伴</span><span class="sxs-lookup"><span data-stu-id="227c0-132">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="227c0-133">在 office 365 中存档第三方数据的关键组件是查找和使用 Microsoft 合作伙伴, 该合作伙伴专门负责捕获第三方数据源中的数据, 并将其导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="227c0-133">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="227c0-134">导入数据后, 可以对其进行存档和保留, 以及组织的其他 Microsoft 数据 (例如来自 SharePoint 和 OneDrive for business 的 Exchange 和文档的电子邮件)。</span><span class="sxs-lookup"><span data-stu-id="227c0-134">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="227c0-135">合作伙伴创建从组织的第三方数据源 (如 BlackBerry、Facebook、Google +、Thomson Reuters、Twitter 和 YouTube) 提取数据的连接器, 并将该数据传递给将项目导入 Exchange 邮箱的 Office 365 API电子邮件。</span><span class="sxs-lookup"><span data-stu-id="227c0-135">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="227c0-136">以下各节列出了 Microsoft 合作伙伴 (以及他们支持的第三方数据源), 他们参与了在 Office 365 中存档第三方数据的计划。</span><span class="sxs-lookup"><span data-stu-id="227c0-136">The following sections list the Microsoft partners—and the third-party data sources they support—that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="227c0-137">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="227c0-137">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="227c0-138">Actiance</span><span class="sxs-lookup"><span data-stu-id="227c0-138">Actiance</span></span>](#actiance)
  
[<span data-ttu-id="227c0-139">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="227c0-139">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="227c0-140">Globanet</span><span class="sxs-lookup"><span data-stu-id="227c0-140">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="227c0-141">OpenText</span><span class="sxs-lookup"><span data-stu-id="227c0-141">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="227c0-142">Verba</span><span class="sxs-lookup"><span data-stu-id="227c0-142">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="227c0-143">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="227c0-143">17a-4 LLC</span></span>

<span data-ttu-id="227c0-144">17a-4 LLC 支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="227c0-144">17a-4 LLC supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="227c0-145">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="227c0-145">BlackBerry</span></span>
    
- <span data-ttu-id="227c0-146">Bloomberg 数据流</span><span class="sxs-lookup"><span data-stu-id="227c0-146">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="227c0-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="227c0-147">Cisco Jabber</span></span>
    
- <span data-ttu-id="227c0-148">FactSet</span><span class="sxs-lookup"><span data-stu-id="227c0-148">FactSet</span></span>
    
- <span data-ttu-id="227c0-149">HipChat</span><span class="sxs-lookup"><span data-stu-id="227c0-149">HipChat</span></span>
    
- <span data-ttu-id="227c0-150">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="227c0-150">InvestEdge</span></span>
    
- <span data-ttu-id="227c0-151">LivePerson</span><span class="sxs-lookup"><span data-stu-id="227c0-151">LivePerson</span></span>
    
- <span data-ttu-id="227c0-152">MessageLabs 数据流</span><span class="sxs-lookup"><span data-stu-id="227c0-152">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="227c0-153">OpenText</span><span class="sxs-lookup"><span data-stu-id="227c0-153">OpenText</span></span>
    
- <span data-ttu-id="227c0-154">Oracle/ATG“单击以呼叫”Live 帮助</span><span class="sxs-lookup"><span data-stu-id="227c0-154">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="227c0-155">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="227c0-155">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="227c0-156">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="227c0-156">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="227c0-157">MindAlign</span><span class="sxs-lookup"><span data-stu-id="227c0-157">MindAlign</span></span>
    
- <span data-ttu-id="227c0-158">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="227c0-158">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="227c0-159">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="227c0-159">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="227c0-160">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="227c0-160">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="227c0-161">SQL 数据库</span><span class="sxs-lookup"><span data-stu-id="227c0-161">SQL Databases</span></span>
    
- <span data-ttu-id="227c0-162">Squawker</span><span class="sxs-lookup"><span data-stu-id="227c0-162">Squawker</span></span>
    
- <span data-ttu-id="227c0-163">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="227c0-163">Thomson Reuters Eikon Messenger</span></span>
  
### <a name="actiance"></a><span data-ttu-id="227c0-164">Actiance</span><span class="sxs-lookup"><span data-stu-id="227c0-164">Actiance</span></span>

<span data-ttu-id="227c0-165">[Actiance](https://www.actiance.com)支持以下第三方数据源:</span><span class="sxs-lookup"><span data-stu-id="227c0-165">[Actiance](https://www.actiance.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="227c0-166">对准</span><span class="sxs-lookup"><span data-stu-id="227c0-166">AIM</span></span>
    
- <span data-ttu-id="227c0-167">American Idol</span><span class="sxs-lookup"><span data-stu-id="227c0-167">American Idol</span></span>
    
- <span data-ttu-id="227c0-168">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="227c0-168">Apple Juice</span></span>
    
- <span data-ttu-id="227c0-169">使用 Pivot 客户端的 AOL</span><span class="sxs-lookup"><span data-stu-id="227c0-169">AOL with Pivot client</span></span>
    
- <span data-ttu-id="227c0-170">Ares</span><span class="sxs-lookup"><span data-stu-id="227c0-170">Ares</span></span>
    
- <span data-ttu-id="227c0-171">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="227c0-171">Bazaar Voice</span></span>
    
- <span data-ttu-id="227c0-172">Bear Share</span><span class="sxs-lookup"><span data-stu-id="227c0-172">Bear Share</span></span>
    
- <span data-ttu-id="227c0-173">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="227c0-173">Bit Torrent</span></span>
    
- <span data-ttu-id="227c0-174">BlackBerry 呼叫日志（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="227c0-174">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="227c0-175">BlackBerry Messenger（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="227c0-175">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="227c0-176">BlackBerry PIN（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="227c0-176">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="227c0-177">BlackBerry 短信（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="227c0-177">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="227c0-178">Bloomberg 邮件</span><span class="sxs-lookup"><span data-stu-id="227c0-178">Bloomberg Mail</span></span>
    
- <span data-ttu-id="227c0-179">CellTrust</span><span class="sxs-lookup"><span data-stu-id="227c0-179">CellTrust</span></span>
    
- <span data-ttu-id="227c0-180">Chat Import</span><span class="sxs-lookup"><span data-stu-id="227c0-180">Chat Import</span></span>
    
- <span data-ttu-id="227c0-181">聊天实时日志记录和策略</span><span class="sxs-lookup"><span data-stu-id="227c0-181">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="227c0-182">Chatter</span><span class="sxs-lookup"><span data-stu-id="227c0-182">Chatter</span></span>
    
- <span data-ttu-id="227c0-183">Cisco IM &amp;状态服务器 (v 9.0.1、9.1、v 9.1.1 SU1、v10、v v10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="227c0-183">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="227c0-184">Cisco Unified Presence 服务器（v8.6.3、v8.6.4、v8.6.5）</span><span class="sxs-lookup"><span data-stu-id="227c0-184">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="227c0-185">协作导入</span><span class="sxs-lookup"><span data-stu-id="227c0-185">Collaboration Import</span></span>
    
- <span data-ttu-id="227c0-186">协作实时日志记录</span><span class="sxs-lookup"><span data-stu-id="227c0-186">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="227c0-187">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="227c0-187">Direct Connect</span></span>
    
- <span data-ttu-id="227c0-188">Facebook</span><span class="sxs-lookup"><span data-stu-id="227c0-188">Facebook</span></span>
    
- <span data-ttu-id="227c0-189">FactSet</span><span class="sxs-lookup"><span data-stu-id="227c0-189">FactSet</span></span>
    
- <span data-ttu-id="227c0-190">FastTrack</span><span class="sxs-lookup"><span data-stu-id="227c0-190">FastTrack</span></span>
    
- <span data-ttu-id="227c0-191">Gnutella</span><span class="sxs-lookup"><span data-stu-id="227c0-191">Gnutella</span></span>
    
- <span data-ttu-id="227c0-192">Google +</span><span class="sxs-lookup"><span data-stu-id="227c0-192">Google+</span></span>
    
- <span data-ttu-id="227c0-193">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="227c0-193">GoToMyPC</span></span>
    
- <span data-ttu-id="227c0-194">Hopster</span><span class="sxs-lookup"><span data-stu-id="227c0-194">Hopster</span></span>
    
- <span data-ttu-id="227c0-195">HubConnex</span><span class="sxs-lookup"><span data-stu-id="227c0-195">HubConnex</span></span>
    
- <span data-ttu-id="227c0-196">IBM Connections（v3.0.1、v4.0、v4.5、v4.5 CR3、v5）</span><span class="sxs-lookup"><span data-stu-id="227c0-196">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="227c0-197">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="227c0-197">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="227c0-198">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="227c0-198">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="227c0-199">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="227c0-199">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="227c0-200">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="227c0-200">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="227c0-201">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)</span><span class="sxs-lookup"><span data-stu-id="227c0-201">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="227c0-202">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="227c0-202">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="227c0-203">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="227c0-203">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="227c0-204">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="227c0-204">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="227c0-205">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="227c0-205">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="227c0-206">即时消息导入</span><span class="sxs-lookup"><span data-stu-id="227c0-206">IM Import</span></span>
    
- <span data-ttu-id="227c0-207">即时消息实时日志记录和策略</span><span class="sxs-lookup"><span data-stu-id="227c0-207">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="227c0-208">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="227c0-208">Indii Messenger</span></span>
    
- <span data-ttu-id="227c0-209">即时 Bloomberg</span><span class="sxs-lookup"><span data-stu-id="227c0-209">Instant Bloomberg</span></span>
    
- <span data-ttu-id="227c0-210">IRC</span><span class="sxs-lookup"><span data-stu-id="227c0-210">IRC</span></span>
    
- <span data-ttu-id="227c0-211">Jive</span><span class="sxs-lookup"><span data-stu-id="227c0-211">Jive</span></span>
    
- <span data-ttu-id="227c0-212">Jive 6 实时日志记录（v6、v7）</span><span class="sxs-lookup"><span data-stu-id="227c0-212">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="227c0-213">Jive 导入</span><span class="sxs-lookup"><span data-stu-id="227c0-213">Jive Import</span></span>
    
- <span data-ttu-id="227c0-214">JXTA</span><span class="sxs-lookup"><span data-stu-id="227c0-214">JXTA</span></span>
    
- <span data-ttu-id="227c0-215">领英</span><span class="sxs-lookup"><span data-stu-id="227c0-215">LinkedIn</span></span>
    
- <span data-ttu-id="227c0-216">Microsoft Lync（2010、2013）</span><span class="sxs-lookup"><span data-stu-id="227c0-216">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="227c0-217">MFTP</span><span class="sxs-lookup"><span data-stu-id="227c0-217">MFTP</span></span>
    
- <span data-ttu-id="227c0-218">Microsoft Lync 2013 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-218">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="227c0-219">Microsoft SharePoint（2010、2013）</span><span class="sxs-lookup"><span data-stu-id="227c0-219">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="227c0-220">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="227c0-220">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="227c0-221">Microsoft UC（统一通信）</span><span class="sxs-lookup"><span data-stu-id="227c0-221">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="227c0-222">MindAlign</span><span class="sxs-lookup"><span data-stu-id="227c0-222">MindAlign</span></span>
    
- <span data-ttu-id="227c0-223">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="227c0-223">Mobile Guard</span></span>
    
- <span data-ttu-id="227c0-224">直接</span><span class="sxs-lookup"><span data-stu-id="227c0-224">MSN</span></span>
    
- <span data-ttu-id="227c0-225">My Space</span><span class="sxs-lookup"><span data-stu-id="227c0-225">My Space</span></span>
    
- <span data-ttu-id="227c0-226">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="227c0-226">NEONetwork</span></span>
    
- <span data-ttu-id="227c0-227">Office 365 Lync 专用</span><span class="sxs-lookup"><span data-stu-id="227c0-227">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="227c0-228">Office 365 共享即时消息</span><span class="sxs-lookup"><span data-stu-id="227c0-228">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="227c0-229">Pinterest</span><span class="sxs-lookup"><span data-stu-id="227c0-229">Pinterest</span></span>
    
- <span data-ttu-id="227c0-230">透视</span><span class="sxs-lookup"><span data-stu-id="227c0-230">Pivot</span></span>
    
- <span data-ttu-id="227c0-231">QQ</span><span class="sxs-lookup"><span data-stu-id="227c0-231">QQ</span></span>
    
- <span data-ttu-id="227c0-232">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="227c0-232">Skype for Business 2015</span></span>
    
- <span data-ttu-id="227c0-233">SoftEther</span><span class="sxs-lookup"><span data-stu-id="227c0-233">SoftEther</span></span>
    
- <span data-ttu-id="227c0-234">Symphony</span><span class="sxs-lookup"><span data-stu-id="227c0-234">Symphony</span></span>
    
- <span data-ttu-id="227c0-235">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="227c0-235">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="227c0-236">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="227c0-236">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="227c0-237">Tor</span><span class="sxs-lookup"><span data-stu-id="227c0-237">Tor</span></span>
    
- <span data-ttu-id="227c0-238">TTT</span><span class="sxs-lookup"><span data-stu-id="227c0-238">TTT</span></span>
    
- <span data-ttu-id="227c0-239">Twitter</span><span class="sxs-lookup"><span data-stu-id="227c0-239">Twitter</span></span>
    
- <span data-ttu-id="227c0-240">WinMX</span><span class="sxs-lookup"><span data-stu-id="227c0-240">WinMX</span></span>
    
- <span data-ttu-id="227c0-241">Winny</span><span class="sxs-lookup"><span data-stu-id="227c0-241">Winny</span></span>
    
- <span data-ttu-id="227c0-242">Yahoo</span><span class="sxs-lookup"><span data-stu-id="227c0-242">Yahoo</span></span>
    
- <span data-ttu-id="227c0-243">Yammer</span><span class="sxs-lookup"><span data-stu-id="227c0-243">Yammer</span></span>
    
- <span data-ttu-id="227c0-244">YouTube</span><span class="sxs-lookup"><span data-stu-id="227c0-244">YouTube</span></span>
    
  
### <a name="archivesocial"></a><span data-ttu-id="227c0-245">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="227c0-245">ArchiveSocial</span></span>

<span data-ttu-id="227c0-246">[ArchiveSocial](https://www.archivesocial.com)支持以下第三方数据源:</span><span class="sxs-lookup"><span data-stu-id="227c0-246">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="227c0-247">Facebook</span><span class="sxs-lookup"><span data-stu-id="227c0-247">Facebook</span></span>
    
- <span data-ttu-id="227c0-248">Flickr</span><span class="sxs-lookup"><span data-stu-id="227c0-248">Flickr</span></span>
    
- <span data-ttu-id="227c0-249">Instagram</span><span class="sxs-lookup"><span data-stu-id="227c0-249">Instagram</span></span>
    
- <span data-ttu-id="227c0-250">领英</span><span class="sxs-lookup"><span data-stu-id="227c0-250">LinkedIn</span></span>
    
- <span data-ttu-id="227c0-251">Pinterest</span><span class="sxs-lookup"><span data-stu-id="227c0-251">Pinterest</span></span>
    
- <span data-ttu-id="227c0-252">Twitter</span><span class="sxs-lookup"><span data-stu-id="227c0-252">Twitter</span></span>
    
- <span data-ttu-id="227c0-253">YouTube</span><span class="sxs-lookup"><span data-stu-id="227c0-253">YouTube</span></span>
    
- <span data-ttu-id="227c0-254">Vimeo</span><span class="sxs-lookup"><span data-stu-id="227c0-254">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="227c0-255">Globanet</span><span class="sxs-lookup"><span data-stu-id="227c0-255">Globanet</span></span>

<span data-ttu-id="227c0-256">[Globanet](https://www.globanet.com)支持以下第三方数据源:</span><span class="sxs-lookup"><span data-stu-id="227c0-256">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="227c0-257">使用 Pivot 客户端的 AOL</span><span class="sxs-lookup"><span data-stu-id="227c0-257">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="227c0-258">BlackBerry 呼叫日志（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="227c0-258">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="227c0-259">BlackBerry Messenger（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="227c0-259">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="227c0-260">BlackBerry PIN（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="227c0-260">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="227c0-261">BlackBerry 短信（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="227c0-261">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="227c0-262">Bloomberg 聊天</span><span class="sxs-lookup"><span data-stu-id="227c0-262">Bloomberg Chat</span></span>
    
- <span data-ttu-id="227c0-263">Bloomberg 邮件</span><span class="sxs-lookup"><span data-stu-id="227c0-263">Bloomberg Mail</span></span>
    
- <span data-ttu-id="227c0-264">Box</span><span class="sxs-lookup"><span data-stu-id="227c0-264">Box</span></span>
    
- <span data-ttu-id="227c0-265">适用于 Salesforce Chatter 的 CipherCloud</span><span class="sxs-lookup"><span data-stu-id="227c0-265">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="227c0-266">Cisco IM &amp;状态服务器 (v10, v v10.5.1 SU1, app-v 11.0, v 11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="227c0-266">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="227c0-267">Cisco Webex 团队</span><span class="sxs-lookup"><span data-stu-id="227c0-267">Cisco Webex Teams</span></span>

- <span data-ttu-id="227c0-268">Citrix 工作&amp;区 ShareFile</span><span class="sxs-lookup"><span data-stu-id="227c0-268">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="227c0-269">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="227c0-269">CrowdCompass</span></span>

- <span data-ttu-id="227c0-270">自定义带分隔符的文本文件</span><span class="sxs-lookup"><span data-stu-id="227c0-270">Custom delimited text files</span></span>
    
- <span data-ttu-id="227c0-271">自定义 XML 文件</span><span class="sxs-lookup"><span data-stu-id="227c0-271">Custom XML files</span></span>
    
- <span data-ttu-id="227c0-272">Facebook (页面)</span><span class="sxs-lookup"><span data-stu-id="227c0-272">Facebook (Pages)</span></span>
    
- <span data-ttu-id="227c0-273">Factset</span><span class="sxs-lookup"><span data-stu-id="227c0-273">Factset</span></span>
    
- <span data-ttu-id="227c0-274">FXConnect</span><span class="sxs-lookup"><span data-stu-id="227c0-274">FXConnect</span></span>
    
- <span data-ttu-id="227c0-275">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="227c0-275">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="227c0-276">Jive</span><span class="sxs-lookup"><span data-stu-id="227c0-276">Jive</span></span>
    
- <span data-ttu-id="227c0-277">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="227c0-277">Macgregor XIP</span></span>

- <span data-ttu-id="227c0-278">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="227c0-278">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="227c0-279">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="227c0-279">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="227c0-280">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="227c0-280">Microsoft Teams</span></span>
       
- <span data-ttu-id="227c0-281">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="227c0-281">Microsoft Yammer</span></span>
    
- <span data-ttu-id="227c0-282">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="227c0-282">Mobile Guard</span></span>
    
- <span data-ttu-id="227c0-283">透视</span><span class="sxs-lookup"><span data-stu-id="227c0-283">Pivot</span></span>
    
- <span data-ttu-id="227c0-284">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="227c0-284">Salesforce Chatter</span></span>

- <span data-ttu-id="227c0-285">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="227c0-285">Skype for Business Online</span></span>
    
- <span data-ttu-id="227c0-286">Skype for Business，版本 2007 R2 - 2016（本地）</span><span class="sxs-lookup"><span data-stu-id="227c0-286">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="227c0-287">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="227c0-287">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="227c0-288">Symphony</span><span class="sxs-lookup"><span data-stu-id="227c0-288">Symphony</span></span>
    
- <span data-ttu-id="227c0-289">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="227c0-289">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="227c0-290">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="227c0-290">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="227c0-291">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="227c0-291">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="227c0-292">Twitter</span><span class="sxs-lookup"><span data-stu-id="227c0-292">Twitter</span></span>
    
- <span data-ttu-id="227c0-293">UBS 聊天</span><span class="sxs-lookup"><span data-stu-id="227c0-293">UBS Chat</span></span>
    
- <span data-ttu-id="227c0-294">YouTube</span><span class="sxs-lookup"><span data-stu-id="227c0-294">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="227c0-295">OpenText</span><span class="sxs-lookup"><span data-stu-id="227c0-295">OpenText</span></span>

<span data-ttu-id="227c0-296">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)支持以下第三方数据源:</span><span class="sxs-lookup"><span data-stu-id="227c0-296">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="227c0-297">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="227c0-297">Axs Encrypted</span></span>
    
- <span data-ttu-id="227c0-298">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="227c0-298">Axs Exchange</span></span>
    
- <span data-ttu-id="227c0-299">Axs 本地存档</span><span class="sxs-lookup"><span data-stu-id="227c0-299">Axs Local Archive</span></span>
    
- <span data-ttu-id="227c0-300">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="227c0-300">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="227c0-301">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="227c0-301">Axs Signed</span></span>
    
- <span data-ttu-id="227c0-302">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="227c0-302">Bloomberg</span></span>
    
- <span data-ttu-id="227c0-303">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="227c0-303">Thomson Reuters</span></span>
  
### <a name="verba"></a><span data-ttu-id="227c0-304">Verba</span><span class="sxs-lookup"><span data-stu-id="227c0-304">Verba</span></span>

<span data-ttu-id="227c0-305">[Verba](https://www.verba.com)支持以下第三方数据源:</span><span class="sxs-lookup"><span data-stu-id="227c0-305">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="227c0-306">Avaya Aura 视频</span><span class="sxs-lookup"><span data-stu-id="227c0-306">Avaya Aura Video</span></span>
    
- <span data-ttu-id="227c0-307">Avaya Aura 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-307">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="227c0-308">Avtec 调频广播</span><span class="sxs-lookup"><span data-stu-id="227c0-308">Avtec Radio</span></span>
    
- <span data-ttu-id="227c0-309">Bosch/Telex 调频广播</span><span class="sxs-lookup"><span data-stu-id="227c0-309">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="227c0-310">BroadSoft 视频</span><span class="sxs-lookup"><span data-stu-id="227c0-310">BroadSoft Video</span></span>
    
- <span data-ttu-id="227c0-311">BroadSoft 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-311">BroadSoft Voice</span></span>
    
- <span data-ttu-id="227c0-312">Centile 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-312">Centile Voice</span></span>
    
- <span data-ttu-id="227c0-313">Cisco Jabber 即时消息</span><span class="sxs-lookup"><span data-stu-id="227c0-313">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="227c0-314">Cisco UC 视频</span><span class="sxs-lookup"><span data-stu-id="227c0-314">Cisco UC Video</span></span>
    
- <span data-ttu-id="227c0-315">Cisco UC 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-315">Cisco UC Voice</span></span>
    
- <span data-ttu-id="227c0-316">Cisco UCCX/UCCE 视频</span><span class="sxs-lookup"><span data-stu-id="227c0-316">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="227c0-317">Cisco UCCX/UCCE 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-317">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="227c0-318">ESChat 调频广播</span><span class="sxs-lookup"><span data-stu-id="227c0-318">ESChat Radio</span></span>
    
- <span data-ttu-id="227c0-319">Geoman 联络专家</span><span class="sxs-lookup"><span data-stu-id="227c0-319">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="227c0-320">IP Trade 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-320">IP Trade Voice</span></span>
    
- <span data-ttu-id="227c0-321">Luware LUCS 联络中心</span><span class="sxs-lookup"><span data-stu-id="227c0-321">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="227c0-322">Microsoft UC（统一通信）</span><span class="sxs-lookup"><span data-stu-id="227c0-322">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="227c0-323">适用于 Lync 的 Mitel MiContact 中心 (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="227c0-323">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="227c0-324">Oracle / Acme 数据包会话边界控制器视频</span><span class="sxs-lookup"><span data-stu-id="227c0-324">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="227c0-325">Oracle / Acme 数据包会话边界控制器语音</span><span class="sxs-lookup"><span data-stu-id="227c0-325">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="227c0-326">Singtel Mobile 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-326">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="227c0-327">SIPREC 视频</span><span class="sxs-lookup"><span data-stu-id="227c0-327">SIPREC Video</span></span>
    
-  <span data-ttu-id="227c0-328">SIPREC 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-328">SIPREC Voice</span></span> 
    
- <span data-ttu-id="227c0-329">Skype for Business/Lync 即时消息</span><span class="sxs-lookup"><span data-stu-id="227c0-329">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="227c0-330">Skype for Business/Lync 视频</span><span class="sxs-lookup"><span data-stu-id="227c0-330">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="227c0-331">Skype for Business/Lync 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-331">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="227c0-332">Speakerbus 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-332">Speakerbus Voice</span></span>
    
- <span data-ttu-id="227c0-333">标准 SIP/H.323 视频</span><span class="sxs-lookup"><span data-stu-id="227c0-333">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="227c0-334">标准 SIP/H.323 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-334">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="227c0-335">Truphone 语音</span><span class="sxs-lookup"><span data-stu-id="227c0-335">Truphone Voice</span></span>
    
- <span data-ttu-id="227c0-336">TwistedPair 调频广播</span><span class="sxs-lookup"><span data-stu-id="227c0-336">TwistedPair Radio</span></span>
    
- <span data-ttu-id="227c0-337">Windows 桌面计算机屏幕</span><span class="sxs-lookup"><span data-stu-id="227c0-337">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="227c0-338">步骤 2：在 Office 365 中创建和配置第三方数据邮箱</span><span class="sxs-lookup"><span data-stu-id="227c0-338">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="227c0-339">以下是创建和配置将数据导入到 Office 365 的第三方数据邮箱的步骤。</span><span class="sxs-lookup"><span data-stu-id="227c0-339">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="227c0-340">如前所述, 如果合作伙伴连接器无法将项目的用户 ID 映射到 Office 365 用户帐户, 则会将项目导入此邮箱。</span><span class="sxs-lookup"><span data-stu-id="227c0-340">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="227c0-341">**在 Microsoft 365 管理中心完成这些任务**</span><span class="sxs-lookup"><span data-stu-id="227c0-341">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="227c0-342">在 Office 365 中创建一个新的用户帐户, 并为其分配 Exchange Online 计划2许可证;请参阅[向 Office 365 添加用户](https://go.microsoft.com/fwlink/p/?LinkId=692098)。</span><span class="sxs-lookup"><span data-stu-id="227c0-342">Create a new user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="227c0-343">需要 Plan 2 许可证将邮箱置于诉讼保留状态, 或启用具有无限存储配额的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="227c0-343">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="227c0-344">将第三方数据邮箱的用户帐户添加到 Office 365 中的**Exchange 管理员**管理员角色中;请参阅[在 Office 365 中分配管理员角色](https://go.microsoft.com/fwlink/p/?LinkId=532393)。</span><span class="sxs-lookup"><span data-stu-id="227c0-344">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="227c0-345">写下此用户帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="227c0-345">Write down the credentials for this user account.</span></span> <span data-ttu-id="227c0-346">您需要将它们提供给您的合作伙伴，如步骤 4 中所述。</span><span class="sxs-lookup"><span data-stu-id="227c0-346">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="227c0-347">**在 Exchange 管理中心中完成这些任务**</span><span class="sxs-lookup"><span data-stu-id="227c0-347">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="227c0-348">从通讯簿和组织中的其他地址列表中隐藏第三方数据邮箱;请参阅[管理用户邮箱](https://go.microsoft.com/fwlink/p/?LinkId=616058)。</span><span class="sxs-lookup"><span data-stu-id="227c0-348">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="227c0-349">或者，可以运行以下 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="227c0-349">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="227c0-350">为第三方数据邮箱分配**FullAccess**权限, 以便管理员或合规专员可以在 Outlook 桌面客户端中打开第三方数据邮箱;请参阅[管理收件人的权限](https://go.microsoft.com/fwlink/p/?LinkId=692104)。</span><span class="sxs-lookup"><span data-stu-id="227c0-350">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="227c0-351">为第三方数据邮箱启用以下与合规性相关的 Office 365 功能:</span><span class="sxs-lookup"><span data-stu-id="227c0-351">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="227c0-352">启用存档邮箱;请参阅[启用存档邮箱](enable-archive-mailboxes.md)和[启用无限制存档](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="227c0-352">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="227c0-353">这将允许您通过设置将第三方数据项移动到存档邮箱的存档策略来释放主邮箱中的存储空间。</span><span class="sxs-lookup"><span data-stu-id="227c0-353">This will let you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="227c0-354">这将为第三方数据提供无限存储空间。</span><span class="sxs-lookup"><span data-stu-id="227c0-354">This will provide you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="227c0-355">将第三方数据邮箱置于诉讼保留的位置。</span><span class="sxs-lookup"><span data-stu-id="227c0-355">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="227c0-356">您还可以在安全与合规中心中应用 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="227c0-356">You can also apply an Office 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="227c0-357">将此邮箱置于保留状态时, 将保留第三方数据项 (无限期或指定的持续时间), 并防止从邮箱中清除这些项目。</span><span class="sxs-lookup"><span data-stu-id="227c0-357">Placing this mailbox on hold will retain third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="227c0-358">请参阅下列主题之一:</span><span class="sxs-lookup"><span data-stu-id="227c0-358">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="227c0-359">将邮箱置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="227c0-359">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="227c0-360">Office 365 中的保留策略概述</span><span class="sxs-lookup"><span data-stu-id="227c0-360">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="227c0-361">对访问第三方数据邮箱的所有者、委派用户和管理员启用邮箱审核日志记录；请参阅[Enable mailbox auditing in Office 365](enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="227c0-361">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="227c0-362">这将允许您审核有权访问第三方数据邮箱的任何用户执行的所有活动。</span><span class="sxs-lookup"><span data-stu-id="227c0-362">This will allow you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="227c0-363">步骤 3：为第三方数据配置用户邮箱</span><span class="sxs-lookup"><span data-stu-id="227c0-363">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="227c0-364">下一步是配置用户邮箱以支持第三方数据。</span><span class="sxs-lookup"><span data-stu-id="227c0-364">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="227c0-365">通过使用 Exchange 管理中心或使用相应的 Windows PowerShell cmdlet 完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="227c0-365">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="227c0-366">为每个用户启用存档邮箱;请参阅[启用存档邮箱](enable-archive-mailboxes.md)和[启用无限制存档](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="227c0-366">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="227c0-367">将用户邮箱置于诉讼保留或应用 Office 365 保留策略;请参阅下列主题之一:</span><span class="sxs-lookup"><span data-stu-id="227c0-367">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="227c0-368">将邮箱置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="227c0-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="227c0-369">Office 365 中的保留策略概述</span><span class="sxs-lookup"><span data-stu-id="227c0-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="227c0-370">如前所述，在将邮箱置于保留时，您可以设置保留第三方数据源中项目的时长，或者也可以选择无限期保留这些项目。</span><span class="sxs-lookup"><span data-stu-id="227c0-370">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="227c0-371">步骤 4：为合作伙伴提供信息</span><span class="sxs-lookup"><span data-stu-id="227c0-371">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="227c0-372">最后一步是为您的合作伙伴提供以下信息，这样他们便能够配置连接器以连接到 Office 365 组织，从而将数据导入到用户邮箱和第三方数据邮箱。</span><span class="sxs-lookup"><span data-stu-id="227c0-372">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="227c0-373">用于连接到 Office 365 中的 Azure 服务的终结点:</span><span class="sxs-lookup"><span data-stu-id="227c0-373">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="227c0-374">您在步骤2中创建的第三方数据邮箱的登录凭据 (Office 365 用户 ID 和密码)。</span><span class="sxs-lookup"><span data-stu-id="227c0-374">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="227c0-375">这些凭据是必需的，以便合作伙伴连接器可以访问并将项目导入用户邮箱和第三方数据邮箱。</span><span class="sxs-lookup"><span data-stu-id="227c0-375">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="227c0-376">步骤 5: 在 Azure Active Directory 中注册第三方数据连接器</span><span class="sxs-lookup"><span data-stu-id="227c0-376">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="227c0-377">从2018年9月30日起, Office 365 中的 Azure 服务将开始使用 Exchange Online 中的新式验证来验证尝试连接到 Office 365 组织的第三方数据连接器以导入数据。</span><span class="sxs-lookup"><span data-stu-id="227c0-377">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data.</span></span> <span data-ttu-id="227c0-378">此更改的原因是新式验证提供的安全性高于当前方法, 后者基于使用前面所述的终结点连接到 Azure 服务的白名单第三方连接器。</span><span class="sxs-lookup"><span data-stu-id="227c0-378">The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="227c0-379">若要使第三方数据连接器能够使用新式新式身份验证方法连接到 Office 365, Office 365 组织中的管理员必须同意在 Azure Active Directory 中将连接器注册为受信任的服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="227c0-379">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="227c0-380">这是通过接受允许连接器在 Azure Active Directory 中访问组织数据的权限请求来实现的。</span><span class="sxs-lookup"><span data-stu-id="227c0-380">This is done by accepting a permissions request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="227c0-381">接受此请求后, 第三方数据连接器将作为企业应用程序添加到 Azure Active Directory, 并表示为服务主体。</span><span class="sxs-lookup"><span data-stu-id="227c0-381">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="227c0-382">有关许可过程的详细信息, 请参阅[租户管理员同意](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)。</span><span class="sxs-lookup"><span data-stu-id="227c0-382">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="227c0-383">以下是访问和接受注册连接器的请求的步骤:</span><span class="sxs-lookup"><span data-stu-id="227c0-383">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="227c0-384">转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), 并使用 Office 365 全局管理员的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="227c0-384">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="227c0-385">将显示以下对话框。</span><span class="sxs-lookup"><span data-stu-id="227c0-385">The following dialog box is displayed.</span></span> <span data-ttu-id="227c0-386">您可以展开 carets 以查看将分配给连接器的权限。</span><span class="sxs-lookup"><span data-stu-id="227c0-386">You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/><span data-ttu-id="227c0-387">![将显示 "权限请求" 对话框](media/O365_ThirdPartyDataConnector_OptIn1.png)</span><span class="sxs-lookup"><span data-stu-id="227c0-387">![The permissions request dialog is displayed](media/O365_ThirdPartyDataConnector_OptIn1.png)</span></span>
2. <span data-ttu-id="227c0-388">单击“Accept”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="227c0-388">Click **Accept**.</span></span>

<span data-ttu-id="227c0-389">接受请求后, 将显示[Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="227c0-389">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="227c0-390">若要查看您的组织的应用程序列表, 请单击 " **Azure Active Directory** > **企业应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="227c0-390">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="227c0-391">**企业应用程序**边栏上列出了 Office 365 第三方数据连接器。</span><span class="sxs-lookup"><span data-stu-id="227c0-391">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="227c0-392">在2018年9月30日之后, 如果未在 Azure Active Directory 中注册第三方数据连接器, 则将不再将第三方数据导入组织中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="227c0-392">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="227c0-393">注释现有的第三方数据连接器 (在9月30日之前创建的数据连接器) 还必须在 Azure Active Directory 中进行注册, 具体步骤是执行步骤5中的过程。</span><span class="sxs-lookup"><span data-stu-id="227c0-393">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="227c0-394">撤销第三方数据连接器的同意</span><span class="sxs-lookup"><span data-stu-id="227c0-394">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="227c0-395">在您的组织同意要在 Azure Active Directory 中注册第三方数据连接器的权限请求后, 您的组织可以随时撤销该许可。</span><span class="sxs-lookup"><span data-stu-id="227c0-395">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="227c0-396">但是, 如果吊销连接器的许可, 则将不再将第三方数据源中的数据导入到 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="227c0-396">However, revoking the consent for a connector will mean that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="227c0-397">若要撤销第三方数据连接器的同意, 可以使用 azure 门户中的 "**企业应用程序**" 边栏从 azure Active Directory 中删除应用程序 (通过删除相应的服务主体), 或使用[new-msolserviceprincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal)在 Office 365 PowerShell 中删除。</span><span class="sxs-lookup"><span data-stu-id="227c0-397">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="227c0-398">您还可以在 Azure Active Directory PowerShell 中使用[AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="227c0-398">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="227c0-399">更多信息</span><span class="sxs-lookup"><span data-stu-id="227c0-399">More information</span></span>

- <span data-ttu-id="227c0-400">如前所述，第三方数据源中的项目将作为电子邮件导入到 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="227c0-400">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="227c0-401">合作伙伴连接器使用 Office 365 API 所需的架构导入项目。</span><span class="sxs-lookup"><span data-stu-id="227c0-401">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="227c0-402">下表介绍了第三方数据源中的项目作为电子邮件导入到 Exchange 邮箱之后的邮件属性。</span><span class="sxs-lookup"><span data-stu-id="227c0-402">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="227c0-403">该表还指出该邮件属性是否是强制属性。</span><span class="sxs-lookup"><span data-stu-id="227c0-403">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="227c0-404">必须填充强制属性。</span><span class="sxs-lookup"><span data-stu-id="227c0-404">Mandatory properties must be populated.</span></span> <span data-ttu-id="227c0-405">如果某项缺少强制属性, 则不会将其导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="227c0-405">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="227c0-406">导入过程将返回一条错误消息，解释未导入项目的原因以及缺少了哪些属性。</span><span class="sxs-lookup"><span data-stu-id="227c0-406">The import process will return an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="227c0-407">**邮件属性**</span><span class="sxs-lookup"><span data-stu-id="227c0-407">**Message property**</span></span>|<span data-ttu-id="227c0-408">**强制？**</span><span class="sxs-lookup"><span data-stu-id="227c0-408">**Mandatory?**</span></span>|<span data-ttu-id="227c0-409">**说明**</span><span class="sxs-lookup"><span data-stu-id="227c0-409">**Description**</span></span>|<span data-ttu-id="227c0-410">**示例值**</span><span class="sxs-lookup"><span data-stu-id="227c0-410">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="227c0-411">**FROM**</span><span class="sxs-lookup"><span data-stu-id="227c0-411">**FROM**</span></span> <br/> |<span data-ttu-id="227c0-412">是</span><span class="sxs-lookup"><span data-stu-id="227c0-412">Yes</span></span>  <br/> |<span data-ttu-id="227c0-413">最初创建或发送第三方数据源中的项目的用户。</span><span class="sxs-lookup"><span data-stu-id="227c0-413">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="227c0-414">合作伙伴连接器将尝试将源项目 (例如 Twitter 句柄) 中的用户 ID 映射到所有参与者 ("from" 和 "to" 字段中的用户) 的 Office 365 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="227c0-414">The partner connector will attempt to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="227c0-415">邮件的副本将导入到每个参与者的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="227c0-415">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="227c0-416">如果无法将项目中的任何参与者映射到 office 365 用户帐户, 则会将该项目导入 office 365 中的第三方存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="227c0-416">If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="227c0-417">标识为项目的发件人的参与者必须在要向其导入项目的 Office 365 组织中具有活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="227c0-417">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to.</span></span> <span data-ttu-id="227c0-418">如果发件人没有活动邮箱，则会返回以下错误：</span><span class="sxs-lookup"><span data-stu-id="227c0-418">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="227c0-419">**TO**</span><span class="sxs-lookup"><span data-stu-id="227c0-419">**TO**</span></span> <br/> |<span data-ttu-id="227c0-420">是</span><span class="sxs-lookup"><span data-stu-id="227c0-420">Yes</span></span>  <br/> |<span data-ttu-id="227c0-421">接收项目的用户（如果适用于数据源中的项目）。</span><span class="sxs-lookup"><span data-stu-id="227c0-421">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="227c0-422">**主题**</span><span class="sxs-lookup"><span data-stu-id="227c0-422">**SUBJECT**</span></span> <br/> |<span data-ttu-id="227c0-423">否</span><span class="sxs-lookup"><span data-stu-id="227c0-423">No</span></span>  <br/> |<span data-ttu-id="227c0-424">源项目中的主题。</span><span class="sxs-lookup"><span data-stu-id="227c0-424">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="227c0-425">**结束**</span><span class="sxs-lookup"><span data-stu-id="227c0-425">**DATE**</span></span> <br/> |<span data-ttu-id="227c0-426">是</span><span class="sxs-lookup"><span data-stu-id="227c0-426">Yes</span></span>  <br/> |<span data-ttu-id="227c0-427">最初在客户数据源中创建或发布项目的日期；例如，发布 Twitter 消息的日期。</span><span class="sxs-lookup"><span data-stu-id="227c0-427">The date the item was originally created or posted in the customer data source; for example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="227c0-428">**大量**</span><span class="sxs-lookup"><span data-stu-id="227c0-428">**BODY**</span></span> <br/> |<span data-ttu-id="227c0-429">否</span><span class="sxs-lookup"><span data-stu-id="227c0-429">No</span></span>  <br/> |<span data-ttu-id="227c0-430">消息或帖子的内容。</span><span class="sxs-lookup"><span data-stu-id="227c0-430">The contents of the message or post.</span></span> <span data-ttu-id="227c0-431">对于某些数据源，此属性的内容可能与\*\*\*\*“主题”属性的内容相同。</span><span class="sxs-lookup"><span data-stu-id="227c0-431">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="227c0-432">在导入过程中，合作伙伴连接器将尝试尽可能维护内容源的完全保真度。</span><span class="sxs-lookup"><span data-stu-id="227c0-432">During the import process, the partner connector will attempt to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="227c0-433">如果可能，源项目正文中的文件、图形或其他内容会包含在此属性中。</span><span class="sxs-lookup"><span data-stu-id="227c0-433">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="227c0-434">否则，源项目中的内容会包含在\*\*\*\*“附件”属性中。</span><span class="sxs-lookup"><span data-stu-id="227c0-434">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="227c0-435">此属性的内容将取决于合作伙伴连接器和源平台的功能。</span><span class="sxs-lookup"><span data-stu-id="227c0-435">The contents of this property will depend on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="227c0-436">**附着**</span><span class="sxs-lookup"><span data-stu-id="227c0-436">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="227c0-437">否</span><span class="sxs-lookup"><span data-stu-id="227c0-437">No</span></span>  <br/> |<span data-ttu-id="227c0-438">如果数据源中的项 (如 Twitter 或即时消息对话中的 twitter) 具有附加的文件或包含图像, 则合作伙伴连接将首先尝试在**BODY**属性中包含附件。</span><span class="sxs-lookup"><span data-stu-id="227c0-438">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="227c0-439">如果无法这样做, 则会将其添加到 \* \* 附件 \* \* 属性中。</span><span class="sxs-lookup"><span data-stu-id="227c0-439">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="227c0-440">其他附件示例包括 Facebook 中的点赞，内容源中的元数据，以及对消息或帖子的回复。</span><span class="sxs-lookup"><span data-stu-id="227c0-440">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="227c0-441">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="227c0-441">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="227c0-442">是</span><span class="sxs-lookup"><span data-stu-id="227c0-442">Yes</span></span>  <br/> | <span data-ttu-id="227c0-443">这是一个多值属性，由合作伙伴连接器创建和填充。</span><span class="sxs-lookup"><span data-stu-id="227c0-443">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="227c0-444">此属性的格式为`IPM.NOTE.Source.Event`。</span><span class="sxs-lookup"><span data-stu-id="227c0-444">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="227c0-445">(此属性必须以开头`IPM.NOTE`; 这种格式类似于`IPM.NOTE.X`消息类的格式。)此属性包含以下信息:</span><span class="sxs-lookup"><span data-stu-id="227c0-445">(This property must begin with  `IPM.NOTE`; this format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="227c0-446">`Source`-指示第三方数据源;例如, Twitter、Facebook 或 BlackBerry。</span><span class="sxs-lookup"><span data-stu-id="227c0-446">`Source` - Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="227c0-447">`Event`-指示在生成项目的第三方数据源中执行的活动类型。例如, 在 Twitter 中的 twitter 或 Facebook 中的帖子。</span><span class="sxs-lookup"><span data-stu-id="227c0-447">`Event` - Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="227c0-448">事件是特定于数据源的。</span><span class="sxs-lookup"><span data-stu-id="227c0-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="227c0-449">此属性的一个目的是基于项目源自的数据源或基于事件类型筛选特定项目。</span><span class="sxs-lookup"><span data-stu-id="227c0-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="227c0-450">例如，在电子数据展示搜索中，您可以创建一个搜索查询来查找特定用户发布的所有微博。</span><span class="sxs-lookup"><span data-stu-id="227c0-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="227c0-451">将项目成功导入 Office 365 中的邮箱时, 会将唯一标识符作为 HTTP 响应的一部分返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="227c0-451">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="227c0-452">此标识符 (称为`x-IngestionCorrelationID`) 可用于合作伙伴对项目进行端到端跟踪的后续故障排除目的。</span><span class="sxs-lookup"><span data-stu-id="227c0-452">This identifier—called  `x-IngestionCorrelationID`—can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="227c0-453">建议合作伙伴捕获此信息，并在他们的所在端相应地记录此信息。</span><span class="sxs-lookup"><span data-stu-id="227c0-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="227c0-454">下面是显示此标识符的 HTTP 响应的示例：</span><span class="sxs-lookup"><span data-stu-id="227c0-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="227c0-455">您可以使用安全与合规中心中的内容搜索工具来搜索从第三方数据源导入到 Office 365 中的邮箱的项目。</span><span class="sxs-lookup"><span data-stu-id="227c0-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="227c0-456">若要专门搜索这些导入项, 可以在内容搜索的关键字框中使用以下消息属性-值对。</span><span class="sxs-lookup"><span data-stu-id="227c0-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="227c0-457">**`kind:externaldata`**-使用此属性-值对可搜索所有第三方数据类型。</span><span class="sxs-lookup"><span data-stu-id="227c0-457">**`kind:externaldata`** - Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="227c0-458">例如, 若要搜索从第三方数据源导入, 并在导入项目的 Subject 属性中包含 "contoso" 一词的项目, 请使用关键字查询`kind:externaldata AND subject:contoso`。</span><span class="sxs-lookup"><span data-stu-id="227c0-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="227c0-459">**`itemclass:ipm.externaldata.<third-party data type>`**-使用此属性-值对仅搜索第三方数据的指定类型。</span><span class="sxs-lookup"><span data-stu-id="227c0-459">**`itemclass:ipm.externaldata.<third-party data type>`** - Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="227c0-460">例如, 若要在 Subject 属性中仅搜索包含 "contoso" 一词的 Facebook 数据, 则应使用关键字查询`itemclass:ipm.externaldata.Facebook* AND subject:contoso`。</span><span class="sxs-lookup"><span data-stu-id="227c0-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="227c0-461">有关用于`itemclass`属性的第三方数据类型的值的完整列表, 请参阅[使用内容搜索来搜索导入到 Office 365 的第三方数据](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="227c0-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="227c0-462">有关如何使用内容搜索以及创建关键字搜索查询的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="227c0-462">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="227c0-463">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="227c0-463">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="227c0-464">内容搜索的关键字查询和搜索条件</span><span class="sxs-lookup"><span data-stu-id="227c0-464">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 

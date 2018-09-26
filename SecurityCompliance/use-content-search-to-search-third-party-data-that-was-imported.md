---
title: 使用内容搜索搜索第三方数据导入到 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: 使用内容搜索电子数据展示工具来搜索已导入到 Office 365 中的邮箱从第三方数据源的项。您可以创建查询搜索所有导入的项或创建一个查询来搜索特定第三方数据类型。本文列出了您可以使用关键字查询中搜索可导入到 Office 365 的第三方数据类型的值。
ms.openlocfilehash: 6829e894ba687fb09184c32201f76394e37bbbf8
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037965"
---
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a><span data-ttu-id="2fa0c-105">使用内容搜索搜索第三方数据导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="2fa0c-105">Use Content Search to search third-party data that was imported to Office 365</span></span>

<span data-ttu-id="2fa0c-p102">您可以在 Office 365 安全性使用[内容搜索电子数据展示工具](content-search.md)&amp;合规性中心搜索已导入到 Office 365 中的邮箱从第三方数据源的项目。可以创建一个查询搜索所有导入第三方数据项也可以创建唯一的搜索查询特定第三方数据项。此外，您还可以创建基于查询的保留策略或基于查询的电子数据展示保留要保留在 Office 365 中的第三方数据。</span><span class="sxs-lookup"><span data-stu-id="2fa0c-p102">You can use the [Content Search eDiscovery tool](content-search.md) in the Office 365 Security &amp; Compliance Center to search for items that were imported to mailboxes in Office 365 from a third-party data source. You can create a query to search all imported third-party data items or you can create a query to only search specific third-party data items. Additionally, you can also create a query-based Preservation Policy or a query-based eDiscovery hold to preserve third-party data in Office 365.</span></span> 
  
<span data-ttu-id="2fa0c-109">有关导入第三方数据以及可以导入到 Office 365 的第三方数据类型的列表的详细信息，请参阅[Office 365 中的存档第三方数据](archiving-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa0c-109">For more information about importing third-party data and a list of the third-party data types that can be imported to Office 365, see [Archiving third-party data in Office 365](archiving-third-party-data.md).</span></span> 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="2fa0c-110">创建一个查询搜索所有第三方数据</span><span class="sxs-lookup"><span data-stu-id="2fa0c-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="2fa0c-p103">搜索 （或置于保持状态） 第三方数据已导入到 Office 365 的任何类型，您可以您可以使用`kind:externaldata`消息关键字框中的属性值对内容进行搜索或创建基于查询的保留时。例如，若要搜索已从任何第三方数据源导入的项目和导入的项目的 Subject 属性中包含"contoso"一词，您使用以下查询：</span><span class="sxs-lookup"><span data-stu-id="2fa0c-p103">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold. For example, to search for items that were imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```
kind:externaldata AND subject:contoso
```

<span data-ttu-id="2fa0c-p104">以前的关键字查询示例包含 subject 属性。有关其他属性的列表的第三方数据项的可以包含关键字查询，请参阅[Office 365 中的存档第三方数据](archiving-third-party-data.md#more-information)中的"详细信息"部分。</span><span class="sxs-lookup"><span data-stu-id="2fa0c-p104">The previous keyword query example includes the subject property. For a list of other properties for third-party data items that can included in a keyword query, see the "More information" section in [Archiving third-party data in Office 365](archiving-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="2fa0c-p105">在创建时查询搜索并保留第三方数据，您可以使用条件范围缩小搜索结果。有关创建内容的搜索查询的详细信息，请参阅[关键字查询和内容搜索的搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa0c-p105">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results. For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="2fa0c-117">创建查询来搜索特定类型的第三方数据</span><span class="sxs-lookup"><span data-stu-id="2fa0c-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="2fa0c-118">而不是搜索所有类型的第三方数据，您可以创建查询指定类型的第三方数据仅搜索使用下面的消息属性值对关键字框中的内容搜索：</span><span class="sxs-lookup"><span data-stu-id="2fa0c-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message property-value pair in the keyword box for a Content Search:</span></span>
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="2fa0c-119">例如，若要仅搜索包含单词"contoso"的使用者属性中的 Facebook 数据，将使用以下查询：</span><span class="sxs-lookup"><span data-stu-id="2fa0c-119">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="2fa0c-p106">下表列出了您可以搜索的第三方数据类型和值用于`itemclass:`消息属性设为专门的第三方数据类型的搜索。请注意查询语法不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="2fa0c-p106">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data. Note that the query syntax isn't case sensitive.</span></span> 
  
|<span data-ttu-id="2fa0c-122">**第三方数据类型**</span><span class="sxs-lookup"><span data-stu-id="2fa0c-122">**Third-party data type**</span></span>|<span data-ttu-id="2fa0c-123">**值`itemclass:`属性**</span><span class="sxs-lookup"><span data-stu-id="2fa0c-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2fa0c-124">AIM</span><span class="sxs-lookup"><span data-stu-id="2fa0c-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="2fa0c-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="2fa0c-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="2fa0c-126">使用 Pivot 客户端的 AOL</span><span class="sxs-lookup"><span data-stu-id="2fa0c-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="2fa0c-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="2fa0c-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="2fa0c-128">Ares</span><span class="sxs-lookup"><span data-stu-id="2fa0c-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="2fa0c-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="2fa0c-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="2fa0c-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="2fa0c-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="2fa0c-131">Axs 本地存档</span><span class="sxs-lookup"><span data-stu-id="2fa0c-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="2fa0c-132">A 占位符</span><span class="sxs-lookup"><span data-stu-id="2fa0c-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="2fa0c-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="2fa0c-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="2fa0c-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="2fa0c-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="2fa0c-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="2fa0c-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="2fa0c-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="2fa0c-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="2fa0c-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="2fa0c-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="2fa0c-138">BlackBerry 呼叫日志</span><span class="sxs-lookup"><span data-stu-id="2fa0c-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="2fa0c-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="2fa0c-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="2fa0c-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="2fa0c-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="2fa0c-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="2fa0c-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="2fa0c-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="2fa0c-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="2fa0c-143">Bloomberg 邮件
</span><span class="sxs-lookup"><span data-stu-id="2fa0c-143">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="2fa0c-144">彭博美国消息</span><span class="sxs-lookup"><span data-stu-id="2fa0c-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="2fa0c-145">Box
</span><span class="sxs-lookup"><span data-stu-id="2fa0c-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="2fa0c-146">Cisco IM&amp;状态服务器</span><span class="sxs-lookup"><span data-stu-id="2fa0c-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="2fa0c-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="2fa0c-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="2fa0c-148">适用于 Salesforce Chatter 的 CipherCloud</span><span class="sxs-lookup"><span data-stu-id="2fa0c-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="2fa0c-149">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="2fa0c-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="2fa0c-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="2fa0c-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="2fa0c-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="2fa0c-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="2fa0c-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="2fa0c-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="2fa0c-153">Flickr
</span><span class="sxs-lookup"><span data-stu-id="2fa0c-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="2fa0c-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="2fa0c-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="2fa0c-155">Google+
</span><span class="sxs-lookup"><span data-stu-id="2fa0c-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="2fa0c-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="2fa0c-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="2fa0c-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="2fa0c-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="2fa0c-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="2fa0c-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="2fa0c-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="2fa0c-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="2fa0c-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="2fa0c-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="2fa0c-161">IBM 连接</span><span class="sxs-lookup"><span data-stu-id="2fa0c-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="2fa0c-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="2fa0c-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="2fa0c-163">ICE 聊天</span><span class="sxs-lookup"><span data-stu-id="2fa0c-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="2fa0c-164">Indii Messenger
</span><span class="sxs-lookup"><span data-stu-id="2fa0c-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="2fa0c-165">Instagram
</span><span class="sxs-lookup"><span data-stu-id="2fa0c-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="2fa0c-166">即时 Bloomberg
</span><span class="sxs-lookup"><span data-stu-id="2fa0c-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="2fa0c-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="2fa0c-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="2fa0c-168">IRC</span><span class="sxs-lookup"><span data-stu-id="2fa0c-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="2fa0c-169">Jive
</span><span class="sxs-lookup"><span data-stu-id="2fa0c-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="2fa0c-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="2fa0c-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="2fa0c-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="2fa0c-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="2fa0c-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="2fa0c-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="2fa0c-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="2fa0c-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="2fa0c-174">Microsoft 统一沟通</span><span class="sxs-lookup"><span data-stu-id="2fa0c-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="2fa0c-175">注意对齐</span><span class="sxs-lookup"><span data-stu-id="2fa0c-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="2fa0c-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="2fa0c-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="2fa0c-177">MSN</span><span class="sxs-lookup"><span data-stu-id="2fa0c-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="2fa0c-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="2fa0c-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="2fa0c-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="2fa0c-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="2fa0c-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="2fa0c-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="2fa0c-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="2fa0c-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="2fa0c-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="2fa0c-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="2fa0c-183">QQ</span><span class="sxs-lookup"><span data-stu-id="2fa0c-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="2fa0c-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="2fa0c-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="2fa0c-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="2fa0c-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="2fa0c-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2fa0c-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="2fa0c-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="2fa0c-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="2fa0c-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="2fa0c-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="2fa0c-189">
Squawker
</span><span class="sxs-lookup"><span data-stu-id="2fa0c-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="2fa0c-190">Symphony
</span><span class="sxs-lookup"><span data-stu-id="2fa0c-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="2fa0c-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="2fa0c-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="2fa0c-192">Thomson Reuters Eikon Messenger
</span><span class="sxs-lookup"><span data-stu-id="2fa0c-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="2fa0c-193">Tor</span><span class="sxs-lookup"><span data-stu-id="2fa0c-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="2fa0c-194">TTT</span><span class="sxs-lookup"><span data-stu-id="2fa0c-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="2fa0c-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="2fa0c-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="2fa0c-196">UBS 聊天
</span><span class="sxs-lookup"><span data-stu-id="2fa0c-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="2fa0c-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="2fa0c-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="2fa0c-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="2fa0c-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="2fa0c-199">Winny</span><span class="sxs-lookup"><span data-stu-id="2fa0c-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="2fa0c-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="2fa0c-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="2fa0c-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="2fa0c-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="2fa0c-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="2fa0c-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="2fa0c-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="2fa0c-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |

---
title: 使用内容搜索来搜索导入到 Office 365 的第三方数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/27/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: 使用内容搜索电子数据展示工具搜索从第三方数据源导入到 Office 365 中的邮箱的项目。 您可以创建查询以搜索所有导入的项, 或创建查询以搜索特定的第三方数据类型。 本文列出了可以在关键字查询中使用的值, 以搜索可导入到 Office 365 的第三方数据类型。
ms.openlocfilehash: 0881456d377569fb55f0daf0d0a8a2a15bce62fc
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014742"
---
# <a name="use-content-search-to-search-third-party-data-that-was-imported-to-office-365"></a>使用内容搜索来搜索导入到 Office 365 的第三方数据

您可以使用安全性 & 合规性中心中的[内容搜索电子数据展示工具](content-search.md), 从第三方数据源搜索导入到 Office 365 中的邮箱的项目。 您可以创建查询来搜索所有导入的第三方数据项, 也可以创建查询仅搜索特定的第三方数据项。 此外, 还可以创建基于查询的 Office 365 保留策略或基于查询的电子数据展示保留, 以在 Office 365 中保留第三方数据。 
  
有关导入第三方数据和可以导入到 Office 365 的第三方数据类型列表的详细信息, 请参阅[在 office 365 中使用合作伙伴存档第三方数据](work-with-partner-to-archive-third-party-data.md)。 
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>创建查询以搜索所有第三方数据

若要搜索 (或置于保留状态) 您导入到 Office 365 的任何第三方数据类型, 您可以在内容搜索的`kind:externaldata`关键字框中使用邮件属性-值对, 也可以在创建基于查询的保留时使用。 例如, 若要搜索从任何第三方数据源导入的项目, 并在导入项目的 Subject 属性中包含 "contoso" 一词, 应使用以下查询: 
  
```
kind:externaldata AND subject:contoso
```

上一个关键字查询示例包括 subject 属性。 有关可包含在关键字查询中的第三方数据项的其他属性的列表, 请参阅在[Office 365 中存档第三方数据](work-with-partner-to-archive-third-party-data.md#more-information)一节中的 "详细信息" 部分。
  
创建查询以搜索并保存第三方数据时, 您还可以使用条件来缩小搜索结果的范围。 有关创建内容搜索查询的详细信息, 请参阅[用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>创建查询以搜索特定类型的第三方数据

您可以通过在内容搜索关键字框中使用以下消息属性值对来创建仅搜索指定类型的第三方数据的查询, 而不是搜索所有类型的第三方数据:
  
```
itemclass:ipm.externaldata.<third-party data type>* 
```

例如, 若要在 Subject 属性中仅搜索包含 "contoso" 一词的 Facebook 数据, 应使用以下查询:
  
```
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

下表列出了可以搜索的第三方数据类型, 以及要用于`itemclass:`邮件属性以专门搜索那种类型的第三方数据的值。 请注意, 查询语法不区分大小写。 
  
|**第三方数据类型**|**属性的`itemclass:`值**|
|:-----|:-----|
|对准  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|使用 Pivot 客户端的 AOL  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs 本地存档  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Axs 占位符  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry 呼叫日志  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry 针  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry 短信  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg 邮件  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|Bloomberg 消息传递  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM &amp;状态服务器  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|适用于 Salesforce Chatter 的 CipherCloud  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Direct Connect  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google +  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google 对话  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM 连接  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|ICE 聊天  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram  <br/> | `ipm.externaldata.Instagram*` <br/> |
|即时 Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|领英  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|构思对齐  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|直接  <br/> | `ipm.externaldata.MSN*` <br/> |
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|透视  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype for Business  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Squawker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS 聊天  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |

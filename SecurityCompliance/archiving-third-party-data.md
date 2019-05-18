---
title: 在 Office 365 中存档第三方数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: 管理员可以将来自社交媒体平台、即时消息平台和文档协作平台的第三方数据导入 Office 365 组织中的邮箱。 这样, 你就可以在 Office 365 中存档 Facebook、Twitter 和其他第三方数据源中的数据。 然后, 您可以使用并应用适用于第三方数据的 Office 365 合规性功能 (如法律封存、电子数据展示、就地存档和保留策略)。
ms.openlocfilehash: 33ce9c0d648d0c247abcaac8838e351d413a1990
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152075"
---
# <a name="archive-third-party-data-in-office-365"></a>在 Office 365 中存档第三方数据

Office 365 使管理员能够从社交媒体平台、即时消息平台和文档协作平台将第三方数据导入和存档到 Office 365 组织中的邮箱。 可以导入到 Office 365 的第三方数据源示例包括以下内容: 
  
- **社交**-Twitter、Facebook、Yammer 和 LinkedIn 
    
- **即时消息**-Yahoo Messenger、GoogleTalk 和 Cisco Jabber 
    
- **文档协作**-Box 和 DropBox 
    
- **垂直行业**-客户关系管理 (如 Salesforce Chatter) 和金融服务 (如 Bloomberg 和 Thomson Reuters) 
    
- **SMS/短信**-BlackBerry 
    
导入第三方数据后, 可以将 Office 365 合规性功能 (如诉讼保留、电子数据展示、就地存档、审核、监督和 Office 365 保留策略) 应用于此类数据。 例如，当将邮箱置于诉讼保留时，将保留第三方数据。 您可以使用 Microsoft 电子数据展示工具搜索第三方数据。 或者，您可以将存档和保留策略应用于第三方数据，就像可以应用于 Microsoft 数据那样。 简言之, 在 Office 365 中存档第三方数据可帮助您的组织遵守政府和法规策略。

有两种方法可在 Office 365 中导入和存档第三方数据:

- **在安全 _AMP_ 合规中心中使用第三方数据连接器**-使用在 Office 365 的 Security _AMP_ 合规性中心中提供的自定义数据连接器。 设置并配置连接器后, 它会连接到第三方数据源, 将项目的内容转换为电子邮件格式, 然后将该项目导入 Office 365 中的邮箱。 目前, 您可以实施示例连接器以导入和存档 Facebook 商业页面和 Twitter 中的数据。 有关设置连接器的分步说明, 请参阅:
   
   - **Facebook** - [使用示例连接器在 Office 365 中存档 Facebook 数据 (预览)](archive-facebook-data-with-sample-connector.md)
  
   - **Twitter** - [使用示例连接器在 Office 365 中存档 Twitter 数据 (预览)](archive-twitter-data-with-sample-connector.md)

- **使用 microsoft 合作伙伴**-你的组织与 microsoft 合作伙伴合作, 该合作伙伴将提供一个自定义连接器, 该合作伙伴将配置为从第三方数据源提取项目 (定期), 然后连接到 Microsoft 云第三方 API 并将这些项目导入到 Office 365。 合作伙伴连接器还将项目的内容从第三方数据源转换为电子邮件, 然后将其导入到 Office 365 中的邮箱。 有关可以使用的合作伙伴列表和此方法的分步过程, 请参阅在[Office 365 中存档第三方数据](work-with-partner-to-archive-third-party-data.md)的合作合作伙伴。
---
title: Office 365 云应用安全的 Web 流量日志和数据源
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: Office 365 云应用安全性适用于各种提供程序中的 web 流量日志。阅读本文以了解有关 Office 365 云应用安全的 web 流量日志和受支持的数据源的详细信息。
ms.openlocfilehash: 67246ded0e3d39c81b5b906f753b91298309d1d8
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218102"
---
# <a name="web-traffic-logs-and-data-sources-for-office-365-cloud-app-security"></a>Office 365 云应用安全的 Web 流量日志和数据源
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|[开始评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |你在这里!  <br/> [后续步骤](#next-steps) <br/> |
  
您可以使用各种 web 流量日志文件和具有 Office 365 云应用安全性的数据源。但是, web 流量日志文件必须包含特定的信息并以某种方式进行格式设置, 这样它们才能与 Office 365 云应用安全应用程序发现报告和云发现仪表板配合使用。将本文作为参考指南, 可用于将用于 Office 365 云应用安全的 web 流量日志和数据源。
  
> [!NOTE]
> 您必须是全局管理员、安全管理员或安全读者才能访问安全&amp;合规性中心和 Office 365 云应用安全门户。请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="web-traffic-log-requirements"></a>Web 流量日志要求

Office 365 云应用安全使用 web 流量日志中的数据来帮助您了解贵组织中的哪些应用程序正在使用哪些应用程序。日志文件中包含的详细信息越多, 您对用户活动的可见性越好。
  
以下各节列出了在 Office 365 云应用安全中正常运行所需的必要属性和其他要求。

### <a name="attributes"></a>特性

Office 365 云应用安全无法显示或分析 web 流量日志中未包含的属性。例如, Cisco ASA 防火墙的标准日志格式没有每个事务、用户名或目标 URL (仅目标 IP) 上传的字节数。因此, 这些属性不会显示在云发现数据中, 并且对云应用的可见性将受到限制。对于 Cisco ASA 防火墙, 信息级别必须设置为6。 

web 流量日志应包含以下属性:

- 交易记录日期
- 源 IP
- 源用户 (强烈推荐)
- 目标 IP 地址
- 目标 URL (推荐);与 IP 地址相比, url 提供了更高的云应用检测精度
- 总数据量 (推荐); 数据信息非常有价值
- 上载或下载的数据量 (推荐); 提供有关云应用使用模式的见解
- 执行的操作 (允许或阻止)

### <a name="additional-requirements"></a>其他要求 

除了本文前面列出的属性之外, web 流量日志还应满足以下要求:

- 必须支持日志文件的数据源。
- 日志文件使用的格式必须与标准格式相匹配。上载文件后, 应用程序发现将对此进行验证。
- 日志中的事件必须在90天前不会发生。
- 日志文件必须包含可针对网络活动进行分析的出站流量信息。
  
## <a name="data-attributes-for-different-vendors"></a>不同供应商的数据属性

下表汇总了来自不同供应商的 web 流量日志中的信息。**请务必与供应商联系, 了解最新信息。**


|                 数据源                  |    目标应用程序 URL    |    目标应用程序 IP     |       用户名       |      源 IP       |    总流量     |    上载的字节    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |          否          |          否          |
|                  蓝色 Coat                   | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  Checkpoint                  |          否          | <strong>是</strong> |          否          | <strong>是</strong> |          否          |          否          |
|              Cisco ASA (Syslog)              |          否          | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> |          否          |
|           具有 FirePOWER 的 Cisco ASA           | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  Cisco FWSM                  |          否          | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> |          否          |
|              Cisco Ironport WSA              | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                 Cisco Meraki                 | <strong>是</strong> | <strong>是</strong> |          否          | <strong>是</strong> |          否          |          否          |
|           Clavister NGFW (Syslog)            | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                SonicWall (以前称为戴尔)                | <strong>是</strong> | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|            数字艺术 i-筛选器             | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  Fortigate                   |          否          | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                 刺柏 SRX                  |          否          | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                 刺柏 SSG                  |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                  McAfee SWG                  | <strong>是</strong> |          否          |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                    MS TMG                    | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|              Palo Alto 网络              |          否          | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                    Sophos                    | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |          否          |
|                Squid (通用)                | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> |          否          | <strong>是</strong> |
|                Squid (本机)                | <strong>是</strong> |          否          | <strong>是</strong> | <strong>是</strong> |          否          | <strong>是</strong> |
| Websense-调查详细信息报告 (CSV) | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|    Websense-Internet 活动日志 (CEF)    | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
|                   Zscaler                    | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> | <strong>是</strong> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>支持的供应商防火墙和代理

Office 365 云应用安全支持以下防火墙和代理。
  
- Barracuda-Web 应用程序防火墙 (W3C)  
- 蓝色 Coat 代理 SG-Access 日志 (W3C)
- 检查点
- Cisco ASA 防火墙 (请确保将信息级别设置为 6)
- 具有 FirePOWER 的 Cisco ASA   
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Merkai-url 日志
- Clavister NGFW (Syslog)
- 数字艺术 i-筛选器
- Fortinet Fortigate
- iboss 安全云网关
- 刺柏 SRX
- 刺柏 SSG
- McAfee 安全 Web 网关
- Microsoft Forefront 威胁管理网关 (W3C)
- Palo Alto 系列防火墙
- Sonicwall (以前称为戴尔)   
- Sophos SG
- Sophos XG
- Sophos Cyberoam
- Squid (通用)
- Squid (本机)
- Websense-Web 安全解决方案-调查详细信息报告 (CSV)
- Websense-Web 安全解决方案-Internet 活动日志 (CEF)
- Zscaler
    
> [!NOTE]
> 如果此处未包含要使用的数据源, 则可以请求将其添加到应用发现中。若要执行此操作, 请在创建报表时, 选择 "**其他**" 作为 "**数据源**"。然后键入要尝试上载的数据源的名称。我们将查看日志, 并告诉你我们是否添加了对该日志类型的支持。或者, 您可以定义与您的格式匹配的[自定义分析器](https://docs.microsoft.com/cloud-app-security/custom-log-parser)。 
  
## <a name="troubleshoot-errors-when-log-files-are-uploaded"></a>在上载日志文件时排查错误

上载 web 流量日志文件后, 请检查调控日志以查看是否有任何错误。如果有错误, 请使用下表中的信息来解决这些错误。
  
|**错误**|**说明**|**解决方法**|
|:-----|:-----|:-----|
|不支持的文件类型  <br/> |上载的文件不是有效的日志文件。例如, 图像文件。  <br/> |上载直接从防火墙或代理导出的文本、zip 或 gzip 文件。  <br/> |
|内部错误  <br/> |检测到内部资源故障。  <br/> |单击 "**重试**" 以重新运行该任务。  <br/> |
|日志格式不匹配  <br/> |您上载的日志格式与此数据源的预期日志格式不匹配。  <br/> |
验证日志是否未损坏。比较日志文件格式并将其与上载页面上显示的示例格式相匹配。 |
|事务超过90天  <br/> |所有事务的历史时间超过90天, 因此将被忽略。  <br/> |使用最新的事件导出新日志并重新上载它。  <br/> |
|无交易到目录云应用  <br/> |日志中找不到任何可识别的云应用的事务。  <br/> |验证日志中是否包含出站流量信息。  <br/> |
|不支持的日志类型  <br/> |如果选择 "**数据源 = 其他 (不受支持)**", 则不会对日志进行分析。而是发送给[Microsoft 云应用安全](https://aka.ms/whatiscas)技术团队进行审阅。<br/> |[Microsoft 云应用安全](https://aka.ms/whatiscas)技术团队为每个数据源生成专用分析器。已支持大多数热门数据源。当上载不受支持的数据源时, 将对其进行检查并将其添加到潜在的新数据源分析程序列表中。<br/> 将新的分析器添加到功能时, Microsoft 云应用安全发布说明中包含一个通知。  <br/> |
   
## <a name="next-steps"></a>后续步骤

- [查看警报并对其执行操作](review-office-365-cas-alerts.md)
    
- [创建应用发现报告](create-app-discovery-reports-in-ocas.md)
    
- [查看应用程序发现结果](review-app-discovery-findings-in-ocas.md)
    
- [查看 Office 365 云应用安全性的利用率活动](utilization-activities-for-ocas.md)
    


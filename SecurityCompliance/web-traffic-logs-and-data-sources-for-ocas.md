---
title: Office 365 云应用安全的 Web 流量日志和数据源
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: 从各种各样的提供程序的 web 流量日志云应用程序安全性适用于 office 365。阅读此文，了解有关 web 流量日志的详细信息和支持的 Office 365 云应用程序安全性的数据源。
ms.openlocfilehash: 09b0358e0d8b9a6ed59393d8771237f7eaf8bb98
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525499"
---
# <a name="web-traffic-logs-and-data-sources-for-office-365-cloud-app-security"></a>Office 365 云应用安全的 Web 流量日志和数据源
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|使用率 ***|
|:-----|:-----|:-----|:-----|
|[启动评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |在这里 ！  <br/> [后续步骤](#next-steps) <br/> |
  
您可以使用 Office 365 云应用程序安全性各种各样的 web 流量日志文件和数据源。但是，您的 web 流量日志文件必须包括特定信息，并且要设置格式以某种方式，以便它们可以使用 Office 365 云应用程序安全性应用程序发现报告和云发现仪表板。使用本文作为参考指南 web 流量日志和将用于 Office 365 云应用程序安全性的数据源。
  
> [!NOTE]
> 您必须是全局管理员、 安全管理员或安全读者访问安全性&amp;合规性中心和 Office 365 云应用程序安全性门户。请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="web-traffic-log-requirements"></a>Web 流量日志要求

使用您的 web 流量日志，以帮助您了解您的组织中人员的应用程序中的 office 365 云应用程序安全性使用数据。在日志文件中，更好地了解您必须用户活动包含更多详细信息。
  
下表列出的要求和 web 流量日志与 Office 365 云应用程序安全性正常工作所需的属性：
  
|**特性**|**其他要求 **|
|:-----|:-----|
| 交易记录日期  <br/>  源 IP  <br/>  源用户 （推荐）  <br/>  目标 IP 地址  <br/>  目标 URL (推荐： Url 提供准确度云应用程序检测比 IP 地址)  <br/>  总 （推荐） 的数据量  <br/>  量上载或下载数据 (推荐： 提供有关云见解应用程序使用模式)  <br/>  采取 （允许或阻止）  <br/> | 必须支持的日志文件的数据源。  <br/>  日志文件使用的格式必须匹配标准格式。在上载该文件时应用程序发现将验证这。  <br/>  事件日志中的必须发生不超过 90 天。  <br/>  日志文件必须包含可以分析的网络活动的出站通信信息。  <br/> |
   
如果属性不包括在加载的日志，Office 365 云应用程序安全性无法显示或分析您的信息。例如，Cisco ASA 防火墙标准日志格式不包括每个事务、 username 或目标 URL (仅目标 IP) 上载字节的数。因为这些信息不在 Cisco 日志文件中，Office 365 云应用程序安全性将不会将其包含时分析贵组织的网络流量。
  
> [!NOTE]
> 对于某些类型的防火墙，必须设置 web 流量日志，以包含所需的属性的信息级别。例如，Cisco ASA 防火墙必须具有信息级别设置为 6。请确保以确认您的防火墙已设置为在您的 web 流量日志中提供了正确的信息。 
  
## <a name="data-attributes-for-different-vendors"></a>其他供应商数据属性
<a name="BKMK_LogAndData"> </a>

下表总结了各种供应商的 web 流量日志中的信息。**一定要查看您的供应商的最新信息。**
  
|**数据源**|**目标应用程序 URL**|**目标应用程序 IP**|**Username**|**原点 IP**|**总的流量**|**上载的字节**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Barracuda  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |否  <br/> |否  <br/> |
|蓝色衣帽  <br/> |**是** <br/> |否  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|检查点  <br/> |否  <br/> |**是** <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|Cisco ASA  <br/> |否  <br/> |**是** <br/> |否  <br/> |**是** <br/> |**是** <br/> |否  <br/> |
|Cisco FWSM  <br/> |否  <br/> |**是** <br/> |否  <br/> |**是** <br/> |**是** <br/> |否  <br/> |
|Cisco Ironport WSA  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Cisco Meraki  <br/> |**是** <br/> |**是** <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|Clavister NGFW (Syslog)  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Dell 使 SonicWall  <br/> |**是** <br/> |**是** <br/> |否  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Fortigate  <br/> |否  <br/> |**是** <br/> |否  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Juniper SRX  <br/> |否  <br/> |**是** <br/> |否  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Juniper SSG  <br/> |否  <br/> |**是** <br/> |否  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|McAfee SWG  <br/> |**是** <br/> |否  <br/> |否  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Meraki (Cisco)  <br/> |**是** <br/> |**是** <br/> |否  <br/> |**是** <br/> |否  <br/> |否  <br/> |
|Microsoft Threat Management Gateway  <br/> |**是** <br/> |否  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|帕洛阿尔托市网络  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Sophos  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |否  <br/> |
|Squid （通用）  <br/> |**是** <br/> |否  <br/> |**是** <br/> |**是** <br/> |否  <br/> |**是** <br/> |
|Squid （本机）  <br/> |**是** <br/> |否  <br/> |**是** <br/> |**是** <br/> |否  <br/> |**是** <br/> |
|Websense-调查的详细信息报告 (CSV)  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Websense-Internet 活动日志 (CEF)  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
|Zscaler  <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |**是** <br/> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>支持供应商防火墙和代理
<a name="BKMK_Supported"> </a>

Office 365 云应用程序安全性支持下列防火墙和代理。
  
- Barracuda-Web 应用程序防火墙 (W3C)
    
- 蓝色衣帽代理 SG-访问日志 (W3C)
    
- 检查点
    
- Cisco ASA 防火墙 （请注意，您必须将信息级别设置为 6）
    
- Cisco IronPort WSA
    
- Cisco ScanSafe
    
- Cisco Merkai-Url 日志
    
- Dell 使 Sonicwall
    
- Fortinet Fortigate
    
- Juniper SRX
    
- Juniper SSG
    
- McAfee 安全 Web 网关
    
- Microsoft Forefront Threat Management Gateway (W3C)
    
- 帕洛阿尔托市系列防火墙
    
- Sophos SG
    
- Sophos Cyberoam
    
- Squid （通用）
    
- Squid （本机）
    
- Websense-Web 安全解决方案-调查的详细信息报告 (CSV)
    
- Websense-Web 安全解决方案-Internet 活动日志 (CEF)
    
- Zscaler
    
> [!NOTE]
> 如果您想要使用的数据源不包含此处，您可以请求将其添加到应用程序发现。若要这样一来，您正在创建报告时，选择**其他****数据**源。然后键入您要上载的数据源的名称。我们将查看日志，并让您了解如果我们添加对该日志类型的支持。 
  
## <a name="troubleshoot-errors-when-log-files-are-uploaded"></a>上载日志文件时解决错误

上载 web 流量日志文件后，检查调控日志，以查看是否存在任何错误。如果没有错误，使用下表中的信息来解决这些错误。
  
|**错误**|**说明**|**解决方案**|
|:-----|:-----|:-----|
|不受支持的文件类型  <br/> |上载的文件不是有效的日志文件。例如，图像文件。  <br/> |上载文本、 zip 或直接从您的防火墙或代理导出的 gzip 文件。  <br/> |
|内部错误  <br/> |检测到内部资源失败。  <br/> |单击**重试**重新运行任务。  <br/> |
|日志格式不匹配  <br/> |您上载日志格式与该数据源的预期的日志格式不匹配。  <br/> |
确认日志未损坏。比较并匹配在上载页上显示的示例格式的日志文件格式。 |
|事务的多个已存在 90 天  <br/> |所有的交易记录是多个已存在 90 天，因此被忽略。  <br/> |导出最新事件与新的日志，并将其重新上载。  <br/> |
|目录中的云应用程序没有事务  <br/> |无需任何识别的云应用程序的事务日志中找到。  <br/> |确认日志包含的出站流量的信息。  <br/> |
|不支持的日志类型  <br/> |当您选择**数据源 = 其他 （不支持的）**，日志未分列。而是将其发送至[Microsoft 云应用程序安全性](https://aka.ms/whatiscas)技术组审阅。<br/> |[Microsoft 云应用程序安全性](https://aka.ms/whatiscas)技术团队项目生成每个数据源的专用的分析器。已支持最常用的数据源。如果上载的不受支持的数据源，它为审阅并添加到的潜在的新数据源分析程序列表。<br/> 将新的分析程序添加到该功能后，Microsoft 云应用程序安全性发行说明包含通知。  <br/> |
   
## <a name="next-steps"></a>后续步骤

- [查看并通知对其执行操作](review-office-365-cas-alerts.md)
    
- [创建应用程序发现报告](create-app-discovery-reports-in-ocas.md)
    
- [查看应用程序发现结果](review-app-discovery-findings-in-ocas.md)
    
- [查看使用率活动的 Office 365 云应用程序安全性](utilization-activities-for-ocas.md)
    


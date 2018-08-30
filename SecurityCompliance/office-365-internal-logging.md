---
title: Office 365 的 Office 365 工程内部日志记录
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/18/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 说明如何内部日志记录的 Office 365 工程团队的工作原理。
ms.openlocfilehash: 1a613584b6b815524435acb20db7a8022d95e3bc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525112"
---
# <a name="internal-logging-for-office-365-engineering"></a><span data-ttu-id="ac4a9-103">Office 365 工程部的内部日志记录</span><span class="sxs-lookup"><span data-stu-id="ac4a9-103">Internal Logging for Office 365 Engineering</span></span>
<span data-ttu-id="ac4a9-p101">除了事件和可用于客户的日志数据，还有一些可供 Office 365 工程师内部日志数据收集系统。许多不同类型的日志数据上载到数据计算调用宇宙服务的内部、 大从 Office 365 服务器。每个服务工作组会从其各自的服务器的审核日志上载到聚合和分析的宇宙数据库。此数据传输通过 FIPS 140 2 验证 TLS 连接上专门批准的端口和协议使用专有自动化工具调用 Office 数据加载程序 (ODL) 发生此事件。</span><span class="sxs-lookup"><span data-stu-id="ac4a9-p101">In addition to the events and log data available for customers, there is also an internal log data collection system that is available to Office 365 engineers. Many different types of log data are uploaded from Office 365 servers to an internal, big data computing service called Cosmos. Each service team uploads audit logs from their respective servers into the Cosmos database for aggregation and analysis. This data transfer occurs over a FIPS 140-2-validated TLS connection on specifically approved ports and protocols using a proprietary automation tool called the Office Data Loader (ODL).</span></span>

<span data-ttu-id="ac4a9-p102">服务团队使用宇宙作为中央存储库的应用程序使用率，来测量系统和运行性能，并查找异常情况和可能指示问题或安全问题的模式进行分析。每个服务工作组上载比较基准的登录到宇宙，具体取决于他们希望分析，通常包括：</span><span class="sxs-lookup"><span data-stu-id="ac4a9-p102">Service teams use Cosmos as a centralized repository to conduct an analysis of application usage, to measure system and operational performance, and to look for abnormalities and patterns that may indicate problems or security issues. Each service team uploads a baseline of logs into Cosmos, depending on what they are looking to analyze, that often include:</span></span>
- <span data-ttu-id="ac4a9-110">事件日志</span><span class="sxs-lookup"><span data-stu-id="ac4a9-110">Event logs</span></span>
- <span data-ttu-id="ac4a9-111">AppLocker 日志</span><span class="sxs-lookup"><span data-stu-id="ac4a9-111">AppLocker logs</span></span>
- <span data-ttu-id="ac4a9-112">性能数据</span><span class="sxs-lookup"><span data-stu-id="ac4a9-112">Performance data</span></span>
- <span data-ttu-id="ac4a9-113">系统中心数据</span><span class="sxs-lookup"><span data-stu-id="ac4a9-113">System Center data</span></span>
- <span data-ttu-id="ac4a9-114">呼叫详细记录</span><span class="sxs-lookup"><span data-stu-id="ac4a9-114">Call detail records</span></span>
- <span data-ttu-id="ac4a9-115">体验质量数据</span><span class="sxs-lookup"><span data-stu-id="ac4a9-115">Quality of experience data</span></span>
- <span data-ttu-id="ac4a9-116">IIS Web 服务器日志</span><span class="sxs-lookup"><span data-stu-id="ac4a9-116">IIS Web Server logs</span></span>
- <span data-ttu-id="ac4a9-117">SQL Server 日志</span><span class="sxs-lookup"><span data-stu-id="ac4a9-117">SQL Server logs</span></span>
- <span data-ttu-id="ac4a9-118">系统日志数据</span><span class="sxs-lookup"><span data-stu-id="ac4a9-118">Syslog data</span></span>
- <span data-ttu-id="ac4a9-119">安全审核日志</span><span class="sxs-lookup"><span data-stu-id="ac4a9-119">Security audit logs</span></span>

<span data-ttu-id="ac4a9-p103">将数据上载到宇宙之前, ODL 应用程序使用清理服务模糊化包含客户数据，例如租户信息和最终用户身份信息的任何字段并将这些字段替换哈希值。Anonymized 和哈希日志是重写，然后上载到宇宙。服务团队对宇宙中进行关联，警报，并报告其数据运行作用域的查询。由服务团队中; 确定宇宙中的审核日志数据保留期大多数审核日志数据保留 90 天或更长时间支持安全事件调查，从而满足法规保留要求。</span><span class="sxs-lookup"><span data-stu-id="ac4a9-p103">Prior to uploading data into Cosmos, the ODL application uses a scrubbing service to obfuscate any fields that contain customer data, such as tenant information and end-user identifiable information, and replace those fields with a hash value. The anonymized and hashed logs are rewritten and then uploaded into Cosmos. Service teams run scoped queries against their data in Cosmos for correlation, alerting, and reporting. The period of audit log data retention in Cosmos is determined by the service teams; most audit log data is retained for 90 days or longer to support security incident investigations and to meet regulatory retention requirements.</span></span>

<span data-ttu-id="ac4a9-p104">Office 365 中宇宙存储的数据访问仅限于授权的人员。Microsoft 限制对服务工作组成员的负责审核功能有限子集的审核功能的管理。这些团队成员不具有能够修改或删除数据从宇宙，并记录和审核日志记录机制宇宙对所有更改。</span><span class="sxs-lookup"><span data-stu-id="ac4a9-p104">Access to Office 365 data stored in Cosmos is restricted to authorized personnel. Microsoft restricts the management of audit functionality to the limited subset of service team members that are responsible for audit functionality. These team members do not have the ability to modify or delete data from Cosmos, and all changes to logging mechanisms for Cosmos are recorded and audited.</span></span>

<span data-ttu-id="ac4a9-p105">每个服务工作组的授权某些应用程序来执行特定的分析来访问其日志数据进行分析。例如，Office 365 安全工作组使用数据从宇宙通过专有的事件日志分析程序关联，通知中，并在 Office 365 生产环境中生成可操作可能可疑活动的报告。若要更正漏洞，并提高该服务的总体性能使用此数据的报告。如果特定警报或报表需要进一步调查，服务人员可以请求将数据导入回 Office 365 服务。以来特定日志正在从宇宙导入中加密和服务人员有权访问解密密钥，目标日志以编程方式传递通过作用域的结果返回到授权的服务人员解密服务。从本练习发现的任何漏洞报告并上报使用 Microsoft 的标准安全事件管理通道。</span><span class="sxs-lookup"><span data-stu-id="ac4a9-p105">Each service team accesses its log data for analysis by authorizing certain applications to conduct specific analysis. For example, the Office 365 Security team uses data from Cosmos through a proprietary event log parser to correlate, alert, and generate actionable reports on possible suspicious activity in the Office 365 production environment. The reports from this data are used to correct vulnerabilities, and to improve the overall performance of the service. If a specific alert or report requires further investigation, service personnel can request that data be imported back into the Office 365 service. Since the specific log being imported from Cosmos is in encrypted and service personnel do not have access to decryption keys, the target log is programmatically passed through a decryption service that returns scoped results to the authorized service personnel. Any vulnerabilities found from this exercise are reported and escalated using Microsoft's standard security incident management channels.</span></span>

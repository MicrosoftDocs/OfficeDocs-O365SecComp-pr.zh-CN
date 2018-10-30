---
title: 与 Microsoft 365 SIEM 服务器集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- SIEM
description: 摘要： 阅读这篇文章，获取 SIEM server 与 Microsoft 365 的集成的概述。
ms.openlocfilehash: bd512ca6d75928712e3444581a78610a0869123d
ms.sourcegitcommit: 63ed467fc3e1ab1ab9ee122df97c64737169834e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2018
ms.locfileid: "25842675"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="62f74-103">SIEM server 与 Microsoft 365 服务和应用程序的集成</span><span class="sxs-lookup"><span data-stu-id="62f74-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="overview"></a><span data-ttu-id="62f74-104">概述</span><span class="sxs-lookup"><span data-stu-id="62f74-104">Overview</span></span>

<span data-ttu-id="62f74-p101">如果您的组织使用的安全信息和事件管理 (SIEM) 的服务器，或者如果您打算很快获取 SIEM 服务器，您可能想知道的将如何集成进行 Microsoft 365，包括 Office 365 企业版。是否需要 SIEM 服务器取决于多个因素，如贵组织的安全要求。Microsoft 365 提供了多种安全功能;但是，如果您的组织有内容和应用程序在本地和在云中 （如所混合云部署的大小写），则可以考虑添加额外保护 SIEM 服务器。或者，如果您的组织必须满足的特别严格的安全要求，则可以考虑将 SIEM 服务器添加到您的环境。</span><span class="sxs-lookup"><span data-stu-id="62f74-p101">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with your Microsoft 365, including Office 365 Enterprise. Whether you need a SIEM server depends on many factors, such as your organization's security requirements. Microsoft 365 offers a variety of security features; however, if your organization has content and applications on premises and in the cloud (as in the case of a hybrid cloud deployment), you might consider adding a SIEM server for extra protection. Or, if your organization has particularly stringent security requirements you must meet, you might consider adding a SIEM server to your environment.</span></span>

## <a name="siem-server-integration-microsoft-365"></a><span data-ttu-id="62f74-109">SIEM 服务器集成 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62f74-109">SIEM server integration Microsoft 365</span></span>

<span data-ttu-id="62f74-p102">SIEM 服务器可以接收来自各种 Microsoft 365 服务和应用程序的数据。下表列出了多个 Microsoft 365 服务和应用程序以及 SIEM 服务器输入和位置单击以了解有关 SIEM 服务器集成。</span><span class="sxs-lookup"><span data-stu-id="62f74-p102">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications. The following table lists several Microsoft 365 services and applications along with SIEM server inputs and where to go to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="62f74-112">Microsoft 365 服务或应用程序</span><span class="sxs-lookup"><span data-stu-id="62f74-112">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="62f74-113">SIEM 服务器输入</span><span class="sxs-lookup"><span data-stu-id="62f74-113">SIEM server inputs</span></span> | <span data-ttu-id="62f74-114">若要了解更多的资源</span><span class="sxs-lookup"><span data-stu-id="62f74-114">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="62f74-115">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="62f74-115">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md) <br/>   <span data-ttu-id="62f74-116">或</span><span class="sxs-lookup"><span data-stu-id="62f74-116">or</span></span>   <br/>[<span data-ttu-id="62f74-117">Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="62f74-117">Office 365 Threat Intelligence</span></span>](office-365-ti.md) | <span data-ttu-id="62f74-118">审核日志</span><span class="sxs-lookup"><span data-stu-id="62f74-118">Audit logs</span></span> | [<span data-ttu-id="62f74-119">与 Office 365 威胁智能和高级威胁保护 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="62f74-119">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="62f74-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="62f74-120">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="62f74-121">日志集成</span><span class="sxs-lookup"><span data-stu-id="62f74-121">Log integration</span></span> | [<span data-ttu-id="62f74-122">与 Microsoft 云应用程序安全性的 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="62f74-122">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="62f74-123">Office 365 云应用安全</span><span class="sxs-lookup"><span data-stu-id="62f74-123">Office 365 Cloud App Security</span></span>](office-365-cas-overview.md) | <span data-ttu-id="62f74-124">日志集成</span><span class="sxs-lookup"><span data-stu-id="62f74-124">Log integration</span></span> | [<span data-ttu-id="62f74-125">将 SIEM 服务器与 Office 365 云应用安全集成</span><span class="sxs-lookup"><span data-stu-id="62f74-125">Integrate your SIEM server with Office 365 Cloud App Security</span></span>](integrate-your-siem-server-with-office-365-cas.md) |
| [<span data-ttu-id="62f74-126">Windows Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="62f74-126">Windows Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="62f74-127">日志集成</span><span class="sxs-lookup"><span data-stu-id="62f74-127">Log integration</span></span> | [<span data-ttu-id="62f74-128">SIEM 工具拉通知</span><span class="sxs-lookup"><span data-stu-id="62f74-128">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| <span data-ttu-id="62f74-129">[Azure 安全中心](https://docs.microsoft.com/azure/security-center/security-center-intro)（威胁保护和威胁检测）</span><span class="sxs-lookup"><span data-stu-id="62f74-129">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Threat Protection and Threat Detection)</span></span> | <span data-ttu-id="62f74-130">警报</span><span class="sxs-lookup"><span data-stu-id="62f74-130">Alerts</span></span> | [<span data-ttu-id="62f74-131">Azure 安全数据导出到 SIEM-管道配置-预览</span><span class="sxs-lookup"><span data-stu-id="62f74-131">Azure Security data export to SIEM - Pipeline Configuration - Preview</span></span>](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [<span data-ttu-id="62f74-132">Azure Active Directory 标识保护</span><span class="sxs-lookup"><span data-stu-id="62f74-132">Azure Active Directory Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | <span data-ttu-id="62f74-133">审核日志</span><span class="sxs-lookup"><span data-stu-id="62f74-133">Audit logs</span></span> | [<span data-ttu-id="62f74-134">集成 Azure Active Directory 审核日志</span><span class="sxs-lookup"><span data-stu-id="62f74-134">Integrate Azure Active Directory audit logs</span></span>](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [<span data-ttu-id="62f74-135">Azure 高级的威胁分析</span><span class="sxs-lookup"><span data-stu-id="62f74-135">Azure Advanced Threat Analytics</span></span>](https://docs.microsoft.com/azure/security/azure-threat-detection) | <span data-ttu-id="62f74-136">日志集成</span><span class="sxs-lookup"><span data-stu-id="62f74-136">Log integration</span></span> | [<span data-ttu-id="62f74-137">ATA SIEM 日志参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="62f74-137">ATA SIEM log reference</span></span>](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="62f74-138">必须打开审核日志记录</span><span class="sxs-lookup"><span data-stu-id="62f74-138">Audit logging must be turned on</span></span>

<span data-ttu-id="62f74-139">请确保之前配置 SIEM 服务器集成审核日志记录已打开。</span><span class="sxs-lookup"><span data-stu-id="62f74-139">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="62f74-140">SharePoint online，OneDrive for Business 和 Azure Active Directory[中的安全性和合规性中心启用审核日志记录](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="62f74-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="62f74-141">有关 Exchange Online，[使用 Windows PowerShell 开启审核日志记录](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)。</span><span class="sxs-lookup"><span data-stu-id="62f74-141">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="62f74-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62f74-142">See Also</span></span>

[<span data-ttu-id="62f74-143">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="62f74-143">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="62f74-144">云采用测试实验室指南 (TLG)</span><span class="sxs-lookup"><span data-stu-id="62f74-144">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)



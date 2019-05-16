---
title: SIEM server 与 Microsoft 365 的集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: '摘要: 阅读本文, 了解 SIEM server 与 Microsoft 365 集成的概述。'
ms.openlocfilehash: f1911aabaccb7a6c2a56bbd5ff37e396730db72a
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077518"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="dff3b-103">SIEM server 与 Microsoft 365 服务和应用程序的集成</span><span class="sxs-lookup"><span data-stu-id="dff3b-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="overview"></a><span data-ttu-id="dff3b-104">概述</span><span class="sxs-lookup"><span data-stu-id="dff3b-104">Overview</span></span>

<span data-ttu-id="dff3b-105">如果您的组织使用的是安全信息和事件管理 (SIEM) 服务器, 或者您打算马上获取 SIEM 服务器, 那么您可能会想知道如何与您的 Microsoft 365 (包括 Office 365 企业版) 集成。</span><span class="sxs-lookup"><span data-stu-id="dff3b-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with your Microsoft 365, including Office 365 Enterprise.</span></span> <span data-ttu-id="dff3b-106">您是否需要 SIEM 服务器取决于多个因素, 例如组织的安全要求。</span><span class="sxs-lookup"><span data-stu-id="dff3b-106">Whether you need a SIEM server depends on many factors, such as your organization's security requirements.</span></span> <span data-ttu-id="dff3b-107">Microsoft 365 提供了多种安全功能;但是, 如果您的组织在本地和云中有内容和应用程序 (如混合云部署的情况), 则可以考虑添加 SIEM 服务器以实现额外保护。</span><span class="sxs-lookup"><span data-stu-id="dff3b-107">Microsoft 365 offers a variety of security features; however, if your organization has content and applications on premises and in the cloud (as in the case of a hybrid cloud deployment), you might consider adding a SIEM server for extra protection.</span></span> <span data-ttu-id="dff3b-108">或者, 如果您的组织具有特别严格的安全要求, 必须满足这些要求, 则可以考虑将 SIEM 服务器添加到您的环境中。</span><span class="sxs-lookup"><span data-stu-id="dff3b-108">Or, if your organization has particularly stringent security requirements you must meet, you might consider adding a SIEM server to your environment.</span></span>

## <a name="siem-server-integration-microsoft-365"></a><span data-ttu-id="dff3b-109">SIEM server 集成 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dff3b-109">SIEM server integration Microsoft 365</span></span>

<span data-ttu-id="dff3b-110">SIEM 服务器可以接收来自各种 Microsoft 365 服务和应用程序的数据。</span><span class="sxs-lookup"><span data-stu-id="dff3b-110">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="dff3b-111">下表列出了几个 Microsoft 365 服务和应用程序以及 SIEM 服务器输入, 以及在哪里可以了解有关 SIEM server 集成的更多信息。</span><span class="sxs-lookup"><span data-stu-id="dff3b-111">The following table lists several Microsoft 365 services and applications along with SIEM server inputs and where to go to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="dff3b-112">Microsoft 365 服务或应用程序</span><span class="sxs-lookup"><span data-stu-id="dff3b-112">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="dff3b-113">SIEM 服务器输入</span><span class="sxs-lookup"><span data-stu-id="dff3b-113">SIEM server inputs</span></span> | <span data-ttu-id="dff3b-114">要了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="dff3b-114">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="dff3b-115">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="dff3b-115">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md) <br/>   <span data-ttu-id="dff3b-116">或</span><span class="sxs-lookup"><span data-stu-id="dff3b-116">or</span></span>   <br/>[<span data-ttu-id="dff3b-117">Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="dff3b-117">Office 365 Threat Intelligence</span></span>](office-365-ti.md) | <span data-ttu-id="dff3b-118">审核日志</span><span class="sxs-lookup"><span data-stu-id="dff3b-118">Audit logs</span></span> | [<span data-ttu-id="dff3b-119">SIEM 与 Office 365 高级威胁防护的集成</span><span class="sxs-lookup"><span data-stu-id="dff3b-119">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="dff3b-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dff3b-120">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="dff3b-121">日志集成</span><span class="sxs-lookup"><span data-stu-id="dff3b-121">Log integration</span></span> | [<span data-ttu-id="dff3b-122">SIEM 与 Microsoft Cloud App Security 的集成</span><span class="sxs-lookup"><span data-stu-id="dff3b-122">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="dff3b-123">Office 365 云应用安全</span><span class="sxs-lookup"><span data-stu-id="dff3b-123">Office 365 Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="dff3b-124">日志集成</span><span class="sxs-lookup"><span data-stu-id="dff3b-124">Log integration</span></span> | [<span data-ttu-id="dff3b-125">将 SIEM 服务器与云应用安全集成</span><span class="sxs-lookup"><span data-stu-id="dff3b-125">Integrate your SIEM server with Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="dff3b-126">Windows Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="dff3b-126">Windows Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="dff3b-127">日志集成</span><span class="sxs-lookup"><span data-stu-id="dff3b-127">Log integration</span></span> | [<span data-ttu-id="dff3b-128">将警报拉入 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="dff3b-128">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| <span data-ttu-id="dff3b-129">[Azure 安全中心](https://docs.microsoft.com/azure/security-center/security-center-intro)(威胁防护和威胁检测)</span><span class="sxs-lookup"><span data-stu-id="dff3b-129">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Threat Protection and Threat Detection)</span></span> | <span data-ttu-id="dff3b-130">警报</span><span class="sxs-lookup"><span data-stu-id="dff3b-130">Alerts</span></span> | [<span data-ttu-id="dff3b-131">Azure 安全数据导出到 SIEM 配置-预览</span><span class="sxs-lookup"><span data-stu-id="dff3b-131">Azure Security data export to SIEM - Pipeline Configuration - Preview</span></span>](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [<span data-ttu-id="dff3b-132">Azure Active Directory Identity Protection</span><span class="sxs-lookup"><span data-stu-id="dff3b-132">Azure Active Directory Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | <span data-ttu-id="dff3b-133">审核日志</span><span class="sxs-lookup"><span data-stu-id="dff3b-133">Audit logs</span></span> | [<span data-ttu-id="dff3b-134">集成 Azure Active Directory 审核日志</span><span class="sxs-lookup"><span data-stu-id="dff3b-134">Integrate Azure Active Directory audit logs</span></span>](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [<span data-ttu-id="dff3b-135">Azure 高级威胁分析</span><span class="sxs-lookup"><span data-stu-id="dff3b-135">Azure Advanced Threat Analytics</span></span>](https://docs.microsoft.com/azure/security/azure-threat-detection) | <span data-ttu-id="dff3b-136">日志集成</span><span class="sxs-lookup"><span data-stu-id="dff3b-136">Log integration</span></span> | [<span data-ttu-id="dff3b-137">ATA SIEM 日志引用</span><span class="sxs-lookup"><span data-stu-id="dff3b-137">ATA SIEM log reference</span></span>](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="dff3b-138">必须打开审核日志记录</span><span class="sxs-lookup"><span data-stu-id="dff3b-138">Audit logging must be turned on</span></span>

<span data-ttu-id="dff3b-139">在配置 SIEM server 集成之前, 请确保审核日志记录已打开。</span><span class="sxs-lookup"><span data-stu-id="dff3b-139">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="dff3b-140">对于 SharePoint Online、OneDrive for business 和 Azure Active Directory,[审核日志记录在安全 _AMP_ 合规性中心中打开](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="dff3b-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="dff3b-141">对于 Exchange Online,[审核日志记录是使用 Windows PowerShell 打开](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)的。</span><span class="sxs-lookup"><span data-stu-id="dff3b-141">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="dff3b-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dff3b-142">See Also</span></span>

[<span data-ttu-id="dff3b-143">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="dff3b-143">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="dff3b-144">云应用测试实验室指南 (TLG) </span><span class="sxs-lookup"><span data-stu-id="dff3b-144">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)



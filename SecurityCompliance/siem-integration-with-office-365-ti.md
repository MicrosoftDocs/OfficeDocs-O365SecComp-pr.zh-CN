---
title: SIEM 与 Office 365 威胁智能和高级威胁防护的集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
description: 将组织的 SIEM 服务器与 office 365 的威胁智能和高级威胁防护与 office 365 活动管理 API 集成。
ms.openlocfilehash: cecfb3910520ddf535c50bbe4bccbf200ae8e121
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30212732"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a><span data-ttu-id="c1e3b-103">SIEM 与 Office 365 威胁智能和高级威胁防护的集成</span><span class="sxs-lookup"><span data-stu-id="c1e3b-103">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>

<span data-ttu-id="c1e3b-p101">如果您的组织使用的是安全事件和事件管理 (SIEM) 服务器, 则可以将 Office 365 威胁智能和高级威胁防护与您的 SIEM 服务器集成。SIEM 集成使您能够查看 SIEM 服务器报告中的信息, 如 Office 365 高级保护和威胁智能检测到的恶意软件。若要设置 SIEM 集成, 请使用[Office 365 活动管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="c1e3b-p101">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Threat Intelligence and Advanced Threat Protection with your SIEM server. SIEM integration enables you to view information, such as malware detected by Office 365 Advanced Protection and Threat Intelligence, in your SIEM server reports. To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="c1e3b-p102">Office 365 活动管理 API 检索组织的 Office 365 和 Azure Active Directory 活动日志中的用户、管理员、系统和策略操作以及事件的相关信息。[Office 365 高级威胁防护和威胁智能架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema)适用于威胁智能和/或高级威胁防护, 因此, 如果您的组织具有高级威胁防护而不是威胁情报 (反之亦然), 则可以仍对您的 SIEM 服务器集成使用相同的 API。</span><span class="sxs-lookup"><span data-stu-id="c1e3b-p102">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs. The [Office 365 Advanced Threat Protection and Threat Intelligence schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Threat Intelligence and/or Advanced Threat Protection, so if your organization has Advanced Threat Protection but not Threat Intelligence (or vice versa), you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="c1e3b-p103">SIEM 服务器或其他类似系统应轮询**审核。常规**工作负荷以访问检测事件。若要了解详细信息, 请参阅[Office 365 管理 api 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="c1e3b-p103">The SIEM server or other similar system should poll the **audit.general** workload to access detection events. To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c1e3b-111">您必须是 Office 365 全局管理员, 或者已为安全 & 合规中心分配安全管理员角色, 以便设置 SIEM 与 Office 365 高级威胁防护的集成。</span><span class="sxs-lookup"><span data-stu-id="c1e3b-111">You must be an Office 365 global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="c1e3b-p104">必须为你的 Office 365 环境启用审核日志记录。若要获取有关此功能的帮助, 请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="c1e3b-p104">Audit logging must be turned on for your Office 365 environment. To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c1e3b-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="c1e3b-114">Related topics</span></span>

[<span data-ttu-id="c1e3b-115">Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="c1e3b-115">Office 365 Threat Intelligence</span></span>](office-365-ti.md)

[<span data-ttu-id="c1e3b-116">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="c1e3b-116">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="c1e3b-117">Office 365 安全&amp;合规中心中的智能报告和见解</span><span class="sxs-lookup"><span data-stu-id="c1e3b-117">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="c1e3b-118">Office 365 安全&amp;合规中心中的权限</span><span class="sxs-lookup"><span data-stu-id="c1e3b-118">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  


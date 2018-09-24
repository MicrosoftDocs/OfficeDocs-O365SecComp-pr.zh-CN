---
title: 与 Office 365 威胁智能和高级威胁保护 SIEM 集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
description: 将您的组织 SIEM 服务器与 Office 365 威胁智能解决方案和使用 Office 365 活动管理 API 的高级威胁保护集成。
ms.openlocfilehash: 057d8ac101b96f37846ac751645934279d45dc88
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972254"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a><span data-ttu-id="b73e2-103">与 Office 365 威胁智能和高级威胁保护 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="b73e2-103">SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection</span></span>

<span data-ttu-id="b73e2-p101">如果您的组织正在使用安全事件和事件管理 (SIEM) 服务器，您可以与 SIEM 服务器集成 Office 365 威胁智能和高级威胁保护。SIEM 集成，可以查看信息，如通过 Office 365 高级保护和威胁智能 SIEM server 报表中检测到恶意软件。若要设置 SIEM 集成，您可以使用[Office 365 活动管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="b73e2-p101">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Threat Intelligence and Advanced Threat Protection with your SIEM server. SIEM integration enables you to view information, such as malware detected by Office 365 Advanced Protection and Threat Intelligence, in your SIEM server reports. To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="b73e2-p102">Office 365 活动管理 API 检索贵组织的 Office 365 和 Azure Active Directory 活动日志用户、 管理、 系统和策略操作和事件的信息。[Office 365 高级威胁保护和威胁智能架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema)适用于威胁智能和/或高级威胁保护，因此如果您的组织具有高级威胁保护但不是威胁智能 （反之亦然），您可以仍将该相同的 API 用于您 SIEM 服务器集成。</span><span class="sxs-lookup"><span data-stu-id="b73e2-p102">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs. The [Office 365 Advanced Threat Protection and Threat Intelligence schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema) works with Threat Intelligence and/or Advanced Threat Protection, so if your organization has Advanced Threat Protection but not Threat Intelligence (or vice versa), you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="b73e2-p103">SIEM 服务器或其他类似系统应轮询访问检测事件**audit.general**工作负荷。若要了解更多信息，请参见[开始使用 Office 365 管理 Api](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="b73e2-p103">The SIEM server or other similar system should poll the **audit.general** workload to access detection events. To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b73e2-111">您必须是 Office 365 全局管理员或具有安全管理员角色分配中安全性和合规性中心设置与 Office 365 威胁智能和高级威胁保护 SIEM 集成。</span><span class="sxs-lookup"><span data-stu-id="b73e2-111">You must be an Office 365 global administrator or have the security administrator role assigned in the Security & Compliance Center to set up SIEM integration with Office 365 Threat Intelligence and Advanced Threat Protection.</span></span><br/><span data-ttu-id="b73e2-p104">必须为您的 Office 365 环境开启审核日志记录。要获取与此帮助，请参阅[打开 Office 365 审核日志搜索打开或关闭](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="b73e2-p104">Audit logging must be turned on for your Office 365 environment. To get help with this, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b73e2-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="b73e2-114">Related topics</span></span>

[<span data-ttu-id="b73e2-115">Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="b73e2-115">Office 365 Threat Intelligence</span></span>](office-365-ti.md)

[<span data-ttu-id="b73e2-116">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="b73e2-116">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="b73e2-117">智能报告和 Office 365 安全性见解&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="b73e2-117">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="b73e2-118">Office 365 安全性权限&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="b73e2-118">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  


---
title: Office 365 安全与合规中心中的报告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: '使用 Office 365 安全 & 合规中心获取您的 SharePoint online 和 Exchange online 组织的各种报告, 以及 Azure Active Directory 报告。  '
ms.openlocfilehash: 5f3e510aaacd82095cf502acd5609a204e738bd3
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223541"
---
# <a name="reports-in-the-office-365-security--compliance-center"></a><span data-ttu-id="898a8-103">Office 365 安全与合规中心中的报告</span><span class="sxs-lookup"><span data-stu-id="898a8-103">Reports in the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="898a8-p101">您可以使用 Office 365 Security & 合规中心中的 "**查看报告**" 页快速访问您的 SharePoint online 和 Exchange Online 组织的审核报告。您还可以从 "**查看报告**" 页访问 azure Active Directory (AD) 用户登录报告、用户活动报告和 azure AD 审核日志。这是因为付费 Office 365 订阅包括对 Microsoft Azure 的免费订阅。首次尝试访问这些 Azure 报告时, 您必须完成一次性注册过程。</span><span class="sxs-lookup"><span data-stu-id="898a8-p101">You can use the **View reports** page in the Office 365 Security & Compliance Center to quickly access audit reports for your SharePoint Online and Exchange Online organizations. You can also access Azure Active Directory (AD) user sign-in reports, user activity reports, and the Azure AD audit log from the **View reports** page. This is because your paid Office 365 subscription includes a free subscription to Microsoft Azure. The first time that you try to access these Azure reports, you will have to complete a one-time registration process.</span></span> 
  
> [!TIP]
> <span data-ttu-id="898a8-108">若要查看有关 office 365 组织中的活动的其他报告, 请参阅[office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。</span><span class="sxs-lookup"><span data-stu-id="898a8-108">To view additional reports about activity in your Office 365 organization, see [Activity Reports in the Office 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).</span></span> 
  
 <span data-ttu-id="898a8-109">**开始之前**</span><span class="sxs-lookup"><span data-stu-id="898a8-109">**Before you begin**</span></span>
  
<span data-ttu-id="898a8-110">您需要以下权限以查看安全 & 合规性中心中的报告。</span><span class="sxs-lookup"><span data-stu-id="898a8-110">You need the following permissions to view reports in the Security & Compliance Center.</span></span>
  
- <span data-ttu-id="898a8-p102">您必须在 Exchange 管理中心 (EAC) 中分配 "安全读者" 角色, 才能在 Security & 合规性中心查看报告。默认情况下, 将此角色分配给 EAC 中的 "组织管理" 和 "安全读者" 角色组。</span><span class="sxs-lookup"><span data-stu-id="898a8-p102">You have to be assigned the Security Reader role in the Exchange admin center (EAC) to view reports in the Security & Compliance Center. By default, this role is assigned to the Organization Management and Security Reader role groups in the EAC.</span></span>
    
- <span data-ttu-id="898a8-p103">必须在 security & 合规性中心中向您分配 "仅查看 dlp 合规性管理" 角色, 才能在 security & 合规性中心中查看 DLP 报告。默认情况下, 将此角色分配给安全 & 合规中心中的合规性管理员、组织管理、安全管理员和安全读者角色组。</span><span class="sxs-lookup"><span data-stu-id="898a8-p103">You have to be assigned the View-Only DLP Compliance Management role in the Security & Compliance Center to view DLP reports in the Security & Compliance Center. By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="898a8-p104">此外, 您还必须分配到 eac 中的 "仅查看收件人" 角色, 才能查看 eac 中的 DLP 报告。默认情况下, 将此角色分配给 EAC 中的合规性管理、组织管理和仅查看组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="898a8-p104">Additionally, you have to be assigned the View-Only Recipients role in the EAC to view DLP reports in the EAC. By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the EAC.</span></span>
  
 <span data-ttu-id="898a8-117">**若要打开 Security & 合规中心中的 "查看报告" 页, 请执行以下操作:**</span><span class="sxs-lookup"><span data-stu-id="898a8-117">**To open the View reports page in the Security & Compliance Center:**</span></span>
  
1. <span data-ttu-id="898a8-118">转到 [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)。</span><span class="sxs-lookup"><span data-stu-id="898a8-118">Go to [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).</span></span>
    
2. <span data-ttu-id="898a8-119">使用 office 365 组织中的用户帐户的凭据登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="898a8-119">Sign in to Office 365 using the credentials for a user account in your Office 365 organization.</span></span>
    
<span data-ttu-id="898a8-120">在 "**查看报告**" 页上, 您可以查看以下报告类型:</span><span class="sxs-lookup"><span data-stu-id="898a8-120">On the **View reports** page, you can view the following types of reports:</span></span> 
  
- [<span data-ttu-id="898a8-121">EOP 中的审核报告</span><span class="sxs-lookup"><span data-stu-id="898a8-121">Auditing reports</span></span>](#auditing-reports)
- [<span data-ttu-id="898a8-122">监察审核报告</span><span class="sxs-lookup"><span data-stu-id="898a8-122">Supervisory review report</span></span>](#supervisory-review-report)
- [<span data-ttu-id="898a8-123">数据丢失防护报告</span><span class="sxs-lookup"><span data-stu-id="898a8-123">Data loss prevention reports</span></span>](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a><span data-ttu-id="898a8-124">审核报告</span><span class="sxs-lookup"><span data-stu-id="898a8-124">Auditing reports</span></span>

<span data-ttu-id="898a8-125">下表介绍了 Security & 合规性中心的 "**查看报告**" 页上的 "**审核**" 部分中的报告。</span><span class="sxs-lookup"><span data-stu-id="898a8-125">The following table describes the reports in the **Auditing** section on the **View reports** page in the Security & Compliance Center.</span></span> 
  
|<span data-ttu-id="898a8-126">**报表**</span><span class="sxs-lookup"><span data-stu-id="898a8-126">**Report**</span></span>|<span data-ttu-id="898a8-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="898a8-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="898a8-128">**Office 365 审核日志报告**</span><span class="sxs-lookup"><span data-stu-id="898a8-128">**Office 365 audit log report**</span></span> <br/> |<span data-ttu-id="898a8-p105">您可以在 office 365 组织中搜索用户和管理员活动的 office 365 审核日志。此报告包含 Exchange online、SharePoint online、OneDrive for business 和 Azure Active Directory (这是 Office 365 的目录服务) 中的 "用户和管理员活动" 条目。有关详细信息, 请参阅[在 Office 365 安全 & 合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="898a8-p105">You can search the Office 365 audit log for user and admin activity in your Office 365 organization. The report contains entries user and admin activity in Exchange Online, SharePoint Online, OneDrive for Business, and Azure Active Directory, which is the directory service for Office 365. For more information, see [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).  </span></span><br/> |
|<span data-ttu-id="898a8-132">**Azure AD 报告**</span><span class="sxs-lookup"><span data-stu-id="898a8-132">**Azure AD reports**</span></span> <br/> |<span data-ttu-id="898a8-p106">若要查找 Office 365 组织中的异常或可疑登录活动, 您可以使用 Microsoft Azure 中的登录和活动报告。您还可以在 Azure AD 审核日志中查看事件。若要在 Azure 中查看报告, 只需单击 "**查看 azure AD 报告**"。有关详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="898a8-p106">To look for unusual or suspicious sign-in activity in your Office 365 organization, you can use sign-in and activity reports in Microsoft Azure. You can also view events in the Azure AD audit log. To view reports in Azure, just click **View Azure AD reports**. For more information, see: </span></span><br/><br/><span data-ttu-id="898a8-137">[在 Office 365 中使用免费的 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="898a8-137">[Use your free Azure Active Directory subscription in Office 365](use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <br/> <span data-ttu-id="898a8-138">[查看您的访问和使用情况报告](http://go.microsoft.com/fwlink/p/?LinkId=506902)。</span><span class="sxs-lookup"><span data-stu-id="898a8-138">[View your access and usage reports](http://go.microsoft.com/fwlink/p/?LinkId=506902).</span></span>  <br/> |
|<span data-ttu-id="898a8-139">**Exchange 审核报告**</span><span class="sxs-lookup"><span data-stu-id="898a8-139">**Exchange audit reports**</span></span> <br/> | <span data-ttu-id="898a8-p107">您可以使用 Office 365 中的审核功能来跟踪组织管理员对 Exchange Online 配置所做的更改。由 Microsoft 数据中心管理员或委派管理员对 Exchange Online 组织所做的更改也会记录下来。对于 Exchange Online, 管理员审核日志记录在默认情况下处于启用状态, 因此您无需执行任何操作即可将其打开。Exchange Online 还提供了邮箱审核日志记录功能, 使您能够跟踪邮箱所有者以外的邮箱对邮箱的访问。对于要跟踪非所有者访问的每个邮箱, 您必须启用邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="898a8-p107">You can use the auditing functionality in Office 365 to track changes made to your Exchange Online configuration by your organization's administrators. Changes made to your Exchange Online organization by a Microsoft data center administrator or by a delegated administrator are also logged. For Exchange Online, administrator audit logging is enabled by default, so you don't have to do anything to turn it on. Exchange Online also provides mailbox audit logging to let you track access to mailboxes by someone other than the mailbox owner. You have to enable mailbox audit logging for each mailbox that you want to track non-owner access.  </span></span><br/>  <span data-ttu-id="898a8-p108">对于管理员和邮箱审核日志记录, 您可以运行审核报告查看审核日志条目。您还可以导出邮箱和管理员审核日志, 这些日志将在附加到电子邮件的 XML 文件中的24小时内发送给您。</span><span class="sxs-lookup"><span data-stu-id="898a8-p108">For both admin and mailbox audit logging, you can run audit reports to view the audit log entries. You can also export mailbox and admin audit logs, which are sent to you within 24 hours in an XML file that is attached to email message. </span></span><br/><br/><span data-ttu-id="898a8-147">有关导出审核日志的详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="898a8-147">For more information about exporting audit logs, see:</span></span>  <br/><br/> [<span data-ttu-id="898a8-148">导出邮箱审核日志</span><span class="sxs-lookup"><span data-stu-id="898a8-148">Export mailbox audit logs</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [<span data-ttu-id="898a8-149">查看和导出数据中心管理员审核日志</span><span class="sxs-lookup"><span data-stu-id="898a8-149">View and export the datacenter admin audit log</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [<span data-ttu-id="898a8-150">搜索角色组更改或管理员审核日志</span><span class="sxs-lookup"><span data-stu-id="898a8-150">Search the role group changes or administrator audit logs</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   <span data-ttu-id="898a8-151">[Exchange 审核报告](http://go.microsoft.com/fwlink/p/?LinkID=395232)。</span><span class="sxs-lookup"><span data-stu-id="898a8-151">[Exchange auditing reports](http://go.microsoft.com/fwlink/p/?LinkID=395232).</span></span>  <br/> |
   
## <a name="supervisory-review-report"></a><span data-ttu-id="898a8-152">监察审核报告</span><span class="sxs-lookup"><span data-stu-id="898a8-152">Supervisory review report</span></span>

<span data-ttu-id="898a8-p109">使用监管审核报告, 您可以查看组织中所有监管审核策略的状态。有关详细信息, 请参阅为[您的组织配置监管审核策略](configure-supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="898a8-p109">With the supervisory review report, you can see the status of all the supervisory review policies in your organization. For more information, see [Configure supervisory review policies for your organization](configure-supervision-policies.md).</span></span>
  
## <a name="data-loss-prevention-reports"></a><span data-ttu-id="898a8-155">数据丢失防护报告</span><span class="sxs-lookup"><span data-stu-id="898a8-155">Data loss prevention reports</span></span>

<span data-ttu-id="898a8-p110">数据丢失防护 (DLP) 报告包含有关已应用于内容的 DLP 策略和规则的信息, 这些信息包含 Office 365 组织中的敏感数据。您还可以将报告配置为显示基于您的 dlp 策略和规则的 dlp 操作的相关信息。有关详细信息, 请参阅[查看报告以了解数据丢失防护](view-the-dlp-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="898a8-p110">Data loss prevention (DLP) reports contain information about the DLP policies and rules that have been applied to content contain sensitive data in your Office 365 organization. You can also configure the report to display information about DLP actions that were based on your DLP policy and rules. For more information, see [View the report for data loss prevention](view-the-dlp-reports.md).</span></span>

---
title: Reports in Office 365 安全性&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/1/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: '使用 Office 365 安全性&amp;合规性中心以获取 SharePoint Online 和 Exchange Online 组织的各种报告以及 Azure Active Directory 报告。  '
ms.openlocfilehash: 0b633583e14a18c7cf579d10462cf41714397812
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524884"
---
# <a name="reports-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="a01e4-103">Reports in Office 365 安全性&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="a01e4-103">Reports in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="a01e4-p101">在 Office 365 安全性，可以使用**查看报告**页上&amp;合规性中心，以快速访问 SharePoint Online 和 Exchange Online 组织的审核报告。您还可以访问 Azure Active Directory (AD) 用户注册报告，用户活动报告，并从**查看报告**页上的 Azure AD 审核日志。这是因为您的付费的 Office 365 订阅包括对 Microsoft Azure 的免费订阅。第一次尝试访问这些 Azure 报告，您将需要完成一次性注册过程。</span><span class="sxs-lookup"><span data-stu-id="a01e4-p101">You can use the **View reports** page in the Office 365 Security &amp; Compliance Center to quickly access audit reports for your SharePoint Online and Exchange Online organizations. You can also access Azure Active Directory (AD) user sign-in reports, user activity reports, and the Azure AD audit log from the **View reports** page. This is because your paid Office 365 subscription includes a free subscription to Microsoft Azure. The first time that you try to access these Azure reports, you will have to complete a one-time registration process.</span></span> 
  
> [!TIP]
> <span data-ttu-id="a01e4-108">若要在 Office 365 组织中查看有关活动的其他报告，请参阅[Office 365 管理中心中的活动报告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)。</span><span class="sxs-lookup"><span data-stu-id="a01e4-108">To view additional reports about activity in your Office 365 organization, see [Activity Reports in the Office 365 admin center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263).</span></span> 
  
 <span data-ttu-id="a01e4-109">**开始之前**</span><span class="sxs-lookup"><span data-stu-id="a01e4-109">**Before you begin**</span></span>
  
<span data-ttu-id="a01e4-110">您需要以下权限才能安全中查看报告&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="a01e4-110">You need the following permissions to view reports in the Security &amp; Compliance Center.</span></span>
  
- <span data-ttu-id="a01e4-p102">您需要分配 Exchange 管理员中心 (EAC) 安全中查看报告中的安全读者角色&amp;合规性中心。默认情况下，此角色分配给在 EAC 中的组织管理和安全读者角色组。</span><span class="sxs-lookup"><span data-stu-id="a01e4-p102">You have to be assigned the Security Reader role in the Exchange admin center (EAC) to view reports in the Security &amp; Compliance Center. By default, this role is assigned to the Organization Management and Security Reader role groups in the EAC.</span></span>
    
- <span data-ttu-id="a01e4-p103">您必须为其分配安全中的 DLP 合规性管理角色&amp;合规性中心安全中查看 DLP 报告 （和 DLP 策略）&amp;合规性中心。默认情况下，此角色分配给安全中的合规性管理员、 组织管理和安全管理员角色组&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="a01e4-p103">You have to be assigned the DLP Compliance Management role in the Security &amp; Compliance Center to view DLP reports (and DLP policies) in the Security &amp; Compliance Center. By default, this role is assigned to the Compliance Administrator, Organization Management, and Security Administrator role groups in the Security &amp; Compliance Center.</span></span>
    
<span data-ttu-id="a01e4-p104">此外，您将需要在 EAC 中查看 DLP 报告 （和 DLP 策略） 的数据丢失防护角色分配在 EAC 中。默认情况下，此角色分配给在 EAC 中的合规性管理和组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="a01e4-p104">Additionally, you would have to be assigned the Data Loss Prevention role in the EAC to view DLP reports (and DLP policies) in the EAC. By default, this role is assigned to the Compliance Management and Organization Management role groups in the EAC.</span></span>
  
 <span data-ttu-id="a01e4-117">**在安全中打开查看报告页&amp;合规性中心：**</span><span class="sxs-lookup"><span data-stu-id="a01e4-117">**To open the View reports page in the Security &amp; Compliance Center:**</span></span>
  
1. <span data-ttu-id="a01e4-118">转到[https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports)。</span><span class="sxs-lookup"><span data-stu-id="a01e4-118">Go to [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).</span></span>
    
2. <span data-ttu-id="a01e4-119">登录到 Office 365 使用的 Office 365 组织中的用户帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="a01e4-119">Sign in to Office 365 using the credentials for a user account in your Office 365 organization.</span></span>
    
<span data-ttu-id="a01e4-120">在**查看报告**页上，您可以查看以下类型的报告：</span><span class="sxs-lookup"><span data-stu-id="a01e4-120">On the **View reports** page, you can view the following types of reports:</span></span> 
  
- [<span data-ttu-id="a01e4-121">EOP 中的审核报告</span><span class="sxs-lookup"><span data-stu-id="a01e4-121">Auditing reports</span></span>](#auditing-reports)
- [<span data-ttu-id="a01e4-122">监督审阅报告</span><span class="sxs-lookup"><span data-stu-id="a01e4-122">Supervisory review report</span></span>](#supervisory-review-report)
- [<span data-ttu-id="a01e4-123">数据丢失防护报告</span><span class="sxs-lookup"><span data-stu-id="a01e4-123">Data loss prevention reports</span></span>](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a><span data-ttu-id="a01e4-124">审核报告</span><span class="sxs-lookup"><span data-stu-id="a01e4-124">Auditing reports</span></span>

<span data-ttu-id="a01e4-125">下表介绍在安全中的**查看报告**页上的**审核**部分报告&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="a01e4-125">The following table describes the reports in the **Auditing** section on the **View reports** page in the Security &amp; Compliance Center.</span></span> 
  
|<span data-ttu-id="a01e4-126">**报告**</span><span class="sxs-lookup"><span data-stu-id="a01e4-126">**Report**</span></span>|<span data-ttu-id="a01e4-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="a01e4-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a01e4-128">**Office 365 审核日志报告**</span><span class="sxs-lookup"><span data-stu-id="a01e4-128">**Office 365 audit log report**</span></span> <br/> |<span data-ttu-id="a01e4-p105">您可以在 Office 365 组织中搜索用户和管理活动的 Office 365 审核日志。报告中包含条目用户和管理活动中 Exchange Online、 SharePoint Online 的 OneDrive for Business 和 Azure Active Directory，这是 Office 365 的目录服务。有关详细信息，请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="a01e4-p105">You can search the Office 365 audit log for user and admin activity in your Office 365 organization. The report contains entries user and admin activity in Exchange Online, SharePoint Online, OneDrive for Business, and Azure Active Directory, which is the directory service for Office 365. For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).  </span></span><br/> |
|<span data-ttu-id="a01e4-132">**Azure AD 报告**</span><span class="sxs-lookup"><span data-stu-id="a01e4-132">**Azure AD reports**</span></span> <br/> |<span data-ttu-id="a01e4-p106">若要查找的不寻常或可疑登录活动 Office 365 组织中，可以使用登录和活动 Microsoft Azure 中的报告。您还可以查看事件中的 Azure AD 审核日志。若要在 Azure 中查看报告，只需单击**查看 Azure AD 的报告**。有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a01e4-p106">To look for unusual or suspicious sign-in activity in your Office 365 organization, you can use sign-in and activity reports in Microsoft Azure. You can also view events in the Azure AD audit log. To view reports in Azure, just click **View Azure AD reports**. For more information, see: </span></span><br/><br/><span data-ttu-id="a01e4-137">[使用您在 Office 365 中可用的 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a01e4-137">[Use your free Azure Active Directory subscription in Office 365](use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <br/> <span data-ttu-id="a01e4-138">[查看您访问和使用情况的报告](http://go.microsoft.com/fwlink/p/?LinkId=506902)。</span><span class="sxs-lookup"><span data-stu-id="a01e4-138">[View your access and usage reports](http://go.microsoft.com/fwlink/p/?LinkId=506902).</span></span>  <br/> |
|<span data-ttu-id="a01e4-139">**Exchange 审核报告**</span><span class="sxs-lookup"><span data-stu-id="a01e4-139">**Exchange audit reports**</span></span> <br/> | <span data-ttu-id="a01e4-p107">可以使用 Office 365 中的审核功能跟踪对 Exchange Online 配置组织的管理员所做的更改。此外会记录由 Microsoft 数据中心管理员或委派管理员对 Exchange Online 组织所做更改。Exchange online，管理员审核日志记录默认情况下，启用，所以您无需执行任何操作即可将其打开。Exchange Online 还提供了邮箱审核日志记录，让您通过邮箱所有者以外的某个人跟踪对邮箱的访问。您必须启用邮箱审核日志记录要跟踪非所有者访问的每个邮箱。</span><span class="sxs-lookup"><span data-stu-id="a01e4-p107">You can use the auditing functionality in Office 365 to track changes made to your Exchange Online configuration by your organization's administrators. Changes made to your Exchange Online organization by a Microsoft data center administrator or by a delegated administrator are also logged. For Exchange Online, administrator audit logging is enabled by default, so you don't have to do anything to turn it on. Exchange Online also provides mailbox audit logging to let you track access to mailboxes by someone other than the mailbox owner. You have to enable mailbox audit logging for each mailbox that you want to track non-owner access.  </span></span><br/>  <span data-ttu-id="a01e4-p108">管理和邮箱审核日志记录，您可以运行审核报告，来查看审核日志条目。您还可以导出邮箱和管理员审核日志，发送到您在 24 小时内附加到电子邮件的 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="a01e4-p108">For both admin and mailbox audit logging, you can run audit reports to view the audit log entries. You can also export mailbox and admin audit logs, which are sent to you within 24 hours in an XML file that is attached to email message. </span></span><br/><br/><span data-ttu-id="a01e4-147">有关导出审核日志的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a01e4-147">For more information about exporting audit logs, see:</span></span>  <br/><br/> [<span data-ttu-id="a01e4-148">导出邮箱审核日志</span><span class="sxs-lookup"><span data-stu-id="a01e4-148">Export mailbox audit logs</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [<span data-ttu-id="a01e4-149">查看和导出数据中心管理员审核日志</span><span class="sxs-lookup"><span data-stu-id="a01e4-149">View and export the datacenter admin audit log</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [<span data-ttu-id="a01e4-150">搜索角色组更改或管理员审核日志</span><span class="sxs-lookup"><span data-stu-id="a01e4-150">Search the role group changes or administrator audit logs</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   <span data-ttu-id="a01e4-151">[Exchange 审核报告](http://go.microsoft.com/fwlink/p/?LinkID=395232)。</span><span class="sxs-lookup"><span data-stu-id="a01e4-151">[Exchange auditing reports](http://go.microsoft.com/fwlink/p/?LinkID=395232).</span></span>  <br/> |
   
## <a name="supervisory-review-report"></a><span data-ttu-id="a01e4-152">监督审阅报告</span><span class="sxs-lookup"><span data-stu-id="a01e4-152">Supervisory review report</span></span>

<span data-ttu-id="a01e4-p109">使用监督查看报表，您可以在组织中查看所有监督审阅策略的状态。有关详细信息，请参阅[Configure 监督查看为您的组织的策略](configure-supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a01e4-p109">With the supervisory review report, you can see the status of all the supervisory review policies in your organization. For more information, see [Configure supervisory review policies for your organization](configure-supervision-policies.md).</span></span>
  
## <a name="data-loss-prevention-reports"></a><span data-ttu-id="a01e4-155">数据丢失防护报告</span><span class="sxs-lookup"><span data-stu-id="a01e4-155">Data loss prevention reports</span></span>

<span data-ttu-id="a01e4-p110">数据丢失防护 (DLP) 报告包含有关 DLP 策略的信息，并且已应用于内容的规则包含 Office 365 组织中的敏感数据。您还可以配置报表以显示有关已根据您的 DLP 策略和规则的 DLP 操作的信息。有关详细信息，请参阅[查看的报告的数据丢失防护](view-the-dlp-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="a01e4-p110">Data loss prevention (DLP) reports contain information about the DLP policies and rules that have been applied to content contain sensitive data in your Office 365 organization. You can also configure the report to display information about DLP actions that were based on your DLP policy and rules. For more information, see [View the report for data loss prevention](view-the-dlp-reports.md).</span></span>

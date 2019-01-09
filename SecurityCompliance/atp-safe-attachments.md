---
title: Office 365 ATP 安全附件
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 01/08/2019
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
description: 安全附件功能提供电子邮件附件的时间的单击的验证。使用安全附件组织防止恶意文件人员发送或接收电子邮件中。
ms.openlocfilehash: 85c1ec3e0126a155f863b9fef9ddb36b13d0b3fb
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769836"
---
# <a name="office-365-atp-safe-attachments"></a><span data-ttu-id="586f5-104">Office 365 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="586f5-104">Office 365 ATP Safe Attachments</span></span>

## <a name="overview-of-office-365-atp-safe-attachments"></a><span data-ttu-id="586f5-105">Office 365 ATP 安全附件的概述</span><span class="sxs-lookup"><span data-stu-id="586f5-105">Overview of Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="586f5-p102">ATP （以及[ATP 安全链接](atp-safe-links.md)） 的安全附件是[Office 365 高级威胁保护](office-365-atp.md)(ATP) 的一部分。ATP 安全附件功能将查看是否恶意，电子邮件附件，然后执行操作以保护您的组织。ATP 安全附件功能保护您的组织根据您的 Office 365 全局或安全管理员设置的[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="586f5-p102">ATP Safe Attachments (along with [ATP Safe Links](atp-safe-links.md)) is part of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). The ATP Safe Attachments feature checks to see if email attachments are malicious, and then takes action to protect your organization. The ATP Safe Attachments feature protects your organization according to [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) that are set by your Office 365 global or security administrators.</span></span> 
  
<span data-ttu-id="586f5-p103">最近，ATP 保护已延长至文件在 SharePoint Online、 OneDrive for Business 和 Microsoft 团队。若要了解详细信息，请参阅[Office 365 高级威胁 Protection for SharePoint、 OneDrive 和 Microsoft 团队](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="586f5-p103">Recently, ATP protection has been extended to files in SharePoint Online, OneDrive for Business, and Microsoft Teams. To learn more, see [Office 365 Advanced Threat Protection for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>
       
## <a name="how-it-works"></a><span data-ttu-id="586f5-111">如何工作</span><span class="sxs-lookup"><span data-stu-id="586f5-111">How it works</span></span>

<span data-ttu-id="586f5-p104">ATP 安全附件功能检查您的组织中的人员的电子邮件附件。时 ATP 安全附件策略已就绪某人覆盖策略在 Office 365 中查看其电子邮件，则检查其电子邮件附件，并采取相应的操作，基于您 ATP 安全附件策略。根据您的策略定义的方式，人员可以继续工作，而不会知道他们发送恶意文件。</span><span class="sxs-lookup"><span data-stu-id="586f5-p104">The ATP Safe Attachments feature checks email attachments for people in your organization. When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies. Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="586f5-115">下面是在工作场所 ATP 安全附件的两个示例。</span><span class="sxs-lookup"><span data-stu-id="586f5-115">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="586f5-p105">**示例 1： 通过电子邮件附件**假设李接收包含附件的电子邮件。不明显到李是否附件安全或实际上包含恶意软件旨在窃取李的用户凭据。李的组织中的安全管理员定义的 ATP 安全附件策略几天前。使用 ATP 安全附件功能，电子邮件附件是打开和李获得它之前测试虚拟环境中。如果附件确定恶意，将自动删除。如果附件是安全的它将打开预期李单击它时。</span><span class="sxs-lookup"><span data-stu-id="586f5-p105">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment. It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials. In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago. With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it. If the attachment is determined to be malicious, it will be removed automatically. If the attachment is safe, it will open as expected when Lee clicks on it.</span></span> 
    
- <span data-ttu-id="586f5-p106">**示例 2: SharePoint Online 中的文件**假设 Jean 收到的文件上载到 SharePoint Online 中的库。Jean 与工作组、 的其余部分不知道该文件实际恶意共享文件的链接。幸运的是， [SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)检测到恶意文件，并阻止。更高版本，几天 Chris 转打开文档。尽管 Chris 可以看到该文件存在，Chris 无法打开或其，它可防止恶意文件 Chris 的计算机和其他人共享。</span><span class="sxs-lookup"><span data-stu-id="586f5-p106">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online. Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious. Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it. A few days later, Chris goes to open the document. Although Chris can see the file is there, Chris cannot open or share it, which prevents Chris's computer and others from the malicious file.</span></span> 
    
<span data-ttu-id="586f5-p107">ATP 安全附件扫描考虑放置在 Office 365 数据所在的同一区域中。有关数据中心地理区域的详细信息，请参阅[其中是位于数据？](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="586f5-p107">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides. For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

<span data-ttu-id="586f5-p108">ATP 安全附件策略可以应用到特定的某个人或组织中的组或整个域。此外，可以配置 ATP 安全附件策略用于占位符附件时正在被扫描实际附件。若要了解详细信息，请参阅**[设置 Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)**。</span><span class="sxs-lookup"><span data-stu-id="586f5-p108">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain. In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned. To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span> 
  
## <a name="how-to-get-atp-safe-attachments"></a><span data-ttu-id="586f5-132">如何获取 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="586f5-132">How to get ATP Safe Attachments</span></span>

<span data-ttu-id="586f5-p109">ATP 安全附件功能是[Office 365 高级威胁保护](office-365-atp.md)的一部分。ATP 安全附件功能适用时：</span><span class="sxs-lookup"><span data-stu-id="586f5-p109">The ATP Safe Attachments feature is part of [Office 365 Advanced Threat Protection](office-365-atp.md). The ATP Safe Attachments features apply when:</span></span>
  
- <span data-ttu-id="586f5-p110">ATP 安全附件策略设置。（请参阅[Set up Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)）。</span><span class="sxs-lookup"><span data-stu-id="586f5-p110">ATP Safe Attachments policies are set up. (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md).)</span></span>
    
- <span data-ttu-id="586f5-p111">用户已登录到 Office 365 使用其工作或学校帐户。（请参阅[登录到 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。</span><span class="sxs-lookup"><span data-stu-id="586f5-p111">Users have signed into Office 365 using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)</span></span>
    
## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a><span data-ttu-id="586f5-139">如何知道 ATP 安全附件保护是否就地</span><span class="sxs-lookup"><span data-stu-id="586f5-139">How to know if ATP Safe Attachments protection is in place</span></span>

<span data-ttu-id="586f5-140">请参阅如何使用服务一个好方法是通过[查看高级威胁保护报告](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="586f5-140">One good way to see how the service is working is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span>


<span data-ttu-id="586f5-141">为了 ATP 安全附件保护，以准备就绪，必须定义[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="586f5-141">[ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) must be defined in order for ATP Safe Attachments protection to be in place.</span></span>   
  
<span data-ttu-id="586f5-p112">下表介绍了一些示例方案。在所有这些情况下，我们假定组织具有包含高级威胁保护的 Office 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="586f5-p112">The following table describes some example scenarios. In all of these cases, we assume the organization has an Office 365 subscription that includes Advanced Threat Protection.</span></span>
  
|<span data-ttu-id="586f5-144">**示例应用场景**</span><span class="sxs-lookup"><span data-stu-id="586f5-144">**Example scenario**</span></span>|<span data-ttu-id="586f5-145">**ATP 安全附件保护不适用于这种情况下？**</span><span class="sxs-lookup"><span data-stu-id="586f5-145">**Does ATP Safe Attachments protection apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="586f5-146">Pat 组织具有 Office 365 企业 E5，但没有人具有尚未为 ATP 安全附件定义的任何策略。</span><span class="sxs-lookup"><span data-stu-id="586f5-146">Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP Safe Attachments yet.</span></span>  <br/> |<span data-ttu-id="586f5-p113">不。尽管功能可用，但至少一个 ATP 安全附件策略必须定义 ATP 安全附件保护，以准备就绪的顺序。</span><span class="sxs-lookup"><span data-stu-id="586f5-p113">No. Although the feature is available, at least one ATP Safe Attachments policy must be defined in order for ATP Safe Attachments protection to be in place.</span></span>  <br/> |
|<span data-ttu-id="586f5-p114">李是 contoso 销售部的员工。李的组织仅财务人员应用于的位置中具有 ATP 安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="586f5-p114">Lee is an employee in the sales department at Contoso. Lee's organization has an ATP Safe Attachments policy in place that applies to finance employees only.</span></span>  <br/> |<span data-ttu-id="586f5-p115">不。在这种情况下，财务人员将具有 ATP 安全附件保护，但其他员工，包括销售部门，将不是直到包括这些组的策略定义。</span><span class="sxs-lookup"><span data-stu-id="586f5-p115">No. In this case, finance employees would have ATP Safe Attachments protection, but other employees, including the sales department, would not until policies that include those groups are defined.</span></span>  <br/> |
|<span data-ttu-id="586f5-p116">昨天、 上 Jean 的组织的 Office 365 管理员设置适用于所有员工 ATP 安全附件策略。如今，前面 Jean 收到包含附件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="586f5-p116">Yesterday, an Office 365 administrator at Jean's organization set up an ATP Safe Attachments policy that applies to all employees. Earlier today, Jean received an email message that includes an attachment.</span></span>  <br/> |<span data-ttu-id="586f5-p117">是的。本示例中，Jean 具有许可证的高级威胁保护，并已定义 ATP 安全附件策略，其中包括 Jean。通常大约需要 30 分钟的新策略跨数据中心; 才会生效由于一天过后在这种情况下，该策略应实际上所示。</span><span class="sxs-lookup"><span data-stu-id="586f5-p117">Yes. In this example, Jean has a license for Advanced Threat Protection, and an ATP Safe Attachments policy that includes Jean has been defined. It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.</span></span>  <br/> |
|<span data-ttu-id="586f5-p118">Chris 的组织中的组织中的每个人的 ATP 安全附件策略与具有 Office 365 企业 E5。Chris 接收电子邮件有附件，并将转发组织之外的其他人的邮件。</span><span class="sxs-lookup"><span data-stu-id="586f5-p118">Chris's organization has Office 365 Enterprise E5 with ATP Safe Attachments policies in place for everyone in the organization. Chris receives an email that has an attachment, and forwards the message to others who are outside the organization.</span></span>  <br/> |<span data-ttu-id="586f5-p119">Chris 接收的邮件 ATP 安全附件保护。如果收件人的组织还就地具有 ATP 安全附件策略，则 Chris 转发的邮件将这些策略受转发的邮件到达时。</span><span class="sxs-lookup"><span data-stu-id="586f5-p119">ATP Safe Attachments protection is in place for messages that Chris receives. If the recipients' organizations also have ATP Safe Attachments policies in place, then the message that Chris forwards would be subject to those policies when the forwarded message arrives.</span></span>  <br/> |
|<span data-ttu-id="586f5-p120">晓明的组织在有 ATP 安全附件的策略和[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)开启。晓明假定 SharePoint Online 中的每个文件已扫描，可以安全地打开或下载。</span><span class="sxs-lookup"><span data-stu-id="586f5-p120">Jamie's organization has ATP Safe Attachments policies in place, and [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) has been turned on. Jamie assumes that every file in SharePoint Online has been scanned and is safe to open or download.  </span></span><br/> |<span data-ttu-id="586f5-p121">根据定义; 策略就地是 ATP 安全附件保护但是，这并不意味着 SharePoint Online 的 OneDrive for Business 或 Microsoft 团队中的每个文件进行扫描。（若要了解详细信息，请参阅[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)。）</span><span class="sxs-lookup"><span data-stu-id="586f5-p121">ATP Safe Attachments protection is in place according to the policies that are defined; however, this does not mean that every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams is scanned. (To learn more, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).)  </span></span><br/> |
   
## <a name="submitting-files-for-malware-analysis"></a><span data-ttu-id="586f5-166">提交的恶意软件分析的文件</span><span class="sxs-lookup"><span data-stu-id="586f5-166">Submitting files for malware analysis</span></span>

- <span data-ttu-id="586f5-167">如果您收到要询问 Microsoft 进行分析的文件，请访问[提交恶意软件分析的文件](https://aka.ms/wdsi/submit)。</span><span class="sxs-lookup"><span data-stu-id="586f5-167">If you receive a file that you want to ask Microsoft to analyze, visit [Submit a file for malware analysis](https://aka.ms/wdsi/submit).</span></span>

- <span data-ttu-id="586f5-168">如果您收到想要提交给 Microsoft 进行分析的电子邮件 （使用或不附件），使用[报告消息加载项](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="586f5-168">If you receive an email message (with or without an attachment) that you want to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>
  

---
title: Office 365 ATP 安全附件
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 08/03/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
description: 安全附件功能提供电子邮件附件的时间的单击的验证。使用安全附件组织防止恶意文件人员发送或接收电子邮件中。
ms.openlocfilehash: 0a28923bff8aa2cd987159edd3cad77ed42f80f4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525403"
---
# <a name="office-365-atp-safe-attachments"></a><span data-ttu-id="d6464-104">Office 365 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="d6464-104">Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="d6464-p102">ATP （以及[ATP 安全链接](atp-safe-links.md)） 的安全附件是[Office 365 高级威胁保护](office-365-atp.md)(ATP) 的一部分。ATP 安全附件功能将查看是否恶意，电子邮件附件，然后执行操作以保护您的组织。ATP 安全附件功能保护您的组织根据您的 Office 365 全局或安全管理员设置的[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d6464-p102">ATP Safe Attachments (along with [ATP Safe Links](atp-safe-links.md)) is part of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). The ATP Safe Attachments feature checks to see if email attachments are malicious, and then takes action to protect your organization. The ATP Safe Attachments feature protects your organization according to [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) that are set by your Office 365 global or security administrators.</span></span> 
  
<span data-ttu-id="d6464-p103">后期年 3 月 2018年中和下一步的几个星期开始，ATP 保护进行了扩展到文件中 SharePoint Online、 OneDrive for Business 和 Microsoft 团队。若要了解详细信息，请参阅[Office 365 高级威胁 Protection for SharePoint、 OneDrive 和 Microsoft 团队](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d6464-p103">Beginning in late March 2018 and over the next several weeks, ATP protection is being extended to files in SharePoint Online, OneDrive for Business, and Microsoft Teams. To learn more, see [Office 365 Advanced Threat Protection for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>
       
## <a name="how-it-works"></a><span data-ttu-id="d6464-110">如何工作</span><span class="sxs-lookup"><span data-stu-id="d6464-110">How it works</span></span>

<span data-ttu-id="d6464-p104">ATP 安全附件功能检查您的组织中的人员的电子邮件附件。时 ATP 安全附件策略已就绪某人覆盖策略在 Office 365 中查看其电子邮件，则检查其电子邮件附件，并采取相应的操作，基于您 ATP 安全附件策略。根据您的策略定义的方式，人员可以继续工作，而不会知道他们发送恶意文件。</span><span class="sxs-lookup"><span data-stu-id="d6464-p104">The ATP Safe Attachments feature checks email attachments for people in your organization. When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies. Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="d6464-114">下面是在工作场所 ATP 安全附件的两个示例。</span><span class="sxs-lookup"><span data-stu-id="d6464-114">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="d6464-p105">**示例 1： 通过电子邮件附件**假设李接收包含附件的电子邮件。不明显到李是否附件安全或实际上包含恶意软件旨在窃取李的用户凭据。李的组织中的安全管理员定义的 ATP 安全附件策略几天前。使用 ATP 安全附件功能，电子邮件附件是打开和李获得它之前测试虚拟环境中。如果附件确定恶意，将自动删除。如果附件是安全的它将打开预期李单击它时。</span><span class="sxs-lookup"><span data-stu-id="d6464-p105">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment. It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal the Lee's user credentials. In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago. With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it. If the attachment is determined to be malicious, it will be removed automatically. If the attachment is safe, it will open as expected when Lee clicks on it.</span></span> 
    
- <span data-ttu-id="d6464-p106">**示例 2: SharePoint Online 中的文件**假设 Jean 收到的文件上载到 SharePoint Online 中的库。Jean 与工作组、 的其余部分不知道该文件实际恶意共享文件的链接。幸运的是， [SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)检测到恶意文件，并阻止。更高版本，几天 Chris 转打开文档。尽管 Chris 可以看到该文件存在，Chris 无法打开或其，它可防止恶意文件 Chris 的计算机和其他人共享。</span><span class="sxs-lookup"><span data-stu-id="d6464-p106">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online. Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious. Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it. A few days later, Chris goes to open the document. Although Chris can see the file is there, Chris cannot open or share it, which prevents Chris's computer and others from the malicious file.</span></span> 
    
<span data-ttu-id="d6464-p107">ATP 安全附件策略可以应用到特定的某个人或组织中的组或整个域。若要了解详细信息，请参阅**[设置 Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)**。</span><span class="sxs-lookup"><span data-stu-id="d6464-p107">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain. To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span> 
  
## <a name="how-to-get-atp-safe-attachments"></a><span data-ttu-id="d6464-128">如何获取 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="d6464-128">How to get ATP Safe Attachments</span></span>

<span data-ttu-id="d6464-p108">ATP 安全附件功能是高级威胁保护，它包含 Office 365 企业 E5 的一部分。如果您的组织使用的另一个 Office 365 企业版订阅，高级威胁保护可以作为加载项进行购买。(作为全局管理员，在 Office 365 管理中心中，选择**帐单** \> **添加订阅**。)有关详细信息，请参阅[Office 365 平台服务说明： Office 365 安全性&amp;合规性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[购买或编辑企业的 Office 365 的加载项](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。</span><span class="sxs-lookup"><span data-stu-id="d6464-p108">The ATP Safe Attachments feature is part of Advanced Threat Protection, which is included in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Advanced Threat Protection can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span>
  
<span data-ttu-id="d6464-132">ATP 安全附件功能时适用：</span><span class="sxs-lookup"><span data-stu-id="d6464-132">The ATP Safe Attachments feature applies when:</span></span>
  
- <span data-ttu-id="d6464-p109">ATP 安全附件策略设置。（请参阅[Set up Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)）。</span><span class="sxs-lookup"><span data-stu-id="d6464-p109">ATP Safe Attachments policies are set up. (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md).)</span></span>
    
- <span data-ttu-id="d6464-p110">用户已登录到 Office 365 使用其工作或学校帐户。（请参阅[登录到 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。</span><span class="sxs-lookup"><span data-stu-id="d6464-p110">Users have signed into Office 365 using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)</span></span>
    
## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a><span data-ttu-id="d6464-137">如何知道 ATP 安全附件保护是否就地</span><span class="sxs-lookup"><span data-stu-id="d6464-137">How to know if ATP Safe Attachments protection is in place</span></span>

 <span data-ttu-id="d6464-138">为了 ATP 安全附件保护，以准备就绪，必须定义[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="d6464-138">[ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) must be defined in order for ATP Safe Attachments protection to be in place.</span></span> 
  
<span data-ttu-id="d6464-139">请参阅如何使用服务一个好方法是通过[查看高级威胁保护报告](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="d6464-139">One good way to see how the service is working is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span>
  
<span data-ttu-id="d6464-p111">此外下, 表介绍了一些示例方案。在所有这些情况下，我们假定组织具有 Office 365 企业 E5，其中包括高级威胁保护。</span><span class="sxs-lookup"><span data-stu-id="d6464-p111">In addition, the following table describes some example scenarios. In all of these cases, we assume the organization has Office 365 Enterprise E5, which includes Advanced Threat Protection.</span></span>
  
|<span data-ttu-id="d6464-142">**示例应用场景**</span><span class="sxs-lookup"><span data-stu-id="d6464-142">**Example scenario**</span></span>|<span data-ttu-id="d6464-143">**ATP 安全附件保护不适用于这种情况下？**</span><span class="sxs-lookup"><span data-stu-id="d6464-143">**Does ATP Safe Attachments protection apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d6464-144">Pat 组织具有 Office 365 企业 E5，但没有人具有尚未为 ATP 安全附件定义的任何策略。</span><span class="sxs-lookup"><span data-stu-id="d6464-144">Pat's organization has Office 365 Enterprise E5, but no one has defined any policies for ATP Safe Attachments yet.</span></span>  <br/> |<span data-ttu-id="d6464-p112">不。尽管功能可用，但至少一个 ATP 安全附件策略必须定义 ATP 安全附件保护，以准备就绪的顺序。</span><span class="sxs-lookup"><span data-stu-id="d6464-p112">No. Although the feature is available, at least one ATP Safe Attachments policy must be defined in order for ATP Safe Attachments protection to be in place.</span></span>  <br/> |
|<span data-ttu-id="d6464-p113">李是 contoso 销售部的员工。李的组织仅财务人员应用于的位置中具有 ATP 安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="d6464-p113">Lee is an employee in the sales department at Contoso. Lee's organization has an ATP Safe Attachments policy in place that applies to finance employees only.</span></span>  <br/> |<span data-ttu-id="d6464-p114">不。在这种情况下，财务人员将具有 ATP 安全附件保护，但其他员工，包括销售部门，将不是直到包括这些组的策略定义。</span><span class="sxs-lookup"><span data-stu-id="d6464-p114">No. In this case, finance employees would have ATP Safe Attachments protection, but other employees, including the sales department, would not until policies that include those groups are defined.</span></span>  <br/> |
|<span data-ttu-id="d6464-p115">昨天、 上 Jean 的组织的 Office 365 管理员设置适用于所有员工 ATP 安全附件策略。如今，前面 Jean 收到包含附件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d6464-p115">Yesterday, an Office 365 administrator at Jean's organization set up an ATP Safe Attachments policy that applies to all employees. Earlier today, Jean received an email message that includes an attachment.</span></span>  <br/> |<span data-ttu-id="d6464-p116">是的。本示例中，Jean 具有许可证的高级威胁保护，并已定义 ATP 安全附件策略，其中包括 Jean。通常大约需要 30 分钟的新策略跨数据中心; 才会生效由于一天过后在这种情况下，该策略应实际上所示。</span><span class="sxs-lookup"><span data-stu-id="d6464-p116">Yes. In this example, Jean has a license for Advanced Threat Protection, and an ATP Safe Attachments policy that includes Jean has been defined. It typically takes about 30 minutes for a new policy to take effect across datacenters; since a day has passed in this case, the policy should be in effect.</span></span>  <br/> |
|<span data-ttu-id="d6464-p117">Chris 的组织中的组织中的每个人的 ATP 安全附件策略与具有 Office 365 企业 E5。Chris 接收电子邮件有附件，并将转发组织之外的其他人的邮件。</span><span class="sxs-lookup"><span data-stu-id="d6464-p117">Chris's organization has Office 365 Enterprise E5 with ATP Safe Attachments policies in place for everyone in the organization. Chris receives an email that has an attachment, and forwards the message to others who are outside the organization.</span></span>  <br/> |<span data-ttu-id="d6464-p118">Chris 接收的邮件 ATP 安全附件保护。如果收件人的组织还就地具有 ATP 安全附件策略，则 Chris 转发的邮件将这些策略受转发的邮件到达时。</span><span class="sxs-lookup"><span data-stu-id="d6464-p118">ATP Safe Attachments protection is in place for messages that Chris receives. If the recipients' organizations also have ATP Safe Attachments policies in place, then the message that Chris forwards would be subject to those policies when the forwarded message arrives.</span></span>  <br/> |
|<span data-ttu-id="d6464-p119">晓明的组织在有 ATP 安全附件的策略和[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)开启。晓明假定 SharePoint Online 中的每个文件已扫描，可以安全地打开或下载。</span><span class="sxs-lookup"><span data-stu-id="d6464-p119">Jamie's organization has ATP Safe Attachments policies in place, and [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) has been turned on. Jamie assumes that every file in SharePoint Online has been scanned and is safe to open or download.  </span></span><br/> |<span data-ttu-id="d6464-p120">根据定义; 策略就地是 ATP 安全附件保护但是，这并不意味着 SharePoint Online 的 OneDrive for Business 或 Microsoft 团队中的每个文件进行扫描。（若要了解详细信息，请参阅[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)。）</span><span class="sxs-lookup"><span data-stu-id="d6464-p120">ATP Safe Attachments protection is in place according to the policies that are defined; however, this does not mean that every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams is scanned. (To learn more, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).)  </span></span><br/> |
   
## <a name="submitting-files-for-malware-analysis"></a><span data-ttu-id="d6464-164">提交的恶意软件分析的文件</span><span class="sxs-lookup"><span data-stu-id="d6464-164">Submitting files for malware analysis</span></span>

<span data-ttu-id="d6464-165">如果您收到要询问 Microsoft 进行分析的文件，请访问[提交恶意软件分析的文件](https://aka.ms/wdsi/submit)。</span><span class="sxs-lookup"><span data-stu-id="d6464-165">If you receive a file that you want to ask Microsoft to analyze, visit [Submit a file for malware analysis](https://aka.ms/wdsi/submit).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d6464-166">相关主题</span><span class="sxs-lookup"><span data-stu-id="d6464-166">Related topics</span></span>

[<span data-ttu-id="d6464-167">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="d6464-167">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="d6464-168">设置 Office 365 中的 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="d6464-168">Set up ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="d6464-169">SharePoint、 OneDrive 和 Microsoft 团队 ATP</span><span class="sxs-lookup"><span data-stu-id="d6464-169">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)
  
[<span data-ttu-id="d6464-170">Office 365 中的 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="d6464-170">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="d6464-171">Office 365 中的 ATP 防钓鱼功能</span><span class="sxs-lookup"><span data-stu-id="d6464-171">ATP anti-phishing capabilities in Office 365</span></span>](atp-anti-phishing.md)
  
[<span data-ttu-id="d6464-172">查看高级威胁保护报告</span><span class="sxs-lookup"><span data-stu-id="d6464-172">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  


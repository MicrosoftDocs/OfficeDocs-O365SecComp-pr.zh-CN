---
title: Office 365 ATP 安全附件的工作原理
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: "\"安全附件\" 功能可提供电子邮件附件的单击时间验证。 使用安全附件保护组织免受用户在电子邮件中发送或接收的恶意文件的攻击。"
ms.openlocfilehash: 14db6bc51f2017388639eb4270d7c5fc67b4ff7d
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230606"
---
# <a name="how-ffice-365-atp-safe-attachments-works"></a><span data-ttu-id="5e933-104">Office 365 ATP 安全附件的工作原理</span><span class="sxs-lookup"><span data-stu-id="5e933-104">How ffice 365 ATP Safe Attachments works</span></span>

## <a name="how-it-works"></a><span data-ttu-id="5e933-105">运作方式</span><span class="sxs-lookup"><span data-stu-id="5e933-105">How it works</span></span>

<span data-ttu-id="5e933-106">ATP 安全附件功能检查组织中人员的电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="5e933-106">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="5e933-107">如果 ATP 安全附件策略已就绪, 并且该策略涵盖的人在 Office 365 中查看其电子邮件, 则会检查其电子邮件附件, 并根据 ATP 安全附件策略采取相应的操作。</span><span class="sxs-lookup"><span data-stu-id="5e933-107">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="5e933-108">根据您的策略定义方式, 用户可以继续工作, 而无需知道他们是否发送了恶意文件。</span><span class="sxs-lookup"><span data-stu-id="5e933-108">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="5e933-109">以下是有关工作的 ATP 安全附件的两个示例。</span><span class="sxs-lookup"><span data-stu-id="5e933-109">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="5e933-110">**示例 1: 电子邮件附件**假设收到电子邮件, 其中包含附件。</span><span class="sxs-lookup"><span data-stu-id="5e933-110">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="5e933-111">如果附件是安全的还是实际包含旨在窃取用户的用户凭据的恶意软件, 则不会这样。</span><span class="sxs-lookup"><span data-stu-id="5e933-111">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="5e933-112">在先生/她的组织中, 安全管理员在几天前定义了 ATP 安全附件策略。</span><span class="sxs-lookup"><span data-stu-id="5e933-112">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="5e933-113">使用 ATP 安全附件功能, 在获得电子邮件附件之前, 将在虚拟环境中打开并测试该附件。</span><span class="sxs-lookup"><span data-stu-id="5e933-113">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="5e933-114">如果认为附件是恶意的, 则会自动将其删除。</span><span class="sxs-lookup"><span data-stu-id="5e933-114">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="5e933-115">如果附件是安全的, 则会在您通过单击它时按预期方式打开。</span><span class="sxs-lookup"><span data-stu-id="5e933-115">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="5e933-116">**示例 2: SharePoint Online 中的文件**假设 Jean 收到一个文件, 并将其上载到 SharePoint Online 中的库中。</span><span class="sxs-lookup"><span data-stu-id="5e933-116">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="5e933-117">Jean 与团队的其余部分共享指向文件的链接, 而不知道该文件实际是恶意的。</span><span class="sxs-lookup"><span data-stu-id="5e933-117">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="5e933-118">幸运的是, [SharePoint、OneDrive 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)会检测恶意文件并阻止它。</span><span class="sxs-lookup"><span data-stu-id="5e933-118">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="5e933-119">几天后, Chris 将转到 "打开" 文档。</span><span class="sxs-lookup"><span data-stu-id="5e933-119">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="5e933-120">尽管 Chris 可以看到该文件, Chris 也无法打开或共享该文件, 这将保护 Chris 的计算机和恶意文件中的其他人。</span><span class="sxs-lookup"><span data-stu-id="5e933-120">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="5e933-121">ATP 安全附件策略可应用于组织中的特定用户或组, 或应用于整个域。</span><span class="sxs-lookup"><span data-stu-id="5e933-121">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="5e933-122">此外, 还可以将 ATP 安全附件策略配置为在扫描实际附件时使用占位符附件。</span><span class="sxs-lookup"><span data-stu-id="5e933-122">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="5e933-123">若要了解详细信息, 请参阅**[在 Office 365 中设置 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)**。</span><span class="sxs-lookup"><span data-stu-id="5e933-123">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="5e933-124">ATP 安全附件扫描发生在 Office 365 数据所在的同一个区域中。</span><span class="sxs-lookup"><span data-stu-id="5e933-124">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides.</span></span> <span data-ttu-id="5e933-125">有关数据中心地理位置的详细信息, 请参阅[您的数据位于何处？](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="5e933-125">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 


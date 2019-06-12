---
title: 将 Office 365 高级威胁防护与 Microsoft Defender 高级威胁防护集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: 将 Office 365 高级威胁防护与 Microsoft Defender 高级威胁防护集成, 以查看更详细的威胁管理信息。
ms.openlocfilehash: 2d1c88f9911a9940589cdafcc7b12980f2e61a7e
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852556"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="94c97-103">将 Office 365 高级威胁防护与 Microsoft Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="94c97-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="94c97-104">如果您是组织的安全团队的一部分, 则可以使用[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)将[Office 365 高级威胁防护](office-365-atp.md)与相关调查和响应功能集成。</span><span class="sxs-lookup"><span data-stu-id="94c97-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="94c97-105">这可以帮助您快速了解在调查 Office 365 中的威胁时用户的计算机是否存在风险。</span><span class="sxs-lookup"><span data-stu-id="94c97-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="94c97-106">例如, 在启用集成后, 您将能够查看检测到的电子邮件的收件人使用的计算机列表, 以及这些计算机在 Microsoft Defender 高级威胁防护中的最近通知数。</span><span class="sxs-lookup"><span data-stu-id="94c97-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="94c97-107">下图显示了启用 Microsoft Defender ATP 集成时将看到的 "**设备**" 选项卡:</span><span class="sxs-lookup"><span data-stu-id="94c97-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![启用 Microsoft Defender ATP 后, 你可以查看包含警报的计算机列表。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="94c97-109">在此示例中, 您可以看到电子邮件的收件人有四台设备, 并且有一个警报。</span><span class="sxs-lookup"><span data-stu-id="94c97-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="94c97-110">单击设备的链接将在 Microsoft Defender 安全中心中打开其页面。</span><span class="sxs-lookup"><span data-stu-id="94c97-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="94c97-111">要求</span><span class="sxs-lookup"><span data-stu-id="94c97-111">Requirements</span></span>

- <span data-ttu-id="94c97-112">您的组织必须具有 Office 365 ATP 计划 2 (或 Office 365 E5) 和 Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="94c97-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="94c97-113">您必须是 Office 365 全局管理员或在[ &amp;安全合规中心](https://protection.office.com)中分配安全管理员角色 (例如安全管理员)。</span><span class="sxs-lookup"><span data-stu-id="94c97-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="94c97-114">(请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="94c97-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="94c97-115">您必须有权访问安全 & 合规性中心和 Microsoft Defender 安全中心中的[资源管理器 (或实时检测)](threat-explorer.md) 。</span><span class="sxs-lookup"><span data-stu-id="94c97-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="94c97-116">将 Office 365 ATP 与 Microsoft Defender ATP 集成</span><span class="sxs-lookup"><span data-stu-id="94c97-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="94c97-117">通过使用安全 & 合规性中心和 Microsoft Defender 安全中心, 将 Office 365 ATP 与 Microsoft Defender ATP 集成。</span><span class="sxs-lookup"><span data-stu-id="94c97-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="94c97-118">作为 Office 365 全局管理员或安全管理员, 请转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="94c97-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span>
    
2. <span data-ttu-id="94c97-119">选择 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="94c97-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="94c97-120">![威胁管理菜单中的资源管理器](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="94c97-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="94c97-121">在屏幕的右上角, 选择 " **WDATP 设置**"。</span><span class="sxs-lookup"><span data-stu-id="94c97-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="94c97-122">在 "Windows Defender ATP 连接" 对话框中, 启用 "连接到 Windows ATP"。</span><span class="sxs-lookup"><span data-stu-id="94c97-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Microsoft Defender ATP 连接](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="94c97-124">在 Microsoft Defender 安全中心启用连接。</span><span class="sxs-lookup"><span data-stu-id="94c97-124">Enable the connection in the Microsoft Defender Security Center.</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="94c97-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="94c97-125">Related topics</span></span>

[<span data-ttu-id="94c97-126">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="94c97-126">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)
  
[<span data-ttu-id="94c97-127">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="94c97-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  


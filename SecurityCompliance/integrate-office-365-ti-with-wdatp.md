---
title: 将 Office 365 高级威胁防护与 Windows Defender 高级威胁防护集成
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
description: 将 Office 365 高级威胁防护与 Windows Defender 高级威胁防护集成, 以查看更详细的威胁管理信息。
ms.openlocfilehash: 8fbbc8beeeba6cfee0e87ee44f99819094d5569e
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408267"
---
# <a name="integrate-office-365-advanced-threat-protection-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="75069-103">将 Office 365 高级威胁防护与 Windows Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="75069-103">Integrate Office 365 Advanced Threat Protection with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="75069-104">如果您是组织的安全团队的一部分, 则可以使用 Windows Defender 高级威胁防护将 Office 365 高级威胁防护与相关调查和响应功能集成。</span><span class="sxs-lookup"><span data-stu-id="75069-104">If you are part of your organization's security team, you can integrate Office 365 Advanced Threat Protection and related investigation and response features with Windows Defender Advanced Threat Protection.</span></span> <span data-ttu-id="75069-105">这可以帮助您快速了解在调查 Office 365 中的威胁时用户的计算机是否存在风险。</span><span class="sxs-lookup"><span data-stu-id="75069-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="75069-106">例如, 在启用集成后, 您将能够查看检测到的电子邮件的收件人使用的计算机列表, 以及这些计算机在 Windows Defender 高级威胁防护中的最近通知数。</span><span class="sxs-lookup"><span data-stu-id="75069-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="75069-107">下图显示了启用 Windows Defender 高级威胁防护集成时将看到的 "**设备**" 选项卡:</span><span class="sxs-lookup"><span data-stu-id="75069-107">The following image shows the **Devices** tab that you'll see when have Windows Defender Advanced Threat Protection integration enabled:</span></span> 
  
![启用 Windows Defender ATP 后, 你可以查看包含警报的计算机列表。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="75069-109">在此示例中, 您可以看到电子邮件的收件人有四台设备, 并且有一个警报。</span><span class="sxs-lookup"><span data-stu-id="75069-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="75069-110">单击设备的链接将在 Windows Defender 高级威胁防护门户中打开其页面。</span><span class="sxs-lookup"><span data-stu-id="75069-110">Clicking the link for a device opens its page in the Windows Defender Advanced Threat Protection portal.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="75069-111">要求</span><span class="sxs-lookup"><span data-stu-id="75069-111">Requirements</span></span>

- <span data-ttu-id="75069-112">您的组织必须具有 Office 365 高级威胁防护计划 2 (或 Office 365 E5) 和 Windows Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="75069-112">Your organization must have Office 365 Advanced Threat Protection Plan 2 (or Office 365 E5) and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="75069-113">您必须是 Office 365 全局管理员或在[ &amp;安全合规中心](https://protection.office.com)中分配安全管理员角色 (例如安全管理员)。</span><span class="sxs-lookup"><span data-stu-id="75069-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="75069-114">(请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="75069-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="75069-115">您必须具有安全 & 合规性中心和 Windows Defender 高级威胁防护门户中的[浏览器 (或实时检测)](threat-explorer.md)的访问权限。</span><span class="sxs-lookup"><span data-stu-id="75069-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Windows Defender Advanced Threat Protection portal.</span></span>
    
## <a name="to-integrate-office-365-advanced-threat-protection-with-windows-defender-atp"></a><span data-ttu-id="75069-116">将 Office 365 高级威胁防护与 Windows Defender ATP 集成</span><span class="sxs-lookup"><span data-stu-id="75069-116">To integrate Office 365 Advanced Threat Protection with Windows Defender ATP</span></span>

<span data-ttu-id="75069-117">将 Office 365 高级威胁防护与 Windows Defender 高级威胁防护结合使用安全 & 合规性中心和 Windows Defender 高级威胁防护门户进行设置。</span><span class="sxs-lookup"><span data-stu-id="75069-117">Integrating Office 365 Advanced Threat Protection with Windows Defender Advanced Threat Protection is set up by using both the Security & Compliance Center AND the Windows Defender Advanced Threat Protection portal.</span></span>
  
1. <span data-ttu-id="75069-118">作为 Office 365 全局管理员或安全管理员, 请转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="75069-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="75069-119">选择 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="75069-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="75069-120">![威胁管理菜单中的资源管理器](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="75069-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="75069-121">在屏幕的右上角, 选择 " **WDATP 设置**"。</span><span class="sxs-lookup"><span data-stu-id="75069-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="75069-122">在 "Windows Defender ATP 连接" 对话框中, 启用 "连接到 Windows ATP"。</span><span class="sxs-lookup"><span data-stu-id="75069-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Windows Defender ATP 连接](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="75069-124">启用 Windows Defender 高级威胁防护中的连接。</span><span class="sxs-lookup"><span data-stu-id="75069-124">Enable the connection in Windows Defender Advanced Threat Protection.</span></span> <span data-ttu-id="75069-125">请参阅[使用 Windows Defender 高级威胁防护门户](https://go.microsoft.com/fwlink/?linkid=859690)。</span><span class="sxs-lookup"><span data-stu-id="75069-125">See [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="75069-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="75069-126">Related topics</span></span>

[<span data-ttu-id="75069-127">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="75069-127">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)
  
[<span data-ttu-id="75069-128">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="75069-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  


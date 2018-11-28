---
title: 将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: 与 Windows Defender 高级威胁保护威胁管理的详细的信息，请参阅集成 Office 365 高级威胁保护。
ms.openlocfilehash: 1198f53c47811d69b93106c413e3d3a09d83e736
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706136"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="48b87-103">将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="48b87-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="48b87-p101">如果您是组织的安全工作组的一部分，您可以将 Office 365 集成与 Windows Defender 高级威胁保护 (ATP)。这可以帮助您快速了解用户的计算机是否在风险时正在调查 Office 365 中的威胁。例如，启用集成后，您将能够列表，请参阅使用检测到的电子邮件的收件人的计算机以及如何在 Windows Defender ATP 中的多个最近的通知这些计算机具有。</span><span class="sxs-lookup"><span data-stu-id="48b87-p101">If you are part of your organization's security team, you can integrate Office 365 with Windows Defender Advanced Threat Protection (ATP). This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender ATP.</span></span>
  
<span data-ttu-id="48b87-107">下图显示**设备**选项卡，您将看到已启用 Windows Defender ATP 集成时：</span><span class="sxs-lookup"><span data-stu-id="48b87-107">The following image shows the **Devices** tab that you'll see when have Windows Defender ATP integration enabled:</span></span> 
  
![启用 Windows Defender ATP 后，您可以看到计算机的通知的列表。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="48b87-p102">本示例中，您可以看到收件人的电子邮件有四个计算机和一个 Windows Defender ATP 中有一条通知。单击指向计算机的链接计算机页中打开 Windows Defender ATP 新选项卡。</span><span class="sxs-lookup"><span data-stu-id="48b87-p102">In this example, you can see that the recipients of the email message have four machines and one has an alert in Windows Defender ATP. Clicking the link to a machine opens the machine page in Windows Defender ATP in a new tab.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="48b87-111">要求</span><span class="sxs-lookup"><span data-stu-id="48b87-111">Requirements</span></span>

- <span data-ttu-id="48b87-112">您的组织必须具有 Office 365 威胁智能和 Windows Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="48b87-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="48b87-p103">您必须是 Office 365 全局管理员或具有安全管理员角色中分配[安全&amp;合规性中心](https://security.microsoft.com)。(请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="48b87-p103">You must be an Office 365 global administrator or have a security administrator role assigned in the [Security &amp; Compliance Center](https://security.microsoft.com). (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="48b87-115">您必须具有对 Office 365 威胁智能和 Windows Defender ATP 门户网站的访问。</span><span class="sxs-lookup"><span data-stu-id="48b87-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender ATP portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="48b87-116">与 Windows Defender ATP 集成 Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="48b87-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="48b87-117">在 Office 365 和 Windows Defender ATP 门户中与 Windows Defender ATP 集成 Office 365 威胁智能是设置。</span><span class="sxs-lookup"><span data-stu-id="48b87-117">Integrating Office 365 Threat Intelligence with Windows Defender ATP is set up both in Office 365 and in the Windows Defender ATP portal.</span></span>
  
1. <span data-ttu-id="48b87-118">作为 Office 365 全局或安全管理员，请转到[https://security.microsoft.com](https://security.microsoft.com)和使用 Office 365 您工作或学校的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="48b87-118">As an Office 365 global or a security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="48b87-119">选择**威胁管理** \> **威胁资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="48b87-119">Choose **Threat management** \> **Threat explorer**.</span></span>
    
3. <span data-ttu-id="48b87-120">在**详细**菜单中，选择**WDATP 设置**。</span><span class="sxs-lookup"><span data-stu-id="48b87-120">On the **More** menu, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="48b87-121">选择**连接到 Windows ATP**。</span><span class="sxs-lookup"><span data-stu-id="48b87-121">Select **Connect to Windows ATP**.</span></span>
    
<span data-ttu-id="48b87-p104">当您更改在 Office 365 中的设置后，必须启用从 Windows Defender ATP 的连接。为此，请参阅[Use Windows Defender 高级威胁保护门户](https://go.microsoft.com/fwlink/?linkid=859690)。</span><span class="sxs-lookup"><span data-stu-id="48b87-p104">After you have changed the settings in Office 365, you must enable the connection from Windows Defender ATP. To do that, see [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="48b87-124">相关主题</span><span class="sxs-lookup"><span data-stu-id="48b87-124">Related topics</span></span>

[<span data-ttu-id="48b87-125">Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="48b87-125">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="48b87-126">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="48b87-126">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  


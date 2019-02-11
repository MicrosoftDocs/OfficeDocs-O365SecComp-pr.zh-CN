---
title: 将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: 与 Windows Defender 高级威胁保护威胁管理的详细的信息，请参阅集成 Office 365 高级威胁保护。
ms.openlocfilehash: e5070e003972ae5308415dcdcca85b069d1163ac
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29382535"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="05124-103">将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="05124-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="05124-p101">如果您是组织的安全工作组的一部分，您可以与 Windows Defender 高级威胁保护集成 Office 365 高级威胁保护和威胁智能功能。这可以帮助您快速了解用户的计算机是否在风险时正在调查 Office 365 中的威胁。例如，启用集成后，您将能够列表，请参阅使用检测到的电子邮件的收件人的计算机以及如何在 Windows Defender 高级威胁保护中的多个最近的通知这些计算机具有。</span><span class="sxs-lookup"><span data-stu-id="05124-p101">If you are part of your organization's security team, you can integrate Office 365 Advanced Threat Protection and Threat Intelligence features with Windows Defender Advanced Threat Protection. This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="05124-107">下图显示**设备**选项卡，您将看到已启用 Windows Defender 高级威胁保护集成时：</span><span class="sxs-lookup"><span data-stu-id="05124-107">The following image shows the **Devices** tab that you'll see when have Windows Defender Advanced Threat Protection integration enabled:</span></span> 
  
![启用 Windows Defender ATP 后，您可以看到计算机的通知的列表。](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="05124-p102">本示例中，您可以看到收件人的电子邮件有四个设备和一个具有一条通知。单击设备链接将在 Windows Defender 高级威胁保护门户中打开其页面。</span><span class="sxs-lookup"><span data-stu-id="05124-p102">In this example, you can see that the recipients of the email message have four devices and one has an alert. Clicking the link for a device opens its page in the Windows Defender Advanced Threat Protection portal.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="05124-111">要求</span><span class="sxs-lookup"><span data-stu-id="05124-111">Requirements</span></span>

- <span data-ttu-id="05124-112">您的组织必须具有 Office 365 威胁智能和 Windows Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="05124-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="05124-p103">您必须是 Office 365 全局管理员或具有安全管理员角色 （如安全管理员） 中分配[安全&amp;合规性中心](https://protection.office.com)。(请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="05124-p103">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com). (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="05124-115">您必须具有对 Office 365 威胁智能和 Windows Defender 高级威胁保护门户网站的访问。</span><span class="sxs-lookup"><span data-stu-id="05124-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender Advanced Threat Protection portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="05124-116">与 Windows Defender ATP 集成 Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="05124-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="05124-117">与 Windows Defender 高级威胁保护集成 Office 365 威胁智能设置使用这两个 Office 365 安全性 & 合规性中心和 Windows Defender 高级威胁保护门户。</span><span class="sxs-lookup"><span data-stu-id="05124-117">Integrating Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection is set up by using both the Office 365 Security & Compliance Center AND the Windows Defender Advanced Threat Protection portal.</span></span>
  
1. <span data-ttu-id="05124-118">作为 Office 365 全局管理员或安全管理员，请转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 您工作或学校的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="05124-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="05124-119">选择**威胁管理** \> **资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="05124-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="05124-120">![威胁管理菜单中的资源管理器](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="05124-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="05124-121">在屏幕的右上角，选择**WDATP 设置**。</span><span class="sxs-lookup"><span data-stu-id="05124-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="05124-122">在 Windows Defender ATP 连接对话框中，打开连接到 Windows ATP。</span><span class="sxs-lookup"><span data-stu-id="05124-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Windows Defender ATP 连接](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="05124-p104">启用 Windows Defender 高级威胁 Protection 中的连接。请参阅[Use Windows Defender 高级威胁保护门户](https://go.microsoft.com/fwlink/?linkid=859690)。</span><span class="sxs-lookup"><span data-stu-id="05124-p104">Enable the connection in Windows Defender Advanced Threat Protection. See [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="05124-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="05124-126">Related topics</span></span>

[<span data-ttu-id="05124-127">Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="05124-127">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="05124-128">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="05124-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  


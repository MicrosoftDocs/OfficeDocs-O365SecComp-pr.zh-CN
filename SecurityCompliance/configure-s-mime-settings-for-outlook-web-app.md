---
title: 配置 Outlook Web App 的 S/MIME 设置
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/8/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
description: 为 Exchange 2013 和 Exchange Online 的组织管理员，您可以设置 Outlook Web App 以允许发送和接收 S/MIME 的受保护的邮件。使用等 cmdlet 可以管理此功能通过 Exchange 命令行管理程序接口。
ms.openlocfilehash: e4bbf6cb8b0e2976b856045fc8a474bc2aa2a55a
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002499"
---
# <a name="configure-smime-settings-for-outlook-web-app"></a><span data-ttu-id="db0b0-104">配置 Outlook Web App 的 S/MIME 设置</span><span class="sxs-lookup"><span data-stu-id="db0b0-104">Configure S/MIME settings for Outlook Web App</span></span>

<span data-ttu-id="db0b0-p102">作为 Exchange 2013 和 Exchange Online 组织管理员，您可以设置 Outlook Web App，以允许发送和接收受 S/MIME 保护的邮件。使用  `SMIMEConfig` cmdlet 可通过 Exchange 命令行管理程序界面管理此功能。</span><span class="sxs-lookup"><span data-stu-id="db0b0-p102">As an organization administrator for both Exchange 2013 and Exchange Online, you can set up Outlook Web App to allow sending and receiving S/MIME-protected messages. Use the  `SMIMEConfig` cmdlet to manage this feature through the Exchange Management Shell interface.</span></span> 
  
<span data-ttu-id="db0b0-107">若要了解参数的详细说明以及  `get-SMIMEConfig` 和  `set-SMIMEConfig` 的示例等详细信息，请参阅 [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) 和 [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx) 文档。</span><span class="sxs-lookup"><span data-stu-id="db0b0-107">For more information such as a detailed description of parameters and examples for  `get-SMIMEConfig` and  `set-SMIMEConfig`, see the [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) and [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx) documentation.</span></span> 
  
<span data-ttu-id="db0b0-p103">只能使用命令行管理程序执行此过程。 若要了解如何在本地 Exchange 组织中打开 Exchange 命令行管理程序，请参阅 **Open the Shell**。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="db0b0-p103">You can only use the Shell to perform this procedure. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="db0b0-111">详细信息</span><span class="sxs-lookup"><span data-stu-id="db0b0-111">For more information</span></span>

[<span data-ttu-id="db0b0-112">邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="db0b0-112">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
  


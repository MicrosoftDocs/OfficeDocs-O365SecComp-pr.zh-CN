---
title: 弃用 Office 365 邮件加密查看器应用
ms.author: krowley
author: kccross
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
description: 在2018年8月15日, 我们将从 Android 和 Apple 商店中删除 Office 365 邮件加密 (OME) 查看器移动应用。Office 365 邮件加密查看器移动应用程序需要阅读使用 Apple 和 Android 手机上的早期版本的 OME 加密的电子邮件和附件。除了删除 OME Viewer 应用程序, 我们不会对早期版本的 OME 进行任何其他更改。
ms.openlocfilehash: e2ca43f2bca6e419a5dfeb2ff5ca2c554598357c
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357473"
---
# <a name="deprecating-office-365-message-encryption-viewer-app"></a><span data-ttu-id="2ee2e-105">弃用 Office 365 邮件加密查看器应用</span><span class="sxs-lookup"><span data-stu-id="2ee2e-105">Deprecating Office 365 Message Encryption Viewer App</span></span>

<span data-ttu-id="2ee2e-p102">在2018年8月15日, 我们将从 Android 和 Apple 商店中删除 Office 365 邮件加密 (OME) 查看器移动应用。Office 365 邮件加密查看器移动应用程序需要阅读使用 Apple 和 Android 手机上的早期版本的 OME 加密的电子邮件和附件。除了删除 OME Viewer 应用程序, 我们不会对早期版本的 OME 进行任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="2ee2e-p102">On August 15, 2018, we will be removing the Office 365 Message Encryption (OME) Viewer mobile app from Android and Apple stores. The Office 365 Message Encryption Viewer mobile app was required to read email messages and attachments that were encrypted with the previous version of OME on Apple and Android phones. Apart from removing the OME Viewer app, we are not making any other changes to the previous version of OME.</span></span>
  
## <a name="changes-beginning-august-2018"></a><span data-ttu-id="2ee2e-109">2018年8月开始的更改</span><span class="sxs-lookup"><span data-stu-id="2ee2e-109">Changes beginning August 2018</span></span>

<span data-ttu-id="2ee2e-p103">如最后在九月宣布宣布, 我们发布了[Office 365 邮件加密](https://aka.ms/ome2017)的新版本, 以便用户可以向组织内外的任何人发送加密和受保护的邮件, 而不需要移动应用。从那时起, 我们添加了其他功能:</span><span class="sxs-lookup"><span data-stu-id="2ee2e-p103">As announced last September, we have released a new version of [Office 365 Message Encryption](https://aka.ms/ome2017) so that users can send encrypted and protected messages to anyone inside or outside the organization without the requirement of the mobile app. Since then, we've added additional capabilities:</span></span> 
  
- [<span data-ttu-id="2ee2e-112">仅加密模板</span><span class="sxs-lookup"><span data-stu-id="2ee2e-112">Encrypt-only template</span></span>](https://aka.ms/encryptonly)
    
- [<span data-ttu-id="2ee2e-113">用于解密附件的控件</span><span class="sxs-lookup"><span data-stu-id="2ee2e-113">Control to decrypt attachments</span></span>](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
<span data-ttu-id="2ee2e-p104">进行此更改后, 用户将不再能够从8月1日开始下载 Office 365 邮件加密查看器移动应用。因此, 邮件收件人可能无法读取在某些 Android 和 Apple 移动设备上使用 OME 的早期版本加密的邮件。但是, 他们仍可以在个人计算机上读取这些邮件 (通过桌面浏览器)。已下载应用程序的用户将继续能够使用它。</span><span class="sxs-lookup"><span data-stu-id="2ee2e-p104">With this change, users will no longer be able to download the Office 365 Message Encryption Viewer mobile app beginning August 1. As a result, mail recipients may not be able to read messages encrypted with the previous version of OME on some Android and Apple mobile devices. However, they will still be able to read these messages on personal computers (via desktop browsers). Users who have already downloaded the app will continue to be able to use it.</span></span>
  
## <a name="why-this-change-was-made"></a><span data-ttu-id="2ee2e-118">为什么要进行此更改</span><span class="sxs-lookup"><span data-stu-id="2ee2e-118">Why this change was made</span></span>

<span data-ttu-id="2ee2e-p105">新版本的 OME 不再需要移动应用读取受保护的电子邮件和附件。使用新 OME 功能的 Office 365 客户可以在 Outlook mobile 和非 Office 365 客户中查看受保护的邮件。可以在浏览器中查看受保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="2ee2e-p105">The new version of OME no longer requires a mobile app to read protected email messages and attachments. Office 365 customers using the new OME capabilities can view the protected message in Outlook mobile and non-Office 365 customers can view protected messages in a browser.</span></span>
  
<span data-ttu-id="2ee2e-p106">要求用户下载移动应用是客户查看受保护邮件的另一个障碍。新的 Office 365 邮件加密功能可提供更好的移动体验。</span><span class="sxs-lookup"><span data-stu-id="2ee2e-p106">Requiring users to download a mobile app is another hurdle for customers to view protected messages. The new Office 365 Message Encryption capabilities provide a better mobile experience.</span></span>
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="2ee2e-123">我仍然可以使用以前版本的 Office 365 邮件加密</span><span class="sxs-lookup"><span data-stu-id="2ee2e-123">Can I still use the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="2ee2e-124">早期版本的 office 365 邮件加密目前不会被弃用。但是, 我们对 office 365 邮件加密的新版本进行了重大增强, 这使得加密和权限保护对敏感数据的保护变得更加简单以及任何设备 (包括 Office 365 用户在 Outlook 中直接阅读受保护的邮件的功能) (桌面、移动和 web)。</span><span class="sxs-lookup"><span data-stu-id="2ee2e-124">The previous version of Office 365 Message Encryption will not be deprecated at this time, however, we have made significant enhancements to the new version of Office 365 Message Encryption, which make it easier to encrypt and rights protect sensitive data to anyone and on any device - including the ability for Office 365 users to read protected messages directly in Outlook (desktop, mobile, and web).</span></span> 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="2ee2e-125">需要执行哪些操作才能为此更改做准备</span><span class="sxs-lookup"><span data-stu-id="2ee2e-125">What do I need to do to prepare for this change</span></span>

<span data-ttu-id="2ee2e-126">如果您的组织当前向需要 OME 查看器应用程序的收件人发送了加密附件, 则应更新您的文档和培训资源。</span><span class="sxs-lookup"><span data-stu-id="2ee2e-126">If your organization currently sends encrypted attachments to recipients that require the OME Viewer app, you should update your documentation and training resources.</span></span>
  
<span data-ttu-id="2ee2e-p107">我们建议您更新现有的 Exchange 邮件流规则, 以使用当前版本的 OME, 以便您的组织可以利用新的和改进的功能。一旦设置了新的 OME 功能, 收件人就不需要 OME 查看器应用来在移动设备上阅读加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="2ee2e-p107">We recommend updating existing Exchange mail flow rules to use the current version of OME so that your organization can take advantage of the new and improved capabilities. Once you have set up the new OME capabilities, recipients won't need the OME Viewer app to read encrypted messages on mobile devices.</span></span>
  
<span data-ttu-id="2ee2e-p108">Microsoft 建议您制定一个计划, 尽快移动到新的 OME 功能, 因为它对您的组织合理。有关说明, 请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。如果您想要详细了解新功能的工作方式, 请参阅[Office 365 邮件加密](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="2ee2e-p108">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md). If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span>
  


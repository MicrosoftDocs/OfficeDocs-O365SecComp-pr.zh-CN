---
title: 在 Exchange Online 中为 web 上的 Outlook 配置 S/MIME 设置
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: exchange online 管理员在 exchange online 中查看和配置 Outlook 网页中的 S/MIME 设置时需要执行的操作的简短说明。
ms.openlocfilehash: 74d2f37f0cabc0b49abdd78d2a10928b543fd615
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295355"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="3720a-103">在 Exchange Online 中为 web 上的 Outlook 配置 S/MIME 设置</span><span class="sxs-lookup"><span data-stu-id="3720a-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="3720a-p101">作为 Exchange Online 管理员, 您可以设置 web 上的 outlook (以前称为 "outlook web App"), 以允许发送和接收受 S/MIME 保护的邮件。使用**get-smimeconfig**和**get-smimeconfig** cmdlet 在 Exchange Online PowerShell 中查看和管理此功能。若要连接到 exchange online powershell, 请参阅[连接到 exchange online powershell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="3720a-p101">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages. Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell. To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

<span data-ttu-id="3720a-107">有关语法和参数的详细信息, 请参阅[get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)和[get-smimeconfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3720a-107">For detailed syntax and parameter information, see [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) and [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="3720a-108">Chrome 注意事项</span><span class="sxs-lookup"><span data-stu-id="3720a-108">Considerations for Chrome</span></span>

<span data-ttu-id="3720a-p102">若要在 Google Chrome web 浏览器中使用 web 上的 Outlook 中的 S/MIME, 您 (或另一个管理员) 必须设置和配置名为**ExtensionInstallForcelist**的 Chromium 策略, 以在 Chrome 中安装 Microsoft S/mime 扩展。该策略应使用语法: `<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`例如:。 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`此步骤是使用 Chrome 的先决条件;它不会替换用户安装的 S/MIME 控件。有关**ExtensionInstallForcelist**策略的详细信息, 请参阅[ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist)。</span><span class="sxs-lookup"><span data-stu-id="3720a-p102">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome. The policy should use the syntax: `<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` For example: `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`. This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users. For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="3720a-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="3720a-113">For more information</span></span>

[<span data-ttu-id="3720a-114">邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="3720a-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

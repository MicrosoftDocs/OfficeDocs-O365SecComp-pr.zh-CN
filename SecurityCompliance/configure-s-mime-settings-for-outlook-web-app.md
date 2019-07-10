---
title: 在 Exchange Online 中为 web 上的 Outlook 配置 S/MIME 设置
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange online 管理员在 Exchange Online 中查看和配置 Outlook 网页中的 S/MIME 设置时需要执行的操作的简短说明。
ms.openlocfilehash: 6e390e377369dc0de73d5e063a6a21fd549c3bef
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600128"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="230d4-103">在 Exchange Online 中为 web 上的 Outlook 配置 S/MIME 设置</span><span class="sxs-lookup"><span data-stu-id="230d4-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="230d4-104">作为 Exchange Online 管理员, 您可以设置 web 上的 Outlook (以前称为 "Outlook Web App"), 以允许发送和接收受 S/MIME 保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="230d4-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="230d4-105">使用**get-smimeconfig**和**Get-smimeconfig** Cmdlet 在 Exchange Online PowerShell 中查看和管理此功能。</span><span class="sxs-lookup"><span data-stu-id="230d4-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="230d4-106">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="230d4-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

<span data-ttu-id="230d4-107">有关语法和参数的详细信息, 请参阅[get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)和[get-smimeconfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="230d4-107">For detailed syntax and parameter information, see [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) and [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="230d4-108">Chrome 注意事项</span><span class="sxs-lookup"><span data-stu-id="230d4-108">Considerations for Chrome</span></span>

<span data-ttu-id="230d4-109">若要在 Google Chrome web 浏览器中使用 web 上的 Outlook 中的 S/MIME, 您 (或另一个管理员) 必须设置和配置名为**ExtensionInstallForcelist**的 Chromium 策略, 以在 Chrome 中安装 Microsoft S/mime 扩展。</span><span class="sxs-lookup"><span data-stu-id="230d4-109">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="230d4-110">策略值为`maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`。</span><span class="sxs-lookup"><span data-stu-id="230d4-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="230d4-111">请注意, 应用此策略需要加入域的计算机, 因此使用 Chrome 中的 S/MIME 可有效地要求加入域的计算机。</span><span class="sxs-lookup"><span data-stu-id="230d4-111">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="230d4-112">有关**ExtensionInstallForcelist**策略的详细信息, 请参阅[ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist)。</span><span class="sxs-lookup"><span data-stu-id="230d4-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span></span>

<span data-ttu-id="230d4-113">此步骤是使用 Chrome 的先决条件;它不会替换用户安装的 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="230d4-113">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="230d4-114">在首次使用 S/MIME 时, 系统会提示用户在 web 上的 Outlook 中下载并安装 S/MIME 控件。</span><span class="sxs-lookup"><span data-stu-id="230d4-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="230d4-115">或者, 用户可以在其 Outlook 的 web 设置中主动转到**S/MIME** , 以获取该控件的下载链接。</span><span class="sxs-lookup"><span data-stu-id="230d4-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="230d4-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="230d4-116">For more information</span></span>

[<span data-ttu-id="230d4-117">邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="230d4-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

---
title: 在 Exchange Online 中为 web 上的 Outlook 配置 S/MIME 设置
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange online 管理员在 Exchange Online 中查看和配置 Outlook 网页中的 S/MIME 设置时需要执行的操作的简短说明。
ms.openlocfilehash: 41ec5b675284b2040a11f9e076ccef4afcda561a
ms.sourcegitcommit: d24f50347c671cf5d2d8afec2f80d37d18af8b5d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "33867825"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>在 Exchange Online 中为 web 上的 Outlook 配置 S/MIME 设置

作为 Exchange Online 管理员, 您可以设置 web 上的 Outlook (以前称为 "Outlook Web App"), 以允许发送和接收受 S/MIME 保护的邮件。 使用**get-smimeconfig**和**Get-smimeconfig** Cmdlet 在 Exchange Online PowerShell 中查看和管理此功能。 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。

有关语法和参数的详细信息, 请参阅[get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)和[get-smimeconfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx)。

## <a name="considerations-for-chrome"></a>Chrome 注意事项

若要在 Google Chrome web 浏览器中使用 web 上的 Outlook 中的 S/MIME, 您 (或另一个管理员) 必须设置和配置名为**ExtensionInstallForcelist**的 Chromium 策略, 以在 Chrome 中安装 Microsoft S/mime 扩展。 策略值为`maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`。 请注意, 应用此策略需要加入域的计算机, 因此使用 Chrome 中的 S/MIME 可有效地要求加入域的计算机。

有关**ExtensionInstallForcelist**策略的详细信息, 请参阅[ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist)。

此步骤是使用 Chrome 的先决条件;它不会替换用户安装的 S/MIME 控件。 在首次使用 S/MIME 时, 系统会提示用户在 web 上的 Outlook 中下载并安装 S/MIME 控件。 或者, 用户可以在其 Outlook 的 web 设置中主动转到**S/MIME** , 以获取该控件的下载链接。

## <a name="for-more-information"></a>详细信息

[邮件签名和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)

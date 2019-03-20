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
description: exchange online 管理员在 exchange online 中查看和配置 Outlook 网页中的 S/MIME 设置时需要执行的操作的简短说明。
ms.openlocfilehash: d890b7f39d16d8c0f3866d5ff0024fe31160af6b
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693331"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>在 Exchange Online 中为 web 上的 Outlook 配置 S/MIME 设置

作为 Exchange Online 管理员, 您可以设置 web 上的 outlook (以前称为 "outlook web App"), 以允许发送和接收受 S/MIME 保护的邮件。 使用**get-smimeconfig**和**get-smimeconfig** cmdlet 在 Exchange Online PowerShell 中查看和管理此功能。 若要连接到 exchange online powershell, 请参阅[连接到 exchange online powershell](https://go.microsoft.com/fwlink/p/?linkid=396554)。

有关语法和参数的详细信息, 请参阅[get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)和[get-smimeconfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx)。

## <a name="considerations-for-chrome"></a>Chrome 注意事项

若要在 Google Chrome web 浏览器中使用 web 上的 Outlook 中的 S/MIME, 您 (或另一个管理员) 必须设置和配置名为**ExtensionInstallForcelist**的 Chromium 策略, 以在 Chrome 中安装 Microsoft S/mime 扩展。 该策略应使用语法: `<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`例如:。 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 请注意, 应用此策略需要加入域的计算机, 因此使用 Chrome 中的 S/MIME 可有效地要求加入域的计算机。

此步骤是使用 Chrome 的先决条件;它不会替换用户安装的 S/MIME 控件。 有关**ExtensionInstallForcelist**策略的详细信息, 请参阅[ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist)。

## <a name="for-more-information"></a>有关详细信息

[邮件签名和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)

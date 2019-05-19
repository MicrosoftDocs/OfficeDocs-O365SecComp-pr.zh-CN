---
title: 在 Exchange Online 中设置虚拟证书集合以验证 S/MIME
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 管理员可以了解如何创建将用于验证 Exchange Online 中的 S/MIME 证书的虚拟证书集合。
ms.openlocfilehash: 5af332a6daf745ff6bc1334d9bb2b9d3dcb259be
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158314"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>在 Exchange Online 中设置虚拟证书集合以验证 S/MIME

作为管理员, 你将需要在 Exchange Online 中配置将用于验证 S/MIME 证书的虚拟证书集合。 此虚拟证书集合设置为具有 SST 文件扩展名的证书存储。 SST 文件包含验证 S/MIME 证书时使用的所有根证书和中间证书。

## <a name="create-and-save-an-sst"></a>创建并保存 SST

您可以通过在 Windows PowerShell 中使用**导出证书**cmdlet 导出证书, 并将_Type_值指定为 SST, 从而创建此 SST 证书存储文件。 有关说明, 请参阅[Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)。

拥有 SST 证书存储文件后, 在 Exchange Online PowerShell 中使用以下语法将 SST 文件内容保存在 Exchange Online 虚拟证书存储中。 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

本示例将导入 SST 文件 C:\My Documents\Exported 证书存储 SST。

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

有关语法和参数的详细信息, 请参阅[get-smimeconfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig)。

## <a name="ensuring-a-certificate-is-valid"></a>确保证书有效

在 Exchange Online 中, 仅将 SST 用于证书验证。

## <a name="more-information"></a>详细信息

[邮件签名和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)

[Get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)

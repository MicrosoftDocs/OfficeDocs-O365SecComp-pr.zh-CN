---
title: 在 Exchange Online 中设置虚拟证书集合以验证 S/MIME
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 管理员可以了解如何创建将用于验证 Exchange Online 中的 S/MIME 证书的虚拟证书集合。
ms.openlocfilehash: 15998bce1971952286d8dd4401a92f1e9e47c25d
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693551"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="1abb4-103">在 Exchange Online 中设置虚拟证书集合以验证 S/MIME</span><span class="sxs-lookup"><span data-stu-id="1abb4-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="1abb4-104">作为管理员, 你将需要在 Exchange Online 中配置将用于验证 S/MIME 证书的虚拟证书集合。</span><span class="sxs-lookup"><span data-stu-id="1abb4-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="1abb4-105">此虚拟证书集合设置为具有 SST 文件扩展名的证书存储。</span><span class="sxs-lookup"><span data-stu-id="1abb4-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="1abb4-106">SST 文件包含验证 S/MIME 证书时使用的所有根证书和中间证书。</span><span class="sxs-lookup"><span data-stu-id="1abb4-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="1abb4-107">创建并保存 SST</span><span class="sxs-lookup"><span data-stu-id="1abb4-107">Create and save an SST</span></span>

<span data-ttu-id="1abb4-108">您可以通过在 Windows PowerShell 中使用**导出证书**cmdlet 导出证书, 并将_Type_值指定为 SST, 从而创建此 SST 证书存储文件。</span><span class="sxs-lookup"><span data-stu-id="1abb4-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="1abb4-109">有关说明, 请参阅[Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)。</span><span class="sxs-lookup"><span data-stu-id="1abb4-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="1abb4-110">拥有 SST 证书存储文件后, 在 exchange online PowerShell 中使用以下语法将 SST 文件内容保存在 exchange online 虚拟证书存储中。</span><span class="sxs-lookup"><span data-stu-id="1abb4-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="1abb4-111">若要连接到 exchange online powershell, 请参阅[连接到 exchange online powershell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="1abb4-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="1abb4-112">本示例将导入 SST 文件 C:\My Documents\Exported 证书存储 SST。</span><span class="sxs-lookup"><span data-stu-id="1abb4-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="1abb4-113">有关语法和参数的详细信息, 请参阅[get-smimeconfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig)。</span><span class="sxs-lookup"><span data-stu-id="1abb4-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="1abb4-114">确保证书有效</span><span class="sxs-lookup"><span data-stu-id="1abb4-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="1abb4-115">在 Exchange Online 中, 仅将 SST 用于证书验证。</span><span class="sxs-lookup"><span data-stu-id="1abb4-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="1abb4-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="1abb4-116">More Information</span></span>

[<span data-ttu-id="1abb4-117">邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="1abb4-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="1abb4-118">get-smimeconfig</span><span class="sxs-lookup"><span data-stu-id="1abb4-118">Get-SmimeConfig</span></span>](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)

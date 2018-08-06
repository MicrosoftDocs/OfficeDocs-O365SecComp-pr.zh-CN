---
title: 设置虚拟证书集合以验证 S/MIME
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: s 您将需要配置虚拟证书集合将用于验证 S/MIME 证书的租户管理员。
ms.openlocfilehash: 4b2d85181d95bb1f90d46412cca85c2356d98e10
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22028139"
---
# <a name="set-up-virtual-certificate-collection-to-validate-smime"></a><span data-ttu-id="3bce8-103">设置虚拟证书集合以验证 S/MIME</span><span class="sxs-lookup"><span data-stu-id="3bce8-103">Set up virtual certificate collection to validate S/MIME</span></span>

<span data-ttu-id="3bce8-p101">作为租户管理员，您将需要配置用于验证 S/MIME 证书的虚拟证书集合。虚拟证书集合设置为具有 SST 文件名扩展名的证书存储文件类型。SST 文件包含验证 S/MIME 证书时使用的所有根证书和中间证书。</span><span class="sxs-lookup"><span data-stu-id="3bce8-p101">As a tenant administrator you will need to configure a virtual certificate collection that will be used to validate S/MIME certificates. This virtual certificate collection is set up as a certificate store file type with an SST filename extension. The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>
  
## <a name="create-and-save-an-sst"></a><span data-ttu-id="3bce8-107">创建并保存 SST</span><span class="sxs-lookup"><span data-stu-id="3bce8-107">Create and save an SST</span></span>
<span data-ttu-id="3bce8-108"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="3bce8-108"></span></span>

<span data-ttu-id="3bce8-p102">只能使用命令行管理程序执行此过程。 若要了解如何在本地 Exchange 组织中打开 Exchange 命令行管理程序，请参阅 **Open the Shell**。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="3bce8-p102">You can only use the Shell to perform this procedure. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
<span data-ttu-id="3bce8-p103">作为管理员，您可以创建此 SST 文件，方法是使用  `Export-Certificate` cmdlet 从受信任的计算机导出证书并将类型指定为 SST。有关  `Export-Certificate` cmdlet 的详细信息，请参阅 [Export-Certificate](https://technet.microsoft.com/en-us/library/hh848628.aspx) 参考主题。</span><span class="sxs-lookup"><span data-stu-id="3bce8-p103">As an administrator, you can create this SST file by exporting the certificates from a trusted machine using the  `Export-Certificate` cmdlet and specifying the type as SST. For more information the  `Export-Certificate` cmdlet, see the [Export-Certificate](https://technet.microsoft.com/en-us/library/hh848628.aspx) reference topic.</span></span> 
  
<span data-ttu-id="3bce8-p104">生成 SST 文件后，使用  `Set-Smimeconfig` cmdlet 将其保存在虚拟证书存储中，方法是使用  _-SMIMECertificateIssuingCA_ 参数。例如：  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`</span><span class="sxs-lookup"><span data-stu-id="3bce8-p104">Once the SST file is generated, use the  `Set-Smimeconfig` cmdlet to save it in the virtual certificate store by using the  _-SMIMECertificateIssuingCA_ parameter. For example:  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`</span></span>
  
## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="3bce8-116">确保证书有效</span><span class="sxs-lookup"><span data-stu-id="3bce8-116">Ensuring a certificate is valid</span></span>
<span data-ttu-id="3bce8-117"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="3bce8-117"></span></span>

<span data-ttu-id="3bce8-p105">Exchange 2013 SP1 首先检查 SST 文件并验证证书。如果验证失败，它将检查本地计算机证书存储以验证证书。此行为是 Exchange 2013 SP1 的新增功能，与 Exchange 的以前版本不同。在 Exchange Online 中，仅使用 SST 进行验证。</span><span class="sxs-lookup"><span data-stu-id="3bce8-p105">Exchange 2013 SP1 first checks for the SST file and validates the certificate. If the validation fails, it will look at the local machine certificate store to validate the certificate. This behavior is new for Exchange 2013 SP1 and different from prior versions of Exchange. In Exchange Online only the SST will be used for validation.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="3bce8-122">详细信息</span><span class="sxs-lookup"><span data-stu-id="3bce8-122">More Information</span></span>
<span data-ttu-id="3bce8-123"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="3bce8-123"></span></span>

[<span data-ttu-id="3bce8-124">邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="3bce8-124">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
  
[<span data-ttu-id="3bce8-125">Get-smimeconfig</span><span class="sxs-lookup"><span data-stu-id="3bce8-125">Get-SmimeConfig</span></span>](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
  


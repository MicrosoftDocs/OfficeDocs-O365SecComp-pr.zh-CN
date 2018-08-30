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
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: s 您将需要配置虚拟证书集合将用于验证 S/MIME 证书的租户管理员。
ms.openlocfilehash: 88d12b3c1d5f36c58f278cf304237a569a8b92c4
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003031"
---
# <a name="set-up-virtual-certificate-collection-to-validate-smime"></a>设置虚拟证书集合以验证 S/MIME

作为租户管理员，您将需要配置用于验证 S/MIME 证书的虚拟证书集合。虚拟证书集合设置为具有 SST 文件名扩展名的证书存储文件类型。SST 文件包含验证 S/MIME 证书时使用的所有根证书和中间证书。
  
## <a name="create-and-save-an-sst"></a>创建并保存 SST
<a name="sectionSection0"> </a>

只能使用命令行管理程序执行此过程。 若要了解如何在本地 Exchange 组织中打开 Exchange 命令行管理程序，请参阅 **Open the Shell**。 若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
  
作为管理员，您可以创建此 SST 文件，方法是使用  `Export-Certificate` cmdlet 从受信任的计算机导出证书并将类型指定为 SST。有关  `Export-Certificate` cmdlet 的详细信息，请参阅 [Export-Certificate](https://technet.microsoft.com/en-us/library/hh848628.aspx) 参考主题。 
  
生成 SST 文件后，使用  `Set-Smimeconfig` cmdlet 将其保存在虚拟证书存储中，方法是使用  _-SMIMECertificateIssuingCA_ 参数。例如：  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`
  
## <a name="ensuring-a-certificate-is-valid"></a>确保证书有效
<a name="sectionSection1"> </a>

Exchange 2013 SP1 首先检查 SST 文件并验证证书。如果验证失败，它将检查本地计算机证书存储以验证证书。此行为是 Exchange 2013 SP1 的新增功能，与 Exchange 的以前版本不同。在 Exchange Online 中，仅使用 SST 进行验证。
  
## <a name="more-information"></a>详细信息
<a name="sectionSection2"> </a>

[邮件签名和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)
  
[Get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
  


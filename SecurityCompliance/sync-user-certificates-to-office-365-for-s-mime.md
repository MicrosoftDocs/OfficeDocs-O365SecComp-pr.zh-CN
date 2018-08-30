---
title: 出于 S/MIME 目的将用户证书同步到 Office 365
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
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: 必须先设置适当的证书，然后才能够发送受 S/MIME 保护的邮件。发件人的电子邮件程序使用收件人的公用证书对邮件进行加密，以通过 Exchange Online 发送加密邮件。此公用 X.509 证书必须向 Office 365 发布。
ms.openlocfilehash: 452b538b4515bdbcd5fcbdedad17f0450c04207a
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002364"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>出于 S/MIME 目的将用户证书同步到 Office 365

必须先设置适当的证书，然后才能够发送受 S/MIME 保护的邮件。发件人的电子邮件程序使用收件人的公用证书对邮件进行加密，以通过 Exchange Online 发送加密邮件。此公用 X.509 证书必须向 Office 365 发布。
  
## <a name="to-sync-certificates-that-support-smime"></a>对支持 S/MIME 的证书进行同步

首先，通过颁发证书并在本地 Active Directory 域服务中发布证书来设置 S/MIME。有关在 Exchange 2013 中管理证书的详细信息，请参阅[Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx)。
  
发布证书之后，使用 Azure Active Directory 同步工具将本地 Exchange 环境中的用户数据同步至 Office 365。有关此过程的详细信息，请参阅[目录同步：目录同步工具版本历史](https://go.microsoft.com/fwlink/p/?LinkId=392587)。
  
在（出于 S/MIME 目的）同步其他目录数据的同时，该工具还会同步每个用户对象的  `userCertificate` 和  `userSMIMECertificate` 属性，以便这些数据可用于签名和加密邮件。 
  
## <a name="more-information"></a>详细信息

[邮件签名和加密的 S/MIME](s-mime-for-message-signing-and-encryption.md)
  
[Azure Active Directory 同步工具](https://go.microsoft.com/fwlink/p/?LinkId=392587)
  


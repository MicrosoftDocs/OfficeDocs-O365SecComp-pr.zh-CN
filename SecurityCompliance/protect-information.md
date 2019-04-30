---
title: 保护信息
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/26/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 保护信息的登录页
ms.openlocfilehash: 1c673c2417b399c57ca7ac7e5c5a7b7351de1edd
ms.sourcegitcommit: 696c1ed6b270be3f9da7395b49a7d8fec98e6db0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2019
ms.locfileid: "33473016"
---
# <a name="protect-information"></a>保护信息

Microsoft 365 和 Office 365 包含可应用于特定类型的数据以保护信息的功能。 


|**功能**|**详细信息**|
|:-----|:-----|
|[敏感度标签](sensitivity-labels.md) <br/> |使用灵敏度标签, 你可以对敏感内容进行分类和帮助保护。 保护选项包括标签、水印和加密。 敏感度标签使用 Azure 信息保护。 如果您使用的是 Azure 信息保护标签, 我们建议您在完成迁移后, 避免在其他管理中心中心创建新标签。 请参阅[Azure 信息保护迁移](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-migrate-labels)。 <br/> [保留标签](retention-policies.md)不同于敏感度标签。 保留标签可帮助您根据定义的策略保留或删除内容。 这些帮助组织应遵守行业法规和内部策略。|
|[数据丢失防护](data-loss-prevention-policies.md)DLP  <br/> |使用 DLP 策略, 您可以在 Office 365 中识别、监视和自动保护敏感信息。 数据丢失防护策略可以使用敏感度标签和敏感信息类型来标识敏感信息。 <br/> |
|[敏感信息类型](what-the-sensitive-information-types-look-for.md)  <br/> |dlp 包括很多可供您在 DLP 策略中使用的敏感信息类型。 敏感信息类型定义了自动化过程如何识别特定的信息类型, 如运行状况服务号码和信用卡号。   <br/> |
|[Office 365 邮件加密](ome.md)OME  <br/> |使用 Office 365 邮件加密, 组织可以在组织内部和外部的人员之间发送和接收加密的电子邮件。 Office 365 邮件加密适用于 Outlook.com、yahoo!、Gmail 和其他电子邮件服务。 电子邮件加密有助于确保只有预期的收件人可以查看邮件内容。  <br/> |
|[Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/)（Azure 信息保护）<br/> |如果使用的是敏感度标签或 Office 邮件加密, 则您已在使用 Azure 信息保护。 如果尚未将 Azure 信息保护标签迁移到 Office 365, 请继续在 Azure 信息保护中管理这些标签。  <br/>[Azure 信息保护扫描程序](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner)可在本地运行, 以对 Windows Server、网络共享和 SharePoint server 网站和库上的文件进行分类和保护。 这可能是确定要迁移到 Office 365 的数据的第一步。
|使用 BYOK 或 HYOK 解决方案的 Azure 信息保护 <br/> |某些组织具有业务需求或合规性要求, 以便在本地或在云中保留对 encyption 密钥的控制。 这并不常见。 有关详细信息, 请参阅[为 azure 信息保护保留你自己的密钥 (HYOK)](https://docs.microsoft.com/en-us/azure/information-protection/configure-adrms-restrictions) , 并[为 azure 信息保护引入你自己的密钥 (BYOK)](https://docs.microsoft.com/en-us/azure/information-protection/byok-price-restrictions)。 <br/> |
    


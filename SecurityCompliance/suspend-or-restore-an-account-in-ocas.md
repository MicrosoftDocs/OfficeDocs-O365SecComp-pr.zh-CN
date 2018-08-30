---
title: 暂停或还原 Office 365 云应用安全中的用户帐户
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: '与 Office 365 云应用程序安全性，您可以采取的治理操作的挂起或 unsuspend 的用户帐户。 '
ms.openlocfilehash: a5c75edefc6ddb87b5676c4253aafe04817f6a1d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524997"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a>暂停或还原 Office 365 云应用安全中的用户帐户

Office 365 高级安全管理现在是 Office 365 云应用程序安全性。
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|使用率 ***|
|:-----|:-----|:-----|:-----|
|[启动评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |在这里 ！  <br/> [后续步骤](suspend-or-restore-an-account-in-ocas.md#nextsteps) <br/> |
   
假定收到一个 Office 365 组织的用户帐户已泄露的警报。或者，假设您已收到一条警报，指示有问题的用户帐户。与 Office 365 云应用程序安全性，可以挂起的用户帐户和更高版本将其还原后调查收到通知。
  
> [!NOTE]
> Office 365 云应用程序安全性是在 Office 365 企业 E5 中可用。如果您的组织使用的另一个 Office 365 企业版订阅，可以作为购买 Office 365 云应用程序安全性。(作为全局管理员，在 Office 365 管理中心中，选择**帐单** \> **添加订阅**。)有关详细信息，请参阅[Office 365 平台服务说明： Office 365 安全性&amp;合规性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[购买或编辑企业的 Office 365 的加载项](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a>Office 365 云应用程序安全性挂起的用户帐户

当您挂起的用户帐户时，可以防止用户再次登录。已编辑的用户帐户直接的 Office 365 设置为**登录被阻止**的登录状态相同。
  
> [!NOTE]
> 如果您阻止用户与登录到 Office 365 中，通过这些挂起或通过编辑其登录状态，请注意，可能需要一小时或这样才会生效上所有用户的设备和客户端 （[编辑或更改 Office 365 中的用户](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)）。如果用户登录到 Office 365，阻止将会生效，只要 Office 365 要求其再次登录。 
  
1. 作为[全局管理员或安全管理员](permissions-in-the-security-and-compliance-center.md)，请转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。(您将转到安全&amp;合规性中心。) 
    
2. 安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。
    
3. 选择**转到 Office 365 云应用程序安全性**。
    
    ![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. 在屏幕顶部导航栏中，选择**通知**。
    
5. 在**通知**列中，双击警报与特定的用户帐户。 
    
6. 在**帐户**下的**状态**列中，选择设置![设置图标](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **挂起用户**。
    
## <a name="to-restore-a-user-account"></a>若要还原的用户帐户

请参阅[还原 Office 365 中的用户](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)
  
## <a name="next-steps"></a>后续步骤

- [查看 Office 365 云应用安全中的警报并执行相应操作](review-office-365-cas-alerts.md)
    
- [使用 Office 365 云应用安全管理应用权限](manage-app-permissions-in-ocas.md)
    
- 查看您[的 Office 365 云应用程序安全性的使用率活动](utilization-activities-for-ocas.md)
    


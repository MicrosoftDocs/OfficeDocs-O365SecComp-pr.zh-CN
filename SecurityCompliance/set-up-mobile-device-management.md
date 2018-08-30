---
title: 设置向上移动设备管理 (MDM) 在 Office 365 中
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_OverviewMDM
- 'O365E_OverviewMDM '
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: dd892318-bc44-4eb1-af00-9db5430be3cd
description: 内置移动设备管理 Office 365 帮助您保护和管理 iPhones、 Ipad，Androids，如用户的移动设备和 Windows 电话。若要开始，按照以下步骤激活并针对 Office 365 设置移动设备管理。
ms.openlocfilehash: c92290170b2937067e7407787282eaaa368b25b7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272357"
---
# <a name="set-up-mobile-device-management-mdm-in-office-365"></a>设置向上移动设备管理 (MDM) 在 Office 365 中

Windows 电话和 Office 365 内置移动设备管理 (MDM) 可帮助您保护和管理 iPhones、 Ipad，Androids，如用户的移动设备。您可以创建和管理设备安全策略、 远程擦除设备和查看详细的设备报告。
  
有问题？我们已将一起[常见问题，以帮助地址的常见问题](frequently-asked-questions-about-mdm.md)。请注意，不能使用[合作伙伴： 提供委派管理](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e)for Office 365 中管理移动设备管理。 
  
设备管理是安全的一部分&amp;合规性中心，因此您将需要转那里以启动 MDM 安装程序。
  
设置移动设备管理 Office 365 您将需要：
  
1. [激活的移动设备管理服务](#activate-the-mobile-device-management-service)  
2. [设置移动设备管理](#set-up-mobile-device-management)
3. [确保用户注册其设备](#step-4-recommended-manage-device-security-policies)
  
## <a name="activate-the-mobile-device-management-service"></a>激活的移动设备管理服务

1. 使用您的工作或学校帐户登录 Office 365。 
    
2. 转到[安全&amp;合规性中心](https://protection.office.com)。
    
3. 导航到**数据丢失防护** \> **设备管理**，然后单击**让我们开始吧**以启动的激活过程。 
    
    ![针对 Office 365 设置移动设备管理](media/368e1026-9aa5-431b-a722-8f7cf528f263.png)
  
4. 我们创建的默认安全策略，用于帮助您开始。更新在此页上的安全策略的名称，然后单击**启动安装程序**。
    
    ![设置移动设备管理安全策略](media/5619a2d1-f900-4268-9050-5d7eb57429a5.png)
  
5. 您将看到的安装程序屏幕上显示进度设置服务。
    
    ![MDM 安装进度](media/db45d1bb-d247-4ac0-9deb-1b0c1ace9bfa.png)
  
> [!TIP]
> 您还可以查找**MDM 安装**通过搜索。在 Office 365 管理中心\>**主页**上，在**搜索**框中键入移动设备管理。>![搜索管理中心中的移动设备管理](media/cd0ebf15-ef79-4eaa-ab5b-041ac0bd4e5b.png)
  
它可以花一些时间来激活的 Office 365 的移动设备管理但完成后，您会收到电子邮件的说明要执行的下一个步骤。
  
## <a name="set-up-mobile-device-management"></a>设置移动设备管理

服务准备就绪后，完成以下四个步骤以完成安装。您可能需要安全中**设备管理**页上单击[管理设置](https://portal.office.com/EAdmin/Device/IntuneInventory.aspx)&amp;合规性中心以查看以下设置。 
  
![设置建议的步骤和所需的移动设备管理](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
### <a name="step-1-required-configure-domains-for-mdm"></a>步骤 1: MDM （必需） 配置域

如果您没有与 Office 365 关联的自定义域名，或者如果您不管理 Windows 设备，则可以跳过本节。否则，您需要添加您的 DNS 主机的域的 DNS 记录。如果您已设置您的域与 Office 365 的一部分已，添加记录所有正在您设置。添加记录之后，您的组织中使用您的自定义域的电子邮件地址与 Windows 设备上登录的 Office 365 用户将重定向以在 MDM 注册 Office 365。
  
需要帮助设置记录？在[为 Office 365 管理 DNS 记录时创建 DNS 记录](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)中提供的列表中找到域名注册机构，然后选择要转到有关创建 DNS 记录的分步帮助的注册器名称。使用这些指令添加以下两个记录： 
  
|**主机名**|**记录类型**|**地址**|**TTL**|
|:-----|:-----|:-----|:-----|
|EnterpriseEnrollment  <br/> |CNAME  <br/> |EnterpriseEnrollment.manage.microsoft.com  <br/> |3600  <br/> |
|EnterpriseRegistration  <br/> |CNAME  <br/> |EnterpriseRegistration.windows.net  <br/> |3600  <br/> |
   
添加两个记录后，返回到安全&amp;合规性中心并导航到**设备管理** \> **管理设置**以完成下一步。 
  
### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>步骤 2: （必需） 配置的 iOS 设备 APNs 证书

若要管理如 iPad 和 Iphone iOS 设备，您需要创建 APNs 证书。
  
为此，请**设置移动设备管理页面**上的**设置**链接从按照的步骤。
  
1. 旁边**配置 iOS 设备 APNs 证书**，选择**设置**。
    
2. 选择**下载 CSR 文件**并保存到这二者的证书签名请求将请记住在计算机上。 
    
    ![安装 APN 证书对话框](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. 选择**下一步**。
    
4. 创建 APN 证书。
    
  - 选择以打开 Apple 推送证书门户**Apple APNS 门户**。 
    
    ![使用 Apple APNS 门户选择安装 APN 通知证书对话框](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - 登录 Apple id。
    
    > [!IMPORTANT]
    > 使用 Apple ID 与即使管理帐户的用户离开将保持与您的组织的电子邮件帐户关联的公司。保存此 ID，因为您需要在需要时续订证书使用相同的 ID。 
  
  - 选择**创建的证书**，并接受**使用条款**。
    
  - **浏览**证书签名请求从 Office 365 下载到您的计算机，并选择**上载**。
    
  - **下载**APN 证书创建 Apple 推送证书门户到您的计算机。 
    
    > [!TIP]
    > 如果您在遇到问题下载证书，请刷新浏览器。 
  
5. 返回到 Office 365，并选择**下一步**，转到**上载 APNS 证书**页。 
    
6. 浏览到从 Apple 推送证书门户下载 APN 证书。
    
    ![单击浏览按钮以选择 APNS cert 从 Apple 下载](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. 选择**完成**。
    
添加 APN 证书后，返回到安全&amp;合规性中心并导航到**设备管理** \> **管理设置**以完成下一步。 
  
### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>步骤 3： 设置多因素身份验证的 （推荐）

如果您看不到下**推荐步骤**多因素身份验证 (MFA)，则可以跳过本节。如果列出了此选项，我们建议您在 Azure AD 门户以增加的 Office 365 注册过程移动设备管理安全性开启 MFA。默认情况下，它处于状态。
  
MFA 有助于防止通过要求第二个窗体的身份验证的移动设备注册到 Office 365 中的注册。用户所需确认电话呼叫、 文本消息或在其移动设备上的应用程序通知后正确地输入其工作帐户密码。完成此第二个表单的身份验证后，他们可以仅注册其设备。Office 365 中移动设备管理注册用户的设备后，用户可以访问 Office 365 资源与他们显示工作的所有服务器的帐户。
  
旁边**设置多因素身份验证**，请选择**设置**。若要了解如何在 Azure AD 门户中打开 MFA，请参阅[设置多因素身份验证](https://go.microsoft.com/fwlink/p/?LinkId=519255)。
  
设置 MFA 后，返回到安全&amp;合规性中心并导航到**设备管理** \> **管理设置**以完成下一步。 
  
### <a name="step-4-recommended-manage-device-security-policies"></a>步骤 4: （推荐） 管理设备安全策略

下一步是创建和部署设备安全策略，以帮助保护您的 Office 365 组织的数据。例如，可以帮助防止数据丢失，如果用户通过 5 分钟无活动之后创建到锁定设备策略丢失其设备和设备擦除后 3 登录失败。
  
在**安全&amp;合规性中心**，请转到**安全策略** \> **设备安全策略**创建设备安全策略和访问规则。 
  
![添加的设备安全策略](media/69a027f5-fbfb-482a-b850-9ccb280b8c62.png)
  
有关如何创建新策略的循序渐进说明，请参阅[创建和部署设备安全策略](create-device-security-policies.md)。
  
> [!TIP]
>  创建新策略时，您可能想要设置以允许访问和报告策略违规其中用户设备不符合策略的策略。这样可以看到多少个移动设备会受到不阻止对 Office 365 的访问的策略。> 在组织中所有人都部署一个新的策略之前，我们建议使用少量用户的设备上对其进行测试。> 此外，部署策略之前，让您知道注册 Office 365 中 MDM 的设备的潜在影响的组织。如何设置策略，根据设备不符合这些 （不兼容的设备） 都可访问 Office 365 被阻止。安装的应用程序、 照片和其他个人信息的注册在设备上，无法删除如果擦除设备后，还可能具有非标准的设备。更多信息：[擦除 Office 365 中的移动设备](wipe-a-mobile-device.md)。 
  
## <a name="make-sure-users-enroll-their-devices"></a>确保用户注册其设备

您已创建和部署的移动设备管理策略后，设备策略应用于您组织内的每个许可的 Office 365 用户将收到注册消息的下次他们登录到 Office 365 从其移动设备。他们可以访问 Office 365 电子邮件和文档之前，他们必须完成的注册和激活步骤。请参阅[注册移动设备有工作或学校](enroll-your-mobile-device.md)。
  
> [!IMPORTANT]
> 如果注册过程不支持用户的首选的语言，用户可能会在另一种语言中收到注册通知和其移动设备上的步骤。为移动设备上注册过程当前支持不是所有 Office 365 中都支持的语言。 
  
Android 或 iOS 设备的用户需要安装的公司门户应用程序注册过程的一部分。
  
## <a name="related-topics"></a>相关主题

[移动设备管理功能](capabilities-of-mobile-device-management.md)
  
[创建和部署设备安全策略](create-device-security-policies.md)
  


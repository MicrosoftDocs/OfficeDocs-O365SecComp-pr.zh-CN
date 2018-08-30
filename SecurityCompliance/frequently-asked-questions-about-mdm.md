---
title: 常见问题有关移动设备管理 Office 365 (英文）
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 3871f99c-c9db-4a23-86f9-902c1b02f58d
description: 本文包含常见问题进行了的解答有关移动设备管理 (MDM) for Office 365，可帮助您管理和保护 Office 365 中的移动设备的功能。
ms.openlocfilehash: 6c4a5b3603d392b3d83769cd0f17450ce70565be
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272267"
---
# <a name="frequently-asked-questions-about-mobile-device-management-for-office-365"></a>常见问题有关移动设备管理 Office 365 (英文）

本文包含常见问题进行了的解答有关移动设备管理 (MDM) for Office 365，可帮助您管理和保护 Office 365 中的移动设备的功能。
  
## <a name="faqs"></a>常见问题

- [如何获取 Office 365 MDM？看不到它在 Office 365 管理中心](#how-can-i-get-mdm-for-office-365-i-dont-see-it-in-the-office-365-admin-center)
    
- [如何可以开始与 MDM 中的设备管理](#how-can-i-get-started-with-device-management-in-mdm)
    
- [我尝试设置 MDM 但似乎停滞。Office 365 服务运行状况具有"设置"一段已显示。我可以做什么？](#im-trying-to-set-up-mdm-but-it-seems-stuck-the-office-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do)
    
- [如果设备注册失败，我可以做什么？](#what-can-i-do-if-device-enrollment-fails)
    
- [Office 365 MDM Intune 之间的区别是什么？](#whats-the-difference-between-intune-and-mdm-for-office-365)
    
- [策略的 MDM 如何工作？如何设置这些？禁用它们？](#how-do-policies-work-for-mdm-how-do-i-set-them-up-disable-them)
    
- [可以从切换到其他 Exchange ActiveSync 设备管理 MDM 到 Office 365？](#can-i-switch-from-exchange-activesync-device-management-to-mdm-for-office-365)
    
- [设置 MDM，但现在我想要将其删除。步骤有哪些？](#i-set-up-mdm-but-now-i-want-to-remove-it-what-are-the-steps)
    
- [仍需要帮助](#still-need-help)
    
## <a name="how-can-i-get-mdm-for-office-365-i-dont-see-it-in-the-office-365-admin-center"></a>如何获取 Office 365 MDM？看不到它在 Office 365 管理中心

我们已经完成向 Office 365 客户推出此功能。查找中的**设备管理**选项卡[转到 Office 365 安全性&amp;合规性中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)。如果您看不到它，请让我们知道。请参阅[仍需要帮助？](#still-need-help)，我们将帮助您着手展开和。 
  
## <a name="how-can-i-get-started-with-device-management-in-mdm"></a>如何可以开始与 MDM 中的设备管理

有四个入门 MDM Office 365 （了解集中[向上移动设备管理 (MDM) 在 Office 365 中](set-up-mobile-device-management.md)的详细信息） 的步骤：
  
1. **激活 mdm。** 转到[转到 Office 365 安全性&amp;合规性中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)，然后选择**设备管理**。单击**让我们开始吧**以启动的激活过程。 
    
2. **MDM 完成配置**。为您的域，这可能需要 APNs 证书配置和 DNS 记录的更新。 
    
3. **创建策略**。创建设备管理策略，并将它们应用于的[安全组中设置](create-device-security-policies.md)用户的组。我们建议您首先部署到小型测试组策略。安全中&amp;合规性中心中，选择**设备安全策略**。
    
4. **用户注册设备。** 在尝试访问 Office 365 数据 （通过使用其电子邮件客户端，例如） 时，将[注册其设备](enroll-your-mobile-device.md)到提示用户具备应用于它们的策略。 
    
## <a name="im-trying-to-set-up-mdm-but-it-seems-stuck-the-office-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>我尝试设置 MDM 但似乎停滞。Office 365 服务运行状况具有"设置"一段已显示。我可以做什么？

可能需要一些时间来大致服务供您。设置完成后，您将看到移动设备管理 Office 365 页。如果您已经等待 24 小时，状态仍为**设置**，请参阅[仍需要帮助？](#still-need-help) ，我们将帮助您判断该问题。 
  
## <a name="what-can-i-do-if-device-enrollment-fails"></a>如果设备注册失败，我可以做什么？

如果您在遇到获取注册设备的问题，首先请检查以下：
  
- 请确保，设备不已经注册了其他移动设备管理提供程序，如 Intune。
    
- 请确保设备设置为正确的日期和时间。
    
- 切换到不同 Wi-fi 或移动设备上的网络。
    
- Android 或 iOS 设备，卸载并重新 Intune 的公司门户应用程序安装在设备上。
    
如果注册仍未运行，[请尝试以下额外的故障排除步骤](troubleshoot-mdm.md)。
  
## <a name="whats-the-difference-between-intune-and-mdm-for-office-365"></a>Office 365 MDM Intune 之间的区别是什么？

这两个 MDM for Office 365 和 Intune 管理您的组织中的设备提供基于云的解决方案。使用此[-并排比较](choose-between-mdm-and-intune.md)两个服务可帮助您确定使用 Office 365 Intune 或 MDM 是否是您最适合您。 
  
## <a name="how-do-policies-work-for-mdm-how-do-i-set-them-up-disable-them"></a>策略的 MDM 如何工作？如何设置这些？禁用它们？

Office 365，您[创建策略，并将它们应用于的用户组](create-device-security-policies.md)中的 MDM 完成初始安装后[转到 Office 365 安全性&amp;合规性中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)。策略应用于的用户，策略要求用户在 Office 365 注册 MDM 在其设备之前设备可以用于访问 Office 365 数据。您设置的策略确定移动设备，例如，频率必须重置密码或是否需要数据加密的设置。 
  
我们提供用于[创建和部署设备安全策略](create-device-security-policies.md)的循序渐进说明。在安全中创建策略&amp;合规性中心，您可以通过将返回到安全禁用一个或多个策略&amp;合规性中心和编辑策略的应用组中删除。或者，您可以选择不完全删除的策略。
  
如果您想要从受策略中排除特定的用户组，可以将组添加到排除组。安全中&amp;合规性中心中，在**设备**选项卡中，选择**管理设备访问设置**，然后添加到组**是否有任何安全组，您想要排除在访问控制？** 部分。 
  
## <a name="can-i-switch-from-exchange-activesync-device-management-to-mdm-for-office-365"></a>可以从切换到其他 Exchange ActiveSync 设备管理 MDM 到 Office 365？

如果您已使用[Exchange ActiveSync 策略](https://go.microsoft.com/fwlink/?LinkId=615145)来管理移动设备，您可以开始使用 Office 365 的 MDM，按照到[设置向上移动设备管理 (MDM) 在 Office 365 中](set-up-mobile-device-management.md)的步骤。
  
当您应用到用户组的 Office 365 在 MDM 中创建的策略时，这些策略将覆盖 Exchange ActiveSync 移动设备邮箱策略和您之前创建 Exchange 管理员中心这些用户中的设备访问规则。 
  
设备中 MDM 注册 Office 365 后，将忽略任何 Exchange ActiveSync 移动设备邮箱策略或设备访问规则应用于该设备。
  
## <a name="i-set-up-mdm-but-now-i-want-to-remove-it-what-are-the-steps"></a>设置 MDM，但现在我想要将其删除。步骤有哪些？

遗憾的是，您不能只是"取消设置"MDM for Office 365 后已设置。但是，您可以通过从您已创建的设备策略中删除用户安全组中删除它的用户组。或者，通过删除设备策略，因此它们不就地和不强制执行禁用它让每个人。请参阅[How to 关闭 Office 365 中的移动设备管理](turn-off-mdm.md)。
  
## <a name="still-need-help"></a>仍需要帮助？

[![从 Office 365 社区论坛获取帮助](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![管理员：登录并创建一个服务请求](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![管理员：电话支持](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  

  


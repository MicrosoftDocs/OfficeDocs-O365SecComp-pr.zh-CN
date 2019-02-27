---
title: Office 365 电子邮件中的安全提示
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 10/6/2016
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: 介绍 EOP 和 Office 365 垃圾邮件筛选器筛选出的电子邮件的安全提示。
ms.openlocfilehash: d85eb0bde24220fbbfc12e7b5f01acec69571dee
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276282"
---
# <a name="safety-tips-in-email-messages-in-office-365"></a>Office 365 电子邮件中的安全提示

Exchange Online Protection (EOP) 和 Office 365 针对垃圾邮件、网络钓鱼和恶意软件阻止提供保护。如今, 其中一些攻击非常精心编制, 使其看起来是合法的。将邮件发送到 "垃圾邮件" 文件夹并不总是足够。现在, 当您在 outlook 或 web 上的 outlook 中检查您的电子邮件时, EOP 会自动检查发件人, 并将安全提示添加到电子邮件的顶部。 
  
安全提示 (一种由颜色编码的邮件) 将警告您可能有害的邮件。您的收件箱中的大多数邮件不会有安全提示。只有在 EOP 和 Office 365 包含可帮助阻止垃圾邮件、网络钓鱼和恶意软件攻击的信息时, 才会看到它们。如果安全提示确实显示在收件箱中, 则可以使用以下示例来了解有关每种安全提示的详细信息。
  
- 可疑邮件 (红色安全提示)。
    
    ![显示红色安全提示的屏幕截图。](media/5078a0be-e556-44a1-b169-09d780d26898.png)
  
    电子邮件中的红色安全提示意味着您收到的邮件包含可疑的内容, 如仿冒骗局。我们建议您从收件箱中删除此类电子邮件, 而无需打开它。
    
- 垃圾邮件 (黄色安全提示)。
    
    ![显示黄色安全提示的屏幕截图。](media/793c9265-ea44-48fd-a98f-804fadd4163b.png)
  
    电子邮件中的黄色安全提示意味着邮件已被标记为垃圾邮件。如果您不能识别和信任邮件的发件人, 则不要下载任何附件或图片, 也不要单击邮件中的任何链接。在 web 上的 Outlook 中, 可以单击 "垃圾邮件" 项目的黄色栏中**的 "不是垃圾**邮件", 将邮件移至您的收件箱。如果在发送到您的收件箱的邮件上显示黄色安全提示, 则可能是因为您已禁用将垃圾邮件移动到 "垃圾邮件" 文件夹。 
    
- 安全邮件 (绿色安全提示)。
    
    ![显示绿色安全提示的屏幕截图。](media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)
  
    除了不安全的邮件之外, 我们还将通过绿色安全提示告诉你我们信任的发件人发来的有效邮件。电子邮件中的绿色安全提示意味着我们检查邮件的发件人并验证其安全。Microsoft 维护此受信任发件人列表, 其中包括金融组织和经常被欺骗或模拟的人。
    
- 未筛选邮件 (灰色安全提示)。
    
    ![显示灰色安全提示的屏幕截图。](media/c4d0cf8f-08e9-4c84-beee-1d9e0b022e0a.png)
  
    我们还将告诉你当我们跳过对某个邮件的检查时, 因为它来自安全发件人列表中信任的发件人, 或者如果有邮件流规则, 可以绕过筛选。 
    
    当外部图像被阻止 (即邮件在收件箱中而不是垃圾邮件) 时, 还会显示灰色安全提示, 其中包含尚未选择下载的外部图像。
    
## <a name="working-with-safety-tips"></a>使用安全提示

始终为 web 上的 Outlook 启用安全提示, 即使每封邮件都将收到一个。Office 365 管理员可以关闭其他电子邮件客户端 (如 Outlook) 的安全提示。有关详细信息, 请参阅[在 Office 365 中启用或禁用安全提示](enable-or-disable-safety-tips.md)。
  
如果您不同意 Office 365 和 EOP 如何对邮件进行分类 (即, 它不是垃圾邮件或不合法), 您可以提交邮件进行分析以帮助提高您的体验。有关详细信息, 请参阅[在 Outlook 网页版中报告垃圾电子邮件和网络钓鱼诈骗](https://technet.microsoft.com/library/dn594557.aspx)。您还可以单击安全提示中的 "反馈" 链接以将评论直接提交给 Microsoft, 以帮助我们改进。
  
## <a name="see-also"></a>另请参阅

[启用或禁用 Office 365 中的安全提示](enable-or-disable-safety-tips.md)


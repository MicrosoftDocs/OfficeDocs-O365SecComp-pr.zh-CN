---
title: Office 365 ATP 安全链接警告页
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fc4e6ebb-5acc-4bc5-bad8-4f3407d1d3f4
ms.collection:
- M365-security-compliance
description: 获取在 Office 365 高级威胁防护工作时可能看到的警告页面的概述。
ms.openlocfilehash: bc0f0859263c72b2d058366a6268663d0dd6b9a6
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598648"
---
# <a name="office-365-atp-safe-links-warning-pages"></a>Office 365 ATP 安全链接警告页

> [!IMPORTANT]
> 本文适用于具有[Office 365 高级威胁防护](office-365-atp.md)的商业客户。 如果您使用的是 Outlook.com、Office 365 家庭版或 Office 365 个人版, 并且您正在查找有关 Outlook 中的安全链接的信息, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

[Office 365 高级威胁防护](office-365-atp.md)(ATP) 通过功能 (如[Atp 安全链接](atp-safe-links.md)、 [atp 安全附件](atp-safe-attachments.md)和[反网络钓鱼防护](anti-phishing-protection.md)) 帮助保护您的组织免受网络钓鱼企图和恶意软件的攻击。 保护准备就绪后, 将检查电子邮件和 Office 文档中的链接 (Url)。 如果 URL 被标识为可疑或恶意, 则在单击时可能会阻止您打开该 URL。 您可能会看到一个警告页面, 而不是直接转到该网站。 
  
阅读本文, 以查看可能显示的警告页的示例, 以及最近对警告页的更新。
  
## <a name="examples-of-warning-pages"></a>警告页面示例

### <a name="atp-is-scanning-the-link"></a>ATP 正在扫描链接

通过 ATP 安全链接扫描 URL。 您可能需要等待几分钟才能再次尝试链接。

![ATP 正在扫描链接](media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="a-url-is-in-a-suspicious-email-message"></a>可疑电子邮件中的 URL

该 URL 在类似于其他电子邮件的电子邮件中, 类似于其他被视为可疑的电子邮件。 建议您先仔细检查电子邮件, 然后再继续转到网站。

![此 URL 位于可疑的电子邮件中](media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="a-url-is-in-a-message-identified-as-a-phishing-attempt"></a>URL 位于标识为网络钓鱼尝试的邮件中

该 URL 位于已标识为 "网络钓鱼" 攻击的电子邮件中。 因此, 电子邮件中的所有 Url 都将被阻止。 我们建议您不要继续转到网站。

![此 URL 位于标识为网络钓鱼尝试的邮件中](media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="a-site-has-been-identified-as-malicious"></a>已将网站标识为恶意

该 URL 指向已被标识为恶意的网站。  <br/> 我们建议您不要继续转到网站。

![此网站已被标识为恶意网站](media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="a-site-is-blocked"></a>网站被阻止

为您的组织阻止该 URL。 可能会阻止 URL 的原因有多种。 我们建议您与组织的 Office 365 管理员联系。

![阻止此网站](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="an-error-has-occurred"></a>出现错误

出现了某种类型的错误, 无法打开该 URL。

![出现错误](media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

## <a name="recent-updates-to-warning-pages"></a>最近对警告页的更新

最近针对 Office 365 ATP 更新了几个警告页面。 如果您还没有看到更新的页面, 很快就会了。 这些更新包括新的配色方案、更多详细信息以及在给定警告和建议的情况下能够继续使用网站的功能。

### <a name="url-scan-in-progress"></a>正在扫描 URL

原始警告页面:

![有关正在进行的 URL 扫描的原始警告页面](media/04368763-763f-43d6-94a4-a48291d36893.png)

更新的警告页面:

![ATP 正在扫描链接](media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="malicious-site-warning"></a>恶意网站警告

原始警告页面:

![关于恶意网站的原始警告页](media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

更新的警告页面:

![此网站已被标识为恶意网站](media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="blocked-url-warning"></a>阻止的 URL 警告

原始警告页面:

![有关被阻止的 URL 的原始警告页](media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

更新的警告页面:

![阻止此网站](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="error-occurred-warning-page"></a>"发生错误" 警告页

原始警告页面:

![原始 "发生错误" 警告页](media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)

更新的警告页面:

![出现错误](media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)
   

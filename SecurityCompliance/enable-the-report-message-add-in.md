---
title: 启用报告消息加载项
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/28/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: 了解如何启用报告消息加载项的 Outlook 和 Outlook web，为各个用户或您的整个组织上。
ms.openlocfilehash: 2260f8823132d23e0e1f57a421fd223ea3ab14bd
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23229994"
---
# <a name="enable-the-report-message-add-in"></a>启用报告消息加载项

报告消息外接程序 Outlook 中，使人们能够轻松地分类的电子邮件安全还是恶意，向 Microsoft 和报告或其关联公司进行分析。Microsoft 使用这些提交来提高效率的电子邮件保护技术。
  
如果您是单个用户，您可以启用报告消息外接程序自己。 
  
如果您的 Exchange Online 管理员，可以为组织启用的邮件报告加载项。
    
## <a name="get-the-report-message-add-in-for-yourself"></a>获取外接程序为自己的报告邮件

1. 转到[https://store.office.com](https://store.office.com)，并搜索报告消息加载项。
    
2. 选择**立即获取**（或**添加**）。 
    
3. 查看相应条款的使用和隐私策略。然后选择**继续**。 
    
4. 登录到 Office 365 电子邮件使用您的工作或学校 （供业务使用） 的帐户或您的 Microsoft 帐户 （供个人使用）。
    
外接程序是安装并启用后，您将看到以下图标： 

- 在 Outlook 中图标如下所示： </br> ![Outlook 报表消息外接程序图标](media/OutlookReportMessageIcon.png)</br>
- 在 Outlook Web App 中图标如下所示：</br>![Outlook Web 报告消息外接程序图标](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)</br>

  
下一步，以了解如何[使用报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>获取和报告消息外接程序为组织启用

> [!IMPORTANT]
> 您必须是 Exchange Online 管理员才能执行此任务。
  
1. 转到[https://portal.office.com](https://portal.office.com)和使用工作或学校帐户登录。 
    
2. 选择**管理**以转到管理中心。 
    
3. 选择**管理中心** \> **Exchange**转到 Exchange 管理员中心 (EAC)。 
    
4. 选择**组织** \> **外接程序**。 
    
5. 选择**+** \> **从 Office 商店添加**。 
    
6. 搜索报告消息。
    
7. 在**应用程序结果**列表中，查找**报告消息**，，然后选择**立即获取**（或**添加**）。 
    
8. 查看相应条款的使用和隐私策略。然后选择**继续**。 
    
    ![单击继续以接受条款和隐私策略](media/3c813cd6-1601-4791-97dc-f8edbbd3fb6b.png)
  
9. 在确认屏幕中，选择**是**。 
    
10. 已安装的邮件报告加载项后，您必须启用它。为此，请按照下列步骤：
    
1. 返回到 EAC 中，并刷新浏览器窗口。
    
2. 选择**组织** \> **外接程序**。 
    
3. 在加载项列表中，选择**报告消息**。 
    
    ![在 EAC 中，您可以启用报告消息加载项的 Outlook](media/b496743c-55fa-4cdb-aa06-0b2a7aec6dab.png)
  
4. 选择**编辑**，然后选择要启用外接程序选项。 
    
    ![启用邮件报告加载项在 EAC 中](media/578b1b66-3620-4a8a-9819-1c9cc6836f37.png)
  
5. 选择**保存**。 
    
> [!TIP]
> 外接程序是安装并启用后，您的组织中的人员将看到以下图标： 
  
接下来，了解如何[使用报告消息外接程序](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)和设置规则以查看报告的电子邮件。
  
### <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>设置规则来获取一份报告的用户的电子邮件

> [!IMPORTANT]
> 您必须是 Exchange Online 管理员才能执行此任务。
  
您可以设置规则，若要获取的电子邮件组织中的用户报告的副本。在下载并为组织启用报告消息外接程序后执行此操作。
  
1. 在 EAC 中，选择**邮件流** \> **规则**。 
    
2. 选择**+** \> **创建新规则**。 
    
3. 在**名称**框中，键入一个名称，例如提交。
    
4. 在**以下情况应用此规则**列表中，选择**在收件人地址包括...**。 
    
5. 在**指定词语或短语**屏幕中，添加 junk@office365.microsoft.com 和 phish@office365.microsoft.com，，然后选择**确定**。 
    
    ![指定规则的垃圾邮件和网络钓鱼电子邮件地址](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)
  
6. 在 **...请执行以下**列表中，选择**密件抄送邮件到...**。 
    
7. 添加的全局管理员、 安全管理员和/或安全读者用户应收到人员报告给 Microsoft，每个电子邮件的副本，然后选择**确定**。 
    
    ![添加全局或安全管理员以接收报告的每封邮件的副本](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)
  
8. 选择**审核严重性级别与此规则**，然后选择**中等**。 
    
9. 在**选择此规则的模式**，下选择**强制**。 
    
    ![设置规则来获取每个报告的邮件的副本](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)
  
10. 选择**保存**。 
    
与就地此规则，当您的组织中的某人报告电子邮件的邮件报告加载项，使用您的全局管理员、 安全管理员和/或安全读者将收到该邮件的副本。这些信息使您可以设置或调整策略，如[Office 365 ATP 安全链接](atp-safe-links.md)策略。 
  
## <a name="related-topics"></a>相关主题

[使用报告消息外接程序](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[Office 365 高级威胁防护](office-365-atp.md)
  


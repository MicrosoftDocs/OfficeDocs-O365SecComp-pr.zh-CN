---
title: 使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
description: 您可以创建传输规则来设置电子邮件的垃圾邮件可信度 (SCL)。SCL 是判断某个邮件在多大程度上是垃圾邮件的衡量手段。"垃圾邮件"是未经请求的（并且通常是不必要的）电子邮件。根据 SCL 评级的不同，该服务对邮件采取不同的操作。例如，您可能想要使从您组织内部人员发送的邮件规避垃圾邮件内容筛选，因为您相信从内部同事发送的邮件并非垃圾邮件。使用传输规则设置邮件的 SCL 值可提高您处理垃圾邮件的控制能力。
ms.openlocfilehash: 7abd0d1881374b1f2a4bd32ee480445f7683d1b3
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002891"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)

您可以创建传输规则来设置电子邮件的垃圾邮件可信度 (SCL)。SCL 是判断某个邮件在多大程度上是垃圾邮件的衡量手段。"垃圾邮件"是未经请求的（并且通常是不必要的）电子邮件。根据 SCL 评级的不同，该服务对邮件采取不同的操作。例如，您可能想要使从您组织内部人员发送的邮件规避垃圾邮件内容筛选，因为您相信从内部同事发送的邮件并非垃圾邮件。使用传输规则设置邮件的 SCL 值可提高您处理垃圾邮件的控制能力。 
  
 **在开始之前，您需要知道什么？**
  
- 估计完成该过程的时间：10 分钟。
    
- 您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)或[功能在 EOP 中的权限](eop/feature-permissions-in-eop.md)中的"传输规则"条目。 
    
- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
### <a name="to-create-a-transport-rule-that-sets-the-scl-of-a-message"></a>创建设置邮件的 SCL 的传输规则

1. 在 Exchange 管理员中心 (EAC) 中，选择**邮件流** \> **规则**。
    
2. 选择**新建**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后选择**创建新规则**。
    
3. 指定规则名称。
    
4. 选择**更多选项**，并在**以下情况应用此规则**，指定将触发的操作，您将设置为此规则 （这是设置 SCL 值） 的条件。
    
    例如，您可以设置**发件人** \> **是内部/外部**，然后**选择发件人位置**对话框中，在选择**组织内部**，并选择**确定**。</br>
    ![选择发件人位置](media/EOP-ETR-SetSCL-1.jpg)
  
5. 在**执行以下操作**，下选择**修改邮件属性** \> **将垃圾邮件可信度 (SCL) 设置**。
  
6. **指定 SCL**对话框中，选择下列值之一，然后选择**确定**:
    
  - **绕过垃圾邮件筛选**-的 SCL 为-1，这意味着内容筛选不会执行此设置。 
    
  - **0-4** -将 SCL 设置为下列值之一时，邮件都将传递到其他处理的内容筛选器。 
    
  - 将应用**5、 6** -当您将 SCL 设置为其中一个值，适用的内容筛选器策略中指定的**垃圾邮件**的操作。默认情况下操作是将邮件发送到收件人的垃圾邮件文件夹。 
    
  - 将应用**7-9** -当您将 SCL 设置为其中一个值，适用的内容筛选器策略中指定的**高可信度垃圾邮件**的操作。默认情况下操作是将邮件发送到收件人的垃圾邮件文件夹。 
    
    有关如何配置内容筛选器策略的详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。
    
7. 指定该规则的其他属性，然后选择**保存**。
    
    > [!TIP]
    > 有关可以为此规则选择或指定的其他属性的详细信息，请参阅[Use the EAC to create a transport rule](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC)。 
  
## <a name="how-do-you-know-this-worked"></a>您如何知道操作成功？

若要验证此过程正常工作，向您的组织内的某人发送一封电子邮件，并验证对邮件执行的操作按预期方式。例如，如果**将垃圾邮件可信度 (SCL) 设置**为**绕过垃圾邮件筛选**，然后邮件应发送给指定的收件人的收件箱。但是，如果**将垃圾邮件可信度 (SCL) 设置**为**9**，以及您适用的内容筛选器策略的**高可信度垃圾邮件**操作是将邮件移动到垃圾邮件文件夹，然后邮件应发送到指定收件人的垃圾邮件文件夹。 
  


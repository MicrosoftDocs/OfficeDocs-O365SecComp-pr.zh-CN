---
title: 使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online Protection 中设置邮件的 SCL。
ms.openlocfilehash: e07b90ab1ab004c39ef36b2aa744ca87120c11fe
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692741"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)

您可以创建邮件流规则 (也称为传输规则), 以设置电子邮件的垃圾邮件可信度 (SCL)。 SCL 是判断某个邮件在多大程度上是垃圾邮件的衡量手段。 "垃圾邮件"是未经请求的（并且通常是不必要的）电子邮件。 根据 SCL 评级的不同，该服务对邮件采取不同的操作。 例如，您可能想要使从您组织内部人员发送的邮件规避垃圾邮件内容筛选，因为您相信从内部同事发送的邮件并非垃圾邮件。 使用邮件流规则设置邮件的 SCL 值为您提供了对处理垃圾邮件的更多控制。 
  
 **在开始之前，您需要知道什么？**
  
- 估计完成该过程的时间：10 分钟。
    
- 您必须先获得权限，然后才能执行此过程或多个过程。 若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)或 EOP 中的[功能权限](eop/feature-permissions-in-eop.md)中的 "邮件流规则" 条目。 
    
- 若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>创建设置邮件 SCL 的邮件流规则

1. 在 Exchange 管理中心 (EAC) 中, 选择 "**邮件流** \> **规则**"。
    
2. 选择 "**新建**!["](media/ITPro-EAC-AddIcon.gif)"添加" 图标, 然后选择 "**创建新规则**"。
    
3. 指定规则名称。
    
4. 选择 "**更多选项**", 然后在 "在**以下情况应用此规则**" 下, 指定将触发要为此规则设置的操作 (即设置 SCL 值) 的条件。
    
    例如, 您可以将**发件人** \> **设置为 "内部/外部**", 然后在 "**选择发件人位置**" 对话框中, 选择**组织内部**, 然后选择 **"确定"**。<br/>
    ![选择发件人位置](media/EOP-ETR-SetSCL-1.jpg)
  
5. 在 "**执行以下操作**" 下, 选择 "**修改邮件属性** \> **" "设置垃圾邮件可信度 (SCL)"**。
  
6. 在“指定 SCL”**** 对话框中，选择以下值之一，然后选择“确定”****：
    
  - **绕过垃圾邮件筛选**-这会将 SCL 设置为-1, 这意味着不会执行内容筛选。 
    
  - **0-4** -当您将 SCL 设置为这些值之一时, 邮件将被传递到内容筛选器进行其他处理。 
    
  - **5, 6** -当您将 SCL 设置为这些值之一时, 将应用在适用的内容筛选器策略中为**垃圾邮件**指定的操作。 默认情况下，该操作是将邮件发送至收件人的"垃圾邮件"文件夹。 
    
  - **7-9** -当您将 SCL 设置为这些值之一时, 将应用为适用的内容筛选器策略中的**高可信度垃圾邮件**指定的操作。 默认情况下，该操作是将邮件发送至收件人的"垃圾邮件"文件夹。 
    
    有关如何配置内容筛选器策略的详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。
    
7. 指定该规则的其他属性，并选择“保存”****。
    
    > [!TIP]
    > 有关可以为此规则选择或指定的其他属性的详细信息, 请参阅[使用 EAC 创建邮件流规则](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules)。 
  
## <a name="how-do-you-know-this-worked"></a>您如何知道操作成功？

要验证此步骤是否能正常工作，请发送电子邮件至组织中的某位同事，并验证是否对该邮件执行预期的操作。 例如, 如果**将垃圾邮件可信度 (SCL) 设置**为 "**绕过垃圾邮件筛选**", 则应将邮件发送到指定收件人的收件箱。 但是, 如果**将垃圾邮件可信度 (SCL) 设置**为**9**, 并且适用的内容筛选器策略的**高可信度垃圾邮件**操作是将邮件移动到 "垃圾邮件" 文件夹, 则应将邮件发送到指定的收件人的 "垃圾邮件" 文件夹。 
  


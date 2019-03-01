---
title: 使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)
ms.author: tracyp
author: MSFTTracyP
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
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Exchange Online Protection 中设置邮件的 SCL。
ms.openlocfilehash: 48569087fe8455dbb5500add435430ec8e78ea30
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341343"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>使用邮件流规则设置邮件中的垃圾邮件可信度 (SCL)

您可以创建邮件流规则 (也称为传输规则), 以设置电子邮件的垃圾邮件可信度 (SCL)。SCL 可衡量邮件是垃圾邮件的可能性。垃圾邮件是未经请求的 (通常是不必要的) 电子邮件。根据邮件的 SCL 分级, 该服务对邮件采取不同的操作。例如, 您可能希望对从组织内部人员发送的邮件绕过垃圾邮件内容筛选, 因为您信任从某个同事内部发送的邮件不是垃圾邮件。使用邮件流规则设置邮件的 SCL 值为您提供了对处理垃圾邮件的更多控制。 
  
 **在开始之前，您需要知道什么？**
  
- 估计完成该过程的时间：10 分钟。
    
- 您需要先分配权限, 然后才能执行此过程或过程。若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)或 EOP 中的[功能权限](eop/feature-permissions-in-eop.md)中的 "邮件流规则" 条目。 
    
- 若要了解本主题中的过程可能适用的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>创建设置邮件 SCL 的邮件流规则

1. 在 Exchange 管理中心 (EAC) 中, 选择 "**邮件流** \> **规则**"。
    
2. 选择 "**新建**!["](media/ITPro-EAC-AddIcon.gif)"添加" 图标, 然后选择 "**创建新规则**"。
    
3. 指定规则名称。
    
4. 选择 "**更多选项**", 然后在 "在**以下情况应用此规则**" 下, 指定将触发要为此规则设置的操作 (即设置 SCL 值) 的条件。
    
    例如, 您可以将**发件人** \> **设置为 "内部/外部**", 然后在 "**选择发件人位置**" 对话框中, 选择**组织内部**, 然后选择 **"确定"**。<br/>
    ![选择发件人位置](media/EOP-ETR-SetSCL-1.jpg)
  
5. 在 "**执行以下操作**" 下, 选择 "**修改邮件属性** \> **" "设置垃圾邮件可信度 (SCL)"**。
  
6. 在 "**指定 SCL** " 对话框中, 选择以下值之一, 然后选择 **"确定"**:
    
  - **绕过垃圾邮件筛选**-这会将 SCL 设置为-1, 这意味着不会执行内容筛选。 
    
  - **0-4** -当您将 SCL 设置为这些值之一时, 邮件将被传递到内容筛选器进行其他处理。 
    
  - **5, 6** -当您将 SCL 设置为这些值之一时, 将应用在适用的内容筛选器策略中为**垃圾邮件**指定的操作。默认情况下, 该操作是将邮件发送到收件人的 "垃圾邮件" 文件夹。 
    
  - **7-9** -当您将 SCL 设置为这些值之一时, 将应用为适用的内容筛选器策略中的**高可信度垃圾邮件**指定的操作。默认情况下, 该操作是将邮件发送到收件人的 "垃圾邮件" 文件夹。 
    
    有关如何配置内容筛选器策略的详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。
    
7. 指定规则的其他属性, 然后选择 "**保存**"。
    
    > [!TIP]
    > 有关可以为此规则选择或指定的其他属性的详细信息, 请参阅[使用 EAC 创建邮件流规则](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules)。 
  
## <a name="how-do-you-know-this-worked"></a>如何知道操作成功？

若要验证此过程是否正常运行, 请将电子邮件发送给组织内部的某个人, 并验证对邮件执行的操作是否符合预期。例如, 如果**将垃圾邮件可信度 (SCL) 设置**为 "**绕过垃圾邮件筛选**", 则应将邮件发送到指定收件人的收件箱。但是, 如果**将垃圾邮件可信度 (SCL) 设置**为**9**, 并且适用的内容筛选器策略的**高可信度垃圾邮件**操作是将邮件移动到 "垃圾邮件" 文件夹, 则应将邮件发送到指定的收件人的 "垃圾邮件" 文件夹。 
  


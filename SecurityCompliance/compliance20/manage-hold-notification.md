---
title: 管理保留通知
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 0b1b20a8b41803a945bc9f5c39cd0618c420b0c0
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151734"
---
# <a name="manage-hold-notifications"></a>管理保留通知

启动法律保留通知工作流后, 可以利用高级电子数据展示来跟踪您的通信的状态。 "通信" 选项卡展示了高级电子数据展示事例中的所有保留通知。 你可以在此处查看详细信息, 如已分配的保管人数量或已确认通知。

## <a name="view-communication-details"></a>查看通信详细信息

### <a name="track-acknowledgements"></a>跟踪确认

从**通信**中选择通信后, 可以查看已确认保留通知的保管人列表。 

### <a name="preview-acknowledgements"></a>预览确认

在 "通信详细信息" 浮出控件中, 可以预览有关合法保留通信的详细信息。 在**预览**面板中, 你将能够查看你的法律保留通知的快速快照以及工作流通知的设置和内容。 预览面板还将显示关于保管人已确认通知的详细信息。

## <a name="taking-action-on-existing-communications"></a>对现有通信采取操作

### <a name="re-send-a-hold-notice"></a>重新发送保留通知

有时, 保管人会在日常工作中失去对其电子邮件的跟踪。 或者, 对于长期运行的诉讼, 保管人可能会进入, 并要求您重新发送通知。 在围绕法律封存通知管理工作流时, 您可能需要重新发送通知, 以使其返回到 "用户邮箱的顶部"。

你可以通过以下方式将保留通知重新发送给你的管理员:
1. 导航到**Security And 合规性 _GT_ 高级电子数据展示**中的事例。
2. 选择了事例后, 导航到 "**通信**" 选项卡。
3. 若要将合法保留通知重新发送给管理员, 请选择相应的通信, 然后单击 "**重新发送**" 选项。
4. 如果管理员尚未确认其保留通知, 则会重新启动提醒和升级流。 如果管理员已确认保留通知, 则保管人将仅收到初始保留通知的副本。

> [!NOTE]
> 只能将合法保留通知重新发送给分配给该通信的保管人。 

### <a name="edit-a-communication"></a>编辑通信

#### <a name="update-preservation-requirements"></a>更新保留要求
  
在这种情况下, 可能需要保管人来保留比以前所指示的更多或少的数据。 在电子数据展示术语中, 需要使用更新后的内容重新发布保留通知。

若要更新初始保留通知的内容, 请执行以下操作:

1. 导航到**Security And 合规性 _GT_ 高级电子数据展示**中的事例。
2. 选择了事例后, 导航到 "**通信**" 选项卡。
3. 选择您想要更新的保留通知, 然后单击 "**编辑**"。
4. 在 "编辑工作流" 中, 选择 "**定义门户内容**" 并更新通知的内容。 
5. 单击“保存”****。 保存后, 系统会将重新发布通知发送给当前分配了法定保留通知的所有保管人。 此外, 如果启用了提醒/上报通知, 则这些工作流也将重新启动。 


#### <a name="update-legal-hold-notifications-and-settings"></a>更新合法保留通知和设置

当您更新发布、发布、重新颁发、提醒或上报通知的内容或设置时, 这些更改将应用于工作流生成的所有未来通信。

## <a name="related-information"></a>相关信息 

- [创建合法保留通知](create-hold-notification.md)
    
- [确认保留通知](acknowledge-hold-notification.md)
    
- [向事例添加保管人](add-custodians-to-case.md)
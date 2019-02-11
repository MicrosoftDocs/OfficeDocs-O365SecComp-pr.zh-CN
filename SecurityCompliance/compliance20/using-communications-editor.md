---
title: 使用通信编辑器
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: b148ff1a77cd9225a26f98e7612e9fb5b57331e3
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706053"
---
# <a name="use-the-communications-editor"></a>使用通信编辑器

定义门户内容的内容，如法律保留通知以及相关的提醒升级，您可以利用 Communications 编辑器格式和动态自定义您的内容。

## <a name="rich-text-editor"></a>格式文本编辑器 

Communications 编辑器允许用户自定义使用编辑器选项的文本。例如，用户可以更改字体类型，创建项目符号列表、 突出显示内容和详细信息。 

## <a name="merge-field-variables"></a>合并域变量

您可以利用电子邮件合并变量从 Communications 编辑器要将自定义的 custodian 属性嵌入通信的正文文本。发送到 custodian 时，将相应的字段与填充合并域。例如，当发送到 custodian John Smith，则翻译合并域 [Custodian 名] 的相应名称。 

您可以通过选择格式文本编辑器控件顶部**合并域**图标使用电子邮件合并域。将基于用户的指针的位置禁用添加占位符。 

### <a name="list-of-merge-field-variables"></a>合并字段变量的列表

| 字段名称                  | 字段的详细信息 | 
| :------------------- | :------------------- |
| 显示名称  | Custodian 的姓和姓。 | 
| 确认链接 | 记录每个 custodian 确认自定义的链接。|                 |
| 门户链接     | 自定义的链接 custodian 的合规性门户。|                |
| 发出部主管                   | 指定颁发部主管电子邮件地址。|                   |
| 发布日期                   | 请注意颁发 (UTC) 的日期。              |
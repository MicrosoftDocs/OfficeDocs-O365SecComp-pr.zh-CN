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
ms.openlocfilehash: 107f45510bcf70942c6f03bdfed0a9090f1d83c0
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607455"
---
# <a name="using-the-communications-editor"></a>使用 Communications 编辑器
定义门户内容的内容，如法律保留通知以及相关的提醒升级，您可以利用 Communications 编辑器格式和动态自定义您的内容。

## <a name="rich-text-editor"></a>格式文本编辑器 

Communications 编辑器允许用户自定义使用编辑器选项的文本。例如，用户可以更改字体类型，创建项目符号列表、 突出显示内容和详细信息。 

<<include screenshot>>

## <a name="merge-field-variables"></a>合并域变量

您可以利用电子邮件合并变量从 Communications 编辑器要将自定义的 custodian 属性嵌入通信的正文文本。发送到 custodian 时，将相应的字段与填充合并域。例如，当发送到 custodian John Smith，则翻译合并域 [Custodian 名] 的相应名称。 

您可以通过选择格式文本编辑器控件顶部**合并域**图标使用电子邮件合并域。将基于用户的指针的位置禁用添加占位符。 

### <a name="list-of-merge-field-variables"></a>合并字段变量的列表
| 字段名称                  | 字段的详细信息 | 
| :------------------- | :-------------------: |
| 显示名称  | Custodian 的姓氏和名字 | 
| 确认链接                 | 记录每个 custodian 确认的自定义的链接                 |
| 门户链接     | Custodian 的合规性门户的自定义的链接                 |
| 发出部主管                   | 指定颁发部主管电子邮件地址                   |
| 发布日期                   | 请注意颁发 (UTC) 的日期              |
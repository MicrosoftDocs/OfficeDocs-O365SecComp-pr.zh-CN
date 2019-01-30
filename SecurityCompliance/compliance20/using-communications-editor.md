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
# <a name="using-the-communications-editor"></a><span data-ttu-id="919cf-102">使用 Communications 编辑器</span><span class="sxs-lookup"><span data-stu-id="919cf-102">Using the Communications Editor</span></span>
<span data-ttu-id="919cf-103">定义门户内容的内容，如法律保留通知以及相关的提醒升级，您可以利用 Communications 编辑器格式和动态自定义您的内容。</span><span class="sxs-lookup"><span data-stu-id="919cf-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="919cf-104">格式文本编辑器</span><span class="sxs-lookup"><span data-stu-id="919cf-104">Rich-Text Editor</span></span> 

<span data-ttu-id="919cf-p101">Communications 编辑器允许用户自定义使用编辑器选项的文本。例如，用户可以更改字体类型，创建项目符号列表、 突出显示内容和详细信息。</span><span class="sxs-lookup"><span data-stu-id="919cf-p101">The Communications Editor allows user to customize the text using the editor options. For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

<<include screenshot>>

## <a name="merge-field-variables"></a><span data-ttu-id="919cf-107">合并域变量</span><span class="sxs-lookup"><span data-stu-id="919cf-107">Merge Field Variables</span></span>

<span data-ttu-id="919cf-p102">您可以利用电子邮件合并变量从 Communications 编辑器要将自定义的 custodian 属性嵌入通信的正文文本。发送到 custodian 时，将相应的字段与填充合并域。例如，当发送到 custodian John Smith，则翻译合并域 [Custodian 名] 的相应名称。</span><span class="sxs-lookup"><span data-stu-id="919cf-p102">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text. When sent to the custodian, the merge field will be populated with the corresponding field. For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="919cf-p103">您可以通过选择格式文本编辑器控件顶部**合并域**图标使用电子邮件合并域。将基于用户的指针的位置禁用添加占位符。</span><span class="sxs-lookup"><span data-stu-id="919cf-p103">You can use email merge fields by selecting the **Merge Field** icons on the top of the rich-text editor control. The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="919cf-113">合并字段变量的列表</span><span class="sxs-lookup"><span data-stu-id="919cf-113">List of Merge Field Variables</span></span>
| <span data-ttu-id="919cf-114">字段名称</span><span class="sxs-lookup"><span data-stu-id="919cf-114">Field Name</span></span>                  | <span data-ttu-id="919cf-115">字段的详细信息</span><span class="sxs-lookup"><span data-stu-id="919cf-115">Field Details</span></span> | 
| :------------------- | :-------------------: |
| <span data-ttu-id="919cf-116">显示名称</span><span class="sxs-lookup"><span data-stu-id="919cf-116">Display Name</span></span>  | <span data-ttu-id="919cf-117">Custodian 的姓氏和名字</span><span class="sxs-lookup"><span data-stu-id="919cf-117">Custodian's first and last name</span></span> | 
| <span data-ttu-id="919cf-118">确认链接</span><span class="sxs-lookup"><span data-stu-id="919cf-118">Acknowledgement Link</span></span>                 | <span data-ttu-id="919cf-119">记录每个 custodian 确认的自定义的链接</span><span class="sxs-lookup"><span data-stu-id="919cf-119">Customized link to record each custodian's acknowledgement</span></span>                 |
| <span data-ttu-id="919cf-120">门户链接</span><span class="sxs-lookup"><span data-stu-id="919cf-120">Portal Link</span></span>     | <span data-ttu-id="919cf-121">Custodian 的合规性门户的自定义的链接</span><span class="sxs-lookup"><span data-stu-id="919cf-121">Customized link for the custodian's Compliance Portal</span></span>                 |
| <span data-ttu-id="919cf-122">发出部主管</span><span class="sxs-lookup"><span data-stu-id="919cf-122">Issuing Officer</span></span>                   | <span data-ttu-id="919cf-123">指定颁发部主管电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="919cf-123">Email address of the specified issuing officer</span></span>                   |
| <span data-ttu-id="919cf-124">发布日期</span><span class="sxs-lookup"><span data-stu-id="919cf-124">Issuing Date</span></span>                   | <span data-ttu-id="919cf-125">请注意颁发 (UTC) 的日期</span><span class="sxs-lookup"><span data-stu-id="919cf-125">date that the notice was issued (UTC)</span></span>              |
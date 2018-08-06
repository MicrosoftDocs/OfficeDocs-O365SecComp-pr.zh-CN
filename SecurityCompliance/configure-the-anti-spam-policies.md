---
title: 配置反垃圾邮件策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
description: 反垃圾邮件筛选通过默认反垃圾邮件策略（连接筛选器、垃圾邮件筛选器和出站垃圾邮件）在全公司自动启用。作为管理员，您可以查看和编辑，但不能删除默认反垃圾邮件策略，以最适合贵组织的需求。更精确地讲，您也可以创建自定义策略，并将其应用到特定的用户、组或者组织中的域。默认情况下，自定义策略优先于默认策略，但您可以更改策略的优先顺序。
ms.openlocfilehash: b96620705b0a62b8e8f7804f518651a10e0a63c1
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026249"
---
# <a name="configure-the-anti-spam-policies"></a>配置反垃圾邮件策略

反垃圾邮件筛选通过默认反垃圾邮件策略（连接筛选器、垃圾邮件筛选器和出站垃圾邮件）在全公司自动启用。作为管理员，您可以查看和编辑，但不能删除默认反垃圾邮件策略，以最适合贵组织的需求。更精确地讲，您也可以创建自定义策略，并将其应用到特定的用户、组或者组织中的域。默认情况下，自定义策略优先于默认策略，但您可以更改策略的优先顺序。 
  
有关配置反垃圾邮件策略的详细信息，请参阅以下主题：
  
[配置连接筛选器策略](configure-the-connection-filter-policy.md)
  
[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> 为独立 EOP 客户： 默认情况下，EOP 内容筛选器将垃圾邮件检测到的邮件发送到每个收件人的垃圾邮件文件夹。但是，为了确保**移动到垃圾邮件文件夹的邮件**操作将处理的本地邮箱，必须配置这两种 Exchange 传输规则来检测垃圾邮件邮件头由 EOP 添加您的本地服务器上。有关详细信息，请参阅[确保垃圾邮件被路由到每个用户的垃圾邮件文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 
  
[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)
  


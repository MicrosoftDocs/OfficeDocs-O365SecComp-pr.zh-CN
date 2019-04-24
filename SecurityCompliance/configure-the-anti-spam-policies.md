---
title: 配置反垃圾邮件策略
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: 反垃圾邮件筛选通过默认反垃圾邮件策略（连接筛选器、垃圾邮件筛选器和出站垃圾邮件）在全公司自动启用。作为管理员，您可以查看和编辑，但不能删除默认反垃圾邮件策略，以最适合贵组织的需求。更精确地讲，您也可以创建自定义策略，并将其应用到特定的用户、组或者组织中的域。默认情况下，自定义策略优先于默认策略，但您可以更改策略的优先顺序。
ms.openlocfilehash: 992885a394031e133008f28a455383fc2f3f0616
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260800"
---
# <a name="configure-the-anti-spam-policies"></a>配置反垃圾邮件策略

反垃圾邮件筛选通过默认反垃圾邮件策略（连接筛选器、垃圾邮件筛选器和出站垃圾邮件）在全公司自动启用。作为管理员，您可以查看和编辑，但不能删除默认反垃圾邮件策略，以最适合贵组织的需求。更精确地讲，您也可以创建自定义策略，并将其应用到特定的用户、组或者组织中的域。默认情况下，自定义策略优先于默认策略，但您可以更改策略的优先顺序。 
  
有关配置反垃圾邮件策略的详细信息，请参阅以下主题：
  
[配置连接筛选器策略](configure-the-connection-filter-policy.md)
  
[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> 对于 EOP 独立客户：默认情况下，EOP 内容筛选器将检测到的垃圾邮件发送到每个收件人的"垃圾邮件"文件夹。 但是, 为了确保 "**将邮件移动到垃圾邮件文件夹**" 操作可用于内部部署邮箱, 必须在您的本地服务器上配置两个 Exchange 邮件流规则 (也称为传输规则), 以检测添加的垃圾邮件头EOP. 有关详细信息，请参阅[确保垃圾邮件已路由到每个用户的"垃圾邮件"文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 
  
[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)
  


---
title: Office 365 安全事件响应
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
ms.audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: 此解决方案告诉您在 Office 365 中最常见的网络安全攻击可能是什么, 以及如何对其进行响应
ms.openlocfilehash: 473a7db30df72ecbe0bdc58d578f4c82c31beaca
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217262"
---
# <a name="office-365-security-incident-response"></a><span data-ttu-id="7cc72-103">Office 365 安全事件响应</span><span class="sxs-lookup"><span data-stu-id="7cc72-103">Office 365 Security Incident Response</span></span>

 <span data-ttu-id="7cc72-104">**摘要:** 此解决方案告诉你在 Office 365 中最常见的网络安全攻击的指标, 如何正确确认任何给定的攻击以及如何对其做出响应。</span><span class="sxs-lookup"><span data-stu-id="7cc72-104">**Summary:** This solution tells you what the indicators are for the most common cyber-security attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>
  
## <a name="overview"></a><span data-ttu-id="7cc72-105">概述</span><span class="sxs-lookup"><span data-stu-id="7cc72-105">Overview</span></span>
<span data-ttu-id="7cc72-p101">并不是所有的网络攻击都可以 thwarted。攻击者经常在防御策略中寻找新的弱点, 或者他们在利用旧弱点。了解如何识别攻击允许您更快地响应它, 从而缩短了安全事件的持续时间。</span><span class="sxs-lookup"><span data-stu-id="7cc72-p101">Not all cyber attacks can be thwarted. Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones. Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="7cc72-p102">本系列文章可帮助您了解特定类型的攻击在 Office 365 中的外观, 并提供您可以采取的措施来做出响应。它们是快速入门点以了解:</span><span class="sxs-lookup"><span data-stu-id="7cc72-p102">This series of article helps you understand what a particular type of attack might look like in Office 365 and gives you steps you can take to respond. They are quick entry points to understanding:</span></span>
 
- <span data-ttu-id="7cc72-111">什么是攻击以及它的工作原理。</span><span class="sxs-lookup"><span data-stu-id="7cc72-111">What the attack is and how it works.</span></span>
- <span data-ttu-id="7cc72-112">应查找的标志 (称为 "泄露" (IOC)) 以及如何查找它们。</span><span class="sxs-lookup"><span data-stu-id="7cc72-112">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>
- <span data-ttu-id="7cc72-113">如何正确地确认攻击。</span><span class="sxs-lookup"><span data-stu-id="7cc72-113">How to positively confirm the attack.</span></span>
- <span data-ttu-id="7cc72-114">减少攻击并在将来更好地保护组织的步骤。</span><span class="sxs-lookup"><span data-stu-id="7cc72-114">Steps to take to cut off the attack and better protect your organization in the future.</span></span>
- <span data-ttu-id="7cc72-115">指向有关每种攻击类型的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="7cc72-115">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="7cc72-116">每月查看一次, 在一段时间后将添加更多文章。</span><span class="sxs-lookup"><span data-stu-id="7cc72-116">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="7cc72-117">检测和修正文章</span><span class="sxs-lookup"><span data-stu-id="7cc72-117">Detect and remediate articles</span></span>

- [<span data-ttu-id="7cc72-118">检测和修正 Office 365 中的非法授权</span><span class="sxs-lookup"><span data-stu-id="7cc72-118">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)
- [<span data-ttu-id="7cc72-119">在 Office 365 中检测并修正 Outlook 规则和自定义窗体注入攻击</span><span class="sxs-lookup"><span data-stu-id="7cc72-119">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)
 
## <a name="incident-response-articles"></a><span data-ttu-id="7cc72-120">事件响应文章</span><span class="sxs-lookup"><span data-stu-id="7cc72-120">Incident response articles</span></span>

- [<span data-ttu-id="7cc72-121">响应 Office 365 中遭到入侵的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="7cc72-121">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="7cc72-122">安全的 Office 365, 如 cybersecurity pro</span><span class="sxs-lookup"><span data-stu-id="7cc72-122">Secure Office 365 like a cybersecurity pro</span></span>
<span data-ttu-id="7cc72-p103">您的 Office 365 订阅附带了一组功能强大的安全功能, 可用于保护您的数据和用户。 使用[Office 365 安全路线图: 前30天、90天和更高版本的首要优先级](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352), 以实现 Microsoft 建议的保护 Office 365 租户的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="7cc72-p103">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.  Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>
- <span data-ttu-id="7cc72-p104">在前30天内要完成的任务。 这些值会立即生效, 并对用户造成影响较小。</span><span class="sxs-lookup"><span data-stu-id="7cc72-p104">Tasks to accomplish in the first 30 days.  These have immediate affect and are low-impact to your users.</span></span>
- <span data-ttu-id="7cc72-p105">要在90天内完成的任务。这些工作需要花一点时间来进行规划和实施, 但大大提高了安全状况</span><span class="sxs-lookup"><span data-stu-id="7cc72-p105">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture</span></span>
- <span data-ttu-id="7cc72-p106">超过90天。这些增强功能将在您的前90天工作中构建。</span><span class="sxs-lookup"><span data-stu-id="7cc72-p106">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>







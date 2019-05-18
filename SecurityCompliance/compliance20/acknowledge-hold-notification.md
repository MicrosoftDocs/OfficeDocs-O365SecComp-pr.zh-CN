---
title: 确认保留通知
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
ms.openlocfilehash: eb29ff34d663cf43af4a9a4b1e966a282d16eaf2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151944"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="8d31e-102">确认保留通知</span><span class="sxs-lookup"><span data-stu-id="8d31e-102">Acknowledge a hold notification</span></span> 
<span data-ttu-id="8d31e-103">在响应法规请求或调查时, 可能需要通知保管人, 让其义务保留电子存储的信息 (ESI) 以及可能与活跃或即将发生的法律事务相关的任何材料。</span><span class="sxs-lookup"><span data-stu-id="8d31e-103">When responding to a regulatory request or investigation, you may be required to  inform custodians of their obligation to preserve electronically stored information (ESI) as well as any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="8d31e-104">一旦发送, 法律团队必须知道每位管理员已收到、阅读和理解, 并同意遵守给定的说明。</span><span class="sxs-lookup"><span data-stu-id="8d31e-104">Once sent, legal teams must know that each custodian has received, read, and understood, and agreed to comply with the given instructions.</span></span>

<span data-ttu-id="8d31e-105">为了帮助减少与您的保管人的时间、成本和工作效率, 高级电子数据展示允许您通过电子邮件发送法律封存通知并跟进这些通知。</span><span class="sxs-lookup"><span data-stu-id="8d31e-105">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow-up on legal hold notifications through email.</span></span> <span data-ttu-id="8d31e-106">除了电子邮件通知之外, 每个管理员还将有权访问个人合规性门户, 使保管人能够及时了解其合同状态的更改。</span><span class="sxs-lookup"><span data-stu-id="8d31e-106">In addition to email notices, each custodian will also have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="8d31e-107">电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="8d31e-107">Email notifications</span></span>
<span data-ttu-id="8d31e-108">发出合法保留通知后, 每位管理员都将收到一个唯一且个性化的电子邮件, 其中包含定义的合法保留通知和添加的说明。</span><span class="sxs-lookup"><span data-stu-id="8d31e-108">Once a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!Tip] 
> <span data-ttu-id="8d31e-109">了解如何使用内置[通信编辑器](using-communications-editor.md), 以允许保管人确认其通知或从其电子邮件直接访问其合规性门户。</span><span class="sxs-lookup"><span data-stu-id="8d31e-109">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="8d31e-110">根据您的法定保留通知的配置, 您的保管人可能会收到以下通知:</span><span class="sxs-lookup"><span data-stu-id="8d31e-110">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="8d31e-111">**颁发通知**-这是发送给你的保管人的第一个通知。</span><span class="sxs-lookup"><span data-stu-id="8d31e-111">**Issuance notice** - This is the first notice sent to your custodian.</span></span> <span data-ttu-id="8d31e-112">这将包含发布说明以及在邮件末尾追加的保留通知。</span><span class="sxs-lookup"><span data-stu-id="8d31e-112">This will contain your issuance instructions as well as the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="8d31e-113">**提醒通知**-如果启用, 将根据指定的频率和间隔将提醒通知发送给你的保管人。</span><span class="sxs-lookup"><span data-stu-id="8d31e-113">**Reminder notice** - If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="8d31e-114">提醒将继续发送, 直到管理员已确认其通知或已耗尽提醒的次数。</span><span class="sxs-lookup"><span data-stu-id="8d31e-114">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="8d31e-115">**上报通知**-如果启用, 则在提醒通知耗尽后, 会向你的保管人及其经理发送上报通知。</span><span class="sxs-lookup"><span data-stu-id="8d31e-115">**Escalation notice** - If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="8d31e-116">系统将在 alloted 升级完成之前或在保管人确认其保留通知之前自动发送上报通知。</span><span class="sxs-lookup"><span data-stu-id="8d31e-116">The system will automatically send escalation notices until the alloted escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="8d31e-117">**重新颁发通知**-在调查过程中, 如果保留通知的内容已更新, 则会自动向保管人发送已更新的通知。</span><span class="sxs-lookup"><span data-stu-id="8d31e-117">**Re-issue notice** - During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="8d31e-118">**发布通知**-当管理员从包装箱中发布时, 系统将向其发送发布通知。</span><span class="sxs-lookup"><span data-stu-id="8d31e-118">**Release notice** - When a custodian is released from the case, they will be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="8d31e-119">合规性门户</span><span class="sxs-lookup"><span data-stu-id="8d31e-119">Compliance Portal</span></span>
<span data-ttu-id="8d31e-120">除了电子邮件通知之外, 每个管理员还将有权访问唯一的合规性门户。</span><span class="sxs-lookup"><span data-stu-id="8d31e-120">In addition to the email notifications, each custodian will also have access to a unique Compliance Portal.</span></span> <span data-ttu-id="8d31e-121">通过门户, 每位管理员都可以查看、访问和确认其活动保留通知。</span><span class="sxs-lookup"><span data-stu-id="8d31e-121">Through the portal, each custodian will be able to view, access, and acknowledge their active hold notifications.</span></span>

![对保管人的合规性门户](../media/CustodianPortal.jpg)

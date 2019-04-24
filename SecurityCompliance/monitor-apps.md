---
title: 在 Microsoft 365 安全中监视和报告应用状态
description: 介绍如何能够深入了解组织中的云应用程序使用情况
keywords: security、恶意软件、Microsoft 365、M365、security center、monitor、report、apps
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 33a10996ceaf3023d5aee58aaabf3fef54372c30
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263306"
---
# <a name="monitor-and-report-app-status-in-microsoft-365-security"></a>在 Microsoft 365 安全中监视和报告应用状态


这些报告可更深入地了解如何在组织中使用云应用程序, 包括哪些类型的应用、风险级别和警报。

## <a name="monitor-email-accounts-at-risk"></a>监视电子邮件帐户的风险

**电子邮件保护**显示有风险的电子邮件帐户。 您可以单击某个帐户以在 Windows Defender 安全中心中进行进一步调查。

![电子邮件保护卡](./media/security-docs/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>监视用户授予的应用程序权限

**云应用安全-OAuth 应用**列出由用户授予权限的云应用安全发现的应用程序。 云应用安全性风险目录包含16000个以上使用超过70个风险因素评估的应用程序。

风险因素从一般信息 (如应用程序发布者) 开始, 到安全措施和控件, 例如应用程序是否支持在 rest 上进行加密或提供用户活动的审核日志。

![云应用安全 OAuth 应用程序卡片](./media/security-docs/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>监视云应用程序用户帐户

**适用于审阅的云应用帐户**列表可能需要注意的帐户。

![审阅卡片的云应用程序帐户](./media/security-docs/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>了解使用的是哪些云应用程序

已**发现的云应用程序 (类别)** 显示在您的组织中使用的是哪些类型的应用程序, 以及云发现仪表板在云应用安全中的链接。 有关详细信息, 请参阅[快速入门: 使用已发现的应用](https://docs.microsoft.com/cloud-app-security/discovered-apps)。  

![发现的云应用类别卡片](./media/security-docs/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>监视用户访问云应用程序的位置

**云应用活动位置**显示用户在访问云应用程序的位置。

![云应用活动位置卡片](./media/security-docs/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>监视基础架构工作负载的运行状况

**基础结构运行状况**在 Azure 安全中心中显示基础结构工作负荷的运行状况状态警报。

Azure 安全中心在内部部署和云工作负载中提供统一的安全管理和高级威胁保护。 您可以从各种源 (包括防火墙和其他合作伙伴解决方案) 收集、搜索和分析安全数据。

有关详细信息, 请参阅[Azure 安全中心文档](https://docs.microsoft.com/azure/security-center/)。

![基础结构运行状况卡片](./media/security-docs/infrastructure-health.png)

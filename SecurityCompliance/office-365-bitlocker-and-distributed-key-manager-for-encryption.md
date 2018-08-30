---
title: Office 365 BitLocker 加密
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 有关 BitLocker 加密在云中的信息。
ms.openlocfilehash: 86c6bc9282d7c2b0a7d4e08d4636c8f9c2fa5db8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525420"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>用于加密的 BitLocker 和 Distributed Key Manager (DKM)
Office 365 服务器使用 BitLocker 加密磁盘驱动器包含客户数据在 rest 的音量级别。BitLocker 加密是一种 Windows 中内置的数据保护功能。BitLocker 是硬件的用于有停止其他进程或可能会导致物理磁盘包含客户数据访问某人的控件 （例如，访问控制或回收） 的情况下保护抵御威胁的技术之一。在这种情况下，BitLocker 消除数据盗窃或暴露可能由于丢失、 盗取或配置取消不当计算机和磁盘。

BitLocker 部署与磁盘其中包含客户数据在 Exchange Online、 SharePoint Online 和 Skype for Business 的高级加密标准 (AES) 256 位加密。磁盘扇区进行加密与完全批量加密密钥 (FVEK)，其加密与卷主密钥 (VMK)，这又绑定到受信任平台模块 (TPM) 服务器中。VMK 直接保护 FVEK 并因此，保护 VMK 成为关键。下图显示了给定服务器 （在本例中为使用 Exchange Online 服务器） 的 BitLocker 密钥保护链的示例。

下表介绍用于给定服务器 （在此情况下，Exchange Online 的服务器） 的 BitLocker 密钥保护链。

| 密钥保护程序 | 粒度 | 如何生成？ | 存储在何处？ | 保护 |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256 位外部项 | 每台服务器 | BitLocker Api | TPM 或机密的安全 | 密码箱 / 访问控制 |
|  |  |  | 邮箱服务器注册表 | TPM 加密 |
| 48 位数字密码 | 每个磁盘 | BitLocker Api | Active Directory | 密码箱 / 访问控制 |
| X.509 证书作为数据恢复代理 (DRA) 也称为公共密钥保护程序 | 环境 (例如，Exchange Online multitenant) | Microsoft CA | 生成系统 | 任何用户不具有完全私钥密码。在物理保护密码。 |


BitLocker 密钥管理涉及恢复键的用来解除锁定/恢复 Office 365 数据中心中的加密的磁盘管理。Office 365 中仅可访问已筛选并批准的个人的安全共享存储主密钥。注册表项的凭据存储在安全存储库的访问控制数据 （我们所说"机密存储"），这要求高级别提升和管理审批访问使用实时中访问提升工具。

BitLocker 支持键其分为两个管理类别：
- BitLocker 托管键，它们通常是短期和绑定到服务器上安装操作系统实例的生存期内或给定磁盘。这些项的删除和重置期间服务器重新安装或磁盘格式。
- BitLocker 恢复键，它们都是托管 BitLocker 之外但用于磁盘解密。BitLocker 使用的方案顺序重新安装操作系统，并且加密的数据磁盘存在恢复密钥。托管可用性监视探测器在 Exchange Online 响应器可能需要其中还使用恢复密钥解锁磁盘。

受保护的 BitLocker 卷使用一个完整批量加密密钥，又使用卷主密钥加密加密。BitLocker 使用符合 FIPS 的算法来确保加密密钥永远不会存储或通过线路以明文发送。客户数据在-rest-保护的 Office 365 实现不偏离默认 BitLocker 实现。
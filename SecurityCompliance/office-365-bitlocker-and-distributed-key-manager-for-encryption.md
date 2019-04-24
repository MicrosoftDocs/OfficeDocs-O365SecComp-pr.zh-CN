---
title: 用于加密的 Office 365 BitLocker
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: '摘要: 有关云中的加密的 BitLocker 相关信息。'
ms.openlocfilehash: 293c7a3cef3ae2c55a0b12df139baf5302dd3b04
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262934"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>用于加密的 BitLocker 和 Distributed Key Manager (DKM)

Office 365 服务器使用 BitLocker 在卷级别加密包含客户数据的磁盘驱动器。 BitLocker 加密是 Windows 中内置的数据保护功能。 BitLocker 是一种用于预防威胁的技术, 以防发生其他进程或控件 (例如, 对硬件的访问控制或回收) 发生时出现的情况, 从而导致某人能够物理访问包含客户数据的磁盘。 在这种情况下, BitLocker 可消除因丢失、被盗或取消授权不当的计算机和磁盘而导致数据失窃或泄露的可能性。

BitLocker 在 Exchange online、SharePoint online 和 Skype for business 中包含客户数据的磁盘上使用高级加密标准 (AES) 256 位加密进行部署。 磁盘扇区使用完整的卷加密密钥 (FVEK) 进行加密, 该密钥使用卷主密钥 (VMK) 进行加密, 后者又绑定到服务器中受信任的平台模块 (TPM)。 VMK 直接保护 FVEK, 因此保护 VMK 变得至关重要。 下图说明了给定服务器 (在此示例中, 使用 Exchange Online server) 的 BitLocker 密钥保护链的一个示例。

下表介绍了给定服务器的 BitLocker 密钥保护链 (在此示例中为 Exchange Online server)。

| 密钥保护程序 | 间隔 | 如何生成？ | 它存储在什么位置？ | 保护 |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256 位外部密钥 | 每台服务器 | BitLocker api | TPM 或秘密安全 | 密码箱/访问控制 |
|  |  |  | 邮箱服务器注册表 | TPM 加密 |
| 48位数字密码 | 每个磁盘 | BitLocker api | Active Directory | 密码箱/访问控制 |
| 将 x.509 证书作为数据恢复代理 (DRA) 也称为公钥保护程序 | 环境 (例如, Exchange Online 多租户) | Microsoft CA | 生成系统 | 没有用户拥有私钥的完整密码。 密码位于物理保护之下。 |


BitLocker 密钥管理涉及到用于在 Office 365 数据中心中解锁/恢复加密磁盘的恢复密钥的管理。 Office 365 将主密钥存储在安全共享中, 仅供已被筛选和批准的个人访问。 密钥的凭据存储在访问控制数据的安全存储库中 (我们称之为 "秘密存储"), 这需要高级别的提升和管理批准才能使用实时访问提升工具进行访问。

BitLocker 支持属于两个管理类别的密钥:

- BitLocker 管理的密钥, 通常为短寿命, 并与安装在服务器上的操作系统实例的生存期或指定磁盘相关联。 在服务器重新安装或磁盘格式化过程中, 将删除和重置这些密钥。

- bitlocker 恢复密钥, 在 bitlocker 之外进行管理, 但用于磁盘解密。 BitLocker 在重新安装操作系统的情况下使用恢复密钥, 并且已存在已加密的数据磁盘。 在 Exchange Online 中, 托管可用性监视探测器也使用恢复密钥, 其中响应器可能需要对磁盘进行解锁。

受 BitLocker 保护的卷使用完整卷加密密钥进行加密, 该密钥又使用卷主密钥进行加密。 BitLocker 使用符合 FIPS 标准的算法, 以确保不会以明文形式在线路中存储或发送加密密钥。 "Office 365 的客户数据保护" 实施不与默认的 BitLocker 实施有偏离。
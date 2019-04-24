---
title: Office 365 数据销毁
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 有关对 Office 365 数据中心磁盘驱动器和服务器进行回收、处置或销毁的 Microsoft 策略的概述。
ms.openlocfilehash: fec6065434fa9fa555a057c68eca60082225652c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262904"
---
# <a name="office-365-data-destruction"></a>Office 365 数据销毁

## <a name="physical-data-destruction"></a>物理数据销毁

Microsoft 具有数据处理标准策略, 这些策略可解决磁盘驱动器的回收和处置故障, 以及服务器的故障或淘汰。 在重新使用 Office 365 中的任何磁盘驱动器之前, Microsoft 会执行物理净化过程, 该过程与美国国家标准和技术专用出版物 800-88 ([NIST SP 800-88 适用于媒体清理指南](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf)) 一致). Office 365 中的所有磁盘驱动器都使用 BitLocker 卷级加密进行加密, 因此在实践中, 不需要 NIST SP 800-88 兼容的擦除。 不过, 它仍由 Microsoft 执行。

在 Office 365 数据中心内使用的故障磁盘是通过 ISO 进程物理销毁和审核的。 适当的处置方式取决于资产类型。 对于无法擦除的硬驱, Microsoft 使用销毁媒体的销毁过程 (例如, disintegrates、pulverizes 或 incinerates), 并呈现无法恢复的信息。 Microsoft 还保留了销毁的所有记录。 Microsoft 在 Office 365 中重新使用的服务器上执行类似的清理过程。 这些准则包含电子和物理净化。

无法重新使用的磁盘驱动器是使用在包含要销毁的磁盘的数据中心内的站点内执行的物理销毁过程来释放的。 为处置而指定的存储媒体放置在位于数据中心每个区域中的安全区域中。 每个安全的 bin 工作站都受视频监控监控。 一旦处置空间达到约 50% 的容量, 网站服务团队将与物理安全团队联系以协调其删除。 然后, 网站服务人员在 escort 下删除处置邮箱, 然后将安全主管放在受保护的存储区域中, 以等待数据销毁。 在处置过程中管理数据贴出设备处理的策略和程序将定期进行测试, 包括确保机械销毁的设备条件的过程。

在数据销毁过程中, 第一次擦除磁盘时采用与 NIST 800-88 兼容的方式 (如果可能), 然后将其放入行业清除程序和物理 demolished 中。 Microsoft 为那些离开数据中心的资产提供责任, 即使用 NIST SP 800-88 一致的清理/清除、资产销毁、加密、准确清查、跟踪和保护在传输过程中的保管链。 此过程通过闭合电路电视进行监控, 并在完成后发出销毁证书。

Microsoft 使用来自[极限协议解决方案](http://www.enterprisedataerasure.com/)(EPS) 的数据擦除单元。 EPS 软件支持对清理和清除/安全擦除的 NIST SP 800-88 要求。 在清理或销毁之前, 清单由 Microsoft 资产管理器创建。 如果供应商用于销毁, 供应商为销毁的每个资产提供一个销毁证书, 该证书由资产管理者进行验证。

## <a name="virtual-data-destruction"></a>虚拟数据销毁

Microsoft 有一些数据处理策略和过程, 它还可以解决数据的有效虚拟破坏, 以防止数据在服务租户之间无法被不当共享, 或在服务中进行硬删除后可访问的可能性。 在一个租户中从服务中删除的数据即使在稍后重新分配了部分或全部相同的基础物理存储时, 也无法访问另一个服务租户。 这是用于扩展虚拟环境的多个虚拟化和碎片技术的复合效果的结果, 每个服务租户中的应用程序的活动删除行为 (如[页面清零](https://docs.microsoft.com/office365/securitycompliance/office-365-exchange-online-data-deletion#page-zeroing)), 以及所需的媒体和应用程序内容加密过程。
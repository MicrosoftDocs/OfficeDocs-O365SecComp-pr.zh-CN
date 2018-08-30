---
title: Office 365 数据破坏
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
description: 有关回收、 处置或销毁的 Office 365 数据中心磁盘驱动器和服务器的 Microsoft 的策略的概述。
ms.openlocfilehash: c9950be4919520f2f46badaa4a7d4cfce5c55b45
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525146"
---
# <a name="office-365-data-destruction"></a><span data-ttu-id="84474-103">Office 365 数据破坏</span><span class="sxs-lookup"><span data-stu-id="84474-103">Office 365 Data Destruction</span></span>
<span data-ttu-id="84474-p101">Microsoft 具有地址回收站和释放磁盘驱动器和失败或停用服务器的数据处理标准策略。重新使用 Office 365 中的任何磁盘驱动器之前, Microsoft 执行与国家标准和技术特殊发布 800 88 （[NIST SP 800 88 准则进行媒体清理](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf)一致的物理过滤过程).Office 365 中的所有磁盘驱动器都加密使用 BitLocker 卷级别加密，因此实际上，NIST SP 800 88 符合擦除不需要。但是，它仍然由 Microsoft 执行。</span><span class="sxs-lookup"><span data-stu-id="84474-p101">Microsoft has Data Handling Standard policies that addresses recycle and disposal of disk drives and failed or retiring servers. Before re-using any disk drives within Office 365, Microsoft performs a physical sanitization process that is consistent with National Institute of Standards and Technology Special Publication 800-88 ([NIST SP 800-88 Guidelines for Media Sanitization](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf)). All disk drives in Office 365 are encrypted using BitLocker volume level encryption, so in practice, NIST SP 800-88-compliant erasure is not necessary. Nonetheless, it is still performed by Microsoft.</span></span>

<span data-ttu-id="84474-p102">无法在 Office 365 数据中心是物理销毁和审计通过 ISO 过程内使用的磁盘。释放的适当方法取决于资产类型。对于无法之前的硬盘，Microsoft 使用销毁媒体销毁过程 （例如，disintegrates、 pulverizes，或 incinerates） 并呈现信息的恢复意思。Microsoft 还保留销毁的所有记录。Microsoft 被重新使用 Office 365 中的服务器上执行类似的清理过程。这些准则涵盖电子和物理清理。</span><span class="sxs-lookup"><span data-stu-id="84474-p102">Failed disks used within Office 365 datacenters are physically destroyed and audited through the ISO process. The appropriate means of disposal is determined by the asset type. For hard drives that can't be wiped, Microsoft uses a destruction process that destroys the media (e.g., disintegrates, pulverizes, or incinerates) and renders the recovery of information impossible. Microsoft also retains all records of the destruction. Microsoft performs a similar sanitization process on servers that are being re-used within Office 365. These guidelines encompass both electronic and physical sanitization.</span></span>

<span data-ttu-id="84474-p103">使用现场包含被销毁磁盘的数据中心内执行的物理销毁过程的情况下，不能重复使用的磁盘驱动器都得到释放。存储媒体的处置指定放在安全位于数据中心的每个区域中的优化格。每个安全 bin 工作站由视频监控监控。一旦释放 bin 达到了大约 50%的容量，在网站 Services 团队的联系人的物理安全团队进行协调其删除。网站服务人员然后删除下陪同安全部主管释放 bin，直到它放在受保护的存储区，等待数据破坏。策略和调控处理期间释放带有设备的数据的过程进行定期测试包括过程以确保机械销毁批准的条件。</span><span class="sxs-lookup"><span data-stu-id="84474-p103">Disk drives that cannot be re-used are disposed of using a physical destruction process that is performed on-site within the datacenter containing the disks being destroyed. Storage media designated for disposal are placed in secure bins located in each area of the datacenter. Each secure bin station is monitored by video surveillance. Once a disposal bin reaches approximately 50% capacity, the Site Services team contacts the Physical Security team to coordinate its removal. Site Services personnel then remove the disposal bin under escort by a Security Officer until it is placed in a secured storage area to await data destruction. Policies and procedures governing the handling of data bearing devices during disposal are routinely tested including procedures to ensure the condition of machinery approved for destruction.</span></span>

<span data-ttu-id="84474-p104">对数据销毁过程中磁盘首先擦除，以符合 NIST 88 （如果可能），800 的方式，然后它是放入行业碎，并从物理上隔离破坏。Microsoft 维护离开使用 NIST SP 800 88 一致清理/清除、 资产销毁、 加密、 准确清点、 跟踪和保护的监管链在传输过程中的数据中心的资产的责任。此过程监控通过关闭电路电视并销毁证书颁发完毕。</span><span class="sxs-lookup"><span data-stu-id="84474-p104">In the data destruction process, the disk is first erased in a manner that is compliant with NIST 800-88 (if possible), and then it is placed into an industrial shredder and physically demolished. Microsoft maintains accountability for assets leaving the datacenter using NIST SP 800-88 consistent cleansing/purging, asset destruction, encryption, accurate inventorying, tracking, and protection of chain of custody during transport. This process is monitored via closed-circuit television and a Certificate of Destruction is issued upon completion.</span></span>

<span data-ttu-id="84474-p105">Microsoft 使用[极高强度协议解决方案](http://www.enterprisedataerasure.com/)(EPS) 中的数据擦除单元。EPS 软件的清理和清除安全擦除支持 NIST SP 800 88 要求。之前清理或破坏，由 Microsoft 资源管理器中创建清单。如果销毁使用供应商，则在供应商提供销毁销毁，每个资源的资源管理器验证该的证书。</span><span class="sxs-lookup"><span data-stu-id="84474-p105">Microsoft uses data erasure units from [Extreme Protocol Solutions](http://www.enterprisedataerasure.com/) (EPS). EPS software supports NIST SP 800-88 requirements for cleansing and purging/secure erasure. Prior to cleansing or destruction, an inventory is created by the Microsoft asset manager. If a vendor is used for destruction, the vendor provides a certificate of destruction for each asset destroyed, which is validated by the asset manager.</span></span>
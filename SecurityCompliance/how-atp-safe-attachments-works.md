---
title: Office 365 ATP 安全附件的工作原理
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: "\"安全附件\" 功能可提供电子邮件附件的单击时间验证。 使用安全附件保护组织免受用户在电子邮件中发送或接收的恶意文件的攻击。"
ms.openlocfilehash: f0f117388957a14e3765b963a0e390ffb8fd7943
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599167"
---
# <a name="how-ffice-365-atp-safe-attachments-works"></a>Office 365 ATP 安全附件的工作原理

## <a name="how-it-works"></a>运作方式

ATP 安全附件功能检查组织中人员的电子邮件附件。 如果 ATP 安全附件策略已就绪, 并且该策略涵盖的人在 Office 365 中查看其电子邮件, 则会检查其电子邮件附件, 并根据 ATP 安全附件策略采取相应的操作。 根据您的策略定义方式, 用户可以继续工作, 而无需知道他们是否发送了恶意文件。
  
以下是有关工作的 ATP 安全附件的两个示例。
  
- **示例 1: 电子邮件附件**假设收到电子邮件, 其中包含附件。 如果附件是安全的还是实际包含旨在窃取用户的用户凭据的恶意软件, 则不会这样。 在先生/她的组织中, 安全管理员在几天前定义了 ATP 安全附件策略。 使用 ATP 安全附件功能, 在获得电子邮件附件之前, 将在虚拟环境中打开并测试该附件。 如果认为附件是恶意的, 则会自动将其删除。 如果附件是安全的, 则会在您通过单击它时按预期方式打开。

- **示例 2: SharePoint Online 中的文件**假设 Jean 收到一个文件, 并将其上载到 SharePoint Online 中的库中。 Jean 与团队的其余部分共享指向文件的链接, 而不知道该文件实际是恶意的。 幸运的是, [SharePoint、OneDrive 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)会检测恶意文件并阻止它。 几天后, Chris 将转到 "打开" 文档。 尽管 Chris 可以看到该文件, Chris 也无法打开或共享该文件, 这将保护 Chris 的计算机和恶意文件中的其他人。

ATP 安全附件策略可应用于组织中的特定用户或组, 或应用于整个域。 此外, 还可以将 ATP 安全附件策略配置为在扫描实际附件时使用占位符附件。 若要了解详细信息, 请参阅**[在 Office 365 中设置 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)**。

> [!NOTE]
> ATP 安全附件扫描发生在 Office 365 数据所在的同一个区域中。 有关数据中心地理位置的详细信息, 请参阅[您的数据位于何处？](https://products.office.com/where-is-your-data-located?geo=All) 


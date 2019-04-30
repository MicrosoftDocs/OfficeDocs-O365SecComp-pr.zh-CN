---
title: Microsoft 合规性管理器发行说明
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: microsoft 合规性管理器是 microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使你能够跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。
ms.openlocfilehash: 5e18445e3f9ad2848f18174788ec6dd40bc4a178
ms.sourcegitcommit: 696c1ed6b270be3f9da7395b49a7d8fec98e6db0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2019
ms.locfileid: "33473012"
---
# <a name="release-notes-for-compliance-manager-preview"></a>合规性管理器的发行说明 (预览)

合规性管理器的公共预览版为您提供早期访问即将推出的功能和更新。

您可以使用[服务信任门户](https://servicetrust.microsoft.com)上的更新的[合规性管理器](https://servicetrust.microsoft.com/ComplianceManager)工具来跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。

## <a name="whats-new-in-compliance-manager-preview"></a>合规性管理器中的新增功能 (预览)

- **与 Microsoft 安全分数的集成:** 合规性管理器通过将客户管理的操作映射到50以上的安全分数操作, 支持与[Microsoft 安全分数](microsoft-secure-score.md)的集成。 在安全分数中完成映射的操作后, 相应的合规性管理器操作将自动更新。

- **导入自定义评估:** 除了内置评估, 合规性管理器现在还支持导入自定义模板, 从而使您能够为任何产品或服务以及任何标准或法规创建自定义评估。

- **Actions 项:** 操作项现在是单个项目, 并且许多包含来自 Microsoft 安全分数图形 API 的遥测集合。 在可能的情况下, 技术操作建议现在有指向 Office 365 服务中适用配置页面的链接。

- **租户管理:** 用于管理合规性管理器中的新数据元素的新界面 (预览):
    - **维:** 查看、添加和自定义模板、评估和操作项的元数据, 以允许您为筛选器创建自定义透视。
    - **所有者:** 为每个即席项目指定一个所有者。
    - **客户操作:** 管理合规性管理器 (预览版) 中包含的操作项的完整列表, 并为与安全得分集成的操作项启用/禁用安全分数监视。

- **更新了合规性分数**: 该方法已更改为支持与 Microsoft 安全分数同步。 评分系统删除了 Microsoft 托管的控制积分, 并仅侧重于客户托管的控制措施的完成。

## <a name="known-issues-in-compliance-manager-preview"></a>合规性管理器中的已知问题 (预览)

以下各节介绍了即将在即将发布的合规性管理器中解决的已知问题。

### <a name="compliance-score"></a>合规性分数

- 将措施项标记为**不在范围中**时, 分配给措施项的分数不会从合规性分数计算中排除。 标记为**不在作用域中的**操作项不应增加合规性分数。

### <a name="microsoft-managed-controls"></a>Microsoft 托管控件

- Microsoft 托管控件的测试日期不会显示在 UI 中, 即使在评估中也不会如此。 若要查看测试日期信息, 必须导出该评估。

### <a name="customization"></a>自定义

- 通过添加自定义控件, 可以向现有控件系列添加新控件, 但不允许添加新的控件系列。
- 此版本不支持链接操作项或向评估添加操作项或控件。
- 如果创建自定义操作, 则无法对其进行编辑或将其删除。

### <a name="control-families-not-shown-in-assessments"></a>控制系列未在评估中显示

- 导入模板时, 基于该模板的所有评估将反映属于该模板的所有控制系列。 但是, 如果向模板中添加新的控制系列, 则任何现有评估都不会反映所做的更改。 仅根据更新后的模板创建的新评估将反映所做的更改。

### <a name="filters"></a>筛选器

- 对交办事项或控件的筛选不会始终如一地生成正确的结果。

### <a name="templates"></a>模板

- 存档的模板是可编辑的, 不应是可编辑的。
- 锁定的模板允许在不应进行评估时创建评估。 锁定模板旨在防止它用于创建评估。

### <a name="export"></a>导出

- 将模板状态设置为 "已**导入**" 或 "**待审批**" 时, 模板导出到 JSON 失败。

### <a name="supported-browsers"></a>支持的浏览器

- Microsoft Edge、Chrome 和 Safari 的最新版本均受支持。
- 在刷新浏览器之前, 可能会出现更新后的数据未出现的情况。
- Microsoft Edge 的预览版本不受支持, 但没有已知问题。
- 不支持 Internet Explorer。

### <a name="session-timeout"></a>会话超时

- 会话超时时, 可能会出现 "发生错误" 错误。 若要解决此问题, 请转到[合规性管理器](https://servicetrust.microsoft.com/ComplianceManager), 然后重新登录。
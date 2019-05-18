---
title: Microsoft 合规性管理器和 GDPR
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性管理器是 Microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使你能够跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。
ms.openlocfilehash: a082d069aced13aa9260a1a856d942c4feb7dd4b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152083"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Microsoft 合规性管理器和 GDPR

欧盟制定的一般数据保护条例 (GDPR) 可能会影响您的合规性策略, 并强制执行管理合规性管理器中使用的用户和客户信息所需的操作。

## <a name="user-privacy-settings"></a>用户隐私设置

某些法规要求组织必须能够删除用户历史记录数据。 合规性管理器提供的**用户隐私设置**功能允许管理员执行以下操作:
  
- [搜索用户](#search-for-a-user)
- [导出帐户数据历史记录报告](#export-a-report-of-account-data-history)
- [删除用户数据历史记录](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>搜索用户

若要搜索用户帐户，请执行以下操作：
  
1. 输入用户电子邮件别名 (@ 符号左侧的信息), 然后从右侧的 "域后缀" 列表中选择域名。 对于具有多个注册域的组织, 请仔细检查域名后缀以确保其正确无误。

2. 正确输入了用户名后, 选择 "**搜索**"。

3. 对于未返回的用户帐户, 页面上将显示 "找不到用户"。 检查用户的电子邮件地址信息, 并根据需要进行更正。 若要重试, 请选择 "**搜索**"。

4. 对于返回的用户帐户, 该按钮的文本将从 "**搜索**" 更改为 "**清除**"。 这表示返回的用户帐户是其他函数的操作上下文, 并且这些函数适用于此用户帐户。

5. 若要清除搜索结果并搜索其他用户, 请选择 "**清除**"。

## <a name="export-a-report-of-account-data-history"></a>导出帐户数据历史记录报告

对于标识的每个用户帐户, 您可以生成链接到此帐户的依赖项的报告。 此信息使您可以重新分配打开的操作项或确保对以前上载的证据的访问权限。
  
 若要生成并导出报告，请执行以下操作：
  
1. 选择 "**导出**" 以生成并下载当前分配给返回的用户帐户的合规性管理器控件操作项的报告, 以及该用户上载的文档列表。 如果没有分配的操作或上载的文档, 则错误消息将显示 "没有此用户的数据"。

2. 报告在活动浏览器窗口的后台下载—如果看不到要检查浏览器下载历史记录的下载弹出菜单。

3. 打开文档即可查看报告数据。

> [!IMPORTANT]
> 这不是一个保留并显示对措施项分配历史记录的状态更改的历史报告。 生成的报告是运行报告时分配的控制措施项目 (写入报告中的日期和时间戳) 的快照。 例如, 如果对同一用户再次生成此报告, 则操作项目的任何后续重新分配将导致不同的快照报告数据。
  
## <a name="delete-user-data-history"></a>删除用户数据历史记录

将所有分配给返回的用户的控制操作项设置为 "未分配"。 将由返回的用户上载的任何文档的已**上载**的值设置为 "用户删除"。
  
删除用户帐户操作项和文档上载历史记录:
  
1. 选择 "**删除**"。

    将显示确认对话框, "*这将删除所选用户的所有控制措施项分配和文档上传历史记录。此操作是永久性的。是否确实要继续？*

2. 若要继续, 请选择 **"确定"**, 否则选择 "**取消**"。
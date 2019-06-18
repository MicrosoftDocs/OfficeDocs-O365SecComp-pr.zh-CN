---
title: 设置连接器以存档 Office 365 中的 LinkedIn 数据 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器以将数据从 LinkedIn 公司页面导入到 Office 365。 这使您可以在 Office 365 中存档第三方数据源中的数据, 以便您可以使用合规性功能 (如法律封存、内容搜索和保留策略) 来管理组织的第三方数据的合规性。
ms.openlocfilehash: 2b89f990f18ae13ad15015f240ea4c4b0ec434b0
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2019
ms.locfileid: "35017943"
---
# <a name="set-up-a-connector-to-archive-linkedin-data-in-office-365-preview"></a>设置连接器以存档 Office 365 中的 LinkedIn 数据 (预览)

在 Office 365 中存档来自 LinkedIn 公司页面的数据的连接器功能处于预览阶段。

在 Office 365 的 Security & 合规性中心中使用本机连接器, 以从 LinkedIn 公司页面导入和存档数据。 在设置和配置连接器后, 它会每24小时连接到特定 "LinkedIn 公司" 页面的帐户。 连接器将发布到公司页面的邮件转换为电子邮件, 然后将这些项目导入 Office 365 中的邮箱。

在将 LinkedIn 公司页面数据存储在邮箱中之后, 您可以将 Office 365 合规性功能 (如诉讼保留、内容搜索、就地存档、审核和 Office 365 保留策略) 应用于 LinkedIn 数据。 例如, 可以使用内容搜索来搜索这些项目, 或将存储邮箱与高级电子数据展示事例中的管理员相关联。 创建连接器以在 Office 365 中导入和存档 LinkedIn 数据可帮助您的组织遵守政府和法规策略。

## <a name="before-you--begin"></a>开始之前

- 您必须具有作为您要存档的 "LinkedIn 公司" 页面的管理员的 LinkedIn 用户帐户的登录凭据 (电子邮件地址或电话号码和密码)。 设置连接器时, 可以使用这些凭据登录到 LinkedIn。

- 必须在 Exchange Online 中为创建 LinkedIn 公司页面连接器的用户分配邮箱导入导出角色。 这是访问安全 & 合规中心中的 "**存档第三方数据**" 页所必需的。 默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者, 您可以创建角色组, 分配邮箱导入导出角色, 然后将相应的用户添加为成员。 有关详细信息, 请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。

## <a name="create-a-linkedin-connector"></a>创建 LinkedIn 连接器

1. 转到<https://protection.office.com> , 然后单击 "**数据\>调控导入**", 然后单击 "**存档第三方数据**"。

2. 在 "**存档第三方数据**" 页上, 单击 "**添加连接器**", 然后单击 " **LinkedIn**"。

3. 在 "**服务条款**" 页上, 单击 "**接受**"。

4. 在 "**使用 Linkedin 登录**" 页面上, 单击 "**使用 linkedin 登录**"。

   将显示 "LinkedIn 登录" 页面。

   ![LinkedIn 登录页](media/LinkedInSigninPage.png)

5. 在 "LinkedIn 登录" 页面上, 输入与要存档的公司页面相关联的 LinkedIn 帐户的电子邮件地址 (或电话号码) 和密码, 然后单击 "**登录**"。

   将显示一个向导页, 其中包含与您登录的帐户关联的所有 LinkedIn 公司页面的列表。 仅可为一个公司页面配置连接器。 如果您的组织具有多个 LinkedIn 公司页面, 则必须为每个公司创建一个连接器。

   ![将显示一个包含 "LinkedIn 公司" 页面列表的页面](media/LinkedInSelectCompanyPage.png)


6. 选择要存档其项目的公司页面, 然后单击 "**下一步**"。

7. 在 "**设置筛选器**" 页上, 您可以将筛选器应用于最初导入特定年龄的项目。 选择年龄, 然后单击 "**下一步**"。

8. 在 "**设置存储帐户**" 页上, 键入将向其导入 LinkedIn 项目的 Office 365 邮箱的电子邮件地址, 然后单击 "**下一步**"。 项目将导入到此邮箱的 "收件箱" 文件夹中。

9. 查看连接器设置, 然后单击 "**保存**" 以完成连接器设置。

创建连接器后, 可以返回到 "**存档第三方数据**" 页 (如果需要更新连接器列表, 请单击 "**刷新**") 查看新的连接器。 "**状态**" 列中的值为 "**正在等待启动**"。 启动初始导入过程需要长达24小时。 在第一次运行连接器并导入 LinkedIn 项目后, 连接器将每24小时运行一次, 并导入 "LinkedIn 公司" 页上的 "在前24小时内创建的任何新项目"。

若要查看更多详细信息, 请单击 "**存档第三方数据**" 页上的列表中的连接器以显示弹出页面。 在 "**状态**" 下, 显示的日期范围表示创建连接器时选择的年龄筛选器。 

## <a name="more-information"></a>更多信息

- 将 LinkedIn 项目导入到 Office 365 中的存储邮箱的 "收件箱" 文件夹中。 它们显示为电子邮件。 邮件发件人的显示名称是 "LinkedIn 公司" 页面的名称。 发件人的实际电子邮件地址是存储邮箱的电子邮件地址。 公司页面的名称也会预先追加到主题行。 

- 由于以前的行为, 在使用 Microsoft 电子数据`from`展示`subject`工具搜索在 Office 365 中存档的 LinkedIn 项目时, 可以搜索或电子邮件属性。 例如, 如果公司页面的名称是 "Contoso Company Page", 则可以在关键字搜索查询中使用下列*属性之一: 值*对:
   
   ```
   from:"Contoso Company Page"
   ```

    或

   ```
   subject:"Contoso Company Page"
   ```

- 若要更轻松地查找或管理导入到 Office 365 的 LinkedIn 项目, 存储邮箱的所有者 (或任何被分配了 FullAccess 权限的人) 可以设置收件箱规则, 将项目从特定的 "LinkedIn 公司" 页面移至特定文件夹。 如果存储邮箱用于存档从不同第三方数据源导入的项目, 这将非常有用。 例如, 您可以创建收件箱规则, 将 "主题" 字段中包含特定 "LinkedIn 公司" 页面的所有项目移到特定文件夹中。
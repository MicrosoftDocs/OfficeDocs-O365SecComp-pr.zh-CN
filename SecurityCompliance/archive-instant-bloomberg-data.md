---
title: 设置连接器以在 Office 365 中存档即时 Bloomberg 数据 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器以将数据从即时 Bloomberg 聊天工具导入 Office 365。 这使您可以在 Office 365 中存档第三方数据源中的数据, 以便您可以使用合规性功能 (如法律封存、内容搜索和保留策略) 来管理组织的第三方数据。
ms.openlocfilehash: 0b69ddaa21196bd0e149eba672fec104eabe2e5e
ms.sourcegitcommit: ab16ddf4c050a995471a058150767a0778be0b88
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35431593"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data-in-office-365-preview"></a>设置连接器以在 Office 365 中存档即时 Bloomberg 数据 (预览)

在 Office 365 中存档即时 Bloomberg 数据的连接器功能处于预览阶段。

使用 Office 365 的 Security & 合规性中心中的本机连接器从[即时 Bloomberg](https://www.bloomberg.com/professional/product/collaboration/)协作工具导入和存档金融 services 聊天数据。 在设置和配置连接器后, 它每天连接到组织的 Bloomberg 安全 FTP 站点 (SFTP), 将聊天消息的内容转换为电子邮件格式, 然后将这些项目导入 Office 365 中的邮箱。

将即时 Bloomberg 数据存储在用户邮箱中之后, 您可以将 Office 365 合规性功能 (如诉讼保留、内容搜索、就地存档、审核和 Office 365 保留策略) 应用于即时 Bloomberg 数据。 例如, 您可以使用内容搜索来搜索即时 Bloomberg 聊天邮件, 或将包含即时 Bloomberg 数据的邮箱与高级电子数据展示事例中的管理员关联起来。 使用即时 Bloomberg 连接器在 Office 365 中导入和存档数据可帮助您的组织遵守政府和法规策略。

## <a name="overview-of-archiving-instant-bloomberg-data"></a>存档即时 Bloomberg 数据概述

以下概述说明了使用连接器在 Office 365 中存档即时 Bloomberg 聊天数据的过程。 

![即时 Bloomberg 导入和存档过程](media/InstantBloombergDataArchiving.png)

1. 您的组织与 Bloomberg 配合使用来设置 Bloomberg SFTP 站点。 您还将使用 Bloomberg 将 "即时 Bloomberg" 配置为将聊天邮件复制到 Bloomberg SFTP 站点。

2. 每24小时一次, 来自即时 Bloomberg 的聊天邮件将复制到 Bloomberg SFTP 站点。
    
3. 您在安全 & 合规中心中创建的即时 Bloomberg 连接器每天连接到 Bloomberg SFTP 站点, 并将聊天消息从以前的24小时传输到 Microsoft 云中的安全 Azure 存储区域。 连接器还将聊天 massage 的内容转换为电子邮件格式。
    
4. 连接器将聊天邮件项目导入到特定用户的邮箱或备用邮箱。 连接器通过使用*CorporateEmailAddress*属性的值来执行。 每个聊天邮件都包含此属性, 该属性由聊天消息的每个参与者的电子邮件地址填充。 是否将项目导入特定用户邮箱或根据以下条件将项目导入备用邮箱:
    
    a. **CorporateEmailAddress 属性中具有与 office 365 用户帐户对应的值的项目**–如果该连接器可以将*CorporateEmailAddress*属性中的电子邮件地址与 office 365 中的特定用户帐户相关联, 则将项目复制到用户的 Office 365 邮箱中的 "收件箱" 文件夹中。
    
    b. **CorporateEmailAddress 属性中的值与 office 365 用户帐户不对应的项**–如果连接器无法将*CorporateEmailAddress*属性中的电子邮件地址与 office 中的特定用户帐户关联365, 将项目复制到 Office 365 中的替代 "捕获全部" 邮箱的 "收件箱" 文件夹中。

## <a name="before-you-begin"></a>开始之前

存档即时 Bloomberg 数据所需的许多实施步骤都是 Office 365 外部的, 并且必须先完成, 然后才能在安全 & 合规性中心中创建连接器。

- 订阅[Blooomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA)。 这是必需的, 以便您可以登录到 Bloomberg Anywhere 以访问您必须设置和配置的 Bloomberg SFTP 站点。

- 设置 Bloomberg SFTP (安全文件传输协议) 站点。 使用 Bloomberg 设置 SFTP 站点后, 即时 Bloomberg 中的数据每天都将上传到 SFTP 站点。 您在步骤2中创建的连接器将连接到此 SFTP 站点, 并将聊天数据传输到 Office 365 邮箱。 SFTP 还对在传输过程中发送到 Office 365 邮箱的即时 Bloomberg 聊天数据进行加密。

    有关 Bloomberg SFTP (也称为*BB-SFTP*) 的信息, 请执行以下操作:

    - 请参阅[Bloomberg 支持](https://www.bloomberg.com/professional/support/documentation/)中的 "SFTP 连接标准" 文档。
    
    - 请联系[Bloomberg 客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)部门。

    在使用 Bloomberg 设置 SFTP 站点之后, 在您响应 Bloomberg 实施电子邮件之后, Bloomberg 将为您提供一些信息。 保存以下信息的副本。 您可以使用它来设置步骤3中的连接器。

    - 固定代码, 它是组织的 ID, 用于登录到 Bloomberg SFTP 站点。

    - Bloomberg SFTP 站点的密码

    - Bloomberg SFTP 网站的 URL (例如, sftp.bloomberg.com)

    - Bloomberg SFTP 站点的端口号

- 您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 若要同意此请求, 请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), 使用 Office 365 全局管理员的凭据登录, 然后接受该请求。 您必须完成此步骤, 然后才能在步骤3中成功创建即时 Bloomberg 连接器。

- 在第3步 (以及在第1步中下载公钥和 IP 地址的用户) 中创建即时 Bloomberg 连接器的用户必须在 Exchange Online 中分配邮箱导入导出角色。 这是访问安全 & 合规中心中的 "**存档第三方数据**" 页所必需的。 默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者, 您可以创建角色组, 分配邮箱导入导出角色, 然后将相应的用户添加为成员。 有关详细信息, 请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>步骤 1: 获取 SSH 和 PGP 公钥

第一步是获取用于安全命令行管理程序 (SSH) 和相当出色的隐私 (PGP) 的公钥副本。 您可以在步骤2中使用这些键来配置 Bloomberg SFTP 站点, 以允许连接器 (在步骤3中创建) 连接到 SFTP 站点, 并将 "即时 Bloomberg" 聊天数据传输到 Office 365 邮箱。 您还可以在此步骤中获取 IP 地址, 在配置 Bloomberg SFTP 站点时使用此地址。

1. 转到<https://protection.office.com> , 然后单击 "**数据\>调控导入**", 然后单击 "**存档第三方数据**"。

2. 在 "**存档第三方数据**" 页上, 单击 "**添加一个连接器**", 然后单击 "**即时 Bloomberg**"。

3. 在 "**服务条款**" 页上, 单击 "**接受**"。

4. 在步骤1下的**BLOOMBERG SFTP 网站的 "添加凭据**" 中, 单击 "**下载 SSH 密钥**" 并**下载 "PGP 密钥**下载链接", 将每个公钥文件的副本保存到本地计算机。 这些文件包含以下将在步骤2中用于配置 Bloomberg SFTP 网站的项:

   - SSH 公钥–此密钥将用于配置安全命令行管理程序 (SSH), 以便在连接器连接到 Bloomberg SFTP 站点时启用安全的远程登录。

   - PGP 公钥–此密钥将用于配置从 Bloomberg SFTP 站点传输到 Office 365 的数据的加密。

   - IP 地址– Bloomberg SFTP 站点将配置为仅接受来自此 IP 地址的连接请求, 该请求由您在步骤3中创建的 "即时 Bloomberg" 连接器使用。 

5. 单击 "**取消**" 关闭该向导。 您将在步骤3中返回到此向导来创建连接器。

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>步骤 2: 配置 Bloomberg SFTP 站点

下一步是使用 SSH 和 PGP 公钥以及您在步骤1中获取的 IP 地址, 以配置 Bloomberg SFTP 站点的 SSH 身份验证和 PGP 加密。 这将允许您在步骤3中创建的即时 Bloomberg 连接器连接到 Bloomberg SFTP 站点, 并将即时 Bloomberg 数据传输到 Office 365。 如果你需要进行设置, 请联系[Bloomberg 客户支持](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)部门。

1. 使用您的组织的帐户登录到 Bloomberg CCNS "控制面板"。

2. 转到 "CCNS", 然后单击 "**公钥**" 选项卡。

3. 若要启用 SSH 身份验证, 请单击 "**添加**"。

4. 在 "**添加公钥**" 窗口中, 单击 "**密钥类型**" 下拉列表, 然后单击 "**登录**"。

5. 复制您在步骤1中下载的整个 SSH 公钥 (但不包括双引号), 并将其粘贴到此字段中, 然后单击 "**提交**" 以保存该注册表项。
 
    例如, 您可以复制以下 SSH 公钥:

    `
    ssh-rsa
    AAAAB3NzaC1yc2EAAAABIwAAAQEA1dxAyc0JzCmc5NzgyzRYhnj3FGHK5Kd9T2cwZNkmL/9nFhQupQor081rmuw9gACAmeot7y+V/fmijo/q4rxDe3Auu3hfLl1NpWlIssQJHzycms8zimtdQcXbMKwDQOnRthpEocF5ySs76KE72vaYQJTvclAamWWq0D75SUmXDFFr7afvEy57F7KgMD1ecg6lH7q8seSKbiiWxX1Ul0kL15fzpUyhjDP41owb1XC/dF7fJwAmCO1+HZfDLEp62q4tnApLpdd92KoR41LZTryO5dICKhk+S+JxPLkksxL0wm5YevOr2n4ScuRdsBV8mWKZ1Xw+cOss9O6L7cCcEiB3Ow==
    `

6. 若要启用 PGP 加密, 请再次单击 "**公钥**" 选项卡上的 "**添加**", 单击 "**密钥类型**" 下拉列表, 这次单击 "**加密**"。

7. 复制您在步骤1中下载的整个 PGP 公钥 (但不包括双引号), 并将其粘贴到此字段中, 然后单击 "**提交**" 以保存该注册表项。 

    例如, 您可以复制以下 PGP 公钥:

    `
    -----BEGIN PGP PUBLIC KEY BLOCK-----
    Version: BCPG C# v1.7.4137.9688
    nmQENBFz+6UQBCACKC4ilYoVOP5b/F0CO+oQYbag79Ov4NZxM4EKW51lUAvKNExRM\nc1C/gwXm8bghht8GEODckXXqx8qSSXUEeA/ROweXNtD1u1kn7PgYEFUeD/qE739m\nm5lxXF9Vod26AtKQ9Y1EvYoQEltwztAaXg8K8LQzB+tzN079d1cxM5tbiRQLttAh\nOt5amLXuINt8+dWyNas3DfgIBUmwfkwCbUO0ElrIhvvO3A85K97SX9Q6Py0SkfkK\nQpnULuhdjSm+7k7qlVMf0s8e/9jUXYKbMFkxlOoMq052vV0l0VQNSeuKoC+m6+LT\nEPab89AMt6S4Ujum9wTUy1eWNx9vV0y/w8N7ABEBAAG0JDM5MjM4ZTg3LWI1YWIt\nNGVmNi1hNTU5LWFmNTRjNmIwN2I0MokBHAQQAQIABgUCXP7pRAAKCRAJQdjaG//S\nCy70B/wKrR2CcqtZx56yrGJFfVy3niEt16VEA3xJM3D9nX0gmgo85Nh5gkiY3ahH\nnNEmgW5vlCM1gcgFeoZWe8A80G4QoabslSUzLbq9HsHOOAQApsfhrhXpylrAVa4n\nI53XUOxWdOTa4xsOob8hSRADqJbwHPOsoAr2A87TvZ9LSi2Mii5omeTq416CLnoS\nPBAEhelZm+ruy5JhzA1yXvWYFH08wNqSHO3bskdES2yW5SyQmYlcoEztWE0Q0Z+G\nZT3kOa/W2MbcZovFCQIfqhwVfXtIzx5uYUmxgk5cFKUJJMlO0AZK/HwM22xuuIWe\ndMa6OMo/n8tvEBxrLQMdVPlz+hZ6
    =AwmP
    -----END PGP PUBLIC KEY BLOCK-----
    `
8. 返回到 CCNS 控制面板主窗口中的 "在**此处添加 IP 地址**" 下, 在 "**添加地址" 字段**中输入以下 IP 地址 (包含在您在步骤1中下载的 Keys .txt 文件中)。

   `
   40.124.28.216
   `

## <a name="step-3-create-an-instant-bloomberg-connector"></a>步骤 3: 创建即时 Bloomberg 连接器

最后一步是在安全 & 合规性中心中创建一个即时 Bloomberg 连接器。 连接器使用您提供的信息连接到 Bloomberg SFTP 站点, 并将聊天邮件传输到 Office 365 中对应的用户邮箱框中。 

1. 转到<https://protection.office.com> , 然后单击 "**数据\>调控导入**", 然后单击 "**存档第三方数据**"。

2. 在 "**存档第三方数据**" 页上, 单击 "**添加一个连接器**", 然后单击 "**即时 Bloomberg**"。

3. 在 "**服务条款**" 页上, 单击 "**接受**"。

4. 在 "**添加 BLOOMBERG SFTP 网站的凭据**" 页上的 "步骤 3" 中的以下框中, 输入所需信息, 然后单击 "**下一步**"。

    - **固定代码**–您的组织的 ID, 用作 Bloomberg SFTP 站点的用户名。

    - **Password** – Bloomberg SFTP 站点的密码

    - **SFTP url** – Bloomberg SFTP 网站的 URL (例如, sftp.bloomberg.com)。

    - **SFTP 端口**– Bloomberg SFTP 站点的端口号。 连接器使用此连接到 SFTP 站点。

5. 在 "**备用邮箱**" 页上, 键入将用于存储来自即时 Bloomberg 的聊天消息的邮箱的电子邮件地址, 这些消息无法与组织中的用户邮箱相关联。

   > [!NOTE]
   > Bloomberg 中每个对话中的每个聊天邮件都包含一个名为*CorporateEmailAddress*的属性, 其中包含您的聊天参与者的组织的电子邮件地址。 在导入过程中, 连接器将尝试将聊天邮件导入到 Office 365 中的用户邮箱, 该邮箱与*CorporateEmailAddress*属性中的电子邮件地址相匹配。 如果没有 Office 365 邮箱与*CorporateEmailAddress*属性中的地址相同, 则连接器会将聊天消息导入您在此页面上指定的备用邮箱。 目前, Office 365 中的监督策略不会监视存档在备用邮箱中的即时 Bloomberg 聊天邮件。

6. 单击 "**下一步**", 查看设置, 然后单击 "**准备**" 以创建连接器。

7. 转到 "**存档第三方数据**" 页, 查看新连接器的导入过程的进度。

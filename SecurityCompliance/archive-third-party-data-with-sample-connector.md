---
title: 使用示例连接器在 Office 365 中存档第三方数据 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理员可以设置本机连接器, 以便从数据源 (如 Facebook 商业页面、LinkedIn 公司网页和即时 Bloomberg) 导入第三方数据。 这使您可以在 Office 365 中存档第三方数据源中的数据, 以便您可以使用合规性功能 (如法律封存、内容搜索和保留策略) 来管理组织的第三方数据的管理。
ms.openlocfilehash: bca193753d0a63de867bdb11cfce3918c124f429
ms.sourcegitcommit: 63a10dc5ffa9d709fac437d3fc9e554b1bcd826f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "33307763"
---
# <a name="use-sample-connectors-to-archive-third-party-data-in-office-365-preview"></a>使用示例连接器在 Office 365 中存档第三方数据 (预览)

在 Office 365 中存档第三方数据的示例连接器功能处于预览阶段。

使用 Office 365 中安全 & 合规中心中的示例连接器从第三方数据源 (如 Facebook、LinkedIn、Twitter 和 Bloomberg) 导入和存档数据。 在设置和配置示例连接器之后, 它会连接到第三方数据源 (定期), 将项目的内容转换为电子邮件格式, 然后将这些项目导入到 Office 365 中的邮箱中。

导入第三方数据后, 可以将 Office 365 合规性功能 (如诉讼保留、内容搜索、就地存档、审核、监督和 Office 365 保留策略) 应用于第三方数据。 例如, 当将邮箱置于诉讼保留状态或分配到保留策略时, 将保留第三方数据。 您可以使用内容搜索来搜索第三方数据, 或将其与高级电子数据展示事例中的保管人程序相关联。 使用示例连接器在 Office 365 中导入和存档第三方数据可帮助您的组织遵守政府和法规策略。

> [!NOTE]
> 目前, 只有 Facebook 商业页面的示例连接器可供预览。 即将推出更多示例连接器。


## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>设置用于 Facebook 商业页面的连接器的先决条件

您必须先完成以下先决条件, 然后才能在安全 & 合规中心中设置和配置示例连接器, 以便从组织的 Facebook 商业页面导入和存档数据。 

- 您的组织的业务页面需要一个 Facebook 帐户 (在设置连接器时, 需要登录到此帐户)。 目前, 您只能存档 Facebook 商业页面中的数据;您不能存档单个 Facebook 配置文件中的数据。

- 您的组织必须具有有效的 Azure 订阅。 如果你没有现有的 Azure 订阅, 你可以注册以下选项之一:

    - [注册免费的1年 Azure 订阅](https://azure.microsoft.com/free) 

    - [注册 "转到即点即用 Azure 订阅"](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Office 365 订阅附带的[免费 Azure Active Directory 订阅](use-your-free-azure-ad-subscription-in-office-365.md)不支持 Security & 合规中心中的示例连接器。

- 您的组织必须同意允许 Office 365 导入服务访问组织中的邮箱数据。 若要同意此请求, 请转到[此页](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), 使用 Office 365 全局管理员的凭据登录, 然后接受该请求。

- 在安全 & 合规性 (步骤 7) 中设置自定义连接器的用户必须在 Exchange Online 中分配邮箱导入导出角色。 默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。 或者, 您可以创建新的角色组, 分配邮箱导入导出角色, 然后将相应的用户添加为成员。 有关详细信息, 请参阅文章 "管理 Exchange Online 中的角色组" 中的 "[创建角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)" 或 "[修改角色组](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)" 部分。

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a>步骤 1: 从 Github 下载预建的连接器应用程序包

第一步是下载预构建的 Facebook 连接器应用程序的源代码, 该应用程序将使用 facebook API 连接到你的 facebook 商业页面并提取 facebook 数据, 以便可以将其导入 Office 365。

1. 转到[此 GitHub 网站](https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases)。 
2. 在最新版本下, 单击 " **SampleConnector** " 文件。
3. 将 ZIP 文件保存到本地计算机上的某个位置。 你将在步骤4中将此 zip 文件上传到 Azure。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>步骤 2: 在 Azure Active Directory 中创建应用程序

下一步是在 Azure Active Directory (AAD) 中注册新应用程序。 此应用程序将对应于您将在第4步中为 Facebook 连接器实现的 web 应用资源。 

有关分步说明, 请参阅[在 Azure Active Directory 中创建应用](deploy-facebook-connector.md#step-2-create-an-app-in-azure-active-directory)。

在完成此步骤 (按照分步说明操作) 后, 您将把以下信息保存到文本文件中。 这些值将在部署过程的后续步骤中使用。

- AAD 应用程序 ID
- AAD 应用程序密码
- AAD 应用程序 Uri
- 租户 Id

## <a name="step-3-create-an-azure-storage-account"></a>步骤 3: 创建 Azure 存储帐户

您为组织部署的 facebook 连接器会将您的 facebook 商业页面中的项目上载到您在此步骤中创建的 Azure 存储位置。 在 Security & 合规中心 (步骤 7) 中创建自定义连接器后, office 365 导入服务会将 Facebook 数据从 Azure 存储位置复制到 Office 365 中的邮箱。 如前面的 "[先决条件](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)" 部分中所述, 您必须具有有效的 azure 订阅才能创建 azure 存储帐户。

有关分步说明, 请参阅[创建 Azure 存储帐户](deploy-facebook-connector.md#step-3-create-an-azure-storage-account)。

在完成此步骤 (按照分步说明操作) 后, 将保存生成的连接字符串 Uri。 在第4步中的 Azure 中创建 web 应用资源时, 将使用此字符串。

## <a name="step-4-create-a-web-app-resource-in-azure"></a>步骤 4: 在 Azure 中创建 web 应用资源

下一步是在 Azure 中为 Facebook 连接器创建 web 应用资源。 

有关分步说明, 请参阅[在 Azure 中创建新的 web 应用资源](deploy-facebook-connector.md#step-4-create-a-new-web-app-resource-in-azure)。

在完成此步骤 (按照分步说明操作) 后, 您将在创建 web 应用资源时提供以下信息 (在完成前面的步骤之后, 您已将其复制到文本文件中)。

- APISecretKey –你将在完成此步骤过程中创建此密码;它将在步骤7中使用。
- StorageAccountConnectionString –在步骤3中创建 Azure 存储帐户后复制的连接字符串 Uri。
- tenantId –在步骤2中创建 Azure Active Directory 中的 Facebook 连接器应用之后复制的 Office 365 组织的租户 ID。

此外, 在此步骤中, 您将上载在步骤1中下载的 SampleConnector 文件, 以部署 Facebook 连接器应用程序的源代码。

完成此步骤后, 请务必复制应用服务 URL (例如, https://fbconnector.azurewebsites.net)。 您需要使用此操作来完成步骤5、步骤6和步骤7。

## <a name="step-5-register-the-web-app-on-facebook"></a>步骤 5: 在 Facebook 上注册 web 应用程序

下一步是在 Facebook 上创建和配置新的应用程序。 您在步骤7中创建的自定义连接器将使用 facebook web 应用与 facebook API 进行交互, 以从组织的 Facebook 商业版页面中获取数据。

有关分步说明, 请参阅[注册 Facebook 应用](deploy-facebook-connector.md#step-5-register-the-facebook-app)。

在完成此步骤 (按照分步说明操作) 后, 您将把以下信息保存到文本文件中。 这些值将用于配置步骤6中的 Facebook 连接器应用。

- Facebook 应用程序 ID
- Facebook 应用程序密码
- Facebook webhook verify token

## <a name="step-6-configure-the-facebook-connector-app"></a>步骤 6: 配置 Facebook 连接器应用程序

下一步是将配置设置添加到在步骤4中创建 Azure web 应用资源时上载的 Facebook 连接器应用。 你将通过转到连接器应用的主页并对其进行配置来执行此操作。

有关分步说明, 请参阅 "[步骤 6: 配置连接器 web 应用程序"](deploy-facebook-connector.md#step-6-configure-the-connector-web-app)。

在完成此步骤 (按照分步说明操作) 后, 您将提供以下信息 (在完成上述步骤后, 您已将其复制到文本文件中):

- Facebook 应用程序 ID (在步骤5中获取)
- Facebook 应用程序密码 (在步骤5中获取)
- Facebook webhook verify token (在步骤5中获取)
- Azure Active Directory 应用程序 id (在步骤2中获取的 AAD 应用程序 id)
- Azure Active Directory 应用程序密码 (在步骤2中获取的 AAD 应用程序密码)
- Azure Active Directory 应用程序 uri (在步骤2中获取的 AAD 应用程序 uri; 例如,https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>步骤 7: 在安全 & 合规中心中设置自定义连接器

最后一步是在安全 & 合规性中心中设置自定义连接器, 以将来自 Facebook 商业页面的数据导入 Office 365 中的指定邮箱。 在成功完成此步骤后, Office 365 导入服务将启动从 Facebook 商业版页面向 Office 365 导入数据的过程。 

有关分步说明, 请参阅[在安全 & 合规中心中设置自定义连接器](deploy-facebook-connector.md#step-7-set-up-a-custom-connector-in-the-security--compliance-center)。 

在完成此步骤 (按照分步说明操作) 后, 您将提供以下信息 (在完成这些步骤后, 您已将其复制到文本文件中)。

- Azure 应用服务 URL (在步骤4中获取; 例如https://fbconnector.azurewebsites.net)
- APISecretKey (您在步骤4中创建)

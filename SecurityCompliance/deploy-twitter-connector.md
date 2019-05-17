---
title: 部署连接器以在 Office 365 中存档 Twitter 数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理员可以设置本机连接器以将 Twitter 数据导入和存档到 Office 365。 将此数据导入 Office 365 后, 您可以使用合规性功能 (如法律封存、内容搜索和保留策略) 来管理组织的 Twitter 数据的管理。
ms.openlocfilehash: 2f9d4842a834858b40e1d788f34f4fb8b2d5b9fd
ms.sourcegitcommit: 5bd7a97aeab1c89e0a3660ba7bdb3200224107a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2019
ms.locfileid: "34103763"
---
# <a name="deploy-a-connector-to-archive-twitter-data-in-office-365"></a>部署连接器以在 Office 365 中存档 Twitter 数据

本文包含的分步过程可部署使用 Office 365 导入服务将数据从组织的 Twitter 帐户导入 Office 365 的连接器。 有关此过程的高级概述以及部署 Twitter 连接器所需的先决条件列表, 请参阅[使用示例连接器在 Office 365 中存档 Twitter 数据 (预览)](archive-twitter-data-with-sample-connector.md)。 

## <a name="step-1-download-the-package"></a>步骤 1: 下载程序包

从位于 GitHub 存储库中的 "发布" 部分下载预[https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)建程序包 (网址为)。 在最新版本下, 下载名为**SampleConnector**的 zip 文件。 你将在步骤4中将此 zip 文件上传到 Azure。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>步骤 2: 在 Azure Active Directory 中创建应用程序

1. 转到<https://portal.azure.com>并使用 Office 365 全局管理员帐户的凭据登录。

   ![](media/TCimage01.png)

2. 在左侧导航窗格中, 单击 " **Azure Active Directory**"。

   ![](media/TCimage02.png)

3. 在左侧导航窗格中, 单击 "**应用程序注册 (预览)** ", 然后单击 "**新建注册**"。

   ![](media/TCimage03.png)

4. 注册应用程序。 在 "**重定向 URI (可选)**" 下, 选择 "应用程序类型" 下拉<https://portal.azure.com>列表中的 "Web", 然后在 URI 框中键入 uri。

   ![](media/TCimage04.png)

5. 复制**应用程序 (客户端) id**和**目录 (租户) id** , 并将其保存到文本文件或其他安全位置。 您将在后续步骤中使用这些 Id。

    ![](media/TCimage05.png)

6. 转到**证书 & 新应用程序的密码**, 在**客户端密码**下, 单击 "**新建客户端密码**"。

   ![](media/TCimage06.png)

7. 创建新的机密。 在 "说明" 框中, 键入密码, 然后选择一个过期时间段。 

   ![](media/TCimage08.png)

8. 复制密码的值, 并将其保存到文本文件或其他存储位置。 这是您将在后续步骤中使用的 AAD 应用程序密码。

   ![](media/TCimage09.png)

9. 转到**清单**并复制 identifierUris (也称为 AAD 应用程序 Uri), 如以下屏幕截图中所示。 将 AAD 应用程序 Uri 复制到文本文件或其他存储位置。 您将在步骤6中使用它。

    ![](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a>步骤 3: 创建 Azure 存储帐户

1.  转到您的组织的 Azure 主页。

    ![](media/TCimage11.png)

2. 单击 "**创建资源**", 然后在搜索框中键入**存储帐户**。

   ![](media/TCimage12.png)

3. 单击 "**存储**", 然后单击 "**存储帐户**"。

   ![](media/TCimage13.png)

4. 在 "**创建存储帐户**" 页上的 "订阅" 框中, 根据您拥有的 Azure 订阅的类型选择 "按即点**即**用" 或 "**免费试用**"。 

   ![](media/TCimage14.png)

5. 选择或创建一个资源组。

   ![](media/TCimage15.png)

6. 键入存储帐户的名称。

   ![](media/TCimage16.png)

7. 查看, 然后单击 "**创建**" 以创建存储帐户。

   ![](media/TCimage17.png)

8. 几分钟后, 单击 "**刷新**", 然后单击 "**转到资源**" 以导航到存储帐户。

   ![](media/TCimage18.png)

9. 单击左侧导航窗格中的 "**访问密钥**"。

   ![](media/TCimage19.png)

10. 复制**连接字符串**并将其保存到文本文件或其他存储位置。 在步骤4中创建 web 应用资源时, 将使用此操作。

    ![](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a>步骤 4: 在 Azure 中创建新的 web 应用资源

1. 在 Azure 门户的**主页**上, 单击 "**创建资源\>所有\> Web 应用程序**"。 在 " **Web 应用程序**" 页上, 单击 "**创建**"。

   ![](media/TCimage21.png)

2. 填写详细信息 (如下所示), 然后创建 Web 应用程序。 请注意, 您在 "**应用程序名称**" 框中输入的名称将用于创建 Azure 应用服务 URL;例如 twitterconnector.azurewebsites.net。

   ![](media/TCimage22.png)

3. 转到新创建的 web 应用资源, 在左侧导航窗格中单击 "**应用程序设置**"。 在 "**应用程序设置**" 下, 单击 "**添加新设置**", 然后添加以下三个设置。 使用从前面的步骤中复制到文本文件中的值: 

    - **APISecretKey** –您可以键入任何值作为密码。 这将用于在步骤7中访问连接器 web 应用。

    - **StorageAccountConnectionString** –在步骤3中创建 Azure 存储帐户后复制的连接字符串 Uri。

    - **tenantId** –在步骤2中创建 Azure Active Directory 中的 Twitter 连接器应用之后复制的 Office 365 组织的租户 ID。

    ![](media/TCimage23.png)

4. 在 "**常规设置**" 下, 单击 "**始终打开**" 旁边的 **""** 。 单击页面顶部的 "**保存**" 以保存应用程序设置。

   ![](media/TCimage24.png)

5. 最后一步是将连接器应用源代码上载到您在步骤1中下载的 Azure。 在 web 浏览器中, 转到<AzureAppResourceName>https://。 scm.azurewebsites.net/ZipDeployUi。 例如, 如果您的 Azure 应用资源的名称 (在此部分中的步骤2中命名) 为**twitterconnector**, 则您将转到https://twitterconnector.scm.azurewebsites.net/ZipDeployUi。

6. 将 SampleConnector (您在步骤1中下载的) 拖放到此页面。 上载文件并成功部署后, 页面外观将类似于以下屏幕截图。

   ![](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a>步骤 5: 创建 Twitter 应用

1. 转到https://developer.twitter.com, 使用组织的开发人员帐户的凭据登录, 然后单击 "**应用**"。

   ![TCimage25-5](media/TCimage25-5.png)
2. 单击 "**创建应用程序**"。
   
   ![](media/TCimage26.png)

3. 在 "**应用程序详细信息**" 下, 添加有关应用程序的信息。

   ![](media/TCimage27.png)

4. 在 Twitter 开发人员仪表板上, 选择刚创建的应用程序, 并复制显示的应用 ID 并将其保存到文本文件或其他存储位置。 然后单击 "**详细信息**"。
   
   ![](media/TCimage28.png)

5. 在 "**密钥和标记**" 选项卡上的 "**使用者 api 密钥**" 下, 复制 api 密钥并将其保存到文本文件或其他存储位置。 然后, 单击 "**创建**" 以生成访问令牌和访问令牌机密, 并将它们复制到文本文件或其他存储位置。
   
   ![](media/TCimage29.png)

   然后, 单击 "**创建**" 以生成访问令牌和访问令牌机密, 并将它们复制到文本文件或其他存储位置。

6. 单击 "**权限**" 选项卡并配置权限, 如以下屏幕截图所示:

   ![](media/TCimage30.png)

7. 保存权限设置后, 单击 "**应用程序详细信息**" 选项卡, 然后单击 "**编辑 _GT_" "编辑详细信息**"。

   ![](media/TCimage31.png)

8. 执行以下任务:

   - 选中此复选框可允许连接器应用登录 Twitter。
   
   - 使用以下格式添加 OAuth 重定向 Uri: ** \<connectorserviceuri>/Views/TwitterOAuth**, 其中*connectorserviceuri*的值为您的组织的 Azure 应用服务 URL;例如https://twitterconnector.azurewebsites.net/Views/TwitterOAuth。

   ![](media/TCimage32.png)

现在可以使用 Twitter 开发人员应用。

## <a name="step-6-configure-the-connector-web-app"></a>步骤 6: 配置连接器 web 应用程序 

1. 转到 https://\<AzureAppResourceName> (其中**AzureAppResourceName**是您在步骤4中命名的 Azure 应用程序资源的名称) 例如, 如果名称为**twitterconnector**, 请转到https://twitterconnector.azurewebsites.net。 该应用程序的主页看起来将类似下面的屏幕截图。

   ![](media/FBCimage41.png)

2. 单击 "**配置**" 以显示登录页。

   ![](media/FBCimage42.png)

3. 在 "租户 Id" 框中, 键入或粘贴您在步骤2中获取的租户 Id。 在 "密码" 框中, 键入或粘贴 APISecretKey (您在步骤2中获取), 然后单击 "**设置配置设置**" 以显示 "**配置详细信息**" 页。

   ![](media/TCimage35.png)

4. 在 "**配置详细信息**" 下, 输入以下配置设置 

   - **Twitter 应用程序 id** -您在步骤5中创建的 twitter 应用程序的应用程序 id。
   - **Twitter 应用程序密码**-您在步骤5中创建的 Twitter 应用程序的 API 密钥。
   - **Twitter 客户端令牌**-您在步骤5中创建的访问令牌。
   - **Twitter 客户端令牌密码**-您在步骤5中创建的访问令牌密码。
   - **AAD 应用程序 id** -您在步骤2中创建的 Azure Active Directory 应用程序的应用程序 id
   - **AAD 应用程序密码**-您在步骤4中创建的 APISecretKey 密码的值。
   - **AAD 应用程序 uri** -在步骤2中获取的 aad 应用程序 uri;例如, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213。
   - **App insights 检测键**-将此框保留为空。

5. 单击 "**保存**" 以保存连接器设置。

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a>步骤 7: 在安全与合规中心中设置自定义连接器

1.  转到<https://protection.office.com> , 然后单击 "**数据\>调控\>导入存档第三方数据**"。

    ![](media/TCimage36.png)

2. 单击 "**添加连接器**", 然后单击 " **Twitter**"。

   ![](media/TCimage37.png)

3. 在 "**添加连接器应用程序**" 页上, 输入以下信息, 然后单击 "**验证连接器**"。

    - 在第一个框中, 键入连接器的名称, 如**Twitter**。
    - 在第二个框中, 键入或粘贴您在步骤4中添加的 APISecretKey 的值。
    - 在第三个框中, 键入或粘贴 Azure 应用服务 URL;例如**https://twitterconnector.azurewebsites.net**。

   成功验证连接器后, 单击 "**下一步**"。

   ![](media/TCimage38.png)

4. 单击 "**使用连接器应用登录**"。

   ![](media/TCimage39.png)

5. 再次键入或粘贴 APISecretKey, 然后单击 "**登录到连接器服务**"。

   ![](media/TCimage40.png)


6. 单击 "**继续使用 Twitter**。

7. 在 Twitter 登录页面上, 使用组织的 Twitter 帐户的帐户的凭据进行登录。

   ![](media/TCimage42.png)

   登录后, Twitter 页面将显示以下消息: "已成功设置 Twitter 连接器作业"。

8. 单击 "**完成**" 以完成 Twitter 连接器的设置。

9. 在 "**设置筛选器**" 页上, 可以应用筛选器以导入 (和存档) 特定时间的项目。 单击“下一步”。****

   ![](media/TCimage44.png)

10. 在 "**设置存储帐户**" 页上, 选择要将 Twitter 项目导入到的 Office 365 邮箱。

    ![](media/TCimage45.png)

11. 查看您的设置, 然后单击 "**完成**" 以完成 Security _AMP_ 合规性中心中的连接器设置。

    ![](media/TCimage46.png)

    ![](media/TCimage47.png)

12. 转到 "**存档第三方数据**" 页, 查看导入过程的进度。

    ![](media/TCimage48.png)

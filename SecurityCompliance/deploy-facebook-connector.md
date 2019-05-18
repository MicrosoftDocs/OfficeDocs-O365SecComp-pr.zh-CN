---
title: 在 Office 365 中部署用于存档 Facebook 数据的连接器
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理员可以设置本机连接器以将 Facebook 商业页面导入和存档到 Office 365。 将此数据导入 Office 365 后, 您可以使用合规性功能 (如法律封存、内容搜索和保留策略) 来管理组织的 Facebook 数据的管理。
ms.openlocfilehash: b0ec46cea2dd5722633e7fc302cdd0d03cd5d56d
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150554"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a>在 Office 365 中部署用于存档 Facebook 数据的连接器

本文包含了部署使用 Office 365 导入服务将数据从 Facebook 商业页面导入 Office 365 的连接器的分步过程。 有关此过程的简要概述以及部署 Facebook 连接器所需的先决条件列表, 请参阅[使用示例连接器存档 Office 365 中的 Facebook 数据 (预览)](archive-facebook-data-with-sample-connector.md)。 

## <a name="step-1-download-the-package"></a>步骤 1: 下载程序包

从位于 GitHub 存储库中的 "发布" 部分下载预建<https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>程序包。 在最新版本下, 下载名为**SampleConnector**的 zip 文件。 你将在步骤4中将此 zip 文件上传到 Azure。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>步骤 2: 在 Azure Active Directory 中创建应用程序

1. 转到<https://portal.azure.com>并使用 Office 365 全局管理员帐户的凭据登录。

    ![在 AAD 中创建应用程序](media/FBCimage1.png)

2. 在左侧导航窗格中, 单击 " **Azure Active Directory**"。

    ![](media/FBCimage2.png)

3. 在左侧导航窗格中, 单击 "**应用程序注册 (预览)** ", 然后单击 "**新建注册**"。

    ![](media/FBCimage3.png)

4. 注册应用程序。 在 "重定向 URI" 下, 选择 "应用程序类型" 下拉<https://portal.azure.com>列表中的 "Web", 然后为 URI 键入相应的框。

   ![](media/FBCimage4.png)

5. 复制**应用程序 (客户端) id**和**目录 (租户) id** , 并将其保存到文本文件或其他安全位置。 您将在后续步骤中使用这些 Id。

   ![](media/FBCimage5.png)

6. 转到**证书 & 新应用程序的密码。**

   ![](media/FBCimage6.png)

7. 单击 "**新建客户端密码**"

   ![](media/FBCimage7.png)

8. 创建新的机密。 在 "说明" 框中, 键入密码, 然后选择一个过期时间段。 

    ![](media/FBCimage8.png)

9. 复制密码的值, 并将其保存到文本文件或其他存储位置。 这是您将在后续步骤中使用的 AAD 应用程序密码。

   ![](media/FBCimage9.png)

10. 转到**清单**并复制 identifierUris (也称为 AAD 应用程序 Uri), 如以下屏幕截图中所示。 将 AAD 应用程序 Uri 复制到文本文件或其他存储位置。 您将在步骤6中使用它。

   ![](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a>步骤 3: 创建 Azure 存储帐户

1. 转到您的组织的 Azure 主页。

    ![](media/FBCimage11.png)

2. 单击 "**创建资源**", 然后在搜索框中键入**存储帐户**。

    ![](media/FBCimage12.png)

3. 单击 "**存储**", 然后单击 "**存储帐户**"。

    ![](media/FBCimage13.png)

4. 在 "**创建存储帐户**" 页上的 "订阅" 框中, 根据您拥有的 Azure 订阅的类型选择 "按即点**即**用" 或 "**免费试用**"。 然后, 选择或创建一个资源组。

    ![](media/FBCimage14.png)

5. 键入存储帐户的名称。

    ![](media/FBCimage15.png)

6. 查看, 然后单击 "**创建**" 以创建存储帐户。

    ![](media/FBCimage16.png)

7. 几分钟后, 单击 "**刷新**", 然后单击 "**转到资源**" 以导航到存储帐户。

    ![](media/FBCimage17.png)

8. 单击左侧导航窗格中的 "**访问密钥**"。

    ![](media/FBCimage18.png)

9. 复制**连接字符串**并将其保存到文本文件或其他存储位置。 您将在创建 web 应用资源时使用它。

    ![](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a>步骤 4: 在 Azure 中创建新的 web 应用资源

1. 在 Azure 门户的**主页**上, 单击 "**创建资源\>所有\> Web 应用程序**"。 在 " **Web 应用程序**" 页上, 单击 "**创建**"。 

   ![](media/FBCimage20.png)

2. 填写详细信息 (如下所示), 然后创建 Web 应用程序。 请注意, 您在 "**应用程序名称**" 框中输入的名称将用于创建 Azure 应用服务 URL;例如 fbconnector.azurewebsites.net。

   ![](media/FBCimage21.png)

3. 转到新创建的 web 应用资源, 在左侧导航窗格中单击 "**应用程序设置**"。 在 "应用程序设置" 下, 单击 "添加新设置", 然后添加以下三个设置。 使用从前面的步骤中复制到文本文件中的值: 

    - **APISecretKey** –您可以键入任何值作为密码。 这将用于在步骤7中访问连接器 web 应用。

    - **StorageAccountConnectionString** –在步骤3中创建 Azure 存储帐户后复制的连接字符串 Uri。

    - **tenantId** –在步骤2中创建 Azure Active Directory 中的 Facebook 连接器应用之后复制的 Office 365 组织的租户 ID。

    ![](media/FBCimage22.png)

4. 在 "**常规设置**" 下, 单击 "**始终打开**" 旁边的 **""** 。 单击页面顶部的 "**保存**" 以保存应用程序设置。

   ![](media/FBCimage23.png)

5. 最后一步是将连接器应用源代码上载到您在步骤1中下载的 Azure。 在 web 浏览器中, 转到<AzureAppResourceName>https://. scm.azurewebsites.net/ZipDeployUi。 例如, 如果您的 Azure 应用资源的名称 (在此部分中的步骤2中命名) 为**fbconnector**, 则您将转到https://fbconnector.scm.azurewebsites.net/ZipDeployUi。 

6. 将 SampleConnector (您在步骤1中下载的) 拖放到此页面。 上载文件并成功部署后, 页面外观将类似于以下屏幕截图。

   ![](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a>步骤 5: 注册 Facebook 应用程序

1. 转到<https://developers.facebook.com> , 使用组织的 Facebook 商业版页面的帐户登录, 然后单击 "**添加新应用**"。

   ![](media/FBCimage25.png)

2. 创建新的应用程序 ID。

   ![](media/FBCimage26.png)

3. 在左侧导航窗格中, 单击 "**添加产品**", 然后单击 " **Facebook 登录**磁贴" 中的 "**设置**"。

   ![](media/FBCimage27.png)

4. 在 "集成 Facebook 登录" 页上, 单击 " **Web**"。

   ![](media/FBCimage28.png)

5. 添加 Azure 应用服务 URL;例如https://fbconnector.azurewebsites.net。

   ![](media/FBCimage29.png)

6. 完成 Facebook 登录设置的快速入门部分。

   ![](media/FBCimage30.png)

7. 在 " **Facebook Login**" 下的左侧导航窗格中, 单击 "**设置**", 然后在 "**有效 OAuth 重定向 Uri** " 框中添加 OAuth 重定向 uri。使用** \<connectorserviceuri>/Views/FacebookOAuth**的格式, 其中 connectorserviceuri 的值是您的组织的 Azure 应用服务 URL;例如https://fbconnector.azurewebsites.net。

   ![](media/FBCimage31.png)

8. 在左侧导航窗格中, 单击 "**添加产品**", 然后单击 " **webhook"。** 在 "**页面**" 下拉菜单中, 单击 "**页面**"。 

   ![](media/FBCimage32.png)

9. 添加 Webhook 回调 URL 并添加验证令牌。 回调 URL 的格式, 使用格式** <connectorserviceuri>/api/FbPageWebhook**, 其中 connectorserviceuri 的值是您的组织的 Azure 应用服务 URL;例如https://fbconnector.azurewebsites.net。 

    验证令牌应类似于强密码。 将验证令牌复制到文本文件或其他存储位置。

     ![](media/FBCimage33.png)

10. 测试并订阅源终结点。

    ![](media/FBCimage34.png)

11. 添加隐私 URL、应用程序图标和业务使用。 此外, 将应用程序 ID 和应用程序密码复制到文本文件或其他存储位置。

    ![](media/FBCimage35.png)

12. 将应用程序公开。

    ![](media/FBCimage36.png)

13. 将用户添加到 "管理员" 或 "测试人员" 角色。

    ![](media/FBCimage37.png)

14. 添加**页面公共内容访问**权限。

    ![](media/FBCimage38.png)

15. 添加 "管理页面" 权限。

    ![](media/FBCimage39.png)

16. 获取由 Facebook 审阅的应用程序。

    ![](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a>步骤 6: 配置连接器 web 应用程序

1. 转到 https://\<AzureAppResourceName> (其中 AzureAppResourceName 是您在步骤4中命名的 Azure 应用程序资源的名称) 例如, 如果名称为**fbconnector**, 请转到https://fbconnector.azurewebsites.net。 该应用程序的主页看起来将类似下面的屏幕截图。


   ![](media/FBCimage41.png)

2. 单击 "**配置**" 以显示登录页。
 
   ![](media/FBCimage42.png)

3. 在 "租户 Id" 框中, 键入或粘贴您在步骤2中获取的租户 Id。 在 "密码" 框中, 键入或粘贴 APISecretKey (您在步骤2中获取), 然后单击 "**设置配置设置**" 以显示 "**配置详细信息**" 页。

    ![](media/FBCimage43.png)


4. 在 "**配置详细信息**" 下, 输入以下配置设置 

   - **Facebook 应用程序 id** -您在步骤5中获取的 facebook 应用程序的应用程序 id。
   - **Facebook 应用程序密码**-您在步骤5中获取的 facebook 应用程序的应用程序密码。
   - **Facebook webhook verify token** -您在步骤5中创建的验证令牌。
   - **AAD 应用程序 id** -您在步骤2中创建的 Azure Active Directory 应用程序的应用程序 id。
   - **AAD 应用程序密码**-您在步骤4中创建的 APISecretKey 密码的值。
   - **AAD 应用程序 uri** -在步骤2中获取的 aad 应用程序 uri;例如, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213。
   - **App insights 检测键**-将此框保留为空。

5. 单击 "**保存**" 以保存连接器设置。

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>步骤 7: 在安全 & 合规中心中设置自定义连接器

1. 转到<https://protection.office.com> , 然后单击 "**数据\>调控\>导入存档第三方数据**"。

   ![](media/FBCimage44.png)

2.  单击 "**添加连接器**", 然后单击 " **Facebook 页面**"。

    ![](media/FBCimage46.png)

3.  在 "**添加连接器应用程序**" 页上, 输入以下信息, 然后单击 "**验证连接器**"。

    - 在第一个框中, 键入连接器的名称, 例如**Facebook**。
    - 在第二个框中, 键入或粘贴您在步骤4中添加的 APISecretKey 的值。
    - 在第三个框中, 键入或粘贴 Azure 应用服务 URL;例如**https://fbconnector.azurewebsites.net**。
 
    成功验证连接器后, 单击 "**下一步**"。
    
    ![](media/FBCimage47.png)

4.  单击 "**使用连接器应用登录**"。

    ![](media/FBCimage45.png)

5. 再次键入或粘贴 APISecretKey, 然后单击 "**登录到连接器服务**"。

   ![](media/FBCimage48.png)


6. 单击 "**使用 Facebook 登录"。**

   ![](media/FBCimage49.png)

7. 在 "**登录到 Facebook** " 页上, 使用组织的 Facebook 商业版页面的帐户登录凭据。 确保您登录到的 Facebook 帐户已分配给您组织的 Facebook 商业页面的管理员角色

   ![](media/FBCimage50.png)

8. 单击 "**选择页面**", 选择您要在 Office 365 中存档的组织的业务页面。

   ![](media/FBCimage51.png)

9. 将显示您登录到的 Facebook 帐户所管理的商业页面的列表。 选择要存档的页面, 然后单击 "**保存**"。

    ![](media/FBCimage52.png)

10. 单击 "**完成**" 退出连接器服务应用程序的安装。

    ![](media/FBCimage53.png)

11. 在 "**设置筛选器**" 页上, 可以应用筛选器以导入 (和存档) 特定时间的项目。 单击“下一步”。****

    ![](media/FBCimage54.png)

12. 在 "**设置存储帐户**" 页上, 选择您之前选择的 Facebook 商业页面中的项目将导入到的 Office 365 邮箱。

    ![](media/FBCimage55.png)

13. 查看您的设置, 然后单击 "**完成**" 以完成 Security _AMP_ 合规性中心中的连接器设置。

    ![](media/FBCimage56.png)

14. 转到 "**存档第三方数据**" 页, 查看导入过程的进度。

    ![](media/FBCimage58.png)

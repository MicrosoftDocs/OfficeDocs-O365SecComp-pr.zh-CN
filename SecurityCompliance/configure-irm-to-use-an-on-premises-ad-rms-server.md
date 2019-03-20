---
title: 将 IRM 配置为使用本地 AD RMS 服务器
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: 本主题显示了如何将 IRM 配置为使用 AD RMS 服务器。
ms.openlocfilehash: 1da66c5afa37c96c061a4bf25c0858e4e71e2313
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693031"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a><span data-ttu-id="cc7d2-103">将 IRM 配置为使用本地 AD RMS 服务器</span><span class="sxs-lookup"><span data-stu-id="cc7d2-103">Configure IRM to use an on-premises AD RMS server</span></span>
  
<span data-ttu-id="cc7d2-104">对于本地部署, Exchange Online 中的信息权限管理 (IRM) 使用 Active Directory 权限管理服务 (AD RMS), 这是 Windows Server 2008 及更高版本中的一种信息保护技术。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-104">For use with on-premises deployments, Information Rights Management (IRM) in Exchange Online uses Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later.</span></span> <span data-ttu-id="cc7d2-105">通过将 AD RMS 权限策略模板应用于电子邮件，可将 IRM 保护应用于电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-105">IRM protection is applied to email by applying an AD RMS rights policy template to an email message.</span></span> <span data-ttu-id="cc7d2-106">权限附加到邮件本身, 以便在联机和脱机以及组织的防火墙内部和外部进行保护。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-106">Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>
  
<span data-ttu-id="cc7d2-107">本主题显示了如何将 IRM 配置为使用 AD RMS 服务器。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-107">This topic shows you how to configure IRM to use an AD RMS server.</span></span> <span data-ttu-id="cc7d2-108">有关在 azure Active Directory 和 azure 权限管理中使用 office 365 邮件加密的新功能的信息, 请参阅[Office 365 邮件加密 FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-108">For information about using the new capabilities for Office 365 Message Encryption with Azure Active Directory and Azure Rights Management, see the [Office 365 Message Encryption FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e).</span></span>
  
<span data-ttu-id="cc7d2-109">有关 Exchange Online 中 IRM 的详细信息，请参阅[Exchange Online 中的信息权限管理](information-rights-management-in-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-109">To learn more about IRM in Exchange Online, see [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cc7d2-110">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="cc7d2-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="cc7d2-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="cc7d2-111"></span></span>

- <span data-ttu-id="cc7d2-112">估计完成该任务的时间：30 分钟</span><span class="sxs-lookup"><span data-stu-id="cc7d2-112">Estimated time to complete this task: 30 minutes</span></span>
    
- <span data-ttu-id="cc7d2-p103">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的"信息权限管理"条目。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Information Rights Management" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="cc7d2-p104">AD RMS 服务器必须运行 Windows Server 2008 或更高版本。有关如何部署 AD RMS 的详细信息，请参阅[安装 AD RMS 群集](https://go.microsoft.com/fwlink/?LinkId=210873)。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-p104">The AD RMS server must be running Windows Server 2008 or later. For details about how to deploy AD RMS, see [Installing an AD RMS Cluster](https://go.microsoft.com/fwlink/?LinkId=210873).</span></span>
    
- <span data-ttu-id="cc7d2-117">有关如何安装和配置 Windows PowerShell 以及连接到服务的详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-117">For details about how to install and configure Windows PowerShell and connect to the service, see [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span></span>
    
- <span data-ttu-id="cc7d2-118">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="cc7d2-p105">遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="how-do-you-do-this"></a><span data-ttu-id="cc7d2-122">您该如何做？</span><span class="sxs-lookup"><span data-stu-id="cc7d2-122">How do you do this?</span></span>
<span data-ttu-id="cc7d2-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="cc7d2-123"></span></span>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a><span data-ttu-id="cc7d2-124">步骤 1：使用 AD RMS 控制台从 AD RMS 服务器导出受信任发布域 (TPD)</span><span class="sxs-lookup"><span data-stu-id="cc7d2-124">Step 1: Use the AD RMS console to export a trusted publishing domain (TPD) from an AD RMS server</span></span>

<span data-ttu-id="cc7d2-p106">第一步是从内部部署 AD RMS 服务器将受信任发布域 (TPD) 导出到 XML 文件。TPD 包含以下使用 RMS 功能所需的设置：</span><span class="sxs-lookup"><span data-stu-id="cc7d2-p106">The first step is to export a trusted publishing domain (TPD) from the on-premises AD RMS server to an XML file. The TPD contains the following settings needed to use RMS features:</span></span> 
  
- <span data-ttu-id="cc7d2-127">用于对证书和许可证进行签名和加密的服务器许可方证书 (SLC)</span><span class="sxs-lookup"><span data-stu-id="cc7d2-127">The server licensor certificate (SLC) used for signing and encrypting certificates and licenses</span></span>
    
- <span data-ttu-id="cc7d2-128">用于许可和发布的 URL</span><span class="sxs-lookup"><span data-stu-id="cc7d2-128">The URLs used for licensing and publishing</span></span>
    
- <span data-ttu-id="cc7d2-129">使用该 TPD 的特定 SLC 创建的 AD RMS 权限策略模板</span><span class="sxs-lookup"><span data-stu-id="cc7d2-129">The AD RMS rights policy templates that were created with the specific SLC for that TPD</span></span>
    
<span data-ttu-id="cc7d2-130">导入 TPD 时，它在 Exchange Online 中进行存储并受保护。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-130">When you import the TPD, it's stored and protected in Exchange Online.</span></span>
  
1. <span data-ttu-id="cc7d2-131">打开 Active Directory Rights Management Services 控制台，然后展开 AD RMS 群集。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-131">Open the Active Directory Rights Management Services console, and then expand the AD RMS cluster.</span></span>
    
2. <span data-ttu-id="cc7d2-132">在控制台树中，展开“信任策略”\*\*\*\*，然后单击“受信任的发布域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-132">In the console tree, expand **Trust Policies**, and then click **Trusted Publishing Domains**.</span></span>
    
3. <span data-ttu-id="cc7d2-133">在结果窗格中，选择要导出的域的证书。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-133">In the results pane, select the certificate for the domain you want to export.</span></span>
    
4. <span data-ttu-id="cc7d2-134">在“操作”\*\*\*\* 窗格中，单击“导出受信任的发布域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-134">In the **Actions** pane, click **Export Trusted Publishing Domain**.</span></span>
    
5. <span data-ttu-id="cc7d2-135">在“发布域文件”\*\*\*\* 框中，单击“另存为”\*\*\*\* 将文件保存到本地计算机上的特定位置。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-135">In the **Publishing domain file** box, click **Save As** to save the file to a specific location on the local computer.</span></span> <span data-ttu-id="cc7d2-136">键入文件名, 确保指定`.xml`文件扩展名, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-136">Type a file name, making sure to specify the  `.xml` file name extension, and then click **Save**.</span></span>
    
6. <span data-ttu-id="cc7d2-p108">在“密码”\*\*\*\* 和“确认密码”\*\*\*\* 框中，键入将用于对受信任的发布域文件加密的强密码。在将 TPD 导入到基于云的电子邮件组织时，必须指定此密码。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-p108">In the **Password** and **Confirm Password** boxes, type a strong password that will be used to encrypt the trusted publishing domain file. You will have to specify this password when you import the TPD to your cloud-based email organization.</span></span> 
    
### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a><span data-ttu-id="cc7d2-139">步骤 2：使用 Exchange 命令行管理程序 将 TPD 导入到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cc7d2-139">Step 2: Use the Exchange Management Shell to import the TPD to Exchange Online</span></span>

<span data-ttu-id="cc7d2-140">将 TPD 导出到 XML 文件之后，必须将其导入到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-140">After the TPD is exported to an XML file, you have to import it to Exchange Online.</span></span> <span data-ttu-id="cc7d2-141">导入 TPD 之后，还将导入组织的 AD RMS 模板。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-141">When a TPD is imported, your organization's AD RMS templates are also imported.</span></span> <span data-ttu-id="cc7d2-142">导入第一个 TPD 时，该 TPD 会成为基于云的组织的默认 TPD。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-142">When the first TPD is imported, it becomes the default TPD for your cloud-based organization.</span></span> <span data-ttu-id="cc7d2-143">如果导入另一个 TPD，则可以使用 **Default** 开关使其成为可供用户使用的默认 TPD。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-143">If you import another TPD, you can use the **Default** switch to make it the default TPD that is available to users.</span></span> 
  
<span data-ttu-id="cc7d2-144">若要导入 TPD，请在 Windows PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cc7d2-144">To import the TPD, run the following command in Windows PowerShell:</span></span>
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

<span data-ttu-id="cc7d2-p110">您可在 Active Directory Rights Management Services 控制台中获取  _ExtranetLicensingUrl_ 和  _IntranetLicensingUrl_ 参数的值。在控制台树中选择 AD RMS 群集。许可 URL 显示在结果窗格中。当必须对内容进行解密时以及 Exchange Online 需要确定要使用的 TPD 时，电子邮件客户端会使用这些 URL。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-p110">You can obtain the values for the  _ExtranetLicensingUrl_ and  _IntranetLicensingUrl_ parameters in the Active Directory Rights Management Services console. Select the AD RMS cluster in the console tree. The licensing URLs are displayed in the results pane. These URLs are used by email clients when content has to be decrypted and when Exchange Online needs to determine which TPD to use.</span></span> 
  
<span data-ttu-id="cc7d2-p111">当运行此命令时，系统会提示您输入密码。输入您在从 AD RMS 服务器导出 TPD 时指定的密码。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-p111">When you run this command, you'll be prompted for a password. Enter the password that you specified when you exported the TPD from your AD RMS server.</span></span>
  
<span data-ttu-id="cc7d2-p112">例如，以下命令使用您从 AD RMS 服务器导出并保存到管理员帐户桌面的 XML 文件来导入名为 Exported TPD 的 TPD。Name 参数用于为 TPD 指定名称。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-p112">For example, the following command imports the TPD named Exported TPD using the XML file that you exported from your AD RMS server and saved to the desktop of the Administrator account. The Name parameter is used to specify a name to the TPD.</span></span>
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

<span data-ttu-id="cc7d2-153">有关语法和参数的详细信息，请参阅 [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-153">For detailed syntax and parameter information, see [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="cc7d2-154">如何判断这一步生效？</span><span class="sxs-lookup"><span data-stu-id="cc7d2-154">How do you know this step worked?</span></span>

<span data-ttu-id="cc7d2-155">若要验证您是否已成功导入 TPD, 请运行**import-rmstrustedpublishingdomain** cmdlet 以检索 Exchange Online 组织中的 tpd。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-155">To verify that you have successfully imported the TPD, run the **Get-RMSTrustedPublishingDomain** cmdlet to retrieve TPDs in your Exchange Online organization.</span></span> <span data-ttu-id="cc7d2-156">有关详细信息，请参阅 [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx) 中的示例。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-156">For details, see the examples in [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx).</span></span>
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a><span data-ttu-id="cc7d2-157">步骤 3：使用 Exchange 命令行管理程序 来分发 AD RMS 权限策略模板</span><span class="sxs-lookup"><span data-stu-id="cc7d2-157">Step 3: Use the Exchange Management Shell to distribute an AD RMS rights policy template</span></span>

<span data-ttu-id="cc7d2-158">导入 TPD 之后，必须确保已分发 AD RMS 权限策略模板。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-158">After you import the TPD, you must make sure an AD RMS rights policy template is distributed.</span></span> <span data-ttu-id="cc7d2-159">分布式模板对 web 上的 Outlook (以前称为 "outlook web App") 用户可见, 然后可以将模板应用于电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-159">A distributed template is visible to Outlook on the web (formerly known as Outlook Web App) users, who can then apply the templates to an email message.</span></span>
  
<span data-ttu-id="cc7d2-160">若要返回默认 TPD 中包含的所有模板的列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cc7d2-160">To return a list of all templates contained in the default TPD, run the following command:</span></span>
  
```
Get-RMSTemplate -Type All | fl
```

<span data-ttu-id="cc7d2-161">如果  _Type_ 参数的值为  `Archived`，则模板对用户不可见。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-161">If the value of the  _Type_ parameter is  `Archived`, the template isn't visible to users.</span></span> <span data-ttu-id="cc7d2-162">只有默认 TPD 中的分布式模板可用于 web 上的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-162">Only distributed templates in the default TPD are available in Outlook on the web.</span></span>
  
<span data-ttu-id="cc7d2-163">若要分发模板，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cc7d2-163">To distribute a template, run the following command:</span></span>
  
```
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

<span data-ttu-id="cc7d2-164">例如，以下命令导入 Company Confidential 模板。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-164">For example, the following command imports the Company Confidential template.</span></span>
  
```
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

<span data-ttu-id="cc7d2-165">有关语法和参数的详细信息，请参阅 [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) 和 [Set-RMSTemplate](http://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-165">For detailed syntax and parameter information, see [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) and [Set-RMSTemplate](http://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx).</span></span>
  
 <span data-ttu-id="cc7d2-166">**“不要转发”模板**</span><span class="sxs-lookup"><span data-stu-id="cc7d2-166">**The Do Not Forward template**</span></span>
  
<span data-ttu-id="cc7d2-167">将默认 TPD 从内部部署组织导入到 Exchange Online 时，会导入一个名为“不要转发”\*\*\*\* 的 AD RMS 权限策略模板。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-167">When you import the default TPD from your on-premises organization into Exchange Online, one AD RMS rights policy template named **Do Not Forward** is imported.</span></span> <span data-ttu-id="cc7d2-168">默认情况下，导入默认 TPD 时将分发此模板。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-168">By default, this template is distributed when you import the default TPD.</span></span> <span data-ttu-id="cc7d2-169">不能使用**get-rmstemplate** cmdlet 修改 "**不要转发**" 模板。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-169">You can't use the **Set-RMSTemplate** cmdlet to modify the **Do Not Forward** template.</span></span> 
  
<span data-ttu-id="cc7d2-p117">将“不要转发”\*\*\*\* 模板应用于邮件时，只有邮件的收件人可读取该邮件。另外，收件人不能执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cc7d2-p117">When the **Do Not Forward** template is applied to a message, only the recipients addressed in the message can read the message. Additionally, recipients can't do the following:</span></span> 
  
- <span data-ttu-id="cc7d2-172">将邮件转发给其他人。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-172">Forward the message to another person.</span></span>
    
- <span data-ttu-id="cc7d2-173">复制邮件的内容。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-173">Copy content from the message.</span></span>
    
- <span data-ttu-id="cc7d2-174">打印邮件。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-174">Print the message.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="cc7d2-175">“不要转发”\*\*\*\* 模板无法阻止通过第三方屏幕捕获程序、照相机复制邮件中的信息或阻止用户手动转录这些信息。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-175">The **Do Not Forward** template can't prevent information in a message from being copied with third-party screen capture programs, cameras, or users manually transcribing the information</span></span> 
  
<span data-ttu-id="cc7d2-p118">您可在内部部署组织中的 AD RMS 服务器上创建其他 AD RMS 权限策略模板，以满足 IRM 保护要求。如果创建其他 AD RMS 权限策略模板，则必须再次从内部部署 AD RMS 服务器导出 TPD，并刷新基于云的电子邮件组织中的 TPD。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-p118">You can create additional AD RMS rights policy templates on the AD RMS server in your on-premises organization to meet your IRM protection requirements. If you create additional AD RMS rights policy templates, you have to export the TPD from the on-premises AD RMS server again and refresh the TPD in the cloud-based email organization.</span></span> 
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="cc7d2-178">如何判断这一步生效？</span><span class="sxs-lookup"><span data-stu-id="cc7d2-178">How do you know this step worked?</span></span>

<span data-ttu-id="cc7d2-179">若要验证您是否已成功分发和 AD RMS 权限策略模板, 请运行**get-rmstemplate** cmdlet 以检查模板的属性。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-179">To verify that you have successfully distributed and AD RMS rights policy template, run the **Get-RMSTemplate** cmdlet to check the template's properties.</span></span> <span data-ttu-id="cc7d2-180">有关详细信息，请参阅 [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) 中的示例。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-180">For details, see the examples in [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx).</span></span>
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a><span data-ttu-id="cc7d2-181">步骤 4：使用 Exchange 命令行管理程序 启用 IRM</span><span class="sxs-lookup"><span data-stu-id="cc7d2-181">Step 4: Use the Exchange Management Shell to enable IRM</span></span>

<span data-ttu-id="cc7d2-182">导入 TPD 并分发 AD RMS 权限策略模板之后，请运行以下命令来为基于云的电子邮件组织启用 IRM。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-182">After you import the TPD and distribute an AD RMS rights policy template, run the following command to enable IRM for your cloud-based email organization.</span></span>
  
```
Set-IRMConfiguration -InternalLicensingEnabled $true
```

<span data-ttu-id="cc7d2-183">有关语法和参数的详细信息，请参阅 [Set-IRMConfiguration](http://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-183">For detailed syntax and parameter information, see [Set-IRMConfiguration](http://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="cc7d2-184">如何判断这一步生效？</span><span class="sxs-lookup"><span data-stu-id="cc7d2-184">How do you know this step worked?</span></span>

<span data-ttu-id="cc7d2-185">若要验证是否已成功启用 IRM，请运行 [Get-IRMConfiguration](http://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) cmdlet 来检查 Exchange Online 组织中的 IRM 配置。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-185">To verify that you have successfully enabled IRM, run the [Get-IRMConfiguration](http://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) cmdlet to check IRM configuration in the Exchange Online organization.</span></span> 
  
## <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="cc7d2-186">如何判断此任务生效？</span><span class="sxs-lookup"><span data-stu-id="cc7d2-186">How do you know this task worked?</span></span>
<span data-ttu-id="cc7d2-187"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="cc7d2-187"></span></span>

<span data-ttu-id="cc7d2-188">若要验证是否已成功导入 TPD 并启用 IRM，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cc7d2-188">To verify that you have successfully imported the TPD and enabled IRM, do the following:</span></span>
  
- <span data-ttu-id="cc7d2-189">使用**get-irmconfiguration** cmdlet 测试 IRM 功能。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-189">Use the **Test-IRMConfiguration** cmdlet to test IRM functionality.</span></span> <span data-ttu-id="cc7d2-190">有关详细信息，请参阅 [Test-IRMConfiguration](http://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx) 中的"示例 1"。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-190">For details, see "Example 1" in [Test-IRMConfiguration](http://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx).</span></span>
    
- <span data-ttu-id="cc7d2-191">在 Outlook 网页网站中撰写新邮件并通过从扩展菜单 ( !["更多选项" 图标](media/ITPro-EAC-MoreOptionsIcon.gif)) 中选择 "**设置权限**" 选项来对其进行 IRM 保护。</span><span class="sxs-lookup"><span data-stu-id="cc7d2-191">Compose a new message in Outlook on the web and IRM-protect it by selecting **Set permissions** option from the extended menu ( ![More Options Icon](media/ITPro-EAC-MoreOptionsIcon.gif)).</span></span>
    


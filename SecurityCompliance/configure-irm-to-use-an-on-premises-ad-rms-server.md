---
title: 将 IRM 配置为使用本地 AD RMS 服务器
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
description: 本主题显示了如何将 IRM 配置为使用 AD RMS 服务器。
ms.openlocfilehash: 198d7b86b39318361a174395bc460b4a4bd35847
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027369"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a><span data-ttu-id="0c1e0-103">将 IRM 配置为使用本地 AD RMS 服务器</span><span class="sxs-lookup"><span data-stu-id="0c1e0-103">Configure IRM to use an on-premises AD RMS server</span></span>
  
<span data-ttu-id="0c1e0-p101">用于本地部署，Exchange Online 中的信息权限管理 (IRM) 使用 Active Directory Rights Management Services (AD RMS)，在 Windows Server 2008 及更高版本信息保护技术。通过将 AD RMS 权限策略模板应用于电子邮件到电子邮件应用 IRM 保护。权限附加到邮件本身，以便保护发生联机和脱机和内部和外部组织的防火墙。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p101">For use with on-premises deployments, Information Rights Management (IRM) in Exchange Online uses Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later. IRM protection is applied to email by applying an AD RMS rights policy template to an email message. Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>
  
<span data-ttu-id="0c1e0-p102">本主题演示如何 IRM 配置为使用 AD RMS 服务器。有关使用的 Azure Active Directory 与 Azure 权限管理的 Office 365 邮件加密的新功能的信息，请参阅[Office 365 邮件加密 FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p102">This topic shows you how to configure IRM to use an AD RMS server. For information about using the new capabilities for Office 365 Message Encryption with Azure Active Directory and Azure Rights Management, see the [Office 365 Message Encryption FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e).</span></span>
  
<span data-ttu-id="0c1e0-109">有关 Exchange Online 中 IRM 的详细信息，请参阅[Exchange Online 中的信息权限管理](information-rights-management-in-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-109">To learn more about IRM in Exchange Online, see [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0c1e0-110">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="0c1e0-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="0c1e0-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="0c1e0-111"></span></span>

- <span data-ttu-id="0c1e0-112">估计完成该任务的时间：30 分钟</span><span class="sxs-lookup"><span data-stu-id="0c1e0-112">Estimated time to complete this task: 30 minutes</span></span>
    
- <span data-ttu-id="0c1e0-p103">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的"信息权限管理"条目。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Information Rights Management" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="0c1e0-p104">AD RMS 服务器必须运行 Windows Server 2008 或更高版本。有关如何部署 AD RMS 的详细信息，请参阅[安装 AD RMS 群集](https://go.microsoft.com/fwlink/?LinkId=210873)。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p104">The AD RMS server must be running Windows Server 2008 or later. For details about how to deploy AD RMS, see [Installing an AD RMS Cluster](https://go.microsoft.com/fwlink/?LinkId=210873).</span></span>
    
- <span data-ttu-id="0c1e0-117">有关如何安装和配置 Windows PowerShell 以及连接到服务的详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-117">For details about how to install and configure Windows PowerShell and connect to the service, see [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span></span>
    
- <span data-ttu-id="0c1e0-118">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="0c1e0-p105">遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="how-do-you-do-this"></a><span data-ttu-id="0c1e0-122">您该如何做？</span><span class="sxs-lookup"><span data-stu-id="0c1e0-122">How do you do this?</span></span>
<span data-ttu-id="0c1e0-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="0c1e0-123"></span></span>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a><span data-ttu-id="0c1e0-124">步骤 1：使用 AD RMS 控制台从 AD RMS 服务器导出受信任发布域 (TPD)</span><span class="sxs-lookup"><span data-stu-id="0c1e0-124">Step 1: Use the AD RMS console to export a trusted publishing domain (TPD) from an AD RMS server</span></span>

<span data-ttu-id="0c1e0-p106">第一步是从内部部署 AD RMS 服务器将受信任发布域 (TPD) 导出到 XML 文件。TPD 包含以下使用 RMS 功能所需的设置：</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p106">The first step is to export a trusted publishing domain (TPD) from the on-premises AD RMS server to an XML file. The TPD contains the following settings needed to use RMS features:</span></span> 
  
- <span data-ttu-id="0c1e0-127">用于对证书和许可证进行签名和加密的服务器许可方证书 (SLC)</span><span class="sxs-lookup"><span data-stu-id="0c1e0-127">The server licensor certificate (SLC) used for signing and encrypting certificates and licenses</span></span>
    
- <span data-ttu-id="0c1e0-128">用于许可和发布的 URL</span><span class="sxs-lookup"><span data-stu-id="0c1e0-128">The URLs used for licensing and publishing</span></span>
    
- <span data-ttu-id="0c1e0-129">使用该 TPD 的特定 SLC 创建的 AD RMS 权限策略模板</span><span class="sxs-lookup"><span data-stu-id="0c1e0-129">The AD RMS rights policy templates that were created with the specific SLC for that TPD</span></span>
    
<span data-ttu-id="0c1e0-130">导入 TPD 时，它在 Exchange Online 中进行存储并受保护。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-130">When you import the TPD, it's stored and protected in Exchange Online.</span></span>
  
1. <span data-ttu-id="0c1e0-131">打开 Active Directory Rights Management Services 控制台，然后展开 AD RMS 群集。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-131">Open the Active Directory Rights Management Services console, and then expand the AD RMS cluster.</span></span>
    
2. <span data-ttu-id="0c1e0-132">在控制台树中，展开**信任策略**，然后单击**受信任发布域**。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-132">In the console tree, expand **Trust Policies**, and then click **Trusted Publishing Domains**.</span></span>
    
3. <span data-ttu-id="0c1e0-133">在结果窗格中，选择要导出的域的证书。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-133">In the results pane, select the certificate for the domain you want to export.</span></span>
    
4. <span data-ttu-id="0c1e0-134">在**操作**窗格中，单击**导出受信任的发布域**。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-134">In the **Actions** pane, click **Export Trusted Publishing Domain**.</span></span>
    
5. <span data-ttu-id="0c1e0-p107">在**发布域文件**框中，单击**另存为**文件保存到本地计算机上的特定位置。键入文件名，并确保指定`.xml`文件扩展名，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p107">In the **Publishing domain file** box, click **Save As** to save the file to a specific location on the local computer. Type a file name, making sure to specify the  `.xml` file name extension, and then click **Save**.</span></span>
    
6. <span data-ttu-id="0c1e0-p108">在**密码**和**确认密码**框中，键入将用于加密的受信任的发布域文件的强密码。您将需要向基于云的电子邮件组织导入 TPD 时指定此密码。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p108">In the **Password** and **Confirm Password** boxes, type a strong password that will be used to encrypt the trusted publishing domain file. You will have to specify this password when you import the TPD to your cloud-based email organization.</span></span> 
    
### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a><span data-ttu-id="0c1e0-139">步骤 2：使用 Exchange 命令行管理程序 将 TPD 导入到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0c1e0-139">Step 2: Use the Exchange Management Shell to import the TPD to Exchange Online</span></span>

<span data-ttu-id="0c1e0-p109">TPD 导出到 XML 文件后，您必须将其导入到 Exchange Online。导入 TPD 时，还会导入您的组织的 AD RMS 模板。导入第一个 TPD 时，它将成为默认 TPD 为您的基于云的组织。如果另一个 TPD 导入，您可以使用**默认**开关以使其对用户可用的 TPD 的默认。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p109">After the TPD is exported to an XML file, you have to import it to Exchange Online. When a TPD is imported, your organization's AD RMS templates are also imported. When the first TPD is imported, it becomes the default TPD for your cloud-based organization. If you import another TPD, you can use the **Default** switch to make it the default TPD that is available to users.</span></span> 
  
<span data-ttu-id="0c1e0-144">若要导入 TPD，请在 Windows PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0c1e0-144">To import the TPD, run the following command in Windows PowerShell:</span></span>
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

<span data-ttu-id="0c1e0-p110">您可在 Active Directory Rights Management Services 控制台中获取  _ExtranetLicensingUrl_ 和  _IntranetLicensingUrl_ 参数的值。在控制台树中选择 AD RMS 群集。许可 URL 显示在结果窗格中。当必须对内容进行解密时以及 Exchange Online 需要确定要使用的 TPD 时，电子邮件客户端会使用这些 URL。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p110">You can obtain the values for the  _ExtranetLicensingUrl_ and  _IntranetLicensingUrl_ parameters in the Active Directory Rights Management Services console. Select the AD RMS cluster in the console tree. The licensing URLs are displayed in the results pane. These URLs are used by email clients when content has to be decrypted and when Exchange Online needs to determine which TPD to use.</span></span> 
  
<span data-ttu-id="0c1e0-p111">当运行此命令时，系统会提示您输入密码。输入您在从 AD RMS 服务器导出 TPD 时指定的密码。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p111">When you run this command, you'll be prompted for a password. Enter the password that you specified when you exported the TPD from your AD RMS server.</span></span>
  
<span data-ttu-id="0c1e0-p112">例如，以下命令使用您从 AD RMS 服务器导出并保存到管理员帐户桌面的 XML 文件来导入名为 Exported TPD 的 TPD。Name 参数用于为 TPD 指定名称。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p112">For example, the following command imports the TPD named Exported TPD using the XML file that you exported from your AD RMS server and saved to the desktop of the Administrator account. The Name parameter is used to specify a name to the TPD.</span></span>
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

<span data-ttu-id="0c1e0-153">有关语法和参数的详细信息，请参阅 [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-153">For detailed syntax and parameter information, see [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="0c1e0-154">您如何知道此步骤有效？</span><span class="sxs-lookup"><span data-stu-id="0c1e0-154">How do you know this step worked?</span></span>

<span data-ttu-id="0c1e0-p113">若要验证已成功导入 TPD，运行 Exchange Online 组织中检索 TPDs **Get RMSTrustedPublishingDomain** cmdlet。有关详细信息，请参阅[Get RMSTrustedPublishingDomain](http://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx)中的示例。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p113">To verify that you have successfully imported the TPD, run the **Get-RMSTrustedPublishingDomain** cmdlet to retrieve TPDs in your Exchange Online organization. For details, see the examples in [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx).</span></span>
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a><span data-ttu-id="0c1e0-157">步骤 3：使用 Exchange 命令行管理程序 来分发 AD RMS 权限策略模板</span><span class="sxs-lookup"><span data-stu-id="0c1e0-157">Step 3: Use the Exchange Management Shell to distribute an AD RMS rights policy template</span></span>

<span data-ttu-id="0c1e0-p114">导入 TPD 之后，必须确保已分发 AD RMS 权限策略模板。分发的模板对 Outlook Web App 用户可见，这些用户随后可将模板应用于电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p114">After you import the TPD, you must make sure an AD RMS rights policy template is distributed. A distributed template is visible to Outlook Web App users, who can then apply the templates to an email message.</span></span>
  
<span data-ttu-id="0c1e0-160">若要返回默认 TPD 中包含的所有模板的列表，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0c1e0-160">To return a list of all templates contained in the default TPD, run the following command:</span></span>
  
```
Get-RMSTemplate -Type All | fl
```

<span data-ttu-id="0c1e0-p115">如果  _Type_ 参数的值为  `Archived`，则模板对用户不可见。只有默认 TPD 中的已分发模板才在 Outlook Web App 中可见。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p115">If the value of the  _Type_ parameter is  `Archived`, the template isn't visible to users. Only distributed templates in the default TPD are available in Outlook Web App.</span></span>
  
<span data-ttu-id="0c1e0-163">若要分发模板，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0c1e0-163">To distribute a template, run the following command:</span></span>
  
```
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

<span data-ttu-id="0c1e0-164">例如，以下命令导入 Company Confidential 模板。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-164">For example, the following command imports the Company Confidential template.</span></span>
  
```
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

<span data-ttu-id="0c1e0-165">有关语法和参数的详细信息，请参阅 [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) 和 [Set-RMSTemplate](http://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-165">For detailed syntax and parameter information, see [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) and [Set-RMSTemplate](http://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx).</span></span>
  
 <span data-ttu-id="0c1e0-166">**"不要转发"模板**</span><span class="sxs-lookup"><span data-stu-id="0c1e0-166">**The Do Not Forward template**</span></span>
  
<span data-ttu-id="0c1e0-p116">从内部部署组织到 Exchange Online 导入默认 TPD 时，导入名为**不要转发**的一个 AD RMS 权限策略模板。默认情况下导入默认 TPD 时分布此模板。不能使用**Set-rmstemplate** cmdlet 修改**不要转发**模板。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p116">When you import the default TPD from your on-premises organization into Exchange Online, one AD RMS rights policy template named **Do Not Forward** is imported. By default, this template is distributed when you import the default TPD. You can't use the **Set-RMSTemplate** cmdlet to modify the **Do Not Forward** template.</span></span> 
  
<span data-ttu-id="0c1e0-p117">**不要转发**模板应用于一条消息时, 仅在邮件中解决收件人可以阅读邮件。此外，收件人不能执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p117">When the **Do Not Forward** template is applied to a message, only the recipients addressed in the message can read the message. Additionally, recipients can't do the following:</span></span> 
  
- <span data-ttu-id="0c1e0-172">将邮件转发给其他人。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-172">Forward the message to another person.</span></span>
    
- <span data-ttu-id="0c1e0-173">复制邮件的内容。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-173">Copy content from the message.</span></span>
    
- <span data-ttu-id="0c1e0-174">打印邮件。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-174">Print the message.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="0c1e0-175">**不要转发**模板无法阻止邮件中的信息与第三方屏幕捕获程序、 照相机或手动抄录信息的用户复制</span><span class="sxs-lookup"><span data-stu-id="0c1e0-175">The **Do Not Forward** template can't prevent information in a message from being copied with third-party screen capture programs, cameras, or users manually transcribing the information</span></span> 
  
<span data-ttu-id="0c1e0-p118">您可在内部部署组织中的 AD RMS 服务器上创建其他 AD RMS 权限策略模板，以满足 IRM 保护要求。如果创建其他 AD RMS 权限策略模板，则必须再次从内部部署 AD RMS 服务器导出 TPD，并刷新基于云的电子邮件组织中的 TPD。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p118">You can create additional AD RMS rights policy templates on the AD RMS server in your on-premises organization to meet your IRM protection requirements. If you create additional AD RMS rights policy templates, you have to export the TPD from the on-premises AD RMS server again and refresh the TPD in the cloud-based email organization.</span></span> 
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="0c1e0-178">您如何知道此步骤有效？</span><span class="sxs-lookup"><span data-stu-id="0c1e0-178">How do you know this step worked?</span></span>

<span data-ttu-id="0c1e0-p119">若要验证是否已成功分发和 AD RMS 权限策略模板，运行**Get-rmstemplate** cmdlet 来检查该模板的属性。有关详细信息，请参阅[Get-rmstemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx)中的示例。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p119">To verify that you have successfully distributed and AD RMS rights policy template, run the **Get-RMSTemplate** cmdlet to check the template's properties. For details, see the examples in [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx).</span></span>
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a><span data-ttu-id="0c1e0-181">步骤 4：使用 Exchange 命令行管理程序 启用 IRM</span><span class="sxs-lookup"><span data-stu-id="0c1e0-181">Step 4: Use the Exchange Management Shell to enable IRM</span></span>

<span data-ttu-id="0c1e0-182">导入 TPD 并分发 AD RMS 权限策略模板之后，请运行以下命令来为基于云的电子邮件组织启用 IRM。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-182">After you import the TPD and distribute an AD RMS rights policy template, run the following command to enable IRM for your cloud-based email organization.</span></span>
  
```
Set-IRMConfiguration -InternalLicensingEnabled $true
```

<span data-ttu-id="0c1e0-183">有关语法和参数的详细信息，请参阅 [Set-IRMConfiguration](http://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-183">For detailed syntax and parameter information, see [Set-IRMConfiguration](http://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="0c1e0-184">您如何知道此步骤有效？</span><span class="sxs-lookup"><span data-stu-id="0c1e0-184">How do you know this step worked?</span></span>

<span data-ttu-id="0c1e0-185">若要验证是否已成功启用 IRM，请运行 [Get-IRMConfiguration](http://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) cmdlet 来检查 Exchange Online 组织中的 IRM 配置。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-185">To verify that you have successfully enabled IRM, run the [Get-IRMConfiguration](http://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) cmdlet to check IRM configuration in the Exchange Online organization.</span></span> 
  
## <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="0c1e0-186">您如何知道此任务有效？</span><span class="sxs-lookup"><span data-stu-id="0c1e0-186">How do you know this task worked?</span></span>
<span data-ttu-id="0c1e0-187"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="0c1e0-187"></span></span>

<span data-ttu-id="0c1e0-188">若要验证是否已成功导入 TPD 并启用 IRM，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0c1e0-188">To verify that you have successfully imported the TPD and enabled IRM, do the following:</span></span>
  
- <span data-ttu-id="0c1e0-p120">使用**Test-irmconfiguration** cmdlet 可以测试 IRM 功能。有关详细信息，请参阅[Test-irmconfiguration](http://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx)中的"示例 1"。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-p120">Use the **Test-IRMConfiguration** cmdlet to test IRM functionality. For details, see "Example 1" in [Test-IRMConfiguration](http://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx).</span></span>
    
- <span data-ttu-id="0c1e0-191">撰写新邮件中 Outlook Web App 和 IRM 保护其通过选择**设置的权限**选项从扩展菜单 (![更多选项图标](media/ITPro-EAC-MoreOptionsIcon.png))。</span><span class="sxs-lookup"><span data-stu-id="0c1e0-191">Compose a new message in Outlook Web App and IRM-protect it by selecting **Set permissions** option from the extended menu ( ![More Options Icon](media/ITPro-EAC-MoreOptionsIcon.png)).</span></span>
    


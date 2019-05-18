---
title: 向列表或库应用信息权限管理 (IRM)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
description: 您可以使用信息权限管理 (IRM) 来帮助控制和保护从列表或库中下载的文件。
ms.openlocfilehash: 3c350a3648b77992dd8e86ee47498efc327b2af8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152334"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a><span data-ttu-id="810ce-103">向列表或库应用信息权限管理 (IRM)</span><span class="sxs-lookup"><span data-stu-id="810ce-103">Apply Information Rights Management (IRM) to a list or library</span></span>

<span data-ttu-id="810ce-104">您可以使用信息权限管理 (IRM) 来帮助控制和保护从列表或库中下载的文件。</span><span class="sxs-lookup"><span data-stu-id="810ce-104">You can use Information Rights Management (IRM) to help control and protect files that are downloaded from lists or libraries.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="810ce-105">开始之前</span><span class="sxs-lookup"><span data-stu-id="810ce-105">Before you begin</span></span>

- <span data-ttu-id="810ce-106">Azure Rights Management service (Azure RMS) (来自 Azure 信息保护) 和本地等效项 Active Directory 权限管理服务 (AD RMS), 支持网站的信息权限管理。</span><span class="sxs-lookup"><span data-stu-id="810ce-106">The Azure Rights Management service (Azure RMS) from Azure Information Protection, and the on-premises equivalent, Active Directory Rights Management Services (AD RMS), support Information Rights Management for sites.</span></span> <span data-ttu-id="810ce-107">不需要单独安装或其他安装。</span><span class="sxs-lookup"><span data-stu-id="810ce-107">No separate or additional installations are required.</span></span>
    
- <span data-ttu-id="810ce-108">在将 IRM 应用于列表或库之前, 必须先由网站管理员启用此功能。</span><span class="sxs-lookup"><span data-stu-id="810ce-108">Before you apply IRM to a list or library it must first be enabled by an administrator for your site.</span></span>
    
- <span data-ttu-id="810ce-109">若要将 IRM 应用于列表或库, 您必须具有该列表或库的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="810ce-109">To apply IRM to a list or library, you must have administrator permissions for that list or library.</span></span>
    
- <span data-ttu-id="810ce-110">如果使用的是 SharePoint Online, 则用户在下载大型受 IRM 保护的文件时可能会遇到超时。</span><span class="sxs-lookup"><span data-stu-id="810ce-110">If you are using SharePoint Online, your users might experience timeouts when downloading larger IRM-protected files.</span></span> <span data-ttu-id="810ce-111">如果发生这种情况, 请使用 Office 程序应用 IRM 保护, 并在不使用 IRM 的 SharePoint 库中存储较大的文件。</span><span class="sxs-lookup"><span data-stu-id="810ce-111">If this happens, then apply IRM protection by using your Office programs, and store larger files in a SharePoint library that does not use IRM.</span></span>
    
> [!NOTE]
> <span data-ttu-id="810ce-112">如果使用的是 SharePoint Server 2013, 则服务器管理员必须在所有前端 Web 服务器上为组织中的人员要使用 IRM 保护的每种文件类型安装保护程序。</span><span class="sxs-lookup"><span data-stu-id="810ce-112">If you're using SharePoint Server 2013, a server administrator must install protectors on all front-end Web servers for every file type that the people in your organization want to protect by using IRM.</span></span> 
  
## <a name="apply-irm-to-a-list-or-library"></a><span data-ttu-id="810ce-113">将 IRM 应用于列表或库</span><span class="sxs-lookup"><span data-stu-id="810ce-113">Apply IRM to a list or library</span></span>
<span data-ttu-id="810ce-114"><a name="__toc256598179"> </a></span><span class="sxs-lookup"><span data-stu-id="810ce-114"></span></span>

![信息权限管理设置](media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. <span data-ttu-id="810ce-116">转到要为其配置 IRM 的列表或库。</span><span class="sxs-lookup"><span data-stu-id="810ce-116">Go to the list or library for which you want to configure IRM.</span></span>
    
2. <span data-ttu-id="810ce-117">在功能区上, 单击 "**库**" 选项卡, 然后单击 "**库设置**"。</span><span class="sxs-lookup"><span data-stu-id="810ce-117">On the ribbon, click the **Library** tab, and then click **Library Settings**.</span></span> <span data-ttu-id="810ce-118">(如果使用的是列表, 请单击 "**列表**" 选项卡, 然后单击 "**列表设置**")。</span><span class="sxs-lookup"><span data-stu-id="810ce-118">(If you are working in a list, click the **List** tab, and then click **List Settings**).</span></span>
    
    ![功能区上的 SharePoint 库设置按钮](media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. <span data-ttu-id="810ce-120">在 "**权限和管理**" 下, 单击 "**信息权限管理**"。</span><span class="sxs-lookup"><span data-stu-id="810ce-120">Under **Permissions and Management**, click **Information Rights Management**.</span></span> <span data-ttu-id="810ce-121">如果未显示信息权限管理链接, 则可能尚未为您的网站启用 IRM。</span><span class="sxs-lookup"><span data-stu-id="810ce-121">If the Information Rights Management link does not appear, IRM might not be enabled for your site.</span></span> <span data-ttu-id="810ce-122">请与您的服务器管理员联系, 以查看是否可以为您的网站启用 IRM。</span><span class="sxs-lookup"><span data-stu-id="810ce-122">Contact your server administrator to see if it is possible to enable IRM for your site.</span></span> <span data-ttu-id="810ce-123">不会对图片库显示 "信息权限管理" 链接。</span><span class="sxs-lookup"><span data-stu-id="810ce-123">The Information Rights Management link does not appear for picture libraries.</span></span>
    
4. <span data-ttu-id="810ce-124">在 "**信息权限管理设置**" 页上, 选中 "在**下载时限制对此库中的文档的权限"** 复选框, 以将受限权限应用于从该列表或库下载的文档。</span><span class="sxs-lookup"><span data-stu-id="810ce-124">On the **Information Rights Management Settings** page, select the **Restrict permission to documents in this library on download** check box to apply restricted permission to documents that are downloaded from this list or library.</span></span> 
    
5. <span data-ttu-id="810ce-125">在 "**创建权限策略标题**" 框中, 为策略键入一个描述性名称, 稍后可以使用此策略将此策略与其他策略区分开来。</span><span class="sxs-lookup"><span data-stu-id="810ce-125">In the **Create a permission policy title** box, type a descriptive name for the policy that you can use later to differentiate this policy from other policies.</span></span> <span data-ttu-id="810ce-126">例如, 如果要将受限制的权限应用于将包含公司机密的公司文档的列表或库, 则可以键入**公司机密**。</span><span class="sxs-lookup"><span data-stu-id="810ce-126">For example, you can type **Company Confidential** if you are applying restricted permission to a list or library that will contain company documents that are confidential.</span></span> 
    
6. <span data-ttu-id="810ce-127">在 "**添加权限策略说明**" 框中, 键入将向使用此列表或库的用户显示的说明, 该说明说明他们应如何处理此列表或库中的文档。</span><span class="sxs-lookup"><span data-stu-id="810ce-127">In the **Add a permission policy description** box, type a description that will appear to people who use this list or library that explains how they should handle the documents in this list or library.</span></span> <span data-ttu-id="810ce-128">例如, 如果您想要将对这些文档中的信息的访问限制到内部员工, 则可以键入 **"仅与其他员工讨论此文档的内容"** 。</span><span class="sxs-lookup"><span data-stu-id="810ce-128">For example, you can type **Discuss the contents of this document only with other employees** if you want to restrict access to the information in these documents to internal employees.</span></span> 
    
7. <span data-ttu-id="810ce-129">若要对此列表或库中的文档应用其他限制, 请单击 "**显示选项**", 然后执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="810ce-129">To apply additional restrictions to the documents in this list or library, click **Show Options**, and do any of the following:</span></span>
    
|<span data-ttu-id="810ce-130">**为此, 请执行以下操作:**</span><span class="sxs-lookup"><span data-stu-id="810ce-130">**To do this:**</span></span>|<span data-ttu-id="810ce-131">**执行以下操作:**</span><span class="sxs-lookup"><span data-stu-id="810ce-131">**Do this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="810ce-132">允许用户打印此列表或库中的文档</span><span class="sxs-lookup"><span data-stu-id="810ce-132">Allow people to print documents from this list or library</span></span>  <br/> |<span data-ttu-id="810ce-133">选中 "**允许查看者打印**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="810ce-133">Select the **Allow viewers to print** check box.</span></span>  <br/> |
|<span data-ttu-id="810ce-134">允许至少具有 "查看项目" 权限的用户在文档中运行嵌入的代码或宏。</span><span class="sxs-lookup"><span data-stu-id="810ce-134">Allow people with at least the View Items permission to run embedded code or macros on a document.</span></span>  <br/> |<span data-ttu-id="810ce-135">选中 "**允许查看者运行脚本和屏幕阅读器以在下载的文档上运行"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="810ce-135">Select the **Allow viewers to run script and screen reader to function on downloaded documents** check box.</span></span>  <br/> <span data-ttu-id="810ce-136">如果选择此选项, 则用户可以运行代码来提取文档的内容。</span><span class="sxs-lookup"><span data-stu-id="810ce-136">If you select this option, users could run code to extract the contents of a document.</span></span>           |
|<span data-ttu-id="810ce-137">要求用户按特定间隔验证其凭据。</span><span class="sxs-lookup"><span data-stu-id="810ce-137">Require that people verify their credentials at specific intervals.</span></span>  <br/> <span data-ttu-id="810ce-138">如果想要将对内容的访问限制在指定的一段时间内, 请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="810ce-138">Select this option if you want to restrict access to content to a specified period of time.</span></span> <span data-ttu-id="810ce-139">如果选择此选项, 则用户在指定天数后访问内容的颁发许可证将会过期, 并且将需要用户返回到服务器以验证其凭据并下载新副本。</span><span class="sxs-lookup"><span data-stu-id="810ce-139">If you select this option, people's issuance licenses to access the content will expire after the specified number of days, and people will be required to return to the server to verify their credentials and download a new copy.</span></span>  <br/> |<span data-ttu-id="810ce-140">选中 "**用户必须使用此间隔验证其凭据 (天)** " 复选框, 然后指定您希望文档可查看的天数。</span><span class="sxs-lookup"><span data-stu-id="810ce-140">Select the **Users must verify their credentials using this interval (days)** check box, and then specify the number of days for which you want the document to be viewable.</span></span>  <br/> |
| <span data-ttu-id="810ce-141">阻止人员将不支持 IRM 的文档上载到此列表或库。</span><span class="sxs-lookup"><span data-stu-id="810ce-141">Prevent people from uploading documents that do not support IRM to this list or library.</span></span>  <br/>  <span data-ttu-id="810ce-142">如果选择此选项, 则用户将无法上传以下任何文件类型:</span><span class="sxs-lookup"><span data-stu-id="810ce-142">If you select this option, people will not be able to upload any of the following file types:</span></span>  <br/>  <span data-ttu-id="810ce-143">在所有前端 Web 服务器上都不安装相应 IRM 保护程序的文件类型。</span><span class="sxs-lookup"><span data-stu-id="810ce-143">File types that do not have corresponding IRM protectors installed on all of the front-end Web servers.</span></span>  <br/>  <span data-ttu-id="810ce-144">SharePoint Server 2010 无法解密的文件类型。</span><span class="sxs-lookup"><span data-stu-id="810ce-144">File types that SharePoint Server 2010 cannot decrypt.</span></span>  <br/>  <span data-ttu-id="810ce-145">在其他程序中受 IRM 保护的文件类型</span><span class="sxs-lookup"><span data-stu-id="810ce-145">File types that are IRM protected in another program</span></span>  <br/> |<span data-ttu-id="810ce-146">选中 "不**允许用户上载不支持 IRM 的文档**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="810ce-146">Select the **Do not allow users to upload documents that do not support IRM** check box.</span></span>  <br/> |
|<span data-ttu-id="810ce-147">在特定日期删除此列表或库的受限权限。</span><span class="sxs-lookup"><span data-stu-id="810ce-147">Remove restricted permissions from this list or library on a specific date.</span></span>  <br/> |<span data-ttu-id="810ce-148">选中 "**停止限制对库的访问"** 复选框, 然后选择所需的日期。</span><span class="sxs-lookup"><span data-stu-id="810ce-148">Select the **Stop restricting access to the library at** check box, and then select the date that you want.</span></span>  <br/> |
|<span data-ttu-id="810ce-149">控制为打开文档许可的程序缓存的凭据的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="810ce-149">Control the interval that credentials are cached for the program that is licensed to open the document.</span></span>  <br/> |<span data-ttu-id="810ce-150">在 "**设置组保护和凭据间隔**" 中, 输入 theinterval 以在数天内缓存凭据。</span><span class="sxs-lookup"><span data-stu-id="810ce-150">In the **Set group protection and credentials interval**, enter theinterval for caching credentials in number of days.</span></span>  <br/> |
|<span data-ttu-id="810ce-151">允许组保护, 以便用户可以与同一组的成员共享。</span><span class="sxs-lookup"><span data-stu-id="810ce-151">Allow group protection so that users can share with members of the same group.</span></span>  <br/> |<span data-ttu-id="810ce-152">选择 "**允许组保护**", 然后输入组的名称以进行共享。</span><span class="sxs-lookup"><span data-stu-id="810ce-152">Select **Allow group protection**, and enter the group's name for sharing.</span></span>  <br/> |
   
8. <span data-ttu-id="810ce-153">选择完所需的选项后, 单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="810ce-153">After you finish selecting the options you want, click **OK**.</span></span>
  
## <a name="what-is-information-rights-management"></a><span data-ttu-id="810ce-154">什么是信息权限管理？</span><span class="sxs-lookup"><span data-stu-id="810ce-154">What is Information Rights Management?</span></span>
<span data-ttu-id="810ce-155"><a name="__toc256598175"> </a></span><span class="sxs-lookup"><span data-stu-id="810ce-155"></span></span>

<span data-ttu-id="810ce-156">信息权限管理 (IRM) 使您可以限制用户可以对从列表或库中下载的文件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="810ce-156">Information Rights Management (IRM) enables you to limit the actions that users can take on files that have been downloaded from lists or libraries.</span></span> <span data-ttu-id="810ce-157">IRM 对下载的文件进行加密并限制允许解密这些文件的用户和程序组。</span><span class="sxs-lookup"><span data-stu-id="810ce-157">IRM encrypts the downloaded files and limits the set of users and programs that are allowed to decrypt these files.</span></span> <span data-ttu-id="810ce-158">IRM 还可限制允许读取文件的用户的权限，以便这些用户无法执行打印文件的副本或复制文件中的文本等操作。</span><span class="sxs-lookup"><span data-stu-id="810ce-158">IRM can also limit the rights of the users who are allowed to read files, so that they cannot take actions such as print copies of the files or copy text from them.</span></span>
  
<span data-ttu-id="810ce-159">您可以对列表或库使用 IRM 来限制敏感内容的分发。</span><span class="sxs-lookup"><span data-stu-id="810ce-159">You can use IRM on lists or libraries to limit the dissemination of sensitive content.</span></span> <span data-ttu-id="810ce-160">例如, 如果您要创建一个文档库, 以便与选定的市场营销代表共享有关即将发布的产品的信息, 则可以使用 IRM 来防止这些个人与公司中的其他员工共享此内容。</span><span class="sxs-lookup"><span data-stu-id="810ce-160">For example, if you are creating a document library to share information about upcoming products with selected marketing representatives, you can use IRM to prevent these individuals from sharing this content with other employees in the company.</span></span>
  
<span data-ttu-id="810ce-161">在网站上, 将 IRM 应用于整个列表或库, 而不是单个文件。</span><span class="sxs-lookup"><span data-stu-id="810ce-161">On a site, you apply IRM to an entire list or library, rather than to individual files.</span></span> <span data-ttu-id="810ce-162">这样可以更轻松地确保对整个文档或文件集进行一致的保护级别。</span><span class="sxs-lookup"><span data-stu-id="810ce-162">This makes it easier to ensure a consistent level of protection for an entire set of documents or files.</span></span> <span data-ttu-id="810ce-163">因此, IRM 可帮助您的组织强制实施管理机密或专有信息的使用和传播的公司策略。</span><span class="sxs-lookup"><span data-stu-id="810ce-163">IRM can thus help your organization to enforce corporate policies that govern the use and dissemination of confidential or proprietary information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="810ce-164">本页中有关信息权限管理的信息取代了任何 Microsoft SharePoint Server 2013 和 SharePoint Server 2016 许可条款协议中引用 "信息权限管理" 的术语。</span><span class="sxs-lookup"><span data-stu-id="810ce-164">The information on this page regarding Information Rights Management supersedes any terms that reference 'Information Rights Management' in any Microsoft SharePoint Server 2013 and SharePoint Server 2016 license term agreements.</span></span> 
  
### <a name="how-irm-can-help-protect-content"></a><span data-ttu-id="810ce-165">IRM 可以如何帮助保护内容</span><span class="sxs-lookup"><span data-stu-id="810ce-165">How IRM can help protect content</span></span>
<span data-ttu-id="810ce-166"><a name="__toc256598176"> </a></span><span class="sxs-lookup"><span data-stu-id="810ce-166"></span></span>

<span data-ttu-id="810ce-167">IRM 有助于通过以下方式保护受限制的内容:</span><span class="sxs-lookup"><span data-stu-id="810ce-167">IRM helps to protect restricted content in the following ways:</span></span>
  
- <span data-ttu-id="810ce-168">帮助阻止授权的查看者复制、修改、打印、传真或复制和粘贴内容以进行未经授权的使用</span><span class="sxs-lookup"><span data-stu-id="810ce-168">Helps to prevent an authorized viewer from copying, modifying, printing, faxing, or copying and pasting the content for unauthorized use</span></span>
    
- <span data-ttu-id="810ce-169">帮助防止授权查看者使用 Microsoft Windows 中的打印屏幕功能复制内容</span><span class="sxs-lookup"><span data-stu-id="810ce-169">Helps to prevent an authorized viewer from copying the content by using the Print Screen feature in Microsoft Windows</span></span>
    
- <span data-ttu-id="810ce-170">帮助防止未经授权的查看者查看从服务器下载后通过电子邮件发送的内容</span><span class="sxs-lookup"><span data-stu-id="810ce-170">Helps to prevent an unauthorized viewer from viewing the content if it is sent in e-mail after it is downloaded from the server</span></span>
    
- <span data-ttu-id="810ce-171">将对内容的访问限制在指定的一段时间内, 之后用户必须确认其凭据并再次下载内容</span><span class="sxs-lookup"><span data-stu-id="810ce-171">Restricts access to content to a specified period of time, after which users must confirm their credentials and download the content again</span></span>
    
- <span data-ttu-id="810ce-172">帮助强制实施在组织内控制内容的使用和分发的公司策略</span><span class="sxs-lookup"><span data-stu-id="810ce-172">Helps to enforce corporate policies that govern the use and dissemination of content within your organization</span></span>
    
### <a name="how-irm-cannot-help-protect-content"></a><span data-ttu-id="810ce-173">IRM 无法帮助保护内容的方式</span><span class="sxs-lookup"><span data-stu-id="810ce-173">How IRM cannot help protect content</span></span>
<span data-ttu-id="810ce-174"><a name="__toc256598177"> </a></span><span class="sxs-lookup"><span data-stu-id="810ce-174"></span></span>

<span data-ttu-id="810ce-175">IRM 无法保护以下受限制的内容:</span><span class="sxs-lookup"><span data-stu-id="810ce-175">IRM cannot protect restricted content from the following:</span></span>
  
- <span data-ttu-id="810ce-176">由恶意程序 (如特洛伊木马、击键记录器和特定类型的间谍软件) 擦除、盗窃、捕获或传输</span><span class="sxs-lookup"><span data-stu-id="810ce-176">Erasure, theft, capture, or transmission by malicious programs such as Trojan horses, keystroke loggers, and certain types of spyware</span></span>
    
- <span data-ttu-id="810ce-177">由于计算机病毒的操作而造成的丢失或损坏</span><span class="sxs-lookup"><span data-stu-id="810ce-177">Loss or corruption because of the actions of computer viruses</span></span>
    
- <span data-ttu-id="810ce-178">从屏幕上的显示内容中手动复制或重新键入内容</span><span class="sxs-lookup"><span data-stu-id="810ce-178">Manual copying or retyping of content from the display on a screen</span></span>
    
- <span data-ttu-id="810ce-179">屏幕上显示的内容的数字或胶片照片</span><span class="sxs-lookup"><span data-stu-id="810ce-179">Digital or film photography of content that is displayed on a screen</span></span>
    
- <span data-ttu-id="810ce-180">通过使用第三方屏幕捕获程序进行复制</span><span class="sxs-lookup"><span data-stu-id="810ce-180">Copying through the use of third-party screen-capture programs</span></span>
    
- <span data-ttu-id="810ce-181">通过使用第三方屏幕捕获程序或复制和粘贴操作来复制内容元数据 (列值)</span><span class="sxs-lookup"><span data-stu-id="810ce-181">Copying of content metadata (column values) through the use of third-party screen-capture programs or copy-and-paste action</span></span>
    
[<span data-ttu-id="810ce-182">对列表或库应用信息权限管理</span><span class="sxs-lookup"><span data-stu-id="810ce-182">Apply Information Rights Management to a list or library</span></span>](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a><span data-ttu-id="810ce-183">IRM 对列表和库的工作方式</span><span class="sxs-lookup"><span data-stu-id="810ce-183">How IRM works for lists and libraries</span></span>
<span data-ttu-id="810ce-184"><a name="__toc256598178"> </a></span><span class="sxs-lookup"><span data-stu-id="810ce-184"></span></span>

<span data-ttu-id="810ce-185">IRM 保护应用于列表或库级别的文件。</span><span class="sxs-lookup"><span data-stu-id="810ce-185">IRM protection is applied to files at the list or library level.</span></span> <span data-ttu-id="810ce-186">对库启用 IRM 时, 权限管理将应用于该库中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="810ce-186">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="810ce-187">为列表启用 IRM 时, 权限管理仅适用于附加到列表项 (而不是实际列表项) 的文件。</span><span class="sxs-lookup"><span data-stu-id="810ce-187">When IRM is enabled for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="810ce-188">当用户下载启用 IRM 的列表或库中的文件时, 将对这些文件进行加密, 以便仅获得授权的用户可以查看这些文件。</span><span class="sxs-lookup"><span data-stu-id="810ce-188">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="810ce-189">每个权限管理文件还包含一个发布许可证, 该许可证对查看文件的人员施加限制。</span><span class="sxs-lookup"><span data-stu-id="810ce-189">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="810ce-190">典型限制包括将文件设为只读、禁用文本复制、阻止用户保存本地副本以及阻止用户打印文件。</span><span class="sxs-lookup"><span data-stu-id="810ce-190">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="810ce-191">可以读取受 IRM 支持的文件类型的客户端程序使用权限管理文件中的发布许可证来强制实施这些限制。</span><span class="sxs-lookup"><span data-stu-id="810ce-191">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="810ce-192">这是权限管理文件即使是从服务器下载后仍保留其保护的方式。</span><span class="sxs-lookup"><span data-stu-id="810ce-192">This is how a rights-managed file retains its protection even after it is downloaded from the server.</span></span>
  
<span data-ttu-id="810ce-193">从列表或库中下载文件时应用于该文件的限制类型取决于单个用户对包含该文件的网站的权限。</span><span class="sxs-lookup"><span data-stu-id="810ce-193">The types of restrictions that are applied to a file when it is downloaded from a list or library are based on the individual user's permissions on the site that contains the file.</span></span> <span data-ttu-id="810ce-194">下表说明了网站上的权限如何对应于 IRM 权限。</span><span class="sxs-lookup"><span data-stu-id="810ce-194">The following table explains how the permissions on sites correspond to IRM permissions.</span></span>
  
|<span data-ttu-id="810ce-195">**权限**</span><span class="sxs-lookup"><span data-stu-id="810ce-195">**Permissions**</span></span>|<span data-ttu-id="810ce-196">**IRM 权限**</span><span class="sxs-lookup"><span data-stu-id="810ce-196">**IRM Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="810ce-197">管理权限、管理网站</span><span class="sxs-lookup"><span data-stu-id="810ce-197">Manage Permissions, Manage Web Site</span></span>  <br/> |<span data-ttu-id="810ce-198">**完全控制**(由客户端程序定义): 此权限通常允许用户读取、编辑、复制、保存和修改权限管理内容的权限。</span><span class="sxs-lookup"><span data-stu-id="810ce-198">**Full control** (as defined by the client program): This permission generally allows a user to read, edit, copy, save, and modify permissions of rights-managed content.</span></span>  <br/> |
|<span data-ttu-id="810ce-199">编辑项目、管理列表、添加和自定义页面</span><span class="sxs-lookup"><span data-stu-id="810ce-199">Edit Items, Manage Lists, Add and Customize Pages</span></span>  <br/> |<span data-ttu-id="810ce-200">**编辑**、**复制**和**保存**: 只有在列表或库的 "信息权限管理设置" 页上选中 "**允许用户打印文档**" 复选框时, 用户才能打印文件。</span><span class="sxs-lookup"><span data-stu-id="810ce-200">**Edit**, **Copy**, and **Save**: A user can print a file only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>  <br/> |
|<span data-ttu-id="810ce-201">查看项目</span><span class="sxs-lookup"><span data-stu-id="810ce-201">View Items</span></span>  <br/> |<span data-ttu-id="810ce-202">**阅读**: 用户可以读取文档, 但无法复制或修改其内容。</span><span class="sxs-lookup"><span data-stu-id="810ce-202">**Read**: A user can read the document, but cannot copy or modify its content.</span></span> <span data-ttu-id="810ce-203">只有在列表或库的 "信息权限管理设置" 页上选中了 "**允许用户打印文档**" 复选框时, 用户才能打印。</span><span class="sxs-lookup"><span data-stu-id="810ce-203">A user can print only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>  <br/> |
|<span data-ttu-id="810ce-204">Other</span><span class="sxs-lookup"><span data-stu-id="810ce-204">Other</span></span>  <br/> |<span data-ttu-id="810ce-205">没有直接对应于 IRM 权限的其他权限。</span><span class="sxs-lookup"><span data-stu-id="810ce-205">No other permissions correspond directly to IRM permissions.</span></span>  <br/> |
   
<span data-ttu-id="810ce-206">在 SharePoint Server 2013 中为列表或库启用 IRM 时, 只能保护在所有前端 Web 服务器上都安装了保护程序的列表或库中的文件类型。</span><span class="sxs-lookup"><span data-stu-id="810ce-206">When you enable IRM for a list or library in SharePoint Server 2013, you can only protect file types in that list or library for which a protector is installed on all front-end Web servers.</span></span> <span data-ttu-id="810ce-207">保护程序是一种程序, 用于控制特定文件格式的权限管理文件的加密和解密。</span><span class="sxs-lookup"><span data-stu-id="810ce-207">A protector is a program that controls the encryption and decryption of rights-managed files of a specific file format.</span></span> <span data-ttu-id="810ce-208">SharePoint 包含针对以下文件类型的保护程序:</span><span class="sxs-lookup"><span data-stu-id="810ce-208">SharePoint includes protectors for the following file types:</span></span>
  
- <span data-ttu-id="810ce-209">Microsoft Office InfoPath 表单</span><span class="sxs-lookup"><span data-stu-id="810ce-209">Microsoft Office InfoPath forms</span></span>
    
- <span data-ttu-id="810ce-210">以下 Microsoft Office 程序的97-2003 文件格式: Word、Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="810ce-210">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="810ce-211">适用于以下 Microsoft Office 程序的 Office Open XML 格式: Word、Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="810ce-211">The Office Open XML Formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="810ce-212">XML 纸张规范 (XPS) 格式</span><span class="sxs-lookup"><span data-stu-id="810ce-212">The XML Paper Specification (XPS) format</span></span>
    
<span data-ttu-id="810ce-213">如果您的组织计划使用 IRM 来保护除以上列出的任何其他文件类型, 则服务器管理员必须为这些附加文件格式安装保护程序。</span><span class="sxs-lookup"><span data-stu-id="810ce-213">If your organization plans to use IRM to protect any other file types in addition to those listed above, your server administrator must install protectors for these additional file formats.</span></span>
  


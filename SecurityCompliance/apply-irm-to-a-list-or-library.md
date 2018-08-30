---
title: 对列表或库应用信息权限管理 (IRM)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
description: 信息权限管理 (IRM) 可用于帮助控制和保护从列表或库中下载的文件。
ms.openlocfilehash: 5a48abf13841716d4dba34311d69ca2e6a5ea422
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525334"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a><span data-ttu-id="2b394-103">对列表或库应用信息权限管理 (IRM)</span><span class="sxs-lookup"><span data-stu-id="2b394-103">Apply Information Rights Management (IRM) to a list or library</span></span>

<span data-ttu-id="2b394-104">信息权限管理 (IRM) 可用于帮助控制和保护从列表或库中下载的文件。</span><span class="sxs-lookup"><span data-stu-id="2b394-104">You can use Information Rights Management (IRM) to help control and protect files that are downloaded from lists or libraries.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="2b394-105">准备工作</span><span class="sxs-lookup"><span data-stu-id="2b394-105">Before you begin</span></span>

- <span data-ttu-id="2b394-p101">Azure 权限管理服务 (Azure RMS) 从 Azure 信息保护和本地等效，Active Directory Rights Management Services (AD RMS) 支持的网站的信息权限管理。没有单独或更多安装是必需的。</span><span class="sxs-lookup"><span data-stu-id="2b394-p101">The Azure Rights Management service (Azure RMS) from Azure Information Protection, and the on-premises equivalent, Active Directory Rights Management Services (AD RMS), support Information Rights Management for sites. No separate or additional installations are required.</span></span>
    
- <span data-ttu-id="2b394-108">向列表或库应用 IRM 之前为您的网站管理员必须首先为启用。</span><span class="sxs-lookup"><span data-stu-id="2b394-108">Before you apply IRM to a list or library it must first be enabled by an administrator for your site.</span></span>
    
- <span data-ttu-id="2b394-109">要对列表或库应用 IRM，您必须对该列表或库的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="2b394-109">To apply IRM to a list or library, you must have administrator permissions for that list or library.</span></span>
    
- <span data-ttu-id="2b394-p102">如果您使用 SharePoint Online，用户可能会下载较大受 IRM 保护的文件时遇到超时。如果发生这种情况，然后通过使用 Office 程序，应用 IRM 保护并存储在不使用 IRM 的 SharePoint 库中的较大的文件。</span><span class="sxs-lookup"><span data-stu-id="2b394-p102">If you are using SharePoint Online, your users might experience timeouts when downloading larger IRM-protected files. If this happens, then apply IRM protection by using your Office programs, and store larger files in a SharePoint library that does not use IRM.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2b394-112">如果您使用 SharePoint Server 2013，服务器管理员必须在每个组织中的人员想要使用 IRM 保护的文件类型的所有前端 Web 服务器上安装保护程序。</span><span class="sxs-lookup"><span data-stu-id="2b394-112">If you're using SharePoint Server 2013, a server administrator must install protectors on all front-end Web servers for every file type that the people in your organization want to protect by using IRM.</span></span> 
  
## <a name="apply-irm-to-a-list-or-library"></a><span data-ttu-id="2b394-113">适用于列表或库的 IRM</span><span class="sxs-lookup"><span data-stu-id="2b394-113">Apply IRM to a list or library</span></span>
<span data-ttu-id="2b394-114"><a name="__toc256598179"> </a></span><span class="sxs-lookup"><span data-stu-id="2b394-114"></span></span>

![信息权限管理设置](media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. <span data-ttu-id="2b394-116">转到要为其配置 IRM 的列表或库。</span><span class="sxs-lookup"><span data-stu-id="2b394-116">Go to the list or library for which you want to configure IRM.</span></span>
    
2. <span data-ttu-id="2b394-p103">在功能区上单击**库**选项卡，然后单击**库设置**。（如果您正在列表中，单击**列表**选项卡，然后单击**列表设置**）。</span><span class="sxs-lookup"><span data-stu-id="2b394-p103">On the ribbon, click the **Library** tab, and then click **Library Settings**. (If you are working in a list, click the **List** tab, and then click **List Settings**).</span></span>
    
    ![在功能区上的 SharePoint 库设置按钮](media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. <span data-ttu-id="2b394-p104">单击**权限和管理**下的**信息权限管理**。如果未显示信息权限管理链接，可能尚未为您的网站中启用 IRM。与您的服务器管理员联系，以查看是否可能为您的网站启用 IRM。图片库未显示信息权限管理链接。</span><span class="sxs-lookup"><span data-stu-id="2b394-p104">Under **Permissions and Management**, click **Information Rights Management**. If the Information Rights Management link does not appear, IRM might not be enabled for your site. Contact your server administrator to see if it is possible to enable IRM for your site. The Information Rights Management link does not appear for picture libraries.</span></span>
    
4. <span data-ttu-id="2b394-124">在**信息权限管理设置**页中，选择**限制对在下载此库中文档的权限**复选框将受限的权限应用于此列表或库中下载的文档。</span><span class="sxs-lookup"><span data-stu-id="2b394-124">On the **Information Rights Management Settings** page, select the **Restrict permission to documents in this library on download** check box to apply restricted permission to documents that are downloaded from this list or library.</span></span> 
    
5. <span data-ttu-id="2b394-p105">在**创建权限策略标题**框中，键入以后可以使用它来从其他策略区分此策略的策略的描述性名称。例如，您可以键入**公司机密**如果要将受限的权限应用于列表或库将包含公司机密的文档。</span><span class="sxs-lookup"><span data-stu-id="2b394-p105">In the **Create a permission policy title** box, type a descriptive name for the policy that you can use later to differentiate this policy from other policies. For example, you can type **Company Confidential** if you are applying restricted permission to a list or library that will contain company documents that are confidential.</span></span> 
    
6. <span data-ttu-id="2b394-p106">在**添加权限策略说明**框中，键入将使用此列表或库的说明，他们应如何处理此列表或库中的文档的人员显示的说明。例如，您可以键入**讨论的本文档仅与其他员工内容**如果您想要限制到内部员工这些文档中的信息的访问。</span><span class="sxs-lookup"><span data-stu-id="2b394-p106">In the **Add a permission policy description** box, type a description that will appear to people who use this list or library that explains how they should handle the documents in this list or library. For example, you can type **Discuss the contents of this document only with other employees** if you want to restrict access to the information in these documents to internal employees.</span></span> 
    
7. <span data-ttu-id="2b394-129">要对此列表或库中的文档应用其他限制，单击**显示选项**，然后执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="2b394-129">To apply additional restrictions to the documents in this list or library, click **Show Options**, and do any of the following:</span></span>
    
|<span data-ttu-id="2b394-130">**若要此操作：**</span><span class="sxs-lookup"><span data-stu-id="2b394-130">**To do this:**</span></span>|<span data-ttu-id="2b394-131">**执行此操作：**</span><span class="sxs-lookup"><span data-stu-id="2b394-131">**Do this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2b394-132">允许用户从此列表或库打印文档</span><span class="sxs-lookup"><span data-stu-id="2b394-132">Allow people to print documents from this list or library</span></span>  <br/> |<span data-ttu-id="2b394-133">选择**允许查看器打印**复选框。</span><span class="sxs-lookup"><span data-stu-id="2b394-133">Select the **Allow viewers to print** check box.</span></span>  <br/> |
|<span data-ttu-id="2b394-134">允许人员与至少查看项目权限才能运行文档中嵌入的代码或宏。</span><span class="sxs-lookup"><span data-stu-id="2b394-134">Allow people with at least the View Items permission to run embedded code or macros on a document.</span></span>  <br/> |<span data-ttu-id="2b394-135">选择**允许查看器运行在下载文档的函数的脚本和屏幕阅读器**复选框。</span><span class="sxs-lookup"><span data-stu-id="2b394-135">Select the **Allow viewers to run script and screen reader to function on downloaded documents** check box.</span></span>  <br/> <span data-ttu-id="2b394-136">如果选择此选项，用户可以运行提取文档的内容的代码。</span><span class="sxs-lookup"><span data-stu-id="2b394-136">If you select this option, users could run code to extract the contents of a document.</span></span>           |
|<span data-ttu-id="2b394-137">需要用户的特定间隔验证其凭据。</span><span class="sxs-lookup"><span data-stu-id="2b394-137">Require that people verify their credentials at specific intervals.</span></span>  <br/> <span data-ttu-id="2b394-p107">如果您想要限制对到指定的时间段的内容的访问，请选择此选项。如果选择此选项，以访问该内容的人的发布许可证将过期后返回到服务器，以验证其凭据，并下载新副本都需要指定的数天和人员。</span><span class="sxs-lookup"><span data-stu-id="2b394-p107">Select this option if you want to restrict access to content to a specified period of time. If you select this option, people's issuance licenses to access the content will expire after the specified number of days, and people will be required to return to the server to verify their credentials and download a new copy.</span></span>  <br/> |<span data-ttu-id="2b394-140">选择**用户必须验证凭据使用此时间间隔 （天）** 复选框，，然后指定您希望查看文档的天数。</span><span class="sxs-lookup"><span data-stu-id="2b394-140">Select the **Users must verify their credentials using this interval (days)** check box, and then specify the number of days for which you want the document to be viewable.</span></span>  <br/> |
| <span data-ttu-id="2b394-141">阻止用户上载到此列表或库不支持 IRM 的文档。</span><span class="sxs-lookup"><span data-stu-id="2b394-141">Prevent people from uploading documents that do not support IRM to this list or library.</span></span>  <br/>  <span data-ttu-id="2b394-142">如果选择此选项，用户不能上载任何以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="2b394-142">If you select this option, people will not be able to upload any of the following file types:</span></span>  <br/>  <span data-ttu-id="2b394-143">没有相应的 IRM 保护程序安装在所有前端 Web 服务器上的文件类型。</span><span class="sxs-lookup"><span data-stu-id="2b394-143">File types that do not have corresponding IRM protectors installed on all of the front-end Web servers.</span></span>  <br/>  <span data-ttu-id="2b394-144">SharePoint Server 2010 无法解密的文件类型。</span><span class="sxs-lookup"><span data-stu-id="2b394-144">File types that SharePoint Server 2010 cannot decrypt.</span></span>  <br/>  <span data-ttu-id="2b394-145">受 IRM 保护其他程序中的文件类型</span><span class="sxs-lookup"><span data-stu-id="2b394-145">File types that are IRM protected in another program</span></span>  <br/> |<span data-ttu-id="2b394-146">选择**不允许用户上载不支持 IRM 的文档**复选框。</span><span class="sxs-lookup"><span data-stu-id="2b394-146">Select the **Do not allow users to upload documents that do not support IRM** check box.</span></span>  <br/> |
|<span data-ttu-id="2b394-147">在特定日期，请从此列表或库中删除受限的权限。</span><span class="sxs-lookup"><span data-stu-id="2b394-147">Remove restricted permissions from this list or library on a specific date.</span></span>  <br/> |<span data-ttu-id="2b394-148">选择**停止限制到在库的访问**复选框，然后选择所需的日期。</span><span class="sxs-lookup"><span data-stu-id="2b394-148">Select the **Stop restricting access to the library at** check box, and then select the date that you want.</span></span>  <br/> |
|<span data-ttu-id="2b394-149">控件的许可打开文档的程序缓存凭据的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="2b394-149">Control the interval that credentials are cached for the program that is licensed to open the document.</span></span>  <br/> |<span data-ttu-id="2b394-150">在**组保护和凭据时间间隔设置**，请输入 theinterval 中的天数的缓存凭据。</span><span class="sxs-lookup"><span data-stu-id="2b394-150">In the **Set group protection and credentials interval**, enter theinterval for caching credentials in number of days.</span></span>  <br/> |
|<span data-ttu-id="2b394-151">允许组保护，以便用户可以共享与同一组的成员。</span><span class="sxs-lookup"><span data-stu-id="2b394-151">Allow group protection so that users can share with members of the same group.</span></span>  <br/> |<span data-ttu-id="2b394-152">选择**允许组保护**，并输入用于共享的组的名称。</span><span class="sxs-lookup"><span data-stu-id="2b394-152">Select **Allow group protection**, and enter the group's name for sharing.</span></span>  <br/> |
   
8. <span data-ttu-id="2b394-153">选择所需的选项完后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2b394-153">After you finish selecting the options you want, click **OK**.</span></span>
  
## <a name="what-is-information-rights-management"></a><span data-ttu-id="2b394-154">什么是信息权限管理？</span><span class="sxs-lookup"><span data-stu-id="2b394-154">What is Information Rights Management?</span></span>
<span data-ttu-id="2b394-155"><a name="__toc256598175"> </a></span><span class="sxs-lookup"><span data-stu-id="2b394-155"></span></span>

<span data-ttu-id="2b394-p108">信息权限管理 (IRM)，可以限制用户可对已从列表或库中下载的文件执行的操作。IRM 加密下载的文件，并限制的用户和允许进行解密这些文件的程序集。IRM 还可以限制用户有权读取文件，以使它们无法执行操作，例如打印副本的文件或从中复制文本的权限。</span><span class="sxs-lookup"><span data-stu-id="2b394-p108">Information Rights Management (IRM) enables you to limit the actions that users can take on files that have been downloaded from lists or libraries. IRM encrypts the downloaded files and limits the set of users and programs that are allowed to decrypt these files. IRM can also limit the rights of the users who are allowed to read files, so that they cannot take actions such as print copies of the files or copy text from them.</span></span>
  
<span data-ttu-id="2b394-p109">您可以使用对列表或库 IRM 限制敏感内容的分发。例如，如果您正在创建文档库与选定的营销代表共享信息即将推出的产品，您可以使用 IRM 防止这些人员与公司中其他员工共享此内容。</span><span class="sxs-lookup"><span data-stu-id="2b394-p109">You can use IRM on lists or libraries to limit the dissemination of sensitive content. For example, if you are creating a document library to share information about upcoming products with selected marketing representatives, you can use IRM to prevent these individuals from sharing this content with other employees in the company.</span></span>
  
<span data-ttu-id="2b394-p110">在网站上，您应用 IRM 整个列表或库，而不是单个文件。这使得容易确保一致的整个组的文档或文件的保护级别。IRM 可以帮助组织强制实施调控的使用和分发的机密或专有信息的公司策略。</span><span class="sxs-lookup"><span data-stu-id="2b394-p110">On a site, you apply IRM to an entire list or library, rather than to individual files. This makes it easier to ensure a consistent level of protection for an entire set of documents or files. IRM can thus help your organization to enforce corporate policies that govern the use and dissemination of confidential or proprietary information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b394-164">信息权限管理有关此页上的信息取代所有 Microsoft SharePoint Server 2013 和 SharePoint Server 2016 许可证术语协议中的任何引用信息权限管理的术语。</span><span class="sxs-lookup"><span data-stu-id="2b394-164">The information on this page regarding Information Rights Management supersedes any terms that reference 'Information Rights Management' in any Microsoft SharePoint Server 2013 and SharePoint Server 2016 license term agreements.</span></span> 
  
### <a name="how-irm-can-help-protect-content"></a><span data-ttu-id="2b394-165">IRM 可帮助保护内容</span><span class="sxs-lookup"><span data-stu-id="2b394-165">How IRM can help protect content</span></span>
<span data-ttu-id="2b394-166"><a name="__toc256598176"> </a></span><span class="sxs-lookup"><span data-stu-id="2b394-166"></span></span>

<span data-ttu-id="2b394-167">IRM 有助于保护受限制的内容，按以下方式：</span><span class="sxs-lookup"><span data-stu-id="2b394-167">IRM helps to protect restricted content in the following ways:</span></span>
  
- <span data-ttu-id="2b394-168">有助于防止授权的查看者复制、 修改、 打印、 传真，或复制并粘贴未经授权使用的内容</span><span class="sxs-lookup"><span data-stu-id="2b394-168">Helps to prevent an authorized viewer from copying, modifying, printing, faxing, or copying and pasting the content for unauthorized use</span></span>
    
- <span data-ttu-id="2b394-169">有助于防止未授权的查看者通过 Microsoft Windows 中使用 Print Screen 功能复制的内容</span><span class="sxs-lookup"><span data-stu-id="2b394-169">Helps to prevent an authorized viewer from copying the content by using the Print Screen feature in Microsoft Windows</span></span>
    
- <span data-ttu-id="2b394-170">有助于防止未授权的查看如果从服务器下载后发送电子邮件中查看的内容</span><span class="sxs-lookup"><span data-stu-id="2b394-170">Helps to prevent an unauthorized viewer from viewing the content if it is sent in e-mail after it is downloaded from the server</span></span>
    
- <span data-ttu-id="2b394-171">限制访问内容设为一段指定时间，用户必须其后确认其凭据并再次下载内容</span><span class="sxs-lookup"><span data-stu-id="2b394-171">Restricts access to content to a specified period of time, after which users must confirm their credentials and download the content again</span></span>
    
- <span data-ttu-id="2b394-172">帮助强制实施调控的使用和分发的组织内的内容的公司策略</span><span class="sxs-lookup"><span data-stu-id="2b394-172">Helps to enforce corporate policies that govern the use and dissemination of content within your organization</span></span>
    
### <a name="how-irm-cannot-help-protect-content"></a><span data-ttu-id="2b394-173">IRM 无法帮助保护内容</span><span class="sxs-lookup"><span data-stu-id="2b394-173">How IRM cannot help protect content</span></span>
<span data-ttu-id="2b394-174"><a name="__toc256598177"> </a></span><span class="sxs-lookup"><span data-stu-id="2b394-174"></span></span>

<span data-ttu-id="2b394-175">IRM 无法从以下保护受限制的内容：</span><span class="sxs-lookup"><span data-stu-id="2b394-175">IRM cannot protect restricted content from the following:</span></span>
  
- <span data-ttu-id="2b394-176">擦除、 窃取、 捕获或通过恶意特洛伊木马、 击键记录器和某些类型的间谍软件等程序的传输</span><span class="sxs-lookup"><span data-stu-id="2b394-176">Erasure, theft, capture, or transmission by malicious programs such as Trojan horses, keystroke loggers, and certain types of spyware</span></span>
    
- <span data-ttu-id="2b394-177">丢失或损坏由于计算机病毒的操作</span><span class="sxs-lookup"><span data-stu-id="2b394-177">Loss or corruption because of the actions of computer viruses</span></span>
    
- <span data-ttu-id="2b394-178">手动复制或重新键入从屏幕上显示的内容</span><span class="sxs-lookup"><span data-stu-id="2b394-178">Manual copying or retyping of content from the display on a screen</span></span>
    
- <span data-ttu-id="2b394-179">数字或胶片屏幕上显示的内容的照片</span><span class="sxs-lookup"><span data-stu-id="2b394-179">Digital or film photography of content that is displayed on a screen</span></span>
    
- <span data-ttu-id="2b394-180">使用第三方屏幕捕获程序复制</span><span class="sxs-lookup"><span data-stu-id="2b394-180">Copying through the use of third-party screen-capture programs</span></span>
    
- <span data-ttu-id="2b394-181">复制内容元数据 （列值） 通过使用第三方屏幕捕获程序或复制和粘贴操作</span><span class="sxs-lookup"><span data-stu-id="2b394-181">Copying of content metadata (column values) through the use of third-party screen-capture programs or copy-and-paste action</span></span>
    
[<span data-ttu-id="2b394-182">对列表或库应用信息权限管理</span><span class="sxs-lookup"><span data-stu-id="2b394-182">Apply Information Rights Management to a list or library</span></span>](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a><span data-ttu-id="2b394-183">列表和库的 IRM 工作原理</span><span class="sxs-lookup"><span data-stu-id="2b394-183">How IRM works for lists and libraries</span></span>
<span data-ttu-id="2b394-184"><a name="__toc256598178"> </a></span><span class="sxs-lookup"><span data-stu-id="2b394-184"></span></span>

<span data-ttu-id="2b394-p111">IRM 保护应用于列表或库级别的文件。当为库启用 IRM 时，权限管理适用于所有的库中的文件。当列表启用 IRM 时，权限管理仅适用于附加到列表项，不是实际列表项的文件。</span><span class="sxs-lookup"><span data-stu-id="2b394-p111">IRM protection is applied to files at the list or library level. When IRM is enabled for a library, rights management applies to all of the files in that library. When IRM is enabled for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="2b394-p112">当人员下载 IRM 启用列表或库中的文件时，对文件进行加密，以便只有授权的用户可以查看它们。每个权限管理文件还包含对查看该文件的人员限制的发布许可证。典型的限制包括使文件只读的禁用文本，禁止用户保存的本地副本，并禁止用户打印文件复制。可以读取 IRM 支持的文件类型的客户端程序权限管理文件内使用的发布许可证强制实施这些限制。这是如何权限管理文件保留保护，即使它从服务器下载。</span><span class="sxs-lookup"><span data-stu-id="2b394-p112">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them. Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file. Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file. Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions. This is how a rights-managed file retains its protection even after it is downloaded from the server.</span></span>
  
<span data-ttu-id="2b394-p113">从列表或库中下载它时应用于文件的限制的类型基于的文件所在的网站上的单个用户的权限。下表介绍如何在网站上的权限对应的 IRM 权限。</span><span class="sxs-lookup"><span data-stu-id="2b394-p113">The types of restrictions that are applied to a file when it is downloaded from a list or library are based on the individual user's permissions on the site that contains the file. The following table explains how the permissions on sites correspond to IRM permissions.</span></span>
  
|<span data-ttu-id="2b394-195">**权限**</span><span class="sxs-lookup"><span data-stu-id="2b394-195">**Permissions**</span></span>|<span data-ttu-id="2b394-196">**IRM 权限**</span><span class="sxs-lookup"><span data-stu-id="2b394-196">**IRM Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2b394-197">管理权限、 管理网站</span><span class="sxs-lookup"><span data-stu-id="2b394-197">Manage Permissions, Manage Web Site</span></span>  <br/> |<span data-ttu-id="2b394-198">**完全控制**（在客户端程序中定义）： 此权限通常允许用户读取、 编辑、 复制、 保存和修改权限管理内容的权限。</span><span class="sxs-lookup"><span data-stu-id="2b394-198">**Full control** (as defined by the client program): This permission generally allows a user to read, edit, copy, save, and modify permissions of rights-managed content.</span></span>  <br/> |
|<span data-ttu-id="2b394-199">编辑项目、 管理列表、 添加和自定义页面</span><span class="sxs-lookup"><span data-stu-id="2b394-199">Edit Items, Manage Lists, Add and Customize Pages</span></span>  <br/> |<span data-ttu-id="2b394-200">**编辑**、**复制**和**保存**： 用户可以打印文件，仅当列表或库信息权限管理设置页上选择了**允许用户打印文档**复选框。</span><span class="sxs-lookup"><span data-stu-id="2b394-200">**Edit**, **Copy**, and **Save**: A user can print a file only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>  <br/> |
|<span data-ttu-id="2b394-201">查看项目</span><span class="sxs-lookup"><span data-stu-id="2b394-201">View Items</span></span>  <br/> |<span data-ttu-id="2b394-p114">**读取**： 用户可以读取文档，但不能复制或修改其内容。用户可以打印才列表或库信息权限管理设置页上选择了**允许用户打印文档**复选框。</span><span class="sxs-lookup"><span data-stu-id="2b394-p114">**Read**: A user can read the document, but cannot copy or modify its content. A user can print only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.  </span></span><br/> |
|<span data-ttu-id="2b394-204">其他</span><span class="sxs-lookup"><span data-stu-id="2b394-204">Other</span></span>  <br/> |<span data-ttu-id="2b394-205">没有其他权限直接对应于 IRM 权限。</span><span class="sxs-lookup"><span data-stu-id="2b394-205">No other permissions correspond directly to IRM permissions.</span></span>  <br/> |
   
<span data-ttu-id="2b394-p115">当您为列表或库 SharePoint Server 2013 中的启用 IRM 时，您可以仅保护该列表或为其保护程序安装在所有前端 Web 服务器的库中的文件类型。保护程序是一个控件的加密和解密权限管理的特定文件格式的文件的程序。SharePoint 包含以下文件类型的保护程序：</span><span class="sxs-lookup"><span data-stu-id="2b394-p115">When you enable IRM for a list or library in SharePoint Server 2013, you can only protect file types in that list or library for which a protector is installed on all front-end Web servers. A protector is a program that controls the encryption and decryption of rights-managed files of a specific file format. SharePoint includes protectors for the following file types:</span></span>
  
- <span data-ttu-id="2b394-209">Microsoft Office InfoPath 表单</span><span class="sxs-lookup"><span data-stu-id="2b394-209">Microsoft Office InfoPath forms</span></span>
    
- <span data-ttu-id="2b394-210">下面的 Microsoft Office 程序的 97-2003年文件格式： Word、 Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2b394-210">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="2b394-211">Office Open XML 格式的下列 Microsoft Office 程序： Word、 Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="2b394-211">The Office Open XML Formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="2b394-212">XML 纸张规范 (XPS) 格式</span><span class="sxs-lookup"><span data-stu-id="2b394-212">The XML Paper Specification (XPS) format</span></span>
    
<span data-ttu-id="2b394-213">如果您的组织计划使用 IRM 保护除外上面列出的任何其他文件类型，您的服务器管理员必须安装这些其他文件格式的保护程序。</span><span class="sxs-lookup"><span data-stu-id="2b394-213">If your organization plans to use IRM to protect any other file types in addition to those listed above, your server administrator must install protectors for these additional file formats.</span></span>
  


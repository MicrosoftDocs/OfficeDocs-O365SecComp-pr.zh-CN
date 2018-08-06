---
title: 使用除名门户来将自己从 Office 365 阻止的发件人名单中删除
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/18/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
description: 当您尝试向其电子邮件地址位于 Office 365 中的收件人发送电子邮件时，是否收到一条错误消息？如果您认为不应该会收到错误消息，则可以使用除名门户将自己从 Office 365 阻止的发件人名单中删除。
ms.openlocfilehash: 127b305cdb27cffadc7ad6a43a5d2db2440365ca
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026229"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a>使用除名门户来将自己从 Office 365 阻止的发件人名单中删除

当您尝试向其电子邮件地址位于 Office 365 中的收件人发送电子邮件时，是否收到一条错误消息？如果您认为不应该会收到错误消息，则可以使用除名门户将自己从 Office 365 阻止的发件人名单中删除。
  
## <a name="what-is-the-office-365-blocked-senders-list"></a>什么是 Office 365 阻止的发件人名单？

Microsoft 使用阻止的发件人名单来防止其客户遭受垃圾邮件、欺诈和网络钓鱼网站的攻击。您的邮件服务器的 IP 地址就是邮件服务器用来在 Internet 上标识自己的地址，由于以下各种原因之一，IP 地址被标记为 Office 365 的一个潜在威胁。当 Office 365 将该 IP 地址添加到列表中时，它会阻止该 IP 地址与通过我们数据中心我的所有客户进行任何进一步的通信。
  
在您收到包含类似于以下错误的邮件回复时，您就知道自己已被添加到该列表中：
  
访问被拒绝，550 5.7.606-649 禁止发送 IP [ _IP 地址_];请求此列表中的删除，请访问https://sender.office.com/然后按照说明操作。有关详细信息，请参阅[Office 365 中的电子邮件未送达报告](http://go.microsoft.com/fwlink/?LinkID=526653)。
  
其中  _IP address_ 是邮件服务器在其上运行的计算机的 IP 地址。 
  
### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>若要使用 Office 365 除名门户来将自己从阻止的发件人名单中删除

1. 在 Web 浏览器中，请转至 [https://sender.office.com](https://sender.office.com)。
    
2. 按照页面上的说明执行操作。请确保您使用收到错误消息的电子邮件地址，以及错误消息中指定的 IP 地址。每次访问只能输入一个电子邮件地址和一个 IP 地址。
    
3. 单击"提交"。
    
    门户向您提供的电子邮件地址发送电子邮件。电子邮件将类似于以下：![提交通过 delist 门户请求时所接收的电子邮件的屏幕截图](media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)
  
4. 单击除名门户发送给您的电子邮件中的确认链接。
    
    这将使您返回到除名门户。
    
5. 在 delist 门户中，单击**Delist IP**。
    
    从阻止的发件人名单中删除 IP 地址后，来自该 IP 地址的电子邮件将发送给使用 Office 365 的收件人。因此，请确保您确信从该 IP 地址发送的电子邮件不会被滥用或恶意攻击。否则，可能会再次阻止该 IP 地址。
    


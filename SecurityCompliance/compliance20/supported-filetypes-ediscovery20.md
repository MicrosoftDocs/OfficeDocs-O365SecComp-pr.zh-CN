---
title: 高级电子数据展示中支持的文件类型
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 378bd9ae88269d6a6d15a672473550e50179f772
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834931"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>高级电子数据展示中支持的文件类型

高级电子数据展示支持多种文件类型, 并支持它们在不同的级别, 如下表所述。 此列表尚未最终完成, 我们将在继续进行验证测试时添加新的文件类型。 该表还指示是否可以在高级电子数据展示中的可用查看器中查看文件类型。

| Mime 类型 | 说明 | 本机查看器 | 文本查看器 | 批注查看器 | 容器提取 | 扩展 |
| :- | :- | :- | :- | :- | :- | :- |
| application/mbox | 存档/容器 |  |  |  | 是 | .mbox |
| application/msword | 工作效率 | 是 | 是 | 是 |  | .doc; .dat |
| application/pdf | 工作效率 | 是 | 是 | 是 |  | .pdf |
| 应用程序/rtf | Document | 是 | 是 | 是 |  | .rtf;。首 |
| application/vnd.ms-excel ms-excel | 工作效率 | 是 | 是 | 是 |  | .xls; .dat |
| ms-excel 的应用程序/vnd.ms-excel | 工作效率 | 是 | 是 | 否 |  | 。 xlsb |
| ms-excel 的应用程序/vnd.ms-excel | 工作效率 | 是 | 是 | 是 |  | 。 xlsm |
| ms-excel 的应用程序/vnd.ms-excel | 工作效率 | 否 | 必需 | 否 |  | 。 .xltm |
| application/vnd.ms-excel ms-outlook | 协作 | 是 | 是 | 是 |  | .msg |
| application/vnd.ms-excel ms-outlook-pst | 存档/容器 |  |  |  | 是 | .pst |
| application/vnd.ms-excel ms-powerpoint | 工作效率 | 是 | 是 | 是 |  | .ppt; .pps;。尽头 |
| ms-word 的应用程序/vnd.ms-excel | 工作效率 | 是 | 是 | 是 |  | .docm |
| ms-word 的应用程序/vnd.ms-excel | 工作效率 | 是 | 是 | 是 |  | normal.dotm |
| oasis 的应用程序/vnd.ms-excel | 工作效率 | 是 | 是 | 是 |  | odt  |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | 工作效率 | 是 | 是 | 是 |  | .pptx |
| openxmlformats-officedocument 的应用程序/vnd.ms-excel | 工作效率 | 是 | 是 | 是 |  | 。 ppsx |
| openxmlformats-officedocument 的应用程序/vnd.ms-excel | 工作效率 | 是 | 是 | 是 |  | 。 .potx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | 工作效率 | 是 | 是 | 是 |  | .xlsx |
| openxmlformats-officedocument 的应用程序/vnd.ms-excel | 工作效率 | 是 | 是 | 是 |  | 。 .xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | 工作效率 | 是 | 是 | 是 |  | .docx |
| openxmlformats-officedocument 的应用程序/vnd.ms-excel | 工作效率 | 是 | 是 | 是 |  | 。 .dotx |
| application/vnd.ms-excel | 工作效率 | 是 | 是 | 是 |  | .vsd |
| application/x-.7z-压缩 | 存档/容器 |  |  |  | 是 | 。 .7z |
| application/xhtml + xml | Document | 是 | 是 | 是 |  | 的 xhtml |
| application/xml | Document | 是 | 是 | 是 |  | .xml |
| application/x-msaccess | 工作效率 | 是 | 是 | 是 |  | .mdb |
| application/x-mspublisher | 工作效率 | 是 | 是 | 是 |  | .pub |
| application/x-已压缩的 rar | 存档/容器 |  |  |  | 是 | rar |
| 应用程序/x-tar | 存档/容器 |  |  |  | 是 | tar |
| application/zip | 存档/容器 |  |  |  | 是 | .zip |
| image/bmp | 图像 | 是 | 是 | 是 |  | .bmp |
| image/emf | 图像 | 是 | 是 | 是 |  | .emf |
| image/gif | 图像 | 是 | 是 | 是 |  | .gif |
| image/jpeg | 图像 | 是 | 是 | 是 |  | .jpg;。 jpeg; .dat;。jpgt |
| image/png | 图像 | 是 | 是 | 是 |  | .png |
| image/tiff | 图像 | 是 | 是 | 是 |  | .tif |
| image/vnd.ms-excel | 绘图 | 是 | 是 | 是 |  | dwg;。.dxf |
| image/wmf | Document | 是 | 是 | 是 |  | .wmf |
| message//rfc822 | 协作 | 是 | 是 | 是 |  | .eml |
| text/csv | Document | 是 | 是 | 是 |  | .csv |
| 文本/html | Document | 是 | 是 | 是 |  | .html;。shtml |
| text/plain | Document | 是 | 是 | 是 |  | .txt; .css;。con;。 pl; .csv; .dat |
| 文本/电子名片-联系人 | 协作 | 是 | 是 | 是 |  | .vcf |
||||||||

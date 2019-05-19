---
title: 数据调查中支持的文件类型 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 60e4baf2df94793b532fb4035a34ca3c7a5cd332
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153574"
---
# <a name="supported-file-types-in-data-investigations-preview"></a>数据调查中支持的文件类型 (预览)

数据调查 (预览) 通过几种不同的方式支持多种文件类型, 如下表所述。 此列表未定稿, 我们将在继续进行验证测试时添加新的文件类型。 该表还指示在审阅证据时是否可以在可用查看器中查看文件类型。

| Mime 类型 | File 类 | 本机查看器 | 文本查看器 | 批注查看器 | 容器提取 | 扩展 |
| :- | :- | :- | :- | :- | :- | :- |
| application/msword | Document | 是 | 是 | 是 | 否 | .doc; .dat |
| application/pdf | Document | 是 | 是 | 是 | 否 | .pdf |
| 应用程序/rtf | Document | 是 | 是 | 是 | 否 | .rtf;。首 |
| application/vnd.ms-excel ms-excel | Document | 是 | 是 | 是 | 否 | .xls; .dat |
| ms-excel 的应用程序/vnd.ms-excel | 生产率/开放式文档格式 | 是 | 是 | 否 | 否 | 。 xlsb |
| ms-excel 的应用程序/vnd.ms-excel | Document | 是 | 是 | 是 | 否 | 。 xlsm |
| ms-excel 的应用程序/vnd.ms-excel | 生产率/开放式文档格式 | 否 | 必需 | 否 | 否 | 。 .xltm |
| application/vnd.ms-excel ms-outlook | 工作效率 | 否 | 否 | 否 | 否 | .msg |
| application/vnd.ms-excel ms-outlook-pst | 工作效率/协作 | 否 | 否 | 否 | 可访问 | .pst |
| application/vnd.ms-excel ms-powerpoint | Document | 是 | 是 | 是 | 否 | .ppt; .pps;。尽头 |
| ms-word 的应用程序/vnd.ms-excel | Document | 是 | 是 | 是 | 否 | .docm |
| ms-word 的应用程序/vnd.ms-excel | Document | 是 | 是 | 是 | 否 | normal.dotm |
| oasis 的应用程序/vnd.ms-excel | Document | 是 | 是 | 是 | 否 | odt  |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | Document | 是 | 是 | 是 | 否 | .pptx |
| openxmlformats-officedocument 的应用程序/vnd.ms-excel | 生产率/开放式文档格式 | 是 | 是 | 是 | 否 | 。 ppsx |
| openxmlformats-officedocument 的应用程序/vnd.ms-excel | Document | 是 | 是 | 是 | 否 | 。 .potx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Document | 是 | 是 | 是 | 否 | .xlsx |
| openxmlformats-officedocument 的应用程序/vnd.ms-excel | Document | 是 | 是 | 是 | 否 | 。 .xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | Document | 是 | 是 | 是 | 否 | .docx |
| openxmlformats-officedocument 的应用程序/vnd.ms-excel | Document | 是 | 是 | 是 | 否 | 。 .dotx |
| application/vnd.ms-excel | Document | 是 | 是 | 是 | 否 | .vsd |
| application/x-.7z-压缩 | 存档/容器 | 否 | 否 | 否 | 可访问 | 。 .7z |
| application/xhtml + xml | Document | 是 | 是 | 是 | 否 | 的 xhtml |
| application/xml | Document | 是 | 是 | 是 | 否 | .xml |
| application/x-msaccess | Document | 是 | 是 | 是 | 否 | .mdb |
| application/x-mspublisher | Document | 是 | 是 | 是 | 否 | .pub |
| application/x-已压缩的 rar | 存档/容器 | 否 | 否 | 否 | 可访问 | rar |
| application/zip | 存档/容器 | 否 | 否 | 否 | 可访问 | .zip |
| image/bmp | 图像 | 是 | 是 | 是 | 否 | .bmp |
| image/emf | 图像 | 是 | 是 | 是 | 否 | .emf |
| image/gif | Document | 是 | 是 | 是 | 否 | .gif |
| image/jpeg | 图像 | 是 | 是 | 是 | 否 | .jpg;. jpeg; .dat;。jpgt |
| image/png | 图像 | 是 | 是 | 是 | 否 | .png |
| image/tiff | 图像 | 是 | 是 | 是 | 否 | .tif |
| image/vnd.ms-excel | Document | 是 | 是 | 是 | 否 | dwg;。.dxf |
| image/wmf | Document | 是 | 是 | 是 | 否 | .wmf |
| message//rfc822 | 工作效率/协作 | 否 | 否 | 否 | 否 | .eml |
| text/csv | Document | 是 | 是 | 是 | 否 | .csv |
| 文本/html | Document | 是 | 是 | 是 | 否 | .html;。shtml |
| text/plain | Document | 是 | 是 | 是 | 否 | .txt; .css;。con;. pl; .csv; .dat |
| 文本/电子名片-联系人 | Document | 是 | 是 | 是 | 否 | .vcf |
||||||||

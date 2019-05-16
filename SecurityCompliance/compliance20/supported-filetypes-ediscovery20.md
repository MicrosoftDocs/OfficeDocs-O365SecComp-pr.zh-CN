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
ms.openlocfilehash: d8e9689cb04929137787225579dcda17005c8bfe
ms.sourcegitcommit: 7be8617ce75909f0fa1a2f6e72749e2ef4bb2d3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2019
ms.locfileid: "34088805"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>高级电子数据展示中支持的文件类型

高级电子数据展示支持多种不同级别的文件类型, 如下表所述。 此列表未定稿, 我们将在继续进行验证测试时添加新的文件类型。 这些表指示文件类型是否支持文本提取 (图像的 OCR)、在本机查看器中可见, 还支持高级电子数据展示中的批注查看器。

## <a name="archive--container"></a>存档/容器

| Mime 类型 | 文件标识 | 元数据提取 | 容器提取 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |
| application/x-.7z-压缩 | 是 | 是 | 是 | 。 .7z |
| application/x-已压缩的 rar | 是 | 是 | 是 | rar |
| 应用程序/x-tar | 是 | 是 | 是 | tar |
| application/zip | 是 | 是 | 是 | .zip |
||||||||

## <a name="database"></a>数据库

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/x-msaccess | 是 | 是 | 是 | 否 | 否 | .mdb |
||||||||

## <a name="email"></a>电子邮件

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd.ms-excel ms-outlook | 是 | 是 | 是 | 是 | 是 | .msg |
| message//rfc822 | 是 | 是 | 是 | 是 | 是 | .eml |
| 文本/电子名片-联系人 | 是 | 是 | 是 | 是 | 是 | .vcf |
||||||||

## <a name="email-container"></a>电子邮件容器

| Mime 类型 | 文件标识 | 元数据提取 | 容器提取 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |
| application/mbox | 是 | 是 | 是 | .mbox |
| application/vnd.ms-excel ms-outlook-pst | 是 | 是 | 是 | .pst |
||||||||

## <a name="html"></a>HTML

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/xhtml + xml | 是 | 是 | 是 | 是 | 是 | 的 xhtml |
| application/xml | 是 | 是 | 是 | 是 | 是 | .xml |
| 文本/html | 是 | 是 | 是 | 是 | 是 | .htm; .html;。 shtml |
||||||||

## <a name="image"></a>图像

| Mime 类型 | 文件标识 | 元数据提取 | OCR 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| image/bmp | 是 | 是 | 是 | 是 | 是 | .bmp |
| image/emf | 是 | 是 | 是 | 是 | 是 | .emf |
| image/gif | 是 | 是 | 是 | 是 | 是 | .gif |
| image/jpeg | 是 | 是 | 是 | 是 | 是 | jpeg; .jpg |
| image/png | 是 | 是 | 是 | 是 | 是 | .png |
| image/svg + xml | 是 | 是 | 是 | 是 | 否 | svg |
| image/tiff | 是 | 是 | 是 | 是 | 是 | .tif |
| image/vnd.ms-excel | 是 | 是 | 是 | 是 | 是 | dwg; dxf |
| image/wmf | 是 | 是 | 是 | 是 | 是 | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd.ms-excel ms-excel | 是 | 是 | 是 | 是 | 是 | .dat; .xls |
| ms-excel 的应用程序/vnd.ms-excel | 是 | 是 | 是 | 是 | 否 | 。 xlsb |
| ms-excel 的应用程序/vnd.ms-excel | 是 | 是 | 是 | 是 | 是 | 。 xlsm |
| ms-excel 的应用程序/vnd.ms-excel | 是 | 是 | 是 | 否 | 否 | 。 .xltm |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | 是 | 是 | 是 | 是 | 是 | .xlsx |
| openxmlformats-officedocument 的应用程序/vnd.ms-excel | 是 | 是 | 是 | 是 | 是 | 。 .xltx |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft Powerpoint

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd.ms-excel ms-powerpoint | 是 | 是 | 是 | 是 | 是 | .pot; .pps; .ppt |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | 是 | 是 | 是 | 是 | 是 | .pptx |
| openxmlformats-officedocument 的应用程序/vnd.ms-excel | 是 | 是 | 是 | 是 | 是 | 。 ppsx |
| openxmlformats-officedocument 的应用程序/vnd.ms-excel | 是 | 是 | 是 | 是 | 是 | 。 .potx |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/x-mspublisher | 是 | 是 | 是 | 是 | 是 | .pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| ms-visio 的应用程序/vnd.ms-excel | 是 | 是 | 是 | 是 | 否 |  |
| application/vnd.ms-excel | 是 | 是 | 是 | 是 | 是 | .vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/msword | 是 | 是 | 是 | 是 | 是 | .dat; .doc |
| 应用程序/rtf | 是 | 是 | 是 | 是 | 是 | .doc; .rtf |
| ms-word 的应用程序/vnd.ms-excel | 是 | 是 | 是 | 是 | 是 | .docm |
| ms-word 的应用程序/vnd.ms-excel | 是 | 是 | 是 | 是 | 是 | normal.dotm |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | 是 | 是 | 是 | 是 | 是 | .docx |
| openxmlformats-officedocument 的应用程序/vnd.ms-excel | 是 | 是 | 是 | 是 | 是 | 。 .dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft 工作

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| ms-works-ss 的应用程序/vnd.ms-excel | 是 | 是 | 否 | 否 | 否 | wps |
| application/vnd.ms-excel ms-works-wp | 是 | 是 | 否 | 否 | 否 | wps |
||||||||

## <a name="open-document-format"></a>打开文档格式

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| oasis 的应用程序/vnd.ms-excel | 是 | 是 | 是 | 是 | 是 | odt |
||||||||

## <a name="other"></a>Other

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/json | 是 | 是 | 是 | 是 | 是 | 不适用 |
| application/vnd.ms-excel ms-graph | 是 | 是 | 否 | 否 | 否 |  |
| application/winhlp | 是 | 是 | 否 | 否 | 否 | .hlp |
| 应用程序/x-tnef | 是 | 是 | 否 | 否 | 否 |  |
||||||||

## <a name="plain-text"></a>纯文本

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| text/csv | 是 | 是 | 是 | 是 | 是 | .csv |
| text/plain | 是 | 是 | 是 | 是 | 是 | con; .css; .csv; .dat;。 pl; .txt |
||||||||

## <a name="portable-document-format"></a>Portable Document Format

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/pdf | 是 | 是 | 是 | 是 | 是 | .pdf |
||||||||

## <a name="word-perfect"></a>Word 完美

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd.ms-excel;版本 = 5。0 | 是 | 是 | 是 | 否 | 否 | .wpd |
| application/vnd.ms-excel;版本 = 5。1 | 是 | 是 | 是 | 否 | 否 | .wpd |
| application/vnd.ms-excel;版本 = 6。 x | 是 | 是 | 是 | 否 | 否 | .wpd |
||||||||

## <a name="word-pro"></a>Word Pro

| Mime 类型 | 文件标识 | 元数据提取 | 文本提取 | 本机查看器 | 批注查看器 | 可能的扩展 |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd.ms-excel lotus-wordpro | 是 | 是 | 否 | 否 | 否 | lwp |
||||||||

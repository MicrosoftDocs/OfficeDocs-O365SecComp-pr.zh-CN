---
title: 主题
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
ms.openlocfilehash: b26b031b767f23504294880f4424be5042350c71
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151434"
---
# <a name="themes"></a><span data-ttu-id="9f212-102">主题</span><span class="sxs-lookup"><span data-stu-id="9f212-102">Themes</span></span>
<span data-ttu-id="9f212-103">用户如何编写文档？</span><span class="sxs-lookup"><span data-stu-id="9f212-103">How does a person write a document?</span></span> <span data-ttu-id="9f212-104">它们通常从要在文档中传达的一个或多个想法开始, 并使用与想法一致的单词进行撰写。</span><span class="sxs-lookup"><span data-stu-id="9f212-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="9f212-105">概念越普遍, 与该想法相关的词越常见。</span><span class="sxs-lookup"><span data-stu-id="9f212-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="9f212-106">这将通知用户如何同时使用文档;从阅读文档中获取的重要内容是文档试图传达的想法, 以及在何处显示的想法, 以及这些想法之间的关系。</span><span class="sxs-lookup"><span data-stu-id="9f212-106">This informs how people consume documents as well; the important thing to get from reading a document is the ideas that the document is trying to convey, and which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="9f212-107">这可以扩展到用户想要使用一组文档的方式。</span><span class="sxs-lookup"><span data-stu-id="9f212-107">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="9f212-108">他们想要了解哪些想法在集合中, 以及哪些文档在谈论这些想法。</span><span class="sxs-lookup"><span data-stu-id="9f212-108">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="9f212-109">此外, 如果他们找到感兴趣的特定文档, 他们希望能够查看讨论类似想法的文档。</span><span class="sxs-lookup"><span data-stu-id="9f212-109">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="9f212-110">主题模块尝试通过分析审阅集中讨论的 "主题" 并将其分配给文档来模拟文档的人方面原因。</span><span class="sxs-lookup"><span data-stu-id="9f212-110">Themes module tries to mimic how humans reason about documents, by analyzing the "themes" that are discussed in a review set and assigning them to documents.</span></span> <span data-ttu-id="9f212-111">主题更深入一步, 并将每个文档标识为 "主要主题";即显示最多的主题。</span><span class="sxs-lookup"><span data-stu-id="9f212-111">Themes goes one step further and identifies per document the "dominant theme"; i.e. the theme that appears the most.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="9f212-112">主题的工作原理是什么？</span><span class="sxs-lookup"><span data-stu-id="9f212-112">How does Themes work?</span></span>
<span data-ttu-id="9f212-113">主题使用审阅集中的文本分析文档, 以分析在文档中显示的常见主题。</span><span class="sxs-lookup"><span data-stu-id="9f212-113">Themes analyzes documents with text in a review set to parse out common themes that appear accross the documents.</span></span> <span data-ttu-id="9f212-114">然后, 它会将这些主题分配给它们显示的文档。</span><span class="sxs-lookup"><span data-stu-id="9f212-114">Then, it assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="9f212-115">它还使用在文档中使用的单词进行标记, 这些文档代表主题。</span><span class="sxs-lookup"><span data-stu-id="9f212-115">It also labels each with words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="9f212-116">由于文档可能不止一个主题, 因此在很多情况下, 一个文档会分配多个主题。</span><span class="sxs-lookup"><span data-stu-id="9f212-116">Since a document can be about more than one subject matter, in many cases a document has more than one themes assigned to it.</span></span> <span data-ttu-id="9f212-117">文档中显示最醒目的主题被指定为其主要主题。</span><span class="sxs-lookup"><span data-stu-id="9f212-117">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
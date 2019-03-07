---
title: 查询工作集中的数据
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
ms.openlocfilehash: 2523072181307cce510f0f318834329b2c70b376
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454984"
---
# <a name="query-the-data-in-a-working-set"></a><span data-ttu-id="b44ff-102">查询工作集中的数据</span><span class="sxs-lookup"><span data-stu-id="b44ff-102">Query the data in a working set</span></span>

<span data-ttu-id="b44ff-103">在大多数情况下, 能够深入了解工作集中存在的内容并对其进行组织以更高效地进行查看, 这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="b44ff-103">In most cases, it will be useful to be able to dig deeper into what is there in a working set and organize them to review more efficiently.</span></span> <span data-ttu-id="b44ff-104">使用工作集中的查询, 您可以将重点放在符合您一次定义的条件的文档子集上, 从而实现此目的。</span><span class="sxs-lookup"><span data-stu-id="b44ff-104">Queries within a working set enables you to do so by letting you focus on a subset of documents that meet the criteria defined by you at once.</span></span>

## <a name="creating-and-running-a-query-within-a-working-set"></a><span data-ttu-id="b44ff-105">在工作集中创建和运行查询</span><span class="sxs-lookup"><span data-stu-id="b44ff-105">Creating and running a query within a working set</span></span>

<span data-ttu-id="b44ff-106">若要在工作集中创建和运行查询, 请单击工作集中的 "新建查询"。</span><span class="sxs-lookup"><span data-stu-id="b44ff-106">In order to create and run a query within your working set, click on "New Query" in your working set.</span></span> <span data-ttu-id="b44ff-107">命名查询并定义条件后, 请单击 "保存" 以运行查询。</span><span class="sxs-lookup"><span data-stu-id="b44ff-107">After you name your query and define the conditions, click "Save" to run the query.</span></span> <span data-ttu-id="b44ff-108">若要运行以前保存的查询, 只需单击已保存的查询即可。</span><span class="sxs-lookup"><span data-stu-id="b44ff-108">To run a query that has been previously saved, simply click on the saved query.</span></span> <span data-ttu-id="b44ff-109">有关可以搜索的元数据列表, 请参阅[文档元数据字段](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="b44ff-109">Refer to [Document metadata fields](document-metadata-fields.md) for a list of metadata you can search by.</span></span>

## <a name="building-your-query"></a><span data-ttu-id="b44ff-110">构建查询</span><span class="sxs-lookup"><span data-stu-id="b44ff-110">Building your query</span></span>

<span data-ttu-id="b44ff-111">您可以在关键字条件卡中使用条件卡片和查询语言的组合生成查询。</span><span class="sxs-lookup"><span data-stu-id="b44ff-111">You can build your query using a combination of condition cards and query language in the Keywords condition card.</span></span>

### <a name="condition-card"></a><span data-ttu-id="b44ff-112">条件卡片</span><span class="sxs-lookup"><span data-stu-id="b44ff-112">Condition card</span></span>

<span data-ttu-id="b44ff-113">工作集中的每个可搜索字段都有一个对应的条件卡, 可用于生成查询。</span><span class="sxs-lookup"><span data-stu-id="b44ff-113">Every searchable field in a working set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="b44ff-114">有多种类型的条件卡:</span><span class="sxs-lookup"><span data-stu-id="b44ff-114">There are multiple types of condition cards:</span></span>
- <span data-ttu-id="b44ff-115">Freetext: freetext 条件卡片用于文本字段, 如 subject。</span><span class="sxs-lookup"><span data-stu-id="b44ff-115">Freetext: freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="b44ff-116">您可以通过用逗号分隔多个搜索词来列出它们。</span><span class="sxs-lookup"><span data-stu-id="b44ff-116">You can list multiple search terms by separating them out with a comma.</span></span>
- <span data-ttu-id="b44ff-117">日期: 日期条件卡片用于日期字段 (如 "上次修改日期")。</span><span class="sxs-lookup"><span data-stu-id="b44ff-117">Date: date condition card is used for date fields such as last modified date.</span></span>
- <span data-ttu-id="b44ff-118">搜索选项: 搜索选项条件卡片将为工作集中的特定字段提供可能的值列表。</span><span class="sxs-lookup"><span data-stu-id="b44ff-118">Search options: search options condition card will provide a list of possible values for the particular field in your working set.</span></span> <span data-ttu-id="b44ff-119">这用于发件人之类的字段, 其中的工作集中有有限数量的可能值。</span><span class="sxs-lookup"><span data-stu-id="b44ff-119">This is used for fields such as sender, where there is a finite number of possible values in your working set.</span></span>
- <span data-ttu-id="b44ff-120">关键字: 关键字条件卡片是 freetext 条件卡的特定实例, 可用于搜索术语, 或在中使用类似 KQL 的查询语言。</span><span class="sxs-lookup"><span data-stu-id="b44ff-120">Keyword: keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="b44ff-121">有关更多详细信息, 请参阅下文。</span><span class="sxs-lookup"><span data-stu-id="b44ff-121">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="b44ff-122">查询语言</span><span class="sxs-lookup"><span data-stu-id="b44ff-122">Query language</span></span>

<span data-ttu-id="b44ff-123">除了条件卡片之外, 还可以使用关键字卡片中类似于 KQL 的查询语言来手工创建查询。</span><span class="sxs-lookup"><span data-stu-id="b44ff-123">In addition to condition cards, you can use a KQL-like query language in the Keywords card to craft your query.</span></span> <span data-ttu-id="b44ff-124">查询语言支持标准 KQL 语法, 如 AND、OR、NOT 和 NEAR (n)。</span><span class="sxs-lookup"><span data-stu-id="b44ff-124">The query language supports standard KQL syntax like AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="b44ff-125">它还支持单字符通配符 (？) 和多字符通配符 (\*)。</span><span class="sxs-lookup"><span data-stu-id="b44ff-125">It also supports single-character wildcard (?) and multi-character wildcard (\*).</span></span>
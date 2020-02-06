---
title: 商務用 Skype Server 2015 中的主控表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: 主控資料表是一種支援表格，可儲存點對點工作階段和會議會話中所使用的內容類型清單。 資料表中的每一筆記錄代表一種內容類型。
ms.openlocfilehash: 6dadf7de0107005cca751e27f0c0250bc8f9f03a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815301"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e4dde-104">商務用 Skype Server 2015 中的主控表格</span><span class="sxs-lookup"><span data-stu-id="e4dde-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e4dde-105">主控資料表是一種支援表格，可儲存點對點工作階段和會議會話中所使用的內容類型清單。</span><span class="sxs-lookup"><span data-stu-id="e4dde-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="e4dde-106">資料表中的每一筆記錄代表一種內容類型。</span><span class="sxs-lookup"><span data-stu-id="e4dde-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="e4dde-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="e4dde-107">**Column**</span></span>|<span data-ttu-id="e4dde-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="e4dde-108">**Data Type**</span></span>|<span data-ttu-id="e4dde-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="e4dde-109">**Key/Index**</span></span>|<span data-ttu-id="e4dde-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="e4dde-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e4dde-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="e4dde-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="e4dde-112">int</span><span class="sxs-lookup"><span data-stu-id="e4dde-112">int</span></span>  <br/> |<span data-ttu-id="e4dde-113">首選</span><span class="sxs-lookup"><span data-stu-id="e4dde-113">Primary</span></span>  <br/> |<span data-ttu-id="e4dde-114">識別內容類型的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="e4dde-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="e4dde-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="e4dde-115">**ContentType**</span></span> <br/> |<span data-ttu-id="e4dde-116">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e4dde-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="e4dde-117">內容類型名稱。</span><span class="sxs-lookup"><span data-stu-id="e4dde-117">Content type name.</span></span>  <br/> |
   


---
title: CodecDescription 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 表格會將唯一的編解碼器識別碼對應至其相對應的編解碼器。 編解碼器是用來編碼傳輸和廣播的數位信號，然後解碼這些信號以進行播放。 此表格是在 Microsoft Lync Server 2013 中推出
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810361"
---
# <a name="codecdescription-table"></a><span data-ttu-id="c0076-105">CodecDescription 資料表</span><span class="sxs-lookup"><span data-stu-id="c0076-105">CodecDescription table</span></span>
 
<span data-ttu-id="c0076-106">CodecDescription 表格會將唯一的編解碼器識別碼對應至其相對應的編解碼器。</span><span class="sxs-lookup"><span data-stu-id="c0076-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="c0076-107">編解碼器是用來編碼傳輸和廣播的數位信號，然後解碼這些信號以進行播放。</span><span class="sxs-lookup"><span data-stu-id="c0076-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="c0076-108">此表格是在 Microsoft Lync Server 2013 中推出</span><span class="sxs-lookup"><span data-stu-id="c0076-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="c0076-109">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c0076-109">**Column**</span></span>|<span data-ttu-id="c0076-110">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="c0076-110">**Data Type**</span></span>|<span data-ttu-id="c0076-111">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="c0076-111">**Key/Index**</span></span>|<span data-ttu-id="c0076-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="c0076-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c0076-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="c0076-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="c0076-114">Smallint</span><span class="sxs-lookup"><span data-stu-id="c0076-114">smallint</span></span>  <br/> |<span data-ttu-id="c0076-115">首選</span><span class="sxs-lookup"><span data-stu-id="c0076-115">Primary</span></span>  <br/> |<span data-ttu-id="c0076-116">指派給編解碼器的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c0076-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="c0076-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="c0076-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="c0076-118">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="c0076-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="c0076-119">唯一</span><span class="sxs-lookup"><span data-stu-id="c0076-119">Unique</span></span>  <br/> |<span data-ttu-id="c0076-120">對應至 CodecDescriptionKey 的編解碼器的唯一描述。</span><span class="sxs-lookup"><span data-stu-id="c0076-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   


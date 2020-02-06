---
title: 商務用 Skype Server 2015 中的 CallPriorities 表格
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 資料表是一個靜態資料表，可儲存可能的通話優先順序清單，例如「緊急」、「緊急」或「標準」。
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815441"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="59a03-103">商務用 Skype Server 2015 中的 CallPriorities 表格</span><span class="sxs-lookup"><span data-stu-id="59a03-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="59a03-104">CallPriorities 資料表是一個靜態資料表，可儲存可能的通話優先順序清單，例如「緊急」、「緊急」或「標準」。</span><span class="sxs-lookup"><span data-stu-id="59a03-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="59a03-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="59a03-105">**Column**</span></span>|<span data-ttu-id="59a03-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="59a03-106">**Data Type**</span></span>|<span data-ttu-id="59a03-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="59a03-107">**Key/Index**</span></span>|<span data-ttu-id="59a03-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="59a03-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="59a03-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="59a03-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="59a03-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="59a03-110">tinyint</span></span>  <br/> |<span data-ttu-id="59a03-111">首選</span><span class="sxs-lookup"><span data-stu-id="59a03-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="59a03-112">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="59a03-112">**Priority**</span></span> <br/> |<span data-ttu-id="59a03-113">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="59a03-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="59a03-114">允許的值：</span><span class="sxs-lookup"><span data-stu-id="59a03-114">Allowed values:</span></span> <br/>  <span data-ttu-id="59a03-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="59a03-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="59a03-116">1-非緊急</span><span class="sxs-lookup"><span data-stu-id="59a03-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="59a03-117">2-標準</span><span class="sxs-lookup"><span data-stu-id="59a03-117">2 - Normal</span></span> <br/>  <span data-ttu-id="59a03-118">3-緊急</span><span class="sxs-lookup"><span data-stu-id="59a03-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="59a03-119">4-緊急</span><span class="sxs-lookup"><span data-stu-id="59a03-119">4 - Emergency</span></span> <br/> |
   


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
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 資料表是一個靜態資料表, 可儲存可能的通話優先順序清單, 例如「緊急」、「緊急」或「標準」。
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192904"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b8738-103">商務用 Skype Server 2015 中的 CallPriorities 表格</span><span class="sxs-lookup"><span data-stu-id="b8738-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b8738-104">CallPriorities 資料表是一個靜態資料表, 可儲存可能的通話優先順序清單, 例如「緊急」、「緊急」或「標準」。</span><span class="sxs-lookup"><span data-stu-id="b8738-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="b8738-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="b8738-105">**Column**</span></span>|<span data-ttu-id="b8738-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="b8738-106">**Data Type**</span></span>|<span data-ttu-id="b8738-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="b8738-107">**Key/Index**</span></span>|<span data-ttu-id="b8738-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="b8738-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b8738-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="b8738-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="b8738-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="b8738-110">tinyint</span></span>  <br/> |<span data-ttu-id="b8738-111">首選</span><span class="sxs-lookup"><span data-stu-id="b8738-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="b8738-112">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="b8738-112">**Priority**</span></span> <br/> |<span data-ttu-id="b8738-113">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b8738-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="b8738-114">允許的值:</span><span class="sxs-lookup"><span data-stu-id="b8738-114">Allowed values:</span></span> <br/>  <span data-ttu-id="b8738-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="b8738-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="b8738-116">1-非緊急</span><span class="sxs-lookup"><span data-stu-id="b8738-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="b8738-117">2-標準</span><span class="sxs-lookup"><span data-stu-id="b8738-117">2 - Normal</span></span> <br/>  <span data-ttu-id="b8738-118">3-緊急</span><span class="sxs-lookup"><span data-stu-id="b8738-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="b8738-119">4-緊急</span><span class="sxs-lookup"><span data-stu-id="b8738-119">4 - Emergency</span></span> <br/> |
   


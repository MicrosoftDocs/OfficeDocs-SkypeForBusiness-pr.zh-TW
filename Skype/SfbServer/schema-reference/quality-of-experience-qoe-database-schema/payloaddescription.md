---
title: PayloadDescription 表格
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
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription 資料表是支援資料表。 每個記錄代表一個在音訊或視頻會話中使用的編解碼器。
ms.openlocfilehash: 3a5719d7fbfe23eb8c1457565a36df0a02617fde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807491"
---
# <a name="payloaddescription-table"></a><span data-ttu-id="bc2ca-104">PayloadDescription 表格</span><span class="sxs-lookup"><span data-stu-id="bc2ca-104">PayloadDescription table</span></span>
 
<span data-ttu-id="bc2ca-105">PayloadDescription 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="bc2ca-105">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="bc2ca-106">每個記錄代表一個在音訊或視頻會話中使用的編解碼器。</span><span class="sxs-lookup"><span data-stu-id="bc2ca-106">Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="bc2ca-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="bc2ca-107">**Column**</span></span>|<span data-ttu-id="bc2ca-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bc2ca-108">**Data Type**</span></span>|<span data-ttu-id="bc2ca-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="bc2ca-109">**Key/Index**</span></span>|<span data-ttu-id="bc2ca-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="bc2ca-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bc2ca-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="bc2ca-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="bc2ca-112">int</span><span class="sxs-lookup"><span data-stu-id="bc2ca-112">int</span></span>  <br/> |<span data-ttu-id="bc2ca-113">首選</span><span class="sxs-lookup"><span data-stu-id="bc2ca-113">Primary</span></span>  <br/> |<span data-ttu-id="bc2ca-114">識別編解碼器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="bc2ca-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="bc2ca-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="bc2ca-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="bc2ca-116">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="bc2ca-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bc2ca-117">唯一</span><span class="sxs-lookup"><span data-stu-id="bc2ca-117">Unique</span></span>  <br/> |<span data-ttu-id="bc2ca-118">編解碼器名稱。</span><span class="sxs-lookup"><span data-stu-id="bc2ca-118">Codec name.</span></span>  <br/> |
   


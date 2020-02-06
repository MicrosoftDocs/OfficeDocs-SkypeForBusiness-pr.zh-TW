---
title: QoE 檢視詳細資料
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: '[視圖] 涵蓋從 QoE SQL 資料庫傳回資料最常見的案例。 它是用來建立自訂報表的建議視圖，而不是直接存取資料庫資料表;這是因為視圖更可能會維持與未來版本的向後相容性。'
ms.openlocfilehash: d207c2cff86c398fed62023b30d193e974cbca7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807171"
---
# <a name="qoe-view-details"></a><span data-ttu-id="5f315-104">QoE 檢視詳細資料</span><span class="sxs-lookup"><span data-stu-id="5f315-104">QoE view details</span></span>
 
<span data-ttu-id="5f315-105">[視圖] 涵蓋從 QoE SQL 資料庫傳回資料最常見的案例。</span><span class="sxs-lookup"><span data-stu-id="5f315-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="5f315-106">它是用來建立自訂報表的建議視圖，而不是直接存取資料庫資料表;這是因為視圖更可能會維持與未來版本的向後相容性。</span><span class="sxs-lookup"><span data-stu-id="5f315-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="5f315-107">**[視圖名稱]**</span><span class="sxs-lookup"><span data-stu-id="5f315-107">**View Name**</span></span>|<span data-ttu-id="5f315-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="5f315-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5f315-109">AudioStreamDetail 視圖</span><span class="sxs-lookup"><span data-stu-id="5f315-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="5f315-110">儲存資料庫中每個音訊資料流程的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5f315-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="5f315-111">MediaLine 視圖</span><span class="sxs-lookup"><span data-stu-id="5f315-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="5f315-112">儲存資料庫中每個媒體線的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5f315-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="5f315-113">一個音訊會話通常包含一個音訊媒體線。</span><span class="sxs-lookup"><span data-stu-id="5f315-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="5f315-114">一個音訊與影片（A/V）會話通常包含一個音訊媒體線和一個影片媒體線;不過，如果使用會議裝置或使用圖庫視圖，該會話可能會包含兩個視頻媒體線。</span><span class="sxs-lookup"><span data-stu-id="5f315-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="5f315-115">NetworkConfigurationSettings 視圖</span><span class="sxs-lookup"><span data-stu-id="5f315-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="5f315-116">儲存網路設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5f315-116">Stores information about the network configuration.</span></span>  <br/> |
|<span data-ttu-id="5f315-117">[[會話] 視圖](session-0.md)</span><span class="sxs-lookup"><span data-stu-id="5f315-117">[Session view](session-0.md)</span></span> <br/> |<span data-ttu-id="5f315-118">儲存在資料庫中有記錄的會話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5f315-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="5f315-119">UserAgent 視圖</span><span class="sxs-lookup"><span data-stu-id="5f315-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="5f315-120">儲存在資料庫中有記錄的會話中所涉及之使用者代理程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5f315-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="5f315-121">VideoStreamDetail 視圖</span><span class="sxs-lookup"><span data-stu-id="5f315-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="5f315-122">儲存資料庫中每個影片資料流程的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5f315-122">Stores information about each video stream in the database.</span></span>  <br/> |
   


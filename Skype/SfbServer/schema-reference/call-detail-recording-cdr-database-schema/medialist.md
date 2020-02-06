---
title: MediaList 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 資料表是一個靜態資料表，可儲存各種媒體類型的清單。
ms.openlocfilehash: 7742baf17240ca810268721c0e47e37f17e555cd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815031"
---
# <a name="medialist-table"></a><span data-ttu-id="775f5-103">MediaList 表格</span><span class="sxs-lookup"><span data-stu-id="775f5-103">MediaList table</span></span>
 
<span data-ttu-id="775f5-104">MediaList 資料表是一個靜態資料表，可儲存各種媒體類型的清單。</span><span class="sxs-lookup"><span data-stu-id="775f5-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="775f5-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="775f5-105">**Column**</span></span>|<span data-ttu-id="775f5-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="775f5-106">**Data Type**</span></span>|<span data-ttu-id="775f5-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="775f5-107">**Key/Index**</span></span>|<span data-ttu-id="775f5-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="775f5-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="775f5-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="775f5-109">**MediaId**</span></span> <br/> |<span data-ttu-id="775f5-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="775f5-110">tinyint</span></span>  <br/> |<span data-ttu-id="775f5-111">首選</span><span class="sxs-lookup"><span data-stu-id="775f5-111">Primary</span></span>  <br/> |<span data-ttu-id="775f5-112">值：1-7</span><span class="sxs-lookup"><span data-stu-id="775f5-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="775f5-113">**媒體**</span><span class="sxs-lookup"><span data-stu-id="775f5-113">**Media**</span></span> <br/> |<span data-ttu-id="775f5-114">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="775f5-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="775f5-115">MediaID 和媒體值的靜態對應：</span><span class="sxs-lookup"><span data-stu-id="775f5-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="775f5-116">1--IM</span><span class="sxs-lookup"><span data-stu-id="775f5-116">1 -- IM</span></span> <br/>  <span data-ttu-id="775f5-117">2-檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="775f5-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="775f5-118">3-遠端協助</span><span class="sxs-lookup"><span data-stu-id="775f5-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="775f5-119">4-應用程式共用</span><span class="sxs-lookup"><span data-stu-id="775f5-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="775f5-120">5--音訊</span><span class="sxs-lookup"><span data-stu-id="775f5-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="775f5-121">6--影片</span><span class="sxs-lookup"><span data-stu-id="775f5-121">6 -- Video</span></span> <br/>  <span data-ttu-id="775f5-122">7-App 邀請</span><span class="sxs-lookup"><span data-stu-id="775f5-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="775f5-123">如果您要嘗試判斷 LcsCDR 中的值的模態類型，則需要使用下列聯結程式碼片段：</span><span class="sxs-lookup"><span data-stu-id="775f5-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```

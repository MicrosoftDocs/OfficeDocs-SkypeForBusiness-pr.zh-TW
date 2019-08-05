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
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 資料表是一個靜態資料表, 可儲存各種媒體類型的清單。
ms.openlocfilehash: 308a9eee57089a02b8e3ff9924e0d9d34162f33e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192823"
---
# <a name="medialist-table"></a><span data-ttu-id="bca65-103">MediaList 表格</span><span class="sxs-lookup"><span data-stu-id="bca65-103">MediaList table</span></span>
 
<span data-ttu-id="bca65-104">MediaList 資料表是一個靜態資料表, 可儲存各種媒體類型的清單。</span><span class="sxs-lookup"><span data-stu-id="bca65-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="bca65-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="bca65-105">**Column**</span></span>|<span data-ttu-id="bca65-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="bca65-106">**Data Type**</span></span>|<span data-ttu-id="bca65-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="bca65-107">**Key/Index**</span></span>|<span data-ttu-id="bca65-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="bca65-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bca65-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="bca65-109">**MediaId**</span></span> <br/> |<span data-ttu-id="bca65-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="bca65-110">tinyint</span></span>  <br/> |<span data-ttu-id="bca65-111">首選</span><span class="sxs-lookup"><span data-stu-id="bca65-111">Primary</span></span>  <br/> |<span data-ttu-id="bca65-112">值: 1-7</span><span class="sxs-lookup"><span data-stu-id="bca65-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="bca65-113">**媒體**</span><span class="sxs-lookup"><span data-stu-id="bca65-113">**Media**</span></span> <br/> |<span data-ttu-id="bca65-114">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bca65-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="bca65-115">MediaID 和媒體值的靜態對應:</span><span class="sxs-lookup"><span data-stu-id="bca65-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="bca65-116">1--IM</span><span class="sxs-lookup"><span data-stu-id="bca65-116">1 -- IM</span></span> <br/>  <span data-ttu-id="bca65-117">2-檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="bca65-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="bca65-118">3-遠端協助</span><span class="sxs-lookup"><span data-stu-id="bca65-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="bca65-119">4-應用程式共用</span><span class="sxs-lookup"><span data-stu-id="bca65-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="bca65-120">5--音訊</span><span class="sxs-lookup"><span data-stu-id="bca65-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="bca65-121">6--影片</span><span class="sxs-lookup"><span data-stu-id="bca65-121">6 -- Video</span></span> <br/>  <span data-ttu-id="bca65-122">7-App 邀請</span><span class="sxs-lookup"><span data-stu-id="bca65-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="bca65-123">如果您要嘗試判斷 LcsCDR 中的值的模態類型, 則需要使用下列聯結程式碼片段:</span><span class="sxs-lookup"><span data-stu-id="bca65-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
